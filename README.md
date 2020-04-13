//"請助教下載GitHub版本評分"
// 10727139 蘇崇傑    10727150 廖泓閔

# include <stdio.h>
# include <stdlib.h>
# include <string.h>
# include <iostream>
# include <vector>
# include <algorithm>
# include <sstream>
# include <fstream>
# include <io.h>
# include <cmath>

using namespace std ;

typedef char Str100[100] ;

// ==================================    global function head    =======================================

/*
 * to change type String to type integer
 */

int ChangeStringToInteger( string temp ) ;

// ===============================    class GraduaionInfo    =================================

class GraduationInfo {

	private :

		int number ;
		string schoolName ;
		string majorName ;
		string dayOrNight ;
		string rank ;
		int numOfGraduations ;

	public :

		/*
		 * to set number
		 */

		void SetNumber( int temp ) ;

		/*
		 * to get number
		 */

		int GetNumber() ;

		/*
		 * to set schoolName
		 */

		void SetSchoolName( string tempString ) ;

		/*
		 * to get schoolName
		 */

		string GetSchoolName() ;

		/*
		 * to set majorName
		 */

		void SetMajorName( string tempString ) ;

		/*
		 * to get majorName
		 */

		string GetMajorName() ;

		/*
		 * to set dayOrNight
		 */

		void SetDayOrNight( string tempString ) ;

		/*
		 * to get dayOrNight
		 */

		string GetDayOrNight() ;

		/*
		 * to set rank
		 */

		void SetRank( string tempString ) ;

		/*
		 * to get rank
		 */

		string GetRank() ;

		/*
		 * to set numOfGraduations
		 */

		void SetNumOfGraduations( int temp ) ;

		/*
		 * to get numOfGraduaitons
		 */

		int GetNumOfGraduations() ;

} ; // GraduationInfo

// ===============================    class AVL_TreeInfo    =================================

class AVL_TreeInfo {

	private :

	public :

		vector<GraduationInfo> graduation ;

		AVL_TreeInfo *left ;
		AVL_TreeInfo *right ;

		/*
		 * the constructor of AVL_TreeInfo
		 */

		AVL_TreeInfo( GraduationInfo temp ) ;

		/*
		 * to print all the informations in graduation
		 */

		void PrintInformation() ;

} ; // AVL_TreeInfo

typedef AVL_TreeInfo *AVL_TreeInfoPtr ;

// ===============================    class AVL_Tree    =================================

class AVL_Tree {

	private :

		AVL_TreeInfoPtr root ;
		int numOfNodes ;

	public :

		/*
		 * the constructor of AVL_Tree
		 */

		AVL_Tree() ;

		/*
		 * initialize tree pointer
		 */

		void InitTheTree() ;

		/*
		 * clear all the nodes and return memory
		 */

		void DeleteAll( AVL_TreeInfoPtr temp ) ;

		/*
		 * to count the treeHeight
		 */

		int CountTreeHeight( AVL_TreeInfoPtr temp ) ;

		/*
		 * to count the balance factor
		 */

		int CountBalanceFactor( AVL_TreeInfoPtr temp ) ;

		/*
		 * the balance factor is 2 and left child's balance factor is 1
		 */

		AVL_TreeInfoPtr LL( AVL_TreeInfoPtr temp ) ;

		/*
		 * the balance factor is 2 and left child's balance factor is -1
		 */

		AVL_TreeInfoPtr LR( AVL_TreeInfoPtr temp ) ;

		/*
		 * the balance factor is -2 and left child's balance factor is -1
		 */

		AVL_TreeInfoPtr RR( AVL_TreeInfoPtr temp ) ;

		/*
		 * the balance factor is -2 and left child's balance factor is 1
		 */

		AVL_TreeInfoPtr RL( AVL_TreeInfoPtr temp ) ;

		/*
		 * to balance the tree
		 */

		AVL_TreeInfoPtr Rotate( AVL_TreeInfoPtr temp ) ;

		/*
		 * insert node to AVL tree
		 */

		AVL_TreeInfoPtr Insert( AVL_TreeInfoPtr walk, GraduationInfo temp ) ;

		/*
		 * to create a AVL tree
		 */

		void CreateTree( Str100 filePath ) ;

		/*
		 * to print the height of the tree
		 */

		void PrintTreeHeight() ;

		/*
		 * to print the num of nodes
		 */

		void PrintNumOfNodes() ;

		/*
		 * to get a pointer point to root
		 */

		AVL_TreeInfoPtr GetRoot() ;

} ; // AVL_Tree

// ===============================    main    =================================

int main() {

	Str100 filePath = {0} ;
	Str100 fileNumberChar = {0} ;
	Str100 command = {0} ;
	AVL_Tree tree ;
	bool createdTree = false ;

	cout << "##########################################" << endl ;
	cout << "##########################################" << endl ;
	cout << "##### ------------------------------ #####" << endl ;
	cout << "#####|*  Welcome  to  create tree  *|#####" << endl ;
	cout << "##### ------------------------------ #####" << endl ;
	cout << "##########################################" << endl ;
	cout << "##########################################" << endl ;
	cout << endl ;
	cout << endl ;
	cout << "----------------------------------------------------------------------" << endl ;
	cout << "Please input a command to choose mode.                                |" << endl ;
	cout << endl ;
	cout << "If you want to create 23 tree please input \"1\".                        |" << endl ;
	cout << endl ;
	cout << "If you want to create AVL tree please input \"2\".                        |" << endl ;
	cout << endl ;
	cout << "If you want to exit this program please input \"0\".                    |" << endl ;
	cout << "----------------------------------------------------------------------" ;
	cout << endl ;
	cout << "Input a command : " ;
	cin >> command ;

	while ( strcmp( command, "0" ) != 0  ) {

		while ( strcmp( command, "0" ) != 0 && strcmp( command, "1" ) != 0 &&
						strcmp( command, "2" ) != 0 ) {

			cout << endl ;
			cout << "Illegel command please try again." << endl ;
			cout << "Input a command : " ;
			cin >> command ;

		} // while

		if ( strcmp( command, "0" ) == 0 )
			break ;

		// ↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓		mission 1		↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓

		if ( strcmp( command, "1" ) == 0 ) {

		} // if

		// ↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓		mission 2		↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓

		else if ( strcmp( command, "2" ) == 0 ) {

			cout << "You choosed the first mode, if you want to exit, please input \"..\"" << endl ;
			cout << endl ;
			cout << "Please input the file number(e.g. 201, 202...) : " ;

			cin >> fileNumberChar ;

			if ( strcmp( fileNumberChar, ".." ) == 0 )
				;

			else {

				strcpy( filePath, "input" ) ;
				strcat( filePath, fileNumberChar ) ;
				strcat( filePath, ".txt" ) ;

				while ( access( filePath, 0 ) < 0 ) {

					cout << endl << "This file does not exist, please try again." << endl ;
					cout << "if you want to exit, please input \"..\"" << endl ;
					cout  << endl << "Please input the file number(e.g. 201, 202...) : " ;

					strcpy( filePath, "input" ) ;
					cin >> fileNumberChar ;

					if ( strcmp( fileNumberChar, ".." ) == 0 )
						break ;

					strcat( filePath, fileNumberChar ) ;
					strcat( filePath, ".txt" ) ;

				} // while

				if ( strcmp( fileNumberChar, ".." ) == 0 )
					;

				else {

					if ( createdTree ) {

						tree.DeleteAll( tree.GetRoot() ) ;
						tree.InitTheTree() ;

					} // if

					tree.CreateTree( filePath ) ;
					tree.PrintTreeHeight() ;
					cout << endl ;
					tree.PrintNumOfNodes() ;
					tree.GetRoot()->PrintInformation() ;

					createdTree = true ;

				} // else

			} // else

		} // else if

		cout << endl ;
		cout << endl ;
		cout << "########################################" << endl ;
		cout << "########################################" << endl ;
		cout << "##### ---------------------------- #####" << endl ;
		cout << "#####|*  Welcome  to  data sort  *|#####" << endl ;
		cout << "##### ---------------------------- #####" << endl ;
		cout << "########################################" << endl ;
		cout << "########################################" << endl ;
		cout << endl ;
		cout << endl ;
		cout << "----------------------------------------------------------------------" << endl ;
		cout << "Please input a command to choose mode.                                |" << endl ;
		cout << endl ;
		cout << "If you want to create 23 tree please input \"1\".                        |" << endl ;
		cout << endl ;
		cout << "If you want to create AVL tree please input \"2\".                        |" << endl ;
		cout << endl ;
		cout << "If you want to exit this program please input \"0\".                    |" << endl ;
		cout << "----------------------------------------------------------------------" ;
		cout << endl ;
		cout << "Input a command : " ;
		cin >> command ;

	} // while

	cout << endl ;

	cout << "Thank you for using this program, good bye." ;

} // main()

// ==================================    the implement of method in global    =======================================

/*
 * to change type String to type integer
 */

int ChangeStringToInteger( string temp ) {

	int num = 0 ;

	stringstream stringNum ;

	stringNum << temp ;
	stringNum >> num ;

	return num ;

} // ChangeStringToInteger()

// ===============================    the implement of method in GraduaionInfo    =================================

/*
 * to set number
 */

void GraduationInfo::SetNumber( int temp ) {

	number = temp ;

} // GraduationInfo::SetNumber()

/*
 * to get number
 */

int GraduationInfo::GetNumber() {

	return number ;

} // GraduationInfo::GetNumber()

/*
 * to set schoolName
 */

void GraduationInfo::SetSchoolName( string tempString ) {

	schoolName = tempString ;

} // GraduationInfo::SetSchoolName()

/*
 * to get schoolName
 */

string GraduationInfo::GetSchoolName() {

	return schoolName ;

} // GraduationInfo::GetSchoolName()

/*
 * to set majorName
 */

void GraduationInfo::SetMajorName( string tempString ) {

	majorName = tempString ;

} // GraduationInfo::SetMajorName()

/*
 * to get majorName
 */

string GraduationInfo::GetMajorName() {

	return majorName ;

} // GraduationInfo::GetMajorName()

/*
 * to set dayOrNight
 */

void GraduationInfo::SetDayOrNight( string tempString ) {

	dayOrNight = tempString ;

} // GraduationInfo::SetDayOrNight()

/*
 * to get dayOrNight
 */

string GraduationInfo::GetDayOrNight() {

	return dayOrNight ;

} // GraduationInfo::GetDayOrNight()

/*
 * to set rank
 */

void GraduationInfo::SetRank( string tempString ) {

	rank = tempString ;

} // GraduationInfo::SetRank()

/*
 * to get rank
 */

string GraduationInfo::GetRank() {

	return rank ;

} // GraduationInfo::GetRank()

/*
 * to set numOfGraduations
 */

void GraduationInfo::SetNumOfGraduations( int temp ) {

	numOfGraduations = temp ;

} // GraduationInfo::SetNumOfGraduation()

/*
 * to get numOfGraduations
 */

int GraduationInfo::GetNumOfGraduations() {

	return numOfGraduations ;

} // GraduationInfo::GetNumOfGraduation()

// ===============================    the implement of method in AVL_TreeInfo    =================================

/*
 * the constructor of AVL_TreeInfo
 */

AVL_TreeInfo::AVL_TreeInfo( GraduationInfo temp ) {

	graduation.push_back( temp ) ;
	left = NULL ;
	right = NULL ;

} // AVL_TreeInfo::AVL_TreeInfo

/*
 * to print all the informations in graduation
 */

void AVL_TreeInfo::PrintInformation() {

	for ( int i = 0 ; i < graduation.size() ; i++ ) {

		cout << i + 1 << " : [" << graduation[i].GetNumber() << "] " ;
		cout << graduation[i].GetSchoolName() << ",	"
				 << graduation[i].GetMajorName() << ",	"
				 << graduation[i].GetDayOrNight() << ",	"
				 << graduation[i].GetRank() << ",	"
				 << graduation[i].GetNumOfGraduations() << endl ;

	} // for

} // AVL_TreeInfo::PrintInformation()

// ===============================    the implement of method in AVL_Tree    =================================

/*
 * the constructor of AVL_Tree
 */

AVL_Tree::AVL_Tree() {

	root = NULL ;
	numOfNodes = 0 ;

} // AVL_Tree::AVL_Tree()

/*
 * initialize tree pointer
 */

void AVL_Tree::InitTheTree() {

	numOfNodes = 0 ;
	root = NULL ;

} // AVL_Tree::InitTheTree()

/*
 * clear all the nodes and return memory
 */

void AVL_Tree::DeleteAll( AVL_TreeInfoPtr temp ) {

	if ( temp != NULL ) {

		DeleteAll( temp->left ) ;
		DeleteAll( temp->right ) ;

		delete temp ;

		temp = NULL ;

	} // if

} // AVL_Tree::DeleteAll()

/*
 * to count the treeHeight
 */

int AVL_Tree::CountTreeHeight( AVL_TreeInfoPtr temp ) {

	if ( temp == NULL )
		return 0 ;

	int left = CountTreeHeight( temp->left ) ;
	int right = CountTreeHeight( temp->right ) ;

	if ( left > right )
		return left + 1 ;

	else
		return right + 1 ;

} // AVL_Tree::CountTreeHeight()
/*
 * to count the balance factor
 */

int AVL_Tree::CountBalanceFactor( AVL_TreeInfoPtr temp ) {

	int leftHeight = CountTreeHeight( temp->left ) ;
	int rightHeight = CountTreeHeight( temp->right ) ;

	return leftHeight - rightHeight ;

} // int AVL_Tree::CountBalanceFactor()

/*
 * the balance factor is 2 and left child's balance factor is 1
 */

AVL_TreeInfoPtr AVL_Tree::LL( AVL_TreeInfoPtr temp ) {

	AVL_TreeInfoPtr walk = temp->left ;
	temp->left = walk->right ;
	walk->right = temp ;

	return walk ;

} // AVL_Tree::LL()

/*
 * the balance factor is -2 and left child's balance factor is -1
 */

AVL_TreeInfoPtr AVL_Tree::RR( AVL_TreeInfoPtr temp ) {

	AVL_TreeInfoPtr walk = temp->right ;
	temp->right = walk->left ;
	walk->left = temp ;

	return walk ;

} // AVL_Tree::RR()

/*
 * the balance factor is 2 and left child's balance factor is -1
 */

AVL_TreeInfoPtr AVL_Tree::LR( AVL_TreeInfoPtr temp ) {

	temp->left = RR( temp->left ) ;
	return LL( temp ) ;

} // AVL_Tree::LR()

/*
 * the balance factor is -2 and left child's balance factor is 1
 */

AVL_TreeInfoPtr AVL_Tree::RL( AVL_TreeInfoPtr temp ) {

	temp->right = LL( temp->right ) ;
	return RR( temp ) ;

} // AVL_Tree::RL()

/*
 * to balance the tree
 */

AVL_TreeInfoPtr AVL_Tree::Rotate( AVL_TreeInfoPtr temp ) {

	int balanceFactor = CountBalanceFactor( temp ) ;

	if ( balanceFactor == 2 ) {

		if ( CountBalanceFactor( temp->left ) == 1 ||
			 CountBalanceFactor( temp->left ) == 0 )
			temp = LL( temp ) ;

		else
			temp = LR( temp ) ;

	} // if

	else if ( balanceFactor == -2 ) {

		if ( CountBalanceFactor( temp->right ) == -1 ||
			 CountBalanceFactor( temp->right ) == 0 )
			temp = RR( temp ) ;

		else
			temp = RL( temp ) ;

	} // else if

	return temp ;

} // AVL_Tree::Rotate()

/*
 * insert node to AVL tree
 */

AVL_TreeInfoPtr AVL_Tree::Insert( AVL_TreeInfoPtr walk, GraduationInfo temp ) {


	if ( walk == NULL ) {

		walk = new AVL_TreeInfo( temp ) ;
		numOfNodes++ ;
		return walk ;

	} // if

	else if ( walk->graduation[0].GetNumOfGraduations() ==
						temp.GetNumOfGraduations() ) {

		walk->graduation.push_back( temp ) ;

		return walk ;

	} // else if

	else if ( walk->graduation[0].GetNumOfGraduations() <
						temp.GetNumOfGraduations() ) {

		walk->right = Insert( walk->right, temp ) ;

	} // else if

	else {

		walk->left = Insert( walk->left, temp ) ;

	} // else

	walk = Rotate( walk ) ;

	return walk ;

} // AVL_Tree::Insert()

/*
 * to create a AVL tree
 */

void AVL_Tree::CreateTree( Str100 filePath ) {

	GraduationInfo temp ;
	AVL_TreeInfoPtr it = NULL ;

	int tempNum = 0 ;
	int number = 1 ;

	string tempString ;
	tempString.clear() ;

	ifstream input( filePath, ios::in ) ;

	for ( int i = 0 ; i < 3 ; i++ )
		getline( input, tempString ) ;

	while ( getline( input, tempString, '\t' ) ) {
		// school code

		temp.SetNumber( number ) ;

		getline( input, tempString, '\t' ) ; // school Name
		temp.SetSchoolName( tempString ) ;

		getline( input, tempString, '\t' ) ; // major code

		getline( input, tempString, '\t' ) ; // major name
		temp.SetMajorName( tempString ) ;

		getline( input, tempString, '\t' ) ; // degree
		temp.SetDayOrNight( tempString ) ;

		getline( input, tempString, '\t' ) ; // rank
		temp.SetRank( tempString ) ;

		getline( input, tempString, '\t' ) ; // how many students

		getline( input, tempString, '\t' ) ; // how many teachers

		getline( input, tempString, '\t' ) ; // how many graduations in last year
		tempNum = ChangeStringToInteger( tempString ) ;
		temp.SetNumOfGraduations( tempNum ) ;

		getline( input, tempString, '\t' ) ; // city

		getline( input, tempString, '\n' ) ; // system

		if ( root == NULL )
			root = Insert( root, temp ) ;

		else {

			it = root ;
			root = Insert( it, temp ) ;

		} // else

		number++ ;

	} // while

	input.close() ;

} // AVL_Tree::CreateTree()

/*
 * to print the height of the tree
 */

void AVL_Tree::PrintTreeHeight() {

	cout << "Tree height = " << CountTreeHeight( root ) ;

} // AVL_Tree::PrintTreeHeight()

/*
 * to print the num of nodes
 */

void AVL_Tree::PrintNumOfNodes() {

	cout << "Number of nodes = " << numOfNodes << endl ;

} // AVL_Tree::PrintNumOfNodes()

/*
 * to get a pointer point to root
 */

AVL_TreeInfoPtr AVL_Tree::GetRoot() {

	return root ;

} // AVL_Tree::GetRoot()

# System.Windows.Input.CommandConverter::GetKnownCommand

- ea: `0x6c210`
- end: `0x6dda2`
- name: `System.Windows.Input.CommandConverter::GetKnownCommand`
- size: `7058`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, broker_com_uri`

## callers

- `0x6c060`

## callees

- `0x6c210`
- `0xd0660`
- `0xd0670`
- `0xd0680`
- `0xd0690`
- `0xd06a0`
- `0xd06b0`
- `0xd06c0`
- `0xd06d0`
- `0xd06e0`
- `0xd06f0`
- `0xd0700`
- `0xd0710`
- `0xd0720`
- `0xd0730`
- `0xd0740`
- `0xd0750`
- `0xd0760`
- `0xd0770`
- `0xd0780`
- `0xd0790`
- `0xd07a0`
- `0xd07b0`
- `0xd07c0`
- `0xd07d0`
- `0xd07e0`
- `0xd07f0`
- `0xd0800`
- `0xd0810`
- `0xd0820`
- `0xd0830`
- `0xd0840`
- `0xd0850`
- `0xd0860`
- `0xd0870`
- `0xd0880`
- `0xd0890`
- `0xd08a0`
- `0xd08b0`
- `0xd08c0`
- `0xd08d0`
- `0xd08e0`
- `0xd08f0`
- `0xd0900`
- `0xd0910`
- `0xd0920`
- `0xd0930`
- `0xd0940`
- `0xd0950`
- `0xd0960`

## string_xrefs

- `0x6c709`: `Delete`
- `0x6d254`: `Delete`
- `0x6c733`: `Replace`
- `0x6c86e`: `NotACommand`
- `0x6cb88`: `MoveLeft`
- `0x6cb9d`: `MoveRight`
- `0x6cbb2`: `MoveUp`
- `0x6cbc7`: `MoveDown`
- `0x6cc30`: `MoveToHome`
- `0x6cc45`: `MoveToEnd`
- `0x6cc5a`: `MoveToPageUp`
- `0x6cc6f`: `MoveToPageDown`
- `0x6ccd8`: `MoveFocusUp`
- `0x6cced`: `MoveFocusDown`
- `0x6cd02`: `MoveFocusBack`
- `0x6cd17`: `MoveFocusForward`
- `0x6cd2c`: `MoveFocusPageUp`
- `0x6cd41`: `MoveFocusPageDown`
- `0x6d27e`: `DeleteNextWord`
- `0x6d293`: `DeletePreviousWord`
- `0x6d2fc`: `MoveRightByCharacter`
- `0x6d311`: `MoveLeftByCharacter`
- `0x6d326`: `MoveRightByWord`
- `0x6d33b`: `MoveLeftByWord`
- `0x6d350`: `MoveDownByLine`
- `0x6d365`: `MoveUpByLine`
- `0x6d37a`: `MoveDownByParagraph`
- `0x6d38f`: `MoveUpByParagraph`
- `0x6d3a4`: `MoveDownByPage`
- `0x6d3b9`: `MoveUpByPage`
- `0x6d3ce`: `MoveToLineStart`
- `0x6d3e3`: `MoveToLineEnd`
- `0x6d3f8`: `MoveToDocumentStart`
- `0x6d40d`: `MoveToDocumentEnd`

## pseudocode

```c

```

## disassembly

```asm
0x6c210  ldnull
0x6c211  stloc.0
0x6c212  ldc.i4.0
0x6c213  stloc.1
0x6c214  ldarg.1
0x6c215  ldnull
0x6c216  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c21b  brfalse.s loc_6C21F
0x6c21d  ldc.i4.1
0x6c21e  stloc.1
0x6c21f  ldarg.1
0x6c220  ldtoken  [PresentationCore]System.Windows.Input.NavigationCommands
0x6c225  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c22a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c22f  brtrue.s loc_6C23C
0x6c231  ldloc.0
0x6c232  ldnull
0x6c233  ceq
0x6c235  ldloc.1
0x6c236  and
0x6c237  brfalse  loc_6C51B
0x6c23c  ldarg.0
0x6c23d  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6c242  stloc.2
0x6c243  ldloc.2
0x6c244  ldc.i4   0x6AA01656
0x6c249  bgt.un   loc_6C2D2
0x6c24e  ldloc.2
0x6c24f  ldc.i4   0x3751EB2C
0x6c254  bgt.un.s loc_6C294
0x6c256  ldloc.2
0x6c257  ldc.i4   0x12DDD2B3
0x6c25c  bgt.un.s loc_6C279
0x6c25e  ldloc.2
0x6c25f  ldc.i4   0x815AAD4
0x6c264  beq      loc_6C3A7
0x6c269  ldloc.2
0x6c26a  ldc.i4   0x12DDD2B3
0x6c26f  beq      loc_6C43A
0x6c274  br       loc_6C51B
0x6c279  ldloc.2
0x6c27a  ldc.i4   0x37252DB1
0x6c27f  beq      loc_6C48E
0x6c284  ldloc.2
0x6c285  ldc.i4   0x3751EB2C
0x6c28a  beq      loc_6C37D
0x6c28f  br       loc_6C51B
0x6c294  ldloc.2
0x6c295  ldc.i4   0x5412DE7F
0x6c29a  bgt.un.s loc_6C2B7
0x6c29c  ldloc.2
0x6c29d  ldc.i4   0x45267154
0x6c2a2  beq      loc_6C368
0x6c2a7  ldloc.2
0x6c2a8  ldc.i4   0x5412DE7F
0x6c2ad  beq      loc_6C392
0x6c2b2  br       loc_6C51B
0x6c2b7  ldloc.2
0x6c2b8  ldc.i4   0x62399752
0x6c2bd  beq      loc_6C410
0x6c2c2  ldloc.2
0x6c2c3  ldc.i4   0x6AA01656
0x6c2c8  beq      loc_6C3FB
0x6c2cd  br       loc_6C51B
0x6c2d2  ldloc.2
0x6c2d3  ldc.i4   0xBC16163A
0x6c2d8  bgt.un.s loc_6C318
0x6c2da  ldloc.2
0x6c2db  ldc.i4   0x9E090D73
0x6c2e0  bgt.un.s loc_6C2FD
0x6c2e2  ldloc.2
0x6c2e3  ldc.i4   0x7C2C53BA
0x6c2e8  beq      loc_6C3BC
0x6c2ed  ldloc.2
0x6c2ee  ldc.i4   0x9E090D73
0x6c2f3  beq      loc_6C425
0x6c2f8  br       loc_6C51B
0x6c2fd  ldloc.2
0x6c2fe  ldc.i4   0xB25ACA1A
0x6c303  beq      loc_6C3E6
0x6c308  ldloc.2
0x6c309  ldc.i4   0xBC16163A
0x6c30e  beq      loc_6C464
0x6c313  br       loc_6C51B
0x6c318  ldloc.2
0x6c319  ldc.i4   0xCB46F0F0
0x6c31e  bgt.un.s loc_6C338
0x6c320  ldloc.2
0x6c321  ldc.i4   0xC646A2C9
0x6c326  beq      loc_6C3D1
0x6c32b  ldloc.2
0x6c32c  ldc.i4   0xCB46F0F0
0x6c331  beq.s    loc_6C353
0x6c333  br       loc_6C51B
0x6c338  ldloc.2
0x6c339  ldc.i4   0xE3967A42
0x6c33e  beq      loc_6C44F
0x6c343  ldloc.2
0x6c344  ldc.i4   0xEFDF586D
0x6c349  beq      loc_6C479
0x6c34e  br       loc_6C51B
0x6c353  ldarg.0
0x6c354  ldstr    aBrowseback// "BrowseBack"
0x6c359  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c35e  brtrue   loc_6C49D
0x6c363  br       loc_6C51B
0x6c368  ldarg.0
0x6c369  ldstr    aBrowseforward// "BrowseForward"
0x6c36e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c373  brtrue   loc_6C4A5
0x6c378  br       loc_6C51B
0x6c37d  ldarg.0
0x6c37e  ldstr    aBrowsehome// "BrowseHome"
0x6c383  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c388  brtrue   loc_6C4AD
0x6c38d  br       loc_6C51B
0x6c392  ldarg.0
0x6c393  ldstr    aBrowsestop// "BrowseStop"
0x6c398  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c39d  brtrue   loc_6C4B5
0x6c3a2  br       loc_6C51B
0x6c3a7  ldarg.0
0x6c3a8  ldstr    aRefresh// "Refresh"
0x6c3ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c3b2  brtrue   loc_6C4BD
0x6c3b7  br       loc_6C51B
0x6c3bc  ldarg.0
0x6c3bd  ldstr    aFavorites// "Favorites"
0x6c3c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c3c7  brtrue   loc_6C4C5
0x6c3cc  br       loc_6C51B
0x6c3d1  ldarg.0
0x6c3d2  ldstr    aSearch// "Search"
0x6c3d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c3dc  brtrue   loc_6C4CD
0x6c3e1  br       loc_6C51B
0x6c3e6  ldarg.0
0x6c3e7  ldstr    aIncreasezoom// "IncreaseZoom"
0x6c3ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c3f1  brtrue   loc_6C4D5
0x6c3f6  br       loc_6C51B
0x6c3fb  ldarg.0
0x6c3fc  ldstr    aDecreasezoom// "DecreaseZoom"
0x6c401  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c406  brtrue   loc_6C4DD
0x6c40b  br       loc_6C51B
0x6c410  ldarg.0
0x6c411  ldstr    aZoom// "Zoom"
0x6c416  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c41b  brtrue   loc_6C4E5
0x6c420  br       loc_6C51B
0x6c425  ldarg.0
0x6c426  ldstr    aNextpage// "NextPage"
0x6c42b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c430  brtrue   loc_6C4ED
0x6c435  br       loc_6C51B
0x6c43a  ldarg.0
0x6c43b  ldstr    aPreviouspage// "PreviousPage"
0x6c440  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c445  brtrue   loc_6C4F5
0x6c44a  br       loc_6C51B
0x6c44f  ldarg.0
0x6c450  ldstr    aFirstpage// "FirstPage"
0x6c455  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c45a  brtrue   loc_6C4FD
0x6c45f  br       loc_6C51B
0x6c464  ldarg.0
0x6c465  ldstr    aLastpage// "LastPage"
0x6c46a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c46f  brtrue   loc_6C505
0x6c474  br       loc_6C51B
0x6c479  ldarg.0
0x6c47a  ldstr    aGotopage// "GoToPage"
0x6c47f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c484  brtrue   loc_6C50D
0x6c489  br       loc_6C51B
0x6c48e  ldarg.0
0x6c48f  ldstr    aNavigatejourna// "NavigateJournal"
0x6c494  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c499  brtrue.s loc_6C515
0x6c49b  br.s     loc_6C51B
0x6c49d  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_BrowseBack()
0x6c4a2  stloc.0
0x6c4a3  br.s     loc_6C51B
0x6c4a5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_BrowseForward()
0x6c4aa  stloc.0
0x6c4ab  br.s     loc_6C51B
0x6c4ad  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_BrowseHome()
0x6c4b2  stloc.0
0x6c4b3  br.s     loc_6C51B
0x6c4b5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_BrowseStop()
0x6c4ba  stloc.0
0x6c4bb  br.s     loc_6C51B
0x6c4bd  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Refresh()
0x6c4c2  stloc.0
0x6c4c3  br.s     loc_6C51B
0x6c4c5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Favorites()
0x6c4ca  stloc.0
0x6c4cb  br.s     loc_6C51B
0x6c4cd  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Search()
0x6c4d2  stloc.0
0x6c4d3  br.s     loc_6C51B
0x6c4d5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_IncreaseZoom()
0x6c4da  stloc.0
0x6c4db  br.s     loc_6C51B
0x6c4dd  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_DecreaseZoom()
0x6c4e2  stloc.0
0x6c4e3  br.s     loc_6C51B
0x6c4e5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Zoom()
0x6c4ea  stloc.0
0x6c4eb  br.s     loc_6C51B
0x6c4ed  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_NextPage()
0x6c4f2  stloc.0
0x6c4f3  br.s     loc_6C51B
0x6c4f5  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_PreviousPage()
0x6c4fa  stloc.0
0x6c4fb  br.s     loc_6C51B
0x6c4fd  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_FirstPage()
0x6c502  stloc.0
0x6c503  br.s     loc_6C51B
0x6c505  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_LastPage()
0x6c50a  stloc.0
0x6c50b  br.s     loc_6C51B
0x6c50d  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_GoToPage()
0x6c512  stloc.0
0x6c513  br.s     loc_6C51B
0x6c515  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_NavigateJournal()
0x6c51a  stloc.0
0x6c51b  ldarg.1
0x6c51c  ldtoken  [PresentationCore]System.Windows.Input.ApplicationCommands
0x6c521  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c526  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c52b  brtrue.s loc_6C538
0x6c52d  ldloc.0
0x6c52e  ldnull
0x6c52f  ceq
0x6c531  ldloc.1
0x6c532  and
0x6c533  brfalse  loc_6C94A
0x6c538  ldarg.0
0x6c539  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6c53e  stloc.2
0x6c53f  ldloc.2
0x6c540  ldc.i4   0x7412E5E9
0x6c545  bgt.un   loc_6C5EF
0x6c54a  ldloc.2
0x6c54b  ldc.i4   0x4D2D5D68
0x6c550  bgt.un.s loc_6C59B
0x6c552  ldloc.2
0x6c553  ldc.i4   0xEC3C8CA
0x6c558  bgt.un.s loc_6C575
0x6c55a  ldloc.2
0x6c55b  ldc.i4   0xDC87D53
0x6c560  beq      loc_6C819
0x6c565  ldloc.2
0x6c566  ldc.i4   0xEC3C8CA
0x6c56b  beq      loc_6C7DA
0x6c570  br       loc_6C94A
0x6c575  ldloc.2
0x6c576  ldc.i4   0x3E1CD17A
0x6c57b  beq      loc_6C71D
0x6c580  ldloc.2
0x6c581  ldc.i4   0x4B7F7705
0x6c586  beq      loc_6C858
0x6c58b  ldloc.2
0x6c58c  ldc.i4   0x4D2D5D68
0x6c591  beq      loc_6C786
0x6c596  br       loc_6C94A
0x6c59b  ldloc.2
0x6c59c  ldc.i4   0x58E25863
0x6c5a1  bgt.un.s loc_6C5C9
0x6c5a3  ldloc.2
0x6c5a4  ldc.i4   0x538B10E9
0x6c5a9  beq      loc_6C771
0x6c5ae  ldloc.2
0x6c5af  ldc.i4   0x5797EA6A
0x6c5b4  beq      loc_6C708
0x6c5b9  ldloc.2
0x6c5ba  ldc.i4   0x58E25863
0x6c5bf  beq      loc_6C69F
0x6c5c4  br       loc_6C94A
0x6c5c9  ldloc.2
0x6c5ca  ldc.i4   0x658F3664
0x6c5cf  beq      loc_6C6B4
0x6c5d4  ldloc.2
0x6c5d5  ldc.i4   0x71FD4ACF
0x6c5da  beq      loc_6C6DE
0x6c5df  ldloc.2
0x6c5e0  ldc.i4   0x7412E5E9
0x6c5e5  beq      loc_6C6F3
0x6c5ea  br       loc_6C94A
0x6c5ef  ldloc.2
0x6c5f0  ldc.i4   0xB89DF01A
0x6c5f5  bgt.un.s loc_6C64B
0x6c5f7  ldloc.2
0x6c5f8  ldc.i4   0x83536B68
0x6c5fd  bgt.un.s loc_6C625
0x6c5ff  ldloc.2
0x6c600  ldc.i4   0x81C809FC
0x6c605  beq      loc_6C804
  ... truncated ...
```

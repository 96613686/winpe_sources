# ParseCommandLine(ushort const *,_GAPP *)

- ea: `0x140016fa8`
- end: `0x140018a31`
- name: `?ParseCommandLine@@YAJPEBGPEAU_GAPP@@@Z`
- size: `6793`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GAPP *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140021744`

## callees

- `0x140002116`
- `0x14000283c`
- `0x140002a98`
- `0x140005e4c`
- `0x1400076c8`
- `0x140008434`
- `0x140009f00`
- `0x14000bf54`
- `0x14000fcf0`
- `0x140011f04`
- `0x1400135b8`
- `0x140016bb4`
- `0x140016fa8`
- `0x14001cfa4`
- `0x14001d4ac`
- `0x140053ba0`
- `0x140054ac8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001722d`
- `KERNEL32!HeapFree` at `0x1400173c5`
- `KERNEL32!HeapFree` at `0x14001747b`
- `KERNEL32!HeapFree` at `0x140017531`
- `KERNEL32!HeapFree` at `0x140017671`
- `KERNEL32!HeapFree` at `0x140017957`
- `KERNEL32!HeapFree` at `0x140018333`
- `KERNEL32!HeapFree` at `0x140018842`
- `KERNEL32!HeapFree` at `0x140018870`
- `KERNEL32!HeapFree` at `0x1400188a5`
- `KERNEL32!HeapFree` at `0x1400188d3`
- `KERNEL32!HeapFree` at `0x140018901`
- `KERNEL32!HeapFree` at `0x14001892f`
- `KERNEL32!HeapFree` at `0x14001895e`
- `KERNEL32!HeapFree` at `0x14001898c`
- `KERNEL32!HeapFree` at `0x1400189ba`
- `KERNEL32!HeapFree` at `0x1400189ef`
- `KERNEL32!HeapFree` at `0x14001722d`
- `KERNEL32!HeapFree` at `0x1400173c5`
- `KERNEL32!HeapFree` at `0x14001747b`
- `KERNEL32!HeapFree` at `0x140017531`
- `KERNEL32!HeapFree` at `0x140017671`
- `KERNEL32!HeapFree` at `0x140017957`
- `KERNEL32!HeapFree` at `0x140018333`
- `KERNEL32!HeapFree` at `0x140018842`
- `KERNEL32!HeapFree` at `0x140018870`
- `KERNEL32!HeapFree` at `0x1400188a5`
- `KERNEL32!HeapFree` at `0x1400188d3`
- `KERNEL32!HeapFree` at `0x140018901`
- `KERNEL32!HeapFree` at `0x14001892f`
- `KERNEL32!HeapFree` at `0x14001895e`
- `KERNEL32!HeapFree` at `0x14001898c`
- `KERNEL32!HeapFree` at `0x1400189ba`
- `KERNEL32!HeapFree` at `0x1400189ef`
- `KERNEL32!GetProcessHeap` at `0x140017218`
- `KERNEL32!GetProcessHeap` at `0x1400173af`
- `KERNEL32!GetProcessHeap` at `0x140017466`
- `KERNEL32!GetProcessHeap` at `0x14001751c`
- `KERNEL32!GetProcessHeap` at `0x14001765c`
- `KERNEL32!GetProcessHeap` at `0x14001793e`
- `KERNEL32!GetProcessHeap` at `0x14001831e`
- `KERNEL32!GetProcessHeap` at `0x140018829`
- `KERNEL32!GetProcessHeap` at `0x14001885b`
- `KERNEL32!GetProcessHeap` at `0x140018891`
- `KERNEL32!GetProcessHeap` at `0x1400188be`
- `KERNEL32!GetProcessHeap` at `0x1400188ec`
- `KERNEL32!GetProcessHeap` at `0x14001891a`
- `KERNEL32!GetProcessHeap` at `0x140018948`
- `KERNEL32!GetProcessHeap` at `0x140018977`
- `KERNEL32!GetProcessHeap` at `0x1400189a5`
- `KERNEL32!GetProcessHeap` at `0x1400189db`
- `KERNEL32!GetProcessHeap` at `0x140017218`
- `KERNEL32!GetProcessHeap` at `0x1400173af`
- `KERNEL32!GetProcessHeap` at `0x140017466`
- `KERNEL32!GetProcessHeap` at `0x14001751c`
- `KERNEL32!GetProcessHeap` at `0x14001765c`
- `KERNEL32!GetProcessHeap` at `0x14001793e`
- `KERNEL32!GetProcessHeap` at `0x14001831e`
- `KERNEL32!GetProcessHeap` at `0x140018829`
- `KERNEL32!GetProcessHeap` at `0x14001885b`
- `KERNEL32!GetProcessHeap` at `0x140018891`
- `KERNEL32!GetProcessHeap` at `0x1400188be`
- `KERNEL32!GetProcessHeap` at `0x1400188ec`
- `KERNEL32!GetProcessHeap` at `0x14001891a`
- `KERNEL32!GetProcessHeap` at `0x140018948`
- `KERNEL32!GetProcessHeap` at `0x140018977`
- `KERNEL32!GetProcessHeap` at `0x1400189a5`
- `KERNEL32!GetProcessHeap` at `0x1400189db`
- `KERNEL32!GetLastError` at `0x140018472`
- `KERNEL32!GetLastError` at `0x140018472`
- `KERNEL32!GetFileAttributesW` at `0x1400179a1`
- `KERNEL32!GetFileAttributesW` at `0x1400179a1`
- `KERNEL32!GetModuleFileNameW` at `0x14001845e`
- `KERNEL32!GetModuleFileNameW` at `0x14001845e`
- `KERNEL32!GetCommandLineW` at `0x140017126`
- `KERNEL32!GetCommandLineW` at `0x140017177`
- `KERNEL32!GetCommandLineW` at `0x140017126`
- `KERNEL32!GetCommandLineW` at `0x140017177`
- `KERNEL32!CompareStringW` at `0x1400171ea`
- `KERNEL32!CompareStringW` at `0x140017300`
- `KERNEL32!CompareStringW` at `0x140017385`
- `KERNEL32!CompareStringW` at `0x14001743c`
- `KERNEL32!CompareStringW` at `0x1400174f2`
- `KERNEL32!CompareStringW` at `0x1400175a8`
- `KERNEL32!CompareStringW` at `0x1400175f0`
- `KERNEL32!CompareStringW` at `0x140017632`
- `KERNEL32!CompareStringW` at `0x1400176e8`
- `KERNEL32!CompareStringW` at `0x14001773f`
- `KERNEL32!CompareStringW` at `0x140017789`
- `KERNEL32!CompareStringW` at `0x1400177d7`
- `KERNEL32!CompareStringW` at `0x140017827`
- `KERNEL32!CompareStringW` at `0x140017875`
- `KERNEL32!CompareStringW` at `0x1400178c4`
- `KERNEL32!CompareStringW` at `0x14001790e`
- `KERNEL32!CompareStringW` at `0x140017a18`
- `KERNEL32!CompareStringW` at `0x140017a6a`
- `KERNEL32!CompareStringW` at `0x140017ab0`
- `KERNEL32!CompareStringW` at `0x140017afa`
- `KERNEL32!CompareStringW` at `0x140017b43`
- `KERNEL32!CompareStringW` at `0x140017b8c`
- `KERNEL32!CompareStringW` at `0x140017be2`
- `KERNEL32!CompareStringW` at `0x140017c34`
- `KERNEL32!CompareStringW` at `0x140017c76`
- `KERNEL32!CompareStringW` at `0x140017cba`
- `KERNEL32!CompareStringW` at `0x140017d07`
- `KERNEL32!CompareStringW` at `0x140017d4c`
- `KERNEL32!CompareStringW` at `0x140017d91`
- `KERNEL32!CompareStringW` at `0x140017dec`
- `KERNEL32!CompareStringW` at `0x140017e46`
- `KERNEL32!CompareStringW` at `0x140017e8a`
- `KERNEL32!CompareStringW` at `0x140017ecf`
- `KERNEL32!CompareStringW` at `0x140017f26`
- `KERNEL32!CompareStringW` at `0x140017f71`
- `KERNEL32!CompareStringW` at `0x140017fb6`
- `KERNEL32!CompareStringW` at `0x14001800d`
- `KERNEL32!CompareStringW` at `0x14001805a`
- `KERNEL32!CompareStringW` at `0x14001809c`
- `KERNEL32!CompareStringW` at `0x1400180df`
- `KERNEL32!CompareStringW` at `0x140018125`
- `KERNEL32!CompareStringW` at `0x140018178`
- `KERNEL32!CompareStringW` at `0x1400181c1`
- `KERNEL32!CompareStringW` at `0x140018202`
- `KERNEL32!CompareStringW` at `0x140018243`
- `KERNEL32!CompareStringW` at `0x140018284`
- `KERNEL32!CompareStringW` at `0x1400182c5`
- `KERNEL32!CompareStringW` at `0x1400171ea`
- `KERNEL32!CompareStringW` at `0x140017300`
- `KERNEL32!CompareStringW` at `0x140017385`
- `KERNEL32!CompareStringW` at `0x14001743c`
- `KERNEL32!CompareStringW` at `0x1400174f2`
- `KERNEL32!CompareStringW` at `0x1400175a8`
- `KERNEL32!CompareStringW` at `0x1400175f0`
- `KERNEL32!CompareStringW` at `0x140017632`
- `KERNEL32!CompareStringW` at `0x1400176e8`
- `KERNEL32!CompareStringW` at `0x14001773f`
- `KERNEL32!CompareStringW` at `0x140017789`
- `KERNEL32!CompareStringW` at `0x1400177d7`
- `KERNEL32!CompareStringW` at `0x140017827`
- `KERNEL32!CompareStringW` at `0x140017875`
- `KERNEL32!CompareStringW` at `0x1400178c4`
- `KERNEL32!CompareStringW` at `0x14001790e`
- `KERNEL32!CompareStringW` at `0x140017a18`
- `KERNEL32!CompareStringW` at `0x140017a6a`
- `KERNEL32!CompareStringW` at `0x140017ab0`
- `KERNEL32!CompareStringW` at `0x140017afa`
- `KERNEL32!CompareStringW` at `0x140017b43`
- `KERNEL32!CompareStringW` at `0x140017b8c`
- `KERNEL32!CompareStringW` at `0x140017be2`
- `KERNEL32!CompareStringW` at `0x140017c34`
- `KERNEL32!CompareStringW` at `0x140017c76`
- `KERNEL32!CompareStringW` at `0x140017cba`
- `KERNEL32!CompareStringW` at `0x140017d07`
- `KERNEL32!CompareStringW` at `0x140017d4c`
- `KERNEL32!CompareStringW` at `0x140017d91`
- `KERNEL32!CompareStringW` at `0x140017dec`
- `KERNEL32!CompareStringW` at `0x140017e46`
- `KERNEL32!CompareStringW` at `0x140017e8a`
- `KERNEL32!CompareStringW` at `0x140017ecf`
- `KERNEL32!CompareStringW` at `0x140017f26`
- `KERNEL32!CompareStringW` at `0x140017f71`
- `KERNEL32!CompareStringW` at `0x140017fb6`
- `KERNEL32!CompareStringW` at `0x14001800d`
- `KERNEL32!CompareStringW` at `0x14001805a`
- `KERNEL32!CompareStringW` at `0x14001809c`
- `KERNEL32!CompareStringW` at `0x1400180df`
- `KERNEL32!CompareStringW` at `0x140018125`
- `KERNEL32!CompareStringW` at `0x140018178`
- `KERNEL32!CompareStringW` at `0x1400181c1`
- `KERNEL32!CompareStringW` at `0x140018202`
- `KERNEL32!CompareStringW` at `0x140018243`
- `KERNEL32!CompareStringW` at `0x140018284`
- `KERNEL32!CompareStringW` at `0x1400182c5`
- `SHELL32!CommandLineToArgvW` at `0x14001718b`
- `SHELL32!CommandLineToArgvW` at `0x14001718b`

## string_xrefs

- `0x1400185a6`: `Opening Box: [%s]`
- `0x14001714a`: `CommandLine: [%s]`
- `0x1400171cd`: `/InstallFrom`
- `0x14001735f`: `/ClassId`
- `0x1400178e8`: `/SetupDUPath`
- `0x140017bc2`: `/Update`
- `0x140017e26`: `/Install`
- `0x1400180bd`: `ComputeHost`
- `0x1400185d3`: `Opening Box Result: [0x%X]`
- `0x1400184fd`: `Detecting Product from config file.`
- `0x14001854f`: `ParseCommandLine`
- `0x140018688`: `ParseCommandLine`
- `0x1400187fc`: `ParseCommandLine`

## pseudocode

```c
__int64 __fastcall ParseCommandLine(unsigned __int16 *a1, struct _GAPP *a2)
{
  __int64 v2; // rbx
  unsigned __int16 *v3; // rsi
  __int64 v4; // r12
  __int64 v5; // r13
  __int64 v6; // r15
  __int64 v7; // rdi
  __int64 v8; // r14
  __int64 v9; // rcx
  int StringCch; // eax
  int Internal; // eax
  int ModulePath; // eax
  LPWSTR CommandLineW; // r9
  HANDLE v14; // rcx
  const WCHAR *v15; // rax
  LPWSTR *v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // eax
  HANDLE ProcessHeap; // rax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // eax
  __int64 v24; // rcx
  int v25; // edx
  signed int LastError; // eax
  unsigned int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  HANDLE v30; // rax
  int v31; // eax
  unsigned int v32; // eax
  HANDLE v33; // rax
  int v34; // eax
  unsigned int v35; // eax
  HANDLE v36; // rax
  int v37; // eax
  unsigned int v38; // eax
  HANDLE v39; // rax
  int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  HANDLE v45; // rax
  int v46; // eax
  DWORD FileAttributesW; // eax
  int v48; // eax
  unsigned int v49; // eax
  int v50; // edx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  unsigned __int16 *v54; // rdx
  DWORD ModuleFileNameW; // eax
  int v56; // eax
  int v57; // eax
  HANDLE v58; // rcx
  int v59; // edx
  HANDLE v60; // rcx
  char *v61; // rax
  HANDLE v62; // rcx
  HANDLE v63; // rcx
  LPVOID v64; // rcx
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // rdx
  LPCWSTR v72; // rdx
  struct _GAPP *v73; // rax
  __int64 v74; // rdx
  struct _GAPP *v75; // rcx
  unsigned int v76; // eax
  HANDLE v77; // rcx
  HANDLE v78; // rax
  HANDLE v79; // rax
  WCHAR *v80; // r14
  HANDLE v81; // rax
  HANDLE v82; // rax
  HANDLE v83; // rax
  HANDLE v84; // rax
  HANDLE v85; // rax
  HANDLE v86; // rax
  HANDLE v87; // rax
  void *v88; // rbx
  HANDLE v89; // rax
  PCNZWCH lpString2; // [rsp+28h] [rbp-E0h]
  int v92; // [rsp+38h] [rbp-D0h]
  unsigned int v93; // [rsp+38h] [rbp-D0h]
  int v94; // [rsp+38h] [rbp-D0h]
  int v95; // [rsp+3Ch] [rbp-CCh]
  int v96; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v97; // [rsp+44h] [rbp-C4h]
  __int64 v98; // [rsp+48h] [rbp-C0h]
  LPWSTR *v99; // [rsp+50h] [rbp-B8h]
  int pNumArgs[2]; // [rsp+58h] [rbp-B0h] BYREF
  void *Src; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v102; // [rsp+68h] [rbp-A0h] BYREF
  struct _GAPP *v103; // [rsp+70h] [rbp-98h]
  int v104; // [rsp+78h] [rbp-90h]
  int v105; // [rsp+7Ch] [rbp-8Ch]
  int v106; // [rsp+80h] [rbp-88h]
  __int64 v107; // [rsp+88h] [rbp-80h] BYREF
  LPCWSTR v108; // [rsp+90h] [rbp-78h]
  int v109; // [rsp+98h] [rbp-70h]
  int v110; // [rsp+9Ch] [rbp-6Ch]
  int v111; // [rsp+A0h] [rbp-68h]
  int v112; // [rsp+A4h] [rbp-64h]
  int v113; // [rsp+A8h] [rbp-60h]
  int v114; // [rsp+ACh] [rbp-5Ch]
  int v115; // [rsp+B0h] [rbp-58h]
  int v116; // [rsp+B4h] [rbp-54h]
  int v117; // [rsp+B8h] [rbp-50h]
  int v118; // [rsp+BCh] [rbp-4Ch]
  int v119; // [rsp+C0h] [rbp-48h]
  int v120; // [rsp+C4h] [rbp-44h]
  __int64 v121; // [rsp+C8h] [rbp-40h]
  unsigned __int16 *v122; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v123; // [rsp+D8h] [rbp-30h]
  __int64 v124; // [rsp+E0h] [rbp-28h]
  __int64 v125; // [rsp+E8h] [rbp-20h]
  __int64 v126; // [rsp+F0h] [rbp-18h]
  LPCWSTR lpFileName; // [rsp+F8h] [rbp-10h]
  unsigned __int16 *v128; // [rsp+100h] [rbp-8h] BYREF
  __int64 v129; // [rsp+108h] [rbp+0h]
  LPVOID lpMem[5]; // [rsp+110h] [rbp+8h] BYREF
  WCHAR Filename[264]; // [rsp+138h] [rbp+30h] BYREF

  lpMem[1] = (LPVOID)-2LL;
  v103 = a2;
  Src = a1;
  pNumArgs[0] = 0;
  v129 = 0;
  v2 = 0;
  v107 = 0;
  v3 = 0;
  v122 = 0;
  v4 = 0;
  v123 = 0;
  v5 = 0;
  v124 = 0;
  v6 = 0;
  v126 = 0;
  v7 = 0;
  v121 = 0;
  v108 = 0;
  lpFileName = 0;
  lpMem[2] = 0;
  lpMem[3] = 0;
  v8 = 0;
  v125 = 0;
  v128 = 0;
  v92 = -1;
  v117 = 0;
  v119 = 0;
  v120 = 0;
  v104 = 0;
  v113 = 0;
  v116 = 0;
  v105 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v118 = 0;
  v114 = 0;
  v115 = 0;
  v97 = 0;
  v98 = 0;
  v106 = 0;
  pNumArgs[1] = 0;
  v102 = 0xFFFFFFFF00000000uLL;
  lpMem[0] = 0;
  memset_0(Filename, 0, 0x208u);
  if ( !Src || !v103 )
  {
LABEL_2:
    v9 = 2147942487LL;
    v95 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_221;
  }
  v96 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(&dword_1400860C4, &v96, 0x7FFFFFFF);
  v95 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal((void *)&dword_1400860C4);
    v95 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v2 = v107;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v95);
  ModulePath = v95;
  if ( v95 < 0 )
    goto LABEL_194;
  CommandLineW = GetCommandLineW();
  v14 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v14 = g_shLogFile;
  OutputMsg(v14, g_shLogEvent, L"CommandLine: [%s]", CommandLineW);
  ModulePath = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Src);
  v95 = ModulePath;
  if ( ModulePath < 0 )
    goto LABEL_194;
  v15 = GetCommandLineW();
  v16 = CommandLineToArgvW(v15, pNumArgs);
  v99 = v16;
  if ( !v16 )
    goto LABEL_174;
  v17 = 1;
  v96 = 1;
  if ( pNumArgs[0] <= 1u )
    goto LABEL_173;
  while ( 1 )
  {
    v93 = v17;
    Src = (void *)v17;
    if ( CompareStringW(0x409u, 1u, v16[v17], -1, L"/InstallFrom", -1) == 2 )
    {
      v18 = v96 + 1;
      v96 = v18;
      if ( v18 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v7 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v121 = 0;
        v18 = v96;
      }
      v20 = CMoSetupHelpersT<CEmptyType>::ResolveAndVerifyPathFromCmdLine(v99[v18]);
      v21 = (unsigned int)v20;
      v95 = v20;
      if ( v20 < 0 )
        goto LABEL_159;
      if ( !v105 )
      {
        v21 = 2147942487LL;
        v95 = -2147024809;
LABEL_159:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
        v7 = v121;
        goto LABEL_221;
      }
      v7 = v121;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/SessionId", -1) == 2 )
    {
      v27 = v96 + 1;
      v96 = v27;
      if ( v27 >= pNumArgs[0] )
        goto LABEL_2;
      v28 = CMiscHelpersT<CEmptyType>::ConvertString2Number<unsigned long>(v99[v27], (char *)&v102 + 4);
      v9 = (unsigned int)v28;
      v95 = v28;
      if ( v28 < 0 )
        goto LABEL_3;
      v22 = 1;
      HIDWORD(v98) = 1;
      goto LABEL_24;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/ClassId", -1) == 2 )
    {
      v29 = v96 + 1;
      v96 = v29;
      if ( v29 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v4 )
      {
        v30 = GetProcessHeap();
        HeapFree(v30, 0, (LPVOID)(v4 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v123 = 0;
        v29 = v96;
      }
      v31 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v29]);
      v95 = v31;
      if ( v31 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v31);
        v4 = v123;
        goto LABEL_221;
      }
      v4 = v123;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/ReportId", -1) == 2 )
    {
      v32 = v96 + 1;
      v96 = v32;
      if ( v32 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v5 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, (LPVOID)(v5 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v124 = 0;
        v32 = v96;
      }
      v34 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v32]);
      v95 = v34;
      if ( v34 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34);
        v5 = v124;
        goto LABEL_221;
      }
      v5 = v124;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/SuspendId", -1) == 2 )
    {
      v35 = v96 + 1;
      v96 = v35;
      if ( v35 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v8 )
      {
        v36 = GetProcessHeap();
        HeapFree(v36, 0, (LPVOID)(v8 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v125 = 0;
        v35 = v96;
      }
      v37 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v35]);
      v95 = v37;
      if ( v37 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
        v8 = v125;
        goto LABEL_221;
      }
      v8 = v125;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/CorrelationVector", -1) == 2
      && (unsigned int)(v96 + 1) < pNumArgs[0]
      && CompareStringW(0x409u, 1u, v99[v96 + 1], -1, L"/FlightData", -1) == 2 )
    {
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/FlightData", -1) == 2 )
    {
      v38 = v96 + 1;
      v96 = v38;
      if ( v38 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v6 )
      {
        v39 = GetProcessHeap();
        HeapFree(v39, 0, (LPVOID)(v6 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v126 = 0;
        v38 = v96;
      }
      v40 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v38]);
      v95 = v40;
      if ( v40 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
        v6 = v126;
        goto LABEL_221;
      }
      v6 = v126;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/Eula", -1) == 2 )
    {
      v41 = v96 + 1;
      v96 = v41;
      if ( v41 >= pNumArgs[0] )
        goto LABEL_2;
      Src = (void *)v41;
      if ( CompareStringW(0x409u, 1u, v99[v41], -1, L"Accept", -1) == 2 )
      {
        v111 = 1;
      }
      else
      {
        if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"Defer", -1) != 2 )
          goto LABEL_2;
        v112 = 1;
      }
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/Prompt", -1) == 2 )
    {
      v42 = v96 + 1;
      v96 = v42;
      if ( v42 >= pNumArgs[0] || CompareStringW(0x409u, 1u, v99[v42], -1, L"Defer", -1) != 2 )
        goto LABEL_2;
      v110 = 1;
      goto LABEL_23;
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/Priority", -1) == 2 )
    {
      v43 = v96 + 1;
      v96 = v43;
      if ( v43 >= pNumArgs[0] )
        goto LABEL_2;
      if ( CompareStringW(0x409u, 1u, v99[v43], -1, L"Normal", -1) == 2 )
      {
        v118 = 1;
        goto LABEL_23;
      }
    }
    if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"/SetupDUPath", -1) == 2 )
    {
      v44 = v93 + 1;
      v96 = v93 + 1;
      if ( v93 + 1 >= pNumArgs[0] )
        goto LABEL_2;
      if ( v108 )
      {
        v45 = GetProcessHeap();
        HeapFree(v45, 0, (LPVOID)(v108 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        lpFileName = 0;
        v44 = v96;
      }
      v46 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v44]);
      v95 = v46;
      if ( v46 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v46);
        v108 = lpFileName;
        goto LABEL_221;
      }
      v108 = lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
        v94 = 0;
      else
        v94 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v95 = 0;
      if ( !v94 )
        goto LABEL_2;
LABEL_23:
      v22 = HIDWORD(v98);
LABEL_24:
      v23 = v96;
      goto LABEL_25;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Console", -1) == 2 )
    {
      v117 = 1;
      goto LABEL_91;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Selfhost", -1) == 2 )
    {
      v120 = 1;
      goto LABEL_91;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Quiet", -1) == 2 )
    {
      v104 = 1;
      goto LABEL_91;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/ExpressPackage", -1) == 2 )
    {
      v113 = 1;
      goto LABEL_91;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Override", -1) == 2 )
    {
      v119 = 1;
      goto LABEL_91;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/AzureHost", -1) == 2 )
    {
      v24 = 8;
      v97 = 8;
      v23 = v93;
      v22 = HIDWORD(v98);
      goto LABEL_26;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Update", -1) == 2 )
    {
      v24 = 5;
      goto LABEL_105;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Package", -1) == 2 )
    {
      v24 = 6;
      goto LABEL_105;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Recovery", -1) == 2 )
    {
      v24 = 2;
      goto LABEL_105;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Web", -1) == 2 )
    {
      v24 = 7;
      v97 = 7;
      goto LABEL_106;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Boot", -1) == 2 )
    {
      v24 = 4;
LABEL_105:
      v97 = v24;
LABEL_106:
      v23 = v93;
      v22 = HIDWORD(v98);
      goto LABEL_26;
    }
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Servicing", -1) == 2 )
    {
      v24 = 9;
      goto LABEL_105;
    }
    v48 = CompareStringW(0x409u, 1u, v99[v93], -1, L"/PreDownload", -1);
    v25 = 1;
    if ( v48 == 2 )
      goto LABEL_118;
    if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Download", -1) != 2 )
    {
      if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Install", -1) == 2 )
      {
        v25 = 2;
      }
      else if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Finalize", -1) == 2 )
      {
        v25 = 3;
      }
      else
      {
        if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Query", -1) == 2 )
        {
          LODWORD(v98) = 11;
          v96 = v93 + 1;
          if ( v93 + 1 >= pNumArgs[0] || CompareStringW(0x409u, 1u, v99[v93 + 1], -1, L"DowntimeLevel", -1) != 2 )
            goto LABEL_2;
          v106 |= 1u;
          goto LABEL_23;
        }
        if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/PostReboot", -1) != 2 )
        {
          if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Product", -1) == 2 )
          {
            v49 = v93 + 1;
            v96 = v93 + 1;
            if ( v93 + 1 >= pNumArgs[0] )
              goto LABEL_2;
            Src = (void *)v49;
            if ( CompareStringW(0x409u, 1u, v99[v49], -1, L"AzsHci", -1) == 2 )
            {
              v50 = 4;
            }
            else if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"Server", -1) == 2 )
            {
              v50 = 2;
            }
            else
            {
              v51 = CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"Client", -1);
              v50 = 1;
              if ( v51 != 2 )
              {
                if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"ComputeHost", -1) != 2 )
                {
                  if ( CompareStringW(0x409u, 1u, v99[(_QWORD)Src], -1, L"CloudHost", -1) != 2 )
                    goto LABEL_2;
                  pNumArgs[1] = 7;
                  LODWORD(v102) = 7;
                  goto LABEL_23;
                }
                v50 = 6;
              }
            }
            pNumArgs[1] = v50;
            LODWORD(v102) = v50;
            goto LABEL_23;
          }
          if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/Cleanup", -1) == 2 )
          {
            v114 = 1;
            goto LABEL_91;
          }
          if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/WDS", -1) == 2
            || CompareStringW(0x409u, 1u, v99[v93], -1, L"/WDSDiscover", -1) == 2
            || CompareStringW(0x409u, 1u, v99[v93], -1, L"/WDSDiscoverV6", -1) == 2
            || CompareStringW(0x409u, 1u, v99[v93], -1, L"/WDSServer", -1) == 2 )
          {
            v115 = 1;
LABEL_91:
            v23 = v93;
          }
          else
          {
            if ( CompareStringW(0x409u, 1u, v99[v93], -1, L"/?", -1) == 2 )
            {
              v109 = 1;
              goto LABEL_91;
            }
            if ( v2 )
            {
              v53 = STRAPI_Format(&v122, L"%s \"%s\"", v2, v99[v93]);
              v95 = v53;
              if ( v53 < 0 )
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v53);
                v3 = v122;
                goto LABEL_221;
              }
              v54 = v122;
              v3 = 0;
              v122 = 0;
              SH<unsigned short *,SH_SSTRING>::Attach(&v107, v54);
            }
            else
            {
              v52 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v99[v93]);
              v95 = v52;
              if ( v52 < 0 )
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v52);
                v2 = v107;
                goto LABEL_221;
              }
            }
            v23 = v93;
            v96 = v93;
            v2 = v107;
          }
          v22 = HIDWORD(v98);
LABEL_25:
          v24 = v97;
LABEL_26:
          v25 = v98;
          goto LABEL_27;
        }
        v25 = 9;
      }
LABEL_118:
      LODWORD(v98) = v25;
      v23 = v93;
      v24 = v97;
      v22 = HIDWORD(v98);
      goto LABEL_27;
    }
    v25 = 8;
    LODWORD(v98) = 8;
    v23 = v93;
    v24 = v97;
    v22 = HIDWORD(v98);
LABEL_27:
    v17 = (unsigned int)(v23 + 1);
    v96 = v17;
    if ( (unsigned int)v17 >= pNumArgs[0] )
      break;
    v16 = v99;
  }
  v92 = HIDWORD(v102);
  if ( (((_DWORD)v24 - 5) & 0xFFFFFFFA) == 0 && (_DWORD)v24 != 10 && v25 != 3 && (!v22 || !HIDWORD(v102)) )
  {
    v104 = 1;
    goto LABEL_172;
  }
  if ( (_DWORD)v24 == 8 )
  {
    v104 = 1;
    goto LABEL_178;
  }
LABEL_172:
  if ( (_DWORD)v24 )
    goto LABEL_178;
LABEL_173:
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW >= 0x104 )
    {
      ModulePath = -2147024774;
      v95 = -2147024774;
      goto LABEL_194;
    }
    v62 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v62 = g_shLogFile;
    OutputMsg(v62, g_shLogEvent, L"Opening Box: [%s]", Filename);
    v63 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v63 = g_shLogFile;
    OutputMsg(v63, g_shLogEvent, L"Opening Box Result: [0x%X]", (unsigned int)v95);
    v105 = BoxOpenFromPath(Filename, lpMem);
    v64 = lpMem[0];
    if ( lpMem[0] )
    {
      FreeBoxFileHandle(lpMem[0]);
      lpMem[0] = 0;
    }
    HIDWORD(v102) = 0;
    v65 = CRegUtilT<unsigned short *,CRegType,0,1>::KeyExists(
            v64,
            L"SYSTEM\\CurrentControlSet\\Control\\MiniNt",
            (char *)&v102 + 4);
    v95 = v65;
    if ( v65 >= 0 )
    {
      v116 = HIDWORD(v102);
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v65);
      v65 = v95;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v65);
    v9 = (unsigned int)v95;
    if ( v95 < 0 )
      goto LABEL_3;
    if ( v116 )
    {
      v24 = 4;
    }
    else
    {
      v24 = 1;
      if ( v105 >= 0 )
        v24 = 7;
    }
    v97 = v24;
LABEL_178:
    if ( !(_DWORD)v98 )
    {
      v56 = 2;
      if ( (_DWORD)v24 == 7 )
        v56 = 8;
      LODWORD(v98) = v56;
    }
    v57 = pNumArgs[1];
    if ( pNumArgs[1] )
    {
LABEL_219:
      v66 = v129;
      v129 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach(v103, v66);
      v67 = v2;
      v2 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 8, v67);
      v68 = v4;
      v4 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 16, v68);
      v69 = v5;
      v5 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 24, v69);
      v70 = v6;
      v6 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 40, v70);
      v71 = v7;
      v7 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 48, v71);
      v72 = v108;
      v108 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v103 + 56, v72);
      v73 = v103;
      *((_DWORD *)v103 + 16) = v92;
      *((_DWORD *)v73 + 17) = v117;
      *((_DWORD *)v73 + 18) = v119;
      *((_DWORD *)v73 + 19) = v120;
      *((_DWORD *)v73 + 20) = v104;
      *((_DWORD *)v73 + 21) = v113;
      *((_DWORD *)v73 + 22) = v109;
      *((_DWORD *)v73 + 23) = v110;
      *((_DWORD *)v73 + 24) = v111;
      *((_DWORD *)v73 + 25) = v112;
      *((_DWORD *)v73 + 26) = v118;
      v74 = v8;
      v8 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((char *)v73 + 32, v74);
      v75 = v103;
      *((_DWORD *)v103 + 29) = v97;
      *((_DWORD *)v75 + 30) = v98;
      *((_DWORD *)v75 + 31) = v106;
      *((_DWORD *)v75 + 32) = pNumArgs[1];
      *((_DWORD *)v75 + 27) = v114;
      *((_DWORD *)v75 + 28) = v115;
      goto LABEL_220;
    }
    if ( (_DWORD)v24 != 1 && (_DWORD)v24 != 4 )
    {
LABEL_216:
      if ( (_DWORD)v24 == 8 )
        v57 = 7;
      pNumArgs[1] = v57;
      goto LABEL_219;
    }
    ModulePath = CMiscHelpersT<CEmptyType>::GetModulePath(v24, &v128);
    v95 = ModulePath;
    if ( ModulePath >= 0 )
    {
      v58 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v58 = g_shLogFile;
      OutputMsg(v58, g_shLogEvent, L"Detecting Product from config file.");
      v59 = DetectProductFromConfigFile(v128, (enum MoSetupProduct *)&v102);
      v95 = v59;
      pNumArgs[1] = v102;
      v60 = 0;
      v61 = (char *)g_shLogFile - 1;
      if ( v59 >= 0 )
      {
        if ( (unsigned __int64)v61 <= 0xFFFFFFFFFFFFFFFDuLL )
          v60 = g_shLogFile;
        LODWORD(lpString2) = v102;
        OutputMsg(v60, g_shLogEvent, L"%s: Product from Setup.cfg: [%lu]", L"ParseCommandLine", lpString2);
      }
      else
      {
        if ( (unsigned __int64)v61 <= 0xFFFFFFFFFFFFFFFDuLL )
          v60 = g_shLogFile;
        LODWORD(lpString2) = v59;
        OutputMsg(
          v60,
          g_shLogEvent,
          L"%s: Failed to Detect Product from Setup.cfg. Error = 0x%X",
          L"ParseCommandLine",
          lpString2);
        v95 = 0;
      }
      v57 = pNumArgs[1];
      if ( pNumArgs[1] )
        goto LABEL_219;
      LODWORD(v24) = v97;
      goto LABEL_216;
    }
LABEL_194:
    v9 = (unsigned int)ModulePath;
    goto LABEL_3;
  }
LABEL_174:
  LastError = GetLastError();
  v95 = LastError;
  if ( !LastError )
  {
    LastError = -2147467259;
    goto LABEL_32;
  }
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_32:
    v95 = LastError;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)LastError);
LABEL_220:
  v76 = v95;
  if ( v95 < 0 )
  {
LABEL_221:
    v77 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v77 = g_shLogFile;
    LODWORD(lpString2) = v95;
    OutputMsg(v77, g_shLogEvent, L"%s: Error = 0x%X", L"ParseCommandLine", lpString2);
    v76 = v95;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v76);
  if ( v128 )
  {
    v78 = GetProcessHeap();
    HeapFree(v78, 0, v128 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
  {
    v79 = GetProcessHeap();
    HeapFree(v79, 0, (LPVOID)(v8 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v108 )
  {
    v80 = (WCHAR *)(v108 - 2);
    v81 = GetProcessHeap();
    HeapFree(v81, 0, v80);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
  {
    v82 = GetProcessHeap();
    HeapFree(v82, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v83 = GetProcessHeap();
    HeapFree(v83, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v85 = GetProcessHeap();
    HeapFree(v85, 0, (LPVOID)(v4 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v86 = GetProcessHeap();
    HeapFree(v86, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v87 = GetProcessHeap();
    HeapFree(v87, 0, (LPVOID)(v2 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v129 )
  {
    v88 = (void *)(v129 - 4);
    v89 = GetProcessHeap();
    HeapFree(v89, 0, v88);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v95;
}

```

## disassembly

```asm
0x140016fa8  mov     rax, rsp
0x140016fab  push    rbp
0x140016fac  push    rsi
0x140016fad  push    rdi
0x140016fae  push    r12
0x140016fb0  push    r13
0x140016fb2  push    r14
0x140016fb4  push    r15
0x140016fb6  lea     rbp, [rax-288h]
0x140016fbd  sub     rsp, 350h
0x140016fc4  mov     [rbp+280h+var_270], 0FFFFFFFFFFFFFFFEh
0x140016fcc  mov     [rax+18h], rbx
0x140016fd0  mov     rax, cs:__security_cookie
0x140016fd7  xor     rax, rsp
0x140016fda  mov     [rbp+280h+var_40], rax
0x140016fe1  mov     qword ptr [rsp+380h+var_318], rdx
0x140016fe6  mov     [rsp+380h+Src], rcx
0x140016feb  xor     ecx, ecx
0x140016fed  mov     [rsp+380h+pNumArgs], ecx
0x140016ff1  mov     [rbp+280h+var_280], rcx
0x140016ff5  mov     ebx, ecx
0x140016ff7  mov     [rbp+280h+var_300], rcx
0x140016ffb  mov     esi, ecx
0x140016ffd  mov     [rbp+280h+var_2B8], rcx
0x140017001  mov     r12d, ecx
0x140017004  mov     [rbp+280h+var_2B0], rcx
0x140017008  mov     r13d, ecx
0x14001700b  mov     [rbp+280h+var_2A8], rcx
0x14001700f  mov     r15d, ecx
0x140017012  mov     [rbp+280h+var_298], rcx
0x140017016  mov     edi, ecx
0x140017018  mov     [rbp+280h+var_2C0], rcx
0x14001701c  mov     [rbp+280h+var_2F8], rcx
0x140017020  mov     [rbp+280h+lpFileName], rcx
0x140017024  mov     [rbp+280h+var_268], rcx
0x140017028  mov     [rbp+280h+var_260], rcx
0x14001702c  mov     r14d, ecx
0x14001702f  mov     [rbp+280h+var_2A0], rcx
0x140017033  mov     [rbp+280h+var_288], rcx
0x140017037  or      eax, 0FFFFFFFFh
0x14001703a  mov     [rsp+380h+var_350], eax
0x14001703e  mov     dword ptr [rsp+380h+var_320+4], eax
0x140017042  mov     dword ptr [rsp+380h+var_340+4], ecx
0x140017046  mov     [rbp+280h+var_2D0], ecx
0x140017049  mov     [rbp+280h+var_2C8], ecx
0x14001704c  mov     [rbp+280h+var_2C4], ecx
0x14001704f  mov     [rsp+380h+var_310], ecx
0x140017053  mov     [rbp+280h+var_2E0], ecx
0x140017056  mov     [rbp+280h+var_2D4], ecx
0x140017059  mov     [rsp+380h+var_30C], ecx
0x14001705d  mov     [rbp+280h+var_2F0], ecx
0x140017060  mov     [rbp+280h+var_2EC], ecx
0x140017063  mov     [rbp+280h+var_2E8], ecx
0x140017066  mov     [rbp+280h+var_2E4], ecx
0x140017069  mov     [rbp+280h+var_2CC], ecx
0x14001706c  mov     [rbp+280h+var_2DC], ecx
0x14001706f  mov     [rbp+280h+var_2D8], ecx
0x140017072  mov     [rsp+380h+var_344], ecx
0x140017076  mov     dword ptr [rsp+380h+var_340], ecx
0x14001707a  mov     [rsp+380h+var_308], ecx
0x14001707e  mov     [rsp+380h+pNumArgs+4], ecx
0x140017082  mov     dword ptr [rsp+380h+var_320], ecx
0x140017086  mov     [rbp+280h+lpMem], rcx
0x14001708a  xor     edx, edx; Val
0x14001708c  mov     r8d, 208h; Size
0x140017092  lea     rcx, [rbp+280h+Filename]; void *
0x140017096  call    memset_0
0x14001709b  xor     eax, eax
0x14001709d  cmp     [rsp+380h+Src], rax
0x1400170a2  jnz     short loc_1400170B7
0x1400170a4  mov     ecx, 80070057h
0x1400170a9  mov     [rsp+380h+var_34C], ecx
0x1400170ad  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400170b2  jmp     loc_1400187DF
0x1400170b7  cmp     qword ptr [rsp+380h+var_318], rax
0x1400170bc  jz      short loc_1400170A4
0x1400170be  mov     [rsp+380h+var_348], eax
0x1400170c2  mov     r8d, 7FFFFFFFh
0x1400170c8  lea     rdx, [rsp+380h+var_348]
0x1400170cd  lea     rcx, dword_1400860C4
0x1400170d4  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1400170d9  mov     [rsp+380h+var_34C], eax
0x1400170dd  test    eax, eax
0x1400170df  jns     short loc_1400170EA
0x1400170e1  mov     ecx, eax
0x1400170e3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400170e8  jmp     short loc_140017111
0x1400170ea  lea     r8, [rbp+280h+var_300]
0x1400170ee  mov     edx, [rsp+380h+var_348]
0x1400170f2  lea     rcx, dword_1400860C4; Src
0x1400170f9  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1400170fe  mov     [rsp+380h+var_34C], eax
0x140017102  test    eax, eax
0x140017104  jns     short loc_14001710D
0x140017106  mov     ecx, eax
0x140017108  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001710d  mov     rbx, [rbp+280h+var_300]
0x140017111  mov     ecx, [rsp+380h+var_34C]
0x140017115  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001711a  mov     eax, [rsp+380h+var_34C]
0x14001711e  test    eax, eax
0x140017120  js      loc_140018586
0x140017126  call    cs:__imp_GetCommandLineW
0x14001712d  nop     dword ptr [rax+rax+00h]
0x140017132  mov     r9, rax
0x140017135  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001713c  lea     rax, [r8-1]
0x140017140  xor     ecx, ecx
0x140017142  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140017146  cmovbe  rcx, r8; hFile
0x14001714a  lea     r8, aCommandlineS; "CommandLine: [%s]"
0x140017151  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140017158  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001715d  lea     rdx, [rbp+280h+var_280]
0x140017161  mov     rcx, [rsp+380h+Src]; Src
0x140017166  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x14001716b  mov     [rsp+380h+var_34C], eax
0x14001716f  test    eax, eax
0x140017171  js      loc_140018586
0x140017177  call    cs:__imp_GetCommandLineW
0x14001717e  nop     dword ptr [rax+rax+00h]
0x140017183  mov     rcx, rax; lpCmdLine
0x140017186  lea     rdx, [rsp+380h+pNumArgs]; pNumArgs
0x14001718b  call    cs:__imp_CommandLineToArgvW
0x140017192  nop     dword ptr [rax+rax+00h]
0x140017197  mov     rcx, rax
0x14001719a  mov     qword ptr [rsp+380h+var_338], rax
0x14001719f  test    rax, rax
0x1400171a2  jz      loc_140018472
0x1400171a8  mov     eax, 1
0x1400171ad  mov     [rsp+380h+var_348], eax
0x1400171b1  cmp     [rsp+380h+pNumArgs], 1
0x1400171b6  jbe     loc_140018452
0x1400171bc  mov     [rsp+380h+var_350], eax
0x1400171c0  mov     [rsp+380h+Src], rax
0x1400171c5  mov     [rsp+380h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400171cd  lea     rdx, String2; "/InstallFrom"
0x1400171d4  mov     [rsp+380h+lpString2], rdx; lpString2
0x1400171d9  or      r9d, 0FFFFFFFFh; cchCount1
0x1400171dd  mov     r8, [rcx+rax*8]; lpString1
0x1400171e1  lea     edx, [r9+2]; dwCmpFlags
0x1400171e5  mov     ecx, 409h; Locale
0x1400171ea  call    cs:__imp_CompareStringW
0x1400171f1  nop     dword ptr [rax+rax+00h]
0x1400171f6  cmp     eax, 2
0x1400171f9  jnz     loc_1400172D4
0x1400171ff  mov     eax, [rsp+380h+var_348]
0x140017203  inc     eax
0x140017205  mov     [rsp+380h+var_348], eax
0x140017209  cmp     eax, [rsp+380h+pNumArgs]
0x14001720d  jnb     loc_1400170A4
0x140017213  test    rdi, rdi
0x140017216  jz      short loc_14001724C
0x140017218  call    cs:__imp_GetProcessHeap
0x14001721f  nop     dword ptr [rax+rax+00h]
0x140017224  mov     rcx, rax; hHeap
0x140017227  lea     r8, [rdi-4]; lpMem
0x14001722b  xor     edx, edx; dwFlags
0x14001722d  call    cs:__imp_HeapFree
0x140017234  nop     dword ptr [rax+rax+00h]
0x140017239  xor     ecx, ecx
0x14001723b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140017240  mov     [rbp+280h+var_2C0], 0
0x140017248  mov     eax, [rsp+380h+var_348]
0x14001724c  mov     ecx, eax
0x14001724e  lea     r9, [rbp+280h+var_2C0]
0x140017252  lea     r8, [rsp+380h+var_30C]
0x140017257  mov     rax, qword ptr [rsp+380h+var_338]
0x14001725c  mov     rcx, [rax+rcx*8]; lpFileName
0x140017260  call    ?ResolveAndVerifyPathFromCmdLine@?$CMoSetupHelpersT@VCEmptyType@@@@SAJPEBGHPEAHPEAPEAG@Z; CMoSetupHelpersT<CEmptyType>::ResolveAndVerifyPathFromCmdLine(ushort const *,int,int *,ushort * *)
0x140017265  mov     ecx, eax
0x140017267  mov     [rsp+380h+var_34C], eax
0x14001726b  test    eax, eax
0x14001726d  js      loc_1400183B4
0x140017273  cmp     [rsp+380h+var_30C], 0
0x140017278  jz      loc_1400183AB
0x14001727e  mov     rdi, [rbp+280h+var_2C0]
0x140017282  mov     r8d, dword ptr [rsp+380h+var_340+4]
0x140017287  mov     eax, [rsp+380h+var_348]
0x14001728b  mov     ecx, [rsp+380h+var_344]
0x14001728f  mov     r10d, 8
0x140017295  mov     edx, dword ptr [rsp+380h+var_340]
0x140017299  inc     eax
0x14001729b  mov     [rsp+380h+var_348], eax
0x14001729f  cmp     eax, [rsp+380h+pNumArgs]
0x1400172a3  jnb     loc_14001841E
0x1400172a9  mov     rcx, qword ptr [rsp+380h+var_338]
0x1400172ae  jmp     loc_1400171BC
0x1400172b3  mov     eax, 80004005h
0x1400172b8  jmp     short loc_1400172C4
0x1400172ba  jle     short loc_1400172C8
0x1400172bc  movzx   eax, ax
0x1400172bf  or      eax, 80070000h
0x1400172c4  mov     [rsp+380h+var_34C], eax
0x1400172c8  mov     ecx, eax
0x1400172ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400172cf  jmp     loc_1400187D7
0x1400172d4  or      r9d, 0FFFFFFFFh; cchCount1
0x1400172d8  mov     [rsp+380h+cchCount2], r9d; cchCount2
0x1400172dd  lea     rax, aSessionid; "/SessionId"
0x1400172e4  mov     [rsp+380h+lpString2], rax; lpString2
0x1400172e9  mov     rax, qword ptr [rsp+380h+var_338]
0x1400172ee  mov     r8, [rsp+380h+Src]
0x1400172f3  mov     r8, [rax+r8*8]; lpString1
0x1400172f7  lea     edx, [r9+2]; dwCmpFlags
0x1400172fb  mov     ecx, 409h; Locale
0x140017300  call    cs:__imp_CompareStringW
0x140017307  nop     dword ptr [rax+rax+00h]
0x14001730c  cmp     eax, 2
0x14001730f  jnz     short loc_140017358
0x140017311  mov     eax, [rsp+380h+var_348]
0x140017315  inc     eax
0x140017317  mov     [rsp+380h+var_348], eax
0x14001731b  cmp     eax, [rsp+380h+pNumArgs]
0x14001731f  jnb     loc_1400170A4
0x140017325  mov     ecx, eax
0x140017327  lea     rdx, [rsp+380h+var_320+4]
0x14001732c  mov     rax, qword ptr [rsp+380h+var_338]
0x140017331  mov     rcx, [rax+rcx*8]
0x140017335  call    ??$ConvertString2Number@K@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAK@Z; CMiscHelpersT<CEmptyType>::ConvertString2Number<ulong>(ushort const *,ulong *)
0x14001733a  mov     ecx, eax
0x14001733c  mov     [rsp+380h+var_34C], eax
0x140017340  test    eax, eax
0x140017342  js      loc_1400170AD
0x140017348  mov     r8d, 1
0x14001734e  mov     dword ptr [rsp+380h+var_340+4], r8d
0x140017353  jmp     loc_140017287
0x140017358  or      ecx, 0FFFFFFFFh
0x14001735b  mov     [rsp+380h+cchCount2], ecx; cchCount2
0x14001735f  lea     rax, aClassid; "/ClassId"
0x140017366  mov     [rsp+380h+lpString2], rax; lpString2
0x14001736b  mov     r9d, ecx; cchCount1
0x14001736e  mov     rax, qword ptr [rsp+380h+var_338]
0x140017373  mov     rcx, [rsp+380h+Src]
0x140017378  mov     r8, [rax+rcx*8]; lpString1
0x14001737c  lea     edx, [r9+2]; dwCmpFlags
0x140017380  mov     ecx, 409h; Locale
0x140017385  call    cs:__imp_CompareStringW
0x14001738c  nop     dword ptr [rax+rax+00h]
0x140017391  cmp     eax, 2
0x140017394  jnz     short loc_14001740F
0x140017396  mov     eax, [rsp+380h+var_348]
0x14001739a  inc     eax
0x14001739c  mov     [rsp+380h+var_348], eax
0x1400173a0  cmp     eax, [rsp+380h+pNumArgs]
0x1400173a4  jnb     loc_1400170A4
0x1400173aa  test    r12, r12
0x1400173ad  jz      short loc_1400173E4
0x1400173af  call    cs:__imp_GetProcessHeap
0x1400173b6  nop     dword ptr [rax+rax+00h]
0x1400173bb  mov     rcx, rax; hHeap
0x1400173be  lea     r8, [r12-4]; lpMem
0x1400173c3  xor     edx, edx; dwFlags
0x1400173c5  call    cs:__imp_HeapFree
0x1400173cc  nop     dword ptr [rax+rax+00h]
0x1400173d1  xor     ecx, ecx
0x1400173d3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400173d8  mov     [rbp+280h+var_2B0], 0
0x1400173e0  mov     eax, [rsp+380h+var_348]
0x1400173e4  mov     ecx, eax
0x1400173e6  lea     rdx, [rbp+280h+var_2B0]
0x1400173ea  mov     rax, qword ptr [rsp+380h+var_338]
0x1400173ef  mov     rcx, [rax+rcx*8]; Src
0x1400173f3  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x1400173f8  mov     ecx, eax
0x1400173fa  mov     [rsp+380h+var_34C], eax
0x1400173fe  test    eax, eax
0x140017400  js      loc_1400183C2
0x140017406  mov     r12, [rbp+280h+var_2B0]
0x14001740a  jmp     loc_140017282
0x14001740f  or      ecx, 0FFFFFFFFh
0x140017412  mov     [rsp+380h+cchCount2], ecx; cchCount2
0x140017416  lea     rax, aReportid; "/ReportId"
0x14001741d  mov     [rsp+380h+lpString2], rax; lpString2
0x140017422  mov     r9d, ecx; cchCount1
0x140017425  mov     rax, qword ptr [rsp+380h+var_338]
0x14001742a  mov     rcx, [rsp+380h+Src]
0x14001742f  mov     r8, [rax+rcx*8]; lpString1
0x140017433  lea     edx, [r9+2]; dwCmpFlags
0x140017437  mov     ecx, 409h; Locale
0x14001743c  call    cs:__imp_CompareStringW
0x140017443  nop     dword ptr [rax+rax+00h]
0x140017448  cmp     eax, 2
0x14001744b  jnz     short loc_1400174C5
0x14001744d  mov     eax, [rsp+380h+var_348]
0x140017451  inc     eax
0x140017453  mov     [rsp+380h+var_348], eax
0x140017457  cmp     eax, [rsp+380h+pNumArgs]
0x14001745b  jnb     loc_1400170A4
0x140017461  test    r13, r13
0x140017464  jz      short loc_14001749A
0x140017466  call    cs:__imp_GetProcessHeap
0x14001746d  nop     dword ptr [rax+rax+00h]
0x140017472  mov     rcx, rax; hHeap
0x140017475  lea     r8, [r13-4]; lpMem
0x140017479  xor     edx, edx; dwFlags
0x14001747b  call    cs:__imp_HeapFree
0x140017482  nop     dword ptr [rax+rax+00h]
0x140017487  xor     ecx, ecx
0x140017489  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
  ... truncated ...
```

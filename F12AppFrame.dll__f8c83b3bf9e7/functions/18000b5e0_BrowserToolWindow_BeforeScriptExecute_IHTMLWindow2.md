# BrowserToolWindow::BeforeScriptExecute(IHTMLWindow2 *)

- ea: `0x18000b5e0`
- end: `0x18000bb1b`
- name: `?BeforeScriptExecute@BrowserToolWindow@@UEAAJPEAUIHTMLWindow2@@@Z`
- size: `1339`
- prototype: `__int64 __fastcall(BrowserToolWindow *__hidden this, struct IHTMLWindow2 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180002dd4`
- `0x180003880`
- `0x180003c38`
- `0x1800045b4`
- `0x18000b5e0`
- `0x18000d48c`
- `0x18002edec`
- `0x180031ec0`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b6aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b6d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b9ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b6aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b6d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b9ca`
- `SHLWAPI!PathFindFileNameW` at `0x18000b66f`
- `SHLWAPI!PathFindFileNameW` at `0x18000b66f`
- `USER32!MessageBoxW` at `0x18000b9df`
- `USER32!MessageBoxW` at `0x18000b9df`

## string_xrefs

- `0x18000b898`: `Debug Plugin - %s`
- `0x18000b8b2`: `Debug Plugin - %s`

## pseudocode

```c
__int64 __fastcall BrowserToolWindow::BeforeScriptExecute(BrowserToolWindow *this, struct IHTMLWindow2 *a2)
{
  int ModuleFileNameW; // ebx
  volatile signed __int32 *v4; // rdx
  LPWSTR FileNameW; // rax
  __int64 v7; // r8
  LPCWSTR v8; // r15
  int v9; // eax
  const wchar_t *v10; // rdx
  int v11; // eax
  const wchar_t *v12; // rdx
  int EnvironmentVariableW; // eax
  LPCWSTR v14; // rdi
  int v15; // edx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  __int64 v20; // rsi
  LPCWSTR v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // r14
  LPCWSTR v24; // rbx
  int v25; // edx
  const WCHAR *v26; // r14
  const WCHAR *v27; // rbx
  _QWORD *v28; // rdx
  _QWORD *v29; // rdx
  _QWORD *v30; // rdx
  __int64 v31; // [rsp+20h] [rbp-40h]
  __int64 v32; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpCaption; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR lpText; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v35[8]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v36; // [rsp+50h] [rbp-10h]
  __int64 v37; // [rsp+58h] [rbp-8h]
  LPCWSTR pszPath; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v39; // [rsp+B8h] [rbp+58h] BYREF

  pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***, struct IHTMLWindow2 *))ATL::g_strmgr[3])(&ATL::g_strmgr, a2)
                    + 24);
  ModuleFileNameW = Win32Helpers::GetModuleFileNameW(0);
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW >= 0 )
      ModuleFileNameW = -2147467259;
    v4 = (volatile signed __int32 *)(pszPath - 12);
LABEL_5:
    if ( _InterlockedDecrement(v4 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
    return (unsigned int)ModuleFileNameW;
  }
  FileNameW = PathFindFileNameW(pszPath);
  if ( FileNameW )
  {
    v7 = -1;
    do
      ++v7;
    while ( FileNameW[v7] );
  }
  else
  {
    v7 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&pszPath, FileNameW, v7);
  v8 = pszPath;
  v9 = _o__wcsicmp(pszPath, L"iechooser.exe");
  v10 = L"F12BREAKONSCRIPTCHOOSER";
  if ( v9 )
    v10 = L"F12BREAKONSCRIPT";
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v39,
    (__int64)v10);
  v11 = _o__wcsicmp(v8, L"iechooser.exe");
  v12 = L"(Other)";
  if ( v11 )
    v12 = L"(Internet Explorer)";
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v32,
    (__int64)v12);
  pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  EnvironmentVariableW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                           &pszPath,
                           v39);
  v14 = pszPath;
  if ( EnvironmentVariableW )
  {
    v15 = *pszPath - 48;
    if ( *pszPath == 48 )
      v15 = pszPath[1];
    if ( v15 )
    {
      v36 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v37 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      ModuleFileNameW = F12::GetScriptToolInitializeInfo(*((unsigned int *)this + 28), v35);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0 )
          ModuleFileNameW = -2147467259;
        v16 = (_QWORD *)(v37 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v37 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
        v17 = (_QWORD *)(v36 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v36 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
        if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
        v18 = (_QWORD *)(v32 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v32 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
        v19 = (_QWORD *)(v39 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v39 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
        v4 = (volatile signed __int32 *)(v8 - 12);
        goto LABEL_5;
      }
      lpCaption = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &pszPath,
                               L"Debug Plugin - %s") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&pszPath, L"Debug Plugin - %s", 17);
      v20 = v36;
      v21 = pszPath;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpCaption,
        pszPath,
        v36);
      if ( _InterlockedDecrement((volatile signed __int32 *)v21 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
      lpText = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      v22 = v39;
      v23 = v32;
      pszPath = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &pszPath,
                               L"Launching %s...\n"
                                "\n"
                                "Attach script debugger now.\n"
                                "\n"
                                "Before anything you must first have UN-checked 'Disable script debugging %s' in the IE G"
                                "ear menu.\n"
                                "\n"
                                "To avoid this dialog, clear %s\n"
                                "environment variable") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          &pszPath,
          L"Launching %s...\n"
           "\n"
           "Attach script debugger now.\n"
           "\n"
           "Before anything you must first have UN-checked 'Disable script debugging %s' in the IE Gear menu.\n"
           "\n"
           "To avoid this dialog, clear %s\n"
           "environment variable",
          196);
      v31 = v22;
      v24 = pszPath;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpText,
        pszPath,
        v20,
        v23,
        v31);
      if ( _InterlockedDecrement((volatile signed __int32 *)v24 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v24 - 3) + 8LL))(*((_QWORD *)v24 - 3));
      v25 = *v14 - 49;
      if ( *v14 == 49 )
        v25 = v14[1];
      v26 = lpCaption;
      v27 = lpText;
      if ( !v25 || !(unsigned int)_o__wcsicmp(v14, v20) )
        MessageBoxW(0, v27, v26, 0);
      if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
      if ( _InterlockedDecrement((volatile signed __int32 *)v26 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
      v28 = (_QWORD *)(v37 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v37 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 8LL))(*v28);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 - 24) + 8LL))(*(_QWORD *)(v20 - 24));
    }
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  v29 = (_QWORD *)(v32 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v32 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 8LL))(*v29);
  v30 = (_QWORD *)(v39 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v39 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
  if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  return 0;
}

```

## disassembly

```asm
0x18000b5e0  mov     [rsp-38h+arg_0], rbx
0x18000b5e5  push    rbp
0x18000b5e6  push    rsi
0x18000b5e7  push    rdi
0x18000b5e8  push    r12
0x18000b5ea  push    r13
0x18000b5ec  push    r14
0x18000b5ee  push    r15
0x18000b5f0  mov     rbp, rsp
0x18000b5f3  sub     rsp, 60h
0x18000b5f7  mov     rsi, rcx
0x18000b5fa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b601  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b608  mov     rcx, r14
0x18000b60b  mov     rax, [rax+18h]
0x18000b60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b614  add     rax, 18h
0x18000b618  mov     [rbp+pszPath], rax
0x18000b61c  lea     rdx, [rbp+pszPath]
0x18000b620  xor     ecx, ecx; hModule
0x18000b622  call    ?GetModuleFileNameW@Win32Helpers@@YAJPEAUHINSTANCE__@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Win32Helpers::GetModuleFileNameW(HINSTANCE__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000b627  mov     ebx, eax
0x18000b629  xor     r13d, r13d
0x18000b62c  test    eax, eax
0x18000b62e  jz      short loc_18000B66B
0x18000b630  mov     eax, 80004005h
0x18000b635  test    ebx, ebx
0x18000b637  cmovns  ebx, eax
0x18000b63a  mov     rdx, [rbp+pszPath]
0x18000b63e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000b642  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b646  mov     ecx, r12d
0x18000b649  lock xadd [rdx+10h], ecx
0x18000b64e  add     ecx, r12d
0x18000b651  test    ecx, ecx
0x18000b653  jg      short loc_18000B664
0x18000b655  mov     rcx, [rdx]
0x18000b658  mov     r8, [rcx]
0x18000b65b  mov     rax, [r8+8]
0x18000b65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b664  mov     eax, ebx
0x18000b666  jmp     loc_18000BB03
0x18000b66b  mov     rcx, [rbp+pszPath]; pszPath
0x18000b66f  call    cs:__imp_PathFindFileNameW
0x18000b675  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000b679  test    rax, rax
0x18000b67c  jnz     short loc_18000B683
0x18000b67e  mov     r8d, r13d
0x18000b681  jmp     short loc_18000B690
0x18000b683  mov     r8, r12
0x18000b686  inc     r8
0x18000b689  cmp     [rax+r8*2], r13w
0x18000b68e  jnz     short loc_18000B686
0x18000b690  mov     rdx, rax
0x18000b693  lea     rcx, [rbp+pszPath]
0x18000b697  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000b69c  lea     rdx, aIechooserExe; "iechooser.exe"
0x18000b6a3  mov     r15, [rbp+pszPath]
0x18000b6a7  mov     rcx, r15
0x18000b6aa  call    cs:__imp__o__wcsicmp
0x18000b6b0  lea     rcx, aF12breakonscri_0; "F12BREAKONSCRIPT"
0x18000b6b7  lea     rdx, aF12breakonscri; "F12BREAKONSCRIPTCHOOSER"
0x18000b6be  test    eax, eax
0x18000b6c0  cmovnz  rdx, rcx
0x18000b6c4  lea     rcx, [rbp+arg_18]
0x18000b6c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b6cd  lea     rdx, aIechooserExe; "iechooser.exe"
0x18000b6d4  mov     rcx, r15
0x18000b6d7  call    cs:__imp__o__wcsicmp
0x18000b6dd  lea     rcx, aInternetExplor; "(Internet Explorer)"
0x18000b6e4  lea     rdx, aOther; "(Other)"
0x18000b6eb  test    eax, eax
0x18000b6ed  cmovnz  rdx, rcx
0x18000b6f1  lea     rcx, [rbp+var_30]
0x18000b6f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b6fa  nop
0x18000b6fb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b702  mov     rcx, r14
0x18000b705  mov     rax, [rax+18h]
0x18000b709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b70e  add     rax, 18h
0x18000b712  mov     [rbp+pszPath], rax
0x18000b716  mov     rdx, [rbp+arg_18]
0x18000b71a  lea     rcx, [rbp+pszPath]
0x18000b71e  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18000b723  mov     rdi, [rbp+pszPath]
0x18000b727  test    eax, eax
0x18000b729  jz      loc_18000BA71
0x18000b72f  movzx   edx, word ptr [rdi]
0x18000b732  sub     edx, 30h ; '0'
0x18000b735  jnz     short loc_18000B741
0x18000b737  movzx   edx, word ptr [rdi+2]
0x18000b73b  movzx   ecx, r13w
0x18000b73f  sub     edx, ecx
0x18000b741  test    edx, edx
0x18000b743  jz      loc_18000BA71
0x18000b749  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b750  mov     rcx, r14
0x18000b753  mov     rax, [rax+18h]
0x18000b757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75c  add     rax, 18h
0x18000b760  mov     [rbp+var_10], rax
0x18000b764  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b76b  mov     rcx, r14
0x18000b76e  mov     rax, [rax+18h]
0x18000b772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b777  add     rax, 18h
0x18000b77b  mov     [rbp+var_8], rax
0x18000b77f  lea     rdx, [rbp+var_18]
0x18000b783  mov     ecx, [rsi+70h]
0x18000b786  call    ?GetScriptToolInitializeInfo@F12@@YAJW4PluginId@@AEAUScriptToolInitializeInfo@@@Z; F12::GetScriptToolInitializeInfo(PluginId,ScriptToolInitializeInfo &)
0x18000b78b  mov     ebx, eax
0x18000b78d  test    eax, eax
0x18000b78f  jz      loc_18000B862
0x18000b795  mov     eax, 80004005h
0x18000b79a  test    ebx, ebx
0x18000b79c  cmovns  ebx, eax
0x18000b79f  mov     rdx, [rbp+var_8]
0x18000b7a3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000b7a7  mov     eax, r12d
0x18000b7aa  lock xadd [rdx+10h], eax
0x18000b7af  add     eax, r12d
0x18000b7b2  test    eax, eax
0x18000b7b4  jg      short loc_18000B7C5
0x18000b7b6  mov     rcx, [rdx]
0x18000b7b9  mov     rax, [rcx]
0x18000b7bc  mov     rax, [rax+8]
0x18000b7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c5  mov     rdx, [rbp+var_10]
0x18000b7c9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000b7cd  mov     eax, r12d
0x18000b7d0  lock xadd [rdx+10h], eax
0x18000b7d5  add     eax, r12d
0x18000b7d8  test    eax, eax
0x18000b7da  jg      short loc_18000B7EB
0x18000b7dc  mov     rcx, [rdx]
0x18000b7df  mov     rax, [rcx]
0x18000b7e2  mov     rax, [rax+8]
0x18000b7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7eb  lea     rdx, [rdi-18h]
0x18000b7ef  mov     eax, r12d
0x18000b7f2  lock xadd [rdx+10h], eax
0x18000b7f7  add     eax, r12d
0x18000b7fa  test    eax, eax
0x18000b7fc  jg      short loc_18000B80D
0x18000b7fe  mov     rcx, [rdx]
0x18000b801  mov     rax, [rcx]
0x18000b804  mov     rax, [rax+8]
0x18000b808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b80d  mov     rdx, [rbp+var_30]
0x18000b811  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000b815  mov     eax, r12d
0x18000b818  lock xadd [rdx+10h], eax
0x18000b81d  add     eax, r12d
0x18000b820  test    eax, eax
0x18000b822  jg      short loc_18000B833
0x18000b824  mov     rcx, [rdx]
0x18000b827  mov     rax, [rcx]
0x18000b82a  mov     rax, [rax+8]
0x18000b82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b833  mov     rdx, [rbp+arg_18]
0x18000b837  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000b83b  mov     eax, r12d
0x18000b83e  lock xadd [rdx+10h], eax
0x18000b843  add     eax, r12d
0x18000b846  test    eax, eax
0x18000b848  jg      short loc_18000B859
0x18000b84a  mov     rcx, [rdx]
0x18000b84d  mov     rax, [rcx]
0x18000b850  mov     rax, [rax+8]
0x18000b854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b859  lea     rdx, [r15-18h]
0x18000b85d  jmp     loc_18000B646
0x18000b862  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b869  mov     rcx, r14
0x18000b86c  mov     rax, [rax+18h]
0x18000b870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b875  add     rax, 18h
0x18000b879  mov     [rbp+lpCaption], rax
0x18000b87d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b884  mov     rcx, r14
0x18000b887  mov     rax, [rax+18h]
0x18000b88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b890  add     rax, 18h
0x18000b894  mov     [rbp+pszPath], rax
0x18000b898  lea     rdx, aDebugPluginS; "Debug Plugin - %s"
0x18000b89f  lea     rcx, [rbp+pszPath]
0x18000b8a3  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18000b8a8  test    al, al
0x18000b8aa  jnz     short loc_18000B8C2
0x18000b8ac  mov     r8d, 11h
0x18000b8b2  lea     rdx, aDebugPluginS; "Debug Plugin - %s"
0x18000b8b9  lea     rcx, [rbp+pszPath]
0x18000b8bd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000b8c2  mov     rsi, [rbp+var_10]
0x18000b8c6  mov     r8, rsi
0x18000b8c9  mov     rbx, [rbp+pszPath]
0x18000b8cd  mov     rdx, rbx
0x18000b8d0  lea     rcx, [rbp+lpCaption]
0x18000b8d4  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b8d9  lea     rdx, [rbx-18h]
0x18000b8dd  mov     eax, r12d
0x18000b8e0  lock xadd [rdx+10h], eax
0x18000b8e5  add     eax, r12d
0x18000b8e8  test    eax, eax
0x18000b8ea  jg      short loc_18000B8FC
0x18000b8ec  mov     rcx, [rdx]
0x18000b8ef  mov     rax, [rcx]
0x18000b8f2  mov     rax, [rax+8]
0x18000b8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8fb  nop
0x18000b8fc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b903  mov     rcx, r14
0x18000b906  mov     rax, [rax+18h]
0x18000b90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b90f  add     rax, 18h
0x18000b913  mov     [rbp+lpText], rax
0x18000b917  mov     rbx, [rbp+arg_18]
0x18000b91b  mov     r14, [rbp+var_30]
0x18000b91f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b926  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000b92d  mov     rax, [rax+18h]
0x18000b931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b936  add     rax, 18h
0x18000b93a  mov     [rbp+pszPath], rax
0x18000b93e  lea     rdx, aLaunchingSAtta; "Launching %s...\n\nAttach script debugg"...
0x18000b945  lea     rcx, [rbp+pszPath]
0x18000b949  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18000b94e  test    al, al
0x18000b950  jnz     short loc_18000B968
0x18000b952  mov     r8d, 0C4h
0x18000b958  lea     rdx, aLaunchingSAtta; "Launching %s...\n\nAttach script debugg"...
0x18000b95f  lea     rcx, [rbp+pszPath]
0x18000b963  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000b968  mov     [rsp+60h+var_40], rbx
0x18000b96d  mov     r9, r14
0x18000b970  mov     r8, rsi
0x18000b973  mov     rbx, [rbp+pszPath]
0x18000b977  mov     rdx, rbx
0x18000b97a  lea     rcx, [rbp+lpText]
0x18000b97e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b983  lea     rdx, [rbx-18h]
0x18000b987  mov     eax, r12d
0x18000b98a  lock xadd [rdx+10h], eax
0x18000b98f  add     eax, r12d
0x18000b992  test    eax, eax
0x18000b994  jg      short loc_18000B9A6
0x18000b996  mov     rcx, [rdx]
0x18000b999  mov     rax, [rcx]
0x18000b99c  mov     rax, [rax+8]
0x18000b9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a5  nop
0x18000b9a6  movzx   edx, word ptr [rdi]
0x18000b9a9  sub     edx, 31h ; '1'
0x18000b9ac  jnz     short loc_18000B9B8
0x18000b9ae  movzx   edx, word ptr [rdi+2]
0x18000b9b2  movzx   ecx, r13w
0x18000b9b6  sub     edx, ecx
0x18000b9b8  mov     r14, [rbp+lpCaption]
0x18000b9bc  mov     rbx, [rbp+lpText]
0x18000b9c0  test    edx, edx
0x18000b9c2  jz      short loc_18000B9D4
0x18000b9c4  mov     rdx, rsi
0x18000b9c7  mov     rcx, rdi
0x18000b9ca  call    cs:__imp__o__wcsicmp
0x18000b9d0  test    eax, eax
0x18000b9d2  jnz     short loc_18000B9E5
0x18000b9d4  xor     r9d, r9d; uType
0x18000b9d7  mov     r8, r14; lpCaption
0x18000b9da  mov     rdx, rbx; lpText
0x18000b9dd  xor     ecx, ecx; hWnd
0x18000b9df  call    cs:__imp_MessageBoxW
0x18000b9e5  lea     rdx, [rbx-18h]
0x18000b9e9  mov     eax, r12d
0x18000b9ec  lock xadd [rdx+10h], eax
0x18000b9f1  add     eax, r12d
0x18000b9f4  test    eax, eax
0x18000b9f6  jg      short loc_18000BA07
0x18000b9f8  mov     rcx, [rdx]
0x18000b9fb  mov     rax, [rcx]
0x18000b9fe  mov     rax, [rax+8]
0x18000ba02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba07  lea     rdx, [r14-18h]
0x18000ba0b  mov     eax, r12d
0x18000ba0e  lock xadd [rdx+10h], eax
0x18000ba13  add     eax, r12d
0x18000ba16  test    eax, eax
0x18000ba18  jg      short loc_18000BA29
0x18000ba1a  mov     rcx, [rdx]
0x18000ba1d  mov     rax, [rcx]
0x18000ba20  mov     rax, [rax+8]
0x18000ba24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba29  mov     rdx, [rbp+var_8]
0x18000ba2d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000ba31  mov     eax, r12d
0x18000ba34  lock xadd [rdx+10h], eax
0x18000ba39  add     eax, r12d
0x18000ba3c  test    eax, eax
0x18000ba3e  jg      short loc_18000BA4F
0x18000ba40  mov     rcx, [rdx]
  ... truncated ...
```

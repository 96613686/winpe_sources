# CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)

- ea: `0x180192acc`
- end: `0x180192ed6`
- name: `?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `1034`
- prototype: `int(CbsOfflineUtil *__hidden this, const wchar_t *, struct ICbsSession **)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180192920`
- `0x180193290`
- `0x180193400`
- `0x180193540`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000ba40`
- `0x180010820`
- `0x180192acc`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192d18`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b23`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b48`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b65`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b23`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b48`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180192b65`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192c2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192cba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192d07`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192c2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192cba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180192d07`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180192c63`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180192c63`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180192bb3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180192bb3`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180192d6a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180192d6a`

## string_xrefs

- `0x180192b1c`: `Cbscore.dll`
- `0x180192b5e`: `servicing_unittests_offline.dll`
- `0x180192b3b`: `cbs_unittests_offline.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  void (*Release)(void); // rax
  FARPROC ProcAddress; // rax
  signed int v12; // eax
  unsigned int v13; // edi
  HMODULE v14; // rcx
  FARPROC v15; // rax
  signed int v16; // eax
  FARPROC v17; // rax
  signed int v18; // eax
  _QWORD *v19; // rdi
  HRESULT Malloc; // eax
  unsigned int v21; // esi
  __int64 v22; // rdx
  __int64 (__fastcall *v23)(); // [rsp+20h] [rbp-60h]
  HMODULE phModule; // [rsp+50h] [rbp-30h] BYREF
  HMODULE v25; // [rsp+58h] [rbp-28h] BYREF
  HMODULE v26; // [rsp+60h] [rbp-20h] BYREF
  struct ICbsSession *v27; // [rsp+68h] [rbp-18h] BYREF
  LPMALLOC ppMalloc; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  ppMalloc = 0;
  v27 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    phModule = 0;
    if ( GetModuleHandleExW(2u, L"Cbscore.dll", &phModule) )
    {
      v25 = 0;
      v26 = 0;
      if ( !GetModuleHandleExW(2u, L"cbs_unittests_offline.dll", &v25)
        && !GetModuleHandleExW(2u, L"servicing_unittests_offline.dll", &v26)
        && phModule != (HMODULE)0x180000000LL )
      {
        Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
        if ( ppMalloc )
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        return 2147942450LL;
      }
    }
    Library = LoadLibraryExW(a2, 0, 8u);
    if ( *((_QWORD *)this + 1) )
      goto LABEL_56;
    *((_QWORD *)this + 1) = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 == -2147024770 )
        v9 = -2147467263;
      Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
      if ( !ppMalloc )
        return v9;
      Release = (void (*)(void))ppMalloc->lpVtbl->Release;
      goto LABEL_17;
    }
    ProcAddress = GetProcAddress(Library, "CbsCoreInitialize");
    *((_QWORD *)this + 12) = ProcAddress;
    if ( !ProcAddress )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_22:
      v14 = (HMODULE)*((_QWORD *)this + 1);
      if ( v14 )
      {
        if ( !FreeLibrary(v14) )
        {
          GetLastError();
          __fastfail(7u);
        }
        *((_QWORD *)this + 1) = 0;
      }
      Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
      if ( ppMalloc )
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      return v13;
    }
    v15 = GetProcAddress(*((HMODULE *)this + 1), "CbsCoreFinalize");
    *((_QWORD *)this + 13) = v15;
    if ( !v15 )
    {
      v16 = GetLastError();
      v13 = v16;
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      *((_QWORD *)this + 12) = 0;
      goto LABEL_22;
    }
    if ( g_TestMode )
    {
      v17 = GetProcAddress(*((HMODULE *)this + 1), "SetTestMode");
      if ( !v17 )
      {
        v18 = GetLastError();
        v13 = v18;
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
        *((_QWORD *)this + 12) = 0;
        *((_QWORD *)this + 13) = 0;
        goto LABEL_22;
      }
      ((void (__fastcall *)(__int64))v17)(1);
    }
  }
  v19 = (_QWORD *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
    goto LABEL_50;
  if ( ppMalloc )
    goto LABEL_56;
  Malloc = CoGetMalloc(1u, &ppMalloc);
  v21 = Malloc;
  if ( Malloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
      (const char *)(unsigned int)Malloc,
      (int)v23);
    Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
    if ( ppMalloc )
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    return v21;
  }
  if ( *v19 )
  {
LABEL_56:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180192ED5LL);
  }
  v23 = CbsUtilInstanceDestroyed;
  v9 = (*((__int64 (__fastcall **)(LPMALLOC, void *, void (*)(const wchar_t *const), __int64 (__fastcall *)()))this + 12))(
         ppMalloc,
         &MinimizeFixUp::GetFlag,
         wil_StagingConfig_LogFeatureProcessUsage,
         CbsUtilInstanceCreated);
  if ( (v9 & 0x80000000) != 0 )
  {
    v22 = 226;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
      (const char *)v9,
      (int)v23);
    Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
    if ( !ppMalloc )
      return v9;
    Release = (void (*)(void))ppMalloc->lpVtbl->Release;
LABEL_17:
    Release();
    return v9;
  }
LABEL_50:
  if ( v27 )
    goto LABEL_56;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct ICbsSession **))(*(_QWORD *)*v19 + 24LL))(
         *v19,
         0,
         &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
         &v27);
  if ( (v9 & 0x80000000) != 0 )
  {
    v22 = 233;
    goto LABEL_48;
  }
  *a3 = v27;
  v27 = 0;
  Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(&v27);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  return 0;
}

```

## disassembly

```asm
0x180192acc  mov     [rsp-28h+arg_18], rbx
0x180192ad1  push    rbp
0x180192ad2  push    rsi
0x180192ad3  push    rdi
0x180192ad4  push    r14
0x180192ad6  push    r15
0x180192ad8  mov     rbp, rsp
0x180192adb  sub     rsp, 80h
0x180192ae2  mov     rax, cs:__security_cookie
0x180192ae9  xor     rax, rsp
0x180192aec  mov     [rbp+var_8], rax
0x180192af0  xor     r15d, r15d
0x180192af3  mov     r14, r8
0x180192af6  mov     rdi, rdx
0x180192af9  mov     rbx, rcx
0x180192afc  mov     [rbp+ppMalloc], r15
0x180192b00  mov     [rbp+var_18], r15
0x180192b04  cmp     [rcx+8], r15
0x180192b08  jnz     loc_180192D4A
0x180192b0e  lea     esi, [r15+2]
0x180192b12  mov     [rbp+phModule], r15
0x180192b16  mov     ecx, esi; dwFlags
0x180192b18  lea     r8, [rbp+phModule]; phModule
0x180192b1c  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x180192b23  call    cs:__imp_GetModuleHandleExW
0x180192b2a  nop     dword ptr [rax+rax+00h]
0x180192b2f  test    eax, eax
0x180192b31  jz      short loc_180192BAA
0x180192b33  lea     r8, [rbp+var_28]; phModule
0x180192b37  mov     [rbp+var_28], r15
0x180192b3b  lea     rdx, aCbsUnittestsOf; "cbs_unittests_offline.dll"
0x180192b42  mov     [rbp+var_20], r15
0x180192b46  mov     ecx, esi; dwFlags
0x180192b48  call    cs:__imp_GetModuleHandleExW
0x180192b4f  nop     dword ptr [rax+rax+00h]
0x180192b54  test    eax, eax
0x180192b56  jnz     short loc_180192BAA
0x180192b58  lea     r8, [rbp+var_20]; phModule
0x180192b5c  mov     ecx, esi; dwFlags
0x180192b5e  lea     rdx, aServicingUnitt; "servicing_unittests_offline.dll"
0x180192b65  call    cs:__imp_GetModuleHandleExW
0x180192b6c  nop     dword ptr [rax+rax+00h]
0x180192b71  test    eax, eax
0x180192b73  jnz     short loc_180192BAA
0x180192b75  lea     rax, cs:180000000h
0x180192b7c  cmp     [rbp+phModule], rax
0x180192b80  jz      short loc_180192BAA
0x180192b82  lea     rcx, [rbp+var_18]
0x180192b86  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192b8b  mov     rcx, [rbp+ppMalloc]
0x180192b8f  test    rcx, rcx
0x180192b92  jz      short loc_180192BA0
0x180192b94  mov     rax, [rcx]
0x180192b97  mov     rax, [rax+10h]
0x180192b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ba0  mov     eax, 80070032h
0x180192ba5  jmp     loc_180192EA7
0x180192baa  xor     edx, edx; hFile
0x180192bac  mov     rcx, rdi; lpLibFileName
0x180192baf  lea     r8d, [rdx+8]; dwFlags
0x180192bb3  call    cs:__imp_LoadLibraryExW
0x180192bba  nop     dword ptr [rax+rax+00h]
0x180192bbf  cmp     [rbx+8], r15
0x180192bc3  jnz     loc_180192ECB
0x180192bc9  mov     [rbx+8], rax
0x180192bcd  test    rax, rax
0x180192bd0  jnz     short loc_180192C20
0x180192bd2  call    cs:__imp_GetLastError
0x180192bd9  nop     dword ptr [rax+rax+00h]
0x180192bde  mov     ebx, eax
0x180192be0  test    eax, eax
0x180192be2  jle     short loc_180192BED
0x180192be4  movzx   ebx, ax
0x180192be7  or      ebx, 80070000h
0x180192bed  mov     eax, 80004001h
0x180192bf2  lea     rcx, [rbp+var_18]
0x180192bf6  cmp     ebx, 8007007Eh
0x180192bfc  cmovz   ebx, eax
0x180192bff  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192c04  mov     rcx, [rbp+ppMalloc]
0x180192c08  test    rcx, rcx
0x180192c0b  jz      short loc_180192C19
0x180192c0d  mov     rdx, [rcx]
0x180192c10  mov     rax, [rdx+10h]
0x180192c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192c19  mov     eax, ebx
0x180192c1b  jmp     loc_180192EA7
0x180192c20  lea     rdx, aCbscoreinitial; "CbsCoreInitialize"
0x180192c27  mov     rcx, rax; hModule
0x180192c2a  call    cs:__imp_GetProcAddress
0x180192c31  nop     dword ptr [rax+rax+00h]
0x180192c36  mov     [rbx+60h], rax
0x180192c3a  test    rax, rax
0x180192c3d  jnz     short loc_180192CAF
0x180192c3f  call    cs:__imp_GetLastError
0x180192c46  nop     dword ptr [rax+rax+00h]
0x180192c4b  mov     edi, eax
0x180192c4d  test    eax, eax
0x180192c4f  jle     short loc_180192C5A
0x180192c51  movzx   edi, ax
0x180192c54  or      edi, 80070000h
0x180192c5a  mov     rcx, [rbx+8]; hLibModule
0x180192c5e  test    rcx, rcx
0x180192c61  jz      short loc_180192C8A
0x180192c63  call    cs:__imp_FreeLibrary
0x180192c6a  nop     dword ptr [rax+rax+00h]
0x180192c6f  test    eax, eax
0x180192c71  jnz     short loc_180192C86
0x180192c73  call    cs:__imp_GetLastError
0x180192c7a  nop     dword ptr [rax+rax+00h]
0x180192c7f  mov     ecx, 7
0x180192c84  int     29h; Win8: RtlFailFast(ecx)
0x180192c86  mov     [rbx+8], r15
0x180192c8a  lea     rcx, [rbp+var_18]
0x180192c8e  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192c93  mov     rcx, [rbp+ppMalloc]
0x180192c97  test    rcx, rcx
0x180192c9a  jz      short loc_180192CA8
0x180192c9c  mov     rdx, [rcx]
0x180192c9f  mov     rax, [rdx+10h]
0x180192ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ca8  mov     eax, edi
0x180192caa  jmp     loc_180192EA7
0x180192caf  mov     rcx, [rbx+8]; hModule
0x180192cb3  lea     rdx, aCbscorefinaliz; "CbsCoreFinalize"
0x180192cba  call    cs:__imp_GetProcAddress
0x180192cc1  nop     dword ptr [rax+rax+00h]
0x180192cc6  mov     [rbx+68h], rax
0x180192cca  test    rax, rax
0x180192ccd  jnz     short loc_180192CF3
0x180192ccf  call    cs:__imp_GetLastError
0x180192cd6  nop     dword ptr [rax+rax+00h]
0x180192cdb  mov     edi, eax
0x180192cdd  test    eax, eax
0x180192cdf  jle     short loc_180192CEA
0x180192ce1  movzx   edi, ax
0x180192ce4  or      edi, 80070000h
0x180192cea  mov     [rbx+60h], r15
0x180192cee  jmp     loc_180192C5A
0x180192cf3  cmp     cs:?g_TestMode@@3_NA, r15b; bool g_TestMode
0x180192cfa  jz      short loc_180192D4A
0x180192cfc  mov     rcx, [rbx+8]; hModule
0x180192d00  lea     rdx, aSettestmode; "SetTestMode"
0x180192d07  call    cs:__imp_GetProcAddress
0x180192d0e  nop     dword ptr [rax+rax+00h]
0x180192d13  test    rax, rax
0x180192d16  jnz     short loc_180192D40
0x180192d18  call    cs:__imp_GetLastError
0x180192d1f  nop     dword ptr [rax+rax+00h]
0x180192d24  mov     edi, eax
0x180192d26  test    eax, eax
0x180192d28  jle     short loc_180192D33
0x180192d2a  movzx   edi, ax
0x180192d2d  or      edi, 80070000h
0x180192d33  mov     [rbx+60h], r15
0x180192d37  mov     [rbx+68h], r15
0x180192d3b  jmp     loc_180192C5A
0x180192d40  mov     ecx, 1
0x180192d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192d4a  lea     rdi, [rbx+70h]
0x180192d4e  cmp     [rdi], r15
0x180192d51  jnz     loc_180192E4D
0x180192d57  cmp     [rbp+ppMalloc], r15
0x180192d5b  jnz     loc_180192ECB
0x180192d61  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x180192d65  mov     ecx, 1; dwMemContext
0x180192d6a  call    cs:__imp_CoGetMalloc
0x180192d71  nop     dword ptr [rax+rax+00h]
0x180192d76  mov     esi, eax
0x180192d78  test    eax, eax
0x180192d7a  jns     short loc_180192DB9
0x180192d7c  mov     rcx, [rbp+28h]; this
0x180192d80  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x180192d87  mov     r9d, eax; char *
0x180192d8a  mov     edx, 0D4h; void *
0x180192d8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192d94  lea     rcx, [rbp+var_18]
0x180192d98  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192d9d  mov     rcx, [rbp+ppMalloc]
0x180192da1  test    rcx, rcx
0x180192da4  jz      short loc_180192DB2
0x180192da6  mov     rax, [rcx]
0x180192da9  mov     rax, [rax+10h]
0x180192dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192db2  mov     eax, esi
0x180192db4  jmp     loc_180192EA7
0x180192db9  cmp     [rdi], r15
0x180192dbc  jnz     loc_180192ECB
0x180192dc2  mov     rcx, [rbp+ppMalloc]
0x180192dc6  lea     rax, wil_StagingConfig_LogFeatureProcessUsage
0x180192dcd  mov     [rsp+80h+var_48], rdi
0x180192dd2  lea     r9, CbsUtilInstanceCreated
0x180192dd9  mov     [rsp+80h+var_50], rax
0x180192dde  lea     r8, wil_StagingConfig_LogFeatureProcessUsage
0x180192de5  lea     rax, wil_StagingConfig_LogFeatureProcessUsage
0x180192dec  mov     [rsp+80h+var_58], rax
0x180192df1  lea     rdx, ?GetFlag@MinimizeFixUp@@UEBA?AW4FixUpFlags@SecurityDescriptor@Rtl@Windows@@XZ; MinimizeFixUp::GetFlag(void)
0x180192df8  lea     rax, CbsUtilInstanceDestroyed
0x180192dff  mov     qword ptr [rsp+80h+var_60], rax; int
0x180192e04  mov     rax, [rbx+60h]
0x180192e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192e0d  mov     ebx, eax
0x180192e0f  test    eax, eax
0x180192e11  jns     short loc_180192E4D
0x180192e13  mov     edx, 0E2h; void *
0x180192e18  mov     rcx, [rbp+28h]; this
0x180192e1c  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x180192e23  mov     r9d, ebx; char *
0x180192e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192e2b  lea     rcx, [rbp+var_18]
0x180192e2f  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192e34  mov     rcx, [rbp+ppMalloc]
0x180192e38  test    rcx, rcx
0x180192e3b  jz      loc_180192C19
0x180192e41  mov     rax, [rcx]
0x180192e44  mov     rax, [rax+10h]
0x180192e48  jmp     loc_180192C14
0x180192e4d  cmp     [rbp+var_18], r15
0x180192e51  jnz     short loc_180192ECB
0x180192e53  mov     rcx, [rdi]
0x180192e56  lea     r9, [rbp+var_18]
0x180192e5a  lea     r8, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed
0x180192e61  xor     edx, edx
0x180192e63  mov     rax, [rcx]
0x180192e66  mov     rax, [rax+18h]
0x180192e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192e6f  mov     ebx, eax
0x180192e71  test    eax, eax
0x180192e73  jns     short loc_180192E7C
0x180192e75  mov     edx, 0E9h
0x180192e7a  jmp     short loc_180192E18
0x180192e7c  mov     rax, [rbp+var_18]
0x180192e80  lea     rcx, [rbp+var_18]
0x180192e84  mov     [r14], rax
0x180192e87  mov     [rbp+var_18], r15
0x180192e8b  call    ??1?$AutoComPtr@UICbsPackage@@@Windows@@QEAA@XZ; Windows::AutoComPtr<ICbsPackage>::~AutoComPtr<ICbsPackage>(void)
0x180192e90  mov     rcx, [rbp+ppMalloc]
0x180192e94  test    rcx, rcx
0x180192e97  jz      short loc_180192EA5
0x180192e99  mov     rax, [rcx]
0x180192e9c  mov     rax, [rax+10h]
0x180192ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ea5  xor     eax, eax
0x180192ea7  mov     rcx, [rbp+var_8]
0x180192eab  xor     rcx, rsp; StackCookie
0x180192eae  call    __security_check_cookie
0x180192eb3  mov     rbx, [rsp+80h+arg_18]
0x180192ebb  add     rsp, 80h
0x180192ec2  pop     r15
0x180192ec4  pop     r14
0x180192ec6  pop     rdi
0x180192ec7  pop     rsi
0x180192ec8  pop     rbp
0x180192ec9  retn
0x180192ecb  mov     ecx, 0C00000E5h; int
0x180192ed0  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

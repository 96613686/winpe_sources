# CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)

- ea: `0x140024604`
- end: `0x14002497a`
- name: `?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, const wchar_t *, struct ICbsSession **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400244a0`
- `0x140024de0`
- `0x140024ed0`
- `0x140024fe0`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x14000731c`
- `0x140012a00`
- `0x140024604`
- `0x140024aa0`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14002465c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14002467d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140024695`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14002465c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x14002467d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140024695`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140024766`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002479e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400247db`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140024766`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x14002479e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400247db`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400246ed`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400246ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400247e6`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14002482f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14002482f`

## string_xrefs

- `0x140024651`: `Cbscore.dll`
- `0x14002466e`: `cbs_unittests_offline.dll`
- `0x14002468b`: `servicing_unittests_offline.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  HMODULE *v3; // rdi
  HMODULE Library; // rax
  int v9; // ecx
  signed int LastError; // eax
  int Malloc; // ebx
  void (*Release)(void); // rax
  FARPROC ProcAddress; // rax
  signed int v14; // eax
  FARPROC v15; // rax
  signed int v16; // eax
  FARPROC v17; // rax
  signed int v18; // eax
  __int64 *v19; // rdi
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  struct ICbsSession *v25; // rax
  LPMALLOC v26; // rcx
  __int64 (__fastcall *v27)(); // [rsp+20h] [rbp-60h]
  HMODULE phModule; // [rsp+50h] [rbp-30h] BYREF
  HMODULE v29; // [rsp+58h] [rbp-28h] BYREF
  HMODULE v30; // [rsp+60h] [rbp-20h] BYREF
  struct ICbsSession *v31; // [rsp+68h] [rbp-18h] BYREF
  LPMALLOC ppMalloc; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = (HMODULE *)((char *)this + 8);
  ppMalloc = 0;
  v31 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    phModule = 0;
    if ( GetModuleHandleExW(2u, L"Cbscore.dll", &phModule) )
    {
      v29 = 0;
      v30 = 0;
      if ( !GetModuleHandleExW(2u, L"cbs_unittests_offline.dll", &v29)
        && !GetModuleHandleExW(2u, L"servicing_unittests_offline.dll", &v30)
        && phModule != (HMODULE)0x140000000LL )
      {
        if ( v31 )
        {
          (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v31 + 16LL))(v31);
          v31 = 0;
        }
        if ( ppMalloc )
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        return 2147942450LL;
      }
    }
    Library = LoadLibraryExW(a2, 0, 8u);
    if ( *v3 )
      INTERNAL_ERROR_ACTION(v9);
    *v3 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      Malloc = LastError;
      if ( LastError > 0 )
        Malloc = (unsigned __int16)LastError | 0x80070000;
      if ( Malloc == -2147024770 )
        Malloc = -2147467263;
      goto LABEL_17;
    }
    ProcAddress = GetProcAddress(Library, "CbsCoreInitialize");
    *((_QWORD *)this + 12) = ProcAddress;
    if ( !ProcAddress )
    {
      v14 = GetLastError();
      Malloc = v14;
      if ( v14 > 0 )
        Malloc = (unsigned __int16)v14 | 0x80070000;
LABEL_26:
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(v3);
LABEL_17:
      if ( v31 )
      {
        (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
      if ( !ppMalloc )
        return (unsigned int)Malloc;
      Release = (void (*)(void))ppMalloc->lpVtbl->Release;
LABEL_21:
      Release();
      return (unsigned int)Malloc;
    }
    v15 = GetProcAddress(*v3, "CbsCoreFinalize");
    *((_QWORD *)this + 13) = v15;
    if ( !v15 )
    {
      v16 = GetLastError();
      Malloc = v16;
      if ( v16 > 0 )
        Malloc = (unsigned __int16)v16 | 0x80070000;
      *((_QWORD *)this + 12) = 0;
      goto LABEL_26;
    }
    if ( g_TestMode )
    {
      v17 = GetProcAddress(*v3, "SetTestMode");
      if ( !v17 )
      {
        v18 = GetLastError();
        Malloc = v18;
        if ( v18 > 0 )
          Malloc = (unsigned __int16)v18 | 0x80070000;
        *((_QWORD *)this + 12) = 0;
        *((_QWORD *)this + 13) = 0;
        goto LABEL_26;
      }
      ((void (__fastcall *)(__int64))v17)(1);
    }
  }
  v19 = (__int64 *)((char *)this + 112);
  if ( !*((_QWORD *)this + 14) )
  {
    if ( ppMalloc )
      INTERNAL_ERROR_ACTION((int)this);
    Malloc = CoGetMalloc(1u, &ppMalloc);
    if ( Malloc < 0 )
    {
      v21 = 212;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
        (const char *)(unsigned int)Malloc,
        (int)v27);
      if ( v31 )
      {
        (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
      if ( !ppMalloc )
        return (unsigned int)Malloc;
      Release = (void (*)(void))ppMalloc->lpVtbl->Release;
      goto LABEL_21;
    }
    if ( *v19 )
      INTERNAL_ERROR_ACTION(v20);
    v27 = CbsUtilInstanceDestroyed;
    Malloc = (*((__int64 (__fastcall **)(LPMALLOC, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)()))this + 12))(
               ppMalloc,
               &CCbsLogMonitorProvider::Init,
               wil_StagingConfig_LogFeatureProcessUsage,
               CbsUtilInstanceCreated);
    if ( Malloc < 0 )
    {
      v21 = 226;
      goto LABEL_41;
    }
  }
  v22 = *v19;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v22 + 24LL);
  InitPointer = Windows::AutoComPtr<ICbsSession>::GetInitPointer(&v31);
  Malloc = v23(v22, 0, &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed, InitPointer);
  if ( Malloc < 0 )
  {
    v21 = 233;
    goto LABEL_41;
  }
  v25 = v31;
  v26 = ppMalloc;
  v31 = 0;
  *a3 = v25;
  if ( v26 )
    ((void (__fastcall *)(LPMALLOC))v26->lpVtbl->Release)(v26);
  return 0;
}

```

## disassembly

```asm
0x140024604  mov     [rsp-28h+arg_18], rbx
0x140024609  push    rbp
0x14002460a  push    rsi
0x14002460b  push    rdi
0x14002460c  push    r14
0x14002460e  push    r15
0x140024610  mov     rbp, rsp
0x140024613  sub     rsp, 80h
0x14002461a  mov     rax, cs:__security_cookie
0x140024621  xor     rax, rsp
0x140024624  mov     [rbp+var_8], rax
0x140024628  xor     r15d, r15d
0x14002462b  lea     rdi, [rcx+8]
0x14002462f  mov     r14, r8
0x140024632  mov     rbx, rdx
0x140024635  mov     rsi, rcx
0x140024638  mov     [rbp+ppMalloc], r15
0x14002463c  mov     [rbp+var_18], r15
0x140024640  cmp     [rdi], r15
0x140024643  jnz     loc_14002480F
0x140024649  lea     r8, [rbp+phModule]; phModule
0x14002464d  mov     [rbp+phModule], r15
0x140024651  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x140024658  lea     ecx, [r15+2]; dwFlags
0x14002465c  call    cs:__imp_GetModuleHandleExW
0x140024662  test    eax, eax
0x140024664  jz      short loc_1400246E4
0x140024666  lea     r8, [rbp+var_28]; phModule
0x14002466a  mov     [rbp+var_28], r15
0x14002466e  lea     rdx, aCbsUnittestsOf; "cbs_unittests_offline.dll"
0x140024675  mov     [rbp+var_20], r15
0x140024679  lea     ecx, [r15+2]; dwFlags
0x14002467d  call    cs:__imp_GetModuleHandleExW
0x140024683  test    eax, eax
0x140024685  jnz     short loc_1400246E4
0x140024687  lea     r8, [rbp+var_20]; phModule
0x14002468b  lea     rdx, aServicingUnitt; "servicing_unittests_offline.dll"
0x140024692  lea     ecx, [rax+2]; dwFlags
0x140024695  call    cs:__imp_GetModuleHandleExW
0x14002469b  test    eax, eax
0x14002469d  jnz     short loc_1400246E4
0x14002469f  lea     rax, cs:140000000h
0x1400246a6  cmp     [rbp+phModule], rax
0x1400246aa  jz      short loc_1400246E4
0x1400246ac  mov     rcx, [rbp+var_18]
0x1400246b0  test    rcx, rcx
0x1400246b3  jz      short loc_1400246C5
0x1400246b5  mov     rax, [rcx]
0x1400246b8  mov     rax, [rax+10h]
0x1400246bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400246c1  mov     [rbp+var_18], r15
0x1400246c5  mov     rcx, [rbp+ppMalloc]
0x1400246c9  test    rcx, rcx
0x1400246cc  jz      short loc_1400246DA
0x1400246ce  mov     rax, [rcx]
0x1400246d1  mov     rax, [rax+10h]
0x1400246d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400246da  mov     eax, 80070032h
0x1400246df  jmp     loc_140024945
0x1400246e4  xor     edx, edx; hFile
0x1400246e6  mov     rcx, rbx; lpLibFileName
0x1400246e9  lea     r8d, [rdx+8]; dwFlags
0x1400246ed  call    cs:__imp_LoadLibraryExW
0x1400246f3  cmp     [rdi], r15
0x1400246f6  jnz     loc_14002496E
0x1400246fc  mov     [rdi], rax
0x1400246ff  test    rax, rax
0x140024702  jnz     short loc_14002475C
0x140024704  call    cs:__imp_GetLastError
0x14002470a  mov     ebx, eax
0x14002470c  test    eax, eax
0x14002470e  jle     short loc_140024719
0x140024710  movzx   ebx, ax
0x140024713  or      ebx, 80070000h
0x140024719  cmp     ebx, 8007007Eh
0x14002471f  mov     eax, 80004001h
0x140024724  cmovz   ebx, eax
0x140024727  mov     rcx, [rbp+var_18]
0x14002472b  test    rcx, rcx
0x14002472e  jz      short loc_140024740
0x140024730  mov     rax, [rcx]
0x140024733  mov     rax, [rax+10h]
0x140024737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002473c  mov     [rbp+var_18], r15
0x140024740  mov     rcx, [rbp+ppMalloc]
0x140024744  test    rcx, rcx
0x140024747  jz      short loc_140024755
0x140024749  mov     rdx, [rcx]
0x14002474c  mov     rax, [rdx+10h]
0x140024750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024755  mov     eax, ebx
0x140024757  jmp     loc_140024945
0x14002475c  lea     rdx, aCbscoreinitial; "CbsCoreInitialize"
0x140024763  mov     rcx, rax; hModule
0x140024766  call    cs:__imp_GetProcAddress
0x14002476c  mov     [rsi+60h], rax
0x140024770  test    rax, rax
0x140024773  jnz     short loc_140024794
0x140024775  call    cs:__imp_GetLastError
0x14002477b  mov     ebx, eax
0x14002477d  test    eax, eax
0x14002477f  jle     short loc_14002478A
0x140024781  movzx   ebx, ax
0x140024784  or      ebx, 80070000h
0x14002478a  mov     rcx, rdi
0x14002478d  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140024792  jmp     short loc_140024727
0x140024794  mov     rcx, [rdi]; hModule
0x140024797  lea     rdx, aCbscorefinaliz; "CbsCoreFinalize"
0x14002479e  call    cs:__imp_GetProcAddress
0x1400247a4  mov     [rsi+68h], rax
0x1400247a8  test    rax, rax
0x1400247ab  jnz     short loc_1400247C8
0x1400247ad  call    cs:__imp_GetLastError
0x1400247b3  mov     ebx, eax
0x1400247b5  test    eax, eax
0x1400247b7  jle     short loc_1400247C2
0x1400247b9  movzx   ebx, ax
0x1400247bc  or      ebx, 80070000h
0x1400247c2  mov     [rsi+60h], r15
0x1400247c6  jmp     short loc_14002478A
0x1400247c8  cmp     cs:?g_TestMode@@3_NA, r15b; bool g_TestMode
0x1400247cf  jz      short loc_14002480F
0x1400247d1  mov     rcx, [rdi]; hModule
0x1400247d4  lea     rdx, aSettestmode; "SetTestMode"
0x1400247db  call    cs:__imp_GetProcAddress
0x1400247e1  test    rax, rax
0x1400247e4  jnz     short loc_140024805
0x1400247e6  call    cs:__imp_GetLastError
0x1400247ec  mov     ebx, eax
0x1400247ee  test    eax, eax
0x1400247f0  jle     short loc_1400247FB
0x1400247f2  movzx   ebx, ax
0x1400247f5  or      ebx, 80070000h
0x1400247fb  mov     [rsi+60h], r15
0x1400247ff  mov     [rsi+68h], r15
0x140024803  jmp     short loc_14002478A
0x140024805  mov     ecx, 1
0x14002480a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002480f  lea     rdi, [rsi+70h]
0x140024813  cmp     [rdi], r15
0x140024816  jnz     loc_1400248E9
0x14002481c  cmp     [rbp+ppMalloc], r15
0x140024820  jnz     loc_140024974
0x140024826  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x14002482a  mov     ecx, 1; dwMemContext
0x14002482f  call    cs:__imp_CoGetMalloc
0x140024835  mov     ebx, eax
0x140024837  test    eax, eax
0x140024839  jns     short loc_140024885
0x14002483b  mov     edx, 0D4h; void *
0x140024840  mov     rcx, [rbp+28h]; this
0x140024844  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x14002484b  mov     r9d, ebx; char *
0x14002484e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024853  mov     rcx, [rbp+var_18]
0x140024857  test    rcx, rcx
0x14002485a  jz      short loc_14002486C
0x14002485c  mov     rdx, [rcx]
0x14002485f  mov     rax, [rdx+10h]
0x140024863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024868  mov     [rbp+var_18], r15
0x14002486c  mov     rcx, [rbp+ppMalloc]
0x140024870  test    rcx, rcx
0x140024873  jz      loc_140024755
0x140024879  mov     rax, [rcx]
0x14002487c  mov     rax, [rax+10h]
0x140024880  jmp     loc_140024750
0x140024885  cmp     [rdi], r15
0x140024888  jnz     loc_140024968
0x14002488e  mov     rcx, [rbp+ppMalloc]
0x140024892  lea     rax, wil_StagingConfig_LogFeatureProcessUsage
0x140024899  mov     [rsp+80h+var_48], rdi
0x14002489e  lea     r9, CbsUtilInstanceCreated
0x1400248a5  mov     [rsp+80h+var_50], rax
0x1400248aa  lea     r8, wil_StagingConfig_LogFeatureProcessUsage
0x1400248b1  lea     rax, wil_StagingConfig_LogFeatureProcessUsage
0x1400248b8  mov     [rsp+80h+var_58], rax
0x1400248bd  lea     rdx, ?Init@CCbsLogMonitorProvider@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CCbsLogMonitorProvider::Init(void *,ILogContext *)
0x1400248c4  lea     rax, CbsUtilInstanceDestroyed
0x1400248cb  mov     [rsp+80h+var_60], rax
0x1400248d0  mov     rax, [rsi+60h]
0x1400248d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400248d9  mov     ebx, eax
0x1400248db  test    eax, eax
0x1400248dd  jns     short loc_1400248E9
0x1400248df  mov     edx, 0E2h
0x1400248e4  jmp     loc_140024840
0x1400248e9  mov     rdi, [rdi]
0x1400248ec  lea     rcx, [rbp+var_18]
0x1400248f0  mov     rax, [rdi]
0x1400248f3  mov     rbx, [rax+18h]
0x1400248f7  call    ?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ; Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)
0x1400248fc  mov     r9, rax
0x1400248ff  lea     r8, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed
0x140024906  mov     rax, rbx
0x140024909  xor     edx, edx
0x14002490b  mov     rcx, rdi
0x14002490e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024913  mov     ebx, eax
0x140024915  test    eax, eax
0x140024917  jns     short loc_140024923
0x140024919  mov     edx, 0E9h
0x14002491e  jmp     loc_140024840
0x140024923  mov     rax, [rbp+var_18]
0x140024927  mov     rcx, [rbp+ppMalloc]
0x14002492b  mov     [rbp+var_18], r15
0x14002492f  mov     [r14], rax
0x140024932  test    rcx, rcx
0x140024935  jz      short loc_140024943
0x140024937  mov     rax, [rcx]
0x14002493a  mov     rax, [rax+10h]
0x14002493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024943  xor     eax, eax
0x140024945  mov     rcx, [rbp+var_8]
0x140024949  xor     rcx, rsp; StackCookie
0x14002494c  call    __security_check_cookie
0x140024951  mov     rbx, [rsp+80h+arg_18]
0x140024959  add     rsp, 80h
0x140024960  pop     r15
0x140024962  pop     r14
0x140024964  pop     rdi
0x140024965  pop     rsi
0x140024966  pop     rbp
0x140024967  retn
0x140024968  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x14002496e  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140024974  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

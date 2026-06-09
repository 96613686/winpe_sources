# UninstallWindows

- ea: `0x18007bdb0`
- end: `0x18007c5dc`
- name: `UninstallWindows`
- size: `2092`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *, LPCWSTR lpValue, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001e51c`
- `0x18001ee38`
- `0x18001f660`
- `0x180022eb0`
- `0x180022ef0`
- `0x1800293a0`
- `0x18003e980`
- `0x1800425ac`
- `0x180044050`
- `0x1800448f4`
- `0x1800463d4`
- `0x180046bb4`
- `0x180046df0`
- `0x18007b860`
- `0x18007b994`
- `0x18007baa8`
- `0x18007bb54`
- `0x18007bdb0`
- `0x18007c760`
- `0x18007c9e8`
- `0x18007cd1c`
- `0x18007d190`
- `0x18007d62c`
- `0x1800a0020`

## string_xrefs

- `0x18007be49`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007beec`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007c10d`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007c314`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007c396`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007c4f6`: `onecore\base\cbs\uninstall\uninstallwindows.cpp`
- `0x18007c00f`: `Uninstall is not supported.`

## pseudocode

```c
__int64 __fastcall UninstallWindows(wchar_t *a1, wchar_t *a2, LPCWSTR lpValue, __int64 a4, _DWORD *a5)
{
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // r15
  CUninstallCbsClient *v13; // rax
  const wchar_t *v14; // rdx
  const wchar_t *v15; // r9
  CUninstallCbsClient *v16; // rdi
  int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // rdx
  __int64 v20; // rcx
  char *v21; // rcx
  __int64 v22; // rcx
  char *v23; // rcx
  unsigned __int64 v25; // r12
  unsigned int v26; // r14d
  __int64 v27; // r13
  int v28; // eax
  unsigned __int64 v29; // r14
  unsigned int v30; // esi
  __int64 v31; // r13
  int v32; // r12d
  unsigned __int64 v33; // r14
  unsigned int v34; // esi
  __int64 v35; // r13
  unsigned __int64 v36; // r14
  unsigned int v37; // esi
  __int64 v38; // r13
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  char *v42; // rcx
  char *v43; // rcx
  __int64 v44; // rcx
  char *v45; // rcx
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  const wchar_t *v48; // [rsp+28h] [rbp-D8h]
  char v49[8]; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v50)(_QWORD, __int64); // [rsp+48h] [rbp-B8h] BYREF
  bool v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v53; // [rsp+60h] [rbp-A0h]
  int v54[6]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  _BYTE v57[24]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v58; // [rsp+C8h] [rbp-38h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  _BYTE v60[24]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+118h] [rbp+18h]
  _BYTE v63[24]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v64; // [rsp+148h] [rbp+48h]
  __int64 v65; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v53 = a5;
  v52 = 0;
  v51 = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v63);
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v60);
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v57);
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v54);
  v49[0] = 0;
  if ( !IsWdsLoggerSetup(0) )
  {
    v9 = CbsOfflineSetLogFile(lpValue);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
        (const char *)(unsigned int)v9,
        v46);
      v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
      _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
      v11 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
      if ( !v11 )
      {
LABEL_13:
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
        g_TracingInitialized = 0;
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
        return v10;
      }
LABEL_12:
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 504LL))(v11, 1);
      goto LABEL_13;
    }
  }
  LogAdapter::WdsLoader::LoadWds((LogAdapter::WdsLoader *)v49);
  v50 = 0;
  if ( !Windows::AutoNewPtr<CCbsUninstallUIHandler>::Allocate<>(&v50) )
  {
    if ( v50 )
      (**v50)(v50, 1);
LABEL_9:
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
      (const char *)0x8007000ELL,
      v46);
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v11 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( !v11 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v12 = v50;
  if ( !v50 )
    goto LABEL_9;
  if ( a4 )
    Windows::AutoComPtr<ICbsUIHandler>::operator=(v50 + 4, a4);
  v13 = (CUninstallCbsClient *)operator new(0x18u);
  v16 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
      (const char *)0x8007000ELL,
      v46);
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v44 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v44 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 504LL))(v44, 1);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    g_TracingInitialized = 0;
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
    v45 = (char *)v12 + *((int *)v12[1] + 1) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v45 + 16LL))(v45);
    return v10;
  }
  *(_QWORD *)v13 = 0;
  *((_QWORD *)v13 + 1) = 0;
  *((_QWORD *)v13 + 2) = 0;
  v17 = CUninstallCbsClient::Initialize(
          v13,
          v14,
          a2,
          v15,
          a1,
          v48,
          (struct ICbsUIHandler *)((char *)v12 + *((int *)v12[1] + 1) + 8));
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = 44;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
      (const char *)(unsigned int)v17,
      v47);
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v22 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v22 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 504LL))(v22, 1);
LABEL_31:
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    g_TracingInitialized = 0;
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
    v23 = (char *)v12 + *((int *)v12[1] + 1) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_32:
    CUninstallCbsClient::~CUninstallCbsClient(v16);
    operator delete(v16, (const struct std::nothrow_t *)0x18);
    return v18;
  }
  if ( !CUninstallCbsClient::MultipleEditionsPresent(v16) )
  {
    CBSWdsLog(0x4000000, 0, 0, "Uninstall is not supported.");
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v20 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v20 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 504LL))(v20, 1);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    g_TracingInitialized = 0;
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
    v21 = (char *)v12 + *((int *)v12[1] + 1) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
    v18 = -2146498523;
    goto LABEL_32;
  }
  v17 = CUninstallCbsClient::ListPackagesForUninstall(
          v16,
          (struct CCbsStringArray *)v63,
          (struct CCbsStringArray *)v60,
          (struct CCbsStringArray *)v57,
          (struct CCbsStringArray *)v54);
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = 54;
    goto LABEL_27;
  }
  v25 = v64;
  v26 = 0;
  if ( v64 )
  {
    v27 = v65;
    while ( 1 )
    {
      if ( v26 >= v25 )
        __fastfail(8u);
      v28 = CUninstallCbsClient::UninstallPackage(v16, *(const wchar_t *const *)(v27 + 8LL * v26));
      v18 = v28;
      if ( v28 < 0 )
        break;
      if ( ++v26 >= v25 )
        goto LABEL_39;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
      (const char *)(unsigned int)v28,
      v47);
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v39 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v39 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 504LL))(v39, 1);
    goto LABEL_31;
  }
LABEL_39:
  v29 = v55;
  v30 = 0;
  if ( v55 )
  {
    v31 = v56;
    while ( 1 )
    {
      if ( v30 >= v29 )
        __fastfail(8u);
      v32 = CUninstallCbsClient::UninstallPackage(v16, *(const wchar_t *const *)(v31 + 8LL * v30));
      if ( v32 < 0 )
        break;
      if ( ++v30 >= v29 )
        goto LABEL_45;
    }
    v40 = 63;
    goto LABEL_65;
  }
LABEL_45:
  v33 = v61;
  v34 = 0;
  if ( v61 )
  {
    v35 = v62;
    while ( 1 )
    {
      if ( v34 >= v33 )
        __fastfail(8u);
      v32 = CUninstallCbsClient::UninstallPackage(v16, *(const wchar_t *const *)(v35 + 8LL * v34));
      if ( v32 < 0 )
        break;
      if ( ++v34 >= v33 )
        goto LABEL_51;
    }
    v40 = 68;
    goto LABEL_65;
  }
LABEL_51:
  v36 = v58;
  v37 = 0;
  if ( v58 )
  {
    v38 = v59;
    while ( 1 )
    {
      if ( v37 >= v36 )
        __fastfail(8u);
      v32 = CUninstallCbsClient::UninstallPackage(v16, *(const wchar_t *const *)(v38 + 8LL * v37));
      if ( v32 < 0 )
        break;
      if ( ++v37 >= v36 )
        goto LABEL_57;
    }
    v40 = 73;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\uninstallwindows.cpp",
      (const char *)(unsigned int)v32,
      v47);
    if ( v49[0] )
      WdsUnload();
    v50 = (void (__fastcall ***)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)&BaseAddress, 0);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    _InterlockedExchange64((volatile __int64 *)&ProcedureAddress, 0);
    v41 = _InterlockedExchange64((volatile __int64 *)&Windows::WCP::Implementation::Rtl::g_TracingStream, 0);
    if ( v41 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 504LL))(v41, 1);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(&v50);
    g_TracingInitialized = 0;
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
    v42 = (char *)v12 + *((int *)v12[1] + 1) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v42 + 16LL))(v42);
    v18 = v32;
    goto LABEL_32;
  }
LABEL_57:
  v17 = CUninstallCbsClient::Finalize(v16, &v51);
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = 76;
    goto LABEL_27;
  }
  if ( v53 )
    *v53 = v51;
  LogAdapter::WdsLoader::Close((LogAdapter::WdsLoader *)v49);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v54);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v57);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v60);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v63);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v52);
  v43 = (char *)v12 + *((int *)v12[1] + 1) + 8;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v43 + 16LL))(v43);
  CUninstallCbsClient::~CUninstallCbsClient(v16);
  operator delete(v16, (const struct std::nothrow_t *)0x18);
  return 0;
}

```

## disassembly

```asm
0x18007bdb0  push    rbp
0x18007bdb2  push    rbx
0x18007bdb3  push    rsi
0x18007bdb4  push    rdi
0x18007bdb5  push    r12
0x18007bdb7  push    r13
0x18007bdb9  push    r14
0x18007bdbb  push    r15
0x18007bdbd  lea     rbp, [rsp-88h]
0x18007bdc5  sub     rsp, 188h
0x18007bdcc  mov     rax, cs:__security_cookie
0x18007bdd3  xor     rax, rsp
0x18007bdd6  mov     [rbp+0C0h+var_50], rax
0x18007bdda  mov     rax, [rbp+0C0h+arg_20]
0x18007bde1  mov     r14, rcx
0x18007bde4  xor     r13d, r13d
0x18007bde7  mov     [rsp+1C0h+var_160], rax
0x18007bdec  lea     rcx, [rbp+0C0h+var_90]; this
0x18007bdf0  mov     [rsp+1C0h+var_168], r13
0x18007bdf5  mov     [rsp+1C0h+var_170], r13b
0x18007bdfa  mov     rsi, r9
0x18007bdfd  mov     rbx, r8
0x18007be00  mov     r12, rdx
0x18007be03  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18007be08  lea     rcx, [rbp+0C0h+var_D0]; this
0x18007be0c  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18007be11  lea     rcx, [rbp+0C0h+var_110]; this
0x18007be15  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18007be1a  lea     rcx, [rsp+1C0h+var_150]; this
0x18007be1f  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18007be24  xor     ecx, ecx; HINSTANCE *
0x18007be26  mov     [rsp+1C0h+var_180], r13b
0x18007be2b  call    ?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z; IsWdsLoggerSetup(HINSTANCE__ * *)
0x18007be30  test    al, al
0x18007be32  jnz     short loc_18007BE9B
0x18007be34  mov     rcx, rbx; lpValue
0x18007be37  call    CbsOfflineSetLogFile
0x18007be3c  mov     edi, eax
0x18007be3e  test    eax, eax
0x18007be40  jns     short loc_18007BE9B
0x18007be42  mov     rcx, [rbp+0C8h]; this
0x18007be49  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\uninstall\\uninstal"...
0x18007be50  mov     r9d, eax; char *
0x18007be53  lea     edx, [r13+21h]; void *
0x18007be57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007be5c  mov     ecx, r13d
0x18007be5f  xchg    rcx, cs:BaseAddress
0x18007be66  mov     [rsp+1C0h+var_178], rcx
0x18007be6b  lea     rcx, [rsp+1C0h+var_178]
0x18007be70  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007be75  mov     eax, r13d
0x18007be78  mov     ecx, r13d
0x18007be7b  xchg    rax, cs:ProcedureAddress
0x18007be82  xchg    rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18007be89  test    rcx, rcx
0x18007be8c  jz      loc_18007BF54
0x18007be92  lea     edx, [r13+1]
0x18007be96  jmp     loc_18007BF45
0x18007be9b  lea     rcx, [rsp+1C0h+var_180]; this
0x18007bea0  call    ?LoadWds@WdsLoader@LogAdapter@@QEAAJXZ; LogAdapter::WdsLoader::LoadWds(void)
0x18007bea5  lea     rcx, [rsp+1C0h+var_178]
0x18007beaa  mov     [rsp+1C0h+var_178], r13
0x18007beaf  call    ??$Allocate@$$V@?$AutoNewPtr@VCCbsUninstallUIHandler@@@Windows@@QEAAPEAVCCbsUninstallUIHandler@@XZ; Windows::AutoNewPtr<CCbsUninstallUIHandler>::Allocate<>(void)
0x18007beb4  mov     ebx, 1
0x18007beb9  test    rax, rax
0x18007bebc  jnz     short loc_18007BED7
0x18007bebe  mov     rcx, [rsp+1C0h+var_178]
0x18007bec3  test    rcx, rcx
0x18007bec6  jz      short loc_18007BEE5
0x18007bec8  mov     rax, [rcx]
0x18007becb  mov     edx, ebx
0x18007becd  mov     rax, [rax]
0x18007bed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bed5  jmp     short loc_18007BEE5
0x18007bed7  mov     r15, [rsp+1C0h+var_178]
0x18007bedc  test    r15, r15
0x18007bedf  jnz     loc_18007BF99
0x18007bee5  mov     rcx, [rbp+0C8h]; this
0x18007beec  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\uninstall\\uninstal"...
0x18007bef3  mov     edi, 8007000Eh
0x18007bef8  mov     edx, 26h ; '&'; void *
0x18007befd  mov     r9d, edi; char *
0x18007bf00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bf05  cmp     [rsp+1C0h+var_180], r13b
0x18007bf0a  jz      short loc_18007BF11
0x18007bf0c  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x18007bf11  mov     rax, r13
0x18007bf14  lea     rcx, [rsp+1C0h+var_178]
0x18007bf19  xchg    rax, cs:BaseAddress
0x18007bf20  mov     [rsp+1C0h+var_178], rax
0x18007bf25  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007bf2a  mov     rax, r13
0x18007bf2d  mov     rcx, r13
0x18007bf30  xchg    rax, cs:ProcedureAddress
0x18007bf37  xchg    rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18007bf3e  test    rcx, rcx
0x18007bf41  jz      short loc_18007BF54
0x18007bf43  mov     edx, ebx
0x18007bf45  mov     rax, [rcx]
0x18007bf48  mov     rax, [rax+1F8h]
0x18007bf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bf54  lea     rcx, [rsp+1C0h+var_178]
0x18007bf59  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007bf5e  lea     rcx, [rsp+1C0h+var_150]
0x18007bf63  mov     cs:?g_TracingInitialized@@3_NA, r13b; bool g_TracingInitialized
0x18007bf6a  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007bf6f  lea     rcx, [rbp+0C0h+var_110]
0x18007bf73  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007bf78  lea     rcx, [rbp+0C0h+var_D0]
0x18007bf7c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007bf81  lea     rcx, [rbp+0C0h+var_90]
0x18007bf85  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007bf8a  lea     rcx, [rsp+1C0h+var_168]
0x18007bf8f  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007bf94  jmp     loc_18007C5B9
0x18007bf99  test    rsi, rsi
0x18007bf9c  jz      short loc_18007BFAA
0x18007bf9e  lea     rcx, [r15+20h]
0x18007bfa2  mov     rdx, rsi
0x18007bfa5  call    ??4?$AutoComPtr@UICbsUIHandler@@@Windows@@QEAAAEAV01@PEAUICbsUIHandler@@@Z; Windows::AutoComPtr<ICbsUIHandler>::operator=(ICbsUIHandler *)
0x18007bfaa  mov     ecx, 18h; Size
0x18007bfaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007bfb4  mov     rdi, rax
0x18007bfb7  test    rax, rax
0x18007bfba  jz      loc_18007C4EF
0x18007bfc0  mov     [rax], r13
0x18007bfc3  mov     r8, r12; wchar_t *
0x18007bfc6  mov     [rax+8], r13
0x18007bfca  mov     rcx, rdi; this
0x18007bfcd  mov     [rax+10h], r13
0x18007bfd1  mov     rax, [r15+8]
0x18007bfd5  movsxd  rax, dword ptr [rax+4]
0x18007bfd9  add     rax, 8
0x18007bfdd  add     rax, r15
0x18007bfe0  mov     [rsp+1C0h+var_190], rax; struct ICbsUIHandler *
0x18007bfe5  mov     [rsp+1C0h+var_1A0], r14; wchar_t *
0x18007bfea  call    ?Initialize@CUninstallCbsClient@@QEAAJQEB_W0000PEAUICbsUIHandler@@@Z; CUninstallCbsClient::Initialize(wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,ICbsUIHandler *)
0x18007bfef  mov     esi, eax
0x18007bff1  test    eax, eax
0x18007bff3  jns     short loc_18007BFFF
0x18007bff5  mov     edx, 2Ch ; ','
0x18007bffa  jmp     loc_18007C106
0x18007bfff  mov     rcx, rdi; this
0x18007c002  call    ?MultipleEditionsPresent@CUninstallCbsClient@@AEAA_NXZ; CUninstallCbsClient::MultipleEditionsPresent(void)
0x18007c007  test    al, al
0x18007c009  jnz     loc_18007C0D9
0x18007c00f  lea     r9, aUninstallIsNot; "Uninstall is not supported."
0x18007c016  xor     r8d, r8d
0x18007c019  xor     edx, edx
0x18007c01b  mov     ecx, 4000000h
0x18007c020  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c025  cmp     [rsp+1C0h+var_180], r13b
0x18007c02a  jz      short loc_18007C031
0x18007c02c  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x18007c031  mov     rax, r13
0x18007c034  lea     rcx, [rsp+1C0h+var_178]
0x18007c039  xchg    rax, cs:BaseAddress
0x18007c040  mov     [rsp+1C0h+var_178], rax
0x18007c045  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007c04a  mov     rax, r13
0x18007c04d  mov     rcx, r13
0x18007c050  xchg    rax, cs:ProcedureAddress
0x18007c057  xchg    rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18007c05e  test    rcx, rcx
0x18007c061  jz      short loc_18007C074
0x18007c063  mov     rax, [rcx]
0x18007c066  mov     edx, ebx
0x18007c068  mov     rax, [rax+1F8h]
0x18007c06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c074  lea     rcx, [rsp+1C0h+var_178]
0x18007c079  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007c07e  lea     rcx, [rsp+1C0h+var_150]
0x18007c083  mov     cs:?g_TracingInitialized@@3_NA, r13b; bool g_TracingInitialized
0x18007c08a  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c08f  lea     rcx, [rbp+0C0h+var_110]
0x18007c093  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c098  lea     rcx, [rbp+0C0h+var_D0]
0x18007c09c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c0a1  lea     rcx, [rbp+0C0h+var_90]
0x18007c0a5  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c0aa  lea     rcx, [rsp+1C0h+var_168]
0x18007c0af  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007c0b4  mov     rax, [r15+8]
0x18007c0b8  movsxd  rcx, dword ptr [rax+4]
0x18007c0bc  add     rcx, 8
0x18007c0c0  add     rcx, r15
0x18007c0c3  mov     rax, [rcx]
0x18007c0c6  mov     rax, [rax+10h]
0x18007c0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c0cf  mov     esi, 800F0825h
0x18007c0d4  jmp     loc_18007C1C6
0x18007c0d9  lea     rax, [rsp+1C0h+var_150]
0x18007c0de  mov     rcx, rdi; this
0x18007c0e1  lea     r9, [rbp+0C0h+var_110]; struct CCbsStringArray *
0x18007c0e5  mov     [rsp+1C0h+var_1A0], rax; int
0x18007c0ea  lea     r8, [rbp+0C0h+var_D0]; struct CCbsStringArray *
0x18007c0ee  lea     rdx, [rbp+0C0h+var_90]; struct CCbsStringArray *
0x18007c0f2  call    ?ListPackagesForUninstall@CUninstallCbsClient@@QEAAJPEAVCCbsStringArray@@000@Z; CUninstallCbsClient::ListPackagesForUninstall(CCbsStringArray *,CCbsStringArray *,CCbsStringArray *,CCbsStringArray *)
0x18007c0f7  mov     esi, eax
0x18007c0f9  test    eax, eax
0x18007c0fb  jns     loc_18007C1E2
0x18007c101  mov     edx, 36h ; '6'; void *
0x18007c106  mov     rcx, [rbp+0C8h]; this
0x18007c10d  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\uninstall\\uninstal"...
0x18007c114  mov     r9d, eax; char *
0x18007c117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c11c  cmp     [rsp+1C0h+var_180], r13b
0x18007c121  jz      short loc_18007C128
0x18007c123  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x18007c128  mov     rax, r13
0x18007c12b  lea     rcx, [rsp+1C0h+var_178]
0x18007c130  xchg    rax, cs:BaseAddress
0x18007c137  mov     [rsp+1C0h+var_178], rax
0x18007c13c  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007c141  mov     rax, r13
0x18007c144  mov     rcx, r13
0x18007c147  xchg    rax, cs:ProcedureAddress
0x18007c14e  xchg    rcx, cs:?g_TracingStream@Rtl@Implementation@WCP@Windows@@3PEAVCBaseTracingStream@1234@EA; Windows::WCP::Implementation::Rtl::CBaseTracingStream * Windows::WCP::Implementation::Rtl::g_TracingStream
0x18007c155  test    rcx, rcx
0x18007c158  jz      short loc_18007C16B
0x18007c15a  mov     rax, [rcx]
0x18007c15d  mov     edx, ebx
0x18007c15f  mov     rax, [rax+1F8h]
0x18007c166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c16b  lea     rcx, [rsp+1C0h+var_178]
0x18007c170  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)>>::Close(void)
0x18007c175  mov     cs:?g_TracingInitialized@@3_NA, r13b; bool g_TracingInitialized
0x18007c17c  lea     rcx, [rsp+1C0h+var_150]
0x18007c181  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c186  lea     rcx, [rbp+0C0h+var_110]
0x18007c18a  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c18f  lea     rcx, [rbp+0C0h+var_D0]
0x18007c193  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c198  lea     rcx, [rbp+0C0h+var_90]
0x18007c19c  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18007c1a1  lea     rcx, [rsp+1C0h+var_168]
0x18007c1a6  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007c1ab  mov     rax, [r15+8]
0x18007c1af  movsxd  rcx, dword ptr [rax+4]
0x18007c1b3  add     rcx, 8
0x18007c1b7  add     rcx, r15
0x18007c1ba  mov     rax, [rcx]
0x18007c1bd  mov     rax, [rax+10h]
0x18007c1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c1c6  mov     rcx, rdi; this
0x18007c1c9  call    ??1CUninstallCbsClient@@QEAA@XZ; CUninstallCbsClient::~CUninstallCbsClient(void)
0x18007c1ce  mov     edx, 18h; struct std::nothrow_t *
0x18007c1d3  mov     rcx, rdi; void *
0x18007c1d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007c1db  mov     eax, esi
0x18007c1dd  jmp     loc_18007C5BB
0x18007c1e2  mov     r12, [rbp+0C0h+var_78]
0x18007c1e6  mov     r14d, r13d
0x18007c1e9  test    r12, r12
0x18007c1ec  jz      short loc_18007C226
0x18007c1ee  mov     r13, [rbp+0C0h+var_68]
0x18007c1f2  mov     edx, r14d
0x18007c1f5  cmp     rdx, r12
0x18007c1f8  jb      short loc_18007C201
0x18007c1fa  mov     ecx, 8
0x18007c1ff  int     29h; Win8: RtlFailFast(ecx)
0x18007c201  mov     rdx, [r13+rdx*8+0]; wchar_t *
0x18007c206  mov     rcx, rdi; this
0x18007c209  call    ?UninstallPackage@CUninstallCbsClient@@QEAAJQEB_W@Z; CUninstallCbsClient::UninstallPackage(wchar_t const * const)
0x18007c20e  mov     esi, eax
0x18007c210  test    eax, eax
0x18007c212  js      loc_18007C30D
0x18007c218  add     r14d, ebx
0x18007c21b  mov     eax, r14d
0x18007c21e  cmp     rax, r12
0x18007c221  jb      short loc_18007C1F2
0x18007c223  xor     r13d, r13d
0x18007c226  mov     r14, [rbp+0C0h+var_138]
0x18007c22a  mov     esi, r13d
0x18007c22d  test    r14, r14
0x18007c230  jz      short loc_18007C268
0x18007c232  mov     r13, [rbp+0C0h+var_128]
0x18007c236  mov     edx, esi
0x18007c238  cmp     rdx, r14
0x18007c23b  jb      short loc_18007C244
0x18007c23d  mov     ecx, 8
0x18007c242  int     29h; Win8: RtlFailFast(ecx)
0x18007c244  mov     rdx, [r13+rdx*8+0]; wchar_t *
0x18007c249  mov     rcx, rdi; this
0x18007c24c  call    ?UninstallPackage@CUninstallCbsClient@@QEAAJQEB_W@Z; CUninstallCbsClient::UninstallPackage(wchar_t const * const)
0x18007c251  mov     r12d, eax
0x18007c254  test    eax, eax
0x18007c256  js      loc_18007C38A
0x18007c25c  add     esi, ebx
0x18007c25e  mov     eax, esi
0x18007c260  cmp     rax, r14
0x18007c263  jb      short loc_18007C236
0x18007c265  xor     r13d, r13d
0x18007c268  mov     r14, [rbp+0C0h+var_B8]
0x18007c26c  mov     esi, r13d
0x18007c26f  test    r14, r14
0x18007c272  jz      short loc_18007C2AA
0x18007c274  mov     r13, [rbp+0C0h+var_A8]
0x18007c278  mov     edx, esi
0x18007c27a  cmp     rdx, r14
  ... truncated ...
```

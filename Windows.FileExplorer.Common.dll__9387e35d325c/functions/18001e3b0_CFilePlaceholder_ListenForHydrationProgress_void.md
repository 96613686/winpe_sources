# CFilePlaceholder::ListenForHydrationProgress(void)

- ea: `0x18001e3b0`
- end: `0x18001e727`
- name: `?ListenForHydrationProgress@CFilePlaceholder@@AEAAJXZ`
- size: `887`
- prototype: `__int64 __fastcall(CFilePlaceholder *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180034908`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x18000c668`
- `0x18001d58c`
- `0x18001e3b0`
- `0x18001e730`
- `0x180030a20`
- `0x18003169c`
- `0x18003cac8`
- `0x180089010`

## import_xrefs

- `Windows.Storage!SHParseDisplayName` at `0x18001e52c`
- `Windows.Storage!SHParseDisplayName` at `0x18001e52c`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18001e420`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18001e420`
- `Windows.Storage!__imp_SHChangeNotifyRegister` at `0x18001e5b0`
- `Windows.Storage!__imp_SHChangeNotifyRegister` at `0x18001e5b0`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001e4ab`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x18001e4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e66a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e66a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001e68f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001e68f`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18001e63c`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18001e63c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e6db`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e6f6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e710`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e6db`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e6f6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18001e710`

## string_xrefs

- `0x18001e3e0`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e434`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e47a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e4be`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e5ca`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e64a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`
- `0x18001e6ba`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\fileplaceholder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFilePlaceholder::ListenForHydrationProgress(CFilePlaceholder *this)
{
  char *v2; // r15
  HRESULT LastError; // ebx
  void **v5; // rsi
  HRESULT v6; // eax
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int v9; // esi
  struct IBindCtx *v10; // rcx
  const char *v11; // r9
  const WCHAR *v12; // rsi
  __int64 v13; // rdx
  ULONG v14; // eax
  unsigned int v15; // r9d
  const char *v16; // r9
  void *v17; // rcx
  int psfgaoOut; // [rsp+20h] [rbp-50h]
  unsigned int psfgaoOuta; // [rsp+20h] [rbp-50h]
  unsigned int pshcne; // [rsp+28h] [rbp-48h]
  SHChangeNotifyEntry v21; // [rsp+30h] [rbp-40h] BYREF
  HWND *p_hwnd; // [rsp+40h] [rbp-30h]
  char v23; // [rsp+48h] [rbp-28h]
  LPVOID *p_pv; // [rsp+50h] [rbp-20h]
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-18h] BYREF
  char v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD NumberOfBytesTransferred; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF
  HWND hwnd; // [rsp+C0h] [rbp+50h] BYREF
  IBindCtx *pbc; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (char *)this + 788;
  if ( *((_DWORD *)this + 197) )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E1,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
      (const char *)0x8000FFFFLL,
      psfgaoOut);
    return (unsigned int)LastError;
  }
  v5 = (void **)((char *)this + 800);
  if ( !*((_QWORD *)this + 100) )
  {
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease((char *)this + 800);
    v6 = SHCreateItemFromParsingName(*((PCWSTR *)this + 15), 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
        (const char *)(unsigned int)v6,
        psfgaoOut);
      return v7;
    }
    v8 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, char *))(*(_QWORD *)*v5 + 152LL))(
           *v5,
           &PKEY_Size,
           (char *)this + 808);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E8,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
        (const char *)(unsigned int)v8,
        psfgaoOut);
      return v9;
    }
  }
  psfgaoOuta = 0;
  hwnd = (HWND)SHCreateWorkerWindowW(CFilePlaceholder::s_HandleProgress, 0, 0, 0);
  if ( !hwnd )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2ED,
             (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
             v11);
  p_hwnd = &hwnd;
  v23 = 1;
  pv = 0;
  p_pv = &pv;
  v26 = 1;
  v12 = (const WCHAR *)*((_QWORD *)this + 15);
  ppidl = 0;
  if ( *v12 )
  {
    pbc = 0;
    LastError = _CreateFileSysBindCtx(v10, 0, &pbc);
    if ( LastError >= 0 )
    {
      LastError = SHParseDisplayName(v12, pbc, &ppidl, 0, 0);
      ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
    }
  }
  else
  {
    LastError = -2147024809;
  }
  if ( v26 )
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      p_pv,
      ppidl);
  if ( LastError < 0 )
  {
    v13 = 755;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
      (const char *)(unsigned int)LastError,
      psfgaoOuta);
LABEL_36:
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &pv,
      0);
LABEL_37:
    DestroyWindow(hwnd);
    return (unsigned int)LastError;
  }
  if ( !pv )
  {
    LastError = -2147418113;
    v13 = 756;
    goto LABEL_35;
  }
  v21.fRecursive = 0;
  v21.pidl = (LPCITEMIDLIST)pv;
  v14 = SHChangeNotifyRegister(hwnd, 32770, 0x2000, 0x410u, 1, &v21);
  *((_DWORD *)this + 197) = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
      (const char *)0x80070057LL,
      psfgaoOuta);
    LastError = -2147024809;
    goto LABEL_36;
  }
  while ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 99) + 24LL))(*((_QWORD *)this + 99)) >= 0 )
  {
    pbc = (IBindCtx *)*((_QWORD *)this + 106);
    if ( SHProcessMessagesUntilEventsEx(hwnd, (HANDLE *)&pbc, pbc != 0, v15, psfgaoOuta, pshcne) != 258 )
      goto LABEL_30;
  }
  *((_BYTE *)this + 856) = 1;
  if ( !CancelIoEx(*((HANDLE *)this + 102), (LPOVERLAPPED)((char *)this + 824)) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x312,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\fileplaceholder.cpp",
                  v16);
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    goto LABEL_37;
  }
  CloudFilesTelemetry::DownloadAndGoUI_HydrationCancelled<unsigned long &>(v2);
LABEL_30:
  NumberOfBytesTransferred = 0;
  if ( GetOverlappedResult(*((HANDLE *)this + 102), (LPOVERLAPPED)((char *)this + 824), &NumberOfBytesTransferred, 1) )
  {
    LastError = 0;
  }
  else
  {
    LastError = ResultFromKnownLastError();
    if ( LastError == -2147023901 )
    {
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pv,
        0);
      DestroyWindow(hwnd);
      return 2147943395LL;
    }
  }
  if ( LastError < 0 )
  {
    v13 = 796;
    goto LABEL_35;
  }
  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &pv,
    0);
  DestroyWindow(hwnd);
  return 0;
}

```

## disassembly

```asm
0x18001e3b0  push    rbp
0x18001e3b2  push    rbx
0x18001e3b3  push    rsi
0x18001e3b4  push    rdi
0x18001e3b5  push    r12
0x18001e3b7  push    r14
0x18001e3b9  push    r15
0x18001e3bb  mov     rbp, rsp
0x18001e3be  sub     rsp, 70h
0x18001e3c2  mov     rdi, rcx
0x18001e3c5  lea     r15, [rcx+314h]
0x18001e3cc  xor     r12d, r12d
0x18001e3cf  cmp     [r15], r12d
0x18001e3d2  jz      short loc_18001E3F8
0x18001e3d4  mov     rcx, [rbp+38h]; this
0x18001e3d8  mov     ebx, 8000FFFFh
0x18001e3dd  mov     r9d, ebx; char *
0x18001e3e0  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e3e7  mov     edx, 2E1h; void *
0x18001e3ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3f1  mov     eax, ebx
0x18001e3f3  jmp     loc_18001E718
0x18001e3f8  lea     rsi, [rcx+320h]
0x18001e3ff  cmp     [rsi], r12
0x18001e402  jnz     loc_18001E492
0x18001e408  mov     rcx, rsi
0x18001e40b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001e410  mov     r9, rsi; ppv
0x18001e413  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18001e41a  xor     edx, edx; pbc
0x18001e41c  mov     rcx, [rdi+78h]; pszPath
0x18001e420  call    cs:__imp_SHCreateItemFromParsingName
0x18001e426  mov     r14d, eax
0x18001e429  test    eax, eax
0x18001e42b  jns     short loc_18001E44D
0x18001e42d  mov     rcx, [rbp+38h]; this
0x18001e431  mov     r9d, eax; char *
0x18001e434  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e43b  mov     edx, 2E7h; void *
0x18001e440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e445  mov     eax, r14d
0x18001e448  jmp     loc_18001E718
0x18001e44d  mov     rcx, [rsi]
0x18001e450  mov     rax, [rcx]
0x18001e453  lea     r8, [rdi+328h]
0x18001e45a  lea     rdx, PKEY_Size
0x18001e461  mov     rax, [rax+98h]
0x18001e468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46d  mov     esi, eax
0x18001e46f  test    eax, eax
0x18001e471  jns     short loc_18001E492
0x18001e473  mov     rcx, [rbp+38h]; this
0x18001e477  mov     r9d, eax; char *
0x18001e47a  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e481  mov     edx, 2E8h; void *
0x18001e486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e48b  mov     eax, esi
0x18001e48d  jmp     loc_18001E718
0x18001e492  mov     [rsp+70h+pshcne], rdi
0x18001e497  mov     [rsp+70h+psfgaoOut], r12
0x18001e49c  xor     r9d, r9d
0x18001e49f  xor     r8d, r8d
0x18001e4a2  xor     edx, edx
0x18001e4a4  lea     rcx, ?s_HandleProgress@CFilePlaceholder@@CA_JPEAUHWND__@@I_K_J@Z; CFilePlaceholder::s_HandleProgress(HWND__ *,uint,unsigned __int64,__int64)
0x18001e4ab  call    cs:__imp_SHCreateWorkerWindowW
0x18001e4b1  mov     [rbp+hwnd], rax
0x18001e4b5  test    rax, rax
0x18001e4b8  jnz     short loc_18001E4D4
0x18001e4ba  mov     rcx, [rbp+38h]; this
0x18001e4be  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e4c5  mov     edx, 2EDh; void *
0x18001e4ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e4cf  jmp     loc_18001E718
0x18001e4d4  lea     rax, [rbp+hwnd]
0x18001e4d8  mov     [rbp+var_30], rax
0x18001e4dc  mov     r14d, 1
0x18001e4e2  mov     [rbp+var_28], r14b
0x18001e4e6  mov     [rbp+pv], r12
0x18001e4ea  lea     rax, [rbp+pv]
0x18001e4ee  mov     [rbp+var_20], rax
0x18001e4f2  mov     [rbp+var_10], r14b
0x18001e4f6  mov     rsi, [rdi+78h]
0x18001e4fa  mov     [rbp+ppidl], r12
0x18001e4fe  cmp     [rsi], r12w
0x18001e502  jz      short loc_18001E546
0x18001e504  mov     [rbp+pbc], r12
0x18001e508  lea     r8, [rbp+pbc]; struct IBindCtx **
0x18001e50c  xor     edx, edx; struct _WIN32_FIND_DATAW *
0x18001e50e  call    ?_CreateFileSysBindCtx@@YAJPEAUIBindCtx@@PEBU_WIN32_FIND_DATAW@@PEAPEAU1@@Z; _CreateFileSysBindCtx(IBindCtx *,_WIN32_FIND_DATAW const *,IBindCtx * *)
0x18001e513  mov     ebx, eax
0x18001e515  test    eax, eax
0x18001e517  js      short loc_18001E54B
0x18001e519  mov     [rsp+70h+psfgaoOut], r12; psfgaoOut
0x18001e51e  xor     r9d, r9d; sfgaoIn
0x18001e521  lea     r8, [rbp+ppidl]; ppidl
0x18001e525  mov     rdx, [rbp+pbc]; pbc
0x18001e529  mov     rcx, rsi; pszName
0x18001e52c  call    cs:__imp_SHParseDisplayName
0x18001e532  mov     ebx, eax
0x18001e534  mov     rcx, [rbp+pbc]
0x18001e538  mov     rax, [rcx]
0x18001e53b  mov     rax, [rax+10h]
0x18001e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e544  jmp     short loc_18001E54B
0x18001e546  mov     ebx, 80070057h
0x18001e54b  cmp     [rbp+var_10], r12b
0x18001e54f  jz      short loc_18001E55E
0x18001e551  mov     rdx, [rbp+ppidl]
0x18001e555  mov     rcx, [rbp+var_20]
0x18001e559  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18001e55e  test    ebx, ebx
0x18001e560  jns     short loc_18001E56C
0x18001e562  mov     edx, 2F3h
0x18001e567  jmp     loc_18001E6B7
0x18001e56c  cmp     [rbp+pv], r12
0x18001e570  jnz     short loc_18001E581
0x18001e572  mov     ebx, 8000FFFFh
0x18001e577  mov     edx, 2F4h
0x18001e57c  jmp     loc_18001E6B7
0x18001e581  mov     [rbp+var_40.fRecursive], r12d
0x18001e585  mov     rax, [rbp+pv]
0x18001e589  mov     [rbp+var_40.pidl], rax
0x18001e58d  lea     rax, [rbp+var_40]
0x18001e591  mov     [rsp+70h+pshcne], rax; unsigned int
0x18001e596  mov     dword ptr [rsp+70h+psfgaoOut], r14d; int
0x18001e59b  mov     edx, 8002h; fSources
0x18001e5a0  mov     r9d, 410h; wMsg
0x18001e5a6  mov     r8d, 2000h; fEvents
0x18001e5ac  mov     rcx, [rbp+hwnd]; hwnd
0x18001e5b0  call    cs:__imp_SHChangeNotifyRegister
0x18001e5b6  mov     [rdi+314h], eax
0x18001e5bc  test    eax, eax
0x18001e5be  jnz     short loc_18001E5E5
0x18001e5c0  mov     rcx, [rbp+38h]; this
0x18001e5c4  mov     r9d, 80070057h; char *
0x18001e5ca  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e5d1  mov     edx, 2FDh; void *
0x18001e5d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5db  mov     ebx, 80070057h
0x18001e5e0  jmp     loc_18001E6CB
0x18001e5e5  lea     rbx, [rdi+338h]
0x18001e5ec  mov     rcx, [rdi+318h]
0x18001e5f3  mov     rax, [rcx]
0x18001e5f6  mov     rax, [rax+18h]
0x18001e5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ff  test    eax, eax
0x18001e601  js      short loc_18001E62B
0x18001e603  mov     rax, [rbx+18h]
0x18001e607  mov     [rbp+pbc], rax
0x18001e60b  mov     r8d, r12d
0x18001e60e  test    rax, rax
0x18001e611  setnz   r8b; nCount
0x18001e615  lea     rdx, [rbp+pbc]; lpHandles
0x18001e619  mov     rcx, [rbp+hwnd]; hWnd
0x18001e61d  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18001e622  cmp     eax, 102h
0x18001e627  jz      short loc_18001E5EC
0x18001e629  jmp     short loc_18001E67A
0x18001e62b  mov     [rdi+358h], r14b
0x18001e632  mov     rdx, rbx; lpOverlapped
0x18001e635  mov     rcx, [rdi+330h]; hFile
0x18001e63c  call    cs:__imp_CancelIoEx
0x18001e642  test    eax, eax
0x18001e644  jnz     short loc_18001E672
0x18001e646  mov     rcx, [rbp+38h]; this
0x18001e64a  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e651  mov     edx, 312h; void *
0x18001e656  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e65b  mov     ebx, eax
0x18001e65d  mov     rcx, [rbp+pv]; pv
0x18001e661  mov     [rbp+pv], r12
0x18001e665  test    rcx, rcx
0x18001e668  jz      short loc_18001E6D7
0x18001e66a  call    cs:__imp_CoTaskMemFree
0x18001e670  jmp     short loc_18001E6D7
0x18001e672  mov     rcx, r15
0x18001e675  call    ??$DownloadAndGoUI_HydrationCancelled@AEAK@CloudFilesTelemetry@@SAXAEAK@Z; CloudFilesTelemetry::DownloadAndGoUI_HydrationCancelled<ulong &>(ulong &)
0x18001e67a  mov     [rbp+NumberOfBytesTransferred], r12d
0x18001e67e  mov     r9d, r14d; bWait
0x18001e681  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001e685  mov     rdx, rbx; lpOverlapped
0x18001e688  mov     rcx, [rdi+330h]; hFile
0x18001e68f  call    cs:__imp_GetOverlappedResult
0x18001e695  test    eax, eax
0x18001e697  jz      short loc_18001E69E
0x18001e699  mov     ebx, r12d
0x18001e69c  jmp     short loc_18001E6AE
0x18001e69e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001e6a3  mov     ebx, eax
0x18001e6a5  mov     edi, 800703E3h
0x18001e6aa  cmp     eax, edi
0x18001e6ac  jz      short loc_18001E700
0x18001e6ae  test    ebx, ebx
0x18001e6b0  jns     short loc_18001E6E6
0x18001e6b2  mov     edx, 31Ch; void *
0x18001e6b7  mov     r9d, ebx; char *
0x18001e6ba  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001e6c1  mov     rcx, [rbp+38h]; this
0x18001e6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6ca  nop
0x18001e6cb  xor     edx, edx
0x18001e6cd  lea     rcx, [rbp+pv]
0x18001e6d1  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18001e6d6  nop
0x18001e6d7  mov     rcx, [rbp+hwnd]; hWnd
0x18001e6db  call    cs:__imp_DestroyWindow
0x18001e6e1  jmp     loc_18001E3F1
0x18001e6e6  xor     edx, edx
0x18001e6e8  lea     rcx, [rbp+pv]
0x18001e6ec  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18001e6f1  nop
0x18001e6f2  mov     rcx, [rbp+hwnd]; hWnd
0x18001e6f6  call    cs:__imp_DestroyWindow
0x18001e6fc  xor     eax, eax
0x18001e6fe  jmp     short loc_18001E718
0x18001e700  xor     edx, edx
0x18001e702  lea     rcx, [rbp+pv]
0x18001e706  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18001e70b  nop
0x18001e70c  mov     rcx, [rbp+hwnd]; hWnd
0x18001e710  call    cs:__imp_DestroyWindow
0x18001e716  mov     eax, edi
0x18001e718  add     rsp, 70h
0x18001e71c  pop     r15
0x18001e71e  pop     r14
0x18001e720  pop     r12
0x18001e722  pop     rdi
0x18001e723  pop     rsi
0x18001e724  pop     rbx
0x18001e725  pop     rbp
0x18001e726  retn
```

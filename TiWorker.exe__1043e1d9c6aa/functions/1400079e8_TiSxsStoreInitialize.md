# TiSxsStoreInitialize

- ea: `0x1400079e8`
- end: `0x140007d32`
- name: `TiSxsStoreInitialize`
- size: `842`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000ade4`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x1400079e8`
- `0x14000e328`
- `0x14001726c`
- `0x1400177d8`
- `0x140018740`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007ba5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007be6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007ba5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007be6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140007cf0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140007cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007bf8`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x140007c1f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x140007c1f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x140007b68`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x140007b68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007a73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007ae6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007a73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140007ae6`

## string_xrefs

- `0x140007c2b`: `Failed to get task allocator for Trusted Installer.`
- `0x140007a28`: `Trusted Installer sxs store already initialized.`
- `0x140007a5a`: `Trusted installer sxs store functions already defined`
- `0x140007a92`: `Failed to get system directory`
- `0x140007abe`: `Failed to allocate memory for sxsstore dll path.`
- `0x140007b03`: `Failed to backslash-terminate system directory: %S.`
- `0x140007b45`: `Failed to append dll name: %S to path: %S.`
- `0x140007b8f`: `Failed to load SxsStore.dll`
- `0x140007c88`: `Failed to initialize sxsstore.dll`
- `0x140007b23`: `SxsStore.dll`

## pseudocode

```c
__int64 TiSxsStoreInitialize()
{
  LPWSTR v0; // rsi
  char v1; // r14
  const char *v2; // r9
  __int64 v3; // rdx
  unsigned int v4; // ebx
  const struct std::nothrow_t *v5; // rdx
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  UINT v8; // esi
  int v9; // eax
  UINT v10; // edx
  int v11; // eax
  int v12; // eax
  HMODULE LibraryW; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  HRESULT Malloc; // eax
  LPWSTR lpBuffer; // [rsp+40h] [rbp-28h] BYREF
  struct IClassFactory *v20; // [rsp+48h] [rbp-20h] BYREF
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-18h] BYREF

  v0 = 0;
  ppMalloc = 0;
  v20 = 0;
  lpBuffer = 0;
  if ( vhSxsStoreModule )
  {
    v1 = 0;
    v2 = "Trusted Installer sxs store already initialized.";
LABEL_3:
    v3 = 2147943647LL;
    v4 = -2147023649;
LABEL_4:
    CBSWdsLog(0x4000000, v3, 1, v2);
    goto LABEL_40;
  }
  v1 = 1;
  if ( vpfnSxsStoreInitialize || vpfnSxsStoreFinalize )
  {
    v2 = "Trusted installer sxs store functions already defined";
    goto LABEL_3;
  }
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  if ( !SystemDirectoryW )
    goto LABEL_9;
  v8 = SystemDirectoryW + 15;
  v9 = SczAlloc(&lpBuffer, SystemDirectoryW + 15);
  v4 = v9;
  if ( v9 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v9, 1, "Failed to allocate memory for sxsstore dll path.");
    v0 = lpBuffer;
    goto LABEL_40;
  }
  v10 = v8;
  v0 = lpBuffer;
  if ( !GetSystemDirectoryW(lpBuffer, v10) )
  {
LABEL_9:
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v2 = "Failed to get system directory";
LABEL_12:
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    v3 = v4;
    goto LABEL_4;
  }
  v11 = SczEnsureBackslashTerminated(&lpBuffer);
  v4 = v11;
  if ( v11 < 0 )
  {
    v0 = lpBuffer;
    CBSWdsLog(0x4000000, (unsigned int)v11, 1, "Failed to backslash-terminate system directory: %S.", lpBuffer);
    goto LABEL_40;
  }
  v12 = SczAllocConcatSz(&lpBuffer, aSxsstoreDll);
  v0 = lpBuffer;
  v4 = v12;
  if ( v12 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v12, 1, "Failed to append dll name: %S to path: %S.", aSxsstoreDll, lpBuffer);
    goto LABEL_40;
  }
  LibraryW = LoadLibraryW(lpBuffer);
  vhSxsStoreModule = LibraryW;
  if ( !LibraryW )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    v2 = "Failed to load SxsStore.dll";
    goto LABEL_12;
  }
  vpfnSxsStoreInitialize = (int (*)(struct IMalloc *, int (*)(int), void (*)(void), void (*)(void), void (*)(void), void (*)(void), struct IClassFactory **))GetProcAddress(LibraryW, "SxsStoreInitialize");
  if ( !vpfnSxsStoreInitialize )
  {
    v15 = GetLastError();
    v4 = v15;
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    v2 = "Failed to locate 'SxsStoreInitialize' method";
    goto LABEL_12;
  }
  vpfnSxsStoreFinalize = (int (*)(void))GetProcAddress(vhSxsStoreModule, "SxsStoreFinalize");
  if ( !vpfnSxsStoreFinalize )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      v4 = (unsigned __int16)v16 | 0x80070000;
    v2 = "Failed to locate 'SxsStoreFinalize' method";
    goto LABEL_12;
  }
  Malloc = CoGetMalloc(1u, &ppMalloc);
  v4 = Malloc;
  if ( Malloc < 0 )
  {
    v2 = "Failed to get task allocator for Trusted Installer.";
LABEL_36:
    v3 = (unsigned int)Malloc;
    goto LABEL_4;
  }
  Malloc = ((__int64 (__fastcall *)(LPMALLOC, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), struct IClassFactory **))vpfnSxsStoreInitialize)(
             ppMalloc,
             TiWorkerCoreLockProcess,
             TiWorkerCoreUnlockProcess,
             TiWorkerCoreInstanceCreatedAndLoadComponentStore,
             TiWorkerCoreInstanceDestroyed,
             TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported,
             &v20);
  v4 = Malloc;
  if ( Malloc < 0 )
  {
    v2 = "Failed to initialize sxsstore.dll";
    goto LABEL_36;
  }
  v1 = 0;
  vpSxSStoreClassFactory = v20;
  v20 = 0;
LABEL_40:
  if ( v20 )
    ((void (__fastcall *)(struct IClassFactory *))v20->lpVtbl->Release)(v20);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( v0 )
    operator delete(v0 - 4, v5);
  if ( v1 && vhSxsStoreModule )
  {
    FreeLibrary(vhSxsStoreModule);
    vhSxsStoreModule = 0;
    vpfnSxsStoreInitialize = 0;
    vpfnSxsStoreFinalize = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1400079e8  push    rbp
0x1400079ea  push    rbx
0x1400079eb  push    rsi
0x1400079ec  push    rdi
0x1400079ed  push    r12
0x1400079ef  push    r14
0x1400079f1  mov     rbp, rsp
0x1400079f4  sub     rsp, 68h
0x1400079f8  mov     rax, cs:__security_cookie
0x1400079ff  xor     rax, rsp
0x140007a02  mov     [rbp+var_10], rax
0x140007a06  xor     esi, esi
0x140007a08  mov     [rbp+ppMalloc], 0
0x140007a10  cmp     cs:?vhSxsStoreModule@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * vhSxsStoreModule
0x140007a17  mov     [rbp+var_20], 0
0x140007a1f  mov     [rbp+lpBuffer], rsi
0x140007a23  jz      short loc_140007A49
0x140007a25  xor     r14b, r14b
0x140007a28  lea     r9, aTrustedInstall_2; "Trusted Installer sxs store already ini"...
0x140007a2f  lea     r8d, [rsi+1]
0x140007a33  mov     edx, 800704DFh
0x140007a38  mov     ebx, edx
0x140007a3a  mov     ecx, 4000000h
0x140007a3f  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007a44  jmp     loc_140007CA7
0x140007a49  cmp     cs:?vpfnSxsStoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, rsi; long (*vpfnSxsStoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007a50  mov     edi, 1
0x140007a55  mov     r14b, dil
0x140007a58  jz      short loc_140007A66
0x140007a5a  lea     r9, aTrustedInstall_3; "Trusted installer sxs store functions a"...
0x140007a61  mov     r8d, edi
0x140007a64  jmp     short loc_140007A33
0x140007a66  cmp     cs:?vpfnSxsStoreFinalize@@3P6AJXZEA, rsi; long (*vpfnSxsStoreFinalize)(void)
0x140007a6d  jnz     short loc_140007A5A
0x140007a6f  xor     edx, edx; uSize
0x140007a71  xor     ecx, ecx; lpBuffer
0x140007a73  call    cs:__imp_GetSystemDirectoryW
0x140007a79  test    eax, eax
0x140007a7b  jnz     short loc_140007AAA
0x140007a7d  call    cs:__imp_GetLastError
0x140007a83  mov     ebx, eax
0x140007a85  test    eax, eax
0x140007a87  jle     short loc_140007A92
0x140007a89  movzx   ebx, ax
0x140007a8c  or      ebx, 80070000h
0x140007a92  lea     r9, aFailedToGetSys; "Failed to get system directory"
0x140007a99  test    ebx, ebx
0x140007a9b  mov     eax, 80004005h
0x140007aa0  mov     r8d, edi
0x140007aa3  cmovns  ebx, eax
0x140007aa6  mov     edx, ebx
0x140007aa8  jmp     short loc_140007A3A
0x140007aaa  lea     esi, [rax+0Fh]
0x140007aad  mov     edx, esi
0x140007aaf  lea     rcx, [rbp+lpBuffer]
0x140007ab3  call    SczAlloc
0x140007ab8  mov     ebx, eax
0x140007aba  test    eax, eax
0x140007abc  jns     short loc_140007ADD
0x140007abe  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for sxsstore "...
0x140007ac5  mov     r8d, edi
0x140007ac8  mov     edx, eax
0x140007aca  mov     ecx, 4000000h
0x140007acf  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007ad4  mov     rsi, [rbp+lpBuffer]
0x140007ad8  jmp     loc_140007CA7
0x140007add  mov     edx, esi; uSize
0x140007adf  mov     rsi, [rbp+lpBuffer]
0x140007ae3  mov     rcx, rsi; lpBuffer
0x140007ae6  call    cs:__imp_GetSystemDirectoryW
0x140007aec  test    eax, eax
0x140007aee  jz      short loc_140007A7D
0x140007af0  lea     rcx, [rbp+lpBuffer]
0x140007af4  call    SczEnsureBackslashTerminated
0x140007af9  mov     ebx, eax
0x140007afb  test    eax, eax
0x140007afd  jns     short loc_140007B23
0x140007aff  mov     rsi, [rbp+lpBuffer]
0x140007b03  lea     r9, aFailedToBacksl_1; "Failed to backslash-terminate system di"...
0x140007b0a  mov     r8d, edi
0x140007b0d  mov     [rsp+68h+var_48], rsi
0x140007b12  mov     edx, eax
0x140007b14  mov     ecx, 4000000h
0x140007b19  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007b1e  jmp     loc_140007CA7
0x140007b23  lea     r12, aSxsstoreDll; "SxsStore.dll"
0x140007b2a  mov     rdx, r12
0x140007b2d  lea     rcx, [rbp+lpBuffer]
0x140007b31  call    SczAllocConcatSz
0x140007b36  mov     rsi, [rbp+lpBuffer]
0x140007b3a  mov     ebx, eax
0x140007b3c  test    eax, eax
0x140007b3e  jns     short loc_140007B65
0x140007b40  mov     [rsp+68h+var_40], rsi
0x140007b45  lea     r9, aFailedToAppend_1; "Failed to append dll name: %S to path: "...
0x140007b4c  mov     r8d, edi
0x140007b4f  mov     [rsp+68h+var_48], r12
0x140007b54  mov     edx, eax
0x140007b56  mov     ecx, 4000000h
0x140007b5b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007b60  jmp     loc_140007CA7
0x140007b65  mov     rcx, rsi; lpLibFileName
0x140007b68  call    cs:__imp_LoadLibraryW
0x140007b6e  mov     cs:?vhSxsStoreModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhSxsStoreModule
0x140007b75  test    rax, rax
0x140007b78  jnz     short loc_140007B9B
0x140007b7a  call    cs:__imp_GetLastError
0x140007b80  mov     ebx, eax
0x140007b82  test    eax, eax
0x140007b84  jle     short loc_140007B8F
0x140007b86  movzx   ebx, ax
0x140007b89  or      ebx, 80070000h
0x140007b8f  lea     r9, aFailedToLoadSx; "Failed to load SxsStore.dll"
0x140007b96  jmp     loc_140007A99
0x140007b9b  lea     rdx, aSxsstoreinitia; "SxsStoreInitialize"
0x140007ba2  mov     rcx, rax; hModule
0x140007ba5  call    cs:__imp_GetProcAddress
0x140007bab  mov     cs:?vpfnSxsStoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, rax; long (*vpfnSxsStoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007bb2  test    rax, rax
0x140007bb5  jnz     short loc_140007BD8
0x140007bb7  call    cs:__imp_GetLastError
0x140007bbd  mov     ebx, eax
0x140007bbf  test    eax, eax
0x140007bc1  jle     short loc_140007BCC
0x140007bc3  movzx   ebx, ax
0x140007bc6  or      ebx, 80070000h
0x140007bcc  lea     r9, aFailedToLocate_8; "Failed to locate 'SxsStoreInitialize' m"...
0x140007bd3  jmp     loc_140007A99
0x140007bd8  mov     rcx, cs:?vhSxsStoreModule@@3PEAUHINSTANCE__@@EA; hModule
0x140007bdf  lea     rdx, aSxsstorefinali; "SxsStoreFinalize"
0x140007be6  call    cs:__imp_GetProcAddress
0x140007bec  mov     cs:?vpfnSxsStoreFinalize@@3P6AJXZEA, rax; long (*vpfnSxsStoreFinalize)(void)
0x140007bf3  test    rax, rax
0x140007bf6  jnz     short loc_140007C19
0x140007bf8  call    cs:__imp_GetLastError
0x140007bfe  mov     ebx, eax
0x140007c00  test    eax, eax
0x140007c02  jle     short loc_140007C0D
0x140007c04  movzx   ebx, ax
0x140007c07  or      ebx, 80070000h
0x140007c0d  lea     r9, aFailedToLocate; "Failed to locate 'SxsStoreFinalize' met"...
0x140007c14  jmp     loc_140007A99
0x140007c19  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x140007c1d  mov     ecx, edi; dwMemContext
0x140007c1f  call    cs:__imp_CoGetMalloc
0x140007c25  mov     ebx, eax
0x140007c27  test    eax, eax
0x140007c29  jns     short loc_140007C3C
0x140007c2b  lea     r9, aFailedToGetTas; "Failed to get task allocator for Truste"...
0x140007c32  mov     r8d, edi
0x140007c35  mov     edx, eax
0x140007c37  jmp     loc_140007A3A
0x140007c3c  mov     rcx, [rbp+ppMalloc]
0x140007c40  lea     rax, [rbp+var_20]
0x140007c44  mov     [rsp+68h+var_38], rax
0x140007c49  lea     r9, TiWorkerCoreInstanceCreatedAndLoadComponentStore
0x140007c50  lea     rax, TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported
0x140007c57  mov     [rsp+68h+var_40], rax
0x140007c5c  lea     r8, TiWorkerCoreUnlockProcess
0x140007c63  lea     rax, TiWorkerCoreInstanceDestroyed
0x140007c6a  mov     [rsp+68h+var_48], rax
0x140007c6f  lea     rdx, TiWorkerCoreLockProcess
0x140007c76  mov     rax, cs:?vpfnSxsStoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA; long (*vpfnSxsStoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c82  mov     ebx, eax
0x140007c84  test    eax, eax
0x140007c86  jns     short loc_140007C91
0x140007c88  lea     r9, aFailedToInitia_5; "Failed to initialize sxsstore.dll"
0x140007c8f  jmp     short loc_140007C32
0x140007c91  mov     rax, [rbp+var_20]
0x140007c95  xor     r14b, r14b
0x140007c98  mov     cs:?vpSxSStoreClassFactory@@3PEAUIClassFactory@@EA, rax; IClassFactory * vpSxSStoreClassFactory
0x140007c9f  mov     [rbp+var_20], 0
0x140007ca7  mov     rcx, [rbp+var_20]
0x140007cab  test    rcx, rcx
0x140007cae  jz      short loc_140007CBC
0x140007cb0  mov     rax, [rcx]
0x140007cb3  mov     rax, [rax+10h]
0x140007cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cbc  mov     rcx, [rbp+ppMalloc]
0x140007cc0  test    rcx, rcx
0x140007cc3  jz      short loc_140007CD1
0x140007cc5  mov     rax, [rcx]
0x140007cc8  mov     rax, [rax+10h]
0x140007ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cd1  test    rsi, rsi
0x140007cd4  jz      short loc_140007CDF
0x140007cd6  lea     rcx, [rsi-8]; void *
0x140007cda  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140007cdf  test    r14b, r14b
0x140007ce2  jz      short loc_140007D17
0x140007ce4  mov     rcx, cs:?vhSxsStoreModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x140007ceb  test    rcx, rcx
0x140007cee  jz      short loc_140007D17
0x140007cf0  call    cs:__imp_FreeLibrary
0x140007cf6  mov     cs:?vhSxsStoreModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * vhSxsStoreModule
0x140007d01  mov     cs:?vpfnSxsStoreInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, 0; long (*vpfnSxsStoreInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x140007d0c  mov     cs:?vpfnSxsStoreFinalize@@3P6AJXZEA, 0; long (*vpfnSxsStoreFinalize)(void)
0x140007d17  mov     eax, ebx
0x140007d19  mov     rcx, [rbp+var_10]
0x140007d1d  xor     rcx, rsp; StackCookie
0x140007d20  call    __security_check_cookie
0x140007d25  add     rsp, 68h
0x140007d29  pop     r14
0x140007d2b  pop     r12
0x140007d2d  pop     rdi
0x140007d2e  pop     rsi
0x140007d2f  pop     rbx
0x140007d30  pop     rbp
0x140007d31  retn
```

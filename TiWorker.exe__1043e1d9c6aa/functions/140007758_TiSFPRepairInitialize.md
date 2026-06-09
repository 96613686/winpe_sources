# TiSFPRepairInitialize

- ea: `0x140007758`
- end: `0x1400079e2`
- name: `TiSFPRepairInitialize`
- size: `650`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000ade4`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x140007758`
- `0x14000e328`
- `0x140016bf8`
- `0x140017464`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007899`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140007899`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140007993`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x140007993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000784d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000784d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400078ab`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400078d2`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400078d2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x14000783b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x14000783b`

## string_xrefs

- `0x14000778f`: `Trusted Installer sfp module already initialized.`
- `0x1400077bb`: `Trusted installer sfp functions already defined`
- `0x1400077d3`: `Failed to find servicing stack directory.`
- `0x1400077f9`: `\wrpint.dll`
- `0x140007812`: `Failed to allocate full path to Core DLL.`
- `0x140007862`: `Failed to load sfp DLL from path: %S`
- `0x1400078c0`: `Failed to locate 'SfpInitialize' method in DLL: %S`
- `0x1400078de`: `Failed to get task allocator for Trusted Installer.`
- `0x140007938`: `Failed to initialize the DLL: %S`

## pseudocode

```c
__int64 TiSFPRepairInitialize()
{
  __int64 v0; // rsi
  LPCWSTR v1; // rdi
  const char *v2; // r9
  signed int v3; // ebx
  const struct std::nothrow_t *v4; // rdx
  int ModulePath; // eax
  int v6; // eax
  HMODULE LibraryW; // rax
  signed int v8; // eax
  const char *v9; // r9
  signed int LastError; // eax
  HRESULT Malloc; // eax
  int v12; // eax
  __int64 v14; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-30h] BYREF
  struct IClassFactory *v16; // [rsp+50h] [rbp-28h] BYREF
  LPMALLOC ppMalloc; // [rsp+58h] [rbp-20h] BYREF

  v0 = 0;
  v1 = 0;
  lpLibFileName = 0;
  v14 = 0;
  ppMalloc = 0;
  v16 = 0;
  if ( vhSfpModule )
  {
    v2 = "Trusted Installer sfp module already initialized.";
LABEL_3:
    v3 = -2147023649;
    CBSWdsLog(0x4000000, 2147943647LL, 1, v2);
    goto LABEL_28;
  }
  if ( vpfnSfpInitialize )
  {
    v2 = "Trusted installer sfp functions already defined";
    goto LABEL_3;
  }
  ModulePath = PathGetModulePath(&v14);
  v3 = ModulePath;
  if ( ModulePath < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)ModulePath, 1, "Failed to find servicing stack directory.");
    v0 = v14;
    goto LABEL_28;
  }
  v0 = v14;
  v6 = SczAllocConcat2Sz(&lpLibFileName, v14, L"\\wrpint.dll");
  v3 = v6;
  if ( v6 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v6, 1, "Failed to allocate full path to Core DLL.");
    v1 = lpLibFileName;
    goto LABEL_28;
  }
  v1 = lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  vhSfpModule = LibraryW;
  if ( LibraryW )
  {
    vpfnSfpInitialize = (int (*)(struct IMalloc *, int (*)(int), void (*)(void), void (*)(void), void (*)(void), void (*)(void), struct IClassFactory **))GetProcAddress(LibraryW, "SfpInitialize");
    if ( vpfnSfpInitialize )
    {
      Malloc = CoGetMalloc(1u, &ppMalloc);
      v3 = Malloc;
      if ( Malloc >= 0 )
      {
        v12 = ((__int64 (__fastcall *)(LPMALLOC, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), struct IClassFactory **))vpfnSfpInitialize)(
                ppMalloc,
                TiWorkerCoreLockProcess,
                TiWorkerCoreUnlockProcess,
                TiWorkerCoreInstanceCreatedAndLoadComponentStore,
                TiWorkerCoreInstanceDestroyed,
                TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported,
                &v16);
        v3 = v12;
        if ( v12 >= 0 )
        {
          vpSFPIntegrityCheckAndRepairClassFactory = v16;
          v16 = 0;
        }
        else
        {
          CBSWdsLog(0x4000000, (unsigned int)v12, 1, "Failed to initialize the DLL: %S", v1);
        }
      }
      else
      {
        CBSWdsLog(0x4000000, (unsigned int)Malloc, 1, "Failed to get task allocator for Trusted Installer.");
      }
      goto LABEL_28;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v9 = "Failed to locate 'SfpInitialize' method in DLL: %S";
  }
  else
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    v9 = "Failed to load sfp DLL from path: %S";
  }
  if ( v3 >= 0 )
    v3 = -2147467259;
  CBSWdsLog(0x4000000, (unsigned int)v3, 1, v9, v1);
LABEL_28:
  if ( v16 )
    ((void (__fastcall *)(struct IClassFactory *))v16->lpVtbl->Release)(v16);
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( v3 < 0 && vhSfpModule )
  {
    FreeLibrary(vhSfpModule);
    vhSfpModule = 0;
    vpfnSfpInitialize = 0;
  }
  if ( v1 )
    operator delete((void *)(v1 - 4), v4);
  if ( v0 )
    operator delete((void *)(v0 - 8), v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140007758  push    rbp
0x14000775a  push    rbx
0x14000775b  push    rsi
0x14000775c  push    rdi
0x14000775d  mov     rbp, rsp
0x140007760  sub     rsp, 78h
0x140007764  mov     rax, cs:__security_cookie
0x14000776b  xor     rax, rsp
0x14000776e  mov     [rbp+var_18], rax
0x140007772  xor     esi, esi
0x140007774  xor     edi, edi
0x140007776  cmp     cs:?vhSfpModule@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * vhSfpModule
0x14000777d  mov     [rbp+lpLibFileName], rdi
0x140007781  mov     [rbp+var_38], rsi
0x140007785  mov     [rbp+ppMalloc], rsi
0x140007789  mov     [rbp+var_28], rsi
0x14000778d  jz      short loc_1400077B2
0x14000778f  lea     r9, aTrustedInstall_4; "Trusted Installer sfp module already in"...
0x140007796  mov     edx, 800704DFh
0x14000779b  mov     ebx, edx
0x14000779d  mov     r8d, 1
0x1400077a3  mov     ecx, 4000000h
0x1400077a8  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400077ad  jmp     loc_140007959
0x1400077b2  cmp     cs:?vpfnSfpInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, rsi; long (*vpfnSfpInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x1400077b9  jz      short loc_1400077C4
0x1400077bb  lea     r9, aTrustedInstall_0; "Trusted installer sfp functions already"...
0x1400077c2  jmp     short loc_140007796
0x1400077c4  lea     rcx, [rbp+var_38]
0x1400077c8  call    PathGetModulePath
0x1400077cd  mov     ebx, eax
0x1400077cf  test    eax, eax
0x1400077d1  jns     short loc_1400077F5
0x1400077d3  lea     r9, aFailedToFindSe; "Failed to find servicing stack director"...
0x1400077da  mov     r8d, 1
0x1400077e0  mov     edx, eax
0x1400077e2  mov     ecx, 4000000h
0x1400077e7  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400077ec  mov     rsi, [rbp+var_38]
0x1400077f0  jmp     loc_140007959
0x1400077f5  mov     rsi, [rbp+var_38]
0x1400077f9  lea     r8, aWrpintDll; "\\wrpint.dll"
0x140007800  mov     rdx, rsi
0x140007803  lea     rcx, [rbp+lpLibFileName]
0x140007807  call    SczAllocConcat2Sz
0x14000780c  mov     ebx, eax
0x14000780e  test    eax, eax
0x140007810  jns     short loc_140007834
0x140007812  lea     r9, aFailedToAlloca_1; "Failed to allocate full path to Core DL"...
0x140007819  mov     r8d, 1
0x14000781f  mov     edx, eax
0x140007821  mov     ecx, 4000000h
0x140007826  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000782b  mov     rdi, [rbp+lpLibFileName]
0x14000782f  jmp     loc_140007959
0x140007834  mov     rdi, [rbp+lpLibFileName]
0x140007838  mov     rcx, rdi; lpLibFileName
0x14000783b  call    cs:__imp_LoadLibraryW
0x140007841  mov     cs:?vhSfpModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhSfpModule
0x140007848  test    rax, rax
0x14000784b  jnz     short loc_14000788F
0x14000784d  call    cs:__imp_GetLastError
0x140007853  mov     ebx, eax
0x140007855  test    eax, eax
0x140007857  jle     short loc_140007862
0x140007859  movzx   ebx, ax
0x14000785c  or      ebx, 80070000h
0x140007862  lea     r9, aFailedToLoadSf; "Failed to load sfp DLL from path: %S"
0x140007869  test    ebx, ebx
0x14000786b  mov     eax, 80004005h
0x140007870  cmovns  ebx, eax
0x140007873  mov     edx, ebx
0x140007875  mov     r8d, 1
0x14000787b  mov     [rsp+78h+var_58], rdi
0x140007880  mov     ecx, 4000000h
0x140007885  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000788a  jmp     loc_140007959
0x14000788f  lea     rdx, aSfpinitialize; "SfpInitialize"
0x140007896  mov     rcx, rax; hModule
0x140007899  call    cs:__imp_GetProcAddress
0x14000789f  mov     cs:?vpfnSfpInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, rax; long (*vpfnSfpInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x1400078a6  test    rax, rax
0x1400078a9  jnz     short loc_1400078C9
0x1400078ab  call    cs:__imp_GetLastError
0x1400078b1  mov     ebx, eax
0x1400078b3  test    eax, eax
0x1400078b5  jle     short loc_1400078C0
0x1400078b7  movzx   ebx, ax
0x1400078ba  or      ebx, 80070000h
0x1400078c0  lea     r9, aFailedToLocate_3; "Failed to locate 'SfpInitialize' method"...
0x1400078c7  jmp     short loc_140007869
0x1400078c9  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x1400078cd  mov     ecx, 1; dwMemContext
0x1400078d2  call    cs:__imp_CoGetMalloc
0x1400078d8  mov     ebx, eax
0x1400078da  test    eax, eax
0x1400078dc  jns     short loc_1400078EC
0x1400078de  lea     r9, aFailedToGetTas; "Failed to get task allocator for Truste"...
0x1400078e5  mov     edx, eax
0x1400078e7  jmp     loc_14000779D
0x1400078ec  mov     rcx, [rbp+ppMalloc]
0x1400078f0  lea     rax, [rbp+var_28]
0x1400078f4  mov     [rsp+78h+var_48], rax
0x1400078f9  lea     r9, TiWorkerCoreInstanceCreatedAndLoadComponentStore
0x140007900  lea     rax, TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported
0x140007907  mov     [rsp+78h+var_50], rax
0x14000790c  lea     r8, TiWorkerCoreUnlockProcess
0x140007913  lea     rax, TiWorkerCoreInstanceDestroyed
0x14000791a  mov     [rsp+78h+var_58], rax
0x14000791f  lea     rdx, TiWorkerCoreLockProcess
0x140007926  mov     rax, cs:?vpfnSfpInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA; long (*vpfnSfpInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x14000792d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007932  mov     ebx, eax
0x140007934  test    eax, eax
0x140007936  jns     short loc_140007946
0x140007938  lea     r9, aFailedToInitia_2; "Failed to initialize the DLL: %S"
0x14000793f  mov     edx, eax
0x140007941  jmp     loc_140007875
0x140007946  mov     rax, [rbp+var_28]
0x14000794a  mov     cs:?vpSFPIntegrityCheckAndRepairClassFactory@@3PEAUIClassFactory@@EA, rax; IClassFactory * vpSFPIntegrityCheckAndRepairClassFactory
0x140007951  mov     [rbp+var_28], 0
0x140007959  mov     rcx, [rbp+var_28]
0x14000795d  test    rcx, rcx
0x140007960  jz      short loc_14000796E
0x140007962  mov     rax, [rcx]
0x140007965  mov     rax, [rax+10h]
0x140007969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000796e  mov     rcx, [rbp+ppMalloc]
0x140007972  test    rcx, rcx
0x140007975  jz      short loc_140007983
0x140007977  mov     rax, [rcx]
0x14000797a  mov     rax, [rax+10h]
0x14000797e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007983  test    ebx, ebx
0x140007985  jns     short loc_1400079AF
0x140007987  mov     rcx, cs:?vhSfpModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x14000798e  test    rcx, rcx
0x140007991  jz      short loc_1400079AF
0x140007993  call    cs:__imp_FreeLibrary
0x140007999  mov     cs:?vhSfpModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * vhSfpModule
0x1400079a4  mov     cs:?vpfnSfpInitialize@@3P6AJPEAUIMalloc@@P6AHH@ZP6AXXZ222PEAPEAUIClassFactory@@@ZEA, 0; long (*vpfnSfpInitialize)(IMalloc *,int (*)(int),void (*)(void),void (*)(void),void (*)(void),void (*)(void),IClassFactory * *)
0x1400079af  test    rdi, rdi
0x1400079b2  jz      short loc_1400079BD
0x1400079b4  lea     rcx, [rdi-8]; void *
0x1400079b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400079bd  test    rsi, rsi
0x1400079c0  jz      short loc_1400079CB
0x1400079c2  lea     rcx, [rsi-8]; void *
0x1400079c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400079cb  mov     eax, ebx
0x1400079cd  mov     rcx, [rbp+var_18]
0x1400079d1  xor     rcx, rsp; StackCookie
0x1400079d4  call    __security_check_cookie
0x1400079d9  add     rsp, 78h
0x1400079dd  pop     rdi
0x1400079de  pop     rsi
0x1400079df  pop     rbx
0x1400079e0  pop     rbp
0x1400079e1  retn
```

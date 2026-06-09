# Csl::EncryptVirtualDiskWithExternalKey(Csl::Path const &,Csl::Path const &,Csl::Path &)

- ea: `0x180196370`
- end: `0x1801965ac`
- name: `?EncryptVirtualDiskWithExternalKey@Csl@@YAJAEBVPath@1@0AEAV21@@Z`
- size: `572`
- prototype: `int(Csl *__hidden this, const struct Path *, const struct Path *, struct Path *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180085654`

## callees

- `0x180004bd0`
- `0x180008d04`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180195844`
- `0x180195e5c`
- `0x180196370`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801964ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801964ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019641a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019653e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019657b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019641a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019653e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019657b`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180196449`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180196449`
- `wcimage!WcMountVirtualDisk` at `0x1801963de`
- `wcimage!WcMountVirtualDisk` at `0x1801963de`

## pseudocode

```c
__int64 __fastcall Csl::EncryptVirtualDiskWithExternalKey(
        Csl *this,
        const struct Path *a2,
        const struct Path *a3,
        struct Path *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  DWORD VirtualDiskPhysicalPath; // eax
  int LastError; // eax
  const struct _GUID *FileW; // rax
  const char *v13; // r9
  struct _GUID *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  struct Path *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-B8h] BYREF
  ULONG DiskPathSizeInBytes[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR DiskPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  hObject = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v7 = WcMountVirtualDisk(0, *(_QWORD *)this, 0, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v7,
      0);
LABEL_3:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v8;
  }
  v20 = hObject;
  DiskPathSizeInBytes[0] = 520;
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(hObject, DiskPathSizeInBytes, DiskPath);
  if ( VirtualDiskPhysicalPath )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x300,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
                  (const char *)VirtualDiskPhysicalPath,
                  0);
LABEL_8:
    v8 = LastError;
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v20);
    goto LABEL_3;
  }
  FileW = (const struct _GUID *)CreateFileW(DiskPath, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
  v14 = (struct _GUID *)FileW;
  if ( FileW == (const struct _GUID *)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x30B,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
                  v13);
    goto LABEL_8;
  }
  v15 = Csl::EncryptDiskWithExternalKey(
          (Csl *)FVE_GUID_PROV_SCENARIO_FVECTL_PROTWITHEK_SANDBOX,
          FileW,
          a2,
          a3,
          dwCreationDisposition);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( v14 )
      CloseHandle(v14);
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v20);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v15,
      dwCreationDispositiona);
    if ( v14 )
      CloseHandle(v14);
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v20);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v16;
  }
}

```

## disassembly

```asm
0x180196370  mov     [rsp-8+arg_18], rbx
0x180196375  push    rbp
0x180196376  push    rsi
0x180196377  push    rdi
0x180196378  lea     rbp, [rsp-180h]
0x180196380  sub     rsp, 280h
0x180196387  mov     rax, cs:__security_cookie
0x18019638e  xor     rax, rsp
0x180196391  mov     [rbp+190h+var_20], rax
0x180196398  mov     rbx, rcx
0x18019639b  mov     [rsp+290h+hObject], 0
0x1801963a4  lea     rcx, [rsp+290h+hObject]
0x1801963a9  mov     rsi, r8
0x1801963ac  mov     rdi, rdx
0x1801963af  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x1801963b4  mov     rdx, [rbx]
0x1801963b7  xor     r9d, r9d
0x1801963ba  mov     [rsp+290h+var_258], rax
0x1801963bf  xor     r8d, r8d
0x1801963c2  mov     dword ptr [rsp+290h+hTemplateFile], 0
0x1801963ca  xor     ecx, ecx
0x1801963cc  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], 0
0x1801963d5  mov     qword ptr [rsp+290h+dwCreationDisposition], 0; unsigned int
0x1801963de  call    cs:__imp_WcMountVirtualDisk
0x1801963e5  nop     dword ptr [rax+rax+00h]
0x1801963ea  mov     ebx, eax
0x1801963ec  test    eax, eax
0x1801963ee  jns     short loc_18019642D
0x1801963f0  mov     rcx, [rbp+198h]; this
0x1801963f7  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801963fe  mov     r9d, eax; char *
0x180196401  mov     edx, 2F7h; void *
0x180196406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019640b  mov     rcx, [rsp+290h+hObject]; hObject
0x180196410  lea     rdx, [rcx-1]
0x180196414  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180196418  ja      short loc_180196426
0x18019641a  call    cs:__imp_CloseHandle
0x180196421  nop     dword ptr [rax+rax+00h]
0x180196426  mov     eax, ebx
0x180196428  jmp     loc_180196589
0x18019642d  mov     rcx, [rsp+290h+hObject]; VirtualDiskHandle
0x180196432  lea     r8, [rsp+290h+DiskPath]; DiskPath
0x180196437  lea     rdx, [rsp+290h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18019643c  mov     [rsp+290h+var_248], rcx
0x180196441  mov     [rsp+290h+DiskPathSizeInBytes], 208h
0x180196449  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180196450  nop     dword ptr [rax+rax+00h]
0x180196455  test    eax, eax
0x180196457  jz      short loc_180196482
0x180196459  mov     rcx, [rbp+198h]; this
0x180196460  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180196467  mov     r9d, eax; char *
0x18019646a  mov     edx, 300h; void *
0x18019646f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180196474  lea     rcx, [rsp+290h+var_248]; this
0x180196479  mov     ebx, eax
0x18019647b  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180196480  jmp     short loc_18019640B
0x180196482  xor     r9d, r9d; lpSecurityAttributes
0x180196485  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x18019648e  mov     [rsp+290h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180196496  lea     rcx, [rsp+290h+DiskPath]; lpFileName
0x18019649b  mov     edx, 0C0000000h; dwDesiredAccess
0x1801964a0  mov     [rsp+290h+dwCreationDisposition], 3; int
0x1801964a8  lea     r8d, [r9+1]; dwShareMode
0x1801964ac  call    cs:__imp_CreateFileW
0x1801964b3  nop     dword ptr [rax+rax+00h]
0x1801964b8  mov     rbx, rax
0x1801964bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801964bf  jnz     short loc_1801964DB
0x1801964c1  mov     rcx, [rbp+198h]; this
0x1801964c8  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801964cf  mov     edx, 30Bh; void *
0x1801964d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801964d9  jmp     short loc_180196474
0x1801964db  mov     r9, rsi; struct Path *
0x1801964de  lea     rcx, FVE_GUID_PROV_SCENARIO_FVECTL_PROTWITHEK_SANDBOX; this
0x1801964e5  mov     r8, rdi; void *
0x1801964e8  mov     rdx, rbx; struct _GUID *
0x1801964eb  call    ?EncryptDiskWithExternalKey@Csl@@YAJPEBU_GUID@@PEAXAEBVPath@1@AEAV31@@Z; Csl::EncryptDiskWithExternalKey(_GUID const *,void *,Csl::Path const &,Csl::Path &)
0x1801964f0  mov     edi, eax
0x1801964f2  test    eax, eax
0x1801964f4  jns     short loc_18019654E
0x1801964f6  mov     rcx, [rbp+198h]; this
0x1801964fd  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180196504  mov     r9d, eax; char *
0x180196507  mov     edx, 311h; void *
0x18019650c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196511  test    rbx, rbx
0x180196514  jz      short loc_180196525
0x180196516  mov     rcx, rbx; hObject
0x180196519  call    cs:__imp_CloseHandle
0x180196520  nop     dword ptr [rax+rax+00h]
0x180196525  lea     rcx, [rsp+290h+var_248]; this
0x18019652a  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x18019652f  mov     rcx, [rsp+290h+hObject]; hObject
0x180196534  lea     rax, [rcx-1]
0x180196538  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18019653c  ja      short loc_18019654A
0x18019653e  call    cs:__imp_CloseHandle
0x180196545  nop     dword ptr [rax+rax+00h]
0x18019654a  mov     eax, edi
0x18019654c  jmp     short loc_180196589
0x18019654e  test    rbx, rbx
0x180196551  jz      short loc_180196562
0x180196553  mov     rcx, rbx; hObject
0x180196556  call    cs:__imp_CloseHandle
0x18019655d  nop     dword ptr [rax+rax+00h]
0x180196562  lea     rcx, [rsp+290h+var_248]; this
0x180196567  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x18019656c  mov     rcx, [rsp+290h+hObject]; hObject
0x180196571  lea     rax, [rcx-1]
0x180196575  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180196579  ja      short loc_180196587
0x18019657b  call    cs:__imp_CloseHandle
0x180196582  nop     dword ptr [rax+rax+00h]
0x180196587  xor     eax, eax
0x180196589  mov     rcx, [rbp+190h+var_20]
0x180196590  xor     rcx, rsp; StackCookie
0x180196593  call    __security_check_cookie
0x180196598  mov     rbx, [rsp+290h+arg_18]
0x1801965a0  add     rsp, 280h
0x1801965a7  pop     rdi
0x1801965a8  pop     rsi
0x1801965a9  pop     rbp
0x1801965aa  retn
```

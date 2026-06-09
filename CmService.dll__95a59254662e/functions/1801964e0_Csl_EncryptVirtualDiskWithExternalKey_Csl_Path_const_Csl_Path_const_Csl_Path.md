# Csl::EncryptVirtualDiskWithExternalKey(Csl::Path const &,Csl::Path const &,Csl::Path &)

- ea: `0x1801964e0`
- end: `0x18019671c`
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
- `0x1801959b4`
- `0x180195fcc`
- `0x1801964e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019661c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019661c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019658a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019658a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801966eb`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801965b9`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801965b9`
- `wcimage!WcMountVirtualDisk` at `0x18019654e`
- `wcimage!WcMountVirtualDisk` at `0x18019654e`

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
          (Csl *)&FVE_GUID_PROV_SCENARIO_FVECTL_PROTWITHEK_SANDBOX,
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
0x1801964e0  mov     [rsp-8+arg_18], rbx
0x1801964e5  push    rbp
0x1801964e6  push    rsi
0x1801964e7  push    rdi
0x1801964e8  lea     rbp, [rsp-180h]
0x1801964f0  sub     rsp, 280h
0x1801964f7  mov     rax, cs:__security_cookie
0x1801964fe  xor     rax, rsp
0x180196501  mov     [rbp+190h+var_20], rax
0x180196508  mov     rbx, rcx
0x18019650b  mov     [rsp+290h+hObject], 0
0x180196514  lea     rcx, [rsp+290h+hObject]
0x180196519  mov     rsi, r8
0x18019651c  mov     rdi, rdx
0x18019651f  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180196524  mov     rdx, [rbx]
0x180196527  xor     r9d, r9d
0x18019652a  mov     [rsp+290h+var_258], rax
0x18019652f  xor     r8d, r8d
0x180196532  mov     dword ptr [rsp+290h+hTemplateFile], 0
0x18019653a  xor     ecx, ecx
0x18019653c  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], 0
0x180196545  mov     qword ptr [rsp+290h+dwCreationDisposition], 0; unsigned int
0x18019654e  call    cs:__imp_WcMountVirtualDisk
0x180196555  nop     dword ptr [rax+rax+00h]
0x18019655a  mov     ebx, eax
0x18019655c  test    eax, eax
0x18019655e  jns     short loc_18019659D
0x180196560  mov     rcx, [rbp+198h]; this
0x180196567  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019656e  mov     r9d, eax; char *
0x180196571  mov     edx, 2F7h; void *
0x180196576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019657b  mov     rcx, [rsp+290h+hObject]; hObject
0x180196580  lea     rdx, [rcx-1]
0x180196584  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180196588  ja      short loc_180196596
0x18019658a  call    cs:__imp_CloseHandle
0x180196591  nop     dword ptr [rax+rax+00h]
0x180196596  mov     eax, ebx
0x180196598  jmp     loc_1801966F9
0x18019659d  mov     rcx, [rsp+290h+hObject]; VirtualDiskHandle
0x1801965a2  lea     r8, [rsp+290h+DiskPath]; DiskPath
0x1801965a7  lea     rdx, [rsp+290h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1801965ac  mov     [rsp+290h+var_248], rcx
0x1801965b1  mov     [rsp+290h+DiskPathSizeInBytes], 208h
0x1801965b9  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1801965c0  nop     dword ptr [rax+rax+00h]
0x1801965c5  test    eax, eax
0x1801965c7  jz      short loc_1801965F2
0x1801965c9  mov     rcx, [rbp+198h]; this
0x1801965d0  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1801965d7  mov     r9d, eax; char *
0x1801965da  mov     edx, 300h; void *
0x1801965df  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801965e4  lea     rcx, [rsp+290h+var_248]; this
0x1801965e9  mov     ebx, eax
0x1801965eb  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x1801965f0  jmp     short loc_18019657B
0x1801965f2  xor     r9d, r9d; lpSecurityAttributes
0x1801965f5  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x1801965fe  mov     [rsp+290h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180196606  lea     rcx, [rsp+290h+DiskPath]; lpFileName
0x18019660b  mov     edx, 0C0000000h; dwDesiredAccess
0x180196610  mov     [rsp+290h+dwCreationDisposition], 3; int
0x180196618  lea     r8d, [r9+1]; dwShareMode
0x18019661c  call    cs:__imp_CreateFileW
0x180196623  nop     dword ptr [rax+rax+00h]
0x180196628  mov     rbx, rax
0x18019662b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019662f  jnz     short loc_18019664B
0x180196631  mov     rcx, [rbp+198h]; this
0x180196638  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18019663f  mov     edx, 30Bh; void *
0x180196644  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180196649  jmp     short loc_1801965E4
0x18019664b  mov     r9, rsi; struct Path *
0x18019664e  lea     rcx, FVE_GUID_PROV_SCENARIO_FVECTL_PROTWITHEK_SANDBOX; this
0x180196655  mov     r8, rdi; void *
0x180196658  mov     rdx, rbx; struct _GUID *
0x18019665b  call    ?EncryptDiskWithExternalKey@Csl@@YAJPEBU_GUID@@PEAXAEBVPath@1@AEAV31@@Z; Csl::EncryptDiskWithExternalKey(_GUID const *,void *,Csl::Path const &,Csl::Path &)
0x180196660  mov     edi, eax
0x180196662  test    eax, eax
0x180196664  jns     short loc_1801966BE
0x180196666  mov     rcx, [rbp+198h]; this
0x18019666d  lea     r8, aOnecoreBaseGen_72; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180196674  mov     r9d, eax; char *
0x180196677  mov     edx, 311h; void *
0x18019667c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196681  test    rbx, rbx
0x180196684  jz      short loc_180196695
0x180196686  mov     rcx, rbx; hObject
0x180196689  call    cs:__imp_CloseHandle
0x180196690  nop     dword ptr [rax+rax+00h]
0x180196695  lea     rcx, [rsp+290h+var_248]; this
0x18019669a  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x18019669f  mov     rcx, [rsp+290h+hObject]; hObject
0x1801966a4  lea     rax, [rcx-1]
0x1801966a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801966ac  ja      short loc_1801966BA
0x1801966ae  call    cs:__imp_CloseHandle
0x1801966b5  nop     dword ptr [rax+rax+00h]
0x1801966ba  mov     eax, edi
0x1801966bc  jmp     short loc_1801966F9
0x1801966be  test    rbx, rbx
0x1801966c1  jz      short loc_1801966D2
0x1801966c3  mov     rcx, rbx; hObject
0x1801966c6  call    cs:__imp_CloseHandle
0x1801966cd  nop     dword ptr [rax+rax+00h]
0x1801966d2  lea     rcx, [rsp+290h+var_248]; this
0x1801966d7  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x1801966dc  mov     rcx, [rsp+290h+hObject]; hObject
0x1801966e1  lea     rax, [rcx-1]
0x1801966e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801966e9  ja      short loc_1801966F7
0x1801966eb  call    cs:__imp_CloseHandle
0x1801966f2  nop     dword ptr [rax+rax+00h]
0x1801966f7  xor     eax, eax
0x1801966f9  mov     rcx, [rbp+190h+var_20]
0x180196700  xor     rcx, rsp; StackCookie
0x180196703  call    __security_check_cookie
0x180196708  mov     rbx, [rsp+290h+arg_18]
0x180196710  add     rsp, 280h
0x180196717  pop     rdi
0x180196718  pop     rsi
0x180196719  pop     rbp
0x18019671a  retn
```

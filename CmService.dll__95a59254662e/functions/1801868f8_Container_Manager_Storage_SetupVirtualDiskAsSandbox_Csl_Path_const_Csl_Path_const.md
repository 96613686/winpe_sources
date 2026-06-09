# Container::Manager::Storage::SetupVirtualDiskAsSandbox(Csl::Path const &,Csl::Path const &)

- ea: `0x1801868f8`
- end: `0x180186b2b`
- name: `?SetupVirtualDiskAsSandbox@Storage@Manager@Container@@YAJAEBVPath@Csl@@0@Z`
- size: `563`
- prototype: `int(Container::Manager::Storage *__hidden this, const struct Path *, const struct Path *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18008815c`

## callees

- `0x180004bd0`
- `0x180008d04`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1801865e0`
- `0x1801868f8`
- `0x1801959b4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180186a33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180186a33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801869a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801869a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186af8`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801869d1`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1801869d1`
- `wcimage!WcMountVirtualDisk` at `0x180186966`
- `wcimage!WcMountVirtualDisk` at `0x180186966`

## pseudocode

```c
__int64 __fastcall Container::Manager::Storage::SetupVirtualDiskAsSandbox(
        Container::Manager::Storage *this,
        const struct Path *a2,
        const struct Path *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  DWORD VirtualDiskPhysicalPath; // eax
  int LastError; // eax
  Container::Manager::Storage *FileW; // rax
  const struct Path *v11; // r8
  const char *v12; // r9
  Container::Manager::Storage *v13; // rbx
  int v14; // eax
  unsigned int v15; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v18; // [rsp+48h] [rbp-B8h] BYREF
  ULONG DiskPathSizeInBytes[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR DiskPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  hObject = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v5 = WcMountVirtualDisk(0, *(_QWORD *)this, 0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)v5,
      0);
LABEL_3:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v6;
  }
  v18 = hObject;
  DiskPathSizeInBytes[0] = 520;
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(hObject, DiskPathSizeInBytes, DiskPath);
  if ( VirtualDiskPhysicalPath )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x3F7,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                  (const char *)VirtualDiskPhysicalPath,
                  0);
LABEL_8:
    v6 = LastError;
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v18);
    goto LABEL_3;
  }
  FileW = (Container::Manager::Storage *)CreateFileW(DiskPath, 0xC0000000, 0, 0, 3u, 0x20000080u, 0);
  v13 = FileW;
  if ( FileW == (Container::Manager::Storage *)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x402,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
                  v12);
    goto LABEL_8;
  }
  v14 = Container::Manager::Storage::SetupSandbox(FileW, a2, v11);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( v13 )
      CloseHandle(v13);
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v18);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\storage\\lib\\cmstorage.cpp",
      (const char *)(unsigned int)v14,
      dwCreationDisposition);
    if ( v13 )
      CloseHandle(v13);
    Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit((Csl::DismountVirtualDiskOnScopeExit *)&v18);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v15;
  }
}

```

## disassembly

```asm
0x1801868f8  mov     [rsp-8+arg_10], rbx
0x1801868fd  mov     [rsp-8+arg_18], rdi
0x180186902  push    rbp
0x180186903  lea     rbp, [rsp-180h]
0x18018690b  sub     rsp, 280h
0x180186912  mov     rax, cs:__security_cookie
0x180186919  xor     rax, rsp
0x18018691c  mov     [rbp+180h+var_10], rax
0x180186923  mov     rbx, rcx
0x180186926  mov     [rsp+280h+hObject], 0
0x18018692f  lea     rcx, [rsp+280h+hObject]
0x180186934  mov     rdi, rdx
0x180186937  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18018693c  mov     rdx, [rbx]
0x18018693f  xor     r9d, r9d
0x180186942  mov     [rsp+280h+var_248], rax
0x180186947  xor     r8d, r8d
0x18018694a  mov     dword ptr [rsp+280h+hTemplateFile], 0
0x180186952  xor     ecx, ecx
0x180186954  mov     qword ptr [rsp+280h+dwFlagsAndAttributes], 0
0x18018695d  mov     qword ptr [rsp+280h+dwCreationDisposition], 0; unsigned int
0x180186966  call    cs:__imp_WcMountVirtualDisk
0x18018696d  nop     dword ptr [rax+rax+00h]
0x180186972  mov     ebx, eax
0x180186974  test    eax, eax
0x180186976  jns     short loc_1801869B5
0x180186978  mov     rcx, [rbp+188h]; this
0x18018697f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186986  mov     r9d, eax; char *
0x180186989  mov     edx, 3EEh; void *
0x18018698e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186993  mov     rcx, [rsp+280h+hObject]; hObject
0x180186998  lea     rdx, [rcx-1]
0x18018699c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801869a0  ja      short loc_1801869AE
0x1801869a2  call    cs:__imp_CloseHandle
0x1801869a9  nop     dword ptr [rax+rax+00h]
0x1801869ae  mov     eax, ebx
0x1801869b0  jmp     loc_180186B06
0x1801869b5  mov     rcx, [rsp+280h+hObject]; VirtualDiskHandle
0x1801869ba  lea     r8, [rsp+280h+DiskPath]; DiskPath
0x1801869bf  lea     rdx, [rsp+280h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1801869c4  mov     [rsp+280h+var_238], rcx
0x1801869c9  mov     [rsp+280h+DiskPathSizeInBytes], 208h
0x1801869d1  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1801869d8  nop     dword ptr [rax+rax+00h]
0x1801869dd  test    eax, eax
0x1801869df  jz      short loc_180186A0A
0x1801869e1  mov     rcx, [rbp+188h]; this
0x1801869e8  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x1801869ef  mov     r9d, eax; char *
0x1801869f2  mov     edx, 3F7h; void *
0x1801869f7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801869fc  lea     rcx, [rsp+280h+var_238]; this
0x180186a01  mov     ebx, eax
0x180186a03  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180186a08  jmp     short loc_180186993
0x180186a0a  mov     [rsp+280h+hTemplateFile], 0; hTemplateFile
0x180186a13  lea     rcx, [rsp+280h+DiskPath]; lpFileName
0x180186a18  mov     [rsp+280h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x180186a20  xor     r9d, r9d; lpSecurityAttributes
0x180186a23  xor     r8d, r8d; dwShareMode
0x180186a26  mov     [rsp+280h+dwCreationDisposition], 3; int
0x180186a2e  mov     edx, 0C0000000h; dwDesiredAccess
0x180186a33  call    cs:__imp_CreateFileW
0x180186a3a  nop     dword ptr [rax+rax+00h]
0x180186a3f  mov     rbx, rax
0x180186a42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180186a46  jnz     short loc_180186A62
0x180186a48  mov     rcx, [rbp+188h]; this
0x180186a4f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186a56  mov     edx, 402h; void *
0x180186a5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180186a60  jmp     short loc_1801869FC
0x180186a62  mov     rdx, rdi; void *
0x180186a65  mov     rcx, rbx; this
0x180186a68  call    ?SetupSandbox@Storage@Manager@Container@@YAJPEAXAEBVPath@Csl@@@Z; Container::Manager::Storage::SetupSandbox(void *,Csl::Path const &)
0x180186a6d  mov     edi, eax
0x180186a6f  test    eax, eax
0x180186a71  jns     short loc_180186ACB
0x180186a73  mov     rcx, [rbp+188h]; this
0x180186a7a  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186a81  mov     r9d, eax; char *
0x180186a84  mov     edx, 405h; void *
0x180186a89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186a8e  test    rbx, rbx
0x180186a91  jz      short loc_180186AA2
0x180186a93  mov     rcx, rbx; hObject
0x180186a96  call    cs:__imp_CloseHandle
0x180186a9d  nop     dword ptr [rax+rax+00h]
0x180186aa2  lea     rcx, [rsp+280h+var_238]; this
0x180186aa7  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180186aac  mov     rcx, [rsp+280h+hObject]; hObject
0x180186ab1  lea     rax, [rcx-1]
0x180186ab5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180186ab9  ja      short loc_180186AC7
0x180186abb  call    cs:__imp_CloseHandle
0x180186ac2  nop     dword ptr [rax+rax+00h]
0x180186ac7  mov     eax, edi
0x180186ac9  jmp     short loc_180186B06
0x180186acb  test    rbx, rbx
0x180186ace  jz      short loc_180186ADF
0x180186ad0  mov     rcx, rbx; hObject
0x180186ad3  call    cs:__imp_CloseHandle
0x180186ada  nop     dword ptr [rax+rax+00h]
0x180186adf  lea     rcx, [rsp+280h+var_238]; this
0x180186ae4  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180186ae9  mov     rcx, [rsp+280h+hObject]; hObject
0x180186aee  lea     rax, [rcx-1]
0x180186af2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180186af6  ja      short loc_180186B04
0x180186af8  call    cs:__imp_CloseHandle
0x180186aff  nop     dword ptr [rax+rax+00h]
0x180186b04  xor     eax, eax
0x180186b06  mov     rcx, [rbp+180h+var_10]
0x180186b0d  xor     rcx, rsp; StackCookie
0x180186b10  call    __security_check_cookie
0x180186b15  lea     r11, [rsp+280h+var_s0]
0x180186b1d  mov     rbx, [r11+20h]
0x180186b21  mov     rdi, [r11+28h]
0x180186b25  mov     rsp, r11
0x180186b28  pop     rbp
0x180186b29  retn
```

# Container::Manager::Storage::SetupVirtualDiskAsSandbox(Csl::Path const &,Csl::Path const &)

- ea: `0x180186788`
- end: `0x1801869bb`
- name: `?SetupVirtualDiskAsSandbox@Storage@Manager@Container@@YAJAEBVPath@Csl@@0@Z`
- size: `563`
- prototype: `__int64 __fastcall(Container::Manager::Storage *this, const struct Path *, const struct Path *)`
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
- `0x180186470`
- `0x180186788`
- `0x180195844`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801868c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801868c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018694b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018694b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180186988`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180186861`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180186861`
- `wcimage!WcMountVirtualDisk` at `0x1801867f6`
- `wcimage!WcMountVirtualDisk` at `0x1801867f6`

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
0x180186788  mov     [rsp-8+arg_10], rbx
0x18018678d  mov     [rsp-8+arg_18], rdi
0x180186792  push    rbp
0x180186793  lea     rbp, [rsp-180h]
0x18018679b  sub     rsp, 280h
0x1801867a2  mov     rax, cs:__security_cookie
0x1801867a9  xor     rax, rsp
0x1801867ac  mov     [rbp+180h+var_10], rax
0x1801867b3  mov     rbx, rcx
0x1801867b6  mov     [rsp+280h+hObject], 0
0x1801867bf  lea     rcx, [rsp+280h+hObject]
0x1801867c4  mov     rdi, rdx
0x1801867c7  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x1801867cc  mov     rdx, [rbx]
0x1801867cf  xor     r9d, r9d
0x1801867d2  mov     [rsp+280h+var_248], rax
0x1801867d7  xor     r8d, r8d
0x1801867da  mov     dword ptr [rsp+280h+hTemplateFile], 0
0x1801867e2  xor     ecx, ecx
0x1801867e4  mov     qword ptr [rsp+280h+dwFlagsAndAttributes], 0
0x1801867ed  mov     qword ptr [rsp+280h+dwCreationDisposition], 0; unsigned int
0x1801867f6  call    cs:__imp_WcMountVirtualDisk
0x1801867fd  nop     dword ptr [rax+rax+00h]
0x180186802  mov     ebx, eax
0x180186804  test    eax, eax
0x180186806  jns     short loc_180186845
0x180186808  mov     rcx, [rbp+188h]; this
0x18018680f  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186816  mov     r9d, eax; char *
0x180186819  mov     edx, 3EEh; void *
0x18018681e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186823  mov     rcx, [rsp+280h+hObject]; hObject
0x180186828  lea     rdx, [rcx-1]
0x18018682c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180186830  ja      short loc_18018683E
0x180186832  call    cs:__imp_CloseHandle
0x180186839  nop     dword ptr [rax+rax+00h]
0x18018683e  mov     eax, ebx
0x180186840  jmp     loc_180186996
0x180186845  mov     rcx, [rsp+280h+hObject]; VirtualDiskHandle
0x18018684a  lea     r8, [rsp+280h+DiskPath]; DiskPath
0x18018684f  lea     rdx, [rsp+280h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180186854  mov     [rsp+280h+var_238], rcx
0x180186859  mov     [rsp+280h+DiskPathSizeInBytes], 208h
0x180186861  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180186868  nop     dword ptr [rax+rax+00h]
0x18018686d  test    eax, eax
0x18018686f  jz      short loc_18018689A
0x180186871  mov     rcx, [rbp+188h]; this
0x180186878  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x18018687f  mov     r9d, eax; char *
0x180186882  mov     edx, 3F7h; void *
0x180186887  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018688c  lea     rcx, [rsp+280h+var_238]; this
0x180186891  mov     ebx, eax
0x180186893  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180186898  jmp     short loc_180186823
0x18018689a  mov     [rsp+280h+hTemplateFile], 0; hTemplateFile
0x1801868a3  lea     rcx, [rsp+280h+DiskPath]; lpFileName
0x1801868a8  mov     [rsp+280h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x1801868b0  xor     r9d, r9d; lpSecurityAttributes
0x1801868b3  xor     r8d, r8d; dwShareMode
0x1801868b6  mov     [rsp+280h+dwCreationDisposition], 3; int
0x1801868be  mov     edx, 0C0000000h; dwDesiredAccess
0x1801868c3  call    cs:__imp_CreateFileW
0x1801868ca  nop     dword ptr [rax+rax+00h]
0x1801868cf  mov     rbx, rax
0x1801868d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801868d6  jnz     short loc_1801868F2
0x1801868d8  mov     rcx, [rbp+188h]; this
0x1801868df  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x1801868e6  mov     edx, 402h; void *
0x1801868eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801868f0  jmp     short loc_18018688C
0x1801868f2  mov     rdx, rdi; void *
0x1801868f5  mov     rcx, rbx; this
0x1801868f8  call    ?SetupSandbox@Storage@Manager@Container@@YAJPEAXAEBVPath@Csl@@@Z; Container::Manager::Storage::SetupSandbox(void *,Csl::Path const &)
0x1801868fd  mov     edi, eax
0x1801868ff  test    eax, eax
0x180186901  jns     short loc_18018695B
0x180186903  mov     rcx, [rbp+188h]; this
0x18018690a  lea     r8, aOnecoreBaseGen_36; "onecore\\base\\gendrv\\silos\\clem\\sto"...
0x180186911  mov     r9d, eax; char *
0x180186914  mov     edx, 405h; void *
0x180186919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018691e  test    rbx, rbx
0x180186921  jz      short loc_180186932
0x180186923  mov     rcx, rbx; hObject
0x180186926  call    cs:__imp_CloseHandle
0x18018692d  nop     dword ptr [rax+rax+00h]
0x180186932  lea     rcx, [rsp+280h+var_238]; this
0x180186937  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x18018693c  mov     rcx, [rsp+280h+hObject]; hObject
0x180186941  lea     rax, [rcx-1]
0x180186945  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180186949  ja      short loc_180186957
0x18018694b  call    cs:__imp_CloseHandle
0x180186952  nop     dword ptr [rax+rax+00h]
0x180186957  mov     eax, edi
0x180186959  jmp     short loc_180186996
0x18018695b  test    rbx, rbx
0x18018695e  jz      short loc_18018696F
0x180186960  mov     rcx, rbx; hObject
0x180186963  call    cs:__imp_CloseHandle
0x18018696a  nop     dword ptr [rax+rax+00h]
0x18018696f  lea     rcx, [rsp+280h+var_238]; this
0x180186974  call    ??1DismountVirtualDiskOnScopeExit@Csl@@QEAA@XZ; Csl::DismountVirtualDiskOnScopeExit::~DismountVirtualDiskOnScopeExit(void)
0x180186979  mov     rcx, [rsp+280h+hObject]; hObject
0x18018697e  lea     rax, [rcx-1]
0x180186982  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180186986  ja      short loc_180186994
0x180186988  call    cs:__imp_CloseHandle
0x18018698f  nop     dword ptr [rax+rax+00h]
0x180186994  xor     eax, eax
0x180186996  mov     rcx, [rbp+180h+var_10]
0x18018699d  xor     rcx, rsp; StackCookie
0x1801869a0  call    __security_check_cookie
0x1801869a5  lea     r11, [rsp+280h+var_s0]
0x1801869ad  mov     rbx, [r11+20h]
0x1801869b1  mov     rdi, [r11+28h]
0x1801869b5  mov     rsp, r11
0x1801869b8  pop     rbp
0x1801869b9  retn
```

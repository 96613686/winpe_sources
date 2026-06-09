# WptsInitialize(void)

- ea: `0x180016120`
- end: `0x1800161c0`
- name: `?WptsInitialize@@YAKXZ`
- size: `160`
- prototype: `DWORD(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180015544`
- `0x1800159c4`
- `0x180015b08`
- `0x180016120`
- `0x180020c02`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016159`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016159`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016165`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016194`

## string_xrefs

- `0x180016152`: `C:\windows\system32\TaskSchedulerSvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD WptsInitialize(void)
{
  HANDLE FirstFileW; // rbx
  signed int LastError; // ebx
  _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(g_szPreviousTaskSchedulerExecutable, &FindFileData);
  FindClose(FirstFileW);
  if ( FirstFileW != (HANDLE)-1LL )
    return 50;
  if ( (int)TsiInitialize() < 0 )
    return GetLastError();
  LastError = 0;
  if ( TsiRegisterRPCInterface() < 0 )
  {
    LastError = GetLastError();
    if ( LastError < 0 )
      TsiUninitialize();
  }
  return LastError;
}

```

## disassembly

```asm
0x180016120  push    rbx
0x180016122  sub     rsp, 280h
0x180016129  mov     rax, cs:__security_cookie
0x180016130  xor     rax, rsp
0x180016133  mov     [rsp+288h+var_18], rax
0x18001613b  xor     edx, edx; Val
0x18001613d  lea     rcx, [rsp+288h+FindFileData]; void *
0x180016142  mov     r8d, 250h; Size
0x180016148  call    memset_0
0x18001614d  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x180016152  lea     rcx, ?g_szPreviousTaskSchedulerExecutable@@3PAGA; "C:\\windows\\system32\\TaskSchedulerSvc"...
0x180016159  call    cs:__imp_FindFirstFileW
0x18001615f  mov     rcx, rax; hFindFile
0x180016162  mov     rbx, rax
0x180016165  call    cs:__imp_FindClose
0x18001616b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001616f  jz      short loc_180016178
0x180016171  mov     eax, 32h ; '2'
0x180016176  jmp     short loc_1800161A7
0x180016178  call    ?TsiInitialize@@YAJXZ; TsiInitialize(void)
0x18001617d  test    eax, eax
0x18001617f  jns     short loc_180016189
0x180016181  call    cs:__imp_GetLastError
0x180016187  jmp     short loc_1800161A7
0x180016189  xor     ebx, ebx
0x18001618b  call    ?TsiRegisterRPCInterface@@YAJXZ; TsiRegisterRPCInterface(void)
0x180016190  test    eax, eax
0x180016192  jns     short loc_1800161A5
0x180016194  call    cs:__imp_GetLastError
0x18001619a  mov     ebx, eax
0x18001619c  test    eax, eax
0x18001619e  jns     short loc_1800161A5
0x1800161a0  call    ?TsiUninitialize@@YAJXZ; TsiUninitialize(void)
0x1800161a5  mov     eax, ebx
0x1800161a7  mov     rcx, [rsp+288h+var_18]
0x1800161af  xor     rcx, rsp; StackCookie
0x1800161b2  call    __security_check_cookie
0x1800161b7  add     rsp, 280h
0x1800161be  pop     rbx
0x1800161bf  retn
```

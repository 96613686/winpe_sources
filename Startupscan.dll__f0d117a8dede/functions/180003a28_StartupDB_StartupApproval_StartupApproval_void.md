# StartupDB::StartupApproval::StartupApproval(void)

- ea: `0x180003a28`
- end: `0x180003abb`
- name: `??0StartupApproval@StartupDB@@QEAA@XZ`
- size: `147`
- prototype: `StartupDB::StartupApproval *__fastcall(StartupDB::StartupApproval *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003cfc`
- `0x180003dec`

## callees

- `0x180003a28`
- `0x1800040f6`
- `0x180004130`

## import_xrefs

- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180003a8e`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180003a8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003a73`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180003a73`

## pseudocode

```c
StartupDB::StartupApproval *__fastcall StartupDB::StartupApproval::StartupApproval(StartupDB::StartupApproval *this)
{
  const CHAR *v2; // rdx
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF
  char v5; // [rsp+138h] [rbp-20h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) && (v5 & 0x40) != 0 || SHWindowsPolicy(POLID_EnableAllStartupApplications, v2) )
    *((_DWORD *)this + 2) = 1;
  return this;
}

```

## disassembly

```asm
0x180003a28  push    rbx
0x180003a2a  sub     rsp, 150h
0x180003a31  mov     rax, cs:__security_cookie
0x180003a38  xor     rax, rsp
0x180003a3b  mov     [rsp+158h+var_18], rax
0x180003a43  mov     rbx, rcx
0x180003a46  mov     qword ptr [rcx], 0
0x180003a4d  mov     dword ptr [rcx+8], 0
0x180003a54  xor     edx, edx; Val
0x180003a56  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x180003a5b  mov     r8d, 118h; Size
0x180003a61  call    memset_0
0x180003a66  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x180003a6b  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180003a73  call    cs:__imp_GetVersionExW
0x180003a79  test    eax, eax
0x180003a7b  jz      short loc_180003A87
0x180003a7d  test    [rsp+158h+var_20], 40h
0x180003a85  jnz     short loc_180003A98
0x180003a87  lea     rcx, POLID_EnableAllStartupApplications; " "
0x180003a8e  call    cs:__imp_SHWindowsPolicy
0x180003a94  test    eax, eax
0x180003a96  jz      short loc_180003A9F
0x180003a98  mov     dword ptr [rbx+8], 1
0x180003a9f  mov     rax, rbx
0x180003aa2  mov     rcx, [rsp+158h+var_18]
0x180003aaa  xor     rcx, rsp; StackCookie
0x180003aad  call    __security_check_cookie
0x180003ab2  add     rsp, 150h
0x180003ab9  pop     rbx
0x180003aba  retn
```

# winreSetPriviledge

- ea: `0x180032dc8`
- end: `0x180032e8f`
- name: `winreSetPriviledge`
- size: `199`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180024ff0`
- `0x180028aac`
- `0x180032728`

## callees

- `0x180032dc8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180032df8`
- `KERNEL32!GetCurrentProcess` at `0x180032df8`
- `KERNEL32!CloseHandle` at `0x180032e6a`
- `KERNEL32!CloseHandle` at `0x180032e6a`
- `ADVAPI32!OpenProcessToken` at `0x180032e09`
- `ADVAPI32!OpenProcessToken` at `0x180032e09`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180032e24`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180032e24`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180032e50`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180032e50`

## pseudocode

```c
__int64 __fastcall winreSetPriviledge(LPCWSTR lpName)
{
  unsigned int v1; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    Luid[0].LowPart = 1;
    if ( LookupPrivilegeValueW(0, lpName, (PLUID)&Luid[0].HighPart) )
    {
      Luid[1].HighPart = 2;
      v1 = AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0x10u, 0, 0);
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x180032dc8  mov     [rsp+arg_8], rbx
0x180032dcd  mov     [rsp+arg_10], rbp
0x180032dd2  push    rdi
0x180032dd3  sub     rsp, 50h
0x180032dd7  mov     rax, cs:__security_cookie
0x180032dde  xor     rax, rsp
0x180032de1  mov     [rsp+58h+var_10], rax
0x180032de6  xorps   xmm0, xmm0
0x180032de9  xor     ebx, ebx
0x180032deb  mov     [rsp+58h+TokenHandle], rbx
0x180032df0  mov     rdi, rcx
0x180032df3  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x180032df8  call    cs:__imp_GetCurrentProcess
0x180032dfe  mov     rcx, rax; ProcessHandle
0x180032e01  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180032e06  lea     edx, [rbx+28h]; DesiredAccess
0x180032e09  call    cs:__imp_OpenProcessToken
0x180032e0f  test    eax, eax
0x180032e11  jz      short loc_180032E70
0x180032e13  lea     ebp, [rbx+1]
0x180032e16  mov     rdx, rdi; lpName
0x180032e19  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x180032e1e  mov     [rsp+58h+Luid.LowPart], ebp
0x180032e22  xor     ecx, ecx; lpSystemName
0x180032e24  call    cs:__imp_LookupPrivilegeValueW
0x180032e2a  test    eax, eax
0x180032e2c  jz      short loc_180032E5B
0x180032e2e  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180032e33  lea     r9d, [rbx+10h]; BufferLength
0x180032e37  mov     [rsp+58h+ReturnLength], rbx; ReturnLength
0x180032e3c  lea     r8, [rsp+58h+Luid]; NewState
0x180032e41  xor     edx, edx; DisableAllPrivileges
0x180032e43  mov     [rsp+58h+PreviousState], rbx; PreviousState
0x180032e48  mov     [rsp+58h+Luid.HighPart+8], 2
0x180032e50  call    cs:__imp_AdjustTokenPrivileges
0x180032e56  test    eax, eax
0x180032e58  cmovnz  ebx, ebp
0x180032e5b  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180032e60  lea     rdx, [rcx-1]
0x180032e64  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180032e68  ja      short loc_180032E70
0x180032e6a  call    cs:__imp_CloseHandle
0x180032e70  mov     eax, ebx
0x180032e72  mov     rcx, [rsp+58h+var_10]
0x180032e77  xor     rcx, rsp; StackCookie
0x180032e7a  call    __security_check_cookie
0x180032e7f  mov     rbx, [rsp+58h+arg_8]
0x180032e84  mov     rbp, [rsp+58h+arg_10]
0x180032e89  add     rsp, 50h
0x180032e8d  pop     rdi
0x180032e8e  retn
```

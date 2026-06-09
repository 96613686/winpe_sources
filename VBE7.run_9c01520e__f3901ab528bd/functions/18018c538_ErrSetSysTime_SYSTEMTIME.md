# ErrSetSysTime(_SYSTEMTIME)

- ea: `0x18018c538`
- end: `0x18018c62f`
- name: `?ErrSetSysTime@@YAIU_SYSTEMTIME@@@Z`
- size: `247`
- prototype: `unsigned int __fastcall(struct _SYSTEMTIME *__struct_ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18018be10`
- `0x18018be80`

## callees

- `0x18018c538`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018c5dc`
- `KERNEL32!GetLastError` at `0x18018c5dc`
- `KERNEL32!CloseHandle` at `0x18018c60d`
- `KERNEL32!CloseHandle` at `0x18018c60d`
- `KERNEL32!GetCurrentProcess` at `0x18018c56e`
- `KERNEL32!GetCurrentProcess` at `0x18018c56e`
- `KERNEL32!SetLocalTime` at `0x18018c5f4`
- `KERNEL32!SetLocalTime` at `0x18018c5f4`
- `ADVAPI32!LookupPrivilegeValueA` at `0x18018c595`
- `ADVAPI32!LookupPrivilegeValueA` at `0x18018c595`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18018c5d2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18018c5d2`
- `ADVAPI32!OpenProcessToken` at `0x18018c57e`
- `ADVAPI32!OpenProcessToken` at `0x18018c57e`

## string_xrefs

- `0x18018c58c`: `SeSystemtimePrivilege`

## pseudocode

```c
__int64 __fastcall ErrSetSysTime(struct _SYSTEMTIME *a1)
{
  SYSTEMTIME v1; // xmm0
  HANDLE CurrentProcess; // rax
  unsigned int v3; // ebx
  HANDLE TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-38h] BYREF
  int v7; // [rsp+40h] [rbp-30h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  v1 = *a1;
  TokenHandle = (HANDLE)-1LL;
  SystemTime = v1;
  if ( g_fChicago
    || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle))
    && LookupPrivilegeValueA(0, "SeSystemtimePrivilege", &Luid)
    && (NewState.Privileges[0].Luid = Luid,
        v7 = 2,
        NewState.Privileges[0].Attributes = 2,
        NewState.PrivilegeCount = 1,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0))
    && GetLastError() != 1300 )
  {
    v3 = !SetLocalTime(&SystemTime) ? 5 : 0;
  }
  else
  {
    v3 = 70;
  }
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18018c538  mov     [rsp-8+arg_8], rbx
0x18018c53d  push    rbp
0x18018c53e  mov     rbp, rsp
0x18018c541  sub     rsp, 70h
0x18018c545  mov     rax, cs:__security_cookie
0x18018c54c  xor     rax, rsp
0x18018c54f  mov     [rbp+var_8], rax
0x18018c553  movups  xmm0, xmmword ptr [rcx]
0x18018c556  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18018c55b  xor     ebx, ebx
0x18018c55d  cmp     cs:g_fChicago, ebx
0x18018c563  movdqu  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18018c568  jnz     loc_18018C5F0
0x18018c56e  call    cs:__imp_GetCurrentProcess
0x18018c574  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18018c578  lea     edx, [rbx+28h]; DesiredAccess
0x18018c57b  mov     rcx, rax; ProcessHandle
0x18018c57e  call    cs:__imp_OpenProcessToken
0x18018c584  test    eax, eax
0x18018c586  jz      short loc_18018C5E9
0x18018c588  lea     r8, [rbp+Luid]; lpLuid
0x18018c58c  lea     rdx, aSesystemtimepr; "SeSystemtimePrivilege"
0x18018c593  xor     ecx, ecx; lpSystemName
0x18018c595  call    cs:__imp_LookupPrivilegeValueA
0x18018c59b  test    eax, eax
0x18018c59d  jz      short loc_18018C5E9
0x18018c59f  mov     eax, [rbp+Luid.LowPart]
0x18018c5a2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18018c5a6  lea     edx, [rbx+2]
0x18018c5a9  mov     [rbp+NewState.Privileges.Luid.LowPart], eax
0x18018c5ac  mov     eax, [rbp+Luid.HighPart]
0x18018c5af  mov     [rbp+var_30], edx
0x18018c5b2  mov     [rbp+NewState.Privileges.Attributes], edx
0x18018c5b5  lea     r8, [rbp+NewState]; NewState
0x18018c5b9  xor     r9d, r9d; BufferLength
0x18018c5bc  xor     edx, edx; DisableAllPrivileges
0x18018c5be  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x18018c5c3  mov     [rbp+NewState.Privileges.Luid.HighPart], eax
0x18018c5c6  mov     [rbp+NewState.PrivilegeCount], 1
0x18018c5cd  mov     [rsp+70h+PreviousState], rbx; PreviousState
0x18018c5d2  call    cs:__imp_AdjustTokenPrivileges
0x18018c5d8  test    eax, eax
0x18018c5da  jz      short loc_18018C5E9
0x18018c5dc  call    cs:__imp_GetLastError
0x18018c5e2  cmp     eax, 514h
0x18018c5e7  jnz     short loc_18018C5F0
0x18018c5e9  mov     ebx, 46h ; 'F'
0x18018c5ee  jmp     short loc_18018C603
0x18018c5f0  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18018c5f4  call    cs:__imp_SetLocalTime
0x18018c5fa  neg     eax
0x18018c5fc  sbb     ebx, ebx
0x18018c5fe  not     ebx
0x18018c600  and     ebx, 5
0x18018c603  mov     rcx, [rbp+TokenHandle]; hObject
0x18018c607  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c60b  jz      short loc_18018C613
0x18018c60d  call    cs:__imp_CloseHandle
0x18018c613  mov     eax, ebx
0x18018c615  mov     rcx, [rbp+var_8]
0x18018c619  xor     rcx, rsp; StackCookie
0x18018c61c  call    __security_check_cookie
0x18018c621  mov     rbx, [rsp+70h+arg_8]
0x18018c629  add     rsp, 70h
0x18018c62d  pop     rbp
0x18018c62e  retn
```

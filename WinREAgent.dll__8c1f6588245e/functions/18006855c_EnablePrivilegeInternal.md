# EnablePrivilegeInternal

- ea: `0x18006855c`
- end: `0x180068653`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180068500`

## callees

- `0x18006855c`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1800685b3`
- `ADVAPI32!OpenProcessToken` at `0x1800685b3`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800685f6`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800685f6`
- `KERNEL32!GetCurrentProcess` at `0x1800685a3`
- `KERNEL32!GetCurrentProcess` at `0x1800685a3`
- `KERNEL32!CloseHandle` at `0x18006862a`
- `KERNEL32!CloseHandle` at `0x18006862a`
- `KERNEL32!GetLastError` at `0x180068600`
- `KERNEL32!GetLastError` at `0x180068600`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeInternal(LUID a1, DWORD a2, DWORD *a3)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  TokenHandle = 0;
  v3 = 0;
  NewState = 0;
  ReturnLength = 0;
  PreviousState = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.Privileges[0].Luid = a1;
    v3 = 1;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) || GetLastError() )
    {
      v3 = 0;
    }
    else if ( a3 )
    {
      if ( PreviousState.PrivilegeCount )
        *a3 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
      else
        *a3 = a2;
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18006855c  mov     [rsp-18h+arg_8], rbx
0x180068561  mov     [rsp-18h+arg_18], rsi
0x180068566  push    rbp
0x180068567  push    rdi
0x180068568  push    r14
0x18006856a  mov     rbp, rsp
0x18006856d  sub     rsp, 70h
0x180068571  mov     rax, cs:__security_cookie
0x180068578  xor     rax, rsp
0x18006857b  mov     [rbp+var_10], rax
0x18006857f  xorps   xmm0, xmm0
0x180068582  mov     [rbp+TokenHandle], 0
0x18006858a  xorps   xmm1, xmm1
0x18006858d  xor     edi, edi
0x18006858f  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180068593  mov     [rbp+var_40], edi
0x180068596  mov     rsi, r8
0x180068599  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18006859d  mov     r14d, edx
0x1800685a0  mov     rbx, rcx
0x1800685a3  call    cs:__imp_GetCurrentProcess
0x1800685a9  mov     rcx, rax; ProcessHandle
0x1800685ac  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800685b0  lea     edx, [rdi+28h]; DesiredAccess
0x1800685b3  call    cs:__imp_OpenProcessToken
0x1800685b9  test    eax, eax
0x1800685bb  jz      short loc_180068630
0x1800685bd  mov     eax, r14d
0x1800685c0  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x1800685c4  neg     eax
0x1800685c6  lea     r8, [rbp+NewState]; NewState
0x1800685ca  mov     edi, 1
0x1800685cf  lea     rax, [rbp+var_40]
0x1800685d3  sbb     ecx, ecx
0x1800685d5  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800685da  and     ecx, 2
0x1800685dd  mov     [rbp+NewState.PrivilegeCount], edi
0x1800685e0  mov     [rbp+NewState.Privileges.Attributes], ecx
0x1800685e3  lea     rax, [rbp+var_20]
0x1800685e7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800685eb  lea     r9d, [rdi+0Fh]; BufferLength
0x1800685ef  xor     edx, edx; DisableAllPrivileges
0x1800685f1  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800685f6  call    cs:__imp_AdjustTokenPrivileges
0x1800685fc  test    eax, eax
0x1800685fe  jz      short loc_180068624
0x180068600  call    cs:__imp_GetLastError
0x180068606  test    eax, eax
0x180068608  jnz     short loc_180068624
0x18006860a  test    rsi, rsi
0x18006860d  jz      short loc_180068626
0x18006860f  cmp     [rbp+var_20.PrivilegeCount], eax
0x180068612  jnz     short loc_180068619
0x180068614  mov     [rsi], r14d
0x180068617  jmp     short loc_180068626
0x180068619  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18006861c  shr     eax, 1
0x18006861e  and     eax, edi
0x180068620  mov     [rsi], eax
0x180068622  jmp     short loc_180068626
0x180068624  xor     edi, edi
0x180068626  mov     rcx, [rbp+TokenHandle]; hObject
0x18006862a  call    cs:__imp_CloseHandle
0x180068630  mov     eax, edi
0x180068632  mov     rcx, [rbp+var_10]
0x180068636  xor     rcx, rsp; StackCookie
0x180068639  call    __security_check_cookie
0x18006863e  lea     r11, [rsp+70h+var_s0]
0x180068643  mov     rbx, [r11+28h]
0x180068647  mov     rsi, [r11+38h]
0x18006864b  mov     rsp, r11
0x18006864e  pop     r14
0x180068650  pop     rdi
0x180068651  pop     rbp
0x180068652  retn
```

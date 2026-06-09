# EnablePrivilegeInternal

- ea: `0x1400289e0`
- end: `0x140028af3`
- name: `EnablePrivilegeInternal`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140028980`

## callees

- `0x1400289e0`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140028a36`
- `ADVAPI32!OpenProcessToken` at `0x140028a36`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140028a83`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140028a83`
- `KERNEL32!CloseHandle` at `0x140028ac3`
- `KERNEL32!CloseHandle` at `0x140028ac3`
- `KERNEL32!GetLastError` at `0x140028a93`
- `KERNEL32!GetLastError` at `0x140028a93`
- `KERNEL32!GetCurrentProcess` at `0x140028a20`
- `KERNEL32!GetCurrentProcess` at `0x140028a20`

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
  PreviousState = 0;
  ReturnLength = 0;
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
0x1400289e0  mov     [rsp-18h+arg_8], rbx
0x1400289e5  mov     [rsp-18h+arg_18], rsi
0x1400289ea  push    rbp
0x1400289eb  push    rdi
0x1400289ec  push    r14
0x1400289ee  mov     rbp, rsp
0x1400289f1  sub     rsp, 70h
0x1400289f5  mov     rax, cs:__security_cookie
0x1400289fc  xor     rax, rsp
0x1400289ff  mov     [rbp+var_10], rax
0x140028a03  xorps   xmm0, xmm0
0x140028a06  mov     [rbp+TokenHandle], 0
0x140028a0e  xor     edi, edi
0x140028a10  mov     rsi, r8
0x140028a13  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm0
0x140028a17  mov     [rbp+var_40], edi
0x140028a1a  mov     r14d, edx
0x140028a1d  mov     rbx, rcx
0x140028a20  call    cs:__imp_GetCurrentProcess
0x140028a27  nop     dword ptr [rax+rax+00h]
0x140028a2c  mov     rcx, rax; ProcessHandle
0x140028a2f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140028a33  lea     edx, [rdi+28h]; DesiredAccess
0x140028a36  call    cs:__imp_OpenProcessToken
0x140028a3d  nop     dword ptr [rax+rax+00h]
0x140028a42  test    eax, eax
0x140028a44  jz      loc_140028ACF
0x140028a4a  mov     eax, r14d
0x140028a4d  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x140028a51  neg     eax
0x140028a53  lea     r8, [rbp+NewState]; NewState
0x140028a57  mov     edi, 1
0x140028a5c  lea     rax, [rbp+var_40]
0x140028a60  sbb     ecx, ecx
0x140028a62  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x140028a67  and     ecx, 2
0x140028a6a  mov     [rbp+NewState.PrivilegeCount], edi
0x140028a6d  mov     [rbp+NewState.Privileges.Attributes], ecx
0x140028a70  lea     rax, [rbp+var_20]
0x140028a74  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140028a78  lea     r9d, [rdi+0Fh]; BufferLength
0x140028a7c  xor     edx, edx; DisableAllPrivileges
0x140028a7e  mov     [rsp+70h+PreviousState], rax; PreviousState
0x140028a83  call    cs:__imp_AdjustTokenPrivileges
0x140028a8a  nop     dword ptr [rax+rax+00h]
0x140028a8f  test    eax, eax
0x140028a91  jz      short loc_140028ABD
0x140028a93  call    cs:__imp_GetLastError
0x140028a9a  nop     dword ptr [rax+rax+00h]
0x140028a9f  test    eax, eax
0x140028aa1  jnz     short loc_140028ABD
0x140028aa3  test    rsi, rsi
0x140028aa6  jz      short loc_140028ABF
0x140028aa8  cmp     [rbp+var_20.PrivilegeCount], eax
0x140028aab  jnz     short loc_140028AB2
0x140028aad  mov     [rsi], r14d
0x140028ab0  jmp     short loc_140028ABF
0x140028ab2  mov     eax, [rbp+var_20.Privileges.Attributes]
0x140028ab5  shr     eax, 1
0x140028ab7  and     eax, edi
0x140028ab9  mov     [rsi], eax
0x140028abb  jmp     short loc_140028ABF
0x140028abd  xor     edi, edi
0x140028abf  mov     rcx, [rbp+TokenHandle]; hObject
0x140028ac3  call    cs:__imp_CloseHandle
0x140028aca  nop     dword ptr [rax+rax+00h]
0x140028acf  mov     eax, edi
0x140028ad1  mov     rcx, [rbp+var_10]
0x140028ad5  xor     rcx, rsp; StackCookie
0x140028ad8  call    __security_check_cookie
0x140028add  lea     r11, [rsp+70h+var_s0]
0x140028ae2  mov     rbx, [r11+28h]
0x140028ae6  mov     rsi, [r11+38h]
0x140028aea  mov     rsp, r11
0x140028aed  pop     r14
0x140028aef  pop     rdi
0x140028af0  pop     rbp
0x140028af1  retn
```

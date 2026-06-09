# EnablePrivilegeInternal

- ea: `0x180067ee4`
- end: `0x180067ffe`
- name: `EnablePrivilegeInternal`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067e80`

## callees

- `0x180067ee4`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067f2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067f41`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067fce`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180067f8e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180067f8e`

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
0x180067ee4  mov     [rsp-18h+arg_8], rbx
0x180067ee9  mov     [rsp-18h+arg_18], rsi
0x180067eee  push    rbp
0x180067eef  push    rdi
0x180067ef0  push    r14
0x180067ef2  mov     rbp, rsp
0x180067ef5  sub     rsp, 70h
0x180067ef9  mov     rax, cs:__security_cookie
0x180067f00  xor     rax, rsp
0x180067f03  mov     [rbp+var_10], rax
0x180067f07  xorps   xmm0, xmm0
0x180067f0a  mov     [rbp+TokenHandle], 0
0x180067f12  xorps   xmm1, xmm1
0x180067f15  xor     edi, edi
0x180067f17  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180067f1b  mov     [rbp+var_40], edi
0x180067f1e  mov     rsi, r8
0x180067f21  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x180067f25  mov     r14d, edx
0x180067f28  mov     rbx, rcx
0x180067f2b  call    cs:__imp_GetCurrentProcess
0x180067f32  nop     dword ptr [rax+rax+00h]
0x180067f37  mov     rcx, rax; ProcessHandle
0x180067f3a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180067f3e  lea     edx, [rdi+28h]; DesiredAccess
0x180067f41  call    cs:__imp_OpenProcessToken
0x180067f48  nop     dword ptr [rax+rax+00h]
0x180067f4d  test    eax, eax
0x180067f4f  jz      loc_180067FDA
0x180067f55  mov     eax, r14d
0x180067f58  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x180067f5c  neg     eax
0x180067f5e  lea     r8, [rbp+NewState]; NewState
0x180067f62  mov     edi, 1
0x180067f67  lea     rax, [rbp+var_40]
0x180067f6b  sbb     ecx, ecx
0x180067f6d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180067f72  and     ecx, 2
0x180067f75  mov     [rbp+NewState.PrivilegeCount], edi
0x180067f78  mov     [rbp+NewState.Privileges.Attributes], ecx
0x180067f7b  lea     rax, [rbp+var_20]
0x180067f7f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180067f83  lea     r9d, [rdi+0Fh]; BufferLength
0x180067f87  xor     edx, edx; DisableAllPrivileges
0x180067f89  mov     [rsp+70h+PreviousState], rax; PreviousState
0x180067f8e  call    cs:__imp_AdjustTokenPrivileges
0x180067f95  nop     dword ptr [rax+rax+00h]
0x180067f9a  test    eax, eax
0x180067f9c  jz      short loc_180067FC8
0x180067f9e  call    cs:__imp_GetLastError
0x180067fa5  nop     dword ptr [rax+rax+00h]
0x180067faa  test    eax, eax
0x180067fac  jnz     short loc_180067FC8
0x180067fae  test    rsi, rsi
0x180067fb1  jz      short loc_180067FCA
0x180067fb3  cmp     [rbp+var_20.PrivilegeCount], eax
0x180067fb6  jnz     short loc_180067FBD
0x180067fb8  mov     [rsi], r14d
0x180067fbb  jmp     short loc_180067FCA
0x180067fbd  mov     eax, [rbp+var_20.Privileges.Attributes]
0x180067fc0  shr     eax, 1
0x180067fc2  and     eax, edi
0x180067fc4  mov     [rsi], eax
0x180067fc6  jmp     short loc_180067FCA
0x180067fc8  xor     edi, edi
0x180067fca  mov     rcx, [rbp+TokenHandle]; hObject
0x180067fce  call    cs:__imp_CloseHandle
0x180067fd5  nop     dword ptr [rax+rax+00h]
0x180067fda  mov     eax, edi
0x180067fdc  mov     rcx, [rbp+var_10]
0x180067fe0  xor     rcx, rsp; StackCookie
0x180067fe3  call    __security_check_cookie
0x180067fe8  lea     r11, [rsp+70h+var_s0]
0x180067fed  mov     rbx, [r11+28h]
0x180067ff1  mov     rsi, [r11+38h]
0x180067ff5  mov     rsp, r11
0x180067ff8  pop     r14
0x180067ffa  pop     rdi
0x180067ffb  pop     rbp
0x180067ffc  retn
```

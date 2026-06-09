# EnablePrivilegeInternal

- ea: `0x18003e7f0`
- end: `0x18003e8e7`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e794`

## callees

- `0x18003e7f0`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e894`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e847`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003e847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e837`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8be`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003e88a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003e88a`

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
0x18003e7f0  mov     [rsp-18h+arg_8], rbx
0x18003e7f5  mov     [rsp-18h+arg_18], rsi
0x18003e7fa  push    rbp
0x18003e7fb  push    rdi
0x18003e7fc  push    r14
0x18003e7fe  mov     rbp, rsp
0x18003e801  sub     rsp, 70h
0x18003e805  mov     rax, cs:__security_cookie
0x18003e80c  xor     rax, rsp
0x18003e80f  mov     [rbp+var_10], rax
0x18003e813  xorps   xmm0, xmm0
0x18003e816  mov     [rbp+TokenHandle], 0
0x18003e81e  xorps   xmm1, xmm1
0x18003e821  xor     edi, edi
0x18003e823  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003e827  mov     [rbp+var_40], edi
0x18003e82a  mov     rsi, r8
0x18003e82d  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x18003e831  mov     r14d, edx
0x18003e834  mov     rbx, rcx
0x18003e837  call    cs:__imp_GetCurrentProcess
0x18003e83d  mov     rcx, rax; ProcessHandle
0x18003e840  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003e844  lea     edx, [rdi+28h]; DesiredAccess
0x18003e847  call    cs:__imp_OpenProcessToken
0x18003e84d  test    eax, eax
0x18003e84f  jz      short loc_18003E8C4
0x18003e851  mov     eax, r14d
0x18003e854  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x18003e858  neg     eax
0x18003e85a  lea     r8, [rbp+NewState]; NewState
0x18003e85e  mov     edi, 1
0x18003e863  lea     rax, [rbp+var_40]
0x18003e867  sbb     ecx, ecx
0x18003e869  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003e86e  and     ecx, 2
0x18003e871  mov     [rbp+NewState.PrivilegeCount], edi
0x18003e874  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18003e877  lea     rax, [rbp+var_20]
0x18003e87b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003e87f  lea     r9d, [rdi+0Fh]; BufferLength
0x18003e883  xor     edx, edx; DisableAllPrivileges
0x18003e885  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18003e88a  call    cs:__imp_AdjustTokenPrivileges
0x18003e890  test    eax, eax
0x18003e892  jz      short loc_18003E8B8
0x18003e894  call    cs:__imp_GetLastError
0x18003e89a  test    eax, eax
0x18003e89c  jnz     short loc_18003E8B8
0x18003e89e  test    rsi, rsi
0x18003e8a1  jz      short loc_18003E8BA
0x18003e8a3  cmp     [rbp+var_20.PrivilegeCount], eax
0x18003e8a6  jnz     short loc_18003E8AD
0x18003e8a8  mov     [rsi], r14d
0x18003e8ab  jmp     short loc_18003E8BA
0x18003e8ad  mov     eax, [rbp+var_20.Privileges.Attributes]
0x18003e8b0  shr     eax, 1
0x18003e8b2  and     eax, edi
0x18003e8b4  mov     [rsi], eax
0x18003e8b6  jmp     short loc_18003E8BA
0x18003e8b8  xor     edi, edi
0x18003e8ba  mov     rcx, [rbp+TokenHandle]; hObject
0x18003e8be  call    cs:__imp_CloseHandle
0x18003e8c4  mov     eax, edi
0x18003e8c6  mov     rcx, [rbp+var_10]
0x18003e8ca  xor     rcx, rsp; StackCookie
0x18003e8cd  call    __security_check_cookie
0x18003e8d2  lea     r11, [rsp+70h+var_s0]
0x18003e8d7  mov     rbx, [r11+28h]
0x18003e8db  mov     rsi, [r11+38h]
0x18003e8df  mov     rsp, r11
0x18003e8e2  pop     r14
0x18003e8e4  pop     rdi
0x18003e8e5  pop     rbp
0x18003e8e6  retn
```

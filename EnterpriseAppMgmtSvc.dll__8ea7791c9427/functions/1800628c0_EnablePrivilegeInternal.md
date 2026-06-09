# EnablePrivilegeInternal

- ea: `0x1800628c0`
- end: `0x1800629b7`
- name: `EnablePrivilegeInternal`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062864`

## callees

- `0x1800628c0`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062907`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062917`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062964`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006298e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006298e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006295a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006295a`

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
0x1800628c0  mov     [rsp-18h+arg_8], rbx
0x1800628c5  mov     [rsp-18h+arg_18], rsi
0x1800628ca  push    rbp
0x1800628cb  push    rdi
0x1800628cc  push    r14
0x1800628ce  mov     rbp, rsp
0x1800628d1  sub     rsp, 70h
0x1800628d5  mov     rax, cs:__security_cookie
0x1800628dc  xor     rax, rsp
0x1800628df  mov     [rbp+var_10], rax
0x1800628e3  xorps   xmm0, xmm0
0x1800628e6  mov     [rbp+TokenHandle], 0
0x1800628ee  xorps   xmm1, xmm1
0x1800628f1  xor     edi, edi
0x1800628f3  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800628f7  mov     [rbp+var_40], edi
0x1800628fa  mov     rsi, r8
0x1800628fd  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x180062901  mov     r14d, edx
0x180062904  mov     rbx, rcx
0x180062907  call    cs:__imp_GetCurrentProcess
0x18006290d  mov     rcx, rax; ProcessHandle
0x180062910  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180062914  lea     edx, [rdi+28h]; DesiredAccess
0x180062917  call    cs:__imp_OpenProcessToken
0x18006291d  test    eax, eax
0x18006291f  jz      short loc_180062994
0x180062921  mov     eax, r14d
0x180062924  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x180062928  neg     eax
0x18006292a  lea     r8, [rbp+NewState]; NewState
0x18006292e  mov     edi, 1
0x180062933  lea     rax, [rbp+var_40]
0x180062937  sbb     ecx, ecx
0x180062939  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18006293e  and     ecx, 2
0x180062941  mov     [rbp+NewState.PrivilegeCount], edi
0x180062944  mov     [rbp+NewState.Privileges.Attributes], ecx
0x180062947  lea     rax, [rbp+var_20]
0x18006294b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18006294f  lea     r9d, [rdi+0Fh]; BufferLength
0x180062953  xor     edx, edx; DisableAllPrivileges
0x180062955  mov     [rsp+70h+PreviousState], rax; PreviousState
0x18006295a  call    cs:__imp_AdjustTokenPrivileges
0x180062960  test    eax, eax
0x180062962  jz      short loc_180062988
0x180062964  call    cs:__imp_GetLastError
0x18006296a  test    eax, eax
0x18006296c  jnz     short loc_180062988
0x18006296e  test    rsi, rsi
0x180062971  jz      short loc_18006298A
0x180062973  cmp     [rbp+var_20.PrivilegeCount], eax
0x180062976  jnz     short loc_18006297D
0x180062978  mov     [rsi], r14d
0x18006297b  jmp     short loc_18006298A
0x18006297d  mov     eax, [rbp+var_20.Privileges.Attributes]
0x180062980  shr     eax, 1
0x180062982  and     eax, edi
0x180062984  mov     [rsi], eax
0x180062986  jmp     short loc_18006298A
0x180062988  xor     edi, edi
0x18006298a  mov     rcx, [rbp+TokenHandle]; hObject
0x18006298e  call    cs:__imp_CloseHandle
0x180062994  mov     eax, edi
0x180062996  mov     rcx, [rbp+var_10]
0x18006299a  xor     rcx, rsp; StackCookie
0x18006299d  call    __security_check_cookie
0x1800629a2  lea     r11, [rsp+70h+var_s0]
0x1800629a7  mov     rbx, [r11+28h]
0x1800629ab  mov     rsi, [r11+38h]
0x1800629af  mov     rsp, r11
0x1800629b2  pop     r14
0x1800629b4  pop     rdi
0x1800629b5  pop     rbp
0x1800629b6  retn
```

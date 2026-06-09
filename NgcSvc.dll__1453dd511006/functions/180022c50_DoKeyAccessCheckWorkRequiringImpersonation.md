# DoKeyAccessCheckWorkRequiringImpersonation

- ea: `0x180022c50`
- end: `0x180022e26`
- name: `DoKeyAccessCheckWorkRequiringImpersonation`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e12c`

## callees

- `0x180022c50`
- `0x18005fb04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022de9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022d83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022d83`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022c90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022e1b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022dca`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022dca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022cf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022cf3`
- `RPCRT4!RpcRevertToSelf` at `0x180022d01`
- `RPCRT4!RpcRevertToSelf` at `0x180022e0d`
- `RPCRT4!RpcRevertToSelf` at `0x180022d01`
- `RPCRT4!RpcRevertToSelf` at `0x180022e0d`
- `RPCRT4!RpcImpersonateClient` at `0x180022cac`
- `RPCRT4!RpcImpersonateClient` at `0x180022cac`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180022d1d`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180022d1d`

## pseudocode

```c
RPC_STATUS __fastcall DoKeyAccessCheckWorkRequiringImpersonation(void *a1, int a2, int a3, _QWORD *a4)
{
  int v5; // esi
  HANDLE CurrentThread; // rax
  void *v7; // rdi
  signed int LastError; // ebx
  RPC_STATUS result; // eax
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength[2]; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle[4]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int TokenInformation; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = a3;
  v5 = 0;
  if ( a2 )
  {
    result = RpcImpersonateClient(a1);
    if ( result )
    {
      if ( result != 1725 )
        return result;
    }
    else
    {
      v5 = 1;
    }
  }
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xAu, TokenHandle) )
      {
        *(_QWORD *)ReturnLength = 0;
        if ( DuplicateTokenEx(
               TokenHandle[0],
               0x2000000u,
               0,
               SecurityIdentification,
               TokenImpersonation,
               (PHANDLE)ReturnLength) )
        {
          CloseHandle(TokenHandle[0]);
          v7 = *(void **)ReturnLength;
          goto LABEL_4;
        }
      }
      LastError = GetLastError();
    }
    v7 = 0;
    if ( TokenHandle[0] )
      CloseHandle(TokenHandle[0]);
    if ( LastError < 0 )
      goto LABEL_15;
    goto LABEL_8;
  }
  v7 = TokenHandle[0];
LABEL_4:
  TokenHandle[0] = 0;
  LastError = 0;
LABEL_8:
  LOBYTE(v14) = 0;
  TokenInformation = 0;
  ReturnLength[0] = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
  {
    if ( v5 )
    {
      RpcRevertToSelf();
      v5 = 0;
    }
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, &v14)
      && (_BYTE)v14 )
    {
      LastError = -2146893808;
    }
    else
    {
      *a4 = v7;
      v7 = 0;
    }
  }
  else
  {
    LastError = -2146893808;
  }
LABEL_15:
  if ( v5 )
    RpcRevertToSelf();
  if ( v7 )
    CloseHandle(v7);
  return LastError;
}

```

## disassembly

```asm
0x180022c50  mov     [rsp+arg_10], r8d
0x180022c55  push    rbp
0x180022c56  push    rsi
0x180022c57  push    r14
0x180022c59  sub     rsp, 40h
0x180022c5d  xor     ebp, ebp
0x180022c5f  mov     r14, r9
0x180022c62  mov     esi, ebp
0x180022c64  test    edx, edx
0x180022c66  jnz     short loc_180022CAC
0x180022c68  mov     [rsp+58h+arg_0], rbx
0x180022c6d  mov     [rsp+58h+arg_18], rdi
0x180022c72  mov     [rsp+58h+TokenHandle], rbp
0x180022c77  call    cs:__imp_GetCurrentThread
0x180022c7d  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180022c82  mov     edx, 8; DesiredAccess
0x180022c87  mov     rcx, rax; ThreadHandle
0x180022c8a  mov     r8d, 1; OpenAsSelf
0x180022c90  call    cs:__imp_OpenThreadToken
0x180022c96  test    eax, eax
0x180022c98  jz      loc_180022D74
0x180022c9e  mov     rdi, [rsp+58h+TokenHandle]
0x180022ca3  mov     [rsp+58h+TokenHandle], rbp
0x180022ca8  mov     ebx, ebp
0x180022caa  jmp     short loc_180022CC5
0x180022cac  call    cs:__imp_RpcImpersonateClient
0x180022cb2  test    eax, eax
0x180022cb4  jnz     loc_180022D68
0x180022cba  mov     esi, 1
0x180022cbf  jmp     short loc_180022C68
0x180022cc1  test    ebx, ebx
0x180022cc3  js      short loc_180022D34
0x180022cc5  lea     rax, [rsp+58h+var_28]
0x180022cca  mov     byte ptr [rsp+58h+arg_10], bpl
0x180022ccf  mov     r9d, 4; TokenInformationLength
0x180022cd5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180022cda  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180022cdf  mov     [rsp+58h+TokenInformation], ebp
0x180022ce3  mov     edx, 0Ch; TokenInformationClass
0x180022ce8  mov     [rsp+58h+var_28], ebp
0x180022cec  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180022cf3  call    cs:__imp_GetTokenInformation
0x180022cf9  test    eax, eax
0x180022cfb  jz      short loc_180022D5A
0x180022cfd  test    esi, esi
0x180022cff  jz      short loc_180022D09
0x180022d01  call    cs:__imp_RpcRevertToSelf
0x180022d07  mov     esi, ebp
0x180022d09  call    IsWinStationIsSessionRemoteablePresent
0x180022d0e  test    al, al
0x180022d10  jz      short loc_180022D2E
0x180022d12  mov     edx, [rsp+58h+TokenInformation]
0x180022d16  lea     r8, [rsp+58h+arg_10]
0x180022d1b  xor     ecx, ecx
0x180022d1d  call    cs:__imp_WinStationIsSessionRemoteable
0x180022d23  test    al, al
0x180022d25  jz      short loc_180022D2E
0x180022d27  cmp     byte ptr [rsp+58h+arg_10], bpl
0x180022d2c  jnz     short loc_180022D61
0x180022d2e  mov     [r14], rdi
0x180022d31  mov     rdi, rbp
0x180022d34  test    esi, esi
0x180022d36  jnz     loc_180022E0D
0x180022d3c  test    rdi, rdi
0x180022d3f  jnz     loc_180022E18
0x180022d45  mov     rdi, [rsp+58h+arg_18]
0x180022d4a  mov     eax, ebx
0x180022d4c  mov     rbx, [rsp+58h+arg_0]
0x180022d51  add     rsp, 40h
0x180022d55  pop     r14
0x180022d57  pop     rsi
0x180022d58  pop     rbp
0x180022d59  retn
0x180022d5a  mov     ebx, 80090010h
0x180022d5f  jmp     short loc_180022D34
0x180022d61  mov     ebx, 80090010h
0x180022d66  jmp     short loc_180022D34
0x180022d68  cmp     eax, 6BDh
0x180022d6d  jnz     short loc_180022D51
0x180022d6f  jmp     loc_180022C68
0x180022d74  call    cs:__imp_GetLastError
0x180022d7a  mov     ebx, eax
0x180022d7c  cmp     eax, 3F0h
0x180022d81  jnz     short loc_180022DF1
0x180022d83  call    cs:__imp_GetCurrentProcess
0x180022d89  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180022d8e  mov     edx, 0Ah; DesiredAccess
0x180022d93  mov     rcx, rax; ProcessHandle
0x180022d96  call    cs:__imp_OpenProcessToken
0x180022d9c  test    eax, eax
0x180022d9e  jz      short loc_180022DE9
0x180022da0  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x180022da5  lea     rax, [rsp+58h+var_28]
0x180022daa  mov     [rsp+58h+phNewToken], rax; phNewToken
0x180022daf  mov     r9d, 1; ImpersonationLevel
0x180022db5  xor     r8d, r8d; lpTokenAttributes
0x180022db8  mov     dword ptr [rsp+58h+ReturnLength], 2; TokenType
0x180022dc0  mov     edx, 2000000h; dwDesiredAccess
0x180022dc5  mov     qword ptr [rsp+58h+var_28], rbp
0x180022dca  call    cs:__imp_DuplicateTokenEx
0x180022dd0  test    eax, eax
0x180022dd2  jz      short loc_180022DE9
0x180022dd4  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180022dd9  call    cs:__imp_CloseHandle
0x180022ddf  mov     rdi, qword ptr [rsp+58h+var_28]
0x180022de4  jmp     loc_180022CA3
0x180022de9  call    cs:__imp_GetLastError
0x180022def  mov     ebx, eax
0x180022df1  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180022df6  mov     rdi, rbp
0x180022df9  test    rcx, rcx
0x180022dfc  jz      loc_180022CC1
0x180022e02  call    cs:__imp_CloseHandle
0x180022e08  jmp     loc_180022CC1
0x180022e0d  call    cs:__imp_RpcRevertToSelf
0x180022e13  jmp     loc_180022D3C
0x180022e18  mov     rcx, rdi; hObject
0x180022e1b  call    cs:__imp_CloseHandle
0x180022e21  jmp     loc_180022D45
```

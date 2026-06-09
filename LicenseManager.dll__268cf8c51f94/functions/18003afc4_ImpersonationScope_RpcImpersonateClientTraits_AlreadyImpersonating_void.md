# ImpersonationScope<RpcImpersonateClientTraits>::AlreadyImpersonating(void)

- ea: `0x18003afc4`
- end: `0x18003b093`
- name: `?AlreadyImpersonating@?$ImpersonationScope@URpcImpersonateClientTraits@@@@CA_NXZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003af60`

## callees

- `0x1800119e0`
- `0x18003afc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b05c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b07a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b07a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003afeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003afeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b003`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b003`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b033`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b033`

## pseudocode

```c
bool ImpersonationScope<RpcImpersonateClientTraits>::AlreadyImpersonating()
{
  bool v0; // bl
  HANDLE CurrentThread; // rax
  int LastError; // eax
  void **v4; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+50h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+18h] BYREF

  TokenHandle = 0;
  v4 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v0 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    TokenInformation = 0;
    ReturnLength = 4;
    if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &ReturnLength) )
      v0 = TokenInformation == 2;
  }
  v4 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( TokenHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v4) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return v0;
}

```

## disassembly

```asm
0x18003afc4  mov     [rsp-8+arg_10], rbx
0x18003afc9  mov     [rsp-8+arg_18], rsi
0x18003afce  push    rbp
0x18003afcf  mov     rbp, rsp
0x18003afd2  sub     rsp, 40h
0x18003afd6  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18003afdd  mov     [rbp+TokenHandle], 0
0x18003afe5  mov     [rbp+var_10], rsi
0x18003afe9  xor     bl, bl
0x18003afeb  call    cs:__imp_GetCurrentThread
0x18003aff1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003aff5  mov     edx, 20008h; DesiredAccess
0x18003affa  mov     rcx, rax; ThreadHandle
0x18003affd  mov     r8d, 1; OpenAsSelf
0x18003b003  call    cs:__imp_OpenThreadToken
0x18003b009  test    eax, eax
0x18003b00b  jz      short loc_18003B044
0x18003b00d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003b011  lea     rax, [rbp+arg_8]
0x18003b015  mov     r9d, 4; TokenInformationLength
0x18003b01b  mov     [rbp+TokenInformation], 0
0x18003b022  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003b026  mov     [rbp+arg_8], r9d
0x18003b02a  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003b02f  lea     edx, [r9+4]; TokenInformationClass
0x18003b033  call    cs:__imp_GetTokenInformation
0x18003b039  test    eax, eax
0x18003b03b  jz      short loc_18003B044
0x18003b03d  cmp     [rbp+TokenInformation], 2
0x18003b041  setz    bl
0x18003b044  cmp     [rbp+TokenHandle], 0
0x18003b049  mov     [rbp+var_10], rsi
0x18003b04d  jz      short loc_18003B081
0x18003b04f  lea     rcx, [rbp+var_10]
0x18003b053  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18003b058  test    al, al
0x18003b05a  jnz     short loc_18003B081
0x18003b05c  call    cs:__imp_GetLastError
0x18003b062  test    eax, eax
0x18003b064  jle     short loc_18003B06E
0x18003b066  movzx   eax, ax
0x18003b069  or      eax, 80070000h
0x18003b06e  xor     r9d, r9d; lpArguments
0x18003b071  xor     r8d, r8d; nNumberOfArguments
0x18003b074  mov     ecx, eax; dwExceptionCode
0x18003b076  lea     edx, [r9+1]; dwExceptionFlags
0x18003b07a  call    cs:__imp_RaiseException
0x18003b080  int     3; Trap to Debugger
0x18003b081  mov     rsi, [rsp+40h+arg_18]
0x18003b086  mov     al, bl
0x18003b088  mov     rbx, [rsp+40h+arg_10]
0x18003b08d  add     rsp, 40h
0x18003b091  pop     rbp
0x18003b092  retn
```

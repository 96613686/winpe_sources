# ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating(void)

- ea: `0x180026970`
- end: `0x180026a41`
- name: `?AlreadyImpersonating@?$ImpersonationScope@ULicenseIdentityContextTraits@@@@CA_NXZ`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011aa0`
- `0x1800263e0`
- `0x180026914`

## callees

- `0x1800119e0`
- `0x180026970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800269ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800269ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026997`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800269af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800269af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026a1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026a1c`

## pseudocode

```c
bool ImpersonationScope<LicenseIdentityContextTraits>::AlreadyImpersonating()
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
0x180026970  mov     [rsp-8+arg_10], rbx
0x180026975  mov     [rsp-8+arg_18], rsi
0x18002697a  push    rbp
0x18002697b  mov     rbp, rsp
0x18002697e  sub     rsp, 40h
0x180026982  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180026989  mov     [rbp+TokenHandle], 0
0x180026991  mov     [rbp+var_10], rsi
0x180026995  xor     bl, bl
0x180026997  call    cs:__imp_GetCurrentThread
0x18002699d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800269a1  mov     edx, 20008h; DesiredAccess
0x1800269a6  mov     rcx, rax; ThreadHandle
0x1800269a9  mov     r8d, 1; OpenAsSelf
0x1800269af  call    cs:__imp_OpenThreadToken
0x1800269b5  test    eax, eax
0x1800269b7  jnz     short loc_1800269F6
0x1800269b9  cmp     [rbp+TokenHandle], 0
0x1800269be  mov     [rbp+var_10], rsi
0x1800269c2  jz      short loc_180026A2F
0x1800269c4  lea     rcx, [rbp+var_10]
0x1800269c8  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800269cd  test    al, al
0x1800269cf  jnz     short loc_180026A2F
0x1800269d1  call    cs:__imp_GetLastError
0x1800269d7  test    eax, eax
0x1800269d9  jle     short loc_1800269E3
0x1800269db  movzx   eax, ax
0x1800269de  or      eax, 80070000h
0x1800269e3  xor     r9d, r9d; lpArguments
0x1800269e6  xor     r8d, r8d; nNumberOfArguments
0x1800269e9  mov     ecx, eax; dwExceptionCode
0x1800269eb  lea     edx, [r9+1]; dwExceptionFlags
0x1800269ef  call    cs:__imp_RaiseException
0x1800269f5  int     3; Trap to Debugger
0x1800269f6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800269fa  lea     rax, [rbp+arg_8]
0x1800269fe  mov     r9d, 4; TokenInformationLength
0x180026a04  mov     [rbp+TokenInformation], 0
0x180026a0b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180026a0f  mov     [rbp+arg_8], r9d
0x180026a13  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180026a18  lea     edx, [r9+4]; TokenInformationClass
0x180026a1c  call    cs:__imp_GetTokenInformation
0x180026a22  test    eax, eax
0x180026a24  jz      short loc_1800269B9
0x180026a26  cmp     [rbp+TokenInformation], 2
0x180026a2a  setz    bl
0x180026a2d  jmp     short loc_1800269B9
0x180026a2f  mov     rsi, [rsp+40h+arg_18]
0x180026a34  mov     al, bl
0x180026a36  mov     rbx, [rsp+40h+arg_10]
0x180026a3b  add     rsp, 40h
0x180026a3f  pop     rbp
0x180026a40  retn
```

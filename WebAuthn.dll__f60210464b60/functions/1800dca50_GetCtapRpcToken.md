# _GetCtapRpcToken

- ea: `0x1800dca50`
- end: `0x1800dcb4a`
- name: `_GetCtapRpcToken`
- size: `250`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, _QWORD *)`
- caller_count: `17`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dfb8`
- `0x1800da7f4`
- `0x1800da85c`
- `0x1800dab70`
- `0x1800db080`
- `0x1800db110`
- `0x1800db20c`
- `0x1800db2b4`
- `0x1800db348`
- `0x1800db3b0`
- `0x1800db548`
- `0x1800db5ac`
- `0x1800db610`
- `0x1800db6b8`
- `0x1800db730`
- `0x1800db85c`
- `0x1800dd350`

## callees

- `0x18002bbf4`
- `0x180077f4c`
- `0x1800dca50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dcae6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dcae6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcac0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcacd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcac0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dcacd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dcb2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dcb2c`
- `RPCRT4!RpcImpersonateClient` at `0x1800dcaa2`
- `RPCRT4!RpcImpersonateClient` at `0x1800dcaa2`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dcb3c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dcb3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800dcb02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800dcb02`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800dca77`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800dca77`

## pseudocode

```c
__int64 __fastcall GetCtapRpcToken(RPC_BINDING_HANDLE BindingHandle, _QWORD *a2)
{
  unsigned int NonzeroLastError; // ebx
  void *v5; // rax
  HANDLE CurrentThread; // rax
  DWORD v8; // edx
  RPC_STATUS v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( BindingHandle == (RPC_BINDING_HANDLE)1 )
  {
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      NonzeroLastError = _GetNonzeroLastError();
LABEL_4:
      v5 = TokenHandle;
      goto LABEL_5;
    }
  }
  else
  {
    NonzeroLastError = RpcImpersonateClient(BindingHandle);
    if ( NonzeroLastError )
      goto LABEL_4;
  }
  NonzeroLastError = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v8 = 983551;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v8 = 12;
  }
  if ( !OpenThreadToken(CurrentThread, v8, 1, &TokenHandle) )
  {
    TokenHandle = 0;
    NonzeroLastError = _GetNonzeroLastError();
  }
  if ( BindingHandle == (RPC_BINDING_HANDLE)1 )
  {
    if ( !RevertToSelf() )
      NonzeroLastError = _GetNonzeroLastError();
  }
  else
  {
    v9 = RpcRevertToSelfEx(BindingHandle);
    if ( v9 )
    {
      NonzeroLastError = v9;
      goto LABEL_16;
    }
  }
  if ( !NonzeroLastError )
    goto LABEL_4;
LABEL_16:
  v5 = TokenHandle;
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v5 = 0;
  }
LABEL_5:
  *a2 = v5;
  return NonzeroLastError;
}

```

## disassembly

```asm
0x1800dca50  mov     [rsp+arg_8], rbx
0x1800dca55  mov     [rsp+arg_10], rsi
0x1800dca5a  push    rdi
0x1800dca5b  sub     rsp, 20h
0x1800dca5f  mov     [rsp+28h+TokenHandle], 0
0x1800dca68  mov     rsi, rdx
0x1800dca6b  mov     rdi, rcx
0x1800dca6e  cmp     rcx, 1
0x1800dca72  jnz     short loc_1800DCAA2
0x1800dca74  lea     ecx, [rdi+1]; ImpersonationLevel
0x1800dca77  call    cs:__imp_ImpersonateSelf
0x1800dca7d  test    eax, eax
0x1800dca7f  jnz     short loc_1800DCAAE
0x1800dca81  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dca86  mov     ebx, eax
0x1800dca88  mov     rax, [rsp+28h+TokenHandle]
0x1800dca8d  mov     [rsi], rax
0x1800dca90  mov     eax, ebx
0x1800dca92  mov     rbx, [rsp+28h+arg_8]
0x1800dca97  mov     rsi, [rsp+28h+arg_10]
0x1800dca9c  add     rsp, 20h
0x1800dcaa0  pop     rdi
0x1800dcaa1  retn
0x1800dcaa2  call    cs:__imp_RpcImpersonateClient
0x1800dcaa8  mov     ebx, eax
0x1800dcaaa  test    eax, eax
0x1800dcaac  jnz     short loc_1800DCA88
0x1800dcaae  xor     ebx, ebx
0x1800dcab0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x1800dcab7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x1800dcabc  test    al, al
0x1800dcabe  jz      short loc_1800DCACD
0x1800dcac0  call    cs:__imp_GetCurrentThread
0x1800dcac6  mov     edx, 0F01FFh
0x1800dcacb  jmp     short loc_1800DCAD8
0x1800dcacd  call    cs:__imp_GetCurrentThread
0x1800dcad3  mov     edx, 0Ch; DesiredAccess
0x1800dcad8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800dcadd  mov     r8d, 1; OpenAsSelf
0x1800dcae3  mov     rcx, rax; ThreadHandle
0x1800dcae6  call    cs:__imp_OpenThreadToken
0x1800dcaec  test    eax, eax
0x1800dcaee  jnz     short loc_1800DCAFC
0x1800dcaf0  mov     [rsp+28h+TokenHandle], rbx
0x1800dcaf5  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dcafa  mov     ebx, eax
0x1800dcafc  cmp     rdi, 1
0x1800dcb00  jnz     short loc_1800DCB39
0x1800dcb02  call    cs:__imp_RevertToSelf
0x1800dcb08  test    eax, eax
0x1800dcb0a  jnz     short loc_1800DCB13
0x1800dcb0c  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800dcb11  mov     ebx, eax
0x1800dcb13  test    ebx, ebx
0x1800dcb15  jz      loc_1800DCA88
0x1800dcb1b  mov     rax, [rsp+28h+TokenHandle]
0x1800dcb20  test    rax, rax
0x1800dcb23  jz      loc_1800DCA8D
0x1800dcb29  mov     rcx, rax; hObject
0x1800dcb2c  call    cs:__imp_CloseHandle
0x1800dcb32  xor     eax, eax
0x1800dcb34  jmp     loc_1800DCA8D
0x1800dcb39  mov     rcx, rdi; BindingHandle
0x1800dcb3c  call    cs:__imp_RpcRevertToSelfEx
0x1800dcb42  test    eax, eax
0x1800dcb44  jz      short loc_1800DCB13
0x1800dcb46  mov     ebx, eax
0x1800dcb48  jmp     short loc_1800DCB1B
```

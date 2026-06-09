# AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StartActivity(void)

- ea: `0x180018400`
- end: `0x1800184a5`
- name: `?StartActivity@PolicyDrivenProfileDelete@AccountManagerUserModelTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016460`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000ebf4`
- `0x18001790c`
- `0x180018400`
- `0x180019b6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018437`

## pseudocode

```c
void __fastcall AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete::StartActivity(
        AccountManagerUserModelTelemetry::PolicyDrivenProfileDelete *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = AccountManagerUserModelTelemetry::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)word_18002CC82,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180018400  mov     [rsp+arg_10], rbx
0x180018405  push    rdi
0x180018406  sub     rsp, 30h
0x18001840a  mov     rbx, rcx
0x18001840d  call    ?zInternalStart@?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018412  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x180018417  mov     rdi, rax
0x18001841a  mov     edx, [rax]
0x18001841c  cmp     edx, 5
0x18001841f  jbe     short loc_180018491
0x180018421  mov     rdx, 200000000000h
0x18001842b  mov     rcx, rax
0x18001842e  call    _tlgKeywordOn
0x180018433  test    al, al
0x180018435  jz      short loc_180018491
0x180018437  call    cs:__imp_GetCurrentThreadId
0x18001843d  mov     [rsp+38h+arg_0], eax
0x180018441  mov     [rsp+38h+arg_8], 0
0x18001844a  mov     r8, [rbx+110h]
0x180018451  cmp     byte ptr [r8+4], 0
0x180018456  jz      short loc_180018465
0x180018458  lea     rcx, [r8+18h]; struct _GUID *
0x18001845c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180018461  test    al, al
0x180018463  jz      short loc_180018467
0x180018465  xor     ecx, ecx
0x180018467  add     r8, 8
0x18001846b  lea     rax, [rsp+38h+arg_0]
0x180018470  mov     [rsp+38h+var_10], rax
0x180018475  lea     rax, [rsp+38h+arg_8]
0x18001847a  mov     [rsp+38h+var_18], rax
0x18001847f  mov     r9, rcx
0x180018482  lea     rdx, word_18002CC82
0x180018489  mov     rcx, rdi
0x18001848c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018491  mov     rcx, rbx
0x180018494  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180018499  nop
0x18001849a  mov     rbx, [rsp+38h+arg_10]
0x18001849f  add     rsp, 30h
0x1800184a3  pop     rdi
0x1800184a4  retn
```

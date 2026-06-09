# PolicyTelemetry::SinglePolicyEvaluation::StartActivity(uint)

- ea: `0x18001c554`
- end: `0x18001c604`
- name: `?StartActivity@SinglePolicyEvaluation@PolicyTelemetry@@QEAAXI@Z`
- size: `176`
- prototype: `void __fastcall(PolicyTelemetry::SinglePolicyEvaluation *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001c238`

## callees

- `0x180001384`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x18001c554`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c591`

## pseudocode

```c
void __fastcall PolicyTelemetry::SinglePolicyEvaluation::StartActivity(
        PolicyTelemetry::SinglePolicyEvaluation *this,
        int a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // [rsp+60h] [rbp+8h] BYREF
  DWORD v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = SharedPCAccountManagerLogging::Provider();
  v6 = (__int64)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v7, v5) )
  {
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v13 = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_18002DE51,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001c554  push    rbx
0x18001c556  push    rsi
0x18001c557  push    rdi
0x18001c558  sub     rsp, 40h
0x18001c55c  mov     esi, edx
0x18001c55e  mov     rbx, rcx
0x18001c561  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c566  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001c56b  mov     rdi, rax
0x18001c56e  mov     r8d, [rax]
0x18001c571  cmp     r8d, 5
0x18001c575  jbe     short loc_18001C5F5
0x18001c577  mov     rdx, 400000000000h
0x18001c581  mov     rcx, rax
0x18001c584  call    _tlgKeywordOn
0x18001c589  test    al, al
0x18001c58b  jz      short loc_18001C5F5
0x18001c58d  mov     [rsp+58h+arg_0], esi
0x18001c591  call    cs:__imp_GetCurrentThreadId
0x18001c597  mov     r8, [rbx+110h]
0x18001c59e  mov     [rsp+58h+arg_10], eax
0x18001c5a2  mov     [rsp+58h+arg_18], 1000000h
0x18001c5ab  cmp     byte ptr [r8+4], 0
0x18001c5b0  jz      short loc_18001C5BF
0x18001c5b2  lea     rcx, [r8+18h]; struct _GUID *
0x18001c5b6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18001c5bb  test    al, al
0x18001c5bd  jz      short loc_18001C5C1
0x18001c5bf  xor     ecx, ecx
0x18001c5c1  lea     rax, [rsp+58h+arg_0]
0x18001c5c6  mov     r9, rcx
0x18001c5c9  mov     [rsp+58h+var_28], rax
0x18001c5ce  lea     rdx, byte_18002DE51
0x18001c5d5  lea     rax, [rsp+58h+arg_10]
0x18001c5da  add     r8, 8
0x18001c5de  mov     [rsp+58h+var_30], rax
0x18001c5e3  mov     rcx, rdi
0x18001c5e6  lea     rax, [rsp+58h+arg_18]
0x18001c5eb  mov     [rsp+58h+var_38], rax
0x18001c5f0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c5f5  mov     rcx, rbx
0x18001c5f8  add     rsp, 40h
0x18001c5fc  pop     rdi
0x18001c5fd  pop     rsi
0x18001c5fe  pop     rbx
0x18001c5ff  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

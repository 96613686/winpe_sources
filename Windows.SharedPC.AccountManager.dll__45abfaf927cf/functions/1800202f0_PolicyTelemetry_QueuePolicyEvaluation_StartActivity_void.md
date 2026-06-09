# PolicyTelemetry::QueuePolicyEvaluation::StartActivity(void)

- ea: `0x1800202f0`
- end: `0x180020395`
- name: `?StartActivity@QueuePolicyEvaluation@PolicyTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(PolicyTelemetry::QueuePolicyEvaluation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020070`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x1800202f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020327`

## pseudocode

```c
void __fastcall PolicyTelemetry::QueuePolicyEvaluation::StartActivity(PolicyTelemetry::QueuePolicyEvaluation *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = SharedPCAccountManagerLogging::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_18002EFE1,
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
0x1800202f0  mov     [rsp+arg_10], rbx
0x1800202f5  push    rdi
0x1800202f6  sub     rsp, 30h
0x1800202fa  mov     rbx, rcx
0x1800202fd  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020302  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180020307  mov     rdi, rax
0x18002030a  mov     edx, [rax]
0x18002030c  cmp     edx, 5
0x18002030f  jbe     short loc_180020381
0x180020311  mov     rdx, 400000000000h
0x18002031b  mov     rcx, rax
0x18002031e  call    _tlgKeywordOn
0x180020323  test    al, al
0x180020325  jz      short loc_180020381
0x180020327  call    cs:__imp_GetCurrentThreadId
0x18002032d  mov     [rsp+38h+arg_0], eax
0x180020331  mov     [rsp+38h+arg_8], 1000000h
0x18002033a  mov     r8, [rbx+110h]
0x180020341  cmp     byte ptr [r8+4], 0
0x180020346  jz      short loc_180020355
0x180020348  lea     rcx, [r8+18h]; struct _GUID *
0x18002034c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180020351  test    al, al
0x180020353  jz      short loc_180020357
0x180020355  xor     ecx, ecx
0x180020357  add     r8, 8
0x18002035b  lea     rax, [rsp+38h+arg_0]
0x180020360  mov     [rsp+38h+var_10], rax
0x180020365  lea     rax, [rsp+38h+arg_8]
0x18002036a  mov     [rsp+38h+var_18], rax
0x18002036f  mov     r9, rcx
0x180020372  lea     rdx, byte_18002EFE1
0x180020379  mov     rcx, rdi
0x18002037c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180020381  mov     rcx, rbx
0x180020384  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180020389  nop
0x18002038a  mov     rbx, [rsp+38h+arg_10]
0x18002038f  add     rsp, 30h
0x180020393  pop     rdi
0x180020394  retn
```

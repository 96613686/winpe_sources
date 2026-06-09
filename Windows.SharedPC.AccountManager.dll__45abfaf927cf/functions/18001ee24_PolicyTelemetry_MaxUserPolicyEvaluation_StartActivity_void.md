# PolicyTelemetry::MaxUserPolicyEvaluation::StartActivity(void)

- ea: `0x18001ee24`
- end: `0x18001eec9`
- name: `?StartActivity@MaxUserPolicyEvaluation@PolicyTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(PolicyTelemetry::MaxUserPolicyEvaluation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001eca0`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x18001ee24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee5b`

## pseudocode

```c
void __fastcall PolicyTelemetry::MaxUserPolicyEvaluation::StartActivity(PolicyTelemetry::MaxUserPolicyEvaluation *this)
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
      (__int64)word_18002E3C2,
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
0x18001ee24  mov     [rsp+arg_10], rbx
0x18001ee29  push    rdi
0x18001ee2a  sub     rsp, 30h
0x18001ee2e  mov     rbx, rcx
0x18001ee31  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001ee36  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001ee3b  mov     rdi, rax
0x18001ee3e  mov     edx, [rax]
0x18001ee40  cmp     edx, 5
0x18001ee43  jbe     short loc_18001EEB5
0x18001ee45  mov     rdx, 400000000000h
0x18001ee4f  mov     rcx, rax
0x18001ee52  call    _tlgKeywordOn
0x18001ee57  test    al, al
0x18001ee59  jz      short loc_18001EEB5
0x18001ee5b  call    cs:__imp_GetCurrentThreadId
0x18001ee61  mov     [rsp+38h+arg_0], eax
0x18001ee65  mov     [rsp+38h+arg_8], 1000000h
0x18001ee6e  mov     r8, [rbx+110h]
0x18001ee75  cmp     byte ptr [r8+4], 0
0x18001ee7a  jz      short loc_18001EE89
0x18001ee7c  lea     rcx, [r8+18h]; struct _GUID *
0x18001ee80  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18001ee85  test    al, al
0x18001ee87  jz      short loc_18001EE8B
0x18001ee89  xor     ecx, ecx
0x18001ee8b  add     r8, 8
0x18001ee8f  lea     rax, [rsp+38h+arg_0]
0x18001ee94  mov     [rsp+38h+var_10], rax
0x18001ee99  lea     rax, [rsp+38h+arg_8]
0x18001ee9e  mov     [rsp+38h+var_18], rax
0x18001eea3  mov     r9, rcx
0x18001eea6  lea     rdx, word_18002E3C2
0x18001eead  mov     rcx, rdi
0x18001eeb0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001eeb5  mov     rcx, rbx
0x18001eeb8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001eebd  nop
0x18001eebe  mov     rbx, [rsp+38h+arg_10]
0x18001eec3  add     rsp, 30h
0x18001eec7  pop     rdi
0x18001eec8  retn
```

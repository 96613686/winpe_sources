# PolicyTelemetry::LocalPolicyEvaluation::StartActivity(void)

- ea: `0x180020244`
- end: `0x1800202e9`
- name: `?StartActivity@LocalPolicyEvaluation@PolicyTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(PolicyTelemetry::LocalPolicyEvaluation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001fcf4`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x180020244`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002027b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002027b`

## pseudocode

```c
void __fastcall PolicyTelemetry::LocalPolicyEvaluation::StartActivity(PolicyTelemetry::LocalPolicyEvaluation *this)
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
      (__int64)byte_18002F17B,
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
0x180020244  mov     [rsp+arg_10], rbx
0x180020249  push    rdi
0x18002024a  sub     rsp, 30h
0x18002024e  mov     rbx, rcx
0x180020251  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020256  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18002025b  mov     rdi, rax
0x18002025e  mov     edx, [rax]
0x180020260  cmp     edx, 5
0x180020263  jbe     short loc_1800202D5
0x180020265  mov     rdx, 400000000000h
0x18002026f  mov     rcx, rax
0x180020272  call    _tlgKeywordOn
0x180020277  test    al, al
0x180020279  jz      short loc_1800202D5
0x18002027b  call    cs:__imp_GetCurrentThreadId
0x180020281  mov     [rsp+38h+arg_0], eax
0x180020285  mov     [rsp+38h+arg_8], 1000000h
0x18002028e  mov     r8, [rbx+110h]
0x180020295  cmp     byte ptr [r8+4], 0
0x18002029a  jz      short loc_1800202A9
0x18002029c  lea     rcx, [r8+18h]; struct _GUID *
0x1800202a0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800202a5  test    al, al
0x1800202a7  jz      short loc_1800202AB
0x1800202a9  xor     ecx, ecx
0x1800202ab  add     r8, 8
0x1800202af  lea     rax, [rsp+38h+arg_0]
0x1800202b4  mov     [rsp+38h+var_10], rax
0x1800202b9  lea     rax, [rsp+38h+arg_8]
0x1800202be  mov     [rsp+38h+var_18], rax
0x1800202c3  mov     r9, rcx
0x1800202c6  lea     rdx, byte_18002F17B
0x1800202cd  mov     rcx, rdi
0x1800202d0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800202d5  mov     rcx, rbx
0x1800202d8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800202dd  nop
0x1800202de  mov     rbx, [rsp+38h+arg_10]
0x1800202e3  add     rsp, 30h
0x1800202e7  pop     rdi
0x1800202e8  retn
```

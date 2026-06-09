# CredUIBrokerTelemetry::BrokerForAppContainersActivity::StartActivity(void)

- ea: `0x140014684`
- end: `0x140014727`
- name: `?StartActivity@BrokerForAppContainersActivity@CredUIBrokerTelemetry@@QEAAXXZ`
- size: `163`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForAppContainersActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010da0`

## callees

- `0x140002370`
- `0x140002f8c`
- `0x14000bb3c`
- `0x140011a40`
- `0x140014684`
- `0x140018fc0`
- `0x14001c0fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400146bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400146bb`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForAppContainersActivity::StartActivity(
        CredUIBrokerTelemetry::BrokerForAppContainersActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // rcx
  DWORD v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = CredUIBrokerLogging::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = *((_QWORD *)this + 34);
    v9 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v7 + 4) || _tlgGuidIsZero((const struct _GUID *)(v7 + 24)) )
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)&byte_1400251AF,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&v9);
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140014684  mov     [rsp+arg_10], rbx
0x140014689  push    rdi
0x14001468a  sub     rsp, 30h
0x14001468e  mov     rbx, rcx
0x140014691  call    ?zInternalStart@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140014696  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x14001469b  mov     rdi, rax
0x14001469e  mov     edx, [rax]
0x1400146a0  cmp     edx, 5
0x1400146a3  jbe     short loc_140014715
0x1400146a5  mov     rdx, 200000000000h
0x1400146af  mov     rcx, rax
0x1400146b2  call    _tlgKeywordOn
0x1400146b7  test    al, al
0x1400146b9  jz      short loc_140014715
0x1400146bb  call    cs:__imp_GetCurrentThreadId
0x1400146c1  mov     r8, [rbx+110h]
0x1400146c8  mov     [rsp+38h+arg_0], eax
0x1400146cc  mov     [rsp+38h+arg_8], 0
0x1400146d5  cmp     byte ptr [r8+4], 0
0x1400146da  jz      short loc_1400146E9
0x1400146dc  lea     rcx, [r8+18h]; struct _GUID *
0x1400146e0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400146e5  test    al, al
0x1400146e7  jz      short loc_1400146EB
0x1400146e9  xor     ecx, ecx
0x1400146eb  lea     rax, [rsp+38h+arg_0]
0x1400146f0  mov     r9, rcx
0x1400146f3  mov     [rsp+38h+var_10], rax
0x1400146f8  lea     rdx, byte_1400251AF
0x1400146ff  lea     rax, [rsp+38h+arg_8]
0x140014704  add     r8, 8
0x140014708  mov     rcx, rdi
0x14001470b  mov     [rsp+38h+var_18], rax
0x140014710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140014715  mov     rcx, rbx
0x140014718  mov     rbx, [rsp+38h+arg_10]
0x14001471d  add     rsp, 30h
0x140014721  pop     rdi
0x140014722  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

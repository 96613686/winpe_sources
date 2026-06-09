# CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StartActivity(void)

- ea: `0x140014730`
- end: `0x1400147d3`
- name: `?StartActivity@BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@QEAAXXZ`
- size: `163`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010f10`

## callees

- `0x140002370`
- `0x140002f8c`
- `0x14000bb3c`
- `0x140011a40`
- `0x140014730`
- `0x140018fc0`
- `0x14001c0fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014767`
- `KERNEL32!GetCurrentThreadId` at `0x140014767`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StartActivity(
        CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *this)
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
      (__int64)&dword_1400249B4,
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
0x140014730  mov     [rsp+arg_10], rbx
0x140014735  push    rdi
0x140014736  sub     rsp, 30h
0x14001473a  mov     rbx, rcx
0x14001473d  call    ?zInternalStart@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140014742  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140014747  mov     rdi, rax
0x14001474a  mov     edx, [rax]
0x14001474c  cmp     edx, 5
0x14001474f  jbe     short loc_1400147C1
0x140014751  mov     rdx, 200000000000h
0x14001475b  mov     rcx, rax
0x14001475e  call    _tlgKeywordOn
0x140014763  test    al, al
0x140014765  jz      short loc_1400147C1
0x140014767  call    cs:__imp_GetCurrentThreadId
0x14001476d  mov     r8, [rbx+110h]
0x140014774  mov     [rsp+38h+arg_0], eax
0x140014778  mov     [rsp+38h+arg_8], 0
0x140014781  cmp     byte ptr [r8+4], 0
0x140014786  jz      short loc_140014795
0x140014788  lea     rcx, [r8+18h]; struct _GUID *
0x14001478c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140014791  test    al, al
0x140014793  jz      short loc_140014797
0x140014795  xor     ecx, ecx
0x140014797  lea     rax, [rsp+38h+arg_0]
0x14001479c  mov     r9, rcx
0x14001479f  mov     [rsp+38h+var_10], rax
0x1400147a4  lea     rdx, dword_1400249B4
0x1400147ab  lea     rax, [rsp+38h+arg_8]
0x1400147b0  add     r8, 8
0x1400147b4  mov     rcx, rdi
0x1400147b7  mov     [rsp+38h+var_18], rax
0x1400147bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400147c1  mov     rcx, rbx
0x1400147c4  mov     rbx, [rsp+38h+arg_10]
0x1400147c9  add     rsp, 30h
0x1400147cd  pop     rdi
0x1400147ce  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

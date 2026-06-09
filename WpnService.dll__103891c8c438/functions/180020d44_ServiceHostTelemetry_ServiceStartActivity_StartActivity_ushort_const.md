# ServiceHostTelemetry::ServiceStartActivity::StartActivity(ushort const *)

- ea: `0x180020d44`
- end: `0x180020e1c`
- name: `?StartActivity@ServiceStartActivity@ServiceHostTelemetry@@QEAAXPEBG@Z`
- size: `216`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180020cfc`

## callees

- `0x1800027a4`
- `0x1800172bc`
- `0x180018430`
- `0x180020d44`
- `0x180022838`
- `0x1800238ac`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020d96`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::StartActivity(
        ServiceHostTelemetry::ServiceStartActivity *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD v12; // [rsp+80h] [rbp+18h] BYREF
  const unsigned __int16 *v13; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = ServiceHostLogging::Provider();
  v6 = (__int64)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v7, v5) )
  {
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v11[0] = 0x1000000;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_18003D5DD,
      v9 + 8,
      v10,
      (__int64)v11,
      (__int64)&v12,
      &v13);
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180020d44  push    rbx
0x180020d46  push    rsi
0x180020d47  push    rdi
0x180020d48  sub     rsp, 50h
0x180020d4c  mov     rsi, rdx
0x180020d4f  mov     rbx, rcx
0x180020d52  call    ?zInternalStart@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020d57  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180020d5c  mov     rdi, rax
0x180020d5f  mov     r8d, [rax]
0x180020d62  cmp     r8d, 5
0x180020d66  jbe     loc_180020E0D
0x180020d6c  mov     rdx, 400000000000h
0x180020d76  mov     rcx, rax
0x180020d79  call    _tlgKeywordOn
0x180020d7e  test    al, al
0x180020d80  jz      loc_180020E0D
0x180020d86  mov     [rsp+68h+arg_0], 1
0x180020d8e  mov     [rsp+68h+arg_18], rsi
0x180020d96  call    cs:__imp_GetCurrentThreadId
0x180020d9c  mov     r8, [rbx+110h]
0x180020da3  mov     [rsp+68h+arg_10], eax
0x180020daa  mov     [rsp+68h+var_28], 1000000h
0x180020db3  cmp     byte ptr [r8+4], 0
0x180020db8  jz      short loc_180020DC7
0x180020dba  lea     rcx, [r8+18h]; struct _GUID *
0x180020dbe  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180020dc3  test    al, al
0x180020dc5  jz      short loc_180020DC9
0x180020dc7  xor     ecx, ecx
0x180020dc9  lea     rax, [rsp+68h+arg_0]
0x180020dce  mov     r9, rcx
0x180020dd1  mov     [rsp+68h+var_30], rax
0x180020dd6  lea     rdx, byte_18003D5DD
0x180020ddd  lea     rax, [rsp+68h+arg_18]
0x180020de5  add     r8, 8
0x180020de9  mov     [rsp+68h+var_38], rax
0x180020dee  mov     rcx, rdi
0x180020df1  lea     rax, [rsp+68h+arg_10]
0x180020df9  mov     [rsp+68h+var_40], rax
0x180020dfe  lea     rax, [rsp+68h+var_28]
0x180020e03  mov     [rsp+68h+var_48], rax
0x180020e08  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180020e0d  mov     rcx, rbx
0x180020e10  add     rsp, 50h
0x180020e14  pop     rdi
0x180020e15  pop     rsi
0x180020e16  pop     rbx
0x180020e17  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

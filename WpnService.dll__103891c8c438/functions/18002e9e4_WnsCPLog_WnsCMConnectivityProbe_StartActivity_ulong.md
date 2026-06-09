# WnsCPLog::WnsCMConnectivityProbe::StartActivity(ulong)

- ea: `0x18002e9e4`
- end: `0x18002ea7e`
- name: `?StartActivity@WnsCMConnectivityProbe@WnsCPLog@@QEAAXK@Z`
- size: `154`
- prototype: `void __fastcall(WnsCPLog::WnsCMConnectivityProbe *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002e4b0`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x18000f2f0`
- `0x180023dc4`
- `0x18002e9e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ea0b`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConnectivityProbe::StartActivity(WnsCPLog::WnsCMConnectivityProbe *this, int a2)
{
  const struct _tlgProvider_t *v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  const GUID *v7; // rcx
  int v8; // [rsp+60h] [rbp+8h] BYREF
  DWORD v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v8 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v9 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v4,
      (unsigned __int8 *)byte_18003EE3B,
      (const GUID *)(v6 + 8),
      v7,
      (__int64)&v10,
      (__int64)&v9,
      (__int64)&v8);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002e9e4  push    rbx
0x18002e9e6  push    rsi
0x18002e9e7  push    rdi
0x18002e9e8  sub     rsp, 40h
0x18002e9ec  mov     edi, edx
0x18002e9ee  mov     rbx, rcx
0x18002e9f1  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002e9f6  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002e9fb  mov     rsi, rax
0x18002e9fe  mov     r8d, [rax]
0x18002ea01  cmp     r8d, 5
0x18002ea05  jbe     short loc_18002EA6F
0x18002ea07  mov     [rsp+58h+arg_0], edi
0x18002ea0b  call    cs:__imp_GetCurrentThreadId
0x18002ea11  mov     r8, [rbx+110h]
0x18002ea18  mov     [rsp+58h+arg_10], eax
0x18002ea1c  mov     [rsp+58h+arg_18], 0
0x18002ea25  cmp     byte ptr [r8+4], 0
0x18002ea2a  jz      short loc_18002EA39
0x18002ea2c  lea     rcx, [r8+18h]; struct _GUID *
0x18002ea30  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002ea35  test    al, al
0x18002ea37  jz      short loc_18002EA3B
0x18002ea39  xor     ecx, ecx
0x18002ea3b  lea     rax, [rsp+58h+arg_0]
0x18002ea40  mov     r9, rcx
0x18002ea43  mov     [rsp+58h+var_28], rax
0x18002ea48  lea     rdx, byte_18003EE3B
0x18002ea4f  lea     rax, [rsp+58h+arg_10]
0x18002ea54  add     r8, 8
0x18002ea58  mov     [rsp+58h+var_30], rax
0x18002ea5d  mov     rcx, rsi
0x18002ea60  lea     rax, [rsp+58h+arg_18]
0x18002ea65  mov     [rsp+58h+var_38], rax
0x18002ea6a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002ea6f  mov     rcx, rbx
0x18002ea72  add     rsp, 40h
0x18002ea76  pop     rdi
0x18002ea77  pop     rsi
0x18002ea78  pop     rbx
0x18002ea79  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

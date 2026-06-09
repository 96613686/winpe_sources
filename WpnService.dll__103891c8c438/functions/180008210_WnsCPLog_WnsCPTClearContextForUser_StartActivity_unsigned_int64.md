# WnsCPLog::WnsCPTClearContextForUser::StartActivity(unsigned __int64)

- ea: `0x180008210`
- end: `0x1800082ac`
- name: `?StartActivity@WnsCPTClearContextForUser@WnsCPLog@@QEAAX_K@Z`
- size: `156`
- prototype: `void __fastcall(WnsCPLog::WnsCPTClearContextForUser *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008cc0`

## callees

- `0x180008210`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x18000f4a0`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008239`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008239`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTClearContextForUser::StartActivity(
        WnsCPLog::WnsCPTClearContextForUser *this,
        __int64 a2)
{
  const struct _tlgProvider_t *v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  const GUID *v7; // rcx
  DWORD v8; // [rsp+60h] [rbp+8h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v9 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v8 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)v4,
      (unsigned __int8 *)&word_18004082E,
      (const GUID *)(v6 + 8),
      v7,
      (__int64)&v10,
      (__int64)&v8,
      (__int64)&v9);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180008210  push    rbx
0x180008212  push    rsi
0x180008213  push    rdi
0x180008214  sub     rsp, 40h
0x180008218  mov     rdi, rdx
0x18000821b  mov     rbx, rcx
0x18000821e  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180008223  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180008228  mov     rsi, rax
0x18000822b  mov     r8d, [rax]
0x18000822e  cmp     r8d, 5
0x180008232  jbe     short loc_18000829D
0x180008234  mov     [rsp+58h+arg_10], rdi
0x180008239  call    cs:__imp_GetCurrentThreadId
0x18000823f  mov     r8, [rbx+110h]
0x180008246  mov     [rsp+58h+arg_0], eax
0x18000824a  mov     [rsp+58h+arg_18], 0
0x180008253  cmp     byte ptr [r8+4], 0
0x180008258  jz      short loc_180008267
0x18000825a  lea     rcx, [r8+18h]; struct _GUID *
0x18000825e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180008263  test    al, al
0x180008265  jz      short loc_180008269
0x180008267  xor     ecx, ecx
0x180008269  lea     rax, [rsp+58h+arg_10]
0x18000826e  mov     r9, rcx
0x180008271  mov     [rsp+58h+var_28], rax
0x180008276  lea     rdx, word_18004082E
0x18000827d  lea     rax, [rsp+58h+arg_0]
0x180008282  add     r8, 8
0x180008286  mov     [rsp+58h+var_30], rax
0x18000828b  mov     rcx, rsi
0x18000828e  lea     rax, [rsp+58h+arg_18]
0x180008293  mov     [rsp+58h+var_38], rax
0x180008298  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000829d  mov     rcx, rbx
0x1800082a0  add     rsp, 40h
0x1800082a4  pop     rdi
0x1800082a5  pop     rsi
0x1800082a6  pop     rbx
0x1800082a7  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

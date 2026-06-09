# WnsCPLog::WnsSinkNotificationDeliveryChanged::StartActivity(long,unsigned __int64,long)

- ea: `0x180033618`
- end: `0x1800336f6`
- name: `?StartActivity@WnsSinkNotificationDeliveryChanged@WnsCPLog@@QEAAXJ_KJ@Z`
- size: `222`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationDeliveryChanged *__hidden this, int, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800333e0`

## callees

- `0x180002d34`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180023dc4`
- `0x180033618`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003365f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003365f`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationDeliveryChanged::StartActivity(
        WnsCPLog::WnsSinkNotificationDeliveryChanged *this)
{
  const struct _tlgProvider_t *v2; // r14
  __int64 v3; // r8

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    GetCurrentThreadId();
    v3 = *((_QWORD *)this + 34);
    if ( *(_BYTE *)(v3 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v3 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)&word_18004224E,
      v3 + 8);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180033618  mov     [rsp+arg_8], rbx
0x18003361d  mov     [rsp+arg_10], rbp
0x180033622  push    rsi
0x180033623  push    rdi
0x180033624  push    r14
0x180033626  sub     rsp, 70h
0x18003362a  mov     edi, r9d
0x18003362d  mov     rsi, r8
0x180033630  mov     ebp, edx
0x180033632  mov     rbx, rcx
0x180033635  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003363a  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18003363f  mov     r14, rax
0x180033642  mov     r10d, [rax]
0x180033645  cmp     r10d, 5
0x180033649  jbe     loc_1800336DA
0x18003364f  mov     [rsp+88h+arg_0], edi
0x180033656  mov     [rsp+88h+var_30], rsi
0x18003365b  mov     [rsp+88h+var_38], ebp
0x18003365f  call    cs:__imp_GetCurrentThreadId
0x180033665  mov     r8, [rbx+110h]
0x18003366c  mov     [rsp+88h+var_34], eax
0x180033670  mov     [rsp+88h+var_28], 0
0x180033679  cmp     byte ptr [r8+4], 0
0x18003367e  jz      short loc_18003368D
0x180033680  lea     rcx, [r8+18h]; struct _GUID *
0x180033684  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180033689  test    al, al
0x18003368b  jz      short loc_18003368F
0x18003368d  xor     ecx, ecx
0x18003368f  lea     rax, [rsp+88h+arg_0]
0x180033697  mov     r9, rcx
0x18003369a  mov     [rsp+88h+var_48], rax
0x18003369f  lea     rdx, word_18004224E
0x1800336a6  lea     rax, [rsp+88h+var_30]
0x1800336ab  add     r8, 8
0x1800336af  mov     [rsp+88h+var_50], rax
0x1800336b4  mov     rcx, r14
0x1800336b7  lea     rax, [rsp+88h+var_38]
0x1800336bc  mov     [rsp+88h+var_58], rax
0x1800336c1  lea     rax, [rsp+88h+var_34]
0x1800336c6  mov     [rsp+88h+var_60], rax
0x1800336cb  lea     rax, [rsp+88h+var_28]
0x1800336d0  mov     [rsp+88h+var_68], rax
0x1800336d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800336da  mov     rcx, rbx
0x1800336dd  lea     r11, [rsp+88h+var_18]
0x1800336e2  mov     rbx, [r11+28h]
0x1800336e6  mov     rbp, [r11+30h]
0x1800336ea  mov     rsp, r11
0x1800336ed  pop     r14
0x1800336ef  pop     rdi
0x1800336f0  pop     rsi
0x1800336f1  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

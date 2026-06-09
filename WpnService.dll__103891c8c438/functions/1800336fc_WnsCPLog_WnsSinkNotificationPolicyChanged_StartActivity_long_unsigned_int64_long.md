# WnsCPLog::WnsSinkNotificationPolicyChanged::StartActivity(long,unsigned __int64,long)

- ea: `0x1800336fc`
- end: `0x1800337da`
- name: `?StartActivity@WnsSinkNotificationPolicyChanged@WnsCPLog@@QEAAXJ_KJ@Z`
- size: `222`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationPolicyChanged *__hidden this, int, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180033470`

## callees

- `0x180002d34`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180023dc4`
- `0x1800336fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033743`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033743`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationPolicyChanged::StartActivity(
        WnsCPLog::WnsSinkNotificationPolicyChanged *this)
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
      (__int64)byte_180042483,
      v3 + 8);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800336fc  mov     [rsp+arg_8], rbx
0x180033701  mov     [rsp+arg_10], rbp
0x180033706  push    rsi
0x180033707  push    rdi
0x180033708  push    r14
0x18003370a  sub     rsp, 70h
0x18003370e  mov     edi, r9d
0x180033711  mov     rsi, r8
0x180033714  mov     ebp, edx
0x180033716  mov     rbx, rcx
0x180033719  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003371e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033723  mov     r14, rax
0x180033726  mov     r10d, [rax]
0x180033729  cmp     r10d, 5
0x18003372d  jbe     loc_1800337BE
0x180033733  mov     [rsp+88h+arg_0], edi
0x18003373a  mov     [rsp+88h+var_30], rsi
0x18003373f  mov     [rsp+88h+var_38], ebp
0x180033743  call    cs:__imp_GetCurrentThreadId
0x180033749  mov     r8, [rbx+110h]
0x180033750  mov     [rsp+88h+var_34], eax
0x180033754  mov     [rsp+88h+var_28], 0
0x18003375d  cmp     byte ptr [r8+4], 0
0x180033762  jz      short loc_180033771
0x180033764  lea     rcx, [r8+18h]; struct _GUID *
0x180033768  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003376d  test    al, al
0x18003376f  jz      short loc_180033773
0x180033771  xor     ecx, ecx
0x180033773  lea     rax, [rsp+88h+arg_0]
0x18003377b  mov     r9, rcx
0x18003377e  mov     [rsp+88h+var_48], rax
0x180033783  lea     rdx, byte_180042483
0x18003378a  lea     rax, [rsp+88h+var_30]
0x18003378f  add     r8, 8
0x180033793  mov     [rsp+88h+var_50], rax
0x180033798  mov     rcx, r14
0x18003379b  lea     rax, [rsp+88h+var_38]
0x1800337a0  mov     [rsp+88h+var_58], rax
0x1800337a5  lea     rax, [rsp+88h+var_34]
0x1800337aa  mov     [rsp+88h+var_60], rax
0x1800337af  lea     rax, [rsp+88h+var_28]
0x1800337b4  mov     [rsp+88h+var_68], rax
0x1800337b9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800337be  mov     rcx, rbx
0x1800337c1  lea     r11, [rsp+88h+var_18]
0x1800337c6  mov     rbx, [r11+28h]
0x1800337ca  mov     rbp, [r11+30h]
0x1800337ce  mov     rsp, r11
0x1800337d1  pop     r14
0x1800337d3  pop     rdi
0x1800337d4  pop     rsi
0x1800337d5  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

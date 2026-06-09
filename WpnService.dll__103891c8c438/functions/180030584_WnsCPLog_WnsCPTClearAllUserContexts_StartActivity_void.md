# WnsCPLog::WnsCPTClearAllUserContexts::StartActivity(void)

- ea: `0x180030584`
- end: `0x180030613`
- name: `?StartActivity@WnsCPTClearAllUserContexts@WnsCPLog@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(WnsCPLog::WnsCPTClearAllUserContexts *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800300a8`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180014d80`
- `0x180023dc4`
- `0x180030584`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800305a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800305a5`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTClearAllUserContexts::StartActivity(WnsCPLog::WnsCPTClearAllUserContexts *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  const GUID *v4; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4) || _tlgGuidIsZero((const struct _GUID *)(v3 + 24)) )
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (unsigned __int8 *)byte_180040C31,
      (const GUID *)(v3 + 8),
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180030584  mov     [rsp+arg_10], rbx
0x180030589  push    rdi
0x18003058a  sub     rsp, 30h
0x18003058e  mov     rbx, rcx
0x180030591  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180030596  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18003059b  mov     rdi, rax
0x18003059e  mov     edx, [rax]
0x1800305a0  cmp     edx, 5
0x1800305a3  jbe     short loc_1800305FF
0x1800305a5  call    cs:__imp_GetCurrentThreadId
0x1800305ab  mov     [rsp+38h+arg_0], eax
0x1800305af  mov     [rsp+38h+arg_8], 0
0x1800305b8  mov     r8, [rbx+110h]
0x1800305bf  cmp     byte ptr [r8+4], 0
0x1800305c4  jz      short loc_1800305D3
0x1800305c6  lea     rcx, [r8+18h]; struct _GUID *
0x1800305ca  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800305cf  test    al, al
0x1800305d1  jz      short loc_1800305D5
0x1800305d3  xor     ecx, ecx
0x1800305d5  add     r8, 8
0x1800305d9  lea     rax, [rsp+38h+arg_0]
0x1800305de  mov     [rsp+38h+var_10], rax
0x1800305e3  lea     rax, [rsp+38h+arg_8]
0x1800305e8  mov     [rsp+38h+var_18], rax
0x1800305ed  mov     r9, rcx
0x1800305f0  lea     rdx, byte_180040C31
0x1800305f7  mov     rcx, rdi
0x1800305fa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800305ff  mov     rcx, rbx
0x180030602  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180030607  nop
0x180030608  mov     rbx, [rsp+38h+arg_10]
0x18003060d  add     rsp, 30h
0x180030611  pop     rdi
0x180030612  retn
```

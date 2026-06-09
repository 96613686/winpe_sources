# WnsCPLog::WnsCMRegisterCallback::StartActivity(void)

- ea: `0x180022380`
- end: `0x18002240f`
- name: `?StartActivity@WnsCMRegisterCallback@WnsCPLog@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(WnsCPLog::WnsCMRegisterCallback *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004d50`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180014d80`
- `0x180022380`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800223a1`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRegisterCallback::StartActivity(WnsCPLog::WnsCMRegisterCallback *this)
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
      (unsigned __int8 *)byte_18003FC2F,
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
0x180022380  mov     [rsp+arg_10], rbx
0x180022385  push    rdi
0x180022386  sub     rsp, 30h
0x18002238a  mov     rbx, rcx
0x18002238d  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180022392  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180022397  mov     rdi, rax
0x18002239a  mov     edx, [rax]
0x18002239c  cmp     edx, 5
0x18002239f  jbe     short loc_1800223FB
0x1800223a1  call    cs:__imp_GetCurrentThreadId
0x1800223a7  mov     [rsp+38h+arg_0], eax
0x1800223ab  mov     [rsp+38h+arg_8], 0
0x1800223b4  mov     r8, [rbx+110h]
0x1800223bb  cmp     byte ptr [r8+4], 0
0x1800223c0  jz      short loc_1800223CF
0x1800223c2  lea     rcx, [r8+18h]; struct _GUID *
0x1800223c6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800223cb  test    al, al
0x1800223cd  jz      short loc_1800223D1
0x1800223cf  xor     ecx, ecx
0x1800223d1  add     r8, 8
0x1800223d5  lea     rax, [rsp+38h+arg_0]
0x1800223da  mov     [rsp+38h+var_10], rax
0x1800223df  lea     rax, [rsp+38h+arg_8]
0x1800223e4  mov     [rsp+38h+var_18], rax
0x1800223e9  mov     r9, rcx
0x1800223ec  lea     rdx, byte_18003FC2F
0x1800223f3  mov     rcx, rdi
0x1800223f6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800223fb  mov     rcx, rbx
0x1800223fe  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180022403  nop
0x180022404  mov     rbx, [rsp+38h+arg_10]
0x180022409  add     rsp, 30h
0x18002240d  pop     rdi
0x18002240e  retn
```

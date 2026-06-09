# WnsCPLog::WnsMuxShutdown::StartActivity(void)

- ea: `0x18002d73c`
- end: `0x18002d7cb`
- name: `?StartActivity@WnsMuxShutdown@WnsCPLog@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(WnsCPLog::WnsMuxShutdown *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002d59c`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180014d80`
- `0x180023dc4`
- `0x18002d73c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d75d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsMuxShutdown::StartActivity(WnsCPLog::WnsMuxShutdown *this)
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
      (unsigned __int8 *)byte_18003DE15,
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
0x18002d73c  mov     [rsp+arg_10], rbx
0x18002d741  push    rdi
0x18002d742  sub     rsp, 30h
0x18002d746  mov     rbx, rcx
0x18002d749  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002d74e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002d753  mov     rdi, rax
0x18002d756  mov     edx, [rax]
0x18002d758  cmp     edx, 5
0x18002d75b  jbe     short loc_18002D7B7
0x18002d75d  call    cs:__imp_GetCurrentThreadId
0x18002d763  mov     [rsp+38h+arg_0], eax
0x18002d767  mov     [rsp+38h+arg_8], 0
0x18002d770  mov     r8, [rbx+110h]
0x18002d777  cmp     byte ptr [r8+4], 0
0x18002d77c  jz      short loc_18002D78B
0x18002d77e  lea     rcx, [r8+18h]; struct _GUID *
0x18002d782  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002d787  test    al, al
0x18002d789  jz      short loc_18002D78D
0x18002d78b  xor     ecx, ecx
0x18002d78d  add     r8, 8
0x18002d791  lea     rax, [rsp+38h+arg_0]
0x18002d796  mov     [rsp+38h+var_10], rax
0x18002d79b  lea     rax, [rsp+38h+arg_8]
0x18002d7a0  mov     [rsp+38h+var_18], rax
0x18002d7a5  mov     r9, rcx
0x18002d7a8  lea     rdx, byte_18003DE15
0x18002d7af  mov     rcx, rdi
0x18002d7b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002d7b7  mov     rcx, rbx
0x18002d7ba  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18002d7bf  nop
0x18002d7c0  mov     rbx, [rsp+38h+arg_10]
0x18002d7c5  add     rsp, 30h
0x18002d7c9  pop     rdi
0x18002d7ca  retn
```

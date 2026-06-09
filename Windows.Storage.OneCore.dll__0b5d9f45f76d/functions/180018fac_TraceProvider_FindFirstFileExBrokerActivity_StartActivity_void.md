# TraceProvider::FindFirstFileExBrokerActivity::StartActivity(void)

- ea: `0x180018fac`
- end: `0x180019044`
- name: `?StartActivity@FindFirstFileExBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::FindFirstFileExBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016a60`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x180018fac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fcd`

## pseudocode

```c
void __fastcall TraceProvider::FindFirstFileExBrokerActivity::StartActivity(
        TraceProvider::FindFirstFileExBrokerActivity *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = TraceProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)&unk_18002A5F0,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180018fac  mov     [rsp+arg_10], rbx
0x180018fb1  push    rdi
0x180018fb2  sub     rsp, 30h
0x180018fb6  mov     rbx, rcx
0x180018fb9  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018fbe  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180018fc3  mov     rdi, rax
0x180018fc6  mov     edx, [rax]
0x180018fc8  cmp     edx, 5
0x180018fcb  jbe     short loc_180019030
0x180018fcd  call    cs:__imp_GetCurrentThreadId
0x180018fd3  mov     [rsp+38h+arg_0], eax
0x180018fd7  xor     eax, eax
0x180018fd9  mov     [rsp+38h+arg_8], rax
0x180018fde  mov     r8, [rbx+110h]
0x180018fe5  cmp     [r8+4], al
0x180018fe9  jz      short loc_180019006
0x180018feb  lea     r9, [r8+18h]
0x180018fef  cmp     [r9], eax
0x180018ff2  jnz     short loc_180019009
0x180018ff4  cmp     [r9+4], eax
0x180018ff8  jnz     short loc_180019009
0x180018ffa  cmp     [r9+8], eax
0x180018ffe  jnz     short loc_180019009
0x180019000  cmp     [r9+0Ch], eax
0x180019004  jnz     short loc_180019009
0x180019006  mov     r9, rax
0x180019009  add     r8, 8
0x18001900d  lea     rax, [rsp+38h+arg_0]
0x180019012  mov     [rsp+38h+var_10], rax
0x180019017  lea     rax, [rsp+38h+arg_8]
0x18001901c  mov     [rsp+38h+var_18], rax
0x180019021  lea     rdx, unk_18002A5F0
0x180019028  mov     rcx, rdi
0x18001902b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019030  mov     rcx, rbx
0x180019033  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019038  nop
0x180019039  mov     rbx, [rsp+38h+arg_10]
0x18001903e  add     rsp, 30h
0x180019042  pop     rdi
0x180019043  retn
```

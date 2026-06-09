# TraceProvider::RemoveDirectoryBrokerActivity::StartActivity(void)

- ea: `0x18001922c`
- end: `0x1800192c4`
- name: `?StartActivity@RemoveDirectoryBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::RemoveDirectoryBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016d60`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001922c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001924d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001924d`

## pseudocode

```c
void __fastcall TraceProvider::RemoveDirectoryBrokerActivity::StartActivity(
        TraceProvider::RemoveDirectoryBrokerActivity *this)
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
      (__int64)&unk_18002A3A0,
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
0x18001922c  mov     [rsp+arg_10], rbx
0x180019231  push    rdi
0x180019232  sub     rsp, 30h
0x180019236  mov     rbx, rcx
0x180019239  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001923e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019243  mov     rdi, rax
0x180019246  mov     edx, [rax]
0x180019248  cmp     edx, 5
0x18001924b  jbe     short loc_1800192B0
0x18001924d  call    cs:__imp_GetCurrentThreadId
0x180019253  mov     [rsp+38h+arg_0], eax
0x180019257  xor     eax, eax
0x180019259  mov     [rsp+38h+arg_8], rax
0x18001925e  mov     r8, [rbx+110h]
0x180019265  cmp     [r8+4], al
0x180019269  jz      short loc_180019286
0x18001926b  lea     r9, [r8+18h]
0x18001926f  cmp     [r9], eax
0x180019272  jnz     short loc_180019289
0x180019274  cmp     [r9+4], eax
0x180019278  jnz     short loc_180019289
0x18001927a  cmp     [r9+8], eax
0x18001927e  jnz     short loc_180019289
0x180019280  cmp     [r9+0Ch], eax
0x180019284  jnz     short loc_180019289
0x180019286  mov     r9, rax
0x180019289  add     r8, 8
0x18001928d  lea     rax, [rsp+38h+arg_0]
0x180019292  mov     [rsp+38h+var_10], rax
0x180019297  lea     rax, [rsp+38h+arg_8]
0x18001929c  mov     [rsp+38h+var_18], rax
0x1800192a1  lea     rdx, unk_18002A3A0
0x1800192a8  mov     rcx, rdi
0x1800192ab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800192b0  mov     rcx, rbx
0x1800192b3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800192b8  nop
0x1800192b9  mov     rbx, [rsp+38h+arg_10]
0x1800192be  add     rsp, 30h
0x1800192c2  pop     rdi
0x1800192c3  retn
```

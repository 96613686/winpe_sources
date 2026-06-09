# TraceProvider::GetFileAttributesExBrokerActivity::StartActivity(void)

- ea: `0x1800190ec`
- end: `0x180019184`
- name: `?StartActivity@GetFileAttributesExBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesExBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016be0`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x1800190ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001910d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001910d`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesExBrokerActivity::StartActivity(
        TraceProvider::GetFileAttributesExBrokerActivity *this)
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
      (__int64)&unk_18002A540,
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
0x1800190ec  mov     [rsp+arg_10], rbx
0x1800190f1  push    rdi
0x1800190f2  sub     rsp, 30h
0x1800190f6  mov     rbx, rcx
0x1800190f9  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800190fe  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019103  mov     rdi, rax
0x180019106  mov     edx, [rax]
0x180019108  cmp     edx, 5
0x18001910b  jbe     short loc_180019170
0x18001910d  call    cs:__imp_GetCurrentThreadId
0x180019113  mov     [rsp+38h+arg_0], eax
0x180019117  xor     eax, eax
0x180019119  mov     [rsp+38h+arg_8], rax
0x18001911e  mov     r8, [rbx+110h]
0x180019125  cmp     [r8+4], al
0x180019129  jz      short loc_180019146
0x18001912b  lea     r9, [r8+18h]
0x18001912f  cmp     [r9], eax
0x180019132  jnz     short loc_180019149
0x180019134  cmp     [r9+4], eax
0x180019138  jnz     short loc_180019149
0x18001913a  cmp     [r9+8], eax
0x18001913e  jnz     short loc_180019149
0x180019140  cmp     [r9+0Ch], eax
0x180019144  jnz     short loc_180019149
0x180019146  mov     r9, rax
0x180019149  add     r8, 8
0x18001914d  lea     rax, [rsp+38h+arg_0]
0x180019152  mov     [rsp+38h+var_10], rax
0x180019157  lea     rax, [rsp+38h+arg_8]
0x18001915c  mov     [rsp+38h+var_18], rax
0x180019161  lea     rdx, unk_18002A540
0x180019168  mov     rcx, rdi
0x18001916b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019170  mov     rcx, rbx
0x180019173  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019178  nop
0x180019179  mov     rbx, [rsp+38h+arg_10]
0x18001917e  add     rsp, 30h
0x180019182  pop     rdi
0x180019183  retn
```

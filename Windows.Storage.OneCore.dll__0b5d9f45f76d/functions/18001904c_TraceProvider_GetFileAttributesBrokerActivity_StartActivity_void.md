# TraceProvider::GetFileAttributesBrokerActivity::StartActivity(void)

- ea: `0x18001904c`
- end: `0x1800190e4`
- name: `?StartActivity@GetFileAttributesBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016b20`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001904c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001906d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001906d`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesBrokerActivity::StartActivity(
        TraceProvider::GetFileAttributesBrokerActivity *this)
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
      (__int64)byte_18002A599,
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
0x18001904c  mov     [rsp+arg_10], rbx
0x180019051  push    rdi
0x180019052  sub     rsp, 30h
0x180019056  mov     rbx, rcx
0x180019059  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001905e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019063  mov     rdi, rax
0x180019066  mov     edx, [rax]
0x180019068  cmp     edx, 5
0x18001906b  jbe     short loc_1800190D0
0x18001906d  call    cs:__imp_GetCurrentThreadId
0x180019073  mov     [rsp+38h+arg_0], eax
0x180019077  xor     eax, eax
0x180019079  mov     [rsp+38h+arg_8], rax
0x18001907e  mov     r8, [rbx+110h]
0x180019085  cmp     [r8+4], al
0x180019089  jz      short loc_1800190A6
0x18001908b  lea     r9, [r8+18h]
0x18001908f  cmp     [r9], eax
0x180019092  jnz     short loc_1800190A9
0x180019094  cmp     [r9+4], eax
0x180019098  jnz     short loc_1800190A9
0x18001909a  cmp     [r9+8], eax
0x18001909e  jnz     short loc_1800190A9
0x1800190a0  cmp     [r9+0Ch], eax
0x1800190a4  jnz     short loc_1800190A9
0x1800190a6  mov     r9, rax
0x1800190a9  add     r8, 8
0x1800190ad  lea     rax, [rsp+38h+arg_0]
0x1800190b2  mov     [rsp+38h+var_10], rax
0x1800190b7  lea     rax, [rsp+38h+arg_8]
0x1800190bc  mov     [rsp+38h+var_18], rax
0x1800190c1  lea     rdx, byte_18002A599
0x1800190c8  mov     rcx, rdi
0x1800190cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800190d0  mov     rcx, rbx
0x1800190d3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800190d8  nop
0x1800190d9  mov     rbx, [rsp+38h+arg_10]
0x1800190de  add     rsp, 30h
0x1800190e2  pop     rdi
0x1800190e3  retn
```

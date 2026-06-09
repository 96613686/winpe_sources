# TraceProvider::CreateFile2BrokerActivity::StartActivity(void)

- ea: `0x180018e6c`
- end: `0x180018f04`
- name: `?StartActivity@CreateFile2BrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::CreateFile2BrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800168e0`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x180018e6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e8d`

## pseudocode

```c
void __fastcall TraceProvider::CreateFile2BrokerActivity::StartActivity(TraceProvider::CreateFile2BrokerActivity *this)
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
      (__int64)byte_18002A695,
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
0x180018e6c  mov     [rsp+arg_10], rbx
0x180018e71  push    rdi
0x180018e72  sub     rsp, 30h
0x180018e76  mov     rbx, rcx
0x180018e79  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018e7e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180018e83  mov     rdi, rax
0x180018e86  mov     edx, [rax]
0x180018e88  cmp     edx, 5
0x180018e8b  jbe     short loc_180018EF0
0x180018e8d  call    cs:__imp_GetCurrentThreadId
0x180018e93  mov     [rsp+38h+arg_0], eax
0x180018e97  xor     eax, eax
0x180018e99  mov     [rsp+38h+arg_8], rax
0x180018e9e  mov     r8, [rbx+110h]
0x180018ea5  cmp     [r8+4], al
0x180018ea9  jz      short loc_180018EC6
0x180018eab  lea     r9, [r8+18h]
0x180018eaf  cmp     [r9], eax
0x180018eb2  jnz     short loc_180018EC9
0x180018eb4  cmp     [r9+4], eax
0x180018eb8  jnz     short loc_180018EC9
0x180018eba  cmp     [r9+8], eax
0x180018ebe  jnz     short loc_180018EC9
0x180018ec0  cmp     [r9+0Ch], eax
0x180018ec4  jnz     short loc_180018EC9
0x180018ec6  mov     r9, rax
0x180018ec9  add     r8, 8
0x180018ecd  lea     rax, [rsp+38h+arg_0]
0x180018ed2  mov     [rsp+38h+var_10], rax
0x180018ed7  lea     rax, [rsp+38h+arg_8]
0x180018edc  mov     [rsp+38h+var_18], rax
0x180018ee1  lea     rdx, byte_18002A695
0x180018ee8  mov     rcx, rdi
0x180018eeb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018ef0  mov     rcx, rbx
0x180018ef3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180018ef8  nop
0x180018ef9  mov     rbx, [rsp+38h+arg_10]
0x180018efe  add     rsp, 30h
0x180018f02  pop     rdi
0x180018f03  retn
```

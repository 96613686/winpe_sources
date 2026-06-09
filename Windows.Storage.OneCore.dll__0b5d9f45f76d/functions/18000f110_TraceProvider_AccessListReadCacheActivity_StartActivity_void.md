# TraceProvider::AccessListReadCacheActivity::StartActivity(void)

- ea: `0x18000f110`
- end: `0x18000f1a8`
- name: `?StartActivity@AccessListReadCacheActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::AccessListReadCacheActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c538`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x18000f110`
- `0x180011570`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f131`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f131`

## pseudocode

```c
void __fastcall TraceProvider::AccessListReadCacheActivity::StartActivity(
        TraceProvider::AccessListReadCacheActivity *this)
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
      (__int64)byte_1800298F1,
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
0x18000f110  mov     [rsp+arg_10], rbx
0x18000f115  push    rdi
0x18000f116  sub     rsp, 30h
0x18000f11a  mov     rbx, rcx
0x18000f11d  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000f122  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18000f127  mov     rdi, rax
0x18000f12a  mov     edx, [rax]
0x18000f12c  cmp     edx, 5
0x18000f12f  jbe     short loc_18000F194
0x18000f131  call    cs:__imp_GetCurrentThreadId
0x18000f137  mov     [rsp+38h+arg_0], eax
0x18000f13b  xor     eax, eax
0x18000f13d  mov     [rsp+38h+arg_8], rax
0x18000f142  mov     r8, [rbx+110h]
0x18000f149  cmp     [r8+4], al
0x18000f14d  jz      short loc_18000F16A
0x18000f14f  lea     r9, [r8+18h]
0x18000f153  cmp     [r9], eax
0x18000f156  jnz     short loc_18000F16D
0x18000f158  cmp     [r9+4], eax
0x18000f15c  jnz     short loc_18000F16D
0x18000f15e  cmp     [r9+8], eax
0x18000f162  jnz     short loc_18000F16D
0x18000f164  cmp     [r9+0Ch], eax
0x18000f168  jnz     short loc_18000F16D
0x18000f16a  mov     r9, rax
0x18000f16d  add     r8, 8
0x18000f171  lea     rax, [rsp+38h+arg_0]
0x18000f176  mov     [rsp+38h+var_10], rax
0x18000f17b  lea     rax, [rsp+38h+arg_8]
0x18000f180  mov     [rsp+38h+var_18], rax
0x18000f185  lea     rdx, byte_1800298F1
0x18000f18c  mov     rcx, rdi
0x18000f18f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000f194  mov     rcx, rbx
0x18000f197  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000f19c  nop
0x18000f19d  mov     rbx, [rsp+38h+arg_10]
0x18000f1a2  add     rsp, 30h
0x18000f1a6  pop     rdi
0x18000f1a7  retn
```

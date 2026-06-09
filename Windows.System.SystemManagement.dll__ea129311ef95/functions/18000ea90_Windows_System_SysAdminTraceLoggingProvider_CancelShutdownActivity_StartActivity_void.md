# Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StartActivity(void)

- ea: `0x18000ea90`
- end: `0x18000eb28`
- name: `?StartActivity@CancelShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d810`

## callees

- `0x1800016c0`
- `0x18000da8c`
- `0x18000e62c`
- `0x18000ea90`
- `0x18000fe0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eab1`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StartActivity(
        Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = Windows::System::SysAdminTraceLoggingProvider::Provider();
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
      (__int64)&unk_180039588,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000ea90  mov     [rsp+arg_10], rbx
0x18000ea95  push    rdi
0x18000ea96  sub     rsp, 30h
0x18000ea9a  mov     rbx, rcx
0x18000ea9d  call    ?zInternalStart@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000eaa2  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000eaa7  mov     rdi, rax
0x18000eaaa  mov     edx, [rax]
0x18000eaac  cmp     edx, 5
0x18000eaaf  jbe     short loc_18000EB14
0x18000eab1  call    cs:__imp_GetCurrentThreadId
0x18000eab7  mov     [rsp+38h+arg_0], eax
0x18000eabb  xor     eax, eax
0x18000eabd  mov     [rsp+38h+arg_8], rax
0x18000eac2  mov     r8, [rbx+110h]
0x18000eac9  cmp     [r8+4], al
0x18000eacd  jz      short loc_18000EAEA
0x18000eacf  lea     r9, [r8+18h]
0x18000ead3  cmp     [r9], eax
0x18000ead6  jnz     short loc_18000EAED
0x18000ead8  cmp     [r9+4], eax
0x18000eadc  jnz     short loc_18000EAED
0x18000eade  cmp     [r9+8], eax
0x18000eae2  jnz     short loc_18000EAED
0x18000eae4  cmp     [r9+0Ch], eax
0x18000eae8  jnz     short loc_18000EAED
0x18000eaea  mov     r9, rax
0x18000eaed  add     r8, 8
0x18000eaf1  lea     rax, [rsp+38h+arg_0]
0x18000eaf6  mov     [rsp+38h+var_10], rax
0x18000eafb  lea     rax, [rsp+38h+arg_8]
0x18000eb00  mov     [rsp+38h+var_18], rax
0x18000eb05  lea     rdx, unk_180039588
0x18000eb0c  mov     rcx, rdi
0x18000eb0f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000eb14  mov     rcx, rbx
0x18000eb17  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000eb1c  nop
0x18000eb1d  mov     rbx, [rsp+38h+arg_10]
0x18000eb22  add     rsp, 30h
0x18000eb26  pop     rdi
0x18000eb27  retn
```

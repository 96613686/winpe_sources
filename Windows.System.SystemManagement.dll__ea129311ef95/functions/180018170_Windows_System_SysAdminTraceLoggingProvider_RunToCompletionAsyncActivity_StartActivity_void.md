# Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StartActivity(void)

- ea: `0x180018170`
- end: `0x180018208`
- name: `?StartActivity@RunToCompletionAsyncActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017f50`

## callees

- `0x1800016c0`
- `0x18000da8c`
- `0x18000e62c`
- `0x18000fe0c`
- `0x180018170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018191`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018191`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity::StartActivity(
        Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncActivity *this)
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
      (__int64)&byte_180039FA7,
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
0x180018170  mov     [rsp+arg_10], rbx
0x180018175  push    rdi
0x180018176  sub     rsp, 30h
0x18001817a  mov     rbx, rcx
0x18001817d  call    ?zInternalStart@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018182  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180018187  mov     rdi, rax
0x18001818a  mov     edx, [rax]
0x18001818c  cmp     edx, 5
0x18001818f  jbe     short loc_1800181F4
0x180018191  call    cs:__imp_GetCurrentThreadId
0x180018197  mov     [rsp+38h+arg_0], eax
0x18001819b  xor     eax, eax
0x18001819d  mov     [rsp+38h+arg_8], rax
0x1800181a2  mov     r8, [rbx+110h]
0x1800181a9  cmp     [r8+4], al
0x1800181ad  jz      short loc_1800181CA
0x1800181af  lea     r9, [r8+18h]
0x1800181b3  cmp     [r9], eax
0x1800181b6  jnz     short loc_1800181CD
0x1800181b8  cmp     [r9+4], eax
0x1800181bc  jnz     short loc_1800181CD
0x1800181be  cmp     [r9+8], eax
0x1800181c2  jnz     short loc_1800181CD
0x1800181c4  cmp     [r9+0Ch], eax
0x1800181c8  jnz     short loc_1800181CD
0x1800181ca  mov     r9, rax
0x1800181cd  add     r8, 8
0x1800181d1  lea     rax, [rsp+38h+arg_0]
0x1800181d6  mov     [rsp+38h+var_10], rax
0x1800181db  lea     rax, [rsp+38h+arg_8]
0x1800181e0  mov     [rsp+38h+var_18], rax
0x1800181e5  lea     rdx, byte_180039FA7
0x1800181ec  mov     rcx, rdi
0x1800181ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800181f4  mov     rcx, rbx
0x1800181f7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800181fc  nop
0x1800181fd  mov     rbx, [rsp+38h+arg_10]
0x180018202  add     rsp, 30h
0x180018206  pop     rdi
0x180018207  retn
```

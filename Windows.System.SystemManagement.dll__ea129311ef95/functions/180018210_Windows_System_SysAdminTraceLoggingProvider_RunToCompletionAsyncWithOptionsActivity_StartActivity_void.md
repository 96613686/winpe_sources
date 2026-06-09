# Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StartActivity(void)

- ea: `0x180018210`
- end: `0x1800182c9`
- name: `?StartActivity@RunToCompletionAsyncWithOptionsActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018020`

## callees

- `0x1800016c0`
- `0x180001ebc`
- `0x18000da8c`
- `0x18000e62c`
- `0x18000fd9c`
- `0x180018210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001824b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001824b`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity::StartActivity(
        Windows::System::SysAdminTraceLoggingProvider::RunToCompletionAsyncWithOptionsActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = Windows::System::SysAdminTraceLoggingProvider::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_180039DA1,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180018210  mov     [rsp+arg_10], rbx
0x180018215  push    rdi
0x180018216  sub     rsp, 30h
0x18001821a  mov     rbx, rcx
0x18001821d  call    ?zInternalStart@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018222  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180018227  mov     rdi, rax
0x18001822a  mov     edx, [rax]
0x18001822c  cmp     edx, 5
0x18001822f  jbe     loc_1800182B5
0x180018235  mov     rdx, 200000000000h
0x18001823f  mov     rcx, rax
0x180018242  call    _tlgKeywordOn
0x180018247  test    al, al
0x180018249  jz      short loc_1800182B5
0x18001824b  call    cs:__imp_GetCurrentThreadId
0x180018251  mov     [rsp+38h+arg_0], eax
0x180018255  mov     [rsp+38h+arg_8], 0
0x18001825e  mov     r8, [rbx+110h]
0x180018265  cmp     byte ptr [r8+4], 0
0x18001826a  jz      short loc_18001828B
0x18001826c  lea     r9, [r8+18h]
0x180018270  cmp     dword ptr [r9], 0
0x180018274  jnz     short loc_18001828E
0x180018276  cmp     dword ptr [r9+4], 0
0x18001827b  jnz     short loc_18001828E
0x18001827d  cmp     dword ptr [r9+8], 0
0x180018282  jnz     short loc_18001828E
0x180018284  cmp     dword ptr [r9+0Ch], 0
0x180018289  jnz     short loc_18001828E
0x18001828b  xor     r9d, r9d
0x18001828e  add     r8, 8
0x180018292  lea     rax, [rsp+38h+arg_0]
0x180018297  mov     [rsp+38h+var_10], rax
0x18001829c  lea     rax, [rsp+38h+arg_8]
0x1800182a1  mov     [rsp+38h+var_18], rax
0x1800182a6  lea     rdx, byte_180039DA1
0x1800182ad  mov     rcx, rdi
0x1800182b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800182b5  mov     rcx, rbx
0x1800182b8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800182bd  nop
0x1800182be  mov     rbx, [rsp+38h+arg_10]
0x1800182c3  add     rsp, 30h
0x1800182c7  pop     rdi
0x1800182c8  retn
```

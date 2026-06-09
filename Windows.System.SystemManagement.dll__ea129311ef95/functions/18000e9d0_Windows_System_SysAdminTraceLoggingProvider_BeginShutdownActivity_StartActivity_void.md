# Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StartActivity(void)

- ea: `0x18000e9d0`
- end: `0x18000ea89`
- name: `?StartActivity@BeginShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d670`

## callees

- `0x1800016c0`
- `0x180001ebc`
- `0x18000da8c`
- `0x18000e62c`
- `0x18000e9d0`
- `0x18000fd9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea0b`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StartActivity(
        Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *this)
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
      (__int64)&word_18003977E,
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
0x18000e9d0  mov     [rsp+arg_10], rbx
0x18000e9d5  push    rdi
0x18000e9d6  sub     rsp, 30h
0x18000e9da  mov     rbx, rcx
0x18000e9dd  call    ?zInternalStart@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000e9e2  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x18000e9e7  mov     rdi, rax
0x18000e9ea  mov     edx, [rax]
0x18000e9ec  cmp     edx, 5
0x18000e9ef  jbe     loc_18000EA75
0x18000e9f5  mov     rdx, 200000000000h
0x18000e9ff  mov     rcx, rax
0x18000ea02  call    _tlgKeywordOn
0x18000ea07  test    al, al
0x18000ea09  jz      short loc_18000EA75
0x18000ea0b  call    cs:__imp_GetCurrentThreadId
0x18000ea11  mov     [rsp+38h+arg_0], eax
0x18000ea15  mov     [rsp+38h+arg_8], 0
0x18000ea1e  mov     r8, [rbx+110h]
0x18000ea25  cmp     byte ptr [r8+4], 0
0x18000ea2a  jz      short loc_18000EA4B
0x18000ea2c  lea     r9, [r8+18h]
0x18000ea30  cmp     dword ptr [r9], 0
0x18000ea34  jnz     short loc_18000EA4E
0x18000ea36  cmp     dword ptr [r9+4], 0
0x18000ea3b  jnz     short loc_18000EA4E
0x18000ea3d  cmp     dword ptr [r9+8], 0
0x18000ea42  jnz     short loc_18000EA4E
0x18000ea44  cmp     dword ptr [r9+0Ch], 0
0x18000ea49  jnz     short loc_18000EA4E
0x18000ea4b  xor     r9d, r9d
0x18000ea4e  add     r8, 8
0x18000ea52  lea     rax, [rsp+38h+arg_0]
0x18000ea57  mov     [rsp+38h+var_10], rax
0x18000ea5c  lea     rax, [rsp+38h+arg_8]
0x18000ea61  mov     [rsp+38h+var_18], rax
0x18000ea66  lea     rdx, word_18003977E
0x18000ea6d  mov     rcx, rdi
0x18000ea70  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000ea75  mov     rcx, rbx
0x18000ea78  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000ea7d  nop
0x18000ea7e  mov     rbx, [rsp+38h+arg_10]
0x18000ea83  add     rsp, 30h
0x18000ea87  pop     rdi
0x18000ea88  retn
```

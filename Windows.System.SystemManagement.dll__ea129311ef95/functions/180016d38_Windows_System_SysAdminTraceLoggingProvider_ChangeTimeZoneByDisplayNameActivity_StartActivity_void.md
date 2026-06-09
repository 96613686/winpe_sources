# Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StartActivity(void)

- ea: `0x180016d38`
- end: `0x180016df1`
- name: `?StartActivity@ChangeTimeZoneByDisplayNameActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014ce0`

## callees

- `0x1800016c0`
- `0x180001ebc`
- `0x18000da8c`
- `0x18000e62c`
- `0x18000fd9c`
- `0x180016d38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d73`

## pseudocode

```c
void __fastcall Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity::StartActivity(
        Windows::System::SysAdminTraceLoggingProvider::ChangeTimeZoneByDisplayNameActivity *this)
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
      (__int64)&byte_180039BA7,
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
0x180016d38  mov     [rsp+arg_10], rbx
0x180016d3d  push    rdi
0x180016d3e  sub     rsp, 30h
0x180016d42  mov     rbx, rcx
0x180016d45  call    ?zInternalStart@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180016d4a  call    ?Provider@SysAdminTraceLoggingProvider@System@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::System::SysAdminTraceLoggingProvider::Provider(void)
0x180016d4f  mov     rdi, rax
0x180016d52  mov     edx, [rax]
0x180016d54  cmp     edx, 5
0x180016d57  jbe     loc_180016DDD
0x180016d5d  mov     rdx, 200000000000h
0x180016d67  mov     rcx, rax
0x180016d6a  call    _tlgKeywordOn
0x180016d6f  test    al, al
0x180016d71  jz      short loc_180016DDD
0x180016d73  call    cs:__imp_GetCurrentThreadId
0x180016d79  mov     [rsp+38h+arg_0], eax
0x180016d7d  mov     [rsp+38h+arg_8], 0
0x180016d86  mov     r8, [rbx+110h]
0x180016d8d  cmp     byte ptr [r8+4], 0
0x180016d92  jz      short loc_180016DB3
0x180016d94  lea     r9, [r8+18h]
0x180016d98  cmp     dword ptr [r9], 0
0x180016d9c  jnz     short loc_180016DB6
0x180016d9e  cmp     dword ptr [r9+4], 0
0x180016da3  jnz     short loc_180016DB6
0x180016da5  cmp     dword ptr [r9+8], 0
0x180016daa  jnz     short loc_180016DB6
0x180016dac  cmp     dword ptr [r9+0Ch], 0
0x180016db1  jnz     short loc_180016DB6
0x180016db3  xor     r9d, r9d
0x180016db6  add     r8, 8
0x180016dba  lea     rax, [rsp+38h+arg_0]
0x180016dbf  mov     [rsp+38h+var_10], rax
0x180016dc4  lea     rax, [rsp+38h+arg_8]
0x180016dc9  mov     [rsp+38h+var_18], rax
0x180016dce  lea     rdx, byte_180039BA7
0x180016dd5  mov     rcx, rdi
0x180016dd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180016ddd  mov     rcx, rbx
0x180016de0  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180016de5  nop
0x180016de6  mov     rbx, [rsp+38h+arg_10]
0x180016deb  add     rsp, 30h
0x180016def  pop     rdi
0x180016df0  retn
```

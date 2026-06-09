# PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction::StartActivity(void)

- ea: `0x180043ef0`
- end: `0x180043fa9`
- name: `?StartActivity@EnergySaverOverrideQuickAction@PowerAndBatteryTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180043b90`

## callees

- `0x18000143c`
- `0x180001c3c`
- `0x18001d9b0`
- `0x180025840`
- `0x18002c804`
- `0x180043ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043f2b`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction::StartActivity(
        PowerAndBatteryTelemetry::EnergySaverOverrideQuickAction *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = PowerAndBatteryLoggingProvider::Provider();
  v4 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL, v3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)&byte_18005AEAF,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180043ef0  mov     [rsp+arg_10], rbx
0x180043ef5  push    rdi
0x180043ef6  sub     rsp, 30h
0x180043efa  mov     rbx, rcx
0x180043efd  call    ?zInternalStart@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180043f02  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180043f07  mov     rdi, rax
0x180043f0a  mov     edx, [rax]
0x180043f0c  cmp     edx, 5
0x180043f0f  jbe     loc_180043F95
0x180043f15  mov     rdx, 400000000000h
0x180043f1f  mov     rcx, rax
0x180043f22  call    _tlgKeywordOn
0x180043f27  test    al, al
0x180043f29  jz      short loc_180043F95
0x180043f2b  call    cs:__imp_GetCurrentThreadId
0x180043f31  mov     [rsp+38h+arg_0], eax
0x180043f35  mov     [rsp+38h+arg_8], 0
0x180043f3e  mov     r8, [rbx+110h]
0x180043f45  cmp     byte ptr [r8+4], 0
0x180043f4a  jz      short loc_180043F6B
0x180043f4c  lea     r9, [r8+18h]
0x180043f50  cmp     dword ptr [r9], 0
0x180043f54  jnz     short loc_180043F6E
0x180043f56  cmp     dword ptr [r9+4], 0
0x180043f5b  jnz     short loc_180043F6E
0x180043f5d  cmp     dword ptr [r9+8], 0
0x180043f62  jnz     short loc_180043F6E
0x180043f64  cmp     dword ptr [r9+0Ch], 0
0x180043f69  jnz     short loc_180043F6E
0x180043f6b  xor     r9d, r9d
0x180043f6e  add     r8, 8
0x180043f72  lea     rax, [rsp+38h+arg_0]
0x180043f77  mov     [rsp+38h+var_10], rax
0x180043f7c  lea     rax, [rsp+38h+arg_8]
0x180043f81  mov     [rsp+38h+var_18], rax
0x180043f86  lea     rdx, byte_18005AEAF
0x180043f8d  mov     rcx, rdi
0x180043f90  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180043f95  mov     rcx, rbx
0x180043f98  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180043f9d  nop
0x180043f9e  mov     rbx, [rsp+38h+arg_10]
0x180043fa3  add     rsp, 30h
0x180043fa7  pop     rdi
0x180043fa8  retn
```

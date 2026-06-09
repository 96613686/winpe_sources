# PowerAndBatteryTelemetry::EnergySaverOverride::StartActivity(void)

- ea: `0x180043d70`
- end: `0x180043e29`
- name: `?StartActivity@EnergySaverOverride@PowerAndBatteryTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::EnergySaverOverride *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800439a8`

## callees

- `0x18000143c`
- `0x180001c3c`
- `0x18001d9b0`
- `0x180025840`
- `0x18002c804`
- `0x180043d70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043dab`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::EnergySaverOverride::StartActivity(
        PowerAndBatteryTelemetry::EnergySaverOverride *this)
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
      (__int64)&word_18005AF56,
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
0x180043d70  mov     [rsp+arg_10], rbx
0x180043d75  push    rdi
0x180043d76  sub     rsp, 30h
0x180043d7a  mov     rbx, rcx
0x180043d7d  call    ?zInternalStart@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180043d82  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180043d87  mov     rdi, rax
0x180043d8a  mov     edx, [rax]
0x180043d8c  cmp     edx, 5
0x180043d8f  jbe     loc_180043E15
0x180043d95  mov     rdx, 400000000000h
0x180043d9f  mov     rcx, rax
0x180043da2  call    _tlgKeywordOn
0x180043da7  test    al, al
0x180043da9  jz      short loc_180043E15
0x180043dab  call    cs:__imp_GetCurrentThreadId
0x180043db1  mov     [rsp+38h+arg_0], eax
0x180043db5  mov     [rsp+38h+arg_8], 0
0x180043dbe  mov     r8, [rbx+110h]
0x180043dc5  cmp     byte ptr [r8+4], 0
0x180043dca  jz      short loc_180043DEB
0x180043dcc  lea     r9, [r8+18h]
0x180043dd0  cmp     dword ptr [r9], 0
0x180043dd4  jnz     short loc_180043DEE
0x180043dd6  cmp     dword ptr [r9+4], 0
0x180043ddb  jnz     short loc_180043DEE
0x180043ddd  cmp     dword ptr [r9+8], 0
0x180043de2  jnz     short loc_180043DEE
0x180043de4  cmp     dword ptr [r9+0Ch], 0
0x180043de9  jnz     short loc_180043DEE
0x180043deb  xor     r9d, r9d
0x180043dee  add     r8, 8
0x180043df2  lea     rax, [rsp+38h+arg_0]
0x180043df7  mov     [rsp+38h+var_10], rax
0x180043dfc  lea     rax, [rsp+38h+arg_8]
0x180043e01  mov     [rsp+38h+var_18], rax
0x180043e06  lea     rdx, word_18005AF56
0x180043e0d  mov     rcx, rdi
0x180043e10  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180043e15  mov     rcx, rbx
0x180043e18  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180043e1d  nop
0x180043e1e  mov     rbx, [rsp+38h+arg_10]
0x180043e23  add     rsp, 30h
0x180043e27  pop     rdi
0x180043e28  retn
```

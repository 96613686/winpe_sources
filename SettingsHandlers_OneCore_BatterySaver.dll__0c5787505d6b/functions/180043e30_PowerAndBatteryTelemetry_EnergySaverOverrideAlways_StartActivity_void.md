# PowerAndBatteryTelemetry::EnergySaverOverrideAlways::StartActivity(void)

- ea: `0x180043e30`
- end: `0x180043ee9`
- name: `?StartActivity@EnergySaverOverrideAlways@PowerAndBatteryTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::EnergySaverOverrideAlways *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180043830`

## callees

- `0x18000143c`
- `0x180001c3c`
- `0x18001d9b0`
- `0x180025840`
- `0x18002c804`
- `0x180043e30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e6b`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::EnergySaverOverrideAlways::StartActivity(
        PowerAndBatteryTelemetry::EnergySaverOverrideAlways *this)
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
      (__int64)byte_18005AF05,
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
0x180043e30  mov     [rsp+arg_10], rbx
0x180043e35  push    rdi
0x180043e36  sub     rsp, 30h
0x180043e3a  mov     rbx, rcx
0x180043e3d  call    ?zInternalStart@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180043e42  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x180043e47  mov     rdi, rax
0x180043e4a  mov     edx, [rax]
0x180043e4c  cmp     edx, 5
0x180043e4f  jbe     loc_180043ED5
0x180043e55  mov     rdx, 400000000000h
0x180043e5f  mov     rcx, rax
0x180043e62  call    _tlgKeywordOn
0x180043e67  test    al, al
0x180043e69  jz      short loc_180043ED5
0x180043e6b  call    cs:__imp_GetCurrentThreadId
0x180043e71  mov     [rsp+38h+arg_0], eax
0x180043e75  mov     [rsp+38h+arg_8], 0
0x180043e7e  mov     r8, [rbx+110h]
0x180043e85  cmp     byte ptr [r8+4], 0
0x180043e8a  jz      short loc_180043EAB
0x180043e8c  lea     r9, [r8+18h]
0x180043e90  cmp     dword ptr [r9], 0
0x180043e94  jnz     short loc_180043EAE
0x180043e96  cmp     dword ptr [r9+4], 0
0x180043e9b  jnz     short loc_180043EAE
0x180043e9d  cmp     dword ptr [r9+8], 0
0x180043ea2  jnz     short loc_180043EAE
0x180043ea4  cmp     dword ptr [r9+0Ch], 0
0x180043ea9  jnz     short loc_180043EAE
0x180043eab  xor     r9d, r9d
0x180043eae  add     r8, 8
0x180043eb2  lea     rax, [rsp+38h+arg_0]
0x180043eb7  mov     [rsp+38h+var_10], rax
0x180043ebc  lea     rax, [rsp+38h+arg_8]
0x180043ec1  mov     [rsp+38h+var_18], rax
0x180043ec6  lea     rdx, byte_18005AF05
0x180043ecd  mov     rcx, rdi
0x180043ed0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180043ed5  mov     rcx, rbx
0x180043ed8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180043edd  nop
0x180043ede  mov     rbx, [rsp+38h+arg_10]
0x180043ee3  add     rsp, 30h
0x180043ee7  pop     rdi
0x180043ee8  retn
```

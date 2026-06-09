# PowerAndBatteryTelemetry::SetEnergySaverThreshold::StartActivity(void)

- ea: `0x1800290a0`
- end: `0x180029159`
- name: `?StartActivity@SetEnergySaverThreshold@PowerAndBatteryTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(PowerAndBatteryTelemetry::SetEnergySaverThreshold *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180028920`

## callees

- `0x18000143c`
- `0x180001c3c`
- `0x18001d9b0`
- `0x180025840`
- `0x1800290a0`
- `0x18002c804`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800290db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800290db`

## pseudocode

```c
void __fastcall PowerAndBatteryTelemetry::SetEnergySaverThreshold::StartActivity(
        PowerAndBatteryTelemetry::SetEnergySaverThreshold *this)
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
      (__int64)byte_18005A3F1,
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
0x1800290a0  mov     [rsp+arg_10], rbx
0x1800290a5  push    rdi
0x1800290a6  sub     rsp, 30h
0x1800290aa  mov     rbx, rcx
0x1800290ad  call    ?zInternalStart@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800290b2  call    ?Provider@PowerAndBatteryLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PowerAndBatteryLoggingProvider::Provider(void)
0x1800290b7  mov     rdi, rax
0x1800290ba  mov     edx, [rax]
0x1800290bc  cmp     edx, 5
0x1800290bf  jbe     loc_180029145
0x1800290c5  mov     rdx, 400000000000h
0x1800290cf  mov     rcx, rax
0x1800290d2  call    _tlgKeywordOn
0x1800290d7  test    al, al
0x1800290d9  jz      short loc_180029145
0x1800290db  call    cs:__imp_GetCurrentThreadId
0x1800290e1  mov     [rsp+38h+arg_0], eax
0x1800290e5  mov     [rsp+38h+arg_8], 0
0x1800290ee  mov     r8, [rbx+110h]
0x1800290f5  cmp     byte ptr [r8+4], 0
0x1800290fa  jz      short loc_18002911B
0x1800290fc  lea     r9, [r8+18h]
0x180029100  cmp     dword ptr [r9], 0
0x180029104  jnz     short loc_18002911E
0x180029106  cmp     dword ptr [r9+4], 0
0x18002910b  jnz     short loc_18002911E
0x18002910d  cmp     dword ptr [r9+8], 0
0x180029112  jnz     short loc_18002911E
0x180029114  cmp     dword ptr [r9+0Ch], 0
0x180029119  jnz     short loc_18002911E
0x18002911b  xor     r9d, r9d
0x18002911e  add     r8, 8
0x180029122  lea     rax, [rsp+38h+arg_0]
0x180029127  mov     [rsp+38h+var_10], rax
0x18002912c  lea     rax, [rsp+38h+arg_8]
0x180029131  mov     [rsp+38h+var_18], rax
0x180029136  lea     rdx, byte_18005A3F1
0x18002913d  mov     rcx, rdi
0x180029140  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180029145  mov     rcx, rbx
0x180029148  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPowerAndBatteryLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PowerAndBatteryLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18002914d  nop
0x18002914e  mov     rbx, [rsp+38h+arg_10]
0x180029153  add     rsp, 30h
0x180029157  pop     rdi
0x180029158  retn
```

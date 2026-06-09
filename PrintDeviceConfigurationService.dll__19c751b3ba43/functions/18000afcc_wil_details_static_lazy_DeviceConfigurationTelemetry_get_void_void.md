# wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))

- ea: `0x18000afcc`
- end: `0x18000b078`
- name: `?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z`
- size: `172`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac9c`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000c19c`
- `0x18000ed18`

## callees

- `0x180002470`
- `0x18000aaec`
- `0x18000afcc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b002`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b002`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<DeviceConfigurationTelemetry>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  WINBOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`DeviceConfigurationTelemetry::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`DeviceConfigurationTelemetry::Instance'::`2'::wrapper;
    v8 = &qword_180024668;
    qword_180024670 = 0;
    qword_180024668 = (__int64)&wil::TraceLoggingProvider::`vftable';
    byte_180024678 = 0;
    dword_18002467C = 0;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<DeviceConfigurationTelemetry>::Completer::~Completer((__int64)&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18000afcc  mov     rax, rsp
0x18000afcf  mov     [rax+10h], rbx
0x18000afd3  mov     [rax+8], rcx
0x18000afd7  push    rsi
0x18000afd8  sub     rsp, 30h
0x18000afdc  mov     rbx, rdx
0x18000afdf  mov     qword ptr [rax+18h], 0
0x18000afe7  lea     rsi, ?wrapper@?1??Instance@DeviceConfigurationTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@A; wil::details::static_lazy<DeviceConfigurationTelemetry> `DeviceConfigurationTelemetry::Instance(void)'::`2'::wrapper
0x18000afee  mov     dword ptr [rax+8], 0
0x18000aff5  mov     rcx, rsi; lpInitOnce
0x18000aff8  lea     r9, [rax+18h]; lpContext
0x18000affc  lea     r8, [rax+8]; fPending
0x18000b000  xor     edx, edx; dwFlags
0x18000b002  call    cs:__imp_InitOnceBeginInitialize
0x18000b008  test    eax, eax
0x18000b00a  jz      short loc_18000B068
0x18000b00c  cmp     [rsp+38h+arg_0], 0
0x18000b011  jz      short loc_18000B068
0x18000b013  lea     rax, qword_180024668
0x18000b01a  mov     [rsp+38h+var_18], rsi
0x18000b01f  mov     [rsp+38h+arg_10], rax
0x18000b024  mov     rcx, rbx; void (__cdecl *)()
0x18000b027  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000b02e  mov     cs:qword_180024670, 0
0x18000b039  mov     cs:qword_180024668, rax
0x18000b040  mov     cs:byte_180024678, 0
0x18000b047  mov     cs:dword_18002467C, 0
0x18000b051  call    atexit
0x18000b056  lea     rcx, [rsp+38h+var_18]
0x18000b05b  mov     [rsp+38h+var_10], 0
0x18000b063  call    ??1Completer@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<DeviceConfigurationTelemetry>::Completer::~Completer(void)
0x18000b068  mov     rax, [rsp+38h+arg_10]
0x18000b06d  mov     rbx, [rsp+38h+arg_8]
0x18000b072  add     rsp, 30h
0x18000b076  pop     rsi
0x18000b077  retn
```

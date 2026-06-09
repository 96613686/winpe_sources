# WaasMedic::TelemetryProvider::Instance(void)

- ea: `0x18000d04c`
- end: `0x18000d131`
- name: `?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ`
- size: `229`
- prototype: `struct WaasMedic::TelemetryProvider *(void)`
- caller_count: `71`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cfe0`
- `0x180010240`
- `0x180015800`
- `0x18001aa34`
- `0x18001ab9c`
- `0x18001ad04`
- `0x18001ae6c`
- `0x18001afd4`
- `0x18001b110`
- `0x18001b414`
- `0x18001b730`
- `0x18001b9c0`
- `0x18001bc50`
- `0x18001bee0`
- `0x18001df78`
- `0x18002271c`
- `0x180024e60`
- `0x180024fc0`
- `0x18002555c`
- `0x180025728`
- `0x180025928`
- `0x180025ba0`
- `0x180025d60`
- `0x180025f0c`
- `0x1800262dc`
- `0x1800271a4`
- `0x18002744c`
- `0x1800277f8`
- `0x18002799c`
- `0x18002a0a0`
- `0x1800301e0`
- `0x180032854`
- `0x180032984`
- `0x180032b08`
- `0x18003300c`
- `0x180033c3c`
- `0x180033cec`
- `0x180033dc4`
- `0x180033f5c`
- `0x180034000`
- `0x1800340b0`
- `0x180034188`
- `0x180034260`
- `0x180034304`
- `0x180034658`
- `0x180034708`
- `0x1800347e0`
- `0x180034964`
- `0x180034ac4`
- `0x180034c28`

## callees

- `0x1800015b4`
- `0x180005564`
- `0x18000d04c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000d074`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000d074`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d120`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d120`

## pseudocode

```c
struct WaasMedic::TelemetryProvider *WaasMedic::TelemetryProvider::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`WaasMedic::TelemetryProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800A4FE0 = 0;
    v2 = &qword_1800A4FD8;
    qword_1800A4FD8 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1800A4FE8 = 0;
    dword_1800A4FEC = 0;
    CallbackContext = &`WaasMedic::TelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_::_lambda_invoker_cdecl_);
    qword_1800A4FE0 = (__int64)CallbackContext;
    byte_1800A4FE8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800A4FEC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A4FD8 + 8))(&qword_1800A4FD8);
    InitOnceComplete(&`WaasMedic::TelemetryProvider::Instance'::`2'::wrapper, 0, &qword_1800A4FD8);
  }
  return (struct WaasMedic::TelemetryProvider *)v2;
}

```

## disassembly

```asm
0x18000d04c  mov     rax, rsp
0x18000d04f  push    rbx
0x18000d050  sub     rsp, 20h
0x18000d054  lea     r9, [rax+10h]; lpContext
0x18000d058  mov     qword ptr [rax+10h], 0
0x18000d060  lea     r8, [rax+8]; fPending
0x18000d064  mov     dword ptr [rax+8], 0
0x18000d06b  xor     edx, edx; dwFlags
0x18000d06d  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x18000d074  call    cs:__imp_InitOnceBeginInitialize
0x18000d07a  test    eax, eax
0x18000d07c  jz      loc_18000D126
0x18000d082  cmp     [rsp+28h+arg_0], 0
0x18000d087  jz      loc_18000D126
0x18000d08d  lea     rbx, qword_1800A4FD8
0x18000d094  mov     cs:qword_1800A4FE0, 0
0x18000d09f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000d0a6  mov     [rsp+28h+arg_8], rbx
0x18000d0ab  mov     cs:qword_1800A4FD8, rax
0x18000d0b2  mov     cs:byte_1800A4FE8, 0
0x18000d0b9  mov     cs:dword_1800A4FEC, 0
0x18000d0c3  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryProvider@WaasMedic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WaasMedic::TelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000d0ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_@@CA@XZ; void (__cdecl *)()
0x18000d0d1  mov     cs:CallbackContext, rax
0x18000d0d8  call    atexit
0x18000d0dd  mov     rcx, cs:CallbackContext; CallbackContext
0x18000d0e4  mov     cs:qword_1800A4FE0, rcx
0x18000d0eb  mov     cs:byte_1800A4FE8, 1
0x18000d0f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000d0f7  mov     rax, cs:qword_1800A4FD8
0x18000d0fe  mov     rcx, rbx
0x18000d101  mov     cs:dword_1800A4FEC, 1
0x18000d10b  mov     rax, [rax+8]
0x18000d10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d114  mov     r8, rbx; lpContext
0x18000d117  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x18000d11e  xor     edx, edx; dwFlags
0x18000d120  call    cs:__imp_InitOnceComplete
0x18000d126  mov     rax, [rsp+28h+arg_8]
0x18000d12b  add     rsp, 20h
0x18000d12f  pop     rbx
0x18000d130  retn
```

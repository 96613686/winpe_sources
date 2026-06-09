# WaasMedic::TelemetryProvider::Provider(void)

- ea: `0x180016c9c`
- end: `0x180016d85`
- name: `?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `50`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c228`
- `0x180016af0`
- `0x180023900`
- `0x180024320`
- `0x180024998`
- `0x180024b40`
- `0x180024cc0`
- `0x180027644`
- `0x180027808`
- `0x180027a80`
- `0x180027c3c`
- `0x180027df8`
- `0x18002845c`
- `0x180029260`
- `0x180029500`
- `0x1800298a0`
- `0x180029a40`
- `0x18002c040`
- `0x180030d34`
- `0x180031cd0`
- `0x180031df4`
- `0x180035efc`
- `0x18003613c`
- `0x18003a4f4`
- `0x18003a650`
- `0x18003b8c0`
- `0x180040f00`
- `0x1800419d0`
- `0x180041bac`
- `0x180041d84`
- `0x180042198`
- `0x1800424a4`
- `0x180045370`
- `0x180047580`
- `0x18004ba58`
- `0x18004bc00`
- `0x18004bee0`
- `0x18004c298`
- `0x18004d5ac`
- `0x18004ec2c`
- `0x1800534f0`
- `0x180054fd0`
- `0x1800555cc`
- `0x180055c98`
- `0x180055fb8`
- `0x18005657c`
- `0x18005f37c`
- `0x18005fc80`
- `0x180060284`
- `0x180060440`

## callees

- `0x180001674`
- `0x180004098`
- `0x180016c9c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016d70`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016d70`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016cc4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016cc4`

## pseudocode

```c
const struct _tlgProvider_t *WaasMedic::TelemetryProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`WaasMedic::TelemetryProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800989A0 = 0;
    v2 = &qword_180098998;
    qword_180098998 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1800989A8 = 0;
    dword_1800989AC = 0;
    CallbackContext = &`WaasMedic::TelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_::_lambda_invoker_cdecl_);
    qword_1800989A0 = (__int64)CallbackContext;
    byte_1800989A8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800989AC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180098998 + 8))(&qword_180098998);
    InitOnceComplete(&`WaasMedic::TelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180098998);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180016c9c  mov     rax, rsp
0x180016c9f  push    rbx
0x180016ca0  sub     rsp, 20h
0x180016ca4  lea     r9, [rax+10h]; lpContext
0x180016ca8  mov     qword ptr [rax+10h], 0
0x180016cb0  lea     r8, [rax+8]; fPending
0x180016cb4  mov     dword ptr [rax+8], 0
0x180016cbb  xor     edx, edx; dwFlags
0x180016cbd  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180016cc4  call    cs:__imp_InitOnceBeginInitialize
0x180016cca  test    eax, eax
0x180016ccc  jz      loc_180016D76
0x180016cd2  cmp     [rsp+28h+arg_0], 0
0x180016cd7  jz      loc_180016D76
0x180016cdd  lea     rbx, qword_180098998
0x180016ce4  mov     cs:qword_1800989A0, 0
0x180016cef  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180016cf6  mov     [rsp+28h+arg_8], rbx
0x180016cfb  mov     cs:qword_180098998, rax
0x180016d02  mov     cs:byte_1800989A8, 0
0x180016d09  mov     cs:dword_1800989AC, 0
0x180016d13  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryProvider@WaasMedic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WaasMedic::TelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180016d1a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_@@CA@XZ; void (__cdecl *)()
0x180016d21  mov     cs:CallbackContext, rax
0x180016d28  call    atexit
0x180016d2d  mov     rcx, cs:CallbackContext; CallbackContext
0x180016d34  mov     cs:qword_1800989A0, rcx
0x180016d3b  mov     cs:byte_1800989A8, 1
0x180016d42  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180016d47  mov     rax, cs:qword_180098998
0x180016d4e  mov     rcx, rbx
0x180016d51  mov     cs:dword_1800989AC, 1
0x180016d5b  mov     rax, [rax+8]
0x180016d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d64  mov     r8, rbx; lpContext
0x180016d67  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180016d6e  xor     edx, edx; dwFlags
0x180016d70  call    cs:__imp_InitOnceComplete
0x180016d76  mov     rax, [rsp+28h+arg_8]
0x180016d7b  mov     rax, [rax+8]
0x180016d7f  add     rsp, 20h
0x180016d83  pop     rbx
0x180016d84  retn
```

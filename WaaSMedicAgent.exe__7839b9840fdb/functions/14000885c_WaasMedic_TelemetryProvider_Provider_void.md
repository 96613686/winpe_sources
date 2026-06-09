# WaasMedic::TelemetryProvider::Provider(void)

- ea: `0x14000885c`
- end: `0x140008945`
- name: `?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `13`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007ab0`
- `0x1400083b0`
- `0x140008cac`
- `0x140008f2c`
- `0x1400090b0`
- `0x14000a120`
- `0x14000a314`
- `0x14000a4f0`
- `0x14000a8f0`
- `0x14001002c`
- `0x140010f14`
- `0x140011128`
- `0x140011508`

## callees

- `0x140001858`
- `0x140002db8`
- `0x14000885c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008930`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008930`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140008884`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140008884`

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
    qword_140020680 = 0;
    v2 = &qword_140020678;
    qword_140020678 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_140020688 = 0;
    dword_14002068C = 0;
    CallbackContext = &`WaasMedic::TelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_::_lambda_invoker_cdecl_);
    qword_140020680 = (__int64)CallbackContext;
    byte_140020688 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14002068C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140020678 + 8))(&qword_140020678);
    InitOnceComplete(&`WaasMedic::TelemetryProvider::Instance'::`2'::wrapper, 0, &qword_140020678);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x14000885c  mov     rax, rsp
0x14000885f  push    rbx
0x140008860  sub     rsp, 20h
0x140008864  lea     r9, [rax+10h]; lpContext
0x140008868  mov     qword ptr [rax+10h], 0
0x140008870  lea     r8, [rax+8]; fPending
0x140008874  mov     dword ptr [rax+8], 0
0x14000887b  xor     edx, edx; dwFlags
0x14000887d  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x140008884  call    cs:__imp_InitOnceBeginInitialize
0x14000888a  test    eax, eax
0x14000888c  jz      loc_140008936
0x140008892  cmp     [rsp+28h+arg_0], 0
0x140008897  jz      loc_140008936
0x14000889d  lea     rbx, qword_140020678
0x1400088a4  mov     cs:qword_140020680, 0
0x1400088af  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1400088b6  mov     [rsp+28h+arg_8], rbx
0x1400088bb  mov     cs:qword_140020678, rax
0x1400088c2  mov     cs:byte_140020688, 0
0x1400088c9  mov     cs:dword_14002068C, 0
0x1400088d3  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryProvider@WaasMedic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WaasMedic::TelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1400088da  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_18bd56ed57d24d1704e4ffe6fb3a8271_@@CA@XZ; void (__cdecl *)()
0x1400088e1  mov     cs:CallbackContext, rax
0x1400088e8  call    atexit
0x1400088ed  mov     rcx, cs:CallbackContext; CallbackContext
0x1400088f4  mov     cs:qword_140020680, rcx
0x1400088fb  mov     cs:byte_140020688, 1
0x140008902  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140008907  mov     rax, cs:qword_140020678
0x14000890e  mov     rcx, rbx
0x140008911  mov     cs:dword_14002068C, 1
0x14000891b  mov     rax, [rax+8]
0x14000891f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008924  mov     r8, rbx; lpContext
0x140008927  lea     rcx, ?wrapper@?1??Instance@TelemetryProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x14000892e  xor     edx, edx; dwFlags
0x140008930  call    cs:__imp_InitOnceComplete
0x140008936  mov     rax, [rsp+28h+arg_8]
0x14000893b  mov     rax, [rax+8]
0x14000893f  add     rsp, 20h
0x140008943  pop     rbx
0x140008944  retn
```

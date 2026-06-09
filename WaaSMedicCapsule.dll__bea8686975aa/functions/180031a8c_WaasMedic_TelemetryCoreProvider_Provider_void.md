# WaasMedic::TelemetryCoreProvider::Provider(void)

- ea: `0x180031a8c`
- end: `0x180031b75`
- name: `?Provider@TelemetryCoreProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180031b7c`

## callees

- `0x180001674`
- `0x180004098`
- `0x180031a8c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031b60`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031b60`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031ab4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031ab4`

## pseudocode

```c
const struct _tlgProvider_t *WaasMedic::TelemetryCoreProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`WaasMedic::TelemetryCoreProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180098E10 = 0;
    v2 = &qword_180098E08;
    qword_180098E08 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180098E18 = 0;
    dword_180098E1C = 0;
    qword_180098E20 = &`WaasMedic::TelemetryCoreProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_85960587c15fd38d1f23642296588c02_::_lambda_invoker_cdecl_);
    qword_180098E10 = (__int64)qword_180098E20;
    byte_180098E18 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180098E20);
    dword_180098E1C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180098E08 + 8))(&qword_180098E08);
    InitOnceComplete(&`WaasMedic::TelemetryCoreProvider::Instance'::`2'::wrapper, 0, &qword_180098E08);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180031a8c  mov     rax, rsp
0x180031a8f  push    rbx
0x180031a90  sub     rsp, 20h
0x180031a94  lea     r9, [rax+10h]; lpContext
0x180031a98  mov     qword ptr [rax+10h], 0
0x180031aa0  lea     r8, [rax+8]; fPending
0x180031aa4  mov     dword ptr [rax+8], 0
0x180031aab  xor     edx, edx; dwFlags
0x180031aad  lea     rcx, ?wrapper@?1??Instance@TelemetryCoreProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryCoreProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180031ab4  call    cs:__imp_InitOnceBeginInitialize
0x180031aba  test    eax, eax
0x180031abc  jz      loc_180031B66
0x180031ac2  cmp     [rsp+28h+arg_0], 0
0x180031ac7  jz      loc_180031B66
0x180031acd  lea     rbx, qword_180098E08
0x180031ad4  mov     cs:qword_180098E10, 0
0x180031adf  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180031ae6  mov     [rsp+28h+arg_8], rbx
0x180031aeb  mov     cs:qword_180098E08, rax
0x180031af2  mov     cs:byte_180098E18, 0
0x180031af9  mov     cs:dword_180098E1C, 0
0x180031b03  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryCoreProvider@WaasMedic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WaasMedic::TelemetryCoreProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180031b0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_85960587c15fd38d1f23642296588c02_@@CA@XZ; void (__cdecl *)()
0x180031b11  mov     cs:qword_180098E20, rax
0x180031b18  call    atexit
0x180031b1d  mov     rcx, cs:qword_180098E20; CallbackContext
0x180031b24  mov     cs:qword_180098E10, rcx
0x180031b2b  mov     cs:byte_180098E18, 1
0x180031b32  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180031b37  mov     rax, cs:qword_180098E08
0x180031b3e  mov     rcx, rbx
0x180031b41  mov     cs:dword_180098E1C, 1
0x180031b4b  mov     rax, [rax+8]
0x180031b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b54  mov     r8, rbx; lpContext
0x180031b57  lea     rcx, ?wrapper@?1??Instance@TelemetryCoreProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryCoreProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180031b5e  xor     edx, edx; dwFlags
0x180031b60  call    cs:__imp_InitOnceComplete
0x180031b66  mov     rax, [rsp+28h+arg_8]
0x180031b6b  mov     rax, [rax+8]
0x180031b6f  add     rsp, 20h
0x180031b73  pop     rbx
0x180031b74  retn
```

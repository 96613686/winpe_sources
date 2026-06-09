# WaasMedic::TelemetryCoreProvider::Provider(void)

- ea: `0x180033b4c`
- end: `0x180033c35`
- name: `?Provider@TelemetryCoreProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800343a8`
- `0x18003450c`
- `0x180035140`

## callees

- `0x1800015b4`
- `0x180005564`
- `0x180033b4c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180033b74`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180033b74`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180033c20`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180033c20`

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
    qword_1800A55E8 = 0;
    v2 = &qword_1800A55E0;
    qword_1800A55E0 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1800A55F0 = 0;
    dword_1800A55F4 = 0;
    qword_1800A55F8 = &`WaasMedic::TelemetryCoreProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_85960587c15fd38d1f23642296588c02_::_lambda_invoker_cdecl_);
    qword_1800A55E8 = (__int64)qword_1800A55F8;
    byte_1800A55F0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800A55F8);
    dword_1800A55F4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A55E0 + 8))(&qword_1800A55E0);
    InitOnceComplete(&`WaasMedic::TelemetryCoreProvider::Instance'::`2'::wrapper, 0, &qword_1800A55E0);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180033b4c  mov     rax, rsp
0x180033b4f  push    rbx
0x180033b50  sub     rsp, 20h
0x180033b54  lea     r9, [rax+10h]; lpContext
0x180033b58  mov     qword ptr [rax+10h], 0
0x180033b60  lea     r8, [rax+8]; fPending
0x180033b64  mov     dword ptr [rax+8], 0
0x180033b6b  xor     edx, edx; dwFlags
0x180033b6d  lea     rcx, ?wrapper@?1??Instance@TelemetryCoreProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryCoreProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180033b74  call    cs:__imp_InitOnceBeginInitialize
0x180033b7a  test    eax, eax
0x180033b7c  jz      loc_180033C26
0x180033b82  cmp     [rsp+28h+arg_0], 0
0x180033b87  jz      loc_180033C26
0x180033b8d  lea     rbx, qword_1800A55E0
0x180033b94  mov     cs:qword_1800A55E8, 0
0x180033b9f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180033ba6  mov     [rsp+28h+arg_8], rbx
0x180033bab  mov     cs:qword_1800A55E0, rax
0x180033bb2  mov     cs:byte_1800A55F0, 0
0x180033bb9  mov     cs:dword_1800A55F4, 0
0x180033bc3  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryCoreProvider@WaasMedic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WaasMedic::TelemetryCoreProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180033bca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_85960587c15fd38d1f23642296588c02_@@CA@XZ; void (__cdecl *)()
0x180033bd1  mov     cs:qword_1800A55F8, rax
0x180033bd8  call    atexit
0x180033bdd  mov     rcx, cs:qword_1800A55F8; CallbackContext
0x180033be4  mov     cs:qword_1800A55E8, rcx
0x180033beb  mov     cs:byte_1800A55F0, 1
0x180033bf2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180033bf7  mov     rax, cs:qword_1800A55E0
0x180033bfe  mov     rcx, rbx
0x180033c01  mov     cs:dword_1800A55F4, 1
0x180033c0b  mov     rax, [rax+8]
0x180033c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c14  mov     r8, rbx; lpContext
0x180033c17  lea     rcx, ?wrapper@?1??Instance@TelemetryCoreProvider@WaasMedic@@KAPEAV23@XZ@4V?$static_lazy@VTelemetryCoreProvider@WaasMedic@@@details@wil@@A; lpInitOnce
0x180033c1e  xor     edx, edx; dwFlags
0x180033c20  call    cs:__imp_InitOnceComplete
0x180033c26  mov     rax, [rsp+28h+arg_8]
0x180033c2b  mov     rax, [rax+8]
0x180033c2f  add     rsp, 20h
0x180033c33  pop     rbx
0x180033c34  retn
```

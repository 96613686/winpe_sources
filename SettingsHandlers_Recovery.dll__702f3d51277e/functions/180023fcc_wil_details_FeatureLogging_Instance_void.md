# wil::details::FeatureLogging::Instance(void)

- ea: `0x180023fcc`
- end: `0x1800240b1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023ae0`

## callees

- `0x1800015b4`
- `0x180002800`
- `0x180023fcc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800240a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800240a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180023ff4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180023ff4`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_18005A088 = 0;
    v2 = &qword_18005A080;
    qword_18005A080 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_18005A090 = 0;
    dword_18005A094 = 0;
    qword_18005A098 = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_18005A088 = (__int64)qword_18005A098;
    byte_18005A090 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_18005A098);
    dword_18005A094 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18005A080 + 8))(&qword_18005A080);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_18005A080);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x180023fcc  mov     rax, rsp
0x180023fcf  push    rbx
0x180023fd0  sub     rsp, 20h
0x180023fd4  lea     r9, [rax+10h]; lpContext
0x180023fd8  mov     qword ptr [rax+10h], 0
0x180023fe0  lea     r8, [rax+8]; fPending
0x180023fe4  mov     dword ptr [rax+8], 0
0x180023feb  xor     edx, edx; dwFlags
0x180023fed  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180023ff4  call    cs:__imp_InitOnceBeginInitialize
0x180023ffa  test    eax, eax
0x180023ffc  jz      loc_1800240A6
0x180024002  cmp     [rsp+28h+arg_0], 0
0x180024007  jz      loc_1800240A6
0x18002400d  lea     rbx, qword_18005A080
0x180024014  mov     cs:qword_18005A088, 0
0x18002401f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180024026  mov     [rsp+28h+arg_8], rbx
0x18002402b  mov     cs:qword_18005A080, rax
0x180024032  mov     cs:byte_18005A090, 0
0x180024039  mov     cs:dword_18005A094, 0
0x180024043  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002404a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180024051  mov     cs:qword_18005A098, rax
0x180024058  call    atexit
0x18002405d  mov     rcx, cs:qword_18005A098; CallbackContext
0x180024064  mov     cs:qword_18005A088, rcx
0x18002406b  mov     cs:byte_18005A090, 1
0x180024072  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180024077  mov     rax, cs:qword_18005A080
0x18002407e  mov     rcx, rbx
0x180024081  mov     cs:dword_18005A094, 1
0x18002408b  mov     rax, [rax+8]
0x18002408f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024094  mov     r8, rbx; lpContext
0x180024097  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18002409e  xor     edx, edx; dwFlags
0x1800240a0  call    cs:__imp_InitOnceComplete
0x1800240a6  mov     rax, [rsp+28h+arg_8]
0x1800240ab  add     rsp, 20h
0x1800240af  pop     rbx
0x1800240b0  retn
```

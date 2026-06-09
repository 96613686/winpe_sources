# wil::details::FeatureLogging::Instance(void)

- ea: `0x14000a98c`
- end: `0x14000aa71`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009bf0`

## callees

- `0x140001008`
- `0x1400026b4`
- `0x14000a98c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000a9b4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000a9b4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000aa60`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000aa60`

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
    qword_14001A698 = 0;
    v2 = &qword_14001A690;
    qword_14001A690 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_14001A6A0 = 0;
    dword_14001A6A4 = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_14001A698 = (__int64)CallbackContext;
    byte_14001A6A0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14001A6A4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14001A690 + 8))(&qword_14001A690);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_14001A690);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x14000a98c  mov     rax, rsp
0x14000a98f  push    rbx
0x14000a990  sub     rsp, 20h
0x14000a994  lea     r9, [rax+10h]; lpContext
0x14000a998  mov     qword ptr [rax+10h], 0
0x14000a9a0  lea     r8, [rax+8]; fPending
0x14000a9a4  mov     dword ptr [rax+8], 0
0x14000a9ab  xor     edx, edx; dwFlags
0x14000a9ad  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000a9b4  call    cs:__imp_InitOnceBeginInitialize
0x14000a9ba  test    eax, eax
0x14000a9bc  jz      loc_14000AA66
0x14000a9c2  cmp     [rsp+28h+arg_0], 0
0x14000a9c7  jz      loc_14000AA66
0x14000a9cd  lea     rbx, qword_14001A690
0x14000a9d4  mov     cs:qword_14001A698, 0
0x14000a9df  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x14000a9e6  mov     [rsp+28h+arg_8], rbx
0x14000a9eb  mov     cs:qword_14001A690, rax
0x14000a9f2  mov     cs:byte_14001A6A0, 0
0x14000a9f9  mov     cs:dword_14001A6A4, 0
0x14000aa03  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000aa0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x14000aa11  mov     cs:CallbackContext, rax
0x14000aa18  call    atexit
0x14000aa1d  mov     rcx, cs:CallbackContext; CallbackContext
0x14000aa24  mov     cs:qword_14001A698, rcx
0x14000aa2b  mov     cs:byte_14001A6A0, 1
0x14000aa32  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000aa37  mov     rax, cs:qword_14001A690
0x14000aa3e  mov     rcx, rbx
0x14000aa41  mov     cs:dword_14001A6A4, 1
0x14000aa4b  mov     rax, [rax+8]
0x14000aa4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa54  mov     r8, rbx; lpContext
0x14000aa57  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000aa5e  xor     edx, edx; dwFlags
0x14000aa60  call    cs:__imp_InitOnceComplete
0x14000aa66  mov     rax, [rsp+28h+arg_8]
0x14000aa6b  add     rsp, 20h
0x14000aa6f  pop     rbx
0x14000aa70  retn
```

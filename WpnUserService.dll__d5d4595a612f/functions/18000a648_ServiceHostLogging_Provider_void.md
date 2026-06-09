# ServiceHostLogging::Provider(void)

- ea: `0x18000a648`
- end: `0x18000a701`
- name: `?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `25`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007e58`
- `0x180007efc`
- `0x180007f84`
- `0x180008f20`
- `0x180009da8`
- `0x18000b740`
- `0x18000bf30`
- `0x18000cad4`
- `0x18000d564`
- `0x18000d600`
- `0x18000d69c`
- `0x18000d73c`
- `0x18000d7e0`
- `0x18000d884`
- `0x18000dd54`
- `0x18000e590`
- `0x18000e9e8`
- `0x18000edbc`
- `0x18000f094`
- `0x18000f28c`
- `0x18000f4b0`
- `0x18000f628`
- `0x18000f908`
- `0x18000fbf0`
- `0x18000fee0`

## callees

- `0x180002f70`
- `0x18000a648`
- `0x18000b644`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a6ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a6ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a670`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a670`

## pseudocode

```c
const struct _tlgProvider_t *ServiceHostLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`ServiceHostLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_1800196A8 = 0;
    v3 = &qword_1800196A0;
    qword_1800196A0 = &wil::details::FeatureLogging::`vftable';
    byte_1800196B0 = 0;
    dword_1800196B4 = 0;
    qword_1800196B8 = (struct _tlgProvider_t *)&`ServiceHostLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_db56a68df751983d7f0fbf9c68f94613_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800196A0, qword_1800196B8, v0);
    InitOnceComplete(&`ServiceHostLogging::Instance'::`2'::wrapper, 0, &qword_1800196A0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000a648  mov     rax, rsp
0x18000a64b  push    rbx
0x18000a64c  sub     rsp, 20h
0x18000a650  lea     r9, [rax+10h]; lpContext
0x18000a654  mov     qword ptr [rax+10h], 0
0x18000a65c  lea     r8, [rax+8]; fPending
0x18000a660  mov     dword ptr [rax+8], 0
0x18000a667  xor     edx, edx; dwFlags
0x18000a669  lea     rcx, ?wrapper@?1??Instance@ServiceHostLogging@@KAPEAV2@XZ@4V?$static_lazy@VServiceHostLogging@@@details@wil@@A; lpInitOnce
0x18000a670  call    cs:__imp_InitOnceBeginInitialize
0x18000a676  test    eax, eax
0x18000a678  jz      short loc_18000A6F2
0x18000a67a  cmp     [rsp+28h+arg_0], 0
0x18000a67f  jz      short loc_18000A6F2
0x18000a681  lea     rbx, qword_1800196A0
0x18000a688  mov     cs:qword_1800196A8, 0
0x18000a693  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000a69a  mov     [rsp+28h+arg_8], rbx
0x18000a69f  mov     cs:qword_1800196A0, rax
0x18000a6a6  mov     cs:byte_1800196B0, 0
0x18000a6ad  mov     cs:dword_1800196B4, 0
0x18000a6b7  lea     rax, ?__hInner@?1???0StaticHandle@ServiceHostLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ServiceHostLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a6be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_db56a68df751983d7f0fbf9c68f94613_@@CA@XZ; void (__cdecl *)()
0x18000a6c5  mov     cs:qword_1800196B8, rax
0x18000a6cc  call    atexit
0x18000a6d1  mov     rdx, cs:qword_1800196B8; struct _tlgProvider_t *
0x18000a6d8  mov     rcx, rbx; this
0x18000a6db  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000a6e0  mov     r8, rbx; lpContext
0x18000a6e3  lea     rcx, ?wrapper@?1??Instance@ServiceHostLogging@@KAPEAV2@XZ@4V?$static_lazy@VServiceHostLogging@@@details@wil@@A; lpInitOnce
0x18000a6ea  xor     edx, edx; dwFlags
0x18000a6ec  call    cs:__imp_InitOnceComplete
0x18000a6f2  mov     rax, [rsp+28h+arg_8]
0x18000a6f7  mov     rax, [rax+8]
0x18000a6fb  add     rsp, 20h
0x18000a6ff  pop     rbx
0x18000a700  retn
```

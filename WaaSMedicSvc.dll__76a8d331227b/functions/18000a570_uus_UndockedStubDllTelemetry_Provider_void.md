# uus::UndockedStubDllTelemetry::Provider(void)

- ea: `0x18000a570`
- end: `0x18000a622`
- name: `?Provider@UndockedStubDllTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a168`
- `0x18000a41c`

## callees

- `0x1800025b0`
- `0x180009010`
- `0x18000a570`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a59b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a59b`

## pseudocode

```c
const struct _tlgProvider_t *uus::UndockedStubDllTelemetry::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`uus::UndockedStubDllTelemetry::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`uus::UndockedStubDllTelemetry::Instance'::`2'::wrapper;
    v4 = &qword_1800135F0;
    qword_1800135F0 = (__int64)&uus::UndockedStubDllTelemetry::`vftable';
    qword_1800135F8 = 0;
    byte_180013600 = 0;
    dword_180013604 = 0;
    qword_180013608 = (__int64)&`uus::UndockedStubDllTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_a86caec4c2c7b81cf4d5633114d3a3c9_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<uus::UndockedStubDllTelemetry>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x18000a570  mov     rax, rsp
0x18000a573  push    rdi
0x18000a574  sub     rsp, 30h
0x18000a578  lea     rdi, ?wrapper@?1??Instance@UndockedStubDllTelemetry@uus@@KAPEAV23@XZ@4V?$static_lazy@VUndockedStubDllTelemetry@uus@@@details@wil@@A; wil::details::static_lazy<uus::UndockedStubDllTelemetry> `uus::UndockedStubDllTelemetry::Instance(void)'::`2'::wrapper
0x18000a57f  mov     qword ptr [rax+10h], 0
0x18000a587  mov     rcx, rdi; lpInitOnce
0x18000a58a  mov     dword ptr [rax+8], 0
0x18000a591  lea     r9, [rax+10h]; lpContext
0x18000a595  xor     edx, edx; dwFlags
0x18000a597  lea     r8, [rax+8]; fPending
0x18000a59b  call    cs:__imp_InitOnceBeginInitialize
0x18000a5a1  test    eax, eax
0x18000a5a3  jz      short loc_18000A613
0x18000a5a5  cmp     [rsp+38h+arg_0], 0
0x18000a5aa  jz      short loc_18000A613
0x18000a5ac  lea     rax, qword_1800135F0
0x18000a5b3  mov     [rsp+38h+var_18], rdi
0x18000a5b8  mov     [rsp+38h+arg_8], rax
0x18000a5bd  lea     rax, ??_7UndockedStubDllTelemetry@uus@@6B@; const uus::UndockedStubDllTelemetry::`vftable'
0x18000a5c4  mov     cs:qword_1800135F0, rax
0x18000a5cb  mov     cs:qword_1800135F8, 0
0x18000a5d6  mov     cs:byte_180013600, 0
0x18000a5dd  mov     cs:dword_180013604, 0
0x18000a5e7  lea     rax, ?__hInner@?1???0StaticHandle@UndockedStubDllTelemetry@uus@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `uus::UndockedStubDllTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a5ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a86caec4c2c7b81cf4d5633114d3a3c9_@@CA@XZ; void (__cdecl *)()
0x18000a5f5  mov     cs:qword_180013608, rax
0x18000a5fc  call    atexit
0x18000a601  lea     rcx, [rsp+38h+var_18]
0x18000a606  mov     [rsp+38h+var_10], 0
0x18000a60e  call    ??1Completer@?$static_lazy@VUndockedStubDllTelemetry@uus@@@details@wil@@QEAA@XZ; wil::details::static_lazy<uus::UndockedStubDllTelemetry>::Completer::~Completer(void)
0x18000a613  mov     rax, [rsp+38h+arg_8]
0x18000a618  mov     rax, [rax+8]
0x18000a61c  add     rsp, 30h
0x18000a620  pop     rdi
0x18000a621  retn
```

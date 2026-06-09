# MidiBS2UMPTransformTelemetryProvider::Instance(void)

- ea: `0x180009528`
- end: `0x1800095d6`
- name: `?Instance@MidiBS2UMPTransformTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct MidiBS2UMPTransformTelemetryProvider *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800093f0`
- `0x180009fb0`
- `0x18000a840`
- `0x18000a980`
- `0x18000ac60`

## callees

- `0x180002280`
- `0x180008c4c`
- `0x180009528`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009553`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009553`

## pseudocode

```c
struct MidiBS2UMPTransformTelemetryProvider *MidiBS2UMPTransformTelemetryProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`MidiBS2UMPTransformTelemetryProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`MidiBS2UMPTransformTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_1800125A8;
    qword_1800125A8 = (__int64)&MidiBS2UMPTransformTelemetryProvider::`vftable';
    qword_1800125B0 = 0;
    byte_1800125B8 = 0;
    dword_1800125BC = 0;
    qword_1800125C0 = (__int64)&`MidiBS2UMPTransformTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiBS2UMPTransformTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MidiBS2UMPTransformTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct MidiBS2UMPTransformTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x180009528  mov     rax, rsp
0x18000952b  push    rdi
0x18000952c  sub     rsp, 30h
0x180009530  lea     rdi, ?wrapper@?1??Instance@MidiBS2UMPTransformTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiBS2UMPTransformTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<MidiBS2UMPTransformTelemetryProvider> `MidiBS2UMPTransformTelemetryProvider::Instance(void)'::`2'::wrapper
0x180009537  mov     qword ptr [rax+10h], 0
0x18000953f  mov     rcx, rdi; lpInitOnce
0x180009542  mov     dword ptr [rax+8], 0
0x180009549  lea     r9, [rax+10h]; lpContext
0x18000954d  xor     edx, edx; dwFlags
0x18000954f  lea     r8, [rax+8]; fPending
0x180009553  call    cs:__imp_InitOnceBeginInitialize
0x180009559  test    eax, eax
0x18000955b  jz      short loc_1800095CB
0x18000955d  cmp     [rsp+38h+arg_0], 0
0x180009562  jz      short loc_1800095CB
0x180009564  lea     rax, qword_1800125A8
0x18000956b  mov     [rsp+38h+var_18], rdi
0x180009570  mov     [rsp+38h+arg_8], rax
0x180009575  lea     rax, ??_7MidiBS2UMPTransformTelemetryProvider@@6B@; const MidiBS2UMPTransformTelemetryProvider::`vftable'
0x18000957c  mov     cs:qword_1800125A8, rax
0x180009583  mov     cs:qword_1800125B0, 0
0x18000958e  mov     cs:byte_1800125B8, 0
0x180009595  mov     cs:dword_1800125BC, 0
0x18000959f  lea     rax, ?__hInner@?1???0StaticHandle@MidiBS2UMPTransformTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiBS2UMPTransformTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800095a6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiBS2UMPTransformTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x1800095ad  mov     cs:qword_1800125C0, rax
0x1800095b4  call    atexit
0x1800095b9  lea     rcx, [rsp+38h+var_18]
0x1800095be  mov     [rsp+38h+var_10], 0
0x1800095c6  call    ??1Completer@?$static_lazy@VMidiBS2UMPTransformTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MidiBS2UMPTransformTelemetryProvider>::Completer::~Completer(void)
0x1800095cb  mov     rax, [rsp+38h+arg_8]
0x1800095d0  add     rsp, 30h
0x1800095d4  pop     rdi
0x1800095d5  retn
```

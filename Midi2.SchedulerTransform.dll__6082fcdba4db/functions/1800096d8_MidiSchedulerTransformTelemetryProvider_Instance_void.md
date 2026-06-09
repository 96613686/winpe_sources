# MidiSchedulerTransformTelemetryProvider::Instance(void)

- ea: `0x1800096d8`
- end: `0x180009786`
- name: `?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct MidiSchedulerTransformTelemetryProvider *(void)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800095a0`
- `0x18000abe0`
- `0x18000af80`
- `0x18000b540`
- `0x18000b964`
- `0x18000ba70`
- `0x18000c780`
- `0x18000cf13`
- `0x18000cfbc`
- `0x18000d09b`
- `0x18000d16e`
- `0x18000d20c`
- `0x18000d2b5`

## callees

- `0x180002420`
- `0x180008dfc`
- `0x1800096d8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009703`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009703`

## pseudocode

```c
struct MidiSchedulerTransformTelemetryProvider *MidiSchedulerTransformTelemetryProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(
         &`MidiSchedulerTransformTelemetryProvider::Instance'::`2'::wrapper,
         0,
         &v3,
         (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`MidiSchedulerTransformTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_1800155A8;
    qword_1800155A8 = (__int64)&MidiSchedulerTransformTelemetryProvider::`vftable';
    qword_1800155B0 = 0;
    byte_1800155B8 = 0;
    dword_1800155BC = 0;
    qword_1800155C0 = (__int64)&`MidiSchedulerTransformTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiSchedulerTransformTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MidiSchedulerTransformTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct MidiSchedulerTransformTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x1800096d8  mov     rax, rsp
0x1800096db  push    rdi
0x1800096dc  sub     rsp, 30h
0x1800096e0  lea     rdi, ?wrapper@?1??Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiSchedulerTransformTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<MidiSchedulerTransformTelemetryProvider> `MidiSchedulerTransformTelemetryProvider::Instance(void)'::`2'::wrapper
0x1800096e7  mov     qword ptr [rax+10h], 0
0x1800096ef  mov     rcx, rdi; lpInitOnce
0x1800096f2  mov     dword ptr [rax+8], 0
0x1800096f9  lea     r9, [rax+10h]; lpContext
0x1800096fd  xor     edx, edx; dwFlags
0x1800096ff  lea     r8, [rax+8]; fPending
0x180009703  call    cs:__imp_InitOnceBeginInitialize
0x180009709  test    eax, eax
0x18000970b  jz      short loc_18000977B
0x18000970d  cmp     [rsp+38h+arg_0], 0
0x180009712  jz      short loc_18000977B
0x180009714  lea     rax, qword_1800155A8
0x18000971b  mov     [rsp+38h+var_18], rdi
0x180009720  mov     [rsp+38h+arg_8], rax
0x180009725  lea     rax, ??_7MidiSchedulerTransformTelemetryProvider@@6B@; const MidiSchedulerTransformTelemetryProvider::`vftable'
0x18000972c  mov     cs:qword_1800155A8, rax
0x180009733  mov     cs:qword_1800155B0, 0
0x18000973e  mov     cs:byte_1800155B8, 0
0x180009745  mov     cs:dword_1800155BC, 0
0x18000974f  lea     rax, ?__hInner@?1???0StaticHandle@MidiSchedulerTransformTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiSchedulerTransformTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009756  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000975d  mov     cs:qword_1800155C0, rax
0x180009764  call    atexit
0x180009769  lea     rcx, [rsp+38h+var_18]
0x18000976e  mov     [rsp+38h+var_10], 0
0x180009776  call    ??1Completer@?$static_lazy@VMidiSchedulerTransformTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MidiSchedulerTransformTelemetryProvider>::Completer::~Completer(void)
0x18000977b  mov     rax, [rsp+38h+arg_8]
0x180009780  add     rsp, 30h
0x180009784  pop     rdi
0x180009785  retn
```

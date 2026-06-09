# MidiUMP2BSTransformTelemetryProvider::Instance(void)

- ea: `0x1800095b8`
- end: `0x180009666`
- name: `?Instance@MidiUMP2BSTransformTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct MidiUMP2BSTransformTelemetryProvider *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009480`
- `0x18000a040`
- `0x18000c2c0`
- `0x18000caf0`
- `0x18000d200`

## callees

- `0x180002310`
- `0x180008cdc`
- `0x1800095b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800095e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800095e3`

## pseudocode

```c
struct MidiUMP2BSTransformTelemetryProvider *MidiUMP2BSTransformTelemetryProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`MidiUMP2BSTransformTelemetryProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`MidiUMP2BSTransformTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_180015648;
    qword_180015648 = (__int64)&MidiUMP2BSTransformTelemetryProvider::`vftable';
    qword_180015650 = 0;
    byte_180015658 = 0;
    dword_18001565C = 0;
    qword_180015660 = (__int64)&`MidiUMP2BSTransformTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiUMP2BSTransformTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MidiUMP2BSTransformTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct MidiUMP2BSTransformTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x1800095b8  mov     rax, rsp
0x1800095bb  push    rdi
0x1800095bc  sub     rsp, 30h
0x1800095c0  lea     rdi, ?wrapper@?1??Instance@MidiUMP2BSTransformTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiUMP2BSTransformTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<MidiUMP2BSTransformTelemetryProvider> `MidiUMP2BSTransformTelemetryProvider::Instance(void)'::`2'::wrapper
0x1800095c7  mov     qword ptr [rax+10h], 0
0x1800095cf  mov     rcx, rdi; lpInitOnce
0x1800095d2  mov     dword ptr [rax+8], 0
0x1800095d9  lea     r9, [rax+10h]; lpContext
0x1800095dd  xor     edx, edx; dwFlags
0x1800095df  lea     r8, [rax+8]; fPending
0x1800095e3  call    cs:__imp_InitOnceBeginInitialize
0x1800095e9  test    eax, eax
0x1800095eb  jz      short loc_18000965B
0x1800095ed  cmp     [rsp+38h+arg_0], 0
0x1800095f2  jz      short loc_18000965B
0x1800095f4  lea     rax, qword_180015648
0x1800095fb  mov     [rsp+38h+var_18], rdi
0x180009600  mov     [rsp+38h+arg_8], rax
0x180009605  lea     rax, ??_7MidiUMP2BSTransformTelemetryProvider@@6B@; const MidiUMP2BSTransformTelemetryProvider::`vftable'
0x18000960c  mov     cs:qword_180015648, rax
0x180009613  mov     cs:qword_180015650, 0
0x18000961e  mov     cs:byte_180015658, 0
0x180009625  mov     cs:dword_18001565C, 0
0x18000962f  lea     rax, ?__hInner@?1???0StaticHandle@MidiUMP2BSTransformTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiUMP2BSTransformTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009636  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiUMP2BSTransformTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000963d  mov     cs:qword_180015660, rax
0x180009644  call    atexit
0x180009649  lea     rcx, [rsp+38h+var_18]
0x18000964e  mov     [rsp+38h+var_10], 0
0x180009656  call    ??1Completer@?$static_lazy@VMidiUMP2BSTransformTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MidiUMP2BSTransformTelemetryProvider>::Completer::~Completer(void)
0x18000965b  mov     rax, [rsp+38h+arg_8]
0x180009660  add     rsp, 30h
0x180009664  pop     rdi
0x180009665  retn
```

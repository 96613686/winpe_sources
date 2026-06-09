# MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)

- ea: `0x18000a798`
- end: `0x18000a846`
- name: `?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct MidiUmpProtocolDownscalerTransformTelemetryProvider *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a660`
- `0x18000d940`
- `0x18000e950`
- `0x18000fac0`
- `0x180010900`

## callees

- `0x180003360`
- `0x180009ebc`
- `0x18000a798`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a7c3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a7c3`

## pseudocode

```c
struct MidiUmpProtocolDownscalerTransformTelemetryProvider *MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(
        void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(
         &`MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance'::`2'::wrapper,
         0,
         &v3,
         (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_18001B9E8;
    qword_18001B9E8 = (__int64)&MidiUmpProtocolDownscalerTransformTelemetryProvider::`vftable';
    qword_18001B9F0 = 0;
    byte_18001B9F8 = 0;
    dword_18001B9FC = 0;
    qword_18001BA00 = (__int64)&`MidiUmpProtocolDownscalerTransformTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MidiUmpProtocolDownscalerTransformTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct MidiUmpProtocolDownscalerTransformTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x18000a798  mov     rax, rsp
0x18000a79b  push    rdi
0x18000a79c  sub     rsp, 30h
0x18000a7a0  lea     rdi, ?wrapper@?1??Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiUmpProtocolDownscalerTransformTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<MidiUmpProtocolDownscalerTransformTelemetryProvider> `MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)'::`2'::wrapper
0x18000a7a7  mov     qword ptr [rax+10h], 0
0x18000a7af  mov     rcx, rdi; lpInitOnce
0x18000a7b2  mov     dword ptr [rax+8], 0
0x18000a7b9  lea     r9, [rax+10h]; lpContext
0x18000a7bd  xor     edx, edx; dwFlags
0x18000a7bf  lea     r8, [rax+8]; fPending
0x18000a7c3  call    cs:__imp_InitOnceBeginInitialize
0x18000a7c9  test    eax, eax
0x18000a7cb  jz      short loc_18000A83B
0x18000a7cd  cmp     [rsp+38h+arg_0], 0
0x18000a7d2  jz      short loc_18000A83B
0x18000a7d4  lea     rax, qword_18001B9E8
0x18000a7db  mov     [rsp+38h+var_18], rdi
0x18000a7e0  mov     [rsp+38h+arg_8], rax
0x18000a7e5  lea     rax, ??_7MidiUmpProtocolDownscalerTransformTelemetryProvider@@6B@; const MidiUmpProtocolDownscalerTransformTelemetryProvider::`vftable'
0x18000a7ec  mov     cs:qword_18001B9E8, rax
0x18000a7f3  mov     cs:qword_18001B9F0, 0
0x18000a7fe  mov     cs:byte_18001B9F8, 0
0x18000a805  mov     cs:dword_18001B9FC, 0
0x18000a80f  lea     rax, ?__hInner@?1???0StaticHandle@MidiUmpProtocolDownscalerTransformTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiUmpProtocolDownscalerTransformTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a816  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000a81d  mov     cs:qword_18001BA00, rax
0x18000a824  call    atexit
0x18000a829  lea     rcx, [rsp+38h+var_18]
0x18000a82e  mov     [rsp+38h+var_10], 0
0x18000a836  call    ??1Completer@?$static_lazy@VMidiUmpProtocolDownscalerTransformTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MidiUmpProtocolDownscalerTransformTelemetryProvider>::Completer::~Completer(void)
0x18000a83b  mov     rax, [rsp+38h+arg_8]
0x18000a840  add     rsp, 30h
0x18000a844  pop     rdi
0x18000a845  retn
```

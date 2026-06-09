# MidiDiagnosticsTransportTelemetryProvider::Instance(void)

- ea: `0x18000add8`
- end: `0x18000ae86`
- name: `?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct MidiDiagnosticsTransportTelemetryProvider *(void)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000aca0`
- `0x18000b9f0`
- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f4f0`
- `0x18000fec0`
- `0x180010a90`
- `0x180010b70`
- `0x1800110f0`
- `0x1800112d0`
- `0x1800113b0`
- `0x180011430`

## callees

- `0x1800037f0`
- `0x18000a4fc`
- `0x18000add8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ae03`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ae03`

## pseudocode

```c
struct MidiDiagnosticsTransportTelemetryProvider *MidiDiagnosticsTransportTelemetryProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(
         &`MidiDiagnosticsTransportTelemetryProvider::Instance'::`2'::wrapper,
         0,
         &v3,
         (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`MidiDiagnosticsTransportTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_18001A678;
    qword_18001A678 = (__int64)&MidiDiagnosticsTransportTelemetryProvider::`vftable';
    qword_18001A680 = 0;
    byte_18001A688 = 0;
    dword_18001A68C = 0;
    qword_18001A690 = (__int64)&`MidiDiagnosticsTransportTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiDiagnosticsTransportTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MidiDiagnosticsTransportTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct MidiDiagnosticsTransportTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x18000add8  mov     rax, rsp
0x18000addb  push    rdi
0x18000addc  sub     rsp, 30h
0x18000ade0  lea     rdi, ?wrapper@?1??Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiDiagnosticsTransportTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<MidiDiagnosticsTransportTelemetryProvider> `MidiDiagnosticsTransportTelemetryProvider::Instance(void)'::`2'::wrapper
0x18000ade7  mov     qword ptr [rax+10h], 0
0x18000adef  mov     rcx, rdi; lpInitOnce
0x18000adf2  mov     dword ptr [rax+8], 0
0x18000adf9  lea     r9, [rax+10h]; lpContext
0x18000adfd  xor     edx, edx; dwFlags
0x18000adff  lea     r8, [rax+8]; fPending
0x18000ae03  call    cs:__imp_InitOnceBeginInitialize
0x18000ae09  test    eax, eax
0x18000ae0b  jz      short loc_18000AE7B
0x18000ae0d  cmp     [rsp+38h+arg_0], 0
0x18000ae12  jz      short loc_18000AE7B
0x18000ae14  lea     rax, qword_18001A678
0x18000ae1b  mov     [rsp+38h+var_18], rdi
0x18000ae20  mov     [rsp+38h+arg_8], rax
0x18000ae25  lea     rax, ??_7MidiDiagnosticsTransportTelemetryProvider@@6B@; const MidiDiagnosticsTransportTelemetryProvider::`vftable'
0x18000ae2c  mov     cs:qword_18001A678, rax
0x18000ae33  mov     cs:qword_18001A680, 0
0x18000ae3e  mov     cs:byte_18001A688, 0
0x18000ae45  mov     cs:dword_18001A68C, 0
0x18000ae4f  lea     rax, ?__hInner@?1???0StaticHandle@MidiDiagnosticsTransportTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiDiagnosticsTransportTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ae56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000ae5d  mov     cs:qword_18001A690, rax
0x18000ae64  call    atexit
0x18000ae69  lea     rcx, [rsp+38h+var_18]
0x18000ae6e  mov     [rsp+38h+var_10], 0
0x18000ae76  call    ??1Completer@?$static_lazy@VMidiDiagnosticsTransportTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MidiDiagnosticsTransportTelemetryProvider>::Completer::~Completer(void)
0x18000ae7b  mov     rax, [rsp+38h+arg_8]
0x18000ae80  add     rsp, 30h
0x18000ae84  pop     rdi
0x18000ae85  retn
```

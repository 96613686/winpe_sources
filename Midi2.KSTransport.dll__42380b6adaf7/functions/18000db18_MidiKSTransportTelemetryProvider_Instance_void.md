# MidiKSTransportTelemetryProvider::Instance(void)

- ea: `0x18000db18`
- end: `0x18000dbcd`
- name: `?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct MidiKSTransportTelemetryProvider *(void)`
- caller_count: `22`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d9e0`
- `0x18000e6f0`
- `0x1800124c8`
- `0x180014550`
- `0x180015810`
- `0x180015a40`
- `0x180015b00`
- `0x180015d40`
- `0x180015e00`
- `0x180016030`
- `0x180018884`
- `0x180018af8`
- `0x18001ad40`
- `0x18001b7a0`
- `0x18001e630`
- `0x18001f460`
- `0x180022690`
- `0x1800230a0`
- `0x180023850`
- `0x180023ac0`
- `0x18003f9e1`
- `0x18003fab9`

## callees

- `0x180004900`
- `0x18000db18`
- `0x18000dc7c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000db40`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000db40`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000dbbc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000dbbc`

## pseudocode

```c
struct MidiKSTransportTelemetryProvider *MidiKSTransportTelemetryProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiKSTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180071D68 = 0;
    v3 = &qword_180071D60;
    qword_180071D60 = &MidiXProcTelemetryProvider::`vftable';
    byte_180071D70 = 0;
    dword_180071D74 = 0;
    qword_180071D78 = (struct _tlgProvider_t *)&`MidiKSTransportTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiKSTransportTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180071D60, qword_180071D78, v0);
    InitOnceComplete(&`MidiKSTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180071D60);
  }
  return (struct MidiKSTransportTelemetryProvider *)v3;
}

```

## disassembly

```asm
0x18000db18  mov     rax, rsp
0x18000db1b  push    rbx
0x18000db1c  sub     rsp, 20h
0x18000db20  lea     r9, [rax+10h]; lpContext
0x18000db24  mov     qword ptr [rax+10h], 0
0x18000db2c  lea     r8, [rax+8]; fPending
0x18000db30  mov     dword ptr [rax+8], 0
0x18000db37  xor     edx, edx; dwFlags
0x18000db39  lea     rcx, ?wrapper@?1??Instance@MidiKSTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiKSTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000db40  call    cs:__imp_InitOnceBeginInitialize
0x18000db46  test    eax, eax
0x18000db48  jz      short loc_18000DBC2
0x18000db4a  cmp     [rsp+28h+arg_0], 0
0x18000db4f  jz      short loc_18000DBC2
0x18000db51  lea     rbx, qword_180071D60
0x18000db58  mov     cs:qword_180071D68, 0
0x18000db63  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x18000db6a  mov     [rsp+28h+arg_8], rbx
0x18000db6f  mov     cs:qword_180071D60, rax
0x18000db76  mov     cs:byte_180071D70, 0
0x18000db7d  mov     cs:dword_180071D74, 0
0x18000db87  lea     rax, ?__hInner@?1???0StaticHandle@MidiKSTransportTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiKSTransportTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000db8e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiKSTransportTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000db95  mov     cs:qword_180071D78, rax
0x18000db9c  call    atexit
0x18000dba1  mov     rdx, cs:qword_180071D78; struct _tlgProvider_t *
0x18000dba8  mov     rcx, rbx; this
0x18000dbab  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000dbb0  mov     r8, rbx; lpContext
0x18000dbb3  lea     rcx, ?wrapper@?1??Instance@MidiKSTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiKSTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000dbba  xor     edx, edx; dwFlags
0x18000dbbc  call    cs:__imp_InitOnceComplete
0x18000dbc2  mov     rax, [rsp+28h+arg_8]
0x18000dbc7  add     rsp, 20h
0x18000dbcb  pop     rbx
0x18000dbcc  retn
```

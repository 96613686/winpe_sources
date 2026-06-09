# MidiSrvTransportTelemetryProvider::Instance(void)

- ea: `0x180009bf8`
- end: `0x180009cad`
- name: `?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct MidiSrvTransportTelemetryProvider *(void)`
- caller_count: `34`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009ac0`
- `0x18000aa80`
- `0x18000b5f0`
- `0x18000b7f0`
- `0x18000b8c0`
- `0x18000baa0`
- `0x18000bbb0`
- `0x18000bcb0`
- `0x18000beb0`
- `0x18000bfc0`
- `0x18000c090`
- `0x18000c170`
- `0x18000c250`
- `0x18000c3b0`
- `0x18000c480`
- `0x18000c570`
- `0x18000c630`
- `0x18000c6d0`
- `0x18000c830`
- `0x18000c8d0`
- `0x18000c9a0`
- `0x18000ca60`
- `0x1800121c4`
- `0x180012448`
- `0x1800126e4`
- `0x180012830`
- `0x180012964`
- `0x180012b04`
- `0x1800136c0`
- `0x180013730`
- `0x1800138f8`
- `0x180013a3c`
- `0x180013bf4`
- `0x180013d98`

## callees

- `0x180002890`
- `0x180009bf8`
- `0x180009d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009c20`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009c20`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009c9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009c9c`

## pseudocode

```c
struct MidiSrvTransportTelemetryProvider *MidiSrvTransportTelemetryProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiSrvTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_18001E690 = 0;
    v3 = &qword_18001E688;
    qword_18001E688 = &MidiXProcTelemetryProvider::`vftable';
    byte_18001E698 = 0;
    dword_18001E69C = 0;
    qword_18001E6A0 = (struct _tlgProvider_t *)&`MidiSrvTransportTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiSrvTransportTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18001E688, qword_18001E6A0, v0);
    InitOnceComplete(&`MidiSrvTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_18001E688);
  }
  return (struct MidiSrvTransportTelemetryProvider *)v3;
}

```

## disassembly

```asm
0x180009bf8  mov     rax, rsp
0x180009bfb  push    rbx
0x180009bfc  sub     rsp, 20h
0x180009c00  lea     r9, [rax+10h]; lpContext
0x180009c04  mov     qword ptr [rax+10h], 0
0x180009c0c  lea     r8, [rax+8]; fPending
0x180009c10  mov     dword ptr [rax+8], 0
0x180009c17  xor     edx, edx; dwFlags
0x180009c19  lea     rcx, ?wrapper@?1??Instance@MidiSrvTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiSrvTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180009c20  call    cs:__imp_InitOnceBeginInitialize
0x180009c26  test    eax, eax
0x180009c28  jz      short loc_180009CA2
0x180009c2a  cmp     [rsp+28h+arg_0], 0
0x180009c2f  jz      short loc_180009CA2
0x180009c31  lea     rbx, qword_18001E688
0x180009c38  mov     cs:qword_18001E690, 0
0x180009c43  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x180009c4a  mov     [rsp+28h+arg_8], rbx
0x180009c4f  mov     cs:qword_18001E688, rax
0x180009c56  mov     cs:byte_18001E698, 0
0x180009c5d  mov     cs:dword_18001E69C, 0
0x180009c67  lea     rax, ?__hInner@?1???0StaticHandle@MidiSrvTransportTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiSrvTransportTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009c6e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiSrvTransportTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180009c75  mov     cs:qword_18001E6A0, rax
0x180009c7c  call    atexit
0x180009c81  mov     rdx, cs:qword_18001E6A0; struct _tlgProvider_t *
0x180009c88  mov     rcx, rbx; this
0x180009c8b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009c90  mov     r8, rbx; lpContext
0x180009c93  lea     rcx, ?wrapper@?1??Instance@MidiSrvTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiSrvTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180009c9a  xor     edx, edx; dwFlags
0x180009c9c  call    cs:__imp_InitOnceComplete
0x180009ca2  mov     rax, [rsp+28h+arg_8]
0x180009ca7  add     rsp, 20h
0x180009cab  pop     rbx
0x180009cac  retn
```

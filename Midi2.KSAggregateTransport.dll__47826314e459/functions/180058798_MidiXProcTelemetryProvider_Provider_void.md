# MidiXProcTelemetryProvider::Provider(void)

- ea: `0x180058798`
- end: `0x180058851`
- name: `?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180058460`
- `0x180058a2c`
- `0x1800593f4`

## callees

- `0x180005510`
- `0x18001193c`
- `0x180058798`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800587c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800587c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005883c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005883c`

## pseudocode

```c
const struct _tlgProvider_t *MidiXProcTelemetryProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180096FE0 = 0;
    v3 = &qword_180096FD8;
    qword_180096FD8 = &MidiXProcTelemetryProvider::`vftable';
    byte_180096FE8 = 0;
    dword_180096FEC = 0;
    qword_180096FF0 = (struct _tlgProvider_t *)&`MidiXProcTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiXProcTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180096FD8, qword_180096FF0, v0);
    InitOnceComplete(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180096FD8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x180058798  mov     rax, rsp
0x18005879b  push    rbx
0x18005879c  sub     rsp, 20h
0x1800587a0  lea     r9, [rax+10h]; lpContext
0x1800587a4  mov     qword ptr [rax+10h], 0
0x1800587ac  lea     r8, [rax+8]; fPending
0x1800587b0  mov     dword ptr [rax+8], 0
0x1800587b7  xor     edx, edx; dwFlags
0x1800587b9  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x1800587c0  call    cs:__imp_InitOnceBeginInitialize
0x1800587c6  test    eax, eax
0x1800587c8  jz      short loc_180058842
0x1800587ca  cmp     [rsp+28h+arg_0], 0
0x1800587cf  jz      short loc_180058842
0x1800587d1  lea     rbx, qword_180096FD8
0x1800587d8  mov     cs:qword_180096FE0, 0
0x1800587e3  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x1800587ea  mov     [rsp+28h+arg_8], rbx
0x1800587ef  mov     cs:qword_180096FD8, rax
0x1800587f6  mov     cs:byte_180096FE8, 0
0x1800587fd  mov     cs:dword_180096FEC, 0
0x180058807  lea     rax, ?__hInner@?1???0StaticHandle@MidiXProcTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiXProcTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18005880e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180058815  mov     cs:qword_180096FF0, rax
0x18005881c  call    atexit
0x180058821  mov     rdx, cs:qword_180096FF0; struct _tlgProvider_t *
0x180058828  mov     rcx, rbx; this
0x18005882b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180058830  mov     r8, rbx; lpContext
0x180058833  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18005883a  xor     edx, edx; dwFlags
0x18005883c  call    cs:__imp_InitOnceComplete
0x180058842  mov     rax, [rsp+28h+arg_8]
0x180058847  mov     rax, [rax+8]
0x18005884b  add     rsp, 20h
0x18005884f  pop     rbx
0x180058850  retn
```

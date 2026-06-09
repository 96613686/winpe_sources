# MidiXProcTelemetryProvider::Provider(void)

- ea: `0x18000f984`
- end: `0x18000fa3d`
- name: `?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f570`
- `0x180010260`
- `0x180010cc0`

## callees

- `0x180002890`
- `0x180009d5c`
- `0x18000f984`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f9ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f9ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000fa28`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000fa28`

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
    qword_18001E840 = 0;
    v3 = &qword_18001E838;
    qword_18001E838 = &MidiXProcTelemetryProvider::`vftable';
    byte_18001E848 = 0;
    dword_18001E84C = 0;
    qword_18001E850 = (struct _tlgProvider_t *)&`MidiXProcTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiXProcTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18001E838, qword_18001E850, v0);
    InitOnceComplete(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_18001E838);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000f984  mov     rax, rsp
0x18000f987  push    rbx
0x18000f988  sub     rsp, 20h
0x18000f98c  lea     r9, [rax+10h]; lpContext
0x18000f990  mov     qword ptr [rax+10h], 0
0x18000f998  lea     r8, [rax+8]; fPending
0x18000f99c  mov     dword ptr [rax+8], 0
0x18000f9a3  xor     edx, edx; dwFlags
0x18000f9a5  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000f9ac  call    cs:__imp_InitOnceBeginInitialize
0x18000f9b2  test    eax, eax
0x18000f9b4  jz      short loc_18000FA2E
0x18000f9b6  cmp     [rsp+28h+arg_0], 0
0x18000f9bb  jz      short loc_18000FA2E
0x18000f9bd  lea     rbx, qword_18001E838
0x18000f9c4  mov     cs:qword_18001E840, 0
0x18000f9cf  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x18000f9d6  mov     [rsp+28h+arg_8], rbx
0x18000f9db  mov     cs:qword_18001E838, rax
0x18000f9e2  mov     cs:byte_18001E848, 0
0x18000f9e9  mov     cs:dword_18001E84C, 0
0x18000f9f3  lea     rax, ?__hInner@?1???0StaticHandle@MidiXProcTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiXProcTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000f9fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000fa01  mov     cs:qword_18001E850, rax
0x18000fa08  call    atexit
0x18000fa0d  mov     rdx, cs:qword_18001E850; struct _tlgProvider_t *
0x18000fa14  mov     rcx, rbx; this
0x18000fa17  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000fa1c  mov     r8, rbx; lpContext
0x18000fa1f  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000fa26  xor     edx, edx; dwFlags
0x18000fa28  call    cs:__imp_InitOnceComplete
0x18000fa2e  mov     rax, [rsp+28h+arg_8]
0x18000fa33  mov     rax, [rax+8]
0x18000fa37  add     rsp, 20h
0x18000fa3b  pop     rbx
0x18000fa3c  retn
```

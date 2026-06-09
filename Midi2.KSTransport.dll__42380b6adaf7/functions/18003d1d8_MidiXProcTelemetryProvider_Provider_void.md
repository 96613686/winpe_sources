# MidiXProcTelemetryProvider::Provider(void)

- ea: `0x18003d1d8`
- end: `0x18003d291`
- name: `?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003ce60`
- `0x18003d46c`
- `0x18003de34`

## callees

- `0x180004900`
- `0x18000dc7c`
- `0x18003d1d8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003d200`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003d200`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d27c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003d27c`

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
    qword_180071FA0 = 0;
    v3 = &qword_180071F98;
    qword_180071F98 = &MidiXProcTelemetryProvider::`vftable';
    byte_180071FA8 = 0;
    dword_180071FAC = 0;
    qword_180071FB0 = (struct _tlgProvider_t *)&`MidiXProcTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiXProcTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180071F98, qword_180071FB0, v0);
    InitOnceComplete(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180071F98);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18003d1d8  mov     rax, rsp
0x18003d1db  push    rbx
0x18003d1dc  sub     rsp, 20h
0x18003d1e0  lea     r9, [rax+10h]; lpContext
0x18003d1e4  mov     qword ptr [rax+10h], 0
0x18003d1ec  lea     r8, [rax+8]; fPending
0x18003d1f0  mov     dword ptr [rax+8], 0
0x18003d1f7  xor     edx, edx; dwFlags
0x18003d1f9  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18003d200  call    cs:__imp_InitOnceBeginInitialize
0x18003d206  test    eax, eax
0x18003d208  jz      short loc_18003D282
0x18003d20a  cmp     [rsp+28h+arg_0], 0
0x18003d20f  jz      short loc_18003D282
0x18003d211  lea     rbx, qword_180071F98
0x18003d218  mov     cs:qword_180071FA0, 0
0x18003d223  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x18003d22a  mov     [rsp+28h+arg_8], rbx
0x18003d22f  mov     cs:qword_180071F98, rax
0x18003d236  mov     cs:byte_180071FA8, 0
0x18003d23d  mov     cs:dword_180071FAC, 0
0x18003d247  lea     rax, ?__hInner@?1???0StaticHandle@MidiXProcTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiXProcTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003d24e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18003d255  mov     cs:qword_180071FB0, rax
0x18003d25c  call    atexit
0x18003d261  mov     rdx, cs:qword_180071FB0; struct _tlgProvider_t *
0x18003d268  mov     rcx, rbx; this
0x18003d26b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18003d270  mov     r8, rbx; lpContext
0x18003d273  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18003d27a  xor     edx, edx; dwFlags
0x18003d27c  call    cs:__imp_InitOnceComplete
0x18003d282  mov     rax, [rsp+28h+arg_8]
0x18003d287  mov     rax, [rax+8]
0x18003d28b  add     rsp, 20h
0x18003d28f  pop     rbx
0x18003d290  retn
```

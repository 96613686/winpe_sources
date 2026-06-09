# FlightDataRecorderActivityClass::Provider(void)

- ea: `0x140018914`
- end: `0x1400189cd`
- name: `?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140015350`
- `0x140018330`
- `0x140018dc4`
- `0x140019314`
- `0x140019680`

## callees

- `0x1400028b8`
- `0x1400078fc`
- `0x140018914`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001893c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001893c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400189b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400189b8`

## pseudocode

```c
const struct _tlgProvider_t *FlightDataRecorderActivityClass::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`FlightDataRecorderActivityClass::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_140030BC0 = 0;
    v3 = &qword_140030BB8;
    qword_140030BB8 = &FlightDataRecorderActivityClass::`vftable';
    byte_140030BC8 = 0;
    dword_140030BCC = 0;
    qword_140030BD0 = (struct _tlgProvider_t *)&`FlightDataRecorderActivityClass::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_12563d7c8dc646babe2507c022b26442_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140030BB8, qword_140030BD0, v0);
    InitOnceComplete(&`FlightDataRecorderActivityClass::Instance'::`2'::wrapper, 0, &qword_140030BB8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x140018914  mov     rax, rsp
0x140018917  push    rbx
0x140018918  sub     rsp, 20h
0x14001891c  lea     r9, [rax+10h]; lpContext
0x140018920  mov     qword ptr [rax+10h], 0
0x140018928  lea     r8, [rax+8]; fPending
0x14001892c  mov     dword ptr [rax+8], 0
0x140018933  xor     edx, edx; dwFlags
0x140018935  lea     rcx, ?wrapper@?1??Instance@FlightDataRecorderActivityClass@@KAPEAV2@XZ@4V?$static_lazy@VFlightDataRecorderActivityClass@@@details@wil@@A; lpInitOnce
0x14001893c  call    cs:__imp_InitOnceBeginInitialize
0x140018942  test    eax, eax
0x140018944  jz      short loc_1400189BE
0x140018946  cmp     [rsp+28h+arg_0], 0
0x14001894b  jz      short loc_1400189BE
0x14001894d  lea     rbx, qword_140030BB8
0x140018954  mov     cs:qword_140030BC0, 0
0x14001895f  lea     rax, ??_7FlightDataRecorderActivityClass@@6B@; const FlightDataRecorderActivityClass::`vftable'
0x140018966  mov     [rsp+28h+arg_8], rbx
0x14001896b  mov     cs:qword_140030BB8, rax
0x140018972  mov     cs:byte_140030BC8, 0
0x140018979  mov     cs:dword_140030BCC, 0
0x140018983  lea     rax, ?__hInner@?1???0StaticHandle@FlightDataRecorderActivityClass@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `FlightDataRecorderActivityClass::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14001898a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_12563d7c8dc646babe2507c022b26442_@@CA@XZ; void (__cdecl *)()
0x140018991  mov     cs:qword_140030BD0, rax
0x140018998  call    atexit
0x14001899d  mov     rdx, cs:qword_140030BD0; struct _tlgProvider_t *
0x1400189a4  mov     rcx, rbx; this
0x1400189a7  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1400189ac  mov     r8, rbx; lpContext
0x1400189af  lea     rcx, ?wrapper@?1??Instance@FlightDataRecorderActivityClass@@KAPEAV2@XZ@4V?$static_lazy@VFlightDataRecorderActivityClass@@@details@wil@@A; lpInitOnce
0x1400189b6  xor     edx, edx; dwFlags
0x1400189b8  call    cs:__imp_InitOnceComplete
0x1400189be  mov     rax, [rsp+28h+arg_8]
0x1400189c3  mov     rax, [rax+8]
0x1400189c7  add     rsp, 20h
0x1400189cb  pop     rbx
0x1400189cc  retn
```

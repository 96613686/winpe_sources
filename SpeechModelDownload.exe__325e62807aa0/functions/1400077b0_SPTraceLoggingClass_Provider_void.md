# SPTraceLoggingClass::Provider(void)

- ea: `0x1400077b0`
- end: `0x140007869`
- name: `?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `35`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003d38`
- `0x140003dd4`
- `0x140004f38`
- `0x140005668`
- `0x140005740`
- `0x140008710`
- `0x1400087c0`
- `0x140008860`
- `0x140008ad0`
- `0x140008b80`
- `0x140008c20`
- `0x14000a5ec`
- `0x14000a688`
- `0x14000a718`
- `0x14000a7b8`
- `0x14000a84c`
- `0x14000a930`
- `0x14000aa08`
- `0x14000aaec`
- `0x14000abc4`
- `0x14000acb0`
- `0x14000ad94`
- `0x14000ae78`
- `0x14000be9c`
- `0x14000bf74`
- `0x14000c04c`
- `0x14000c124`
- `0x14000c1fc`
- `0x14000c2d4`
- `0x14000c3d8`
- `0x14000d1f4`
- `0x14000d41c`
- `0x14000e340`
- `0x14000fdf4`
- `0x14001028c`

## callees

- `0x1400028b8`
- `0x1400077b0`
- `0x1400078fc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400077d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400077d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140007854`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140007854`

## pseudocode

```c
const struct _tlgProvider_t *SPTraceLoggingClass::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SPTraceLoggingClass::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_1400306F0 = 0;
    v3 = &qword_1400306E8;
    qword_1400306E8 = &FlightDataRecorderActivityClass::`vftable';
    byte_1400306F8 = 0;
    dword_1400306FC = 0;
    qword_140030700 = (struct _tlgProvider_t *)&`SPTraceLoggingClass::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_7a980c10fab413e8fd377d5d7cfba827_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1400306E8, qword_140030700, v0);
    InitOnceComplete(&`SPTraceLoggingClass::Instance'::`2'::wrapper, 0, &qword_1400306E8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1400077b0  mov     rax, rsp
0x1400077b3  push    rbx
0x1400077b4  sub     rsp, 20h
0x1400077b8  lea     r9, [rax+10h]; lpContext
0x1400077bc  mov     qword ptr [rax+10h], 0
0x1400077c4  lea     r8, [rax+8]; fPending
0x1400077c8  mov     dword ptr [rax+8], 0
0x1400077cf  xor     edx, edx; dwFlags
0x1400077d1  lea     rcx, ?wrapper@?1??Instance@SPTraceLoggingClass@@KAPEAV2@XZ@4V?$static_lazy@VSPTraceLoggingClass@@@details@wil@@A; lpInitOnce
0x1400077d8  call    cs:__imp_InitOnceBeginInitialize
0x1400077de  test    eax, eax
0x1400077e0  jz      short loc_14000785A
0x1400077e2  cmp     [rsp+28h+arg_0], 0
0x1400077e7  jz      short loc_14000785A
0x1400077e9  lea     rbx, qword_1400306E8
0x1400077f0  mov     cs:qword_1400306F0, 0
0x1400077fb  lea     rax, ??_7FlightDataRecorderActivityClass@@6B@; const FlightDataRecorderActivityClass::`vftable'
0x140007802  mov     [rsp+28h+arg_8], rbx
0x140007807  mov     cs:qword_1400306E8, rax
0x14000780e  mov     cs:byte_1400306F8, 0
0x140007815  mov     cs:dword_1400306FC, 0
0x14000781f  lea     rax, ?__hInner@?1???0StaticHandle@SPTraceLoggingClass@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SPTraceLoggingClass::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140007826  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7a980c10fab413e8fd377d5d7cfba827_@@CA@XZ; void (__cdecl *)()
0x14000782d  mov     cs:qword_140030700, rax
0x140007834  call    atexit
0x140007839  mov     rdx, cs:qword_140030700; struct _tlgProvider_t *
0x140007840  mov     rcx, rbx; this
0x140007843  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140007848  mov     r8, rbx; lpContext
0x14000784b  lea     rcx, ?wrapper@?1??Instance@SPTraceLoggingClass@@KAPEAV2@XZ@4V?$static_lazy@VSPTraceLoggingClass@@@details@wil@@A; lpInitOnce
0x140007852  xor     edx, edx; dwFlags
0x140007854  call    cs:__imp_InitOnceComplete
0x14000785a  mov     rax, [rsp+28h+arg_8]
0x14000785f  mov     rax, [rax+8]
0x140007863  add     rsp, 20h
0x140007867  pop     rbx
0x140007868  retn
```

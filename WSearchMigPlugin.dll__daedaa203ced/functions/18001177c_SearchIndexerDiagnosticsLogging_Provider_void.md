# SearchIndexerDiagnosticsLogging::Provider(void)

- ea: `0x18001177c`
- end: `0x180011835`
- name: `?Provider@SearchIndexerDiagnosticsLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c490`
- `0x18000c590`
- `0x180011678`

## callees

- `0x180002b7c`
- `0x18000b9fc`
- `0x18001177c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011820`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011820`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800117a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800117a4`

## pseudocode

```c
const struct _tlgProvider_t *SearchIndexerDiagnosticsLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerDiagnosticsLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180026098 = 0;
    v3 = &qword_180026090;
    qword_180026090 = &SearchIndexerDiagnosticsLogging::`vftable';
    byte_1800260A0 = 0;
    dword_1800260A4 = 0;
    qword_1800260A8 = (struct _tlgProvider_t *)&`SearchIndexerDiagnosticsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_f5a7b2c01e17025c4bccdc40fa72449f_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180026090, qword_1800260A8, v0);
    InitOnceComplete(&`SearchIndexerDiagnosticsLogging::Instance'::`2'::wrapper, 0, &qword_180026090);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18001177c  mov     rax, rsp
0x18001177f  push    rbx
0x180011780  sub     rsp, 20h
0x180011784  lea     r9, [rax+10h]; lpContext
0x180011788  mov     qword ptr [rax+10h], 0
0x180011790  lea     r8, [rax+8]; fPending
0x180011794  mov     dword ptr [rax+8], 0
0x18001179b  xor     edx, edx; dwFlags
0x18001179d  lea     rcx, ?wrapper@?1??Instance@SearchIndexerDiagnosticsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerDiagnosticsLogging@@@details@wil@@A; lpInitOnce
0x1800117a4  call    cs:__imp_InitOnceBeginInitialize
0x1800117aa  test    eax, eax
0x1800117ac  jz      short loc_180011826
0x1800117ae  cmp     [rsp+28h+arg_0], 0
0x1800117b3  jz      short loc_180011826
0x1800117b5  lea     rbx, qword_180026090
0x1800117bc  mov     cs:qword_180026098, 0
0x1800117c7  lea     rax, ??_7SearchIndexerDiagnosticsLogging@@6B@; const SearchIndexerDiagnosticsLogging::`vftable'
0x1800117ce  mov     [rsp+28h+arg_8], rbx
0x1800117d3  mov     cs:qword_180026090, rax
0x1800117da  mov     cs:byte_1800260A0, 0
0x1800117e1  mov     cs:dword_1800260A4, 0
0x1800117eb  lea     rax, ?__hInner@?1???0StaticHandle@SearchIndexerDiagnosticsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchIndexerDiagnosticsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800117f2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f5a7b2c01e17025c4bccdc40fa72449f_@@CA@XZ; void (__cdecl *)()
0x1800117f9  mov     cs:qword_1800260A8, rax
0x180011800  call    atexit
0x180011805  mov     rdx, cs:qword_1800260A8; struct _tlgProvider_t *
0x18001180c  mov     rcx, rbx; this
0x18001180f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180011814  mov     r8, rbx; lpContext
0x180011817  lea     rcx, ?wrapper@?1??Instance@SearchIndexerDiagnosticsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerDiagnosticsLogging@@@details@wil@@A; lpInitOnce
0x18001181e  xor     edx, edx; dwFlags
0x180011820  call    cs:__imp_InitOnceComplete
0x180011826  mov     rax, [rsp+28h+arg_8]
0x18001182b  mov     rax, [rax+8]
0x18001182f  add     rsp, 20h
0x180011833  pop     rbx
0x180011834  retn
```

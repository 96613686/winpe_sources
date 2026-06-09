# SearchIndexerLogging::Provider(void)

- ea: `0x18000b93c`
- end: `0x18000b9f5`
- name: `?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b500`
- `0x18000b730`

## callees

- `0x180002b7c`
- `0x18000b93c`
- `0x18000b9fc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b9e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b9e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b964`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b964`

## pseudocode

```c
const struct _tlgProvider_t *SearchIndexerLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180025F90 = 0;
    v3 = &qword_180025F88;
    qword_180025F88 = &SearchIndexerDiagnosticsLogging::`vftable';
    byte_180025F98 = 0;
    dword_180025F9C = 0;
    qword_180025FA0 = (struct _tlgProvider_t *)&`SearchIndexerLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_146b59ebcc9f355e66773394ba8c4ff4_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180025F88, qword_180025FA0, v0);
    InitOnceComplete(&`SearchIndexerLogging::Instance'::`2'::wrapper, 0, &qword_180025F88);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000b93c  mov     rax, rsp
0x18000b93f  push    rbx
0x18000b940  sub     rsp, 20h
0x18000b944  lea     r9, [rax+10h]; lpContext
0x18000b948  mov     qword ptr [rax+10h], 0
0x18000b950  lea     r8, [rax+8]; fPending
0x18000b954  mov     dword ptr [rax+8], 0
0x18000b95b  xor     edx, edx; dwFlags
0x18000b95d  lea     rcx, ?wrapper@?1??Instance@SearchIndexerLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerLogging@@@details@wil@@A; lpInitOnce
0x18000b964  call    cs:__imp_InitOnceBeginInitialize
0x18000b96a  test    eax, eax
0x18000b96c  jz      short loc_18000B9E6
0x18000b96e  cmp     [rsp+28h+arg_0], 0
0x18000b973  jz      short loc_18000B9E6
0x18000b975  lea     rbx, qword_180025F88
0x18000b97c  mov     cs:qword_180025F90, 0
0x18000b987  lea     rax, ??_7SearchIndexerDiagnosticsLogging@@6B@; const SearchIndexerDiagnosticsLogging::`vftable'
0x18000b98e  mov     [rsp+28h+arg_8], rbx
0x18000b993  mov     cs:qword_180025F88, rax
0x18000b99a  mov     cs:byte_180025F98, 0
0x18000b9a1  mov     cs:dword_180025F9C, 0
0x18000b9ab  lea     rax, ?__hInner@?1???0StaticHandle@SearchIndexerLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchIndexerLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000b9b2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_146b59ebcc9f355e66773394ba8c4ff4_@@CA@XZ; void (__cdecl *)()
0x18000b9b9  mov     cs:qword_180025FA0, rax
0x18000b9c0  call    atexit
0x18000b9c5  mov     rdx, cs:qword_180025FA0; struct _tlgProvider_t *
0x18000b9cc  mov     rcx, rbx; this
0x18000b9cf  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000b9d4  mov     r8, rbx; lpContext
0x18000b9d7  lea     rcx, ?wrapper@?1??Instance@SearchIndexerLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerLogging@@@details@wil@@A; lpInitOnce
0x18000b9de  xor     edx, edx; dwFlags
0x18000b9e0  call    cs:__imp_InitOnceComplete
0x18000b9e6  mov     rax, [rsp+28h+arg_8]
0x18000b9eb  mov     rax, [rax+8]
0x18000b9ef  add     rsp, 20h
0x18000b9f3  pop     rbx
0x18000b9f4  retn
```

# wil::details::FeatureLogging::Instance(void)

- ea: `0x14000a46c`
- end: `0x14000a521`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009900`

## callees

- `0x140002534`
- `0x14000a46c`
- `0x14000bdf0`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x14000a494`
- `KERNEL32!InitOnceBeginInitialize` at `0x14000a494`
- `KERNEL32!InitOnceComplete` at `0x14000a510`
- `KERNEL32!InitOnceComplete` at `0x14000a510`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_140017D08 = 0;
    v3 = &qword_140017D00;
    qword_140017D00 = &wil::details::FeatureLogging::`vftable';
    byte_140017D10 = 0;
    dword_140017D14 = 0;
    qword_140017D18 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140017D00, qword_140017D18, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_140017D00);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x14000a46c  mov     rax, rsp
0x14000a46f  push    rbx
0x14000a470  sub     rsp, 20h
0x14000a474  lea     r9, [rax+10h]; lpContext
0x14000a478  mov     qword ptr [rax+10h], 0
0x14000a480  lea     r8, [rax+8]; fPending
0x14000a484  mov     dword ptr [rax+8], 0
0x14000a48b  xor     edx, edx; dwFlags
0x14000a48d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000a494  call    cs:__imp_InitOnceBeginInitialize
0x14000a49a  test    eax, eax
0x14000a49c  jz      short loc_14000A516
0x14000a49e  cmp     [rsp+28h+arg_0], 0
0x14000a4a3  jz      short loc_14000A516
0x14000a4a5  lea     rbx, qword_140017D00
0x14000a4ac  mov     cs:qword_140017D08, 0
0x14000a4b7  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x14000a4be  mov     [rsp+28h+arg_8], rbx
0x14000a4c3  mov     cs:qword_140017D00, rax
0x14000a4ca  mov     cs:byte_140017D10, 0
0x14000a4d1  mov     cs:dword_140017D14, 0
0x14000a4db  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000a4e2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x14000a4e9  mov     cs:qword_140017D18, rax
0x14000a4f0  call    atexit
0x14000a4f5  mov     rdx, cs:qword_140017D18; struct _tlgProvider_t *
0x14000a4fc  mov     rcx, rbx; this
0x14000a4ff  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14000a504  mov     r8, rbx; lpContext
0x14000a507  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000a50e  xor     edx, edx; dwFlags
0x14000a510  call    cs:__imp_InitOnceComplete
0x14000a516  mov     rax, [rsp+28h+arg_8]
0x14000a51b  add     rsp, 20h
0x14000a51f  pop     rbx
0x14000a520  retn
```

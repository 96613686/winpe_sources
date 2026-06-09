# wpc::Logging::WpcBaseLogger::Provider(void)

- ea: `0x180010d90`
- end: `0x180010e49`
- name: `?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000edcc`
- `0x1800108b0`
- `0x180012240`
- `0x180012a30`
- `0x180012ba8`
- `0x180012d20`
- `0x180012e98`
- `0x180013010`
- `0x180013140`
- `0x1800133c0`
- `0x180013640`
- `0x1800138c0`

## callees

- `0x1800036b8`
- `0x180010d90`
- `0x180011f18`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010db8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010db8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010e34`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010e34`

## pseudocode

```c
const struct _tlgProvider_t *wpc::Logging::WpcBaseLogger::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wpc::Logging::WpcBaseLogger::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_18004AB68 = 0;
    v3 = &qword_18004AB60;
    qword_18004AB60 = &wpc::Logging::WpcBaseLogger::`vftable';
    byte_18004AB70 = 0;
    dword_18004AB74 = 0;
    qword_18004AB78 = (struct _tlgProvider_t *)&`wpc::Logging::WpcBaseLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_59955177f92948a0ddb59c07058884af_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18004AB60, qword_18004AB78, v0);
    InitOnceComplete(&`wpc::Logging::WpcBaseLogger::Instance'::`2'::wrapper, 0, &qword_18004AB60);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x180010d90  mov     rax, rsp
0x180010d93  push    rbx
0x180010d94  sub     rsp, 20h
0x180010d98  lea     r9, [rax+10h]; lpContext
0x180010d9c  mov     qword ptr [rax+10h], 0
0x180010da4  lea     r8, [rax+8]; fPending
0x180010da8  mov     dword ptr [rax+8], 0
0x180010daf  xor     edx, edx; dwFlags
0x180010db1  lea     rcx, ?wrapper@?1??Instance@WpcBaseLogger@Logging@wpc@@KAPEAV234@XZ@4V?$static_lazy@VWpcBaseLogger@Logging@wpc@@@details@wil@@A; lpInitOnce
0x180010db8  call    cs:__imp_InitOnceBeginInitialize
0x180010dbe  test    eax, eax
0x180010dc0  jz      short loc_180010E3A
0x180010dc2  cmp     [rsp+28h+arg_0], 0
0x180010dc7  jz      short loc_180010E3A
0x180010dc9  lea     rbx, qword_18004AB60
0x180010dd0  mov     cs:qword_18004AB68, 0
0x180010ddb  lea     rax, ??_7WpcBaseLogger@Logging@wpc@@6B@; const wpc::Logging::WpcBaseLogger::`vftable'
0x180010de2  mov     [rsp+28h+arg_8], rbx
0x180010de7  mov     cs:qword_18004AB60, rax
0x180010dee  mov     cs:byte_18004AB70, 0
0x180010df5  mov     cs:dword_18004AB74, 0
0x180010dff  lea     rax, ?__hInner@?1???0StaticHandle@WpcBaseLogger@Logging@wpc@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wpc::Logging::WpcBaseLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180010e06  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_59955177f92948a0ddb59c07058884af_@@CA@XZ; void (__cdecl *)()
0x180010e0d  mov     cs:qword_18004AB78, rax
0x180010e14  call    atexit
0x180010e19  mov     rdx, cs:qword_18004AB78; struct _tlgProvider_t *
0x180010e20  mov     rcx, rbx; this
0x180010e23  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180010e28  mov     r8, rbx; lpContext
0x180010e2b  lea     rcx, ?wrapper@?1??Instance@WpcBaseLogger@Logging@wpc@@KAPEAV234@XZ@4V?$static_lazy@VWpcBaseLogger@Logging@wpc@@@details@wil@@A; lpInitOnce
0x180010e32  xor     edx, edx; dwFlags
0x180010e34  call    cs:__imp_InitOnceComplete
0x180010e3a  mov     rax, [rsp+28h+arg_8]
0x180010e3f  mov     rax, [rax+8]
0x180010e43  add     rsp, 20h
0x180010e47  pop     rbx
0x180010e48  retn
```

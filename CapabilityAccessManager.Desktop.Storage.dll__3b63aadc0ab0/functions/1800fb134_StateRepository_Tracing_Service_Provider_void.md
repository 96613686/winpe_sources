# StateRepository::Tracing::Service::Provider(void)

- ea: `0x1800fb134`
- end: `0x1800fb1ed`
- name: `?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `12`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f84bc`
- `0x1800fa5d0`
- `0x1800fc0cc`
- `0x1800fc228`
- `0x1800fc380`
- `0x1800ffadc`
- `0x180107b48`
- `0x180108760`
- `0x180108aac`
- `0x180108d14`
- `0x180108e8c`
- `0x180109010`

## callees

- `0x180003410`
- `0x1800ea3e8`
- `0x1800fb134`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb15c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb15c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb1d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb1d8`

## pseudocode

```c
const struct _tlgProvider_t *StateRepository::Tracing::Service::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`StateRepository::Tracing::Service::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3)
    && v2 )
  {
    qword_1801402C0 = 0;
    v3 = &qword_1801402B8;
    qword_1801402B8 = &StateRepository::Tracing::Service::`vftable';
    byte_1801402C8 = 0;
    dword_1801402CC = 0;
    qword_1801402D0 = (struct _tlgProvider_t *)&`StateRepository::Tracing::Service::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_1af0911b883bb9c47756bb2ef208bbf6_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1801402B8, qword_1801402D0, v0);
    InitOnceComplete(&`StateRepository::Tracing::Service::Instance'::`2'::wrapper, 0, &qword_1801402B8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1800fb134  mov     rax, rsp
0x1800fb137  push    rbx
0x1800fb138  sub     rsp, 20h
0x1800fb13c  lea     r9, [rax+10h]; lpContext
0x1800fb140  mov     qword ptr [rax+10h], 0
0x1800fb148  lea     r8, [rax+8]; fPending
0x1800fb14c  mov     dword ptr [rax+8], 0
0x1800fb153  xor     edx, edx; dwFlags
0x1800fb155  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x1800fb15c  call    cs:__imp_InitOnceBeginInitialize
0x1800fb162  test    eax, eax
0x1800fb164  jz      short loc_1800FB1DE
0x1800fb166  cmp     [rsp+28h+arg_0], 0
0x1800fb16b  jz      short loc_1800FB1DE
0x1800fb16d  lea     rbx, qword_1801402B8
0x1800fb174  mov     cs:qword_1801402C0, 0
0x1800fb17f  lea     rax, ??_7Service@Tracing@StateRepository@@6B@; const StateRepository::Tracing::Service::`vftable'
0x1800fb186  mov     [rsp+28h+arg_8], rbx
0x1800fb18b  mov     cs:qword_1801402B8, rax
0x1800fb192  mov     cs:byte_1801402C8, 0
0x1800fb199  mov     cs:dword_1801402CC, 0
0x1800fb1a3  lea     rax, ?__hInner@?1???0StaticHandle@Service@Tracing@StateRepository@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `StateRepository::Tracing::Service::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800fb1aa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1af0911b883bb9c47756bb2ef208bbf6_@@CA@XZ; void (__cdecl *)()
0x1800fb1b1  mov     cs:qword_1801402D0, rax
0x1800fb1b8  call    atexit
0x1800fb1bd  mov     rdx, cs:qword_1801402D0; struct _tlgProvider_t *
0x1800fb1c4  mov     rcx, rbx; this
0x1800fb1c7  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800fb1cc  mov     r8, rbx; lpContext
0x1800fb1cf  lea     rcx, ?wrapper@?1??Instance@Service@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VService@Tracing@StateRepository@@@details@wil@@A; lpInitOnce
0x1800fb1d6  xor     edx, edx; dwFlags
0x1800fb1d8  call    cs:__imp_InitOnceComplete
0x1800fb1de  mov     rax, [rsp+28h+arg_8]
0x1800fb1e3  mov     rax, [rax+8]
0x1800fb1e7  add     rsp, 20h
0x1800fb1eb  pop     rbx
0x1800fb1ec  retn
```

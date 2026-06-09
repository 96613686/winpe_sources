# MSAClientTraceTelemetry::Provider(void)

- ea: `0x180005820`
- end: `0x1800058d2`
- name: `?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002f8c`
- `0x180003020`

## callees

- `0x1800021bc`
- `0x180003e40`
- `0x180005820`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000584b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000584b`

## pseudocode

```c
const struct _tlgProvider_t *MSAClientTraceTelemetry::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`MSAClientTraceTelemetry::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`MSAClientTraceTelemetry::Instance'::`2'::wrapper;
    v4 = &qword_1800134E0;
    qword_1800134E0 = (__int64)&MSAClientTraceTelemetry::`vftable';
    qword_1800134E8 = 0;
    byte_1800134F0 = 0;
    dword_1800134F4 = 0;
    qword_1800134F8 = (__int64)&`MSAClientTraceTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180005820  mov     rax, rsp
0x180005823  push    rdi
0x180005824  sub     rsp, 30h
0x180005828  lea     rdi, ?wrapper@?1??Instance@MSAClientTraceTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@A; wil::details::static_lazy<MSAClientTraceTelemetry> `MSAClientTraceTelemetry::Instance(void)'::`2'::wrapper
0x18000582f  mov     qword ptr [rax+10h], 0
0x180005837  mov     rcx, rdi; lpInitOnce
0x18000583a  mov     dword ptr [rax+8], 0
0x180005841  lea     r9, [rax+10h]; lpContext
0x180005845  xor     edx, edx; dwFlags
0x180005847  lea     r8, [rax+8]; fPending
0x18000584b  call    cs:__imp_InitOnceBeginInitialize
0x180005851  test    eax, eax
0x180005853  jz      short loc_1800058C3
0x180005855  cmp     [rsp+38h+arg_0], 0
0x18000585a  jz      short loc_1800058C3
0x18000585c  lea     rax, qword_1800134E0
0x180005863  mov     [rsp+38h+var_18], rdi
0x180005868  mov     [rsp+38h+arg_8], rax
0x18000586d  lea     rax, ??_7MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::`vftable'
0x180005874  mov     cs:qword_1800134E0, rax
0x18000587b  mov     cs:qword_1800134E8, 0
0x180005886  mov     cs:byte_1800134F0, 0
0x18000588d  mov     cs:dword_1800134F4, 0
0x180005897  lea     rax, ?__hInner@?1???0StaticHandle@MSAClientTraceTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MSAClientTraceTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000589e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f3ddbd0a50d11f24ac1f58eb5524dee0_@@CA@XZ; void (__cdecl *)()
0x1800058a5  mov     cs:qword_1800134F8, rax
0x1800058ac  call    atexit
0x1800058b1  lea     rcx, [rsp+38h+var_18]
0x1800058b6  mov     [rsp+38h+var_10], 0
0x1800058be  call    ??1Completer@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(void)
0x1800058c3  mov     rax, [rsp+38h+arg_8]
0x1800058c8  mov     rax, [rax+8]
0x1800058cc  add     rsp, 30h
0x1800058d0  pop     rdi
0x1800058d1  retn
```

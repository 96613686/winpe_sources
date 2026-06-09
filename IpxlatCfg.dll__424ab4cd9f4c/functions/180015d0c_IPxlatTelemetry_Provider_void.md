# IPxlatTelemetry::Provider(void)

- ea: `0x180015d0c`
- end: `0x180015dbe`
- name: `?Provider@IPxlatTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001254c`
- `0x180012620`
- `0x180012728`
- `0x1800127fc`

## callees

- `0x1800020f0`
- `0x1800131d0`
- `0x180015d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d37`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d37`

## pseudocode

```c
const struct _tlgProvider_t *IPxlatTelemetry::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`IPxlatTelemetry::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`IPxlatTelemetry::Instance'::`2'::wrapper;
    v4 = &qword_1800239F8;
    qword_1800239F8 = (__int64)&IPxlatTelemetry::`vftable';
    qword_180023A00 = 0;
    byte_180023A08 = 0;
    dword_180023A0C = 0;
    qword_180023A10 = (__int64)&`IPxlatTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_f17533538631da5b511ca93ca312514d_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<IPxlatTelemetry>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180015d0c  mov     rax, rsp
0x180015d0f  push    rdi
0x180015d10  sub     rsp, 30h
0x180015d14  lea     rdi, ?wrapper@?1??Instance@IPxlatTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VIPxlatTelemetry@@@details@wil@@A; wil::details::static_lazy<IPxlatTelemetry> `IPxlatTelemetry::Instance(void)'::`2'::wrapper
0x180015d1b  mov     qword ptr [rax+10h], 0
0x180015d23  mov     rcx, rdi; lpInitOnce
0x180015d26  mov     dword ptr [rax+8], 0
0x180015d2d  lea     r9, [rax+10h]; lpContext
0x180015d31  xor     edx, edx; dwFlags
0x180015d33  lea     r8, [rax+8]; fPending
0x180015d37  call    cs:__imp_InitOnceBeginInitialize
0x180015d3d  test    eax, eax
0x180015d3f  jz      short loc_180015DAF
0x180015d41  cmp     [rsp+38h+arg_0], 0
0x180015d46  jz      short loc_180015DAF
0x180015d48  lea     rax, qword_1800239F8
0x180015d4f  mov     [rsp+38h+var_18], rdi
0x180015d54  mov     [rsp+38h+arg_8], rax
0x180015d59  lea     rax, ??_7IPxlatTelemetry@@6B@; const IPxlatTelemetry::`vftable'
0x180015d60  mov     cs:qword_1800239F8, rax
0x180015d67  mov     cs:qword_180023A00, 0
0x180015d72  mov     cs:byte_180023A08, 0
0x180015d79  mov     cs:dword_180023A0C, 0
0x180015d83  lea     rax, ?__hInner@?1???0StaticHandle@IPxlatTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `IPxlatTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180015d8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f17533538631da5b511ca93ca312514d_@@CA@XZ; void (__cdecl *)()
0x180015d91  mov     cs:qword_180023A10, rax
0x180015d98  call    atexit
0x180015d9d  lea     rcx, [rsp+38h+var_18]
0x180015da2  mov     [rsp+38h+var_10], 0
0x180015daa  call    ??1Completer@?$static_lazy@VIPxlatTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<IPxlatTelemetry>::Completer::~Completer(void)
0x180015daf  mov     rax, [rsp+38h+arg_8]
0x180015db4  mov     rax, [rax+8]
0x180015db8  add     rsp, 30h
0x180015dbc  pop     rdi
0x180015dbd  retn
```

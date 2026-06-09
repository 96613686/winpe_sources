# OfflineMapsTraceLogging::Provider(void)

- ea: `0x180005c50`
- end: `0x180005d02`
- name: `?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004810`
- `0x180008f30`
- `0x18000aab0`
- `0x18000ae98`
- `0x18000b1cc`
- `0x18000b28c`
- `0x18000b400`
- `0x18000b5c0`

## callees

- `0x180002900`
- `0x180003ea4`
- `0x180005c50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005c7b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005c7b`

## pseudocode

```c
const struct _tlgProvider_t *OfflineMapsTraceLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTraceLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`OfflineMapsTraceLogging::Instance'::`2'::wrapper;
    v4 = &qword_18001C6F0;
    qword_18001C6F0 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_18001C6F8 = 0;
    byte_18001C700 = 0;
    dword_18001C704 = 0;
    qword_18001C708 = (__int64)&`OfflineMapsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b1920e3fd6e26929e52072737012d5c8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180005c50  mov     rax, rsp
0x180005c53  push    rdi
0x180005c54  sub     rsp, 30h
0x180005c58  lea     rdi, ?wrapper@?1??Instance@OfflineMapsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@A; wil::details::static_lazy<OfflineMapsTraceLogging> `OfflineMapsTraceLogging::Instance(void)'::`2'::wrapper
0x180005c5f  mov     qword ptr [rax+10h], 0
0x180005c67  mov     rcx, rdi; lpInitOnce
0x180005c6a  mov     dword ptr [rax+8], 0
0x180005c71  lea     r9, [rax+10h]; lpContext
0x180005c75  xor     edx, edx; dwFlags
0x180005c77  lea     r8, [rax+8]; fPending
0x180005c7b  call    cs:__imp_InitOnceBeginInitialize
0x180005c81  test    eax, eax
0x180005c83  jz      short loc_180005CF3
0x180005c85  cmp     [rsp+38h+arg_0], 0
0x180005c8a  jz      short loc_180005CF3
0x180005c8c  lea     rax, qword_18001C6F0
0x180005c93  mov     [rsp+38h+var_18], rdi
0x180005c98  mov     [rsp+38h+arg_8], rax
0x180005c9d  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180005ca4  mov     cs:qword_18001C6F0, rax
0x180005cab  mov     cs:qword_18001C6F8, 0
0x180005cb6  mov     cs:byte_18001C700, 0
0x180005cbd  mov     cs:dword_18001C704, 0
0x180005cc7  lea     rax, ?__hInner@?1???0StaticHandle@OfflineMapsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `OfflineMapsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180005cce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b1920e3fd6e26929e52072737012d5c8_@@CA@XZ; void (__cdecl *)()
0x180005cd5  mov     cs:qword_18001C708, rax
0x180005cdc  call    atexit
0x180005ce1  lea     rcx, [rsp+38h+var_18]
0x180005ce6  mov     [rsp+38h+var_10], 0
0x180005cee  call    ??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)
0x180005cf3  mov     rax, [rsp+38h+arg_8]
0x180005cf8  mov     rax, [rax+8]
0x180005cfc  add     rsp, 30h
0x180005d00  pop     rdi
0x180005d01  retn
```

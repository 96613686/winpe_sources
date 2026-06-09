# SpeechMicDiagnostic::SmdTraceProvider::Instance(void)

- ea: `0x1800068cc`
- end: `0x180006981`
- name: `?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ`
- size: `181`
- prototype: `struct SpeechMicDiagnostic::SmdTraceProvider *(void)`
- caller_count: `38`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006800`
- `0x180006ce0`
- `0x18000713c`
- `0x180007588`
- `0x180007714`
- `0x180007c88`
- `0x180009420`
- `0x180009df0`
- `0x180009f44`
- `0x18000a098`
- `0x18000a1ec`
- `0x18000a340`
- `0x18000a494`
- `0x18000a5d4`
- `0x18000a714`
- `0x18000a868`
- `0x18000a964`
- `0x18000ac60`
- `0x18000af58`
- `0x18000b26c`
- `0x18000b590`
- `0x18000b888`
- `0x18000bb90`
- `0x18000be20`
- `0x18000c0b0`
- `0x18000c340`
- `0x18000c5d0`
- `0x18000c860`
- `0x18000caf0`
- `0x18000cd80`
- `0x18000d010`
- `0x18000d774`
- `0x18000d8bc`
- `0x18000d93c`
- `0x18000d9f0`
- `0x18000fcf4`
- `0x18000fd74`
- `0x18000fdf4`

## callees

- `0x180002cc0`
- `0x180006630`
- `0x1800068cc`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1800068f7`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800068f7`

## pseudocode

```c
struct SpeechMicDiagnostic::SmdTraceProvider *SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`SpeechMicDiagnostic::SmdTraceProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`SpeechMicDiagnostic::SmdTraceProvider::Instance'::`2'::wrapper;
    v4 = &qword_1800183C8;
    qword_1800183C8 = (__int64)&SpeechMicDiagnostic::SmdTraceProvider::`vftable';
    qword_1800183D0 = 0;
    byte_1800183D8 = 0;
    dword_1800183DC = 0;
    qword_1800183E0 = (__int64)&`SpeechMicDiagnostic::SmdTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_bd42c45b7d465fba873f7002ca40aa0e_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<SpeechMicDiagnostic::SmdTraceProvider>::Completer::~Completer(&v1);
  }
  return (struct SpeechMicDiagnostic::SmdTraceProvider *)v4;
}

```

## disassembly

```asm
0x1800068cc  mov     rax, rsp
0x1800068cf  push    rdi
0x1800068d0  sub     rsp, 30h
0x1800068d4  lea     rdi, ?wrapper@?1??Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV23@XZ@4V?$static_lazy@VSmdTraceProvider@SpeechMicDiagnostic@@@details@wil@@A; wil::details::static_lazy<SpeechMicDiagnostic::SmdTraceProvider> `SpeechMicDiagnostic::SmdTraceProvider::Instance(void)'::`2'::wrapper
0x1800068db  mov     qword ptr [rax+10h], 0
0x1800068e3  mov     rcx, rdi; lpInitOnce
0x1800068e6  mov     dword ptr [rax+8], 0
0x1800068ed  lea     r9, [rax+10h]; lpContext
0x1800068f1  xor     edx, edx; dwFlags
0x1800068f3  lea     r8, [rax+8]; fPending
0x1800068f7  call    cs:__imp_InitOnceBeginInitialize
0x1800068fe  nop     dword ptr [rax+rax+00h]
0x180006903  test    eax, eax
0x180006905  jz      short loc_180006975
0x180006907  cmp     [rsp+38h+arg_0], 0
0x18000690c  jz      short loc_180006975
0x18000690e  lea     rax, qword_1800183C8
0x180006915  mov     [rsp+38h+var_18], rdi
0x18000691a  mov     [rsp+38h+arg_8], rax
0x18000691f  lea     rax, ??_7SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::`vftable'
0x180006926  mov     cs:qword_1800183C8, rax
0x18000692d  mov     cs:qword_1800183D0, 0
0x180006938  mov     cs:byte_1800183D8, 0
0x18000693f  mov     cs:dword_1800183DC, 0
0x180006949  lea     rax, ?__hInner@?1???0StaticHandle@SmdTraceProvider@SpeechMicDiagnostic@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SpeechMicDiagnostic::SmdTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006950  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_bd42c45b7d465fba873f7002ca40aa0e_@@CA@XZ; void (__cdecl *)()
0x180006957  mov     cs:qword_1800183E0, rax
0x18000695e  call    atexit
0x180006963  lea     rcx, [rsp+38h+var_18]
0x180006968  mov     [rsp+38h+var_10], 0
0x180006970  call    ??1Completer@?$static_lazy@VSmdTraceProvider@SpeechMicDiagnostic@@@details@wil@@QEAA@XZ; wil::details::static_lazy<SpeechMicDiagnostic::SmdTraceProvider>::Completer::~Completer(void)
0x180006975  mov     rax, [rsp+38h+arg_8]
0x18000697a  add     rsp, 30h
0x18000697e  pop     rdi
0x18000697f  retn
```

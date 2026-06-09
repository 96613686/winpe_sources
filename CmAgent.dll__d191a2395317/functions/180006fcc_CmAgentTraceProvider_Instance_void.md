# CmAgentTraceProvider::Instance(void)

- ea: `0x180006fcc`
- end: `0x180007081`
- name: `?Instance@CmAgentTraceProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct CmAgentTraceProvider *(void)`
- caller_count: `36`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005a78`
- `0x1800065d0`
- `0x180007140`
- `0x180008648`
- `0x18000877c`
- `0x18000892c`
- `0x180008b20`
- `0x180008dd0`
- `0x180009940`
- `0x180010c5c`
- `0x18001bb20`
- `0x18001bc8c`
- `0x18001bdc0`
- `0x18001bfb4`
- `0x18001c0e8`
- `0x18001c21c`
- `0x18001c350`
- `0x18001c50c`
- `0x18001c640`
- `0x18001c774`
- `0x18001c8a8`
- `0x18001c9dc`
- `0x18001cb10`
- `0x18001cdc0`
- `0x18001d070`
- `0x18001d320`
- `0x18001d5d0`
- `0x18001d880`
- `0x18001db30`
- `0x18001dde0`
- `0x18001e090`
- `0x18001e340`
- `0x18001e5f0`
- `0x18001e8a0`
- `0x18001eb50`
- `0x180022f5c`

## callees

- `0x180002514`
- `0x180005b70`
- `0x180006fcc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006ff7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006ff7`

## pseudocode

```c
struct CmAgentTraceProvider *CmAgentTraceProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`CmAgentTraceProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`CmAgentTraceProvider::Instance'::`2'::wrapper;
    v4 = &qword_18004B818;
    qword_18004B818 = (__int64)&CmAgentTraceProvider::`vftable';
    qword_18004B820 = 0;
    byte_18004B828 = 0;
    dword_18004B82C = 0;
    qword_18004B830 = (__int64)&`CmAgentTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_113790e7e4c52f65595da5b94baed748_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<CmAgentTraceProvider>::Completer::~Completer(&v1);
  }
  return (struct CmAgentTraceProvider *)v4;
}

```

## disassembly

```asm
0x180006fcc  mov     rax, rsp
0x180006fcf  push    rdi
0x180006fd0  sub     rsp, 30h
0x180006fd4  lea     rdi, ?wrapper@?1??Instance@CmAgentTraceProvider@@KAPEAV2@XZ@4V?$static_lazy@VCmAgentTraceProvider@@@details@wil@@A; wil::details::static_lazy<CmAgentTraceProvider> `CmAgentTraceProvider::Instance(void)'::`2'::wrapper
0x180006fdb  mov     qword ptr [rax+10h], 0
0x180006fe3  mov     rcx, rdi; lpInitOnce
0x180006fe6  mov     dword ptr [rax+8], 0
0x180006fed  lea     r9, [rax+10h]; lpContext
0x180006ff1  xor     edx, edx; dwFlags
0x180006ff3  lea     r8, [rax+8]; fPending
0x180006ff7  call    cs:__imp_InitOnceBeginInitialize
0x180006ffe  nop     dword ptr [rax+rax+00h]
0x180007003  test    eax, eax
0x180007005  jz      short loc_180007075
0x180007007  cmp     [rsp+38h+arg_0], 0
0x18000700c  jz      short loc_180007075
0x18000700e  lea     rax, qword_18004B818
0x180007015  mov     [rsp+38h+var_18], rdi
0x18000701a  mov     [rsp+38h+arg_8], rax
0x18000701f  lea     rax, ??_7CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::`vftable'
0x180007026  mov     cs:qword_18004B818, rax
0x18000702d  mov     cs:qword_18004B820, 0
0x180007038  mov     cs:byte_18004B828, 0
0x18000703f  mov     cs:dword_18004B82C, 0
0x180007049  lea     rax, ?__hInner@?1???0StaticHandle@CmAgentTraceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CmAgentTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180007050  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_113790e7e4c52f65595da5b94baed748_@@CA@XZ; void (__cdecl *)()
0x180007057  mov     cs:qword_18004B830, rax
0x18000705e  call    atexit
0x180007063  lea     rcx, [rsp+38h+var_18]
0x180007068  mov     [rsp+38h+var_10], 0
0x180007070  call    ??1Completer@?$static_lazy@VCmAgentTraceProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<CmAgentTraceProvider>::Completer::~Completer(void)
0x180007075  mov     rax, [rsp+38h+arg_8]
0x18000707a  add     rsp, 30h
0x18000707e  pop     rdi
0x18000707f  retn
```

# DeviceCenterContextHandlersLogging::Provider(void)

- ea: `0x180009170`
- end: `0x180009222`
- name: `?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000570c`
- `0x180005b50`
- `0x180008ad0`
- `0x18000a3c4`
- `0x18000ac94`
- `0x18000ae3c`
- `0x18000afb0`
- `0x18000b514`

## callees

- `0x1800021b4`
- `0x180005c40`
- `0x180009170`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000919b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000919b`

## pseudocode

```c
const struct _tlgProvider_t *DeviceCenterContextHandlersLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`DeviceCenterContextHandlersLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4)
    && v3 )
  {
    v1 = &`DeviceCenterContextHandlersLogging::Instance'::`2'::wrapper;
    v4 = &qword_180014B60;
    qword_180014B60 = (__int64)&DeviceCenterContextHandlersLogging::`vftable';
    qword_180014B68 = 0;
    byte_180014B70 = 0;
    dword_180014B74 = 0;
    qword_180014B78 = (__int64)&`DeviceCenterContextHandlersLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b61b5c7b87cb4b9399d843d709a2834a_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<DeviceCenterContextHandlersLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180009170  mov     rax, rsp
0x180009173  push    rdi
0x180009174  sub     rsp, 30h
0x180009178  lea     rdi, ?wrapper@?1??Instance@DeviceCenterContextHandlersLogging@@KAPEAV2@XZ@4V?$static_lazy@VDeviceCenterContextHandlersLogging@@@details@wil@@A; wil::details::static_lazy<DeviceCenterContextHandlersLogging> `DeviceCenterContextHandlersLogging::Instance(void)'::`2'::wrapper
0x18000917f  mov     qword ptr [rax+10h], 0
0x180009187  mov     rcx, rdi; lpInitOnce
0x18000918a  mov     dword ptr [rax+8], 0
0x180009191  lea     r9, [rax+10h]; lpContext
0x180009195  xor     edx, edx; dwFlags
0x180009197  lea     r8, [rax+8]; fPending
0x18000919b  call    cs:__imp_InitOnceBeginInitialize
0x1800091a1  test    eax, eax
0x1800091a3  jz      short loc_180009213
0x1800091a5  cmp     [rsp+38h+arg_0], 0
0x1800091aa  jz      short loc_180009213
0x1800091ac  lea     rax, qword_180014B60
0x1800091b3  mov     [rsp+38h+var_18], rdi
0x1800091b8  mov     [rsp+38h+arg_8], rax
0x1800091bd  lea     rax, ??_7DeviceCenterContextHandlersLogging@@6B@; const DeviceCenterContextHandlersLogging::`vftable'
0x1800091c4  mov     cs:qword_180014B60, rax
0x1800091cb  mov     cs:qword_180014B68, 0
0x1800091d6  mov     cs:byte_180014B70, 0
0x1800091dd  mov     cs:dword_180014B74, 0
0x1800091e7  lea     rax, ?__hInner@?1???0StaticHandle@DeviceCenterContextHandlersLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DeviceCenterContextHandlersLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800091ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b61b5c7b87cb4b9399d843d709a2834a_@@CA@XZ; void (__cdecl *)()
0x1800091f5  mov     cs:qword_180014B78, rax
0x1800091fc  call    atexit
0x180009201  lea     rcx, [rsp+38h+var_18]
0x180009206  mov     [rsp+38h+var_10], 0
0x18000920e  call    ??1Completer@?$static_lazy@VDeviceCenterContextHandlersLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<DeviceCenterContextHandlersLogging>::Completer::~Completer(void)
0x180009213  mov     rax, [rsp+38h+arg_8]
0x180009218  mov     rax, [rax+8]
0x18000921c  add     rsp, 30h
0x180009220  pop     rdi
0x180009221  retn
```

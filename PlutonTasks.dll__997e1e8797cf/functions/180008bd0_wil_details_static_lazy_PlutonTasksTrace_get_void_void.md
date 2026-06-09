# wil::details::static_lazy<PlutonTasksTrace>::get(void (*)(void))

- ea: `0x180008bd0`
- end: `0x180008c86`
- name: `?get@?$static_lazy@VPlutonTasksTrace@@@details@wil@@QEAAPEAVPlutonTasksTrace@@P6AXXZ@Z`
- size: `182`
- prototype: `__int64 *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800081c8`

## callees

- `0x1800021f4`
- `0x1800037dc`
- `0x180008bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008c03`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008c03`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<PlutonTasksTrace>::get(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  void (*v3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  union _RTL_RUN_ONCE *v5; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+28h] [rbp-10h]
  __int64 *v7; // [rsp+40h] [rbp+8h] BYREF
  BOOL v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+4Ch] [rbp+14h]

  v9 = HIDWORD(a2);
  v7 = 0;
  v8 = 0;
  if ( InitOnceBeginInitialize(&`PlutonTasksTrace::Instance'::`2'::wrapper, 0, &v8, (LPVOID *)&v7) && v8 )
  {
    v5 = &`PlutonTasksTrace::Instance'::`2'::wrapper;
    v7 = &qword_18000F470;
    qword_18000F470 = (__int64)&PlutonTasksTrace::`vftable';
    qword_18000F478 = 0;
    byte_18000F480 = 0;
    dword_18000F484 = 0;
    qword_18000F488 = (__int64)&`PlutonTasksTrace::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`PlutonTasksTrace::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v6 = 0;
    wil::details::static_lazy<PlutonTasksTrace>::Completer::~Completer(&v5, v2, v3);
  }
  return v7;
}

```

## disassembly

```asm
0x180008bd0  mov     rax, rsp
0x180008bd3  mov     [rax+10h], rdx
0x180008bd7  mov     [rax+8], rcx
0x180008bdb  push    rdi
0x180008bdc  sub     rsp, 30h
0x180008be0  lea     rdi, ?wrapper@?1??Instance@PlutonTasksTrace@@KAPEAV2@XZ@4V?$static_lazy@VPlutonTasksTrace@@@details@wil@@A; wil::details::static_lazy<PlutonTasksTrace> `PlutonTasksTrace::Instance(void)'::`2'::wrapper
0x180008be7  mov     qword ptr [rax+8], 0
0x180008bef  mov     rcx, rdi; lpInitOnce
0x180008bf2  mov     dword ptr [rax+10h], 0
0x180008bf9  lea     r9, [rax+8]; lpContext
0x180008bfd  xor     edx, edx; dwFlags
0x180008bff  lea     r8, [rax+10h]; fPending
0x180008c03  call    cs:__imp_InitOnceBeginInitialize
0x180008c09  test    eax, eax
0x180008c0b  jz      short loc_180008C7B
0x180008c0d  cmp     [rsp+38h+arg_8], 0
0x180008c12  jz      short loc_180008C7B
0x180008c14  lea     rax, qword_18000F470
0x180008c1b  mov     [rsp+38h+var_18], rdi
0x180008c20  mov     [rsp+38h+arg_0], rax
0x180008c25  lea     rax, ??_7PlutonTasksTrace@@6B@; const PlutonTasksTrace::`vftable'
0x180008c2c  mov     cs:qword_18000F470, rax
0x180008c33  mov     cs:qword_18000F478, 0
0x180008c3e  mov     cs:byte_18000F480, 0
0x180008c45  mov     cs:dword_18000F484, 0
0x180008c4f  lea     rax, ?__hInner@?1???0StaticHandle@PlutonTasksTrace@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PlutonTasksTrace::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008c56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@PlutonTasksTrace@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180008c5d  mov     cs:qword_18000F488, rax
0x180008c64  call    atexit
0x180008c69  lea     rcx, [rsp+38h+var_18]
0x180008c6e  mov     [rsp+38h+var_10], 0
0x180008c76  call    ??1Completer@?$static_lazy@VPlutonTasksTrace@@@details@wil@@QEAA@XZ; wil::details::static_lazy<PlutonTasksTrace>::Completer::~Completer(void)
0x180008c7b  mov     rax, [rsp+38h+arg_0]
0x180008c80  add     rsp, 30h
0x180008c84  pop     rdi
0x180008c85  retn
```

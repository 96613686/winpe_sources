# CTaskCounter::CTaskCounter(void)

- ea: `0x18000754c`
- end: `0x18000760b`
- name: `??0CTaskCounter@@QEAA@XZ`
- size: `191`
- prototype: `CTaskCounter *__fastcall(CTaskCounter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008070`

## callees

- `0x180007648`
- `0x180007830`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007584`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007584`

## string_xrefs

- `0x18000758a`: `CTaskCounter::CTaskCounter`

## pseudocode

```c
CTaskCounter *__fastcall CTaskCounter::CTaskCounter(CTaskCounter *this)
{
  int v2; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v3; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v4[2]; // [rsp+38h] [rbp-38h] BYREF
  char v5[32]; // [rsp+48h] [rbp-28h] BYREF

  `CTaskCounter::Instance'::`2'::theTaskCounter = 0;
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  qword_18002BE08 = 0;
  v4[0] = v5;
  v4[1] = &v2;
  strcpy(v5, "CTaskCounter::CTaskCounter");
  qword_18002BE10 = 0;
  v2 = 0;
  lambda_3812f29f2bc42eee6a1ca7db246da244_::operator()(v4);
  v2 = 1;
  v3 = v4;
  WppTraceUnwinder__lambda_3812f29f2bc42eee6a1ca7db246da244____::_WppTraceUnwinder__lambda_3812f29f2bc42eee6a1ca7db246da244____(&v3);
  return (CTaskCounter *)&`CTaskCounter::Instance'::`2'::theTaskCounter;
}

```

## disassembly

```asm
0x18000754c  mov     [rsp-8+arg_0], rdi
0x180007551  push    rbp
0x180007552  mov     rbp, rsp
0x180007555  sub     rsp, 70h
0x180007559  mov     rax, cs:__security_cookie
0x180007560  xor     rax, rsp
0x180007563  mov     [rbp+var_8], rax
0x180007567  xor     r8d, r8d; Flags
0x18000756a  mov     cs:?theTaskCounter@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4V2@A, 0; CTaskCounter `CTaskCounter::Instance(void)'::`2'::theTaskCounter
0x180007574  xor     edx, edx; dwSpinCount
0x180007576  lea     rcx, CriticalSection; lpCriticalSection
0x18000757d  lea     rdi, ?theTaskCounter@?1??Instance@CTaskCounter@@SAAEAV2@XZ@4V2@A; CTaskCounter `CTaskCounter::Instance(void)'::`2'::theTaskCounter
0x180007584  call    cs:__imp_InitializeCriticalSectionEx
0x18000758a  movups  xmm0, xmmword ptr cs:aCtaskcounterCt; "CTaskCounter::CTaskCounter"
0x180007591  lea     rcx, [rbp+var_28]
0x180007595  mov     cs:qword_18002BE08, 0
0x1800075a0  movups  xmm1, xmmword ptr cs:aCtaskcounterCt+0Bh; "r::CTaskCounter"
0x1800075a7  mov     [rbp+var_38], rcx
0x1800075ab  lea     rcx, [rbp+var_50]
0x1800075af  mov     [rbp+var_30], rcx
0x1800075b3  lea     rcx, [rbp+var_38]
0x1800075b7  movups  xmmword ptr [rbp+var_28], xmm0
0x1800075bb  mov     cs:qword_18002BE10, 0
0x1800075c6  mov     [rbp+var_50], 0
0x1800075cd  movups  xmmword ptr [rbp+var_28+0Bh], xmm1
0x1800075d1  call    _lambda_3812f29f2bc42eee6a1ca7db246da244___operator__
0x1800075d6  lea     rcx, [rbp+var_38]
0x1800075da  mov     [rbp+var_50], 1
0x1800075e1  mov     [rbp+var_40], rcx
0x1800075e5  lea     rcx, [rbp+var_40]
0x1800075e9  call    WppTraceUnwinder__lambda_3812f29f2bc42eee6a1ca7db246da244_______WppTraceUnwinder__lambda_3812f29f2bc42eee6a1ca7db246da244____
0x1800075ee  mov     rax, rdi
0x1800075f1  mov     rcx, [rbp+var_8]
0x1800075f5  xor     rcx, rsp; StackCookie
0x1800075f8  call    __security_check_cookie
0x1800075fd  mov     rdi, [rsp+70h+arg_0]
0x180007605  add     rsp, 70h
0x180007609  pop     rbp
0x18000760a  retn
```

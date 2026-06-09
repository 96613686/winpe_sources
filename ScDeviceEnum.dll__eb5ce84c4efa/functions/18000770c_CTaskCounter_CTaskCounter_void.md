# CTaskCounter::~CTaskCounter(void)

- ea: `0x18000770c`
- end: `0x1800077a2`
- name: `??1CTaskCounter@@QEAA@XZ`
- size: `150`
- prototype: `void __fastcall(CTaskCounter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001f580`

## callees

- `0x180007680`
- `0x1800078e8`
- `0x180007b54`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007781`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007781`

## string_xrefs

- `0x180007731`: `CTaskCounter::~CTaskCounter`

## pseudocode

```c
void __fastcall CTaskCounter::~CTaskCounter(CTaskCounter *this)
{
  int v2; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v3; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
  char v5[32]; // [rsp+40h] [rbp-30h] BYREF

  v2 = 0;
  strcpy(v5, "CTaskCounter::~CTaskCounter");
  v4[0] = v5;
  v4[1] = &v2;
  lambda_4e0ccb10a9df4231d6aded5c1682d8c3_::operator()(v4);
  v2 = 1;
  v3 = v4;
  CTaskCounter::Cleanup();
  WppTraceUnwinder__lambda_4e0ccb10a9df4231d6aded5c1682d8c3____::_WppTraceUnwinder__lambda_4e0ccb10a9df4231d6aded5c1682d8c3____(&v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000770c  mov     [rsp-8+arg_8], rbx
0x180007711  push    rbp
0x180007712  mov     rbp, rsp
0x180007715  sub     rsp, 70h
0x180007719  mov     rax, cs:__security_cookie
0x180007720  xor     rax, rsp
0x180007723  mov     [rbp+var_10], rax
0x180007727  mov     rbx, rcx
0x18000772a  mov     [rbp+var_50], 0
0x180007731  movups  xmm0, xmmword ptr cs:aCtaskcounterCt_0; "CTaskCounter::~CTaskCounter"
0x180007738  movups  xmmword ptr [rbp+var_30], xmm0
0x18000773c  movups  xmm1, xmmword ptr cs:aCtaskcounterCt_0+0Ch; "::~CTaskCounter"
0x180007743  movups  xmmword ptr [rbp+var_30+0Ch], xmm1
0x180007747  lea     rax, [rbp+var_30]
0x18000774b  mov     [rbp+var_40], rax
0x18000774f  lea     rax, [rbp+var_50]
0x180007753  mov     [rbp+var_38], rax
0x180007757  lea     rcx, [rbp+var_40]
0x18000775b  call    _lambda_4e0ccb10a9df4231d6aded5c1682d8c3___operator__
0x180007760  mov     [rbp+var_50], 1
0x180007767  lea     rax, [rbp+var_40]
0x18000776b  mov     [rbp+var_48], rax
0x18000776f  call    ?Cleanup@CTaskCounter@@SAXXZ; CTaskCounter::Cleanup(void)
0x180007774  lea     rcx, [rbp+var_48]
0x180007778  call    WppTraceUnwinder__lambda_4e0ccb10a9df4231d6aded5c1682d8c3_______WppTraceUnwinder__lambda_4e0ccb10a9df4231d6aded5c1682d8c3____
0x18000777d  lea     rcx, [rbx+8]; lpCriticalSection
0x180007781  call    cs:__imp_DeleteCriticalSection
0x180007787  nop
0x180007788  mov     rcx, [rbp+var_10]
0x18000778c  xor     rcx, rsp; StackCookie
0x18000778f  call    __security_check_cookie
0x180007794  mov     rbx, [rsp+70h+arg_8]
0x18000779c  add     rsp, 70h
0x1800077a0  pop     rbp
0x1800077a1  retn
```

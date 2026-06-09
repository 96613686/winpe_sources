# std::_Throw_bad_array_new_length(void)

- ea: `0x1400041c4`
- end: `0x1400041fa`
- name: `?_Throw_bad_array_new_length@std@@YAXXZ`
- size: `54`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000345c`
- `0x14000354c`
- `0x1400036f0`
- `0x14000471c`

## callees

- `0x14000314b`

## pseudocode

```c
void __noreturn std::_Throw_bad_array_new_length(void)
{
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  pExceptionObject[2] = 0;
  pExceptionObject[1] = "bad array new length";
  pExceptionObject[0] = &std::bad_alloc::`vftable';
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x1400041c4  sub     rsp, 48h
0x1400041c8  xorps   xmm0, xmm0
0x1400041cb  lea     rax, aBadArrayNewLen; "bad array new length"
0x1400041d2  movups  [rsp+48h+var_20], xmm0
0x1400041d7  mov     qword ptr [rsp+48h+var_20], rax
0x1400041dc  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1400041e3  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1400041ea  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400041ef  mov     [rsp+48h+pExceptionObject], rax
0x1400041f4  call    _CxxThrowException_0
```

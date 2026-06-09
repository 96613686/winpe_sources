# std::_Throw_bad_array_new_length(void)

- ea: `0x180007a24`
- end: `0x180007a5a`
- name: `?_Throw_bad_array_new_length@std@@YAXXZ`
- size: `54`
- prototype: `void __noreturn(void)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180006190`
- `0x1800061d0`
- `0x180007dc0`
- `0x180007fe4`
- `0x180008010`
- `0x1800080c0`
- `0x18000a7f8`
- `0x18000ab8c`
- `0x18000d628`

## callees

- `0x180002876`

## pseudocode

```c
void __noreturn std::_Throw_bad_array_new_length(void)
{
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  pExceptionObject[2] = 0;
  pExceptionObject[1] = "bad array new length";
  pExceptionObject[0] = &std::bad_array_new_length::`vftable';
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x180007a24  sub     rsp, 48h
0x180007a28  xorps   xmm0, xmm0
0x180007a2b  lea     rax, aBadArrayNewLen; "bad array new length"
0x180007a32  movups  [rsp+48h+var_20], xmm0
0x180007a37  mov     qword ptr [rsp+48h+var_20], rax
0x180007a3c  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180007a43  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x180007a4a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180007a4f  mov     [rsp+48h+pExceptionObject], rax
0x180007a54  call    _CxxThrowException_0
```

# std::_Throw_bad_array_new_length(void)

- ea: `0x18000a694`
- end: `0x18000a6ca`
- name: `?_Throw_bad_array_new_length@std@@YAXXZ`
- size: `54`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004af4`
- `0x18000d990`
- `0x18000d9cc`
- `0x18000db50`
- `0x18000dc74`
- `0x18000f430`

## callees

- `0x180003668`

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
0x18000a694  sub     rsp, 48h
0x18000a698  xorps   xmm0, xmm0
0x18000a69b  lea     rax, aBadArrayNewLen; "bad array new length"
0x18000a6a2  movups  [rsp+48h+var_20], xmm0
0x18000a6a7  mov     qword ptr [rsp+48h+var_20], rax
0x18000a6ac  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000a6b3  lea     rax, ??_7bad_array_new_length@std@@6B@; const std::bad_array_new_length::`vftable'
0x18000a6ba  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000a6bf  mov     [rsp+48h+pExceptionObject], rax
0x18000a6c4  call    _CxxThrowException_0
```

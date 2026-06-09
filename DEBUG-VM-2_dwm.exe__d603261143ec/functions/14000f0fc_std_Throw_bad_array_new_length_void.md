# std::_Throw_bad_array_new_length(void)

- ea: `0x14000f0fc`
- end: `0x14000f123`
- name: `?_Throw_bad_array_new_length@std@@YAXXZ`
- size: `39`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc84`
- `0x14000dce4`
- `0x14000dd14`
- `0x14000dd48`

## callees

- `0x14000f0c0`

## pseudocode

```c
void __noreturn std::_Throw_bad_array_new_length(void)
{
  _QWORD v0[3]; // [rsp+20h] [rbp-18h] BYREF

  v0[1] = "bad array new length";
  v0[0] = &stdext::bad_array_new_length::`vftable';
  stdext::exception::_Raise((stdext::exception *)v0);
}

```

## disassembly

```asm
0x14000f0fc  sub     rsp, 38h
0x14000f100  lea     rax, aBadArrayNewLen; "bad array new length"
0x14000f107  mov     [rsp+38h+var_10], rax
0x14000f10c  lea     rcx, [rsp+38h+var_18]; this
0x14000f111  lea     rax, ??_7bad_array_new_length@stdext@@6B@; const stdext::bad_array_new_length::`vftable'
0x14000f118  mov     [rsp+38h+var_18], rax
0x14000f11d  call    ?_Raise@exception@stdext@@QEBAXXZ; stdext::exception::_Raise(void)
```

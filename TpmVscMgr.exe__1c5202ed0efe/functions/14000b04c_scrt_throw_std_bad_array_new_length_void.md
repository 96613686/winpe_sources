# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000b04c`
- end: `0x14000b06c`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140001990`
- `0x1400067e8`
- `0x1400069b0`
- `0x140006af4`
- `0x140006f18`
- `0x140007058`
- `0x1400074fc`
- `0x140007d04`
- `0x140007dc0`
- `0x14000b8e0`
- `0x14000cd00`
- `0x14000d5a8`
- `0x14000d858`
- `0x14000d974`
- `0x14000e870`
- `0x14000e9f8`

## callees

- `0x140002462`
- `0x140007f28`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x14000b04c  sub     rsp, 48h
0x14000b050  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000b055  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000b05a  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000b061  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b066  call    _CxxThrowException_0
```

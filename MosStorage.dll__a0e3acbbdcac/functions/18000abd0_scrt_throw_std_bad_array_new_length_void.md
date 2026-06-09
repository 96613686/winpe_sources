# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000abd0`
- end: `0x18000abf0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020a0`
- `0x18000694c`
- `0x180009790`
- `0x18000aa8c`
- `0x18000ac28`
- `0x18000c860`
- `0x18000d4e4`

## callees

- `0x18000280e`
- `0x180006bc4`

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
0x18000abd0  sub     rsp, 48h
0x18000abd4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000abd9  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000abde  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000abe5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000abea  call    _CxxThrowException_0
```

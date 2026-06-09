# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000c178`
- end: `0x18000c198`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002050`
- `0x18000a2a0`
- `0x18000a3e0`
- `0x18000be34`

## callees

- `0x180002a74`
- `0x18000a804`

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
0x18000c178  sub     rsp, 48h
0x18000c17c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000c181  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000c186  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000c18d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c192  call    _CxxThrowException_0
```

# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000a1a8`
- end: `0x14000a1c8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023ec`
- `0x140007020`
- `0x140007098`
- `0x1400074b8`
- `0x14000782c`
- `0x1400079a0`
- `0x140007c18`
- `0x140007d80`

## callees

- `0x140002c88`
- `0x14000832c`

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
0x14000a1a8  sub     rsp, 48h
0x14000a1ac  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000a1b1  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000a1b6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000a1bd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000a1c2  call    _CxxThrowException_0
```

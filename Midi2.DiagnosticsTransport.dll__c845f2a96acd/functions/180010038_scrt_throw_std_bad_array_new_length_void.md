# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180010038`
- end: `0x180010058`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003420`
- `0x18000c4c0`
- `0x18000c5cc`
- `0x18000c758`
- `0x18001148c`

## callees

- `0x180004188`
- `0x18000c8fc`

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
0x180010038  sub     rsp, 48h
0x18001003c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180010041  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180010046  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18001004d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010052  call    _CxxThrowException_0
```

# Concurrency::cancel_current_task(void)

- ea: `0x180002e68`
- end: `0x180002e88`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002e88`
- `0x18000e7e4`
- `0x18000e9b4`
- `0x180013ee4`
- `0x180017f70`

## callees

- `0x180002d1c`
- `0x18001a980`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180002D1C(v0);
  sub_18001A980(v0, &_TI3_AVbad_array_new_length_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x180002e68  sub     rsp, 48h
0x180002e6c  lea     rcx, [rsp+48h+var_28]
0x180002e71  call    sub_180002D1C
0x180002e76  lea     rdx, __TI3?AVbad_array_new_length@std@@; throw info for 'class std::bad_array_new_length'
0x180002e7d  lea     rcx, [rsp+48h+var_28]
0x180002e82  call    sub_18001A980
0x180002e87  int     3; Trap to Debugger
```

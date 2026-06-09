# Concurrency::cancel_current_task(void)

- ea: `0x180003090`
- end: `0x1800030b0`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800030b0`
- `0x1800052bc`
- `0x1800065b8`
- `0x180006780`
- `0x180014e3c`
- `0x180015208`
- `0x180018d78`
- `0x18001b088`
- `0x18001b2ac`
- `0x18001e6fc`
- `0x180027d74`

## callees

- `0x180002fd4`
- `0x18002a834`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180002FD4(v0);
  sub_18002A834(v0, &_TI3_AVbad_array_new_length_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x180003090  sub     rsp, 48h
0x180003094  lea     rcx, [rsp+48h+var_28]
0x180003099  call    sub_180002FD4
0x18000309e  lea     rdx, __TI3?AVbad_array_new_length@std@@; throw info for 'class std::bad_array_new_length'
0x1800030a5  lea     rcx, [rsp+48h+var_28]
0x1800030aa  call    sub_18002A834
0x1800030af  int     3; Trap to Debugger
```

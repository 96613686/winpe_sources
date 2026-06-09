# Concurrency::cancel_current_task(void)

- ea: `0x1800188dc`
- end: `0x1800188fc`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017f70`

## callees

- `0x18000f138`
- `0x18001a980`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_18000F138(v0);
  sub_18001A980(v0, &_TI2_AVbad_alloc_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x1800188dc  sub     rsp, 48h
0x1800188e0  lea     rcx, [rsp+48h+var_28]
0x1800188e5  call    sub_18000F138
0x1800188ea  lea     rdx, __TI2?AVbad_alloc@std@@; throw info for 'class std::bad_alloc'
0x1800188f1  lea     rcx, [rsp+48h+var_28]
0x1800188f6  call    sub_18001A980
0x1800188fb  int     3; Trap to Debugger
```

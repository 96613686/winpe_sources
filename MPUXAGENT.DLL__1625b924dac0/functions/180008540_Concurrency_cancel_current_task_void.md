# Concurrency::cancel_current_task(void)

- ea: `0x180008540`
- end: `0x180008560`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800087a0`
- `0x180009f78`
- `0x1800363cc`

## callees

- `0x180008498`
- `0x18000b8ec`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180008498(v0);
  sub_18000B8EC(v0, &_TI2_AVbad_alloc_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x180008540  sub     rsp, 48h
0x180008544  lea     rcx, [rsp+48h+var_28]
0x180008549  call    sub_180008498
0x18000854e  lea     rdx, __TI2?AVbad_alloc@std@@; throw info for 'class std::bad_alloc'
0x180008555  lea     rcx, [rsp+48h+var_28]
0x18000855a  call    sub_18000B8EC
0x18000855f  int     3; Trap to Debugger
```

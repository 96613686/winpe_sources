# Concurrency::cancel_current_task(void)

- ea: `0x18013e1dc`
- end: `0x18013e1fc`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180130578`
- `0x180134310`
- `0x1801345c0`
- `0x18013680c`

## callees

- `0x18013e118`
- `0x180183f30`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_18013E118(v0);
  sub_180183F30(v0, &_TI3_AVlength_error_std__);
  JUMPOUT(0x18013E1FBLL);
}

```

## disassembly

```asm
0x18013e1dc  sub     rsp, 48h
0x18013e1e0  lea     rcx, [rsp+48h+var_28]
0x18013e1e5  call    sub_18013E118
0x18013e1ea  lea     rdx, __TI3?AVlength_error@std@@; throw info for 'class std::length_error'
0x18013e1f1  lea     rcx, [rsp+48h+var_28]
0x18013e1f6  call    sub_180183F30
```

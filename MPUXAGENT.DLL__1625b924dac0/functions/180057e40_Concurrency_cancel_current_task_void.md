# Concurrency::cancel_current_task(void)

- ea: `0x180057e40`
- end: `0x180057e60`
- name: `?cancel_current_task@Concurrency@@YAXXZ_1`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180035eac`

## callees

- `0x18000b8ec`
- `0x180036c90`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180036C90(v0);
  sub_18000B8EC(v0, &_TI2_AVbad_cast_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x180057e40  sub     rsp, 48h
0x180057e44  lea     rcx, [rsp+48h+var_28]
0x180057e49  call    sub_180036C90
0x180057e4e  lea     rdx, __TI2?AVbad_cast@std@@; throw info for 'class std::bad_cast'
0x180057e55  lea     rcx, [rsp+48h+var_28]
0x180057e5a  call    sub_18000B8EC
0x180057e5f  int     3; Trap to Debugger
```

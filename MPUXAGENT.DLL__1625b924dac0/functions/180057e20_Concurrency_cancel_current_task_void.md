# Concurrency::cancel_current_task(void)

- ea: `0x180057e20`
- end: `0x180057e40`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `22`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009f78`
- `0x1800345b0`
- `0x180034a38`
- `0x180034c4c`
- `0x180034e00`
- `0x180034ed8`
- `0x180035354`
- `0x18003548c`
- `0x18003561c`
- `0x1800358f0`
- `0x1800362a4`
- `0x18005753c`
- `0x180057734`
- `0x180058a10`
- `0x18005fd20`
- `0x18006019c`
- `0x180060e84`
- `0x180063ac8`
- `0x180063d50`
- `0x180063ed4`
- `0x180065ce8`
- `0x180066fec`

## callees

- `0x18000b8ec`
- `0x180036c30`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180036C30(v0);
  sub_18000B8EC(v0, &_TI3_AVbad_array_new_length_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x180057e20  sub     rsp, 48h
0x180057e24  lea     rcx, [rsp+48h+var_28]
0x180057e29  call    sub_180036C30
0x180057e2e  lea     rdx, __TI3?AVbad_array_new_length@std@@; throw info for 'class std::bad_array_new_length'
0x180057e35  lea     rcx, [rsp+48h+var_28]
0x180057e3a  call    sub_18000B8EC
0x180057e3f  int     3; Trap to Debugger
```

# Concurrency::cancel_current_task(void)

- ea: `0x1800286e8`
- end: `0x180028708`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180027d74`

## callees

- `0x180004218`
- `0x18002a834`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180004218(v0);
  sub_18002A834(v0, &_TI2_AVbad_alloc_std__);
  __debugbreak();
}

```

## disassembly

```asm
0x1800286e8  sub     rsp, 48h
0x1800286ec  lea     rcx, [rsp+48h+var_28]
0x1800286f1  call    sub_180004218
0x1800286f6  lea     rdx, __TI2?AVbad_alloc@std@@; throw info for 'class std::bad_alloc'
0x1800286fd  lea     rcx, [rsp+48h+var_28]
0x180028702  call    sub_18002A834
0x180028707  int     3; Trap to Debugger
```

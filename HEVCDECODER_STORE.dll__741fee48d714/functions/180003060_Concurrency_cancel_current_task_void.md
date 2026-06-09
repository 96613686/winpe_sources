# Concurrency::cancel_current_task(void)

- ea: `0x180003060`
- end: `0x180003080`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `18`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800095d0`
- `0x180009ad0`
- `0x18002b070`
- `0x18002c6f0`
- `0x18002ca70`
- `0x18002cc70`
- `0x180059920`
- `0x1800607f0`
- `0x180060950`
- `0x180062640`
- `0x1800704a0`
- `0x180070670`
- `0x1800707d0`
- `0x180088360`
- `0x1800884e0`
- `0x1800aa8c0`
- `0x1800aaf70`
- `0x1800ad550`

## callees

- `0x180003010`
- `0x18016aea0`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE v0[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180003010(v0);
  sub_18016AEA0(v0, &_TI3_AVbad_array_new_length_std__);
  JUMPOUT(0x18000307FLL);
}

```

## disassembly

```asm
0x180003060  sub     rsp, 48h
0x180003064  lea     rcx, [rsp+48h+var_28]
0x180003069  call    sub_180003010
0x18000306e  lea     rdx, __TI3?AVbad_array_new_length@std@@; throw info for 'class std::bad_array_new_length'
0x180003075  lea     rcx, [rsp+48h+var_28]
0x18000307a  call    sub_18016AEA0
```

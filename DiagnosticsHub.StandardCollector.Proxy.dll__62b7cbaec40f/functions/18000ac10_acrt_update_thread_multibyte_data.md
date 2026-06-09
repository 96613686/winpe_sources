# __acrt_update_thread_multibyte_data

- ea: `0x18000ac10`
- end: `0x18000ac2c`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800115d4`
- `0x1800135f4`
- `0x180013628`

## callees

- `0x180006ef0`
- `0x18000aad4`

## pseudocode

```c
volatile signed __int32 *_acrt_update_thread_multibyte_data()
{
  __int64 v0; // rax

  v0 = _acrt_getptd();
  return update_thread_multibyte_data_internal(v0, (volatile signed __int32 **)&_acrt_current_multibyte_data);
}

```

## disassembly

```asm
0x18000ac10  sub     rsp, 28h
0x18000ac14  call    __acrt_getptd
0x18000ac19  lea     rdx, __acrt_current_multibyte_data
0x18000ac20  mov     rcx, rax
0x18000ac23  add     rsp, 28h
0x18000ac27  jmp     update_thread_multibyte_data_internal
```

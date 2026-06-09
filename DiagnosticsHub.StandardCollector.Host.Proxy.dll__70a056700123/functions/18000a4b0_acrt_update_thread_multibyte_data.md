# __acrt_update_thread_multibyte_data

- ea: `0x18000a4b0`
- end: `0x18000a4cc`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180010e74`
- `0x180012e94`
- `0x180012ec8`

## callees

- `0x180006790`
- `0x18000a374`

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
0x18000a4b0  sub     rsp, 28h
0x18000a4b4  call    __acrt_getptd
0x18000a4b9  lea     rdx, __acrt_current_multibyte_data
0x18000a4c0  mov     rcx, rax
0x18000a4c3  add     rsp, 28h
0x18000a4c7  jmp     update_thread_multibyte_data_internal
```

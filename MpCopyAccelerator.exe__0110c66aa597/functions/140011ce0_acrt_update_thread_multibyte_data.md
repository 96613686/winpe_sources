# __acrt_update_thread_multibyte_data

- ea: `0x140011ce0`
- end: `0x140011cfc`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140013da0`
- `0x140013dd4`

## callees

- `0x140011bc0`
- `0x140013b68`

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
0x140011ce0  sub     rsp, 28h
0x140011ce4  call    __acrt_getptd
0x140011ce9  lea     rdx, __acrt_current_multibyte_data
0x140011cf0  mov     rcx, rax
0x140011cf3  add     rsp, 28h
0x140011cf7  jmp     update_thread_multibyte_data_internal
```

# __acrt_update_thread_multibyte_data

- ea: `0x1800134b0`
- end: `0x1800134cc`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180010d24`

## callees

- `0x1800102a4`
- `0x180013398`

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
0x1800134b0  sub     rsp, 28h
0x1800134b4  call    __acrt_getptd
0x1800134b9  mov     rcx, rax
0x1800134bc  lea     rdx, __acrt_current_multibyte_data
0x1800134c3  add     rsp, 28h
0x1800134c7  jmp     update_thread_multibyte_data_internal
```

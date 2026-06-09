# int `update_thread_multibyte_data_internal(__acrt_ptd * const,update_thread_multibyte_data_internal * * const)'::`1'::fin$0

- ea: `0x14002b0ef`
- end: `0x14002b108`
- name: `?fin$0@?0??update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z@4HA`
- size: `25`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14001b558`

## pseudocode

```c
__int64 `update_thread_multibyte_data_internal'::`1'::fin$0()
{
  return _vcrt_unlock(5);
}

```

## disassembly

```asm
0x14002b0ef  push    rbp
0x14002b0f1  sub     rsp, 20h
0x14002b0f5  mov     rbp, rdx
0x14002b0f8  mov     ecx, 5
0x14002b0fd  add     rsp, 20h
0x14002b101  pop     rbp
0x14002b102  jmp     __vcrt_unlock
```

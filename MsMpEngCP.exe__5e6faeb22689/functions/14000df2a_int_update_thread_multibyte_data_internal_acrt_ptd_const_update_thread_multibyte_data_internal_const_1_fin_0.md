# int `update_thread_multibyte_data_internal(__acrt_ptd * const,update_thread_multibyte_data_internal * * const)'::`1'::fin$0

- ea: `0x14000df2a`
- end: `0x14000df43`
- name: `?fin$0@?0??update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z@4HA`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140008248`

## pseudocode

```c
__int64 `update_thread_multibyte_data_internal'::`1'::fin$0()
{
  return sub_140008248(5);
}

```

## disassembly

```asm
0x14000df2a  push    rbp
0x14000df2c  sub     rsp, 20h
0x14000df30  mov     rbp, rdx
0x14000df33  mov     ecx, 5
0x14000df38  add     rsp, 20h
0x14000df3c  pop     rbp
0x14000df3d  jmp     sub_140008248
```

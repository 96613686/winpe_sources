# __acrt_update_thread_multibyte_data

- ea: `0x140007850`
- end: `0x14000786c`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000a440`
- `0x14000a474`

## callees

- `0x140005fe8`
- `0x140007730`

## pseudocode

```c
struct __crt_multibyte_data *_acrt_update_thread_multibyte_data()
{
  struct __acrt_ptd *v0; // rax

  v0 = (struct __acrt_ptd *)sub_140005FE8();
  return update_thread_multibyte_data_internal(v0, &Block);
}

```

## disassembly

```asm
0x140007850  sub     rsp, 28h
0x140007854  call    sub_140005FE8
0x140007859  lea     rdx, Block; struct __crt_multibyte_data **
0x140007860  mov     rcx, rax; struct __acrt_ptd *
0x140007863  add     rsp, 28h
0x140007867  jmp     ?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z
```

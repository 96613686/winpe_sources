# __acrt_update_thread_multibyte_data

- ea: `0x140017820`
- end: `0x14001783c`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: `struct __crt_multibyte_data *()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140019890`
- `0x1400198c4`

## callees

- `0x140017708`
- `0x140019658`

## pseudocode

```c
struct __crt_multibyte_data *_acrt_update_thread_multibyte_data()
{
  struct __acrt_ptd *v0; // rax

  v0 = (struct __acrt_ptd *)sub_140019658();
  return update_thread_multibyte_data_internal(v0, &qword_14003E2B8);
}

```

## disassembly

```asm
0x140017820  sub     rsp, 28h
0x140017824  call    sub_140019658
0x140017829  lea     rdx, qword_14003E2B8; struct __crt_multibyte_data **
0x140017830  mov     rcx, rax; struct __acrt_ptd *
0x140017833  add     rsp, 28h
0x140017837  jmp     ?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z
```

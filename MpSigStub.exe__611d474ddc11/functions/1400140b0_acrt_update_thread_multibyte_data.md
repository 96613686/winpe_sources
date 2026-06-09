# __acrt_update_thread_multibyte_data

- ea: `0x1400140b0`
- end: `0x1400140cc`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: `struct __crt_multibyte_data *()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140010310`
- `0x140010344`

## callees

- `0x14000ff40`
- `0x140013f94`

## pseudocode

```c
struct __crt_multibyte_data *_acrt_update_thread_multibyte_data()
{
  struct __acrt_ptd *v0; // rax

  v0 = (struct __acrt_ptd *)_acrt_getptd();
  return update_thread_multibyte_data_internal(v0, &qword_1400D71D8);
}

```

## disassembly

```asm
0x1400140b0  sub     rsp, 28h
0x1400140b4  call    __acrt_getptd
0x1400140b9  lea     rdx, qword_1400D71D8; struct __crt_multibyte_data **
0x1400140c0  mov     rcx, rax; struct __acrt_ptd *
0x1400140c3  add     rsp, 28h
0x1400140c7  jmp     ?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z
```

# __acrt_update_thread_locale_data

- ea: `0x14001ee3c`
- end: `0x14001eeaa`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140019824`
- `0x140019858`

## callees

- `0x140019148`
- `0x140019658`
- `0x14001b4f8`
- `0x14001b558`
- `0x14001ee3c`
- `0x14001eeac`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = sub_140019658();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & dword_14003CA80) == 0 || (v2 = *v1) == 0 )
  {
    _vcrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1, qword_14003E5A8);
    _vcrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x14001ee3c  mov     [rsp+arg_0], rbx
0x14001ee41  push    rdi
0x14001ee42  sub     rsp, 20h
0x14001ee46  call    sub_140019658
0x14001ee4b  lea     rdi, [rax+90h]
0x14001ee52  mov     ecx, [rax+3A8h]
0x14001ee58  mov     eax, cs:dword_14003CA80
0x14001ee5e  test    eax, ecx
0x14001ee60  jz      short loc_14001EE6A
0x14001ee62  mov     rbx, [rdi]
0x14001ee65  test    rbx, rbx
0x14001ee68  jnz     short loc_14001EE96
0x14001ee6a  mov     ecx, 4
0x14001ee6f  call    __vcrt_lock
0x14001ee74  nop
0x14001ee75  mov     rdx, cs:qword_14003E5A8
0x14001ee7c  mov     rcx, rdi
0x14001ee7f  call    _updatetlocinfoEx_nolock
0x14001ee84  mov     rbx, rax
0x14001ee87  mov     ecx, 4
0x14001ee8c  call    __vcrt_unlock
0x14001ee91  test    rbx, rbx
0x14001ee94  jz      short loc_14001EEA4
0x14001ee96  mov     rax, rbx
0x14001ee99  mov     rbx, [rsp+28h+arg_0]
0x14001ee9e  add     rsp, 20h
0x14001eea2  pop     rdi
0x14001eea3  retn
0x14001eea4  call    abort
0x14002b218  push    rbp; Microsoft VisualC 64bit universal runtime
0x14002b21a  sub     rsp, 20h
0x14002b21e  mov     rbp, rdx
0x14002b221  mov     ecx, 4
0x14002b226  add     rsp, 20h
0x14002b22a  pop     rbp
0x14002b22b  jmp     __vcrt_unlock
```

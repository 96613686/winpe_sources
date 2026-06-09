# __acrt_update_thread_locale_data

- ea: `0x18000fb1c`
- end: `0x18000fb8a`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010e74`
- `0x1800110e8`
- `0x180012e28`
- `0x180012e5c`

## callees

- `0x180006790`
- `0x1800069b8`
- `0x180006a18`
- `0x18000f790`
- `0x18000fb1c`
- `0x18000fb8c`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & _globallocalestatus) == 0 || (v2 = *v1) == 0 )
  {
    _acrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1, _acrt_current_locale_data);
    _acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x18000fb1c  mov     [rsp+arg_0], rbx
0x18000fb21  push    rdi
0x18000fb22  sub     rsp, 20h
0x18000fb26  call    __acrt_getptd
0x18000fb2b  lea     rdi, [rax+90h]
0x18000fb32  mov     ecx, [rax+3A8h]
0x18000fb38  mov     eax, cs:__globallocalestatus
0x18000fb3e  test    eax, ecx
0x18000fb40  jz      short loc_18000FB4A
0x18000fb42  mov     rbx, [rdi]
0x18000fb45  test    rbx, rbx
0x18000fb48  jnz     short loc_18000FB76
0x18000fb4a  mov     ecx, 4
0x18000fb4f  call    __acrt_lock
0x18000fb54  nop
0x18000fb55  mov     rdx, cs:__acrt_current_locale_data
0x18000fb5c  mov     rcx, rdi
0x18000fb5f  call    _updatetlocinfoEx_nolock
0x18000fb64  mov     rbx, rax
0x18000fb67  mov     ecx, 4
0x18000fb6c  call    __acrt_unlock
0x18000fb71  test    rbx, rbx
0x18000fb74  jz      short loc_18000FB84
0x18000fb76  mov     rax, rbx
0x18000fb79  mov     rbx, [rsp+28h+arg_0]
0x18000fb7e  add     rsp, 20h
0x18000fb82  pop     rdi
0x18000fb83  retn
0x18000fb84  call    abort
0x18006115c  push    rbp
0x18006115e  sub     rsp, 20h
0x180061162  mov     rbp, rdx
0x180061165  mov     ecx, 4
0x18006116a  add     rsp, 20h
0x18006116e  pop     rbp
0x18006116f  jmp     __acrt_unlock
```

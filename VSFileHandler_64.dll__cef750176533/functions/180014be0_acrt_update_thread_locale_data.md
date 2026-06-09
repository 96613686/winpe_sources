# __acrt_update_thread_locale_data

- ea: `0x180014be0`
- end: `0x180014c4e`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010cf0`

## callees

- `0x18000e7c8`
- `0x1800102a4`
- `0x180011ff8`
- `0x180012058`
- `0x180014be0`
- `0x180014c50`

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
0x180014be0  mov     [rsp+arg_0], rbx
0x180014be5  push    rdi
0x180014be6  sub     rsp, 20h
0x180014bea  call    __acrt_getptd
0x180014bef  lea     rdi, [rax+90h]
0x180014bf6  mov     ecx, [rax+3A8h]
0x180014bfc  mov     eax, cs:__globallocalestatus
0x180014c02  test    eax, ecx
0x180014c04  jz      short loc_180014C0E
0x180014c06  mov     rbx, [rdi]
0x180014c09  test    rbx, rbx
0x180014c0c  jnz     short loc_180014C3A
0x180014c0e  mov     ecx, 4
0x180014c13  call    __acrt_lock
0x180014c18  nop
0x180014c19  mov     rdx, cs:__acrt_current_locale_data
0x180014c20  mov     rcx, rdi
0x180014c23  call    _updatetlocinfoEx_nolock
0x180014c28  mov     rbx, rax
0x180014c2b  mov     ecx, 4
0x180014c30  call    __acrt_unlock
0x180014c35  test    rbx, rbx
0x180014c38  jz      short loc_180014C48
0x180014c3a  mov     rax, rbx
0x180014c3d  mov     rbx, [rsp+28h+arg_0]
0x180014c42  add     rsp, 20h
0x180014c46  pop     rdi
0x180014c47  retn
0x180014c48  call    abort
0x18002527b  push    rbp
0x18002527d  sub     rsp, 20h
0x180025281  mov     rbp, rdx
0x180025284  mov     ecx, 4
0x180025289  add     rsp, 20h
0x18002528d  pop     rbp
0x18002528e  jmp     __acrt_unlock
```

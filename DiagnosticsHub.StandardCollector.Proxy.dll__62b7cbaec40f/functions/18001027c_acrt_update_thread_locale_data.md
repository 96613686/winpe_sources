# __acrt_update_thread_locale_data

- ea: `0x18001027c`
- end: `0x1800102ea`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800115d4`
- `0x180011848`
- `0x180013588`
- `0x1800135bc`

## callees

- `0x180006ef0`
- `0x180007118`
- `0x180007178`
- `0x18000fef0`
- `0x18001027c`
- `0x1800102ec`

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
0x18001027c  mov     [rsp+arg_0], rbx
0x180010281  push    rdi
0x180010282  sub     rsp, 20h
0x180010286  call    __acrt_getptd
0x18001028b  lea     rdi, [rax+90h]
0x180010292  mov     ecx, [rax+3A8h]
0x180010298  mov     eax, cs:__globallocalestatus
0x18001029e  test    eax, ecx
0x1800102a0  jz      short loc_1800102AA
0x1800102a2  mov     rbx, [rdi]
0x1800102a5  test    rbx, rbx
0x1800102a8  jnz     short loc_1800102D6
0x1800102aa  mov     ecx, 4
0x1800102af  call    __acrt_lock
0x1800102b4  nop
0x1800102b5  mov     rdx, cs:__acrt_current_locale_data
0x1800102bc  mov     rcx, rdi
0x1800102bf  call    _updatetlocinfoEx_nolock
0x1800102c4  mov     rbx, rax
0x1800102c7  mov     ecx, 4
0x1800102cc  call    __acrt_unlock
0x1800102d1  test    rbx, rbx
0x1800102d4  jz      short loc_1800102E4
0x1800102d6  mov     rax, rbx
0x1800102d9  mov     rbx, [rsp+28h+arg_0]
0x1800102de  add     rsp, 20h
0x1800102e2  pop     rdi
0x1800102e3  retn
0x1800102e4  call    abort
0x18006143c  push    rbp
0x18006143e  sub     rsp, 20h
0x180061442  mov     rbp, rdx
0x180061445  mov     ecx, 4
0x18006144a  add     rsp, 20h
0x18006144e  pop     rbp
0x18006144f  jmp     __acrt_unlock
```

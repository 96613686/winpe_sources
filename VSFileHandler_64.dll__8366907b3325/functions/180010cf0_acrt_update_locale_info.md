# __acrt_update_locale_info

- ea: `0x180010cf0`
- end: `0x180010d21`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000c5a4`
- `0x180014700`
- `0x18001b3f0`
- `0x18001b4a0`

## callees

- `0x180010cf0`
- `0x180014be0`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = _acrt_current_locale_data;
  if ( *a2 != _acrt_current_locale_data )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_locale_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010cf0  push    rbx
0x180010cf2  sub     rsp, 20h
0x180010cf6  mov     rax, cs:__acrt_current_locale_data
0x180010cfd  mov     rbx, rdx
0x180010d00  cmp     [rdx], rax
0x180010d03  jz      short loc_180010D1B
0x180010d05  mov     eax, [rcx+3A8h]
0x180010d0b  test    cs:__globallocalestatus, eax
0x180010d11  jnz     short loc_180010D1B
0x180010d13  call    __acrt_update_thread_locale_data
0x180010d18  mov     [rbx], rax
0x180010d1b  add     rsp, 20h
0x180010d1f  pop     rbx
0x180010d20  retn
```

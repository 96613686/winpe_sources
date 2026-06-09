# __acrt_update_locale_info

- ea: `0x140013d34`
- end: `0x140013d65`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b800`
- `0x14000b980`
- `0x14000c1f0`
- `0x14001b230`

## callees

- `0x140013d34`
- `0x14001804c`

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
0x140013d34  push    rbx
0x140013d36  sub     rsp, 20h
0x140013d3a  mov     rax, cs:__acrt_current_locale_data
0x140013d41  mov     rbx, rdx
0x140013d44  cmp     [rdx], rax
0x140013d47  jz      short loc_140013D5F
0x140013d49  mov     eax, [rcx+3A8h]
0x140013d4f  test    cs:__globallocalestatus, eax
0x140013d55  jnz     short loc_140013D5F
0x140013d57  call    __acrt_update_thread_locale_data
0x140013d5c  mov     [rbx], rax
0x140013d5f  add     rsp, 20h
0x140013d63  pop     rbx
0x140013d64  retn
```

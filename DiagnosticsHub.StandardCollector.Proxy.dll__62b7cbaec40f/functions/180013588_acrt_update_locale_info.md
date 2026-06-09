# __acrt_update_locale_info

- ea: `0x180013588`
- end: `0x1800135b9`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800093a4`
- `0x18000fad0`
- `0x180013d00`
- `0x180013ea0`
- `0x180014020`
- `0x1800141d0`
- `0x1800160a0`
- `0x1800160d4`
- `0x1800173ac`
- `0x1800173dc`
- `0x18001740c`
- `0x180017440`
- `0x18001a700`
- `0x18001aa20`
- `0x180020de0`

## callees

- `0x18001027c`
- `0x180013588`

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
0x180013588  push    rbx
0x18001358a  sub     rsp, 20h
0x18001358e  mov     rax, cs:__acrt_current_locale_data
0x180013595  mov     rbx, rdx
0x180013598  cmp     [rdx], rax
0x18001359b  jz      short loc_1800135B3
0x18001359d  mov     eax, [rcx+3A8h]
0x1800135a3  test    cs:__globallocalestatus, eax
0x1800135a9  jnz     short loc_1800135B3
0x1800135ab  call    __acrt_update_thread_locale_data
0x1800135b0  mov     [rbx], rax
0x1800135b3  add     rsp, 20h
0x1800135b7  pop     rbx
0x1800135b8  retn
```

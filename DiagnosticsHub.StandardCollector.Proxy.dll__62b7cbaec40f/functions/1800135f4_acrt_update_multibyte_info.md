# __acrt_update_multibyte_info

- ea: `0x1800135f4`
- end: `0x180013625`
- name: `__acrt_update_multibyte_info`
- size: `49`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800093a4`
- `0x180013d00`
- `0x180013ea0`
- `0x180014020`
- `0x1800141d0`
- `0x18001a700`
- `0x18001aa20`
- `0x180020de0`

## callees

- `0x18000ac10`
- `0x1800135f4`

## pseudocode

```c
__int64 __fastcall _acrt_update_multibyte_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = (__int64)_acrt_current_multibyte_data;
  if ( (void *)*a2 != _acrt_current_multibyte_data )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_multibyte_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800135f4  push    rbx
0x1800135f6  sub     rsp, 20h
0x1800135fa  mov     rax, cs:__acrt_current_multibyte_data
0x180013601  mov     rbx, rdx
0x180013604  cmp     [rdx], rax
0x180013607  jz      short loc_18001361F
0x180013609  mov     eax, [rcx+3A8h]
0x18001360f  test    cs:__globallocalestatus, eax
0x180013615  jnz     short loc_18001361F
0x180013617  call    __acrt_update_thread_multibyte_data
0x18001361c  mov     [rbx], rax
0x18001361f  add     rsp, 20h
0x180013623  pop     rbx
0x180013624  retn
```

# __acrt_update_multibyte_info

- ea: `0x180010d24`
- end: `0x180010d55`
- name: `__acrt_update_multibyte_info`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000c5a4`

## callees

- `0x180010d24`
- `0x1800134b0`

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
0x180010d24  push    rbx
0x180010d26  sub     rsp, 20h
0x180010d2a  mov     rax, cs:__acrt_current_multibyte_data
0x180010d31  mov     rbx, rdx
0x180010d34  cmp     [rdx], rax
0x180010d37  jz      short loc_180010D4F
0x180010d39  mov     eax, [rcx+3A8h]
0x180010d3f  test    cs:__globallocalestatus, eax
0x180010d45  jnz     short loc_180010D4F
0x180010d47  call    __acrt_update_thread_multibyte_data
0x180010d4c  mov     [rbx], rax
0x180010d4f  add     rsp, 20h
0x180010d53  pop     rbx
0x180010d54  retn
```

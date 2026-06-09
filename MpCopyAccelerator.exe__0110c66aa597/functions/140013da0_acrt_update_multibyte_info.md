# __acrt_update_multibyte_info

- ea: `0x140013da0`
- end: `0x140013dd1`
- name: `__acrt_update_multibyte_info`
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

- `0x140011ce0`
- `0x140013da0`

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
0x140013da0  push    rbx
0x140013da2  sub     rsp, 20h
0x140013da6  mov     rax, cs:__acrt_current_multibyte_data
0x140013dad  mov     rbx, rdx
0x140013db0  cmp     [rdx], rax
0x140013db3  jz      short loc_140013DCB
0x140013db5  mov     eax, [rcx+3A8h]
0x140013dbb  test    cs:__globallocalestatus, eax
0x140013dc1  jnz     short loc_140013DCB
0x140013dc3  call    __acrt_update_thread_multibyte_data
0x140013dc8  mov     [rbx], rax
0x140013dcb  add     rsp, 20h
0x140013dcf  pop     rbx
0x140013dd0  retn
```

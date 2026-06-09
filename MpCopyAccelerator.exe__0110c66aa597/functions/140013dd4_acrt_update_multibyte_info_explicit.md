# __acrt_update_multibyte_info_explicit

- ea: `0x140013dd4`
- end: `0x140013e09`
- name: `__acrt_update_multibyte_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c750`

## callees

- `0x140011ce0`
- `0x140013dd4`

## pseudocode

```c
volatile signed __int32 *__fastcall _acrt_update_multibyte_info_explicit(
        __int64 a1,
        volatile signed __int32 **a2,
        __int64 a3)
{
  volatile signed __int32 *result; // rax

  result = (volatile signed __int32 *)*(&_acrt_current_multibyte_data + a3);
  if ( *a2 != result )
  {
    result = (volatile signed __int32 *)*(unsigned int *)(a1 + 936);
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
0x140013dd4  push    rbx
0x140013dd6  sub     rsp, 20h
0x140013dda  lea     rax, __acrt_current_multibyte_data
0x140013de1  mov     rbx, rdx
0x140013de4  mov     rax, [rax+r8*8]
0x140013de8  cmp     [rdx], rax
0x140013deb  jz      short loc_140013E03
0x140013ded  mov     eax, [rcx+3A8h]
0x140013df3  test    cs:__globallocalestatus, eax
0x140013df9  jnz     short loc_140013E03
0x140013dfb  call    __acrt_update_thread_multibyte_data
0x140013e00  mov     [rbx], rax
0x140013e03  add     rsp, 20h
0x140013e07  pop     rbx
0x140013e08  retn
```

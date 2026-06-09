# __acrt_update_locale_info_explicit

- ea: `0x140013d68`
- end: `0x140013d9d`
- name: `__acrt_update_locale_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c750`

## callees

- `0x140013d68`
- `0x14001804c`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info_explicit(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 result; // rax

  result = _acrt_current_locale_data[a3];
  if ( *a2 != result )
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
0x140013d68  push    rbx
0x140013d6a  sub     rsp, 20h
0x140013d6e  lea     rax, __acrt_current_locale_data
0x140013d75  mov     rbx, rdx
0x140013d78  mov     rax, [rax+r8*8]
0x140013d7c  cmp     [rdx], rax
0x140013d7f  jz      short loc_140013D97
0x140013d81  mov     eax, [rcx+3A8h]
0x140013d87  test    cs:__globallocalestatus, eax
0x140013d8d  jnz     short loc_140013D97
0x140013d8f  call    __acrt_update_thread_locale_data
0x140013d94  mov     [rbx], rax
0x140013d97  add     rsp, 20h
0x140013d9b  pop     rbx
0x140013d9c  retn
```

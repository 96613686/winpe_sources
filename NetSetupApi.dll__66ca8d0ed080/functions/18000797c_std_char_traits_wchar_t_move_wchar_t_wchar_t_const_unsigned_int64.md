# std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)

- ea: `0x18000797c`
- end: `0x180007998`
- name: `?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059dc`
- `0x180007478`
- `0x180007528`
- `0x1800076b8`

## callees

- `0x18000797c`
- `0x180008982`

## pseudocode

```c
void *__fastcall std::char_traits<wchar_t>::move(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memmove_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x18000797c  sub     rsp, 28h
0x180007980  test    r8, r8
0x180007983  jz      short loc_180007990
0x180007985  add     r8, r8; Size
0x180007988  call    memmove_0
0x18000798d  mov     rcx, rax
0x180007990  mov     rax, rcx
0x180007993  add     rsp, 28h
0x180007997  retn
```

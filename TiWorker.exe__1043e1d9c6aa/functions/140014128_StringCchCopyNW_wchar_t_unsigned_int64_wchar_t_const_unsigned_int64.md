# StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x140014128`
- end: `0x1400141a5`
- name: `?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z`
- size: `125`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400149ec`
- `0x140015228`
- `0x1400164c0`

## callees

- `0x140014128`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(wchar_t *a1, unsigned __int64 a2, wchar_t *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  wchar_t *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x140014128  mov     [rsp+arg_0], rbx
0x14001412d  xor     ebx, ebx
0x14001412f  mov     r10, rdx
0x140014132  mov     r11, rcx
0x140014135  test    rdx, rdx
0x140014138  jz      short loc_140014190
0x14001413a  cmp     rdx, 7FFFFFFFh
0x140014141  jbe     short loc_14001414A
0x140014143  mov     edx, 80070057h
0x140014148  jmp     short loc_14001419A
0x14001414a  cmp     r9, 7FFFFFFEh
0x140014151  ja      short loc_140014143
0x140014153  test    r9, r9
0x140014156  jz      short loc_140014176
0x140014158  movzx   eax, word ptr [r8]
0x14001415c  test    ax, ax
0x14001415f  jz      short loc_140014176
0x140014161  mov     [r11], ax
0x140014165  add     r8, 2
0x140014169  add     r11, 2
0x14001416d  dec     r9
0x140014170  sub     r10, 1
0x140014174  jnz     short loc_140014153
0x140014176  test    r10, r10
0x140014179  lea     rcx, [r11-2]
0x14001417d  cmovnz  rcx, r11
0x140014181  neg     r10
0x140014184  sbb     edx, edx
0x140014186  not     edx
0x140014188  and     edx, 8007007Ah
0x14001418e  jmp     short loc_14001419A
0x140014190  mov     edx, 80070057h
0x140014195  test    r10, r10
0x140014198  jz      short loc_14001419D
0x14001419a  mov     [rcx], bx
0x14001419d  mov     rbx, [rsp+arg_0]
0x1400141a2  mov     eax, edx
0x1400141a4  retn
```

# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180005d00`
- end: `0x180005d71`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e018`

## callees

- `0x180005d00`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int16 *v4; // rax
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    do
    {
      if ( !a4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --a4;
      --a2;
    }
    while ( a2 );
    v4 = a1 - 1;
    if ( a2 )
      v4 = a1;
    *v4 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d00  test    rdx, rdx
0x180005d03  jz      short loc_180005D65
0x180005d05  cmp     rdx, 7FFFFFFFh
0x180005d0c  ja      short loc_180005D58
0x180005d0e  cmp     r9, 7FFFFFFEh
0x180005d15  ja      short loc_180005D58
0x180005d17  test    r9, r9
0x180005d1a  jz      short loc_180005D39
0x180005d1c  movzx   eax, word ptr [r8]
0x180005d20  test    ax, ax
0x180005d23  jz      short loc_180005D39
0x180005d25  mov     [rcx], ax
0x180005d28  add     r8, 2
0x180005d2c  add     rcx, 2
0x180005d30  dec     r9
0x180005d33  sub     rdx, 1
0x180005d37  jnz     short loc_180005D17
0x180005d39  test    rdx, rdx
0x180005d3c  lea     rax, [rcx-2]
0x180005d40  cmovnz  rax, rcx
0x180005d44  xor     r8d, r8d
0x180005d47  test    rdx, rdx
0x180005d4a  mov     [rax], r8w
0x180005d4e  mov     eax, 8007007Ah
0x180005d53  cmovnz  eax, r8d
0x180005d57  retn
0x180005d58  mov     eax, 80070057h
0x180005d5d  xor     r8d, r8d
0x180005d60  mov     [rcx], r8w
0x180005d64  retn
0x180005d65  mov     eax, 80070057h
0x180005d6a  test    rdx, rdx
0x180005d6d  jz      short locret_180005D57
0x180005d6f  jmp     short loc_180005D5D
```

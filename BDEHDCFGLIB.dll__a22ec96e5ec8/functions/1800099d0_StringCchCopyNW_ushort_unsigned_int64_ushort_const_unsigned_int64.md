# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1800099d0`
- end: `0x180009a4d`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007970`
- `0x180007af0`

## callees

- `0x1800099d0`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // r11
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
0x1800099d0  mov     [rsp+arg_0], rbx
0x1800099d5  xor     ebx, ebx
0x1800099d7  mov     r10, rdx
0x1800099da  mov     r11, rcx
0x1800099dd  test    rdx, rdx
0x1800099e0  jz      short loc_180009A38
0x1800099e2  cmp     rdx, 7FFFFFFFh
0x1800099e9  jbe     short loc_1800099F2
0x1800099eb  mov     edx, 80070057h
0x1800099f0  jmp     short loc_180009A42
0x1800099f2  cmp     r9, 7FFFFFFEh
0x1800099f9  ja      short loc_1800099EB
0x1800099fb  test    r9, r9
0x1800099fe  jz      short loc_180009A1E
0x180009a00  movzx   eax, word ptr [r8]
0x180009a04  test    ax, ax
0x180009a07  jz      short loc_180009A1E
0x180009a09  mov     [r11], ax
0x180009a0d  add     r8, 2
0x180009a11  add     r11, 2
0x180009a15  dec     r9
0x180009a18  sub     r10, 1
0x180009a1c  jnz     short loc_1800099FB
0x180009a1e  test    r10, r10
0x180009a21  lea     rcx, [r11-2]
0x180009a25  cmovnz  rcx, r11
0x180009a29  neg     r10
0x180009a2c  sbb     edx, edx
0x180009a2e  not     edx
0x180009a30  and     edx, 8007007Ah
0x180009a36  jmp     short loc_180009A42
0x180009a38  mov     edx, 80070057h
0x180009a3d  test    r10, r10
0x180009a40  jz      short loc_180009A45
0x180009a42  mov     [rcx], bx
0x180009a45  mov     rbx, [rsp+arg_0]
0x180009a4a  mov     eax, edx
0x180009a4c  retn
```

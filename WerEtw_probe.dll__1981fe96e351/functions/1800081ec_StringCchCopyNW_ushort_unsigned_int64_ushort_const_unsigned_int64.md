# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1800081ec`
- end: `0x180008269`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e84`
- `0x180012308`
- `0x1800278ac`

## callees

- `0x1800081ec`

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
0x1800081ec  mov     [rsp+arg_0], rbx
0x1800081f1  xor     ebx, ebx
0x1800081f3  mov     r10, rdx
0x1800081f6  mov     r11, rcx
0x1800081f9  test    rdx, rdx
0x1800081fc  jz      short loc_180008254
0x1800081fe  cmp     rdx, 7FFFFFFFh
0x180008205  jbe     short loc_18000820E
0x180008207  mov     edx, 80070057h
0x18000820c  jmp     short loc_18000825E
0x18000820e  cmp     r9, 7FFFFFFEh
0x180008215  ja      short loc_180008207
0x180008217  test    r9, r9
0x18000821a  jz      short loc_18000823A
0x18000821c  movzx   eax, word ptr [r8]
0x180008220  test    ax, ax
0x180008223  jz      short loc_18000823A
0x180008225  mov     [r11], ax
0x180008229  add     r8, 2
0x18000822d  add     r11, 2
0x180008231  dec     r9
0x180008234  sub     r10, 1
0x180008238  jnz     short loc_180008217
0x18000823a  test    r10, r10
0x18000823d  lea     rcx, [r11-2]
0x180008241  cmovnz  rcx, r11
0x180008245  neg     r10
0x180008248  sbb     edx, edx
0x18000824a  not     edx
0x18000824c  and     edx, 8007007Ah
0x180008252  jmp     short loc_18000825E
0x180008254  mov     edx, 80070057h
0x180008259  test    r10, r10
0x18000825c  jz      short loc_180008261
0x18000825e  mov     [rcx], bx
0x180008261  mov     rbx, [rsp+arg_0]
0x180008266  mov     eax, edx
0x180008268  retn
```

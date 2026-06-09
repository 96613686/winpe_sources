# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180006150`
- end: `0x1800061cd`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005474`

## callees

- `0x180006150`

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
0x180006150  mov     [rsp+arg_0], rbx
0x180006155  xor     ebx, ebx
0x180006157  mov     r10, rdx
0x18000615a  mov     r11, rcx
0x18000615d  test    rdx, rdx
0x180006160  jz      short loc_1800061B8
0x180006162  cmp     rdx, 7FFFFFFFh
0x180006169  jbe     short loc_180006172
0x18000616b  mov     edx, 80070057h
0x180006170  jmp     short loc_1800061C2
0x180006172  cmp     r9, 7FFFFFFEh
0x180006179  ja      short loc_18000616B
0x18000617b  test    r9, r9
0x18000617e  jz      short loc_18000619E
0x180006180  movzx   eax, word ptr [r8]
0x180006184  test    ax, ax
0x180006187  jz      short loc_18000619E
0x180006189  mov     [r11], ax
0x18000618d  add     r8, 2
0x180006191  add     r11, 2
0x180006195  dec     r9
0x180006198  sub     r10, 1
0x18000619c  jnz     short loc_18000617B
0x18000619e  test    r10, r10
0x1800061a1  lea     rcx, [r11-2]
0x1800061a5  cmovnz  rcx, r11
0x1800061a9  neg     r10
0x1800061ac  sbb     edx, edx
0x1800061ae  not     edx
0x1800061b0  and     edx, 8007007Ah
0x1800061b6  jmp     short loc_1800061C2
0x1800061b8  mov     edx, 80070057h
0x1800061bd  test    r10, r10
0x1800061c0  jz      short loc_1800061C5
0x1800061c2  mov     [rcx], bx
0x1800061c5  mov     rbx, [rsp+arg_0]
0x1800061ca  mov     eax, edx
0x1800061cc  retn
```

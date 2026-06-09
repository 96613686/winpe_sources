# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18000ac98`
- end: `0x18000ad15`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000adf8`

## callees

- `0x18000ac98`

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
0x18000ac98  mov     [rsp+arg_0], rbx
0x18000ac9d  xor     ebx, ebx
0x18000ac9f  mov     r10, rdx
0x18000aca2  mov     r11, rcx
0x18000aca5  test    rdx, rdx
0x18000aca8  jz      short loc_18000AD00
0x18000acaa  cmp     rdx, 7FFFFFFFh
0x18000acb1  jbe     short loc_18000ACBA
0x18000acb3  mov     edx, 80070057h
0x18000acb8  jmp     short loc_18000AD0A
0x18000acba  cmp     r9, 7FFFFFFEh
0x18000acc1  ja      short loc_18000ACB3
0x18000acc3  test    r9, r9
0x18000acc6  jz      short loc_18000ACE6
0x18000acc8  movzx   eax, word ptr [r8]
0x18000accc  test    ax, ax
0x18000accf  jz      short loc_18000ACE6
0x18000acd1  mov     [r11], ax
0x18000acd5  add     r8, 2
0x18000acd9  add     r11, 2
0x18000acdd  dec     r9
0x18000ace0  sub     r10, 1
0x18000ace4  jnz     short loc_18000ACC3
0x18000ace6  test    r10, r10
0x18000ace9  lea     rcx, [r11-2]
0x18000aced  cmovnz  rcx, r11
0x18000acf1  neg     r10
0x18000acf4  sbb     edx, edx
0x18000acf6  not     edx
0x18000acf8  and     edx, 8007007Ah
0x18000acfe  jmp     short loc_18000AD0A
0x18000ad00  mov     edx, 80070057h
0x18000ad05  test    r10, r10
0x18000ad08  jz      short loc_18000AD0D
0x18000ad0a  mov     [rcx], bx
0x18000ad0d  mov     rbx, [rsp+arg_0]
0x18000ad12  mov     eax, edx
0x18000ad14  retn
```

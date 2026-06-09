# Utf16Encoder::ProcessCodePoint(char32_t,ushort &)

- ea: `0x1800040b0`
- end: `0x180004115`
- name: `?ProcessCodePoint@Utf16Encoder@@QEAAK_UAEAG@Z`
- size: `101`
- prototype: `__int64 __fastcall(Utf16Encoder *this, unsigned int, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001e80`
- `0x1800027c0`
- `0x180004160`

## callees

- `0x1800040b0`

## pseudocode

```c
__int64 __fastcall Utf16Encoder::ProcessCodePoint(Utf16Encoder *this, unsigned int a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  unsigned int v4; // edx

  if ( *(_WORD *)this )
  {
    *a3 = *(_WORD *)this;
    result = 0;
    *(_WORD *)this = 0;
  }
  else if ( a2 <= 0x10FFFF && a2 - 55296 > 0x7FF )
  {
    if ( a2 > 0xFFFF )
    {
      v4 = a2 - 0x10000;
      *a3 = (v4 >> 10) | 0xD800;
      result = 234;
      *(_WORD *)this = v4 & 0x3FF | 0xDC00;
    }
    else
    {
      *a3 = a2;
      return 0;
    }
  }
  else
  {
    return 582;
  }
  return result;
}

```

## disassembly

```asm
0x1800040b0  movzx   eax, word ptr [rcx]
0x1800040b3  test    ax, ax
0x1800040b6  jnz     short loc_1800040D3
0x1800040b8  cmp     edx, 10FFFFh
0x1800040be  ja      short loc_1800040CD
0x1800040c0  lea     eax, [rdx-0D800h]
0x1800040c6  cmp     eax, 7FFh
0x1800040cb  ja      short loc_1800040DD
0x1800040cd  mov     eax, 246h
0x1800040d2  retn
0x1800040d3  mov     [r8], ax
0x1800040d7  xor     eax, eax
0x1800040d9  mov     [rcx], ax
0x1800040dc  retn
0x1800040dd  cmp     edx, 0FFFFh
0x1800040e3  ja      short loc_1800040EC
0x1800040e5  mov     [r8], dx
0x1800040e9  xor     eax, eax
0x1800040eb  retn
0x1800040ec  add     edx, 0FFFF0000h
0x1800040f2  mov     eax, edx
0x1800040f4  shr     eax, 0Ah
0x1800040f7  or      ax, 0D800h
0x1800040fb  mov     [r8], ax
0x1800040ff  mov     eax, 3FFh
0x180004104  and     dx, ax
0x180004107  mov     eax, 0EAh
0x18000410c  or      dx, 0DC00h
0x180004111  mov     [rcx], dx
0x180004114  retn
```

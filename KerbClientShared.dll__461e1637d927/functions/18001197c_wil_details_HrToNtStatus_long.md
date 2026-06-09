# wil::details::HrToNtStatus(long)

- ea: `0x18001197c`
- end: `0x180011b38`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fb2c`
- `0x18000fba4`
- `0x18000fc24`
- `0x18000fc78`
- `0x180010fc8`
- `0x180011e84`

## callees

- `0x18001197c`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x80070216:
          LODWORD(this) = -1073741675;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
  {
    LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    LODWORD(this) = (unsigned __int16)this;
    if ( (_WORD)this )
      LODWORD(this) = (unsigned __int16)this | 0xC0070000;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x18001197c  mov     eax, 800700EAh
0x180011981  cmp     ecx, eax
0x180011983  jg      loc_180011A58
0x180011989  jz      loc_180011A4E
0x18001198f  mov     eax, 80070057h
0x180011994  cmp     ecx, eax
0x180011996  jg      short loc_180011A02
0x180011998  jz      short loc_1800119F8
0x18001199a  cmp     ecx, 80004005h
0x1800119a0  jz      short loc_1800119EE
0x1800119a2  cmp     ecx, 80070001h
0x1800119a8  jz      short loc_1800119E4
0x1800119aa  cmp     ecx, 80070002h
0x1800119b0  jz      short loc_1800119DA
0x1800119b2  cmp     ecx, 80070003h
0x1800119b8  jz      short loc_1800119D0
0x1800119ba  cmp     ecx, 8007000Eh
0x1800119c0  jnz     loc_180011ADD
0x1800119c6  mov     ecx, 0C0000017h
0x1800119cb  jmp     loc_180011B35
0x1800119d0  mov     ecx, 0C000003Ah
0x1800119d5  jmp     loc_180011B35
0x1800119da  mov     ecx, 0C0000034h
0x1800119df  jmp     loc_180011B35
0x1800119e4  mov     ecx, 0C0000002h
0x1800119e9  jmp     loc_180011B35
0x1800119ee  mov     ecx, 0C0000001h
0x1800119f3  jmp     loc_180011B35
0x1800119f8  mov     ecx, 0C000000Dh
0x1800119fd  jmp     loc_180011B35
0x180011a02  cmp     ecx, 80070070h
0x180011a08  jz      short loc_180011A44
0x180011a0a  cmp     ecx, 8007007Ah
0x180011a10  jz      short loc_180011A3A
0x180011a12  cmp     ecx, 8007007Bh
0x180011a18  jz      short loc_180011A30
0x180011a1a  cmp     ecx, 8007007Eh
0x180011a20  jnz     loc_180011ADD
0x180011a26  mov     ecx, 0C0000135h
0x180011a2b  jmp     loc_180011B35
0x180011a30  mov     ecx, 0C0000033h
0x180011a35  jmp     loc_180011B35
0x180011a3a  mov     ecx, 0C0000023h
0x180011a3f  jmp     loc_180011B35
0x180011a44  mov     ecx, 0C000007Fh
0x180011a49  jmp     loc_180011B35
0x180011a4e  mov     ecx, 80000005h
0x180011a53  jmp     loc_180011B35
0x180011a58  mov     eax, 8007047Eh
0x180011a5d  cmp     ecx, eax
0x180011a5f  jg      short loc_180011AC1
0x180011a61  jz      short loc_180011ABA
0x180011a63  cmp     ecx, 80070216h
0x180011a69  jz      short loc_180011AB3
0x180011a6b  cmp     ecx, 8007023Eh
0x180011a71  jz      short loc_180011AA9
0x180011a73  cmp     ecx, 80070246h
0x180011a79  jz      short loc_180011A9F
0x180011a7b  cmp     ecx, 80070247h
0x180011a81  jz      short loc_180011A95
0x180011a83  cmp     ecx, 80070272h
0x180011a89  jnz     short loc_180011ADD
0x180011a8b  mov     ecx, 0C0000273h
0x180011a90  jmp     loc_180011B35
0x180011a95  mov     ecx, 0C0000163h
0x180011a9a  jmp     loc_180011B35
0x180011a9f  mov     ecx, 0C0000161h
0x180011aa4  jmp     loc_180011B35
0x180011aa9  mov     ecx, 0C0000025h
0x180011aae  jmp     loc_180011B35
0x180011ab3  mov     ecx, 0C0000095h
0x180011ab8  jmp     short loc_180011B35
0x180011aba  mov     ecx, 0C0000059h
0x180011abf  jmp     short loc_180011B35
0x180011ac1  cmp     ecx, 8007050Ch
0x180011ac7  jz      short loc_180011B30
0x180011ac9  cmp     ecx, 8007054Fh
0x180011acf  jz      short loc_180011B29
0x180011ad1  cmp     ecx, 800705B9h
0x180011ad7  jz      short loc_180011B22
0x180011ad9  test    ecx, ecx
0x180011adb  jz      short loc_180011B1E
0x180011add  bt      ecx, 1Ch
0x180011ae1  jnb     short loc_180011AE9
0x180011ae3  btr     ecx, 1Ch
0x180011ae7  jmp     short loc_180011B35
0x180011ae9  mov     eax, ecx
0x180011aeb  and     eax, 1FFF0000h
0x180011af0  cmp     eax, 70000h
0x180011af5  jnz     short loc_180011B08
0x180011af7  movzx   ecx, cx
0x180011afa  mov     eax, ecx
0x180011afc  or      eax, 0C0070000h
0x180011b01  test    ecx, ecx
0x180011b03  cmovnz  ecx, eax
0x180011b06  jmp     short loc_180011B35
0x180011b08  cmp     eax, 90000h
0x180011b0d  jnz     short loc_180011B29
0x180011b0f  test    ecx, ecx
0x180011b11  jle     short loc_180011B35
0x180011b13  movzx   ecx, cx
0x180011b16  or      ecx, 0C0090000h
0x180011b1c  jmp     short loc_180011B35
0x180011b1e  xor     ecx, ecx
0x180011b20  jmp     short loc_180011B35
0x180011b22  mov     ecx, 0C000A083h
0x180011b27  jmp     short loc_180011B35
0x180011b29  mov     ecx, 0C00000E5h
0x180011b2e  jmp     short loc_180011B35
0x180011b30  mov     ecx, 0C000042Bh
0x180011b35  mov     eax, ecx
0x180011b37  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x14000bc6c`
- end: `0x14000be28`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140009624`
- `0x1400097f0`
- `0x1400098a0`
- `0x1400098f8`
- `0x1400099c0`
- `0x140009eec`
- `0x14000b238`
- `0x14000c240`
- `0x14000e1f4`
- `0x14000e864`
- `0x140011e30`
- `0x140016a4a`
- `0x140016ab5`
- `0x140016b7e`
- `0x140016be9`

## callees

- `0x14000bc6c`

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
0x14000bc6c  mov     eax, 800700EAh
0x14000bc71  cmp     ecx, eax
0x14000bc73  jg      loc_14000BD48
0x14000bc79  jz      loc_14000BD3E
0x14000bc7f  mov     eax, 80070057h
0x14000bc84  cmp     ecx, eax
0x14000bc86  jg      short loc_14000BCF2
0x14000bc88  jz      short loc_14000BCE8
0x14000bc8a  cmp     ecx, 80004005h
0x14000bc90  jz      short loc_14000BCDE
0x14000bc92  cmp     ecx, 80070001h
0x14000bc98  jz      short loc_14000BCD4
0x14000bc9a  cmp     ecx, 80070002h
0x14000bca0  jz      short loc_14000BCCA
0x14000bca2  cmp     ecx, 80070003h
0x14000bca8  jz      short loc_14000BCC0
0x14000bcaa  cmp     ecx, 8007000Eh
0x14000bcb0  jnz     loc_14000BDCD
0x14000bcb6  mov     ecx, 0C0000017h
0x14000bcbb  jmp     loc_14000BE25
0x14000bcc0  mov     ecx, 0C000003Ah
0x14000bcc5  jmp     loc_14000BE25
0x14000bcca  mov     ecx, 0C0000034h
0x14000bccf  jmp     loc_14000BE25
0x14000bcd4  mov     ecx, 0C0000002h
0x14000bcd9  jmp     loc_14000BE25
0x14000bcde  mov     ecx, 0C0000001h
0x14000bce3  jmp     loc_14000BE25
0x14000bce8  mov     ecx, 0C000000Dh
0x14000bced  jmp     loc_14000BE25
0x14000bcf2  cmp     ecx, 80070070h
0x14000bcf8  jz      short loc_14000BD34
0x14000bcfa  cmp     ecx, 8007007Ah
0x14000bd00  jz      short loc_14000BD2A
0x14000bd02  cmp     ecx, 8007007Bh
0x14000bd08  jz      short loc_14000BD20
0x14000bd0a  cmp     ecx, 8007007Eh
0x14000bd10  jnz     loc_14000BDCD
0x14000bd16  mov     ecx, 0C0000135h
0x14000bd1b  jmp     loc_14000BE25
0x14000bd20  mov     ecx, 0C0000033h
0x14000bd25  jmp     loc_14000BE25
0x14000bd2a  mov     ecx, 0C0000023h
0x14000bd2f  jmp     loc_14000BE25
0x14000bd34  mov     ecx, 0C000007Fh
0x14000bd39  jmp     loc_14000BE25
0x14000bd3e  mov     ecx, 80000005h
0x14000bd43  jmp     loc_14000BE25
0x14000bd48  mov     eax, 8007047Eh
0x14000bd4d  cmp     ecx, eax
0x14000bd4f  jg      short loc_14000BDB1
0x14000bd51  jz      short loc_14000BDAA
0x14000bd53  cmp     ecx, 80070216h
0x14000bd59  jz      short loc_14000BDA3
0x14000bd5b  cmp     ecx, 8007023Eh
0x14000bd61  jz      short loc_14000BD99
0x14000bd63  cmp     ecx, 80070246h
0x14000bd69  jz      short loc_14000BD8F
0x14000bd6b  cmp     ecx, 80070247h
0x14000bd71  jz      short loc_14000BD85
0x14000bd73  cmp     ecx, 80070272h
0x14000bd79  jnz     short loc_14000BDCD
0x14000bd7b  mov     ecx, 0C0000273h
0x14000bd80  jmp     loc_14000BE25
0x14000bd85  mov     ecx, 0C0000163h
0x14000bd8a  jmp     loc_14000BE25
0x14000bd8f  mov     ecx, 0C0000161h
0x14000bd94  jmp     loc_14000BE25
0x14000bd99  mov     ecx, 0C0000025h
0x14000bd9e  jmp     loc_14000BE25
0x14000bda3  mov     ecx, 0C0000095h
0x14000bda8  jmp     short loc_14000BE25
0x14000bdaa  mov     ecx, 0C0000059h
0x14000bdaf  jmp     short loc_14000BE25
0x14000bdb1  cmp     ecx, 8007050Ch
0x14000bdb7  jz      short loc_14000BE20
0x14000bdb9  cmp     ecx, 8007054Fh
0x14000bdbf  jz      short loc_14000BE19
0x14000bdc1  cmp     ecx, 800705B9h
0x14000bdc7  jz      short loc_14000BE12
0x14000bdc9  test    ecx, ecx
0x14000bdcb  jz      short loc_14000BE0E
0x14000bdcd  bt      ecx, 1Ch
0x14000bdd1  jnb     short loc_14000BDD9
0x14000bdd3  btr     ecx, 1Ch
0x14000bdd7  jmp     short loc_14000BE25
0x14000bdd9  mov     eax, ecx
0x14000bddb  and     eax, 1FFF0000h
0x14000bde0  cmp     eax, 70000h
0x14000bde5  jnz     short loc_14000BDF8
0x14000bde7  movzx   ecx, cx
0x14000bdea  mov     eax, ecx
0x14000bdec  or      eax, 0C0070000h
0x14000bdf1  test    ecx, ecx
0x14000bdf3  cmovnz  ecx, eax
0x14000bdf6  jmp     short loc_14000BE25
0x14000bdf8  cmp     eax, 90000h
0x14000bdfd  jnz     short loc_14000BE19
0x14000bdff  test    ecx, ecx
0x14000be01  jle     short loc_14000BE25
0x14000be03  movzx   ecx, cx
0x14000be06  or      ecx, 0C0090000h
0x14000be0c  jmp     short loc_14000BE25
0x14000be0e  xor     ecx, ecx
0x14000be10  jmp     short loc_14000BE25
0x14000be12  mov     ecx, 0C000A083h
0x14000be17  jmp     short loc_14000BE25
0x14000be19  mov     ecx, 0C00000E5h
0x14000be1e  jmp     short loc_14000BE25
0x14000be20  mov     ecx, 0C000042Bh
0x14000be25  mov     eax, ecx
0x14000be27  retn
```

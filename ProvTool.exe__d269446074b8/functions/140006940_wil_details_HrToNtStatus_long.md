# wil::details::HrToNtStatus(long)

- ea: `0x140006940`
- end: `0x140006afc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023bc`
- `0x140002588`
- `0x140002638`
- `0x140002690`
- `0x1400027b4`
- `0x1400030bc`
- `0x140005038`
- `0x140006df0`
- `0x140007590`
- `0x14000e58a`
- `0x14000e5f5`
- `0x14000e6be`
- `0x14000e729`

## callees

- `0x140006940`

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
0x140006940  mov     eax, 800700EAh
0x140006945  cmp     ecx, eax
0x140006947  jg      loc_140006A1C
0x14000694d  jz      loc_140006A12
0x140006953  mov     eax, 80070057h
0x140006958  cmp     ecx, eax
0x14000695a  jg      short loc_1400069C6
0x14000695c  jz      short loc_1400069BC
0x14000695e  cmp     ecx, 80004005h
0x140006964  jz      short loc_1400069B2
0x140006966  cmp     ecx, 80070001h
0x14000696c  jz      short loc_1400069A8
0x14000696e  cmp     ecx, 80070002h
0x140006974  jz      short loc_14000699E
0x140006976  cmp     ecx, 80070003h
0x14000697c  jz      short loc_140006994
0x14000697e  cmp     ecx, 8007000Eh
0x140006984  jnz     loc_140006AA1
0x14000698a  mov     ecx, 0C0000017h
0x14000698f  jmp     loc_140006AF9
0x140006994  mov     ecx, 0C000003Ah
0x140006999  jmp     loc_140006AF9
0x14000699e  mov     ecx, 0C0000034h
0x1400069a3  jmp     loc_140006AF9
0x1400069a8  mov     ecx, 0C0000002h
0x1400069ad  jmp     loc_140006AF9
0x1400069b2  mov     ecx, 0C0000001h
0x1400069b7  jmp     loc_140006AF9
0x1400069bc  mov     ecx, 0C000000Dh
0x1400069c1  jmp     loc_140006AF9
0x1400069c6  cmp     ecx, 80070070h
0x1400069cc  jz      short loc_140006A08
0x1400069ce  cmp     ecx, 8007007Ah
0x1400069d4  jz      short loc_1400069FE
0x1400069d6  cmp     ecx, 8007007Bh
0x1400069dc  jz      short loc_1400069F4
0x1400069de  cmp     ecx, 8007007Eh
0x1400069e4  jnz     loc_140006AA1
0x1400069ea  mov     ecx, 0C0000135h
0x1400069ef  jmp     loc_140006AF9
0x1400069f4  mov     ecx, 0C0000033h
0x1400069f9  jmp     loc_140006AF9
0x1400069fe  mov     ecx, 0C0000023h
0x140006a03  jmp     loc_140006AF9
0x140006a08  mov     ecx, 0C000007Fh
0x140006a0d  jmp     loc_140006AF9
0x140006a12  mov     ecx, 80000005h
0x140006a17  jmp     loc_140006AF9
0x140006a1c  mov     eax, 8007047Eh
0x140006a21  cmp     ecx, eax
0x140006a23  jg      short loc_140006A85
0x140006a25  jz      short loc_140006A7E
0x140006a27  cmp     ecx, 80070216h
0x140006a2d  jz      short loc_140006A77
0x140006a2f  cmp     ecx, 8007023Eh
0x140006a35  jz      short loc_140006A6D
0x140006a37  cmp     ecx, 80070246h
0x140006a3d  jz      short loc_140006A63
0x140006a3f  cmp     ecx, 80070247h
0x140006a45  jz      short loc_140006A59
0x140006a47  cmp     ecx, 80070272h
0x140006a4d  jnz     short loc_140006AA1
0x140006a4f  mov     ecx, 0C0000273h
0x140006a54  jmp     loc_140006AF9
0x140006a59  mov     ecx, 0C0000163h
0x140006a5e  jmp     loc_140006AF9
0x140006a63  mov     ecx, 0C0000161h
0x140006a68  jmp     loc_140006AF9
0x140006a6d  mov     ecx, 0C0000025h
0x140006a72  jmp     loc_140006AF9
0x140006a77  mov     ecx, 0C0000095h
0x140006a7c  jmp     short loc_140006AF9
0x140006a7e  mov     ecx, 0C0000059h
0x140006a83  jmp     short loc_140006AF9
0x140006a85  cmp     ecx, 8007050Ch
0x140006a8b  jz      short loc_140006AF4
0x140006a8d  cmp     ecx, 8007054Fh
0x140006a93  jz      short loc_140006AED
0x140006a95  cmp     ecx, 800705B9h
0x140006a9b  jz      short loc_140006AE6
0x140006a9d  test    ecx, ecx
0x140006a9f  jz      short loc_140006AE2
0x140006aa1  bt      ecx, 1Ch
0x140006aa5  jnb     short loc_140006AAD
0x140006aa7  btr     ecx, 1Ch
0x140006aab  jmp     short loc_140006AF9
0x140006aad  mov     eax, ecx
0x140006aaf  and     eax, 1FFF0000h
0x140006ab4  cmp     eax, 70000h
0x140006ab9  jnz     short loc_140006ACC
0x140006abb  movzx   ecx, cx
0x140006abe  mov     eax, ecx
0x140006ac0  or      eax, 0C0070000h
0x140006ac5  test    ecx, ecx
0x140006ac7  cmovnz  ecx, eax
0x140006aca  jmp     short loc_140006AF9
0x140006acc  cmp     eax, 90000h
0x140006ad1  jnz     short loc_140006AED
0x140006ad3  test    ecx, ecx
0x140006ad5  jle     short loc_140006AF9
0x140006ad7  movzx   ecx, cx
0x140006ada  or      ecx, 0C0090000h
0x140006ae0  jmp     short loc_140006AF9
0x140006ae2  xor     ecx, ecx
0x140006ae4  jmp     short loc_140006AF9
0x140006ae6  mov     ecx, 0C000A083h
0x140006aeb  jmp     short loc_140006AF9
0x140006aed  mov     ecx, 0C00000E5h
0x140006af2  jmp     short loc_140006AF9
0x140006af4  mov     ecx, 0C000042Bh
0x140006af9  mov     eax, ecx
0x140006afb  retn
```

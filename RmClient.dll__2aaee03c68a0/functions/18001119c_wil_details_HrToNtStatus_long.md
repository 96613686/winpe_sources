# wil::details::HrToNtStatus(long)

- ea: `0x18001119c`
- end: `0x180011358`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180012ac0`
- `0x180012b38`
- `0x180012cf0`
- `0x18001326c`
- `0x180015c34`
- `0x180015cac`

## callees

- `0x18001119c`

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
        case 0x8007054F:
          goto LABEL_53;
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
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
0x18001119c  mov     eax, 800700EAh
0x1800111a1  cmp     ecx, eax
0x1800111a3  jg      loc_180011278
0x1800111a9  jz      loc_18001126E
0x1800111af  mov     eax, 80070057h
0x1800111b4  cmp     ecx, eax
0x1800111b6  jg      short loc_180011222
0x1800111b8  jz      short loc_180011218
0x1800111ba  cmp     ecx, 80004005h
0x1800111c0  jz      short loc_18001120E
0x1800111c2  cmp     ecx, 80070001h
0x1800111c8  jz      short loc_180011204
0x1800111ca  cmp     ecx, 80070002h
0x1800111d0  jz      short loc_1800111FA
0x1800111d2  cmp     ecx, 80070003h
0x1800111d8  jz      short loc_1800111F0
0x1800111da  cmp     ecx, 8007000Eh
0x1800111e0  jnz     loc_1800112FD
0x1800111e6  mov     ecx, 0C0000017h
0x1800111eb  jmp     loc_180011355
0x1800111f0  mov     ecx, 0C000003Ah
0x1800111f5  jmp     loc_180011355
0x1800111fa  mov     ecx, 0C0000034h
0x1800111ff  jmp     loc_180011355
0x180011204  mov     ecx, 0C0000002h
0x180011209  jmp     loc_180011355
0x18001120e  mov     ecx, 0C0000001h
0x180011213  jmp     loc_180011355
0x180011218  mov     ecx, 0C000000Dh
0x18001121d  jmp     loc_180011355
0x180011222  cmp     ecx, 80070070h
0x180011228  jz      short loc_180011264
0x18001122a  cmp     ecx, 8007007Ah
0x180011230  jz      short loc_18001125A
0x180011232  cmp     ecx, 8007007Bh
0x180011238  jz      short loc_180011250
0x18001123a  cmp     ecx, 8007007Eh
0x180011240  jnz     loc_1800112FD
0x180011246  mov     ecx, 0C0000135h
0x18001124b  jmp     loc_180011355
0x180011250  mov     ecx, 0C0000033h
0x180011255  jmp     loc_180011355
0x18001125a  mov     ecx, 0C0000023h
0x18001125f  jmp     loc_180011355
0x180011264  mov     ecx, 0C000007Fh
0x180011269  jmp     loc_180011355
0x18001126e  mov     ecx, 80000005h
0x180011273  jmp     loc_180011355
0x180011278  mov     eax, 8007047Eh
0x18001127d  cmp     ecx, eax
0x18001127f  jg      short loc_1800112E1
0x180011281  jz      short loc_1800112DA
0x180011283  cmp     ecx, 80070216h
0x180011289  jz      short loc_1800112D3
0x18001128b  cmp     ecx, 8007023Eh
0x180011291  jz      short loc_1800112C9
0x180011293  cmp     ecx, 80070246h
0x180011299  jz      short loc_1800112BF
0x18001129b  cmp     ecx, 80070247h
0x1800112a1  jz      short loc_1800112B5
0x1800112a3  cmp     ecx, 80070272h
0x1800112a9  jnz     short loc_1800112FD
0x1800112ab  mov     ecx, 0C0000273h
0x1800112b0  jmp     loc_180011355
0x1800112b5  mov     ecx, 0C0000163h
0x1800112ba  jmp     loc_180011355
0x1800112bf  mov     ecx, 0C0000161h
0x1800112c4  jmp     loc_180011355
0x1800112c9  mov     ecx, 0C0000025h
0x1800112ce  jmp     loc_180011355
0x1800112d3  mov     ecx, 0C0000095h
0x1800112d8  jmp     short loc_180011355
0x1800112da  mov     ecx, 0C0000059h
0x1800112df  jmp     short loc_180011355
0x1800112e1  cmp     ecx, 8007054Fh
0x1800112e7  jz      short loc_180011349
0x1800112e9  cmp     ecx, 8007050Ch
0x1800112ef  jz      short loc_180011350
0x1800112f1  cmp     ecx, 800705B9h
0x1800112f7  jz      short loc_180011342
0x1800112f9  test    ecx, ecx
0x1800112fb  jz      short loc_18001133E
0x1800112fd  bt      ecx, 1Ch
0x180011301  jnb     short loc_180011309
0x180011303  btr     ecx, 1Ch
0x180011307  jmp     short loc_180011355
0x180011309  mov     eax, ecx
0x18001130b  and     eax, 1FFF0000h
0x180011310  cmp     eax, 70000h
0x180011315  jnz     short loc_180011328
0x180011317  movzx   ecx, cx
0x18001131a  mov     eax, ecx
0x18001131c  or      eax, 0C0070000h
0x180011321  test    ecx, ecx
0x180011323  cmovnz  ecx, eax
0x180011326  jmp     short loc_180011355
0x180011328  cmp     eax, 90000h
0x18001132d  jnz     short loc_180011349
0x18001132f  test    ecx, ecx
0x180011331  jle     short loc_180011355
0x180011333  movzx   ecx, cx
0x180011336  or      ecx, 0C0090000h
0x18001133c  jmp     short loc_180011355
0x18001133e  xor     ecx, ecx
0x180011340  jmp     short loc_180011355
0x180011342  mov     ecx, 0C000A083h
0x180011347  jmp     short loc_180011355
0x180011349  mov     ecx, 0C00000E5h
0x18001134e  jmp     short loc_180011355
0x180011350  mov     ecx, 0C000042Bh
0x180011355  mov     eax, ecx
0x180011357  retn
```

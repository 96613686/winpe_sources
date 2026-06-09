# wil::details::HrToNtStatus(long)

- ea: `0x1400061c4`
- end: `0x140006380`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005768`
- `0x1400057b8`
- `0x140005cf4`
- `0x140006388`
- `0x140006b24`
- `0x140006c28`

## callees

- `0x1400061c4`

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
0x1400061c4  mov     eax, 800700EAh
0x1400061c9  cmp     ecx, eax
0x1400061cb  jg      loc_1400062A0
0x1400061d1  jz      loc_140006296
0x1400061d7  mov     eax, 80070057h
0x1400061dc  cmp     ecx, eax
0x1400061de  jg      short loc_14000624A
0x1400061e0  jz      short loc_140006240
0x1400061e2  cmp     ecx, 80004005h
0x1400061e8  jz      short loc_140006236
0x1400061ea  cmp     ecx, 80070001h
0x1400061f0  jz      short loc_14000622C
0x1400061f2  cmp     ecx, 80070002h
0x1400061f8  jz      short loc_140006222
0x1400061fa  cmp     ecx, 80070003h
0x140006200  jz      short loc_140006218
0x140006202  cmp     ecx, 8007000Eh
0x140006208  jnz     loc_140006325
0x14000620e  mov     ecx, 0C0000017h
0x140006213  jmp     loc_14000637D
0x140006218  mov     ecx, 0C000003Ah
0x14000621d  jmp     loc_14000637D
0x140006222  mov     ecx, 0C0000034h
0x140006227  jmp     loc_14000637D
0x14000622c  mov     ecx, 0C0000002h
0x140006231  jmp     loc_14000637D
0x140006236  mov     ecx, 0C0000001h
0x14000623b  jmp     loc_14000637D
0x140006240  mov     ecx, 0C000000Dh
0x140006245  jmp     loc_14000637D
0x14000624a  cmp     ecx, 80070070h
0x140006250  jz      short loc_14000628C
0x140006252  cmp     ecx, 8007007Ah
0x140006258  jz      short loc_140006282
0x14000625a  cmp     ecx, 8007007Bh
0x140006260  jz      short loc_140006278
0x140006262  cmp     ecx, 8007007Eh
0x140006268  jnz     loc_140006325
0x14000626e  mov     ecx, 0C0000135h
0x140006273  jmp     loc_14000637D
0x140006278  mov     ecx, 0C0000033h
0x14000627d  jmp     loc_14000637D
0x140006282  mov     ecx, 0C0000023h
0x140006287  jmp     loc_14000637D
0x14000628c  mov     ecx, 0C000007Fh
0x140006291  jmp     loc_14000637D
0x140006296  mov     ecx, 80000005h
0x14000629b  jmp     loc_14000637D
0x1400062a0  mov     eax, 8007047Eh
0x1400062a5  cmp     ecx, eax
0x1400062a7  jg      short loc_140006309
0x1400062a9  jz      short loc_140006302
0x1400062ab  cmp     ecx, 80070216h
0x1400062b1  jz      short loc_1400062FB
0x1400062b3  cmp     ecx, 8007023Eh
0x1400062b9  jz      short loc_1400062F1
0x1400062bb  cmp     ecx, 80070246h
0x1400062c1  jz      short loc_1400062E7
0x1400062c3  cmp     ecx, 80070247h
0x1400062c9  jz      short loc_1400062DD
0x1400062cb  cmp     ecx, 80070272h
0x1400062d1  jnz     short loc_140006325
0x1400062d3  mov     ecx, 0C0000273h
0x1400062d8  jmp     loc_14000637D
0x1400062dd  mov     ecx, 0C0000163h
0x1400062e2  jmp     loc_14000637D
0x1400062e7  mov     ecx, 0C0000161h
0x1400062ec  jmp     loc_14000637D
0x1400062f1  mov     ecx, 0C0000025h
0x1400062f6  jmp     loc_14000637D
0x1400062fb  mov     ecx, 0C0000095h
0x140006300  jmp     short loc_14000637D
0x140006302  mov     ecx, 0C0000059h
0x140006307  jmp     short loc_14000637D
0x140006309  cmp     ecx, 8007050Ch
0x14000630f  jz      short loc_140006378
0x140006311  cmp     ecx, 8007054Fh
0x140006317  jz      short loc_140006371
0x140006319  cmp     ecx, 800705B9h
0x14000631f  jz      short loc_14000636A
0x140006321  test    ecx, ecx
0x140006323  jz      short loc_140006366
0x140006325  bt      ecx, 1Ch
0x140006329  jnb     short loc_140006331
0x14000632b  btr     ecx, 1Ch
0x14000632f  jmp     short loc_14000637D
0x140006331  mov     eax, ecx
0x140006333  and     eax, 1FFF0000h
0x140006338  cmp     eax, 70000h
0x14000633d  jnz     short loc_140006350
0x14000633f  movzx   ecx, cx
0x140006342  mov     eax, ecx
0x140006344  or      eax, 0C0070000h
0x140006349  test    ecx, ecx
0x14000634b  cmovnz  ecx, eax
0x14000634e  jmp     short loc_14000637D
0x140006350  cmp     eax, 90000h
0x140006355  jnz     short loc_140006371
0x140006357  test    ecx, ecx
0x140006359  jle     short loc_14000637D
0x14000635b  movzx   ecx, cx
0x14000635e  or      ecx, 0C0090000h
0x140006364  jmp     short loc_14000637D
0x140006366  xor     ecx, ecx
0x140006368  jmp     short loc_14000637D
0x14000636a  mov     ecx, 0C000A083h
0x14000636f  jmp     short loc_14000637D
0x140006371  mov     ecx, 0C00000E5h
0x140006376  jmp     short loc_14000637D
0x140006378  mov     ecx, 0C000042Bh
0x14000637d  mov     eax, ecx
0x14000637f  retn
```

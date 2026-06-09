# wil::details::HrToNtStatus(long)

- ea: `0x14000a26c`
- end: `0x14000a428`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140006ed4`
- `0x140006f4c`
- `0x140006fcc`
- `0x140007020`
- `0x140007084`
- `0x14000aaec`

## callees

- `0x14000a26c`

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
0x14000a26c  mov     eax, 800700EAh
0x14000a271  cmp     ecx, eax
0x14000a273  jg      loc_14000A348
0x14000a279  jz      loc_14000A33E
0x14000a27f  mov     eax, 80070057h
0x14000a284  cmp     ecx, eax
0x14000a286  jg      short loc_14000A2F2
0x14000a288  jz      short loc_14000A2E8
0x14000a28a  cmp     ecx, 80004005h
0x14000a290  jz      short loc_14000A2DE
0x14000a292  cmp     ecx, 80070001h
0x14000a298  jz      short loc_14000A2D4
0x14000a29a  cmp     ecx, 80070002h
0x14000a2a0  jz      short loc_14000A2CA
0x14000a2a2  cmp     ecx, 80070003h
0x14000a2a8  jz      short loc_14000A2C0
0x14000a2aa  cmp     ecx, 8007000Eh
0x14000a2b0  jnz     loc_14000A3CD
0x14000a2b6  mov     ecx, 0C0000017h
0x14000a2bb  jmp     loc_14000A425
0x14000a2c0  mov     ecx, 0C000003Ah
0x14000a2c5  jmp     loc_14000A425
0x14000a2ca  mov     ecx, 0C0000034h
0x14000a2cf  jmp     loc_14000A425
0x14000a2d4  mov     ecx, 0C0000002h
0x14000a2d9  jmp     loc_14000A425
0x14000a2de  mov     ecx, 0C0000001h
0x14000a2e3  jmp     loc_14000A425
0x14000a2e8  mov     ecx, 0C000000Dh
0x14000a2ed  jmp     loc_14000A425
0x14000a2f2  cmp     ecx, 80070070h
0x14000a2f8  jz      short loc_14000A334
0x14000a2fa  cmp     ecx, 8007007Ah
0x14000a300  jz      short loc_14000A32A
0x14000a302  cmp     ecx, 8007007Bh
0x14000a308  jz      short loc_14000A320
0x14000a30a  cmp     ecx, 8007007Eh
0x14000a310  jnz     loc_14000A3CD
0x14000a316  mov     ecx, 0C0000135h
0x14000a31b  jmp     loc_14000A425
0x14000a320  mov     ecx, 0C0000033h
0x14000a325  jmp     loc_14000A425
0x14000a32a  mov     ecx, 0C0000023h
0x14000a32f  jmp     loc_14000A425
0x14000a334  mov     ecx, 0C000007Fh
0x14000a339  jmp     loc_14000A425
0x14000a33e  mov     ecx, 80000005h
0x14000a343  jmp     loc_14000A425
0x14000a348  mov     eax, 8007047Eh
0x14000a34d  cmp     ecx, eax
0x14000a34f  jg      short loc_14000A3B1
0x14000a351  jz      short loc_14000A3AA
0x14000a353  cmp     ecx, 80070216h
0x14000a359  jz      short loc_14000A3A3
0x14000a35b  cmp     ecx, 8007023Eh
0x14000a361  jz      short loc_14000A399
0x14000a363  cmp     ecx, 80070246h
0x14000a369  jz      short loc_14000A38F
0x14000a36b  cmp     ecx, 80070247h
0x14000a371  jz      short loc_14000A385
0x14000a373  cmp     ecx, 80070272h
0x14000a379  jnz     short loc_14000A3CD
0x14000a37b  mov     ecx, 0C0000273h
0x14000a380  jmp     loc_14000A425
0x14000a385  mov     ecx, 0C0000163h
0x14000a38a  jmp     loc_14000A425
0x14000a38f  mov     ecx, 0C0000161h
0x14000a394  jmp     loc_14000A425
0x14000a399  mov     ecx, 0C0000025h
0x14000a39e  jmp     loc_14000A425
0x14000a3a3  mov     ecx, 0C0000095h
0x14000a3a8  jmp     short loc_14000A425
0x14000a3aa  mov     ecx, 0C0000059h
0x14000a3af  jmp     short loc_14000A425
0x14000a3b1  cmp     ecx, 8007050Ch
0x14000a3b7  jz      short loc_14000A420
0x14000a3b9  cmp     ecx, 8007054Fh
0x14000a3bf  jz      short loc_14000A419
0x14000a3c1  cmp     ecx, 800705B9h
0x14000a3c7  jz      short loc_14000A412
0x14000a3c9  test    ecx, ecx
0x14000a3cb  jz      short loc_14000A40E
0x14000a3cd  bt      ecx, 1Ch
0x14000a3d1  jnb     short loc_14000A3D9
0x14000a3d3  btr     ecx, 1Ch
0x14000a3d7  jmp     short loc_14000A425
0x14000a3d9  mov     eax, ecx
0x14000a3db  and     eax, 1FFF0000h
0x14000a3e0  cmp     eax, 70000h
0x14000a3e5  jnz     short loc_14000A3F8
0x14000a3e7  movzx   ecx, cx
0x14000a3ea  mov     eax, ecx
0x14000a3ec  or      eax, 0C0070000h
0x14000a3f1  test    ecx, ecx
0x14000a3f3  cmovnz  ecx, eax
0x14000a3f6  jmp     short loc_14000A425
0x14000a3f8  cmp     eax, 90000h
0x14000a3fd  jnz     short loc_14000A419
0x14000a3ff  test    ecx, ecx
0x14000a401  jle     short loc_14000A425
0x14000a403  movzx   ecx, cx
0x14000a406  or      ecx, 0C0090000h
0x14000a40c  jmp     short loc_14000A425
0x14000a40e  xor     ecx, ecx
0x14000a410  jmp     short loc_14000A425
0x14000a412  mov     ecx, 0C000A083h
0x14000a417  jmp     short loc_14000A425
0x14000a419  mov     ecx, 0C00000E5h
0x14000a41e  jmp     short loc_14000A425
0x14000a420  mov     ecx, 0C000042Bh
0x14000a425  mov     eax, ecx
0x14000a427  retn
```

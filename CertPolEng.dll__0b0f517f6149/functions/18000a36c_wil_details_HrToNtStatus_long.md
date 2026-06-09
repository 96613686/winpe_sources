# wil::details::HrToNtStatus(long)

- ea: `0x18000a36c`
- end: `0x18000a528`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a244`
- `0x18000a310`
- `0x18000a620`
- `0x18000ef08`
- `0x18000ef80`
- `0x18000efe4`
- `0x1800172c8`
- `0x180017330`

## callees

- `0x18000a36c`

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
0x18000a36c  mov     eax, 800700EAh
0x18000a371  cmp     ecx, eax
0x18000a373  jg      loc_18000A448
0x18000a379  jz      loc_18000A43E
0x18000a37f  mov     eax, 80070057h
0x18000a384  cmp     ecx, eax
0x18000a386  jg      short loc_18000A3F2
0x18000a388  jz      short loc_18000A3E8
0x18000a38a  cmp     ecx, 80004005h
0x18000a390  jz      short loc_18000A3DE
0x18000a392  cmp     ecx, 80070001h
0x18000a398  jz      short loc_18000A3D4
0x18000a39a  cmp     ecx, 80070002h
0x18000a3a0  jz      short loc_18000A3CA
0x18000a3a2  cmp     ecx, 80070003h
0x18000a3a8  jz      short loc_18000A3C0
0x18000a3aa  cmp     ecx, 8007000Eh
0x18000a3b0  jnz     loc_18000A4CD
0x18000a3b6  mov     ecx, 0C0000017h
0x18000a3bb  jmp     loc_18000A525
0x18000a3c0  mov     ecx, 0C000003Ah
0x18000a3c5  jmp     loc_18000A525
0x18000a3ca  mov     ecx, 0C0000034h
0x18000a3cf  jmp     loc_18000A525
0x18000a3d4  mov     ecx, 0C0000002h
0x18000a3d9  jmp     loc_18000A525
0x18000a3de  mov     ecx, 0C0000001h
0x18000a3e3  jmp     loc_18000A525
0x18000a3e8  mov     ecx, 0C000000Dh
0x18000a3ed  jmp     loc_18000A525
0x18000a3f2  cmp     ecx, 80070070h
0x18000a3f8  jz      short loc_18000A434
0x18000a3fa  cmp     ecx, 8007007Ah
0x18000a400  jz      short loc_18000A42A
0x18000a402  cmp     ecx, 8007007Bh
0x18000a408  jz      short loc_18000A420
0x18000a40a  cmp     ecx, 8007007Eh
0x18000a410  jnz     loc_18000A4CD
0x18000a416  mov     ecx, 0C0000135h
0x18000a41b  jmp     loc_18000A525
0x18000a420  mov     ecx, 0C0000033h
0x18000a425  jmp     loc_18000A525
0x18000a42a  mov     ecx, 0C0000023h
0x18000a42f  jmp     loc_18000A525
0x18000a434  mov     ecx, 0C000007Fh
0x18000a439  jmp     loc_18000A525
0x18000a43e  mov     ecx, 80000005h
0x18000a443  jmp     loc_18000A525
0x18000a448  mov     eax, 8007047Eh
0x18000a44d  cmp     ecx, eax
0x18000a44f  jg      short loc_18000A4B1
0x18000a451  jz      short loc_18000A4AA
0x18000a453  cmp     ecx, 80070216h
0x18000a459  jz      short loc_18000A4A3
0x18000a45b  cmp     ecx, 8007023Eh
0x18000a461  jz      short loc_18000A499
0x18000a463  cmp     ecx, 80070246h
0x18000a469  jz      short loc_18000A48F
0x18000a46b  cmp     ecx, 80070247h
0x18000a471  jz      short loc_18000A485
0x18000a473  cmp     ecx, 80070272h
0x18000a479  jnz     short loc_18000A4CD
0x18000a47b  mov     ecx, 0C0000273h
0x18000a480  jmp     loc_18000A525
0x18000a485  mov     ecx, 0C0000163h
0x18000a48a  jmp     loc_18000A525
0x18000a48f  mov     ecx, 0C0000161h
0x18000a494  jmp     loc_18000A525
0x18000a499  mov     ecx, 0C0000025h
0x18000a49e  jmp     loc_18000A525
0x18000a4a3  mov     ecx, 0C0000095h
0x18000a4a8  jmp     short loc_18000A525
0x18000a4aa  mov     ecx, 0C0000059h
0x18000a4af  jmp     short loc_18000A525
0x18000a4b1  cmp     ecx, 8007054Fh
0x18000a4b7  jz      short loc_18000A519
0x18000a4b9  cmp     ecx, 8007050Ch
0x18000a4bf  jz      short loc_18000A520
0x18000a4c1  cmp     ecx, 800705B9h
0x18000a4c7  jz      short loc_18000A512
0x18000a4c9  test    ecx, ecx
0x18000a4cb  jz      short loc_18000A50E
0x18000a4cd  bt      ecx, 1Ch
0x18000a4d1  jnb     short loc_18000A4D9
0x18000a4d3  btr     ecx, 1Ch
0x18000a4d7  jmp     short loc_18000A525
0x18000a4d9  mov     eax, ecx
0x18000a4db  and     eax, 1FFF0000h
0x18000a4e0  cmp     eax, 70000h
0x18000a4e5  jnz     short loc_18000A4F8
0x18000a4e7  movzx   ecx, cx
0x18000a4ea  mov     eax, ecx
0x18000a4ec  or      eax, 0C0070000h
0x18000a4f1  test    ecx, ecx
0x18000a4f3  cmovnz  ecx, eax
0x18000a4f6  jmp     short loc_18000A525
0x18000a4f8  cmp     eax, 90000h
0x18000a4fd  jnz     short loc_18000A519
0x18000a4ff  test    ecx, ecx
0x18000a501  jle     short loc_18000A525
0x18000a503  movzx   ecx, cx
0x18000a506  or      ecx, 0C0090000h
0x18000a50c  jmp     short loc_18000A525
0x18000a50e  xor     ecx, ecx
0x18000a510  jmp     short loc_18000A525
0x18000a512  mov     ecx, 0C000A083h
0x18000a517  jmp     short loc_18000A525
0x18000a519  mov     ecx, 0C00000E5h
0x18000a51e  jmp     short loc_18000A525
0x18000a520  mov     ecx, 0C000042Bh
0x18000a525  mov     eax, ecx
0x18000a527  retn
```

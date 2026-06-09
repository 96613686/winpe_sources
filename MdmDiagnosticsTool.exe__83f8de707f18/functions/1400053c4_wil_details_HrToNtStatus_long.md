# wil::details::HrToNtStatus(long)

- ea: `0x1400053c4`
- end: `0x140005580`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002484`
- `0x1400024fc`
- `0x140002578`
- `0x1400025c8`
- `0x140002c6c`
- `0x140004328`
- `0x1400055b8`
- `0x140006410`
- `0x14000a074`
- `0x14000a0bf`
- `0x14000a182`
- `0x14000a1cd`

## callees

- `0x1400053c4`

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
0x1400053c4  mov     eax, 800700EAh
0x1400053c9  cmp     ecx, eax
0x1400053cb  jg      loc_1400054A0
0x1400053d1  jz      loc_140005496
0x1400053d7  mov     eax, 80070057h
0x1400053dc  cmp     ecx, eax
0x1400053de  jg      short loc_14000544A
0x1400053e0  jz      short loc_140005440
0x1400053e2  cmp     ecx, 80004005h
0x1400053e8  jz      short loc_140005436
0x1400053ea  cmp     ecx, 80070001h
0x1400053f0  jz      short loc_14000542C
0x1400053f2  cmp     ecx, 80070002h
0x1400053f8  jz      short loc_140005422
0x1400053fa  cmp     ecx, 80070003h
0x140005400  jz      short loc_140005418
0x140005402  cmp     ecx, 8007000Eh
0x140005408  jnz     loc_140005525
0x14000540e  mov     ecx, 0C0000017h
0x140005413  jmp     loc_14000557D
0x140005418  mov     ecx, 0C000003Ah
0x14000541d  jmp     loc_14000557D
0x140005422  mov     ecx, 0C0000034h
0x140005427  jmp     loc_14000557D
0x14000542c  mov     ecx, 0C0000002h
0x140005431  jmp     loc_14000557D
0x140005436  mov     ecx, 0C0000001h
0x14000543b  jmp     loc_14000557D
0x140005440  mov     ecx, 0C000000Dh
0x140005445  jmp     loc_14000557D
0x14000544a  cmp     ecx, 80070070h
0x140005450  jz      short loc_14000548C
0x140005452  cmp     ecx, 8007007Ah
0x140005458  jz      short loc_140005482
0x14000545a  cmp     ecx, 8007007Bh
0x140005460  jz      short loc_140005478
0x140005462  cmp     ecx, 8007007Eh
0x140005468  jnz     loc_140005525
0x14000546e  mov     ecx, 0C0000135h
0x140005473  jmp     loc_14000557D
0x140005478  mov     ecx, 0C0000033h
0x14000547d  jmp     loc_14000557D
0x140005482  mov     ecx, 0C0000023h
0x140005487  jmp     loc_14000557D
0x14000548c  mov     ecx, 0C000007Fh
0x140005491  jmp     loc_14000557D
0x140005496  mov     ecx, 80000005h
0x14000549b  jmp     loc_14000557D
0x1400054a0  mov     eax, 8007047Eh
0x1400054a5  cmp     ecx, eax
0x1400054a7  jg      short loc_140005509
0x1400054a9  jz      short loc_140005502
0x1400054ab  cmp     ecx, 80070216h
0x1400054b1  jz      short loc_1400054FB
0x1400054b3  cmp     ecx, 8007023Eh
0x1400054b9  jz      short loc_1400054F1
0x1400054bb  cmp     ecx, 80070246h
0x1400054c1  jz      short loc_1400054E7
0x1400054c3  cmp     ecx, 80070247h
0x1400054c9  jz      short loc_1400054DD
0x1400054cb  cmp     ecx, 80070272h
0x1400054d1  jnz     short loc_140005525
0x1400054d3  mov     ecx, 0C0000273h
0x1400054d8  jmp     loc_14000557D
0x1400054dd  mov     ecx, 0C0000163h
0x1400054e2  jmp     loc_14000557D
0x1400054e7  mov     ecx, 0C0000161h
0x1400054ec  jmp     loc_14000557D
0x1400054f1  mov     ecx, 0C0000025h
0x1400054f6  jmp     loc_14000557D
0x1400054fb  mov     ecx, 0C0000095h
0x140005500  jmp     short loc_14000557D
0x140005502  mov     ecx, 0C0000059h
0x140005507  jmp     short loc_14000557D
0x140005509  cmp     ecx, 8007050Ch
0x14000550f  jz      short loc_140005578
0x140005511  cmp     ecx, 8007054Fh
0x140005517  jz      short loc_140005571
0x140005519  cmp     ecx, 800705B9h
0x14000551f  jz      short loc_14000556A
0x140005521  test    ecx, ecx
0x140005523  jz      short loc_140005566
0x140005525  bt      ecx, 1Ch
0x140005529  jnb     short loc_140005531
0x14000552b  btr     ecx, 1Ch
0x14000552f  jmp     short loc_14000557D
0x140005531  mov     eax, ecx
0x140005533  and     eax, 1FFF0000h
0x140005538  cmp     eax, 70000h
0x14000553d  jnz     short loc_140005550
0x14000553f  movzx   ecx, cx
0x140005542  mov     eax, ecx
0x140005544  or      eax, 0C0070000h
0x140005549  test    ecx, ecx
0x14000554b  cmovnz  ecx, eax
0x14000554e  jmp     short loc_14000557D
0x140005550  cmp     eax, 90000h
0x140005555  jnz     short loc_140005571
0x140005557  test    ecx, ecx
0x140005559  jle     short loc_14000557D
0x14000555b  movzx   ecx, cx
0x14000555e  or      ecx, 0C0090000h
0x140005564  jmp     short loc_14000557D
0x140005566  xor     ecx, ecx
0x140005568  jmp     short loc_14000557D
0x14000556a  mov     ecx, 0C000A083h
0x14000556f  jmp     short loc_14000557D
0x140005571  mov     ecx, 0C00000E5h
0x140005576  jmp     short loc_14000557D
0x140005578  mov     ecx, 0C000042Bh
0x14000557d  mov     eax, ecx
0x14000557f  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x1800061ac`
- end: `0x180006368`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ff8`
- `0x180006050`
- `0x180006100`
- `0x180008aa0`
- `0x18000a670`
- `0x18000a6c0`

## callees

- `0x1800061ac`

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
0x1800061ac  mov     eax, 800700EAh
0x1800061b1  cmp     ecx, eax
0x1800061b3  jg      loc_180006288
0x1800061b9  jz      loc_18000627E
0x1800061bf  mov     eax, 80070057h
0x1800061c4  cmp     ecx, eax
0x1800061c6  jg      short loc_180006232
0x1800061c8  jz      short loc_180006228
0x1800061ca  cmp     ecx, 80004005h
0x1800061d0  jz      short loc_18000621E
0x1800061d2  cmp     ecx, 80070001h
0x1800061d8  jz      short loc_180006214
0x1800061da  cmp     ecx, 80070002h
0x1800061e0  jz      short loc_18000620A
0x1800061e2  cmp     ecx, 80070003h
0x1800061e8  jz      short loc_180006200
0x1800061ea  cmp     ecx, 8007000Eh
0x1800061f0  jnz     loc_18000630D
0x1800061f6  mov     ecx, 0C0000017h
0x1800061fb  jmp     loc_180006365
0x180006200  mov     ecx, 0C000003Ah
0x180006205  jmp     loc_180006365
0x18000620a  mov     ecx, 0C0000034h
0x18000620f  jmp     loc_180006365
0x180006214  mov     ecx, 0C0000002h
0x180006219  jmp     loc_180006365
0x18000621e  mov     ecx, 0C0000001h
0x180006223  jmp     loc_180006365
0x180006228  mov     ecx, 0C000000Dh
0x18000622d  jmp     loc_180006365
0x180006232  cmp     ecx, 80070070h
0x180006238  jz      short loc_180006274
0x18000623a  cmp     ecx, 8007007Ah
0x180006240  jz      short loc_18000626A
0x180006242  cmp     ecx, 8007007Bh
0x180006248  jz      short loc_180006260
0x18000624a  cmp     ecx, 8007007Eh
0x180006250  jnz     loc_18000630D
0x180006256  mov     ecx, 0C0000135h
0x18000625b  jmp     loc_180006365
0x180006260  mov     ecx, 0C0000033h
0x180006265  jmp     loc_180006365
0x18000626a  mov     ecx, 0C0000023h
0x18000626f  jmp     loc_180006365
0x180006274  mov     ecx, 0C000007Fh
0x180006279  jmp     loc_180006365
0x18000627e  mov     ecx, 80000005h
0x180006283  jmp     loc_180006365
0x180006288  mov     eax, 8007047Eh
0x18000628d  cmp     ecx, eax
0x18000628f  jg      short loc_1800062F1
0x180006291  jz      short loc_1800062EA
0x180006293  cmp     ecx, 80070216h
0x180006299  jz      short loc_1800062E3
0x18000629b  cmp     ecx, 8007023Eh
0x1800062a1  jz      short loc_1800062D9
0x1800062a3  cmp     ecx, 80070246h
0x1800062a9  jz      short loc_1800062CF
0x1800062ab  cmp     ecx, 80070247h
0x1800062b1  jz      short loc_1800062C5
0x1800062b3  cmp     ecx, 80070272h
0x1800062b9  jnz     short loc_18000630D
0x1800062bb  mov     ecx, 0C0000273h
0x1800062c0  jmp     loc_180006365
0x1800062c5  mov     ecx, 0C0000163h
0x1800062ca  jmp     loc_180006365
0x1800062cf  mov     ecx, 0C0000161h
0x1800062d4  jmp     loc_180006365
0x1800062d9  mov     ecx, 0C0000025h
0x1800062de  jmp     loc_180006365
0x1800062e3  mov     ecx, 0C0000095h
0x1800062e8  jmp     short loc_180006365
0x1800062ea  mov     ecx, 0C0000059h
0x1800062ef  jmp     short loc_180006365
0x1800062f1  cmp     ecx, 8007054Fh
0x1800062f7  jz      short loc_180006359
0x1800062f9  cmp     ecx, 8007050Ch
0x1800062ff  jz      short loc_180006360
0x180006301  cmp     ecx, 800705B9h
0x180006307  jz      short loc_180006352
0x180006309  test    ecx, ecx
0x18000630b  jz      short loc_18000634E
0x18000630d  bt      ecx, 1Ch
0x180006311  jnb     short loc_180006319
0x180006313  btr     ecx, 1Ch
0x180006317  jmp     short loc_180006365
0x180006319  mov     eax, ecx
0x18000631b  and     eax, 1FFF0000h
0x180006320  cmp     eax, 70000h
0x180006325  jnz     short loc_180006338
0x180006327  movzx   ecx, cx
0x18000632a  mov     eax, ecx
0x18000632c  or      eax, 0C0070000h
0x180006331  test    ecx, ecx
0x180006333  cmovnz  ecx, eax
0x180006336  jmp     short loc_180006365
0x180006338  cmp     eax, 90000h
0x18000633d  jnz     short loc_180006359
0x18000633f  test    ecx, ecx
0x180006341  jle     short loc_180006365
0x180006343  movzx   ecx, cx
0x180006346  or      ecx, 0C0090000h
0x18000634c  jmp     short loc_180006365
0x18000634e  xor     ecx, ecx
0x180006350  jmp     short loc_180006365
0x180006352  mov     ecx, 0C000A083h
0x180006357  jmp     short loc_180006365
0x180006359  mov     ecx, 0C00000E5h
0x18000635e  jmp     short loc_180006365
0x180006360  mov     ecx, 0C000042Bh
0x180006365  mov     eax, ecx
0x180006367  retn
```

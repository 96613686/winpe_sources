# wil::details::HrToNtStatus(long)

- ea: `0x1400042bc`
- end: `0x140004478`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002784`
- `0x140002824`
- `0x140002874`
- `0x140002934`
- `0x140003898`
- `0x140004480`

## callees

- `0x1400042bc`

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
0x1400042bc  mov     eax, 800700EAh
0x1400042c1  cmp     ecx, eax
0x1400042c3  jg      loc_140004398
0x1400042c9  jz      loc_14000438E
0x1400042cf  mov     eax, 80070057h
0x1400042d4  cmp     ecx, eax
0x1400042d6  jg      short loc_140004342
0x1400042d8  jz      short loc_140004338
0x1400042da  cmp     ecx, 80004005h
0x1400042e0  jz      short loc_14000432E
0x1400042e2  cmp     ecx, 80070001h
0x1400042e8  jz      short loc_140004324
0x1400042ea  cmp     ecx, 80070002h
0x1400042f0  jz      short loc_14000431A
0x1400042f2  cmp     ecx, 80070003h
0x1400042f8  jz      short loc_140004310
0x1400042fa  cmp     ecx, 8007000Eh
0x140004300  jnz     loc_14000441D
0x140004306  mov     ecx, 0C0000017h
0x14000430b  jmp     loc_140004475
0x140004310  mov     ecx, 0C000003Ah
0x140004315  jmp     loc_140004475
0x14000431a  mov     ecx, 0C0000034h
0x14000431f  jmp     loc_140004475
0x140004324  mov     ecx, 0C0000002h
0x140004329  jmp     loc_140004475
0x14000432e  mov     ecx, 0C0000001h
0x140004333  jmp     loc_140004475
0x140004338  mov     ecx, 0C000000Dh
0x14000433d  jmp     loc_140004475
0x140004342  cmp     ecx, 80070070h
0x140004348  jz      short loc_140004384
0x14000434a  cmp     ecx, 8007007Ah
0x140004350  jz      short loc_14000437A
0x140004352  cmp     ecx, 8007007Bh
0x140004358  jz      short loc_140004370
0x14000435a  cmp     ecx, 8007007Eh
0x140004360  jnz     loc_14000441D
0x140004366  mov     ecx, 0C0000135h
0x14000436b  jmp     loc_140004475
0x140004370  mov     ecx, 0C0000033h
0x140004375  jmp     loc_140004475
0x14000437a  mov     ecx, 0C0000023h
0x14000437f  jmp     loc_140004475
0x140004384  mov     ecx, 0C000007Fh
0x140004389  jmp     loc_140004475
0x14000438e  mov     ecx, 80000005h
0x140004393  jmp     loc_140004475
0x140004398  mov     eax, 8007047Eh
0x14000439d  cmp     ecx, eax
0x14000439f  jg      short loc_140004401
0x1400043a1  jz      short loc_1400043FA
0x1400043a3  cmp     ecx, 80070216h
0x1400043a9  jz      short loc_1400043F3
0x1400043ab  cmp     ecx, 8007023Eh
0x1400043b1  jz      short loc_1400043E9
0x1400043b3  cmp     ecx, 80070246h
0x1400043b9  jz      short loc_1400043DF
0x1400043bb  cmp     ecx, 80070247h
0x1400043c1  jz      short loc_1400043D5
0x1400043c3  cmp     ecx, 80070272h
0x1400043c9  jnz     short loc_14000441D
0x1400043cb  mov     ecx, 0C0000273h
0x1400043d0  jmp     loc_140004475
0x1400043d5  mov     ecx, 0C0000163h
0x1400043da  jmp     loc_140004475
0x1400043df  mov     ecx, 0C0000161h
0x1400043e4  jmp     loc_140004475
0x1400043e9  mov     ecx, 0C0000025h
0x1400043ee  jmp     loc_140004475
0x1400043f3  mov     ecx, 0C0000095h
0x1400043f8  jmp     short loc_140004475
0x1400043fa  mov     ecx, 0C0000059h
0x1400043ff  jmp     short loc_140004475
0x140004401  cmp     ecx, 8007050Ch
0x140004407  jz      short loc_140004470
0x140004409  cmp     ecx, 8007054Fh
0x14000440f  jz      short loc_140004469
0x140004411  cmp     ecx, 800705B9h
0x140004417  jz      short loc_140004462
0x140004419  test    ecx, ecx
0x14000441b  jz      short loc_14000445E
0x14000441d  bt      ecx, 1Ch
0x140004421  jnb     short loc_140004429
0x140004423  btr     ecx, 1Ch
0x140004427  jmp     short loc_140004475
0x140004429  mov     eax, ecx
0x14000442b  and     eax, 1FFF0000h
0x140004430  cmp     eax, 70000h
0x140004435  jnz     short loc_140004448
0x140004437  movzx   ecx, cx
0x14000443a  mov     eax, ecx
0x14000443c  or      eax, 0C0070000h
0x140004441  test    ecx, ecx
0x140004443  cmovnz  ecx, eax
0x140004446  jmp     short loc_140004475
0x140004448  cmp     eax, 90000h
0x14000444d  jnz     short loc_140004469
0x14000444f  test    ecx, ecx
0x140004451  jle     short loc_140004475
0x140004453  movzx   ecx, cx
0x140004456  or      ecx, 0C0090000h
0x14000445c  jmp     short loc_140004475
0x14000445e  xor     ecx, ecx
0x140004460  jmp     short loc_140004475
0x140004462  mov     ecx, 0C000A083h
0x140004467  jmp     short loc_140004475
0x140004469  mov     ecx, 0C00000E5h
0x14000446e  jmp     short loc_140004475
0x140004470  mov     ecx, 0C000042Bh
0x140004475  mov     eax, ecx
0x140004477  retn
```

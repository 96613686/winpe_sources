# wil::details::HrToNtStatus(long)

- ea: `0x140002194`
- end: `0x140002350`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002110`
- `0x140003588`
- `0x140003600`
- `0x140003650`
- `0x1400036b4`
- `0x1400050c4`

## callees

- `0x140002194`

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
0x140002194  mov     eax, 800700EAh
0x140002199  cmp     ecx, eax
0x14000219b  jg      loc_140002270
0x1400021a1  jz      loc_140002266
0x1400021a7  mov     eax, 80070057h
0x1400021ac  cmp     ecx, eax
0x1400021ae  jg      short loc_14000221A
0x1400021b0  jz      short loc_140002210
0x1400021b2  cmp     ecx, 80004005h
0x1400021b8  jz      short loc_140002206
0x1400021ba  cmp     ecx, 80070001h
0x1400021c0  jz      short loc_1400021FC
0x1400021c2  cmp     ecx, 80070002h
0x1400021c8  jz      short loc_1400021F2
0x1400021ca  cmp     ecx, 80070003h
0x1400021d0  jz      short loc_1400021E8
0x1400021d2  cmp     ecx, 8007000Eh
0x1400021d8  jnz     loc_1400022F5
0x1400021de  mov     ecx, 0C0000017h
0x1400021e3  jmp     loc_14000234D
0x1400021e8  mov     ecx, 0C000003Ah
0x1400021ed  jmp     loc_14000234D
0x1400021f2  mov     ecx, 0C0000034h
0x1400021f7  jmp     loc_14000234D
0x1400021fc  mov     ecx, 0C0000002h
0x140002201  jmp     loc_14000234D
0x140002206  mov     ecx, 0C0000001h
0x14000220b  jmp     loc_14000234D
0x140002210  mov     ecx, 0C000000Dh
0x140002215  jmp     loc_14000234D
0x14000221a  cmp     ecx, 80070070h
0x140002220  jz      short loc_14000225C
0x140002222  cmp     ecx, 8007007Ah
0x140002228  jz      short loc_140002252
0x14000222a  cmp     ecx, 8007007Bh
0x140002230  jz      short loc_140002248
0x140002232  cmp     ecx, 8007007Eh
0x140002238  jnz     loc_1400022F5
0x14000223e  mov     ecx, 0C0000135h
0x140002243  jmp     loc_14000234D
0x140002248  mov     ecx, 0C0000033h
0x14000224d  jmp     loc_14000234D
0x140002252  mov     ecx, 0C0000023h
0x140002257  jmp     loc_14000234D
0x14000225c  mov     ecx, 0C000007Fh
0x140002261  jmp     loc_14000234D
0x140002266  mov     ecx, 80000005h
0x14000226b  jmp     loc_14000234D
0x140002270  mov     eax, 8007047Eh
0x140002275  cmp     ecx, eax
0x140002277  jg      short loc_1400022D9
0x140002279  jz      short loc_1400022D2
0x14000227b  cmp     ecx, 80070216h
0x140002281  jz      short loc_1400022CB
0x140002283  cmp     ecx, 8007023Eh
0x140002289  jz      short loc_1400022C1
0x14000228b  cmp     ecx, 80070246h
0x140002291  jz      short loc_1400022B7
0x140002293  cmp     ecx, 80070247h
0x140002299  jz      short loc_1400022AD
0x14000229b  cmp     ecx, 80070272h
0x1400022a1  jnz     short loc_1400022F5
0x1400022a3  mov     ecx, 0C0000273h
0x1400022a8  jmp     loc_14000234D
0x1400022ad  mov     ecx, 0C0000163h
0x1400022b2  jmp     loc_14000234D
0x1400022b7  mov     ecx, 0C0000161h
0x1400022bc  jmp     loc_14000234D
0x1400022c1  mov     ecx, 0C0000025h
0x1400022c6  jmp     loc_14000234D
0x1400022cb  mov     ecx, 0C0000095h
0x1400022d0  jmp     short loc_14000234D
0x1400022d2  mov     ecx, 0C0000059h
0x1400022d7  jmp     short loc_14000234D
0x1400022d9  cmp     ecx, 8007050Ch
0x1400022df  jz      short loc_140002348
0x1400022e1  cmp     ecx, 8007054Fh
0x1400022e7  jz      short loc_140002341
0x1400022e9  cmp     ecx, 800705B9h
0x1400022ef  jz      short loc_14000233A
0x1400022f1  test    ecx, ecx
0x1400022f3  jz      short loc_140002336
0x1400022f5  bt      ecx, 1Ch
0x1400022f9  jnb     short loc_140002301
0x1400022fb  btr     ecx, 1Ch
0x1400022ff  jmp     short loc_14000234D
0x140002301  mov     eax, ecx
0x140002303  and     eax, 1FFF0000h
0x140002308  cmp     eax, 70000h
0x14000230d  jnz     short loc_140002320
0x14000230f  movzx   ecx, cx
0x140002312  mov     eax, ecx
0x140002314  or      eax, 0C0070000h
0x140002319  test    ecx, ecx
0x14000231b  cmovnz  ecx, eax
0x14000231e  jmp     short loc_14000234D
0x140002320  cmp     eax, 90000h
0x140002325  jnz     short loc_140002341
0x140002327  test    ecx, ecx
0x140002329  jle     short loc_14000234D
0x14000232b  movzx   ecx, cx
0x14000232e  or      ecx, 0C0090000h
0x140002334  jmp     short loc_14000234D
0x140002336  xor     ecx, ecx
0x140002338  jmp     short loc_14000234D
0x14000233a  mov     ecx, 0C000A083h
0x14000233f  jmp     short loc_14000234D
0x140002341  mov     ecx, 0C00000E5h
0x140002346  jmp     short loc_14000234D
0x140002348  mov     ecx, 0C000042Bh
0x14000234d  mov     eax, ecx
0x14000234f  retn
```

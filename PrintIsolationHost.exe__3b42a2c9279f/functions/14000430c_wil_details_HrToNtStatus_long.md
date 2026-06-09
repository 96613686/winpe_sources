# wil::details::HrToNtStatus(long)

- ea: `0x14000430c`
- end: `0x1400044c8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000284c`
- `0x1400028ec`
- `0x14000293c`
- `0x1400029f4`
- `0x1400038e8`
- `0x140004598`

## callees

- `0x14000430c`

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
0x14000430c  mov     eax, 800700EAh
0x140004311  cmp     ecx, eax
0x140004313  jg      loc_1400043E8
0x140004319  jz      loc_1400043DE
0x14000431f  mov     eax, 80070057h
0x140004324  cmp     ecx, eax
0x140004326  jg      short loc_140004392
0x140004328  jz      short loc_140004388
0x14000432a  cmp     ecx, 80004005h
0x140004330  jz      short loc_14000437E
0x140004332  cmp     ecx, 80070001h
0x140004338  jz      short loc_140004374
0x14000433a  cmp     ecx, 80070002h
0x140004340  jz      short loc_14000436A
0x140004342  cmp     ecx, 80070003h
0x140004348  jz      short loc_140004360
0x14000434a  cmp     ecx, 8007000Eh
0x140004350  jnz     loc_14000446D
0x140004356  mov     ecx, 0C0000017h
0x14000435b  jmp     loc_1400044C5
0x140004360  mov     ecx, 0C000003Ah
0x140004365  jmp     loc_1400044C5
0x14000436a  mov     ecx, 0C0000034h
0x14000436f  jmp     loc_1400044C5
0x140004374  mov     ecx, 0C0000002h
0x140004379  jmp     loc_1400044C5
0x14000437e  mov     ecx, 0C0000001h
0x140004383  jmp     loc_1400044C5
0x140004388  mov     ecx, 0C000000Dh
0x14000438d  jmp     loc_1400044C5
0x140004392  cmp     ecx, 80070070h
0x140004398  jz      short loc_1400043D4
0x14000439a  cmp     ecx, 8007007Ah
0x1400043a0  jz      short loc_1400043CA
0x1400043a2  cmp     ecx, 8007007Bh
0x1400043a8  jz      short loc_1400043C0
0x1400043aa  cmp     ecx, 8007007Eh
0x1400043b0  jnz     loc_14000446D
0x1400043b6  mov     ecx, 0C0000135h
0x1400043bb  jmp     loc_1400044C5
0x1400043c0  mov     ecx, 0C0000033h
0x1400043c5  jmp     loc_1400044C5
0x1400043ca  mov     ecx, 0C0000023h
0x1400043cf  jmp     loc_1400044C5
0x1400043d4  mov     ecx, 0C000007Fh
0x1400043d9  jmp     loc_1400044C5
0x1400043de  mov     ecx, 80000005h
0x1400043e3  jmp     loc_1400044C5
0x1400043e8  mov     eax, 8007047Eh
0x1400043ed  cmp     ecx, eax
0x1400043ef  jg      short loc_140004451
0x1400043f1  jz      short loc_14000444A
0x1400043f3  cmp     ecx, 80070216h
0x1400043f9  jz      short loc_140004443
0x1400043fb  cmp     ecx, 8007023Eh
0x140004401  jz      short loc_140004439
0x140004403  cmp     ecx, 80070246h
0x140004409  jz      short loc_14000442F
0x14000440b  cmp     ecx, 80070247h
0x140004411  jz      short loc_140004425
0x140004413  cmp     ecx, 80070272h
0x140004419  jnz     short loc_14000446D
0x14000441b  mov     ecx, 0C0000273h
0x140004420  jmp     loc_1400044C5
0x140004425  mov     ecx, 0C0000163h
0x14000442a  jmp     loc_1400044C5
0x14000442f  mov     ecx, 0C0000161h
0x140004434  jmp     loc_1400044C5
0x140004439  mov     ecx, 0C0000025h
0x14000443e  jmp     loc_1400044C5
0x140004443  mov     ecx, 0C0000095h
0x140004448  jmp     short loc_1400044C5
0x14000444a  mov     ecx, 0C0000059h
0x14000444f  jmp     short loc_1400044C5
0x140004451  cmp     ecx, 8007050Ch
0x140004457  jz      short loc_1400044C0
0x140004459  cmp     ecx, 8007054Fh
0x14000445f  jz      short loc_1400044B9
0x140004461  cmp     ecx, 800705B9h
0x140004467  jz      short loc_1400044B2
0x140004469  test    ecx, ecx
0x14000446b  jz      short loc_1400044AE
0x14000446d  bt      ecx, 1Ch
0x140004471  jnb     short loc_140004479
0x140004473  btr     ecx, 1Ch
0x140004477  jmp     short loc_1400044C5
0x140004479  mov     eax, ecx
0x14000447b  and     eax, 1FFF0000h
0x140004480  cmp     eax, 70000h
0x140004485  jnz     short loc_140004498
0x140004487  movzx   ecx, cx
0x14000448a  mov     eax, ecx
0x14000448c  or      eax, 0C0070000h
0x140004491  test    ecx, ecx
0x140004493  cmovnz  ecx, eax
0x140004496  jmp     short loc_1400044C5
0x140004498  cmp     eax, 90000h
0x14000449d  jnz     short loc_1400044B9
0x14000449f  test    ecx, ecx
0x1400044a1  jle     short loc_1400044C5
0x1400044a3  movzx   ecx, cx
0x1400044a6  or      ecx, 0C0090000h
0x1400044ac  jmp     short loc_1400044C5
0x1400044ae  xor     ecx, ecx
0x1400044b0  jmp     short loc_1400044C5
0x1400044b2  mov     ecx, 0C000A083h
0x1400044b7  jmp     short loc_1400044C5
0x1400044b9  mov     ecx, 0C00000E5h
0x1400044be  jmp     short loc_1400044C5
0x1400044c0  mov     ecx, 0C000042Bh
0x1400044c5  mov     eax, ecx
0x1400044c7  retn
```

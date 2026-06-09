# wil::details::HrToNtStatus(long)

- ea: `0x14000357c`
- end: `0x140003738`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001bc8`
- `0x140001c68`
- `0x140001cb8`
- `0x140001d70`
- `0x140002b58`
- `0x140003740`

## callees

- `0x14000357c`

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
0x14000357c  mov     eax, 800700EAh
0x140003581  cmp     ecx, eax
0x140003583  jg      loc_140003658
0x140003589  jz      loc_14000364E
0x14000358f  mov     eax, 80070057h
0x140003594  cmp     ecx, eax
0x140003596  jg      short loc_140003602
0x140003598  jz      short loc_1400035F8
0x14000359a  cmp     ecx, 80004005h
0x1400035a0  jz      short loc_1400035EE
0x1400035a2  cmp     ecx, 80070001h
0x1400035a8  jz      short loc_1400035E4
0x1400035aa  cmp     ecx, 80070002h
0x1400035b0  jz      short loc_1400035DA
0x1400035b2  cmp     ecx, 80070003h
0x1400035b8  jz      short loc_1400035D0
0x1400035ba  cmp     ecx, 8007000Eh
0x1400035c0  jnz     loc_1400036DD
0x1400035c6  mov     ecx, 0C0000017h
0x1400035cb  jmp     loc_140003735
0x1400035d0  mov     ecx, 0C000003Ah
0x1400035d5  jmp     loc_140003735
0x1400035da  mov     ecx, 0C0000034h
0x1400035df  jmp     loc_140003735
0x1400035e4  mov     ecx, 0C0000002h
0x1400035e9  jmp     loc_140003735
0x1400035ee  mov     ecx, 0C0000001h
0x1400035f3  jmp     loc_140003735
0x1400035f8  mov     ecx, 0C000000Dh
0x1400035fd  jmp     loc_140003735
0x140003602  cmp     ecx, 80070070h
0x140003608  jz      short loc_140003644
0x14000360a  cmp     ecx, 8007007Ah
0x140003610  jz      short loc_14000363A
0x140003612  cmp     ecx, 8007007Bh
0x140003618  jz      short loc_140003630
0x14000361a  cmp     ecx, 8007007Eh
0x140003620  jnz     loc_1400036DD
0x140003626  mov     ecx, 0C0000135h
0x14000362b  jmp     loc_140003735
0x140003630  mov     ecx, 0C0000033h
0x140003635  jmp     loc_140003735
0x14000363a  mov     ecx, 0C0000023h
0x14000363f  jmp     loc_140003735
0x140003644  mov     ecx, 0C000007Fh
0x140003649  jmp     loc_140003735
0x14000364e  mov     ecx, 80000005h
0x140003653  jmp     loc_140003735
0x140003658  mov     eax, 8007047Eh
0x14000365d  cmp     ecx, eax
0x14000365f  jg      short loc_1400036C1
0x140003661  jz      short loc_1400036BA
0x140003663  cmp     ecx, 80070216h
0x140003669  jz      short loc_1400036B3
0x14000366b  cmp     ecx, 8007023Eh
0x140003671  jz      short loc_1400036A9
0x140003673  cmp     ecx, 80070246h
0x140003679  jz      short loc_14000369F
0x14000367b  cmp     ecx, 80070247h
0x140003681  jz      short loc_140003695
0x140003683  cmp     ecx, 80070272h
0x140003689  jnz     short loc_1400036DD
0x14000368b  mov     ecx, 0C0000273h
0x140003690  jmp     loc_140003735
0x140003695  mov     ecx, 0C0000163h
0x14000369a  jmp     loc_140003735
0x14000369f  mov     ecx, 0C0000161h
0x1400036a4  jmp     loc_140003735
0x1400036a9  mov     ecx, 0C0000025h
0x1400036ae  jmp     loc_140003735
0x1400036b3  mov     ecx, 0C0000095h
0x1400036b8  jmp     short loc_140003735
0x1400036ba  mov     ecx, 0C0000059h
0x1400036bf  jmp     short loc_140003735
0x1400036c1  cmp     ecx, 8007050Ch
0x1400036c7  jz      short loc_140003730
0x1400036c9  cmp     ecx, 8007054Fh
0x1400036cf  jz      short loc_140003729
0x1400036d1  cmp     ecx, 800705B9h
0x1400036d7  jz      short loc_140003722
0x1400036d9  test    ecx, ecx
0x1400036db  jz      short loc_14000371E
0x1400036dd  bt      ecx, 1Ch
0x1400036e1  jnb     short loc_1400036E9
0x1400036e3  btr     ecx, 1Ch
0x1400036e7  jmp     short loc_140003735
0x1400036e9  mov     eax, ecx
0x1400036eb  and     eax, 1FFF0000h
0x1400036f0  cmp     eax, 70000h
0x1400036f5  jnz     short loc_140003708
0x1400036f7  movzx   ecx, cx
0x1400036fa  mov     eax, ecx
0x1400036fc  or      eax, 0C0070000h
0x140003701  test    ecx, ecx
0x140003703  cmovnz  ecx, eax
0x140003706  jmp     short loc_140003735
0x140003708  cmp     eax, 90000h
0x14000370d  jnz     short loc_140003729
0x14000370f  test    ecx, ecx
0x140003711  jle     short loc_140003735
0x140003713  movzx   ecx, cx
0x140003716  or      ecx, 0C0090000h
0x14000371c  jmp     short loc_140003735
0x14000371e  xor     ecx, ecx
0x140003720  jmp     short loc_140003735
0x140003722  mov     ecx, 0C000A083h
0x140003727  jmp     short loc_140003735
0x140003729  mov     ecx, 0C00000E5h
0x14000372e  jmp     short loc_140003735
0x140003730  mov     ecx, 0C000042Bh
0x140003735  mov     eax, ecx
0x140003737  retn
```

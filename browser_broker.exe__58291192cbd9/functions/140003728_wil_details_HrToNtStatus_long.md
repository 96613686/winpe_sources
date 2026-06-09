# wil::details::HrToNtStatus(long)

- ea: `0x140003728`
- end: `0x1400038e4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020c0`
- `0x14000212c`
- `0x1400021a4`
- `0x1400021f4`
- `0x140002da8`
- `0x140003918`

## callees

- `0x140003728`

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
0x140003728  mov     eax, 800700EAh
0x14000372d  cmp     ecx, eax
0x14000372f  jg      loc_140003804
0x140003735  jz      loc_1400037FA
0x14000373b  mov     eax, 80070057h
0x140003740  cmp     ecx, eax
0x140003742  jg      short loc_1400037AE
0x140003744  jz      short loc_1400037A4
0x140003746  cmp     ecx, 80004005h
0x14000374c  jz      short loc_14000379A
0x14000374e  cmp     ecx, 80070001h
0x140003754  jz      short loc_140003790
0x140003756  cmp     ecx, 80070002h
0x14000375c  jz      short loc_140003786
0x14000375e  cmp     ecx, 80070003h
0x140003764  jz      short loc_14000377C
0x140003766  cmp     ecx, 8007000Eh
0x14000376c  jnz     loc_140003889
0x140003772  mov     ecx, 0C0000017h
0x140003777  jmp     loc_1400038E1
0x14000377c  mov     ecx, 0C000003Ah
0x140003781  jmp     loc_1400038E1
0x140003786  mov     ecx, 0C0000034h
0x14000378b  jmp     loc_1400038E1
0x140003790  mov     ecx, 0C0000002h
0x140003795  jmp     loc_1400038E1
0x14000379a  mov     ecx, 0C0000001h
0x14000379f  jmp     loc_1400038E1
0x1400037a4  mov     ecx, 0C000000Dh
0x1400037a9  jmp     loc_1400038E1
0x1400037ae  cmp     ecx, 80070070h
0x1400037b4  jz      short loc_1400037F0
0x1400037b6  cmp     ecx, 8007007Ah
0x1400037bc  jz      short loc_1400037E6
0x1400037be  cmp     ecx, 8007007Bh
0x1400037c4  jz      short loc_1400037DC
0x1400037c6  cmp     ecx, 8007007Eh
0x1400037cc  jnz     loc_140003889
0x1400037d2  mov     ecx, 0C0000135h
0x1400037d7  jmp     loc_1400038E1
0x1400037dc  mov     ecx, 0C0000033h
0x1400037e1  jmp     loc_1400038E1
0x1400037e6  mov     ecx, 0C0000023h
0x1400037eb  jmp     loc_1400038E1
0x1400037f0  mov     ecx, 0C000007Fh
0x1400037f5  jmp     loc_1400038E1
0x1400037fa  mov     ecx, 80000005h
0x1400037ff  jmp     loc_1400038E1
0x140003804  mov     eax, 8007047Eh
0x140003809  cmp     ecx, eax
0x14000380b  jg      short loc_14000386D
0x14000380d  jz      short loc_140003866
0x14000380f  cmp     ecx, 80070216h
0x140003815  jz      short loc_14000385F
0x140003817  cmp     ecx, 8007023Eh
0x14000381d  jz      short loc_140003855
0x14000381f  cmp     ecx, 80070246h
0x140003825  jz      short loc_14000384B
0x140003827  cmp     ecx, 80070247h
0x14000382d  jz      short loc_140003841
0x14000382f  cmp     ecx, 80070272h
0x140003835  jnz     short loc_140003889
0x140003837  mov     ecx, 0C0000273h
0x14000383c  jmp     loc_1400038E1
0x140003841  mov     ecx, 0C0000163h
0x140003846  jmp     loc_1400038E1
0x14000384b  mov     ecx, 0C0000161h
0x140003850  jmp     loc_1400038E1
0x140003855  mov     ecx, 0C0000025h
0x14000385a  jmp     loc_1400038E1
0x14000385f  mov     ecx, 0C0000095h
0x140003864  jmp     short loc_1400038E1
0x140003866  mov     ecx, 0C0000059h
0x14000386b  jmp     short loc_1400038E1
0x14000386d  cmp     ecx, 8007050Ch
0x140003873  jz      short loc_1400038DC
0x140003875  cmp     ecx, 8007054Fh
0x14000387b  jz      short loc_1400038D5
0x14000387d  cmp     ecx, 800705B9h
0x140003883  jz      short loc_1400038CE
0x140003885  test    ecx, ecx
0x140003887  jz      short loc_1400038CA
0x140003889  bt      ecx, 1Ch
0x14000388d  jnb     short loc_140003895
0x14000388f  btr     ecx, 1Ch
0x140003893  jmp     short loc_1400038E1
0x140003895  mov     eax, ecx
0x140003897  and     eax, 1FFF0000h
0x14000389c  cmp     eax, 70000h
0x1400038a1  jnz     short loc_1400038B4
0x1400038a3  movzx   ecx, cx
0x1400038a6  mov     eax, ecx
0x1400038a8  or      eax, 0C0070000h
0x1400038ad  test    ecx, ecx
0x1400038af  cmovnz  ecx, eax
0x1400038b2  jmp     short loc_1400038E1
0x1400038b4  cmp     eax, 90000h
0x1400038b9  jnz     short loc_1400038D5
0x1400038bb  test    ecx, ecx
0x1400038bd  jle     short loc_1400038E1
0x1400038bf  movzx   ecx, cx
0x1400038c2  or      ecx, 0C0090000h
0x1400038c8  jmp     short loc_1400038E1
0x1400038ca  xor     ecx, ecx
0x1400038cc  jmp     short loc_1400038E1
0x1400038ce  mov     ecx, 0C000A083h
0x1400038d3  jmp     short loc_1400038E1
0x1400038d5  mov     ecx, 0C00000E5h
0x1400038da  jmp     short loc_1400038E1
0x1400038dc  mov     ecx, 0C000042Bh
0x1400038e1  mov     eax, ecx
0x1400038e3  retn
```

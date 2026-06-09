# wil::details::HrToNtStatus(long)

- ea: `0x180005670`
- end: `0x18000582c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b44`
- `0x180002bec`
- `0x180002c3c`
- `0x180002cfc`
- `0x180004c48`
- `0x18000591c`

## callees

- `0x180005670`

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
0x180005670  mov     eax, 800700EAh
0x180005675  cmp     ecx, eax
0x180005677  jg      loc_18000574C
0x18000567d  jz      loc_180005742
0x180005683  mov     eax, 80070057h
0x180005688  cmp     ecx, eax
0x18000568a  jg      short loc_1800056F6
0x18000568c  jz      short loc_1800056EC
0x18000568e  cmp     ecx, 80004005h
0x180005694  jz      short loc_1800056E2
0x180005696  cmp     ecx, 80070001h
0x18000569c  jz      short loc_1800056D8
0x18000569e  cmp     ecx, 80070002h
0x1800056a4  jz      short loc_1800056CE
0x1800056a6  cmp     ecx, 80070003h
0x1800056ac  jz      short loc_1800056C4
0x1800056ae  cmp     ecx, 8007000Eh
0x1800056b4  jnz     loc_1800057D1
0x1800056ba  mov     ecx, 0C0000017h
0x1800056bf  jmp     loc_180005829
0x1800056c4  mov     ecx, 0C000003Ah
0x1800056c9  jmp     loc_180005829
0x1800056ce  mov     ecx, 0C0000034h
0x1800056d3  jmp     loc_180005829
0x1800056d8  mov     ecx, 0C0000002h
0x1800056dd  jmp     loc_180005829
0x1800056e2  mov     ecx, 0C0000001h
0x1800056e7  jmp     loc_180005829
0x1800056ec  mov     ecx, 0C000000Dh
0x1800056f1  jmp     loc_180005829
0x1800056f6  cmp     ecx, 80070070h
0x1800056fc  jz      short loc_180005738
0x1800056fe  cmp     ecx, 8007007Ah
0x180005704  jz      short loc_18000572E
0x180005706  cmp     ecx, 8007007Bh
0x18000570c  jz      short loc_180005724
0x18000570e  cmp     ecx, 8007007Eh
0x180005714  jnz     loc_1800057D1
0x18000571a  mov     ecx, 0C0000135h
0x18000571f  jmp     loc_180005829
0x180005724  mov     ecx, 0C0000033h
0x180005729  jmp     loc_180005829
0x18000572e  mov     ecx, 0C0000023h
0x180005733  jmp     loc_180005829
0x180005738  mov     ecx, 0C000007Fh
0x18000573d  jmp     loc_180005829
0x180005742  mov     ecx, 80000005h
0x180005747  jmp     loc_180005829
0x18000574c  mov     eax, 8007047Eh
0x180005751  cmp     ecx, eax
0x180005753  jg      short loc_1800057B5
0x180005755  jz      short loc_1800057AE
0x180005757  cmp     ecx, 80070216h
0x18000575d  jz      short loc_1800057A7
0x18000575f  cmp     ecx, 8007023Eh
0x180005765  jz      short loc_18000579D
0x180005767  cmp     ecx, 80070246h
0x18000576d  jz      short loc_180005793
0x18000576f  cmp     ecx, 80070247h
0x180005775  jz      short loc_180005789
0x180005777  cmp     ecx, 80070272h
0x18000577d  jnz     short loc_1800057D1
0x18000577f  mov     ecx, 0C0000273h
0x180005784  jmp     loc_180005829
0x180005789  mov     ecx, 0C0000163h
0x18000578e  jmp     loc_180005829
0x180005793  mov     ecx, 0C0000161h
0x180005798  jmp     loc_180005829
0x18000579d  mov     ecx, 0C0000025h
0x1800057a2  jmp     loc_180005829
0x1800057a7  mov     ecx, 0C0000095h
0x1800057ac  jmp     short loc_180005829
0x1800057ae  mov     ecx, 0C0000059h
0x1800057b3  jmp     short loc_180005829
0x1800057b5  cmp     ecx, 8007050Ch
0x1800057bb  jz      short loc_180005824
0x1800057bd  cmp     ecx, 8007054Fh
0x1800057c3  jz      short loc_18000581D
0x1800057c5  cmp     ecx, 800705B9h
0x1800057cb  jz      short loc_180005816
0x1800057cd  test    ecx, ecx
0x1800057cf  jz      short loc_180005812
0x1800057d1  bt      ecx, 1Ch
0x1800057d5  jnb     short loc_1800057DD
0x1800057d7  btr     ecx, 1Ch
0x1800057db  jmp     short loc_180005829
0x1800057dd  mov     eax, ecx
0x1800057df  and     eax, 1FFF0000h
0x1800057e4  cmp     eax, 70000h
0x1800057e9  jnz     short loc_1800057FC
0x1800057eb  movzx   ecx, cx
0x1800057ee  mov     eax, ecx
0x1800057f0  or      eax, 0C0070000h
0x1800057f5  test    ecx, ecx
0x1800057f7  cmovnz  ecx, eax
0x1800057fa  jmp     short loc_180005829
0x1800057fc  cmp     eax, 90000h
0x180005801  jnz     short loc_18000581D
0x180005803  test    ecx, ecx
0x180005805  jle     short loc_180005829
0x180005807  movzx   ecx, cx
0x18000580a  or      ecx, 0C0090000h
0x180005810  jmp     short loc_180005829
0x180005812  xor     ecx, ecx
0x180005814  jmp     short loc_180005829
0x180005816  mov     ecx, 0C000A083h
0x18000581b  jmp     short loc_180005829
0x18000581d  mov     ecx, 0C00000E5h
0x180005822  jmp     short loc_180005829
0x180005824  mov     ecx, 0C000042Bh
0x180005829  mov     eax, ecx
0x18000582b  retn
```

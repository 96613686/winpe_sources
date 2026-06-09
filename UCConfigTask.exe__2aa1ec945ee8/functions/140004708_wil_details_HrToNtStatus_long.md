# wil::details::HrToNtStatus(long)

- ea: `0x140004708`
- end: `0x1400048c4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400022dc`
- `0x140002354`
- `0x1400023d4`
- `0x140002424`
- `0x140003cf8`
- `0x140004a0c`

## callees

- `0x140004708`

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
0x140004708  mov     eax, 800700EAh
0x14000470d  cmp     ecx, eax
0x14000470f  jg      loc_1400047E4
0x140004715  jz      loc_1400047DA
0x14000471b  mov     eax, 80070057h
0x140004720  cmp     ecx, eax
0x140004722  jg      short loc_14000478E
0x140004724  jz      short loc_140004784
0x140004726  cmp     ecx, 80004005h
0x14000472c  jz      short loc_14000477A
0x14000472e  cmp     ecx, 80070001h
0x140004734  jz      short loc_140004770
0x140004736  cmp     ecx, 80070002h
0x14000473c  jz      short loc_140004766
0x14000473e  cmp     ecx, 80070003h
0x140004744  jz      short loc_14000475C
0x140004746  cmp     ecx, 8007000Eh
0x14000474c  jnz     loc_140004869
0x140004752  mov     ecx, 0C0000017h
0x140004757  jmp     loc_1400048C1
0x14000475c  mov     ecx, 0C000003Ah
0x140004761  jmp     loc_1400048C1
0x140004766  mov     ecx, 0C0000034h
0x14000476b  jmp     loc_1400048C1
0x140004770  mov     ecx, 0C0000002h
0x140004775  jmp     loc_1400048C1
0x14000477a  mov     ecx, 0C0000001h
0x14000477f  jmp     loc_1400048C1
0x140004784  mov     ecx, 0C000000Dh
0x140004789  jmp     loc_1400048C1
0x14000478e  cmp     ecx, 80070070h
0x140004794  jz      short loc_1400047D0
0x140004796  cmp     ecx, 8007007Ah
0x14000479c  jz      short loc_1400047C6
0x14000479e  cmp     ecx, 8007007Bh
0x1400047a4  jz      short loc_1400047BC
0x1400047a6  cmp     ecx, 8007007Eh
0x1400047ac  jnz     loc_140004869
0x1400047b2  mov     ecx, 0C0000135h
0x1400047b7  jmp     loc_1400048C1
0x1400047bc  mov     ecx, 0C0000033h
0x1400047c1  jmp     loc_1400048C1
0x1400047c6  mov     ecx, 0C0000023h
0x1400047cb  jmp     loc_1400048C1
0x1400047d0  mov     ecx, 0C000007Fh
0x1400047d5  jmp     loc_1400048C1
0x1400047da  mov     ecx, 80000005h
0x1400047df  jmp     loc_1400048C1
0x1400047e4  mov     eax, 8007047Eh
0x1400047e9  cmp     ecx, eax
0x1400047eb  jg      short loc_14000484D
0x1400047ed  jz      short loc_140004846
0x1400047ef  cmp     ecx, 80070216h
0x1400047f5  jz      short loc_14000483F
0x1400047f7  cmp     ecx, 8007023Eh
0x1400047fd  jz      short loc_140004835
0x1400047ff  cmp     ecx, 80070246h
0x140004805  jz      short loc_14000482B
0x140004807  cmp     ecx, 80070247h
0x14000480d  jz      short loc_140004821
0x14000480f  cmp     ecx, 80070272h
0x140004815  jnz     short loc_140004869
0x140004817  mov     ecx, 0C0000273h
0x14000481c  jmp     loc_1400048C1
0x140004821  mov     ecx, 0C0000163h
0x140004826  jmp     loc_1400048C1
0x14000482b  mov     ecx, 0C0000161h
0x140004830  jmp     loc_1400048C1
0x140004835  mov     ecx, 0C0000025h
0x14000483a  jmp     loc_1400048C1
0x14000483f  mov     ecx, 0C0000095h
0x140004844  jmp     short loc_1400048C1
0x140004846  mov     ecx, 0C0000059h
0x14000484b  jmp     short loc_1400048C1
0x14000484d  cmp     ecx, 8007050Ch
0x140004853  jz      short loc_1400048BC
0x140004855  cmp     ecx, 8007054Fh
0x14000485b  jz      short loc_1400048B5
0x14000485d  cmp     ecx, 800705B9h
0x140004863  jz      short loc_1400048AE
0x140004865  test    ecx, ecx
0x140004867  jz      short loc_1400048AA
0x140004869  bt      ecx, 1Ch
0x14000486d  jnb     short loc_140004875
0x14000486f  btr     ecx, 1Ch
0x140004873  jmp     short loc_1400048C1
0x140004875  mov     eax, ecx
0x140004877  and     eax, 1FFF0000h
0x14000487c  cmp     eax, 70000h
0x140004881  jnz     short loc_140004894
0x140004883  movzx   ecx, cx
0x140004886  mov     eax, ecx
0x140004888  or      eax, 0C0070000h
0x14000488d  test    ecx, ecx
0x14000488f  cmovnz  ecx, eax
0x140004892  jmp     short loc_1400048C1
0x140004894  cmp     eax, 90000h
0x140004899  jnz     short loc_1400048B5
0x14000489b  test    ecx, ecx
0x14000489d  jle     short loc_1400048C1
0x14000489f  movzx   ecx, cx
0x1400048a2  or      ecx, 0C0090000h
0x1400048a8  jmp     short loc_1400048C1
0x1400048aa  xor     ecx, ecx
0x1400048ac  jmp     short loc_1400048C1
0x1400048ae  mov     ecx, 0C000A083h
0x1400048b3  jmp     short loc_1400048C1
0x1400048b5  mov     ecx, 0C00000E5h
0x1400048ba  jmp     short loc_1400048C1
0x1400048bc  mov     ecx, 0C000042Bh
0x1400048c1  mov     eax, ecx
0x1400048c3  retn
```

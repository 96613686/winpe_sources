# wil::details::HrToNtStatus(long)

- ea: `0x1800055dc`
- end: `0x180005798`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028d4`
- `0x180002974`
- `0x1800029c4`
- `0x180002a84`
- `0x180004bb8`
- `0x1800058b4`

## callees

- `0x1800055dc`

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
0x1800055dc  mov     eax, 800700EAh
0x1800055e1  cmp     ecx, eax
0x1800055e3  jg      loc_1800056B8
0x1800055e9  jz      loc_1800056AE
0x1800055ef  mov     eax, 80070057h
0x1800055f4  cmp     ecx, eax
0x1800055f6  jg      short loc_180005662
0x1800055f8  jz      short loc_180005658
0x1800055fa  cmp     ecx, 80004005h
0x180005600  jz      short loc_18000564E
0x180005602  cmp     ecx, 80070001h
0x180005608  jz      short loc_180005644
0x18000560a  cmp     ecx, 80070002h
0x180005610  jz      short loc_18000563A
0x180005612  cmp     ecx, 80070003h
0x180005618  jz      short loc_180005630
0x18000561a  cmp     ecx, 8007000Eh
0x180005620  jnz     loc_18000573D
0x180005626  mov     ecx, 0C0000017h
0x18000562b  jmp     loc_180005795
0x180005630  mov     ecx, 0C000003Ah
0x180005635  jmp     loc_180005795
0x18000563a  mov     ecx, 0C0000034h
0x18000563f  jmp     loc_180005795
0x180005644  mov     ecx, 0C0000002h
0x180005649  jmp     loc_180005795
0x18000564e  mov     ecx, 0C0000001h
0x180005653  jmp     loc_180005795
0x180005658  mov     ecx, 0C000000Dh
0x18000565d  jmp     loc_180005795
0x180005662  cmp     ecx, 80070070h
0x180005668  jz      short loc_1800056A4
0x18000566a  cmp     ecx, 8007007Ah
0x180005670  jz      short loc_18000569A
0x180005672  cmp     ecx, 8007007Bh
0x180005678  jz      short loc_180005690
0x18000567a  cmp     ecx, 8007007Eh
0x180005680  jnz     loc_18000573D
0x180005686  mov     ecx, 0C0000135h
0x18000568b  jmp     loc_180005795
0x180005690  mov     ecx, 0C0000033h
0x180005695  jmp     loc_180005795
0x18000569a  mov     ecx, 0C0000023h
0x18000569f  jmp     loc_180005795
0x1800056a4  mov     ecx, 0C000007Fh
0x1800056a9  jmp     loc_180005795
0x1800056ae  mov     ecx, 80000005h
0x1800056b3  jmp     loc_180005795
0x1800056b8  mov     eax, 8007047Eh
0x1800056bd  cmp     ecx, eax
0x1800056bf  jg      short loc_180005721
0x1800056c1  jz      short loc_18000571A
0x1800056c3  cmp     ecx, 80070216h
0x1800056c9  jz      short loc_180005713
0x1800056cb  cmp     ecx, 8007023Eh
0x1800056d1  jz      short loc_180005709
0x1800056d3  cmp     ecx, 80070246h
0x1800056d9  jz      short loc_1800056FF
0x1800056db  cmp     ecx, 80070247h
0x1800056e1  jz      short loc_1800056F5
0x1800056e3  cmp     ecx, 80070272h
0x1800056e9  jnz     short loc_18000573D
0x1800056eb  mov     ecx, 0C0000273h
0x1800056f0  jmp     loc_180005795
0x1800056f5  mov     ecx, 0C0000163h
0x1800056fa  jmp     loc_180005795
0x1800056ff  mov     ecx, 0C0000161h
0x180005704  jmp     loc_180005795
0x180005709  mov     ecx, 0C0000025h
0x18000570e  jmp     loc_180005795
0x180005713  mov     ecx, 0C0000095h
0x180005718  jmp     short loc_180005795
0x18000571a  mov     ecx, 0C0000059h
0x18000571f  jmp     short loc_180005795
0x180005721  cmp     ecx, 8007050Ch
0x180005727  jz      short loc_180005790
0x180005729  cmp     ecx, 8007054Fh
0x18000572f  jz      short loc_180005789
0x180005731  cmp     ecx, 800705B9h
0x180005737  jz      short loc_180005782
0x180005739  test    ecx, ecx
0x18000573b  jz      short loc_18000577E
0x18000573d  bt      ecx, 1Ch
0x180005741  jnb     short loc_180005749
0x180005743  btr     ecx, 1Ch
0x180005747  jmp     short loc_180005795
0x180005749  mov     eax, ecx
0x18000574b  and     eax, 1FFF0000h
0x180005750  cmp     eax, 70000h
0x180005755  jnz     short loc_180005768
0x180005757  movzx   ecx, cx
0x18000575a  mov     eax, ecx
0x18000575c  or      eax, 0C0070000h
0x180005761  test    ecx, ecx
0x180005763  cmovnz  ecx, eax
0x180005766  jmp     short loc_180005795
0x180005768  cmp     eax, 90000h
0x18000576d  jnz     short loc_180005789
0x18000576f  test    ecx, ecx
0x180005771  jle     short loc_180005795
0x180005773  movzx   ecx, cx
0x180005776  or      ecx, 0C0090000h
0x18000577c  jmp     short loc_180005795
0x18000577e  xor     ecx, ecx
0x180005780  jmp     short loc_180005795
0x180005782  mov     ecx, 0C000A083h
0x180005787  jmp     short loc_180005795
0x180005789  mov     ecx, 0C00000E5h
0x18000578e  jmp     short loc_180005795
0x180005790  mov     ecx, 0C000042Bh
0x180005795  mov     eax, ecx
0x180005797  retn
```

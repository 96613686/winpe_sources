# wil::details::HrToNtStatus(long)

- ea: `0x180006f5c`
- end: `0x180007118`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ed0`
- `0x1800080a0`
- `0x180008110`
- `0x180008160`
- `0x1800095f8`
- `0x18000a2a0`

## callees

- `0x180006f5c`

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
0x180006f5c  mov     eax, 800700EAh
0x180006f61  cmp     ecx, eax
0x180006f63  jg      loc_180007038
0x180006f69  jz      loc_18000702E
0x180006f6f  mov     eax, 80070057h
0x180006f74  cmp     ecx, eax
0x180006f76  jg      short loc_180006FE2
0x180006f78  jz      short loc_180006FD8
0x180006f7a  cmp     ecx, 80004005h
0x180006f80  jz      short loc_180006FCE
0x180006f82  cmp     ecx, 80070001h
0x180006f88  jz      short loc_180006FC4
0x180006f8a  cmp     ecx, 80070002h
0x180006f90  jz      short loc_180006FBA
0x180006f92  cmp     ecx, 80070003h
0x180006f98  jz      short loc_180006FB0
0x180006f9a  cmp     ecx, 8007000Eh
0x180006fa0  jnz     loc_1800070BD
0x180006fa6  mov     ecx, 0C0000017h
0x180006fab  jmp     loc_180007115
0x180006fb0  mov     ecx, 0C000003Ah
0x180006fb5  jmp     loc_180007115
0x180006fba  mov     ecx, 0C0000034h
0x180006fbf  jmp     loc_180007115
0x180006fc4  mov     ecx, 0C0000002h
0x180006fc9  jmp     loc_180007115
0x180006fce  mov     ecx, 0C0000001h
0x180006fd3  jmp     loc_180007115
0x180006fd8  mov     ecx, 0C000000Dh
0x180006fdd  jmp     loc_180007115
0x180006fe2  cmp     ecx, 80070070h
0x180006fe8  jz      short loc_180007024
0x180006fea  cmp     ecx, 8007007Ah
0x180006ff0  jz      short loc_18000701A
0x180006ff2  cmp     ecx, 8007007Bh
0x180006ff8  jz      short loc_180007010
0x180006ffa  cmp     ecx, 8007007Eh
0x180007000  jnz     loc_1800070BD
0x180007006  mov     ecx, 0C0000135h
0x18000700b  jmp     loc_180007115
0x180007010  mov     ecx, 0C0000033h
0x180007015  jmp     loc_180007115
0x18000701a  mov     ecx, 0C0000023h
0x18000701f  jmp     loc_180007115
0x180007024  mov     ecx, 0C000007Fh
0x180007029  jmp     loc_180007115
0x18000702e  mov     ecx, 80000005h
0x180007033  jmp     loc_180007115
0x180007038  mov     eax, 8007047Eh
0x18000703d  cmp     ecx, eax
0x18000703f  jg      short loc_1800070A1
0x180007041  jz      short loc_18000709A
0x180007043  cmp     ecx, 80070216h
0x180007049  jz      short loc_180007093
0x18000704b  cmp     ecx, 8007023Eh
0x180007051  jz      short loc_180007089
0x180007053  cmp     ecx, 80070246h
0x180007059  jz      short loc_18000707F
0x18000705b  cmp     ecx, 80070247h
0x180007061  jz      short loc_180007075
0x180007063  cmp     ecx, 80070272h
0x180007069  jnz     short loc_1800070BD
0x18000706b  mov     ecx, 0C0000273h
0x180007070  jmp     loc_180007115
0x180007075  mov     ecx, 0C0000163h
0x18000707a  jmp     loc_180007115
0x18000707f  mov     ecx, 0C0000161h
0x180007084  jmp     loc_180007115
0x180007089  mov     ecx, 0C0000025h
0x18000708e  jmp     loc_180007115
0x180007093  mov     ecx, 0C0000095h
0x180007098  jmp     short loc_180007115
0x18000709a  mov     ecx, 0C0000059h
0x18000709f  jmp     short loc_180007115
0x1800070a1  cmp     ecx, 8007050Ch
0x1800070a7  jz      short loc_180007110
0x1800070a9  cmp     ecx, 8007054Fh
0x1800070af  jz      short loc_180007109
0x1800070b1  cmp     ecx, 800705B9h
0x1800070b7  jz      short loc_180007102
0x1800070b9  test    ecx, ecx
0x1800070bb  jz      short loc_1800070FE
0x1800070bd  bt      ecx, 1Ch
0x1800070c1  jnb     short loc_1800070C9
0x1800070c3  btr     ecx, 1Ch
0x1800070c7  jmp     short loc_180007115
0x1800070c9  mov     eax, ecx
0x1800070cb  and     eax, 1FFF0000h
0x1800070d0  cmp     eax, 70000h
0x1800070d5  jnz     short loc_1800070E8
0x1800070d7  movzx   ecx, cx
0x1800070da  mov     eax, ecx
0x1800070dc  or      eax, 0C0070000h
0x1800070e1  test    ecx, ecx
0x1800070e3  cmovnz  ecx, eax
0x1800070e6  jmp     short loc_180007115
0x1800070e8  cmp     eax, 90000h
0x1800070ed  jnz     short loc_180007109
0x1800070ef  test    ecx, ecx
0x1800070f1  jle     short loc_180007115
0x1800070f3  movzx   ecx, cx
0x1800070f6  or      ecx, 0C0090000h
0x1800070fc  jmp     short loc_180007115
0x1800070fe  xor     ecx, ecx
0x180007100  jmp     short loc_180007115
0x180007102  mov     ecx, 0C000A083h
0x180007107  jmp     short loc_180007115
0x180007109  mov     ecx, 0C00000E5h
0x18000710e  jmp     short loc_180007115
0x180007110  mov     ecx, 0C000042Bh
0x180007115  mov     eax, ecx
0x180007117  retn
```

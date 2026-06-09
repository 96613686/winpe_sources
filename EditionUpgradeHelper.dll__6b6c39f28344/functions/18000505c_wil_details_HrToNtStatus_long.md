# wil::details::HrToNtStatus(long)

- ea: `0x18000505c`
- end: `0x180005218`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027c0`
- `0x180002860`
- `0x1800028b0`
- `0x180002970`
- `0x180004638`
- `0x180005220`

## callees

- `0x18000505c`

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
0x18000505c  mov     eax, 800700EAh
0x180005061  cmp     ecx, eax
0x180005063  jg      loc_180005138
0x180005069  jz      loc_18000512E
0x18000506f  mov     eax, 80070057h
0x180005074  cmp     ecx, eax
0x180005076  jg      short loc_1800050E2
0x180005078  jz      short loc_1800050D8
0x18000507a  cmp     ecx, 80004005h
0x180005080  jz      short loc_1800050CE
0x180005082  cmp     ecx, 80070001h
0x180005088  jz      short loc_1800050C4
0x18000508a  cmp     ecx, 80070002h
0x180005090  jz      short loc_1800050BA
0x180005092  cmp     ecx, 80070003h
0x180005098  jz      short loc_1800050B0
0x18000509a  cmp     ecx, 8007000Eh
0x1800050a0  jnz     loc_1800051BD
0x1800050a6  mov     ecx, 0C0000017h
0x1800050ab  jmp     loc_180005215
0x1800050b0  mov     ecx, 0C000003Ah
0x1800050b5  jmp     loc_180005215
0x1800050ba  mov     ecx, 0C0000034h
0x1800050bf  jmp     loc_180005215
0x1800050c4  mov     ecx, 0C0000002h
0x1800050c9  jmp     loc_180005215
0x1800050ce  mov     ecx, 0C0000001h
0x1800050d3  jmp     loc_180005215
0x1800050d8  mov     ecx, 0C000000Dh
0x1800050dd  jmp     loc_180005215
0x1800050e2  cmp     ecx, 80070070h
0x1800050e8  jz      short loc_180005124
0x1800050ea  cmp     ecx, 8007007Ah
0x1800050f0  jz      short loc_18000511A
0x1800050f2  cmp     ecx, 8007007Bh
0x1800050f8  jz      short loc_180005110
0x1800050fa  cmp     ecx, 8007007Eh
0x180005100  jnz     loc_1800051BD
0x180005106  mov     ecx, 0C0000135h
0x18000510b  jmp     loc_180005215
0x180005110  mov     ecx, 0C0000033h
0x180005115  jmp     loc_180005215
0x18000511a  mov     ecx, 0C0000023h
0x18000511f  jmp     loc_180005215
0x180005124  mov     ecx, 0C000007Fh
0x180005129  jmp     loc_180005215
0x18000512e  mov     ecx, 80000005h
0x180005133  jmp     loc_180005215
0x180005138  mov     eax, 8007047Eh
0x18000513d  cmp     ecx, eax
0x18000513f  jg      short loc_1800051A1
0x180005141  jz      short loc_18000519A
0x180005143  cmp     ecx, 80070216h
0x180005149  jz      short loc_180005193
0x18000514b  cmp     ecx, 8007023Eh
0x180005151  jz      short loc_180005189
0x180005153  cmp     ecx, 80070246h
0x180005159  jz      short loc_18000517F
0x18000515b  cmp     ecx, 80070247h
0x180005161  jz      short loc_180005175
0x180005163  cmp     ecx, 80070272h
0x180005169  jnz     short loc_1800051BD
0x18000516b  mov     ecx, 0C0000273h
0x180005170  jmp     loc_180005215
0x180005175  mov     ecx, 0C0000163h
0x18000517a  jmp     loc_180005215
0x18000517f  mov     ecx, 0C0000161h
0x180005184  jmp     loc_180005215
0x180005189  mov     ecx, 0C0000025h
0x18000518e  jmp     loc_180005215
0x180005193  mov     ecx, 0C0000095h
0x180005198  jmp     short loc_180005215
0x18000519a  mov     ecx, 0C0000059h
0x18000519f  jmp     short loc_180005215
0x1800051a1  cmp     ecx, 8007050Ch
0x1800051a7  jz      short loc_180005210
0x1800051a9  cmp     ecx, 8007054Fh
0x1800051af  jz      short loc_180005209
0x1800051b1  cmp     ecx, 800705B9h
0x1800051b7  jz      short loc_180005202
0x1800051b9  test    ecx, ecx
0x1800051bb  jz      short loc_1800051FE
0x1800051bd  bt      ecx, 1Ch
0x1800051c1  jnb     short loc_1800051C9
0x1800051c3  btr     ecx, 1Ch
0x1800051c7  jmp     short loc_180005215
0x1800051c9  mov     eax, ecx
0x1800051cb  and     eax, 1FFF0000h
0x1800051d0  cmp     eax, 70000h
0x1800051d5  jnz     short loc_1800051E8
0x1800051d7  movzx   ecx, cx
0x1800051da  mov     eax, ecx
0x1800051dc  or      eax, 0C0070000h
0x1800051e1  test    ecx, ecx
0x1800051e3  cmovnz  ecx, eax
0x1800051e6  jmp     short loc_180005215
0x1800051e8  cmp     eax, 90000h
0x1800051ed  jnz     short loc_180005209
0x1800051ef  test    ecx, ecx
0x1800051f1  jle     short loc_180005215
0x1800051f3  movzx   ecx, cx
0x1800051f6  or      ecx, 0C0090000h
0x1800051fc  jmp     short loc_180005215
0x1800051fe  xor     ecx, ecx
0x180005200  jmp     short loc_180005215
0x180005202  mov     ecx, 0C000A083h
0x180005207  jmp     short loc_180005215
0x180005209  mov     ecx, 0C00000E5h
0x18000520e  jmp     short loc_180005215
0x180005210  mov     ecx, 0C000042Bh
0x180005215  mov     eax, ecx
0x180005217  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x180007254`
- end: `0x180007410`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042f4`
- `0x18000439c`
- `0x1800043ec`
- `0x1800044a4`
- `0x18000681c`
- `0x180007580`

## callees

- `0x180007254`

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
0x180007254  mov     eax, 800700EAh
0x180007259  cmp     ecx, eax
0x18000725b  jg      loc_180007330
0x180007261  jz      loc_180007326
0x180007267  mov     eax, 80070057h
0x18000726c  cmp     ecx, eax
0x18000726e  jg      short loc_1800072DA
0x180007270  jz      short loc_1800072D0
0x180007272  cmp     ecx, 80004005h
0x180007278  jz      short loc_1800072C6
0x18000727a  cmp     ecx, 80070001h
0x180007280  jz      short loc_1800072BC
0x180007282  cmp     ecx, 80070002h
0x180007288  jz      short loc_1800072B2
0x18000728a  cmp     ecx, 80070003h
0x180007290  jz      short loc_1800072A8
0x180007292  cmp     ecx, 8007000Eh
0x180007298  jnz     loc_1800073B5
0x18000729e  mov     ecx, 0C0000017h
0x1800072a3  jmp     loc_18000740D
0x1800072a8  mov     ecx, 0C000003Ah
0x1800072ad  jmp     loc_18000740D
0x1800072b2  mov     ecx, 0C0000034h
0x1800072b7  jmp     loc_18000740D
0x1800072bc  mov     ecx, 0C0000002h
0x1800072c1  jmp     loc_18000740D
0x1800072c6  mov     ecx, 0C0000001h
0x1800072cb  jmp     loc_18000740D
0x1800072d0  mov     ecx, 0C000000Dh
0x1800072d5  jmp     loc_18000740D
0x1800072da  cmp     ecx, 80070070h
0x1800072e0  jz      short loc_18000731C
0x1800072e2  cmp     ecx, 8007007Ah
0x1800072e8  jz      short loc_180007312
0x1800072ea  cmp     ecx, 8007007Bh
0x1800072f0  jz      short loc_180007308
0x1800072f2  cmp     ecx, 8007007Eh
0x1800072f8  jnz     loc_1800073B5
0x1800072fe  mov     ecx, 0C0000135h
0x180007303  jmp     loc_18000740D
0x180007308  mov     ecx, 0C0000033h
0x18000730d  jmp     loc_18000740D
0x180007312  mov     ecx, 0C0000023h
0x180007317  jmp     loc_18000740D
0x18000731c  mov     ecx, 0C000007Fh
0x180007321  jmp     loc_18000740D
0x180007326  mov     ecx, 80000005h
0x18000732b  jmp     loc_18000740D
0x180007330  mov     eax, 8007047Eh
0x180007335  cmp     ecx, eax
0x180007337  jg      short loc_180007399
0x180007339  jz      short loc_180007392
0x18000733b  cmp     ecx, 80070216h
0x180007341  jz      short loc_18000738B
0x180007343  cmp     ecx, 8007023Eh
0x180007349  jz      short loc_180007381
0x18000734b  cmp     ecx, 80070246h
0x180007351  jz      short loc_180007377
0x180007353  cmp     ecx, 80070247h
0x180007359  jz      short loc_18000736D
0x18000735b  cmp     ecx, 80070272h
0x180007361  jnz     short loc_1800073B5
0x180007363  mov     ecx, 0C0000273h
0x180007368  jmp     loc_18000740D
0x18000736d  mov     ecx, 0C0000163h
0x180007372  jmp     loc_18000740D
0x180007377  mov     ecx, 0C0000161h
0x18000737c  jmp     loc_18000740D
0x180007381  mov     ecx, 0C0000025h
0x180007386  jmp     loc_18000740D
0x18000738b  mov     ecx, 0C0000095h
0x180007390  jmp     short loc_18000740D
0x180007392  mov     ecx, 0C0000059h
0x180007397  jmp     short loc_18000740D
0x180007399  cmp     ecx, 8007050Ch
0x18000739f  jz      short loc_180007408
0x1800073a1  cmp     ecx, 8007054Fh
0x1800073a7  jz      short loc_180007401
0x1800073a9  cmp     ecx, 800705B9h
0x1800073af  jz      short loc_1800073FA
0x1800073b1  test    ecx, ecx
0x1800073b3  jz      short loc_1800073F6
0x1800073b5  bt      ecx, 1Ch
0x1800073b9  jnb     short loc_1800073C1
0x1800073bb  btr     ecx, 1Ch
0x1800073bf  jmp     short loc_18000740D
0x1800073c1  mov     eax, ecx
0x1800073c3  and     eax, 1FFF0000h
0x1800073c8  cmp     eax, 70000h
0x1800073cd  jnz     short loc_1800073E0
0x1800073cf  movzx   ecx, cx
0x1800073d2  mov     eax, ecx
0x1800073d4  or      eax, 0C0070000h
0x1800073d9  test    ecx, ecx
0x1800073db  cmovnz  ecx, eax
0x1800073de  jmp     short loc_18000740D
0x1800073e0  cmp     eax, 90000h
0x1800073e5  jnz     short loc_180007401
0x1800073e7  test    ecx, ecx
0x1800073e9  jle     short loc_18000740D
0x1800073eb  movzx   ecx, cx
0x1800073ee  or      ecx, 0C0090000h
0x1800073f4  jmp     short loc_18000740D
0x1800073f6  xor     ecx, ecx
0x1800073f8  jmp     short loc_18000740D
0x1800073fa  mov     ecx, 0C000A083h
0x1800073ff  jmp     short loc_18000740D
0x180007401  mov     ecx, 0C00000E5h
0x180007406  jmp     short loc_18000740D
0x180007408  mov     ecx, 0C000042Bh
0x18000740d  mov     eax, ecx
0x18000740f  retn
```

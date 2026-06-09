# wil::details::HrToNtStatus(long)

- ea: `0x1800072dc`
- end: `0x180007498`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a80`
- `0x180004b20`
- `0x180004b70`
- `0x180004c30`
- `0x1800068b8`
- `0x1800074a0`

## callees

- `0x1800072dc`

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
0x1800072dc  mov     eax, 800700EAh
0x1800072e1  cmp     ecx, eax
0x1800072e3  jg      loc_1800073B8
0x1800072e9  jz      loc_1800073AE
0x1800072ef  mov     eax, 80070057h
0x1800072f4  cmp     ecx, eax
0x1800072f6  jg      short loc_180007362
0x1800072f8  jz      short loc_180007358
0x1800072fa  cmp     ecx, 80004005h
0x180007300  jz      short loc_18000734E
0x180007302  cmp     ecx, 80070001h
0x180007308  jz      short loc_180007344
0x18000730a  cmp     ecx, 80070002h
0x180007310  jz      short loc_18000733A
0x180007312  cmp     ecx, 80070003h
0x180007318  jz      short loc_180007330
0x18000731a  cmp     ecx, 8007000Eh
0x180007320  jnz     loc_18000743D
0x180007326  mov     ecx, 0C0000017h
0x18000732b  jmp     loc_180007495
0x180007330  mov     ecx, 0C000003Ah
0x180007335  jmp     loc_180007495
0x18000733a  mov     ecx, 0C0000034h
0x18000733f  jmp     loc_180007495
0x180007344  mov     ecx, 0C0000002h
0x180007349  jmp     loc_180007495
0x18000734e  mov     ecx, 0C0000001h
0x180007353  jmp     loc_180007495
0x180007358  mov     ecx, 0C000000Dh
0x18000735d  jmp     loc_180007495
0x180007362  cmp     ecx, 80070070h
0x180007368  jz      short loc_1800073A4
0x18000736a  cmp     ecx, 8007007Ah
0x180007370  jz      short loc_18000739A
0x180007372  cmp     ecx, 8007007Bh
0x180007378  jz      short loc_180007390
0x18000737a  cmp     ecx, 8007007Eh
0x180007380  jnz     loc_18000743D
0x180007386  mov     ecx, 0C0000135h
0x18000738b  jmp     loc_180007495
0x180007390  mov     ecx, 0C0000033h
0x180007395  jmp     loc_180007495
0x18000739a  mov     ecx, 0C0000023h
0x18000739f  jmp     loc_180007495
0x1800073a4  mov     ecx, 0C000007Fh
0x1800073a9  jmp     loc_180007495
0x1800073ae  mov     ecx, 80000005h
0x1800073b3  jmp     loc_180007495
0x1800073b8  mov     eax, 8007047Eh
0x1800073bd  cmp     ecx, eax
0x1800073bf  jg      short loc_180007421
0x1800073c1  jz      short loc_18000741A
0x1800073c3  cmp     ecx, 80070216h
0x1800073c9  jz      short loc_180007413
0x1800073cb  cmp     ecx, 8007023Eh
0x1800073d1  jz      short loc_180007409
0x1800073d3  cmp     ecx, 80070246h
0x1800073d9  jz      short loc_1800073FF
0x1800073db  cmp     ecx, 80070247h
0x1800073e1  jz      short loc_1800073F5
0x1800073e3  cmp     ecx, 80070272h
0x1800073e9  jnz     short loc_18000743D
0x1800073eb  mov     ecx, 0C0000273h
0x1800073f0  jmp     loc_180007495
0x1800073f5  mov     ecx, 0C0000163h
0x1800073fa  jmp     loc_180007495
0x1800073ff  mov     ecx, 0C0000161h
0x180007404  jmp     loc_180007495
0x180007409  mov     ecx, 0C0000025h
0x18000740e  jmp     loc_180007495
0x180007413  mov     ecx, 0C0000095h
0x180007418  jmp     short loc_180007495
0x18000741a  mov     ecx, 0C0000059h
0x18000741f  jmp     short loc_180007495
0x180007421  cmp     ecx, 8007050Ch
0x180007427  jz      short loc_180007490
0x180007429  cmp     ecx, 8007054Fh
0x18000742f  jz      short loc_180007489
0x180007431  cmp     ecx, 800705B9h
0x180007437  jz      short loc_180007482
0x180007439  test    ecx, ecx
0x18000743b  jz      short loc_18000747E
0x18000743d  bt      ecx, 1Ch
0x180007441  jnb     short loc_180007449
0x180007443  btr     ecx, 1Ch
0x180007447  jmp     short loc_180007495
0x180007449  mov     eax, ecx
0x18000744b  and     eax, 1FFF0000h
0x180007450  cmp     eax, 70000h
0x180007455  jnz     short loc_180007468
0x180007457  movzx   ecx, cx
0x18000745a  mov     eax, ecx
0x18000745c  or      eax, 0C0070000h
0x180007461  test    ecx, ecx
0x180007463  cmovnz  ecx, eax
0x180007466  jmp     short loc_180007495
0x180007468  cmp     eax, 90000h
0x18000746d  jnz     short loc_180007489
0x18000746f  test    ecx, ecx
0x180007471  jle     short loc_180007495
0x180007473  movzx   ecx, cx
0x180007476  or      ecx, 0C0090000h
0x18000747c  jmp     short loc_180007495
0x18000747e  xor     ecx, ecx
0x180007480  jmp     short loc_180007495
0x180007482  mov     ecx, 0C000A083h
0x180007487  jmp     short loc_180007495
0x180007489  mov     ecx, 0C00000E5h
0x18000748e  jmp     short loc_180007495
0x180007490  mov     ecx, 0C000042Bh
0x180007495  mov     eax, ecx
0x180007497  retn
```

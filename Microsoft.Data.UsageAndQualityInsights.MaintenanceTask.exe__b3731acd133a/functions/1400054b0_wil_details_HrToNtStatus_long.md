# wil::details::HrToNtStatus(long)

- ea: `0x1400054b0`
- end: `0x14000566c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000265c`
- `0x1400026fc`
- `0x14000274c`
- `0x14000280c`
- `0x140004a88`
- `0x14000575c`

## callees

- `0x1400054b0`

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
0x1400054b0  mov     eax, 800700EAh
0x1400054b5  cmp     ecx, eax
0x1400054b7  jg      loc_14000558C
0x1400054bd  jz      loc_140005582
0x1400054c3  mov     eax, 80070057h
0x1400054c8  cmp     ecx, eax
0x1400054ca  jg      short loc_140005536
0x1400054cc  jz      short loc_14000552C
0x1400054ce  cmp     ecx, 80004005h
0x1400054d4  jz      short loc_140005522
0x1400054d6  cmp     ecx, 80070001h
0x1400054dc  jz      short loc_140005518
0x1400054de  cmp     ecx, 80070002h
0x1400054e4  jz      short loc_14000550E
0x1400054e6  cmp     ecx, 80070003h
0x1400054ec  jz      short loc_140005504
0x1400054ee  cmp     ecx, 8007000Eh
0x1400054f4  jnz     loc_140005611
0x1400054fa  mov     ecx, 0C0000017h
0x1400054ff  jmp     loc_140005669
0x140005504  mov     ecx, 0C000003Ah
0x140005509  jmp     loc_140005669
0x14000550e  mov     ecx, 0C0000034h
0x140005513  jmp     loc_140005669
0x140005518  mov     ecx, 0C0000002h
0x14000551d  jmp     loc_140005669
0x140005522  mov     ecx, 0C0000001h
0x140005527  jmp     loc_140005669
0x14000552c  mov     ecx, 0C000000Dh
0x140005531  jmp     loc_140005669
0x140005536  cmp     ecx, 80070070h
0x14000553c  jz      short loc_140005578
0x14000553e  cmp     ecx, 8007007Ah
0x140005544  jz      short loc_14000556E
0x140005546  cmp     ecx, 8007007Bh
0x14000554c  jz      short loc_140005564
0x14000554e  cmp     ecx, 8007007Eh
0x140005554  jnz     loc_140005611
0x14000555a  mov     ecx, 0C0000135h
0x14000555f  jmp     loc_140005669
0x140005564  mov     ecx, 0C0000033h
0x140005569  jmp     loc_140005669
0x14000556e  mov     ecx, 0C0000023h
0x140005573  jmp     loc_140005669
0x140005578  mov     ecx, 0C000007Fh
0x14000557d  jmp     loc_140005669
0x140005582  mov     ecx, 80000005h
0x140005587  jmp     loc_140005669
0x14000558c  mov     eax, 8007047Eh
0x140005591  cmp     ecx, eax
0x140005593  jg      short loc_1400055F5
0x140005595  jz      short loc_1400055EE
0x140005597  cmp     ecx, 80070216h
0x14000559d  jz      short loc_1400055E7
0x14000559f  cmp     ecx, 8007023Eh
0x1400055a5  jz      short loc_1400055DD
0x1400055a7  cmp     ecx, 80070246h
0x1400055ad  jz      short loc_1400055D3
0x1400055af  cmp     ecx, 80070247h
0x1400055b5  jz      short loc_1400055C9
0x1400055b7  cmp     ecx, 80070272h
0x1400055bd  jnz     short loc_140005611
0x1400055bf  mov     ecx, 0C0000273h
0x1400055c4  jmp     loc_140005669
0x1400055c9  mov     ecx, 0C0000163h
0x1400055ce  jmp     loc_140005669
0x1400055d3  mov     ecx, 0C0000161h
0x1400055d8  jmp     loc_140005669
0x1400055dd  mov     ecx, 0C0000025h
0x1400055e2  jmp     loc_140005669
0x1400055e7  mov     ecx, 0C0000095h
0x1400055ec  jmp     short loc_140005669
0x1400055ee  mov     ecx, 0C0000059h
0x1400055f3  jmp     short loc_140005669
0x1400055f5  cmp     ecx, 8007050Ch
0x1400055fb  jz      short loc_140005664
0x1400055fd  cmp     ecx, 8007054Fh
0x140005603  jz      short loc_14000565D
0x140005605  cmp     ecx, 800705B9h
0x14000560b  jz      short loc_140005656
0x14000560d  test    ecx, ecx
0x14000560f  jz      short loc_140005652
0x140005611  bt      ecx, 1Ch
0x140005615  jnb     short loc_14000561D
0x140005617  btr     ecx, 1Ch
0x14000561b  jmp     short loc_140005669
0x14000561d  mov     eax, ecx
0x14000561f  and     eax, 1FFF0000h
0x140005624  cmp     eax, 70000h
0x140005629  jnz     short loc_14000563C
0x14000562b  movzx   ecx, cx
0x14000562e  mov     eax, ecx
0x140005630  or      eax, 0C0070000h
0x140005635  test    ecx, ecx
0x140005637  cmovnz  ecx, eax
0x14000563a  jmp     short loc_140005669
0x14000563c  cmp     eax, 90000h
0x140005641  jnz     short loc_14000565D
0x140005643  test    ecx, ecx
0x140005645  jle     short loc_140005669
0x140005647  movzx   ecx, cx
0x14000564a  or      ecx, 0C0090000h
0x140005650  jmp     short loc_140005669
0x140005652  xor     ecx, ecx
0x140005654  jmp     short loc_140005669
0x140005656  mov     ecx, 0C000A083h
0x14000565b  jmp     short loc_140005669
0x14000565d  mov     ecx, 0C00000E5h
0x140005662  jmp     short loc_140005669
0x140005664  mov     ecx, 0C000042Bh
0x140005669  mov     eax, ecx
0x14000566b  retn
```

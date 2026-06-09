# wil::details::HrToNtStatus(long)

- ea: `0x180005010`
- end: `0x1800051cc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003130`
- `0x1800031d0`
- `0x180003220`
- `0x1800032e0`
- `0x1800046a8`
- `0x1800051d4`

## callees

- `0x180005010`

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
0x180005010  mov     eax, 800700EAh
0x180005015  cmp     ecx, eax
0x180005017  jg      loc_1800050EC
0x18000501d  jz      loc_1800050E2
0x180005023  mov     eax, 80070057h
0x180005028  cmp     ecx, eax
0x18000502a  jg      short loc_180005096
0x18000502c  jz      short loc_18000508C
0x18000502e  cmp     ecx, 80004005h
0x180005034  jz      short loc_180005082
0x180005036  cmp     ecx, 80070001h
0x18000503c  jz      short loc_180005078
0x18000503e  cmp     ecx, 80070002h
0x180005044  jz      short loc_18000506E
0x180005046  cmp     ecx, 80070003h
0x18000504c  jz      short loc_180005064
0x18000504e  cmp     ecx, 8007000Eh
0x180005054  jnz     loc_180005171
0x18000505a  mov     ecx, 0C0000017h
0x18000505f  jmp     loc_1800051C9
0x180005064  mov     ecx, 0C000003Ah
0x180005069  jmp     loc_1800051C9
0x18000506e  mov     ecx, 0C0000034h
0x180005073  jmp     loc_1800051C9
0x180005078  mov     ecx, 0C0000002h
0x18000507d  jmp     loc_1800051C9
0x180005082  mov     ecx, 0C0000001h
0x180005087  jmp     loc_1800051C9
0x18000508c  mov     ecx, 0C000000Dh
0x180005091  jmp     loc_1800051C9
0x180005096  cmp     ecx, 80070070h
0x18000509c  jz      short loc_1800050D8
0x18000509e  cmp     ecx, 8007007Ah
0x1800050a4  jz      short loc_1800050CE
0x1800050a6  cmp     ecx, 8007007Bh
0x1800050ac  jz      short loc_1800050C4
0x1800050ae  cmp     ecx, 8007007Eh
0x1800050b4  jnz     loc_180005171
0x1800050ba  mov     ecx, 0C0000135h
0x1800050bf  jmp     loc_1800051C9
0x1800050c4  mov     ecx, 0C0000033h
0x1800050c9  jmp     loc_1800051C9
0x1800050ce  mov     ecx, 0C0000023h
0x1800050d3  jmp     loc_1800051C9
0x1800050d8  mov     ecx, 0C000007Fh
0x1800050dd  jmp     loc_1800051C9
0x1800050e2  mov     ecx, 80000005h
0x1800050e7  jmp     loc_1800051C9
0x1800050ec  mov     eax, 8007047Eh
0x1800050f1  cmp     ecx, eax
0x1800050f3  jg      short loc_180005155
0x1800050f5  jz      short loc_18000514E
0x1800050f7  cmp     ecx, 80070216h
0x1800050fd  jz      short loc_180005147
0x1800050ff  cmp     ecx, 8007023Eh
0x180005105  jz      short loc_18000513D
0x180005107  cmp     ecx, 80070246h
0x18000510d  jz      short loc_180005133
0x18000510f  cmp     ecx, 80070247h
0x180005115  jz      short loc_180005129
0x180005117  cmp     ecx, 80070272h
0x18000511d  jnz     short loc_180005171
0x18000511f  mov     ecx, 0C0000273h
0x180005124  jmp     loc_1800051C9
0x180005129  mov     ecx, 0C0000163h
0x18000512e  jmp     loc_1800051C9
0x180005133  mov     ecx, 0C0000161h
0x180005138  jmp     loc_1800051C9
0x18000513d  mov     ecx, 0C0000025h
0x180005142  jmp     loc_1800051C9
0x180005147  mov     ecx, 0C0000095h
0x18000514c  jmp     short loc_1800051C9
0x18000514e  mov     ecx, 0C0000059h
0x180005153  jmp     short loc_1800051C9
0x180005155  cmp     ecx, 8007050Ch
0x18000515b  jz      short loc_1800051C4
0x18000515d  cmp     ecx, 8007054Fh
0x180005163  jz      short loc_1800051BD
0x180005165  cmp     ecx, 800705B9h
0x18000516b  jz      short loc_1800051B6
0x18000516d  test    ecx, ecx
0x18000516f  jz      short loc_1800051B2
0x180005171  bt      ecx, 1Ch
0x180005175  jnb     short loc_18000517D
0x180005177  btr     ecx, 1Ch
0x18000517b  jmp     short loc_1800051C9
0x18000517d  mov     eax, ecx
0x18000517f  and     eax, 1FFF0000h
0x180005184  cmp     eax, 70000h
0x180005189  jnz     short loc_18000519C
0x18000518b  movzx   ecx, cx
0x18000518e  mov     eax, ecx
0x180005190  or      eax, 0C0070000h
0x180005195  test    ecx, ecx
0x180005197  cmovnz  ecx, eax
0x18000519a  jmp     short loc_1800051C9
0x18000519c  cmp     eax, 90000h
0x1800051a1  jnz     short loc_1800051BD
0x1800051a3  test    ecx, ecx
0x1800051a5  jle     short loc_1800051C9
0x1800051a7  movzx   ecx, cx
0x1800051aa  or      ecx, 0C0090000h
0x1800051b0  jmp     short loc_1800051C9
0x1800051b2  xor     ecx, ecx
0x1800051b4  jmp     short loc_1800051C9
0x1800051b6  mov     ecx, 0C000A083h
0x1800051bb  jmp     short loc_1800051C9
0x1800051bd  mov     ecx, 0C00000E5h
0x1800051c2  jmp     short loc_1800051C9
0x1800051c4  mov     ecx, 0C000042Bh
0x1800051c9  mov     eax, ecx
0x1800051cb  retn
```

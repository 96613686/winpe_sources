# wil::details::HrToNtStatus(long)

- ea: `0x180004edc`
- end: `0x180005098`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003698`
- `0x180003750`
- `0x1800037a8`
- `0x180003860`
- `0x180004454`
- `0x1800050a0`
- `0x180007304`
- `0x180007378`
- `0x18000d7e8`

## callees

- `0x180004edc`

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
0x180004edc  mov     eax, 800700EAh
0x180004ee1  cmp     ecx, eax
0x180004ee3  jg      loc_180004FB8
0x180004ee9  jz      loc_180004FAE
0x180004eef  mov     eax, 80070057h
0x180004ef4  cmp     ecx, eax
0x180004ef6  jg      short loc_180004F62
0x180004ef8  jz      short loc_180004F58
0x180004efa  cmp     ecx, 80004005h
0x180004f00  jz      short loc_180004F4E
0x180004f02  cmp     ecx, 80070001h
0x180004f08  jz      short loc_180004F44
0x180004f0a  cmp     ecx, 80070002h
0x180004f10  jz      short loc_180004F3A
0x180004f12  cmp     ecx, 80070003h
0x180004f18  jz      short loc_180004F30
0x180004f1a  cmp     ecx, 8007000Eh
0x180004f20  jnz     loc_18000503D
0x180004f26  mov     ecx, 0C0000017h
0x180004f2b  jmp     loc_180005095
0x180004f30  mov     ecx, 0C000003Ah
0x180004f35  jmp     loc_180005095
0x180004f3a  mov     ecx, 0C0000034h
0x180004f3f  jmp     loc_180005095
0x180004f44  mov     ecx, 0C0000002h
0x180004f49  jmp     loc_180005095
0x180004f4e  mov     ecx, 0C0000001h
0x180004f53  jmp     loc_180005095
0x180004f58  mov     ecx, 0C000000Dh
0x180004f5d  jmp     loc_180005095
0x180004f62  cmp     ecx, 80070070h
0x180004f68  jz      short loc_180004FA4
0x180004f6a  cmp     ecx, 8007007Ah
0x180004f70  jz      short loc_180004F9A
0x180004f72  cmp     ecx, 8007007Bh
0x180004f78  jz      short loc_180004F90
0x180004f7a  cmp     ecx, 8007007Eh
0x180004f80  jnz     loc_18000503D
0x180004f86  mov     ecx, 0C0000135h
0x180004f8b  jmp     loc_180005095
0x180004f90  mov     ecx, 0C0000033h
0x180004f95  jmp     loc_180005095
0x180004f9a  mov     ecx, 0C0000023h
0x180004f9f  jmp     loc_180005095
0x180004fa4  mov     ecx, 0C000007Fh
0x180004fa9  jmp     loc_180005095
0x180004fae  mov     ecx, 80000005h
0x180004fb3  jmp     loc_180005095
0x180004fb8  mov     eax, 8007047Eh
0x180004fbd  cmp     ecx, eax
0x180004fbf  jg      short loc_180005021
0x180004fc1  jz      short loc_18000501A
0x180004fc3  cmp     ecx, 80070216h
0x180004fc9  jz      short loc_180005013
0x180004fcb  cmp     ecx, 8007023Eh
0x180004fd1  jz      short loc_180005009
0x180004fd3  cmp     ecx, 80070246h
0x180004fd9  jz      short loc_180004FFF
0x180004fdb  cmp     ecx, 80070247h
0x180004fe1  jz      short loc_180004FF5
0x180004fe3  cmp     ecx, 80070272h
0x180004fe9  jnz     short loc_18000503D
0x180004feb  mov     ecx, 0C0000273h
0x180004ff0  jmp     loc_180005095
0x180004ff5  mov     ecx, 0C0000163h
0x180004ffa  jmp     loc_180005095
0x180004fff  mov     ecx, 0C0000161h
0x180005004  jmp     loc_180005095
0x180005009  mov     ecx, 0C0000025h
0x18000500e  jmp     loc_180005095
0x180005013  mov     ecx, 0C0000095h
0x180005018  jmp     short loc_180005095
0x18000501a  mov     ecx, 0C0000059h
0x18000501f  jmp     short loc_180005095
0x180005021  cmp     ecx, 8007050Ch
0x180005027  jz      short loc_180005090
0x180005029  cmp     ecx, 8007054Fh
0x18000502f  jz      short loc_180005089
0x180005031  cmp     ecx, 800705B9h
0x180005037  jz      short loc_180005082
0x180005039  test    ecx, ecx
0x18000503b  jz      short loc_18000507E
0x18000503d  bt      ecx, 1Ch
0x180005041  jnb     short loc_180005049
0x180005043  btr     ecx, 1Ch
0x180005047  jmp     short loc_180005095
0x180005049  mov     eax, ecx
0x18000504b  and     eax, 1FFF0000h
0x180005050  cmp     eax, 70000h
0x180005055  jnz     short loc_180005068
0x180005057  movzx   ecx, cx
0x18000505a  mov     eax, ecx
0x18000505c  or      eax, 0C0070000h
0x180005061  test    ecx, ecx
0x180005063  cmovnz  ecx, eax
0x180005066  jmp     short loc_180005095
0x180005068  cmp     eax, 90000h
0x18000506d  jnz     short loc_180005089
0x18000506f  test    ecx, ecx
0x180005071  jle     short loc_180005095
0x180005073  movzx   ecx, cx
0x180005076  or      ecx, 0C0090000h
0x18000507c  jmp     short loc_180005095
0x18000507e  xor     ecx, ecx
0x180005080  jmp     short loc_180005095
0x180005082  mov     ecx, 0C000A083h
0x180005087  jmp     short loc_180005095
0x180005089  mov     ecx, 0C00000E5h
0x18000508e  jmp     short loc_180005095
0x180005090  mov     ecx, 0C000042Bh
0x180005095  mov     eax, ecx
0x180005097  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x180004ebc`
- end: `0x180005078`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000312c`
- `0x1800031dc`
- `0x180003234`
- `0x1800032fc`
- `0x180004488`
- `0x180005080`
- `0x180005800`
- `0x180007074`
- `0x1800071c8`
- `0x18000bfbe`
- `0x18000c029`
- `0x18000c0f2`
- `0x18000c15d`

## callees

- `0x180004ebc`

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
0x180004ebc  mov     eax, 800700EAh
0x180004ec1  cmp     ecx, eax
0x180004ec3  jg      loc_180004F98
0x180004ec9  jz      loc_180004F8E
0x180004ecf  mov     eax, 80070057h
0x180004ed4  cmp     ecx, eax
0x180004ed6  jg      short loc_180004F42
0x180004ed8  jz      short loc_180004F38
0x180004eda  cmp     ecx, 80004005h
0x180004ee0  jz      short loc_180004F2E
0x180004ee2  cmp     ecx, 80070001h
0x180004ee8  jz      short loc_180004F24
0x180004eea  cmp     ecx, 80070002h
0x180004ef0  jz      short loc_180004F1A
0x180004ef2  cmp     ecx, 80070003h
0x180004ef8  jz      short loc_180004F10
0x180004efa  cmp     ecx, 8007000Eh
0x180004f00  jnz     loc_18000501D
0x180004f06  mov     ecx, 0C0000017h
0x180004f0b  jmp     loc_180005075
0x180004f10  mov     ecx, 0C000003Ah
0x180004f15  jmp     loc_180005075
0x180004f1a  mov     ecx, 0C0000034h
0x180004f1f  jmp     loc_180005075
0x180004f24  mov     ecx, 0C0000002h
0x180004f29  jmp     loc_180005075
0x180004f2e  mov     ecx, 0C0000001h
0x180004f33  jmp     loc_180005075
0x180004f38  mov     ecx, 0C000000Dh
0x180004f3d  jmp     loc_180005075
0x180004f42  cmp     ecx, 80070070h
0x180004f48  jz      short loc_180004F84
0x180004f4a  cmp     ecx, 8007007Ah
0x180004f50  jz      short loc_180004F7A
0x180004f52  cmp     ecx, 8007007Bh
0x180004f58  jz      short loc_180004F70
0x180004f5a  cmp     ecx, 8007007Eh
0x180004f60  jnz     loc_18000501D
0x180004f66  mov     ecx, 0C0000135h
0x180004f6b  jmp     loc_180005075
0x180004f70  mov     ecx, 0C0000033h
0x180004f75  jmp     loc_180005075
0x180004f7a  mov     ecx, 0C0000023h
0x180004f7f  jmp     loc_180005075
0x180004f84  mov     ecx, 0C000007Fh
0x180004f89  jmp     loc_180005075
0x180004f8e  mov     ecx, 80000005h
0x180004f93  jmp     loc_180005075
0x180004f98  mov     eax, 8007047Eh
0x180004f9d  cmp     ecx, eax
0x180004f9f  jg      short loc_180005001
0x180004fa1  jz      short loc_180004FFA
0x180004fa3  cmp     ecx, 80070216h
0x180004fa9  jz      short loc_180004FF3
0x180004fab  cmp     ecx, 8007023Eh
0x180004fb1  jz      short loc_180004FE9
0x180004fb3  cmp     ecx, 80070246h
0x180004fb9  jz      short loc_180004FDF
0x180004fbb  cmp     ecx, 80070247h
0x180004fc1  jz      short loc_180004FD5
0x180004fc3  cmp     ecx, 80070272h
0x180004fc9  jnz     short loc_18000501D
0x180004fcb  mov     ecx, 0C0000273h
0x180004fd0  jmp     loc_180005075
0x180004fd5  mov     ecx, 0C0000163h
0x180004fda  jmp     loc_180005075
0x180004fdf  mov     ecx, 0C0000161h
0x180004fe4  jmp     loc_180005075
0x180004fe9  mov     ecx, 0C0000025h
0x180004fee  jmp     loc_180005075
0x180004ff3  mov     ecx, 0C0000095h
0x180004ff8  jmp     short loc_180005075
0x180004ffa  mov     ecx, 0C0000059h
0x180004fff  jmp     short loc_180005075
0x180005001  cmp     ecx, 8007050Ch
0x180005007  jz      short loc_180005070
0x180005009  cmp     ecx, 8007054Fh
0x18000500f  jz      short loc_180005069
0x180005011  cmp     ecx, 800705B9h
0x180005017  jz      short loc_180005062
0x180005019  test    ecx, ecx
0x18000501b  jz      short loc_18000505E
0x18000501d  bt      ecx, 1Ch
0x180005021  jnb     short loc_180005029
0x180005023  btr     ecx, 1Ch
0x180005027  jmp     short loc_180005075
0x180005029  mov     eax, ecx
0x18000502b  and     eax, 1FFF0000h
0x180005030  cmp     eax, 70000h
0x180005035  jnz     short loc_180005048
0x180005037  movzx   ecx, cx
0x18000503a  mov     eax, ecx
0x18000503c  or      eax, 0C0070000h
0x180005041  test    ecx, ecx
0x180005043  cmovnz  ecx, eax
0x180005046  jmp     short loc_180005075
0x180005048  cmp     eax, 90000h
0x18000504d  jnz     short loc_180005069
0x18000504f  test    ecx, ecx
0x180005051  jle     short loc_180005075
0x180005053  movzx   ecx, cx
0x180005056  or      ecx, 0C0090000h
0x18000505c  jmp     short loc_180005075
0x18000505e  xor     ecx, ecx
0x180005060  jmp     short loc_180005075
0x180005062  mov     ecx, 0C000A083h
0x180005067  jmp     short loc_180005075
0x180005069  mov     ecx, 0C00000E5h
0x18000506e  jmp     short loc_180005075
0x180005070  mov     ecx, 0C000042Bh
0x180005075  mov     eax, ecx
0x180005077  retn
```

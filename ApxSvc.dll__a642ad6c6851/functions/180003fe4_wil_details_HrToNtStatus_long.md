# wil::details::HrToNtStatus(long)

- ea: `0x180003fe4`
- end: `0x1800041a0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022b4`
- `0x18000235c`
- `0x1800023ac`
- `0x180002464`
- `0x1800035b8`
- `0x1800041a8`

## callees

- `0x180003fe4`

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
0x180003fe4  mov     eax, 800700EAh
0x180003fe9  cmp     ecx, eax
0x180003feb  jg      loc_1800040C0
0x180003ff1  jz      loc_1800040B6
0x180003ff7  mov     eax, 80070057h
0x180003ffc  cmp     ecx, eax
0x180003ffe  jg      short loc_18000406A
0x180004000  jz      short loc_180004060
0x180004002  cmp     ecx, 80004005h
0x180004008  jz      short loc_180004056
0x18000400a  cmp     ecx, 80070001h
0x180004010  jz      short loc_18000404C
0x180004012  cmp     ecx, 80070002h
0x180004018  jz      short loc_180004042
0x18000401a  cmp     ecx, 80070003h
0x180004020  jz      short loc_180004038
0x180004022  cmp     ecx, 8007000Eh
0x180004028  jnz     loc_180004145
0x18000402e  mov     ecx, 0C0000017h
0x180004033  jmp     loc_18000419D
0x180004038  mov     ecx, 0C000003Ah
0x18000403d  jmp     loc_18000419D
0x180004042  mov     ecx, 0C0000034h
0x180004047  jmp     loc_18000419D
0x18000404c  mov     ecx, 0C0000002h
0x180004051  jmp     loc_18000419D
0x180004056  mov     ecx, 0C0000001h
0x18000405b  jmp     loc_18000419D
0x180004060  mov     ecx, 0C000000Dh
0x180004065  jmp     loc_18000419D
0x18000406a  cmp     ecx, 80070070h
0x180004070  jz      short loc_1800040AC
0x180004072  cmp     ecx, 8007007Ah
0x180004078  jz      short loc_1800040A2
0x18000407a  cmp     ecx, 8007007Bh
0x180004080  jz      short loc_180004098
0x180004082  cmp     ecx, 8007007Eh
0x180004088  jnz     loc_180004145
0x18000408e  mov     ecx, 0C0000135h
0x180004093  jmp     loc_18000419D
0x180004098  mov     ecx, 0C0000033h
0x18000409d  jmp     loc_18000419D
0x1800040a2  mov     ecx, 0C0000023h
0x1800040a7  jmp     loc_18000419D
0x1800040ac  mov     ecx, 0C000007Fh
0x1800040b1  jmp     loc_18000419D
0x1800040b6  mov     ecx, 80000005h
0x1800040bb  jmp     loc_18000419D
0x1800040c0  mov     eax, 8007047Eh
0x1800040c5  cmp     ecx, eax
0x1800040c7  jg      short loc_180004129
0x1800040c9  jz      short loc_180004122
0x1800040cb  cmp     ecx, 80070216h
0x1800040d1  jz      short loc_18000411B
0x1800040d3  cmp     ecx, 8007023Eh
0x1800040d9  jz      short loc_180004111
0x1800040db  cmp     ecx, 80070246h
0x1800040e1  jz      short loc_180004107
0x1800040e3  cmp     ecx, 80070247h
0x1800040e9  jz      short loc_1800040FD
0x1800040eb  cmp     ecx, 80070272h
0x1800040f1  jnz     short loc_180004145
0x1800040f3  mov     ecx, 0C0000273h
0x1800040f8  jmp     loc_18000419D
0x1800040fd  mov     ecx, 0C0000163h
0x180004102  jmp     loc_18000419D
0x180004107  mov     ecx, 0C0000161h
0x18000410c  jmp     loc_18000419D
0x180004111  mov     ecx, 0C0000025h
0x180004116  jmp     loc_18000419D
0x18000411b  mov     ecx, 0C0000095h
0x180004120  jmp     short loc_18000419D
0x180004122  mov     ecx, 0C0000059h
0x180004127  jmp     short loc_18000419D
0x180004129  cmp     ecx, 8007050Ch
0x18000412f  jz      short loc_180004198
0x180004131  cmp     ecx, 8007054Fh
0x180004137  jz      short loc_180004191
0x180004139  cmp     ecx, 800705B9h
0x18000413f  jz      short loc_18000418A
0x180004141  test    ecx, ecx
0x180004143  jz      short loc_180004186
0x180004145  bt      ecx, 1Ch
0x180004149  jnb     short loc_180004151
0x18000414b  btr     ecx, 1Ch
0x18000414f  jmp     short loc_18000419D
0x180004151  mov     eax, ecx
0x180004153  and     eax, 1FFF0000h
0x180004158  cmp     eax, 70000h
0x18000415d  jnz     short loc_180004170
0x18000415f  movzx   ecx, cx
0x180004162  mov     eax, ecx
0x180004164  or      eax, 0C0070000h
0x180004169  test    ecx, ecx
0x18000416b  cmovnz  ecx, eax
0x18000416e  jmp     short loc_18000419D
0x180004170  cmp     eax, 90000h
0x180004175  jnz     short loc_180004191
0x180004177  test    ecx, ecx
0x180004179  jle     short loc_18000419D
0x18000417b  movzx   ecx, cx
0x18000417e  or      ecx, 0C0090000h
0x180004184  jmp     short loc_18000419D
0x180004186  xor     ecx, ecx
0x180004188  jmp     short loc_18000419D
0x18000418a  mov     ecx, 0C000A083h
0x18000418f  jmp     short loc_18000419D
0x180004191  mov     ecx, 0C00000E5h
0x180004196  jmp     short loc_18000419D
0x180004198  mov     ecx, 0C000042Bh
0x18000419d  mov     eax, ecx
0x18000419f  retn
```

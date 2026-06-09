# wil::details::HrToNtStatus(long)

- ea: `0x180003fa4`
- end: `0x180004160`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002244`
- `0x1800022f4`
- `0x18000234c`
- `0x18000240c`
- `0x180003578`
- `0x180004168`
- `0x1800059a8`
- `0x18000a0a0`

## callees

- `0x180003fa4`

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
0x180003fa4  mov     eax, 800700EAh
0x180003fa9  cmp     ecx, eax
0x180003fab  jg      loc_180004080
0x180003fb1  jz      loc_180004076
0x180003fb7  mov     eax, 80070057h
0x180003fbc  cmp     ecx, eax
0x180003fbe  jg      short loc_18000402A
0x180003fc0  jz      short loc_180004020
0x180003fc2  cmp     ecx, 80004005h
0x180003fc8  jz      short loc_180004016
0x180003fca  cmp     ecx, 80070001h
0x180003fd0  jz      short loc_18000400C
0x180003fd2  cmp     ecx, 80070002h
0x180003fd8  jz      short loc_180004002
0x180003fda  cmp     ecx, 80070003h
0x180003fe0  jz      short loc_180003FF8
0x180003fe2  cmp     ecx, 8007000Eh
0x180003fe8  jnz     loc_180004105
0x180003fee  mov     ecx, 0C0000017h
0x180003ff3  jmp     loc_18000415D
0x180003ff8  mov     ecx, 0C000003Ah
0x180003ffd  jmp     loc_18000415D
0x180004002  mov     ecx, 0C0000034h
0x180004007  jmp     loc_18000415D
0x18000400c  mov     ecx, 0C0000002h
0x180004011  jmp     loc_18000415D
0x180004016  mov     ecx, 0C0000001h
0x18000401b  jmp     loc_18000415D
0x180004020  mov     ecx, 0C000000Dh
0x180004025  jmp     loc_18000415D
0x18000402a  cmp     ecx, 80070070h
0x180004030  jz      short loc_18000406C
0x180004032  cmp     ecx, 8007007Ah
0x180004038  jz      short loc_180004062
0x18000403a  cmp     ecx, 8007007Bh
0x180004040  jz      short loc_180004058
0x180004042  cmp     ecx, 8007007Eh
0x180004048  jnz     loc_180004105
0x18000404e  mov     ecx, 0C0000135h
0x180004053  jmp     loc_18000415D
0x180004058  mov     ecx, 0C0000033h
0x18000405d  jmp     loc_18000415D
0x180004062  mov     ecx, 0C0000023h
0x180004067  jmp     loc_18000415D
0x18000406c  mov     ecx, 0C000007Fh
0x180004071  jmp     loc_18000415D
0x180004076  mov     ecx, 80000005h
0x18000407b  jmp     loc_18000415D
0x180004080  mov     eax, 8007047Eh
0x180004085  cmp     ecx, eax
0x180004087  jg      short loc_1800040E9
0x180004089  jz      short loc_1800040E2
0x18000408b  cmp     ecx, 80070216h
0x180004091  jz      short loc_1800040DB
0x180004093  cmp     ecx, 8007023Eh
0x180004099  jz      short loc_1800040D1
0x18000409b  cmp     ecx, 80070246h
0x1800040a1  jz      short loc_1800040C7
0x1800040a3  cmp     ecx, 80070247h
0x1800040a9  jz      short loc_1800040BD
0x1800040ab  cmp     ecx, 80070272h
0x1800040b1  jnz     short loc_180004105
0x1800040b3  mov     ecx, 0C0000273h
0x1800040b8  jmp     loc_18000415D
0x1800040bd  mov     ecx, 0C0000163h
0x1800040c2  jmp     loc_18000415D
0x1800040c7  mov     ecx, 0C0000161h
0x1800040cc  jmp     loc_18000415D
0x1800040d1  mov     ecx, 0C0000025h
0x1800040d6  jmp     loc_18000415D
0x1800040db  mov     ecx, 0C0000095h
0x1800040e0  jmp     short loc_18000415D
0x1800040e2  mov     ecx, 0C0000059h
0x1800040e7  jmp     short loc_18000415D
0x1800040e9  cmp     ecx, 8007050Ch
0x1800040ef  jz      short loc_180004158
0x1800040f1  cmp     ecx, 8007054Fh
0x1800040f7  jz      short loc_180004151
0x1800040f9  cmp     ecx, 800705B9h
0x1800040ff  jz      short loc_18000414A
0x180004101  test    ecx, ecx
0x180004103  jz      short loc_180004146
0x180004105  bt      ecx, 1Ch
0x180004109  jnb     short loc_180004111
0x18000410b  btr     ecx, 1Ch
0x18000410f  jmp     short loc_18000415D
0x180004111  mov     eax, ecx
0x180004113  and     eax, 1FFF0000h
0x180004118  cmp     eax, 70000h
0x18000411d  jnz     short loc_180004130
0x18000411f  movzx   ecx, cx
0x180004122  mov     eax, ecx
0x180004124  or      eax, 0C0070000h
0x180004129  test    ecx, ecx
0x18000412b  cmovnz  ecx, eax
0x18000412e  jmp     short loc_18000415D
0x180004130  cmp     eax, 90000h
0x180004135  jnz     short loc_180004151
0x180004137  test    ecx, ecx
0x180004139  jle     short loc_18000415D
0x18000413b  movzx   ecx, cx
0x18000413e  or      ecx, 0C0090000h
0x180004144  jmp     short loc_18000415D
0x180004146  xor     ecx, ecx
0x180004148  jmp     short loc_18000415D
0x18000414a  mov     ecx, 0C000A083h
0x18000414f  jmp     short loc_18000415D
0x180004151  mov     ecx, 0C00000E5h
0x180004156  jmp     short loc_18000415D
0x180004158  mov     ecx, 0C000042Bh
0x18000415d  mov     eax, ecx
0x18000415f  retn
```

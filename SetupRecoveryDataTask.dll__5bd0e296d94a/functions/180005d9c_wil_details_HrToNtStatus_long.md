# wil::details::HrToNtStatus(long)

- ea: `0x180005d9c`
- end: `0x180005f58`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024f4`
- `0x180002594`
- `0x1800025e4`
- `0x1800026a4`
- `0x180005028`
- `0x1800069f0`

## callees

- `0x180005d9c`

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
0x180005d9c  mov     eax, 800700EAh
0x180005da1  cmp     ecx, eax
0x180005da3  jg      loc_180005E78
0x180005da9  jz      loc_180005E6E
0x180005daf  mov     eax, 80070057h
0x180005db4  cmp     ecx, eax
0x180005db6  jg      short loc_180005E22
0x180005db8  jz      short loc_180005E18
0x180005dba  cmp     ecx, 80004005h
0x180005dc0  jz      short loc_180005E0E
0x180005dc2  cmp     ecx, 80070001h
0x180005dc8  jz      short loc_180005E04
0x180005dca  cmp     ecx, 80070002h
0x180005dd0  jz      short loc_180005DFA
0x180005dd2  cmp     ecx, 80070003h
0x180005dd8  jz      short loc_180005DF0
0x180005dda  cmp     ecx, 8007000Eh
0x180005de0  jnz     loc_180005EFD
0x180005de6  mov     ecx, 0C0000017h
0x180005deb  jmp     loc_180005F55
0x180005df0  mov     ecx, 0C000003Ah
0x180005df5  jmp     loc_180005F55
0x180005dfa  mov     ecx, 0C0000034h
0x180005dff  jmp     loc_180005F55
0x180005e04  mov     ecx, 0C0000002h
0x180005e09  jmp     loc_180005F55
0x180005e0e  mov     ecx, 0C0000001h
0x180005e13  jmp     loc_180005F55
0x180005e18  mov     ecx, 0C000000Dh
0x180005e1d  jmp     loc_180005F55
0x180005e22  cmp     ecx, 80070070h
0x180005e28  jz      short loc_180005E64
0x180005e2a  cmp     ecx, 8007007Ah
0x180005e30  jz      short loc_180005E5A
0x180005e32  cmp     ecx, 8007007Bh
0x180005e38  jz      short loc_180005E50
0x180005e3a  cmp     ecx, 8007007Eh
0x180005e40  jnz     loc_180005EFD
0x180005e46  mov     ecx, 0C0000135h
0x180005e4b  jmp     loc_180005F55
0x180005e50  mov     ecx, 0C0000033h
0x180005e55  jmp     loc_180005F55
0x180005e5a  mov     ecx, 0C0000023h
0x180005e5f  jmp     loc_180005F55
0x180005e64  mov     ecx, 0C000007Fh
0x180005e69  jmp     loc_180005F55
0x180005e6e  mov     ecx, 80000005h
0x180005e73  jmp     loc_180005F55
0x180005e78  mov     eax, 8007047Eh
0x180005e7d  cmp     ecx, eax
0x180005e7f  jg      short loc_180005EE1
0x180005e81  jz      short loc_180005EDA
0x180005e83  cmp     ecx, 80070216h
0x180005e89  jz      short loc_180005ED3
0x180005e8b  cmp     ecx, 8007023Eh
0x180005e91  jz      short loc_180005EC9
0x180005e93  cmp     ecx, 80070246h
0x180005e99  jz      short loc_180005EBF
0x180005e9b  cmp     ecx, 80070247h
0x180005ea1  jz      short loc_180005EB5
0x180005ea3  cmp     ecx, 80070272h
0x180005ea9  jnz     short loc_180005EFD
0x180005eab  mov     ecx, 0C0000273h
0x180005eb0  jmp     loc_180005F55
0x180005eb5  mov     ecx, 0C0000163h
0x180005eba  jmp     loc_180005F55
0x180005ebf  mov     ecx, 0C0000161h
0x180005ec4  jmp     loc_180005F55
0x180005ec9  mov     ecx, 0C0000025h
0x180005ece  jmp     loc_180005F55
0x180005ed3  mov     ecx, 0C0000095h
0x180005ed8  jmp     short loc_180005F55
0x180005eda  mov     ecx, 0C0000059h
0x180005edf  jmp     short loc_180005F55
0x180005ee1  cmp     ecx, 8007050Ch
0x180005ee7  jz      short loc_180005F50
0x180005ee9  cmp     ecx, 8007054Fh
0x180005eef  jz      short loc_180005F49
0x180005ef1  cmp     ecx, 800705B9h
0x180005ef7  jz      short loc_180005F42
0x180005ef9  test    ecx, ecx
0x180005efb  jz      short loc_180005F3E
0x180005efd  bt      ecx, 1Ch
0x180005f01  jnb     short loc_180005F09
0x180005f03  btr     ecx, 1Ch
0x180005f07  jmp     short loc_180005F55
0x180005f09  mov     eax, ecx
0x180005f0b  and     eax, 1FFF0000h
0x180005f10  cmp     eax, 70000h
0x180005f15  jnz     short loc_180005F28
0x180005f17  movzx   ecx, cx
0x180005f1a  mov     eax, ecx
0x180005f1c  or      eax, 0C0070000h
0x180005f21  test    ecx, ecx
0x180005f23  cmovnz  ecx, eax
0x180005f26  jmp     short loc_180005F55
0x180005f28  cmp     eax, 90000h
0x180005f2d  jnz     short loc_180005F49
0x180005f2f  test    ecx, ecx
0x180005f31  jle     short loc_180005F55
0x180005f33  movzx   ecx, cx
0x180005f36  or      ecx, 0C0090000h
0x180005f3c  jmp     short loc_180005F55
0x180005f3e  xor     ecx, ecx
0x180005f40  jmp     short loc_180005F55
0x180005f42  mov     ecx, 0C000A083h
0x180005f47  jmp     short loc_180005F55
0x180005f49  mov     ecx, 0C00000E5h
0x180005f4e  jmp     short loc_180005F55
0x180005f50  mov     ecx, 0C000042Bh
0x180005f55  mov     eax, ecx
0x180005f57  retn
```

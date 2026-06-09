# wil::details::HrToNtStatus(long)

- ea: `0x140003ea4`
- end: `0x140004060`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020c4`
- `0x14000216c`
- `0x1400021bc`
- `0x14000227c`
- `0x140003478`
- `0x140004068`

## callees

- `0x140003ea4`

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
0x140003ea4  mov     eax, 800700EAh
0x140003ea9  cmp     ecx, eax
0x140003eab  jg      loc_140003F80
0x140003eb1  jz      loc_140003F76
0x140003eb7  mov     eax, 80070057h
0x140003ebc  cmp     ecx, eax
0x140003ebe  jg      short loc_140003F2A
0x140003ec0  jz      short loc_140003F20
0x140003ec2  cmp     ecx, 80004005h
0x140003ec8  jz      short loc_140003F16
0x140003eca  cmp     ecx, 80070001h
0x140003ed0  jz      short loc_140003F0C
0x140003ed2  cmp     ecx, 80070002h
0x140003ed8  jz      short loc_140003F02
0x140003eda  cmp     ecx, 80070003h
0x140003ee0  jz      short loc_140003EF8
0x140003ee2  cmp     ecx, 8007000Eh
0x140003ee8  jnz     loc_140004005
0x140003eee  mov     ecx, 0C0000017h
0x140003ef3  jmp     loc_14000405D
0x140003ef8  mov     ecx, 0C000003Ah
0x140003efd  jmp     loc_14000405D
0x140003f02  mov     ecx, 0C0000034h
0x140003f07  jmp     loc_14000405D
0x140003f0c  mov     ecx, 0C0000002h
0x140003f11  jmp     loc_14000405D
0x140003f16  mov     ecx, 0C0000001h
0x140003f1b  jmp     loc_14000405D
0x140003f20  mov     ecx, 0C000000Dh
0x140003f25  jmp     loc_14000405D
0x140003f2a  cmp     ecx, 80070070h
0x140003f30  jz      short loc_140003F6C
0x140003f32  cmp     ecx, 8007007Ah
0x140003f38  jz      short loc_140003F62
0x140003f3a  cmp     ecx, 8007007Bh
0x140003f40  jz      short loc_140003F58
0x140003f42  cmp     ecx, 8007007Eh
0x140003f48  jnz     loc_140004005
0x140003f4e  mov     ecx, 0C0000135h
0x140003f53  jmp     loc_14000405D
0x140003f58  mov     ecx, 0C0000033h
0x140003f5d  jmp     loc_14000405D
0x140003f62  mov     ecx, 0C0000023h
0x140003f67  jmp     loc_14000405D
0x140003f6c  mov     ecx, 0C000007Fh
0x140003f71  jmp     loc_14000405D
0x140003f76  mov     ecx, 80000005h
0x140003f7b  jmp     loc_14000405D
0x140003f80  mov     eax, 8007047Eh
0x140003f85  cmp     ecx, eax
0x140003f87  jg      short loc_140003FE9
0x140003f89  jz      short loc_140003FE2
0x140003f8b  cmp     ecx, 80070216h
0x140003f91  jz      short loc_140003FDB
0x140003f93  cmp     ecx, 8007023Eh
0x140003f99  jz      short loc_140003FD1
0x140003f9b  cmp     ecx, 80070246h
0x140003fa1  jz      short loc_140003FC7
0x140003fa3  cmp     ecx, 80070247h
0x140003fa9  jz      short loc_140003FBD
0x140003fab  cmp     ecx, 80070272h
0x140003fb1  jnz     short loc_140004005
0x140003fb3  mov     ecx, 0C0000273h
0x140003fb8  jmp     loc_14000405D
0x140003fbd  mov     ecx, 0C0000163h
0x140003fc2  jmp     loc_14000405D
0x140003fc7  mov     ecx, 0C0000161h
0x140003fcc  jmp     loc_14000405D
0x140003fd1  mov     ecx, 0C0000025h
0x140003fd6  jmp     loc_14000405D
0x140003fdb  mov     ecx, 0C0000095h
0x140003fe0  jmp     short loc_14000405D
0x140003fe2  mov     ecx, 0C0000059h
0x140003fe7  jmp     short loc_14000405D
0x140003fe9  cmp     ecx, 8007050Ch
0x140003fef  jz      short loc_140004058
0x140003ff1  cmp     ecx, 8007054Fh
0x140003ff7  jz      short loc_140004051
0x140003ff9  cmp     ecx, 800705B9h
0x140003fff  jz      short loc_14000404A
0x140004001  test    ecx, ecx
0x140004003  jz      short loc_140004046
0x140004005  bt      ecx, 1Ch
0x140004009  jnb     short loc_140004011
0x14000400b  btr     ecx, 1Ch
0x14000400f  jmp     short loc_14000405D
0x140004011  mov     eax, ecx
0x140004013  and     eax, 1FFF0000h
0x140004018  cmp     eax, 70000h
0x14000401d  jnz     short loc_140004030
0x14000401f  movzx   ecx, cx
0x140004022  mov     eax, ecx
0x140004024  or      eax, 0C0070000h
0x140004029  test    ecx, ecx
0x14000402b  cmovnz  ecx, eax
0x14000402e  jmp     short loc_14000405D
0x140004030  cmp     eax, 90000h
0x140004035  jnz     short loc_140004051
0x140004037  test    ecx, ecx
0x140004039  jle     short loc_14000405D
0x14000403b  movzx   ecx, cx
0x14000403e  or      ecx, 0C0090000h
0x140004044  jmp     short loc_14000405D
0x140004046  xor     ecx, ecx
0x140004048  jmp     short loc_14000405D
0x14000404a  mov     ecx, 0C000A083h
0x14000404f  jmp     short loc_14000405D
0x140004051  mov     ecx, 0C00000E5h
0x140004056  jmp     short loc_14000405D
0x140004058  mov     ecx, 0C000042Bh
0x14000405d  mov     eax, ecx
0x14000405f  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140003de4`
- end: `0x140003fa0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002100`
- `0x1400021a8`
- `0x1400021fc`
- `0x1400022b4`
- `0x1400033b8`
- `0x140003fa8`
- `0x1400058d4`

## callees

- `0x140003de4`

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
0x140003de4  mov     eax, 800700EAh
0x140003de9  cmp     ecx, eax
0x140003deb  jg      loc_140003EC0
0x140003df1  jz      loc_140003EB6
0x140003df7  mov     eax, 80070057h
0x140003dfc  cmp     ecx, eax
0x140003dfe  jg      short loc_140003E6A
0x140003e00  jz      short loc_140003E60
0x140003e02  cmp     ecx, 80004005h
0x140003e08  jz      short loc_140003E56
0x140003e0a  cmp     ecx, 80070001h
0x140003e10  jz      short loc_140003E4C
0x140003e12  cmp     ecx, 80070002h
0x140003e18  jz      short loc_140003E42
0x140003e1a  cmp     ecx, 80070003h
0x140003e20  jz      short loc_140003E38
0x140003e22  cmp     ecx, 8007000Eh
0x140003e28  jnz     loc_140003F45
0x140003e2e  mov     ecx, 0C0000017h
0x140003e33  jmp     loc_140003F9D
0x140003e38  mov     ecx, 0C000003Ah
0x140003e3d  jmp     loc_140003F9D
0x140003e42  mov     ecx, 0C0000034h
0x140003e47  jmp     loc_140003F9D
0x140003e4c  mov     ecx, 0C0000002h
0x140003e51  jmp     loc_140003F9D
0x140003e56  mov     ecx, 0C0000001h
0x140003e5b  jmp     loc_140003F9D
0x140003e60  mov     ecx, 0C000000Dh
0x140003e65  jmp     loc_140003F9D
0x140003e6a  cmp     ecx, 80070070h
0x140003e70  jz      short loc_140003EAC
0x140003e72  cmp     ecx, 8007007Ah
0x140003e78  jz      short loc_140003EA2
0x140003e7a  cmp     ecx, 8007007Bh
0x140003e80  jz      short loc_140003E98
0x140003e82  cmp     ecx, 8007007Eh
0x140003e88  jnz     loc_140003F45
0x140003e8e  mov     ecx, 0C0000135h
0x140003e93  jmp     loc_140003F9D
0x140003e98  mov     ecx, 0C0000033h
0x140003e9d  jmp     loc_140003F9D
0x140003ea2  mov     ecx, 0C0000023h
0x140003ea7  jmp     loc_140003F9D
0x140003eac  mov     ecx, 0C000007Fh
0x140003eb1  jmp     loc_140003F9D
0x140003eb6  mov     ecx, 80000005h
0x140003ebb  jmp     loc_140003F9D
0x140003ec0  mov     eax, 8007047Eh
0x140003ec5  cmp     ecx, eax
0x140003ec7  jg      short loc_140003F29
0x140003ec9  jz      short loc_140003F22
0x140003ecb  cmp     ecx, 80070216h
0x140003ed1  jz      short loc_140003F1B
0x140003ed3  cmp     ecx, 8007023Eh
0x140003ed9  jz      short loc_140003F11
0x140003edb  cmp     ecx, 80070246h
0x140003ee1  jz      short loc_140003F07
0x140003ee3  cmp     ecx, 80070247h
0x140003ee9  jz      short loc_140003EFD
0x140003eeb  cmp     ecx, 80070272h
0x140003ef1  jnz     short loc_140003F45
0x140003ef3  mov     ecx, 0C0000273h
0x140003ef8  jmp     loc_140003F9D
0x140003efd  mov     ecx, 0C0000163h
0x140003f02  jmp     loc_140003F9D
0x140003f07  mov     ecx, 0C0000161h
0x140003f0c  jmp     loc_140003F9D
0x140003f11  mov     ecx, 0C0000025h
0x140003f16  jmp     loc_140003F9D
0x140003f1b  mov     ecx, 0C0000095h
0x140003f20  jmp     short loc_140003F9D
0x140003f22  mov     ecx, 0C0000059h
0x140003f27  jmp     short loc_140003F9D
0x140003f29  cmp     ecx, 8007050Ch
0x140003f2f  jz      short loc_140003F98
0x140003f31  cmp     ecx, 8007054Fh
0x140003f37  jz      short loc_140003F91
0x140003f39  cmp     ecx, 800705B9h
0x140003f3f  jz      short loc_140003F8A
0x140003f41  test    ecx, ecx
0x140003f43  jz      short loc_140003F86
0x140003f45  bt      ecx, 1Ch
0x140003f49  jnb     short loc_140003F51
0x140003f4b  btr     ecx, 1Ch
0x140003f4f  jmp     short loc_140003F9D
0x140003f51  mov     eax, ecx
0x140003f53  and     eax, 1FFF0000h
0x140003f58  cmp     eax, 70000h
0x140003f5d  jnz     short loc_140003F70
0x140003f5f  movzx   ecx, cx
0x140003f62  mov     eax, ecx
0x140003f64  or      eax, 0C0070000h
0x140003f69  test    ecx, ecx
0x140003f6b  cmovnz  ecx, eax
0x140003f6e  jmp     short loc_140003F9D
0x140003f70  cmp     eax, 90000h
0x140003f75  jnz     short loc_140003F91
0x140003f77  test    ecx, ecx
0x140003f79  jle     short loc_140003F9D
0x140003f7b  movzx   ecx, cx
0x140003f7e  or      ecx, 0C0090000h
0x140003f84  jmp     short loc_140003F9D
0x140003f86  xor     ecx, ecx
0x140003f88  jmp     short loc_140003F9D
0x140003f8a  mov     ecx, 0C000A083h
0x140003f8f  jmp     short loc_140003F9D
0x140003f91  mov     ecx, 0C00000E5h
0x140003f96  jmp     short loc_140003F9D
0x140003f98  mov     ecx, 0C000042Bh
0x140003f9d  mov     eax, ecx
0x140003f9f  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140003e14`
- end: `0x140003fd0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020b0`
- `0x140002160`
- `0x1400021b8`
- `0x140002278`
- `0x1400033e8`
- `0x140003fd8`
- `0x140004760`
- `0x14000612c`
- `0x14000629c`
- `0x1400072a6`
- `0x140007311`
- `0x1400073da`
- `0x140007445`

## callees

- `0x140003e14`

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
0x140003e14  mov     eax, 800700EAh
0x140003e19  cmp     ecx, eax
0x140003e1b  jg      loc_140003EF0
0x140003e21  jz      loc_140003EE6
0x140003e27  mov     eax, 80070057h
0x140003e2c  cmp     ecx, eax
0x140003e2e  jg      short loc_140003E9A
0x140003e30  jz      short loc_140003E90
0x140003e32  cmp     ecx, 80004005h
0x140003e38  jz      short loc_140003E86
0x140003e3a  cmp     ecx, 80070001h
0x140003e40  jz      short loc_140003E7C
0x140003e42  cmp     ecx, 80070002h
0x140003e48  jz      short loc_140003E72
0x140003e4a  cmp     ecx, 80070003h
0x140003e50  jz      short loc_140003E68
0x140003e52  cmp     ecx, 8007000Eh
0x140003e58  jnz     loc_140003F75
0x140003e5e  mov     ecx, 0C0000017h
0x140003e63  jmp     loc_140003FCD
0x140003e68  mov     ecx, 0C000003Ah
0x140003e6d  jmp     loc_140003FCD
0x140003e72  mov     ecx, 0C0000034h
0x140003e77  jmp     loc_140003FCD
0x140003e7c  mov     ecx, 0C0000002h
0x140003e81  jmp     loc_140003FCD
0x140003e86  mov     ecx, 0C0000001h
0x140003e8b  jmp     loc_140003FCD
0x140003e90  mov     ecx, 0C000000Dh
0x140003e95  jmp     loc_140003FCD
0x140003e9a  cmp     ecx, 80070070h
0x140003ea0  jz      short loc_140003EDC
0x140003ea2  cmp     ecx, 8007007Ah
0x140003ea8  jz      short loc_140003ED2
0x140003eaa  cmp     ecx, 8007007Bh
0x140003eb0  jz      short loc_140003EC8
0x140003eb2  cmp     ecx, 8007007Eh
0x140003eb8  jnz     loc_140003F75
0x140003ebe  mov     ecx, 0C0000135h
0x140003ec3  jmp     loc_140003FCD
0x140003ec8  mov     ecx, 0C0000033h
0x140003ecd  jmp     loc_140003FCD
0x140003ed2  mov     ecx, 0C0000023h
0x140003ed7  jmp     loc_140003FCD
0x140003edc  mov     ecx, 0C000007Fh
0x140003ee1  jmp     loc_140003FCD
0x140003ee6  mov     ecx, 80000005h
0x140003eeb  jmp     loc_140003FCD
0x140003ef0  mov     eax, 8007047Eh
0x140003ef5  cmp     ecx, eax
0x140003ef7  jg      short loc_140003F59
0x140003ef9  jz      short loc_140003F52
0x140003efb  cmp     ecx, 80070216h
0x140003f01  jz      short loc_140003F4B
0x140003f03  cmp     ecx, 8007023Eh
0x140003f09  jz      short loc_140003F41
0x140003f0b  cmp     ecx, 80070246h
0x140003f11  jz      short loc_140003F37
0x140003f13  cmp     ecx, 80070247h
0x140003f19  jz      short loc_140003F2D
0x140003f1b  cmp     ecx, 80070272h
0x140003f21  jnz     short loc_140003F75
0x140003f23  mov     ecx, 0C0000273h
0x140003f28  jmp     loc_140003FCD
0x140003f2d  mov     ecx, 0C0000163h
0x140003f32  jmp     loc_140003FCD
0x140003f37  mov     ecx, 0C0000161h
0x140003f3c  jmp     loc_140003FCD
0x140003f41  mov     ecx, 0C0000025h
0x140003f46  jmp     loc_140003FCD
0x140003f4b  mov     ecx, 0C0000095h
0x140003f50  jmp     short loc_140003FCD
0x140003f52  mov     ecx, 0C0000059h
0x140003f57  jmp     short loc_140003FCD
0x140003f59  cmp     ecx, 8007050Ch
0x140003f5f  jz      short loc_140003FC8
0x140003f61  cmp     ecx, 8007054Fh
0x140003f67  jz      short loc_140003FC1
0x140003f69  cmp     ecx, 800705B9h
0x140003f6f  jz      short loc_140003FBA
0x140003f71  test    ecx, ecx
0x140003f73  jz      short loc_140003FB6
0x140003f75  bt      ecx, 1Ch
0x140003f79  jnb     short loc_140003F81
0x140003f7b  btr     ecx, 1Ch
0x140003f7f  jmp     short loc_140003FCD
0x140003f81  mov     eax, ecx
0x140003f83  and     eax, 1FFF0000h
0x140003f88  cmp     eax, 70000h
0x140003f8d  jnz     short loc_140003FA0
0x140003f8f  movzx   ecx, cx
0x140003f92  mov     eax, ecx
0x140003f94  or      eax, 0C0070000h
0x140003f99  test    ecx, ecx
0x140003f9b  cmovnz  ecx, eax
0x140003f9e  jmp     short loc_140003FCD
0x140003fa0  cmp     eax, 90000h
0x140003fa5  jnz     short loc_140003FC1
0x140003fa7  test    ecx, ecx
0x140003fa9  jle     short loc_140003FCD
0x140003fab  movzx   ecx, cx
0x140003fae  or      ecx, 0C0090000h
0x140003fb4  jmp     short loc_140003FCD
0x140003fb6  xor     ecx, ecx
0x140003fb8  jmp     short loc_140003FCD
0x140003fba  mov     ecx, 0C000A083h
0x140003fbf  jmp     short loc_140003FCD
0x140003fc1  mov     ecx, 0C00000E5h
0x140003fc6  jmp     short loc_140003FCD
0x140003fc8  mov     ecx, 0C000042Bh
0x140003fcd  mov     eax, ecx
0x140003fcf  retn
```

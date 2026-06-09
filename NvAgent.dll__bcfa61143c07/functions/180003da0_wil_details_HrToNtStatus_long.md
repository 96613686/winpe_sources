# wil::details::HrToNtStatus(long)

- ea: `0x180003da0`
- end: `0x180003f5c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020c4`
- `0x180002164`
- `0x1800021b4`
- `0x18000226c`
- `0x180003378`
- `0x180003f64`

## callees

- `0x180003da0`

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
0x180003da0  mov     eax, 800700EAh
0x180003da5  cmp     ecx, eax
0x180003da7  jg      loc_180003E7C
0x180003dad  jz      loc_180003E72
0x180003db3  mov     eax, 80070057h
0x180003db8  cmp     ecx, eax
0x180003dba  jg      short loc_180003E26
0x180003dbc  jz      short loc_180003E1C
0x180003dbe  cmp     ecx, 80004005h
0x180003dc4  jz      short loc_180003E12
0x180003dc6  cmp     ecx, 80070001h
0x180003dcc  jz      short loc_180003E08
0x180003dce  cmp     ecx, 80070002h
0x180003dd4  jz      short loc_180003DFE
0x180003dd6  cmp     ecx, 80070003h
0x180003ddc  jz      short loc_180003DF4
0x180003dde  cmp     ecx, 8007000Eh
0x180003de4  jnz     loc_180003F01
0x180003dea  mov     ecx, 0C0000017h
0x180003def  jmp     loc_180003F59
0x180003df4  mov     ecx, 0C000003Ah
0x180003df9  jmp     loc_180003F59
0x180003dfe  mov     ecx, 0C0000034h
0x180003e03  jmp     loc_180003F59
0x180003e08  mov     ecx, 0C0000002h
0x180003e0d  jmp     loc_180003F59
0x180003e12  mov     ecx, 0C0000001h
0x180003e17  jmp     loc_180003F59
0x180003e1c  mov     ecx, 0C000000Dh
0x180003e21  jmp     loc_180003F59
0x180003e26  cmp     ecx, 80070070h
0x180003e2c  jz      short loc_180003E68
0x180003e2e  cmp     ecx, 8007007Ah
0x180003e34  jz      short loc_180003E5E
0x180003e36  cmp     ecx, 8007007Bh
0x180003e3c  jz      short loc_180003E54
0x180003e3e  cmp     ecx, 8007007Eh
0x180003e44  jnz     loc_180003F01
0x180003e4a  mov     ecx, 0C0000135h
0x180003e4f  jmp     loc_180003F59
0x180003e54  mov     ecx, 0C0000033h
0x180003e59  jmp     loc_180003F59
0x180003e5e  mov     ecx, 0C0000023h
0x180003e63  jmp     loc_180003F59
0x180003e68  mov     ecx, 0C000007Fh
0x180003e6d  jmp     loc_180003F59
0x180003e72  mov     ecx, 80000005h
0x180003e77  jmp     loc_180003F59
0x180003e7c  mov     eax, 8007047Eh
0x180003e81  cmp     ecx, eax
0x180003e83  jg      short loc_180003EE5
0x180003e85  jz      short loc_180003EDE
0x180003e87  cmp     ecx, 80070216h
0x180003e8d  jz      short loc_180003ED7
0x180003e8f  cmp     ecx, 8007023Eh
0x180003e95  jz      short loc_180003ECD
0x180003e97  cmp     ecx, 80070246h
0x180003e9d  jz      short loc_180003EC3
0x180003e9f  cmp     ecx, 80070247h
0x180003ea5  jz      short loc_180003EB9
0x180003ea7  cmp     ecx, 80070272h
0x180003ead  jnz     short loc_180003F01
0x180003eaf  mov     ecx, 0C0000273h
0x180003eb4  jmp     loc_180003F59
0x180003eb9  mov     ecx, 0C0000163h
0x180003ebe  jmp     loc_180003F59
0x180003ec3  mov     ecx, 0C0000161h
0x180003ec8  jmp     loc_180003F59
0x180003ecd  mov     ecx, 0C0000025h
0x180003ed2  jmp     loc_180003F59
0x180003ed7  mov     ecx, 0C0000095h
0x180003edc  jmp     short loc_180003F59
0x180003ede  mov     ecx, 0C0000059h
0x180003ee3  jmp     short loc_180003F59
0x180003ee5  cmp     ecx, 8007050Ch
0x180003eeb  jz      short loc_180003F54
0x180003eed  cmp     ecx, 8007054Fh
0x180003ef3  jz      short loc_180003F4D
0x180003ef5  cmp     ecx, 800705B9h
0x180003efb  jz      short loc_180003F46
0x180003efd  test    ecx, ecx
0x180003eff  jz      short loc_180003F42
0x180003f01  bt      ecx, 1Ch
0x180003f05  jnb     short loc_180003F0D
0x180003f07  btr     ecx, 1Ch
0x180003f0b  jmp     short loc_180003F59
0x180003f0d  mov     eax, ecx
0x180003f0f  and     eax, 1FFF0000h
0x180003f14  cmp     eax, 70000h
0x180003f19  jnz     short loc_180003F2C
0x180003f1b  movzx   ecx, cx
0x180003f1e  mov     eax, ecx
0x180003f20  or      eax, 0C0070000h
0x180003f25  test    ecx, ecx
0x180003f27  cmovnz  ecx, eax
0x180003f2a  jmp     short loc_180003F59
0x180003f2c  cmp     eax, 90000h
0x180003f31  jnz     short loc_180003F4D
0x180003f33  test    ecx, ecx
0x180003f35  jle     short loc_180003F59
0x180003f37  movzx   ecx, cx
0x180003f3a  or      ecx, 0C0090000h
0x180003f40  jmp     short loc_180003F59
0x180003f42  xor     ecx, ecx
0x180003f44  jmp     short loc_180003F59
0x180003f46  mov     ecx, 0C000A083h
0x180003f4b  jmp     short loc_180003F59
0x180003f4d  mov     ecx, 0C00000E5h
0x180003f52  jmp     short loc_180003F59
0x180003f54  mov     ecx, 0C000042Bh
0x180003f59  mov     eax, ecx
0x180003f5b  retn
```

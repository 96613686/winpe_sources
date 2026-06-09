# wil::details::HrToNtStatus(long)

- ea: `0x140006cec`
- end: `0x140006ea8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002594`
- `0x140002634`
- `0x140002684`
- `0x140002744`
- `0x140004ef8`
- `0x14000771c`

## callees

- `0x140006cec`

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
0x140006cec  mov     eax, 800700EAh
0x140006cf1  cmp     ecx, eax
0x140006cf3  jg      loc_140006DC8
0x140006cf9  jz      loc_140006DBE
0x140006cff  mov     eax, 80070057h
0x140006d04  cmp     ecx, eax
0x140006d06  jg      short loc_140006D72
0x140006d08  jz      short loc_140006D68
0x140006d0a  cmp     ecx, 80004005h
0x140006d10  jz      short loc_140006D5E
0x140006d12  cmp     ecx, 80070001h
0x140006d18  jz      short loc_140006D54
0x140006d1a  cmp     ecx, 80070002h
0x140006d20  jz      short loc_140006D4A
0x140006d22  cmp     ecx, 80070003h
0x140006d28  jz      short loc_140006D40
0x140006d2a  cmp     ecx, 8007000Eh
0x140006d30  jnz     loc_140006E4D
0x140006d36  mov     ecx, 0C0000017h
0x140006d3b  jmp     loc_140006EA5
0x140006d40  mov     ecx, 0C000003Ah
0x140006d45  jmp     loc_140006EA5
0x140006d4a  mov     ecx, 0C0000034h
0x140006d4f  jmp     loc_140006EA5
0x140006d54  mov     ecx, 0C0000002h
0x140006d59  jmp     loc_140006EA5
0x140006d5e  mov     ecx, 0C0000001h
0x140006d63  jmp     loc_140006EA5
0x140006d68  mov     ecx, 0C000000Dh
0x140006d6d  jmp     loc_140006EA5
0x140006d72  cmp     ecx, 80070070h
0x140006d78  jz      short loc_140006DB4
0x140006d7a  cmp     ecx, 8007007Ah
0x140006d80  jz      short loc_140006DAA
0x140006d82  cmp     ecx, 8007007Bh
0x140006d88  jz      short loc_140006DA0
0x140006d8a  cmp     ecx, 8007007Eh
0x140006d90  jnz     loc_140006E4D
0x140006d96  mov     ecx, 0C0000135h
0x140006d9b  jmp     loc_140006EA5
0x140006da0  mov     ecx, 0C0000033h
0x140006da5  jmp     loc_140006EA5
0x140006daa  mov     ecx, 0C0000023h
0x140006daf  jmp     loc_140006EA5
0x140006db4  mov     ecx, 0C000007Fh
0x140006db9  jmp     loc_140006EA5
0x140006dbe  mov     ecx, 80000005h
0x140006dc3  jmp     loc_140006EA5
0x140006dc8  mov     eax, 8007047Eh
0x140006dcd  cmp     ecx, eax
0x140006dcf  jg      short loc_140006E31
0x140006dd1  jz      short loc_140006E2A
0x140006dd3  cmp     ecx, 80070216h
0x140006dd9  jz      short loc_140006E23
0x140006ddb  cmp     ecx, 8007023Eh
0x140006de1  jz      short loc_140006E19
0x140006de3  cmp     ecx, 80070246h
0x140006de9  jz      short loc_140006E0F
0x140006deb  cmp     ecx, 80070247h
0x140006df1  jz      short loc_140006E05
0x140006df3  cmp     ecx, 80070272h
0x140006df9  jnz     short loc_140006E4D
0x140006dfb  mov     ecx, 0C0000273h
0x140006e00  jmp     loc_140006EA5
0x140006e05  mov     ecx, 0C0000163h
0x140006e0a  jmp     loc_140006EA5
0x140006e0f  mov     ecx, 0C0000161h
0x140006e14  jmp     loc_140006EA5
0x140006e19  mov     ecx, 0C0000025h
0x140006e1e  jmp     loc_140006EA5
0x140006e23  mov     ecx, 0C0000095h
0x140006e28  jmp     short loc_140006EA5
0x140006e2a  mov     ecx, 0C0000059h
0x140006e2f  jmp     short loc_140006EA5
0x140006e31  cmp     ecx, 8007050Ch
0x140006e37  jz      short loc_140006EA0
0x140006e39  cmp     ecx, 8007054Fh
0x140006e3f  jz      short loc_140006E99
0x140006e41  cmp     ecx, 800705B9h
0x140006e47  jz      short loc_140006E92
0x140006e49  test    ecx, ecx
0x140006e4b  jz      short loc_140006E8E
0x140006e4d  bt      ecx, 1Ch
0x140006e51  jnb     short loc_140006E59
0x140006e53  btr     ecx, 1Ch
0x140006e57  jmp     short loc_140006EA5
0x140006e59  mov     eax, ecx
0x140006e5b  and     eax, 1FFF0000h
0x140006e60  cmp     eax, 70000h
0x140006e65  jnz     short loc_140006E78
0x140006e67  movzx   ecx, cx
0x140006e6a  mov     eax, ecx
0x140006e6c  or      eax, 0C0070000h
0x140006e71  test    ecx, ecx
0x140006e73  cmovnz  ecx, eax
0x140006e76  jmp     short loc_140006EA5
0x140006e78  cmp     eax, 90000h
0x140006e7d  jnz     short loc_140006E99
0x140006e7f  test    ecx, ecx
0x140006e81  jle     short loc_140006EA5
0x140006e83  movzx   ecx, cx
0x140006e86  or      ecx, 0C0090000h
0x140006e8c  jmp     short loc_140006EA5
0x140006e8e  xor     ecx, ecx
0x140006e90  jmp     short loc_140006EA5
0x140006e92  mov     ecx, 0C000A083h
0x140006e97  jmp     short loc_140006EA5
0x140006e99  mov     ecx, 0C00000E5h
0x140006e9e  jmp     short loc_140006EA5
0x140006ea0  mov     ecx, 0C000042Bh
0x140006ea5  mov     eax, ecx
0x140006ea7  retn
```

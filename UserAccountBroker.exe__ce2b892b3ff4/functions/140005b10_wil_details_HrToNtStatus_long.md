# wil::details::HrToNtStatus(long)

- ea: `0x140005b10`
- end: `0x140005ccc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400040a4`
- `0x14000414c`
- `0x14000419c`
- `0x140004254`
- `0x140004ffc`
- `0x140005cd4`

## callees

- `0x140005b10`

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
0x140005b10  mov     eax, 800700EAh
0x140005b15  cmp     ecx, eax
0x140005b17  jg      loc_140005BEC
0x140005b1d  jz      loc_140005BE2
0x140005b23  mov     eax, 80070057h
0x140005b28  cmp     ecx, eax
0x140005b2a  jg      short loc_140005B96
0x140005b2c  jz      short loc_140005B8C
0x140005b2e  cmp     ecx, 80004005h
0x140005b34  jz      short loc_140005B82
0x140005b36  cmp     ecx, 80070001h
0x140005b3c  jz      short loc_140005B78
0x140005b3e  cmp     ecx, 80070002h
0x140005b44  jz      short loc_140005B6E
0x140005b46  cmp     ecx, 80070003h
0x140005b4c  jz      short loc_140005B64
0x140005b4e  cmp     ecx, 8007000Eh
0x140005b54  jnz     loc_140005C71
0x140005b5a  mov     ecx, 0C0000017h
0x140005b5f  jmp     loc_140005CC9
0x140005b64  mov     ecx, 0C000003Ah
0x140005b69  jmp     loc_140005CC9
0x140005b6e  mov     ecx, 0C0000034h
0x140005b73  jmp     loc_140005CC9
0x140005b78  mov     ecx, 0C0000002h
0x140005b7d  jmp     loc_140005CC9
0x140005b82  mov     ecx, 0C0000001h
0x140005b87  jmp     loc_140005CC9
0x140005b8c  mov     ecx, 0C000000Dh
0x140005b91  jmp     loc_140005CC9
0x140005b96  cmp     ecx, 80070070h
0x140005b9c  jz      short loc_140005BD8
0x140005b9e  cmp     ecx, 8007007Ah
0x140005ba4  jz      short loc_140005BCE
0x140005ba6  cmp     ecx, 8007007Bh
0x140005bac  jz      short loc_140005BC4
0x140005bae  cmp     ecx, 8007007Eh
0x140005bb4  jnz     loc_140005C71
0x140005bba  mov     ecx, 0C0000135h
0x140005bbf  jmp     loc_140005CC9
0x140005bc4  mov     ecx, 0C0000033h
0x140005bc9  jmp     loc_140005CC9
0x140005bce  mov     ecx, 0C0000023h
0x140005bd3  jmp     loc_140005CC9
0x140005bd8  mov     ecx, 0C000007Fh
0x140005bdd  jmp     loc_140005CC9
0x140005be2  mov     ecx, 80000005h
0x140005be7  jmp     loc_140005CC9
0x140005bec  mov     eax, 8007047Eh
0x140005bf1  cmp     ecx, eax
0x140005bf3  jg      short loc_140005C55
0x140005bf5  jz      short loc_140005C4E
0x140005bf7  cmp     ecx, 80070216h
0x140005bfd  jz      short loc_140005C47
0x140005bff  cmp     ecx, 8007023Eh
0x140005c05  jz      short loc_140005C3D
0x140005c07  cmp     ecx, 80070246h
0x140005c0d  jz      short loc_140005C33
0x140005c0f  cmp     ecx, 80070247h
0x140005c15  jz      short loc_140005C29
0x140005c17  cmp     ecx, 80070272h
0x140005c1d  jnz     short loc_140005C71
0x140005c1f  mov     ecx, 0C0000273h
0x140005c24  jmp     loc_140005CC9
0x140005c29  mov     ecx, 0C0000163h
0x140005c2e  jmp     loc_140005CC9
0x140005c33  mov     ecx, 0C0000161h
0x140005c38  jmp     loc_140005CC9
0x140005c3d  mov     ecx, 0C0000025h
0x140005c42  jmp     loc_140005CC9
0x140005c47  mov     ecx, 0C0000095h
0x140005c4c  jmp     short loc_140005CC9
0x140005c4e  mov     ecx, 0C0000059h
0x140005c53  jmp     short loc_140005CC9
0x140005c55  cmp     ecx, 8007050Ch
0x140005c5b  jz      short loc_140005CC4
0x140005c5d  cmp     ecx, 8007054Fh
0x140005c63  jz      short loc_140005CBD
0x140005c65  cmp     ecx, 800705B9h
0x140005c6b  jz      short loc_140005CB6
0x140005c6d  test    ecx, ecx
0x140005c6f  jz      short loc_140005CB2
0x140005c71  bt      ecx, 1Ch
0x140005c75  jnb     short loc_140005C7D
0x140005c77  btr     ecx, 1Ch
0x140005c7b  jmp     short loc_140005CC9
0x140005c7d  mov     eax, ecx
0x140005c7f  and     eax, 1FFF0000h
0x140005c84  cmp     eax, 70000h
0x140005c89  jnz     short loc_140005C9C
0x140005c8b  movzx   ecx, cx
0x140005c8e  mov     eax, ecx
0x140005c90  or      eax, 0C0070000h
0x140005c95  test    ecx, ecx
0x140005c97  cmovnz  ecx, eax
0x140005c9a  jmp     short loc_140005CC9
0x140005c9c  cmp     eax, 90000h
0x140005ca1  jnz     short loc_140005CBD
0x140005ca3  test    ecx, ecx
0x140005ca5  jle     short loc_140005CC9
0x140005ca7  movzx   ecx, cx
0x140005caa  or      ecx, 0C0090000h
0x140005cb0  jmp     short loc_140005CC9
0x140005cb2  xor     ecx, ecx
0x140005cb4  jmp     short loc_140005CC9
0x140005cb6  mov     ecx, 0C000A083h
0x140005cbb  jmp     short loc_140005CC9
0x140005cbd  mov     ecx, 0C00000E5h
0x140005cc2  jmp     short loc_140005CC9
0x140005cc4  mov     ecx, 0C000042Bh
0x140005cc9  mov     eax, ecx
0x140005ccb  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140005b70`
- end: `0x140005d2c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039f8`
- `0x140003ab0`
- `0x140003b08`
- `0x140003bc8`
- `0x140005068`
- `0x140005d34`
- `0x140007728`
- `0x140007838`

## callees

- `0x140005b70`

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
0x140005b70  mov     eax, 800700EAh
0x140005b75  cmp     ecx, eax
0x140005b77  jg      loc_140005C4C
0x140005b7d  jz      loc_140005C42
0x140005b83  mov     eax, 80070057h
0x140005b88  cmp     ecx, eax
0x140005b8a  jg      short loc_140005BF6
0x140005b8c  jz      short loc_140005BEC
0x140005b8e  cmp     ecx, 80004005h
0x140005b94  jz      short loc_140005BE2
0x140005b96  cmp     ecx, 80070001h
0x140005b9c  jz      short loc_140005BD8
0x140005b9e  cmp     ecx, 80070002h
0x140005ba4  jz      short loc_140005BCE
0x140005ba6  cmp     ecx, 80070003h
0x140005bac  jz      short loc_140005BC4
0x140005bae  cmp     ecx, 8007000Eh
0x140005bb4  jnz     loc_140005CD1
0x140005bba  mov     ecx, 0C0000017h
0x140005bbf  jmp     loc_140005D29
0x140005bc4  mov     ecx, 0C000003Ah
0x140005bc9  jmp     loc_140005D29
0x140005bce  mov     ecx, 0C0000034h
0x140005bd3  jmp     loc_140005D29
0x140005bd8  mov     ecx, 0C0000002h
0x140005bdd  jmp     loc_140005D29
0x140005be2  mov     ecx, 0C0000001h
0x140005be7  jmp     loc_140005D29
0x140005bec  mov     ecx, 0C000000Dh
0x140005bf1  jmp     loc_140005D29
0x140005bf6  cmp     ecx, 80070070h
0x140005bfc  jz      short loc_140005C38
0x140005bfe  cmp     ecx, 8007007Ah
0x140005c04  jz      short loc_140005C2E
0x140005c06  cmp     ecx, 8007007Bh
0x140005c0c  jz      short loc_140005C24
0x140005c0e  cmp     ecx, 8007007Eh
0x140005c14  jnz     loc_140005CD1
0x140005c1a  mov     ecx, 0C0000135h
0x140005c1f  jmp     loc_140005D29
0x140005c24  mov     ecx, 0C0000033h
0x140005c29  jmp     loc_140005D29
0x140005c2e  mov     ecx, 0C0000023h
0x140005c33  jmp     loc_140005D29
0x140005c38  mov     ecx, 0C000007Fh
0x140005c3d  jmp     loc_140005D29
0x140005c42  mov     ecx, 80000005h
0x140005c47  jmp     loc_140005D29
0x140005c4c  mov     eax, 8007047Eh
0x140005c51  cmp     ecx, eax
0x140005c53  jg      short loc_140005CB5
0x140005c55  jz      short loc_140005CAE
0x140005c57  cmp     ecx, 80070216h
0x140005c5d  jz      short loc_140005CA7
0x140005c5f  cmp     ecx, 8007023Eh
0x140005c65  jz      short loc_140005C9D
0x140005c67  cmp     ecx, 80070246h
0x140005c6d  jz      short loc_140005C93
0x140005c6f  cmp     ecx, 80070247h
0x140005c75  jz      short loc_140005C89
0x140005c77  cmp     ecx, 80070272h
0x140005c7d  jnz     short loc_140005CD1
0x140005c7f  mov     ecx, 0C0000273h
0x140005c84  jmp     loc_140005D29
0x140005c89  mov     ecx, 0C0000163h
0x140005c8e  jmp     loc_140005D29
0x140005c93  mov     ecx, 0C0000161h
0x140005c98  jmp     loc_140005D29
0x140005c9d  mov     ecx, 0C0000025h
0x140005ca2  jmp     loc_140005D29
0x140005ca7  mov     ecx, 0C0000095h
0x140005cac  jmp     short loc_140005D29
0x140005cae  mov     ecx, 0C0000059h
0x140005cb3  jmp     short loc_140005D29
0x140005cb5  cmp     ecx, 8007050Ch
0x140005cbb  jz      short loc_140005D24
0x140005cbd  cmp     ecx, 8007054Fh
0x140005cc3  jz      short loc_140005D1D
0x140005cc5  cmp     ecx, 800705B9h
0x140005ccb  jz      short loc_140005D16
0x140005ccd  test    ecx, ecx
0x140005ccf  jz      short loc_140005D12
0x140005cd1  bt      ecx, 1Ch
0x140005cd5  jnb     short loc_140005CDD
0x140005cd7  btr     ecx, 1Ch
0x140005cdb  jmp     short loc_140005D29
0x140005cdd  mov     eax, ecx
0x140005cdf  and     eax, 1FFF0000h
0x140005ce4  cmp     eax, 70000h
0x140005ce9  jnz     short loc_140005CFC
0x140005ceb  movzx   ecx, cx
0x140005cee  mov     eax, ecx
0x140005cf0  or      eax, 0C0070000h
0x140005cf5  test    ecx, ecx
0x140005cf7  cmovnz  ecx, eax
0x140005cfa  jmp     short loc_140005D29
0x140005cfc  cmp     eax, 90000h
0x140005d01  jnz     short loc_140005D1D
0x140005d03  test    ecx, ecx
0x140005d05  jle     short loc_140005D29
0x140005d07  movzx   ecx, cx
0x140005d0a  or      ecx, 0C0090000h
0x140005d10  jmp     short loc_140005D29
0x140005d12  xor     ecx, ecx
0x140005d14  jmp     short loc_140005D29
0x140005d16  mov     ecx, 0C000A083h
0x140005d1b  jmp     short loc_140005D29
0x140005d1d  mov     ecx, 0C00000E5h
0x140005d22  jmp     short loc_140005D29
0x140005d24  mov     ecx, 0C000042Bh
0x140005d29  mov     eax, ecx
0x140005d2b  retn
```

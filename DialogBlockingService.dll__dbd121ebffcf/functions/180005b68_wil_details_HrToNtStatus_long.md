# wil::details::HrToNtStatus(long)

- ea: `0x180005b68`
- end: `0x180005d24`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f6c`
- `0x180003148`
- `0x1800031f8`
- `0x180003250`
- `0x180003318`
- `0x180004ee8`
- `0x180005db0`
- `0x180006660`
- `0x18000afa8`
- `0x18000ca74`
- `0x18000cadf`
- `0x18000cba8`
- `0x18000cc13`

## callees

- `0x180005b68`

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
0x180005b68  mov     eax, 800700EAh
0x180005b6d  cmp     ecx, eax
0x180005b6f  jg      loc_180005C44
0x180005b75  jz      loc_180005C3A
0x180005b7b  mov     eax, 80070057h
0x180005b80  cmp     ecx, eax
0x180005b82  jg      short loc_180005BEE
0x180005b84  jz      short loc_180005BE4
0x180005b86  cmp     ecx, 80004005h
0x180005b8c  jz      short loc_180005BDA
0x180005b8e  cmp     ecx, 80070001h
0x180005b94  jz      short loc_180005BD0
0x180005b96  cmp     ecx, 80070002h
0x180005b9c  jz      short loc_180005BC6
0x180005b9e  cmp     ecx, 80070003h
0x180005ba4  jz      short loc_180005BBC
0x180005ba6  cmp     ecx, 8007000Eh
0x180005bac  jnz     loc_180005CC9
0x180005bb2  mov     ecx, 0C0000017h
0x180005bb7  jmp     loc_180005D21
0x180005bbc  mov     ecx, 0C000003Ah
0x180005bc1  jmp     loc_180005D21
0x180005bc6  mov     ecx, 0C0000034h
0x180005bcb  jmp     loc_180005D21
0x180005bd0  mov     ecx, 0C0000002h
0x180005bd5  jmp     loc_180005D21
0x180005bda  mov     ecx, 0C0000001h
0x180005bdf  jmp     loc_180005D21
0x180005be4  mov     ecx, 0C000000Dh
0x180005be9  jmp     loc_180005D21
0x180005bee  cmp     ecx, 80070070h
0x180005bf4  jz      short loc_180005C30
0x180005bf6  cmp     ecx, 8007007Ah
0x180005bfc  jz      short loc_180005C26
0x180005bfe  cmp     ecx, 8007007Bh
0x180005c04  jz      short loc_180005C1C
0x180005c06  cmp     ecx, 8007007Eh
0x180005c0c  jnz     loc_180005CC9
0x180005c12  mov     ecx, 0C0000135h
0x180005c17  jmp     loc_180005D21
0x180005c1c  mov     ecx, 0C0000033h
0x180005c21  jmp     loc_180005D21
0x180005c26  mov     ecx, 0C0000023h
0x180005c2b  jmp     loc_180005D21
0x180005c30  mov     ecx, 0C000007Fh
0x180005c35  jmp     loc_180005D21
0x180005c3a  mov     ecx, 80000005h
0x180005c3f  jmp     loc_180005D21
0x180005c44  mov     eax, 8007047Eh
0x180005c49  cmp     ecx, eax
0x180005c4b  jg      short loc_180005CAD
0x180005c4d  jz      short loc_180005CA6
0x180005c4f  cmp     ecx, 80070216h
0x180005c55  jz      short loc_180005C9F
0x180005c57  cmp     ecx, 8007023Eh
0x180005c5d  jz      short loc_180005C95
0x180005c5f  cmp     ecx, 80070246h
0x180005c65  jz      short loc_180005C8B
0x180005c67  cmp     ecx, 80070247h
0x180005c6d  jz      short loc_180005C81
0x180005c6f  cmp     ecx, 80070272h
0x180005c75  jnz     short loc_180005CC9
0x180005c77  mov     ecx, 0C0000273h
0x180005c7c  jmp     loc_180005D21
0x180005c81  mov     ecx, 0C0000163h
0x180005c86  jmp     loc_180005D21
0x180005c8b  mov     ecx, 0C0000161h
0x180005c90  jmp     loc_180005D21
0x180005c95  mov     ecx, 0C0000025h
0x180005c9a  jmp     loc_180005D21
0x180005c9f  mov     ecx, 0C0000095h
0x180005ca4  jmp     short loc_180005D21
0x180005ca6  mov     ecx, 0C0000059h
0x180005cab  jmp     short loc_180005D21
0x180005cad  cmp     ecx, 8007050Ch
0x180005cb3  jz      short loc_180005D1C
0x180005cb5  cmp     ecx, 8007054Fh
0x180005cbb  jz      short loc_180005D15
0x180005cbd  cmp     ecx, 800705B9h
0x180005cc3  jz      short loc_180005D0E
0x180005cc5  test    ecx, ecx
0x180005cc7  jz      short loc_180005D0A
0x180005cc9  bt      ecx, 1Ch
0x180005ccd  jnb     short loc_180005CD5
0x180005ccf  btr     ecx, 1Ch
0x180005cd3  jmp     short loc_180005D21
0x180005cd5  mov     eax, ecx
0x180005cd7  and     eax, 1FFF0000h
0x180005cdc  cmp     eax, 70000h
0x180005ce1  jnz     short loc_180005CF4
0x180005ce3  movzx   ecx, cx
0x180005ce6  mov     eax, ecx
0x180005ce8  or      eax, 0C0070000h
0x180005ced  test    ecx, ecx
0x180005cef  cmovnz  ecx, eax
0x180005cf2  jmp     short loc_180005D21
0x180005cf4  cmp     eax, 90000h
0x180005cf9  jnz     short loc_180005D15
0x180005cfb  test    ecx, ecx
0x180005cfd  jle     short loc_180005D21
0x180005cff  movzx   ecx, cx
0x180005d02  or      ecx, 0C0090000h
0x180005d08  jmp     short loc_180005D21
0x180005d0a  xor     ecx, ecx
0x180005d0c  jmp     short loc_180005D21
0x180005d0e  mov     ecx, 0C000A083h
0x180005d13  jmp     short loc_180005D21
0x180005d15  mov     ecx, 0C00000E5h
0x180005d1a  jmp     short loc_180005D21
0x180005d1c  mov     ecx, 0C000042Bh
0x180005d21  mov     eax, ecx
0x180005d23  retn
```

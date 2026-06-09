# wil::details::HrToNtStatus(long)

- ea: `0x180005b44`
- end: `0x180005d00`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002be0`
- `0x180002c88`
- `0x180002cd8`
- `0x180002d90`
- `0x180005108`
- `0x180005e70`

## callees

- `0x180005b44`

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
0x180005b44  mov     eax, 800700EAh
0x180005b49  cmp     ecx, eax
0x180005b4b  jg      loc_180005C20
0x180005b51  jz      loc_180005C16
0x180005b57  mov     eax, 80070057h
0x180005b5c  cmp     ecx, eax
0x180005b5e  jg      short loc_180005BCA
0x180005b60  jz      short loc_180005BC0
0x180005b62  cmp     ecx, 80004005h
0x180005b68  jz      short loc_180005BB6
0x180005b6a  cmp     ecx, 80070001h
0x180005b70  jz      short loc_180005BAC
0x180005b72  cmp     ecx, 80070002h
0x180005b78  jz      short loc_180005BA2
0x180005b7a  cmp     ecx, 80070003h
0x180005b80  jz      short loc_180005B98
0x180005b82  cmp     ecx, 8007000Eh
0x180005b88  jnz     loc_180005CA5
0x180005b8e  mov     ecx, 0C0000017h
0x180005b93  jmp     loc_180005CFD
0x180005b98  mov     ecx, 0C000003Ah
0x180005b9d  jmp     loc_180005CFD
0x180005ba2  mov     ecx, 0C0000034h
0x180005ba7  jmp     loc_180005CFD
0x180005bac  mov     ecx, 0C0000002h
0x180005bb1  jmp     loc_180005CFD
0x180005bb6  mov     ecx, 0C0000001h
0x180005bbb  jmp     loc_180005CFD
0x180005bc0  mov     ecx, 0C000000Dh
0x180005bc5  jmp     loc_180005CFD
0x180005bca  cmp     ecx, 80070070h
0x180005bd0  jz      short loc_180005C0C
0x180005bd2  cmp     ecx, 8007007Ah
0x180005bd8  jz      short loc_180005C02
0x180005bda  cmp     ecx, 8007007Bh
0x180005be0  jz      short loc_180005BF8
0x180005be2  cmp     ecx, 8007007Eh
0x180005be8  jnz     loc_180005CA5
0x180005bee  mov     ecx, 0C0000135h
0x180005bf3  jmp     loc_180005CFD
0x180005bf8  mov     ecx, 0C0000033h
0x180005bfd  jmp     loc_180005CFD
0x180005c02  mov     ecx, 0C0000023h
0x180005c07  jmp     loc_180005CFD
0x180005c0c  mov     ecx, 0C000007Fh
0x180005c11  jmp     loc_180005CFD
0x180005c16  mov     ecx, 80000005h
0x180005c1b  jmp     loc_180005CFD
0x180005c20  mov     eax, 8007047Eh
0x180005c25  cmp     ecx, eax
0x180005c27  jg      short loc_180005C89
0x180005c29  jz      short loc_180005C82
0x180005c2b  cmp     ecx, 80070216h
0x180005c31  jz      short loc_180005C7B
0x180005c33  cmp     ecx, 8007023Eh
0x180005c39  jz      short loc_180005C71
0x180005c3b  cmp     ecx, 80070246h
0x180005c41  jz      short loc_180005C67
0x180005c43  cmp     ecx, 80070247h
0x180005c49  jz      short loc_180005C5D
0x180005c4b  cmp     ecx, 80070272h
0x180005c51  jnz     short loc_180005CA5
0x180005c53  mov     ecx, 0C0000273h
0x180005c58  jmp     loc_180005CFD
0x180005c5d  mov     ecx, 0C0000163h
0x180005c62  jmp     loc_180005CFD
0x180005c67  mov     ecx, 0C0000161h
0x180005c6c  jmp     loc_180005CFD
0x180005c71  mov     ecx, 0C0000025h
0x180005c76  jmp     loc_180005CFD
0x180005c7b  mov     ecx, 0C0000095h
0x180005c80  jmp     short loc_180005CFD
0x180005c82  mov     ecx, 0C0000059h
0x180005c87  jmp     short loc_180005CFD
0x180005c89  cmp     ecx, 8007050Ch
0x180005c8f  jz      short loc_180005CF8
0x180005c91  cmp     ecx, 8007054Fh
0x180005c97  jz      short loc_180005CF1
0x180005c99  cmp     ecx, 800705B9h
0x180005c9f  jz      short loc_180005CEA
0x180005ca1  test    ecx, ecx
0x180005ca3  jz      short loc_180005CE6
0x180005ca5  bt      ecx, 1Ch
0x180005ca9  jnb     short loc_180005CB1
0x180005cab  btr     ecx, 1Ch
0x180005caf  jmp     short loc_180005CFD
0x180005cb1  mov     eax, ecx
0x180005cb3  and     eax, 1FFF0000h
0x180005cb8  cmp     eax, 70000h
0x180005cbd  jnz     short loc_180005CD0
0x180005cbf  movzx   ecx, cx
0x180005cc2  mov     eax, ecx
0x180005cc4  or      eax, 0C0070000h
0x180005cc9  test    ecx, ecx
0x180005ccb  cmovnz  ecx, eax
0x180005cce  jmp     short loc_180005CFD
0x180005cd0  cmp     eax, 90000h
0x180005cd5  jnz     short loc_180005CF1
0x180005cd7  test    ecx, ecx
0x180005cd9  jle     short loc_180005CFD
0x180005cdb  movzx   ecx, cx
0x180005cde  or      ecx, 0C0090000h
0x180005ce4  jmp     short loc_180005CFD
0x180005ce6  xor     ecx, ecx
0x180005ce8  jmp     short loc_180005CFD
0x180005cea  mov     ecx, 0C000A083h
0x180005cef  jmp     short loc_180005CFD
0x180005cf1  mov     ecx, 0C00000E5h
0x180005cf6  jmp     short loc_180005CFD
0x180005cf8  mov     ecx, 0C000042Bh
0x180005cfd  mov     eax, ecx
0x180005cff  retn
```

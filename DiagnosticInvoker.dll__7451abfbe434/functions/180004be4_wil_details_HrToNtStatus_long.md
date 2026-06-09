# wil::details::HrToNtStatus(long)

- ea: `0x180004be4`
- end: `0x180004da0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002eb0`
- `0x180002f58`
- `0x180002fa8`
- `0x180003060`
- `0x1800041b8`
- `0x180004da8`

## callees

- `0x180004be4`

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
0x180004be4  mov     eax, 800700EAh
0x180004be9  cmp     ecx, eax
0x180004beb  jg      loc_180004CC0
0x180004bf1  jz      loc_180004CB6
0x180004bf7  mov     eax, 80070057h
0x180004bfc  cmp     ecx, eax
0x180004bfe  jg      short loc_180004C6A
0x180004c00  jz      short loc_180004C60
0x180004c02  cmp     ecx, 80004005h
0x180004c08  jz      short loc_180004C56
0x180004c0a  cmp     ecx, 80070001h
0x180004c10  jz      short loc_180004C4C
0x180004c12  cmp     ecx, 80070002h
0x180004c18  jz      short loc_180004C42
0x180004c1a  cmp     ecx, 80070003h
0x180004c20  jz      short loc_180004C38
0x180004c22  cmp     ecx, 8007000Eh
0x180004c28  jnz     loc_180004D45
0x180004c2e  mov     ecx, 0C0000017h
0x180004c33  jmp     loc_180004D9D
0x180004c38  mov     ecx, 0C000003Ah
0x180004c3d  jmp     loc_180004D9D
0x180004c42  mov     ecx, 0C0000034h
0x180004c47  jmp     loc_180004D9D
0x180004c4c  mov     ecx, 0C0000002h
0x180004c51  jmp     loc_180004D9D
0x180004c56  mov     ecx, 0C0000001h
0x180004c5b  jmp     loc_180004D9D
0x180004c60  mov     ecx, 0C000000Dh
0x180004c65  jmp     loc_180004D9D
0x180004c6a  cmp     ecx, 80070070h
0x180004c70  jz      short loc_180004CAC
0x180004c72  cmp     ecx, 8007007Ah
0x180004c78  jz      short loc_180004CA2
0x180004c7a  cmp     ecx, 8007007Bh
0x180004c80  jz      short loc_180004C98
0x180004c82  cmp     ecx, 8007007Eh
0x180004c88  jnz     loc_180004D45
0x180004c8e  mov     ecx, 0C0000135h
0x180004c93  jmp     loc_180004D9D
0x180004c98  mov     ecx, 0C0000033h
0x180004c9d  jmp     loc_180004D9D
0x180004ca2  mov     ecx, 0C0000023h
0x180004ca7  jmp     loc_180004D9D
0x180004cac  mov     ecx, 0C000007Fh
0x180004cb1  jmp     loc_180004D9D
0x180004cb6  mov     ecx, 80000005h
0x180004cbb  jmp     loc_180004D9D
0x180004cc0  mov     eax, 8007047Eh
0x180004cc5  cmp     ecx, eax
0x180004cc7  jg      short loc_180004D29
0x180004cc9  jz      short loc_180004D22
0x180004ccb  cmp     ecx, 80070216h
0x180004cd1  jz      short loc_180004D1B
0x180004cd3  cmp     ecx, 8007023Eh
0x180004cd9  jz      short loc_180004D11
0x180004cdb  cmp     ecx, 80070246h
0x180004ce1  jz      short loc_180004D07
0x180004ce3  cmp     ecx, 80070247h
0x180004ce9  jz      short loc_180004CFD
0x180004ceb  cmp     ecx, 80070272h
0x180004cf1  jnz     short loc_180004D45
0x180004cf3  mov     ecx, 0C0000273h
0x180004cf8  jmp     loc_180004D9D
0x180004cfd  mov     ecx, 0C0000163h
0x180004d02  jmp     loc_180004D9D
0x180004d07  mov     ecx, 0C0000161h
0x180004d0c  jmp     loc_180004D9D
0x180004d11  mov     ecx, 0C0000025h
0x180004d16  jmp     loc_180004D9D
0x180004d1b  mov     ecx, 0C0000095h
0x180004d20  jmp     short loc_180004D9D
0x180004d22  mov     ecx, 0C0000059h
0x180004d27  jmp     short loc_180004D9D
0x180004d29  cmp     ecx, 8007050Ch
0x180004d2f  jz      short loc_180004D98
0x180004d31  cmp     ecx, 8007054Fh
0x180004d37  jz      short loc_180004D91
0x180004d39  cmp     ecx, 800705B9h
0x180004d3f  jz      short loc_180004D8A
0x180004d41  test    ecx, ecx
0x180004d43  jz      short loc_180004D86
0x180004d45  bt      ecx, 1Ch
0x180004d49  jnb     short loc_180004D51
0x180004d4b  btr     ecx, 1Ch
0x180004d4f  jmp     short loc_180004D9D
0x180004d51  mov     eax, ecx
0x180004d53  and     eax, 1FFF0000h
0x180004d58  cmp     eax, 70000h
0x180004d5d  jnz     short loc_180004D70
0x180004d5f  movzx   ecx, cx
0x180004d62  mov     eax, ecx
0x180004d64  or      eax, 0C0070000h
0x180004d69  test    ecx, ecx
0x180004d6b  cmovnz  ecx, eax
0x180004d6e  jmp     short loc_180004D9D
0x180004d70  cmp     eax, 90000h
0x180004d75  jnz     short loc_180004D91
0x180004d77  test    ecx, ecx
0x180004d79  jle     short loc_180004D9D
0x180004d7b  movzx   ecx, cx
0x180004d7e  or      ecx, 0C0090000h
0x180004d84  jmp     short loc_180004D9D
0x180004d86  xor     ecx, ecx
0x180004d88  jmp     short loc_180004D9D
0x180004d8a  mov     ecx, 0C000A083h
0x180004d8f  jmp     short loc_180004D9D
0x180004d91  mov     ecx, 0C00000E5h
0x180004d96  jmp     short loc_180004D9D
0x180004d98  mov     ecx, 0C000042Bh
0x180004d9d  mov     eax, ecx
0x180004d9f  retn
```

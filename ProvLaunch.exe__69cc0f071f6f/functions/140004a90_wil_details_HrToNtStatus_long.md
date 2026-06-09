# wil::details::HrToNtStatus(long)

- ea: `0x140004a90`
- end: `0x140004c4c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002438`
- `0x140002604`
- `0x1400026b4`
- `0x140002714`
- `0x1400027dc`
- `0x140004128`
- `0x140004c54`
- `0x1400053e0`
- `0x14000a6de`
- `0x14000a749`
- `0x14000a812`
- `0x14000a87d`

## callees

- `0x140004a90`

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
0x140004a90  mov     eax, 800700EAh
0x140004a95  cmp     ecx, eax
0x140004a97  jg      loc_140004B6C
0x140004a9d  jz      loc_140004B62
0x140004aa3  mov     eax, 80070057h
0x140004aa8  cmp     ecx, eax
0x140004aaa  jg      short loc_140004B16
0x140004aac  jz      short loc_140004B0C
0x140004aae  cmp     ecx, 80004005h
0x140004ab4  jz      short loc_140004B02
0x140004ab6  cmp     ecx, 80070001h
0x140004abc  jz      short loc_140004AF8
0x140004abe  cmp     ecx, 80070002h
0x140004ac4  jz      short loc_140004AEE
0x140004ac6  cmp     ecx, 80070003h
0x140004acc  jz      short loc_140004AE4
0x140004ace  cmp     ecx, 8007000Eh
0x140004ad4  jnz     loc_140004BF1
0x140004ada  mov     ecx, 0C0000017h
0x140004adf  jmp     loc_140004C49
0x140004ae4  mov     ecx, 0C000003Ah
0x140004ae9  jmp     loc_140004C49
0x140004aee  mov     ecx, 0C0000034h
0x140004af3  jmp     loc_140004C49
0x140004af8  mov     ecx, 0C0000002h
0x140004afd  jmp     loc_140004C49
0x140004b02  mov     ecx, 0C0000001h
0x140004b07  jmp     loc_140004C49
0x140004b0c  mov     ecx, 0C000000Dh
0x140004b11  jmp     loc_140004C49
0x140004b16  cmp     ecx, 80070070h
0x140004b1c  jz      short loc_140004B58
0x140004b1e  cmp     ecx, 8007007Ah
0x140004b24  jz      short loc_140004B4E
0x140004b26  cmp     ecx, 8007007Bh
0x140004b2c  jz      short loc_140004B44
0x140004b2e  cmp     ecx, 8007007Eh
0x140004b34  jnz     loc_140004BF1
0x140004b3a  mov     ecx, 0C0000135h
0x140004b3f  jmp     loc_140004C49
0x140004b44  mov     ecx, 0C0000033h
0x140004b49  jmp     loc_140004C49
0x140004b4e  mov     ecx, 0C0000023h
0x140004b53  jmp     loc_140004C49
0x140004b58  mov     ecx, 0C000007Fh
0x140004b5d  jmp     loc_140004C49
0x140004b62  mov     ecx, 80000005h
0x140004b67  jmp     loc_140004C49
0x140004b6c  mov     eax, 8007047Eh
0x140004b71  cmp     ecx, eax
0x140004b73  jg      short loc_140004BD5
0x140004b75  jz      short loc_140004BCE
0x140004b77  cmp     ecx, 80070216h
0x140004b7d  jz      short loc_140004BC7
0x140004b7f  cmp     ecx, 8007023Eh
0x140004b85  jz      short loc_140004BBD
0x140004b87  cmp     ecx, 80070246h
0x140004b8d  jz      short loc_140004BB3
0x140004b8f  cmp     ecx, 80070247h
0x140004b95  jz      short loc_140004BA9
0x140004b97  cmp     ecx, 80070272h
0x140004b9d  jnz     short loc_140004BF1
0x140004b9f  mov     ecx, 0C0000273h
0x140004ba4  jmp     loc_140004C49
0x140004ba9  mov     ecx, 0C0000163h
0x140004bae  jmp     loc_140004C49
0x140004bb3  mov     ecx, 0C0000161h
0x140004bb8  jmp     loc_140004C49
0x140004bbd  mov     ecx, 0C0000025h
0x140004bc2  jmp     loc_140004C49
0x140004bc7  mov     ecx, 0C0000095h
0x140004bcc  jmp     short loc_140004C49
0x140004bce  mov     ecx, 0C0000059h
0x140004bd3  jmp     short loc_140004C49
0x140004bd5  cmp     ecx, 8007050Ch
0x140004bdb  jz      short loc_140004C44
0x140004bdd  cmp     ecx, 8007054Fh
0x140004be3  jz      short loc_140004C3D
0x140004be5  cmp     ecx, 800705B9h
0x140004beb  jz      short loc_140004C36
0x140004bed  test    ecx, ecx
0x140004bef  jz      short loc_140004C32
0x140004bf1  bt      ecx, 1Ch
0x140004bf5  jnb     short loc_140004BFD
0x140004bf7  btr     ecx, 1Ch
0x140004bfb  jmp     short loc_140004C49
0x140004bfd  mov     eax, ecx
0x140004bff  and     eax, 1FFF0000h
0x140004c04  cmp     eax, 70000h
0x140004c09  jnz     short loc_140004C1C
0x140004c0b  movzx   ecx, cx
0x140004c0e  mov     eax, ecx
0x140004c10  or      eax, 0C0070000h
0x140004c15  test    ecx, ecx
0x140004c17  cmovnz  ecx, eax
0x140004c1a  jmp     short loc_140004C49
0x140004c1c  cmp     eax, 90000h
0x140004c21  jnz     short loc_140004C3D
0x140004c23  test    ecx, ecx
0x140004c25  jle     short loc_140004C49
0x140004c27  movzx   ecx, cx
0x140004c2a  or      ecx, 0C0090000h
0x140004c30  jmp     short loc_140004C49
0x140004c32  xor     ecx, ecx
0x140004c34  jmp     short loc_140004C49
0x140004c36  mov     ecx, 0C000A083h
0x140004c3b  jmp     short loc_140004C49
0x140004c3d  mov     ecx, 0C00000E5h
0x140004c42  jmp     short loc_140004C49
0x140004c44  mov     ecx, 0C000042Bh
0x140004c49  mov     eax, ecx
0x140004c4b  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x1800049b8`
- end: `0x180004b74`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000286c`
- `0x18000291c`
- `0x180002974`
- `0x180002a3c`
- `0x180003e78`
- `0x180004be8`
- `0x1800054c0`
- `0x180007eb0`
- `0x18000fe20`
- `0x18000fe94`
- `0x18001148e`
- `0x1800114f9`
- `0x1800115c2`
- `0x18001162d`

## callees

- `0x1800049b8`

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
0x1800049b8  mov     eax, 800700EAh
0x1800049bd  cmp     ecx, eax
0x1800049bf  jg      loc_180004A94
0x1800049c5  jz      loc_180004A8A
0x1800049cb  mov     eax, 80070057h
0x1800049d0  cmp     ecx, eax
0x1800049d2  jg      short loc_180004A3E
0x1800049d4  jz      short loc_180004A34
0x1800049d6  cmp     ecx, 80004005h
0x1800049dc  jz      short loc_180004A2A
0x1800049de  cmp     ecx, 80070001h
0x1800049e4  jz      short loc_180004A20
0x1800049e6  cmp     ecx, 80070002h
0x1800049ec  jz      short loc_180004A16
0x1800049ee  cmp     ecx, 80070003h
0x1800049f4  jz      short loc_180004A0C
0x1800049f6  cmp     ecx, 8007000Eh
0x1800049fc  jnz     loc_180004B19
0x180004a02  mov     ecx, 0C0000017h
0x180004a07  jmp     loc_180004B71
0x180004a0c  mov     ecx, 0C000003Ah
0x180004a11  jmp     loc_180004B71
0x180004a16  mov     ecx, 0C0000034h
0x180004a1b  jmp     loc_180004B71
0x180004a20  mov     ecx, 0C0000002h
0x180004a25  jmp     loc_180004B71
0x180004a2a  mov     ecx, 0C0000001h
0x180004a2f  jmp     loc_180004B71
0x180004a34  mov     ecx, 0C000000Dh
0x180004a39  jmp     loc_180004B71
0x180004a3e  cmp     ecx, 80070070h
0x180004a44  jz      short loc_180004A80
0x180004a46  cmp     ecx, 8007007Ah
0x180004a4c  jz      short loc_180004A76
0x180004a4e  cmp     ecx, 8007007Bh
0x180004a54  jz      short loc_180004A6C
0x180004a56  cmp     ecx, 8007007Eh
0x180004a5c  jnz     loc_180004B19
0x180004a62  mov     ecx, 0C0000135h
0x180004a67  jmp     loc_180004B71
0x180004a6c  mov     ecx, 0C0000033h
0x180004a71  jmp     loc_180004B71
0x180004a76  mov     ecx, 0C0000023h
0x180004a7b  jmp     loc_180004B71
0x180004a80  mov     ecx, 0C000007Fh
0x180004a85  jmp     loc_180004B71
0x180004a8a  mov     ecx, 80000005h
0x180004a8f  jmp     loc_180004B71
0x180004a94  mov     eax, 8007047Eh
0x180004a99  cmp     ecx, eax
0x180004a9b  jg      short loc_180004AFD
0x180004a9d  jz      short loc_180004AF6
0x180004a9f  cmp     ecx, 80070216h
0x180004aa5  jz      short loc_180004AEF
0x180004aa7  cmp     ecx, 8007023Eh
0x180004aad  jz      short loc_180004AE5
0x180004aaf  cmp     ecx, 80070246h
0x180004ab5  jz      short loc_180004ADB
0x180004ab7  cmp     ecx, 80070247h
0x180004abd  jz      short loc_180004AD1
0x180004abf  cmp     ecx, 80070272h
0x180004ac5  jnz     short loc_180004B19
0x180004ac7  mov     ecx, 0C0000273h
0x180004acc  jmp     loc_180004B71
0x180004ad1  mov     ecx, 0C0000163h
0x180004ad6  jmp     loc_180004B71
0x180004adb  mov     ecx, 0C0000161h
0x180004ae0  jmp     loc_180004B71
0x180004ae5  mov     ecx, 0C0000025h
0x180004aea  jmp     loc_180004B71
0x180004aef  mov     ecx, 0C0000095h
0x180004af4  jmp     short loc_180004B71
0x180004af6  mov     ecx, 0C0000059h
0x180004afb  jmp     short loc_180004B71
0x180004afd  cmp     ecx, 8007050Ch
0x180004b03  jz      short loc_180004B6C
0x180004b05  cmp     ecx, 8007054Fh
0x180004b0b  jz      short loc_180004B65
0x180004b0d  cmp     ecx, 800705B9h
0x180004b13  jz      short loc_180004B5E
0x180004b15  test    ecx, ecx
0x180004b17  jz      short loc_180004B5A
0x180004b19  bt      ecx, 1Ch
0x180004b1d  jnb     short loc_180004B25
0x180004b1f  btr     ecx, 1Ch
0x180004b23  jmp     short loc_180004B71
0x180004b25  mov     eax, ecx
0x180004b27  and     eax, 1FFF0000h
0x180004b2c  cmp     eax, 70000h
0x180004b31  jnz     short loc_180004B44
0x180004b33  movzx   ecx, cx
0x180004b36  mov     eax, ecx
0x180004b38  or      eax, 0C0070000h
0x180004b3d  test    ecx, ecx
0x180004b3f  cmovnz  ecx, eax
0x180004b42  jmp     short loc_180004B71
0x180004b44  cmp     eax, 90000h
0x180004b49  jnz     short loc_180004B65
0x180004b4b  test    ecx, ecx
0x180004b4d  jle     short loc_180004B71
0x180004b4f  movzx   ecx, cx
0x180004b52  or      ecx, 0C0090000h
0x180004b58  jmp     short loc_180004B71
0x180004b5a  xor     ecx, ecx
0x180004b5c  jmp     short loc_180004B71
0x180004b5e  mov     ecx, 0C000A083h
0x180004b63  jmp     short loc_180004B71
0x180004b65  mov     ecx, 0C00000E5h
0x180004b6a  jmp     short loc_180004B71
0x180004b6c  mov     ecx, 0C000042Bh
0x180004b71  mov     eax, ecx
0x180004b73  retn
```

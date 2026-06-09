# wil::details::HrToNtStatus(long)

- ea: `0x1800059a4`
- end: `0x180005b60`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a40`
- `0x180002ae8`
- `0x180002b38`
- `0x180002bf0`
- `0x180004f68`
- `0x180005cd0`

## callees

- `0x1800059a4`

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
0x1800059a4  mov     eax, 800700EAh
0x1800059a9  cmp     ecx, eax
0x1800059ab  jg      loc_180005A80
0x1800059b1  jz      loc_180005A76
0x1800059b7  mov     eax, 80070057h
0x1800059bc  cmp     ecx, eax
0x1800059be  jg      short loc_180005A2A
0x1800059c0  jz      short loc_180005A20
0x1800059c2  cmp     ecx, 80004005h
0x1800059c8  jz      short loc_180005A16
0x1800059ca  cmp     ecx, 80070001h
0x1800059d0  jz      short loc_180005A0C
0x1800059d2  cmp     ecx, 80070002h
0x1800059d8  jz      short loc_180005A02
0x1800059da  cmp     ecx, 80070003h
0x1800059e0  jz      short loc_1800059F8
0x1800059e2  cmp     ecx, 8007000Eh
0x1800059e8  jnz     loc_180005B05
0x1800059ee  mov     ecx, 0C0000017h
0x1800059f3  jmp     loc_180005B5D
0x1800059f8  mov     ecx, 0C000003Ah
0x1800059fd  jmp     loc_180005B5D
0x180005a02  mov     ecx, 0C0000034h
0x180005a07  jmp     loc_180005B5D
0x180005a0c  mov     ecx, 0C0000002h
0x180005a11  jmp     loc_180005B5D
0x180005a16  mov     ecx, 0C0000001h
0x180005a1b  jmp     loc_180005B5D
0x180005a20  mov     ecx, 0C000000Dh
0x180005a25  jmp     loc_180005B5D
0x180005a2a  cmp     ecx, 80070070h
0x180005a30  jz      short loc_180005A6C
0x180005a32  cmp     ecx, 8007007Ah
0x180005a38  jz      short loc_180005A62
0x180005a3a  cmp     ecx, 8007007Bh
0x180005a40  jz      short loc_180005A58
0x180005a42  cmp     ecx, 8007007Eh
0x180005a48  jnz     loc_180005B05
0x180005a4e  mov     ecx, 0C0000135h
0x180005a53  jmp     loc_180005B5D
0x180005a58  mov     ecx, 0C0000033h
0x180005a5d  jmp     loc_180005B5D
0x180005a62  mov     ecx, 0C0000023h
0x180005a67  jmp     loc_180005B5D
0x180005a6c  mov     ecx, 0C000007Fh
0x180005a71  jmp     loc_180005B5D
0x180005a76  mov     ecx, 80000005h
0x180005a7b  jmp     loc_180005B5D
0x180005a80  mov     eax, 8007047Eh
0x180005a85  cmp     ecx, eax
0x180005a87  jg      short loc_180005AE9
0x180005a89  jz      short loc_180005AE2
0x180005a8b  cmp     ecx, 80070216h
0x180005a91  jz      short loc_180005ADB
0x180005a93  cmp     ecx, 8007023Eh
0x180005a99  jz      short loc_180005AD1
0x180005a9b  cmp     ecx, 80070246h
0x180005aa1  jz      short loc_180005AC7
0x180005aa3  cmp     ecx, 80070247h
0x180005aa9  jz      short loc_180005ABD
0x180005aab  cmp     ecx, 80070272h
0x180005ab1  jnz     short loc_180005B05
0x180005ab3  mov     ecx, 0C0000273h
0x180005ab8  jmp     loc_180005B5D
0x180005abd  mov     ecx, 0C0000163h
0x180005ac2  jmp     loc_180005B5D
0x180005ac7  mov     ecx, 0C0000161h
0x180005acc  jmp     loc_180005B5D
0x180005ad1  mov     ecx, 0C0000025h
0x180005ad6  jmp     loc_180005B5D
0x180005adb  mov     ecx, 0C0000095h
0x180005ae0  jmp     short loc_180005B5D
0x180005ae2  mov     ecx, 0C0000059h
0x180005ae7  jmp     short loc_180005B5D
0x180005ae9  cmp     ecx, 8007050Ch
0x180005aef  jz      short loc_180005B58
0x180005af1  cmp     ecx, 8007054Fh
0x180005af7  jz      short loc_180005B51
0x180005af9  cmp     ecx, 800705B9h
0x180005aff  jz      short loc_180005B4A
0x180005b01  test    ecx, ecx
0x180005b03  jz      short loc_180005B46
0x180005b05  bt      ecx, 1Ch
0x180005b09  jnb     short loc_180005B11
0x180005b0b  btr     ecx, 1Ch
0x180005b0f  jmp     short loc_180005B5D
0x180005b11  mov     eax, ecx
0x180005b13  and     eax, 1FFF0000h
0x180005b18  cmp     eax, 70000h
0x180005b1d  jnz     short loc_180005B30
0x180005b1f  movzx   ecx, cx
0x180005b22  mov     eax, ecx
0x180005b24  or      eax, 0C0070000h
0x180005b29  test    ecx, ecx
0x180005b2b  cmovnz  ecx, eax
0x180005b2e  jmp     short loc_180005B5D
0x180005b30  cmp     eax, 90000h
0x180005b35  jnz     short loc_180005B51
0x180005b37  test    ecx, ecx
0x180005b39  jle     short loc_180005B5D
0x180005b3b  movzx   ecx, cx
0x180005b3e  or      ecx, 0C0090000h
0x180005b44  jmp     short loc_180005B5D
0x180005b46  xor     ecx, ecx
0x180005b48  jmp     short loc_180005B5D
0x180005b4a  mov     ecx, 0C000A083h
0x180005b4f  jmp     short loc_180005B5D
0x180005b51  mov     ecx, 0C00000E5h
0x180005b56  jmp     short loc_180005B5D
0x180005b58  mov     ecx, 0C000042Bh
0x180005b5d  mov     eax, ecx
0x180005b5f  retn
```

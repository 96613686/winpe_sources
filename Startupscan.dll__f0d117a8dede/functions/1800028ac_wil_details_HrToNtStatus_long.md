# wil::details::HrToNtStatus(long)

- ea: `0x1800028ac`
- end: `0x180002a68`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cc0`
- `0x180001d60`
- `0x180002448`

## callees

- `0x1800028ac`

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
0x1800028ac  mov     eax, 800700EAh
0x1800028b1  cmp     ecx, eax
0x1800028b3  jg      loc_180002988
0x1800028b9  jz      loc_18000297E
0x1800028bf  mov     eax, 80070057h
0x1800028c4  cmp     ecx, eax
0x1800028c6  jg      short loc_180002932
0x1800028c8  jz      short loc_180002928
0x1800028ca  cmp     ecx, 80004005h
0x1800028d0  jz      short loc_18000291E
0x1800028d2  cmp     ecx, 80070001h
0x1800028d8  jz      short loc_180002914
0x1800028da  cmp     ecx, 80070002h
0x1800028e0  jz      short loc_18000290A
0x1800028e2  cmp     ecx, 80070003h
0x1800028e8  jz      short loc_180002900
0x1800028ea  cmp     ecx, 8007000Eh
0x1800028f0  jnz     loc_180002A0D
0x1800028f6  mov     ecx, 0C0000017h
0x1800028fb  jmp     loc_180002A65
0x180002900  mov     ecx, 0C000003Ah
0x180002905  jmp     loc_180002A65
0x18000290a  mov     ecx, 0C0000034h
0x18000290f  jmp     loc_180002A65
0x180002914  mov     ecx, 0C0000002h
0x180002919  jmp     loc_180002A65
0x18000291e  mov     ecx, 0C0000001h
0x180002923  jmp     loc_180002A65
0x180002928  mov     ecx, 0C000000Dh
0x18000292d  jmp     loc_180002A65
0x180002932  cmp     ecx, 80070070h
0x180002938  jz      short loc_180002974
0x18000293a  cmp     ecx, 8007007Ah
0x180002940  jz      short loc_18000296A
0x180002942  cmp     ecx, 8007007Bh
0x180002948  jz      short loc_180002960
0x18000294a  cmp     ecx, 8007007Eh
0x180002950  jnz     loc_180002A0D
0x180002956  mov     ecx, 0C0000135h
0x18000295b  jmp     loc_180002A65
0x180002960  mov     ecx, 0C0000033h
0x180002965  jmp     loc_180002A65
0x18000296a  mov     ecx, 0C0000023h
0x18000296f  jmp     loc_180002A65
0x180002974  mov     ecx, 0C000007Fh
0x180002979  jmp     loc_180002A65
0x18000297e  mov     ecx, 80000005h
0x180002983  jmp     loc_180002A65
0x180002988  mov     eax, 8007047Eh
0x18000298d  cmp     ecx, eax
0x18000298f  jg      short loc_1800029F1
0x180002991  jz      short loc_1800029EA
0x180002993  cmp     ecx, 80070216h
0x180002999  jz      short loc_1800029E3
0x18000299b  cmp     ecx, 8007023Eh
0x1800029a1  jz      short loc_1800029D9
0x1800029a3  cmp     ecx, 80070246h
0x1800029a9  jz      short loc_1800029CF
0x1800029ab  cmp     ecx, 80070247h
0x1800029b1  jz      short loc_1800029C5
0x1800029b3  cmp     ecx, 80070272h
0x1800029b9  jnz     short loc_180002A0D
0x1800029bb  mov     ecx, 0C0000273h
0x1800029c0  jmp     loc_180002A65
0x1800029c5  mov     ecx, 0C0000163h
0x1800029ca  jmp     loc_180002A65
0x1800029cf  mov     ecx, 0C0000161h
0x1800029d4  jmp     loc_180002A65
0x1800029d9  mov     ecx, 0C0000025h
0x1800029de  jmp     loc_180002A65
0x1800029e3  mov     ecx, 0C0000095h
0x1800029e8  jmp     short loc_180002A65
0x1800029ea  mov     ecx, 0C0000059h
0x1800029ef  jmp     short loc_180002A65
0x1800029f1  cmp     ecx, 8007050Ch
0x1800029f7  jz      short loc_180002A60
0x1800029f9  cmp     ecx, 8007054Fh
0x1800029ff  jz      short loc_180002A59
0x180002a01  cmp     ecx, 800705B9h
0x180002a07  jz      short loc_180002A52
0x180002a09  test    ecx, ecx
0x180002a0b  jz      short loc_180002A4E
0x180002a0d  bt      ecx, 1Ch
0x180002a11  jnb     short loc_180002A19
0x180002a13  btr     ecx, 1Ch
0x180002a17  jmp     short loc_180002A65
0x180002a19  mov     eax, ecx
0x180002a1b  and     eax, 1FFF0000h
0x180002a20  cmp     eax, 70000h
0x180002a25  jnz     short loc_180002A38
0x180002a27  movzx   ecx, cx
0x180002a2a  mov     eax, ecx
0x180002a2c  or      eax, 0C0070000h
0x180002a31  test    ecx, ecx
0x180002a33  cmovnz  ecx, eax
0x180002a36  jmp     short loc_180002A65
0x180002a38  cmp     eax, 90000h
0x180002a3d  jnz     short loc_180002A59
0x180002a3f  test    ecx, ecx
0x180002a41  jle     short loc_180002A65
0x180002a43  movzx   ecx, cx
0x180002a46  or      ecx, 0C0090000h
0x180002a4c  jmp     short loc_180002A65
0x180002a4e  xor     ecx, ecx
0x180002a50  jmp     short loc_180002A65
0x180002a52  mov     ecx, 0C000A083h
0x180002a57  jmp     short loc_180002A65
0x180002a59  mov     ecx, 0C00000E5h
0x180002a5e  jmp     short loc_180002A65
0x180002a60  mov     ecx, 0C000042Bh
0x180002a65  mov     eax, ecx
0x180002a67  retn
```

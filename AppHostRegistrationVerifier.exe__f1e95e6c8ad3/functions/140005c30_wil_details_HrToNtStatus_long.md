# wil::details::HrToNtStatus(long)

- ea: `0x140005c30`
- end: `0x140005dec`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031e4`
- `0x140003264`
- `0x1400032dc`
- `0x14000332c`
- `0x1400033f4`
- `0x1400051a8`
- `0x140005f48`
- `0x140006890`
- `0x140008b7c`
- `0x140008c7c`
- `0x140008ebc`
- `0x140011085`
- `0x1400110d0`
- `0x140011193`
- `0x1400111de`

## callees

- `0x140005c30`

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
0x140005c30  mov     eax, 800700EAh
0x140005c35  cmp     ecx, eax
0x140005c37  jg      loc_140005D0C
0x140005c3d  jz      loc_140005D02
0x140005c43  mov     eax, 80070057h
0x140005c48  cmp     ecx, eax
0x140005c4a  jg      short loc_140005CB6
0x140005c4c  jz      short loc_140005CAC
0x140005c4e  cmp     ecx, 80004005h
0x140005c54  jz      short loc_140005CA2
0x140005c56  cmp     ecx, 80070001h
0x140005c5c  jz      short loc_140005C98
0x140005c5e  cmp     ecx, 80070002h
0x140005c64  jz      short loc_140005C8E
0x140005c66  cmp     ecx, 80070003h
0x140005c6c  jz      short loc_140005C84
0x140005c6e  cmp     ecx, 8007000Eh
0x140005c74  jnz     loc_140005D91
0x140005c7a  mov     ecx, 0C0000017h
0x140005c7f  jmp     loc_140005DE9
0x140005c84  mov     ecx, 0C000003Ah
0x140005c89  jmp     loc_140005DE9
0x140005c8e  mov     ecx, 0C0000034h
0x140005c93  jmp     loc_140005DE9
0x140005c98  mov     ecx, 0C0000002h
0x140005c9d  jmp     loc_140005DE9
0x140005ca2  mov     ecx, 0C0000001h
0x140005ca7  jmp     loc_140005DE9
0x140005cac  mov     ecx, 0C000000Dh
0x140005cb1  jmp     loc_140005DE9
0x140005cb6  cmp     ecx, 80070070h
0x140005cbc  jz      short loc_140005CF8
0x140005cbe  cmp     ecx, 8007007Ah
0x140005cc4  jz      short loc_140005CEE
0x140005cc6  cmp     ecx, 8007007Bh
0x140005ccc  jz      short loc_140005CE4
0x140005cce  cmp     ecx, 8007007Eh
0x140005cd4  jnz     loc_140005D91
0x140005cda  mov     ecx, 0C0000135h
0x140005cdf  jmp     loc_140005DE9
0x140005ce4  mov     ecx, 0C0000033h
0x140005ce9  jmp     loc_140005DE9
0x140005cee  mov     ecx, 0C0000023h
0x140005cf3  jmp     loc_140005DE9
0x140005cf8  mov     ecx, 0C000007Fh
0x140005cfd  jmp     loc_140005DE9
0x140005d02  mov     ecx, 80000005h
0x140005d07  jmp     loc_140005DE9
0x140005d0c  mov     eax, 8007047Eh
0x140005d11  cmp     ecx, eax
0x140005d13  jg      short loc_140005D75
0x140005d15  jz      short loc_140005D6E
0x140005d17  cmp     ecx, 80070216h
0x140005d1d  jz      short loc_140005D67
0x140005d1f  cmp     ecx, 8007023Eh
0x140005d25  jz      short loc_140005D5D
0x140005d27  cmp     ecx, 80070246h
0x140005d2d  jz      short loc_140005D53
0x140005d2f  cmp     ecx, 80070247h
0x140005d35  jz      short loc_140005D49
0x140005d37  cmp     ecx, 80070272h
0x140005d3d  jnz     short loc_140005D91
0x140005d3f  mov     ecx, 0C0000273h
0x140005d44  jmp     loc_140005DE9
0x140005d49  mov     ecx, 0C0000163h
0x140005d4e  jmp     loc_140005DE9
0x140005d53  mov     ecx, 0C0000161h
0x140005d58  jmp     loc_140005DE9
0x140005d5d  mov     ecx, 0C0000025h
0x140005d62  jmp     loc_140005DE9
0x140005d67  mov     ecx, 0C0000095h
0x140005d6c  jmp     short loc_140005DE9
0x140005d6e  mov     ecx, 0C0000059h
0x140005d73  jmp     short loc_140005DE9
0x140005d75  cmp     ecx, 8007050Ch
0x140005d7b  jz      short loc_140005DE4
0x140005d7d  cmp     ecx, 8007054Fh
0x140005d83  jz      short loc_140005DDD
0x140005d85  cmp     ecx, 800705B9h
0x140005d8b  jz      short loc_140005DD6
0x140005d8d  test    ecx, ecx
0x140005d8f  jz      short loc_140005DD2
0x140005d91  bt      ecx, 1Ch
0x140005d95  jnb     short loc_140005D9D
0x140005d97  btr     ecx, 1Ch
0x140005d9b  jmp     short loc_140005DE9
0x140005d9d  mov     eax, ecx
0x140005d9f  and     eax, 1FFF0000h
0x140005da4  cmp     eax, 70000h
0x140005da9  jnz     short loc_140005DBC
0x140005dab  movzx   ecx, cx
0x140005dae  mov     eax, ecx
0x140005db0  or      eax, 0C0070000h
0x140005db5  test    ecx, ecx
0x140005db7  cmovnz  ecx, eax
0x140005dba  jmp     short loc_140005DE9
0x140005dbc  cmp     eax, 90000h
0x140005dc1  jnz     short loc_140005DDD
0x140005dc3  test    ecx, ecx
0x140005dc5  jle     short loc_140005DE9
0x140005dc7  movzx   ecx, cx
0x140005dca  or      ecx, 0C0090000h
0x140005dd0  jmp     short loc_140005DE9
0x140005dd2  xor     ecx, ecx
0x140005dd4  jmp     short loc_140005DE9
0x140005dd6  mov     ecx, 0C000A083h
0x140005ddb  jmp     short loc_140005DE9
0x140005ddd  mov     ecx, 0C00000E5h
0x140005de2  jmp     short loc_140005DE9
0x140005de4  mov     ecx, 0C000042Bh
0x140005de9  mov     eax, ecx
0x140005deb  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140003bcc`
- end: `0x140003d88`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003768`
- `0x140004a5c`
- `0x140004ac0`
- `0x140004d68`
- `0x140004e28`
- `0x140007fa0`
- `0x140008048`
- `0x1400080f4`

## callees

- `0x140003bcc`

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
0x140003bcc  mov     eax, 800700EAh
0x140003bd1  cmp     ecx, eax
0x140003bd3  jg      loc_140003CA8
0x140003bd9  jz      loc_140003C9E
0x140003bdf  mov     eax, 80070057h
0x140003be4  cmp     ecx, eax
0x140003be6  jg      short loc_140003C52
0x140003be8  jz      short loc_140003C48
0x140003bea  cmp     ecx, 80004005h
0x140003bf0  jz      short loc_140003C3E
0x140003bf2  cmp     ecx, 80070001h
0x140003bf8  jz      short loc_140003C34
0x140003bfa  cmp     ecx, 80070002h
0x140003c00  jz      short loc_140003C2A
0x140003c02  cmp     ecx, 80070003h
0x140003c08  jz      short loc_140003C20
0x140003c0a  cmp     ecx, 8007000Eh
0x140003c10  jnz     loc_140003D2D
0x140003c16  mov     ecx, 0C0000017h
0x140003c1b  jmp     loc_140003D85
0x140003c20  mov     ecx, 0C000003Ah
0x140003c25  jmp     loc_140003D85
0x140003c2a  mov     ecx, 0C0000034h
0x140003c2f  jmp     loc_140003D85
0x140003c34  mov     ecx, 0C0000002h
0x140003c39  jmp     loc_140003D85
0x140003c3e  mov     ecx, 0C0000001h
0x140003c43  jmp     loc_140003D85
0x140003c48  mov     ecx, 0C000000Dh
0x140003c4d  jmp     loc_140003D85
0x140003c52  cmp     ecx, 80070070h
0x140003c58  jz      short loc_140003C94
0x140003c5a  cmp     ecx, 8007007Ah
0x140003c60  jz      short loc_140003C8A
0x140003c62  cmp     ecx, 8007007Bh
0x140003c68  jz      short loc_140003C80
0x140003c6a  cmp     ecx, 8007007Eh
0x140003c70  jnz     loc_140003D2D
0x140003c76  mov     ecx, 0C0000135h
0x140003c7b  jmp     loc_140003D85
0x140003c80  mov     ecx, 0C0000033h
0x140003c85  jmp     loc_140003D85
0x140003c8a  mov     ecx, 0C0000023h
0x140003c8f  jmp     loc_140003D85
0x140003c94  mov     ecx, 0C000007Fh
0x140003c99  jmp     loc_140003D85
0x140003c9e  mov     ecx, 80000005h
0x140003ca3  jmp     loc_140003D85
0x140003ca8  mov     eax, 8007047Eh
0x140003cad  cmp     ecx, eax
0x140003caf  jg      short loc_140003D11
0x140003cb1  jz      short loc_140003D0A
0x140003cb3  cmp     ecx, 80070216h
0x140003cb9  jz      short loc_140003D03
0x140003cbb  cmp     ecx, 8007023Eh
0x140003cc1  jz      short loc_140003CF9
0x140003cc3  cmp     ecx, 80070246h
0x140003cc9  jz      short loc_140003CEF
0x140003ccb  cmp     ecx, 80070247h
0x140003cd1  jz      short loc_140003CE5
0x140003cd3  cmp     ecx, 80070272h
0x140003cd9  jnz     short loc_140003D2D
0x140003cdb  mov     ecx, 0C0000273h
0x140003ce0  jmp     loc_140003D85
0x140003ce5  mov     ecx, 0C0000163h
0x140003cea  jmp     loc_140003D85
0x140003cef  mov     ecx, 0C0000161h
0x140003cf4  jmp     loc_140003D85
0x140003cf9  mov     ecx, 0C0000025h
0x140003cfe  jmp     loc_140003D85
0x140003d03  mov     ecx, 0C0000095h
0x140003d08  jmp     short loc_140003D85
0x140003d0a  mov     ecx, 0C0000059h
0x140003d0f  jmp     short loc_140003D85
0x140003d11  cmp     ecx, 8007050Ch
0x140003d17  jz      short loc_140003D80
0x140003d19  cmp     ecx, 8007054Fh
0x140003d1f  jz      short loc_140003D79
0x140003d21  cmp     ecx, 800705B9h
0x140003d27  jz      short loc_140003D72
0x140003d29  test    ecx, ecx
0x140003d2b  jz      short loc_140003D6E
0x140003d2d  bt      ecx, 1Ch
0x140003d31  jnb     short loc_140003D39
0x140003d33  btr     ecx, 1Ch
0x140003d37  jmp     short loc_140003D85
0x140003d39  mov     eax, ecx
0x140003d3b  and     eax, 1FFF0000h
0x140003d40  cmp     eax, 70000h
0x140003d45  jnz     short loc_140003D58
0x140003d47  movzx   ecx, cx
0x140003d4a  mov     eax, ecx
0x140003d4c  or      eax, 0C0070000h
0x140003d51  test    ecx, ecx
0x140003d53  cmovnz  ecx, eax
0x140003d56  jmp     short loc_140003D85
0x140003d58  cmp     eax, 90000h
0x140003d5d  jnz     short loc_140003D79
0x140003d5f  test    ecx, ecx
0x140003d61  jle     short loc_140003D85
0x140003d63  movzx   ecx, cx
0x140003d66  or      ecx, 0C0090000h
0x140003d6c  jmp     short loc_140003D85
0x140003d6e  xor     ecx, ecx
0x140003d70  jmp     short loc_140003D85
0x140003d72  mov     ecx, 0C000A083h
0x140003d77  jmp     short loc_140003D85
0x140003d79  mov     ecx, 0C00000E5h
0x140003d7e  jmp     short loc_140003D85
0x140003d80  mov     ecx, 0C000042Bh
0x140003d85  mov     eax, ecx
0x140003d87  retn
```

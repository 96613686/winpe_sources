# wil::details::HrToNtStatus(long)

- ea: `0x180005aa0`
- end: `0x180005c5c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002304`
- `0x1800023ac`
- `0x1800023fc`
- `0x1800024bc`
- `0x1800050c4`
- `0x180005c64`

## callees

- `0x180005aa0`

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
0x180005aa0  mov     eax, 800700EAh
0x180005aa5  cmp     ecx, eax
0x180005aa7  jg      loc_180005B7C
0x180005aad  jz      loc_180005B72
0x180005ab3  mov     eax, 80070057h
0x180005ab8  cmp     ecx, eax
0x180005aba  jg      short loc_180005B26
0x180005abc  jz      short loc_180005B1C
0x180005abe  cmp     ecx, 80004005h
0x180005ac4  jz      short loc_180005B12
0x180005ac6  cmp     ecx, 80070001h
0x180005acc  jz      short loc_180005B08
0x180005ace  cmp     ecx, 80070002h
0x180005ad4  jz      short loc_180005AFE
0x180005ad6  cmp     ecx, 80070003h
0x180005adc  jz      short loc_180005AF4
0x180005ade  cmp     ecx, 8007000Eh
0x180005ae4  jnz     loc_180005C01
0x180005aea  mov     ecx, 0C0000017h
0x180005aef  jmp     loc_180005C59
0x180005af4  mov     ecx, 0C000003Ah
0x180005af9  jmp     loc_180005C59
0x180005afe  mov     ecx, 0C0000034h
0x180005b03  jmp     loc_180005C59
0x180005b08  mov     ecx, 0C0000002h
0x180005b0d  jmp     loc_180005C59
0x180005b12  mov     ecx, 0C0000001h
0x180005b17  jmp     loc_180005C59
0x180005b1c  mov     ecx, 0C000000Dh
0x180005b21  jmp     loc_180005C59
0x180005b26  cmp     ecx, 80070070h
0x180005b2c  jz      short loc_180005B68
0x180005b2e  cmp     ecx, 8007007Ah
0x180005b34  jz      short loc_180005B5E
0x180005b36  cmp     ecx, 8007007Bh
0x180005b3c  jz      short loc_180005B54
0x180005b3e  cmp     ecx, 8007007Eh
0x180005b44  jnz     loc_180005C01
0x180005b4a  mov     ecx, 0C0000135h
0x180005b4f  jmp     loc_180005C59
0x180005b54  mov     ecx, 0C0000033h
0x180005b59  jmp     loc_180005C59
0x180005b5e  mov     ecx, 0C0000023h
0x180005b63  jmp     loc_180005C59
0x180005b68  mov     ecx, 0C000007Fh
0x180005b6d  jmp     loc_180005C59
0x180005b72  mov     ecx, 80000005h
0x180005b77  jmp     loc_180005C59
0x180005b7c  mov     eax, 8007047Eh
0x180005b81  cmp     ecx, eax
0x180005b83  jg      short loc_180005BE5
0x180005b85  jz      short loc_180005BDE
0x180005b87  cmp     ecx, 80070216h
0x180005b8d  jz      short loc_180005BD7
0x180005b8f  cmp     ecx, 8007023Eh
0x180005b95  jz      short loc_180005BCD
0x180005b97  cmp     ecx, 80070246h
0x180005b9d  jz      short loc_180005BC3
0x180005b9f  cmp     ecx, 80070247h
0x180005ba5  jz      short loc_180005BB9
0x180005ba7  cmp     ecx, 80070272h
0x180005bad  jnz     short loc_180005C01
0x180005baf  mov     ecx, 0C0000273h
0x180005bb4  jmp     loc_180005C59
0x180005bb9  mov     ecx, 0C0000163h
0x180005bbe  jmp     loc_180005C59
0x180005bc3  mov     ecx, 0C0000161h
0x180005bc8  jmp     loc_180005C59
0x180005bcd  mov     ecx, 0C0000025h
0x180005bd2  jmp     loc_180005C59
0x180005bd7  mov     ecx, 0C0000095h
0x180005bdc  jmp     short loc_180005C59
0x180005bde  mov     ecx, 0C0000059h
0x180005be3  jmp     short loc_180005C59
0x180005be5  cmp     ecx, 8007050Ch
0x180005beb  jz      short loc_180005C54
0x180005bed  cmp     ecx, 8007054Fh
0x180005bf3  jz      short loc_180005C4D
0x180005bf5  cmp     ecx, 800705B9h
0x180005bfb  jz      short loc_180005C46
0x180005bfd  test    ecx, ecx
0x180005bff  jz      short loc_180005C42
0x180005c01  bt      ecx, 1Ch
0x180005c05  jnb     short loc_180005C0D
0x180005c07  btr     ecx, 1Ch
0x180005c0b  jmp     short loc_180005C59
0x180005c0d  mov     eax, ecx
0x180005c0f  and     eax, 1FFF0000h
0x180005c14  cmp     eax, 70000h
0x180005c19  jnz     short loc_180005C2C
0x180005c1b  movzx   ecx, cx
0x180005c1e  mov     eax, ecx
0x180005c20  or      eax, 0C0070000h
0x180005c25  test    ecx, ecx
0x180005c27  cmovnz  ecx, eax
0x180005c2a  jmp     short loc_180005C59
0x180005c2c  cmp     eax, 90000h
0x180005c31  jnz     short loc_180005C4D
0x180005c33  test    ecx, ecx
0x180005c35  jle     short loc_180005C59
0x180005c37  movzx   ecx, cx
0x180005c3a  or      ecx, 0C0090000h
0x180005c40  jmp     short loc_180005C59
0x180005c42  xor     ecx, ecx
0x180005c44  jmp     short loc_180005C59
0x180005c46  mov     ecx, 0C000A083h
0x180005c4b  jmp     short loc_180005C59
0x180005c4d  mov     ecx, 0C00000E5h
0x180005c52  jmp     short loc_180005C59
0x180005c54  mov     ecx, 0C000042Bh
0x180005c59  mov     eax, ecx
0x180005c5b  retn
```

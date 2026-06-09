# wil::details::HrToNtStatus(long)

- ea: `0x140004ba0`
- end: `0x140004d5c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004b14`
- `0x140006d08`
- `0x140006d80`
- `0x140006dd0`
- `0x140008898`
- `0x14000943c`

## callees

- `0x140004ba0`

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
0x140004ba0  mov     eax, 800700EAh
0x140004ba5  cmp     ecx, eax
0x140004ba7  jg      loc_140004C7C
0x140004bad  jz      loc_140004C72
0x140004bb3  mov     eax, 80070057h
0x140004bb8  cmp     ecx, eax
0x140004bba  jg      short loc_140004C26
0x140004bbc  jz      short loc_140004C1C
0x140004bbe  cmp     ecx, 80004005h
0x140004bc4  jz      short loc_140004C12
0x140004bc6  cmp     ecx, 80070001h
0x140004bcc  jz      short loc_140004C08
0x140004bce  cmp     ecx, 80070002h
0x140004bd4  jz      short loc_140004BFE
0x140004bd6  cmp     ecx, 80070003h
0x140004bdc  jz      short loc_140004BF4
0x140004bde  cmp     ecx, 8007000Eh
0x140004be4  jnz     loc_140004D01
0x140004bea  mov     ecx, 0C0000017h
0x140004bef  jmp     loc_140004D59
0x140004bf4  mov     ecx, 0C000003Ah
0x140004bf9  jmp     loc_140004D59
0x140004bfe  mov     ecx, 0C0000034h
0x140004c03  jmp     loc_140004D59
0x140004c08  mov     ecx, 0C0000002h
0x140004c0d  jmp     loc_140004D59
0x140004c12  mov     ecx, 0C0000001h
0x140004c17  jmp     loc_140004D59
0x140004c1c  mov     ecx, 0C000000Dh
0x140004c21  jmp     loc_140004D59
0x140004c26  cmp     ecx, 80070070h
0x140004c2c  jz      short loc_140004C68
0x140004c2e  cmp     ecx, 8007007Ah
0x140004c34  jz      short loc_140004C5E
0x140004c36  cmp     ecx, 8007007Bh
0x140004c3c  jz      short loc_140004C54
0x140004c3e  cmp     ecx, 8007007Eh
0x140004c44  jnz     loc_140004D01
0x140004c4a  mov     ecx, 0C0000135h
0x140004c4f  jmp     loc_140004D59
0x140004c54  mov     ecx, 0C0000033h
0x140004c59  jmp     loc_140004D59
0x140004c5e  mov     ecx, 0C0000023h
0x140004c63  jmp     loc_140004D59
0x140004c68  mov     ecx, 0C000007Fh
0x140004c6d  jmp     loc_140004D59
0x140004c72  mov     ecx, 80000005h
0x140004c77  jmp     loc_140004D59
0x140004c7c  mov     eax, 8007047Eh
0x140004c81  cmp     ecx, eax
0x140004c83  jg      short loc_140004CE5
0x140004c85  jz      short loc_140004CDE
0x140004c87  cmp     ecx, 80070216h
0x140004c8d  jz      short loc_140004CD7
0x140004c8f  cmp     ecx, 8007023Eh
0x140004c95  jz      short loc_140004CCD
0x140004c97  cmp     ecx, 80070246h
0x140004c9d  jz      short loc_140004CC3
0x140004c9f  cmp     ecx, 80070247h
0x140004ca5  jz      short loc_140004CB9
0x140004ca7  cmp     ecx, 80070272h
0x140004cad  jnz     short loc_140004D01
0x140004caf  mov     ecx, 0C0000273h
0x140004cb4  jmp     loc_140004D59
0x140004cb9  mov     ecx, 0C0000163h
0x140004cbe  jmp     loc_140004D59
0x140004cc3  mov     ecx, 0C0000161h
0x140004cc8  jmp     loc_140004D59
0x140004ccd  mov     ecx, 0C0000025h
0x140004cd2  jmp     loc_140004D59
0x140004cd7  mov     ecx, 0C0000095h
0x140004cdc  jmp     short loc_140004D59
0x140004cde  mov     ecx, 0C0000059h
0x140004ce3  jmp     short loc_140004D59
0x140004ce5  cmp     ecx, 8007050Ch
0x140004ceb  jz      short loc_140004D54
0x140004ced  cmp     ecx, 8007054Fh
0x140004cf3  jz      short loc_140004D4D
0x140004cf5  cmp     ecx, 800705B9h
0x140004cfb  jz      short loc_140004D46
0x140004cfd  test    ecx, ecx
0x140004cff  jz      short loc_140004D42
0x140004d01  bt      ecx, 1Ch
0x140004d05  jnb     short loc_140004D0D
0x140004d07  btr     ecx, 1Ch
0x140004d0b  jmp     short loc_140004D59
0x140004d0d  mov     eax, ecx
0x140004d0f  and     eax, 1FFF0000h
0x140004d14  cmp     eax, 70000h
0x140004d19  jnz     short loc_140004D2C
0x140004d1b  movzx   ecx, cx
0x140004d1e  mov     eax, ecx
0x140004d20  or      eax, 0C0070000h
0x140004d25  test    ecx, ecx
0x140004d27  cmovnz  ecx, eax
0x140004d2a  jmp     short loc_140004D59
0x140004d2c  cmp     eax, 90000h
0x140004d31  jnz     short loc_140004D4D
0x140004d33  test    ecx, ecx
0x140004d35  jle     short loc_140004D59
0x140004d37  movzx   ecx, cx
0x140004d3a  or      ecx, 0C0090000h
0x140004d40  jmp     short loc_140004D59
0x140004d42  xor     ecx, ecx
0x140004d44  jmp     short loc_140004D59
0x140004d46  mov     ecx, 0C000A083h
0x140004d4b  jmp     short loc_140004D59
0x140004d4d  mov     ecx, 0C00000E5h
0x140004d52  jmp     short loc_140004D59
0x140004d54  mov     ecx, 0C000042Bh
0x140004d59  mov     eax, ecx
0x140004d5b  retn
```

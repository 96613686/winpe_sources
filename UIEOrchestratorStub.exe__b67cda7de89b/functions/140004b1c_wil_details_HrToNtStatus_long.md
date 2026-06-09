# wil::details::HrToNtStatus(long)

- ea: `0x140004b1c`
- end: `0x140004cd8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002de8`
- `0x140002e90`
- `0x140002ee0`
- `0x140002f98`
- `0x1400040e8`
- `0x140004ce0`

## callees

- `0x140004b1c`

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
0x140004b1c  mov     eax, 800700EAh
0x140004b21  cmp     ecx, eax
0x140004b23  jg      loc_140004BF8
0x140004b29  jz      loc_140004BEE
0x140004b2f  mov     eax, 80070057h
0x140004b34  cmp     ecx, eax
0x140004b36  jg      short loc_140004BA2
0x140004b38  jz      short loc_140004B98
0x140004b3a  cmp     ecx, 80004005h
0x140004b40  jz      short loc_140004B8E
0x140004b42  cmp     ecx, 80070001h
0x140004b48  jz      short loc_140004B84
0x140004b4a  cmp     ecx, 80070002h
0x140004b50  jz      short loc_140004B7A
0x140004b52  cmp     ecx, 80070003h
0x140004b58  jz      short loc_140004B70
0x140004b5a  cmp     ecx, 8007000Eh
0x140004b60  jnz     loc_140004C7D
0x140004b66  mov     ecx, 0C0000017h
0x140004b6b  jmp     loc_140004CD5
0x140004b70  mov     ecx, 0C000003Ah
0x140004b75  jmp     loc_140004CD5
0x140004b7a  mov     ecx, 0C0000034h
0x140004b7f  jmp     loc_140004CD5
0x140004b84  mov     ecx, 0C0000002h
0x140004b89  jmp     loc_140004CD5
0x140004b8e  mov     ecx, 0C0000001h
0x140004b93  jmp     loc_140004CD5
0x140004b98  mov     ecx, 0C000000Dh
0x140004b9d  jmp     loc_140004CD5
0x140004ba2  cmp     ecx, 80070070h
0x140004ba8  jz      short loc_140004BE4
0x140004baa  cmp     ecx, 8007007Ah
0x140004bb0  jz      short loc_140004BDA
0x140004bb2  cmp     ecx, 8007007Bh
0x140004bb8  jz      short loc_140004BD0
0x140004bba  cmp     ecx, 8007007Eh
0x140004bc0  jnz     loc_140004C7D
0x140004bc6  mov     ecx, 0C0000135h
0x140004bcb  jmp     loc_140004CD5
0x140004bd0  mov     ecx, 0C0000033h
0x140004bd5  jmp     loc_140004CD5
0x140004bda  mov     ecx, 0C0000023h
0x140004bdf  jmp     loc_140004CD5
0x140004be4  mov     ecx, 0C000007Fh
0x140004be9  jmp     loc_140004CD5
0x140004bee  mov     ecx, 80000005h
0x140004bf3  jmp     loc_140004CD5
0x140004bf8  mov     eax, 8007047Eh
0x140004bfd  cmp     ecx, eax
0x140004bff  jg      short loc_140004C61
0x140004c01  jz      short loc_140004C5A
0x140004c03  cmp     ecx, 80070216h
0x140004c09  jz      short loc_140004C53
0x140004c0b  cmp     ecx, 8007023Eh
0x140004c11  jz      short loc_140004C49
0x140004c13  cmp     ecx, 80070246h
0x140004c19  jz      short loc_140004C3F
0x140004c1b  cmp     ecx, 80070247h
0x140004c21  jz      short loc_140004C35
0x140004c23  cmp     ecx, 80070272h
0x140004c29  jnz     short loc_140004C7D
0x140004c2b  mov     ecx, 0C0000273h
0x140004c30  jmp     loc_140004CD5
0x140004c35  mov     ecx, 0C0000163h
0x140004c3a  jmp     loc_140004CD5
0x140004c3f  mov     ecx, 0C0000161h
0x140004c44  jmp     loc_140004CD5
0x140004c49  mov     ecx, 0C0000025h
0x140004c4e  jmp     loc_140004CD5
0x140004c53  mov     ecx, 0C0000095h
0x140004c58  jmp     short loc_140004CD5
0x140004c5a  mov     ecx, 0C0000059h
0x140004c5f  jmp     short loc_140004CD5
0x140004c61  cmp     ecx, 8007050Ch
0x140004c67  jz      short loc_140004CD0
0x140004c69  cmp     ecx, 8007054Fh
0x140004c6f  jz      short loc_140004CC9
0x140004c71  cmp     ecx, 800705B9h
0x140004c77  jz      short loc_140004CC2
0x140004c79  test    ecx, ecx
0x140004c7b  jz      short loc_140004CBE
0x140004c7d  bt      ecx, 1Ch
0x140004c81  jnb     short loc_140004C89
0x140004c83  btr     ecx, 1Ch
0x140004c87  jmp     short loc_140004CD5
0x140004c89  mov     eax, ecx
0x140004c8b  and     eax, 1FFF0000h
0x140004c90  cmp     eax, 70000h
0x140004c95  jnz     short loc_140004CA8
0x140004c97  movzx   ecx, cx
0x140004c9a  mov     eax, ecx
0x140004c9c  or      eax, 0C0070000h
0x140004ca1  test    ecx, ecx
0x140004ca3  cmovnz  ecx, eax
0x140004ca6  jmp     short loc_140004CD5
0x140004ca8  cmp     eax, 90000h
0x140004cad  jnz     short loc_140004CC9
0x140004caf  test    ecx, ecx
0x140004cb1  jle     short loc_140004CD5
0x140004cb3  movzx   ecx, cx
0x140004cb6  or      ecx, 0C0090000h
0x140004cbc  jmp     short loc_140004CD5
0x140004cbe  xor     ecx, ecx
0x140004cc0  jmp     short loc_140004CD5
0x140004cc2  mov     ecx, 0C000A083h
0x140004cc7  jmp     short loc_140004CD5
0x140004cc9  mov     ecx, 0C00000E5h
0x140004cce  jmp     short loc_140004CD5
0x140004cd0  mov     ecx, 0C000042Bh
0x140004cd5  mov     eax, ecx
0x140004cd7  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140004a24`
- end: `0x140004be0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ca4`
- `0x140002d54`
- `0x140002dac`
- `0x140002e74`
- `0x1400040b8`
- `0x140004be8`
- `0x1400052f0`
- `0x140007690`
- `0x14000e46e`
- `0x14000e4d9`
- `0x14000e5a2`
- `0x14000e60d`

## callees

- `0x140004a24`

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
0x140004a24  mov     eax, 800700EAh
0x140004a29  cmp     ecx, eax
0x140004a2b  jg      loc_140004B00
0x140004a31  jz      loc_140004AF6
0x140004a37  mov     eax, 80070057h
0x140004a3c  cmp     ecx, eax
0x140004a3e  jg      short loc_140004AAA
0x140004a40  jz      short loc_140004AA0
0x140004a42  cmp     ecx, 80004005h
0x140004a48  jz      short loc_140004A96
0x140004a4a  cmp     ecx, 80070001h
0x140004a50  jz      short loc_140004A8C
0x140004a52  cmp     ecx, 80070002h
0x140004a58  jz      short loc_140004A82
0x140004a5a  cmp     ecx, 80070003h
0x140004a60  jz      short loc_140004A78
0x140004a62  cmp     ecx, 8007000Eh
0x140004a68  jnz     loc_140004B85
0x140004a6e  mov     ecx, 0C0000017h
0x140004a73  jmp     loc_140004BDD
0x140004a78  mov     ecx, 0C000003Ah
0x140004a7d  jmp     loc_140004BDD
0x140004a82  mov     ecx, 0C0000034h
0x140004a87  jmp     loc_140004BDD
0x140004a8c  mov     ecx, 0C0000002h
0x140004a91  jmp     loc_140004BDD
0x140004a96  mov     ecx, 0C0000001h
0x140004a9b  jmp     loc_140004BDD
0x140004aa0  mov     ecx, 0C000000Dh
0x140004aa5  jmp     loc_140004BDD
0x140004aaa  cmp     ecx, 80070070h
0x140004ab0  jz      short loc_140004AEC
0x140004ab2  cmp     ecx, 8007007Ah
0x140004ab8  jz      short loc_140004AE2
0x140004aba  cmp     ecx, 8007007Bh
0x140004ac0  jz      short loc_140004AD8
0x140004ac2  cmp     ecx, 8007007Eh
0x140004ac8  jnz     loc_140004B85
0x140004ace  mov     ecx, 0C0000135h
0x140004ad3  jmp     loc_140004BDD
0x140004ad8  mov     ecx, 0C0000033h
0x140004add  jmp     loc_140004BDD
0x140004ae2  mov     ecx, 0C0000023h
0x140004ae7  jmp     loc_140004BDD
0x140004aec  mov     ecx, 0C000007Fh
0x140004af1  jmp     loc_140004BDD
0x140004af6  mov     ecx, 80000005h
0x140004afb  jmp     loc_140004BDD
0x140004b00  mov     eax, 8007047Eh
0x140004b05  cmp     ecx, eax
0x140004b07  jg      short loc_140004B69
0x140004b09  jz      short loc_140004B62
0x140004b0b  cmp     ecx, 80070216h
0x140004b11  jz      short loc_140004B5B
0x140004b13  cmp     ecx, 8007023Eh
0x140004b19  jz      short loc_140004B51
0x140004b1b  cmp     ecx, 80070246h
0x140004b21  jz      short loc_140004B47
0x140004b23  cmp     ecx, 80070247h
0x140004b29  jz      short loc_140004B3D
0x140004b2b  cmp     ecx, 80070272h
0x140004b31  jnz     short loc_140004B85
0x140004b33  mov     ecx, 0C0000273h
0x140004b38  jmp     loc_140004BDD
0x140004b3d  mov     ecx, 0C0000163h
0x140004b42  jmp     loc_140004BDD
0x140004b47  mov     ecx, 0C0000161h
0x140004b4c  jmp     loc_140004BDD
0x140004b51  mov     ecx, 0C0000025h
0x140004b56  jmp     loc_140004BDD
0x140004b5b  mov     ecx, 0C0000095h
0x140004b60  jmp     short loc_140004BDD
0x140004b62  mov     ecx, 0C0000059h
0x140004b67  jmp     short loc_140004BDD
0x140004b69  cmp     ecx, 8007050Ch
0x140004b6f  jz      short loc_140004BD8
0x140004b71  cmp     ecx, 8007054Fh
0x140004b77  jz      short loc_140004BD1
0x140004b79  cmp     ecx, 800705B9h
0x140004b7f  jz      short loc_140004BCA
0x140004b81  test    ecx, ecx
0x140004b83  jz      short loc_140004BC6
0x140004b85  bt      ecx, 1Ch
0x140004b89  jnb     short loc_140004B91
0x140004b8b  btr     ecx, 1Ch
0x140004b8f  jmp     short loc_140004BDD
0x140004b91  mov     eax, ecx
0x140004b93  and     eax, 1FFF0000h
0x140004b98  cmp     eax, 70000h
0x140004b9d  jnz     short loc_140004BB0
0x140004b9f  movzx   ecx, cx
0x140004ba2  mov     eax, ecx
0x140004ba4  or      eax, 0C0070000h
0x140004ba9  test    ecx, ecx
0x140004bab  cmovnz  ecx, eax
0x140004bae  jmp     short loc_140004BDD
0x140004bb0  cmp     eax, 90000h
0x140004bb5  jnz     short loc_140004BD1
0x140004bb7  test    ecx, ecx
0x140004bb9  jle     short loc_140004BDD
0x140004bbb  movzx   ecx, cx
0x140004bbe  or      ecx, 0C0090000h
0x140004bc4  jmp     short loc_140004BDD
0x140004bc6  xor     ecx, ecx
0x140004bc8  jmp     short loc_140004BDD
0x140004bca  mov     ecx, 0C000A083h
0x140004bcf  jmp     short loc_140004BDD
0x140004bd1  mov     ecx, 0C00000E5h
0x140004bd6  jmp     short loc_140004BDD
0x140004bd8  mov     ecx, 0C000042Bh
0x140004bdd  mov     eax, ecx
0x140004bdf  retn
```

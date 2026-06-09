# wil::details::HrToNtStatus(long)

- ea: `0x180004a8c`
- end: `0x180004c48`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024fc`
- `0x1800025a4`
- `0x1800025f4`
- `0x1800026b4`
- `0x180004168`
- `0x180004c50`

## callees

- `0x180004a8c`

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
0x180004a8c  mov     eax, 800700EAh
0x180004a91  cmp     ecx, eax
0x180004a93  jg      loc_180004B68
0x180004a99  jz      loc_180004B5E
0x180004a9f  mov     eax, 80070057h
0x180004aa4  cmp     ecx, eax
0x180004aa6  jg      short loc_180004B12
0x180004aa8  jz      short loc_180004B08
0x180004aaa  cmp     ecx, 80004005h
0x180004ab0  jz      short loc_180004AFE
0x180004ab2  cmp     ecx, 80070001h
0x180004ab8  jz      short loc_180004AF4
0x180004aba  cmp     ecx, 80070002h
0x180004ac0  jz      short loc_180004AEA
0x180004ac2  cmp     ecx, 80070003h
0x180004ac8  jz      short loc_180004AE0
0x180004aca  cmp     ecx, 8007000Eh
0x180004ad0  jnz     loc_180004BED
0x180004ad6  mov     ecx, 0C0000017h
0x180004adb  jmp     loc_180004C45
0x180004ae0  mov     ecx, 0C000003Ah
0x180004ae5  jmp     loc_180004C45
0x180004aea  mov     ecx, 0C0000034h
0x180004aef  jmp     loc_180004C45
0x180004af4  mov     ecx, 0C0000002h
0x180004af9  jmp     loc_180004C45
0x180004afe  mov     ecx, 0C0000001h
0x180004b03  jmp     loc_180004C45
0x180004b08  mov     ecx, 0C000000Dh
0x180004b0d  jmp     loc_180004C45
0x180004b12  cmp     ecx, 80070070h
0x180004b18  jz      short loc_180004B54
0x180004b1a  cmp     ecx, 8007007Ah
0x180004b20  jz      short loc_180004B4A
0x180004b22  cmp     ecx, 8007007Bh
0x180004b28  jz      short loc_180004B40
0x180004b2a  cmp     ecx, 8007007Eh
0x180004b30  jnz     loc_180004BED
0x180004b36  mov     ecx, 0C0000135h
0x180004b3b  jmp     loc_180004C45
0x180004b40  mov     ecx, 0C0000033h
0x180004b45  jmp     loc_180004C45
0x180004b4a  mov     ecx, 0C0000023h
0x180004b4f  jmp     loc_180004C45
0x180004b54  mov     ecx, 0C000007Fh
0x180004b59  jmp     loc_180004C45
0x180004b5e  mov     ecx, 80000005h
0x180004b63  jmp     loc_180004C45
0x180004b68  mov     eax, 8007047Eh
0x180004b6d  cmp     ecx, eax
0x180004b6f  jg      short loc_180004BD1
0x180004b71  jz      short loc_180004BCA
0x180004b73  cmp     ecx, 80070216h
0x180004b79  jz      short loc_180004BC3
0x180004b7b  cmp     ecx, 8007023Eh
0x180004b81  jz      short loc_180004BB9
0x180004b83  cmp     ecx, 80070246h
0x180004b89  jz      short loc_180004BAF
0x180004b8b  cmp     ecx, 80070247h
0x180004b91  jz      short loc_180004BA5
0x180004b93  cmp     ecx, 80070272h
0x180004b99  jnz     short loc_180004BED
0x180004b9b  mov     ecx, 0C0000273h
0x180004ba0  jmp     loc_180004C45
0x180004ba5  mov     ecx, 0C0000163h
0x180004baa  jmp     loc_180004C45
0x180004baf  mov     ecx, 0C0000161h
0x180004bb4  jmp     loc_180004C45
0x180004bb9  mov     ecx, 0C0000025h
0x180004bbe  jmp     loc_180004C45
0x180004bc3  mov     ecx, 0C0000095h
0x180004bc8  jmp     short loc_180004C45
0x180004bca  mov     ecx, 0C0000059h
0x180004bcf  jmp     short loc_180004C45
0x180004bd1  cmp     ecx, 8007050Ch
0x180004bd7  jz      short loc_180004C40
0x180004bd9  cmp     ecx, 8007054Fh
0x180004bdf  jz      short loc_180004C39
0x180004be1  cmp     ecx, 800705B9h
0x180004be7  jz      short loc_180004C32
0x180004be9  test    ecx, ecx
0x180004beb  jz      short loc_180004C2E
0x180004bed  bt      ecx, 1Ch
0x180004bf1  jnb     short loc_180004BF9
0x180004bf3  btr     ecx, 1Ch
0x180004bf7  jmp     short loc_180004C45
0x180004bf9  mov     eax, ecx
0x180004bfb  and     eax, 1FFF0000h
0x180004c00  cmp     eax, 70000h
0x180004c05  jnz     short loc_180004C18
0x180004c07  movzx   ecx, cx
0x180004c0a  mov     eax, ecx
0x180004c0c  or      eax, 0C0070000h
0x180004c11  test    ecx, ecx
0x180004c13  cmovnz  ecx, eax
0x180004c16  jmp     short loc_180004C45
0x180004c18  cmp     eax, 90000h
0x180004c1d  jnz     short loc_180004C39
0x180004c1f  test    ecx, ecx
0x180004c21  jle     short loc_180004C45
0x180004c23  movzx   ecx, cx
0x180004c26  or      ecx, 0C0090000h
0x180004c2c  jmp     short loc_180004C45
0x180004c2e  xor     ecx, ecx
0x180004c30  jmp     short loc_180004C45
0x180004c32  mov     ecx, 0C000A083h
0x180004c37  jmp     short loc_180004C45
0x180004c39  mov     ecx, 0C00000E5h
0x180004c3e  jmp     short loc_180004C45
0x180004c40  mov     ecx, 0C000042Bh
0x180004c45  mov     eax, ecx
0x180004c47  retn
```

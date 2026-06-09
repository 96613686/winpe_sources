# wil::details::HrToNtStatus(long)

- ea: `0x180008f00`
- end: `0x1800090bc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003698`
- `0x180003864`
- `0x180003914`
- `0x180003974`
- `0x180003a3c`
- `0x18000434c`
- `0x180007d68`
- `0x1800092b0`
- `0x18000bdc0`
- `0x1800105d1`
- `0x18001063c`
- `0x180010705`
- `0x180010770`

## callees

- `0x180008f00`

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
0x180008f00  mov     eax, 800700EAh
0x180008f05  cmp     ecx, eax
0x180008f07  jg      loc_180008FDC
0x180008f0d  jz      loc_180008FD2
0x180008f13  mov     eax, 80070057h
0x180008f18  cmp     ecx, eax
0x180008f1a  jg      short loc_180008F86
0x180008f1c  jz      short loc_180008F7C
0x180008f1e  cmp     ecx, 80004005h
0x180008f24  jz      short loc_180008F72
0x180008f26  cmp     ecx, 80070001h
0x180008f2c  jz      short loc_180008F68
0x180008f2e  cmp     ecx, 80070002h
0x180008f34  jz      short loc_180008F5E
0x180008f36  cmp     ecx, 80070003h
0x180008f3c  jz      short loc_180008F54
0x180008f3e  cmp     ecx, 8007000Eh
0x180008f44  jnz     loc_180009061
0x180008f4a  mov     ecx, 0C0000017h
0x180008f4f  jmp     loc_1800090B9
0x180008f54  mov     ecx, 0C000003Ah
0x180008f59  jmp     loc_1800090B9
0x180008f5e  mov     ecx, 0C0000034h
0x180008f63  jmp     loc_1800090B9
0x180008f68  mov     ecx, 0C0000002h
0x180008f6d  jmp     loc_1800090B9
0x180008f72  mov     ecx, 0C0000001h
0x180008f77  jmp     loc_1800090B9
0x180008f7c  mov     ecx, 0C000000Dh
0x180008f81  jmp     loc_1800090B9
0x180008f86  cmp     ecx, 80070070h
0x180008f8c  jz      short loc_180008FC8
0x180008f8e  cmp     ecx, 8007007Ah
0x180008f94  jz      short loc_180008FBE
0x180008f96  cmp     ecx, 8007007Bh
0x180008f9c  jz      short loc_180008FB4
0x180008f9e  cmp     ecx, 8007007Eh
0x180008fa4  jnz     loc_180009061
0x180008faa  mov     ecx, 0C0000135h
0x180008faf  jmp     loc_1800090B9
0x180008fb4  mov     ecx, 0C0000033h
0x180008fb9  jmp     loc_1800090B9
0x180008fbe  mov     ecx, 0C0000023h
0x180008fc3  jmp     loc_1800090B9
0x180008fc8  mov     ecx, 0C000007Fh
0x180008fcd  jmp     loc_1800090B9
0x180008fd2  mov     ecx, 80000005h
0x180008fd7  jmp     loc_1800090B9
0x180008fdc  mov     eax, 8007047Eh
0x180008fe1  cmp     ecx, eax
0x180008fe3  jg      short loc_180009045
0x180008fe5  jz      short loc_18000903E
0x180008fe7  cmp     ecx, 80070216h
0x180008fed  jz      short loc_180009037
0x180008fef  cmp     ecx, 8007023Eh
0x180008ff5  jz      short loc_18000902D
0x180008ff7  cmp     ecx, 80070246h
0x180008ffd  jz      short loc_180009023
0x180008fff  cmp     ecx, 80070247h
0x180009005  jz      short loc_180009019
0x180009007  cmp     ecx, 80070272h
0x18000900d  jnz     short loc_180009061
0x18000900f  mov     ecx, 0C0000273h
0x180009014  jmp     loc_1800090B9
0x180009019  mov     ecx, 0C0000163h
0x18000901e  jmp     loc_1800090B9
0x180009023  mov     ecx, 0C0000161h
0x180009028  jmp     loc_1800090B9
0x18000902d  mov     ecx, 0C0000025h
0x180009032  jmp     loc_1800090B9
0x180009037  mov     ecx, 0C0000095h
0x18000903c  jmp     short loc_1800090B9
0x18000903e  mov     ecx, 0C0000059h
0x180009043  jmp     short loc_1800090B9
0x180009045  cmp     ecx, 8007050Ch
0x18000904b  jz      short loc_1800090B4
0x18000904d  cmp     ecx, 8007054Fh
0x180009053  jz      short loc_1800090AD
0x180009055  cmp     ecx, 800705B9h
0x18000905b  jz      short loc_1800090A6
0x18000905d  test    ecx, ecx
0x18000905f  jz      short loc_1800090A2
0x180009061  bt      ecx, 1Ch
0x180009065  jnb     short loc_18000906D
0x180009067  btr     ecx, 1Ch
0x18000906b  jmp     short loc_1800090B9
0x18000906d  mov     eax, ecx
0x18000906f  and     eax, 1FFF0000h
0x180009074  cmp     eax, 70000h
0x180009079  jnz     short loc_18000908C
0x18000907b  movzx   ecx, cx
0x18000907e  mov     eax, ecx
0x180009080  or      eax, 0C0070000h
0x180009085  test    ecx, ecx
0x180009087  cmovnz  ecx, eax
0x18000908a  jmp     short loc_1800090B9
0x18000908c  cmp     eax, 90000h
0x180009091  jnz     short loc_1800090AD
0x180009093  test    ecx, ecx
0x180009095  jle     short loc_1800090B9
0x180009097  movzx   ecx, cx
0x18000909a  or      ecx, 0C0090000h
0x1800090a0  jmp     short loc_1800090B9
0x1800090a2  xor     ecx, ecx
0x1800090a4  jmp     short loc_1800090B9
0x1800090a6  mov     ecx, 0C000A083h
0x1800090ab  jmp     short loc_1800090B9
0x1800090ad  mov     ecx, 0C00000E5h
0x1800090b2  jmp     short loc_1800090B9
0x1800090b4  mov     ecx, 0C000042Bh
0x1800090b9  mov     eax, ecx
0x1800090bb  retn
```

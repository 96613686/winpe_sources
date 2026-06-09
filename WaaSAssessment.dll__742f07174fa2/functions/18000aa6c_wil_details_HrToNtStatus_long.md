# wil::details::HrToNtStatus(long)

- ea: `0x18000aa6c`
- end: `0x18000ac28`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a608`
- `0x18000ba28`
- `0x18000bad0`
- `0x18000bb20`
- `0x18000bbe0`
- `0x18000eac0`

## callees

- `0x18000aa6c`

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
0x18000aa6c  mov     eax, 800700EAh
0x18000aa71  cmp     ecx, eax
0x18000aa73  jg      loc_18000AB48
0x18000aa79  jz      loc_18000AB3E
0x18000aa7f  mov     eax, 80070057h
0x18000aa84  cmp     ecx, eax
0x18000aa86  jg      short loc_18000AAF2
0x18000aa88  jz      short loc_18000AAE8
0x18000aa8a  cmp     ecx, 80004005h
0x18000aa90  jz      short loc_18000AADE
0x18000aa92  cmp     ecx, 80070001h
0x18000aa98  jz      short loc_18000AAD4
0x18000aa9a  cmp     ecx, 80070002h
0x18000aaa0  jz      short loc_18000AACA
0x18000aaa2  cmp     ecx, 80070003h
0x18000aaa8  jz      short loc_18000AAC0
0x18000aaaa  cmp     ecx, 8007000Eh
0x18000aab0  jnz     loc_18000ABCD
0x18000aab6  mov     ecx, 0C0000017h
0x18000aabb  jmp     loc_18000AC25
0x18000aac0  mov     ecx, 0C000003Ah
0x18000aac5  jmp     loc_18000AC25
0x18000aaca  mov     ecx, 0C0000034h
0x18000aacf  jmp     loc_18000AC25
0x18000aad4  mov     ecx, 0C0000002h
0x18000aad9  jmp     loc_18000AC25
0x18000aade  mov     ecx, 0C0000001h
0x18000aae3  jmp     loc_18000AC25
0x18000aae8  mov     ecx, 0C000000Dh
0x18000aaed  jmp     loc_18000AC25
0x18000aaf2  cmp     ecx, 80070070h
0x18000aaf8  jz      short loc_18000AB34
0x18000aafa  cmp     ecx, 8007007Ah
0x18000ab00  jz      short loc_18000AB2A
0x18000ab02  cmp     ecx, 8007007Bh
0x18000ab08  jz      short loc_18000AB20
0x18000ab0a  cmp     ecx, 8007007Eh
0x18000ab10  jnz     loc_18000ABCD
0x18000ab16  mov     ecx, 0C0000135h
0x18000ab1b  jmp     loc_18000AC25
0x18000ab20  mov     ecx, 0C0000033h
0x18000ab25  jmp     loc_18000AC25
0x18000ab2a  mov     ecx, 0C0000023h
0x18000ab2f  jmp     loc_18000AC25
0x18000ab34  mov     ecx, 0C000007Fh
0x18000ab39  jmp     loc_18000AC25
0x18000ab3e  mov     ecx, 80000005h
0x18000ab43  jmp     loc_18000AC25
0x18000ab48  mov     eax, 8007047Eh
0x18000ab4d  cmp     ecx, eax
0x18000ab4f  jg      short loc_18000ABB1
0x18000ab51  jz      short loc_18000ABAA
0x18000ab53  cmp     ecx, 80070216h
0x18000ab59  jz      short loc_18000ABA3
0x18000ab5b  cmp     ecx, 8007023Eh
0x18000ab61  jz      short loc_18000AB99
0x18000ab63  cmp     ecx, 80070246h
0x18000ab69  jz      short loc_18000AB8F
0x18000ab6b  cmp     ecx, 80070247h
0x18000ab71  jz      short loc_18000AB85
0x18000ab73  cmp     ecx, 80070272h
0x18000ab79  jnz     short loc_18000ABCD
0x18000ab7b  mov     ecx, 0C0000273h
0x18000ab80  jmp     loc_18000AC25
0x18000ab85  mov     ecx, 0C0000163h
0x18000ab8a  jmp     loc_18000AC25
0x18000ab8f  mov     ecx, 0C0000161h
0x18000ab94  jmp     loc_18000AC25
0x18000ab99  mov     ecx, 0C0000025h
0x18000ab9e  jmp     loc_18000AC25
0x18000aba3  mov     ecx, 0C0000095h
0x18000aba8  jmp     short loc_18000AC25
0x18000abaa  mov     ecx, 0C0000059h
0x18000abaf  jmp     short loc_18000AC25
0x18000abb1  cmp     ecx, 8007050Ch
0x18000abb7  jz      short loc_18000AC20
0x18000abb9  cmp     ecx, 8007054Fh
0x18000abbf  jz      short loc_18000AC19
0x18000abc1  cmp     ecx, 800705B9h
0x18000abc7  jz      short loc_18000AC12
0x18000abc9  test    ecx, ecx
0x18000abcb  jz      short loc_18000AC0E
0x18000abcd  bt      ecx, 1Ch
0x18000abd1  jnb     short loc_18000ABD9
0x18000abd3  btr     ecx, 1Ch
0x18000abd7  jmp     short loc_18000AC25
0x18000abd9  mov     eax, ecx
0x18000abdb  and     eax, 1FFF0000h
0x18000abe0  cmp     eax, 70000h
0x18000abe5  jnz     short loc_18000ABF8
0x18000abe7  movzx   ecx, cx
0x18000abea  mov     eax, ecx
0x18000abec  or      eax, 0C0070000h
0x18000abf1  test    ecx, ecx
0x18000abf3  cmovnz  ecx, eax
0x18000abf6  jmp     short loc_18000AC25
0x18000abf8  cmp     eax, 90000h
0x18000abfd  jnz     short loc_18000AC19
0x18000abff  test    ecx, ecx
0x18000ac01  jle     short loc_18000AC25
0x18000ac03  movzx   ecx, cx
0x18000ac06  or      ecx, 0C0090000h
0x18000ac0c  jmp     short loc_18000AC25
0x18000ac0e  xor     ecx, ecx
0x18000ac10  jmp     short loc_18000AC25
0x18000ac12  mov     ecx, 0C000A083h
0x18000ac17  jmp     short loc_18000AC25
0x18000ac19  mov     ecx, 0C00000E5h
0x18000ac1e  jmp     short loc_18000AC25
0x18000ac20  mov     ecx, 0C000042Bh
0x18000ac25  mov     eax, ecx
0x18000ac27  retn
```

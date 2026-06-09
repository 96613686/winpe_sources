# wil::details::HrToNtStatus(long)

- ea: `0x180003ff8`
- end: `0x1800041b4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002918`
- `0x180002990`
- `0x180002a08`
- `0x180002a58`
- `0x180002abc`
- `0x1800041bc`
- `0x180004a10`
- `0x180005ee0`
- `0x180005f34`
- `0x180007c9c`
- `0x18000a468`
- `0x18000f0c8`
- `0x18000f113`
- `0x18000f1d6`
- `0x18000f221`

## callees

- `0x180003ff8`

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
0x180003ff8  mov     eax, 800700EAh
0x180003ffd  cmp     ecx, eax
0x180003fff  jg      loc_1800040D4
0x180004005  jz      loc_1800040CA
0x18000400b  mov     eax, 80070057h
0x180004010  cmp     ecx, eax
0x180004012  jg      short loc_18000407E
0x180004014  jz      short loc_180004074
0x180004016  cmp     ecx, 80004005h
0x18000401c  jz      short loc_18000406A
0x18000401e  cmp     ecx, 80070001h
0x180004024  jz      short loc_180004060
0x180004026  cmp     ecx, 80070002h
0x18000402c  jz      short loc_180004056
0x18000402e  cmp     ecx, 80070003h
0x180004034  jz      short loc_18000404C
0x180004036  cmp     ecx, 8007000Eh
0x18000403c  jnz     loc_180004159
0x180004042  mov     ecx, 0C0000017h
0x180004047  jmp     loc_1800041B1
0x18000404c  mov     ecx, 0C000003Ah
0x180004051  jmp     loc_1800041B1
0x180004056  mov     ecx, 0C0000034h
0x18000405b  jmp     loc_1800041B1
0x180004060  mov     ecx, 0C0000002h
0x180004065  jmp     loc_1800041B1
0x18000406a  mov     ecx, 0C0000001h
0x18000406f  jmp     loc_1800041B1
0x180004074  mov     ecx, 0C000000Dh
0x180004079  jmp     loc_1800041B1
0x18000407e  cmp     ecx, 80070070h
0x180004084  jz      short loc_1800040C0
0x180004086  cmp     ecx, 8007007Ah
0x18000408c  jz      short loc_1800040B6
0x18000408e  cmp     ecx, 8007007Bh
0x180004094  jz      short loc_1800040AC
0x180004096  cmp     ecx, 8007007Eh
0x18000409c  jnz     loc_180004159
0x1800040a2  mov     ecx, 0C0000135h
0x1800040a7  jmp     loc_1800041B1
0x1800040ac  mov     ecx, 0C0000033h
0x1800040b1  jmp     loc_1800041B1
0x1800040b6  mov     ecx, 0C0000023h
0x1800040bb  jmp     loc_1800041B1
0x1800040c0  mov     ecx, 0C000007Fh
0x1800040c5  jmp     loc_1800041B1
0x1800040ca  mov     ecx, 80000005h
0x1800040cf  jmp     loc_1800041B1
0x1800040d4  mov     eax, 8007047Eh
0x1800040d9  cmp     ecx, eax
0x1800040db  jg      short loc_18000413D
0x1800040dd  jz      short loc_180004136
0x1800040df  cmp     ecx, 80070216h
0x1800040e5  jz      short loc_18000412F
0x1800040e7  cmp     ecx, 8007023Eh
0x1800040ed  jz      short loc_180004125
0x1800040ef  cmp     ecx, 80070246h
0x1800040f5  jz      short loc_18000411B
0x1800040f7  cmp     ecx, 80070247h
0x1800040fd  jz      short loc_180004111
0x1800040ff  cmp     ecx, 80070272h
0x180004105  jnz     short loc_180004159
0x180004107  mov     ecx, 0C0000273h
0x18000410c  jmp     loc_1800041B1
0x180004111  mov     ecx, 0C0000163h
0x180004116  jmp     loc_1800041B1
0x18000411b  mov     ecx, 0C0000161h
0x180004120  jmp     loc_1800041B1
0x180004125  mov     ecx, 0C0000025h
0x18000412a  jmp     loc_1800041B1
0x18000412f  mov     ecx, 0C0000095h
0x180004134  jmp     short loc_1800041B1
0x180004136  mov     ecx, 0C0000059h
0x18000413b  jmp     short loc_1800041B1
0x18000413d  cmp     ecx, 8007050Ch
0x180004143  jz      short loc_1800041AC
0x180004145  cmp     ecx, 8007054Fh
0x18000414b  jz      short loc_1800041A5
0x18000414d  cmp     ecx, 800705B9h
0x180004153  jz      short loc_18000419E
0x180004155  test    ecx, ecx
0x180004157  jz      short loc_18000419A
0x180004159  bt      ecx, 1Ch
0x18000415d  jnb     short loc_180004165
0x18000415f  btr     ecx, 1Ch
0x180004163  jmp     short loc_1800041B1
0x180004165  mov     eax, ecx
0x180004167  and     eax, 1FFF0000h
0x18000416c  cmp     eax, 70000h
0x180004171  jnz     short loc_180004184
0x180004173  movzx   ecx, cx
0x180004176  mov     eax, ecx
0x180004178  or      eax, 0C0070000h
0x18000417d  test    ecx, ecx
0x18000417f  cmovnz  ecx, eax
0x180004182  jmp     short loc_1800041B1
0x180004184  cmp     eax, 90000h
0x180004189  jnz     short loc_1800041A5
0x18000418b  test    ecx, ecx
0x18000418d  jle     short loc_1800041B1
0x18000418f  movzx   ecx, cx
0x180004192  or      ecx, 0C0090000h
0x180004198  jmp     short loc_1800041B1
0x18000419a  xor     ecx, ecx
0x18000419c  jmp     short loc_1800041B1
0x18000419e  mov     ecx, 0C000A083h
0x1800041a3  jmp     short loc_1800041B1
0x1800041a5  mov     ecx, 0C00000E5h
0x1800041aa  jmp     short loc_1800041B1
0x1800041ac  mov     ecx, 0C000042Bh
0x1800041b1  mov     eax, ecx
0x1800041b3  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x1800040f4`
- end: `0x1800042b0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002384`
- `0x180002434`
- `0x18000248c`
- `0x180002554`
- `0x1800036c8`
- `0x1800042b8`
- `0x180004a40`
- `0x180006b50`
- `0x18000a1e0`
- `0x18000a24b`
- `0x18000a314`
- `0x18000a37f`

## callees

- `0x1800040f4`

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
0x1800040f4  mov     eax, 800700EAh
0x1800040f9  cmp     ecx, eax
0x1800040fb  jg      loc_1800041D0
0x180004101  jz      loc_1800041C6
0x180004107  mov     eax, 80070057h
0x18000410c  cmp     ecx, eax
0x18000410e  jg      short loc_18000417A
0x180004110  jz      short loc_180004170
0x180004112  cmp     ecx, 80004005h
0x180004118  jz      short loc_180004166
0x18000411a  cmp     ecx, 80070001h
0x180004120  jz      short loc_18000415C
0x180004122  cmp     ecx, 80070002h
0x180004128  jz      short loc_180004152
0x18000412a  cmp     ecx, 80070003h
0x180004130  jz      short loc_180004148
0x180004132  cmp     ecx, 8007000Eh
0x180004138  jnz     loc_180004255
0x18000413e  mov     ecx, 0C0000017h
0x180004143  jmp     loc_1800042AD
0x180004148  mov     ecx, 0C000003Ah
0x18000414d  jmp     loc_1800042AD
0x180004152  mov     ecx, 0C0000034h
0x180004157  jmp     loc_1800042AD
0x18000415c  mov     ecx, 0C0000002h
0x180004161  jmp     loc_1800042AD
0x180004166  mov     ecx, 0C0000001h
0x18000416b  jmp     loc_1800042AD
0x180004170  mov     ecx, 0C000000Dh
0x180004175  jmp     loc_1800042AD
0x18000417a  cmp     ecx, 80070070h
0x180004180  jz      short loc_1800041BC
0x180004182  cmp     ecx, 8007007Ah
0x180004188  jz      short loc_1800041B2
0x18000418a  cmp     ecx, 8007007Bh
0x180004190  jz      short loc_1800041A8
0x180004192  cmp     ecx, 8007007Eh
0x180004198  jnz     loc_180004255
0x18000419e  mov     ecx, 0C0000135h
0x1800041a3  jmp     loc_1800042AD
0x1800041a8  mov     ecx, 0C0000033h
0x1800041ad  jmp     loc_1800042AD
0x1800041b2  mov     ecx, 0C0000023h
0x1800041b7  jmp     loc_1800042AD
0x1800041bc  mov     ecx, 0C000007Fh
0x1800041c1  jmp     loc_1800042AD
0x1800041c6  mov     ecx, 80000005h
0x1800041cb  jmp     loc_1800042AD
0x1800041d0  mov     eax, 8007047Eh
0x1800041d5  cmp     ecx, eax
0x1800041d7  jg      short loc_180004239
0x1800041d9  jz      short loc_180004232
0x1800041db  cmp     ecx, 80070216h
0x1800041e1  jz      short loc_18000422B
0x1800041e3  cmp     ecx, 8007023Eh
0x1800041e9  jz      short loc_180004221
0x1800041eb  cmp     ecx, 80070246h
0x1800041f1  jz      short loc_180004217
0x1800041f3  cmp     ecx, 80070247h
0x1800041f9  jz      short loc_18000420D
0x1800041fb  cmp     ecx, 80070272h
0x180004201  jnz     short loc_180004255
0x180004203  mov     ecx, 0C0000273h
0x180004208  jmp     loc_1800042AD
0x18000420d  mov     ecx, 0C0000163h
0x180004212  jmp     loc_1800042AD
0x180004217  mov     ecx, 0C0000161h
0x18000421c  jmp     loc_1800042AD
0x180004221  mov     ecx, 0C0000025h
0x180004226  jmp     loc_1800042AD
0x18000422b  mov     ecx, 0C0000095h
0x180004230  jmp     short loc_1800042AD
0x180004232  mov     ecx, 0C0000059h
0x180004237  jmp     short loc_1800042AD
0x180004239  cmp     ecx, 8007050Ch
0x18000423f  jz      short loc_1800042A8
0x180004241  cmp     ecx, 8007054Fh
0x180004247  jz      short loc_1800042A1
0x180004249  cmp     ecx, 800705B9h
0x18000424f  jz      short loc_18000429A
0x180004251  test    ecx, ecx
0x180004253  jz      short loc_180004296
0x180004255  bt      ecx, 1Ch
0x180004259  jnb     short loc_180004261
0x18000425b  btr     ecx, 1Ch
0x18000425f  jmp     short loc_1800042AD
0x180004261  mov     eax, ecx
0x180004263  and     eax, 1FFF0000h
0x180004268  cmp     eax, 70000h
0x18000426d  jnz     short loc_180004280
0x18000426f  movzx   ecx, cx
0x180004272  mov     eax, ecx
0x180004274  or      eax, 0C0070000h
0x180004279  test    ecx, ecx
0x18000427b  cmovnz  ecx, eax
0x18000427e  jmp     short loc_1800042AD
0x180004280  cmp     eax, 90000h
0x180004285  jnz     short loc_1800042A1
0x180004287  test    ecx, ecx
0x180004289  jle     short loc_1800042AD
0x18000428b  movzx   ecx, cx
0x18000428e  or      ecx, 0C0090000h
0x180004294  jmp     short loc_1800042AD
0x180004296  xor     ecx, ecx
0x180004298  jmp     short loc_1800042AD
0x18000429a  mov     ecx, 0C000A083h
0x18000429f  jmp     short loc_1800042AD
0x1800042a1  mov     ecx, 0C00000E5h
0x1800042a6  jmp     short loc_1800042AD
0x1800042a8  mov     ecx, 0C000042Bh
0x1800042ad  mov     eax, ecx
0x1800042af  retn
```

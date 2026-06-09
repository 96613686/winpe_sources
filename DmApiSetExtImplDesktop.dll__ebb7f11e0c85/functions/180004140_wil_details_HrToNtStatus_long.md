# wil::details::HrToNtStatus(long)

- ea: `0x180004140`
- end: `0x1800042fc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000237c`
- `0x180002470`
- `0x1800024f0`
- `0x180002578`
- `0x1800025d0`
- `0x180003738`
- `0x180004334`
- `0x180004c10`
- `0x18000a43a`
- `0x18000a485`
- `0x18000a548`
- `0x18000a593`

## callees

- `0x180004140`

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
0x180004140  mov     eax, 800700EAh
0x180004145  cmp     ecx, eax
0x180004147  jg      loc_18000421C
0x18000414d  jz      loc_180004212
0x180004153  mov     eax, 80070057h
0x180004158  cmp     ecx, eax
0x18000415a  jg      short loc_1800041C6
0x18000415c  jz      short loc_1800041BC
0x18000415e  cmp     ecx, 80004005h
0x180004164  jz      short loc_1800041B2
0x180004166  cmp     ecx, 80070001h
0x18000416c  jz      short loc_1800041A8
0x18000416e  cmp     ecx, 80070002h
0x180004174  jz      short loc_18000419E
0x180004176  cmp     ecx, 80070003h
0x18000417c  jz      short loc_180004194
0x18000417e  cmp     ecx, 8007000Eh
0x180004184  jnz     loc_1800042A1
0x18000418a  mov     ecx, 0C0000017h
0x18000418f  jmp     loc_1800042F9
0x180004194  mov     ecx, 0C000003Ah
0x180004199  jmp     loc_1800042F9
0x18000419e  mov     ecx, 0C0000034h
0x1800041a3  jmp     loc_1800042F9
0x1800041a8  mov     ecx, 0C0000002h
0x1800041ad  jmp     loc_1800042F9
0x1800041b2  mov     ecx, 0C0000001h
0x1800041b7  jmp     loc_1800042F9
0x1800041bc  mov     ecx, 0C000000Dh
0x1800041c1  jmp     loc_1800042F9
0x1800041c6  cmp     ecx, 80070070h
0x1800041cc  jz      short loc_180004208
0x1800041ce  cmp     ecx, 8007007Ah
0x1800041d4  jz      short loc_1800041FE
0x1800041d6  cmp     ecx, 8007007Bh
0x1800041dc  jz      short loc_1800041F4
0x1800041de  cmp     ecx, 8007007Eh
0x1800041e4  jnz     loc_1800042A1
0x1800041ea  mov     ecx, 0C0000135h
0x1800041ef  jmp     loc_1800042F9
0x1800041f4  mov     ecx, 0C0000033h
0x1800041f9  jmp     loc_1800042F9
0x1800041fe  mov     ecx, 0C0000023h
0x180004203  jmp     loc_1800042F9
0x180004208  mov     ecx, 0C000007Fh
0x18000420d  jmp     loc_1800042F9
0x180004212  mov     ecx, 80000005h
0x180004217  jmp     loc_1800042F9
0x18000421c  mov     eax, 8007047Eh
0x180004221  cmp     ecx, eax
0x180004223  jg      short loc_180004285
0x180004225  jz      short loc_18000427E
0x180004227  cmp     ecx, 80070216h
0x18000422d  jz      short loc_180004277
0x18000422f  cmp     ecx, 8007023Eh
0x180004235  jz      short loc_18000426D
0x180004237  cmp     ecx, 80070246h
0x18000423d  jz      short loc_180004263
0x18000423f  cmp     ecx, 80070247h
0x180004245  jz      short loc_180004259
0x180004247  cmp     ecx, 80070272h
0x18000424d  jnz     short loc_1800042A1
0x18000424f  mov     ecx, 0C0000273h
0x180004254  jmp     loc_1800042F9
0x180004259  mov     ecx, 0C0000163h
0x18000425e  jmp     loc_1800042F9
0x180004263  mov     ecx, 0C0000161h
0x180004268  jmp     loc_1800042F9
0x18000426d  mov     ecx, 0C0000025h
0x180004272  jmp     loc_1800042F9
0x180004277  mov     ecx, 0C0000095h
0x18000427c  jmp     short loc_1800042F9
0x18000427e  mov     ecx, 0C0000059h
0x180004283  jmp     short loc_1800042F9
0x180004285  cmp     ecx, 8007050Ch
0x18000428b  jz      short loc_1800042F4
0x18000428d  cmp     ecx, 8007054Fh
0x180004293  jz      short loc_1800042ED
0x180004295  cmp     ecx, 800705B9h
0x18000429b  jz      short loc_1800042E6
0x18000429d  test    ecx, ecx
0x18000429f  jz      short loc_1800042E2
0x1800042a1  bt      ecx, 1Ch
0x1800042a5  jnb     short loc_1800042AD
0x1800042a7  btr     ecx, 1Ch
0x1800042ab  jmp     short loc_1800042F9
0x1800042ad  mov     eax, ecx
0x1800042af  and     eax, 1FFF0000h
0x1800042b4  cmp     eax, 70000h
0x1800042b9  jnz     short loc_1800042CC
0x1800042bb  movzx   ecx, cx
0x1800042be  mov     eax, ecx
0x1800042c0  or      eax, 0C0070000h
0x1800042c5  test    ecx, ecx
0x1800042c7  cmovnz  ecx, eax
0x1800042ca  jmp     short loc_1800042F9
0x1800042cc  cmp     eax, 90000h
0x1800042d1  jnz     short loc_1800042ED
0x1800042d3  test    ecx, ecx
0x1800042d5  jle     short loc_1800042F9
0x1800042d7  movzx   ecx, cx
0x1800042da  or      ecx, 0C0090000h
0x1800042e0  jmp     short loc_1800042F9
0x1800042e2  xor     ecx, ecx
0x1800042e4  jmp     short loc_1800042F9
0x1800042e6  mov     ecx, 0C000A083h
0x1800042eb  jmp     short loc_1800042F9
0x1800042ed  mov     ecx, 0C00000E5h
0x1800042f2  jmp     short loc_1800042F9
0x1800042f4  mov     ecx, 0C000042Bh
0x1800042f9  mov     eax, ecx
0x1800042fb  retn
```

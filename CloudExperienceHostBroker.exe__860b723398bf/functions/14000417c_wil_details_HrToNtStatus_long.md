# wil::details::HrToNtStatus(long)

- ea: `0x14000417c`
- end: `0x140004338`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002834`
- `0x1400028b4`
- `0x14000293c`
- `0x140002994`
- `0x1400037f8`
- `0x14000436c`
- `0x140004bb0`
- `0x140006f00`
- `0x140009758`
- `0x1400097a3`
- `0x140009866`
- `0x1400098b1`

## callees

- `0x14000417c`

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
0x14000417c  mov     eax, 800700EAh
0x140004181  cmp     ecx, eax
0x140004183  jg      loc_140004258
0x140004189  jz      loc_14000424E
0x14000418f  mov     eax, 80070057h
0x140004194  cmp     ecx, eax
0x140004196  jg      short loc_140004202
0x140004198  jz      short loc_1400041F8
0x14000419a  cmp     ecx, 80004005h
0x1400041a0  jz      short loc_1400041EE
0x1400041a2  cmp     ecx, 80070001h
0x1400041a8  jz      short loc_1400041E4
0x1400041aa  cmp     ecx, 80070002h
0x1400041b0  jz      short loc_1400041DA
0x1400041b2  cmp     ecx, 80070003h
0x1400041b8  jz      short loc_1400041D0
0x1400041ba  cmp     ecx, 8007000Eh
0x1400041c0  jnz     loc_1400042DD
0x1400041c6  mov     ecx, 0C0000017h
0x1400041cb  jmp     loc_140004335
0x1400041d0  mov     ecx, 0C000003Ah
0x1400041d5  jmp     loc_140004335
0x1400041da  mov     ecx, 0C0000034h
0x1400041df  jmp     loc_140004335
0x1400041e4  mov     ecx, 0C0000002h
0x1400041e9  jmp     loc_140004335
0x1400041ee  mov     ecx, 0C0000001h
0x1400041f3  jmp     loc_140004335
0x1400041f8  mov     ecx, 0C000000Dh
0x1400041fd  jmp     loc_140004335
0x140004202  cmp     ecx, 80070070h
0x140004208  jz      short loc_140004244
0x14000420a  cmp     ecx, 8007007Ah
0x140004210  jz      short loc_14000423A
0x140004212  cmp     ecx, 8007007Bh
0x140004218  jz      short loc_140004230
0x14000421a  cmp     ecx, 8007007Eh
0x140004220  jnz     loc_1400042DD
0x140004226  mov     ecx, 0C0000135h
0x14000422b  jmp     loc_140004335
0x140004230  mov     ecx, 0C0000033h
0x140004235  jmp     loc_140004335
0x14000423a  mov     ecx, 0C0000023h
0x14000423f  jmp     loc_140004335
0x140004244  mov     ecx, 0C000007Fh
0x140004249  jmp     loc_140004335
0x14000424e  mov     ecx, 80000005h
0x140004253  jmp     loc_140004335
0x140004258  mov     eax, 8007047Eh
0x14000425d  cmp     ecx, eax
0x14000425f  jg      short loc_1400042C1
0x140004261  jz      short loc_1400042BA
0x140004263  cmp     ecx, 80070216h
0x140004269  jz      short loc_1400042B3
0x14000426b  cmp     ecx, 8007023Eh
0x140004271  jz      short loc_1400042A9
0x140004273  cmp     ecx, 80070246h
0x140004279  jz      short loc_14000429F
0x14000427b  cmp     ecx, 80070247h
0x140004281  jz      short loc_140004295
0x140004283  cmp     ecx, 80070272h
0x140004289  jnz     short loc_1400042DD
0x14000428b  mov     ecx, 0C0000273h
0x140004290  jmp     loc_140004335
0x140004295  mov     ecx, 0C0000163h
0x14000429a  jmp     loc_140004335
0x14000429f  mov     ecx, 0C0000161h
0x1400042a4  jmp     loc_140004335
0x1400042a9  mov     ecx, 0C0000025h
0x1400042ae  jmp     loc_140004335
0x1400042b3  mov     ecx, 0C0000095h
0x1400042b8  jmp     short loc_140004335
0x1400042ba  mov     ecx, 0C0000059h
0x1400042bf  jmp     short loc_140004335
0x1400042c1  cmp     ecx, 8007050Ch
0x1400042c7  jz      short loc_140004330
0x1400042c9  cmp     ecx, 8007054Fh
0x1400042cf  jz      short loc_140004329
0x1400042d1  cmp     ecx, 800705B9h
0x1400042d7  jz      short loc_140004322
0x1400042d9  test    ecx, ecx
0x1400042db  jz      short loc_14000431E
0x1400042dd  bt      ecx, 1Ch
0x1400042e1  jnb     short loc_1400042E9
0x1400042e3  btr     ecx, 1Ch
0x1400042e7  jmp     short loc_140004335
0x1400042e9  mov     eax, ecx
0x1400042eb  and     eax, 1FFF0000h
0x1400042f0  cmp     eax, 70000h
0x1400042f5  jnz     short loc_140004308
0x1400042f7  movzx   ecx, cx
0x1400042fa  mov     eax, ecx
0x1400042fc  or      eax, 0C0070000h
0x140004301  test    ecx, ecx
0x140004303  cmovnz  ecx, eax
0x140004306  jmp     short loc_140004335
0x140004308  cmp     eax, 90000h
0x14000430d  jnz     short loc_140004329
0x14000430f  test    ecx, ecx
0x140004311  jle     short loc_140004335
0x140004313  movzx   ecx, cx
0x140004316  or      ecx, 0C0090000h
0x14000431c  jmp     short loc_140004335
0x14000431e  xor     ecx, ecx
0x140004320  jmp     short loc_140004335
0x140004322  mov     ecx, 0C000A083h
0x140004327  jmp     short loc_140004335
0x140004329  mov     ecx, 0C00000E5h
0x14000432e  jmp     short loc_140004335
0x140004330  mov     ecx, 0C000042Bh
0x140004335  mov     eax, ecx
0x140004337  retn
```

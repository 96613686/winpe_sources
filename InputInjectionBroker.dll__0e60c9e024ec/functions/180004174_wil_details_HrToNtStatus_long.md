# wil::details::HrToNtStatus(long)

- ea: `0x180004174`
- end: `0x180004330`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002434`
- `0x1800024dc`
- `0x18000252c`
- `0x1800025ec`
- `0x180003808`
- `0x180004338`

## callees

- `0x180004174`

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
0x180004174  mov     eax, 800700EAh
0x180004179  cmp     ecx, eax
0x18000417b  jg      loc_180004250
0x180004181  jz      loc_180004246
0x180004187  mov     eax, 80070057h
0x18000418c  cmp     ecx, eax
0x18000418e  jg      short loc_1800041FA
0x180004190  jz      short loc_1800041F0
0x180004192  cmp     ecx, 80004005h
0x180004198  jz      short loc_1800041E6
0x18000419a  cmp     ecx, 80070001h
0x1800041a0  jz      short loc_1800041DC
0x1800041a2  cmp     ecx, 80070002h
0x1800041a8  jz      short loc_1800041D2
0x1800041aa  cmp     ecx, 80070003h
0x1800041b0  jz      short loc_1800041C8
0x1800041b2  cmp     ecx, 8007000Eh
0x1800041b8  jnz     loc_1800042D5
0x1800041be  mov     ecx, 0C0000017h
0x1800041c3  jmp     loc_18000432D
0x1800041c8  mov     ecx, 0C000003Ah
0x1800041cd  jmp     loc_18000432D
0x1800041d2  mov     ecx, 0C0000034h
0x1800041d7  jmp     loc_18000432D
0x1800041dc  mov     ecx, 0C0000002h
0x1800041e1  jmp     loc_18000432D
0x1800041e6  mov     ecx, 0C0000001h
0x1800041eb  jmp     loc_18000432D
0x1800041f0  mov     ecx, 0C000000Dh
0x1800041f5  jmp     loc_18000432D
0x1800041fa  cmp     ecx, 80070070h
0x180004200  jz      short loc_18000423C
0x180004202  cmp     ecx, 8007007Ah
0x180004208  jz      short loc_180004232
0x18000420a  cmp     ecx, 8007007Bh
0x180004210  jz      short loc_180004228
0x180004212  cmp     ecx, 8007007Eh
0x180004218  jnz     loc_1800042D5
0x18000421e  mov     ecx, 0C0000135h
0x180004223  jmp     loc_18000432D
0x180004228  mov     ecx, 0C0000033h
0x18000422d  jmp     loc_18000432D
0x180004232  mov     ecx, 0C0000023h
0x180004237  jmp     loc_18000432D
0x18000423c  mov     ecx, 0C000007Fh
0x180004241  jmp     loc_18000432D
0x180004246  mov     ecx, 80000005h
0x18000424b  jmp     loc_18000432D
0x180004250  mov     eax, 8007047Eh
0x180004255  cmp     ecx, eax
0x180004257  jg      short loc_1800042B9
0x180004259  jz      short loc_1800042B2
0x18000425b  cmp     ecx, 80070216h
0x180004261  jz      short loc_1800042AB
0x180004263  cmp     ecx, 8007023Eh
0x180004269  jz      short loc_1800042A1
0x18000426b  cmp     ecx, 80070246h
0x180004271  jz      short loc_180004297
0x180004273  cmp     ecx, 80070247h
0x180004279  jz      short loc_18000428D
0x18000427b  cmp     ecx, 80070272h
0x180004281  jnz     short loc_1800042D5
0x180004283  mov     ecx, 0C0000273h
0x180004288  jmp     loc_18000432D
0x18000428d  mov     ecx, 0C0000163h
0x180004292  jmp     loc_18000432D
0x180004297  mov     ecx, 0C0000161h
0x18000429c  jmp     loc_18000432D
0x1800042a1  mov     ecx, 0C0000025h
0x1800042a6  jmp     loc_18000432D
0x1800042ab  mov     ecx, 0C0000095h
0x1800042b0  jmp     short loc_18000432D
0x1800042b2  mov     ecx, 0C0000059h
0x1800042b7  jmp     short loc_18000432D
0x1800042b9  cmp     ecx, 8007050Ch
0x1800042bf  jz      short loc_180004328
0x1800042c1  cmp     ecx, 8007054Fh
0x1800042c7  jz      short loc_180004321
0x1800042c9  cmp     ecx, 800705B9h
0x1800042cf  jz      short loc_18000431A
0x1800042d1  test    ecx, ecx
0x1800042d3  jz      short loc_180004316
0x1800042d5  bt      ecx, 1Ch
0x1800042d9  jnb     short loc_1800042E1
0x1800042db  btr     ecx, 1Ch
0x1800042df  jmp     short loc_18000432D
0x1800042e1  mov     eax, ecx
0x1800042e3  and     eax, 1FFF0000h
0x1800042e8  cmp     eax, 70000h
0x1800042ed  jnz     short loc_180004300
0x1800042ef  movzx   ecx, cx
0x1800042f2  mov     eax, ecx
0x1800042f4  or      eax, 0C0070000h
0x1800042f9  test    ecx, ecx
0x1800042fb  cmovnz  ecx, eax
0x1800042fe  jmp     short loc_18000432D
0x180004300  cmp     eax, 90000h
0x180004305  jnz     short loc_180004321
0x180004307  test    ecx, ecx
0x180004309  jle     short loc_18000432D
0x18000430b  movzx   ecx, cx
0x18000430e  or      ecx, 0C0090000h
0x180004314  jmp     short loc_18000432D
0x180004316  xor     ecx, ecx
0x180004318  jmp     short loc_18000432D
0x18000431a  mov     ecx, 0C000A083h
0x18000431f  jmp     short loc_18000432D
0x180004321  mov     ecx, 0C00000E5h
0x180004326  jmp     short loc_18000432D
0x180004328  mov     ecx, 0C000042Bh
0x18000432d  mov     eax, ecx
0x18000432f  retn
```

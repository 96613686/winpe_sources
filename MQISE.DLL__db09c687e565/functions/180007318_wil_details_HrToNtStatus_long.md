# wil::details::HrToNtStatus(long)

- ea: `0x180007318`
- end: `0x1800074d4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023b4`
- `0x180002454`
- `0x1800024a4`
- `0x180002564`
- `0x180006034`
- `0x1800075e0`

## callees

- `0x180007318`

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
0x180007318  mov     eax, 800700EAh
0x18000731d  cmp     ecx, eax
0x18000731f  jg      loc_1800073F4
0x180007325  jz      loc_1800073EA
0x18000732b  mov     eax, 80070057h
0x180007330  cmp     ecx, eax
0x180007332  jg      short loc_18000739E
0x180007334  jz      short loc_180007394
0x180007336  cmp     ecx, 80004005h
0x18000733c  jz      short loc_18000738A
0x18000733e  cmp     ecx, 80070001h
0x180007344  jz      short loc_180007380
0x180007346  cmp     ecx, 80070002h
0x18000734c  jz      short loc_180007376
0x18000734e  cmp     ecx, 80070003h
0x180007354  jz      short loc_18000736C
0x180007356  cmp     ecx, 8007000Eh
0x18000735c  jnz     loc_180007479
0x180007362  mov     ecx, 0C0000017h
0x180007367  jmp     loc_1800074D1
0x18000736c  mov     ecx, 0C000003Ah
0x180007371  jmp     loc_1800074D1
0x180007376  mov     ecx, 0C0000034h
0x18000737b  jmp     loc_1800074D1
0x180007380  mov     ecx, 0C0000002h
0x180007385  jmp     loc_1800074D1
0x18000738a  mov     ecx, 0C0000001h
0x18000738f  jmp     loc_1800074D1
0x180007394  mov     ecx, 0C000000Dh
0x180007399  jmp     loc_1800074D1
0x18000739e  cmp     ecx, 80070070h
0x1800073a4  jz      short loc_1800073E0
0x1800073a6  cmp     ecx, 8007007Ah
0x1800073ac  jz      short loc_1800073D6
0x1800073ae  cmp     ecx, 8007007Bh
0x1800073b4  jz      short loc_1800073CC
0x1800073b6  cmp     ecx, 8007007Eh
0x1800073bc  jnz     loc_180007479
0x1800073c2  mov     ecx, 0C0000135h
0x1800073c7  jmp     loc_1800074D1
0x1800073cc  mov     ecx, 0C0000033h
0x1800073d1  jmp     loc_1800074D1
0x1800073d6  mov     ecx, 0C0000023h
0x1800073db  jmp     loc_1800074D1
0x1800073e0  mov     ecx, 0C000007Fh
0x1800073e5  jmp     loc_1800074D1
0x1800073ea  mov     ecx, 80000005h
0x1800073ef  jmp     loc_1800074D1
0x1800073f4  mov     eax, 8007047Eh
0x1800073f9  cmp     ecx, eax
0x1800073fb  jg      short loc_18000745D
0x1800073fd  jz      short loc_180007456
0x1800073ff  cmp     ecx, 80070216h
0x180007405  jz      short loc_18000744F
0x180007407  cmp     ecx, 8007023Eh
0x18000740d  jz      short loc_180007445
0x18000740f  cmp     ecx, 80070246h
0x180007415  jz      short loc_18000743B
0x180007417  cmp     ecx, 80070247h
0x18000741d  jz      short loc_180007431
0x18000741f  cmp     ecx, 80070272h
0x180007425  jnz     short loc_180007479
0x180007427  mov     ecx, 0C0000273h
0x18000742c  jmp     loc_1800074D1
0x180007431  mov     ecx, 0C0000163h
0x180007436  jmp     loc_1800074D1
0x18000743b  mov     ecx, 0C0000161h
0x180007440  jmp     loc_1800074D1
0x180007445  mov     ecx, 0C0000025h
0x18000744a  jmp     loc_1800074D1
0x18000744f  mov     ecx, 0C0000095h
0x180007454  jmp     short loc_1800074D1
0x180007456  mov     ecx, 0C0000059h
0x18000745b  jmp     short loc_1800074D1
0x18000745d  cmp     ecx, 8007050Ch
0x180007463  jz      short loc_1800074CC
0x180007465  cmp     ecx, 8007054Fh
0x18000746b  jz      short loc_1800074C5
0x18000746d  cmp     ecx, 800705B9h
0x180007473  jz      short loc_1800074BE
0x180007475  test    ecx, ecx
0x180007477  jz      short loc_1800074BA
0x180007479  bt      ecx, 1Ch
0x18000747d  jnb     short loc_180007485
0x18000747f  btr     ecx, 1Ch
0x180007483  jmp     short loc_1800074D1
0x180007485  mov     eax, ecx
0x180007487  and     eax, 1FFF0000h
0x18000748c  cmp     eax, 70000h
0x180007491  jnz     short loc_1800074A4
0x180007493  movzx   ecx, cx
0x180007496  mov     eax, ecx
0x180007498  or      eax, 0C0070000h
0x18000749d  test    ecx, ecx
0x18000749f  cmovnz  ecx, eax
0x1800074a2  jmp     short loc_1800074D1
0x1800074a4  cmp     eax, 90000h
0x1800074a9  jnz     short loc_1800074C5
0x1800074ab  test    ecx, ecx
0x1800074ad  jle     short loc_1800074D1
0x1800074af  movzx   ecx, cx
0x1800074b2  or      ecx, 0C0090000h
0x1800074b8  jmp     short loc_1800074D1
0x1800074ba  xor     ecx, ecx
0x1800074bc  jmp     short loc_1800074D1
0x1800074be  mov     ecx, 0C000A083h
0x1800074c3  jmp     short loc_1800074D1
0x1800074c5  mov     ecx, 0C00000E5h
0x1800074ca  jmp     short loc_1800074D1
0x1800074cc  mov     ecx, 0C000042Bh
0x1800074d1  mov     eax, ecx
0x1800074d3  retn
```

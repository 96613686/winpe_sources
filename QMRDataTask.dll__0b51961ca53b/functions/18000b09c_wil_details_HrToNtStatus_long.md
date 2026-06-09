# wil::details::HrToNtStatus(long)

- ea: `0x18000b09c`
- end: `0x18000b258`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004934`
- `0x1800049d4`
- `0x180004a24`
- `0x180004ae4`
- `0x180007d88`
- `0x18000bb60`

## callees

- `0x18000b09c`

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
0x18000b09c  mov     eax, 800700EAh
0x18000b0a1  cmp     ecx, eax
0x18000b0a3  jg      loc_18000B178
0x18000b0a9  jz      loc_18000B16E
0x18000b0af  mov     eax, 80070057h
0x18000b0b4  cmp     ecx, eax
0x18000b0b6  jg      short loc_18000B122
0x18000b0b8  jz      short loc_18000B118
0x18000b0ba  cmp     ecx, 80004005h
0x18000b0c0  jz      short loc_18000B10E
0x18000b0c2  cmp     ecx, 80070001h
0x18000b0c8  jz      short loc_18000B104
0x18000b0ca  cmp     ecx, 80070002h
0x18000b0d0  jz      short loc_18000B0FA
0x18000b0d2  cmp     ecx, 80070003h
0x18000b0d8  jz      short loc_18000B0F0
0x18000b0da  cmp     ecx, 8007000Eh
0x18000b0e0  jnz     loc_18000B1FD
0x18000b0e6  mov     ecx, 0C0000017h
0x18000b0eb  jmp     loc_18000B255
0x18000b0f0  mov     ecx, 0C000003Ah
0x18000b0f5  jmp     loc_18000B255
0x18000b0fa  mov     ecx, 0C0000034h
0x18000b0ff  jmp     loc_18000B255
0x18000b104  mov     ecx, 0C0000002h
0x18000b109  jmp     loc_18000B255
0x18000b10e  mov     ecx, 0C0000001h
0x18000b113  jmp     loc_18000B255
0x18000b118  mov     ecx, 0C000000Dh
0x18000b11d  jmp     loc_18000B255
0x18000b122  cmp     ecx, 80070070h
0x18000b128  jz      short loc_18000B164
0x18000b12a  cmp     ecx, 8007007Ah
0x18000b130  jz      short loc_18000B15A
0x18000b132  cmp     ecx, 8007007Bh
0x18000b138  jz      short loc_18000B150
0x18000b13a  cmp     ecx, 8007007Eh
0x18000b140  jnz     loc_18000B1FD
0x18000b146  mov     ecx, 0C0000135h
0x18000b14b  jmp     loc_18000B255
0x18000b150  mov     ecx, 0C0000033h
0x18000b155  jmp     loc_18000B255
0x18000b15a  mov     ecx, 0C0000023h
0x18000b15f  jmp     loc_18000B255
0x18000b164  mov     ecx, 0C000007Fh
0x18000b169  jmp     loc_18000B255
0x18000b16e  mov     ecx, 80000005h
0x18000b173  jmp     loc_18000B255
0x18000b178  mov     eax, 8007047Eh
0x18000b17d  cmp     ecx, eax
0x18000b17f  jg      short loc_18000B1E1
0x18000b181  jz      short loc_18000B1DA
0x18000b183  cmp     ecx, 80070216h
0x18000b189  jz      short loc_18000B1D3
0x18000b18b  cmp     ecx, 8007023Eh
0x18000b191  jz      short loc_18000B1C9
0x18000b193  cmp     ecx, 80070246h
0x18000b199  jz      short loc_18000B1BF
0x18000b19b  cmp     ecx, 80070247h
0x18000b1a1  jz      short loc_18000B1B5
0x18000b1a3  cmp     ecx, 80070272h
0x18000b1a9  jnz     short loc_18000B1FD
0x18000b1ab  mov     ecx, 0C0000273h
0x18000b1b0  jmp     loc_18000B255
0x18000b1b5  mov     ecx, 0C0000163h
0x18000b1ba  jmp     loc_18000B255
0x18000b1bf  mov     ecx, 0C0000161h
0x18000b1c4  jmp     loc_18000B255
0x18000b1c9  mov     ecx, 0C0000025h
0x18000b1ce  jmp     loc_18000B255
0x18000b1d3  mov     ecx, 0C0000095h
0x18000b1d8  jmp     short loc_18000B255
0x18000b1da  mov     ecx, 0C0000059h
0x18000b1df  jmp     short loc_18000B255
0x18000b1e1  cmp     ecx, 8007050Ch
0x18000b1e7  jz      short loc_18000B250
0x18000b1e9  cmp     ecx, 8007054Fh
0x18000b1ef  jz      short loc_18000B249
0x18000b1f1  cmp     ecx, 800705B9h
0x18000b1f7  jz      short loc_18000B242
0x18000b1f9  test    ecx, ecx
0x18000b1fb  jz      short loc_18000B23E
0x18000b1fd  bt      ecx, 1Ch
0x18000b201  jnb     short loc_18000B209
0x18000b203  btr     ecx, 1Ch
0x18000b207  jmp     short loc_18000B255
0x18000b209  mov     eax, ecx
0x18000b20b  and     eax, 1FFF0000h
0x18000b210  cmp     eax, 70000h
0x18000b215  jnz     short loc_18000B228
0x18000b217  movzx   ecx, cx
0x18000b21a  mov     eax, ecx
0x18000b21c  or      eax, 0C0070000h
0x18000b221  test    ecx, ecx
0x18000b223  cmovnz  ecx, eax
0x18000b226  jmp     short loc_18000B255
0x18000b228  cmp     eax, 90000h
0x18000b22d  jnz     short loc_18000B249
0x18000b22f  test    ecx, ecx
0x18000b231  jle     short loc_18000B255
0x18000b233  movzx   ecx, cx
0x18000b236  or      ecx, 0C0090000h
0x18000b23c  jmp     short loc_18000B255
0x18000b23e  xor     ecx, ecx
0x18000b240  jmp     short loc_18000B255
0x18000b242  mov     ecx, 0C000A083h
0x18000b247  jmp     short loc_18000B255
0x18000b249  mov     ecx, 0C00000E5h
0x18000b24e  jmp     short loc_18000B255
0x18000b250  mov     ecx, 0C000042Bh
0x18000b255  mov     eax, ecx
0x18000b257  retn
```

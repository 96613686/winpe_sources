# wil::details::HrToNtStatus(long)

- ea: `0x180005a34`
- end: `0x180005bf0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ad0`
- `0x180002b78`
- `0x180002bc8`
- `0x180002c80`
- `0x180004ff8`
- `0x180005d60`

## callees

- `0x180005a34`

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
0x180005a34  mov     eax, 800700EAh
0x180005a39  cmp     ecx, eax
0x180005a3b  jg      loc_180005B10
0x180005a41  jz      loc_180005B06
0x180005a47  mov     eax, 80070057h
0x180005a4c  cmp     ecx, eax
0x180005a4e  jg      short loc_180005ABA
0x180005a50  jz      short loc_180005AB0
0x180005a52  cmp     ecx, 80004005h
0x180005a58  jz      short loc_180005AA6
0x180005a5a  cmp     ecx, 80070001h
0x180005a60  jz      short loc_180005A9C
0x180005a62  cmp     ecx, 80070002h
0x180005a68  jz      short loc_180005A92
0x180005a6a  cmp     ecx, 80070003h
0x180005a70  jz      short loc_180005A88
0x180005a72  cmp     ecx, 8007000Eh
0x180005a78  jnz     loc_180005B95
0x180005a7e  mov     ecx, 0C0000017h
0x180005a83  jmp     loc_180005BED
0x180005a88  mov     ecx, 0C000003Ah
0x180005a8d  jmp     loc_180005BED
0x180005a92  mov     ecx, 0C0000034h
0x180005a97  jmp     loc_180005BED
0x180005a9c  mov     ecx, 0C0000002h
0x180005aa1  jmp     loc_180005BED
0x180005aa6  mov     ecx, 0C0000001h
0x180005aab  jmp     loc_180005BED
0x180005ab0  mov     ecx, 0C000000Dh
0x180005ab5  jmp     loc_180005BED
0x180005aba  cmp     ecx, 80070070h
0x180005ac0  jz      short loc_180005AFC
0x180005ac2  cmp     ecx, 8007007Ah
0x180005ac8  jz      short loc_180005AF2
0x180005aca  cmp     ecx, 8007007Bh
0x180005ad0  jz      short loc_180005AE8
0x180005ad2  cmp     ecx, 8007007Eh
0x180005ad8  jnz     loc_180005B95
0x180005ade  mov     ecx, 0C0000135h
0x180005ae3  jmp     loc_180005BED
0x180005ae8  mov     ecx, 0C0000033h
0x180005aed  jmp     loc_180005BED
0x180005af2  mov     ecx, 0C0000023h
0x180005af7  jmp     loc_180005BED
0x180005afc  mov     ecx, 0C000007Fh
0x180005b01  jmp     loc_180005BED
0x180005b06  mov     ecx, 80000005h
0x180005b0b  jmp     loc_180005BED
0x180005b10  mov     eax, 8007047Eh
0x180005b15  cmp     ecx, eax
0x180005b17  jg      short loc_180005B79
0x180005b19  jz      short loc_180005B72
0x180005b1b  cmp     ecx, 80070216h
0x180005b21  jz      short loc_180005B6B
0x180005b23  cmp     ecx, 8007023Eh
0x180005b29  jz      short loc_180005B61
0x180005b2b  cmp     ecx, 80070246h
0x180005b31  jz      short loc_180005B57
0x180005b33  cmp     ecx, 80070247h
0x180005b39  jz      short loc_180005B4D
0x180005b3b  cmp     ecx, 80070272h
0x180005b41  jnz     short loc_180005B95
0x180005b43  mov     ecx, 0C0000273h
0x180005b48  jmp     loc_180005BED
0x180005b4d  mov     ecx, 0C0000163h
0x180005b52  jmp     loc_180005BED
0x180005b57  mov     ecx, 0C0000161h
0x180005b5c  jmp     loc_180005BED
0x180005b61  mov     ecx, 0C0000025h
0x180005b66  jmp     loc_180005BED
0x180005b6b  mov     ecx, 0C0000095h
0x180005b70  jmp     short loc_180005BED
0x180005b72  mov     ecx, 0C0000059h
0x180005b77  jmp     short loc_180005BED
0x180005b79  cmp     ecx, 8007050Ch
0x180005b7f  jz      short loc_180005BE8
0x180005b81  cmp     ecx, 8007054Fh
0x180005b87  jz      short loc_180005BE1
0x180005b89  cmp     ecx, 800705B9h
0x180005b8f  jz      short loc_180005BDA
0x180005b91  test    ecx, ecx
0x180005b93  jz      short loc_180005BD6
0x180005b95  bt      ecx, 1Ch
0x180005b99  jnb     short loc_180005BA1
0x180005b9b  btr     ecx, 1Ch
0x180005b9f  jmp     short loc_180005BED
0x180005ba1  mov     eax, ecx
0x180005ba3  and     eax, 1FFF0000h
0x180005ba8  cmp     eax, 70000h
0x180005bad  jnz     short loc_180005BC0
0x180005baf  movzx   ecx, cx
0x180005bb2  mov     eax, ecx
0x180005bb4  or      eax, 0C0070000h
0x180005bb9  test    ecx, ecx
0x180005bbb  cmovnz  ecx, eax
0x180005bbe  jmp     short loc_180005BED
0x180005bc0  cmp     eax, 90000h
0x180005bc5  jnz     short loc_180005BE1
0x180005bc7  test    ecx, ecx
0x180005bc9  jle     short loc_180005BED
0x180005bcb  movzx   ecx, cx
0x180005bce  or      ecx, 0C0090000h
0x180005bd4  jmp     short loc_180005BED
0x180005bd6  xor     ecx, ecx
0x180005bd8  jmp     short loc_180005BED
0x180005bda  mov     ecx, 0C000A083h
0x180005bdf  jmp     short loc_180005BED
0x180005be1  mov     ecx, 0C00000E5h
0x180005be6  jmp     short loc_180005BED
0x180005be8  mov     ecx, 0C000042Bh
0x180005bed  mov     eax, ecx
0x180005bef  retn
```

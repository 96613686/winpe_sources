# wil::details::HrToNtStatus(long)

- ea: `0x1800060fc`
- end: `0x1800062b8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003194`
- `0x18000323c`
- `0x18000328c`
- `0x180003344`
- `0x1800056b8`
- `0x180006430`
- `0x180011ad8`

## callees

- `0x1800060fc`

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
0x1800060fc  mov     eax, 800700EAh
0x180006101  cmp     ecx, eax
0x180006103  jg      loc_1800061D8
0x180006109  jz      loc_1800061CE
0x18000610f  mov     eax, 80070057h
0x180006114  cmp     ecx, eax
0x180006116  jg      short loc_180006182
0x180006118  jz      short loc_180006178
0x18000611a  cmp     ecx, 80004005h
0x180006120  jz      short loc_18000616E
0x180006122  cmp     ecx, 80070001h
0x180006128  jz      short loc_180006164
0x18000612a  cmp     ecx, 80070002h
0x180006130  jz      short loc_18000615A
0x180006132  cmp     ecx, 80070003h
0x180006138  jz      short loc_180006150
0x18000613a  cmp     ecx, 8007000Eh
0x180006140  jnz     loc_18000625D
0x180006146  mov     ecx, 0C0000017h
0x18000614b  jmp     loc_1800062B5
0x180006150  mov     ecx, 0C000003Ah
0x180006155  jmp     loc_1800062B5
0x18000615a  mov     ecx, 0C0000034h
0x18000615f  jmp     loc_1800062B5
0x180006164  mov     ecx, 0C0000002h
0x180006169  jmp     loc_1800062B5
0x18000616e  mov     ecx, 0C0000001h
0x180006173  jmp     loc_1800062B5
0x180006178  mov     ecx, 0C000000Dh
0x18000617d  jmp     loc_1800062B5
0x180006182  cmp     ecx, 80070070h
0x180006188  jz      short loc_1800061C4
0x18000618a  cmp     ecx, 8007007Ah
0x180006190  jz      short loc_1800061BA
0x180006192  cmp     ecx, 8007007Bh
0x180006198  jz      short loc_1800061B0
0x18000619a  cmp     ecx, 8007007Eh
0x1800061a0  jnz     loc_18000625D
0x1800061a6  mov     ecx, 0C0000135h
0x1800061ab  jmp     loc_1800062B5
0x1800061b0  mov     ecx, 0C0000033h
0x1800061b5  jmp     loc_1800062B5
0x1800061ba  mov     ecx, 0C0000023h
0x1800061bf  jmp     loc_1800062B5
0x1800061c4  mov     ecx, 0C000007Fh
0x1800061c9  jmp     loc_1800062B5
0x1800061ce  mov     ecx, 80000005h
0x1800061d3  jmp     loc_1800062B5
0x1800061d8  mov     eax, 8007047Eh
0x1800061dd  cmp     ecx, eax
0x1800061df  jg      short loc_180006241
0x1800061e1  jz      short loc_18000623A
0x1800061e3  cmp     ecx, 80070216h
0x1800061e9  jz      short loc_180006233
0x1800061eb  cmp     ecx, 8007023Eh
0x1800061f1  jz      short loc_180006229
0x1800061f3  cmp     ecx, 80070246h
0x1800061f9  jz      short loc_18000621F
0x1800061fb  cmp     ecx, 80070247h
0x180006201  jz      short loc_180006215
0x180006203  cmp     ecx, 80070272h
0x180006209  jnz     short loc_18000625D
0x18000620b  mov     ecx, 0C0000273h
0x180006210  jmp     loc_1800062B5
0x180006215  mov     ecx, 0C0000163h
0x18000621a  jmp     loc_1800062B5
0x18000621f  mov     ecx, 0C0000161h
0x180006224  jmp     loc_1800062B5
0x180006229  mov     ecx, 0C0000025h
0x18000622e  jmp     loc_1800062B5
0x180006233  mov     ecx, 0C0000095h
0x180006238  jmp     short loc_1800062B5
0x18000623a  mov     ecx, 0C0000059h
0x18000623f  jmp     short loc_1800062B5
0x180006241  cmp     ecx, 8007050Ch
0x180006247  jz      short loc_1800062B0
0x180006249  cmp     ecx, 8007054Fh
0x18000624f  jz      short loc_1800062A9
0x180006251  cmp     ecx, 800705B9h
0x180006257  jz      short loc_1800062A2
0x180006259  test    ecx, ecx
0x18000625b  jz      short loc_18000629E
0x18000625d  bt      ecx, 1Ch
0x180006261  jnb     short loc_180006269
0x180006263  btr     ecx, 1Ch
0x180006267  jmp     short loc_1800062B5
0x180006269  mov     eax, ecx
0x18000626b  and     eax, 1FFF0000h
0x180006270  cmp     eax, 70000h
0x180006275  jnz     short loc_180006288
0x180006277  movzx   ecx, cx
0x18000627a  mov     eax, ecx
0x18000627c  or      eax, 0C0070000h
0x180006281  test    ecx, ecx
0x180006283  cmovnz  ecx, eax
0x180006286  jmp     short loc_1800062B5
0x180006288  cmp     eax, 90000h
0x18000628d  jnz     short loc_1800062A9
0x18000628f  test    ecx, ecx
0x180006291  jle     short loc_1800062B5
0x180006293  movzx   ecx, cx
0x180006296  or      ecx, 0C0090000h
0x18000629c  jmp     short loc_1800062B5
0x18000629e  xor     ecx, ecx
0x1800062a0  jmp     short loc_1800062B5
0x1800062a2  mov     ecx, 0C000A083h
0x1800062a7  jmp     short loc_1800062B5
0x1800062a9  mov     ecx, 0C00000E5h
0x1800062ae  jmp     short loc_1800062B5
0x1800062b0  mov     ecx, 0C000042Bh
0x1800062b5  mov     eax, ecx
0x1800062b7  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x14000615c`
- end: `0x140006318`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000561c`
- `0x1400056c4`
- `0x140005714`
- `0x140005b34`
- `0x140006320`
- `0x1400079d0`

## callees

- `0x14000615c`

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
0x14000615c  mov     eax, 800700EAh
0x140006161  cmp     ecx, eax
0x140006163  jg      loc_140006238
0x140006169  jz      loc_14000622E
0x14000616f  mov     eax, 80070057h
0x140006174  cmp     ecx, eax
0x140006176  jg      short loc_1400061E2
0x140006178  jz      short loc_1400061D8
0x14000617a  cmp     ecx, 80004005h
0x140006180  jz      short loc_1400061CE
0x140006182  cmp     ecx, 80070001h
0x140006188  jz      short loc_1400061C4
0x14000618a  cmp     ecx, 80070002h
0x140006190  jz      short loc_1400061BA
0x140006192  cmp     ecx, 80070003h
0x140006198  jz      short loc_1400061B0
0x14000619a  cmp     ecx, 8007000Eh
0x1400061a0  jnz     loc_1400062BD
0x1400061a6  mov     ecx, 0C0000017h
0x1400061ab  jmp     loc_140006315
0x1400061b0  mov     ecx, 0C000003Ah
0x1400061b5  jmp     loc_140006315
0x1400061ba  mov     ecx, 0C0000034h
0x1400061bf  jmp     loc_140006315
0x1400061c4  mov     ecx, 0C0000002h
0x1400061c9  jmp     loc_140006315
0x1400061ce  mov     ecx, 0C0000001h
0x1400061d3  jmp     loc_140006315
0x1400061d8  mov     ecx, 0C000000Dh
0x1400061dd  jmp     loc_140006315
0x1400061e2  cmp     ecx, 80070070h
0x1400061e8  jz      short loc_140006224
0x1400061ea  cmp     ecx, 8007007Ah
0x1400061f0  jz      short loc_14000621A
0x1400061f2  cmp     ecx, 8007007Bh
0x1400061f8  jz      short loc_140006210
0x1400061fa  cmp     ecx, 8007007Eh
0x140006200  jnz     loc_1400062BD
0x140006206  mov     ecx, 0C0000135h
0x14000620b  jmp     loc_140006315
0x140006210  mov     ecx, 0C0000033h
0x140006215  jmp     loc_140006315
0x14000621a  mov     ecx, 0C0000023h
0x14000621f  jmp     loc_140006315
0x140006224  mov     ecx, 0C000007Fh
0x140006229  jmp     loc_140006315
0x14000622e  mov     ecx, 80000005h
0x140006233  jmp     loc_140006315
0x140006238  mov     eax, 8007047Eh
0x14000623d  cmp     ecx, eax
0x14000623f  jg      short loc_1400062A1
0x140006241  jz      short loc_14000629A
0x140006243  cmp     ecx, 80070216h
0x140006249  jz      short loc_140006293
0x14000624b  cmp     ecx, 8007023Eh
0x140006251  jz      short loc_140006289
0x140006253  cmp     ecx, 80070246h
0x140006259  jz      short loc_14000627F
0x14000625b  cmp     ecx, 80070247h
0x140006261  jz      short loc_140006275
0x140006263  cmp     ecx, 80070272h
0x140006269  jnz     short loc_1400062BD
0x14000626b  mov     ecx, 0C0000273h
0x140006270  jmp     loc_140006315
0x140006275  mov     ecx, 0C0000163h
0x14000627a  jmp     loc_140006315
0x14000627f  mov     ecx, 0C0000161h
0x140006284  jmp     loc_140006315
0x140006289  mov     ecx, 0C0000025h
0x14000628e  jmp     loc_140006315
0x140006293  mov     ecx, 0C0000095h
0x140006298  jmp     short loc_140006315
0x14000629a  mov     ecx, 0C0000059h
0x14000629f  jmp     short loc_140006315
0x1400062a1  cmp     ecx, 8007050Ch
0x1400062a7  jz      short loc_140006310
0x1400062a9  cmp     ecx, 8007054Fh
0x1400062af  jz      short loc_140006309
0x1400062b1  cmp     ecx, 800705B9h
0x1400062b7  jz      short loc_140006302
0x1400062b9  test    ecx, ecx
0x1400062bb  jz      short loc_1400062FE
0x1400062bd  bt      ecx, 1Ch
0x1400062c1  jnb     short loc_1400062C9
0x1400062c3  btr     ecx, 1Ch
0x1400062c7  jmp     short loc_140006315
0x1400062c9  mov     eax, ecx
0x1400062cb  and     eax, 1FFF0000h
0x1400062d0  cmp     eax, 70000h
0x1400062d5  jnz     short loc_1400062E8
0x1400062d7  movzx   ecx, cx
0x1400062da  mov     eax, ecx
0x1400062dc  or      eax, 0C0070000h
0x1400062e1  test    ecx, ecx
0x1400062e3  cmovnz  ecx, eax
0x1400062e6  jmp     short loc_140006315
0x1400062e8  cmp     eax, 90000h
0x1400062ed  jnz     short loc_140006309
0x1400062ef  test    ecx, ecx
0x1400062f1  jle     short loc_140006315
0x1400062f3  movzx   ecx, cx
0x1400062f6  or      ecx, 0C0090000h
0x1400062fc  jmp     short loc_140006315
0x1400062fe  xor     ecx, ecx
0x140006300  jmp     short loc_140006315
0x140006302  mov     ecx, 0C000A083h
0x140006307  jmp     short loc_140006315
0x140006309  mov     ecx, 0C00000E5h
0x14000630e  jmp     short loc_140006315
0x140006310  mov     ecx, 0C000042Bh
0x140006315  mov     eax, ecx
0x140006317  retn
```

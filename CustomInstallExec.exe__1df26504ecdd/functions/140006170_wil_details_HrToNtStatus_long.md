# wil::details::HrToNtStatus(long)

- ea: `0x140006170`
- end: `0x14000632c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000492c`
- `0x140004998`
- `0x140004a1c`
- `0x140004a74`
- `0x1400058c8`
- `0x140006460`
- `0x140007f74`
- `0x140007fe8`
- `0x1400080bc`
- `0x14000c010`
- `0x14000c0b8`
- `0x14000e0e8`

## callees

- `0x140006170`

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
0x140006170  mov     eax, 800700EAh
0x140006175  cmp     ecx, eax
0x140006177  jg      loc_14000624C
0x14000617d  jz      loc_140006242
0x140006183  mov     eax, 80070057h
0x140006188  cmp     ecx, eax
0x14000618a  jg      short loc_1400061F6
0x14000618c  jz      short loc_1400061EC
0x14000618e  cmp     ecx, 80004005h
0x140006194  jz      short loc_1400061E2
0x140006196  cmp     ecx, 80070001h
0x14000619c  jz      short loc_1400061D8
0x14000619e  cmp     ecx, 80070002h
0x1400061a4  jz      short loc_1400061CE
0x1400061a6  cmp     ecx, 80070003h
0x1400061ac  jz      short loc_1400061C4
0x1400061ae  cmp     ecx, 8007000Eh
0x1400061b4  jnz     loc_1400062D1
0x1400061ba  mov     ecx, 0C0000017h
0x1400061bf  jmp     loc_140006329
0x1400061c4  mov     ecx, 0C000003Ah
0x1400061c9  jmp     loc_140006329
0x1400061ce  mov     ecx, 0C0000034h
0x1400061d3  jmp     loc_140006329
0x1400061d8  mov     ecx, 0C0000002h
0x1400061dd  jmp     loc_140006329
0x1400061e2  mov     ecx, 0C0000001h
0x1400061e7  jmp     loc_140006329
0x1400061ec  mov     ecx, 0C000000Dh
0x1400061f1  jmp     loc_140006329
0x1400061f6  cmp     ecx, 80070070h
0x1400061fc  jz      short loc_140006238
0x1400061fe  cmp     ecx, 8007007Ah
0x140006204  jz      short loc_14000622E
0x140006206  cmp     ecx, 8007007Bh
0x14000620c  jz      short loc_140006224
0x14000620e  cmp     ecx, 8007007Eh
0x140006214  jnz     loc_1400062D1
0x14000621a  mov     ecx, 0C0000135h
0x14000621f  jmp     loc_140006329
0x140006224  mov     ecx, 0C0000033h
0x140006229  jmp     loc_140006329
0x14000622e  mov     ecx, 0C0000023h
0x140006233  jmp     loc_140006329
0x140006238  mov     ecx, 0C000007Fh
0x14000623d  jmp     loc_140006329
0x140006242  mov     ecx, 80000005h
0x140006247  jmp     loc_140006329
0x14000624c  mov     eax, 8007047Eh
0x140006251  cmp     ecx, eax
0x140006253  jg      short loc_1400062B5
0x140006255  jz      short loc_1400062AE
0x140006257  cmp     ecx, 80070216h
0x14000625d  jz      short loc_1400062A7
0x14000625f  cmp     ecx, 8007023Eh
0x140006265  jz      short loc_14000629D
0x140006267  cmp     ecx, 80070246h
0x14000626d  jz      short loc_140006293
0x14000626f  cmp     ecx, 80070247h
0x140006275  jz      short loc_140006289
0x140006277  cmp     ecx, 80070272h
0x14000627d  jnz     short loc_1400062D1
0x14000627f  mov     ecx, 0C0000273h
0x140006284  jmp     loc_140006329
0x140006289  mov     ecx, 0C0000163h
0x14000628e  jmp     loc_140006329
0x140006293  mov     ecx, 0C0000161h
0x140006298  jmp     loc_140006329
0x14000629d  mov     ecx, 0C0000025h
0x1400062a2  jmp     loc_140006329
0x1400062a7  mov     ecx, 0C0000095h
0x1400062ac  jmp     short loc_140006329
0x1400062ae  mov     ecx, 0C0000059h
0x1400062b3  jmp     short loc_140006329
0x1400062b5  cmp     ecx, 8007050Ch
0x1400062bb  jz      short loc_140006324
0x1400062bd  cmp     ecx, 8007054Fh
0x1400062c3  jz      short loc_14000631D
0x1400062c5  cmp     ecx, 800705B9h
0x1400062cb  jz      short loc_140006316
0x1400062cd  test    ecx, ecx
0x1400062cf  jz      short loc_140006312
0x1400062d1  bt      ecx, 1Ch
0x1400062d5  jnb     short loc_1400062DD
0x1400062d7  btr     ecx, 1Ch
0x1400062db  jmp     short loc_140006329
0x1400062dd  mov     eax, ecx
0x1400062df  and     eax, 1FFF0000h
0x1400062e4  cmp     eax, 70000h
0x1400062e9  jnz     short loc_1400062FC
0x1400062eb  movzx   ecx, cx
0x1400062ee  mov     eax, ecx
0x1400062f0  or      eax, 0C0070000h
0x1400062f5  test    ecx, ecx
0x1400062f7  cmovnz  ecx, eax
0x1400062fa  jmp     short loc_140006329
0x1400062fc  cmp     eax, 90000h
0x140006301  jnz     short loc_14000631D
0x140006303  test    ecx, ecx
0x140006305  jle     short loc_140006329
0x140006307  movzx   ecx, cx
0x14000630a  or      ecx, 0C0090000h
0x140006310  jmp     short loc_140006329
0x140006312  xor     ecx, ecx
0x140006314  jmp     short loc_140006329
0x140006316  mov     ecx, 0C000A083h
0x14000631b  jmp     short loc_140006329
0x14000631d  mov     ecx, 0C00000E5h
0x140006322  jmp     short loc_140006329
0x140006324  mov     ecx, 0C000042Bh
0x140006329  mov     eax, ecx
0x14000632b  retn
```

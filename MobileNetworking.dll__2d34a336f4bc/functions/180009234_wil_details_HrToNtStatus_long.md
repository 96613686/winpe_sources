# wil::details::HrToNtStatus(long)

- ea: `0x180009234`
- end: `0x1800093f0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800091b0`
- `0x18000f3a4`
- `0x18000f414`
- `0x18000f464`
- `0x18000ff9c`
- `0x1800107d0`

## callees

- `0x180009234`

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
0x180009234  mov     eax, 800700EAh
0x180009239  cmp     ecx, eax
0x18000923b  jg      loc_180009310
0x180009241  jz      loc_180009306
0x180009247  mov     eax, 80070057h
0x18000924c  cmp     ecx, eax
0x18000924e  jg      short loc_1800092BA
0x180009250  jz      short loc_1800092B0
0x180009252  cmp     ecx, 80004005h
0x180009258  jz      short loc_1800092A6
0x18000925a  cmp     ecx, 80070001h
0x180009260  jz      short loc_18000929C
0x180009262  cmp     ecx, 80070002h
0x180009268  jz      short loc_180009292
0x18000926a  cmp     ecx, 80070003h
0x180009270  jz      short loc_180009288
0x180009272  cmp     ecx, 8007000Eh
0x180009278  jnz     loc_180009395
0x18000927e  mov     ecx, 0C0000017h
0x180009283  jmp     loc_1800093ED
0x180009288  mov     ecx, 0C000003Ah
0x18000928d  jmp     loc_1800093ED
0x180009292  mov     ecx, 0C0000034h
0x180009297  jmp     loc_1800093ED
0x18000929c  mov     ecx, 0C0000002h
0x1800092a1  jmp     loc_1800093ED
0x1800092a6  mov     ecx, 0C0000001h
0x1800092ab  jmp     loc_1800093ED
0x1800092b0  mov     ecx, 0C000000Dh
0x1800092b5  jmp     loc_1800093ED
0x1800092ba  cmp     ecx, 80070070h
0x1800092c0  jz      short loc_1800092FC
0x1800092c2  cmp     ecx, 8007007Ah
0x1800092c8  jz      short loc_1800092F2
0x1800092ca  cmp     ecx, 8007007Bh
0x1800092d0  jz      short loc_1800092E8
0x1800092d2  cmp     ecx, 8007007Eh
0x1800092d8  jnz     loc_180009395
0x1800092de  mov     ecx, 0C0000135h
0x1800092e3  jmp     loc_1800093ED
0x1800092e8  mov     ecx, 0C0000033h
0x1800092ed  jmp     loc_1800093ED
0x1800092f2  mov     ecx, 0C0000023h
0x1800092f7  jmp     loc_1800093ED
0x1800092fc  mov     ecx, 0C000007Fh
0x180009301  jmp     loc_1800093ED
0x180009306  mov     ecx, 80000005h
0x18000930b  jmp     loc_1800093ED
0x180009310  mov     eax, 8007047Eh
0x180009315  cmp     ecx, eax
0x180009317  jg      short loc_180009379
0x180009319  jz      short loc_180009372
0x18000931b  cmp     ecx, 80070216h
0x180009321  jz      short loc_18000936B
0x180009323  cmp     ecx, 8007023Eh
0x180009329  jz      short loc_180009361
0x18000932b  cmp     ecx, 80070246h
0x180009331  jz      short loc_180009357
0x180009333  cmp     ecx, 80070247h
0x180009339  jz      short loc_18000934D
0x18000933b  cmp     ecx, 80070272h
0x180009341  jnz     short loc_180009395
0x180009343  mov     ecx, 0C0000273h
0x180009348  jmp     loc_1800093ED
0x18000934d  mov     ecx, 0C0000163h
0x180009352  jmp     loc_1800093ED
0x180009357  mov     ecx, 0C0000161h
0x18000935c  jmp     loc_1800093ED
0x180009361  mov     ecx, 0C0000025h
0x180009366  jmp     loc_1800093ED
0x18000936b  mov     ecx, 0C0000095h
0x180009370  jmp     short loc_1800093ED
0x180009372  mov     ecx, 0C0000059h
0x180009377  jmp     short loc_1800093ED
0x180009379  cmp     ecx, 8007050Ch
0x18000937f  jz      short loc_1800093E8
0x180009381  cmp     ecx, 8007054Fh
0x180009387  jz      short loc_1800093E1
0x180009389  cmp     ecx, 800705B9h
0x18000938f  jz      short loc_1800093DA
0x180009391  test    ecx, ecx
0x180009393  jz      short loc_1800093D6
0x180009395  bt      ecx, 1Ch
0x180009399  jnb     short loc_1800093A1
0x18000939b  btr     ecx, 1Ch
0x18000939f  jmp     short loc_1800093ED
0x1800093a1  mov     eax, ecx
0x1800093a3  and     eax, 1FFF0000h
0x1800093a8  cmp     eax, 70000h
0x1800093ad  jnz     short loc_1800093C0
0x1800093af  movzx   ecx, cx
0x1800093b2  mov     eax, ecx
0x1800093b4  or      eax, 0C0070000h
0x1800093b9  test    ecx, ecx
0x1800093bb  cmovnz  ecx, eax
0x1800093be  jmp     short loc_1800093ED
0x1800093c0  cmp     eax, 90000h
0x1800093c5  jnz     short loc_1800093E1
0x1800093c7  test    ecx, ecx
0x1800093c9  jle     short loc_1800093ED
0x1800093cb  movzx   ecx, cx
0x1800093ce  or      ecx, 0C0090000h
0x1800093d4  jmp     short loc_1800093ED
0x1800093d6  xor     ecx, ecx
0x1800093d8  jmp     short loc_1800093ED
0x1800093da  mov     ecx, 0C000A083h
0x1800093df  jmp     short loc_1800093ED
0x1800093e1  mov     ecx, 0C00000E5h
0x1800093e6  jmp     short loc_1800093ED
0x1800093e8  mov     ecx, 0C000042Bh
0x1800093ed  mov     eax, ecx
0x1800093ef  retn
```

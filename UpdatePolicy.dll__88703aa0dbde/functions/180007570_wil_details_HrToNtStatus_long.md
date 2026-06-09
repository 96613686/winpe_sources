# wil::details::HrToNtStatus(long)

- ea: `0x180007570`
- end: `0x18000772f`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b8c`
- `0x1800060ec`
- `0x180006808`
- `0x180006a30`
- `0x180006ea8`
- `0x1800072b0`
- `0x180007738`
- `0x180008a80`
- `0x1800163af`
- `0x180016425`
- `0x1800164e8`
- `0x18001655e`

## callees

- `0x180007570`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // ecx
  int v2; // eax
  unsigned int v3; // eax

  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return (unsigned int)-1073741595;
        case 0x800705B9:
          return (unsigned int)-1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return (unsigned int)-1073741735;
        case 0x80070216:
          return (unsigned int)-1073741675;
        case 0x8007023E:
          return (unsigned int)-1073741787;
        case 0x80070246:
          return (unsigned int)-1073741471;
        case 0x80070247:
          return (unsigned int)-1073741469;
        case 0x80070272:
          return (unsigned int)-1073741197;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
      return (unsigned int)-2147483643;
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          return (unsigned int)-1073741697;
        case 0x8007007A:
          return (unsigned int)-1073741789;
        case 0x8007007B:
          return (unsigned int)-1073741773;
        case 0x8007007E:
          return (unsigned int)-1073741515;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          return (unsigned int)-1073741811;
        case 0x80004005:
          return (unsigned int)-1073741823;
        case 0x80070001:
          return (unsigned int)-1073741822;
        case 0x80070002:
          return (unsigned int)-1073741772;
        case 0x80070003:
          return (unsigned int)-1073741766;
        case 0x8007000E:
          return (unsigned int)-1073741801;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
    return (unsigned int)this & 0xEFFFFFFF;
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    v2 = (unsigned __int16)this;
    v1 = (unsigned __int16)this | 0xC0070000;
    if ( !v2 )
      return 0;
    return v1;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-1073741595;
  v3 = (unsigned __int16)this | 0xC0090000;
  if ( (int)this <= 0 )
    return (unsigned int)this;
  return v3;
}

```

## disassembly

```asm
0x180007570  mov     eax, 800700EAh
0x180007575  cmp     ecx, eax
0x180007577  jg      loc_18000764C
0x18000757d  jz      loc_180007642
0x180007583  mov     eax, 80070057h
0x180007588  cmp     ecx, eax
0x18000758a  jg      short loc_1800075F6
0x18000758c  jz      short loc_1800075EC
0x18000758e  cmp     ecx, 80004005h
0x180007594  jz      short loc_1800075E2
0x180007596  cmp     ecx, 80070001h
0x18000759c  jz      short loc_1800075D8
0x18000759e  cmp     ecx, 80070002h
0x1800075a4  jz      short loc_1800075CE
0x1800075a6  cmp     ecx, 80070003h
0x1800075ac  jz      short loc_1800075C4
0x1800075ae  cmp     ecx, 8007000Eh
0x1800075b4  jnz     loc_1800076D1
0x1800075ba  mov     ecx, 0C0000017h
0x1800075bf  jmp     loc_18000772C
0x1800075c4  mov     ecx, 0C000003Ah
0x1800075c9  jmp     loc_18000772C
0x1800075ce  mov     ecx, 0C0000034h
0x1800075d3  jmp     loc_18000772C
0x1800075d8  mov     ecx, 0C0000002h
0x1800075dd  jmp     loc_18000772C
0x1800075e2  mov     ecx, 0C0000001h
0x1800075e7  jmp     loc_18000772C
0x1800075ec  mov     ecx, 0C000000Dh
0x1800075f1  jmp     loc_18000772C
0x1800075f6  cmp     ecx, 80070070h
0x1800075fc  jz      short loc_180007638
0x1800075fe  cmp     ecx, 8007007Ah
0x180007604  jz      short loc_18000762E
0x180007606  cmp     ecx, 8007007Bh
0x18000760c  jz      short loc_180007624
0x18000760e  cmp     ecx, 8007007Eh
0x180007614  jnz     loc_1800076D1
0x18000761a  mov     ecx, 0C0000135h
0x18000761f  jmp     loc_18000772C
0x180007624  mov     ecx, 0C0000033h
0x180007629  jmp     loc_18000772C
0x18000762e  mov     ecx, 0C0000023h
0x180007633  jmp     loc_18000772C
0x180007638  mov     ecx, 0C000007Fh
0x18000763d  jmp     loc_18000772C
0x180007642  mov     ecx, 80000005h
0x180007647  jmp     loc_18000772C
0x18000764c  mov     eax, 8007047Eh
0x180007651  cmp     ecx, eax
0x180007653  jg      short loc_1800076B5
0x180007655  jz      short loc_1800076AE
0x180007657  cmp     ecx, 80070216h
0x18000765d  jz      short loc_1800076A7
0x18000765f  cmp     ecx, 8007023Eh
0x180007665  jz      short loc_18000769D
0x180007667  cmp     ecx, 80070246h
0x18000766d  jz      short loc_180007693
0x18000766f  cmp     ecx, 80070247h
0x180007675  jz      short loc_180007689
0x180007677  cmp     ecx, 80070272h
0x18000767d  jnz     short loc_1800076D1
0x18000767f  mov     ecx, 0C0000273h
0x180007684  jmp     loc_18000772C
0x180007689  mov     ecx, 0C0000163h
0x18000768e  jmp     loc_18000772C
0x180007693  mov     ecx, 0C0000161h
0x180007698  jmp     loc_18000772C
0x18000769d  mov     ecx, 0C0000025h
0x1800076a2  jmp     loc_18000772C
0x1800076a7  mov     ecx, 0C0000095h
0x1800076ac  jmp     short loc_18000772C
0x1800076ae  mov     ecx, 0C0000059h
0x1800076b3  jmp     short loc_18000772C
0x1800076b5  cmp     ecx, 8007050Ch
0x1800076bb  jz      short loc_180007727
0x1800076bd  cmp     ecx, 8007054Fh
0x1800076c3  jz      short loc_180007720
0x1800076c5  cmp     ecx, 800705B9h
0x1800076cb  jz      short loc_180007719
0x1800076cd  test    ecx, ecx
0x1800076cf  jz      short loc_180007715
0x1800076d1  bt      ecx, 1Ch
0x1800076d5  jnb     short loc_1800076DD
0x1800076d7  btr     ecx, 1Ch
0x1800076db  jmp     short loc_18000772C
0x1800076dd  mov     eax, ecx
0x1800076df  and     eax, 1FFF0000h
0x1800076e4  cmp     eax, 70000h
0x1800076e9  jnz     short loc_1800076FD
0x1800076eb  movzx   eax, cx
0x1800076ee  mov     ecx, eax
0x1800076f0  or      ecx, 0C0070000h
0x1800076f6  test    eax, eax
0x1800076f8  cmovz   ecx, eax
0x1800076fb  jmp     short loc_18000772C
0x1800076fd  cmp     eax, 90000h
0x180007702  jnz     short loc_180007720
0x180007704  movzx   eax, cx
0x180007707  or      eax, 0C0090000h
0x18000770c  test    ecx, ecx
0x18000770e  cmovle  eax, ecx
0x180007711  mov     ecx, eax
0x180007713  jmp     short loc_18000772C
0x180007715  xor     ecx, ecx
0x180007717  jmp     short loc_18000772C
0x180007719  mov     ecx, 0C000A083h
0x18000771e  jmp     short loc_18000772C
0x180007720  mov     ecx, 0C00000E5h
0x180007725  jmp     short loc_18000772C
0x180007727  mov     ecx, 0C000042Bh
0x18000772c  mov     eax, ecx
0x18000772e  retn
```

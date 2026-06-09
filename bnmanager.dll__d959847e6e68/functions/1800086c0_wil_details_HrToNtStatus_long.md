# wil::details::HrToNtStatus(long)

- ea: `0x1800086c0`
- end: `0x18000887c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028c4`
- `0x180002964`
- `0x1800029b4`
- `0x180002a74`
- `0x180007bc8`
- `0x1800088d8`

## callees

- `0x1800086c0`

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
0x1800086c0  mov     eax, 800700EAh
0x1800086c5  cmp     ecx, eax
0x1800086c7  jg      loc_18000879C
0x1800086cd  jz      loc_180008792
0x1800086d3  mov     eax, 80070057h
0x1800086d8  cmp     ecx, eax
0x1800086da  jg      short loc_180008746
0x1800086dc  jz      short loc_18000873C
0x1800086de  cmp     ecx, 80004005h
0x1800086e4  jz      short loc_180008732
0x1800086e6  cmp     ecx, 80070001h
0x1800086ec  jz      short loc_180008728
0x1800086ee  cmp     ecx, 80070002h
0x1800086f4  jz      short loc_18000871E
0x1800086f6  cmp     ecx, 80070003h
0x1800086fc  jz      short loc_180008714
0x1800086fe  cmp     ecx, 8007000Eh
0x180008704  jnz     loc_180008821
0x18000870a  mov     ecx, 0C0000017h
0x18000870f  jmp     loc_180008879
0x180008714  mov     ecx, 0C000003Ah
0x180008719  jmp     loc_180008879
0x18000871e  mov     ecx, 0C0000034h
0x180008723  jmp     loc_180008879
0x180008728  mov     ecx, 0C0000002h
0x18000872d  jmp     loc_180008879
0x180008732  mov     ecx, 0C0000001h
0x180008737  jmp     loc_180008879
0x18000873c  mov     ecx, 0C000000Dh
0x180008741  jmp     loc_180008879
0x180008746  cmp     ecx, 80070070h
0x18000874c  jz      short loc_180008788
0x18000874e  cmp     ecx, 8007007Ah
0x180008754  jz      short loc_18000877E
0x180008756  cmp     ecx, 8007007Bh
0x18000875c  jz      short loc_180008774
0x18000875e  cmp     ecx, 8007007Eh
0x180008764  jnz     loc_180008821
0x18000876a  mov     ecx, 0C0000135h
0x18000876f  jmp     loc_180008879
0x180008774  mov     ecx, 0C0000033h
0x180008779  jmp     loc_180008879
0x18000877e  mov     ecx, 0C0000023h
0x180008783  jmp     loc_180008879
0x180008788  mov     ecx, 0C000007Fh
0x18000878d  jmp     loc_180008879
0x180008792  mov     ecx, 80000005h
0x180008797  jmp     loc_180008879
0x18000879c  mov     eax, 8007047Eh
0x1800087a1  cmp     ecx, eax
0x1800087a3  jg      short loc_180008805
0x1800087a5  jz      short loc_1800087FE
0x1800087a7  cmp     ecx, 80070216h
0x1800087ad  jz      short loc_1800087F7
0x1800087af  cmp     ecx, 8007023Eh
0x1800087b5  jz      short loc_1800087ED
0x1800087b7  cmp     ecx, 80070246h
0x1800087bd  jz      short loc_1800087E3
0x1800087bf  cmp     ecx, 80070247h
0x1800087c5  jz      short loc_1800087D9
0x1800087c7  cmp     ecx, 80070272h
0x1800087cd  jnz     short loc_180008821
0x1800087cf  mov     ecx, 0C0000273h
0x1800087d4  jmp     loc_180008879
0x1800087d9  mov     ecx, 0C0000163h
0x1800087de  jmp     loc_180008879
0x1800087e3  mov     ecx, 0C0000161h
0x1800087e8  jmp     loc_180008879
0x1800087ed  mov     ecx, 0C0000025h
0x1800087f2  jmp     loc_180008879
0x1800087f7  mov     ecx, 0C0000095h
0x1800087fc  jmp     short loc_180008879
0x1800087fe  mov     ecx, 0C0000059h
0x180008803  jmp     short loc_180008879
0x180008805  cmp     ecx, 8007050Ch
0x18000880b  jz      short loc_180008874
0x18000880d  cmp     ecx, 8007054Fh
0x180008813  jz      short loc_18000886D
0x180008815  cmp     ecx, 800705B9h
0x18000881b  jz      short loc_180008866
0x18000881d  test    ecx, ecx
0x18000881f  jz      short loc_180008862
0x180008821  bt      ecx, 1Ch
0x180008825  jnb     short loc_18000882D
0x180008827  btr     ecx, 1Ch
0x18000882b  jmp     short loc_180008879
0x18000882d  mov     eax, ecx
0x18000882f  and     eax, 1FFF0000h
0x180008834  cmp     eax, 70000h
0x180008839  jnz     short loc_18000884C
0x18000883b  movzx   ecx, cx
0x18000883e  mov     eax, ecx
0x180008840  or      eax, 0C0070000h
0x180008845  test    ecx, ecx
0x180008847  cmovnz  ecx, eax
0x18000884a  jmp     short loc_180008879
0x18000884c  cmp     eax, 90000h
0x180008851  jnz     short loc_18000886D
0x180008853  test    ecx, ecx
0x180008855  jle     short loc_180008879
0x180008857  movzx   ecx, cx
0x18000885a  or      ecx, 0C0090000h
0x180008860  jmp     short loc_180008879
0x180008862  xor     ecx, ecx
0x180008864  jmp     short loc_180008879
0x180008866  mov     ecx, 0C000A083h
0x18000886b  jmp     short loc_180008879
0x18000886d  mov     ecx, 0C00000E5h
0x180008872  jmp     short loc_180008879
0x180008874  mov     ecx, 0C000042Bh
0x180008879  mov     eax, ecx
0x18000887b  retn
```

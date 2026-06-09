# wil::details::HrToNtStatus(long)

- ea: `0x18000680c`
- end: `0x1800069c8`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002764`
- `0x180002804`
- `0x180002854`
- `0x180002914`
- `0x1800055a8`
- `0x180006ae0`

## callees

- `0x18000680c`

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
0x18000680c  mov     eax, 800700EAh
0x180006811  cmp     ecx, eax
0x180006813  jg      loc_1800068E8
0x180006819  jz      loc_1800068DE
0x18000681f  mov     eax, 80070057h
0x180006824  cmp     ecx, eax
0x180006826  jg      short loc_180006892
0x180006828  jz      short loc_180006888
0x18000682a  cmp     ecx, 80004005h
0x180006830  jz      short loc_18000687E
0x180006832  cmp     ecx, 80070001h
0x180006838  jz      short loc_180006874
0x18000683a  cmp     ecx, 80070002h
0x180006840  jz      short loc_18000686A
0x180006842  cmp     ecx, 80070003h
0x180006848  jz      short loc_180006860
0x18000684a  cmp     ecx, 8007000Eh
0x180006850  jnz     loc_18000696D
0x180006856  mov     ecx, 0C0000017h
0x18000685b  jmp     loc_1800069C5
0x180006860  mov     ecx, 0C000003Ah
0x180006865  jmp     loc_1800069C5
0x18000686a  mov     ecx, 0C0000034h
0x18000686f  jmp     loc_1800069C5
0x180006874  mov     ecx, 0C0000002h
0x180006879  jmp     loc_1800069C5
0x18000687e  mov     ecx, 0C0000001h
0x180006883  jmp     loc_1800069C5
0x180006888  mov     ecx, 0C000000Dh
0x18000688d  jmp     loc_1800069C5
0x180006892  cmp     ecx, 80070070h
0x180006898  jz      short loc_1800068D4
0x18000689a  cmp     ecx, 8007007Ah
0x1800068a0  jz      short loc_1800068CA
0x1800068a2  cmp     ecx, 8007007Bh
0x1800068a8  jz      short loc_1800068C0
0x1800068aa  cmp     ecx, 8007007Eh
0x1800068b0  jnz     loc_18000696D
0x1800068b6  mov     ecx, 0C0000135h
0x1800068bb  jmp     loc_1800069C5
0x1800068c0  mov     ecx, 0C0000033h
0x1800068c5  jmp     loc_1800069C5
0x1800068ca  mov     ecx, 0C0000023h
0x1800068cf  jmp     loc_1800069C5
0x1800068d4  mov     ecx, 0C000007Fh
0x1800068d9  jmp     loc_1800069C5
0x1800068de  mov     ecx, 80000005h
0x1800068e3  jmp     loc_1800069C5
0x1800068e8  mov     eax, 8007047Eh
0x1800068ed  cmp     ecx, eax
0x1800068ef  jg      short loc_180006951
0x1800068f1  jz      short loc_18000694A
0x1800068f3  cmp     ecx, 80070216h
0x1800068f9  jz      short loc_180006943
0x1800068fb  cmp     ecx, 8007023Eh
0x180006901  jz      short loc_180006939
0x180006903  cmp     ecx, 80070246h
0x180006909  jz      short loc_18000692F
0x18000690b  cmp     ecx, 80070247h
0x180006911  jz      short loc_180006925
0x180006913  cmp     ecx, 80070272h
0x180006919  jnz     short loc_18000696D
0x18000691b  mov     ecx, 0C0000273h
0x180006920  jmp     loc_1800069C5
0x180006925  mov     ecx, 0C0000163h
0x18000692a  jmp     loc_1800069C5
0x18000692f  mov     ecx, 0C0000161h
0x180006934  jmp     loc_1800069C5
0x180006939  mov     ecx, 0C0000025h
0x18000693e  jmp     loc_1800069C5
0x180006943  mov     ecx, 0C0000095h
0x180006948  jmp     short loc_1800069C5
0x18000694a  mov     ecx, 0C0000059h
0x18000694f  jmp     short loc_1800069C5
0x180006951  cmp     ecx, 8007050Ch
0x180006957  jz      short loc_1800069C0
0x180006959  cmp     ecx, 8007054Fh
0x18000695f  jz      short loc_1800069B9
0x180006961  cmp     ecx, 800705B9h
0x180006967  jz      short loc_1800069B2
0x180006969  test    ecx, ecx
0x18000696b  jz      short loc_1800069AE
0x18000696d  bt      ecx, 1Ch
0x180006971  jnb     short loc_180006979
0x180006973  btr     ecx, 1Ch
0x180006977  jmp     short loc_1800069C5
0x180006979  mov     eax, ecx
0x18000697b  and     eax, 1FFF0000h
0x180006980  cmp     eax, 70000h
0x180006985  jnz     short loc_180006998
0x180006987  movzx   ecx, cx
0x18000698a  mov     eax, ecx
0x18000698c  or      eax, 0C0070000h
0x180006991  test    ecx, ecx
0x180006993  cmovnz  ecx, eax
0x180006996  jmp     short loc_1800069C5
0x180006998  cmp     eax, 90000h
0x18000699d  jnz     short loc_1800069B9
0x18000699f  test    ecx, ecx
0x1800069a1  jle     short loc_1800069C5
0x1800069a3  movzx   ecx, cx
0x1800069a6  or      ecx, 0C0090000h
0x1800069ac  jmp     short loc_1800069C5
0x1800069ae  xor     ecx, ecx
0x1800069b0  jmp     short loc_1800069C5
0x1800069b2  mov     ecx, 0C000A083h
0x1800069b7  jmp     short loc_1800069C5
0x1800069b9  mov     ecx, 0C00000E5h
0x1800069be  jmp     short loc_1800069C5
0x1800069c0  mov     ecx, 0C000042Bh
0x1800069c5  mov     eax, ecx
0x1800069c7  retn
```

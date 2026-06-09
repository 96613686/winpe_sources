# wil::details::HrToNtStatus(long)

- ea: `0x1800196dc`
- end: `0x180019898`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180018124`
- `0x180018194`
- `0x18001820c`
- `0x18001825c`
- `0x180018e88`
- `0x1800199e0`

## callees

- `0x1800196dc`

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
0x1800196dc  mov     eax, 800700EAh
0x1800196e1  cmp     ecx, eax
0x1800196e3  jg      loc_1800197B8
0x1800196e9  jz      loc_1800197AE
0x1800196ef  mov     eax, 80070057h
0x1800196f4  cmp     ecx, eax
0x1800196f6  jg      short loc_180019762
0x1800196f8  jz      short loc_180019758
0x1800196fa  cmp     ecx, 80004005h
0x180019700  jz      short loc_18001974E
0x180019702  cmp     ecx, 80070001h
0x180019708  jz      short loc_180019744
0x18001970a  cmp     ecx, 80070002h
0x180019710  jz      short loc_18001973A
0x180019712  cmp     ecx, 80070003h
0x180019718  jz      short loc_180019730
0x18001971a  cmp     ecx, 8007000Eh
0x180019720  jnz     loc_18001983D
0x180019726  mov     ecx, 0C0000017h
0x18001972b  jmp     loc_180019895
0x180019730  mov     ecx, 0C000003Ah
0x180019735  jmp     loc_180019895
0x18001973a  mov     ecx, 0C0000034h
0x18001973f  jmp     loc_180019895
0x180019744  mov     ecx, 0C0000002h
0x180019749  jmp     loc_180019895
0x18001974e  mov     ecx, 0C0000001h
0x180019753  jmp     loc_180019895
0x180019758  mov     ecx, 0C000000Dh
0x18001975d  jmp     loc_180019895
0x180019762  cmp     ecx, 80070070h
0x180019768  jz      short loc_1800197A4
0x18001976a  cmp     ecx, 8007007Ah
0x180019770  jz      short loc_18001979A
0x180019772  cmp     ecx, 8007007Bh
0x180019778  jz      short loc_180019790
0x18001977a  cmp     ecx, 8007007Eh
0x180019780  jnz     loc_18001983D
0x180019786  mov     ecx, 0C0000135h
0x18001978b  jmp     loc_180019895
0x180019790  mov     ecx, 0C0000033h
0x180019795  jmp     loc_180019895
0x18001979a  mov     ecx, 0C0000023h
0x18001979f  jmp     loc_180019895
0x1800197a4  mov     ecx, 0C000007Fh
0x1800197a9  jmp     loc_180019895
0x1800197ae  mov     ecx, 80000005h
0x1800197b3  jmp     loc_180019895
0x1800197b8  mov     eax, 8007047Eh
0x1800197bd  cmp     ecx, eax
0x1800197bf  jg      short loc_180019821
0x1800197c1  jz      short loc_18001981A
0x1800197c3  cmp     ecx, 80070216h
0x1800197c9  jz      short loc_180019813
0x1800197cb  cmp     ecx, 8007023Eh
0x1800197d1  jz      short loc_180019809
0x1800197d3  cmp     ecx, 80070246h
0x1800197d9  jz      short loc_1800197FF
0x1800197db  cmp     ecx, 80070247h
0x1800197e1  jz      short loc_1800197F5
0x1800197e3  cmp     ecx, 80070272h
0x1800197e9  jnz     short loc_18001983D
0x1800197eb  mov     ecx, 0C0000273h
0x1800197f0  jmp     loc_180019895
0x1800197f5  mov     ecx, 0C0000163h
0x1800197fa  jmp     loc_180019895
0x1800197ff  mov     ecx, 0C0000161h
0x180019804  jmp     loc_180019895
0x180019809  mov     ecx, 0C0000025h
0x18001980e  jmp     loc_180019895
0x180019813  mov     ecx, 0C0000095h
0x180019818  jmp     short loc_180019895
0x18001981a  mov     ecx, 0C0000059h
0x18001981f  jmp     short loc_180019895
0x180019821  cmp     ecx, 8007050Ch
0x180019827  jz      short loc_180019890
0x180019829  cmp     ecx, 8007054Fh
0x18001982f  jz      short loc_180019889
0x180019831  cmp     ecx, 800705B9h
0x180019837  jz      short loc_180019882
0x180019839  test    ecx, ecx
0x18001983b  jz      short loc_18001987E
0x18001983d  bt      ecx, 1Ch
0x180019841  jnb     short loc_180019849
0x180019843  btr     ecx, 1Ch
0x180019847  jmp     short loc_180019895
0x180019849  mov     eax, ecx
0x18001984b  and     eax, 1FFF0000h
0x180019850  cmp     eax, 70000h
0x180019855  jnz     short loc_180019868
0x180019857  movzx   ecx, cx
0x18001985a  mov     eax, ecx
0x18001985c  or      eax, 0C0070000h
0x180019861  test    ecx, ecx
0x180019863  cmovnz  ecx, eax
0x180019866  jmp     short loc_180019895
0x180019868  cmp     eax, 90000h
0x18001986d  jnz     short loc_180019889
0x18001986f  test    ecx, ecx
0x180019871  jle     short loc_180019895
0x180019873  movzx   ecx, cx
0x180019876  or      ecx, 0C0090000h
0x18001987c  jmp     short loc_180019895
0x18001987e  xor     ecx, ecx
0x180019880  jmp     short loc_180019895
0x180019882  mov     ecx, 0C000A083h
0x180019887  jmp     short loc_180019895
0x180019889  mov     ecx, 0C00000E5h
0x18001988e  jmp     short loc_180019895
0x180019890  mov     ecx, 0C000042Bh
0x180019895  mov     eax, ecx
0x180019897  retn
```

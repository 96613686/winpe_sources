# wil::details::HrToNtStatus(long)

- ea: `0x14000a5cc`
- end: `0x14000a788`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140007d70`
- `0x140007e10`
- `0x140007e60`
- `0x140007f20`
- `0x140009ba8`
- `0x14000a790`

## callees

- `0x14000a5cc`

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
0x14000a5cc  mov     eax, 800700EAh
0x14000a5d1  cmp     ecx, eax
0x14000a5d3  jg      loc_14000A6A8
0x14000a5d9  jz      loc_14000A69E
0x14000a5df  mov     eax, 80070057h
0x14000a5e4  cmp     ecx, eax
0x14000a5e6  jg      short loc_14000A652
0x14000a5e8  jz      short loc_14000A648
0x14000a5ea  cmp     ecx, 80004005h
0x14000a5f0  jz      short loc_14000A63E
0x14000a5f2  cmp     ecx, 80070001h
0x14000a5f8  jz      short loc_14000A634
0x14000a5fa  cmp     ecx, 80070002h
0x14000a600  jz      short loc_14000A62A
0x14000a602  cmp     ecx, 80070003h
0x14000a608  jz      short loc_14000A620
0x14000a60a  cmp     ecx, 8007000Eh
0x14000a610  jnz     loc_14000A72D
0x14000a616  mov     ecx, 0C0000017h
0x14000a61b  jmp     loc_14000A785
0x14000a620  mov     ecx, 0C000003Ah
0x14000a625  jmp     loc_14000A785
0x14000a62a  mov     ecx, 0C0000034h
0x14000a62f  jmp     loc_14000A785
0x14000a634  mov     ecx, 0C0000002h
0x14000a639  jmp     loc_14000A785
0x14000a63e  mov     ecx, 0C0000001h
0x14000a643  jmp     loc_14000A785
0x14000a648  mov     ecx, 0C000000Dh
0x14000a64d  jmp     loc_14000A785
0x14000a652  cmp     ecx, 80070070h
0x14000a658  jz      short loc_14000A694
0x14000a65a  cmp     ecx, 8007007Ah
0x14000a660  jz      short loc_14000A68A
0x14000a662  cmp     ecx, 8007007Bh
0x14000a668  jz      short loc_14000A680
0x14000a66a  cmp     ecx, 8007007Eh
0x14000a670  jnz     loc_14000A72D
0x14000a676  mov     ecx, 0C0000135h
0x14000a67b  jmp     loc_14000A785
0x14000a680  mov     ecx, 0C0000033h
0x14000a685  jmp     loc_14000A785
0x14000a68a  mov     ecx, 0C0000023h
0x14000a68f  jmp     loc_14000A785
0x14000a694  mov     ecx, 0C000007Fh
0x14000a699  jmp     loc_14000A785
0x14000a69e  mov     ecx, 80000005h
0x14000a6a3  jmp     loc_14000A785
0x14000a6a8  mov     eax, 8007047Eh
0x14000a6ad  cmp     ecx, eax
0x14000a6af  jg      short loc_14000A711
0x14000a6b1  jz      short loc_14000A70A
0x14000a6b3  cmp     ecx, 80070216h
0x14000a6b9  jz      short loc_14000A703
0x14000a6bb  cmp     ecx, 8007023Eh
0x14000a6c1  jz      short loc_14000A6F9
0x14000a6c3  cmp     ecx, 80070246h
0x14000a6c9  jz      short loc_14000A6EF
0x14000a6cb  cmp     ecx, 80070247h
0x14000a6d1  jz      short loc_14000A6E5
0x14000a6d3  cmp     ecx, 80070272h
0x14000a6d9  jnz     short loc_14000A72D
0x14000a6db  mov     ecx, 0C0000273h
0x14000a6e0  jmp     loc_14000A785
0x14000a6e5  mov     ecx, 0C0000163h
0x14000a6ea  jmp     loc_14000A785
0x14000a6ef  mov     ecx, 0C0000161h
0x14000a6f4  jmp     loc_14000A785
0x14000a6f9  mov     ecx, 0C0000025h
0x14000a6fe  jmp     loc_14000A785
0x14000a703  mov     ecx, 0C0000095h
0x14000a708  jmp     short loc_14000A785
0x14000a70a  mov     ecx, 0C0000059h
0x14000a70f  jmp     short loc_14000A785
0x14000a711  cmp     ecx, 8007050Ch
0x14000a717  jz      short loc_14000A780
0x14000a719  cmp     ecx, 8007054Fh
0x14000a71f  jz      short loc_14000A779
0x14000a721  cmp     ecx, 800705B9h
0x14000a727  jz      short loc_14000A772
0x14000a729  test    ecx, ecx
0x14000a72b  jz      short loc_14000A76E
0x14000a72d  bt      ecx, 1Ch
0x14000a731  jnb     short loc_14000A739
0x14000a733  btr     ecx, 1Ch
0x14000a737  jmp     short loc_14000A785
0x14000a739  mov     eax, ecx
0x14000a73b  and     eax, 1FFF0000h
0x14000a740  cmp     eax, 70000h
0x14000a745  jnz     short loc_14000A758
0x14000a747  movzx   ecx, cx
0x14000a74a  mov     eax, ecx
0x14000a74c  or      eax, 0C0070000h
0x14000a751  test    ecx, ecx
0x14000a753  cmovnz  ecx, eax
0x14000a756  jmp     short loc_14000A785
0x14000a758  cmp     eax, 90000h
0x14000a75d  jnz     short loc_14000A779
0x14000a75f  test    ecx, ecx
0x14000a761  jle     short loc_14000A785
0x14000a763  movzx   ecx, cx
0x14000a766  or      ecx, 0C0090000h
0x14000a76c  jmp     short loc_14000A785
0x14000a76e  xor     ecx, ecx
0x14000a770  jmp     short loc_14000A785
0x14000a772  mov     ecx, 0C000A083h
0x14000a777  jmp     short loc_14000A785
0x14000a779  mov     ecx, 0C00000E5h
0x14000a77e  jmp     short loc_14000A785
0x14000a780  mov     ecx, 0C000042Bh
0x14000a785  mov     eax, ecx
0x14000a787  retn
```

# wil::details::HrToNtStatus(long)

- ea: `0x140001b30`
- end: `0x140001cef`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400016e8`
- `0x1400026e0`
- `0x14000463c`
- `0x140004778`
- `0x1400049fc`
- `0x140004a4c`

## callees

- `0x140001b30`

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
0x140001b30  mov     eax, 800700EAh
0x140001b35  cmp     ecx, eax
0x140001b37  jg      loc_140001C0C
0x140001b3d  jz      loc_140001C02
0x140001b43  mov     eax, 80070057h
0x140001b48  cmp     ecx, eax
0x140001b4a  jg      short loc_140001BB6
0x140001b4c  jz      short loc_140001BAC
0x140001b4e  cmp     ecx, 80004005h
0x140001b54  jz      short loc_140001BA2
0x140001b56  cmp     ecx, 80070001h
0x140001b5c  jz      short loc_140001B98
0x140001b5e  cmp     ecx, 80070002h
0x140001b64  jz      short loc_140001B8E
0x140001b66  cmp     ecx, 80070003h
0x140001b6c  jz      short loc_140001B84
0x140001b6e  cmp     ecx, 8007000Eh
0x140001b74  jnz     loc_140001C91
0x140001b7a  mov     ecx, 0C0000017h
0x140001b7f  jmp     loc_140001CEC
0x140001b84  mov     ecx, 0C000003Ah
0x140001b89  jmp     loc_140001CEC
0x140001b8e  mov     ecx, 0C0000034h
0x140001b93  jmp     loc_140001CEC
0x140001b98  mov     ecx, 0C0000002h
0x140001b9d  jmp     loc_140001CEC
0x140001ba2  mov     ecx, 0C0000001h
0x140001ba7  jmp     loc_140001CEC
0x140001bac  mov     ecx, 0C000000Dh
0x140001bb1  jmp     loc_140001CEC
0x140001bb6  cmp     ecx, 80070070h
0x140001bbc  jz      short loc_140001BF8
0x140001bbe  cmp     ecx, 8007007Ah
0x140001bc4  jz      short loc_140001BEE
0x140001bc6  cmp     ecx, 8007007Bh
0x140001bcc  jz      short loc_140001BE4
0x140001bce  cmp     ecx, 8007007Eh
0x140001bd4  jnz     loc_140001C91
0x140001bda  mov     ecx, 0C0000135h
0x140001bdf  jmp     loc_140001CEC
0x140001be4  mov     ecx, 0C0000033h
0x140001be9  jmp     loc_140001CEC
0x140001bee  mov     ecx, 0C0000023h
0x140001bf3  jmp     loc_140001CEC
0x140001bf8  mov     ecx, 0C000007Fh
0x140001bfd  jmp     loc_140001CEC
0x140001c02  mov     ecx, 80000005h
0x140001c07  jmp     loc_140001CEC
0x140001c0c  mov     eax, 8007047Eh
0x140001c11  cmp     ecx, eax
0x140001c13  jg      short loc_140001C75
0x140001c15  jz      short loc_140001C6E
0x140001c17  cmp     ecx, 80070216h
0x140001c1d  jz      short loc_140001C67
0x140001c1f  cmp     ecx, 8007023Eh
0x140001c25  jz      short loc_140001C5D
0x140001c27  cmp     ecx, 80070246h
0x140001c2d  jz      short loc_140001C53
0x140001c2f  cmp     ecx, 80070247h
0x140001c35  jz      short loc_140001C49
0x140001c37  cmp     ecx, 80070272h
0x140001c3d  jnz     short loc_140001C91
0x140001c3f  mov     ecx, 0C0000273h
0x140001c44  jmp     loc_140001CEC
0x140001c49  mov     ecx, 0C0000163h
0x140001c4e  jmp     loc_140001CEC
0x140001c53  mov     ecx, 0C0000161h
0x140001c58  jmp     loc_140001CEC
0x140001c5d  mov     ecx, 0C0000025h
0x140001c62  jmp     loc_140001CEC
0x140001c67  mov     ecx, 0C0000095h
0x140001c6c  jmp     short loc_140001CEC
0x140001c6e  mov     ecx, 0C0000059h
0x140001c73  jmp     short loc_140001CEC
0x140001c75  cmp     ecx, 8007050Ch
0x140001c7b  jz      short loc_140001CE7
0x140001c7d  cmp     ecx, 8007054Fh
0x140001c83  jz      short loc_140001CE0
0x140001c85  cmp     ecx, 800705B9h
0x140001c8b  jz      short loc_140001CD9
0x140001c8d  test    ecx, ecx
0x140001c8f  jz      short loc_140001CD5
0x140001c91  bt      ecx, 1Ch
0x140001c95  jnb     short loc_140001C9D
0x140001c97  btr     ecx, 1Ch
0x140001c9b  jmp     short loc_140001CEC
0x140001c9d  mov     eax, ecx
0x140001c9f  and     eax, 1FFF0000h
0x140001ca4  cmp     eax, 70000h
0x140001ca9  jnz     short loc_140001CBD
0x140001cab  movzx   eax, cx
0x140001cae  mov     ecx, eax
0x140001cb0  or      ecx, 0C0070000h
0x140001cb6  test    eax, eax
0x140001cb8  cmovz   ecx, eax
0x140001cbb  jmp     short loc_140001CEC
0x140001cbd  cmp     eax, 90000h
0x140001cc2  jnz     short loc_140001CE0
0x140001cc4  movzx   eax, cx
0x140001cc7  or      eax, 0C0090000h
0x140001ccc  test    ecx, ecx
0x140001cce  cmovle  eax, ecx
0x140001cd1  mov     ecx, eax
0x140001cd3  jmp     short loc_140001CEC
0x140001cd5  xor     ecx, ecx
0x140001cd7  jmp     short loc_140001CEC
0x140001cd9  mov     ecx, 0C000A083h
0x140001cde  jmp     short loc_140001CEC
0x140001ce0  mov     ecx, 0C00000E5h
0x140001ce5  jmp     short loc_140001CEC
0x140001ce7  mov     ecx, 0C000042Bh
0x140001cec  mov     eax, ecx
0x140001cee  retn
```

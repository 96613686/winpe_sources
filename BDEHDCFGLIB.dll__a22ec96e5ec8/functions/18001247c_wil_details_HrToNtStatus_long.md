# wil::details::HrToNtStatus(long)

- ea: `0x18001247c`
- end: `0x180012638`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ab0`
- `0x180010b50`
- `0x180010ba0`
- `0x180010c58`
- `0x180011a58`
- `0x180012640`

## callees

- `0x18001247c`

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
0x18001247c  mov     eax, 800700EAh
0x180012481  cmp     ecx, eax
0x180012483  jg      loc_180012558
0x180012489  jz      loc_18001254E
0x18001248f  mov     eax, 80070057h
0x180012494  cmp     ecx, eax
0x180012496  jg      short loc_180012502
0x180012498  jz      short loc_1800124F8
0x18001249a  cmp     ecx, 80004005h
0x1800124a0  jz      short loc_1800124EE
0x1800124a2  cmp     ecx, 80070001h
0x1800124a8  jz      short loc_1800124E4
0x1800124aa  cmp     ecx, 80070002h
0x1800124b0  jz      short loc_1800124DA
0x1800124b2  cmp     ecx, 80070003h
0x1800124b8  jz      short loc_1800124D0
0x1800124ba  cmp     ecx, 8007000Eh
0x1800124c0  jnz     loc_1800125DD
0x1800124c6  mov     ecx, 0C0000017h
0x1800124cb  jmp     loc_180012635
0x1800124d0  mov     ecx, 0C000003Ah
0x1800124d5  jmp     loc_180012635
0x1800124da  mov     ecx, 0C0000034h
0x1800124df  jmp     loc_180012635
0x1800124e4  mov     ecx, 0C0000002h
0x1800124e9  jmp     loc_180012635
0x1800124ee  mov     ecx, 0C0000001h
0x1800124f3  jmp     loc_180012635
0x1800124f8  mov     ecx, 0C000000Dh
0x1800124fd  jmp     loc_180012635
0x180012502  cmp     ecx, 80070070h
0x180012508  jz      short loc_180012544
0x18001250a  cmp     ecx, 8007007Ah
0x180012510  jz      short loc_18001253A
0x180012512  cmp     ecx, 8007007Bh
0x180012518  jz      short loc_180012530
0x18001251a  cmp     ecx, 8007007Eh
0x180012520  jnz     loc_1800125DD
0x180012526  mov     ecx, 0C0000135h
0x18001252b  jmp     loc_180012635
0x180012530  mov     ecx, 0C0000033h
0x180012535  jmp     loc_180012635
0x18001253a  mov     ecx, 0C0000023h
0x18001253f  jmp     loc_180012635
0x180012544  mov     ecx, 0C000007Fh
0x180012549  jmp     loc_180012635
0x18001254e  mov     ecx, 80000005h
0x180012553  jmp     loc_180012635
0x180012558  mov     eax, 8007047Eh
0x18001255d  cmp     ecx, eax
0x18001255f  jg      short loc_1800125C1
0x180012561  jz      short loc_1800125BA
0x180012563  cmp     ecx, 80070216h
0x180012569  jz      short loc_1800125B3
0x18001256b  cmp     ecx, 8007023Eh
0x180012571  jz      short loc_1800125A9
0x180012573  cmp     ecx, 80070246h
0x180012579  jz      short loc_18001259F
0x18001257b  cmp     ecx, 80070247h
0x180012581  jz      short loc_180012595
0x180012583  cmp     ecx, 80070272h
0x180012589  jnz     short loc_1800125DD
0x18001258b  mov     ecx, 0C0000273h
0x180012590  jmp     loc_180012635
0x180012595  mov     ecx, 0C0000163h
0x18001259a  jmp     loc_180012635
0x18001259f  mov     ecx, 0C0000161h
0x1800125a4  jmp     loc_180012635
0x1800125a9  mov     ecx, 0C0000025h
0x1800125ae  jmp     loc_180012635
0x1800125b3  mov     ecx, 0C0000095h
0x1800125b8  jmp     short loc_180012635
0x1800125ba  mov     ecx, 0C0000059h
0x1800125bf  jmp     short loc_180012635
0x1800125c1  cmp     ecx, 8007050Ch
0x1800125c7  jz      short loc_180012630
0x1800125c9  cmp     ecx, 8007054Fh
0x1800125cf  jz      short loc_180012629
0x1800125d1  cmp     ecx, 800705B9h
0x1800125d7  jz      short loc_180012622
0x1800125d9  test    ecx, ecx
0x1800125db  jz      short loc_18001261E
0x1800125dd  bt      ecx, 1Ch
0x1800125e1  jnb     short loc_1800125E9
0x1800125e3  btr     ecx, 1Ch
0x1800125e7  jmp     short loc_180012635
0x1800125e9  mov     eax, ecx
0x1800125eb  and     eax, 1FFF0000h
0x1800125f0  cmp     eax, 70000h
0x1800125f5  jnz     short loc_180012608
0x1800125f7  movzx   ecx, cx
0x1800125fa  mov     eax, ecx
0x1800125fc  or      eax, 0C0070000h
0x180012601  test    ecx, ecx
0x180012603  cmovnz  ecx, eax
0x180012606  jmp     short loc_180012635
0x180012608  cmp     eax, 90000h
0x18001260d  jnz     short loc_180012629
0x18001260f  test    ecx, ecx
0x180012611  jle     short loc_180012635
0x180012613  movzx   ecx, cx
0x180012616  or      ecx, 0C0090000h
0x18001261c  jmp     short loc_180012635
0x18001261e  xor     ecx, ecx
0x180012620  jmp     short loc_180012635
0x180012622  mov     ecx, 0C000A083h
0x180012627  jmp     short loc_180012635
0x180012629  mov     ecx, 0C00000E5h
0x18001262e  jmp     short loc_180012635
0x180012630  mov     ecx, 0C000042Bh
0x180012635  mov     eax, ecx
0x180012637  retn
```

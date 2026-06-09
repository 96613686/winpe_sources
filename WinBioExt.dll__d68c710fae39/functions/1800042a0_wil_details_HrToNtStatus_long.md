# wil::details::HrToNtStatus(long)

- ea: `0x1800042a0`
- end: `0x18000445c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024f0`
- `0x180002590`
- `0x1800025e0`
- `0x1800026a8`
- `0x180003878`
- `0x180004464`
- `0x180004b70`
- `0x1800065dc`
- `0x18000a1ff`
- `0x18000a26a`
- `0x18000a333`
- `0x18000a39e`

## callees

- `0x1800042a0`

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
0x1800042a0  mov     eax, 800700EAh
0x1800042a5  cmp     ecx, eax
0x1800042a7  jg      loc_18000437C
0x1800042ad  jz      loc_180004372
0x1800042b3  mov     eax, 80070057h
0x1800042b8  cmp     ecx, eax
0x1800042ba  jg      short loc_180004326
0x1800042bc  jz      short loc_18000431C
0x1800042be  cmp     ecx, 80004005h
0x1800042c4  jz      short loc_180004312
0x1800042c6  cmp     ecx, 80070001h
0x1800042cc  jz      short loc_180004308
0x1800042ce  cmp     ecx, 80070002h
0x1800042d4  jz      short loc_1800042FE
0x1800042d6  cmp     ecx, 80070003h
0x1800042dc  jz      short loc_1800042F4
0x1800042de  cmp     ecx, 8007000Eh
0x1800042e4  jnz     loc_180004401
0x1800042ea  mov     ecx, 0C0000017h
0x1800042ef  jmp     loc_180004459
0x1800042f4  mov     ecx, 0C000003Ah
0x1800042f9  jmp     loc_180004459
0x1800042fe  mov     ecx, 0C0000034h
0x180004303  jmp     loc_180004459
0x180004308  mov     ecx, 0C0000002h
0x18000430d  jmp     loc_180004459
0x180004312  mov     ecx, 0C0000001h
0x180004317  jmp     loc_180004459
0x18000431c  mov     ecx, 0C000000Dh
0x180004321  jmp     loc_180004459
0x180004326  cmp     ecx, 80070070h
0x18000432c  jz      short loc_180004368
0x18000432e  cmp     ecx, 8007007Ah
0x180004334  jz      short loc_18000435E
0x180004336  cmp     ecx, 8007007Bh
0x18000433c  jz      short loc_180004354
0x18000433e  cmp     ecx, 8007007Eh
0x180004344  jnz     loc_180004401
0x18000434a  mov     ecx, 0C0000135h
0x18000434f  jmp     loc_180004459
0x180004354  mov     ecx, 0C0000033h
0x180004359  jmp     loc_180004459
0x18000435e  mov     ecx, 0C0000023h
0x180004363  jmp     loc_180004459
0x180004368  mov     ecx, 0C000007Fh
0x18000436d  jmp     loc_180004459
0x180004372  mov     ecx, 80000005h
0x180004377  jmp     loc_180004459
0x18000437c  mov     eax, 8007047Eh
0x180004381  cmp     ecx, eax
0x180004383  jg      short loc_1800043E5
0x180004385  jz      short loc_1800043DE
0x180004387  cmp     ecx, 80070216h
0x18000438d  jz      short loc_1800043D7
0x18000438f  cmp     ecx, 8007023Eh
0x180004395  jz      short loc_1800043CD
0x180004397  cmp     ecx, 80070246h
0x18000439d  jz      short loc_1800043C3
0x18000439f  cmp     ecx, 80070247h
0x1800043a5  jz      short loc_1800043B9
0x1800043a7  cmp     ecx, 80070272h
0x1800043ad  jnz     short loc_180004401
0x1800043af  mov     ecx, 0C0000273h
0x1800043b4  jmp     loc_180004459
0x1800043b9  mov     ecx, 0C0000163h
0x1800043be  jmp     loc_180004459
0x1800043c3  mov     ecx, 0C0000161h
0x1800043c8  jmp     loc_180004459
0x1800043cd  mov     ecx, 0C0000025h
0x1800043d2  jmp     loc_180004459
0x1800043d7  mov     ecx, 0C0000095h
0x1800043dc  jmp     short loc_180004459
0x1800043de  mov     ecx, 0C0000059h
0x1800043e3  jmp     short loc_180004459
0x1800043e5  cmp     ecx, 8007050Ch
0x1800043eb  jz      short loc_180004454
0x1800043ed  cmp     ecx, 8007054Fh
0x1800043f3  jz      short loc_18000444D
0x1800043f5  cmp     ecx, 800705B9h
0x1800043fb  jz      short loc_180004446
0x1800043fd  test    ecx, ecx
0x1800043ff  jz      short loc_180004442
0x180004401  bt      ecx, 1Ch
0x180004405  jnb     short loc_18000440D
0x180004407  btr     ecx, 1Ch
0x18000440b  jmp     short loc_180004459
0x18000440d  mov     eax, ecx
0x18000440f  and     eax, 1FFF0000h
0x180004414  cmp     eax, 70000h
0x180004419  jnz     short loc_18000442C
0x18000441b  movzx   ecx, cx
0x18000441e  mov     eax, ecx
0x180004420  or      eax, 0C0070000h
0x180004425  test    ecx, ecx
0x180004427  cmovnz  ecx, eax
0x18000442a  jmp     short loc_180004459
0x18000442c  cmp     eax, 90000h
0x180004431  jnz     short loc_18000444D
0x180004433  test    ecx, ecx
0x180004435  jle     short loc_180004459
0x180004437  movzx   ecx, cx
0x18000443a  or      ecx, 0C0090000h
0x180004440  jmp     short loc_180004459
0x180004442  xor     ecx, ecx
0x180004444  jmp     short loc_180004459
0x180004446  mov     ecx, 0C000A083h
0x18000444b  jmp     short loc_180004459
0x18000444d  mov     ecx, 0C00000E5h
0x180004452  jmp     short loc_180004459
0x180004454  mov     ecx, 0C000042Bh
0x180004459  mov     eax, ecx
0x18000445b  retn
```

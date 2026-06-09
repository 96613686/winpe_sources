# wil::details::HrToNtStatus(long)

- ea: `0x18000428c`
- end: `0x180004448`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002820`
- `0x1800028c0`
- `0x180002910`
- `0x1800029d0`
- `0x180003868`
- `0x180004450`

## callees

- `0x18000428c`

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
0x18000428c  mov     eax, 800700EAh
0x180004291  cmp     ecx, eax
0x180004293  jg      loc_180004368
0x180004299  jz      loc_18000435E
0x18000429f  mov     eax, 80070057h
0x1800042a4  cmp     ecx, eax
0x1800042a6  jg      short loc_180004312
0x1800042a8  jz      short loc_180004308
0x1800042aa  cmp     ecx, 80004005h
0x1800042b0  jz      short loc_1800042FE
0x1800042b2  cmp     ecx, 80070001h
0x1800042b8  jz      short loc_1800042F4
0x1800042ba  cmp     ecx, 80070002h
0x1800042c0  jz      short loc_1800042EA
0x1800042c2  cmp     ecx, 80070003h
0x1800042c8  jz      short loc_1800042E0
0x1800042ca  cmp     ecx, 8007000Eh
0x1800042d0  jnz     loc_1800043ED
0x1800042d6  mov     ecx, 0C0000017h
0x1800042db  jmp     loc_180004445
0x1800042e0  mov     ecx, 0C000003Ah
0x1800042e5  jmp     loc_180004445
0x1800042ea  mov     ecx, 0C0000034h
0x1800042ef  jmp     loc_180004445
0x1800042f4  mov     ecx, 0C0000002h
0x1800042f9  jmp     loc_180004445
0x1800042fe  mov     ecx, 0C0000001h
0x180004303  jmp     loc_180004445
0x180004308  mov     ecx, 0C000000Dh
0x18000430d  jmp     loc_180004445
0x180004312  cmp     ecx, 80070070h
0x180004318  jz      short loc_180004354
0x18000431a  cmp     ecx, 8007007Ah
0x180004320  jz      short loc_18000434A
0x180004322  cmp     ecx, 8007007Bh
0x180004328  jz      short loc_180004340
0x18000432a  cmp     ecx, 8007007Eh
0x180004330  jnz     loc_1800043ED
0x180004336  mov     ecx, 0C0000135h
0x18000433b  jmp     loc_180004445
0x180004340  mov     ecx, 0C0000033h
0x180004345  jmp     loc_180004445
0x18000434a  mov     ecx, 0C0000023h
0x18000434f  jmp     loc_180004445
0x180004354  mov     ecx, 0C000007Fh
0x180004359  jmp     loc_180004445
0x18000435e  mov     ecx, 80000005h
0x180004363  jmp     loc_180004445
0x180004368  mov     eax, 8007047Eh
0x18000436d  cmp     ecx, eax
0x18000436f  jg      short loc_1800043D1
0x180004371  jz      short loc_1800043CA
0x180004373  cmp     ecx, 80070216h
0x180004379  jz      short loc_1800043C3
0x18000437b  cmp     ecx, 8007023Eh
0x180004381  jz      short loc_1800043B9
0x180004383  cmp     ecx, 80070246h
0x180004389  jz      short loc_1800043AF
0x18000438b  cmp     ecx, 80070247h
0x180004391  jz      short loc_1800043A5
0x180004393  cmp     ecx, 80070272h
0x180004399  jnz     short loc_1800043ED
0x18000439b  mov     ecx, 0C0000273h
0x1800043a0  jmp     loc_180004445
0x1800043a5  mov     ecx, 0C0000163h
0x1800043aa  jmp     loc_180004445
0x1800043af  mov     ecx, 0C0000161h
0x1800043b4  jmp     loc_180004445
0x1800043b9  mov     ecx, 0C0000025h
0x1800043be  jmp     loc_180004445
0x1800043c3  mov     ecx, 0C0000095h
0x1800043c8  jmp     short loc_180004445
0x1800043ca  mov     ecx, 0C0000059h
0x1800043cf  jmp     short loc_180004445
0x1800043d1  cmp     ecx, 8007050Ch
0x1800043d7  jz      short loc_180004440
0x1800043d9  cmp     ecx, 8007054Fh
0x1800043df  jz      short loc_180004439
0x1800043e1  cmp     ecx, 800705B9h
0x1800043e7  jz      short loc_180004432
0x1800043e9  test    ecx, ecx
0x1800043eb  jz      short loc_18000442E
0x1800043ed  bt      ecx, 1Ch
0x1800043f1  jnb     short loc_1800043F9
0x1800043f3  btr     ecx, 1Ch
0x1800043f7  jmp     short loc_180004445
0x1800043f9  mov     eax, ecx
0x1800043fb  and     eax, 1FFF0000h
0x180004400  cmp     eax, 70000h
0x180004405  jnz     short loc_180004418
0x180004407  movzx   ecx, cx
0x18000440a  mov     eax, ecx
0x18000440c  or      eax, 0C0070000h
0x180004411  test    ecx, ecx
0x180004413  cmovnz  ecx, eax
0x180004416  jmp     short loc_180004445
0x180004418  cmp     eax, 90000h
0x18000441d  jnz     short loc_180004439
0x18000441f  test    ecx, ecx
0x180004421  jle     short loc_180004445
0x180004423  movzx   ecx, cx
0x180004426  or      ecx, 0C0090000h
0x18000442c  jmp     short loc_180004445
0x18000442e  xor     ecx, ecx
0x180004430  jmp     short loc_180004445
0x180004432  mov     ecx, 0C000A083h
0x180004437  jmp     short loc_180004445
0x180004439  mov     ecx, 0C00000E5h
0x18000443e  jmp     short loc_180004445
0x180004440  mov     ecx, 0C000042Bh
0x180004445  mov     eax, ecx
0x180004447  retn
```

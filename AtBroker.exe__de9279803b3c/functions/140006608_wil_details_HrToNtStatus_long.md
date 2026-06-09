# wil::details::HrToNtStatus(long)

- ea: `0x140006608`
- end: `0x1400067c4`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e84`
- `0x140002f2c`
- `0x140002f7c`
- `0x14000303c`
- `0x1400057f8`
- `0x140006e5c`

## callees

- `0x140006608`

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
0x140006608  mov     eax, 800700EAh
0x14000660d  cmp     ecx, eax
0x14000660f  jg      loc_1400066E4
0x140006615  jz      loc_1400066DA
0x14000661b  mov     eax, 80070057h
0x140006620  cmp     ecx, eax
0x140006622  jg      short loc_14000668E
0x140006624  jz      short loc_140006684
0x140006626  cmp     ecx, 80004005h
0x14000662c  jz      short loc_14000667A
0x14000662e  cmp     ecx, 80070001h
0x140006634  jz      short loc_140006670
0x140006636  cmp     ecx, 80070002h
0x14000663c  jz      short loc_140006666
0x14000663e  cmp     ecx, 80070003h
0x140006644  jz      short loc_14000665C
0x140006646  cmp     ecx, 8007000Eh
0x14000664c  jnz     loc_140006769
0x140006652  mov     ecx, 0C0000017h
0x140006657  jmp     loc_1400067C1
0x14000665c  mov     ecx, 0C000003Ah
0x140006661  jmp     loc_1400067C1
0x140006666  mov     ecx, 0C0000034h
0x14000666b  jmp     loc_1400067C1
0x140006670  mov     ecx, 0C0000002h
0x140006675  jmp     loc_1400067C1
0x14000667a  mov     ecx, 0C0000001h
0x14000667f  jmp     loc_1400067C1
0x140006684  mov     ecx, 0C000000Dh
0x140006689  jmp     loc_1400067C1
0x14000668e  cmp     ecx, 80070070h
0x140006694  jz      short loc_1400066D0
0x140006696  cmp     ecx, 8007007Ah
0x14000669c  jz      short loc_1400066C6
0x14000669e  cmp     ecx, 8007007Bh
0x1400066a4  jz      short loc_1400066BC
0x1400066a6  cmp     ecx, 8007007Eh
0x1400066ac  jnz     loc_140006769
0x1400066b2  mov     ecx, 0C0000135h
0x1400066b7  jmp     loc_1400067C1
0x1400066bc  mov     ecx, 0C0000033h
0x1400066c1  jmp     loc_1400067C1
0x1400066c6  mov     ecx, 0C0000023h
0x1400066cb  jmp     loc_1400067C1
0x1400066d0  mov     ecx, 0C000007Fh
0x1400066d5  jmp     loc_1400067C1
0x1400066da  mov     ecx, 80000005h
0x1400066df  jmp     loc_1400067C1
0x1400066e4  mov     eax, 8007047Eh
0x1400066e9  cmp     ecx, eax
0x1400066eb  jg      short loc_14000674D
0x1400066ed  jz      short loc_140006746
0x1400066ef  cmp     ecx, 80070216h
0x1400066f5  jz      short loc_14000673F
0x1400066f7  cmp     ecx, 8007023Eh
0x1400066fd  jz      short loc_140006735
0x1400066ff  cmp     ecx, 80070246h
0x140006705  jz      short loc_14000672B
0x140006707  cmp     ecx, 80070247h
0x14000670d  jz      short loc_140006721
0x14000670f  cmp     ecx, 80070272h
0x140006715  jnz     short loc_140006769
0x140006717  mov     ecx, 0C0000273h
0x14000671c  jmp     loc_1400067C1
0x140006721  mov     ecx, 0C0000163h
0x140006726  jmp     loc_1400067C1
0x14000672b  mov     ecx, 0C0000161h
0x140006730  jmp     loc_1400067C1
0x140006735  mov     ecx, 0C0000025h
0x14000673a  jmp     loc_1400067C1
0x14000673f  mov     ecx, 0C0000095h
0x140006744  jmp     short loc_1400067C1
0x140006746  mov     ecx, 0C0000059h
0x14000674b  jmp     short loc_1400067C1
0x14000674d  cmp     ecx, 8007050Ch
0x140006753  jz      short loc_1400067BC
0x140006755  cmp     ecx, 8007054Fh
0x14000675b  jz      short loc_1400067B5
0x14000675d  cmp     ecx, 800705B9h
0x140006763  jz      short loc_1400067AE
0x140006765  test    ecx, ecx
0x140006767  jz      short loc_1400067AA
0x140006769  bt      ecx, 1Ch
0x14000676d  jnb     short loc_140006775
0x14000676f  btr     ecx, 1Ch
0x140006773  jmp     short loc_1400067C1
0x140006775  mov     eax, ecx
0x140006777  and     eax, 1FFF0000h
0x14000677c  cmp     eax, 70000h
0x140006781  jnz     short loc_140006794
0x140006783  movzx   ecx, cx
0x140006786  mov     eax, ecx
0x140006788  or      eax, 0C0070000h
0x14000678d  test    ecx, ecx
0x14000678f  cmovnz  ecx, eax
0x140006792  jmp     short loc_1400067C1
0x140006794  cmp     eax, 90000h
0x140006799  jnz     short loc_1400067B5
0x14000679b  test    ecx, ecx
0x14000679d  jle     short loc_1400067C1
0x14000679f  movzx   ecx, cx
0x1400067a2  or      ecx, 0C0090000h
0x1400067a8  jmp     short loc_1400067C1
0x1400067aa  xor     ecx, ecx
0x1400067ac  jmp     short loc_1400067C1
0x1400067ae  mov     ecx, 0C000A083h
0x1400067b3  jmp     short loc_1400067C1
0x1400067b5  mov     ecx, 0C00000E5h
0x1400067ba  jmp     short loc_1400067C1
0x1400067bc  mov     ecx, 0C000042Bh
0x1400067c1  mov     eax, ecx
0x1400067c3  retn
```

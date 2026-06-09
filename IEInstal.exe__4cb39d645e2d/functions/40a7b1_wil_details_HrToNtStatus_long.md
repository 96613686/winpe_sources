# wil::details::HrToNtStatus(long)

- ea: `0x40a7b1`
- end: `0x40a980`
- name: `?HrToNtStatus@details@wil@@YGJJ@Z`
- size: `463`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x40a692`
- `0x40aa18`
- `0x40bb71`
- `0x40bc9a`
- `0x40bf2a`
- `0x40bf6f`

## callees

- `0x40a7b1`

## pseudocode

```c
unsigned int __fastcall wil::details::HrToNtStatus(int a1)
{
  unsigned int v1; // ecx
  int v2; // eax
  unsigned int v3; // eax

  if ( a1 > -2147024662 )
  {
    if ( a1 > -2147023746 )
    {
      switch ( a1 )
      {
        case -2147023604:
          return -1073740757;
        case -2147023537:
          return -1073741595;
        case -2147023431:
          return -1073700733;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( a1 )
      {
        case -2147023746:
          return -1073741735;
        case -2147024362:
          return -1073741675;
        case -2147024322:
          return -1073741787;
        case -2147024314:
          return -1073741471;
        case -2147024313:
          return -1073741469;
        case -2147024270:
          return -1073741197;
      }
    }
  }
  else
  {
    if ( a1 == -2147024662 )
      return -2147483643;
    if ( a1 > -2147024809 )
    {
      switch ( a1 )
      {
        case -2147024784:
          return -1073741697;
        case -2147024774:
          return -1073741789;
        case -2147024773:
          return -1073741773;
        case -2147024770:
          return -1073741515;
      }
    }
    else
    {
      switch ( a1 )
      {
        case -2147024809:
          return -1073741811;
        case -2147467259:
          return -1073741823;
        case -2147024895:
          return -1073741822;
        case -2147024894:
          return -1073741772;
        case -2147024893:
          return -1073741766;
        case -2147024882:
          return -1073741801;
      }
    }
  }
  if ( (a1 & 0x10000000) != 0 )
    return a1 & 0xEFFFFFFF;
  if ( (a1 & 0x1FFF0000) == 0x70000 )
  {
    v2 = (unsigned __int16)a1;
    v1 = (unsigned __int16)a1 | 0xC0070000;
    if ( !v2 )
      return 0;
    return v1;
  }
  if ( (a1 & 0x1FFF0000) != 0x90000 )
    return -1073741595;
  v3 = (unsigned __int16)a1 | 0xC0090000;
  if ( a1 <= 0 )
    return a1;
  return v3;
}

```

## disassembly

```asm
0x40a7b1  mov     eax, 800700EAh
0x40a7b6  cmp     ecx, eax
0x40a7b8  jg      loc_40A88D
0x40a7be  jz      loc_40A883
0x40a7c4  mov     eax, 80070057h
0x40a7c9  cmp     ecx, eax
0x40a7cb  jg      short loc_40A837
0x40a7cd  jz      short loc_40A82D
0x40a7cf  cmp     ecx, 80004005h
0x40a7d5  jz      short loc_40A823
0x40a7d7  cmp     ecx, 80070001h
0x40a7dd  jz      short loc_40A819
0x40a7df  cmp     ecx, 80070002h
0x40a7e5  jz      short loc_40A80F
0x40a7e7  cmp     ecx, 80070003h
0x40a7ed  jz      short loc_40A805
0x40a7ef  cmp     ecx, 8007000Eh
0x40a7f5  jnz     loc_40A918
0x40a7fb  mov     ecx, 0C0000017h
0x40a800  jmp     loc_40A97D
0x40a805  mov     ecx, 0C000003Ah
0x40a80a  jmp     loc_40A97D
0x40a80f  mov     ecx, 0C0000034h
0x40a814  jmp     loc_40A97D
0x40a819  mov     ecx, 0C0000002h
0x40a81e  jmp     loc_40A97D
0x40a823  mov     ecx, 0C0000001h
0x40a828  jmp     loc_40A97D
0x40a82d  mov     ecx, 0C000000Dh
0x40a832  jmp     loc_40A97D
0x40a837  cmp     ecx, 80070070h
0x40a83d  jz      short loc_40A879
0x40a83f  cmp     ecx, 8007007Ah
0x40a845  jz      short loc_40A86F
0x40a847  cmp     ecx, 8007007Bh
0x40a84d  jz      short loc_40A865
0x40a84f  cmp     ecx, 8007007Eh
0x40a855  jnz     loc_40A918
0x40a85b  mov     ecx, 0C0000135h
0x40a860  jmp     loc_40A97D
0x40a865  mov     ecx, 0C0000033h
0x40a86a  jmp     loc_40A97D
0x40a86f  mov     ecx, 0C0000023h
0x40a874  jmp     loc_40A97D
0x40a879  mov     ecx, 0C000007Fh
0x40a87e  jmp     loc_40A97D
0x40a883  mov     ecx, 80000005h
0x40a888  jmp     loc_40A97D
0x40a88d  mov     eax, 8007047Eh
0x40a892  cmp     ecx, eax
0x40a894  jg      short loc_40A8FC
0x40a896  jz      short loc_40A8F2
0x40a898  cmp     ecx, 80070216h
0x40a89e  jz      short loc_40A8E8
0x40a8a0  cmp     ecx, 8007023Eh
0x40a8a6  jz      short loc_40A8DE
0x40a8a8  cmp     ecx, 80070246h
0x40a8ae  jz      short loc_40A8D4
0x40a8b0  cmp     ecx, 80070247h
0x40a8b6  jz      short loc_40A8CA
0x40a8b8  cmp     ecx, 80070272h
0x40a8be  jnz     short loc_40A918
0x40a8c0  mov     ecx, 0C0000273h
0x40a8c5  jmp     loc_40A97D
0x40a8ca  mov     ecx, 0C0000163h
0x40a8cf  jmp     loc_40A97D
0x40a8d4  mov     ecx, 0C0000161h
0x40a8d9  jmp     loc_40A97D
0x40a8de  mov     ecx, 0C0000025h
0x40a8e3  jmp     loc_40A97D
0x40a8e8  mov     ecx, 0C0000095h
0x40a8ed  jmp     loc_40A97D
0x40a8f2  mov     ecx, 0C0000059h
0x40a8f7  jmp     loc_40A97D
0x40a8fc  cmp     ecx, 8007050Ch
0x40a902  jz      short loc_40A978
0x40a904  cmp     ecx, 8007054Fh
0x40a90a  jz      short loc_40A971
0x40a90c  cmp     ecx, 800705B9h
0x40a912  jz      short loc_40A96A
0x40a914  test    ecx, ecx
0x40a916  jz      short loc_40A966
0x40a918  test    ecx, 10000000h
0x40a91e  jz      short loc_40A928
0x40a920  and     ecx, 0EFFFFFFFh
0x40a926  jmp     short loc_40A97D
0x40a928  mov     eax, ecx
0x40a92a  mov     edx, 1FFF0000h
0x40a92f  and     eax, edx
0x40a931  cmp     eax, 70000h
0x40a936  jnz     short loc_40A94A
0x40a938  movzx   eax, cx
0x40a93b  mov     ecx, eax
0x40a93d  or      ecx, 0C0070000h
0x40a943  test    eax, eax
0x40a945  cmovz   ecx, eax
0x40a948  jmp     short loc_40A97D
0x40a94a  mov     eax, ecx
0x40a94c  and     eax, edx
0x40a94e  cmp     eax, 90000h
0x40a953  jnz     short loc_40A971
0x40a955  movzx   eax, cx
0x40a958  or      eax, 0C0090000h
0x40a95d  test    ecx, ecx
0x40a95f  cmovle  eax, ecx
0x40a962  mov     ecx, eax
0x40a964  jmp     short loc_40A97D
0x40a966  xor     ecx, ecx
0x40a968  jmp     short loc_40A97D
0x40a96a  mov     ecx, 0C000A083h
0x40a96f  jmp     short loc_40A97D
0x40a971  mov     ecx, 0C00000E5h
0x40a976  jmp     short loc_40A97D
0x40a978  mov     ecx, 0C000042Bh
0x40a97d  mov     eax, ecx
0x40a97f  retn
```

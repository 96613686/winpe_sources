# GetCharacterType(ushort,ulong)

- ea: `0x180008af8`
- end: `0x180009028`
- name: `?GetCharacterType@@YAIGK@Z`
- size: `1328`
- prototype: `__int64 __fastcall(wint_t, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007280`
- `0x180009238`

## callees

- `0x180008af8`
- `0x180009030`

## import_xrefs

- `msvcrt!iswspace` at `0x180008b0f`
- `msvcrt!iswspace` at `0x180008b0f`
- `msvcrt!iswalnum` at `0x180008be3`
- `msvcrt!iswalnum` at `0x180008be3`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x180008f80`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x180008f80`

## pseudocode

```c
__int64 __fastcall GetCharacterType(wint_t a1, int a2)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  unsigned int v5; // eax
  int v6; // ecx
  int v7; // edx
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // eax
  int v15; // ecx
  int v16; // ecx
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // ecx
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  WORD CharType; // [rsp+50h] [rbp+18h] BYREF
  WCHAR SrcStr; // [rsp+58h] [rbp+20h] BYREF

  v2 = a1;
  if ( iswspace(a1) )
    return 4;
  if ( GetLangType(v2) != 1 )
    return 8;
  if ( (unsigned __int16)(v2 + 10240) <= 0x7FFu )
    return 64;
  if ( (unsigned __int16)(v2 - 8960) <= 0x10FFu )
    return 32;
  if ( (_WORD)v2 == 8482 )
    return 32;
  if ( (_WORD)v2 == 8505 )
    return 32;
  v5 = (unsigned __int16)v2;
  if ( (unsigned __int16)(v2 - 8596) <= 0x16u )
  {
    v6 = 6291519;
    LOWORD(v5) = v2 - 8596;
    if ( _bittest(&v6, v5) )
      return 32;
  }
  if ( (_WORD)v2 == 8265 || (_WORD)v2 == 8252 || (_WORD)v2 == 169 || (_WORD)v2 == 174 )
    return 32;
  if ( iswalnum(v2) )
    return 1;
  if ( (unsigned __int16)v2 > 0x2FFu
    && (unsigned __int16)(v2 - 6099) > 8u
    && (unsigned __int16)(v2 - 4254) > 0x6E1u
    && (unsigned __int16)(v2 - 4170) > 1u
    && (unsigned __int16)(v2 - 3802) > 0x125u
    && (unsigned __int16)(v2 - 3572) > 0x8Cu )
  {
    v7 = 805306371;
    if ( ((unsigned __int16)(v2 - 3428) > 0x1Du || !_bittest(&v7, (unsigned __int16)(v2 - 3428)))
      && (unsigned __int16)(v2 - 3300) > 1u
      && ((unsigned __int16)(v2 - 3172) > 0x1Du || !_bittest(&v7, (unsigned __int16)(v2 - 3172))) )
    {
      v8 = (unsigned __int16)v2;
      if ( (unsigned __int16)(v2 - 3032) > 0x27u || (v9 = 0xFFF8003FFFLL, LOWORD(v8) = v2 - 3032, !_bittest64(&v9, v8)) )
      {
        if ( (unsigned __int16)(v2 - 2916) > 1u )
        {
          v10 = (unsigned __int16)v2;
          if ( (unsigned __int16)(v2 - 2766) > 0x32u
            || (v11 = 0x4000000C3FFFFLL, LOWORD(v10) = v2 - 2766, !_bittest64(&v11, v10)) )
          {
            v12 = (unsigned __int16)v2;
            if ( (unsigned __int16)(v2 - 2655) > 0x21u
              || (v13 = 0x3FF00007FLL, LOWORD(v12) = v2 - 2655, !_bittest64(&v13, v12)) )
            {
              v14 = (unsigned __int16)v2;
              if ( (unsigned __int16)(v2 - 2532) > 0x1Cu
                || (v15 = 419418111, LOWORD(v14) = v2 - 2532, !_bittest(&v15, v14)) )
              {
                if ( (_WORD)v2 != 2432
                  && (unsigned __int16)(v2 - 2404) > 1u
                  && (unsigned __int16)(v2 - 1792) > 0x1FFu
                  && (unsigned __int16)(v2 - 1757) > 1u
                  && (unsigned __int16)(v2 - 1642) > 3u
                  && (unsigned __int16)(v2 - 1480) > 0x47u
                  && (unsigned __int16)(v2 - 880) > 0x220u
                  && (unsigned __int16)v2 < 0x17FAu )
                {
                  return 1;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( (_WORD)v2 == 39 || (_WORD)v2 == 8217 )
  {
    if ( (unsigned int)(a2 - 1027) <= 0x1F )
    {
      v16 = -1845418943;
      if ( _bittest(&v16, a2 - 1027) )
        return 1;
    }
    if ( a2 == 2057 || a2 == 3081 || a2 == 4105 || a2 == 1091 || a2 == 2115 || a2 == 5132 )
      return 1;
  }
  if ( (_WORD)v2 == 45 )
  {
    v17 = (unsigned int)(a2 - 1025);
    if ( (unsigned int)v17 <= 0x3E )
    {
      v18 = 0x4000101313AC2D67LL;
      if ( _bittest64(&v18, v17) )
        return 1;
    }
    if ( (unsigned int)(a2 - 2057) <= 0xD )
    {
      v19 = 10241;
      if ( _bittest(&v19, a2 - 2057) )
        return 1;
    }
    if ( a2 == 3081 || a2 == 4105 || a2 == 9242 || a2 == 10266 )
      return 1;
  }
  if ( (_WORD)v2 == 183 && a2 == 1027
    || (_WORD)v2 == 34 && a2 == 1037
    || ((_WORD)v2 == 9676 || (unsigned __int16)(v2 - 781) <= 1u) && a2 == 1054 )
  {
    return 1;
  }
  if ( (_WORD)v2 == 8216 && ((a2 - 1091) & 0xFFFFFBFF) == 0 )
    return 1;
  if ( (unsigned __int16)(v2 - 768) <= 1u && a2 == 1130 )
    return 1;
  SrcStr = v2;
  CharType = 0;
  if ( GetStringTypeExW(0, 4u, &SrcStr, 1, &CharType) )
  {
    if ( (CharType & 4) != 0 )
    {
      v20 = (unsigned int)(a2 - 1054);
      v21 = 0x22697B8008000001LL;
      if ( (unsigned int)v20 <= 0x3D )
      {
        if ( _bittest64(&v21, v20) )
          return 1;
      }
      if ( a2 == 0x2000 )
        return 1;
      if ( a2 == 2117 )
        return 1;
      v22 = (unsigned int)(a2 - 1115166);
      if ( (unsigned int)v22 <= 0x3D )
      {
        if ( _bittest64(&v21, v22) )
          return 1;
      }
      if ( a2 == 1122304 || a2 == 1116229 )
        return 1;
    }
  }
  if ( (_WORD)v2 == 0xFFFC || (unsigned __int16)(v2 + 1795) <= 1u )
    return 16;
  result = 16;
  if ( (_WORD)v2 != 0xF8FC )
    return 2;
  return result;
}

```

## disassembly

```asm
0x180008af8  mov     [rsp+arg_0], rbx
0x180008afd  mov     [rsp+arg_8], rsi
0x180008b02  push    rdi
0x180008b03  sub     rsp, 30h
0x180008b07  movzx   ebx, cx
0x180008b0a  mov     edi, edx
0x180008b0c  movzx   ecx, bx; C
0x180008b0f  call    cs:__imp_iswspace
0x180008b15  test    eax, eax
0x180008b17  jz      short loc_180008B23
0x180008b19  mov     eax, 4
0x180008b1e  jmp     loc_180009018
0x180008b23  mov     ecx, ebx; unsigned int
0x180008b25  call    ?GetLangType@@YAII@Z; GetLangType(uint)
0x180008b2a  mov     esi, 1
0x180008b2f  cmp     eax, esi
0x180008b31  jz      short loc_180008B3B
0x180008b33  lea     eax, [rsi+7]
0x180008b36  jmp     loc_180009018
0x180008b3b  mov     eax, 2800h
0x180008b40  mov     ecx, 7FFh
0x180008b45  add     eax, ebx
0x180008b47  cmp     ax, cx
0x180008b4a  ja      short loc_180008B56
0x180008b4c  mov     eax, 40h ; '@'
0x180008b51  jmp     loc_180009018
0x180008b56  mov     ecx, 2300h
0x180008b5b  movzx   eax, bx
0x180008b5e  sub     ax, cx
0x180008b61  mov     ecx, 10FFh
0x180008b66  cmp     ax, cx
0x180008b69  jbe     loc_180009013
0x180008b6f  mov     eax, 2122h
0x180008b74  cmp     bx, ax
0x180008b77  jz      loc_180009013
0x180008b7d  mov     eax, 2139h
0x180008b82  cmp     bx, ax
0x180008b85  jz      loc_180009013
0x180008b8b  lea     ecx, [rax+5Bh]
0x180008b8e  movzx   eax, bx
0x180008b91  sub     ax, cx
0x180008b94  cmp     ax, 16h
0x180008b98  ja      short loc_180008BA8
0x180008b9a  mov     ecx, 60003Fh
0x180008b9f  bt      ecx, eax
0x180008ba2  jb      loc_180009013
0x180008ba8  mov     eax, 2049h
0x180008bad  cmp     bx, ax
0x180008bb0  jz      loc_180009013
0x180008bb6  mov     eax, 203Ch
0x180008bbb  cmp     bx, ax
0x180008bbe  jz      loc_180009013
0x180008bc4  mov     eax, 0A9h
0x180008bc9  cmp     bx, ax
0x180008bcc  jz      loc_180009013
0x180008bd2  mov     eax, 0AEh
0x180008bd7  cmp     bx, ax
0x180008bda  jz      loc_180009013
0x180008be0  movzx   ecx, bx; C
0x180008be3  call    cs:__imp_iswalnum
0x180008be9  test    eax, eax
0x180008beb  jnz     loc_18000900F
0x180008bf1  mov     eax, 2FFh
0x180008bf6  mov     r9d, 27h ; '''
0x180008bfc  cmp     bx, ax
0x180008bff  jbe     loc_180008DF2
0x180008c05  mov     ecx, 17D3h
0x180008c0a  movzx   eax, bx
0x180008c0d  sub     ax, cx
0x180008c10  lea     ecx, [r9-1Fh]
0x180008c14  cmp     ax, cx
0x180008c17  jbe     loc_180008DF2
0x180008c1d  mov     ecx, 109Eh
0x180008c22  movzx   eax, bx
0x180008c25  sub     ax, cx
0x180008c28  mov     ecx, 6E1h
0x180008c2d  cmp     ax, cx
0x180008c30  jbe     loc_180008DF2
0x180008c36  mov     ecx, 104Ah
0x180008c3b  movzx   eax, bx
0x180008c3e  sub     ax, cx
0x180008c41  cmp     ax, si
0x180008c44  jbe     loc_180008DF2
0x180008c4a  mov     ecx, 0EDAh
0x180008c4f  movzx   eax, bx
0x180008c52  sub     ax, cx
0x180008c55  mov     ecx, 125h
0x180008c5a  cmp     ax, cx
0x180008c5d  jbe     loc_180008DF2
0x180008c63  mov     ecx, 0DF4h
0x180008c68  movzx   eax, bx
0x180008c6b  sub     ax, cx
0x180008c6e  lea     ecx, [r9+65h]
0x180008c72  cmp     ax, cx
0x180008c75  jbe     loc_180008DF2
0x180008c7b  mov     ecx, 0D64h
0x180008c80  movzx   eax, bx
0x180008c83  sub     ax, cx
0x180008c86  mov     edx, 30000003h
0x180008c8b  cmp     ax, 1Dh
0x180008c8f  ja      short loc_180008C9D
0x180008c91  movzx   eax, ax
0x180008c94  bt      edx, eax
0x180008c97  jb      loc_180008DF2
0x180008c9d  mov     ecx, 0CE4h
0x180008ca2  movzx   eax, bx
0x180008ca5  sub     ax, cx
0x180008ca8  cmp     ax, si
0x180008cab  jbe     loc_180008DF2
0x180008cb1  mov     ecx, 0C64h
0x180008cb6  movzx   eax, bx
0x180008cb9  sub     ax, cx
0x180008cbc  cmp     ax, 1Dh
0x180008cc0  ja      short loc_180008CCE
0x180008cc2  movzx   eax, ax
0x180008cc5  bt      edx, eax
0x180008cc8  jb      loc_180008DF2
0x180008cce  mov     ecx, 0BD8h
0x180008cd3  movzx   eax, bx
0x180008cd6  sub     ax, cx
0x180008cd9  cmp     ax, r9w
0x180008cdd  ja      short loc_180008CF3
0x180008cdf  mov     rcx, 0FFF8003FFFh
0x180008ce9  bt      rcx, rax
0x180008ced  jb      loc_180008DF2
0x180008cf3  mov     ecx, 0B64h
0x180008cf8  movzx   eax, bx
0x180008cfb  sub     ax, cx
0x180008cfe  cmp     ax, si
0x180008d01  jbe     loc_180008DF2
0x180008d07  mov     ecx, 0ACEh
0x180008d0c  movzx   eax, bx
0x180008d0f  sub     ax, cx
0x180008d12  cmp     ax, 32h ; '2'
0x180008d16  ja      short loc_180008D2C
0x180008d18  mov     rcx, 4000000C3FFFFh
0x180008d22  bt      rcx, rax
0x180008d26  jb      loc_180008DF2
0x180008d2c  mov     ecx, 0A5Fh
0x180008d31  movzx   eax, bx
0x180008d34  sub     ax, cx
0x180008d37  cmp     ax, 21h ; '!'
0x180008d3b  ja      short loc_180008D51
0x180008d3d  mov     rcx, 3FF00007Fh
0x180008d47  bt      rcx, rax
0x180008d4b  jb      loc_180008DF2
0x180008d51  mov     ecx, 9E4h
0x180008d56  movzx   eax, bx
0x180008d59  sub     ax, cx
0x180008d5c  cmp     ax, 1Ch
0x180008d60  ja      short loc_180008D70
0x180008d62  mov     ecx, 18FFCFFFh
0x180008d67  bt      ecx, eax
0x180008d6a  jb      loc_180008DF2
0x180008d70  mov     eax, 980h
0x180008d75  cmp     bx, ax
0x180008d78  jz      short loc_180008DF2
0x180008d7a  lea     ecx, [rax-1Ch]
0x180008d7d  movzx   eax, bx
0x180008d80  sub     ax, cx
0x180008d83  cmp     ax, si
0x180008d86  jbe     short loc_180008DF2
0x180008d88  mov     ecx, 700h
0x180008d8d  movzx   eax, bx
0x180008d90  sub     ax, cx
0x180008d93  mov     ecx, 1FFh
0x180008d98  cmp     ax, cx
0x180008d9b  jbe     short loc_180008DF2
0x180008d9d  mov     ecx, 6DDh
0x180008da2  movzx   eax, bx
0x180008da5  sub     ax, cx
0x180008da8  cmp     ax, si
0x180008dab  jbe     short loc_180008DF2
0x180008dad  mov     ecx, 66Ah
0x180008db2  movzx   eax, bx
0x180008db5  sub     ax, cx
0x180008db8  cmp     ax, 3
0x180008dbc  jbe     short loc_180008DF2
0x180008dbe  mov     ecx, 5C8h
0x180008dc3  movzx   eax, bx
0x180008dc6  sub     ax, cx
0x180008dc9  cmp     ax, 47h ; 'G'
0x180008dcd  jbe     short loc_180008DF2
0x180008dcf  mov     ecx, 370h
0x180008dd4  movzx   eax, bx
0x180008dd7  sub     ax, cx
0x180008dda  mov     ecx, 220h
0x180008ddf  cmp     ax, cx
0x180008de2  jbe     short loc_180008DF2
0x180008de4  mov     eax, 17FAh
0x180008de9  cmp     bx, ax
0x180008dec  jb      loc_18000900F
0x180008df2  mov     edx, 1009h
0x180008df7  mov     r8d, 0C09h
0x180008dfd  cmp     r9w, bx
0x180008e01  jz      short loc_180008E0D
0x180008e03  mov     eax, 2019h
0x180008e08  cmp     ax, bx
0x180008e0b  jnz     short loc_180008E67
0x180008e0d  lea     eax, [rdi-403h]
0x180008e13  cmp     eax, 1Fh
0x180008e16  ja      short loc_180008E26
0x180008e18  mov     ecx, 92012441h
0x180008e1d  bt      ecx, eax
0x180008e20  jb      loc_18000900F
0x180008e26  cmp     edi, 809h
0x180008e2c  jz      loc_18000900F
0x180008e32  cmp     edi, r8d
0x180008e35  jz      loc_18000900F
0x180008e3b  cmp     edi, edx
0x180008e3d  jz      loc_18000900F
0x180008e43  cmp     edi, 443h
0x180008e49  jz      loc_18000900F
0x180008e4f  cmp     edi, 843h
0x180008e55  jz      loc_18000900F
0x180008e5b  cmp     edi, 140Ch
0x180008e61  jz      loc_18000900F
0x180008e67  mov     eax, 2Dh ; '-'
0x180008e6c  cmp     ax, bx
0x180008e6f  jnz     short loc_180008ED2
0x180008e71  lea     eax, [rdi-401h]
0x180008e77  cmp     eax, 3Eh ; '>'
0x180008e7a  ja      short loc_180008E90
0x180008e7c  mov     rcx, 4000101313AC2D67h
0x180008e86  bt      rcx, rax
0x180008e8a  jb      loc_18000900F
0x180008e90  lea     eax, [rdi-809h]
0x180008e96  cmp     eax, 0Dh
0x180008e99  ja      short loc_180008EA9
0x180008e9b  mov     ecx, 2801h
0x180008ea0  bt      ecx, eax
0x180008ea3  jb      loc_18000900F
0x180008ea9  cmp     edi, r8d
0x180008eac  jz      loc_18000900F
0x180008eb2  cmp     edi, edx
0x180008eb4  jz      loc_18000900F
0x180008eba  cmp     edi, 241Ah
0x180008ec0  jz      loc_18000900F
0x180008ec6  cmp     edi, 281Ah
0x180008ecc  jz      loc_18000900F
0x180008ed2  mov     eax, 0B7h
0x180008ed7  cmp     ax, bx
0x180008eda  jnz     short loc_180008EE8
0x180008edc  cmp     edi, 403h
0x180008ee2  jz      loc_18000900F
0x180008ee8  mov     eax, 22h ; '"'
0x180008eed  cmp     ax, bx
0x180008ef0  jnz     short loc_180008EFE
0x180008ef2  cmp     edi, 40Dh
0x180008ef8  jz      loc_18000900F
0x180008efe  mov     eax, 25CCh
0x180008f03  cmp     bx, ax
0x180008f06  jz      short loc_180008F18
0x180008f08  mov     ecx, 30Dh
0x180008f0d  movzx   eax, bx
0x180008f10  sub     ax, cx
0x180008f13  cmp     ax, si
0x180008f16  ja      short loc_180008F24
0x180008f18  cmp     edi, 41Eh
0x180008f1e  jz      loc_18000900F
0x180008f24  mov     eax, 2018h
0x180008f29  cmp     ax, bx
0x180008f2c  jnz     short loc_180008F3F
0x180008f2e  lea     eax, [rdi-443h]
0x180008f34  test    eax, 0FFFFFBFFh
0x180008f39  jz      loc_18000900F
0x180008f3f  mov     ecx, 300h
0x180008f44  movzx   eax, bx
0x180008f47  sub     ax, cx
0x180008f4a  cmp     ax, si
0x180008f4d  ja      short loc_180008F5B
0x180008f4f  cmp     edi, 46Ah
0x180008f55  jz      loc_18000900F
0x180008f5b  xor     eax, eax
0x180008f5d  mov     [rsp+38h+SrcStr], bx
0x180008f62  mov     [rsp+38h+CharType], ax
0x180008f67  lea     r8, [rsp+38h+SrcStr]; lpSrcStr
0x180008f6c  lea     rax, [rsp+38h+CharType]
0x180008f71  mov     r9d, esi; cchSrc
0x180008f74  mov     edx, 4; dwInfoType
0x180008f79  mov     [rsp+38h+lpCharType], rax; lpCharType
0x180008f7e  xor     ecx, ecx; Locale
0x180008f80  call    cs:__imp_GetStringTypeExW
0x180008f86  test    eax, eax
0x180008f88  jz      short loc_180008FDD
0x180008f8a  test    byte ptr [rsp+38h+CharType], 4
0x180008f8f  jz      short loc_180008FDD
0x180008f91  lea     eax, [rdi-41Eh]
0x180008f97  mov     rcx, 22697B8008000001h
0x180008fa1  cmp     eax, 3Dh ; '='
0x180008fa4  ja      short loc_180008FAC
0x180008fa6  bt      rcx, rax
0x180008faa  jb      short loc_18000900F
0x180008fac  cmp     edi, 2000h
0x180008fb2  jz      short loc_18000900F
0x180008fb4  cmp     edi, 845h
0x180008fba  jz      short loc_18000900F
0x180008fbc  lea     eax, [rdi-11041Eh]
0x180008fc2  cmp     eax, 3Dh ; '='
0x180008fc5  ja      short loc_180008FCD
  ... truncated ...
```

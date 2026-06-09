# Windows::Internal::CLanguage::ValidateTagAndInitialize(ushort const *)

- ea: `0x180006750`
- end: `0x180006a9f`
- name: `?ValidateTagAndInitialize@CLanguage@Internal@Windows@@IEAA_NPEBG@Z`
- size: `847`
- prototype: `bool(Windows::Internal::CLanguage *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000418c`
- `0x1800061f0`
- `0x1800064d0`
- `0x180006710`
- `0x18000ab34`

## callees

- `0x180006750`
- `0x180006ab0`
- `0x18000a9fc`
- `0x18000b388`
- `0x18001386c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069ec`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a5e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800069ec`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006807`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006807`

## pseudocode

```c
bool __fastcall Windows::Internal::CLanguage::ValidateTagAndInitialize(void **this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rsi
  bool result; // al
  char v5; // r9
  bool v6; // di
  bool v7; // cl
  __int16 v8; // ax
  const WCHAR *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // rax
  char *v14; // rax
  unsigned __int64 j; // r8
  char *v16; // r14
  __int64 v17; // rcx
  char *v18; // rcx
  unsigned __int64 v19; // rdx
  char *v20; // rcx
  unsigned __int64 i; // rdx
  unsigned __int64 v22; // r8
  char *v23; // rcx
  unsigned __int64 v24; // rdx
  char *v25; // rcx
  unsigned __int64 k; // rdx
  unsigned __int64 v27; // r8
  Windows::Internal *v28; // r10

  v2 = a2;
  result = Windows::Internal::CLanguage::ValidateTag((Windows::Internal::CLanguage *)this, a2);
  v5 = *((_BYTE *)this + 72);
  v6 = result;
  if ( (v5 & 4) != 0 || (v5 & 0x40) != 0 )
  {
    v7 = 0;
    if ( (v5 & 0x30) == 0 )
      v7 = (v5 & 0x40) == 0;
    if ( v7 && ((_BYTE)this[4] & 0x70) == 0 )
    {
      if ( (v5 & 8) != 0 )
        return v6;
      v8 = *((_WORD *)this + 26);
      if ( v8
        && (v8 != 6211 || CompareStringOrdinal(v2, -1, L"qut", -1, 1) != 2)
        && (*((_WORD *)this + 30) || ((_BYTE)this[4] & 2) == 0)
        && (*((_WORD *)this + 27) || ((_BYTE)this[4] & 4) == 0)
        && (*((_WORD *)this + 28) || ((_BYTE)this[4] & 8) == 0) )
      {
        return v6;
      }
    }
    if ( v2 != this[2] && v2 )
    {
      v9 = v2;
      v10 = 85;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v10;
      }
      while ( v10 );
      v11 = 85 - v10;
      if ( v10 )
      {
        v12 = v11 + 1;
        v13 = 2 * (v11 + 1);
        if ( !is_mul_ok(v11 + 1, 2u) )
          v13 = -1;
        v14 = (char *)operator new[](v13, (const struct std::nothrow_t *)byte_18002CD7B);
        v16 = v14;
        if ( v14 )
        {
          if ( v12 )
          {
            if ( v12 > 0x7FFFFFFF )
            {
              *(_WORD *)v14 = 0;
            }
            else
            {
              v17 = 2147483646;
              do
              {
                if ( !v17 )
                  break;
                if ( !*v2 )
                  break;
                *(_WORD *)v14 = *v2++;
                v14 += 2;
                --v17;
                --v12;
              }
              while ( v12 );
              v18 = v14 - 2;
              if ( v12 )
                v18 = v14;
              *(_WORD *)v18 = 0;
              if ( v12 )
              {
                if ( ((_BYTE)this[4] & 1) != 0 )
                {
                  v19 = *((unsigned __int16 *)this + 18);
                  v20 = &v16[2 * (unsigned __int8)v19];
                  for ( i = v19 >> 8; *(_WORD *)v20; --i )
                  {
                    if ( !i )
                      break;
                    j = *(unsigned __int16 *)v20;
                    if ( (unsigned __int16)(j - 65) <= 0x19u )
                    {
                      LOWORD(j) = j | 0x20;
                      *(_WORD *)v20 = j;
                    }
                    v20 += 2;
                  }
                }
                if ( ((_BYTE)this[4] & 4) != 0 && *((_BYTE *)this + 41) == 4 && ((_BYTE)this[9] & 0x20) == 0 )
                {
                  Windows::Internal::ToLowerCase(
                    (Windows::Internal *)&v16[2 * (unsigned __int8)*((_WORD *)this + 20)],
                    (unsigned __int16 *)((unsigned __int64)*((unsigned __int16 *)this + 20) >> 8),
                    j);
                  Windows::Internal::ToUpperCase(v28, (unsigned __int16 *)1, v27);
                }
                if ( ((_BYTE)this[4] & 8) != 0 )
                {
                  v22 = *((unsigned __int16 *)this + 21);
                  v23 = &v16[2 * (unsigned __int8)v22];
                  for ( j = v22 >> 8; *(_WORD *)v23; --j )
                  {
                    if ( !j )
                      break;
                    if ( (unsigned __int16)(*(_WORD *)v23 - 97) <= 0x19u )
                      *(_WORD *)v23 &= 0xDFu;
                    v23 += 2;
                  }
                }
                if ( ((_BYTE)this[4] & 0x10) != 0 )
                {
                  v24 = *((unsigned __int16 *)this + 22);
                  v25 = &v16[2 * (unsigned __int8)v24];
                  for ( k = v24 >> 8; *(_WORD *)v25; --k )
                  {
                    if ( !k )
                      break;
                    j = *(unsigned __int16 *)v25;
                    if ( (unsigned __int16)(j - 65) <= 0x19u )
                    {
                      LOWORD(j) = j | 0x20;
                      *(_WORD *)v25 = j;
                    }
                    v25 += 2;
                  }
                }
                if ( ((_BYTE)this[4] & 0x20) != 0 )
                  Windows::Internal::ToLowerCase(
                    (Windows::Internal *)&v16[2 * (unsigned __int8)*((_WORD *)this + 23)],
                    (unsigned __int16 *)((unsigned __int64)*((unsigned __int16 *)this + 23) >> 8),
                    j);
                if ( ((_BYTE)this[4] & 0x40) != 0 )
                  Windows::Internal::ToLowerCase(
                    (Windows::Internal *)&v16[2 * (unsigned __int8)*((_WORD *)this + 24)],
                    (unsigned __int16 *)((unsigned __int64)*((unsigned __int16 *)this + 24) >> 8),
                    j);
                operator delete[](this[2]);
                this[2] = v16;
                goto LABEL_8;
              }
            }
          }
          operator delete[](v16);
        }
        v6 = 0;
      }
    }
LABEL_8:
    this[3] = this[2];
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180006750  mov     [rsp+arg_10], rbx
0x180006755  mov     [rsp+arg_18], rsi
0x18000675a  push    rdi
0x18000675b  sub     rsp, 30h
0x18000675f  mov     rsi, rdx
0x180006762  mov     rbx, rcx
0x180006765  call    ?ValidateTag@CLanguage@Internal@Windows@@IEAA_NPEBG@Z; Windows::Internal::CLanguage::ValidateTag(ushort const *)
0x18000676a  movzx   r9d, byte ptr [rbx+48h]
0x18000676f  movzx   edi, al
0x180006772  movzx   edx, r9b
0x180006776  shr     dl, 6
0x180006779  and     dl, 1
0x18000677c  test    r9b, 4
0x180006780  jnz     short loc_180006786
0x180006782  test    dl, dl
0x180006784  jz      short loc_1800067C6
0x180006786  xor     dl, 1
0x180006789  mov     [rsp+38h+arg_8], r14
0x18000678e  xor     ecx, ecx
0x180006790  movzx   eax, dl
0x180006793  test    r9b, 30h
0x180006797  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000679e  cmovz   ecx, eax
0x1800067a1  test    cl, cl
0x1800067a3  jz      short loc_1800067AB
0x1800067a5  test    byte ptr [rbx+20h], 70h
0x1800067a9  jz      short loc_1800067D6
0x1800067ab  cmp     rsi, [rbx+10h]
0x1800067af  jnz     loc_180006842
0x1800067b5  mov     rax, [rbx+10h]
0x1800067b9  mov     [rbx+18h], rax
0x1800067bd  mov     r14, [rsp+38h+arg_8]
0x1800067c2  movzx   eax, dil
0x1800067c6  mov     rbx, [rsp+38h+arg_10]
0x1800067cb  mov     rsi, [rsp+38h+arg_18]
0x1800067d0  add     rsp, 30h
0x1800067d4  pop     rdi
0x1800067d5  retn
0x1800067d6  test    r9b, 8
0x1800067da  jnz     short loc_1800067BD
0x1800067dc  movzx   eax, word ptr [rbx+34h]
0x1800067e0  test    ax, ax
0x1800067e3  jz      short loc_1800067AB
0x1800067e5  mov     ecx, 1843h
0x1800067ea  cmp     ax, cx
0x1800067ed  jnz     short loc_180006812
0x1800067ef  mov     r9d, r14d; cchCount2
0x1800067f2  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800067fa  lea     r8, String2; "qut"
0x180006801  mov     edx, r14d; cchCount1
0x180006804  mov     rcx, rsi; lpString1
0x180006807  call    cs:__imp_CompareStringOrdinal
0x18000680d  cmp     eax, 2
0x180006810  jz      short loc_1800067AB
0x180006812  cmp     word ptr [rbx+3Ch], 0
0x180006817  jnz     short loc_18000681F
0x180006819  test    byte ptr [rbx+20h], 2
0x18000681d  jnz     short loc_1800067AB
0x18000681f  cmp     word ptr [rbx+36h], 0
0x180006824  jnz     short loc_180006830
0x180006826  test    byte ptr [rbx+20h], 4
0x18000682a  jnz     loc_1800067AB
0x180006830  cmp     word ptr [rbx+38h], 0
0x180006835  jnz     short loc_1800067BD
0x180006837  test    byte ptr [rbx+20h], 8
0x18000683b  jz      short loc_1800067BD
0x18000683d  jmp     loc_1800067AB
0x180006842  test    rsi, rsi
0x180006845  jz      loc_1800067B5
0x18000684b  mov     ecx, 55h ; 'U'
0x180006850  mov     rax, rsi
0x180006853  mov     edx, ecx
0x180006855  cmp     word ptr [rax], 0
0x180006859  jz      short loc_180006865
0x18000685b  add     rax, 2
0x18000685f  sub     rdx, 1
0x180006863  jnz     short loc_180006855
0x180006865  sub     rcx, rdx
0x180006868  xor     eax, eax
0x18000686a  test    rdx, rdx
0x18000686d  cmovz   rcx, rax
0x180006871  jz      loc_1800067B5
0x180006877  mov     [rsp+38h+arg_0], rbp
0x18000687c  mov     eax, 2
0x180006881  lea     rbp, [rcx+1]
0x180006885  mul     rbp
0x180006888  lea     rdx, byte_18002CD7B; struct std::nothrow_t *
0x18000688f  cmovb   rax, r14
0x180006893  mov     rcx, rax; unsigned __int64
0x180006896  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000689b  mov     r14, rax
0x18000689e  test    rax, rax
0x1800068a1  jz      loc_180006A64
0x1800068a7  test    rbp, rbp
0x1800068aa  jz      loc_180006A5B
0x1800068b0  cmp     rbp, 7FFFFFFFh
0x1800068b7  ja      loc_180006A56
0x1800068bd  mov     ecx, 7FFFFFFEh
0x1800068c2  test    rcx, rcx
0x1800068c5  jz      short loc_1800068E3
0x1800068c7  movzx   edx, word ptr [rsi]
0x1800068ca  test    dx, dx
0x1800068cd  jz      short loc_1800068E3
0x1800068cf  mov     [rax], dx
0x1800068d2  add     rsi, 2
0x1800068d6  add     rax, 2
0x1800068da  dec     rcx
0x1800068dd  sub     rbp, 1
0x1800068e1  jnz     short loc_1800068C2
0x1800068e3  test    rbp, rbp
0x1800068e6  lea     rcx, [rax-2]
0x1800068ea  cmovnz  rcx, rax
0x1800068ee  xor     eax, eax
0x1800068f0  mov     [rcx], ax
0x1800068f3  test    rbp, rbp
0x1800068f6  jz      loc_180006A5B
0x1800068fc  test    byte ptr [rbx+20h], 1
0x180006900  jz      short loc_180006944
0x180006902  movzx   eax, word ptr [rbx+24h]
0x180006906  mov     edx, eax
0x180006908  movzx   eax, al
0x18000690b  lea     rcx, [r14+rax*2]
0x18000690f  shr     rdx, 8
0x180006913  cmp     word ptr [rcx], 0
0x180006917  jz      short loc_180006944
0x180006919  nop     dword ptr [rax+00000000h]
0x180006920  test    rdx, rdx
0x180006923  jz      short loc_180006944
0x180006925  movzx   r8d, word ptr [rcx]; unsigned __int64
0x180006929  lea     eax, [r8-41h]
0x18000692d  cmp     ax, 19h
0x180006931  jbe     loc_180006A00
0x180006937  add     rcx, 2
0x18000693b  dec     rdx
0x18000693e  cmp     word ptr [rcx], 0
0x180006942  jnz     short loc_180006920
0x180006944  test    byte ptr [rbx+20h], 4
0x180006948  jnz     loc_180006A19
0x18000694e  test    byte ptr [rbx+20h], 8
0x180006952  jz      short loc_180006997
0x180006954  movzx   eax, word ptr [rbx+2Ah]
0x180006958  mov     r8d, eax
0x18000695b  movzx   eax, al
0x18000695e  lea     rcx, [r14+rax*2]
0x180006962  shr     r8, 8
0x180006966  cmp     word ptr [rcx], 0
0x18000696a  jz      short loc_180006997
0x18000696c  mov     r9d, 0DFh
0x180006972  test    r8, r8
0x180006975  jz      short loc_180006997
0x180006977  movzx   edx, word ptr [rcx]
0x18000697a  lea     eax, [rdx-61h]
0x18000697d  cmp     ax, 19h
0x180006981  ja      short loc_18000698A
0x180006983  and     dx, r9w
0x180006987  mov     [rcx], dx
0x18000698a  add     rcx, 2
0x18000698e  dec     r8
0x180006991  cmp     word ptr [rcx], 0
0x180006995  jnz     short loc_180006972
0x180006997  test    byte ptr [rbx+20h], 10h
0x18000699b  jz      short loc_1800069D4
0x18000699d  movzx   eax, word ptr [rbx+2Ch]
0x1800069a1  mov     edx, eax
0x1800069a3  movzx   eax, al
0x1800069a6  lea     rcx, [r14+rax*2]
0x1800069aa  shr     rdx, 8
0x1800069ae  cmp     word ptr [rcx], 0
0x1800069b2  jz      short loc_1800069D4
0x1800069b4  test    rdx, rdx
0x1800069b7  jz      short loc_1800069D4
0x1800069b9  movzx   r8d, word ptr [rcx]; unsigned __int64
0x1800069bd  lea     eax, [r8-41h]
0x1800069c1  cmp     ax, 19h
0x1800069c5  jbe     short loc_180006A0E
0x1800069c7  add     rcx, 2
0x1800069cb  dec     rdx
0x1800069ce  cmp     word ptr [rcx], 0
0x1800069d2  jnz     short loc_1800069B4
0x1800069d4  test    byte ptr [rbx+20h], 20h
0x1800069d8  jnz     loc_180006A69
0x1800069de  test    byte ptr [rbx+20h], 40h
0x1800069e2  jnz     loc_180006A84
0x1800069e8  mov     rcx, [rbx+10h]
0x1800069ec  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800069f2  mov     [rbx+10h], r14
0x1800069f6  mov     rbp, [rsp+38h+arg_0]
0x1800069fb  jmp     loc_1800067B5
0x180006a00  or      r8w, 20h
0x180006a05  mov     [rcx], r8w
0x180006a09  jmp     loc_180006937
0x180006a0e  or      r8w, 20h
0x180006a13  mov     [rcx], r8w
0x180006a17  jmp     short loc_1800069C7
0x180006a19  cmp     byte ptr [rbx+29h], 4
0x180006a1d  jnz     loc_18000694E
0x180006a23  test    byte ptr [rbx+48h], 20h
0x180006a27  jnz     loc_18000694E
0x180006a2d  movzx   edx, word ptr [rbx+28h]
0x180006a31  movzx   eax, dl
0x180006a34  shr     rdx, 8; unsigned __int16 *
0x180006a38  lea     r10, [r14+rax*2]
0x180006a3c  mov     rcx, r10; this
0x180006a3f  call    ?ToLowerCase@Internal@Windows@@YAXPEAG_K@Z; Windows::Internal::ToLowerCase(ushort *,unsigned __int64)
0x180006a44  mov     edx, 1; unsigned __int16 *
0x180006a49  mov     rcx, r10; this
0x180006a4c  call    ?ToUpperCase@Internal@Windows@@YAXPEAG_K@Z; Windows::Internal::ToUpperCase(ushort *,unsigned __int64)
0x180006a51  jmp     loc_18000694E
0x180006a56  xor     ecx, ecx
0x180006a58  mov     [rax], cx
0x180006a5b  mov     rcx, r14
0x180006a5e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006a64  xor     dil, dil
0x180006a67  jmp     short loc_1800069F6
0x180006a69  movzx   eax, word ptr [rbx+2Eh]
0x180006a6d  mov     edx, eax
0x180006a6f  movzx   eax, al
0x180006a72  shr     rdx, 8; unsigned __int16 *
0x180006a76  lea     rcx, [r14+rax*2]; this
0x180006a7a  call    ?ToLowerCase@Internal@Windows@@YAXPEAG_K@Z; Windows::Internal::ToLowerCase(ushort *,unsigned __int64)
0x180006a7f  jmp     loc_1800069DE
0x180006a84  movzx   eax, word ptr [rbx+30h]
0x180006a88  mov     edx, eax
0x180006a8a  movzx   eax, al
0x180006a8d  shr     rdx, 8; unsigned __int16 *
0x180006a91  lea     rcx, [r14+rax*2]; this
0x180006a95  call    ?ToLowerCase@Internal@Windows@@YAXPEAG_K@Z; Windows::Internal::ToLowerCase(ushort *,unsigned __int64)
0x180006a9a  jmp     loc_1800069E8
```

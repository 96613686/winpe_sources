# Windows::Internal::CLanguage::ValidateTag(ushort const *)

- ea: `0x180006ab0`
- end: `0x18000763e`
- name: `?ValidateTag@CLanguage@Internal@Windows@@IEAA_NPEBG@Z`
- size: `2958`
- prototype: `bool __fastcall(Windows::Internal::CLanguage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180006ab0`
- `0x180007650`
- `0x180007cd0`
- `0x180008ce0`

## import_xrefs

- `msvcrt!bsearch` at `0x180006b21`
- `msvcrt!bsearch` at `0x180006b21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007126`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007150`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000717a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800071e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007253`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000728d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007331`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007445`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007477`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007126`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007150`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000717a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800071e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007253`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000728d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007331`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007445`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007477`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800074a5`

## pseudocode

```c
bool __fastcall Windows::Internal::CLanguage::ValidateTag(
        Windows::Internal::CLanguage *this,
        const unsigned __int16 *a2)
{
  const WCHAR *v2; // r14
  unsigned __int16 v4; // r12
  __int64 v5; // r13
  unsigned __int16 v6; // r15
  char v7; // al
  _QWORD *v8; // rax
  const WCHAR *v9; // rdx
  char v10; // cl
  bool v11; // sf
  char v12; // si
  int v13; // r8d
  const WCHAR *v14; // rdx
  unsigned __int64 v15; // r10
  int v16; // eax
  __int64 v17; // r11
  __int64 v18; // r10
  char v19; // si
  __int16 v20; // di
  unsigned __int16 v21; // r15
  char v22; // si
  char v23; // al
  int v24; // r9d
  const WCHAR *v25; // r8
  __int64 v26; // r10
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r10
  char v30; // dl
  unsigned __int16 v31; // ax
  unsigned __int16 v32; // dx
  char v33; // cl
  unsigned __int16 v34; // di
  char v35; // si
  int v36; // eax
  int v38; // r11d
  const WCHAR *v39; // r9
  __int64 v40; // r10
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r10
  char v44; // dl
  int v45; // eax
  bool v46; // zf
  __int16 v47; // r14
  unsigned __int16 v48; // si
  __int16 v49; // ax
  char v50; // r15
  unsigned __int64 v51; // r14
  __int16 v52; // [rsp+30h] [rbp-38h]
  unsigned __int64 v53; // [rsp+38h] [rbp-30h] BYREF
  _BYTE *v54; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v55[4]; // [rsp+48h] [rbp-20h] BYREF
  char v56; // [rsp+B0h] [rbp+48h]
  const unsigned __int16 *v57; // [rsp+B8h] [rbp+50h]
  unsigned __int16 v58; // [rsp+C0h] [rbp+58h]
  __int16 v59; // [rsp+C8h] [rbp+60h]

  v57 = a2;
  v55[1] = -2;
  v2 = a2;
  v58 = 0;
  v52 = 0;
  v4 = 0;
  LOWORD(v5) = 0;
  v6 = 0;
  v59 = 0;
  v56 = 0;
  *((_QWORD *)this + 8) = 0;
  v7 = *((_BYTE *)this + 72);
  if ( (v7 & 1) == 0 )
  {
    *((_BYTE *)this + 72) = v7 & 0xEF;
    v8 = bsearch(a2, &grandfatheredTagsTable, 0x1Au, 0x10u, CompareGrandfatheredTags);
    if ( v8 )
    {
      v9 = (const WCHAR *)v8[1];
      v10 = 0x80;
      if ( !*v9 )
        v9 = 0;
    }
    else
    {
      v9 = 0;
      v10 = 0;
    }
    *((_BYTE *)this + 72) &= ~0x80u;
    v11 = ((v10 | *((_BYTE *)this + 72)) & 0x80u) != 0;
    *((_BYTE *)this + 72) |= v10;
    if ( v11 )
    {
      if ( v9 )
      {
        v2 = v9;
        v57 = v9;
      }
      else
      {
        *((_BYTE *)this + 72) |= 0x10u;
      }
    }
  }
  if ( Windows::Internal::CLanguage::ParseTag(this, v2) )
  {
    v12 = *((_BYTE *)this + 72);
    if ( (v12 & 2) == 0 )
    {
      v13 = 0;
      v14 = v2;
      v15 = 0;
      v53 = 0;
      while ( 1 )
      {
        v16 = *v14;
        if ( !(_WORD)v16 || v16 == 45 )
          break;
        v17 = 32 * v15;
        if ( (unsigned __int16)(v16 - 48) <= 9u )
          goto LABEL_80;
        if ( (unsigned __int16)(v16 - 97) > 0x19u )
        {
          if ( (unsigned __int16)(v16 - 65) > 0x19u )
          {
LABEL_80:
            *((_BYTE *)this + 72) = v12 & 0xF7;
            goto LABEL_58;
          }
          v18 = -64;
        }
        else
        {
          v18 = -96;
        }
        v15 = v17 + v18 + *v14;
        v53 = v15;
        if ( (unsigned int)++v13 > 8 )
          goto LABEL_80;
        ++v14;
      }
      v19 = v12 & 0xF7 | 8;
      *((_BYTE *)this + 72) = v19;
      v20 = 3;
      if ( (*((_BYTE *)this + 32) & 1) == 0 )
      {
        if ( (v19 & 0x10) == 0 && ((v19 & 0x40) == 0 || *((_BYTE *)this + 48)) )
          v19 &= ~4u;
        v22 = v19 & 0xF7;
        v21 = 0;
LABEL_21:
        *((_BYTE *)this + 72) = v22;
        if ( (v22 & 0x20) != 0 )
          goto LABEL_24;
        if ( (*((_BYTE *)this + 32) & 2) != 0 && InitSearchKey(&v2[*((unsigned __int8 *)this + 38)], 5u, &v53) )
        {
          v54 = 0;
          v55[0] = 0;
          v47 = v53;
          if ( (unsigned __int8)TryFindTableEntry(v53, 0, 4, &v54, v55) )
          {
            v53 = 0;
            v48 = (unsigned __int16)v54;
            if ( (unsigned __int8)TryFindTableEntry(v54, 1, 2, &v53, 0) )
            {
              if ( v21 == (_DWORD)v53 )
              {
                if ( (*(_BYTE *)v55[0] & 1) != 0 )
                {
                  v55[0] = 0;
                  if ( (unsigned __int8)TryFindTableEntry(0, 1, 1, v55, 0) )
                    v48 = v55[0];
                }
                v58 = v48;
                *((_WORD *)this + 18) = *((_WORD *)this + 19);
                *((_DWORD *)this + 8) &= ~2u;
              }
            }
          }
          v49 = 0;
          if ( (*((_BYTE *)this + 32) & 2) != 0 )
            v49 = v47;
          v52 = v49;
          v2 = v57;
        }
        if ( (*((_BYTE *)this + 32) & 4) == 0 )
        {
LABEL_24:
          v23 = *((_BYTE *)this + 72);
          if ( (v23 & 0x20) != 0 )
          {
LABEL_57:
            *((_BYTE *)this + 72) = v23 | 2;
            v6 = v59;
            goto LABEL_58;
          }
          if ( (*((_BYTE *)this + 32) & 8) != 0 )
          {
            v24 = 0;
            v25 = &v2[*((unsigned __int8 *)this + 42)];
            v26 = 0;
            while ( 1 )
            {
              v27 = *v25;
              if ( !(_WORD)v27 || (_DWORD)v27 == 45 )
                break;
              v28 = v26 << v20;
              if ( (unsigned __int16)(v27 - 48) <= 9u )
              {
                if ( v20 == 3 )
                {
                  v20 = 4;
                  v28 = 16;
                }
                else if ( v20 == 5 )
                {
                  goto LABEL_43;
                }
                v26 = v28 + v27 - 47;
              }
              else
              {
                if ( (unsigned __int16)(v27 - 97) > 0x19u )
                {
                  if ( (unsigned __int16)(v27 - 65) > 0x19u )
                    goto LABEL_43;
                  if ( v20 == 3 )
                  {
                    v20 = 5;
                    v29 = -64;
                  }
                  else
                  {
                    if ( v20 == 4 )
                      goto LABEL_43;
                    v29 = -64;
                  }
                }
                else
                {
                  if ( v20 == 3 )
                  {
                    v20 = 5;
                  }
                  else if ( v20 == 4 )
                  {
                    goto LABEL_43;
                  }
                  v29 = -96;
                }
                v26 = v27 + v28 + v29;
              }
              if ( (unsigned int)++v24 > 8 )
                goto LABEL_43;
              ++v25;
            }
            v55[0] = 0;
            v54 = 0;
            if ( (unsigned __int8)TryFindTableEntry(v26, 0, 6, v55, &v54) )
            {
              v5 = LOWORD(v55[0]);
              if ( (*v54 & 1) != 0 )
              {
                v55[0] = 0;
                if ( (unsigned __int8)TryFindTableEntry(v5, 0, 14, v55, 0) )
                  LOWORD(v5) = v55[0];
              }
            }
LABEL_43:
            v30 = *((_BYTE *)this + 72);
            if ( (v30 & 8) != 0 )
              *((_BYTE *)this + 72) = v30 & 0xF7 | ((_WORD)v5 != 0 ? 8 : 0);
          }
          v31 = v58;
          if ( (*((_BYTE *)this + 32) & 0x10) == 0 )
            goto LABEL_46;
          if ( v58 == 23 )
          {
            v45 = CompareStringOrdinal(&v2[*((unsigned __int8 *)this + 44)], -1, L"valencia", -1, 1);
            v32 = 81;
            if ( v45 != 2 )
              v32 = 0;
            v59 = v32;
            v31 = v58;
          }
          else
          {
            if ( v58 != 14
              || (v46 = CompareStringOrdinal(&v2[*((unsigned __int8 *)this + 44)], -1, L"tarask", -1, 1) == 2,
                  v31 = 14,
                  !v46) )
            {
LABEL_46:
              v32 = 0;
              goto LABEL_47;
            }
            v32 = 75;
            v59 = 75;
          }
LABEL_47:
          v33 = *((_BYTE *)this + 72);
          if ( (v33 & 8) == 0 )
          {
LABEL_55:
            if ( (v33 & 0x10) != 0 )
              v23 = v33 & 0xF7 | (v4 != 0 ? 8 : 0) | 4;
            else
              v23 = v33;
            goto LABEL_57;
          }
          v34 = v4;
          v35 = 0;
          v55[0] = 0;
          if ( (_WORD)v5 )
          {
            v50 = *((_BYTE *)this + 8);
            v51 = (unsigned __int64)v31 << 8;
            if ( (unsigned __int8)TryFindTableEntry(
                                    v32 + (((unsigned __int16)v5 + ((v51 + v4) << 9)) << 7),
                                    0,
                                    0,
                                    v55,
                                    0) )
            {
              if ( !v4 )
                v34 = BYTE2(v55[0]);
              if ( !(unsigned __int8)TryFindTableEntry((v51 + v34) << 16, 0, 13, 0, 0) && v50 )
                LOWORD(v5) = 0;
            }
          }
          if ( (unsigned __int16)(v58 - 1) <= 0x21C4u )
          {
            v55[0] = 0;
            if ( !(unsigned __int8)TryFindTableEntry(v58, 0, 1, v55, 0) )
            {
              if ( v34 )
                goto LABEL_51;
              if ( v58 > 0x9FEu )
              {
                if ( v58 == 5611 )
                {
                  v34 = 5;
                  goto LABEL_51;
                }
                if ( v58 != 6229 )
                  goto LABEL_52;
              }
              else if ( v58 != 2558 && v58 != 107 && v58 != 184 && v58 != 2137 )
              {
                goto LABEL_52;
              }
              v34 = 85;
              goto LABEL_51;
            }
            if ( !v34 )
              v34 = v55[0];
            if ( v34 == LOWORD(v55[0]) )
              v35 = 1;
          }
          if ( v34 )
          {
LABEL_51:
            v4 = v34;
            v56 = v35;
          }
LABEL_52:
          v33 = *((_BYTE *)this + 72) & 0xF7 | (v4 != 0 ? 8 : 0);
          if ( v4 )
          {
            v36 = *((_DWORD *)this + 8);
            if ( (v36 & 4) == 0 )
            {
              *((_DWORD *)this + 8) = v36 | 4;
              *((_BYTE *)this + 41) = 0;
            }
          }
          goto LABEL_55;
        }
        v38 = 0;
        v39 = &v2[*((unsigned __int8 *)this + 40)];
        v40 = 0;
        while ( 1 )
        {
          v41 = *v39;
          if ( !(_WORD)v41 || (_DWORD)v41 == 45 )
            break;
          v42 = 32 * v40;
          if ( (unsigned __int16)(v41 - 48) <= 9u )
            goto LABEL_73;
          if ( (unsigned __int16)(v41 - 97) > 0x19u )
          {
            if ( (unsigned __int16)(v41 - 65) > 0x19u )
              goto LABEL_73;
            v43 = -64;
          }
          else
          {
            v43 = -96;
          }
          v40 = v41 + v42 + v43;
          if ( (unsigned int)++v38 > 8 )
            goto LABEL_73;
          ++v39;
        }
        v55[0] = 0;
        if ( (unsigned __int8)TryFindTableEntry(v40, 0, 5, v55, 0) )
          v4 = v55[0];
LABEL_73:
        if ( !v4 )
        {
          if ( CompareStringOrdinal(v2, -1, L"ar-ploc-SA", -1, 1) == 2 )
          {
            v4 = 5;
            LOWORD(v5) = 221;
          }
          else if ( CompareStringOrdinal(v2, -1, L"ja-ploc-JP", -1, 1) == 2 )
          {
            v4 = 68;
          }
          else
          {
            if ( CompareStringOrdinal(v2, -1, L"en-locr-US", -1, 1) != 2 )
              goto LABEL_74;
            v4 = 85;
            LOWORD(v5) = 265;
          }
          *((_BYTE *)this + 72) |= 0x28u;
          v56 = 1;
        }
LABEL_74:
        v44 = *((_BYTE *)this + 72);
        if ( (v44 & 8) != 0 )
          *((_BYTE *)this + 72) = v44 & 0xF7 | (v4 != 0 ? 8 : 0);
        goto LABEL_24;
      }
      v54 = 0;
      if ( (unsigned __int8)TryFindTableEntry(v15, 0, 3, &v54, 0) )
      {
        v21 = (unsigned __int16)v54;
        v58 = (unsigned __int16)v54;
        if ( (_WORD)v54 != 6097 )
        {
LABEL_20:
          v22 = *((_BYTE *)this + 72) & 0xF7 | (v21 != 0 ? 8 : 0);
          goto LABEL_21;
        }
        if ( CompareStringOrdinal(v2, -1, L"qps-ploc", -1, 1) != 2
          && CompareStringOrdinal(v2, -1, L"qps-latn-x-sh", -1, 1) != 2 )
        {
          if ( CompareStringOrdinal(v2, -1, L"qps-plocm", -1, 1) != 2 )
          {
            if ( CompareStringOrdinal(v2, -1, L"qps-ploca", -1, 1) == 2 )
            {
              v21 = 77;
              v58 = 77;
              v4 = 68;
              v56 = 1;
              *((_BYTE *)this + 72) |= 0x20u;
              *((_DWORD *)this + 8) = 133;
              *((_WORD *)this + 20) = 1284;
            }
            goto LABEL_20;
          }
          v58 = 8;
          v4 = 5;
          LOWORD(v5) = 221;
          v56 = 1;
          *((_BYTE *)this + 72) |= 0x20u;
          *((_DWORD *)this + 8) = 133;
          *((_WORD *)this + 20) = 1284;
LABEL_91:
          v21 = v58;
          goto LABEL_20;
        }
        v58 = 38;
        v4 = 85;
        LOWORD(v5) = 265;
        v56 = 1;
        *((_BYTE *)this + 72) |= 0x20u;
      }
      else if ( *((_BYTE *)this + 51) >= 3u )
      {
        if ( CompareStringOrdinal(v2, 3, L"qut", 3, 1) == 2 )
        {
          v21 = 6211;
          v58 = 6211;
          goto LABEL_20;
        }
        goto LABEL_91;
      }
      v21 = v58;
      goto LABEL_20;
    }
  }
LABEL_58:
  *((_WORD *)this + 26) = v58;
  *((_WORD *)this + 30) = v52;
  *((_WORD *)this + 27) = v4;
  *((_WORD *)this + 28) = v5;
  *((_WORD *)this + 29) = v6;
  *((_BYTE *)this + 62) = v56;
  *((_QWORD *)this + 8) = v6 + (((unsigned __int16)v5 + ((v4 + ((unsigned __int64)v58 << 8)) << 9)) << 7);
  return (*((_BYTE *)this + 72) & 8) != 0;
}

```

## disassembly

```asm
0x180006ab0  mov     [rsp-40h+arg_8], rdx
0x180006ab5  push    rbp
0x180006ab6  push    rbx
0x180006ab7  push    rsi
0x180006ab8  push    rdi
0x180006ab9  push    r12
0x180006abb  push    r13
0x180006abd  push    r14
0x180006abf  push    r15
0x180006ac1  mov     rbp, rsp
0x180006ac4  sub     rsp, 68h
0x180006ac8  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180006ad0  mov     r14, rdx
0x180006ad3  mov     rbx, rcx
0x180006ad6  xor     edi, edi
0x180006ad8  mov     [rbp+arg_10], edi
0x180006adb  mov     dword ptr [rbp+var_38], edi
0x180006ade  mov     r12d, edi
0x180006ae1  mov     r13d, edi
0x180006ae4  mov     r15d, edi
0x180006ae7  mov     [rbp+arg_18], edi
0x180006aea  mov     [rbp+arg_0], dil
0x180006aee  mov     [rcx+40h], rdi
0x180006af2  movzx   eax, byte ptr [rcx+48h]
0x180006af6  test    al, 1
0x180006af8  jnz     short loc_180006B41
0x180006afa  and     al, 0EFh
0x180006afc  mov     [rcx+48h], al
0x180006aff  lea     rax, CompareGrandfatheredTags
0x180006b06  mov     [rsp+68h+CompareFunction], rax; CompareFunction
0x180006b0b  mov     r9d, 10h; SizeOfElements
0x180006b11  mov     r8d, 1Ah; NumOfElements
0x180006b17  lea     rdx, ?grandfatheredTagsTable@@3QBUGrandfatheredTagsTableEntry@@B; Base
0x180006b1e  mov     rcx, r14; Key
0x180006b21  call    cs:__imp_bsearch
0x180006b27  test    rax, rax
0x180006b2a  jnz     loc_1800072CB
0x180006b30  mov     edx, edi
0x180006b32  xor     cl, cl
0x180006b34  and     byte ptr [rbx+48h], 7Fh
0x180006b38  or      [rbx+48h], cl
0x180006b3b  jl      loc_1800072DD
0x180006b41  mov     rdx, r14; unsigned __int16 *
0x180006b44  mov     rcx, rbx; this
0x180006b47  call    ?ParseTag@CLanguage@Internal@Windows@@IEAA_NPEBG@Z; Windows::Internal::CLanguage::ParseTag(ushort const *)
0x180006b4c  test    al, al
0x180006b4e  jz      loc_180006E78
0x180006b54  movzx   esi, byte ptr [rbx+48h]
0x180006b58  test    sil, 2
0x180006b5c  jnz     loc_180006E78
0x180006b62  mov     r9d, 5
0x180006b68  mov     r8d, edi
0x180006b6b  mov     rdx, r14
0x180006b6e  mov     dil, 1
0x180006b71  xor     r10d, r10d
0x180006b74  mov     [rbp+var_30], r10
0x180006b78  nop     dword ptr [rax+rax+00000000h]
0x180006b80  movzx   eax, word ptr [rdx]
0x180006b83  test    ax, ax
0x180006b86  jz      loc_180006C39
0x180006b8c  cmp     eax, 2Dh ; '-'
0x180006b8f  jz      loc_180006C39
0x180006b95  movzx   ecx, r9b
0x180006b99  shl     r10, cl
0x180006b9c  mov     r11, r10
0x180006b9f  lea     ecx, [rax-30h]
0x180006ba2  cmp     cx, 9
0x180006ba6  jbe     loc_18000705C
0x180006bac  lea     ecx, [rax-61h]
0x180006baf  cmp     cx, 19h
0x180006bb3  ja      short loc_180006C06
0x180006bb5  cmp     r9w, 3
0x180006bba  jz      loc_180006F0F
0x180006bc0  cmp     r9w, 4
0x180006bc5  jz      loc_1800070A9
0x180006bcb  mov     rcx, 0FFFFFFFFFFFFFFAAh
0x180006bd2  mov     r10, 0FFFFFFFFFFFFFFA0h
0x180006bd9  cmp     r9w, 6
0x180006bde  cmovnz  rcx, r10
0x180006be2  mov     r10, rax
0x180006be5  lea     rax, [r11+rcx]
0x180006be9  add     r10, rax
0x180006bec  mov     [rbp+var_30], r10
0x180006bf0  inc     r8d
0x180006bf3  cmp     r8d, 8
0x180006bf7  ja      loc_1800070A9
0x180006bfd  add     rdx, 2
0x180006c01  jmp     loc_180006B80
0x180006c06  lea     ecx, [rax-41h]
0x180006c09  cmp     cx, 19h
0x180006c0d  ja      loc_1800070A9
0x180006c13  cmp     r9w, 3
0x180006c18  jz      loc_180006EDE
0x180006c1e  cmp     r9w, 4
0x180006c23  jz      loc_1800070A9
0x180006c29  mov     rcx, 0FFFFFFFFFFFFFFCAh
0x180006c30  mov     r10, 0FFFFFFFFFFFFFFC0h
0x180006c37  jmp     short loc_180006BD9
0x180006c39  and     sil, 0F7h
0x180006c3d  shl     dil, 3
0x180006c41  or      sil, dil
0x180006c44  mov     [rbx+48h], sil
0x180006c48  mov     edi, 3
0x180006c4d  test    byte ptr [rbx+20h], 1
0x180006c51  jz      loc_1800070DE
0x180006c57  mov     [rbp+var_28], r12
0x180006c5b  mov     [rsp+68h+CompareFunction], r12
0x180006c60  lea     r9, [rbp+var_28]
0x180006c64  mov     r8d, edi
0x180006c67  xor     edx, edx
0x180006c69  mov     rcx, r10
0x180006c6c  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x180006c71  test    al, al
0x180006c73  jz      loc_180007310
0x180006c79  movzx   r15d, word ptr [rbp+var_28]
0x180006c7e  mov     [rbp+arg_10], r15d
0x180006c82  mov     eax, 17D1h
0x180006c87  cmp     r15w, ax
0x180006c8b  jz      loc_18000710B
0x180006c91  mov     ecx, 5
0x180006c96  movzx   eax, r15w
0x180006c9a  neg     ax
0x180006c9d  sbb     sil, sil
0x180006ca0  and     sil, 8
0x180006ca4  movzx   eax, byte ptr [rbx+48h]
0x180006ca8  and     al, 0F7h
0x180006caa  or      sil, al
0x180006cad  mov     [rbx+48h], sil
0x180006cb1  test    sil, 20h
0x180006cb5  jnz     short loc_180006CCB
0x180006cb7  test    byte ptr [rbx+20h], 2
0x180006cbb  jnz     loc_180007354
0x180006cc1  test    byte ptr [rbx+20h], 4
0x180006cc5  jnz     loc_180006F24
0x180006ccb  movzx   eax, byte ptr [rbx+48h]
0x180006ccf  test    al, 20h
0x180006cd1  jnz     loc_180006E6F
0x180006cd7  xor     r15d, r15d
0x180006cda  test    byte ptr [rbx+20h], 8
0x180006cde  jz      loc_180006DE9
0x180006ce4  mov     r9d, r15d
0x180006ce7  movzx   eax, byte ptr [rbx+2Ah]
0x180006ceb  lea     r8, [r14+rax*2]
0x180006cef  mov     r10d, r15d
0x180006cf2  movzx   edx, word ptr [r8]
0x180006cf6  test    dx, dx
0x180006cf9  jz      loc_180006D91
0x180006cff  cmp     edx, 2Dh ; '-'
0x180006d02  jz      loc_180006D91
0x180006d08  movzx   ecx, dil
0x180006d0c  shl     r10, cl
0x180006d0f  mov     rcx, r10
0x180006d12  lea     eax, [rdx-30h]
0x180006d15  cmp     ax, 9
0x180006d19  jbe     loc_180007086
0x180006d1f  lea     eax, [rdx-61h]
0x180006d22  cmp     ax, 19h
0x180006d26  ja      short loc_180006D68
0x180006d28  cmp     di, 3
0x180006d2c  jz      loc_180006F1A
0x180006d32  cmp     di, 4
0x180006d36  jz      loc_180006DCC
0x180006d3c  mov     rax, 0FFFFFFFFFFFFFFAAh
0x180006d43  mov     r10, 0FFFFFFFFFFFFFFA0h
0x180006d4a  cmp     di, 6
0x180006d4e  cmovnz  rax, r10
0x180006d52  lea     r10, [rcx+rax]
0x180006d56  add     r10, rdx
0x180006d59  inc     r9d
0x180006d5c  cmp     r9d, 8
0x180006d60  ja      short loc_180006DCC
0x180006d62  add     r8, 2
0x180006d66  jmp     short loc_180006CF2
0x180006d68  lea     eax, [rdx-41h]
0x180006d6b  cmp     ax, 19h
0x180006d6f  ja      short loc_180006DCC
0x180006d71  cmp     di, 3
0x180006d75  jz      loc_180006EF7
0x180006d7b  cmp     di, 4
0x180006d7f  jz      short loc_180006DCC
0x180006d81  mov     rax, 0FFFFFFFFFFFFFFCAh
0x180006d88  mov     r10, 0FFFFFFFFFFFFFFC0h
0x180006d8f  jmp     short loc_180006D4A
0x180006d91  mov     [rbp+var_20], r15
0x180006d95  mov     [rbp+var_28], r15
0x180006d99  lea     rax, [rbp+var_28]
0x180006d9d  mov     [rsp+68h+CompareFunction], rax
0x180006da2  lea     r9, [rbp+var_20]
0x180006da6  xor     edx, edx
0x180006da8  mov     r8d, 6
0x180006dae  mov     rcx, r10
0x180006db1  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x180006db6  test    al, al
0x180006db8  jz      short loc_180006DCC
0x180006dba  movzx   r13d, word ptr [rbp+var_20]
0x180006dbf  mov     rax, [rbp+var_28]
0x180006dc3  test    byte ptr [rax], 1
0x180006dc6  jnz     loc_1800074CD
0x180006dcc  movzx   edx, byte ptr [rbx+48h]
0x180006dd0  test    dl, 8
0x180006dd3  jz      short loc_180006DE9
0x180006dd5  movzx   eax, r13w
0x180006dd9  neg     ax
0x180006ddc  sbb     cl, cl
0x180006dde  and     cl, 8
0x180006de1  and     dl, 0F7h
0x180006de4  or      cl, dl
0x180006de6  mov     [rbx+48h], cl
0x180006de9  mov     eax, [rbp+arg_10]
0x180006dec  test    byte ptr [rbx+20h], 10h
0x180006df0  jnz     loc_1800071BF
0x180006df6  mov     edx, [rbp+arg_18]
0x180006df9  movzx   ecx, byte ptr [rbx+48h]
0x180006dfd  test    cl, 8
0x180006e00  jz      short loc_180006E63
0x180006e02  movzx   edi, r12w
0x180006e06  xor     sil, sil
0x180006e09  mov     [rbp+var_20], r15
0x180006e0d  test    r13w, r13w
0x180006e11  jnz     loc_1800074F7
0x180006e17  mov     ecx, [rbp+arg_10]
0x180006e1a  lea     eax, [rcx-1]
0x180006e1d  mov     edx, 21C4h
0x180006e22  cmp     ax, dx
0x180006e25  jbe     loc_180007590
0x180006e2b  test    di, di
0x180006e2e  jz      short loc_180006E38
0x180006e30  movzx   r12d, di
0x180006e34  mov     [rbp+arg_0], sil
0x180006e38  movzx   eax, r12w
0x180006e3c  neg     ax
0x180006e3f  sbb     cl, cl
0x180006e41  and     cl, 8
0x180006e44  movzx   eax, byte ptr [rbx+48h]
0x180006e48  and     al, 0F7h
0x180006e4a  or      cl, al
0x180006e4c  test    r12w, r12w
0x180006e50  jz      short loc_180006E63
0x180006e52  mov     eax, [rbx+20h]
0x180006e55  test    al, 4
0x180006e57  jnz     short loc_180006E63
0x180006e59  or      eax, 4
0x180006e5c  mov     [rbx+20h], eax
0x180006e5f  mov     byte ptr [rbx+29h], 0
0x180006e63  test    cl, 10h
0x180006e66  jnz     loc_180007627
0x180006e6c  movzx   eax, cl
0x180006e6f  or      al, 2
0x180006e71  mov     [rbx+48h], al
0x180006e74  mov     r15d, [rbp+arg_18]
0x180006e78  mov     eax, [rbp+arg_10]
0x180006e7b  mov     [rbx+34h], ax
0x180006e7f  mov     ecx, dword ptr [rbp+var_38]
0x180006e82  mov     [rbx+3Ch], cx
0x180006e86  mov     [rbx+36h], r12w
0x180006e8b  mov     [rbx+38h], r13w
0x180006e90  mov     [rbx+3Ah], r15w
0x180006e95  movzx   ecx, [rbp+arg_0]
0x180006e99  mov     [rbx+3Eh], cl
0x180006e9c  movzx   ecx, ax
0x180006e9f  shl     rcx, 8
0x180006ea3  movzx   eax, r12w
0x180006ea7  add     rcx, rax
0x180006eaa  shl     rcx, 9
0x180006eae  movzx   eax, r13w
0x180006eb2  add     rcx, rax
0x180006eb5  shl     rcx, 7
0x180006eb9  movzx   eax, r15w
0x180006ebd  add     rcx, rax
0x180006ec0  mov     [rbx+40h], rcx
0x180006ec4  movzx   eax, byte ptr [rbx+48h]
0x180006ec8  shr     al, 3
0x180006ecb  and     al, 1
0x180006ecd  add     rsp, 68h
0x180006ed1  pop     r15
0x180006ed3  pop     r14
0x180006ed5  pop     r13
0x180006ed7  pop     r12
0x180006ed9  pop     rdi
0x180006eda  pop     rsi
0x180006edb  pop     rbx
0x180006edc  pop     rbp
0x180006edd  retn
0x180006ede  mov     r9d, 5
0x180006ee4  mov     rcx, 0FFFFFFFFFFFFFFCAh
0x180006eeb  mov     r10, 0FFFFFFFFFFFFFFC0h
0x180006ef2  jmp     loc_180006BD9
0x180006ef7  mov     edi, 5
0x180006efc  mov     rax, 0FFFFFFFFFFFFFFCAh
0x180006f03  mov     r10, 0FFFFFFFFFFFFFFC0h
0x180006f0a  jmp     loc_180006D4A
0x180006f0f  mov     r9d, 5
0x180006f15  jmp     loc_180006BCB
0x180006f1a  mov     edi, 5
0x180006f1f  jmp     loc_180006D3C
0x180006f24  movzx   r8d, cx
0x180006f28  xor     r11d, r11d
0x180006f2b  movzx   eax, byte ptr [rbx+28h]
0x180006f2f  lea     r9, [r14+rax*2]
0x180006f33  xor     r10d, r10d
  ... truncated ...
```

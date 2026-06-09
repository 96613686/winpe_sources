# Windows::Internal::CLanguage::ValidateTag(ushort const *)

- ea: `0x18003f570`
- end: `0x1800401f1`
- name: `?ValidateTag@CLanguage@Internal@Windows@@IEAA_NPEBG@Z`
- size: `3201`
- prototype: `bool __fastcall(Windows::Internal::CLanguage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f2dc`

## callees

- `0x18003f570`
- `0x180040200`
- `0x180040240`
- `0x180040ea0`
- `0x180049100`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fca6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fce3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fd13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fd43`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fe3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ff85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800400bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800400f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040128`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800401b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fca6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fce3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fd13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fd43`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003fe3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ff85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800400bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800400f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040128`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800401b1`

## pseudocode

```c
bool __fastcall Windows::Internal::CLanguage::ValidateTag(
        Windows::Internal::CLanguage *this,
        const unsigned __int16 *a2)
{
  char v2; // al
  unsigned __int16 v3; // bx
  unsigned __int16 v4; // r14
  unsigned __int16 v5; // r15
  unsigned __int16 v6; // si
  const struct GrandfatheredTagsTableEntry near *const *v9; // rsi
  wchar_t **v10; // r15
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  bool v13; // zf
  const struct GrandfatheredTagsTableEntry near *const *v14; // r14
  int v15; // eax
  const unsigned __int16 *v16; // rcx
  char v17; // al
  bool v18; // sf
  char v19; // di
  unsigned int v20; // r11d
  unsigned __int64 v21; // r10
  const unsigned __int16 *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r10
  char v26; // di
  __int16 v27; // bx
  char v28; // di
  int v29; // edi
  char v30; // al
  int v31; // r9d
  __int64 v32; // r10
  const unsigned __int16 *j; // r8
  __int64 v34; // rdx
  __int64 v35; // r10
  __int64 v36; // rcx
  __int64 v37; // r10
  int v38; // ebx
  char v39; // dl
  char v40; // cl
  char v41; // si
  unsigned __int16 v42; // bx
  char v43; // r14
  unsigned __int64 v44; // rdi
  int v45; // eax
  bool result; // al
  int v47; // r9d
  __int64 v48; // r10
  const unsigned __int16 *i; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r10
  char TableEntry; // al
  char v54; // dl
  __int16 v55; // si
  unsigned __int16 v56; // di
  int v57; // eax
  unsigned __int16 v58; // [rsp+30h] [rbp-30h]
  unsigned __int16 v59; // [rsp+34h] [rbp-2Ch]
  __int16 v60; // [rsp+38h] [rbp-28h]
  unsigned __int64 v61; // [rsp+40h] [rbp-20h] BYREF
  __int64 v62; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v63[2]; // [rsp+50h] [rbp-10h] BYREF
  char v64; // [rsp+A0h] [rbp+40h]
  __int64 v65; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v66; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *((_BYTE *)this + 72);
  v3 = 0;
  v4 = 0;
  LODWORD(v65) = 0;
  v5 = 0;
  v58 = 0;
  v6 = 0;
  v60 = 0;
  LODWORD(v66) = 0;
  v59 = 0;
  v64 = 0;
  *((_QWORD *)this + 8) = 0;
  if ( (v2 & 1) == 0 )
  {
    v9 = &grandfatheredTagsTable;
    *((_BYTE *)this + 72) = v2 & 0xEF;
    v10 = off_180109B00;
    v11 = 26;
    while ( 1 )
    {
      if ( v9 > (const struct GrandfatheredTagsTableEntry near *const *)v10 )
        goto LABEL_15;
      v12 = v11 >> 1;
      if ( !(v11 >> 1) )
        break;
      v13 = (v11 & 1) == 0;
      v11 >>= 1;
      if ( v13 )
        v11 = v12 - 1;
      v14 = &v9[2 * v11];
      v15 = CompareGrandfatheredTags(a2, v14);
      if ( !v15 )
        goto LABEL_14;
      if ( v15 >= 0 )
      {
        v9 = v14 + 2;
        v11 = v12;
      }
      else
      {
        v10 = (wchar_t **)(v14 - 2);
      }
    }
    if ( !v11 )
      goto LABEL_15;
    v14 = 0;
    if ( !(unsigned int)CompareGrandfatheredTags(a2, v9) )
      v14 = v9;
LABEL_14:
    if ( !v14 )
    {
LABEL_15:
      v16 = 0;
      v17 = 0;
      goto LABEL_16;
    }
    v16 = 0;
    if ( **((_WORD **)v14 + 1) )
      v16 = (const unsigned __int16 *)*((_QWORD *)v14 + 1);
    v17 = 0x80;
LABEL_16:
    *((_BYTE *)this + 72) &= ~0x80u;
    v18 = ((v17 | *((_BYTE *)this + 72)) & 0x80u) != 0;
    *((_BYTE *)this + 72) |= v17;
    v5 = v66;
    v4 = 0;
    v3 = v65;
    v6 = 0;
    if ( v18 )
    {
      if ( v16 )
        a2 = v16;
      else
        *((_BYTE *)this + 72) |= 0x10u;
    }
  }
  if ( Windows::Internal::CLanguage::ParseTag(this, a2) )
  {
    v19 = *((_BYTE *)this + 72);
    if ( (v19 & 2) == 0 )
    {
      v20 = 0;
      v21 = 0;
      v22 = a2;
      v61 = 0;
      while ( 1 )
      {
        v23 = *v22;
        if ( !(_WORD)v23 || (_DWORD)v23 == 45 )
          break;
        v24 = 32 * v21;
        if ( (unsigned __int16)(v23 - 48) <= 9u )
          goto LABEL_103;
        if ( (unsigned __int16)(v23 - 97) > 0x19u )
        {
          if ( (unsigned __int16)(v23 - 65) > 0x19u )
          {
LABEL_103:
            *((_BYTE *)this + 72) = v19 & 0xF7;
            goto LABEL_77;
          }
          v25 = -64;
        }
        else
        {
          v25 = -96;
        }
        v21 = v23 + v24 + v25;
        ++v20;
        v61 = v21;
        if ( v20 > 8 )
          goto LABEL_103;
        ++v22;
      }
      v26 = v19 | 8;
      v27 = 3;
      v13 = (*((_BYTE *)this + 32) & 1) == 0;
      *((_BYTE *)this + 72) = v26;
      if ( v13 )
      {
        if ( (v26 & 0x10) == 0 && ((v26 & 0x40) == 0 || *((_BYTE *)this + 48)) )
          v26 &= ~4u;
        v28 = v26 & 0xF7;
LABEL_31:
        *((_BYTE *)this + 72) = v28;
        if ( (v28 & 0x20) != 0 )
          goto LABEL_34;
        v29 = *((_DWORD *)this + 8);
        if ( (v29 & 2) != 0 && InitSearchKey(&a2[*((unsigned __int8 *)this + 38)], 5u, &v61) )
        {
          v55 = v61;
          v62 = 0;
          v63[0] = 0;
          if ( (unsigned __int8)TryFindTableEntry(v61, 0, 4, &v62, v63) )
          {
            v56 = v62;
            v61 = 0;
            if ( (unsigned __int8)TryFindTableEntry(v62, 1, 2, &v61, 0) )
            {
              if ( v4 == (_DWORD)v61 )
              {
                if ( (*(_BYTE *)v63[0] & 1) != 0 )
                {
                  v63[0] = 0;
                  if ( (unsigned __int8)TryFindTableEntry(0, 1, 1, v63, 0) )
                    v56 = v63[0];
                }
                v4 = v56;
                *((_WORD *)this + 18) = *((_WORD *)this + 19);
                *((_DWORD *)this + 8) &= ~2u;
                v58 = v56;
              }
            }
          }
          v29 = *((_DWORD *)this + 8);
          if ( (v29 & 2) != 0 )
          {
            v60 = v55;
            v6 = 0;
          }
          else
          {
            v6 = 0;
            v60 = 0;
          }
        }
        if ( (v29 & 4) == 0 )
        {
LABEL_34:
          v5 = v66;
          goto LABEL_35;
        }
        v47 = 0;
        v48 = 0;
        for ( i = &a2[*((unsigned __int8 *)this + 40)]; ; ++i )
        {
          v50 = *i;
          if ( !(_WORD)v50 || (_DWORD)v50 == 45 )
            break;
          v51 = 32 * v48;
          if ( (unsigned __int16)(v50 - 48) <= 9u )
            goto LABEL_115;
          if ( (unsigned __int16)(v50 - 97) > 0x19u )
          {
            if ( (unsigned __int16)(v50 - 65) > 0x19u )
            {
LABEL_115:
              v5 = v66;
              goto LABEL_98;
            }
            v52 = -64;
          }
          else
          {
            v52 = -96;
          }
          v48 = v50 + v51 + v52;
          if ( (unsigned int)++v47 > 8 )
            goto LABEL_115;
        }
        v63[0] = 0;
        TableEntry = TryFindTableEntry(v48, 0, 5, v63, 0);
        v5 = v66;
        if ( TableEntry )
          v5 = v63[0];
LABEL_98:
        if ( v5 )
        {
LABEL_99:
          v54 = *((_BYTE *)this + 72);
          if ( (v54 & 8) != 0 )
            *((_BYTE *)this + 72) = v54 & 0xF7 | (v5 != 0 ? 8 : 0);
LABEL_35:
          v30 = *((_BYTE *)this + 72);
          if ( (v30 & 0x20) != 0 )
          {
LABEL_76:
            v3 = v65;
            *((_BYTE *)this + 72) = v30 | 2;
            goto LABEL_77;
          }
          if ( (*((_BYTE *)this + 32) & 8) != 0 )
          {
            v31 = 0;
            v32 = 0;
            for ( j = &a2[*((unsigned __int8 *)this + 42)]; ; ++j )
            {
              v34 = *j;
              if ( !(_WORD)v34 || (_DWORD)v34 == 45 )
                break;
              v35 = v32 << v27;
              v36 = v35;
              if ( (unsigned __int16)(v34 - 48) <= 9u )
              {
                if ( v27 == 3 )
                {
                  v32 = v34 - 47 + 16;
                  v27 = 4;
                }
                else
                {
                  if ( v27 == 5 )
                    goto LABEL_85;
                  v32 = v35 + v34 - 47;
                }
              }
              else
              {
                if ( (unsigned __int16)(v34 - 97) > 0x19u )
                {
                  if ( (unsigned __int16)(v34 - 65) > 0x19u )
                    goto LABEL_85;
                  if ( v27 == 3 )
                  {
                    v27 = 5;
                    v37 = -64;
                  }
                  else
                  {
                    if ( v27 == 4 )
                      goto LABEL_85;
                    v37 = -64;
                  }
                }
                else
                {
                  if ( v27 == 3 )
                  {
                    v27 = 5;
                  }
                  else if ( v27 == 4 )
                  {
                    goto LABEL_85;
                  }
                  v37 = -96;
                }
                v32 = v34 + v36 + v37;
              }
              if ( (unsigned int)++v31 > 8 )
                goto LABEL_85;
            }
            v66 = 0;
            v63[0] = 0;
            if ( !(unsigned __int8)TryFindTableEntry(v32, 0, 6, &v66, v63) )
            {
LABEL_85:
              LOWORD(v38) = v65;
              goto LABEL_50;
            }
            v38 = (unsigned __int16)v66;
            LODWORD(v65) = (unsigned __int16)v66;
            if ( (*(_BYTE *)v63[0] & 1) != 0 )
            {
              v65 = 0;
              if ( (unsigned __int8)TryFindTableEntry((unsigned __int16)v66, 0, 14, &v65, 0) )
                LOWORD(v38) = v65;
              LODWORD(v65) = v38;
            }
LABEL_50:
            v39 = *((_BYTE *)this + 72);
            if ( (v39 & 8) != 0 )
              *((_BYTE *)this + 72) = v39 & 0xF7 | ((_WORD)v38 != 0 ? 8 : 0);
          }
          if ( (*((_BYTE *)this + 32) & 0x10) == 0 )
          {
LABEL_53:
            v40 = *((_BYTE *)this + 72);
            if ( (v40 & 8) == 0 )
            {
LABEL_74:
              if ( (v40 & 0x10) != 0 )
                v30 = v40 & 0xF7 | (v5 != 0 ? 8 : 0) | 4;
              else
                v30 = v40;
              goto LABEL_76;
            }
            v41 = 0;
            v66 = 0;
            v42 = v5;
            if ( (_WORD)v65 )
            {
              v43 = *((_BYTE *)this + 8);
              v44 = (unsigned __int64)v58 << 8;
              if ( !(unsigned __int8)TryFindTableEntry(
                                       v59 + (((unsigned __int16)v65 + ((v44 + v5) << 9)) << 7),
                                       0,
                                       0,
                                       &v66,
                                       0) )
                goto LABEL_86;
              if ( !v5 )
                v42 = BYTE2(v66);
              if ( (unsigned __int8)TryFindTableEntry((v44 + v42) << 16, 0, 13, 0, 0) )
              {
LABEL_86:
                v4 = v58;
              }
              else
              {
                v13 = v43 == 0;
                v4 = v58;
                if ( !v13 )
                  LODWORD(v65) = 0;
              }
            }
            if ( (unsigned __int16)(v4 - 1) > 0x21C4u )
            {
LABEL_67:
              if ( !v42 )
                goto LABEL_71;
              goto LABEL_70;
            }
            v66 = 0;
            if ( (unsigned __int8)TryFindTableEntry(v4, 0, 1, &v66, 0) )
            {
              if ( !v42 )
                v42 = v66;
              if ( v42 == (_WORD)v66 )
                v41 = 1;
              goto LABEL_67;
            }
            if ( !v42 )
            {
              if ( v4 != 184 && v4 != 107 && v4 != 2137 && v4 != 2558 )
              {
                if ( v4 == 5611 )
                {
                  v42 = 5;
                  goto LABEL_70;
                }
                if ( v4 != 6229 )
                  goto LABEL_71;
              }
              v42 = 85;
            }
LABEL_70:
            v5 = v42;
            v64 = v41;
LABEL_71:
            v6 = v59;
            v40 = *((_BYTE *)this + 72) & 0xF7 | (v5 != 0 ? 8 : 0);
            if ( v5 )
            {
              v45 = *((_DWORD *)this + 8);
              if ( (v45 & 4) == 0 )
              {
                *((_DWORD *)this + 8) = v45 | 4;
                *((_BYTE *)this + 41) = 0;
              }
            }
            goto LABEL_74;
          }
          if ( v4 == 23 )
          {
            if ( CompareStringOrdinal(&a2[*((unsigned __int8 *)this + 44)], -1, L"valencia", -1, 1) != 2 )
              goto LABEL_53;
            v6 = 81;
          }
          else
          {
            if ( v4 != 14 || CompareStringOrdinal(&a2[*((unsigned __int8 *)this + 44)], -1, L"tarask", -1, 1) != 2 )
              goto LABEL_53;
            v6 = 75;
          }
          v59 = v6;
          goto LABEL_53;
        }
        if ( CompareStringOrdinal(a2, -1, L"ar-ploc-SA", -1, 1) == 2 )
        {
          v57 = 221;
          v5 = 5;
        }
        else
        {
          if ( CompareStringOrdinal(a2, -1, L"ja-ploc-JP", -1, 1) == 2 )
          {
            v5 = 68;
LABEL_163:
            *((_BYTE *)this + 72) |= 0x28u;
            v64 = 1;
            goto LABEL_99;
          }
          if ( CompareStringOrdinal(a2, -1, L"en-locr-US", -1, 1) != 2 )
            goto LABEL_99;
          v57 = 265;
          v5 = 85;
        }
        LODWORD(v65) = v57;
        goto LABEL_163;
      }
      v62 = 0;
      if ( !(unsigned __int8)TryFindTableEntry(v21, 0, 3, &v62, 0) )
      {
        if ( *((_BYTE *)this + 51) >= 3u && CompareStringOrdinal(a2, 3, L"qut", 3, 1) == 2 )
        {
          v4 = 6211;
          v58 = 6211;
        }
        goto LABEL_30;
      }
      v4 = v62;
      v58 = v62;
      if ( (_WORD)v62 == 6097 )
      {
        if ( CompareStringOrdinal(a2, -1, L"qps-ploc", -1, 1) == 2
          || CompareStringOrdinal(a2, -1, L"qps-latn-x-sh", -1, 1) == 2 )
        {
          *((_BYTE *)this + 72) |= 0x20u;
          LODWORD(v66) = 85;
          v4 = 38;
          v58 = 38;
          LODWORD(v65) = 265;
          v64 = 1;
        }
        else
        {
          if ( CompareStringOrdinal(a2, -1, L"qps-plocm", -1, 1) == 2 )
          {
            v4 = 8;
            LODWORD(v66) = 5;
            LODWORD(v65) = 221;
          }
          else
          {
            if ( CompareStringOrdinal(a2, -1, L"qps-ploca", -1, 1) != 2 )
              goto LABEL_30;
            v4 = 77;
            LODWORD(v66) = 68;
          }
          *((_BYTE *)this + 72) |= 0x20u;
          *((_DWORD *)this + 8) = 133;
          *((_WORD *)this + 20) = 1284;
          v58 = v4;
          v64 = 1;
        }
      }
LABEL_30:
      v28 = *((_BYTE *)this + 72) & 0xF7 | (v4 != 0 ? 8 : 0);
      goto LABEL_31;
    }
  }
LABEL_77:
  *((_WORD *)this + 30) = v60;
  *((_BYTE *)this + 62) = v64;
  *((_WORD *)this + 28) = v3;
  *((_WORD *)this + 26) = v4;
  result = (*((_BYTE *)this + 72) & 8) != 0;
  *((_WORD *)this + 27) = v5;
  *((_WORD *)this + 29) = v6;
  *((_QWORD *)this + 8) = v6 + ((v3 + ((v5 + ((unsigned __int64)v4 << 8)) << 9)) << 7);
  return result;
}

```

## disassembly

```asm
0x18003f570  mov     [rsp-38h+arg_8], rbx
0x18003f575  push    rbp
0x18003f576  push    rsi
0x18003f577  push    rdi
0x18003f578  push    r12
0x18003f57a  push    r13
0x18003f57c  push    r14
0x18003f57e  push    r15
0x18003f580  mov     rbp, rsp
0x18003f583  sub     rsp, 60h
0x18003f587  movzx   eax, byte ptr [rcx+48h]
0x18003f58b  xor     ebx, ebx
0x18003f58d  xor     r14d, r14d
0x18003f590  mov     dword ptr [rbp+arg_10], ebx
0x18003f593  xor     r15d, r15d
0x18003f596  mov     [rbp+var_30], r14d
0x18003f59a  xor     esi, esi
0x18003f59c  mov     dword ptr [rbp+var_28], r14d
0x18003f5a0  mov     dword ptr [rbp+arg_18], r15d
0x18003f5a4  mov     r12, rdx
0x18003f5a7  mov     [rbp+var_2C], esi
0x18003f5aa  mov     r13, rcx
0x18003f5ad  mov     [rbp+arg_0], bl
0x18003f5b0  mov     [rcx+40h], rbx
0x18003f5b4  test    al, 1
0x18003f5b6  jnz     loc_18003F65D
0x18003f5bc  and     al, 0EFh
0x18003f5be  lea     rsi, ?grandfatheredTagsTable@@3QBUGrandfatheredTagsTableEntry@@B; GrandfatheredTagsTableEntry const near * const grandfatheredTagsTable
0x18003f5c5  mov     [rcx+48h], al
0x18003f5c8  lea     r15, off_180109B00; "zh-xiang"
0x18003f5cf  mov     edi, 1Ah
0x18003f5d4  cmp     rsi, r15
0x18003f5d7  ja      short loc_18003F63C
0x18003f5d9  mov     rbx, rdi
0x18003f5dc  shr     rbx, 1
0x18003f5df  jz      short loc_18003F61A
0x18003f5e1  test    dil, 1
0x18003f5e5  lea     rax, [rbx-1]
0x18003f5e9  mov     rdi, rbx
0x18003f5ec  mov     rcx, r12
0x18003f5ef  cmovz   rdi, rax
0x18003f5f3  mov     r14, rdi
0x18003f5f6  shl     r14, 4
0x18003f5fa  add     r14, rsi
0x18003f5fd  mov     rdx, r14
0x18003f600  call    CompareGrandfatheredTags
0x18003f605  test    eax, eax
0x18003f607  jz      short loc_18003F633
0x18003f609  jns     short loc_18003F611
0x18003f60b  lea     r15, [r14-10h]
0x18003f60f  jmp     short loc_18003F5D4
0x18003f611  lea     rsi, [r14+10h]
0x18003f615  mov     rdi, rbx
0x18003f618  jmp     short loc_18003F5D4
0x18003f61a  test    rdi, rdi
0x18003f61d  jz      short loc_18003F63C
0x18003f61f  mov     rdx, rsi
0x18003f622  mov     rcx, r12
0x18003f625  call    CompareGrandfatheredTags
0x18003f62a  xor     r14d, r14d
0x18003f62d  test    eax, eax
0x18003f62f  cmovz   r14, rsi
0x18003f633  test    r14, r14
0x18003f636  jnz     loc_18003FDB2
0x18003f63c  xor     ecx, ecx
0x18003f63e  xor     al, al
0x18003f640  and     byte ptr [r13+48h], 7Fh
0x18003f645  or      [r13+48h], al
0x18003f649  mov     r15d, dword ptr [rbp+arg_18]
0x18003f64d  mov     r14d, [rbp+var_30]
0x18003f651  mov     ebx, dword ptr [rbp+arg_10]
0x18003f654  mov     esi, [rbp+var_2C]
0x18003f657  jl      loc_18003FDC8
0x18003f65d  mov     rdx, r12; unsigned __int16 *
0x18003f660  mov     rcx, r13; this
0x18003f663  call    ?ParseTag@CLanguage@Internal@Windows@@IEAA_NPEBG@Z; Windows::Internal::CLanguage::ParseTag(ushort const *)
0x18003f668  test    al, al
0x18003f66a  jz      loc_18003FA0F
0x18003f670  movzx   edi, byte ptr [r13+48h]
0x18003f675  test    dil, 2
0x18003f679  jnz     loc_18003FA0F
0x18003f67f  xor     r11d, r11d
0x18003f682  mov     r8d, 5
0x18003f688  xor     r10d, r10d
0x18003f68b  mov     r9, r12
0x18003f68e  mov     [rbp+var_20], r10
0x18003f692  movzx   edx, word ptr [r9]
0x18003f696  test    dx, dx
0x18003f699  jz      short loc_18003F70F
0x18003f69b  cmp     edx, 2Dh ; '-'
0x18003f69e  jz      short loc_18003F70F
0x18003f6a0  movzx   ecx, r8b
0x18003f6a4  lea     eax, [rdx-30h]
0x18003f6a7  shl     r10, cl
0x18003f6aa  mov     rcx, r10
0x18003f6ad  cmp     ax, 9
0x18003f6b1  jbe     loc_18003FE01
0x18003f6b7  lea     eax, [rdx-61h]
0x18003f6ba  cmp     ax, 19h
0x18003f6be  ja      loc_18003FA7D
0x18003f6c4  cmp     r8w, 3
0x18003f6c9  jz      loc_18003FAD7
0x18003f6cf  cmp     r8w, 4
0x18003f6d4  jz      loc_18003FC6D
0x18003f6da  mov     rax, 0FFFFFFFFFFFFFFAAh
0x18003f6e1  mov     r10, 0FFFFFFFFFFFFFFA0h
0x18003f6e8  cmp     r8w, 6
0x18003f6ed  cmovnz  rax, r10
0x18003f6f1  lea     r10, [rcx+rax]
0x18003f6f5  add     r10, rdx
0x18003f6f8  inc     r11d
0x18003f6fb  mov     [rbp+var_20], r10
0x18003f6ff  cmp     r11d, 8
0x18003f703  ja      loc_18003FC6D
0x18003f709  add     r9, 2
0x18003f70d  jmp     short loc_18003F692
0x18003f70f  or      dil, 8
0x18003f713  mov     ebx, 3
0x18003f718  test    byte ptr [r13+20h], 1
0x18003f71d  mov     r15d, 0DDh
0x18003f723  mov     [r13+48h], dil
0x18003f727  jz      loc_18003FD91
0x18003f72d  xor     eax, eax
0x18003f72f  lea     r9, [rbp+var_18]
0x18003f733  mov     r8d, ebx
0x18003f736  mov     [rbp+var_18], rax
0x18003f73a  xor     edx, edx
0x18003f73c  mov     qword ptr [rsp+60h+bIgnoreCase], rax
0x18003f741  mov     rcx, r10
0x18003f744  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x18003f749  test    al, al
0x18003f74b  jz      loc_18003FF64
0x18003f751  movzx   r14d, word ptr [rbp+var_18]
0x18003f756  mov     eax, 17D1h
0x18003f75b  mov     [rbp+var_30], r14d
0x18003f75f  cmp     r14w, ax
0x18003f763  jz      loc_18003FCC8
0x18003f769  mov     ecx, 5
0x18003f76e  movzx   eax, r14w
0x18003f772  neg     ax
0x18003f775  movzx   eax, byte ptr [r13+48h]
0x18003f77a  sbb     dil, dil
0x18003f77d  and     al, 0F7h
0x18003f77f  and     dil, 8
0x18003f783  or      dil, al
0x18003f786  mov     [r13+48h], dil
0x18003f78a  test    dil, 20h
0x18003f78e  jnz     short loc_18003F7A8
0x18003f790  mov     edi, [r13+20h]
0x18003f794  test    dil, 2
0x18003f798  jnz     loc_18003FFAE
0x18003f79e  test    dil, 4
0x18003f7a2  jnz     loc_18003FB30
0x18003f7a8  mov     r15d, dword ptr [rbp+arg_18]
0x18003f7ac  xor     edi, edi
0x18003f7ae  movzx   eax, byte ptr [r13+48h]
0x18003f7b3  test    al, 20h
0x18003f7b5  jnz     loc_18003FA06
0x18003f7bb  test    byte ptr [r13+20h], 8
0x18003f7c0  jz      loc_18003F8A9
0x18003f7c6  movzx   eax, byte ptr [r13+2Ah]
0x18003f7cb  mov     r9d, edi
0x18003f7ce  mov     r10, rdi
0x18003f7d1  lea     r8, [r12+rax*2]
0x18003f7d5  movzx   edx, word ptr [r8]
0x18003f7d9  test    dx, dx
0x18003f7dc  jz      short loc_18003F84A
0x18003f7de  cmp     edx, 2Dh ; '-'
0x18003f7e1  jz      short loc_18003F84A
0x18003f7e3  movzx   ecx, bl
0x18003f7e6  lea     eax, [rdx-30h]
0x18003f7e9  shl     r10, cl
0x18003f7ec  mov     rcx, r10
0x18003f7ef  cmp     ax, 9
0x18003f7f3  jbe     loc_18003FE6B
0x18003f7f9  lea     eax, [rdx-61h]
0x18003f7fc  cmp     ax, 19h
0x18003f800  ja      loc_18003FAAF
0x18003f806  cmp     bx, 3
0x18003f80a  jz      loc_18003FAE2
0x18003f810  cmp     bx, 4
0x18003f814  jz      loc_18003FAEC
0x18003f81a  mov     rax, 0FFFFFFFFFFFFFFAAh
0x18003f821  mov     r10, 0FFFFFFFFFFFFFFA0h
0x18003f828  cmp     bx, 6
0x18003f82c  cmovnz  rax, r10
0x18003f830  lea     r10, [rcx+rax]
0x18003f834  add     r10, rdx
0x18003f837  inc     r9d
0x18003f83a  cmp     r9d, 8
0x18003f83e  ja      loc_18003FAEC
0x18003f844  add     r8, 2
0x18003f848  jmp     short loc_18003F7D5
0x18003f84a  lea     rax, [rbp+var_10]
0x18003f84e  mov     [rbp+arg_18], rdi
0x18003f852  lea     r9, [rbp+arg_18]
0x18003f856  mov     qword ptr [rsp+60h+bIgnoreCase], rax
0x18003f85b  xor     edx, edx
0x18003f85d  mov     [rbp+var_10], rdi
0x18003f861  mov     r8d, 6
0x18003f867  mov     rcx, r10
0x18003f86a  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x18003f86f  test    al, al
0x18003f871  jz      loc_18003FAEC
0x18003f877  mov     rax, [rbp+var_10]
0x18003f87b  movzx   ebx, word ptr [rbp+arg_18]
0x18003f87f  mov     dword ptr [rbp+arg_10], ebx
0x18003f882  test    byte ptr [rax], 1
0x18003f885  jnz     loc_180040159
0x18003f88b  movzx   edx, byte ptr [r13+48h]
0x18003f890  test    dl, 8
0x18003f893  jz      short loc_18003F8A9
0x18003f895  movzx   eax, bx
0x18003f898  neg     ax
0x18003f89b  sbb     cl, cl
0x18003f89d  and     dl, 0F7h
0x18003f8a0  and     cl, 8
0x18003f8a3  or      cl, dl
0x18003f8a5  mov     [r13+48h], cl
0x18003f8a9  test    byte ptr [r13+20h], 10h
0x18003f8ae  jnz     loc_18003FC7A
0x18003f8b4  movzx   ecx, byte ptr [r13+48h]
0x18003f8b9  test    cl, 8
0x18003f8bc  jz      loc_18003F9FA
0x18003f8c2  mov     eax, dword ptr [rbp+arg_10]
0x18003f8c5  xor     sil, sil
0x18003f8c8  mov     [rbp+arg_18], rdi
0x18003f8cc  movzx   ebx, r15w
0x18003f8d0  test    ax, ax
0x18003f8d3  jz      loc_18003F96C
0x18003f8d9  movzx   edi, word ptr [rbp+var_30]
0x18003f8dd  lea     r9, [rbp+arg_18]
0x18003f8e1  movzx   r14d, byte ptr [r13+8]
0x18003f8e6  xor     r8d, r8d
0x18003f8e9  movzx   eax, ax
0x18003f8ec  xor     edx, edx
0x18003f8ee  shl     rdi, 8
0x18003f8f2  movzx   ecx, r15w
0x18003f8f6  add     rcx, rdi
0x18003f8f9  mov     qword ptr [rsp+60h+bIgnoreCase], 0
0x18003f902  shl     rcx, 9
0x18003f906  add     rcx, rax
0x18003f909  movzx   eax, word ptr [rbp+var_2C]
0x18003f90d  shl     rcx, 7
0x18003f911  add     rcx, rax
0x18003f914  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x18003f919  test    al, al
0x18003f91b  jz      loc_18003FB0D
0x18003f921  test    r15w, r15w
0x18003f925  jnz     short loc_18003F937
0x18003f927  mov     rbx, [rbp+arg_18]
0x18003f92b  mov     eax, 0FFh
0x18003f930  shr     rbx, 10h
0x18003f934  and     bx, ax
0x18003f937  movzx   ecx, bx
0x18003f93a  xor     r9d, r9d
0x18003f93d  add     rcx, rdi
0x18003f940  xor     edx, edx
0x18003f942  xor     edi, edi
0x18003f944  shl     rcx, 10h
0x18003f948  mov     r8d, 0Dh
0x18003f94e  mov     qword ptr [rsp+60h+bIgnoreCase], rdi
0x18003f953  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x18003f958  test    al, al
0x18003f95a  jnz     loc_18003FB0F
0x18003f960  test    r14b, r14b
0x18003f963  mov     r14d, [rbp+var_30]
0x18003f967  jz      short loc_18003F96C
0x18003f969  mov     dword ptr [rbp+arg_10], edi
0x18003f96c  lea     eax, [r14-1]
0x18003f970  mov     ecx, 21C4h
0x18003f975  cmp     ax, cx
0x18003f978  ja      short loc_18003F9B0
0x18003f97a  movzx   ecx, r14w
0x18003f97e  lea     r9, [rbp+arg_18]
0x18003f982  xor     edx, edx
0x18003f984  mov     [rbp+arg_18], rdi
0x18003f988  mov     r8d, 1
0x18003f98e  mov     qword ptr [rsp+60h+bIgnoreCase], rdi
0x18003f993  call    ?TryFindTableEntry@@YA_N_K0W4SEARCH_TABLE_TYPE@@PEA_KPEAPEBX@Z; TryFindTableEntry(unsigned __int64,unsigned __int64,SEARCH_TABLE_TYPE,unsigned __int64 *,void const * *)
0x18003f998  test    al, al
0x18003f99a  jz      short loc_18003F9B7
0x18003f99c  mov     rax, [rbp+arg_18]
0x18003f9a0  test    bx, bx
0x18003f9a3  jnz     short loc_18003F9A8
0x18003f9a5  movzx   ebx, ax
0x18003f9a8  cmp     bx, ax
0x18003f9ab  jnz     short loc_18003F9B0
0x18003f9ad  mov     sil, 1
0x18003f9b0  test    bx, bx
0x18003f9b3  jnz     short loc_18003F9C0
0x18003f9b5  jmp     short loc_18003F9C8
0x18003f9b7  test    bx, bx
0x18003f9ba  jz      loc_18003FE87
0x18003f9c0  movzx   r15d, bx
0x18003f9c4  mov     [rbp+arg_0], sil
0x18003f9c8  mov     esi, [rbp+var_2C]
0x18003f9cb  movzx   eax, r15w
0x18003f9cf  neg     ax
0x18003f9d2  movzx   eax, byte ptr [r13+48h]
  ... truncated ...
```

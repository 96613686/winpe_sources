# ARI::Internal::PackageFamilyNameFromProductId(_GUID const *,uint *,ushort *)

- ea: `0x1800415a0`
- end: `0x180041e88`
- name: `?PackageFamilyNameFromProductId@Internal@ARI@@YAJPEBU_GUID@@PEAIPEAG@Z`
- size: `2280`
- prototype: `int(ARI::Internal *__hidden this, const struct _GUID *, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180041420`

## callees

- `0x1800415a0`
- `0x180041e90`
- `0x180042080`
- `0x180071f50`
- `0x1800992a0`
- `0x1800992c4`
- `0x18009d729`
- `0x1801051e4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041bbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041c13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041cc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041bbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041c13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041cc5`

## string_xrefs

- `0x18004193e`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18004199d`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800419b0`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180041923`: `onecore\base\appmodel\common\guid.cpp`

## pseudocode

```c
__int64 __fastcall ARI::Internal::PackageFamilyNameFromProductId(
        const struct _GUID *this,
        const struct _GUID *a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdi
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int128 v15; // xmm1
  _OWORD *v16; // rcx
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  _OWORD *v19; // rax
  int v20; // ebx
  __int128 v21; // xmm1
  __int128 v22; // xmm1
  __int64 v23; // r9
  const wchar_t *v24; // r10
  __int128 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int128 *v28; // rcx
  __int128 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  _WORD *v32; // rax
  __int128 *p_Src; // rcx
  __int64 v34; // rdx
  _WORD *v35; // rcx
  __int128 *v36; // rax
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r9
  unsigned int v43; // edi
  int v44; // eax
  unsigned int v45; // edx
  __int64 v46; // rcx
  __int64 v47; // rbx
  _OWORD *v48; // rcx
  const WCHAR *v49; // rsi
  unsigned int v50; // r14d
  LPCWCH v51; // rdx
  WCHAR *v52; // r8
  unsigned int i; // eax
  WCHAR v54; // cx
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // rdi
  __int64 v57; // r9
  unsigned __int64 j; // rbx
  unsigned __int64 v59; // rdx
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rdi
  __int64 v62; // rdx
  unsigned int v63; // edi
  int v64; // eax
  unsigned __int16 *v65; // r9
  __int64 v66; // rax
  __int64 v67; // r14
  unsigned __int16 *v68; // r11
  unsigned int v69; // r10d
  int v70; // r8d
  const char *k; // rax
  _WORD *v72; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned int v74; // [rsp+30h] [rbp-D0h] BYREF
  void **v75; // [rsp+38h] [rbp-C8h] BYREF
  void **v76; // [rsp+40h] [rbp-C0h]
  void **v77; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v78[40]; // [rsp+50h] [rbp-B0h] BYREF
  void *v79[2]; // [rsp+78h] [rbp-88h] BYREF
  int v80; // [rsp+88h] [rbp-78h]
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v82; // [rsp+B0h] [rbp-50h]
  __int128 v83; // [rsp+C0h] [rbp-40h]
  __int128 v84; // [rsp+D0h] [rbp-30h]
  __int64 v85; // [rsp+E0h] [rbp-20h]
  __int16 v86; // [rsp+E8h] [rbp-18h]
  __int128 v87; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v88; // [rsp+100h] [rbp+0h]
  __int128 v89; // [rsp+110h] [rbp+10h]
  __int128 v90; // [rsp+120h] [rbp+20h]
  __int128 v91; // [rsp+130h] [rbp+30h]
  __int128 v92; // [rsp+140h] [rbp+40h]
  __int128 v93; // [rsp+150h] [rbp+50h]
  __int128 v94; // [rsp+160h] [rbp+60h]
  int v95; // [rsp+170h] [rbp+70h]
  int v96; // [rsp+174h] [rbp+74h]
  __int64 v97; // [rsp+178h] [rbp+78h]
  LPCWCH lpString1; // [rsp+180h] [rbp+80h]
  _WORD *v99; // [rsp+188h] [rbp+88h]
  __int64 v100; // [rsp+190h] [rbp+90h]
  void *v101; // [rsp+198h] [rbp+98h]
  _BYTE v102[288]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( this && a2 && (!a2->Data1 || a3) )
  {
    v76 = v79;
    v75 = &Common::StringBufferBuilder::`vftable';
    v77 = v79;
    v80 = 0;
    *(_OWORD *)v79 = 0;
    v74 = 0;
    v6 = Common::Guid::Encode(this, v78, (unsigned int)a3, &v74);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\base\\appmodel\\common\\guid.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
    }
    else
    {
      v8 = v74;
      if ( v74 <= 0x24 )
      {
        v9 = 0;
        if ( v74 >= 4 )
        {
          if ( v74 < 0x20 )
            goto LABEL_130;
          do
          {
            *(__int128 *)((char *)&Src + 2 * v9) = (__int128)_mm_unpacklo_epi8(
                                                               _mm_loadl_epi64((const __m128i *)&v78[v9]),
                                                               (__m128i)0LL);
            *(__int128 *)((char *)&Src + 2 * (unsigned int)(v9 + 8)) = (__int128)_mm_unpacklo_epi8(
                                                                                   _mm_loadl_epi64((const __m128i *)&v78[(unsigned int)(v9 + 8)]),
                                                                                   (__m128i)0LL);
            *(__int128 *)((char *)&Src + 2 * (unsigned int)(v9 + 16)) = (__int128)_mm_unpacklo_epi8(
                                                                                    _mm_loadl_epi64((const __m128i *)&v78[(unsigned int)(v9 + 16)]),
                                                                                    (__m128i)0LL);
            v10 = (unsigned int)(v9 + 24);
            v9 = (unsigned int)(v9 + 32);
            *(__int128 *)((char *)&Src + 2 * v10) = (__int128)_mm_unpacklo_epi8(
                                                                _mm_loadl_epi64((const __m128i *)&v78[v10]),
                                                                (__m128i)0LL);
          }
          while ( (unsigned int)v9 < (v8 & 0xFFFFFFE0) );
          if ( (v8 & 0x1F) >= 4 )
          {
LABEL_130:
            do
            {
              *(_QWORD *)((char *)&Src + 2 * v9) = _mm_unpacklo_epi8(
                                                     _mm_cvtsi32_si128(*(_DWORD *)&v78[v9]),
                                                     (__m128i)0LL).m128i_u64[0];
              v9 = (unsigned int)(v9 + 4);
            }
            while ( (unsigned int)v9 < v8 - (v8 & 3) );
          }
        }
        for ( ; (unsigned int)v9 < v8; *((_WORD *)&Src + v11) = v78[v11] )
        {
          v11 = (unsigned int)v9;
          LODWORD(v9) = v9 + 1;
        }
        v12 = *(unsigned int *)v76;
        if ( (unsigned int)v12 > 0xFFFFFFDB )
        {
          v7 = -2147024362;
          v41 = 263;
          v42 = 2147942934LL;
        }
        else
        {
          if ( (unsigned int)(v12 + 36) > 0x3FFFFFFF )
          {
            v7 = -2147023613;
            goto LABEL_54;
          }
          v13 = ((__int64 (__fastcall *)(void ***))*v75)(&v75);
          v7 = v13;
          if ( v13 >= 0 )
          {
            if ( (_DWORD)v12 )
              memmove_0((char *)v76[1] + 72, v76[1], 2 * v12);
            v7 = 0;
            v15 = v82;
            v16 = v76[1];
            *v16 = Src;
            v17 = v83;
            v16[1] = v15;
            v18 = v84;
            v16[2] = v17;
            *(_QWORD *)&v17 = v85;
            v16[3] = v18;
            *((_QWORD *)v16 + 8) = v17;
LABEL_19:
            if ( (v7 & 0x80000000) == 0 )
            {
              v86 = 0;
              v19 = v76[1];
              v20 = *(_DWORD *)v76;
              v21 = v19[1];
              Src = *v19;
              v82 = v21;
              v22 = v19[3];
              v83 = v19[2];
              v85 = *((_QWORD *)v19 + 8);
              v84 = v22;
              if ( v79[1] )
                operator delete(v79[1], v14);
              v23 = 2147483646;
              v24 = L"CN=";
              v25 = &v87;
              v26 = 2147483646;
              v27 = 40;
              do
              {
                if ( !v26 )
                  break;
                if ( !*v24 )
                  break;
                *(_WORD *)v25 = *v24++;
                v25 = (__int128 *)((char *)v25 + 2);
                --v26;
                --v27;
              }
              while ( v27 );
              v28 = (__int128 *)((char *)v25 - 2);
              if ( v27 )
                v28 = v25;
              v29 = &v87;
              *(_WORD *)v28 = 0;
              v30 = 40;
              do
              {
                if ( !*(_WORD *)v29 )
                  break;
                v29 = (__int128 *)((char *)v29 + 2);
                --v30;
              }
              while ( v30 );
              v31 = 40 - v30;
              if ( v30 )
              {
                v32 = (_WORD *)&v87 + v31;
                p_Src = &Src;
                v34 = 40 - v31;
                if ( 40 != v31 )
                {
                  do
                  {
                    if ( !v23 )
                      break;
                    if ( !*(_WORD *)p_Src )
                      break;
                    *v32 = *(_WORD *)p_Src;
                    p_Src = (__int128 *)((char *)p_Src + 2);
                    ++v32;
                    --v23;
                    --v34;
                  }
                  while ( v34 );
                }
                v35 = v32 - 1;
                if ( v34 )
                  v35 = v32;
                *v35 = 0;
              }
              v36 = &v87;
              v37 = 0;
              while ( *(_WORD *)v36 )
              {
                if ( v37 >= 0x2000 )
                  return 87;
                ++v37;
                v36 = (__int128 *)((char *)v36 + 2);
              }
              if ( v37 < 3 )
                return 87;
              v74 = 0;
              v43 = 14;
              v44 = ReservedForLocalUse::HashThePublisher<unsigned short,unsigned short const *>(
                      v37,
                      (__int64)&v87,
                      14,
                      &v74,
                      (__int64)v79);
              v38 = v44;
              if ( v44 < 0 )
              {
                if ( (v44 & 0x1FFF0000) == 0x70000 )
                  v38 = (unsigned __int16)v44;
                if ( v38 )
                  return v38;
              }
              else
              {
                v45 = v74;
                *((_WORD *)v79 + v74) = 0;
                v43 = v45 + 1;
              }
              v46 = (unsigned int)(v20 + 1);
              if ( 2 * ((unsigned int)v46 + v43) + 128 > 0x142 )
                return 122;
              v47 = 2 * v46;
              v95 = 0;
              v96 = 11;
              v97 = 0;
              lpString1 = (LPCWCH)v102;
              memcpy_0(v102, &Src, 2 * v46);
              v48 = &v102[v47];
              v99 = v48;
              *v48 = v87;
              v48[1] = v88;
              v48[2] = v89;
              v48[3] = v90;
              v48[4] = v91;
              v100 = 0;
              v101 = &v102[v47 + 80];
              memcpy_0(v101, v79, 2LL * v43);
              if ( a2->Data1 )
              {
                if ( !a3 )
                  return 87;
              }
              v49 = lpString1;
              v50 = 0;
              v87 = 0;
              v88 = 0;
              v89 = 0;
              v90 = 0;
              v91 = 0;
              v92 = 0;
              v93 = 0;
              v94 = 0;
              if ( !lpString1 )
                return 87;
              v51 = lpString1;
              v52 = (WCHAR *)&v87;
              for ( i = 0; ; i = ++v50 )
              {
                v54 = *v51;
                if ( !*v51 )
                  break;
                if ( i >= 0x32 )
                  return 87;
                if ( v54 >= 0x61u )
                {
                  if ( v54 > 0x7Au )
                    return 87;
                }
                else if ( v54 >= 0x41u )
                {
                  if ( v54 > 0x5Au )
                    return 87;
                }
                else if ( (unsigned __int16)(v54 - 45) > 1u && (unsigned __int16)(v54 - 48) > 9u )
                {
                  return 87;
                }
                *v52 = v54;
                ++v51;
                ++v52;
              }
              if ( i < 3 )
                return 87;
              v55 = 0;
              v56 = (unsigned int)(v51 - v49);
              while ( v55 < 0x18 )
              {
                v57 = (unsigned int)dword_180109CD0[4 * v55];
                if ( v56 == v57 && CompareStringOrdinal(v49, v56, (&off_180109CD8)[2 * v55], v57, 1) == 2 )
                  return 87;
                ++v55;
              }
              for ( j = 0; j < 0x17; ++j )
              {
                v59 = (unsigned int)dword_180109B60[4 * j];
                if ( v56 >= v59 && CompareStringOrdinal(v49, v59, (&off_180109B68)[2 * j], v59, 1) == 2 )
                  return 87;
              }
              if ( v56 && v49[v56 - 1] == 46 )
                return 87;
              if ( v56 >= 5 )
              {
                v60 = 0;
                v61 = v56 - 5;
                while ( v60 <= v61 )
                {
                  if ( CompareStringOrdinal(&v49[v60], 5, L".xn--", 5, 1) == 2 )
                    return 87;
                  ++v60;
                }
              }
              v65 = (unsigned __int16 *)v101;
              v66 = v50;
              v67 = v50 + 1;
              v74 = v67;
              *((_WORD *)&v87 + v66) = 95;
              if ( v65 )
              {
                v68 = v65;
                v69 = 0;
LABEL_113:
                v70 = *v68;
                if ( (_WORD)v70 )
                {
                  if ( v69 < 0xD )
                  {
                    for ( k = "1234567890abcdefghjkmnpqrstvwxyzABCDEFGHJKMNPQRSTVWXYZ"; *k; ++k )
                    {
                      if ( v70 == *k )
                      {
                        ++v69;
                        ++v68;
                        goto LABEL_113;
                      }
                    }
                  }
                  return 87;
                }
                if ( v69 != 13 )
                  return 87;
                v62 = (__int64)v99;
              }
              else
              {
                v62 = (__int64)v99;
                v72 = v99;
                if ( !v99 )
                  return 87;
                v69 = 0;
                while ( *v72 )
                {
                  if ( v69 >= 0x2000 )
                    return 87;
                  ++v69;
                  ++v72;
                }
                if ( v69 < 3 )
                  return 87;
              }
              v63 = v67 + 13;
              if ( a2->Data1 < (unsigned int)(v67 + 14) )
              {
                a2->Data1 = v67 + 14;
                return 122;
              }
              else
              {
                if ( v65 )
                {
                  memcpy_0((char *)&v87 + 2 * v67, v65, 2LL * v69);
                }
                else
                {
                  v64 = ReservedForLocalUse::HashThePublisher<unsigned short,unsigned short const *>(
                          v69,
                          v62,
                          64,
                          &v74,
                          (__int64)&v87);
                  v38 = v64;
                  if ( v64 < 0 )
                  {
                    if ( (v64 & 0x1FFF0000) == 0x70000 )
                      return (unsigned __int16)v64;
                    return v38;
                  }
                  v63 = v74;
                }
                memcpy_0(a3, &v87, 2LL * v63);
                *((_WORD *)a3 + v63) = 0;
                v38 = 0;
                a2->Data1 = v63 + 1;
              }
              return v38;
            }
LABEL_50:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x37,
              (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\productidinternal.cpp",
              (const char *)v7,
              bIgnoreCase);
            if ( v79[1] )
            {
              operator delete(v79[1], v40);
              return 87;
            }
            return 87;
          }
          v42 = (unsigned int)v13;
          v41 = 269;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)v42,
          bIgnoreCase);
LABEL_54:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)v7,
          bIgnoreCase);
        goto LABEL_19;
      }
      v7 = -2147024774;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v7,
      bIgnoreCase);
    goto LABEL_50;
  }
  return 87;
}

```

## disassembly

```asm
0x1800415a0  push    rbp
0x1800415a2  push    r12
0x1800415a4  push    r15
0x1800415a6  lea     rbp, [rsp-1F0h]
0x1800415ae  sub     rsp, 2F0h
0x1800415b5  mov     rax, cs:__security_cookie
0x1800415bc  xor     rax, rsp
0x1800415bf  mov     [rbp+200h+var_40], rax
0x1800415c6  mov     r12, r8
0x1800415c9  mov     r15, rdx
0x1800415cc  test    rcx, rcx
0x1800415cf  jz      loc_180041C57
0x1800415d5  test    rdx, rdx
0x1800415d8  jz      loc_180041C57
0x1800415de  cmp     dword ptr [rdx], 0
0x1800415e1  ja      loc_180041C4E
0x1800415e7  lea     rax, [rsp+300h+var_288]
0x1800415ec  mov     [rsp+300h+arg_0], rbx
0x1800415f4  mov     [rsp+300h+var_2C0], rax
0x1800415f9  lea     r9, [rsp+300h+var_2D0]; unsigned int *
0x1800415fe  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180041605  mov     [rsp+300h+var_20], rdi
0x18004160d  mov     [rsp+300h+var_2C8], rax
0x180041612  lea     rdx, [rsp+300h+var_2B0]; unsigned __int8 *
0x180041617  lea     rax, [rsp+300h+var_288]
0x18004161c  mov     [rsp+300h+var_28], r13
0x180041624  xor     r13d, r13d
0x180041627  mov     [rsp+300h+var_2B8], rax
0x18004162c  xorps   xmm0, xmm0
0x18004162f  mov     [rbp+200h+var_278], r13d
0x180041633  movups  xmmword ptr [rsp+300h+var_288], xmm0
0x180041638  mov     [rsp+300h+var_2D0], r13d
0x18004163d  call    ?Encode@Guid@Common@@SAJPEBU_GUID@@PEAEKPEAK@Z; Common::Guid::Encode(_GUID const *,uchar *,ulong,ulong *)
0x180041642  mov     ebx, eax
0x180041644  test    eax, eax
0x180041646  js      loc_18004191C
0x18004164c  mov     r8d, [rsp+300h+var_2D0]
0x180041651  cmp     r8d, 24h ; '$'
0x180041655  ja      loc_180041C70
0x18004165b  mov     edx, r13d
0x18004165e  cmp     r8d, 4
0x180041662  jb      loc_1800416F1
0x180041668  cmp     r8d, 20h ; ' '
0x18004166c  jb      short loc_1800416CF
0x18004166e  mov     r9d, r8d
0x180041671  and     r9d, 0FFFFFFE0h
0x180041675  movq    xmm1, qword ptr [rsp+rdx+300h+var_2B0]
0x18004167b  lea     eax, [rdx+8]
0x18004167e  punpcklbw xmm1, xmm0
0x180041682  movdqu  [rbp+rdx*2+200h+Src], xmm1
0x180041688  movq    xmm1, qword ptr [rsp+rax+300h+var_2B0]
0x18004168e  punpcklbw xmm1, xmm0
0x180041692  movdqu  [rbp+rax*2+200h+Src], xmm1
0x180041698  lea     eax, [rdx+10h]
0x18004169b  movq    xmm1, qword ptr [rsp+rax+300h+var_2B0]
0x1800416a1  punpcklbw xmm1, xmm0
0x1800416a5  movdqu  [rbp+rax*2+200h+Src], xmm1
0x1800416ab  lea     eax, [rdx+18h]
0x1800416ae  add     edx, 20h ; ' '
0x1800416b1  movq    xmm1, qword ptr [rsp+rax+300h+var_2B0]
0x1800416b7  punpcklbw xmm1, xmm0
0x1800416bb  movdqu  [rbp+rax*2+200h+Src], xmm1
0x1800416c1  cmp     edx, r9d
0x1800416c4  jb      short loc_180041675
0x1800416c6  mov     eax, r8d
0x1800416c9  and     al, 1Fh
0x1800416cb  cmp     al, 4
0x1800416cd  jb      short loc_1800416F1
0x1800416cf  mov     eax, r8d
0x1800416d2  mov     ecx, r8d
0x1800416d5  and     eax, 3
0x1800416d8  sub     ecx, eax
0x1800416da  movd    xmm1, dword ptr [rsp+rdx+300h+var_2B0]
0x1800416e0  punpcklbw xmm1, xmm0
0x1800416e4  movq    qword ptr [rbp+rdx*2+200h+Src], xmm1
0x1800416ea  add     edx, 4
0x1800416ed  cmp     edx, ecx
0x1800416ef  jb      short loc_1800416DA
0x1800416f1  cmp     edx, r8d
0x1800416f4  jnb     short loc_180041709
0x1800416f6  mov     ecx, edx
0x1800416f8  inc     edx
0x1800416fa  movzx   eax, [rsp+rcx+300h+var_2B0]
0x1800416ff  mov     word ptr [rbp+rcx*2+200h+Src], ax
0x180041704  cmp     edx, r8d
0x180041707  jb      short loc_1800416F6
0x180041709  mov     rax, [rsp+300h+var_2C0]
0x18004170e  mov     edi, [rax]
0x180041710  cmp     edi, 0FFFFFFDBh
0x180041713  ja      loc_180041989
0x180041719  lea     edx, [rdi+24h]
0x18004171c  cmp     edx, 3FFFFFFFh
0x180041722  ja      loc_1800419C9
0x180041728  mov     rax, [rsp+300h+var_2C8]
0x18004172d  lea     rcx, [rsp+300h+var_2C8]
0x180041732  mov     rax, [rax]
0x180041735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004173a  mov     ebx, eax
0x18004173c  test    eax, eax
0x18004173e  js      loc_1800419D0
0x180041744  test    edi, edi
0x180041746  jnz     loc_180041DB5
0x18004174c  mov     rax, [rsp+300h+var_2C0]
0x180041751  mov     ebx, r13d
0x180041754  movups  xmm0, [rbp+200h+Src]
0x180041758  movups  xmm1, [rbp+200h+var_250]
0x18004175c  mov     rcx, [rax+8]
0x180041760  movups  xmmword ptr [rcx], xmm0
0x180041763  movups  xmm0, [rbp+200h+var_240]
0x180041767  movups  xmmword ptr [rcx+10h], xmm1
0x18004176b  movups  xmm1, [rbp+200h+var_230]
0x18004176f  movups  xmmword ptr [rcx+20h], xmm0
0x180041773  movsd   xmm0, [rbp+200h+var_220]
0x180041778  movups  xmmword ptr [rcx+30h], xmm1
0x18004177c  movsd   qword ptr [rcx+40h], xmm0
0x180041781  test    ebx, ebx
0x180041783  js      loc_180041952
0x180041789  mov     rcx, [rsp+300h+var_2C0]
0x18004178e  mov     [rbp+200h+var_218], r13w
0x180041793  mov     rax, [rcx+8]
0x180041797  mov     ebx, [rcx]
0x180041799  mov     rcx, [rbp+200h+var_288+8]; void *
0x18004179d  movups  xmm0, xmmword ptr [rax]
0x1800417a0  movups  xmm1, xmmword ptr [rax+10h]
0x1800417a4  movups  [rbp+200h+Src], xmm0
0x1800417a8  movups  [rbp+200h+var_250], xmm1
0x1800417ac  movups  xmm0, xmmword ptr [rax+20h]
0x1800417b0  movups  xmm1, xmmword ptr [rax+30h]
0x1800417b4  movups  [rbp+200h+var_240], xmm0
0x1800417b8  movsd   xmm0, qword ptr [rax+40h]
0x1800417bd  movsd   [rbp+200h+var_220], xmm0
0x1800417c2  movups  [rbp+200h+var_230], xmm1
0x1800417c6  test    rcx, rcx
0x1800417c9  jz      short loc_1800417D0
0x1800417cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800417d0  mov     r9d, 7FFFFFFEh
0x1800417d6  lea     r10, aCn; "CN="
0x1800417dd  mov     edx, 28h ; '('
0x1800417e2  lea     rax, [rbp+200h+var_210]
0x1800417e6  mov     ecx, r9d
0x1800417e9  mov     r8d, edx
0x1800417ec  nop     dword ptr [rax+00h]
0x1800417f0  test    rcx, rcx
0x1800417f3  jz      short loc_180041814
0x1800417f5  movzx   r11d, word ptr [r10]
0x1800417f9  test    r11w, r11w
0x1800417fd  jz      short loc_180041814
0x1800417ff  mov     [rax], r11w
0x180041803  add     r10, 2
0x180041807  add     rax, 2
0x18004180b  dec     rcx
0x18004180e  sub     r8, 1
0x180041812  jnz     short loc_1800417F0
0x180041814  lea     rcx, [rax-2]
0x180041818  test    r8, r8
0x18004181b  cmovnz  rcx, rax
0x18004181f  lea     rax, [rbp+200h+var_210]
0x180041823  mov     [rcx], r13w
0x180041827  mov     rcx, rdx
0x18004182a  nop     word ptr [rax+rax+00h]
0x180041830  cmp     [rax], r13w
0x180041834  jz      short loc_180041840
0x180041836  add     rax, 2
0x18004183a  sub     rcx, 1
0x18004183e  jnz     short loc_180041830
0x180041840  mov     r8, rdx
0x180041843  sub     r8, rcx
0x180041846  test    rcx, rcx
0x180041849  cmovz   r8, r13
0x18004184d  jz      short loc_180041893
0x18004184f  lea     rax, [rbp+200h+var_210]
0x180041853  lea     rax, [rax+r8*2]
0x180041857  lea     rcx, [rbp+200h+Src]
0x18004185b  sub     rdx, r8
0x18004185e  jz      short loc_180041884
0x180041860  test    r9, r9
0x180041863  jz      short loc_180041884
0x180041865  movzx   r8d, word ptr [rcx]
0x180041869  test    r8w, r8w
0x18004186d  jz      short loc_180041884
0x18004186f  mov     [rax], r8w
0x180041873  add     rcx, 2
0x180041877  add     rax, 2
0x18004187b  dec     r9
0x18004187e  sub     rdx, 1
0x180041882  jnz     short loc_180041860
0x180041884  test    rdx, rdx
0x180041887  lea     rcx, [rax-2]
0x18004188b  cmovnz  rcx, rax
0x18004188f  mov     [rcx], r13w
0x180041893  lea     rax, [rbp+200h+var_210]
0x180041897  mov     ecx, r13d
0x18004189a  nop     word ptr [rax+rax+00h]
0x1800418a0  cmp     [rax], r13w
0x1800418a4  jz      short loc_1800418B6
0x1800418a6  cmp     ecx, 2000h
0x1800418ac  jnb     short loc_1800418BF
0x1800418ae  inc     ecx
0x1800418b0  add     rax, 2
0x1800418b4  jmp     short loc_1800418A0
0x1800418b6  cmp     ecx, 3
0x1800418b9  jnb     loc_1800419DA
0x1800418bf  mov     ecx, 57h ; 'W'
0x1800418c4  jmp     short loc_1800418E5
0x1800418c6  cmp     r10d, 0Dh
0x1800418ca  jz      loc_180041CDF
0x1800418d0  mov     ecx, 57h ; 'W'
0x1800418d5  mov     rsi, [rsp+300h+var_18]
0x1800418dd  mov     r14, [rsp+300h+var_30]
0x1800418e5  mov     rdi, [rsp+300h+var_20]
0x1800418ed  mov     eax, ecx
0x1800418ef  mov     rbx, [rsp+300h+arg_0]
0x1800418f7  mov     r13, [rsp+300h+var_28]
0x1800418ff  mov     rcx, [rbp+200h+var_40]
0x180041906  xor     rcx, rsp; StackCookie
0x180041909  call    __security_check_cookie
0x18004190e  add     rsp, 2F0h
0x180041915  pop     r15
0x180041917  pop     r12
0x180041919  pop     rbp
0x18004191a  retn
0x18004191c  mov     rcx, [rbp+208h]; this
0x180041923  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\guid.c"...
0x18004192a  mov     r9d, eax; char *
0x18004192d  mov     edx, 63h ; 'c'; void *
0x180041932  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041937  mov     rcx, [rbp+208h]; this
0x18004193e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x180041945  mov     r9d, ebx; char *
0x180041948  mov     edx, 0EFh; void *
0x18004194d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041952  mov     rcx, [rbp+208h]; this
0x180041959  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\runtime\\src\\"...
0x180041960  mov     r9d, ebx; char *
0x180041963  mov     edx, 37h ; '7'; void *
0x180041968  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004196d  mov     rcx, [rbp+200h+var_288+8]; void *
0x180041971  test    rcx, rcx
0x180041974  jz      loc_1800418BF
0x18004197a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004197f  mov     ecx, 57h ; 'W'
0x180041984  jmp     loc_1800418E5
0x180041989  mov     ebx, 80070216h
0x18004198e  mov     edx, 107h; void *
0x180041993  mov     r9d, ebx; char *
0x180041996  mov     rcx, [rbp+208h]; this
0x18004199d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800419a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800419a9  mov     rcx, [rbp+208h]; this
0x1800419b0  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\string"...
0x1800419b7  mov     r9d, ebx; char *
0x1800419ba  mov     edx, 79h ; 'y'; void *
0x1800419bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800419c4  jmp     loc_180041781
0x1800419c9  mov     ebx, 80070503h
0x1800419ce  jmp     short loc_1800419A9
0x1800419d0  mov     r9d, eax
0x1800419d3  mov     edx, 10Dh
0x1800419d8  jmp     short loc_180041996
0x1800419da  lea     rax, [rsp+300h+var_288]
0x1800419df  mov     [rsp+300h+var_2D0], r13d
0x1800419e4  mov     edi, 0Eh
0x1800419e9  mov     qword ptr [rsp+300h+bIgnoreCase], rax
0x1800419ee  mov     r8d, edi
0x1800419f1  lea     r9, [rsp+300h+var_2D0]
0x1800419f6  lea     rdx, [rbp+200h+var_210]
0x1800419fa  call    ??$HashThePublisher@GPEBG@ReservedForLocalUse@@YAJIPEBGIAEAIPEAG@Z; ReservedForLocalUse::HashThePublisher<ushort,ushort const *>(uint,ushort const *,uint,uint &,ushort *)
0x1800419ff  mov     ecx, eax
0x180041a01  test    eax, eax
0x180041a03  js      loc_180041D48
0x180041a09  mov     edx, [rsp+300h+var_2D0]
0x180041a0d  mov     word ptr [rsp+rdx*2+300h+var_288], r13w
0x180041a13  lea     edi, [rdx+1]
0x180041a16  jmp     short loc_180041A20
0x180041a18  test    ecx, ecx
0x180041a1a  jnz     loc_1800418E5
0x180041a20  lea     ecx, [rbx+1]
0x180041a23  lea     eax, [rcx+rdi]
0x180041a26  lea     eax, ds:80h[rax*2]
0x180041a2d  cmp     eax, 142h
0x180041a32  ja      loc_180041D60
0x180041a38  lea     rbx, [rcx+rcx]
0x180041a3c  mov     [rbp+200h+var_190], r13d
0x180041a40  lea     rax, [rbp+200h+var_160]
0x180041a47  mov     [rbp+200h+var_18C], 0Bh
0x180041a4e  mov     r8, rbx; Size
0x180041a51  mov     [rbp+200h+var_188], r13
0x180041a55  lea     rdx, [rbp+200h+Src]; Src
0x180041a59  mov     [rbp+200h+lpString1], rax
0x180041a60  lea     rcx, [rbp+200h+var_160]; void *
0x180041a67  call    memcpy_0
0x180041a6c  movups  xmm0, [rbp+200h+var_210]
0x180041a70  lea     rcx, [rbp+200h+var_160]
0x180041a77  add     rcx, rbx
0x180041a7a  mov     r8d, edi
0x180041a7d  mov     [rbp+200h+var_178], rcx
0x180041a84  lea     rdx, [rsp+300h+var_288]; Src
0x180041a89  add     r8, r8; Size
0x180041a8c  movups  xmmword ptr [rcx], xmm0
0x180041a8f  movups  xmm1, [rbp+200h+var_200]
  ... truncated ...
```

# FontNameList::AppendItems(OpenTypeNameTable const &,ushort)

- ea: `0x180024db0`
- end: `0x180025a80`
- name: `?AppendItems@FontNameList@@QEAAXAEBVOpenTypeNameTable@@G@Z`
- size: `3280`
- prototype: `void __fastcall(FontNameList *__hidden this, const struct OpenTypeNameTable *, unsigned __int16)`
- caller_count: `6`
- callee_count: `30`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001f934`
- `0x180020b88`
- `0x180026834`
- `0x1800268c0`
- `0x180027e0c`
- `0x18004f71c`

## callees

- `0x180004810`
- `0x18000a97c`
- `0x18000ab04`
- `0x180021474`
- `0x180021fa0`
- `0x180024c50`
- `0x180024c5c`
- `0x180024db0`
- `0x180025a90`
- `0x1800261d8`
- `0x180026364`
- `0x180026450`
- `0x180026504`
- `0x18002671c`
- `0x180029d78`
- `0x180029f04`
- `0x18004d664`
- `0x18009c0e0`
- `0x18009d96c`
- `0x18009df80`
- `0x18009e420`
- `0x18009f1ec`
- `0x1800aa650`
- `0x1800aaa58`
- `0x1800aaf88`
- `0x1800ab0aa`
- `0x1800ab168`
- `0x1800ab180`
- `0x1800b2f20`
- `0x1800b2f6c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025a63`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025a63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025593`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025593`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
void __fastcall FontNameList::AppendItems(FontNameList *this, const struct OpenTypeNameTable *a2, __int16 a3)
{
  __int16 v3; // r14
  const struct OpenTypeNameTable *v4; // rbx
  unsigned __int64 v5; // rdx
  const wchar_t *v6; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdi
  __int64 v9; // rax
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rcx
  const wchar_t *v13; // rdx
  bool v14; // al
  unsigned __int64 v15; // rbx
  char *v16; // rsi
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int64 i; // rax
  unsigned __int64 k; // rdx
  unsigned __int64 v21; // r13
  __int64 v22; // r9
  const char *v23; // rdx
  wchar_t **v24; // r15
  size_t v25; // r8
  const wchar_t *v26; // rcx
  unsigned __int64 j; // rcx
  wchar_t *v28; // r13
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rsi
  void **v31; // rax
  __int64 v32; // r8
  void **v33; // rax
  unsigned __int64 v34; // rbx
  void **v35; // rsi
  int v36; // r14d
  unsigned __int64 v37; // rax
  _DWORD *v38; // rax
  __int64 v39; // rdx
  void **v40; // rdi
  size_t v41; // r8
  void *v42; // rcx
  void **v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // r9
  void *v46; // rcx
  wchar_t *v47; // r8
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // r14
  const char *v50; // rdi
  __int64 v51; // rcx
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rcx
  size_t size_of; // rax
  void *v55; // r15
  unsigned __int64 v56; // r9
  void *v57; // rdi
  char *v58; // rax
  size_t v59; // rdi
  __int64 v60; // [rsp+0h] [rbp-208h] BYREF
  unsigned __int64 v61; // [rsp+30h] [rbp-1D8h]
  __int64 v62; // [rsp+38h] [rbp-1D0h] BYREF
  void **v63; // [rsp+40h] [rbp-1C8h]
  void **v64; // [rsp+48h] [rbp-1C0h]
  void *v65[2]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v66; // [rsp+60h] [rbp-1A8h]
  unsigned __int64 v67; // [rsp+68h] [rbp-1A0h]
  unsigned __int64 v68; // [rsp+70h] [rbp-198h]
  __int128 v69; // [rsp+78h] [rbp-190h] BYREF
  unsigned __int64 v70; // [rsp+88h] [rbp-180h]
  _QWORD *v71; // [rsp+90h] [rbp-178h]
  void **v72; // [rsp+98h] [rbp-170h]
  __int64 v73; // [rsp+A0h] [rbp-168h]
  void **v74; // [rsp+A8h] [rbp-160h]
  void **v75; // [rsp+B0h] [rbp-158h]
  _QWORD v76[9]; // [rsp+C0h] [rbp-148h] BYREF
  void *Src[2]; // [rsp+108h] [rbp-100h] BYREF
  unsigned __int64 v78; // [rsp+118h] [rbp-F0h]
  unsigned __int64 v79; // [rsp+120h] [rbp-E8h]
  void *v80[2]; // [rsp+128h] [rbp-E0h] BYREF
  __int64 v81; // [rsp+138h] [rbp-D0h]
  unsigned __int64 v82; // [rsp+140h] [rbp-C8h]
  void *Block[2]; // [rsp+148h] [rbp-C0h]
  unsigned __int64 v84; // [rsp+158h] [rbp-B0h]
  wchar_t *v85[2]; // [rsp+160h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+170h] [rbp-98h]
  unsigned __int64 v87; // [rsp+178h] [rbp-90h]
  wchar_t *S2[2]; // [rsp+180h] [rbp-88h] BYREF
  __int64 v89; // [rsp+190h] [rbp-78h]
  unsigned __int64 v90; // [rsp+198h] [rbp-70h]
  wchar_t *S1[2]; // [rsp+1A0h] [rbp-68h] BYREF
  size_t N; // [rsp+1B0h] [rbp-58h]
  unsigned __int64 v93; // [rsp+1B8h] [rbp-50h]

  v3 = a3;
  v4 = a2;
  v71 = this;
  v68 = (unsigned __int64)this;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v62);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v65);
  v7 = *(unsigned int *)(v5 + 48);
  v67 = v7;
  v8 = 0;
  while ( 1 )
  {
    v61 = v8;
    if ( v8 >= v7 )
      break;
    if ( v8 >= *((unsigned int *)v4 + 12) )
      FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v6, v5);
    v5 = 12 * v8;
    v9 = *((_QWORD *)v4 + 5);
    v6 = (const wchar_t *)*(unsigned __int8 *)(v9 + 12 * v8 + 6);
    LOWORD(v6) = _byteswap_ushort(*(_WORD *)(v9 + 12 * v8 + 6));
    if ( (_WORD)v6 == v3 )
    {
      try
      {
        if ( v8 >= *((unsigned int *)v4 + 12) )
          FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v6, v5);
        v10 = *((_QWORD *)v4 + 8);
        v11 = v5 + *((_QWORD *)v4 + 5);
        LOWORD(v69) = _byteswap_ushort(*(_WORD *)v11);
        WORD1(v69) = _byteswap_ushort(*(_WORD *)(v11 + 2));
        WORD2(v69) = _byteswap_ushort(*(_WORD *)(v11 + 4));
        v12 = ((unsigned __int64)*(unsigned __int8 *)(v11 + 10) << 8) | *(unsigned __int8 *)(v11 + 11);
        if ( v10 < v12
          || (v5 = ((unsigned __int64)*(unsigned __int8 *)(v11 + 8) << 8) | *(unsigned __int8 *)(v11 + 9), v10 - v12 < v5) )
        {
          FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v12, v5);
        }
        *((_QWORD *)&v69 + 1) = *((_QWORD *)v4 + 7) + v12;
        v70 = v5;
        LOBYTE(v11) = 1;
        OpenTypeName::TryGetLanguage(&v69, S2, v11);
        if ( v89 )
        {
          v72 = v80;
          std::wstring::wstring(v80, S2);
          *(_OWORD *)Block = v69;
          v84 = v70;
          if ( v63 == v64 )
          {
            std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName>>(
              &v62,
              (__int64)v63,
              (__int64)v80);
          }
          else
          {
            v73 = (__int64)v63;
            v74 = v63;
            std::wstring::wstring(v63, v80);
            *(_OWORD *)(v51 + 32) = *(_OWORD *)Block;
            *(_QWORD *)(v51 + 48) = v84;
            v63 += 7;
          }
          v75 = v80;
          if ( v82 > 7 )
            std::_Deallocate<16>(v80[0], 2 * v82 + 2);
          v81 = 0;
          v82 = 7;
          LOWORD(v80[0]) = 0;
          OpenTypeName::TryGetLanguage(&v69, S1, 0);
          v13 = (const wchar_t *)S2;
          if ( v90 > 7 )
            v13 = S2[0];
          v6 = (const wchar_t *)S1;
          if ( v93 > 7 )
            v6 = S1[0];
          if ( N == v89 )
          {
            if ( N )
              v14 = wmemcmp(v6, v13, N) == 0;
            else
              v14 = 1;
          }
          else
          {
            v14 = 0;
          }
          if ( !v14 )
            OpenTypeNameList<GenericLanguageTag<std::wstring>>::Add(&v62, S1, &v69);
          if ( v93 > 7 )
            std::_Deallocate<16>(S1[0], 2 * v93 + 2);
          N = 0;
          v93 = 7;
          LOWORD(S1[0]) = 0;
        }
        v5 = v90;
        if ( v90 > 7 )
          std::_Deallocate<16>(S2[0], 2 * v90 + 2);
        v89 = 0;
        v90 = 7;
        LOWORD(S2[0]) = 0;
      }
      catch ( FileFormatException )
      {
        v5 = (unsigned __int64)&v60;
        v3 = a3;
        v4 = a2;
        v7 = v67;
        v8 = v61;
        v6 = (const wchar_t *)v68;
        v71 = (_QWORD *)v68;
        goto LABEL_5;
      }
      ++v8;
    }
    else
    {
LABEL_5:
      ++v8;
    }
  }
  v15 = 0x6DB6DB6DB6DB6DB7LL * (((__int64)v63 - v62) >> 3);
  v16 = (char *)v65[1];
  v17 = v65[0];
  v18 = ((char *)v65[1] - (char *)v65[0]) >> 3;
  if ( v15 < v18 )
  {
    v58 = (char *)v65[0] + 0x6DB6DB6DB6DB6DB8LL * (((__int64)v63 - v62) >> 3);
  }
  else
  {
    if ( v15 <= v18 )
      goto LABEL_34;
    if ( v15 > (signed __int64)(v66 - (unsigned __int64)v65[0]) >> 3 )
    {
      std::vector<GlyphGraphicDataBuilder::BuilderLinkedEntry *>::_Resize_reallocate<std::_Value_init_tag>(
        (__int64)v65,
        0x6DB6DB6DB6DB6DB7LL * (((__int64)v63 - v62) >> 3));
      v17 = v65[0];
      goto LABEL_34;
    }
    v59 = 8 * (v15 - v18);
    memset_0(v65[1], 0, v59);
    v58 = &v16[v59];
    v17 = v65[0];
  }
  v65[1] = v58;
LABEL_34:
  for ( i = 0; i < v15; v17 = v65[0] )
  {
    v17[i] = i;
    ++i;
  }
  std::_Sort_unchecked<unsigned __int64 *,_lambda_c80a0a30d397bbb4dbaf80130ad47a37_>(
    v17,
    v65[1],
    ((char *)v65[1] - (char *)v17) >> 3,
    &v62);
  v68 = 0x6DB6DB6DB6DB6DB7LL * (((__int64)v63 - v62) >> 3);
  *(_OWORD *)Src = 0;
  v78 = 0;
  v79 = 0;
  std::wstring::_Construct_empty(Src);
  *(_OWORD *)v85 = 0;
  v86 = 0;
  v87 = 0;
  std::wstring::_Construct_empty(v85);
  v21 = 0;
  v61 = 0;
  if ( k )
  {
    do
    {
      v22 = 0x7FFFFFFFFFFFFFFELL;
      if ( v21 >= ((char *)v65[1] - (char *)v65[0]) >> 3 )
      {
        FailAssert(0x33u, (const char *)k);
        JUMPOUT(0x180025A7FLL);
      }
      v23 = (const char *)*((_QWORD *)v65[0] + v21);
      if ( (unsigned __int64)v23 >= 0x6DB6DB6DB6DB6DB7LL * (((__int64)v63 - v62) >> 3) )
      {
        FailAssert(0x36u, v23);
        __debugbreak();
      }
      v24 = (wchar_t **)(v62 + 56LL * (_QWORD)v23);
      v67 = (unsigned __int64)v24;
      k = (unsigned __int64)v85;
      if ( v87 > 7 )
        k = (unsigned __int64)v85[0];
      v25 = (size_t)v24[2];
      if ( (unsigned __int64)v24[3] <= 7 )
        v26 = (const wchar_t *)v24;
      else
        v26 = *v24;
      if ( v25 == v86 )
      {
        if ( !v25 || !wmemcmp(v26, (const wchar_t *)k, v25) )
          goto LABEL_88;
        v22 = 0x7FFFFFFFFFFFFFFELL;
      }
      k = *((unsigned __int16 *)v24 + 17);
      j = *((unsigned __int16 *)v24 + 16);
      if ( (_DWORD)j == 3 )
      {
        j = *((unsigned __int16 *)v24 + 17);
        if ( (_DWORD)k == 1 || (_DWORD)k == 10 || !*((_WORD *)v24 + 17) || (j = (unsigned int)(k - 2), (_DWORD)k == 2) )
        {
LABEL_49:
          v28 = v24[5];
          v29 = (unsigned __int64)v24[6] >> 1;
          v30 = v78;
          if ( v29 > v78 )
          {
            v48 = v29 - v78;
            v49 = v79;
            if ( v29 - v78 > v79 - v78 )
            {
              if ( 0x7FFFFFFFFFFFFFFELL - v78 < v48 )
                std::_Xlength_error("string too long");
              v52 = v29 | 7;
              if ( (v29 | 7) > 0x7FFFFFFFFFFFFFFELL )
              {
                v52 = 0x7FFFFFFFFFFFFFFELL;
              }
              else
              {
                v53 = v79 >> 1;
                if ( v79 > 0x7FFFFFFFFFFFFFFELL - (v79 >> 1) )
                {
                  v52 = 0x7FFFFFFFFFFFFFFELL;
                }
                else if ( v52 < v79 + v53 )
                {
                  v52 = v79 + v53;
                }
              }
              size_of = std::_Get_size_of_n<2>(v52 + 1, k, v25, 0x7FFFFFFFFFFFFFFELL);
              v55 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
              v78 = v29;
              v79 = v52;
              v56 = v29 - v30;
              if ( v49 > 7 )
              {
                v57 = Src[0];
                _lambda_a3050a43f3157934f354774ab3dd2e02_::operator()(v55, Src[0], v30, v56);
                std::_Deallocate<16>(v57, 2 * v49 + 2);
              }
              else
              {
                _lambda_a3050a43f3157934f354774ab3dd2e02_::operator()(v55, Src, v30, v56);
              }
              Src[0] = v55;
              v32 = 0;
              v24 = (wchar_t **)v67;
            }
            else
            {
              v78 = (unsigned __int64)v24[6] >> 1;
              k = (unsigned __int64)Src;
              if ( v79 > 7 )
                k = (unsigned __int64)Src[0];
              v50 = (const char *)(k + 2 * v30);
              v32 = 0;
              if ( v48 )
              {
                for ( j = v29 - v30; j; --j )
                {
                  *(_WORD *)v50 = 0;
                  v50 += 2;
                }
                do
                  --v48;
                while ( v48 );
              }
              *(_WORD *)(k + 2 * v29) = 0;
            }
          }
          else
          {
            v78 = (unsigned __int64)v24[6] >> 1;
            v31 = Src;
            if ( v79 > 7 )
              v31 = (void **)Src[0];
            v32 = 0;
            *((_WORD *)v31 + v29) = 0;
          }
          if ( v29 )
          {
            for ( k = 0; k < v29; ++k )
            {
              j = LOBYTE(v28[k]);
              LOWORD(j) = _byteswap_ushort(v28[k]);
              if ( !(_WORD)j )
              {
                std::wstring::resize(Src, k, 0, v22);
                break;
              }
              v33 = Src;
              if ( v79 > 7 )
                v33 = (void **)Src[0];
              *((_WORD *)v33 + k) = j;
            }
          }
          v21 = v61;
          goto LABEL_62;
        }
        switch ( (_DWORD)k )
        {
          case 3:
            v76[6] = v24[5];
            v76[7] = v24[6];
            ConvertOpenTypeName(0x3A8u);
            goto LABEL_62;
          case 4:
            v76[4] = v24[5];
            v76[5] = v24[6];
            ConvertOpenTypeName(0x3B6u);
            goto LABEL_62;
          case 5:
            v76[2] = v24[5];
            v76[3] = v24[6];
            ConvertOpenTypeName(0x3B5u);
LABEL_62:
            v34 = v78;
            v35 = Src;
            if ( v79 > 7 )
              v35 = (void **)Src[0];
            if ( v78 )
            {
              if ( v78 > 0xFFFFFFFF
                || (v36 = v78, j = 2LL * (unsigned int)v78, !is_mul_ok(2u, v78))
                || (v37 = (unsigned int)j, j = (unsigned int)j + 10LL, j < v37)
                || j > 0xFFFFFFFF )
              {
                SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(j, k, v32, v22);
              }
              v38 = operator new((unsigned int)j);
              v40 = (void **)v38;
              *v38 = 1;
              v38[1] = v36;
              if ( v35 )
              {
                v41 = 2 * v34;
                if ( 2 * v34 )
                {
                  v42 = v38 + 2;
                  if ( v38 == (_DWORD *)-8LL )
                  {
                    *(_DWORD *)_o__errno(v42, v39, v41) = 22;
                    invalid_parameter_noinfo();
                  }
                  else
                  {
                    memcpy_0(v42, v35, v41);
                  }
                }
              }
              *((_WORD *)v40 + v34 + 4) = 0;
            }
            else
            {
              v40 = (void **)&DWrite::RefString::empty_;
            }
            v75 = v40;
            v74 = v80;
            std::wstring::wstring(v80, v24);
            Block[0] = v40;
            _InterlockedIncrement((volatile signed __int32 *)v40);
            v43 = (void **)v71[1];
            if ( v43 == (void **)v71[2] )
            {
              std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>(
                v71,
                v71[1],
                (__int64)v80);
            }
            else
            {
              v73 = v71[1];
              v72 = v43;
              std::wstring::wstring(v43, v80);
              *(void **)(v44 + 32) = Block[0];
              _InterlockedIncrement((volatile signed __int32 *)Block[0]);
              *(_QWORD *)(v45 + 8) += 40LL;
            }
            v46 = Block[0];
            if ( Block[0] != &DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0], 0xFFFFFFFF) == 1 )
            {
              operator delete(v46);
            }
            v76[8] = v80;
            k = v82;
            if ( v82 > 7 )
              std::_Deallocate<16>(v80[0], 2 * v82 + 2);
            v81 = 0;
            v82 = 7;
            LOWORD(v80[0]) = 0;
            if ( v40 != (void **)&DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)v40, 0xFFFFFFFF) == 1 )
            {
              operator delete(v40);
            }
            if ( v85 != v24 )
            {
              v47 = v24[2];
              if ( (unsigned __int64)v24[3] > 7 )
                v24 = (wchar_t **)*v24;
              std::wstring::assign(v85, v24, v47);
            }
            break;
        }
      }
      else
      {
        if ( !*((_WORD *)v24 + 16) )
          goto LABEL_49;
        if ( (_DWORD)j == 1 && !(_WORD)k )
        {
          v76[0] = v24[5];
          v76[1] = v24[6];
          ParseMacRomanName(v76, Src, v25, 0x7FFFFFFFFFFFFFFELL);
          goto LABEL_62;
        }
      }
LABEL_88:
      v61 = ++v21;
    }
    while ( v21 < v68 );
  }
  if ( v87 > 7 )
    std::_Deallocate<16>(v85[0], 2 * v87 + 2);
  v86 = 0;
  v87 = 7;
  LOWORD(v85[0]) = 0;
  if ( v79 > 7 )
    std::_Deallocate<16>(Src[0], 2 * v79 + 2);
  v78 = 0;
  v79 = 7;
  LOWORD(Src[0]) = 0;
  if ( v65[0] )
  {
    std::_Deallocate<16>(v65[0], (v66 - (unsigned __int64)v65[0]) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_OWORD *)v65 = 0;
    v66 = 0;
  }
  std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName>>::_Tidy(&v62);
}

```

## disassembly

```asm
0x180024db0  mov     [rsp+arg_10], r8w
0x180024db6  mov     [rsp+arg_8], rdx
0x180024dbb  push    rbx
0x180024dbc  push    rsi
0x180024dbd  push    rdi
0x180024dbe  push    r12
0x180024dc0  push    r13
0x180024dc2  push    r14
0x180024dc4  push    r15
0x180024dc6  sub     rsp, 1D0h
0x180024dcd  mov     rax, cs:__security_cookie
0x180024dd4  xor     rax, rsp
0x180024dd7  mov     [rsp+208h+var_48], rax
0x180024ddf  movzx   r14d, r8w
0x180024de3  mov     rbx, rdx
0x180024de6  mov     [rsp+208h+var_178], rcx
0x180024dee  mov     [rsp+208h+var_198], rcx
0x180024df3  lea     rcx, [rsp+208h+var_1D0]; void *
0x180024df8  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180024dfd  nop
0x180024dfe  lea     rcx, [rsp+208h+var_1B8]; void *
0x180024e03  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180024e08  nop
0x180024e09  mov     esi, [rdx+30h]
0x180024e0c  mov     [rsp+208h+var_1A0], rsi
0x180024e11  xor     r12d, r12d
0x180024e14  mov     edi, r12d
0x180024e17  mov     [rsp+208h+var_1D8], rdi
0x180024e1c  cmp     rdi, rsi
0x180024e1f  jnb     loc_180025119
0x180024e25  mov     eax, [rbx+30h]
0x180024e28  cmp     rdi, rax
0x180024e2b  jnb     loc_180025962
0x180024e31  lea     rax, [rdi+rdi*2]
0x180024e35  lea     rdx, ds:0[rax*4]
0x180024e3d  mov     rax, [rbx+28h]
0x180024e41  movzx   ecx, byte ptr [rax+rdx+6]
0x180024e46  shl     cx, 8
0x180024e4a  movzx   eax, byte ptr [rax+rdx+7]
0x180024e4f  or      cx, ax
0x180024e52  cmp     cx, r14w
0x180024e56  jz      short loc_180024E5D
0x180024e58  inc     rdi
0x180024e5b  jmp     short loc_180024E17
0x180024e5d  mov     eax, [rbx+30h]
0x180024e60  cmp     rdi, rax
0x180024e63  jnb     loc_180025968
0x180024e69  mov     r9, [rbx+40h]
0x180024e6d  mov     r8, [rbx+28h]
0x180024e71  add     r8, rdx
0x180024e74  movzx   ecx, byte ptr [r8]
0x180024e78  shl     cx, 8
0x180024e7c  movzx   eax, byte ptr [r8+1]
0x180024e81  or      cx, ax
0x180024e84  mov     word ptr [rsp+208h+var_190], cx
0x180024e89  movzx   ecx, byte ptr [r8+2]
0x180024e8e  shl     cx, 8
0x180024e92  movzx   eax, byte ptr [r8+3]
0x180024e97  or      cx, ax
0x180024e9a  mov     word ptr [rsp+208h+var_190+2], cx
0x180024e9f  movzx   ecx, byte ptr [r8+4]
0x180024ea4  shl     cx, 8
0x180024ea8  movzx   eax, byte ptr [r8+5]
0x180024ead  or      cx, ax
0x180024eb0  mov     word ptr [rsp+208h+var_190+4], cx
0x180024eb5  movzx   ecx, byte ptr [r8+0Bh]
0x180024eba  movzx   eax, byte ptr [r8+0Ah]
0x180024ebf  shl     rax, 8
0x180024ec3  or      rcx, rax
0x180024ec6  cmp     r9, rcx
0x180024ec9  jb      loc_18002597C
0x180024ecf  movzx   edx, byte ptr [r8+9]
0x180024ed4  movzx   eax, byte ptr [r8+8]
0x180024ed9  shl     rax, 8
0x180024edd  or      rdx, rax
0x180024ee0  sub     r9, rcx
0x180024ee3  cmp     r9, rdx
0x180024ee6  jb      loc_18002597C
0x180024eec  add     rcx, [rbx+38h]
0x180024ef0  mov     qword ptr [rsp+208h+var_190+8], rcx
0x180024ef8  mov     [rsp+208h+var_180], rdx
0x180024f00  mov     r8b, 1
0x180024f03  lea     rdx, [rsp+208h+S2]
0x180024f0b  lea     rcx, [rsp+208h+var_190]
0x180024f10  call    ?TryGetLanguage@OpenTypeName@@QEBA?AV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@_N@Z; OpenTypeName::TryGetLanguage(bool)
0x180024f15  nop
0x180024f16  cmp     [rsp+208h+var_78], 0
0x180024f1f  jz      loc_1800250B8
0x180024f25  lea     rax, [rsp+208h+var_E0]
0x180024f2d  mov     [rsp+208h+var_170], rax
0x180024f35  lea     rdx, [rsp+208h+S2]
0x180024f3d  lea     rcx, [rsp+208h+var_E0]
0x180024f45  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024f4a  nop
0x180024f4b  movups  xmm0, [rsp+208h+var_190]
0x180024f50  movups  xmmword ptr [rsp+208h+Block], xmm0
0x180024f58  movsd   xmm1, [rsp+208h+var_180]
0x180024f61  movsd   [rsp+208h+var_B0], xmm1
0x180024f6a  mov     rcx, [rsp+208h+var_1C8]
0x180024f6f  cmp     rcx, [rsp+208h+var_1C0]
0x180024f74  jnz     loc_18002573C
0x180024f7a  lea     r8, [rsp+208h+var_E0]
0x180024f82  mov     rdx, rcx
0x180024f85  lea     rcx, [rsp+208h+var_1D0]
0x180024f8a  call    ??$_Emplace_reallocate@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VOpenTypeName@@@@@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VOpenTypeName@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VOpenTypeName@@@@@std@@@std@@AEAAPEAV?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VOpenTypeName@@@@QEAV2@$$QEAV2@@Z; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName>>(KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName> * const,KeyValuePair<GenericLanguageTag<std::wstring>,OpenTypeName> &&)
0x180024f8f  nop
0x180024f90  lea     rax, [rsp+208h+var_E0]
0x180024f98  mov     [rsp+208h+var_158], rax
0x180024fa0  mov     rdx, [rsp+208h+var_C8]
0x180024fa8  cmp     rdx, 7
0x180024fac  jbe     loc_1800250F9
0x180024fb2  mov     al, 1
0x180024fb4  test    al, al
0x180024fb6  jnz     loc_1800258BD
0x180024fbc  mov     [rsp+208h+var_D0], r12
0x180024fc4  mov     [rsp+208h+var_C8], 7
0x180024fd0  mov     word ptr [rsp+208h+var_E0], r12w
0x180024fd9  xor     r8d, r8d
0x180024fdc  lea     rdx, [rsp+208h+S1]
0x180024fe4  lea     rcx, [rsp+208h+var_190]
0x180024fe9  call    ?TryGetLanguage@OpenTypeName@@QEBA?AV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@_N@Z; OpenTypeName::TryGetLanguage(bool)
0x180024fee  nop
0x180024fef  cmp     [rsp+208h+var_70], 7
0x180024ff8  jbe     loc_180025100
0x180024ffe  mov     al, 1
0x180025000  lea     rdx, [rsp+208h+S2]
0x180025008  test    al, al
0x18002500a  jz      short loc_180025014
0x18002500c  mov     rdx, [rsp+208h+S2]; S2
0x180025014  cmp     [rsp+208h+var_50], 7
0x18002501d  jbe     loc_180025107
0x180025023  mov     al, 1
0x180025025  lea     rcx, [rsp+208h+S1]
0x18002502d  test    al, al
0x18002502f  jz      short loc_180025039
0x180025031  mov     rcx, [rsp+208h+S1]; S1
0x180025039  mov     r8, [rsp+208h+N]; N
0x180025041  cmp     r8, [rsp+208h+var_78]
0x180025049  jnz     loc_18002596E
0x18002504f  test    r8, r8
0x180025052  jz      loc_180025975
0x180025058  call    wmemcmp
0x18002505d  test    eax, eax
0x18002505f  jnz     loc_180025112
0x180025065  mov     al, 1
0x180025067  test    al, al
0x180025069  jnz     short loc_180025083
0x18002506b  lea     r8, [rsp+208h+var_190]
0x180025070  lea     rdx, [rsp+208h+S1]
0x180025078  lea     rcx, [rsp+208h+var_1D0]
0x18002507d  call    ?Add@?$OpenTypeNameList@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@@@QEAAXAEBV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@AEBVOpenTypeName@@@Z; OpenTypeNameList<GenericLanguageTag<std::wstring>>::Add(GenericLanguageTag<std::wstring> const &,OpenTypeName const &)
0x180025082  nop
0x180025083  mov     rdx, [rsp+208h+var_50]
0x18002508b  cmp     rdx, 7
0x18002508f  jbe     short loc_18002510E
0x180025091  mov     al, 1
0x180025093  test    al, al
0x180025095  jnz     loc_1800258D7
0x18002509b  mov     [rsp+208h+N], r12
0x1800250a3  mov     [rsp+208h+var_50], 7
0x1800250af  mov     word ptr [rsp+208h+S1], r12w
0x1800250b8  mov     rdx, [rsp+208h+var_70]
0x1800250c0  cmp     rdx, 7
0x1800250c4  jbe     short loc_1800250F5
0x1800250c6  mov     al, 1
0x1800250c8  test    al, al
0x1800250ca  jnz     loc_1800258A3
0x1800250d0  mov     [rsp+208h+var_78], r12
0x1800250d8  mov     [rsp+208h+var_70], 7
0x1800250e4  mov     word ptr [rsp+208h+S2], r12w
0x1800250ed  inc     rdi
0x1800250f0  jmp     loc_180024E17
0x1800250f5  xor     al, al
0x1800250f7  jmp     short loc_1800250C8
0x1800250f9  xor     al, al
0x1800250fb  jmp     loc_180024FB4
0x180025100  xor     al, al
0x180025102  jmp     loc_180025000
0x180025107  xor     al, al
0x180025109  jmp     loc_180025025
0x18002510e  xor     al, al
0x180025110  jmp     short loc_180025093
0x180025112  xor     al, al
0x180025114  jmp     loc_180025067
0x180025119  mov     rbx, [rsp+208h+var_1C8]
0x18002511e  sub     rbx, [rsp+208h+var_1D0]
0x180025123  sar     rbx, 3
0x180025127  mov     r15, 6DB6DB6DB6DB6DB7h
0x180025131  imul    rbx, r15
0x180025135  mov     rsi, [rsp+208h+var_1B8+8]
0x18002513a  mov     rdx, rsi
0x18002513d  mov     rcx, [rsp+208h+var_1B8]
0x180025142  sub     rdx, rcx
0x180025145  sar     rdx, 3
0x180025149  cmp     rbx, rdx
0x18002514c  jb      loc_1800259B2
0x180025152  jbe     short loc_18002517B
0x180025154  mov     rax, [rsp+208h+var_1A8]
0x180025159  sub     rax, rcx
0x18002515c  sar     rax, 3
0x180025160  cmp     rbx, rax
0x180025163  jbe     loc_1800259B8
0x180025169  mov     rdx, rbx
0x18002516c  lea     rcx, [rsp+208h+var_1B8]
0x180025171  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@PEAUBuilderLinkedEntry@GlyphGraphicDataBuilder@@V?$allocator@PEAUBuilderLinkedEntry@GlyphGraphicDataBuilder@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<GlyphGraphicDataBuilder::BuilderLinkedEntry *>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180025176  mov     rcx, [rsp+208h+var_1B8]
0x18002517b  mov     rax, r12
0x18002517e  test    rbx, rbx
0x180025181  jz      short loc_180025194
0x180025183  mov     [rcx+rax*8], rax
0x180025187  inc     rax
0x18002518a  mov     rcx, [rsp+208h+var_1B8]
0x18002518f  cmp     rax, rbx
0x180025192  jb      short loc_180025183
0x180025194  mov     rdx, [rsp+208h+var_1B8+8]
0x180025199  mov     r8, rdx
0x18002519c  sub     r8, rcx
0x18002519f  sar     r8, 3
0x1800251a3  lea     r9, [rsp+208h+var_1D0]
0x1800251a8  call    ??$_Sort_unchecked@PEA_KV_lambda_c80a0a30d397bbb4dbaf80130ad47a37_@@@std@@YAXPEA_K0_JV_lambda_c80a0a30d397bbb4dbaf80130ad47a37_@@@Z; std::_Sort_unchecked<unsigned __int64 *,_lambda_c80a0a30d397bbb4dbaf80130ad47a37_>(unsigned __int64 *,unsigned __int64 *,__int64,_lambda_c80a0a30d397bbb4dbaf80130ad47a37_)
0x1800251ad  mov     rdx, [rsp+208h+var_1C8]
0x1800251b2  sub     rdx, [rsp+208h+var_1D0]
0x1800251b7  sar     rdx, 3
0x1800251bb  imul    rdx, r15
0x1800251bf  mov     [rsp+208h+var_198], rdx
0x1800251c4  xorps   xmm0, xmm0
0x1800251c7  movups  xmmword ptr [rsp+208h+Src], xmm0
0x1800251cf  mov     [rsp+208h+var_F0], r12
0x1800251d7  mov     [rsp+208h+var_E8], r12
0x1800251df  lea     rcx, [rsp+208h+Src]
0x1800251e7  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800251ec  nop
0x1800251ed  movups  xmmword ptr [rsp+208h+var_A8], xmm0
0x1800251f5  mov     [rsp+208h+var_98], r12
0x1800251fd  mov     [rsp+208h+var_90], r12
0x180025205  lea     rcx, [rsp+208h+var_A8]
0x18002520d  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180025212  nop
0x180025213  mov     r13, r12
0x180025216  mov     [rsp+208h+var_1D8], r12
0x18002521b  test    rdx, rdx
0x18002521e  jz      loc_18002561C
0x180025224  mov     edi, 0FFFFFFFFh
0x180025229  lea     r14, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180025230  mov     r9, 7FFFFFFFFFFFFFFEh
0x18002523a  mov     rax, [rsp+208h+var_1B8+8]
0x18002523f  mov     rcx, [rsp+208h+var_1B8]
0x180025244  sub     rax, rcx
0x180025247  sar     rax, 3
0x18002524b  cmp     r13, rax
0x18002524e  jnb     loc_180025A75
0x180025254  mov     rdx, [rcx+r13*8]; char *
0x180025258  mov     rax, [rsp+208h+var_1C8]
0x18002525d  mov     rcx, [rsp+208h+var_1D0]
0x180025262  sub     rax, rcx
0x180025265  sar     rax, 3
0x180025269  imul    rax, r15
0x18002526d  cmp     rdx, rax
0x180025270  jnb     loc_180025A6A
0x180025276  imul    r15, rdx, 38h ; '8'
0x18002527a  add     r15, rcx
0x18002527d  mov     [rsp+208h+var_1A0], r15
0x180025282  lea     rdx, [rsp+208h+var_A8]
0x18002528a  cmp     [rsp+208h+var_90], 7
0x180025293  cmova   rdx, [rsp+208h+var_A8]; S2
0x18002529c  mov     r8, [r15+10h]; N
0x1800252a0  cmp     qword ptr [r15+18h], 7
0x1800252a5  jbe     loc_18002558B
0x1800252ab  mov     rcx, [r15]; S1
0x1800252ae  cmp     r8, [rsp+208h+var_98]
0x1800252b6  jnz     short loc_1800252D8
0x1800252b8  test    r8, r8
0x1800252bb  jz      loc_180025569
0x1800252c1  call    wmemcmp
0x1800252c6  test    eax, eax
0x1800252c8  jz      loc_180025569
0x1800252ce  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800252d8  movzx   edx, word ptr [r15+22h]
0x1800252dd  movzx   ecx, word ptr [r15+20h]
0x1800252e2  cmp     ecx, 3
0x1800252e5  jnz     loc_180025835
0x1800252eb  mov     ecx, edx
0x1800252ed  cmp     edx, 1
0x1800252f0  jnz     loc_1800256D0
0x1800252f6  mov     r12, [r15+30h]
0x1800252fa  mov     r13, [r15+28h]
0x1800252fe  shr     r12, 1
0x180025301  mov     rsi, [rsp+208h+var_F0]
0x180025309  cmp     r12, rsi
0x18002530c  ja      loc_1800255AE
0x180025312  mov     [rsp+208h+var_F0], r12
0x18002531a  lea     rax, [rsp+208h+Src]
0x180025322  cmp     [rsp+208h+var_E8], 7
0x18002532b  cmova   rax, [rsp+208h+Src]
0x180025334  xor     r8d, r8d
0x180025337  mov     [rax+r12*2], r8w
0x18002533c  test    r12, r12
0x18002533f  jz      short loc_18002538E
0x180025341  mov     rdx, r8
0x180025344  cmp     rdx, r12
  ... truncated ...
```

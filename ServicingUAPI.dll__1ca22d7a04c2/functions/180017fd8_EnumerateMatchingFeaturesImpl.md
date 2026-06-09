# EnumerateMatchingFeaturesImpl

- ea: `0x180017fd8`
- end: `0x1800190d3`
- name: `EnumerateMatchingFeaturesImpl`
- size: `4347`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017ef8`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x1800062b8`
- `0x180006932`
- `0x18000693e`
- `0x180008a90`
- `0x180009750`
- `0x18000c468`
- `0x18000fef0`
- `0x180010450`
- `0x180010a18`
- `0x180010cd0`
- `0x1800126d4`
- `0x18001284c`
- `0x180012a70`
- `0x180012dbc`
- `0x1800130a0`
- `0x1800132dc`
- `0x180013860`
- `0x180017018`
- `0x180017fd8`
- `0x1800194a4`
- `0x180019df4`
- `0x1800497c0`
- `0x18004c014`
- `0x1800eb4b4`
- `0x1801a03d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800185e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018616`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800185e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018616`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018c10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180018c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183d5`

## string_xrefs

- `0x1800183e9`: `OneCore\Internal\Base\inc\wcp_auto_com.h`
- `0x1800183f4`: `Windows::COM::CUnicodeStringBaseTraits::Duplicate`
- `0x180018407`: `ppszTemp = AllocateChars(cchTotal)`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall EnumerateMatchingFeaturesImpl(
        int a1,
        struct _LUNICODE_STRING *a2,
        __int64 a3,
        __int64 **a4,
        __int64 **a5,
        __int64 a6)
{
  struct _LUNICODE_STRING *v7; // rdi
  int v8; // eax
  __int64 v9; // r12
  char v10; // r15
  int v11; // esi
  __int128 v12; // xmm7
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  unsigned __int16 *v15; // xmm6_8
  __int64 *v16; // r13
  __int64 v17; // rax
  _WORD *v18; // rcx
  char v19; // bl
  __int64 v20; // rcx
  __int128 v21; // xmm0
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rcx
  __int128 v25; // xmm2
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int128 v29; // xmm1
  __int64 v30; // rax
  __int64 v31; // rax
  _WORD *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  _OWORD *v35; // r14
  __int64 v36; // rcx
  struct _LUNICODE_STRING *v37; // rsi
  unsigned __int64 v38; // rbx
  unsigned __int64 v39; // rdx
  int v40; // eax
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rax
  size_t v43; // rbx
  wchar_t **v44; // r8
  const char *v45; // r9
  _DWORD *v46; // rcx
  __int128 *p_Src; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  struct _LUNICODE_STRING *v50; // rdx
  __int128 *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  struct _LUNICODE_STRING *v54; // rdx
  __int128 *v55; // rcx
  __int64 v56; // r8
  __int128 *v57; // rsi
  __int64 *v58; // rdi
  __int64 *v59; // rbx
  __int64 v60; // rbx
  const char *v61; // r9
  __int64 v62; // rcx
  int v63; // edx
  __int64 v64; // rax
  int v66; // edx
  _DWORD *v67; // rcx
  struct _LUNICODE_STRING *v68; // rcx
  __int128 v69; // xmm0
  struct _LUNICODE_STRING *v70; // rbx
  struct _LUNICODE_STRING *v71; // rcx
  struct _LUNICODE_STRING *v72; // rax
  __int64 v73; // rax
  unsigned __int64 v74; // rdx
  bool v75; // al
  int v76; // eax
  struct _LUNICODE_STRING *v77; // rcx
  struct _LUNICODE_STRING *v78; // rax
  __int64 v79; // r15
  _QWORD *v80; // rdx
  struct _LUNICODE_STRING *v81; // rbx
  __int64 v82; // rax
  Windows::COM **v83; // r12
  _QWORD *v84; // rdi
  _QWORD *v85; // r12
  __int64 v86; // rsi
  __int64 v87; // r14
  unsigned __int16 *v88; // rbx
  __int64 v89; // r10
  unsigned __int16 *v90; // r9
  __int64 v91; // rdx
  __int64 v92; // rdx
  __int64 v93; // r11
  unsigned __int16 v94; // cx
  unsigned __int16 v95; // r8
  int v96; // eax
  int v97; // ecx
  __int64 v98; // rbx
  __int64 v99; // r14
  Windows::COM *v100; // rcx
  int v101; // eax
  Windows::COM *v102; // rcx
  int v103; // eax
  LPCWCH *v104; // rsi
  void *v105; // rdi
  wchar_t **v106; // r8
  int v107; // eax
  struct _LUNICODE_STRING *v108; // rcx
  _OWORD *v109; // rax
  __int64 v110; // rsi
  Windows::COM *v111; // rcx
  int v112; // eax
  Windows::COM *v113; // rcx
  int v114; // eax
  _QWORD **v115; // rbx
  _QWORD **v116; // r14
  void *v117; // rdi
  wchar_t **v118; // r8
  int v119; // ecx
  int v120; // ecx
  int v121; // eax
  struct _LUNICODE_STRING *v122; // rbx
  struct _LUNICODE_STRING *v123; // rcx
  const char *v124; // r9
  int bIgnoreCase; // [rsp+28h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+28h] [rbp-E0h]
  __int64 v127; // [rsp+48h] [rbp-C0h] BYREF
  struct _LUNICODE_STRING *v128; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v129; // [rsp+58h] [rbp-B0h]
  wchar_t v130[4]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v131; // [rsp+68h] [rbp-A0h]
  struct _LUNICODE_STRING *v132; // [rsp+70h] [rbp-98h] BYREF
  struct _LUNICODE_STRING *v133; // [rsp+78h] [rbp-90h]
  __int128 v134; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 *v135; // [rsp+90h] [rbp-78h]
  int v136; // [rsp+98h] [rbp-70h]
  int v137; // [rsp+9Ch] [rbp-6Ch]
  int v138[4]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v139; // [rsp+B0h] [rbp-58h]
  const char *v140; // [rsp+B8h] [rbp-50h]
  _OWORD *v141; // [rsp+C0h] [rbp-48h]
  __int64 v142; // [rsp+C8h] [rbp-40h]
  __int128 v143; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v144; // [rsp+E0h] [rbp-28h]
  void *Buf1; // [rsp+E8h] [rbp-20h]
  __int64 v146; // [rsp+F0h] [rbp-18h]
  __int64 v147; // [rsp+F8h] [rbp-10h]
  __int128 v148; // [rsp+100h] [rbp-8h]
  __int128 v149; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v150; // [rsp+128h] [rbp+20h]
  __int64 v151; // [rsp+138h] [rbp+30h]
  __int128 v152; // [rsp+148h] [rbp+40h] BYREF
  __int64 v153; // [rsp+158h] [rbp+50h]
  __int128 v154; // [rsp+168h] [rbp+60h] BYREF
  __int64 v155; // [rsp+178h] [rbp+70h]
  __int128 v156; // [rsp+188h] [rbp+80h] BYREF
  __int64 v157; // [rsp+198h] [rbp+90h]
  __int128 v158; // [rsp+1A8h] [rbp+A0h] BYREF
  _WORD *v159; // [rsp+1B8h] [rbp+B0h]
  __int128 v160; // [rsp+1C0h] [rbp+B8h] BYREF
  Windows::COM *v161; // [rsp+1D0h] [rbp+C8h]
  __int128 v162; // [rsp+1D8h] [rbp+D0h] BYREF
  struct _LUNICODE_STRING *v163; // [rsp+1E8h] [rbp+E0h]
  __int128 Src; // [rsp+1F0h] [rbp+E8h] BYREF
  struct _LUNICODE_STRING *v165; // [rsp+200h] [rbp+F8h]
  unsigned __int64 v166; // [rsp+208h] [rbp+100h]
  _QWORD v167[5]; // [rsp+210h] [rbp+108h] BYREF
  __int64 v168; // [rsp+238h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v151 = -2;
  v146 = a3;
  v7 = a2;
  Buf1 = a2;
  v8 = a1;
  v9 = a6;
  v142 = a6;
  v10 = 0;
  v136 = a1 & 2;
  v11 = a1 & 4;
  LODWORD(v129) = v11;
  LOBYTE(v8) = a1 & 1;
  v137 = v8;
  v12 = 0;
  v135 = 0;
  if ( a2 )
  {
    v13 = *(unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 && *v13 )
    {
      v160 = 0;
      v161 = 0;
      v14 = -1;
      v7 = 0;
      do
        ++v14;
      while ( v13[v14] );
LABEL_6:
      *(_QWORD *)&v160 = 2 * v14;
      *((_QWORD *)&v160 + 1) = 2 * v14 + 2;
      v12 = v160;
      v15 = v13;
      goto LABEL_13;
    }
    v13 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
    v7 = 0;
    if ( v13 && *v13 )
    {
      v160 = 0;
      v161 = 0;
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      goto LABEL_6;
    }
  }
  v15 = v135;
LABEL_13:
  Src = 0;
  v165 = v7;
  v166 = 7;
  LOWORD(Src) = (_WORD)v7;
  ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(&Src);
  v165 = v7;
  v16 = *a4;
  v17 = (__int64)&(*a4)[21 * (_QWORD)a4[1]];
  v131 = v17;
  if ( v16 != (__int64 *)v17 )
  {
    v147 = 32;
    do
    {
      v18 = (_WORD *)v16[3];
      if ( v18 )
      {
        if ( (_WORD)v7 != *v18 && (unsigned int)(*((_DWORD *)v16 + 16) - 3) > 1 )
        {
          v19 = 1;
LABEL_21:
          v20 = *v16;
          v21 = 0;
          v22 = 0;
          v160 = 0;
          if ( v20 )
          {
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)(v20 + 2 * v23) != (_WORD)v7 );
            *(_QWORD *)&v160 = 2 * v23;
            *((_QWORD *)&v160 + 1) = 2 * v23 + 2;
            v22 = v20;
            v21 = v160;
          }
          v24 = v16[2];
          v25 = 0;
          v26 = 0;
          v143 = 0;
          if ( v24 )
          {
            v27 = -1;
            do
              ++v27;
            while ( *(_WORD *)(v24 + 2 * v27) != (_WORD)v7 );
            *(_QWORD *)&v143 = 2 * v27;
            *((_QWORD *)&v143 + 1) = 2 * v27 + 2;
            v26 = v24;
            v25 = v143;
          }
          v28 = v16[1];
          v29 = 0;
          v30 = 0;
          v134 = 0;
          if ( v28 )
          {
            v31 = -1;
            do
              ++v31;
            while ( *(_WORD *)(v28 + 2 * v31) != (_WORD)v7 );
            *(_QWORD *)&v134 = 2 * v31;
            *((_QWORD *)&v134 + 1) = 2 * v31 + 2;
            v30 = v28;
            v29 = v134;
          }
          v152 = v21;
          v153 = v22;
          v154 = v25;
          v155 = v26;
          v156 = v29;
          v157 = v30;
          v149 = v12;
          v150 = v15;
          LOBYTE(v28) = v19;
          if ( (unsigned __int8)IsNamespaceMatch(
                                  v28,
                                  (unsigned int)&v149,
                                  (unsigned int)&v156,
                                  (unsigned int)&v154,
                                  (__int64)&v152) )
          {
            *(_OWORD *)v138 = 0;
            v139 = 0;
            v32 = (_WORD *)v16[3];
            if ( v32 )
            {
              if ( (_WORD)v7 != *v32 )
              {
                v148 = 0;
                v33 = -1;
                do
                  ++v33;
                while ( v32[v33] != (_WORD)v7 );
                *(_QWORD *)&v148 = 2 * v33;
                *((_QWORD *)&v148 + 1) = 2 * v33 + 2;
                v158 = v148;
                v159 = v32;
                v34 = ShredStringIdIntoAttributes(
                        (const struct _LUNICODE_STRING *)&v158,
                        0x7Eu,
                        (struct _LUNICODE_STRING *)v138,
                        0,
                        v7,
                        v7,
                        v7);
                if ( v34 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x163,
                    (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                    (const char *)(unsigned int)v34,
                    bIgnoreCase);
              }
            }
            v132 = v7;
            v35 = operator new(0x28u);
            v141 = v35;
            *v35 = 0;
            v35[1] = 0;
            *((_QWORD *)v35 + 4) = 0;
            v132 = (struct _LUNICODE_STRING *)v35;
            bIgnoreCasea = (int)v35;
            LOBYTE(v36) = v19;
            GetFeatureName(v36, v16[1], v16[2], *v16);
            v37 = v7;
            v133 = v7;
            if ( *(_QWORD *)v35 )
            {
              v38 = -1;
              do
                ++v38;
              while ( *(_WORD *)(*(_QWORD *)v35 + 2 * v38) );
              if ( v38 )
              {
                v39 = v38 + 1;
                if ( v38 + 1 < v38 )
                  goto LABEL_59;
                if ( HIDWORD(v39) )
                {
                  if ( ((2 * HIDWORD(v39)) & 0xFFFFFFFF00000000uLL) != 0 )
                  {
                    v40 = -2147024362;
                    v41 = -1;
                  }
                  else
                  {
                    v42 = 2LL * (unsigned int)v39;
                    v41 = v42 + (HIDWORD(v39) << 33);
                    if ( v41 < v42 )
                      v40 = -2147024362;
                    else
                      v40 = 0;
                  }
                }
                else
                {
                  v40 = 0;
                  v41 = 2LL * (unsigned int)v39;
                }
                if ( v40 < 0 || v41 > 0xFFFFFFFF )
                  v7 = 0;
                else
                  v7 = (struct _LUNICODE_STRING *)CoTaskMemAlloc((unsigned int)v41);
                if ( !v7 )
                {
                  *(_QWORD *)v138 = "OneCore\\Internal\\Base\\inc\\wcp_auto_com.h";
                  *(_QWORD *)&v138[2] = "Windows::COM::CUnicodeStringBaseTraits::Duplicate";
                  v139 = 120;
                  v140 = "ppszTemp = AllocateChars(cchTotal)";
                  RtlReportErrorOrigination(v138, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942414LL);
                  goto LABEL_59;
                }
                v43 = 2 * v38;
                memcpy_0(v7, *(const void **)v35, v43);
                *(_WORD *)((char *)v7 + v43) = 0;
              }
            }
            v37 = v7;
LABEL_59:
            *((_QWORD *)v35 + 1) = v37;
            *(_QWORD *)v130 = 0;
            if ( !Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResultInfo,3,&void CloseWithFreeFeatureResultInfo(FeatureResultInfo)>>::Allocate<>(v130) )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x179,
                (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                v45);
            v46 = *(_DWORD **)v130;
            *(_DWORD *)(*(_QWORD *)v130 + 4LL) = *((_DWORD *)v16 + 30);
            *v46 = *((_DWORD *)v16 + 29);
            *((_QWORD *)v35 + 2) = v46;
            v133 = 0;
            if ( v136 )
            {
              v165 = 0;
              p_Src = &Src;
              if ( v166 > 7 )
                p_Src = (__int128 *)Src;
              *(_WORD *)p_Src = 0;
              v48 = v16[1];
              if ( v48 )
              {
                v49 = -1;
                do
                  ++v49;
                while ( *(_WORD *)(v48 + 2 * v49) );
                std::wstring::_Append<wchar_t>(&Src);
                v50 = v165;
                v51 = &Src;
                if ( (unsigned __int64)v165 >= v166 )
                {
                  ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&Src);
                }
                else
                {
                  v165 = (struct _LUNICODE_STRING *)((char *)v165 + 1);
                  if ( v166 > 7 )
                    v51 = (__int128 *)Src;
                  *(_DWORD *)((char *)v51 + 2 * (_QWORD)v50) = 46;
                }
              }
              v52 = v16[2];
              if ( v52 )
              {
                v53 = -1;
                do
                  ++v53;
                while ( *(_WORD *)(v52 + 2 * v53) );
                std::wstring::_Append<wchar_t>(&Src);
                v54 = v165;
                v55 = &Src;
                if ( (unsigned __int64)v165 >= v166 )
                {
                  ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&Src);
                }
                else
                {
                  v165 = (struct _LUNICODE_STRING *)((char *)v165 + 1);
                  if ( v166 > 7 )
                    v55 = (__int128 *)Src;
                  *(_DWORD *)((char *)v55 + 2 * (_QWORD)v54) = 46;
                }
              }
              v56 = -1;
              do
                ++v56;
              while ( *(_WORD *)(*v16 + 2 * v56) );
              std::wstring::_Append<wchar_t>(&Src);
              v57 = &Src;
              if ( v166 > 7 )
                v57 = (__int128 *)Src;
              v58 = *a5;
              v59 = (__int64 *)(*a5)[1];
              v138[3] = 0;
              v44 = 0;
              if ( !*((_BYTE *)v59 + 25) )
              {
                do
                {
                  if ( (int)_o__wcsicmp(v59[4], v57) >= 0 )
                  {
                    v58 = v59;
                    v59 = (__int64 *)*v59;
                  }
                  else
                  {
                    v59 = (__int64 *)v59[2];
                  }
                }
                while ( !*((_BYTE *)v59 + 25) );
                v9 = v142;
                v44 = 0;
              }
              if ( !*((_BYTE *)v58 + 25) && (int)_o__wcsicmp(v57, v58[4]) >= 0 && v58 != *a5 )
              {
                v60 = v58[5];
                if ( *(_DWORD *)(v60 + 4) != *((_DWORD *)v16 + 29) || *(_DWORD *)(v60 + 8) != *((_DWORD *)v16 + 30) )
                {
                  v133 = (struct _LUNICODE_STRING *)v58[5];
                  if ( v60 )
                  {
                    *(_QWORD *)v130 = 0;
                    if ( !Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResultInfo,3,&void CloseWithFreeFeatureResultInfo(FeatureResultInfo)>>::Allocate<>(v130) )
                      wil::details::in1diag3::_Throw_NullAlloc(
                        retaddr,
                        (void *)0x1A6,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                        v61);
                    v62 = *(_QWORD *)v130;
                    **(_DWORD **)v130 = *(_DWORD *)(v60 + 4);
                    *(_DWORD *)(v62 + 4) = *(_DWORD *)(v60 + 8);
                    *((_QWORD *)v35 + 3) = v62;
                  }
                }
              }
            }
            v7 = (struct _LUNICODE_STRING *)Buf1;
            if ( Buf1 )
            {
              v63 = *((_DWORD *)Buf1 + 5);
              if ( v63 )
              {
                if ( (v63 & *(_DWORD *)(*((_QWORD *)v35 + 2) + 4LL)) != v63 )
                {
                  v64 = *((_QWORD *)v35 + 3);
                  if ( !v64 || (v63 & *(_DWORD *)(v64 + 4)) != v63 )
                  {
                    Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v35);
                    operator delete(v35);
                    v7 = 0;
                    goto LABEL_103;
                  }
                }
              }
              v66 = *((_DWORD *)Buf1 + 4);
              v7 = 0;
              if ( v66 )
              {
                if ( (v66 & **((_DWORD **)v35 + 2)) != v66 )
                {
                  v67 = (_DWORD *)*((_QWORD *)v35 + 3);
                  if ( !v67 || (*v67 & v66) != v66 )
                  {
                    Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v35);
                    v68 = (struct _LUNICODE_STRING *)v35;
                    goto LABEL_112;
                  }
                }
              }
            }
            v69 = 0;
            v162 = 0;
            v163 = v7;
            v70 = v7;
            *(_QWORD *)v130 = v7;
            v71 = (struct _LUNICODE_STRING *)*v16;
            v72 = 0;
            v134 = 0;
            if ( v71 )
            {
              v73 = -1;
              do
                ++v73;
              while ( *((_WORD *)v71 + v73) != (_WORD)v7 );
              v74 = 2 * v73;
              *(_QWORD *)&v134 = 2 * v73;
              *((_QWORD *)&v134 + 1) = 2 * v73 + 2;
              v72 = v71;
              v69 = v134;
            }
            else
            {
              v74 = (unsigned __int64)v7;
              v71 = v7;
            }
            *(_OWORD *)v138 = v69;
            v139 = (__int64)v72;
            if ( v74 < 0x12 )
              v75 = (char)v7;
            else
              v75 = memcmp_0(v71, L"Language.", 0x12u) == 0;
            if ( v75 )
            {
              v160 = 0;
              v161 = 0;
              LOBYTE(v127) = 46;
              if ( (unsigned __int8)Windows::StringUtil::Impl::TrySplitStringOnAsciiPredicateMatch<_LUNICODE_STRING,Windows::StringUtil::Impl::AsciiCharEqualPredicate>(
                                      1,
                                      (unsigned int)v138,
                                      (unsigned int)&v127,
                                      (unsigned int)&v149,
                                      (__int64)&v160) )
              {
                LOBYTE(v127) = 45;
                if ( (unsigned __int8)Windows::StringUtil::Impl::TrySplitStringOnAsciiPredicateMatch<_LUNICODE_STRING,Windows::StringUtil::Impl::AsciiCharEqualPredicate>(
                                        0,
                                        (unsigned int)&v160,
                                        (unsigned int)&v127,
                                        (unsigned int)&v149,
                                        (__int64)v138) )
                {
                  v76 = Windows::COM::CopyOut(v161, v130, v44);
                  if ( v76 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x1CF,
                      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                      (const char *)(unsigned int)v76,
                      bIgnoreCasea);
                  v70 = *(struct _LUNICODE_STRING **)v130;
                  if ( *(_QWORD *)v130 && (_WORD)v7 != **(_WORD **)v130 )
                  {
                    v128 = v7;
                    v77 = (struct _LUNICODE_STRING *)operator new(0x18u);
                    *(_OWORD *)v77 = 0;
                    v128 = v77;
                    *((_DWORD *)v77 + 2) = 2;
                    *((_DWORD *)v77 + 3) = 2;
                    v78 = v70;
                    v70 = v7;
                    *(_QWORD *)v130 = v7;
                    *((_QWORD *)v77 + 2) = v78;
                    if ( *((struct _LUNICODE_STRING **)&v162 + 1) == v163 )
                    {
                      std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                        &v162,
                        *((_QWORD *)&v162 + 1),
                        &v128);
                    }
                    else
                    {
                      v128 = v7;
                      **((_QWORD **)&v162 + 1) = v77;
                      *((_QWORD *)&v162 + 1) += 8LL;
                    }
                    Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
                  }
                }
              }
            }
            if ( v70 )
              CoTaskMemFree(v70);
            v79 = *((_QWORD *)v35 + 2);
            if ( (_BYTE)v137 == (_BYTE)v7 )
            {
              if ( (_QWORD)v162 != *((_QWORD *)&v162 + 1) )
                DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                  &v162,
                  v79 + 40);
              v10 = 1;
              v80 = *(_QWORD **)(v9 + 8);
              if ( v80 != *(_QWORD **)(v9 + 16) )
              {
                *v80 = v35;
                goto LABEL_138;
              }
LABEL_139:
              std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>>(
                v9,
                v80,
                &v132);
              v81 = v132;
            }
            else
            {
              v82 = v16[4];
              if ( !v82 )
                v82 = v16[5];
              *(_QWORD *)(v79 + 24) = v82;
              *(_QWORD *)(v79 + 32) = v16[5];
              *(_QWORD *)(v79 + 8) = v7;
              v83 = (Windows::COM **)(v79 + 16);
              *(_QWORD *)(v79 + 16) = v7;
              if ( *((_DWORD *)v16 + 20) > (unsigned int)v7 )
              {
                v84 = *(_QWORD **)v146;
                v85 = *(_QWORD **)(v146 + 8);
                while ( 1 )
                {
                  if ( v84 == v85 )
                  {
                    v7 = 0;
                    v83 = (Windows::COM **)(v79 + 16);
                    goto LABEL_178;
                  }
                  v86 = v16[9];
                  v87 = v86 + 24LL * *((unsigned int *)v16 + 20);
                  if ( v86 != v87 )
                    break;
LABEL_175:
                  v84 += 4;
                }
                v44 = 0;
                while ( 1 )
                {
                  v88 = v84[3] <= 7u ? (unsigned __int16 *)v84 : (unsigned __int16 *)*v84;
                  v89 = 2LL * v84[2];
                  v90 = *(unsigned __int16 **)v86;
                  if ( *(_QWORD *)v86 )
                  {
                    v91 = -1;
                    do
                      ++v91;
                    while ( v90[v91] );
                    v92 = 2 * v91;
                    v93 = v92 + 2;
                  }
                  else
                  {
                    v92 = 0;
                    v90 = 0;
                    v93 = 0;
                  }
                  while ( 1 )
                  {
                    if ( !v89 )
                    {
                      v96 = -(v92 != 0);
                      goto LABEL_171;
                    }
                    if ( !v92 )
                    {
                      v96 = 1;
                      goto LABEL_171;
                    }
                    if ( *v88 > 0x7Fu )
                      break;
                    v94 = *v90;
                    v95 = v147 + *v88;
                    if ( (unsigned __int16)(*v88 - 65) > 0x19u )
                      v95 = *v88;
                    if ( (unsigned __int16)(v94 - 65) <= 0x19u )
                      v94 += 32;
                    if ( v95 != v94 )
                    {
                      v96 = v95 < v94 ? -1 : 1;
                      v44 = 0;
LABEL_171:
                      v97 = 0;
                      goto LABEL_172;
                    }
                    ++v88;
                    v89 -= 2;
                    ++v90;
                    v92 -= 2;
                    v93 -= 2;
                    v44 = 0;
                  }
                  LODWORD(v128) = 0;
                  *(_QWORD *)&v143 = v89;
                  *((_QWORD *)&v143 + 1) = v89;
                  v144 = v88;
                  *(_QWORD *)&v134 = v92;
                  *((_QWORD *)&v134 + 1) = v93;
                  v135 = v90;
                  v97 = RtlCompareEncodedLBlobs(
                          (unsigned int)&v143,
                          (unsigned int)RtlDecodeUtf16LE,
                          (unsigned int)&v134,
                          (unsigned int)RtlDecodeUtf16LE,
                          (__int64)RtlDowncaseUCSCharacter,
                          (__int64)&v128);
                  v44 = 0;
                  if ( v97 >= 0 )
                    v97 = 0;
                  v96 = (int)v128;
LABEL_172:
                  if ( !v96 && v97 >= 0 )
                    break;
                  v86 += 24;
                  if ( v86 == v87 )
                    goto LABEL_175;
                }
                v100 = *(Windows::COM **)(v86 + 16);
                v7 = 0;
                if ( v100 )
                {
                  v101 = Windows::COM::CopyOut(v100, (const wchar_t *)(v79 + 8), 0);
                  if ( v101 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x209,
                      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                      (const char *)(unsigned int)v101,
                      bIgnoreCasea);
                }
                v102 = *(Windows::COM **)(v86 + 8);
                v83 = (Windows::COM **)(v79 + 16);
                if ( v102 )
                {
                  v103 = Windows::COM::CopyOut(v102, (const wchar_t *)(v79 + 16), v44);
                  if ( v103 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20E,
                      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                      (const char *)(unsigned int)v103,
                      bIgnoreCasea);
                }
              }
LABEL_178:
              v98 = v16[11];
              v99 = v98 + 24LL * *((unsigned int *)v16 + 24);
              while ( v98 != v99 )
              {
                v167[0] = L"SettingsPageOptions.ManageFeatureSettings";
                v167[1] = L"SettingsPageOptions.FeatureType";
                v167[2] = L"SettingsPageOptions.Language";
                v167[3] = L"SettingsPageOptions.SharedLanguages";
                v167[4] = L"SettingsPageOptions.Visibility";
                v104 = (LPCWCH *)v167;
                do
                {
                  if ( CompareStringOrdinal(*(LPCWCH *)v98, -1, *v104, -1, 1) == 2 )
                  {
                    v128 = v7;
                    v105 = operator new(0x18u);
                    *(_QWORD *)v130 = v105;
                    *(_OWORD *)v105 = 0;
                    *((_QWORD *)v105 + 2) = 0;
                    v128 = (struct _LUNICODE_STRING *)v105;
                    *(_QWORD *)v105 = *v104;
                    *((_DWORD *)v105 + 2) = 1;
                    v107 = Windows::COM::CopyOut(*(Windows::COM **)(v98 + 8), (const wchar_t *)v105 + 8, v106);
                    if ( v107 < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x11B,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                        (const char *)(unsigned int)v107,
                        bIgnoreCasea);
                    *((_DWORD *)v105 + 3) = 2;
                    if ( *((struct _LUNICODE_STRING **)&v162 + 1) == v163 )
                    {
                      std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                        &v162,
                        *((_QWORD *)&v162 + 1),
                        &v128);
                    }
                    else
                    {
                      v128 = 0;
                      **((_QWORD **)&v162 + 1) = v105;
                      *((_QWORD *)&v162 + 1) += 8LL;
                    }
                    Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
                  }
                  ++v104;
                  v7 = 0;
                }
                while ( v104 != (LPCWCH *)&v168 );
                v98 += 24;
              }
              if ( *((_DWORD *)v16 + 39) != (_DWORD)v7 || *((_DWORD *)v16 + 40) != (_DWORD)v7 )
              {
                v128 = v7;
                v108 = (struct _LUNICODE_STRING *)operator new(0x18u);
                *(_QWORD *)v130 = v108;
                *(_OWORD *)v108 = 0;
                *((_QWORD *)v108 + 2) = 0;
                v128 = v108;
                *((_DWORD *)v108 + 2) = 3;
                *((_DWORD *)v108 + 3) = 3;
                *((_QWORD *)v108 + 2) = *(__int64 *)((char *)v16 + 156);
                if ( *((struct _LUNICODE_STRING **)&v162 + 1) == v163 )
                {
                  std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                    &v162,
                    *((_QWORD *)&v162 + 1),
                    &v128);
                }
                else
                {
                  v128 = v7;
                  **((_QWORD **)&v162 + 1) = v108;
                  *((_QWORD *)&v162 + 1) += 8LL;
                }
                Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
              }
              if ( (_QWORD)v162 != *((_QWORD *)&v162 + 1) )
                DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                  &v162,
                  v79 + 40);
              v109 = v141;
              v110 = *((_QWORD *)v141 + 3);
              if ( v110 )
              {
                *(_QWORD *)(v110 + 24) = *(_QWORD *)(v79 + 24);
                *(_QWORD *)(v110 + 32) = *(_QWORD *)(v79 + 32);
                v111 = *v83;
                if ( *v83 )
                {
                  if ( (_WORD)v7 != *(_WORD *)v111 )
                  {
                    v112 = Windows::COM::CopyOut(v111, (const wchar_t *)(v110 + 16), v44);
                    if ( v112 < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x233,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                        (const char *)(unsigned int)v112,
                        bIgnoreCasea);
                  }
                }
                v113 = *(Windows::COM **)(v79 + 8);
                if ( v113 )
                {
                  if ( (_WORD)v7 != *(_WORD *)v113 )
                  {
                    v114 = Windows::COM::CopyOut(v113, (const wchar_t *)(v110 + 8), v44);
                    if ( v114 < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x238,
                        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                        (const char *)(unsigned int)v114,
                        bIgnoreCasea);
                  }
                }
                v160 = 0;
                v161 = v7;
                v115 = *(_QWORD ***)(v79 + 40);
                v116 = &v115[*(_QWORD *)(v79 + 48)];
                while ( v115 != v116 )
                {
                  if ( *((_DWORD *)*v115 + 3) != 3 )
                  {
                    v128 = v7;
                    v117 = operator new(0x18u);
                    *(_QWORD *)v130 = v117;
                    *(_OWORD *)v117 = 0;
                    *((_QWORD *)v117 + 2) = 0;
                    v128 = (struct _LUNICODE_STRING *)v117;
                    *(_QWORD *)v117 = **v115;
                    *((_DWORD *)v117 + 2) = *((_DWORD *)*v115 + 2);
                    v119 = *((_DWORD *)*v115 + 3);
                    *((_DWORD *)v117 + 3) = v119;
                    v120 = v119 - 1;
                    if ( v120 )
                    {
                      if ( v120 != 1 )
                      {
                        v124 = (const char *)(unsigned int)EnsureNTSTATUS<long>(2147549183LL);
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0x25A,
                          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                          v124,
                          bIgnoreCasea);
                      }
                      v121 = Windows::COM::CopyOut((Windows::COM *)(*v115)[2], (const wchar_t *)v117 + 8, v118);
                      if ( v121 < 0 )
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0x257,
                          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
                          (const char *)(unsigned int)v121,
                          bIgnoreCasea);
                    }
                    else
                    {
                      *((_QWORD *)v117 + 2) = (*v115)[2];
                    }
                    if ( *((Windows::COM **)&v160 + 1) == v161 )
                    {
                      std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                        &v160,
                        *((_QWORD *)&v160 + 1),
                        &v128);
                    }
                    else
                    {
                      v128 = 0;
                      **((_QWORD **)&v160 + 1) = v117;
                      *((_QWORD *)&v160 + 1) += 8LL;
                    }
                    Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
                    v7 = 0;
                  }
                  ++v115;
                }
                v122 = v133;
                if ( v133 && (*((_DWORD *)v133 + 10) != (_DWORD)v7 || *((_DWORD *)v133 + 11) != (_DWORD)v7) )
                {
                  v128 = v7;
                  v123 = (struct _LUNICODE_STRING *)operator new(0x18u);
                  v133 = v123;
                  *(_OWORD *)v123 = 0;
                  *((_QWORD *)v123 + 2) = 0;
                  v128 = v123;
                  *((_DWORD *)v123 + 2) = 3;
                  *((_DWORD *)v123 + 3) = 3;
                  *((_QWORD *)v123 + 2) = *((_QWORD *)v122 + 5);
                  if ( *((Windows::COM **)&v160 + 1) == v161 )
                  {
                    std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::_Emplace_reallocate<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(
                      &v160,
                      *((_QWORD *)&v160 + 1),
                      &v128);
                  }
                  else
                  {
                    v128 = v7;
                    **((_QWORD **)&v160 + 1) = v123;
                    *((_QWORD *)&v160 + 1) += 8LL;
                  }
                  Windows::AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~AutoPointerBase<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v128);
                }
                if ( (_QWORD)v160 != *((_QWORD *)&v160 + 1) )
                  DisownResults<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>,FeatureProperties>(
                    &v160,
                    v110 + 40);
                std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v160);
                v109 = v141;
              }
              v10 = 1;
              v9 = v142;
              v80 = *(_QWORD **)(v142 + 8);
              if ( v80 == *(_QWORD **)(v142 + 16) )
                goto LABEL_139;
              *v80 = v109;
LABEL_138:
              v81 = v7;
              *(_QWORD *)(v9 + 8) += 8LL;
            }
            std::vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>::~vector<Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureProperty,4,&void CloseWithFreeFeatureProperty(FeatureProperty)>>>(&v162);
            if ( v81 )
            {
              Windows::AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>::~AutoGenericHandleBase<FeatureResult,4,Windows::AutoGenericHandle<FeatureResult,4,&void CloseWithFreeFeatureResult(FeatureResult)>>(v81);
              v68 = v81;
LABEL_112:
              operator delete(v68);
            }
LABEL_103:
            v11 = v129;
          }
          v17 = v131;
          goto LABEL_105;
        }
        v17 = v131;
      }
      v19 = (char)v7;
      if ( v11 )
        goto LABEL_21;
LABEL_105:
      v16 += 21;
    }
    while ( v16 != (__int64 *)v17 );
  }
  std::wstring::~wstring(&Src);
  return v10;
}

```

## disassembly

```asm
0x180017fd8  mov     rax, rsp
0x180017fdb  push    rbp
0x180017fdc  push    rbx
0x180017fdd  push    rsi
0x180017fde  push    rdi
0x180017fdf  push    r12
0x180017fe1  push    r13
0x180017fe3  push    r14
0x180017fe5  push    r15
0x180017fe7  lea     rbp, [rax-1A8h]
0x180017fee  sub     rsp, 268h
0x180017ff5  mov     [rbp+1A0h+var_170], 0FFFFFFFFFFFFFFFEh
0x180017ffd  movaps  xmmword ptr [rax-58h], xmm6
0x180018001  movaps  xmmword ptr [rax-68h], xmm7
0x180018005  mov     rax, cs:__security_cookie
0x18001800c  xor     rax, rsp
0x18001800f  mov     [rbp+1A0h+var_70], rax
0x180018016  mov     rbx, r9
0x180018019  mov     [rbp+1A0h+var_1B8], r8
0x18001801d  mov     rdi, rdx
0x180018020  mov     [rbp+1A0h+Buf1], rdx
0x180018024  mov     eax, ecx
0x180018026  mov     r12, [rbp+1A0h+arg_28]
0x18001802d  mov     [rbp+1A0h+var_1E0], r12
0x180018031  xor     edx, edx
0x180018033  mov     r15b, dl
0x180018036  and     ecx, 2
0x180018039  mov     [rbp+1A0h+var_210], ecx
0x18001803c  mov     esi, eax
0x18001803e  and     esi, 4
0x180018041  mov     dword ptr [rsp+2A0h+var_250], esi
0x180018045  and     al, 1
0x180018047  mov     [rbp+1A0h+var_20C], eax
0x18001804a  xorps   xmm7, xmm7
0x18001804d  xor     eax, eax
0x18001804f  mov     [rbp+1A0h+var_218], rax
0x180018053  test    rdi, rdi
0x180018056  jz      loc_1800180DC
0x18001805c  mov     rcx, [rdi]
0x18001805f  test    rcx, rcx
0x180018062  jz      short loc_1800180AC
0x180018064  cmp     dx, [rcx]
0x180018067  jz      short loc_1800180AC
0x180018069  xorps   xmm0, xmm0
0x18001806c  movups  [rbp+1A0h+var_E8], xmm0
0x180018073  mov     [rbp+1A0h+var_D8], rax
0x18001807a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001807e  xor     edi, edi
0x180018080  inc     rax
0x180018083  cmp     [rcx+rax*2], di
0x180018087  jnz     short loc_180018080
0x180018089  add     rax, rax
0x18001808c  mov     qword ptr [rbp+1A0h+var_E8], rax
0x180018093  add     rax, 2
0x180018097  mov     qword ptr [rbp+1A0h+var_E8+8], rax
0x18001809e  movups  xmm7, [rbp+1A0h+var_E8]
0x1800180a5  movq    xmm6, rcx
0x1800180aa  jmp     short loc_1800180E1
0x1800180ac  mov     rcx, [rdi+8]
0x1800180b0  xor     edi, edi
0x1800180b2  test    rcx, rcx
0x1800180b5  jz      short loc_1800180DC
0x1800180b7  cmp     di, [rcx]
0x1800180ba  jz      short loc_1800180DC
0x1800180bc  xorps   xmm0, xmm0
0x1800180bf  movups  [rbp+1A0h+var_E8], xmm0
0x1800180c6  mov     [rbp+1A0h+var_D8], rax
0x1800180cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800180d1  inc     rax
0x1800180d4  cmp     [rcx+rax*2], di
0x1800180d8  jnz     short loc_1800180D1
0x1800180da  jmp     short loc_180018089
0x1800180dc  movsd   xmm6, [rbp+1A0h+var_218]
0x1800180e1  xorps   xmm0, xmm0
0x1800180e4  movups  [rbp+1A0h+Src], xmm0
0x1800180eb  mov     [rbp+1A0h+var_A8], rdi
0x1800180f2  mov     [rbp+1A0h+var_A0], 7
0x1800180fd  mov     word ptr [rbp+1A0h+Src], di
0x180018104  mov     edx, 104h
0x180018109  lea     rcx, [rbp+1A0h+Src]; Src
0x180018110  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180018115  mov     [rbp+1A0h+var_A8], rdi
0x18001811c  mov     r13, [rbx]
0x18001811f  imul    rax, [rbx+8], 0A8h
0x180018127  add     rax, r13
0x18001812a  mov     [rsp+2A0h+var_240], rax
0x18001812f  cmp     r13, rax
0x180018132  jz      loc_1800186F2
0x180018138  mov     [rbp+1A0h+var_1B0], 20h ; ' '
0x180018140  mov     rcx, [r13+18h]
0x180018144  test    rcx, rcx
0x180018147  jz      short loc_180018163
0x180018149  cmp     di, [rcx]
0x18001814c  jz      short loc_18001815E
0x18001814e  mov     eax, [r13+40h]
0x180018152  sub     eax, 3
0x180018155  cmp     eax, 1
0x180018158  jbe     short loc_18001815E
0x18001815a  mov     bl, 1
0x18001815c  jmp     short loc_18001816E
0x18001815e  mov     rax, [rsp+2A0h+var_240]
0x180018163  mov     bl, dil
0x180018166  test    esi, esi
0x180018168  jz      loc_1800186E2
0x18001816e  mov     rcx, [r13+0]
0x180018172  xorps   xmm0, xmm0
0x180018175  xor     r8d, r8d
0x180018178  movups  [rbp+1A0h+var_E8], xmm0
0x18001817f  test    rcx, rcx
0x180018182  jz      short loc_1800181B0
0x180018184  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018188  inc     rax
0x18001818b  cmp     [rcx+rax*2], di
0x18001818f  jnz     short loc_180018188
0x180018191  add     rax, rax
0x180018194  mov     qword ptr [rbp+1A0h+var_E8], rax
0x18001819b  add     rax, 2
0x18001819f  mov     qword ptr [rbp+1A0h+var_E8+8], rax
0x1800181a6  mov     r8, rcx
0x1800181a9  movups  xmm0, [rbp+1A0h+var_E8]
0x1800181b0  mov     rcx, [r13+10h]
0x1800181b4  xorps   xmm2, xmm2
0x1800181b7  xor     edx, edx
0x1800181b9  movups  [rbp+1A0h+var_1D8], xmm2
0x1800181bd  test    rcx, rcx
0x1800181c0  jz      short loc_1800181E5
0x1800181c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800181c6  inc     rax
0x1800181c9  cmp     [rcx+rax*2], di
0x1800181cd  jnz     short loc_1800181C6
0x1800181cf  add     rax, rax
0x1800181d2  mov     qword ptr [rbp+1A0h+var_1D8], rax
0x1800181d6  add     rax, 2
0x1800181da  mov     qword ptr [rbp+1A0h+var_1D8+8], rax
0x1800181de  mov     rdx, rcx
0x1800181e1  movups  xmm2, [rbp+1A0h+var_1D8]
0x1800181e5  mov     rcx, [r13+8]
0x1800181e9  xorps   xmm1, xmm1
0x1800181ec  xor     eax, eax
0x1800181ee  movups  [rsp+2A0h+var_230+8], xmm1
0x1800181f3  test    rcx, rcx
0x1800181f6  jz      short loc_18001821D
0x1800181f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800181fc  inc     rax
0x1800181ff  cmp     [rcx+rax*2], di
0x180018203  jnz     short loc_1800181FC
0x180018205  add     rax, rax
0x180018208  mov     qword ptr [rsp+2A0h+var_230+8], rax
0x18001820d  add     rax, 2
0x180018211  mov     [rbp+1A0h+var_220], rax
0x180018215  mov     rax, rcx
0x180018218  movups  xmm1, [rsp+2A0h+var_230+8]
0x18001821d  movaps  [rbp+1A0h+var_160], xmm0
0x180018221  mov     [rbp+1A0h+var_150], r8
0x180018225  movaps  [rbp+1A0h+var_140], xmm2
0x180018229  mov     [rbp+1A0h+var_130], rdx
0x18001822d  movaps  [rbp+1A0h+var_120], xmm1
0x180018234  mov     [rbp+1A0h+var_110], rax
0x18001823b  movaps  [rbp+1A0h+var_190], xmm7
0x18001823f  movsd   [rbp+1A0h+var_180], xmm6
0x180018244  lea     rax, [rbp+1A0h+var_160]
0x180018248  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax
0x18001824d  lea     r9, [rbp+1A0h+var_140]
0x180018251  lea     r8, [rbp+1A0h+var_120]
0x180018258  lea     rdx, [rbp+1A0h+var_190]
0x18001825c  mov     cl, bl
0x18001825e  call    IsNamespaceMatch
0x180018263  test    al, al
0x180018265  jz      loc_1800186DD
0x18001826b  xorps   xmm0, xmm0
0x18001826e  xor     eax, eax
0x180018270  movups  xmmword ptr [rbp+1A0h+var_208], xmm0
0x180018274  mov     [rbp+1A0h+var_1F8], rax
0x180018278  mov     rcx, [r13+18h]
0x18001827c  test    rcx, rcx
0x18001827f  jz      short loc_1800182EE
0x180018281  cmp     di, [rcx]
0x180018284  jz      short loc_1800182EE
0x180018286  movups  [rbp+1A0h+var_1A8], xmm0
0x18001828a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001828e  inc     rax
0x180018291  cmp     [rcx+rax*2], di
0x180018295  jnz     short loc_18001828E
0x180018297  add     rax, rax
0x18001829a  mov     qword ptr [rbp+1A0h+var_1A8], rax
0x18001829e  add     rax, 2
0x1800182a2  mov     qword ptr [rbp+1A0h+var_1A8+8], rax
0x1800182a6  movups  xmm0, [rbp+1A0h+var_1A8]
0x1800182aa  movups  [rbp+1A0h+var_100], xmm0
0x1800182b1  mov     [rbp+1A0h+var_F0], rcx
0x1800182b8  mov     edx, 7Eh ; '~'; wchar_t
0x1800182bd  mov     [rsp+2A0h+var_270], rdi; struct _LUNICODE_STRING *
0x1800182c2  mov     [rsp+2A0h+var_278], rdi; struct _LUNICODE_STRING *
0x1800182c7  mov     qword ptr [rsp+2A0h+bIgnoreCase], rdi; int
0x1800182cc  xor     r9d, r9d; struct _LUNICODE_STRING *
0x1800182cf  lea     r8, [rbp+1A0h+var_208]; struct _LUNICODE_STRING *
0x1800182d3  lea     rcx, [rbp+1A0h+var_100]; struct _LUNICODE_STRING *
0x1800182da  call    ?ShredStringIdIntoAttributes@@YAJAEBU_LUNICODE_STRING@@_WPEAU1@2222@Z; ShredStringIdIntoAttributes(_LUNICODE_STRING const &,wchar_t,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *)
0x1800182df  mov     rcx, [rbp+1A8h]; this
0x1800182e6  test    eax, eax
0x1800182e8  js      loc_180019043
0x1800182ee  mov     [rsp+2A0h+var_238], rdi
0x1800182f3  mov     ecx, 28h ; '('; Size
0x1800182f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800182fd  mov     r14, rax
0x180018300  mov     [rbp+1A0h+var_1E8], rax
0x180018304  xorps   xmm0, xmm0
0x180018307  xor     eax, eax
0x180018309  movups  xmmword ptr [r14], xmm0
0x18001830d  movups  xmmword ptr [r14+10h], xmm0
0x180018312  mov     [r14+20h], rax
0x180018316  mov     [rsp+2A0h+var_238], r14
0x18001831b  mov     qword ptr [rsp+2A0h+bIgnoreCase], r14
0x180018320  mov     r9, [r13+0]
0x180018324  mov     r8, [r13+10h]
0x180018328  mov     rdx, [r13+8]
0x18001832c  mov     cl, bl
0x18001832e  call    GetFeatureName
0x180018333  mov     rsi, rdi
0x180018336  mov     qword ptr [rsp+2A0h+var_230], rdi
0x18001833b  mov     rax, [r14]
0x18001833e  xor     r8d, r8d
0x180018341  test    rax, rax
0x180018344  jz      loc_180018443
0x18001834a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001834e  mov     rbx, r9
0x180018351  inc     rbx
0x180018354  cmp     [rax+rbx*2], r8w
0x180018359  jnz     short loc_180018351
0x18001835b  test    rbx, rbx
0x18001835e  jz      loc_180018443
0x180018364  lea     rdx, [rbx+1]
0x180018368  cmp     rdx, rbx
0x18001836b  jb      loc_180018446
0x180018371  mov     rax, rdx
0x180018374  shr     rax, 20h
0x180018378  test    eax, eax
0x18001837a  jnz     short loc_180018386
0x18001837c  mov     eax, r8d
0x18001837f  mov     ecx, edx
0x180018381  add     rcx, rcx
0x180018384  jmp     short loc_1800183C0
0x180018386  mov     rcx, rax
0x180018389  add     rcx, rcx
0x18001838c  mov     rax, 0FFFFFFFF00000000h
0x180018396  test    rax, rcx
0x180018399  jnz     short loc_1800183B8
0x18001839b  mov     eax, edx
0x18001839d  add     rax, rax
0x1800183a0  shl     rcx, 20h
0x1800183a4  add     rcx, rax
0x1800183a7  cmp     rcx, rax
0x1800183aa  jb      short loc_1800183B1
0x1800183ac  mov     eax, r8d
0x1800183af  jmp     short loc_1800183C0
0x1800183b1  mov     eax, 80070216h
0x1800183b6  jmp     short loc_1800183C0
0x1800183b8  mov     eax, 80070216h
0x1800183bd  mov     rcx, r9
0x1800183c0  test    eax, eax
0x1800183c2  jns     short loc_1800183C9
0x1800183c4  mov     rdi, r8
0x1800183c7  jmp     short loc_1800183E4
0x1800183c9  mov     eax, 0FFFFFFFFh
0x1800183ce  cmp     rcx, rax
0x1800183d1  ja      short loc_1800183C4
0x1800183d3  mov     ecx, ecx; cb
0x1800183d5  call    cs:__imp_CoTaskMemAlloc
0x1800183dc  nop     dword ptr [rax+rax+00h]
0x1800183e1  mov     rdi, rax
0x1800183e4  test    rdi, rdi
0x1800183e7  jnz     short loc_18001842A
0x1800183e9  lea     rax, aOnecoreInterna_8; "OneCore\\Internal\\Base\\inc\\wcp_auto_"...
0x1800183f0  mov     qword ptr [rbp+1A0h+var_208], rax
0x1800183f4  lea     rax, aWindowsComCuni; "Windows::COM::CUnicodeStringBaseTraits:"...
0x1800183fb  mov     qword ptr [rbp+1A0h+var_208+8], rax
0x1800183ff  mov     [rbp+1A0h+var_1F8], 78h ; 'x'
0x180018407  lea     rax, aPpsztempAlloca; "ppszTemp = AllocateChars(cchTotal)"
0x18001840e  mov     [rbp+1A0h+var_1F0], rax
0x180018412  mov     r8d, 8007000Eh
0x180018418  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001841f  lea     rcx, [rbp+1A0h+var_208]
0x180018423  call    RtlReportErrorOrigination
0x180018428  jmp     short loc_180018446
0x18001842a  add     rbx, rbx
0x18001842d  mov     r8, rbx; Size
0x180018430  mov     rdx, [r14]; Src
0x180018433  mov     rcx, rdi; void *
0x180018436  call    memcpy_0
0x18001843b  xor     r8d, r8d
0x18001843e  mov     [rdi+rbx], r8w
0x180018443  mov     rsi, rdi
0x180018446  mov     [r14+8], rsi
0x18001844a  xor     edi, edi
0x18001844c  mov     qword ptr [rsp+2A0h+var_248], rdi
0x180018451  lea     rcx, [rsp+2A0h+var_248]
0x180018456  call    ??$Allocate@$$V@?$AutoNewPtr@V?$AutoGenericHandle@UFeatureResultInfo@@$02$1?CloseWithFreeFeatureResultInfo@@YAXU1@@Z@Windows@@@Windows@@QEAAPEAV?$AutoGenericHandle@UFeatureResultInfo@@$02$1?CloseWithFreeFeatureResultInfo@@YAXU1@@Z@1@XZ; Windows::AutoNewPtr<Windows::AutoGenericHandle<FeatureResultInfo,3,&CloseWithFreeFeatureResultInfo(FeatureResultInfo)>>::Allocate<>(void)
0x18001845b  mov     rcx, [rbp+1A8h]; this
0x180018462  test    rax, rax
0x180018465  jz      loc_180019031
  ... truncated ...
```

# inverted::CSemanticCursor::GetResults(std::vector<std::shared_ptr<inverted::IDecoder>,std::allocator<std::shared_ptr<inverted::IDecoder>>> const &,inverted::IInvertedQuery *,std::shared_ptr<inverted::CScanRestrictions> const &,inverted::RETRIEVAL_FLAGS,dynamic_sparse_bit<unsigned __int64> *)

- ea: `0x1802423c0`
- end: `0x180243f1b`
- name: `?GetResults@CSemanticCursor@inverted@@UEAAXAEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@PEAUIInvertedQuery@2@AEBV?$shared_ptr@VCScanRestrictions@inverted@@@4@W4RETRIEVAL_FLAGS@2@PEAU?$dynamic_sparse_bit@_K@@@Z`
- size: `7003`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002b290`
- `0x18002b7b8`
- `0x1800324c8`
- `0x180033000`
- `0x180036d60`
- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x18005cd60`
- `0x180099f2c`
- `0x18009e1dc`
- `0x18009f018`
- `0x1800e98fc`
- `0x1801183f0`
- `0x1801470bc`
- `0x1801470d4`
- `0x180147190`
- `0x180153610`
- `0x1801772c8`
- `0x1801774f0`
- `0x180188d90`
- `0x180189cce`
- `0x1801b2c24`
- `0x1801b2c64`
- `0x1801c3fdc`
- `0x1801ff710`
- `0x180219644`
- `0x180219934`
- `0x180219a94`
- `0x180219ba4`
- `0x180219e4c`
- `0x180220084`
- `0x180220138`
- `0x180225dd4`
- `0x1802262a4`
- `0x180226484`
- `0x180226720`
- `0x180241378`
- `0x1802415e8`
- `0x1802423c0`
- `0x180243f24`
- `0x180244420`
- `0x180244498`
- `0x18029437c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1802436d6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1802438c5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180243a94`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180243c7a`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1802436d6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1802438c5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180243a94`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180243c7a`

## string_xrefs

- `0x180243ecd`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180243edf`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180243ef1`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180243f09`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1802426c4`: `CONVEXCOMBINATION`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall inverted::CSemanticCursor::GetResults(
        std::_Ref_count_base **a1,
        int a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  std::_Ref_count_base **v8; // r12
  _OWORD *v9; // rsi
  BOOL v10; // edi
  __int64 result; // rax
  __int64 *v12; // rcx
  int v13; // edx
  __int64 v14; // rdx
  std::_Ref_count_base **v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  std::_Ref_count_base ***v18; // r15
  std::_Ref_count_base **v19; // r8
  std::_Ref_count_base **v20; // r9
  std::_Ref_count_base **v21; // rdx
  std::_Ref_count_base **v22; // r10
  __int64 v23; // rax
  const wchar_t *v24; // rcx
  __int64 v25; // rdx
  int v26; // ebx
  __int64 (__fastcall *v27)(__int64 *, __int128 *); // rax
  __int64 v28; // r14
  __int64 v29; // r15
  __int64 v30; // rax
  std::_Ref_count_base *v31; // rcx
  __int64 v32; // r14
  __int64 v33; // r15
  __int64 v34; // rax
  std::_Ref_count_base **v35; // rbx
  __int64 (__fastcall *v36)(__int64 *, std::_Ref_count_base **); // rax
  __int64 v37; // r14
  __int64 v38; // r15
  __int64 v39; // rax
  __int64 v40; // r14
  __int64 v41; // r15
  __int64 v42; // rax
  std::_Ref_count_base **v43; // r15
  __int64 (__fastcall *v44)(__int64 *, std::_Ref_count_base **); // rax
  __int64 v45; // rax
  __int64 v46; // r13
  void (__fastcall *v47)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, __int64, std::_Ref_count_base **, __int64, __int64); // r12
  __int64 v48; // r15
  __int64 v49; // r14
  __int64 v50; // rsi
  __int64 v51; // rdi
  __int64 v52; // rbx
  __int64 v53; // rax
  std::_Ref_count_base *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // r15
  void (__fastcall *v57)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, __int64, std::_Ref_count_base **, GUID *, GUID *); // r14
  __int64 v58; // rsi
  __int64 v59; // rdi
  __int64 v60; // rbx
  __int64 v61; // rax
  std::_Ref_count_base **v62; // r12
  __int64 (__fastcall *v63)(__int64 *, std::_Ref_count_base **); // rax
  __int64 v64; // rax
  __int64 v65; // r12
  void (__fastcall *v66)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, __int64, __int64); // r15
  __int64 v67; // r14
  __int64 v68; // rsi
  __int64 v69; // rdi
  __int64 v70; // rbx
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // r14
  void (__fastcall *v74)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, GUID *, GUID *); // rsi
  __int64 v75; // rdi
  __int64 v76; // rbx
  __int64 v77; // rax
  std::_Ref_count_base *v78; // rax
  int v79; // eax
  float v80; // xmm6_4
  std::_Ref_count_base *v81; // r12
  std::_Ref_count_base *v82; // rdi
  unsigned int v83; // ebx
  unsigned int v84; // edx
  std::_Ref_count_base **v85; // r15
  __int64 v86; // rax
  unsigned int *v87; // r14
  signed __int64 v88; // rbx
  __int64 v89; // rax
  __int64 v90; // r8
  std::_Ref_count_base *v91; // rdi
  unsigned int v92; // ecx
  std::_Ref_count_base *v93; // rax
  const char *v94; // r9
  std::_Ref_count_base **v95; // rdx
  unsigned __int64 v96; // rdx
  signed __int64 v97; // rcx
  void **v98; // rax
  unsigned __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // rax
  unsigned int **v102; // r14
  std::_Ref_count_base *v103; // rbx
  std::_Ref_count_base **v104; // rbx
  bool i; // zf
  unsigned int v106; // edi
  unsigned int v107; // edx
  __int128 *v108; // rax
  unsigned int *v109; // r15
  signed __int64 v110; // rbx
  __int64 v111; // rax
  __int64 v112; // r8
  std::_Ref_count_base *v113; // rdi
  unsigned int v114; // ecx
  const char *v115; // r9
  _QWORD *v116; // rax
  std::_Ref_count_base **v117; // rdx
  unsigned __int64 v118; // rdx
  void **v119; // rax
  unsigned __int64 v120; // r8
  __int64 v121; // rdx
  __int64 v122; // rax
  unsigned int v123; // edi
  unsigned int v124; // edx
  unsigned int v125; // eax
  __int128 *v126; // rax
  unsigned int *v127; // r15
  signed __int64 v128; // rbx
  __int64 v129; // rax
  __int64 v130; // r8
  std::_Ref_count_base *v131; // rdi
  unsigned int v132; // ecx
  const char *v133; // r9
  _QWORD *v134; // rax
  std::_Ref_count_base **v135; // rdx
  unsigned __int64 v136; // rdx
  void **v137; // rax
  unsigned __int64 v138; // r8
  __int64 v139; // rdx
  __int64 v140; // rax
  std::_Ref_count_base *v141; // rbx
  std::_Ref_count_base *v142; // r14
  unsigned int v143; // edi
  unsigned int v144; // edx
  std::_Ref_count_base **v145; // r15
  __int64 v146; // rax
  unsigned int *v147; // r14
  signed __int64 v148; // rbx
  __int64 v149; // rax
  __int64 v150; // r8
  std::_Ref_count_base *v151; // rdi
  unsigned int v152; // ecx
  std::_Ref_count_base *v153; // rax
  const char *v154; // r9
  std::_Ref_count_base **v155; // rdx
  unsigned __int64 v156; // rdx
  void **v157; // rax
  unsigned __int64 v158; // r8
  __int64 v159; // rdx
  __int64 v160; // rax
  std::_Ref_count_base *v161; // rbx
  __int64 v162; // rax
  std::_Ref_count_base **v163; // rax
  BOOL v164; // [rsp+80h] [rbp-378h] BYREF
  __int64 *v165; // [rsp+88h] [rbp-370h] BYREF
  std::_Ref_count_base **v166; // [rsp+90h] [rbp-368h] BYREF
  std::_Ref_count_base *v167; // [rsp+98h] [rbp-360h] BYREF
  int v168; // [rsp+A0h] [rbp-358h]
  __int128 *v169; // [rsp+A8h] [rbp-350h]
  std::_Ref_count_base **v170; // [rsp+B0h] [rbp-348h] BYREF
  std::_Ref_count_base **v171; // [rsp+B8h] [rbp-340h]
  int v172; // [rsp+C0h] [rbp-338h] BYREF
  std::_Ref_count_base **v173; // [rsp+C8h] [rbp-330h] BYREF
  _QWORD v174[2]; // [rsp+D0h] [rbp-328h] BYREF
  std::_Ref_count_base *v175[2]; // [rsp+E0h] [rbp-318h] BYREF
  __int128 v176; // [rsp+F0h] [rbp-308h] BYREF
  std::_Ref_count_base *Buf1[2]; // [rsp+100h] [rbp-2F8h] BYREF
  std::_Ref_count_base **v178; // [rsp+110h] [rbp-2E8h]
  __int64 v179; // [rsp+118h] [rbp-2E0h]
  _BYTE v180[16]; // [rsp+120h] [rbp-2D8h] BYREF
  _BYTE v181[56]; // [rsp+130h] [rbp-2C8h] BYREF
  _QWORD v182[3]; // [rsp+168h] [rbp-290h] BYREF
  char v183; // [rsp+180h] [rbp-278h]
  _BYTE v184[32]; // [rsp+188h] [rbp-270h] BYREF
  _BYTE v185[32]; // [rsp+1A8h] [rbp-250h] BYREF
  _BYTE Src[40]; // [rsp+1C8h] [rbp-230h] BYREF
  int v187[108]; // [rsp+1F0h] [rbp-208h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v179 = a4;
  v8 = a1;
  v178 = a1;
  v9 = (_OWORD *)a6;
  v169 = (__int128 *)a6;
  v173 = a1;
  v165 = a3;
  v10 = 1;
  v172 = 1;
  v182[1] = &v165;
  v182[2] = &v172;
  v183 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480857>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60480857>::GetImpl'::`2'::impl)
    && !v8[8] )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl'::`2'::impl) )
      v172 = 3;
    goto LABEL_5;
  }
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>>((struct wil::details::IFailureCallback *)v181);
  inverted::CursorLogger::CursorLogger((inverted::CursorLogger *)v187);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
  {
    *(_OWORD *)Buf1 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64 *))(*v165 + 264))(v165);
    inverted::CursorLogger::LogBegin((int)v187, (int)L"Semantic", a2, *(_QWORD *)a4, a6, Buf1);
  }
  else
  {
    inverted::CursorLogBegin((unsigned int)L"Semantic", a2, *(_QWORD *)a4, a6);
  }
  *((_DWORD *)v8 + 66) = a5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59871929>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59871929>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v14) = 1;
    (*(void (__fastcall **)(__int64 *, __int64))(*v165 + 232))(v165, v14);
  }
  tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(
    &v170,
    v182);
  v167 = (std::_Ref_count_base *)(v8 + 29);
  v15 = v170;
  std::wstring::operator=(v170 + 34, v8 + 29);
  v15[40] = v8[8];
  *((_BYTE *)v15 + 360) = 0;
  v166 = v8 + 26;
  v16 = inverted::PidFilter_to_csvString(Src);
  std::string::operator=(v15 + 41, v16);
  std::string::_Tidy_deallocate(Src);
  v17 = 1;
  v18 = (std::_Ref_count_base ***)(v8 + 6);
  v171 = v8 + 6;
  if ( (unsigned __int64)v8[9] <= 7 )
  {
    v19 = v8 + 6;
    v21 = v8 + 6;
    v20 = v8 + 6;
  }
  else
  {
    v19 = *v18;
    v20 = *v18;
    v21 = *v18;
  }
  v22 = (std::_Ref_count_base **)((char *)v20 + 2 * (_QWORD)v8[8]);
  if ( v19 != v22 )
  {
    do
    {
      v23 = v17 + 1;
      if ( *(_WORD *)v21 != 32 )
        v23 = v17;
      v17 = v23;
      v21 = (std::_Ref_count_base **)((char *)v21 + 2);
    }
    while ( v21 != v22 );
  }
  v15[39] = (std::_Ref_count_base *)v17;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl,
                          v21) )
    *((_BYTE *)v15 + 364) = (*((unsigned int (__fastcall **)(std::_Ref_count_base **))*v8 + 11))(v8) == 2;
  tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(&v170);
  LOBYTE(v10) = 0;
  v164 = v10;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53998201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53998201>::GetImpl'::`2'::impl) )
  {
    v24 = (const wchar_t *)(v8 + 36);
    if ( (unsigned __int64)v8[39] > 7 )
      v24 = *(const wchar_t **)v24;
    v10 = wcscmp_0(v24, L"CONVEXCOMBINATION") == 0;
    v164 = v10;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54887487>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54887487>::GetImpl'::`2'::impl) )
    v26 = (*(__int64 (__fastcall **)(__int64 *))(*v165 + 208))(v165);
  else
    v26 = 0;
  v168 = v26;
  v174[0] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl,
                          v25) )
  {
    v170 = (std::_Ref_count_base **)v182[0];
    if ( v182[0] )
      _InterlockedIncrement((volatile signed __int32 *)(v182[0] + 392LL));
    wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::operator=(
      v174,
      &v170);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>(&v170);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighUserImpact_BugFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HighUserImpact_BugFix>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59294866>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59294866>::GetImpl'::`2'::impl) )
    {
      i = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) == 0;
      v44 = *(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **))(*v165 + 96);
      if ( i )
      {
        v55 = v44(v165, Buf1);
        v56 = *(_QWORD *)v55;
        v57 = *(void (__fastcall **)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, __int64, std::_Ref_count_base **, GUID *, GUID *))(**(_QWORD **)v55 + 296LL);
        v173 = (std::_Ref_count_base **)&v176;
        v58 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v165 + 200))(v165, &v176);
        v59 = *(_QWORD *)(*(_QWORD *)v179 + 200LL);
        *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, Src);
        v60 = to_utf8(v184, v175);
        *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, v180);
        v61 = to_utf8(v185, v175);
        v62 = v8 + 43;
        v170 = v62;
        v57(v56, v61, v60, v166, v62, v178 + 47, v168, v164, v174, v59, v58, v178 + 46, &GUID_NULL, &GUID_NULL);
        std::string::_Tidy_deallocate(v185);
        std::string::_Tidy_deallocate(v184);
        v54 = Buf1[1];
        if ( !Buf1[1] )
        {
          v170 = v62;
          goto LABEL_53;
        }
        goto LABEL_50;
      }
      v45 = v44(v165, Buf1);
      v46 = *(_QWORD *)v45;
      v47 = *(void (__fastcall **)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, __int64, std::_Ref_count_base **, __int64, __int64))(**(_QWORD **)v45 + 296LL);
      v48 = (*(__int64 (__fastcall **)(__int64 *))(*v165 + 264))(v165);
      v49 = (*(__int64 (__fastcall **)(__int64 *))(*v165 + 248))(v165);
      v173 = (std::_Ref_count_base **)&v176;
      v50 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v165 + 200))(v165, &v176);
      v51 = *(_QWORD *)(*(_QWORD *)v179 + 200LL);
      *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v171, Src);
      v52 = to_utf8(v184, v175);
      *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v167, v180);
      v53 = to_utf8(v185, v175);
      v170 = v178 + 43;
      v47(v46, v53, v52, v166, v178 + 43, v178 + 47, v168, v164, v174, v51, v50, v178 + 46, v49, v48);
      std::string::_Tidy_deallocate(v185);
      std::string::_Tidy_deallocate(v184);
      v54 = Buf1[1];
    }
    else
    {
      i = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) == 0;
      v63 = *(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **))(*v165 + 96);
      if ( i )
      {
        v72 = v63(v165, v175);
        v73 = *(_QWORD *)v72;
        v74 = *(void (__fastcall **)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, GUID *, GUID *))(**(_QWORD **)v72 + 296LL);
        v173 = Buf1;
        *(_OWORD *)Buf1 = 0;
        v75 = *(_QWORD *)(*(_QWORD *)v179 + 200LL);
        v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, Src);
        v76 = to_utf8(v184, &v176);
        v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, v180);
        v77 = to_utf8(v185, &v176);
        v43 = v8 + 43;
        v74(v73, v77, v76, v8 + 26, v8 + 43, v8 + 47, v168, v164, v174, v75, Buf1, v8 + 46, &GUID_NULL, &GUID_NULL);
        std::string::_Tidy_deallocate(v185);
        std::string::_Tidy_deallocate(v184);
        if ( v175[1] )
          std::_Ref_count_base::_Decref(v175[1]);
        goto LABEL_58;
      }
      v64 = v63(v165, v175);
      v65 = *(_QWORD *)v64;
      v66 = *(void (__fastcall **)(__int64, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, __int64, __int64))(**(_QWORD **)v64 + 296LL);
      v67 = (*(__int64 (__fastcall **)(__int64 *))(*v165 + 264))(v165);
      v68 = (*(__int64 (__fastcall **)(__int64 *))(*v165 + 248))(v165);
      v173 = Buf1;
      *(_OWORD *)Buf1 = 0;
      v69 = *(_QWORD *)(*(_QWORD *)v179 + 200LL);
      v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v171, Src);
      v70 = to_utf8(v184, &v176);
      v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v167, v180);
      v71 = to_utf8(v185, &v176);
      v170 = v178 + 43;
      v66(v65, v71, v70, v166, v178 + 43, v178 + 47, v168, v164, v174, v69, Buf1, v178 + 46, v68, v67);
      std::string::_Tidy_deallocate(v185);
      std::string::_Tidy_deallocate(v184);
      v54 = v175[1];
    }
    if ( !v54 )
    {
LABEL_53:
      v43 = v170;
      v8 = v178;
LABEL_58:
      v9 = v169;
      goto LABEL_190;
    }
LABEL_50:
    std::_Ref_count_base::_Decref(v54);
    goto LABEL_53;
  }
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59294866>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59294866>::GetImpl'::`2'::impl) )
    {
      i = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) == 0;
      v27 = *(__int64 (__fastcall **)(__int64 *, __int128 *))(*v165 + 96);
      if ( !i )
      {
        v169 = *(__int128 **)v27(v165, &v176);
        v178 = *(std::_Ref_count_base ***)(*(_QWORD *)v169 + 296LL);
        v167 = (std::_Ref_count_base *)(*(__int64 (__fastcall **)(__int64 *))(*v165 + 264))(v165);
        v171 = (std::_Ref_count_base **)(*(__int64 (__fastcall **)(__int64 *))(*v165 + 248))(v165);
        v170 = Buf1;
        v166 = (std::_Ref_count_base **)(*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **))(*v165 + 200))(
                                          v165,
                                          Buf1);
        v28 = *(_QWORD *)(*(_QWORD *)a4 + 200LL);
        *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, v180);
        v29 = to_utf8(v185, v175);
        *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, Src);
        v30 = to_utf8(v184, v175);
        v170 = v8 + 43;
        ((void (__fastcall *)(__int128 *, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base *))v178)(
          v169,
          v30,
          v29,
          v8 + 26,
          v8 + 43,
          v8 + 47,
          v26,
          v10,
          v174,
          v28,
          v166,
          v8 + 46,
          v171,
          v167);
        std::string::_Tidy_deallocate(v184);
        std::string::_Tidy_deallocate(v185);
        v31 = (std::_Ref_count_base *)*((_QWORD *)&v176 + 1);
        goto LABEL_40;
      }
      v171 = *(std::_Ref_count_base ***)v27(v165, (__int128 *)Buf1);
      v166 = (std::_Ref_count_base **)*((_QWORD *)*v171 + 37);
      v169 = &v176;
      v167 = (std::_Ref_count_base *)(*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v165 + 200))(v165, &v176);
      v32 = *(_QWORD *)(*(_QWORD *)a4 + 200LL);
      *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, Src);
      v33 = to_utf8(v184, v175);
      *(_OWORD *)v175 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, v180);
      v34 = to_utf8(v185, v175);
      v35 = v8 + 43;
      v170 = v8 + 43;
      ((void (__fastcall *)(std::_Ref_count_base **, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base *, std::_Ref_count_base **, GUID *, GUID *))v166)(
        v171,
        v34,
        v33,
        v8 + 26,
        v8 + 43,
        v8 + 47,
        v168,
        v10,
        v174,
        v32,
        v167,
        v8 + 46,
        &GUID_NULL,
        &GUID_NULL);
      std::string::_Tidy_deallocate(v185);
      std::string::_Tidy_deallocate(v184);
      v31 = Buf1[1];
    }
    else
    {
      i = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl'::`2'::impl) == 0;
      v36 = *(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **))(*v165 + 96);
      if ( !i )
      {
        v166 = *(std::_Ref_count_base ***)v36(v165, v175);
        v169 = (__int128 *)*((_QWORD *)*v166 + 37);
        v167 = (std::_Ref_count_base *)(*(__int64 (__fastcall **)(__int64 *))(*v165 + 264))(v165);
        v171 = (std::_Ref_count_base **)(*(__int64 (__fastcall **)(__int64 *))(*v165 + 248))(v165);
        v178 = Buf1;
        *(_OWORD *)Buf1 = 0;
        v37 = *(_QWORD *)(*(_QWORD *)a4 + 200LL);
        v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, Src);
        v38 = to_utf8(v184, &v176);
        v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, v180);
        v39 = to_utf8(v185, &v176);
        v170 = v8 + 43;
        ((void (__fastcall *)(std::_Ref_count_base **, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base *))v169)(
          v166,
          v39,
          v38,
          v8 + 26,
          v8 + 43,
          v8 + 47,
          v26,
          v10,
          v174,
          v37,
          Buf1,
          v8 + 46,
          v171,
          v167);
        std::string::_Tidy_deallocate(v185);
        std::string::_Tidy_deallocate(v184);
        v31 = v175[1];
LABEL_40:
        if ( !v31 )
        {
LABEL_45:
          v43 = v170;
          goto LABEL_190;
        }
LABEL_41:
        std::_Ref_count_base::_Decref(v31);
        goto LABEL_45;
      }
      v167 = *(std::_Ref_count_base **)v36(v165, v175);
      v171 = *(std::_Ref_count_base ***)(*(_QWORD *)v167 + 296LL);
      v166 = Buf1;
      *(_OWORD *)Buf1 = 0;
      v40 = *(_QWORD *)(*(_QWORD *)a4 + 200LL);
      v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 6, Src);
      v41 = to_utf8(v184, &v176);
      v176 = *(_OWORD *)std::wstring::operator std::wstring_view(v8 + 29, v180);
      v42 = to_utf8(v185, &v176);
      v35 = v8 + 43;
      v170 = v8 + 43;
      ((void (__fastcall *)(std::_Ref_count_base *, __int64, __int64, std::_Ref_count_base **, std::_Ref_count_base **, std::_Ref_count_base **, int, BOOL, _QWORD *, __int64, std::_Ref_count_base **, std::_Ref_count_base **, GUID *, GUID *))v171)(
        v167,
        v42,
        v41,
        v8 + 26,
        v8 + 43,
        v8 + 47,
        v168,
        v10,
        v174,
        v40,
        Buf1,
        v8 + 46,
        &GUID_NULL,
        &GUID_NULL);
      std::string::_Tidy_deallocate(v185);
      std::string::_Tidy_deallocate(v184);
      v31 = v175[1];
    }
    if ( !v31 )
    {
      v170 = v35;
      goto LABEL_45;
    }
    goto LABEL_41;
  }
  catch ( ... )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl'::`2'::impl) )
      v172 = 2;
    if ( v173[43] != v173[44] )
      v173[44] = v173[43];
    tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(
      &v166,
      v182);
    v163 = v166;
    *((_BYTE *)v166 + 361) = 1;
    v163[38] = 0;
    tip2::details::shared_data<0,0,0>::complete_without_lock(v182[0] + 8LL);
    tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(&v166);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>(v174);
    SearchIndexerTelemetry::CursorActivity::~CursorActivity((SearchIndexerTelemetry::CursorActivity *)v187);
    tip2::test_watcher<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_watcher<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(v181);
LABEL_5:
    result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl'::`2'::impl);
    if ( !(_BYTE)result )
      return result;
    v12 = v165;
    v13 = v172;
    goto LABEL_175;
  }
LABEL_190:
  tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(
    &v167,
    v182);
  v78 = v167;
  *((_BYTE *)v167 + 361) = 0;
  *((_QWORD *)v78 + 38) = (v43[1] - *v43) >> 4;
  tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(&v167);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55466686>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55466686>::GetImpl'::`2'::impl) )
  {
    v141 = *v43;
    v142 = v43[1];
    v169 = (__int128 *)v142;
    while ( 1 )
    {
      v171 = (std::_Ref_count_base **)v141;
      if ( v141 == v142 )
      {
        if ( ((_BYTE)v8[33] & 8) != 0 )
        {
          v161 = *(std::_Ref_count_base **)(*(_QWORD *)v179 + 184LL);
          dynamic_sparse_bit<unsigned __int64>::Empty(v8 + 40);
          v8[40] = v161;
          dynamic_sparse_bit<unsigned __int64>::Union(v8 + 40, v9);
        }
        goto LABEL_170;
      }
      v143 = *(_DWORD *)v141;
      v164 = v143;
      v144 = v143 >> *(_DWORD *)(*(_QWORD *)v9 + 20LL);
      if ( v144 < *((_DWORD *)v9 + 2) )
      {
        v146 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v9);
      }
      else
      {
        if ( v144 < *((_DWORD *)v9 + 3) )
        {
          v145 = (std::_Ref_count_base **)(*((_QWORD *)v9 + 2) + 8LL * (v144 - *((_DWORD *)v9 + 2)));
          goto LABEL_149;
        }
        v146 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v9);
      }
      v145 = (std::_Ref_count_base **)v146;
LABEL_149:
      v166 = v145;
      if ( !*v145 )
      {
        v147 = *(unsigned int **)v9;
        v148 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*(_QWORD *)v9 + 48LL));
        v149 = *(_QWORD *)(v148 + 24);
        if ( *(_QWORD *)(v148 + 16) == v149 )
        {
          v150 = *(unsigned int *)(v148 + 8);
          if ( (unsigned int)v150 >= v147[7] )
          {
            v153 = (std::_Ref_count_base *)_aligned_malloc(8LL * v147[7], v147[8]);
            v151 = v153;
            v167 = v153;
            if ( !v153 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v154);
            v155 = *(std::_Ref_count_base ***)(v148 + 48);
            if ( v155 == *(std::_Ref_count_base ***)(v148 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v148 + 40,
                v155,
                &v167);
              v151 = v167;
            }
            else
            {
              *v155 = v153;
              *(_QWORD *)(v148 + 48) += 8LL;
            }
            v156 = v147[6] * ((__int64)(*(_QWORD *)(v148 + 48) - *(_QWORD *)(v148 + 40)) >> 3);
            v173 = (std::_Ref_count_base **)v156;
            v97 = v148 + 16;
            if ( v156 > (__int64)(*(_QWORD *)(v148 + 32) - *(_QWORD *)(v148 + 16)) >> 3 )
            {
              if ( v156 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_180:
                std::vector<ScreenOnMergeEvent::PrePostMergeData>::_Xlength(v97);
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v97, &v173);
            }
            *(_QWORD *)v148 = v151;
            v152 = v147[2];
            v145 = v166;
          }
          else
          {
            v151 = (std::_Ref_count_base *)(*(_QWORD *)v148 + 8 * v150);
            v152 = v150 + v147[2];
          }
          *(_DWORD *)(v148 + 8) = v152;
        }
        else
        {
          v157 = (void **)(v149 - 8);
          v151 = (std::_Ref_count_base *)*v157;
          *(_QWORD *)(v148 + 24) = v157;
        }
        *v145 = v151;
        memset_0(v151, 0, v147[1]);
        v141 = (std::_Ref_count_base *)v171;
        v143 = v164;
        v142 = (std::_Ref_count_base *)v169;
      }
      v158 = *(unsigned int *)(*(_QWORD *)v9 + 16LL) & ((unsigned __int64)v143 >> 6);
      v159 = 1LL << (v143 & 0x3F);
      v160 = *((_QWORD *)*v145 + v158);
      if ( (v160 & v159) == 0 )
        *((_QWORD *)*v145 + v158) = v159 | v160;
      v141 = (std::_Ref_count_base *)((char *)v141 + 16);
    }
  }
  v79 = (*((__int64 (__fastcall **)(std::_Ref_count_base **))*v8 + 11))(v8);
  if ( v79 == 1 )
  {
    v80 = RankingHelpers::PostSupressionSpaceV6Threshold;
  }
  else if ( v79 == 2 )
  {
    v80 = RankingHelpers::PostSupressionFlorenceThreshold;
  }
  else
  {
    v80 = FLOAT_N1_0;
  }
  if ( ((_BYTE)v8[33] & 0x18) == 0 )
  {
    v81 = *v43;
    v82 = v43[1];
    v171 = (std::_Ref_count_base **)v82;
    if ( v81 == v82 )
      goto LABEL_170;
    while ( 1 )
    {
      v83 = *(_DWORD *)v81;
      v164 = v83;
      v84 = v83 >> *(_DWORD *)(*(_QWORD *)v9 + 20LL);
      if ( v84 < *((_DWORD *)v9 + 2) )
        break;
      if ( v84 >= *((_DWORD *)v9 + 3) )
      {
        v86 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v9);
LABEL_72:
        v85 = (std::_Ref_count_base **)v86;
        goto LABEL_73;
      }
      v85 = (std::_Ref_count_base **)(*((_QWORD *)v9 + 2) + 8LL * (v84 - *((_DWORD *)v9 + 2)));
LABEL_73:
      v166 = v85;
      if ( !*v85 )
      {
        v87 = *(unsigned int **)v9;
        v88 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*(_QWORD *)v9 + 48LL));
        v89 = *(_QWORD *)(v88 + 24);
        if ( *(_QWORD *)(v88 + 16) == v89 )
        {
          v90 = *(unsigned int *)(v88 + 8);
          if ( (unsigned int)v90 >= v87[7] )
          {
            v93 = (std::_Ref_count_base *)_aligned_malloc(8LL * v87[7], v87[8]);
            v91 = v93;
            v167 = v93;
            if ( !v93 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v94);
            v95 = *(std::_Ref_count_base ***)(v88 + 48);
            if ( v95 == *(std::_Ref_count_base ***)(v88 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v88 + 40,
                v95,
                &v167);
              v91 = v167;
            }
            else
            {
              *v95 = v93;
              *(_QWORD *)(v88 + 48) += 8LL;
            }
            v96 = v87[6] * ((__int64)(*(_QWORD *)(v88 + 48) - *(_QWORD *)(v88 + 40)) >> 3);
            v173 = (std::_Ref_count_base **)v96;
            v97 = v88 + 16;
            if ( v96 > (__int64)(*(_QWORD *)(v88 + 32) - *(_QWORD *)(v88 + 16)) >> 3 )
            {
              if ( v96 > 0x1FFFFFFFFFFFFFFFLL )
                goto LABEL_180;
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v97, &v173);
            }
            *(_QWORD *)v88 = v91;
            v92 = v87[2];
            v85 = v166;
          }
          else
          {
            v91 = (std::_Ref_count_base *)(*(_QWORD *)v88 + 8 * v90);
            v92 = v90 + v87[2];
          }
          *(_DWORD *)(v88 + 8) = v92;
        }
        else
        {
          v98 = (void **)(v89 - 8);
          v91 = (std::_Ref_count_base *)*v98;
          *(_QWORD *)(v88 + 24) = v98;
        }
        *v85 = v91;
        memset_0(v91, 0, v87[1]);
        v83 = v164;
        v82 = (std::_Ref_count_base *)v171;
      }
      v99 = *(unsigned int *)(*(_QWORD *)v9 + 16LL) & ((unsigned __int64)v83 >> 6);
      v100 = 1LL << (v83 & 0x3F);
      v101 = *((_QWORD *)*v85 + v99);
      if ( (v101 & v100) == 0 )
        *((_QWORD *)*v85 + v99) = v100 | v101;
      v81 = (std::_Ref_count_base *)((char *)v81 + 16);
      if ( v81 == v82 )
        goto LABEL_170;
    }
    v86 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v9);
    goto LABEL_72;
  }
  v102 = (unsigned int **)(v8 + 40);
  v103 = *(std::_Ref_count_base **)(*(_QWORD *)v179 + 184LL);
  dynamic_sparse_bit<unsigned __int64>::Empty(v8 + 40);
  v8[40] = v103;
  v104 = (std::_Ref_count_base **)*v43;
  v171 = (std::_Ref_count_base **)v43[1];
  for ( i = v104 == v171; ; i = v104 == v171 )
  {
    v166 = v104;
    if ( i )
      break;
    v106 = *(_DWORD *)v104;
    v168 = v106;
    v107 = v106 >> *(_DWORD *)(*(_QWORD *)v9 + 20LL);
    if ( v107 < *((_DWORD *)v9 + 2) )
    {
      v108 = (__int128 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v9);
    }
    else if ( v107 >= *((_DWORD *)v9 + 3) )
    {
      v108 = (__int128 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v9);
    }
    else
    {
      v108 = (__int128 *)(*((_QWORD *)v9 + 2) + 8LL * (v107 - *((_DWORD *)v9 + 2)));
    }
    v169 = v108;
    if ( !*(_QWORD *)v108 )
    {
      v109 = *(unsigned int **)v9;
      v110 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*(_QWORD *)v9 + 48LL));
      v111 = *(_QWORD *)(v110 + 24);
      if ( *(_QWORD *)(v110 + 16) == v111 )
      {
        v112 = *(unsigned int *)(v110 + 8);
        if ( (unsigned int)v112 >= v109[7] )
        {
          v113 = (std::_Ref_count_base *)_aligned_malloc(8LL * v109[7], v109[8]);
          v167 = v113;
          if ( !v113 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v115);
          v116 = (_QWORD *)(v110 + 40);
          v117 = *(std::_Ref_count_base ***)(v110 + 48);
          if ( v117 == *(std::_Ref_count_base ***)(v110 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v116,
              v117,
              &v167);
            v113 = v167;
            v116 = (_QWORD *)(v110 + 40);
          }
          else
          {
            *v117 = v113;
            *(_QWORD *)(v110 + 48) += 8LL;
          }
          v118 = v109[6] * ((__int64)(*(_QWORD *)(v110 + 48) - *v116) >> 3);
          v173 = (std::_Ref_count_base **)v118;
          v97 = v110 + 16;
          if ( v118 > (__int64)(*(_QWORD *)(v110 + 32) - *(_QWORD *)(v110 + 16)) >> 3 )
          {
            if ( v118 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_180;
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v97, &v173);
          }
          *(_QWORD *)v110 = v113;
          v114 = v109[2];
        }
        else
        {
          v113 = (std::_Ref_count_base *)(*(_QWORD *)v110 + 8 * v112);
          v114 = v112 + v109[2];
        }
        *(_DWORD *)(v110 + 8) = v114;
      }
      else
      {
        v119 = (void **)(v111 - 8);
        v113 = (std::_Ref_count_base *)*v119;
        *(_QWORD *)(v110 + 24) = v119;
      }
      *(_QWORD *)v169 = v113;
      memset_0(v113, 0, v109[1]);
      v104 = v166;
      v106 = v168;
    }
    v120 = *(unsigned int *)(*(_QWORD *)v9 + 16LL) & ((unsigned __int64)v106 >> 6);
    v121 = 1LL << (v106 & 0x3F);
    v122 = *(_QWORD *)(*(_QWORD *)v169 + 8 * v120);
    if ( (v122 & v121) == 0 )
      *(_QWORD *)(*(_QWORD *)v169 + 8 * v120) = v121 | v122;
    if ( !v164 || *((float *)v104 + 1) >= v80 )
    {
      v123 = *(_DWORD *)v104;
      v168 = v123;
      v124 = v123 >> (*v102)[5];
      v125 = *((_DWORD *)v8 + 82);
      if ( v124 < v125 )
      {
        v126 = (__int128 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v8 + 40);
      }
      else if ( v124 >= *((_DWORD *)v8 + 83) )
      {
        v126 = (__int128 *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v8 + 40);
      }
      else
      {
        v126 = (__int128 *)((char *)v8[42] + 8 * (v124 - v125));
      }
      v169 = v126;
      if ( !*(_QWORD *)v126 )
      {
        v127 = *v102;
        v128 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v102 + 12));
        v129 = *(_QWORD *)(v128 + 24);
        if ( *(_QWORD *)(v128 + 16) == v129 )
        {
          v130 = *(unsigned int *)(v128 + 8);
          if ( (unsigned int)v130 >= v127[7] )
          {
            v131 = (std::_Ref_count_base *)_aligned_malloc(8LL * v127[7], v127[8]);
            v167 = v131;
            if ( !v131 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v133);
            v134 = (_QWORD *)(v128 + 40);
            v135 = *(std::_Ref_count_base ***)(v128 + 48);
            if ( v135 == *(std::_Ref_count_base ***)(v128 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v134,
                v135,
                &v167);
              v131 = v167;
              v134 = (_QWORD *)(v128 + 40);
            }
            else
            {
              *v135 = v131;
              *(_QWORD *)(v128 + 48) += 8LL;
            }
            v136 = v127[6] * ((__int64)(*(_QWORD *)(v128 + 48) - *v134) >> 3);
            v173 = (std::_Ref_count_base **)v136;
            v97 = v128 + 16;
            if ( v136 > (__int64)(*(_QWORD *)(v128 + 32) - *(_QWORD *)(v128 + 16)) >> 3 )
            {
              if ( v136 > 0x1FFFFFFFFFFFFFFFLL )
                goto LABEL_180;
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v97, &v173);
            }
            *(_QWORD *)v128 = v131;
            v132 = v127[2];
          }
          else
          {
            v131 = (std::_Ref_count_base *)(*(_QWORD *)v128 + 8 * v130);
            v132 = v130 + v127[2];
          }
          *(_DWORD *)(v128 + 8) = v132;
        }
        else
        {
          v137 = (void **)(v129 - 8);
          v131 = (std::_Ref_count_base *)*v137;
          *(_QWORD *)(v128 + 24) = v137;
        }
        *(_QWORD *)v169 = v131;
        memset_0(v131, 0, v127[1]);
        v104 = v166;
        v123 = v168;
      }
      v138 = (*v102)[4] & ((unsigned __int64)v123 >> 6);
      v139 = 1LL << (v123 & 0x3F);
      v140 = *(_QWORD *)(*(_QWORD *)v169 + 8 * v138);
      if ( (v140 & v139) == 0 )
        *(_QWORD *)(*(_QWORD *)v169 + 8 * v138) = v139 | v140;
    }
    v104 += 2;
  }
LABEL_170:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl'::`2'::impl) )
    inverted::CursorLogger::LogEnd(v187, L"Semantic", v9);
  else
    inverted::CursorLogEnd(L"Semantic", v9);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v182[0] + 8LL);
  wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>(v174);
  SearchIndexerTelemetry::CursorActivity::~CursorActivity((SearchIndexerTelemetry::CursorActivity *)v187);
  tip2::test_watcher<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_watcher<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(v181);
  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl'::`2'::impl);
  if ( (_BYTE)result )
  {
    v12 = v165;
    v13 = v172;
LABEL_175:
    v162 = *v12;
    v164 = v13;
    return (*(__int64 (__fastcall **)(__int64 *, BOOL *))(v162 + 296))(v12, &v164);
  }
  return result;
}

```

## disassembly

```asm
0x1802423c0  mov     r11, rsp
0x1802423c3  push    rbx
0x1802423c4  push    rsi
0x1802423c5  push    rdi
0x1802423c6  push    r12
0x1802423c8  push    r13
0x1802423ca  push    r14
0x1802423cc  push    r15
0x1802423ce  sub     rsp, 3C0h
0x1802423d5  movaps  xmmword ptr [r11-48h], xmm6
0x1802423da  mov     rax, cs:__security_cookie
0x1802423e1  xor     rax, rsp
0x1802423e4  mov     [rsp+3F8h+var_58], rax
0x1802423ec  mov     r14, r9
0x1802423ef  mov     [rsp+3F8h+var_2E0], r9
0x1802423f7  mov     rbx, rdx
0x1802423fa  mov     r12, rcx
0x1802423fd  mov     [rsp+3F8h+var_2E8], rcx
0x180242405  mov     rsi, [rsp+3F8h+arg_28]
0x18024240d  mov     [rsp+3F8h+var_350], rsi
0x180242415  mov     [rsp+3F8h+var_330], rcx
0x18024241d  mov     [r11-370h], r8
0x180242424  mov     edi, 1
0x180242429  mov     [rsp+3F8h+var_338], edi
0x180242430  lea     rax, [r11-370h]
0x180242437  mov     [r11-288h], rax
0x18024243e  lea     rax, [r11-338h]
0x180242445  mov     [r11-280h], rax
0x18024244c  mov     [rsp+3F8h+var_278], dil
0x180242454  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60480857@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60480857@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480857> `wil::Feature<__WilFeatureTraits_Feature_60480857>::GetImpl(void)'::`2'::impl
0x18024245b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60480857@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60480857>::__private_IsEnabled(void)
0x180242460  xor     r13d, r13d
0x180242463  test    al, al
0x180242465  jz      short loc_1802424B1
0x180242467  cmp     [r12+40h], r13
0x18024246c  jnz     short loc_1802424B1
0x18024246e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60934957@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60934957@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957> `wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl(void)'::`2'::impl
0x180242475  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60934957@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(void)
0x18024247a  test    al, al
0x18024247c  jz      short loc_180242489
0x18024247e  mov     [rsp+3F8h+var_338], 3
0x180242489  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60934957@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60934957@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957> `wil::Feature<__WilFeatureTraits_Feature_60934957>::GetImpl(void)'::`2'::impl
0x180242490  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60934957@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60934957>::__private_IsEnabled(void)
0x180242495  test    al, al
0x180242497  jz      loc_180243EA2
0x18024249d  mov     rcx, [rsp+3F8h+var_370]
0x1802424a5  mov     edx, [rsp+3F8h+var_338]
0x1802424ac  jmp     loc_180243E83
0x1802424b1  lea     rcx, [rsp+3F8h+var_2C8]; struct wil::details::IFailureCallback *
0x1802424b9  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1802424be  nop
0x1802424bf  lea     rcx, [rsp+3F8h+var_208]; this
0x1802424c7  call    ??0CursorLogger@inverted@@QEAA@XZ; inverted::CursorLogger::CursorLogger(void)
0x1802424cc  nop
0x1802424cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59422362@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362> `wil::Feature<__WilFeatureTraits_Feature_59422362>::GetImpl(void)'::`2'::impl
0x1802424d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59422362@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59422362>::__private_IsEnabled(void)
0x1802424d9  test    al, al
0x1802424db  jz      short loc_18024252E
0x1802424dd  mov     rcx, [rsp+3F8h+var_370]
0x1802424e5  mov     rax, [rcx]
0x1802424e8  mov     rax, [rax+108h]
0x1802424ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802424f4  movups  xmm0, xmmword ptr [rax]
0x1802424f7  movdqu  xmmword ptr [rsp+3F8h+var_2F8], xmm0
0x180242500  lea     rax, [rsp+3F8h+var_2F8]
0x180242508  mov     [rsp+3F8h+Buf1], rax; Buf1
0x18024250d  mov     [rsp+3F8h+var_3D8], rsi; __int64
0x180242512  mov     r9, [r14]; int
0x180242515  mov     r8, rbx; int
0x180242518  lea     rdx, aSemantic_0; "Semantic"
0x18024251f  lea     rcx, [rsp+3F8h+var_208]; int
0x180242527  call    ?LogBegin@CursorLogger@inverted@@QEAAXPEB_WAEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@AEBVCScanRestrictions@2@AEBU?$dynamic_sparse_bit@_K@@U_GUID@@@Z; inverted::CursorLogger::LogBegin(wchar_t const *,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::CScanRestrictions const &,dynamic_sparse_bit<unsigned __int64> const &,_GUID)
0x18024252c  jmp     short loc_180242543
0x18024252e  mov     r9, rsi
0x180242531  mov     r8, [r14]
0x180242534  mov     rdx, rbx
0x180242537  lea     rcx, aSemantic_0; "Semantic"
0x18024253e  call    ?CursorLogBegin@inverted@@YAXPEB_WAEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@AEBVCScanRestrictions@1@AEBU?$dynamic_sparse_bit@_K@@@Z; inverted::CursorLogBegin(wchar_t const *,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::CScanRestrictions const &,dynamic_sparse_bit<unsigned __int64> const &)
0x180242543  mov     eax, [rsp+3F8h+arg_20]
0x18024254a  mov     [r12+108h], eax
0x180242552  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59871929@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59871929@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59871929> `wil::Feature<__WilFeatureTraits_Feature_59871929>::GetImpl(void)'::`2'::impl
0x180242559  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59871929@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59871929>::__private_IsEnabled(void)
0x18024255e  test    al, al
0x180242560  jz      short loc_18024257C
0x180242562  mov     rcx, [rsp+3F8h+var_370]
0x18024256a  mov     rax, [rcx]
0x18024256d  mov     dl, dil
0x180242570  mov     rax, [rax+0E8h]
0x180242577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024257c  lea     rdx, [rsp+3F8h+var_290]
0x180242584  lea     rcx, [rsp+3F8h+var_348]
0x18024258c  call    ??0?$test_data_control@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy> const &)
0x180242591  nop
0x180242592  lea     rax, [r12+0E8h]
0x18024259a  mov     [rsp+3F8h+var_360], rax
0x1802425a2  mov     rbx, [rsp+3F8h+var_348]
0x1802425aa  lea     rcx, [rbx+110h]
0x1802425b1  mov     rdx, rax
0x1802425b4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1802425b9  mov     rax, [r12+40h]
0x1802425be  mov     [rbx+140h], rax
0x1802425c5  mov     [rbx+168h], r13b
0x1802425cc  lea     rax, [r12+0D0h]
0x1802425d4  mov     [rsp+3F8h+var_368], rax
0x1802425dc  mov     rdx, rax
0x1802425df  lea     rcx, [rsp+3F8h+Src]; Src
0x1802425e7  call    ?PidFilter_to_csvString@inverted@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBU?$dynamic_sparse_bit@_K@@@Z; inverted::PidFilter_to_csvString(dynamic_sparse_bit<unsigned __int64> const &)
0x1802425ec  lea     rcx, [rbx+148h]
0x1802425f3  mov     rdx, rax
0x1802425f6  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1802425fb  lea     rcx, [rsp+3F8h+Src]
0x180242603  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180242608  mov     rcx, rdi
0x18024260b  lea     r15, [r12+30h]
0x180242610  mov     [rsp+3F8h+var_340], r15
0x180242618  cmp     qword ptr [r15+18h], 7
0x18024261d  jbe     short loc_18024262A
0x18024261f  mov     r8, [r15]
0x180242622  mov     r9, r8
0x180242625  mov     rdx, r8
0x180242628  jmp     short loc_180242633
0x18024262a  mov     r8, r15
0x18024262d  mov     rdx, r15
0x180242630  mov     r9, r15
0x180242633  mov     rax, [r15+10h]
0x180242637  lea     r10, [r9+rax*2]
0x18024263b  cmp     r8, r10
0x18024263e  jz      short loc_180242658
0x180242640  lea     rax, [rcx+1]
0x180242644  cmp     word ptr [rdx], 20h ; ' '
0x180242648  cmovnz  rax, rcx
0x18024264c  mov     rcx, rax
0x18024264f  add     rdx, 2
0x180242653  cmp     rdx, r10
0x180242656  jnz     short loc_180242640
0x180242658  mov     [rbx+138h], rcx
0x18024265f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180242666  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18024266b  test    al, al
0x18024266d  jz      short loc_18024268B
0x18024266f  mov     rax, [r12]
0x180242673  mov     rcx, r12
0x180242676  mov     rax, [rax+58h]
0x18024267a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024267f  cmp     eax, 2
0x180242682  setz    al
0x180242685  mov     [rbx+16Ch], al
0x18024268b  lea     rcx, [rsp+3F8h+var_348]
0x180242693  call    ??1?$test_data_control@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>::~test_data_control<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>>(void)
0x180242698  mov     dil, r13b
0x18024269b  mov     [rsp+3F8h+var_378], edi
0x1802426a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53998201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53998201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53998201> `wil::Feature<__WilFeatureTraits_Feature_53998201>::GetImpl(void)'::`2'::impl
0x1802426a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53998201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53998201>::__private_IsEnabled(void)
0x1802426ae  test    al, al
0x1802426b0  jz      short loc_1802426E5
0x1802426b2  lea     rcx, [r12+120h]
0x1802426ba  cmp     qword ptr [rcx+18h], 7
0x1802426bf  jbe     short loc_1802426C4
0x1802426c1  mov     rcx, [rcx]; String1
0x1802426c4  lea     rdx, aConvexcombinat; "CONVEXCOMBINATION"
0x1802426cb  call    wcscmp_0
0x1802426d0  movzx   edi, dil
0x1802426d4  test    eax, eax
0x1802426d6  mov     eax, 1
0x1802426db  cmovz   edi, eax
0x1802426de  mov     [rsp+3F8h+var_378], edi
0x1802426e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54887487@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54887487@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54887487> `wil::Feature<__WilFeatureTraits_Feature_54887487>::GetImpl(void)'::`2'::impl
0x1802426ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54887487@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54887487>::__private_IsEnabled(void)
0x1802426f1  test    al, al
0x1802426f3  jz      short loc_180242710
0x1802426f5  mov     rcx, [rsp+3F8h+var_370]
0x1802426fd  mov     rax, [rcx]
0x180242700  mov     rax, [rax+0D0h]
0x180242707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024270c  mov     ebx, eax
0x18024270e  jmp     short loc_180242713
0x180242710  mov     ebx, r13d
0x180242713  mov     [rsp+3F8h+var_358], ebx
0x18024271a  mov     [rsp+3F8h+var_328], r13
0x180242722  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180242729  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18024272e  test    al, al
0x180242730  jz      short loc_180242770
0x180242732  mov     rax, [rsp+3F8h+var_290]
0x18024273a  mov     [rsp+3F8h+var_348], rax
0x180242742  test    rax, rax
0x180242745  jz      short loc_18024274E
0x180242747  lock inc dword ptr [rax+188h]
0x18024274e  lea     rdx, [rsp+3F8h+var_348]
0x180242756  lea     rcx, [rsp+3F8h+var_328]
0x18024275e  call    ??4?$com_ptr_t@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy> &&)
0x180242763  lea     rcx, [rsp+3F8h+var_348]
0x18024276b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SemanticQueryTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SemanticQueryTest,_tip_SemanticQueryTest>,wil::err_returncode_policy>(void)
0x180242770  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HighUserImpact_BugFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HighUserImpact_BugFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighUserImpact_BugFix> `wil::Feature<__WilFeatureTraits_Feature_HighUserImpact_BugFix>::GetImpl(void)'::`2'::impl
0x180242777  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HighUserImpact_BugFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighUserImpact_BugFix>::__private_IsEnabled(void)
0x18024277c  test    al, al
0x18024277e  jz      loc_180242EC2
0x180242784  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59294866@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59294866@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59294866> `wil::Feature<__WilFeatureTraits_Feature_59294866>::GetImpl(void)'::`2'::impl
0x18024278b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59294866@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59294866>::__private_IsEnabled(void)
0x180242790  test    al, al
0x180242792  jz      loc_180242B21
0x180242798  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57994465@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465> `wil::Feature<__WilFeatureTraits_Feature_57994465>::GetImpl(void)'::`2'::impl
0x18024279f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57994465@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57994465>::__private_IsEnabled(void)
0x1802427a4  mov     rcx, [rsp+3F8h+var_370]
0x1802427ac  test    al, al
0x1802427ae  mov     rax, [rcx]
0x1802427b1  mov     rax, [rax+60h]
0x1802427b5  jz      loc_18024298E
0x1802427bb  lea     rdx, [rsp+3F8h+var_308]
0x1802427c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802427c8  nop
0x1802427c9  mov     rax, [rax]
0x1802427cc  mov     [rsp+3F8h+var_350], rax
0x1802427d4  mov     rax, [rax]
0x1802427d7  mov     rax, [rax+128h]
0x1802427de  mov     [rsp+3F8h+var_2E8], rax
0x1802427e6  mov     rcx, [rsp+3F8h+var_370]
0x1802427ee  mov     rax, [rcx]
0x1802427f1  mov     rax, [rax+108h]
0x1802427f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802427fd  mov     [rsp+3F8h+var_360], rax
0x180242805  mov     rcx, [rsp+3F8h+var_370]
0x18024280d  mov     rdx, [rcx]
0x180242810  mov     rax, [rdx+0F8h]
0x180242817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024281c  mov     [rsp+3F8h+var_340], rax
0x180242824  lea     rax, [rsp+3F8h+var_2F8]
0x18024282c  mov     [rsp+3F8h+var_348], rax
0x180242834  mov     rcx, [rsp+3F8h+var_370]
0x18024283c  mov     rdx, [rcx]
0x18024283f  mov     rax, [rdx+0C8h]
0x180242846  lea     rdx, [rsp+3F8h+var_2F8]
0x18024284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180242853  mov     [rsp+3F8h+var_368], rax
0x18024285b  mov     rdx, [r14]
0x18024285e  mov     r14, [rdx+0C8h]
0x180242865  lea     rdx, [rsp+3F8h+var_2D8]
0x18024286d  mov     rcx, r15
0x180242870  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180242875  movups  xmm0, xmmword ptr [rax]
0x180242878  movdqu  xmmword ptr [rsp+3F8h+var_318], xmm0
0x180242881  lea     rdx, [rsp+3F8h+var_318]
0x180242889  lea     rcx, [rsp+3F8h+var_250]
0x180242891  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x180242896  mov     r15, rax
0x180242899  lea     rdx, [rsp+3F8h+Src]
0x1802428a1  lea     rcx, [r12+0E8h]
0x1802428a9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802428ae  movups  xmm0, xmmword ptr [rax]
0x1802428b1  movdqu  xmmword ptr [rsp+3F8h+var_318], xmm0
0x1802428ba  lea     rdx, [rsp+3F8h+var_318]
0x1802428c2  lea     rcx, [rsp+3F8h+var_270]
0x1802428ca  call    ?to_utf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_utf8(std::wstring_view)
0x1802428cf  nop
0x1802428d0  lea     r10, [r12+158h]
0x1802428d8  mov     [rsp+3F8h+var_348], r10
0x1802428e0  lea     rdx, [r12+170h]
0x1802428e8  lea     r8, [r12+178h]
0x1802428f0  mov     rcx, [rsp+3F8h+var_360]
0x1802428f8  mov     [rsp+3F8h+var_390], rcx
0x1802428fd  mov     rcx, [rsp+3F8h+var_340]
0x180242905  mov     [rsp+3F8h+var_398], rcx
0x18024290a  mov     [rsp+3F8h+var_3A0], rdx
0x18024290f  mov     rcx, [rsp+3F8h+var_368]
0x180242917  mov     [rsp+3F8h+var_3A8], rcx
0x18024291c  mov     [rsp+3F8h+var_3B0], r14
0x180242921  lea     rcx, [rsp+3F8h+var_328]
0x180242929  mov     [rsp+3F8h+var_3B8], rcx
0x18024292e  mov     [rsp+3F8h+var_3C0], dil
0x180242933  mov     [rsp+3F8h+var_3C8], ebx
0x180242937  mov     [rsp+3F8h+Buf1], r8
0x18024293c  mov     [rsp+3F8h+var_3D8], r10
0x180242941  lea     r9, [r12+0D0h]
0x180242949  mov     r8, r15
0x18024294c  mov     rdx, rax
0x18024294f  mov     rcx, [rsp+3F8h+var_350]
0x180242957  mov     rax, [rsp+3F8h+var_2E8]
0x18024295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180242964  nop
0x180242965  lea     rcx, [rsp+3F8h+var_270]
0x18024296d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180242972  nop
0x180242973  lea     rcx, [rsp+3F8h+var_250]
0x18024297b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180242980  nop
0x180242981  mov     rcx, qword ptr [rsp+3F8h+var_308+8]
0x180242989  jmp     loc_180242CF7
0x18024298e  lea     rdx, [rsp+3F8h+var_2F8]
0x180242996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024299b  nop
0x18024299c  mov     rax, [rax]
0x18024299f  mov     [rsp+3F8h+var_340], rax
0x1802429a7  mov     rax, [rax]
0x1802429aa  mov     rax, [rax+128h]
0x1802429b1  mov     [rsp+3F8h+var_368], rax
0x1802429b9  lea     rcx, [rsp+3F8h+var_308]
0x1802429c1  mov     [rsp+3F8h+var_350], rcx
0x1802429c9  mov     rcx, [rsp+3F8h+var_370]
0x1802429d1  mov     rax, [rcx]
0x1802429d4  lea     rdx, [rsp+3F8h+var_308]
  ... truncated ...
```

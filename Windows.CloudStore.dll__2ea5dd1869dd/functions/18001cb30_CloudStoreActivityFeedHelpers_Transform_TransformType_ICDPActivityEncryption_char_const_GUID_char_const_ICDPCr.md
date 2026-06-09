# CloudStoreActivityFeedHelpers::Transform(TransformType,ICDPActivityEncryption *,char const *,_GUID,char const *,ICDPCrossPlatformAppId *,char const *,ICloudStoreActivityFeedData * *)

- ea: `0x18001cb30`
- end: `0x18001e1b3`
- name: `?Transform@CloudStoreActivityFeedHelpers@@UEAAJW4TransformType@@PEAVICDPActivityEncryption@@PEBDU_GUID@@2PEAVICDPCrossPlatformAppId@@2PEAPEAUICloudStoreActivityFeedData@@@Z`
- size: `5763`
- prototype: ``
- caller_count: `0`
- callee_count: `68`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000dfe4`
- `0x180016cf4`
- `0x180016f88`
- `0x180019720`
- `0x180019a40`
- `0x18001c620`
- `0x18001cb30`
- `0x18001e1c0`
- `0x18001e1d8`
- `0x18001e280`
- `0x18001e290`
- `0x18001e394`
- `0x18001e5a8`
- `0x1800219e0`
- `0x180021ae0`
- `0x180021b10`
- `0x180021f40`
- `0x18002231c`
- `0x180023530`
- `0x180023fd4`
- `0x180024e90`
- `0x1800250e0`
- `0x180025508`
- `0x18002a8a0`
- `0x18002b464`
- `0x18002c020`
- `0x18002e010`
- `0x180030c64`
- `0x18003f364`
- `0x180047904`
- `0x18004f6e0`
- `0x180050d44`
- `0x18005e384`
- `0x18005edd0`
- `0x18006767c`
- `0x180067f60`
- `0x1800687b8`
- `0x1800689ac`
- `0x1800689dc`
- `0x180068ab8`
- `0x1800693bc`
- `0x18007d350`
- `0x180091b34`
- `0x180092a34`
- `0x180094d30`
- `0x180096880`
- `0x18009bd10`
- `0x1800adaa4`
- `0x1800ae89c`
- `0x1800b35cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001cd71`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001cd71`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ded7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df03`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df11`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ded7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df03`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df11`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001ce80`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001ce80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de89`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall CloudStoreActivityFeedHelpers::Transform(
        CloudStoreActivityFeedHelpers *a1,
        unsigned int a2,
        std::_Ref_count_base *a3,
        void *a4,
        IID *a5,
        _BYTE *a6,
        __int64 a7,
        _BYTE *Src,
        _QWORD *a9)
{
  __int64 v9; // rdx
  _QWORD *TypeNameFromAppActivityId; // rbx
  __int64 v11; // r8
  _DWORD *v12; // r13
  int v13; // eax
  __int64 v14; // rax
  _QWORD *v15; // rdi
  int v16; // ecx
  _DWORD *v17; // r14
  _QWORD *v18; // r8
  void *v19; // rcx
  const struct std::nothrow_t *v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  const char *v23; // r9
  size_t v24; // rbx
  __int64 v25; // rsi
  void *v26; // rdi
  void *v27; // rcx
  const struct std::nothrow_t *v28; // rdx
  HRESULT v29; // eax
  size_t v30; // rbx
  __int64 v31; // rsi
  void *v32; // rdi
  LPOLESTR v33; // rsi
  unsigned __int64 v34; // rbx
  __int64 v35; // r14
  IID *v36; // rdi
  size_t v37; // rbx
  int v38; // eax
  IID **v39; // r8
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  void **v43; // rax
  _QWORD *v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rdi
  char v47; // bl
  void *v48; // rcx
  const struct std::nothrow_t *v49; // rdx
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  void *v52; // rcx
  const struct std::nothrow_t *v53; // rdx
  const char *v54; // r9
  void *v55; // rcx
  const struct std::nothrow_t *v56; // rdx
  void **v57; // rcx
  char *v58; // rsi
  void **v59; // rdi
  __int64 v60; // rdx
  __int64 v61; // rcx
  int v62; // r9d
  size_t v63; // rbx
  void *v64; // r15
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // eax
  void *v68; // rbx
  IID **v69; // r8
  __int64 v70; // rax
  _QWORD *v71; // rbx
  int v72; // eax
  _QWORD *v73; // r8
  __int64 v74; // rsi
  IID *v75; // rdi
  __int64 v76; // rdx
  __int64 v77; // rcx
  _QWORD *EncryptedTypeName; // rax
  size_t v79; // rsi
  size_t v80; // r15
  void **v81; // rcx
  void *v82; // rdi
  unsigned __int64 v83; // r14
  size_t v84; // r8
  int v85; // eax
  char v86; // si
  const struct std::nothrow_t *v87; // rdx
  const struct std::nothrow_t *v88; // rdx
  IID *v89; // rcx
  IID *v90; // rbx
  _DWORD *v91; // rax
  __int64 v92; // rax
  void *v93; // r8
  void *v94; // r9
  unsigned __int64 v95; // rax
  size_t v96; // r10
  __int64 v97; // rcx
  __int64 v98; // r11
  __int64 v99; // rbx
  _QWORD *CloudStoreActivityFeed; // rax
  _DWORD *v101; // rbx
  const char *v102; // r9
  __int64 result; // rax
  char v104; // di
  const struct walkable::structure *v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 versioned; // rdx
  __int64 *v111; // rax
  __int64 v112; // rbx
  size_t v113; // rbx
  __int64 v114; // rdi
  __int64 v115; // rax
  int v116; // eax
  int v117; // ebx
  int EncryptedTypeSchema; // eax
  int v119; // r9d
  __int64 *v120; // rax
  __int64 v121; // rbx
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rcx
  int Size; // [rsp+20h] [rbp-2F8h]
  int Sizea; // [rsp+20h] [rbp-2F8h]
  char v127[8]; // [rsp+30h] [rbp-2E8h] BYREF
  void *v128; // [rsp+38h] [rbp-2E0h] BYREF
  void *v129; // [rsp+40h] [rbp-2D8h] BYREF
  _DWORD *v130; // [rsp+48h] [rbp-2D0h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-2C8h] BYREF
  void *v132; // [rsp+58h] [rbp-2C0h] BYREF
  unsigned int v133; // [rsp+60h] [rbp-2B8h]
  _QWORD *v134; // [rsp+68h] [rbp-2B0h]
  _BYTE *v135; // [rsp+70h] [rbp-2A8h] BYREF
  std::_Ref_count_base *v136[2]; // [rsp+78h] [rbp-2A0h] BYREF
  __int128 v137; // [rsp+88h] [rbp-290h] BYREF
  __int64 v138; // [rsp+98h] [rbp-280h]
  char v139[8]; // [rsp+A0h] [rbp-278h] BYREF
  char v140[8]; // [rsp+A8h] [rbp-270h] BYREF
  int v141; // [rsp+B0h] [rbp-268h]
  void *v142; // [rsp+B8h] [rbp-260h]
  __int64 v143; // [rsp+C0h] [rbp-258h]
  CloudStoreActivityFeedHelpers *v144[2]; // [rsp+C8h] [rbp-250h] BYREF
  void *v145; // [rsp+D8h] [rbp-240h] BYREF
  _QWORD v146[4]; // [rsp+E0h] [rbp-238h] BYREF
  _QWORD v147[2]; // [rsp+100h] [rbp-218h] BYREF
  char v148; // [rsp+110h] [rbp-208h]
  __int64 v149; // [rsp+118h] [rbp-200h]
  char v150[8]; // [rsp+120h] [rbp-1F8h] BYREF
  char v151[32]; // [rsp+128h] [rbp-1F0h] BYREF
  char v152[40]; // [rsp+148h] [rbp-1D0h] BYREF
  IID *rclsid[2]; // [rsp+170h] [rbp-1A8h] BYREF
  unsigned __int64 v154; // [rsp+180h] [rbp-198h]
  unsigned __int64 v155; // [rsp+188h] [rbp-190h]
  void *Buf1[2]; // [rsp+190h] [rbp-188h] BYREF
  size_t v157; // [rsp+1A0h] [rbp-178h]
  unsigned __int64 v158; // [rsp+1A8h] [rbp-170h]
  __int64 v159; // [rsp+1B0h] [rbp-168h]
  __int64 v160; // [rsp+1B8h] [rbp-160h]
  __int64 v161; // [rsp+1C0h] [rbp-158h]
  char v162; // [rsp+1C8h] [rbp-150h]
  void *v163[2]; // [rsp+1D0h] [rbp-148h] BYREF
  __int128 v164; // [rsp+1E0h] [rbp-138h] BYREF
  __int64 v165; // [rsp+1F0h] [rbp-128h]
  __int64 v166; // [rsp+1F8h] [rbp-120h]
  __int64 v167; // [rsp+200h] [rbp-118h]
  void *v168[2]; // [rsp+208h] [rbp-110h] BYREF
  __int128 v169; // [rsp+218h] [rbp-100h]
  void *v170[2]; // [rsp+228h] [rbp-F0h] BYREF
  __int64 v171; // [rsp+238h] [rbp-E0h]
  unsigned __int64 v172; // [rsp+240h] [rbp-D8h]
  char v173; // [rsp+248h] [rbp-D0h]
  _QWORD v174[4]; // [rsp+260h] [rbp-B8h] BYREF
  void *v175[2]; // [rsp+280h] [rbp-98h] BYREF
  __int128 v176; // [rsp+290h] [rbp-88h]
  __int64 v177; // [rsp+2A0h] [rbp-78h]
  __int64 v178; // [rsp+2A8h] [rbp-70h]
  __int64 v179; // [rsp+2B0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  try
  {
    v142 = a4;
    v136[0] = a3;
    v133 = a2;
    v144[0] = a1;
    rclsid[0] = a5;
    v143 = a7;
    v135 = Src;
    v134 = a9;
    LODWORD(v128) = 0;
    *a9 = 0;
    if ( !a3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
        (const char *)0x80070057LL,
        Sizea);
      return 2147942487LL;
    }
    TypeNameFromAppActivityId = (_QWORD *)CloudStoreUtilities::GetTypeNameFromAppActivityId(v170, a6);
    v12 = (_DWORD *)*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v13 = v12[35];
    if ( (v13 & 1) == 0 )
    {
      v12[35] = v13 | 1;
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
        v12 + 36,
        v9,
        v11);
      _tlregdtor(Utf8StringToWideString_::_2_::_dynamic_atexit_destructor_for__converter_utf8_utf16__);
    }
    v132 = v12 + 36;
    if ( TypeNameFromAppActivityId[3] > 0xFu )
      TypeNameFromAppActivityId = (_QWORD *)*TypeNameFromAppActivityId;
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)TypeNameFromAppActivityId + v14) );
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v12 + 36,
      v163,
      TypeNameFromAppActivityId,
      (char *)TypeNameFromAppActivityId + v14);
    v15 = (_QWORD *)WideStringToLowerCase(v175, v163);
    v16 = v12[34];
    if ( (v16 & 1) == 0 )
    {
      v12[34] = v16 | 1;
      std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v12 + 4);
      _tlregdtor(WideStringToUtf8String_::_2_::_dynamic_atexit_destructor_for__converter_utf8__);
    }
    v17 = v12 + 4;
    v130 = v12 + 4;
    if ( v15[3] <= 7u )
      v18 = v15;
    else
      v18 = (_QWORD *)*v15;
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v17,
      v174,
      v18,
      (char *)v18 + 2 * v15[2]);
    if ( *((_QWORD *)&v176 + 1) > 7u )
      std::_Deallocate<16>(v175[0], (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v176 + 1) + 2));
    *(_QWORD *)&v176 = 0;
    *((_QWORD *)&v176 + 1) = 7;
    LOWORD(v175[0]) = 0;
    if ( *((_QWORD *)&v164 + 1) > 7u )
      std::_Deallocate<16>(v163[0], (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v164 + 1) + 2));
    if ( v172 > 0xF )
    {
      v19 = v170[0];
      v20 = (const struct std::nothrow_t *)(v172 + 1);
      v128 = (void *)(v172 + 1);
      v129 = v170[0];
      if ( v172 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v129, (unsigned __int64 *)&v128);
        v20 = (const struct std::nothrow_t *)v128;
        v19 = v129;
      }
      operator delete(v19, v20);
    }
    v171 = 0;
    v172 = 15;
    LOBYTE(v170[0]) = 0;
    v21 = (_QWORD *)((__int64 (*)(void))GetEncryptedTypeName)();
    if ( v21[3] > 0xFu )
      v21 = (_QWORD *)*v21;
    v22 = v174;
    if ( v174[3] > 0xFu )
      v22 = (_QWORD *)v174[0];
    if ( !(unsigned int)_o__stricmp(v22, v21) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
        v23);
    *(_OWORD *)Buf1 = 0;
    v157 = 0;
    v158 = 0;
    v24 = -1;
    do
      ++v24;
    while ( Src[v24] );
    if ( v24 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("string too long");
    if ( v24 <= 0xF )
    {
      v157 = v24;
      v158 = 15;
      memcpy_0(Buf1, Src, v24);
      *((_BYTE *)Buf1 + v24) = 0;
    }
    else
    {
      v25 = std::string::_Calculate_growth(v24, 15, 0x7FFFFFFFFFFFFFFFLL);
      v26 = (void *)std::allocator<char>::allocate(Buf1, v25 + 1);
      Buf1[0] = v26;
      v157 = v24;
      v158 = v25;
      memcpy_0(v26, Src, v24);
      *((_BYTE *)v26 + v24) = 0;
    }
    Base64DecodeInternal(v139, Buf1);
    if ( v158 > 0xF )
    {
      v27 = Buf1[0];
      v28 = (const struct std::nothrow_t *)(v158 + 1);
      v128 = (void *)(v158 + 1);
      v129 = Buf1[0];
      if ( v158 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v129, (unsigned __int64 *)&v128);
        v27 = v129;
        v28 = (const struct std::nothrow_t *)v128;
      }
      operator delete(v27, v28);
    }
    lpsz = 0;
    v29 = StringFromCLSID(rclsid[0], &lpsz);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
        (const char *)(unsigned int)v29,
        Sizea);
    *(_OWORD *)Buf1 = 0;
    v157 = 0;
    v158 = 0;
    v30 = -1;
    do
      ++v30;
    while ( a6[v30] );
    if ( v30 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("string too long");
    if ( v30 <= 0xF )
    {
      v157 = v30;
      v158 = 15;
      memcpy_0(Buf1, a6, v30);
      *((_BYTE *)Buf1 + v30) = 0;
    }
    else
    {
      v31 = std::string::_Calculate_growth(v30, 15, 0x7FFFFFFFFFFFFFFFLL);
      v32 = (void *)std::allocator<char>::allocate(Buf1, v31 + 1);
      Buf1[0] = v32;
      v157 = v30;
      v158 = v31;
      memcpy_0(v32, a6, v30);
      *((_BYTE *)v32 + v30) = 0;
    }
    v33 = lpsz;
    *(_OWORD *)rclsid = 0;
    v154 = 0;
    v155 = 0;
    v34 = -1;
    do
      ++v34;
    while ( lpsz[v34] );
    if ( v34 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v34 <= 7 )
    {
      v154 = v34;
      v155 = 7;
      v113 = 2 * v34;
      memcpy_0(rclsid, lpsz, v113);
      *(_WORD *)((char *)rclsid + v113) = 0;
    }
    else
    {
      v35 = std::wstring::_Calculate_growth(v34);
      if ( (unsigned __int64)(v35 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v36 = (IID *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v35 + 1));
      rclsid[0] = v36;
      v154 = v34;
      v155 = v35;
      v37 = 2 * v34;
      memcpy_0(v36, v33, v37);
      *(_WORD *)((char *)&v36->Data1 + v37) = 0;
      v17 = v130;
    }
    v38 = v12[34];
    if ( (v38 & 1) == 0 )
    {
      v12[34] = v38 | 1;
      std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v17);
      _tlregdtor(WideStringToUtf8String_::_2_::_dynamic_atexit_destructor_for__converter_utf8__);
    }
    v39 = rclsid;
    if ( v155 > 7 )
      v39 = (IID **)rclsid[0];
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v17,
      v175,
      v39,
      (char *)v39 + 2 * v154);
    v40 = v176;
    if ( *((_QWORD *)&v176 + 1) == (_QWORD)v176 )
    {
      v43 = (void **)std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                       v175,
                       1u);
    }
    else
    {
      *(_QWORD *)&v176 = v176 + 1;
      v41 = v176;
      v42 = std::_String_val<std::_Simple_types<char>>::_Myptr(v175);
      *(_BYTE *)(v40 + v42) = asc_1802284D0[0];
      *(_BYTE *)(v42 + v41) = 0;
      v43 = v175;
    }
    *(_OWORD *)v163 = *(_OWORD *)v43;
    v164 = *((_OWORD *)v43 + 1);
    v43[2] = 0;
    v43[3] = (void *)15;
    *(_BYTE *)v43 = 0;
    v44 = (_QWORD *)std::operator+<char>(v170, v163, Buf1);
    v45 = (__int64)v44;
    v46 = v44[2];
    if ( v44[3] == v46 )
    {
      v45 = std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
              v44,
              1u);
    }
    else
    {
      v44[2] = v46 + 1;
      strcpy((char *)(std::_String_val<std::_Simple_types<char>>::_Myptr(v44) + v46), "\\");
    }
    *(_OWORD *)v168 = 0;
    v169 = 0u;
    *(_OWORD *)v168 = *(_OWORD *)v45;
    v169 = *(_OWORD *)(v45 + 16);
    *(_QWORD *)(v45 + 16) = 0;
    *(_QWORD *)(v45 + 24) = 15;
    *(_BYTE *)v45 = 0;
    v47 = -32;
    if ( v172 > 0xF )
    {
      v48 = v170[0];
      v49 = (const struct std::nothrow_t *)(v172 + 1);
      v129 = (void *)(v172 + 1);
      v128 = v170[0];
      if ( v172 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v128, (unsigned __int64 *)&v129);
        v49 = (const struct std::nothrow_t *)v129;
        v48 = v128;
      }
      operator delete(v48, v49);
    }
    v171 = 0;
    v172 = 15;
    LOBYTE(v170[0]) = 0;
    if ( *((_QWORD *)&v164 + 1) > 0xFu )
    {
      v50 = (const struct std::nothrow_t *)(*((_QWORD *)&v164 + 1) + 1LL);
      v129 = (void *)(*((_QWORD *)&v164 + 1) + 1LL);
      v51 = v163[0];
      v128 = v163[0];
      if ( (unsigned __int64)(*((_QWORD *)&v164 + 1) + 1LL) >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v128, (unsigned __int64 *)&v129);
        v50 = (const struct std::nothrow_t *)v129;
        v51 = v128;
      }
      operator delete(v51, v50);
    }
    if ( *((_QWORD *)&v176 + 1) > 0xFu )
    {
      v52 = v175[0];
      v53 = (const struct std::nothrow_t *)(*((_QWORD *)&v176 + 1) + 1LL);
      v129 = (void *)(*((_QWORD *)&v176 + 1) + 1LL);
      v128 = v175[0];
      if ( (unsigned __int64)(*((_QWORD *)&v176 + 1) + 1LL) >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v128, (unsigned __int64 *)&v129);
        v53 = (const struct std::nothrow_t *)v129;
        v52 = v128;
      }
      operator delete(v52, v53);
    }
    *(_QWORD *)&v176 = 0;
    *((_QWORD *)&v176 + 1) = 15;
    LOBYTE(v175[0]) = 0;
    if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(rclsid) )
      std::_Deallocate<16>(rclsid[0], (const struct std::nothrow_t *)(2 * v155 + 2));
    v154 = 0;
    v155 = 7;
    LOWORD(rclsid[0]) = 0;
    if ( v158 > 0xF )
    {
      v55 = Buf1[0];
      v56 = (const struct std::nothrow_t *)(v158 + 1);
      v129 = (void *)(v158 + 1);
      v128 = Buf1[0];
      if ( v158 + 1 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v128, (unsigned __int64 *)&v129);
        v56 = (const struct std::nothrow_t *)v129;
        v55 = v128;
      }
      operator delete(v55, v56);
    }
    v57 = v168;
    if ( *((_QWORD *)&v169 + 1) > 0xFu )
      v57 = (void **)v168[0];
    v58 = (char *)v57 + v169;
    v59 = v168;
    if ( *((_QWORD *)&v169 + 1) > 0xFu )
      v59 = (void **)v168[0];
    v137 = 0;
    v138 = 0;
    v60 = v58 - 1 - (char *)v59;
    if ( v58 - 1 != (char *)v59 )
    {
      std::vector<unsigned char>::_Buy_nonzero(&v137, v60);
      *((_QWORD *)&v137 + 1) = std::_Uninitialized_copy<char const *,char const *,std::allocator<unsigned char>>(
                                 v59,
                                 (__int64)(v58 - 1),
                                 (void *)v137);
      v130 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v130);
    }
    v61 = v133;
    if ( v133 )
    {
      if ( v133 != 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
          v54);
      CloudStoreActivityFeedHelpers::TryGetSchemaFromTypeNameAndAppId(v144[0]);
      if ( v141 )
      {
        *(_OWORD *)rclsid = 0;
        v154 = 0;
        v155 = 0;
        v63 = -1;
        v64 = v142;
        do
          ++v63;
        while ( *((_BYTE *)v142 + v63) );
        if ( v63 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlen_string();
        if ( v63 > 0xF )
        {
          v74 = std::string::_Calculate_growth(v63, 15, 0x7FFFFFFFFFFFFFFFLL);
          v75 = (IID *)std::allocator<char>::allocate(rclsid, v74 + 1);
          rclsid[0] = v75;
          v154 = v63;
          v155 = v74;
          memcpy_0(v75, v64, v63);
          *((_BYTE *)&v75->Data1 + v63) = 0;
        }
        else
        {
          v154 = v63;
          v155 = 15;
          memcpy_0(rclsid, v142, v63);
          *((_BYTE *)rclsid + v63) = 0;
        }
        LODWORD(v128) = 11283684;
        v67 = v12[35];
        if ( (v67 & 1) != 0 )
        {
          v68 = v132;
        }
        else
        {
          v12[35] = v67 | 1;
          v68 = v132;
          std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
            v132,
            v65,
            v66);
          _tlregdtor(Utf8StringToWideString_::_2_::_dynamic_atexit_destructor_for__converter_utf8_utf16__);
        }
        v69 = rclsid;
        if ( v155 > 0xF )
          v69 = (IID **)rclsid[0];
        v70 = -1;
        do
          ++v70;
        while ( *((_BYTE *)v69 + v70) );
        std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
          v68,
          v163,
          v69,
          (char *)v69 + v70);
        LODWORD(v128) = -2136199964;
        v71 = (_QWORD *)WideStringToLowerCase(v175, v163);
        v72 = v12[34];
        if ( (v72 & 1) == 0 )
        {
          v12[34] = v72 | 1;
          std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v17);
          _tlregdtor(WideStringToUtf8String_::_2_::_dynamic_atexit_destructor_for__converter_utf8__);
        }
        if ( v71[3] > 7u )
          v73 = (_QWORD *)*v71;
        else
          v73 = v71;
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
          v17,
          Buf1,
          v73,
          (char *)v73 + 2 * v71[2]);
        if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v175) )
          std::_Deallocate<16>(v175[0], (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v176 + 1) + 2));
        *(_QWORD *)&v176 = 0;
        *((_QWORD *)&v176 + 1) = 7;
        LOWORD(v175[0]) = 0;
        if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v163) )
          std::_Deallocate<16>(v163[0], (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v164 + 1) + 2));
        v47 = -20;
        LODWORD(v128) = -1062458132;
        EncryptedTypeName = (_QWORD *)GetEncryptedTypeName(v77, v76);
        v79 = EncryptedTypeName[2];
        if ( EncryptedTypeName[3] > 0xFu )
          EncryptedTypeName = (_QWORD *)*EncryptedTypeName;
        v80 = v157;
        v81 = Buf1;
        v82 = Buf1[0];
        v83 = v158;
        if ( v158 > 0xF )
          v81 = (void **)Buf1[0];
        v84 = v157;
        if ( v79 < v157 )
          v84 = v79;
        v85 = memcmp_0(v81, EncryptedTypeName, v84);
        if ( !v85 && v80 >= v79 && v80 <= v79 )
        {
          v86 = 0;
          goto LABEL_120;
        }
      }
      else
      {
        v83 = v158;
        v82 = Buf1[0];
      }
      v86 = 1;
LABEL_120:
      if ( (v47 & 8) != 0 )
      {
        v47 &= ~8u;
        if ( v83 > 0xF )
        {
          v87 = (const struct std::nothrow_t *)(v83 + 1);
          v129 = (void *)(v83 + 1);
          v132 = v82;
          if ( v83 + 1 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(&v132, (unsigned __int64 *)&v129);
            v82 = v132;
            v87 = (const struct std::nothrow_t *)v129;
          }
          operator delete(v82, v87);
        }
      }
      if ( (v47 & 4) != 0 && v155 > 0xF )
      {
        v88 = (const struct std::nothrow_t *)(v155 + 1);
        v132 = (void *)(v155 + 1);
        v89 = rclsid[0];
        v129 = rclsid[0];
        if ( v155 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v129, (unsigned __int64 *)&v132);
          v88 = (const struct std::nothrow_t *)v132;
          v89 = (IID *)v129;
        }
        operator delete(v89, v88);
      }
      if ( !v86 )
      {
        if ( v173 )
        {
          try
          {
            v130 = 0;
            Windows::Data::Platform::Encryption::StructureValue::StructureValue((Windows::Data::Platform::Encryption::StructureValue *)v150);
            UnmarshalStruct<Windows::Data::Platform::Encryption::StructureValue>(v139, v150);
            v90 = (IID *)v136[0];
            (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v136[0] + 8LL))(v136[0]);
            *(_OWORD *)v136 = 0;
            rclsid[0] = v90;
            rclsid[1] = (IID *)v127;
            LOBYTE(v154) = 1;
            v91 = operator new(0x18u);
            v91[2] = 1;
            v91[3] = 1;
            *(_QWORD *)v91 = &std::_Ref_count_resource<ICDPActivityEncryption *,cdp::detail::iunknown_deleter<ICDPActivityEncryption>>::`vftable';
            *((_QWORD *)v91 + 2) = v90;
            v136[0] = (std::_Ref_count_base *)v90;
            v136[1] = (std::_Ref_count_base *)v91;
            if ( !v173 )
              std::_Throw_bad_optional_access();
            v92 = EncryptedToEncryptable(&v145, v170, v150, v136);
            EncryptableToWalkable(v175, v170, v92);
            boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v147);
            std::_Tree<std::_Tmap_traits<unsigned short,Windows::Data::Platform::Encryption::FieldValue,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,Windows::Data::Platform::Encryption::FieldValue>>,0>>::~_Tree<std::_Tmap_traits<unsigned short,Windows::Data::Platform::Encryption::FieldValue,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,Windows::Data::Platform::Encryption::FieldValue>>,0>>(v146);
            bond::nullable<Windows::Data::Platform::Encryption::StructureValue,void>::reset(&v145);
            if ( !v173 )
              std::_Throw_bad_optional_access();
            schematized_data::schematized_data(v163, v170, v175);
            walkable::structure::~structure((walkable::structure *)v175);
            if ( v136[1] )
              std::_Ref_count_base::_Decref(v136[1]);
            v93 = v163[0];
            v175[0] = v163[0];
            v94 = v163[1];
            v175[1] = v163[1];
            __SET_PAIR__(v95, v96, v164);
            v176 = v164;
            if ( *((_QWORD *)&v164 + 1) )
              _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v164 + 1) + 8LL));
            v97 = v166;
            if ( v166 )
            {
              _InterlockedIncrement((volatile signed __int32 *)(v166 + 8));
              v97 = v166;
            }
            v98 = v165;
            v177 = v165;
            v178 = v97;
            v99 = v167;
            v179 = v167;
            Buf1[0] = v93;
            Buf1[1] = v94;
            v157 = v96;
            v158 = v95;
            if ( v95 )
              _InterlockedIncrement((volatile signed __int32 *)(v95 + 8));
            if ( v97 )
              _InterlockedIncrement((volatile signed __int32 *)(v97 + 8));
            v159 = v98;
            v160 = v97;
            v161 = v99;
            v162 = 0;
            v145 = v93;
            v146[0] = v94;
            v146[1] = v96;
            v146[2] = v95;
            if ( v95 )
              _InterlockedIncrement((volatile signed __int32 *)(v95 + 8));
            if ( v97 )
              _InterlockedIncrement((volatile signed __int32 *)(v97 + 8));
            v146[3] = v98;
            v147[0] = v97;
            v147[1] = v99;
            v148 = 0;
            v149 = -1;
            schematized_data::~schematized_data((schematized_data *)Buf1);
            schematized_data::~schematized_data((schematized_data *)v175);
            CloudStoreActivityFeed = (_QWORD *)CloudStoreActivityFeedHelpers::MakeCloudStoreActivityFeedData<versioned<tombstoned<schematized_data>>>(
                                                 rclsid,
                                                 &v145);
            v101 = (_DWORD *)*CloudStoreActivityFeed;
            *CloudStoreActivityFeed = 0;
            v130 = v101;
            if ( rclsid[0] )
              (*(void (__fastcall **)(IID *))(*(_QWORD *)rclsid[0] + 16LL))(rclsid[0]);
            schematized_data::~schematized_data((schematized_data *)&v145);
            schematized_data::~schematized_data((schematized_data *)v163);
            boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v152);
            std::_Tree<std::_Tmap_traits<unsigned short,Windows::Data::Platform::Encryption::FieldValue,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,Windows::Data::Platform::Encryption::FieldValue>>,0>>::~_Tree<std::_Tmap_traits<unsigned short,Windows::Data::Platform::Encryption::FieldValue,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,Windows::Data::Platform::Encryption::FieldValue>>,0>>(v151);
            bond::nullable<Windows::Data::Platform::Encryption::StructureValue,void>::reset(v150);
            *v134 = v101;
            std::optional<bond::RuntimeSchema>::~optional<bond::RuntimeSchema>(v170);
            std::vector<unsigned char>::_Tidy(&v137);
            std::string::_Tidy_deallocate(v168);
            if ( lpsz )
              CoTaskMemFree(lpsz);
            boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v140);
            std::string::_Tidy_deallocate(v174);
            result = 0;
          }
          catch ( CorruptDataException )
          {
            if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
            {
              v122 = std::optional<bond::RuntimeSchema const>::value(v170);
              v123 = std::_String_val<std::_Simple_types<char>>::_Myptr(216LL
                                                                      * *(unsigned __int16 *)(*(_QWORD *)(v122 + 8) + 4LL)
                                                                      + 32 + **(_QWORD **)v122);
              McTemplateU0ss_EventWriteTransfer(v124, DecryptionPayloadDeserializationError, v123, v135);
            }
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x16E,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
              (const char *)0x8007000DLL,
              Size);
          }
          return result;
        }
        std::optional<bond::RuntimeSchema>::~optional<bond::RuntimeSchema>(v170);
        std::vector<unsigned char>::_Tidy(&v137);
        std::string::_Tidy_deallocate(v168);
        if ( lpsz )
          goto LABEL_170;
        goto LABEL_171;
      }
      v127[0] = 0;
      CloudStoreActivityFeedHelpers::MakeCloudStoreActivityFeedData<std::optional<bond::RuntimeSchema const> const &,std::string const &,unsigned __int64 const &,bool,char const * &>(
        (unsigned int)&v130,
        (unsigned int)v170,
        (unsigned int)v174,
        v62,
        (__int64)v127,
        (__int64)&v135);
      *v134 = v130;
      std::optional<bond::RuntimeSchema>::~optional<bond::RuntimeSchema>(v170);
      std::vector<unsigned char>::_Tidy(&v137);
      std::string::_Tidy_deallocate(v168);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v140);
      std::string::_Tidy_deallocate(v174);
      return 0;
    }
    if ( !v141 )
      goto LABEL_162;
    std::string::string(v163, (const char *)v142);
    LODWORD(v128) = 11283681;
    v114 = Utf8StringToLowerCase(v170, v163);
    v47 = -29;
    LODWORD(v128) = 11283683;
    v115 = ((__int64 (*)(void))GetEncryptedTypeName)();
    v116 = std::string::compare(v114, v115);
    v104 = 0;
    if ( !v116 )
LABEL_162:
      v104 = 1;
    if ( (v47 & 2) != 0 )
    {
      v47 &= ~2u;
      std::string::_Tidy_deallocate(v170);
    }
    if ( (v47 & 1) != 0 )
      std::string::_Tidy_deallocate(v163);
    if ( v104 )
    {
      v127[0] = 0;
      v117 = GetEncryptedTypeName(v61, v60);
      EncryptedTypeSchema = GetEncryptedTypeSchema(v163);
      v120 = (__int64 *)CloudStoreActivityFeedHelpers::MakeCloudStoreActivityFeedData<bond::RuntimeSchema,std::string const &,unsigned __int64 const &,bool,char const * &>(
                          (unsigned int)&v130,
                          EncryptedTypeSchema,
                          v117,
                          v119,
                          (__int64)v127,
                          (__int64)&v135);
      v121 = *v120;
      *v120 = 0;
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v130);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v164 + 8));
      v130 = 0;
      *v134 = v121;
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v130);
      std::vector<unsigned char>::_Tidy(&v137);
      std::string::_Tidy_deallocate(v168);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v140);
      std::string::_Tidy_deallocate(v174);
      return 0;
    }
    std::_String_val<std::_Simple_types<char>>::_Myptr(v174);
    CloudStoreActivityFeedHelpers::TryGetSchemaFromTypeNameAndAppId(v144[0]);
    if ( !(_BYTE)v165 )
    {
      std::optional<bond::RuntimeSchema>::~optional<bond::RuntimeSchema>(v163);
      std::vector<unsigned char>::_Tidy(&v137);
      std::string::_Tidy_deallocate(v168);
      if ( lpsz )
LABEL_170:
        CoTaskMemFree(lpsz);
LABEL_171:
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v140);
      std::string::_Tidy_deallocate(v174);
      return 2147943568LL;
    }
    schematized_data::schematized_data(
      (schematized_data *)v170,
      (const struct bond::RuntimeSchema *)v163,
      (const struct bond::blob *)v139);
    cdp::detail::wrap_unknown<ICDPActivityEncryption>(rclsid, v136[0]);
    v105 = schematized_data::as_walkable((schematized_data *)v170);
    v106 = EncryptStructure(v150, v105, &v137, rclsid);
    deserializable_data<Windows::Data::Platform::Encryption::StructureValue>::deserializable_data<Windows::Data::Platform::Encryption::StructureValue>(
      v144,
      v106);
    Windows::Data::Platform::Encryption::StructureValue::~StructureValue((Windows::Data::Platform::Encryption::StructureValue *)v150);
    if ( rclsid[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)rclsid[1]);
    v107 = deserializable_data<Windows::Data::Platform::Encryption::StructureValue>::serialized(v144);
    versioned = make_versioned_tombstoned<schematized_data,schematized_data const &>(&v145, v108, v109, v107);
    v111 = (__int64 *)CloudStoreActivityFeedHelpers::MakeCloudStoreActivityFeedData<versioned<tombstoned<schematized_data>>>(
                        &v130,
                        versioned);
    v112 = *v111;
    *v111 = 0;
    if ( v130 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v130 + 16LL))(v130);
    schematized_data::~schematized_data((schematized_data *)&v145);
    *v134 = v112;
    std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(v144);
    schematized_data::~schematized_data((schematized_data *)v170);
    std::optional<bond::RuntimeSchema>::~optional<bond::RuntimeSchema>(v163);
    std::vector<unsigned char>::_Tidy(&v137);
    std::string::_Tidy_deallocate(v168);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v140);
    std::string::_Tidy_deallocate(v174);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x17C,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoreactivityfeedhelpers.cpp",
                           v102);
  }
  return result;
}

```

## disassembly

```asm
0x18001cb30  push    rbx
0x18001cb32  push    rsi
0x18001cb33  push    rdi
0x18001cb34  push    r12
0x18001cb36  push    r13
0x18001cb38  push    r14
0x18001cb3a  push    r15
0x18001cb3c  sub     rsp, 2E0h
0x18001cb43  mov     rax, cs:__security_cookie
0x18001cb4a  xor     rax, rsp
0x18001cb4d  mov     [rsp+318h+var_48], rax
0x18001cb55  mov     [rsp+318h+var_260], r9
0x18001cb5d  mov     [rsp+318h+var_2A0], r8
0x18001cb62  mov     [rsp+318h+var_2B8], edx
0x18001cb66  mov     [rsp+318h+var_250], rcx
0x18001cb6e  mov     rax, [rsp+318h+arg_20]
0x18001cb76  mov     [rsp+318h+rclsid], rax
0x18001cb7e  mov     r12, [rsp+318h+arg_28]
0x18001cb86  mov     rax, [rsp+318h+arg_30]
0x18001cb8e  mov     [rsp+318h+var_258], rax
0x18001cb96  mov     r15, [rsp+318h+Src]
0x18001cb9e  mov     [rsp+318h+var_2A8], r15
0x18001cba3  mov     rax, [rsp+318h+arg_40]
0x18001cbab  mov     [rsp+318h+var_2B0], rax
0x18001cbb0  xor     ecx, ecx
0x18001cbb2  mov     dword ptr [rsp+318h+var_2E0], ecx
0x18001cbb6  mov     [rax], rcx
0x18001cbb9  test    r8, r8
0x18001cbbc  jz      loc_18001DCC4
0x18001cbc2  mov     rdx, r12
0x18001cbc5  lea     rcx, [rsp+318h+var_F0]
0x18001cbcd  call    ?GetTypeNameFromAppActivityId@CloudStoreUtilities@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CloudStoreUtilities::GetTypeNameFromAppActivityId(char const *)
0x18001cbd2  mov     rbx, rax
0x18001cbd5  mov     esi, cs:_tls_index
0x18001cbdb  mov     r14, gs:58h
0x18001cbe4  mov     r13, [r14+rsi*8]
0x18001cbe8  mov     ecx, 8Ch
0x18001cbed  mov     eax, [rcx+r13]
0x18001cbf1  mov     edi, 90h
0x18001cbf6  test    al, 1
0x18001cbf8  jz      loc_18001DB9F
0x18001cbfe  lea     rcx, [rdi+r13]
0x18001cc02  mov     [rsp+318h+var_2C0], rcx
0x18001cc07  cmp     qword ptr [rbx+18h], 0Fh
0x18001cc0c  jbe     short loc_18001CC11
0x18001cc0e  mov     rbx, [rbx]
0x18001cc11  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cc15  inc     rax
0x18001cc18  cmp     byte ptr [rbx+rax], 0
0x18001cc1c  jnz     short loc_18001CC15
0x18001cc1e  lea     r9, [rax+rbx]
0x18001cc22  mov     r8, rbx
0x18001cc25  lea     rdx, [rsp+318h+var_148]
0x18001cc2d  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x18001cc32  nop
0x18001cc33  lea     rdx, [rsp+318h+var_148]
0x18001cc3b  lea     rcx, [rsp+318h+var_98]
0x18001cc43  call    ?WideStringToLowerCase@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; WideStringToLowerCase(std::wstring const &)
0x18001cc48  mov     rdi, rax
0x18001cc4b  mov     eax, 88h
0x18001cc50  mov     ecx, [rax+r13]
0x18001cc54  mov     ebx, 10h
0x18001cc59  test    cl, 1
0x18001cc5c  jz      loc_18001D36A
0x18001cc62  lea     r14, [rbx+r13]
0x18001cc66  mov     [rsp+318h+var_2D0], r14
0x18001cc6b  mov     ebx, 7
0x18001cc70  cmp     [rdi+18h], rbx
0x18001cc74  jbe     loc_18001CF93
0x18001cc7a  mov     r8, [rdi]
0x18001cc7d  mov     rax, [rdi+10h]
0x18001cc81  lea     r9, [r8+rax*2]
0x18001cc85  lea     rdx, [rsp+318h+var_B8]
0x18001cc8d  mov     rcx, r14
0x18001cc90  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18001cc95  nop
0x18001cc96  mov     rdx, [rsp+318h+var_80]
0x18001cc9e  cmp     rdx, rbx
0x18001cca1  jbe     short loc_18001CCB8
0x18001cca3  lea     rdx, ds:2[rdx*2]
0x18001ccab  mov     rcx, [rsp+318h+var_98]
0x18001ccb3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ccb8  xor     edi, edi
0x18001ccba  mov     [rsp+318h+var_88], rdi
0x18001ccc2  mov     [rsp+318h+var_80], rbx
0x18001ccca  mov     word ptr [rsp+318h+var_98], di
0x18001ccd2  mov     rdx, [rsp+318h+var_130]
0x18001ccda  cmp     rdx, rbx
0x18001ccdd  jbe     short loc_18001CCF5
0x18001ccdf  lea     rdx, ds:2[rdx*2]
0x18001cce7  mov     rcx, [rsp+318h+var_148]
0x18001ccef  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ccf4  nop
0x18001ccf5  mov     rdx, [rsp+318h+var_D8]
0x18001ccfd  mov     esi, 0Fh
0x18001cd02  cmp     rdx, rsi
0x18001cd05  jbe     short loc_18001CD2E
0x18001cd07  mov     rcx, [rsp+318h+var_F0]; void *
0x18001cd0f  inc     rdx; struct std::nothrow_t *
0x18001cd12  mov     [rsp+318h+var_2E0], rdx
0x18001cd17  mov     [rsp+318h+var_2D8], rcx
0x18001cd1c  cmp     rdx, 1000h
0x18001cd23  jnb     loc_18001DEB2
0x18001cd29  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cd2e  mov     [rsp+318h+var_E0], rdi
0x18001cd36  mov     [rsp+318h+var_D8], rsi
0x18001cd3e  mov     byte ptr [rsp+318h+var_F0], dil
0x18001cd46  call    ?GetEncryptedTypeName@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; GetEncryptedTypeName(void)
0x18001cd4b  cmp     [rax+18h], rsi
0x18001cd4f  ja      loc_18001CF9B
0x18001cd55  lea     rcx, [rsp+318h+var_B8]
0x18001cd5d  cmp     [rsp+318h+var_A0], rsi
0x18001cd65  cmova   rcx, [rsp+318h+var_B8]
0x18001cd6e  mov     rdx, rax
0x18001cd71  call    cs:__imp__o__stricmp
0x18001cd77  test    eax, eax
0x18001cd79  jz      loc_18001D55C
0x18001cd7f  xorps   xmm0, xmm0
0x18001cd82  movups  xmmword ptr [rsp+318h+Buf1], xmm0
0x18001cd8a  mov     [rsp+318h+var_178], rdi
0x18001cd92  mov     [rsp+318h+var_170], rdi
0x18001cd9a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cd9e  inc     rbx
0x18001cda1  cmp     [r15+rbx], dil
0x18001cda5  jnz     short loc_18001CD9E
0x18001cda7  mov     rdi, 7FFFFFFFFFFFFFFFh
0x18001cdb1  cmp     rbx, rdi
0x18001cdb4  ja      loc_18001DED0
0x18001cdba  cmp     rbx, rsi
0x18001cdbd  jbe     loc_18001D307
0x18001cdc3  mov     r8, rdi
0x18001cdc6  mov     rdx, rsi
0x18001cdc9  mov     rcx, rbx
0x18001cdcc  call    ?_Calculate_growth@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CA_K_K00@Z; std::string::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001cdd1  mov     rsi, rax
0x18001cdd4  lea     rdx, [rax+1]
0x18001cdd8  lea     rcx, [rsp+318h+Buf1]
0x18001cde0  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x18001cde5  mov     rdi, rax
0x18001cde8  mov     [rsp+318h+Buf1], rax
0x18001cdf0  mov     [rsp+318h+var_178], rbx
0x18001cdf8  mov     [rsp+318h+var_170], rsi
0x18001ce00  mov     r8, rbx; Size
0x18001ce03  mov     rdx, r15; Src
0x18001ce06  mov     rcx, rax; void *
0x18001ce09  call    memcpy_0
0x18001ce0e  xor     r15d, r15d
0x18001ce11  mov     [rbx+rdi], r15b
0x18001ce15  lea     esi, [r15+0Fh]
0x18001ce19  mov     rdi, 7FFFFFFFFFFFFFFFh
0x18001ce23  lea     rdx, [rsp+318h+Buf1]
0x18001ce2b  lea     rcx, [rsp+318h+var_278]
0x18001ce33  call    ?Base64DecodeInternal@@YA?AVblob@bond@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Base64DecodeInternal(std::string const &)
0x18001ce38  nop
0x18001ce39  mov     rdx, [rsp+318h+var_170]
0x18001ce41  cmp     rdx, rsi
0x18001ce44  jbe     short loc_18001CE6E
0x18001ce46  mov     rcx, [rsp+318h+Buf1]; void *
0x18001ce4e  inc     rdx; struct std::nothrow_t *
0x18001ce51  mov     [rsp+318h+var_2E0], rdx
0x18001ce56  mov     [rsp+318h+var_2D8], rcx
0x18001ce5b  cmp     rdx, 1000h
0x18001ce62  jnb     loc_18001DEDE
0x18001ce68  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ce6d  nop
0x18001ce6e  mov     [rsp+318h+lpsz], r15
0x18001ce73  lea     rdx, [rsp+318h+lpsz]; lplpsz
0x18001ce78  mov     rcx, [rsp+318h+rclsid]; rclsid
0x18001ce80  call    cs:__imp_StringFromCLSID
0x18001ce86  mov     rcx, [rsp+318h]; this
0x18001ce8e  test    eax, eax
0x18001ce90  js      loc_18001DBC1
0x18001ce96  xorps   xmm0, xmm0
0x18001ce99  movups  xmmword ptr [rsp+318h+Buf1], xmm0
0x18001cea1  mov     [rsp+318h+var_178], r15
0x18001cea9  mov     [rsp+318h+var_170], r15
0x18001ceb1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ceb5  inc     rbx
0x18001ceb8  cmp     [r12+rbx], r15b
0x18001cebc  jnz     short loc_18001CEB5
0x18001cebe  cmp     rbx, rdi
0x18001cec1  ja      loc_18001DEFC
0x18001cec7  cmp     rbx, rsi
0x18001ceca  jbe     loc_18001D33A
0x18001ced0  mov     r8, rdi
0x18001ced3  mov     rdx, rsi
0x18001ced6  mov     rcx, rbx
0x18001ced9  call    ?_Calculate_growth@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@CA_K_K00@Z; std::string::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001cede  mov     rsi, rax
0x18001cee1  lea     rdx, [rax+1]
0x18001cee5  lea     rcx, [rsp+318h+Buf1]
0x18001ceed  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x18001cef2  mov     rdi, rax
0x18001cef5  mov     [rsp+318h+Buf1], rax
0x18001cefd  mov     [rsp+318h+var_178], rbx
0x18001cf05  mov     [rsp+318h+var_170], rsi
0x18001cf0d  mov     r8, rbx; Size
0x18001cf10  mov     rdx, r12; Src
0x18001cf13  mov     rcx, rax; void *
0x18001cf16  call    memcpy_0
0x18001cf1b  mov     [rbx+rdi], r15b
0x18001cf1f  mov     rdi, 7FFFFFFFFFFFFFFFh
0x18001cf29  mov     rsi, [rsp+318h+lpsz]
0x18001cf2e  xorps   xmm0, xmm0
0x18001cf31  movups  xmmword ptr [rsp+318h+rclsid], xmm0
0x18001cf39  mov     [rsp+318h+var_198], r15
0x18001cf41  mov     [rsp+318h+var_190], r15
0x18001cf49  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cf4d  inc     rbx
0x18001cf50  cmp     [rsi+rbx*2], r15w
0x18001cf55  jnz     short loc_18001CF4D
0x18001cf57  mov     r8, 7FFFFFFFFFFFFFFEh
0x18001cf61  cmp     rbx, r8
0x18001cf64  ja      loc_18001DF0A
0x18001cf6a  cmp     rbx, 7
0x18001cf6e  jbe     loc_18001DF17
0x18001cf74  mov     edx, 7
0x18001cf79  mov     rcx, rbx
0x18001cf7c  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001cf81  mov     r14, rax
0x18001cf84  lea     rcx, [rax+1]
0x18001cf88  cmp     rcx, rdi
0x18001cf8b  jbe     short loc_18001CFA3
0x18001cf8d  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18001cf93  mov     r8, rdi
0x18001cf96  jmp     loc_18001CC7D
0x18001cf9b  mov     rax, [rax]
0x18001cf9e  jmp     loc_18001CD55
0x18001cfa3  add     rcx, rcx
0x18001cfa6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001cfab  mov     rdi, rax
0x18001cfae  mov     [rsp+318h+rclsid], rax
0x18001cfb6  mov     [rsp+318h+var_198], rbx
0x18001cfbe  mov     [rsp+318h+var_190], r14
0x18001cfc6  add     rbx, rbx
0x18001cfc9  mov     r8, rbx; Size
0x18001cfcc  mov     rdx, rsi; Src
0x18001cfcf  mov     rcx, rax; void *
0x18001cfd2  call    memcpy_0
0x18001cfd7  mov     [rdi+rbx], r15w
0x18001cfdc  mov     r14, [rsp+318h+var_2D0]
0x18001cfe1  mov     ecx, 88h
0x18001cfe6  mov     eax, [rcx+r13]
0x18001cfea  mov     r12d, 1
0x18001cff0  test    r12b, al
0x18001cff3  jz      loc_18001D38C
0x18001cff9  lea     r8, [rsp+318h+rclsid]
0x18001d001  cmp     [rsp+318h+var_190], 7
0x18001d00a  cmova   r8, [rsp+318h+rclsid]
0x18001d013  mov     rax, [rsp+318h+var_198]
0x18001d01b  lea     r9, [r8+rax*2]
0x18001d01f  lea     rdx, [rsp+318h+var_98]
0x18001d027  mov     rcx, r14
0x18001d02a  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18001d02f  nop
0x18001d030  mov     rdi, [rsp+318h+var_88]
0x18001d038  mov     rax, [rsp+318h+var_80]
0x18001d040  sub     rax, rdi
0x18001d043  lea     rcx, [rsp+318h+var_98]; Src
0x18001d04b  cmp     rax, r12
0x18001d04e  jb      loc_18001DB46
0x18001d054  lea     rbx, [rdi+1]
0x18001d058  mov     [rsp+318h+var_88], rbx
0x18001d060  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d065  movzx   ecx, word ptr cs:asc_1802284D0; "\\"
0x18001d06c  mov     [rdi+rax], cl
0x18001d06f  mov     [rax+rbx], r15b
0x18001d073  lea     rax, [rsp+318h+var_98]
0x18001d07b  movups  xmm0, xmmword ptr [rax]
0x18001d07e  movups  xmmword ptr [rsp+318h+var_148], xmm0
0x18001d086  movups  xmm1, xmmword ptr [rax+10h]
0x18001d08a  movups  xmmword ptr [rsp+1E0h], xmm1
0x18001d092  mov     [rax+10h], r15
0x18001d096  mov     esi, 0Fh
0x18001d09b  mov     [rax+18h], rsi
0x18001d09f  mov     [rax], r15b
0x18001d0a2  lea     r8, [rsp+318h+Buf1]
0x18001d0aa  lea     rdx, [rsp+318h+var_148]
0x18001d0b2  lea     rcx, [rsp+318h+var_F0]
0x18001d0ba  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x18001d0bf  mov     rbx, rax
0x18001d0c2  mov     rdi, [rax+10h]
0x18001d0c6  mov     rcx, [rax+18h]
0x18001d0ca  sub     rcx, rdi
0x18001d0cd  cmp     rcx, r12
0x18001d0d0  jb      loc_18001DB5F
0x18001d0d6  lea     rcx, [rdi+1]
0x18001d0da  mov     [rax+10h], rcx
0x18001d0de  mov     rcx, rax
0x18001d0e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d0e6  movzx   ecx, word ptr cs:asc_1802284D0; "\\"
0x18001d0ed  mov     [rax+rdi], cl
0x18001d0f0  mov     [rax+rdi+1], r15b
0x18001d0f5  xorps   xmm0, xmm0
0x18001d0f8  movups  xmmword ptr [rsp+318h+var_110], xmm0
0x18001d100  mov     qword ptr [rsp+318h+var_100], r15
0x18001d108  mov     qword ptr [rsp+318h+var_100+8], r15
0x18001d110  movups  xmm0, xmmword ptr [rbx]
0x18001d113  movups  xmmword ptr [rsp+318h+var_110], xmm0
0x18001d11b  movups  xmm1, xmmword ptr [rbx+10h]
  ... truncated ...
```

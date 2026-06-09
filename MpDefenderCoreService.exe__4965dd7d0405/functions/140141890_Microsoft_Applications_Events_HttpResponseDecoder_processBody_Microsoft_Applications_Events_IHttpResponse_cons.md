# Microsoft::Applications::Events::HttpResponseDecoder::processBody(Microsoft::Applications::Events::IHttpResponse const &,Microsoft::Applications::Events::HttpRequestResult &)

- ea: `0x140141890`
- end: `0x14014241d`
- name: `?processBody@HttpResponseDecoder@Events@Applications@Microsoft@@IEAAXAEBVIHttpResponse@234@AEAW4HttpRequestResult@234@@Z`
- size: `2957`
- prototype: `void __fastcall(Microsoft::Applications::Events::HttpResponseDecoder *__hidden this, const struct Microsoft::Applications::Events::IHttpResponse *, enum Microsoft::Applications::Events::HttpRequestResult *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140141140`

## callees

- `0x14003a0f4`
- `0x14003a5c0`
- `0x14003c78c`
- `0x14007e034`
- `0x14007e088`
- `0x14007e14c`
- `0x14007fb68`
- `0x140084a18`
- `0x140084b00`
- `0x1400ff188`
- `0x1401048f8`
- `0x140105fbc`
- `0x1401066d0`
- `0x140109c24`
- `0x140109d48`
- `0x14010a970`
- `0x14010aa28`
- `0x14010ae68`
- `0x1401409ac`
- `0x140140a04`
- `0x140140c44`
- `0x140140d38`
- `0x140140e14`
- `0x140140f8c`
- `0x140141890`
- `0x140166250`
- `0x1401662d0`

## string_xrefs

- `0x1401422c8`: `cannot compare iterators of different containers`
- `0x1401423d8`: `cannot compare iterators of different containers`
- `0x140142086`: `TokenCrackingFailure`
- `0x1401420b3`: `TokenCrackingFailure`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Microsoft::Applications::Events::HttpResponseDecoder::processBody(
        Microsoft::Applications::Events::HttpResponseDecoder *this,
        const struct Microsoft::Applications::Events::IHttpResponse *a2,
        enum Microsoft::Applications::Events::HttpRequestResult *a3)
{
  _BYTE *v4; // rsi
  _BYTE *v5; // r12
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r14
  size_t v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  void *v11; // rax
  void **v12; // rbx
  void **v13; // rax
  __int64 v14; // rax
  unsigned __int8 v15; // dl
  _QWORD *v16; // rdx
  __int64 v17; // rdx
  char v18; // al
  __int64 v19; // rdx
  unsigned __int8 *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  char v24; // al
  __int64 v25; // rdx
  unsigned __int8 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rdi
  unsigned __int64 v31; // rbx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned __int8 *v34; // rax
  __int64 v35; // r8
  unsigned __int8 *v36; // r9
  unsigned __int64 v37; // rdx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // rax
  bool v42; // zf
  __int64 v43; // rsi
  _OWORD *v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  _QWORD *v51; // rcx
  __int64 v52; // rax
  bool v53; // bl
  int v54; // edx
  unsigned __int64 v55; // rsi
  __int64 v56; // rdi
  __int64 v57; // rbx
  __int64 v58; // r12
  __int64 v59; // r13
  char v60; // al
  __int64 *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rax
  bool v64; // zf
  __int64 *v65; // rdx
  __int64 v66; // [rsp+0h] [rbp-2D8h] BYREF
  unsigned __int8 *v67; // [rsp+30h] [rbp-2A8h] BYREF
  __int128 v68; // [rsp+38h] [rbp-2A0h]
  unsigned __int64 v69; // [rsp+48h] [rbp-290h]
  __int128 v70; // [rsp+50h] [rbp-288h] BYREF
  __int128 v71; // [rsp+60h] [rbp-278h]
  void **v72; // [rsp+70h] [rbp-268h] BYREF
  int v73; // [rsp+78h] [rbp-260h]
  enum Microsoft::Applications::Events::HttpRequestResult *v74; // [rsp+80h] [rbp-258h]
  __int128 v75; // [rsp+88h] [rbp-250h] BYREF
  __int128 v76; // [rsp+98h] [rbp-240h]
  _OWORD v77[3]; // [rsp+A8h] [rbp-230h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-200h]
  __int64 v79; // [rsp+E0h] [rbp-1F8h]
  char v80[8]; // [rsp+E8h] [rbp-1F0h] BYREF
  char v81[4]; // [rsp+F0h] [rbp-1E8h] BYREF
  int v82; // [rsp+F4h] [rbp-1E4h]
  Microsoft::Applications::Events::HttpResponseDecoder *v83; // [rsp+100h] [rbp-1D8h]
  __int128 v84; // [rsp+110h] [rbp-1C8h] BYREF
  __int128 v85; // [rsp+120h] [rbp-1B8h]
  __int128 v86; // [rsp+130h] [rbp-1A8h]
  __int64 v87; // [rsp+140h] [rbp-198h]
  _BYTE pExceptionObject[56]; // [rsp+150h] [rbp-188h] BYREF
  _BYTE v89[56]; // [rsp+188h] [rbp-150h] BYREF
  _BYTE v90[56]; // [rsp+1C0h] [rbp-118h] BYREF
  _BYTE v91[56]; // [rsp+1F8h] [rbp-E0h] BYREF
  char v92[8]; // [rsp+268h] [rbp-70h] BYREF
  _QWORD *v93; // [rsp+270h] [rbp-68h] BYREF
  void *v94[2]; // [rsp+278h] [rbp-60h] BYREF
  size_t v95; // [rsp+288h] [rbp-50h]
  __int64 v96; // [rsp+290h] [rbp-48h]

  v74 = a3;
  v83 = this;
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
    v92,
    0);
  try
  {
    v4 = *(_BYTE **)((*(__int64 (**)(void))(*(_QWORD *)a2 + 40LL))() + 8);
    v5 = *(_BYTE **)(*(__int64 (__fastcall **)(const struct Microsoft::Applications::Events::IHttpResponse *))(*(_QWORD *)a2 + 40LL))(a2);
    *(_OWORD *)v94 = 0;
    v95 = 0;
    if ( v5 == v4 )
    {
      v6 = 15;
      v96 = 15;
      LOBYTE(v94[0]) = 0;
      v7 = 0x8000000000000000uLL;
      goto LABEL_22;
    }
    v8 = v4 - v5;
    v96 = 15;
    if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlen_string();
    v9 = 15;
    if ( v8 <= 0xF )
    {
      v7 = 0x8000000000000000uLL;
      goto LABEL_19;
    }
    v9 = v8 | 0xF;
    if ( (v8 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v9 = 0x7FFFFFFFFFFFFFFFLL;
      v7 = 0x8000000000000000uLL;
      v10 = 0x8000000000000000uLL;
LABEL_14:
      _mm_lfence();
      v11 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v10);
LABEL_17:
      v94[0] = v11;
      v96 = v9;
LABEL_19:
      _mm_lfence();
      v12 = v94;
      if ( v9 > 0xF )
        v12 = (void **)v94[0];
      memmove(v12, v5, v8);
      v95 = v8;
      *((_BYTE *)v12 + v8) = 0;
      v6 = v96;
LABEL_22:
      v79 = 0;
      v13 = v94;
      if ( v6 > 0xF )
        v13 = (void **)v94[0];
      v72 = v13;
      v14 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::parse<char const *>(
              v80,
              &v72,
              v77);
      v15 = v92[0];
      v92[0] = *(_BYTE *)v14;
      *(_BYTE *)v14 = v15;
      v16 = v93;
      v93 = *(_QWORD **)(v14 + 8);
      *(_QWORD *)(v14 + 8) = v16;
      LOBYTE(v16) = *(_BYTE *)v14;
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
        v14 + 8,
        v16);
      LODWORD(v72) = 0;
      v70 = 0;
      v71 = 0;
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[4],0>(
        (__int64)v92,
        (unsigned __int8 **)&v70,
        "acc");
      v67 = (unsigned __int8 *)v92;
      v68 = 0u;
      v69 = 0x8000000000000000uLL;
      if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
      {
        if ( v92[0] == 1 )
          goto LABEL_31;
        if ( v92[0] == 2 )
        {
LABEL_30:
          *((_QWORD *)&v68 + 1) = v93[1];
LABEL_33:
          if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
                 &v67,
                 (unsigned __int8 **)&v70) )
          {
            v18 = *(_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                              &v70,
                              v17);
            if ( v18 == 5 || (unsigned __int8)(v18 - 6) <= 1u )
            {
              v20 = (unsigned __int8 *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                                         &v70,
                                         v19);
              LODWORD(v72) = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<int,int>(
                               v20,
                               v21,
                               v22);
            }
          }
          v73 = 0;
          v70 = 0;
          v71 = 0;
          nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[4],0>(
            (__int64)v92,
            (unsigned __int8 **)&v70,
            "rej");
          v67 = (unsigned __int8 *)v92;
          v68 = 0u;
          v69 = 0x8000000000000000uLL;
          if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
          {
            if ( v92[0] == 1 )
              goto LABEL_44;
            if ( v92[0] == 2 )
            {
LABEL_43:
              *((_QWORD *)&v68 + 1) = v93[1];
LABEL_46:
              if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
                     &v67,
                     (unsigned __int8 **)&v70) )
              {
                v24 = *(_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                                  &v70,
                                  v23);
                if ( v24 == 5 || (unsigned __int8)(v24 - 6) <= 1u )
                {
                  v26 = (unsigned __int8 *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                                             &v70,
                                             v25);
                  v73 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<int,int>(
                          v26,
                          v27,
                          v28);
                }
              }
              v75 = 0;
              v76 = 0;
              nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[4],0>(
                (__int64)v92,
                (unsigned __int8 **)&v75,
                "efi");
              v67 = (unsigned __int8 *)v92;
              v68 = 0u;
              v69 = 0x8000000000000000uLL;
              if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
              {
                if ( v92[0] == 1 )
                  goto LABEL_57;
                if ( v92[0] == 2 )
                {
LABEL_56:
                  *((_QWORD *)&v68 + 1) = v93[1];
                  goto LABEL_59;
                }
                if ( v92[0] == 1 )
                {
LABEL_57:
                  *(_QWORD *)&v68 = *v93;
                  goto LABEL_59;
                }
                if ( v92[0] == 2 )
                  goto LABEL_56;
              }
              v69 = 1;
LABEL_59:
              if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
                     &v67,
                     (unsigned __int8 **)&v75) )
              {
                v70 = 0;
                v71 = 0u;
                std::string::_Construct<1,char const *>(&v70, "efi", 3u);
                v29 = (unsigned __int8 *)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                                           v92,
                                           &v70);
                v30 = v29;
                v67 = v29;
                v68 = 0u;
                v31 = 0x8000000000000000uLL;
                v69 = 0x8000000000000000uLL;
                v32 = *v29;
                if ( v32 <= 4 )
                {
                  if ( !*v29 )
                  {
                    v31 = 1;
LABEL_70:
                    v69 = v31;
                    goto LABEL_71;
                  }
                  if ( v32 == 1 )
                    goto LABEL_67;
                  if ( v32 == 2 )
                  {
LABEL_66:
                    *((_QWORD *)&v68 + 1) = **((_QWORD **)v29 + 1);
                    while ( 1 )
                    {
LABEL_71:
                      v75 = 0;
                      v76 = 0u;
                      std::string::_Construct<1,char const *>(&v75, "efi", 3u);
                      v34 = (unsigned __int8 *)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                                                 v92,
                                                 &v75);
                      v36 = v34;
                      *((_QWORD *)&v70 + 1) = 0;
                      v71 = 0;
                      v37 = 0x8000000000000000uLL;
                      v38 = *v34;
                      if ( v38 <= 4 )
                      {
                        v35 = *v34;
                        if ( *v34 )
                        {
                          v35 = (unsigned int)(v35 - 1);
                          if ( !(_DWORD)v35 )
                            goto LABEL_80;
                          v35 = (unsigned int)(v35 - 1);
                          if ( !(_DWORD)v35 )
                            goto LABEL_79;
                        }
                      }
                      v37 = 0x8000000000000000uLL;
                      if ( v38 > 4 || !*v34 )
                        goto LABEL_81;
                      v39 = v38 - 1;
                      if ( !v39 )
                      {
LABEL_80:
                        v41 = **((_QWORD **)v34 + 1);
                        v40 = v71;
                        goto LABEL_83;
                      }
                      if ( v39 == 1 )
                      {
LABEL_79:
                        v40 = *(_QWORD *)(*((_QWORD *)v34 + 1) + 8LL);
                      }
                      else
                      {
LABEL_81:
                        v37 = 1;
                        v40 = v71;
                      }
                      v41 = *((_QWORD *)&v70 + 1);
LABEL_83:
                      if ( v30 != v36 )
                      {
                        std::string::string(&v84, "cannot compare iterators of different containers", v35);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)pExceptionObject,
                          212,
                          (__int64)&v84);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)pExceptionObject;
                      }
                      if ( *v30 <= 4u && *v30 )
                      {
                        if ( *v30 == 1 )
                        {
                          v42 = (_QWORD)v68 == v41;
                          goto LABEL_91;
                        }
                        if ( *v30 == 2 )
                        {
                          v42 = *((_QWORD *)&v68 + 1) == v40;
                          goto LABEL_91;
                        }
                      }
                      v42 = v31 == v37;
LABEL_91:
                      if ( v42 )
                        goto LABEL_113;
                      if ( *v30 != 1 )
                      {
                        std::string::string(v77, "cannot use key() for non-object iterators", v35);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v91,
                          207,
                          (__int64)v77);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v91;
                      }
                      v43 = v68;
                      v84 = 0;
                      v85 = 0;
                      v44 = (_OWORD *)(v68 + 32);
                      if ( *(_QWORD *)(v68 + 56) > 0xFu )
                        v44 = *(_OWORD **)(v68 + 32);
                      std::string::_Construct<2,char const *>((__int64)&v84, v44, *(_QWORD *)(v68 + 48));
                      v46 = *v30;
                      if ( v46 <= 4 )
                      {
                        if ( !*v30 )
                        {
                          std::string::string(&v75, "cannot get value", v45);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v89,
                            214,
                            (__int64)&v75);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v89;
                        }
                        v47 = v46 - 1;
                        if ( !v47 )
                        {
                          v30 = (unsigned __int8 *)(v43 + 64);
                          goto LABEL_102;
                        }
                        if ( v47 == 1 )
                        {
                          v30 = (unsigned __int8 *)*((_QWORD *)&v68 + 1);
                          goto LABEL_102;
                        }
                      }
                      if ( v31 )
                      {
                        std::string::string(v77, "cannot get value", v45);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v90,
                          214,
                          (__int64)v77);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v90;
                      }
LABEL_102:
                      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
                        v80,
                        v30);
                      if ( v80[0] == 3 )
                      {
                        v51 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                                v80,
                                v77,
                                v49,
                                v50);
                        v52 = v51[2];
                        if ( v51[3] > 0xFu )
                          v51 = (_QWORD *)*v51;
                        if ( v52 == 3 )
                        {
                          v54 = *(unsigned __int16 *)v51 - 27745;
                          if ( *(_WORD *)v51 == 27745 )
                            v54 = *((unsigned __int8 *)v51 + 2) - 108;
                          v53 = v54 == 0;
                        }
                        else
                        {
                          v53 = 0;
                        }
                        std::string::_Tidy_deallocate(v77);
                        if ( v53 )
                          *(_DWORD *)v74 = 1;
                      }
                      LOBYTE(v48) = v80[0];
                      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
                        v81,
                        v48);
                      std::string::_Tidy_deallocate(&v84);
                      nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator++(&v67);
                      v31 = v69;
                      v30 = v67;
                    }
                  }
                  v33 = v32 - 1;
                  if ( !v33 )
                  {
LABEL_67:
                    *(_QWORD *)&v68 = ***((_QWORD ***)v29 + 1);
                    goto LABEL_71;
                  }
                  if ( v33 == 1 )
                    goto LABEL_66;
                }
                v31 = 0;
                goto LABEL_70;
              }
LABEL_113:
              *((_QWORD *)&v70 + 1) = 0;
              v71 = 0;
              v55 = 0x8000000000000000uLL;
              if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
              {
                if ( v92[0] == 1 )
                  goto LABEL_122;
                if ( v92[0] == 2 )
                {
LABEL_121:
                  v56 = v93[1];
LABEL_124:
                  v57 = *((_QWORD *)&v70 + 1);
LABEL_125:
                  if ( v92[0] == 1 )
                  {
                    v58 = *v93;
                    v59 = *(_QWORD *)(*v93 + 8LL);
                    v82 = 0;
                    v57 = v58;
                    while ( !*(_BYTE *)(v59 + 25) )
                    {
                      v60 = std::operator<<char>(v59 + 32, "TokenCrackingFailure");
                      if ( !v60 )
                        v57 = v59;
                      v61 = (__int64 *)(v59 + 16);
                      if ( !v60 )
                        v61 = (__int64 *)v59;
                      v59 = *v61;
                    }
                    if ( *(_BYTE *)(v57 + 25)
                      || (unsigned __int8)std::operator<<char>("TokenCrackingFailure", (void *)(v57 + 32)) )
                    {
                      v57 = v58;
                    }
                  }
                  *((_QWORD *)&v70 + 1) = 0;
                  v71 = 0;
                  if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
                  {
                    if ( v92[0] == 1 )
                      goto LABEL_145;
                    if ( v92[0] == 2 )
                    {
LABEL_144:
                      v62 = v93[1];
LABEL_147:
                      v63 = *((_QWORD *)&v70 + 1);
                      goto LABEL_148;
                    }
                  }
                  if ( (unsigned __int8)v92[0] > 4u || !v92[0] )
                    goto LABEL_146;
                  if ( v92[0] != 1 )
                  {
                    if ( v92[0] == 2 )
                      goto LABEL_144;
LABEL_146:
                    v7 = 1;
                    v62 = v71;
                    goto LABEL_147;
                  }
LABEL_145:
                  v63 = *v93;
                  v62 = v71;
LABEL_148:
                  if ( (unsigned __int8)v92[0] <= 4u && v92[0] )
                  {
                    if ( v92[0] == 1 )
                    {
                      v64 = v63 == v57;
                      goto LABEL_155;
                    }
                    if ( v92[0] == 2 )
                    {
                      v64 = v62 == v56;
LABEL_155:
                      if ( !v64 )
                      {
                        v77[1] = 0xF000000u;
                        v77[0] = 0u;
                        v77[2] = 0u;
                        v78 = 0;
                        v84 = 0u;
                        v85 = 0xF000000u;
                        v86 = 0u;
                        v87 = 0;
                        (**(void (__fastcall ***)(Microsoft::Applications::Events::HttpResponseDecoder *, __int128 *))v83)(
                          v83,
                          &v84);
                      }
                      if ( *(_DWORD *)v74 == 1 )
                      {
                        if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
                          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
                            4,
                            "MATSDK",
                            "HTTP response: all rejected");
                      }
                      else if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
                      {
                        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
                          4,
                          "MATSDK",
                          "HTTP response: accepted=%d rejected=%d",
                          (_DWORD)v72,
                          v73);
                      }
                      goto LABEL_174;
                    }
                  }
                  v64 = v7 == v55;
                  goto LABEL_155;
                }
              }
              v55 = 0x8000000000000000uLL;
              if ( (unsigned __int8)v92[0] > 4u || !v92[0] )
                goto LABEL_123;
              if ( v92[0] != 1 )
              {
                if ( v92[0] == 2 )
                  goto LABEL_121;
LABEL_123:
                v55 = 1;
                v56 = v71;
                goto LABEL_124;
              }
LABEL_122:
              v57 = *v93;
              v56 = v71;
              goto LABEL_125;
            }
            if ( v92[0] == 1 )
            {
LABEL_44:
              *(_QWORD *)&v68 = *v93;
              goto LABEL_46;
            }
            if ( v92[0] == 2 )
              goto LABEL_43;
          }
          v69 = 1;
          goto LABEL_46;
        }
        if ( v92[0] == 1 )
        {
LABEL_31:
          *(_QWORD *)&v68 = *v93;
          goto LABEL_33;
        }
        if ( v92[0] == 2 )
          goto LABEL_30;
      }
      v69 = 1;
      goto LABEL_33;
    }
    if ( v9 < 0x16 )
      v9 = 22;
    v10 = v9 + 1;
    if ( v9 == -1 )
    {
      v11 = 0;
    }
    else
    {
      if ( v10 >= 0x1000 )
      {
        v7 = 0x8000000000000000uLL;
        goto LABEL_14;
      }
      _mm_lfence();
      v11 = operator new(v10);
    }
    v7 = 0x8000000000000000uLL;
    goto LABEL_17;
  }
  catch ( ... )
  {
    v65 = &v66;
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "HTTP response: JSON parsing failed");
    goto LABEL_163;
  }
LABEL_174:
  std::string::_Tidy_deallocate(v94);
LABEL_163:
  LOBYTE(v65) = v92[0];
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
    &v93,
    v65);
}

```

## disassembly

```asm
0x140141890  mov     r11, rsp
0x140141893  push    rbx
0x140141894  push    rsi
0x140141895  push    rdi
0x140141896  push    r12
0x140141898  push    r13
0x14014189a  push    r14
0x14014189c  push    r15
0x14014189e  sub     rsp, 2A0h
0x1401418a5  mov     rax, cs:__security_cookie
0x1401418ac  xor     rax, rsp
0x1401418af  mov     [rsp+2D8h+var_40], rax
0x1401418b7  mov     [rsp+2D8h+var_258], r8
0x1401418bf  mov     rbx, rdx
0x1401418c2  mov     [rsp+2D8h+var_1D8], rcx
0x1401418ca  xor     edx, edx
0x1401418cc  lea     rcx, [r11-70h]
0x1401418d0  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA@W4value_t@detail@12@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>(nlohmann::json_abi_v3_11_3::detail::value_t)
0x1401418d5  nop
0x1401418d6  mov     rax, [rbx]
0x1401418d9  mov     rcx, rbx
0x1401418dc  mov     rax, [rax+28h]
0x1401418e0  call    cs:__guard_dispatch_icall_fptr
0x1401418e6  mov     rsi, [rax+8]
0x1401418ea  mov     rax, [rbx]
0x1401418ed  mov     rcx, rbx
0x1401418f0  mov     rax, [rax+28h]
0x1401418f4  call    cs:__guard_dispatch_icall_fptr
0x1401418fa  mov     r12, [rax]
0x1401418fd  xorps   xmm0, xmm0
0x140141900  movups  xmmword ptr [rsp+2D8h+var_60], xmm0
0x140141908  xor     r15d, r15d
0x14014190b  lea     r13d, [r15+0Fh]
0x14014190f  mov     [rsp+2D8h+var_50], r15
0x140141917  cmp     r12, rsi
0x14014191a  jnz     short loc_14014193E
0x14014191c  mov     ecx, r13d
0x14014191f  mov     [rsp+2D8h+var_48], rcx
0x140141927  mov     byte ptr [rsp+2D8h+var_60], r15b
0x14014192f  mov     r14, 8000000000000000h
0x140141939  jmp     loc_140141A1F
0x14014193e  sub     rsi, r12
0x140141941  mov     [rsp+2D8h+var_48], r13
0x140141949  mov     rax, 7FFFFFFFFFFFFFFFh
0x140141953  cmp     rsi, rax
0x140141956  ja      loc_1401422C2
0x14014195c  mov     rdi, r13
0x14014195f  cmp     rsi, r13
0x140141962  jbe     short loc_1401419DC
0x140141964  mov     rdi, rsi
0x140141967  or      rdi, r13
0x14014196a  cmp     rdi, rax
0x14014196d  jbe     short loc_140141981
0x14014196f  mov     rdi, rax
0x140141972  mov     r14, 8000000000000000h
0x14014197c  mov     rcx, r14
0x14014197f  jmp     short loc_1401419AE
0x140141981  mov     eax, 16h
0x140141986  cmp     rdi, rax
0x140141989  cmovb   rdi, rax
0x14014198d  lea     rcx, [rdi+1]; Size
0x140141991  test    rcx, rcx
0x140141994  jnz     short loc_14014199B
0x140141996  mov     rax, r15
0x140141999  jmp     short loc_1401419C0
0x14014199b  cmp     rcx, 1000h
0x1401419a2  jb      short loc_1401419B8
0x1401419a4  mov     r14, 8000000000000000h
0x1401419ae  lfence
0x1401419b1  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1401419b6  jmp     short loc_1401419CA
0x1401419b8  lfence
0x1401419bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401419c0  mov     r14, 8000000000000000h
0x1401419ca  mov     [rsp+2D8h+var_60], rax
0x1401419d2  mov     [rsp+2D8h+var_48], rdi
0x1401419da  jmp     short loc_1401419E6
0x1401419dc  mov     r14, 8000000000000000h
0x1401419e6  lfence
0x1401419e9  lea     rbx, [rsp+2D8h+var_60]
0x1401419f1  cmp     rdi, r13
0x1401419f4  cmova   rbx, [rsp+2D8h+var_60]
0x1401419fd  mov     r8, rsi; Size
0x140141a00  mov     rdx, r12; Src
0x140141a03  mov     rcx, rbx; void *
0x140141a06  call    memmove
0x140141a0b  mov     [rsp+2D8h+var_50], rsi
0x140141a13  mov     [rbx+rsi], r15b
0x140141a17  mov     rcx, [rsp+2D8h+var_48]
0x140141a1f  mov     [rsp+2D8h+var_1F8], r15
0x140141a27  lea     rax, [rsp+2D8h+var_60]
0x140141a2f  cmp     rcx, r13
0x140141a32  cmova   rax, [rsp+2D8h+var_60]
0x140141a3b  mov     [rsp+2D8h+var_268], rax
0x140141a40  lea     r8, [rsp+2D8h+var_230]
0x140141a48  lea     rdx, [rsp+2D8h+var_268]
0x140141a4d  lea     rcx, [rsp+2D8h+var_1F0]
0x140141a55  call    ??$parse@PEBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@SA?AV012@$$QEAPEBDV?$function@$$A6A_NHW4parse_event_t@detail@json_abi_v3_11_3@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@34@@Z@std@@_N2@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::parse<char const *>(char const * &&,std::function<bool (int,nlohmann::json_abi_v3_11_3::detail::parse_event_t,nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> &)>,bool,bool)
0x140141a5a  mov     dl, [rsp+2D8h+var_70]
0x140141a61  mov     cl, [rax]
0x140141a63  mov     [rsp+2D8h+var_70], cl
0x140141a6a  mov     [rax], dl
0x140141a6c  lea     r8, [rax+8]
0x140141a70  mov     rdx, [rsp+2D8h+var_68]
0x140141a78  mov     rcx, [r8]
0x140141a7b  mov     [rsp+2D8h+var_68], rcx
0x140141a83  mov     [r8], rdx
0x140141a86  mov     dl, [rax]
0x140141a88  mov     rcx, r8
0x140141a8b  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x140141a90  nop
0x140141a91  mov     dword ptr [rsp+2D8h+var_268], r15d
0x140141a96  xorps   xmm0, xmm0
0x140141a99  movups  [rsp+2D8h+var_288], xmm0
0x140141a9e  movups  [rsp+2D8h+var_278], xmm0
0x140141aa3  lea     r8, aAcc; "acc"
0x140141aaa  lea     rdx, [rsp+2D8h+var_288]
0x140141aaf  lea     rcx, [rsp+2D8h+var_70]
0x140141ab7  call    ??$find@AEAY03$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA?AV?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@12@AEAY03$$CBD@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::find<char const (&)[4],0>(char const (&)[4])
0x140141abc  lea     r8, [rsp+2D8h+var_70]
0x140141ac4  mov     [rsp+2D8h+var_2A8], r8
0x140141ac9  xorps   xmm0, xmm0
0x140141acc  movdqu  [rsp+2D8h+var_2A0], xmm0
0x140141ad2  xorps   xmm1, xmm1
0x140141ad5  movdqu  [rsp+2D8h+var_2A0+8], xmm1
0x140141adb  mov     [rsp+2D8h+var_290], r14
0x140141ae0  movzx   ecx, byte ptr [r8]
0x140141ae4  mov     esi, 5
0x140141ae9  cmp     ecx, esi
0x140141aeb  ja      short loc_140141B30
0x140141aed  jz      short loc_140141B30
0x140141aef  mov     edx, ecx
0x140141af1  test    ecx, ecx
0x140141af3  jz      short loc_140141B30
0x140141af5  sub     edx, 1
0x140141af8  jz      short loc_140141B1C
0x140141afa  sub     edx, 1
0x140141afd  jz      short loc_140141B0D
0x140141aff  test    ecx, ecx
0x140141b01  jz      short loc_140141B30
0x140141b03  sub     ecx, 1
0x140141b06  jz      short loc_140141B1C
0x140141b08  sub     ecx, 1
0x140141b0b  jnz     short loc_140141B30
0x140141b0d  mov     rax, [r8+8]
0x140141b11  mov     rcx, [rax+8]
0x140141b15  mov     qword ptr [rsp+2D8h+var_2A0+8], rcx
0x140141b1a  jmp     short loc_140141B28
0x140141b1c  mov     rax, [r8+8]
0x140141b20  mov     rcx, [rax]
0x140141b23  mov     qword ptr [rsp+2D8h+var_2A0], rcx
0x140141b28  mov     r12d, 1
0x140141b2e  jmp     short loc_140141B3B
0x140141b30  mov     r12d, 1
0x140141b36  mov     [rsp+2D8h+var_290], r12
0x140141b3b  lea     rdx, [rsp+2D8h+var_288]
0x140141b40  lea     rcx, [rsp+2D8h+var_2A8]
0x140141b45  call    ??$?9V?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@$0A@@?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBA_NAEBV0123@@Z; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>,0>(nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>> const &)
0x140141b4a  test    al, al
0x140141b4c  jz      short loc_140141B7C
0x140141b4e  lea     rcx, [rsp+2D8h+var_288]
0x140141b53  call    ??D?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@23@XZ; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator*(void)
0x140141b58  mov     al, [rax]
0x140141b5a  cmp     al, sil
0x140141b5d  jz      short loc_140141B66
0x140141b5f  sub     al, 6
0x140141b61  cmp     al, r12b
0x140141b64  ja      short loc_140141B7C
0x140141b66  lea     rcx, [rsp+2D8h+var_288]
0x140141b6b  call    ??D?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@23@XZ; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator*(void)
0x140141b70  mov     rcx, rax
0x140141b73  call    ??$get@HH@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEBAHXZ; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::get<int,int>(void)
0x140141b78  mov     dword ptr [rsp+2D8h+var_268], eax
0x140141b7c  mov     [rsp+2D8h+var_260], r15d
0x140141b81  xorps   xmm0, xmm0
0x140141b84  movups  [rsp+2D8h+var_288], xmm0
0x140141b89  movups  [rsp+2D8h+var_278], xmm0
0x140141b8e  lea     r8, aRej; "rej"
0x140141b95  lea     rdx, [rsp+2D8h+var_288]
0x140141b9a  lea     rcx, [rsp+2D8h+var_70]
0x140141ba2  call    ??$find@AEAY03$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA?AV?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@12@AEAY03$$CBD@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::find<char const (&)[4],0>(char const (&)[4])
0x140141ba7  lea     r8, [rsp+2D8h+var_70]
0x140141baf  mov     [rsp+2D8h+var_2A8], r8
0x140141bb4  xorps   xmm0, xmm0
0x140141bb7  movdqu  [rsp+2D8h+var_2A0], xmm0
0x140141bbd  xorps   xmm1, xmm1
0x140141bc0  movdqu  [rsp+2D8h+var_2A0+8], xmm1
0x140141bc6  mov     [rsp+2D8h+var_290], r14
0x140141bcb  movzx   ecx, byte ptr [r8]
0x140141bcf  cmp     ecx, esi
0x140141bd1  ja      short loc_140141C10
0x140141bd3  jz      short loc_140141C10
0x140141bd5  mov     edx, ecx
0x140141bd7  test    ecx, ecx
0x140141bd9  jz      short loc_140141C10
0x140141bdb  sub     edx, 1
0x140141bde  jz      short loc_140141C02
0x140141be0  sub     edx, 1
0x140141be3  jz      short loc_140141BF3
0x140141be5  test    ecx, ecx
0x140141be7  jz      short loc_140141C10
0x140141be9  sub     ecx, 1
0x140141bec  jz      short loc_140141C02
0x140141bee  sub     ecx, 1
0x140141bf1  jnz     short loc_140141C10
0x140141bf3  mov     rax, [r8+8]
0x140141bf7  mov     rcx, [rax+8]
0x140141bfb  mov     qword ptr [rsp+2D8h+var_2A0+8], rcx
0x140141c00  jmp     short loc_140141C15
0x140141c02  mov     rax, [r8+8]
0x140141c06  mov     rcx, [rax]
0x140141c09  mov     qword ptr [rsp+2D8h+var_2A0], rcx
0x140141c0e  jmp     short loc_140141C15
0x140141c10  mov     [rsp+2D8h+var_290], r12
0x140141c15  lea     rdx, [rsp+2D8h+var_288]
0x140141c1a  lea     rcx, [rsp+2D8h+var_2A8]
0x140141c1f  call    ??$?9V?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@$0A@@?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBA_NAEBV0123@@Z; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>,0>(nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>> const &)
0x140141c24  test    al, al
0x140141c26  jz      short loc_140141C56
0x140141c28  lea     rcx, [rsp+2D8h+var_288]
0x140141c2d  call    ??D?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@23@XZ; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator*(void)
0x140141c32  mov     al, [rax]
0x140141c34  cmp     al, sil
0x140141c37  jz      short loc_140141C40
0x140141c39  sub     al, 6
0x140141c3b  cmp     al, r12b
0x140141c3e  ja      short loc_140141C56
0x140141c40  lea     rcx, [rsp+2D8h+var_288]
0x140141c45  call    ??D?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@23@XZ; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator*(void)
0x140141c4a  mov     rcx, rax
0x140141c4d  call    ??$get@HH@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEBAHXZ; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::get<int,int>(void)
0x140141c52  mov     [rsp+2D8h+var_260], eax
0x140141c56  xorps   xmm0, xmm0
0x140141c59  movups  [rsp+2D8h+var_250], xmm0
0x140141c61  movups  [rsp+2D8h+var_240], xmm0
0x140141c69  lea     r8, aEfi; "efi"
0x140141c70  lea     rdx, [rsp+2D8h+var_250]
0x140141c78  lea     rcx, [rsp+2D8h+var_70]
0x140141c80  call    ??$find@AEAY03$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA?AV?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@12@AEAY03$$CBD@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::find<char const (&)[4],0>(char const (&)[4])
0x140141c85  lea     r8, [rsp+2D8h+var_70]
0x140141c8d  mov     [rsp+2D8h+var_2A8], r8
0x140141c92  xorps   xmm0, xmm0
0x140141c95  movdqu  [rsp+2D8h+var_2A0], xmm0
0x140141c9b  xorps   xmm1, xmm1
0x140141c9e  movdqu  [rsp+2D8h+var_2A0+8], xmm1
0x140141ca4  mov     [rsp+2D8h+var_290], r14
0x140141ca9  movzx   ecx, byte ptr [r8]
0x140141cad  cmp     ecx, esi
0x140141caf  ja      short loc_140141CEE
0x140141cb1  jz      short loc_140141CEE
0x140141cb3  mov     edx, ecx
0x140141cb5  test    ecx, ecx
0x140141cb7  jz      short loc_140141CEE
0x140141cb9  sub     edx, 1
0x140141cbc  jz      short loc_140141CE0
0x140141cbe  sub     edx, 1
0x140141cc1  jz      short loc_140141CD1
0x140141cc3  test    ecx, ecx
0x140141cc5  jz      short loc_140141CEE
0x140141cc7  sub     ecx, 1
0x140141cca  jz      short loc_140141CE0
0x140141ccc  sub     ecx, 1
0x140141ccf  jnz     short loc_140141CEE
0x140141cd1  mov     rax, [r8+8]
0x140141cd5  mov     rcx, [rax+8]
0x140141cd9  mov     qword ptr [rsp+2D8h+var_2A0+8], rcx
0x140141cde  jmp     short loc_140141CF3
0x140141ce0  mov     rax, [r8+8]
0x140141ce4  mov     rcx, [rax]
0x140141ce7  mov     qword ptr [rsp+2D8h+var_2A0], rcx
0x140141cec  jmp     short loc_140141CF3
0x140141cee  mov     [rsp+2D8h+var_290], r12
0x140141cf3  lea     rdx, [rsp+2D8h+var_250]
0x140141cfb  lea     rcx, [rsp+2D8h+var_2A8]
0x140141d00  call    ??$?9V?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@$0A@@?$iter_impl@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEBA_NAEBV0123@@Z; nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>,0>(nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>> const &)
0x140141d05  test    al, al
0x140141d07  jz      loc_140141FE7
0x140141d0d  xorps   xmm0, xmm0
0x140141d10  movups  [rsp+2D8h+var_288], xmm0
0x140141d15  mov     qword ptr [rsp+2D8h+var_278], r15
0x140141d1a  mov     qword ptr [rsp+2D8h+var_278+8], r15
0x140141d1f  mov     r8d, 3
0x140141d25  lea     rdx, aEfi; "efi"
0x140141d2c  lea     rcx, [rsp+2D8h+var_288]
0x140141d31  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140141d36  lea     rdx, [rsp+2D8h+var_288]
0x140141d3b  lea     rcx, [rsp+2D8h+var_70]
0x140141d43  call    ??A?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAAEAV012@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::operator[](std::string)
0x140141d48  mov     rdi, rax
0x140141d4b  mov     [rsp+2D8h+var_2A8], rax
0x140141d50  xorps   xmm0, xmm0
0x140141d53  movdqu  [rsp+2D8h+var_2A0], xmm0
0x140141d59  xorps   xmm1, xmm1
0x140141d5c  movdqu  [rsp+2D8h+var_2A0+8], xmm1
0x140141d62  mov     rbx, r14
0x140141d65  mov     [rsp+2D8h+var_290], rbx
0x140141d6a  movzx   ecx, byte ptr [rax]
0x140141d6d  cmp     ecx, esi
0x140141d6f  ja      short loc_140141DB5
0x140141d71  jz      short loc_140141DB5
  ... truncated ...
```

# asg::SemanticRegistry::from_json(nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar,std::allocator<uchar>>> const &,asg::SemanticRegistry::RegistrySchema &)

- ea: `0x180093d40`
- end: `0x180094dbc`
- name: `?from_json@SemanticRegistry@asg@@YAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@AEAVRegistrySchema@12@@Z`
- size: `4220`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180088100`

## callees

- `0x180006220`
- `0x180007a00`
- `0x180007c20`
- `0x180007ce0`
- `0x180007d30`
- `0x180007de0`
- `0x18003f6a0`
- `0x180074790`
- `0x180075080`
- `0x1800755e0`
- `0x1800756a0`
- `0x180075750`
- `0x180076000`
- `0x1800760d0`
- `0x1800761b0`
- `0x180076610`
- `0x180076fb0`
- `0x18007b3e0`
- `0x18007d640`
- `0x1800872b0`
- `0x180089c30`
- `0x18008fa70`
- `0x18008fd60`
- `0x18008fef0`
- `0x1800906b0`
- `0x180090f20`
- `0x180091030`
- `0x180091460`
- `0x180091670`
- `0x180091b50`
- `0x1800923d0`
- `0x180093be0`
- `0x180093cc0`
- `0x180093d40`
- `0x180098100`
- `0x180099be0`
- `0x180099ee0`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180242860`
- `0x180242ca0`

## string_xrefs

- `0x18009473c`: `vectorSpaceCombinationCoefficients`
- `0x180094787`: `vectorSpaceCombinationCoefficients`
- `0x180094832`: `vectorSpaceCombinationCoefficients`
- `0x180094b9f`: `vectorSpaceCombinationCoefficients`
- `0x18009433e`: `No sources in registry`
- `0x1800946cc`: `No vectorSpaces in registry`
- `0x1800947b8`: `No vectorSpaceCombinationCoefficients in registry`
- `0x180094a4e`: `cannot compare iterators of different containers`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
char __fastcall asg::SemanticRegistry::from_json(__int64 *a1, __int64 *a2)
{
  __int64 *v2; // r13
  __int64 *v3; // r14
  unsigned int v4; // esi
  __int64 **v5; // rbx
  __int64 **v6; // rax
  __int64 *v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rbx
  __int64 *v10; // r13
  unsigned __int64 v11; // rdi
  __int64 *i; // rbx
  __int64 *v13; // r14
  unsigned __int64 v14; // rsi
  __int64 **v15; // r15
  __int64 *v16; // r12
  bool v17; // zf
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 *v20; // r13
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r13
  struct asg::SemanticRegistry::SourceDescriptionSchema *v24; // rax
  _QWORD **v25; // rcx
  _QWORD *v26; // rcx
  _QWORD *v27; // r13
  _QWORD **v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v30; // r13
  __int64 *v31; // rax
  __int64 *v32; // rcx
  __int64 **v33; // rbx
  __int64 **v34; // rax
  __int64 *v35; // rdi
  __int64 v36; // r8
  __int64 v37; // rbx
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  _QWORD **v40; // rcx
  _QWORD *v41; // rcx
  _QWORD *v42; // rbx
  __int64 v43; // rax
  __int64 *v44; // rsi
  __int64 *j; // rbx
  unsigned __int64 v46; // rdi
  _QWORD *v47; // rcx
  size_t v48; // r8
  int v49; // eax
  _QWORD *v50; // rcx
  unsigned __int64 v51; // rbx
  size_t v52; // r8
  int v53; // eax
  char result; // al
  __int64 **v55; // rcx
  __int64 *v56; // rbx
  __int64 v57; // r8
  __int64 *v58; // rbx
  __int64 v59; // r8
  _BYTE *v60; // r14
  __int64 v61; // r12
  __int64 v62; // rsi
  _BYTE *v63; // r15
  __int64 *k; // rbx
  bool v65; // zf
  _BYTE *v66; // rcx
  __int64 v67; // rdx
  __int64 *v68; // rax
  __int64 *v69; // rcx
  __int64 v70; // rax
  _QWORD *v71; // rax
  __int64 v72; // rax
  _QWORD *v73; // rax
  __int64 v74; // rax
  _QWORD *v75; // rax
  __int64 *v76; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v77; // [rsp+30h] [rbp-D0h]
  __int64 *v78; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v79[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 Src; // [rsp+70h] [rbp-90h] BYREF
  __int128 v81; // [rsp+80h] [rbp-80h]
  __int64 *v82; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+98h] [rbp-68h] BYREF
  char v84; // [rsp+B8h] [rbp-48h]
  __int64 *v85; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v86[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v87[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v88[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v89; // [rsp+200h] [rbp+100h] BYREF
  __int128 v90; // [rsp+210h] [rbp+110h]
  __int128 v91; // [rsp+220h] [rbp+120h]
  __int128 v92; // [rsp+230h] [rbp+130h] BYREF
  __int128 v93; // [rsp+240h] [rbp+140h]
  __int128 v94; // [rsp+250h] [rbp+150h] BYREF
  __int128 v95; // [rsp+260h] [rbp+160h]
  __int128 v96; // [rsp+270h] [rbp+170h] BYREF
  __int128 v97; // [rsp+280h] [rbp+180h]
  __int128 v98; // [rsp+290h] [rbp+190h]
  __int128 v99; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v100; // [rsp+2B0h] [rbp+1B0h]
  __int128 v101; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v102; // [rsp+2D0h] [rbp+1D0h]

  v2 = a2;
  v78 = a2;
  v3 = a1;
  v82 = a1;
  v4 = 0;
  v77 = 0;
  if ( *(_BYTE *)a1 != 1
    || (v5 = (__int64 **)a1[1],
        v6 = std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find<char [8],std::less<void>,0>(
               v5,
               &v85,
               "sources"),
        v7 = *v5,
        *v6 == *v5) )
  {
    BYTE8(v79[1]) = 0;
    Src = v79[0];
    v81 = v79[1];
    asg::details::_asg_Log<std::integral_constant<bool,0>>(pExceptionObject, &Src, 3, L"No sources in registry");
    if ( v84 )
      std::basic_string<char16_t>::_Tidy_deallocate(pExceptionObject);
  }
  else
  {
    v76 = 0;
    std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find<char [8],std::less<void>,0>(
      v5,
      &v76,
      "sources");
    if ( v76 == v7 )
    {
      v70 = std::string::string(v79, "sources", v8);
      v71 = nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[6],std::string,char const (&)[12]>(
              &Src,
              (__int64)"key '",
              v70,
              (__int64)"' not found");
      nlohmann::json_abi_v3_11_2::detail::out_of_range::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
        (__int64)pExceptionObject,
        403,
        (__int64)v71);
      throw (nlohmann::json_abi_v3_11_2::detail::out_of_range *)pExceptionObject;
    }
    v76 += 8;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>::begin(
      &v76,
      &v89);
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    v102 = 0;
    nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>::end(
      &v76,
      &v96);
    if ( nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator!=<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>,0>(
           (__int64)&v89,
           &v96) )
    {
      while ( 1 )
      {
        v9 = nlohmann::json_abi_v3_11_2::detail::get<0,nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>,0>((char **)&v89);
        v10 = (__int64 *)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator*(&v89);
        v85 = v10;
        LODWORD(v76) = asg::SemanticRegistry::StringToSourceName(v9);
        *((_QWORD *)&Src + 1) = 0;
        v81 = 0;
        v11 = 0x8000000000000000uLL;
        switch ( *(_BYTE *)v10 )
        {
          case 0:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 8:
          case 9:
            switch ( *(_BYTE *)v10 )
            {
              case 0:
                v11 = 1;
                goto LABEL_11;
              case 1:
                goto LABEL_8;
              case 2:
                goto LABEL_9;
              default:
                goto LABEL_10;
            }
          case 1:
LABEL_8:
            i = **(__int64 ***)v10[1];
            goto LABEL_12;
          case 2:
LABEL_9:
            v13 = *(__int64 **)v10[1];
            i = (__int64 *)*((_QWORD *)&Src + 1);
            goto LABEL_13;
          default:
LABEL_10:
            v11 = 0;
LABEL_11:
            i = (__int64 *)*((_QWORD *)&Src + 1);
LABEL_12:
            v13 = (__int64 *)v81;
LABEL_13:
            *((_QWORD *)&v79[0] + 1) = 0;
            v79[1] = 0;
            v14 = 0x8000000000000000uLL;
            switch ( *(_BYTE *)v10 )
            {
              case 0:
              case 3:
              case 4:
              case 5:
              case 6:
              case 7:
              case 8:
              case 9:
                switch ( *(_BYTE *)v10 )
                {
                  case 1:
                    goto LABEL_15;
                  case 2:
                    goto LABEL_16;
                  default:
                    goto LABEL_17;
                }
              case 1:
LABEL_15:
                v15 = *(__int64 ***)v10[1];
                goto LABEL_18;
              case 2:
LABEL_16:
                v16 = *(__int64 **)(v10[1] + 8);
                v15 = (__int64 **)*((_QWORD *)&v79[0] + 1);
                goto LABEL_19;
              default:
LABEL_17:
                v14 = 1;
                v15 = (__int64 **)*((_QWORD *)&v79[0] + 1);
LABEL_18:
                v16 = *(__int64 **)&v79[1];
                break;
            }
            break;
        }
        while ( 1 )
        {
LABEL_19:
          switch ( *(_BYTE *)v10 )
          {
            case 1:
              v17 = i == (__int64 *)v15;
              break;
            case 2:
              v17 = v13 == v16;
              break;
            default:
              v17 = v11 == v14;
              break;
          }
          if ( v17 )
            break;
          switch ( *(_BYTE *)v10 )
          {
            case 0:
              std::string::string(v79, "cannot get value", 0x180000000uLL);
              nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
                (__int64)pExceptionObject,
                214,
                (__int64)v79);
              throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)pExceptionObject;
            case 1:
              v10 = i + 8;
              break;
            case 2:
              v10 = v13;
              break;
            default:
              if ( v11 )
              {
                std::string::string(v79, "cannot get value", 0x180000000uLL);
                nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
                  (__int64)pExceptionObject,
                  214,
                  (__int64)v79);
                throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)pExceptionObject;
              }
              return result;
          }
          memset(v86, 0, 192);
          std::basic_string<char8_t>::_Construct<1,char8_t const *>(v86, "1.0", 3);
          memset(&v86[2], 0, 32);
          std::basic_string<char8_t>::_Construct<1,char8_t const *>(&v86[2], "1970-01-01", 10);
          std::unordered_set<asg::Guid>::unordered_set<asg::Guid>(&v86[4]);
          std::unordered_set<asg::SemanticIndex::DiskAnn::QueryDistance>::unordered_set<asg::SemanticIndex::DiskAnn::QueryDistance>(&v86[8]);
          v77 |= 2u;
          asg::SemanticRegistry::from_json(v10, v86);
          v77 = v77 & 0xFFFFFFFC | 1;
          _mm_lfence();
          v18 = v78[11];
          v19 = *(_QWORD *)(v18
                          + 16
                          * (v78[14]
                           & (0x100000001B3LL
                            * (BYTE3(v76)
                             ^ (0x100000001B3LL
                              * (BYTE2(v76)
                               ^ (0x100000001B3LL
                                * (BYTE1(v76) ^ (0x100000001B3LL * ((unsigned __int8)v76 ^ 0xCBF29CE484222325uLL)))))))))
                          + 8);
          if ( v19 != v78[9] )
          {
            if ( (_DWORD)v76 == *(_DWORD *)(v19 + 16) )
            {
LABEL_31:
              v20 = v78 + 8;
              goto LABEL_33;
            }
            while ( v19 != *(_QWORD *)(v18
                                     + 16
                                     * (v78[14]
                                      & (0x100000001B3LL
                                       * (BYTE3(v76)
                                        ^ (0x100000001B3LL
                                         * (BYTE2(v76)
                                          ^ (0x100000001B3LL
                                           * (BYTE1(v76)
                                            ^ (0x100000001B3LL * ((unsigned __int8)v76 ^ 0xCBF29CE484222325uLL)))))))))) )
            {
              v19 = *(_QWORD *)(v19 + 8);
              if ( (_DWORD)v76 == *(_DWORD *)(v19 + 16) )
                goto LABEL_31;
            }
          }
          v20 = v78 + 8;
          v21 = std::_Hash<std::_Umap_traits<enum asg::SemanticRegistry::SourceName,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>,std::_Uhash_compare<enum asg::SemanticRegistry::SourceName,std::hash<enum asg::SemanticRegistry::SourceName>,std::equal_to<enum asg::SemanticRegistry::SourceName>>,std::allocator<std::pair<enum asg::SemanticRegistry::SourceName const,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>>>,0>>::_Try_emplace<enum asg::SemanticRegistry::SourceName const &,>(
                  (__int64)(v78 + 8),
                  (__int64)v88,
                  (unsigned __int8 *)&v76);
          std::vector<asg::SemanticRegistry::SourceDescriptionSchema>::_Assign_counted_range<asg::SemanticRegistry::SourceDescriptionSchema const *>(
            (asg::SemanticRegistry::SourceDescriptionSchema **)(*(_QWORD *)v21 + 24LL),
            0,
            0);
LABEL_33:
          v22 = std::_Hash<std::_Umap_traits<enum asg::SemanticRegistry::SourceName,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>,std::_Uhash_compare<enum asg::SemanticRegistry::SourceName,std::hash<enum asg::SemanticRegistry::SourceName>,std::equal_to<enum asg::SemanticRegistry::SourceName>>,std::allocator<std::pair<enum asg::SemanticRegistry::SourceName const,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>>>,0>>::_Try_emplace<enum asg::SemanticRegistry::SourceName const &,>(
                  (__int64)v20,
                  (__int64)v87,
                  (unsigned __int8 *)&v76);
          v23 = *(_QWORD *)v22;
          v24 = *(struct asg::SemanticRegistry::SourceDescriptionSchema **)(*(_QWORD *)v22 + 32LL);
          if ( v24 == *(struct asg::SemanticRegistry::SourceDescriptionSchema **)(v23 + 40) )
          {
            std::vector<asg::SemanticRegistry::SourceDescriptionSchema>::_Emplace_reallocate<asg::SemanticRegistry::SourceDescriptionSchema const &>(
              (struct asg::SemanticRegistry::SourceDescriptionSchema **)(v23 + 24),
              v24,
              (const struct asg::SemanticRegistry::SourceDescriptionSchema *)v86);
          }
          else
          {
            asg::SemanticRegistry::SourceDescriptionSchema::SourceDescriptionSchema(
              v24,
              (const struct asg::SemanticRegistry::SourceDescriptionSchema *)v86);
            *(_QWORD *)(v23 + 32) += 192LL;
          }
          std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v86[9] + 8);
          v25 = (_QWORD **)*((_QWORD *)&v86[8] + 1);
          **(_QWORD **)(*((_QWORD *)&v86[8] + 1) + 8LL) = 0;
          v26 = *v25;
          if ( v26 )
          {
            do
            {
              v27 = (_QWORD *)*v26;
              operator delete(v26);
              v26 = v27;
            }
            while ( v27 );
          }
          operator delete(*((void **)&v86[8] + 1));
          std::vector<std::pair<unsigned int,unsigned int>>::_Tidy((char *)&v86[5] + 8);
          v28 = (_QWORD **)*((_QWORD *)&v86[4] + 1);
          **(_QWORD **)(*((_QWORD *)&v86[4] + 1) + 8LL) = 0;
          v29 = *v28;
          if ( v29 )
          {
            do
            {
              v30 = (_QWORD *)*v29;
              operator delete(v29);
              v29 = v30;
            }
            while ( v30 );
          }
          operator delete(*((void **)&v86[4] + 1));
          std::basic_string<char8_t>::_Tidy_deallocate(&v86[2]);
          std::basic_string<char8_t>::_Tidy_deallocate(v86);
          v10 = v85;
          switch ( *(_BYTE *)v85 )
          {
            case 1:
              v31 = i;
              i = (__int64 *)i[2];
              if ( *((_BYTE *)i + 25) )
              {
                for ( i = (__int64 *)v31[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
                {
                  if ( v31 != (__int64 *)i[2] )
                    break;
                  v31 = i;
                }
              }
              else
              {
                v32 = (__int64 *)*i;
                if ( !*(_BYTE *)(*i + 25) )
                {
                  do
                  {
                    i = v32;
                    v32 = (__int64 *)*v32;
                  }
                  while ( !*((_BYTE *)v32 + 25) );
                }
              }
              break;
            case 2:
              v13 += 2;
              break;
            default:
              ++v11;
              break;
          }
        }
        nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator++(&v89);
        *(_QWORD *)&v91 = v91 + 1;
        if ( !nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator!=<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>,0>(
                (__int64)&v89,
                &v96) )
        {
          v2 = v78;
          v4 = v77;
          v3 = v82;
          break;
        }
      }
    }
    std::basic_string<char8_t>::_Tidy_deallocate(&v101);
    std::basic_string<char8_t>::_Tidy_deallocate(&v99);
    std::basic_string<char8_t>::_Tidy_deallocate(&v94);
    std::basic_string<char8_t>::_Tidy_deallocate(&v92);
  }
  if ( *(_BYTE *)v3 != 1
    || (v33 = (__int64 **)v3[1],
        v34 = std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find<char [13],std::less<void>,0>(
                v33,
                &v82,
                (__int64)"vectorSpaces"),
        v35 = *v33,
        *v34 == *v33) )
  {
    BYTE8(v79[1]) = 0;
    Src = v79[0];
    v81 = v79[1];
    asg::details::_asg_Log<std::integral_constant<bool,0>>(pExceptionObject, &Src, 3, L"No vectorSpaces in registry");
    if ( v84 )
      std::basic_string<char16_t>::_Tidy_deallocate(pExceptionObject);
  }
  else
  {
    v78 = 0;
    std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find<char [13],std::less<void>,0>(
      v33,
      &v78,
      (__int64)"vectorSpaces");
    if ( v78 == v35 )
    {
      v72 = std::string::string(v79, "vectorSpaces", v36);
      v73 = nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[6],std::string,char const (&)[12]>(
              &Src,
              (__int64)"key '",
              v72,
              (__int64)"' not found");
      nlohmann::json_abi_v3_11_2::detail::out_of_range::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
        (__int64)pExceptionObject,
        403,
        (__int64)v73);
      throw (nlohmann::json_abi_v3_11_2::detail::out_of_range *)pExceptionObject;
    }
    v78 += 8;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>::begin(
      &v78,
      &v89);
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    v102 = 0;
    nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>>::end(
      &v78,
      &v96);
    for ( ;
          nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator!=<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>,0>(
            (__int64)&v89,
            &v96);
          *(_QWORD *)&v91 = v91 + 1 )
    {
      nlohmann::json_abi_v3_11_2::detail::get<0,nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>,0>((char **)&v89);
      v37 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator*(&v89);
      memset(v86, 0, 0xF8u);
      *(_QWORD *)&v86[0] = 1;
      *(_OWORD *)((char *)v86 + 8) = *(_OWORD *)asg::NewGuid(v87);
      std::unordered_set<asg::Guid>::unordered_set<asg::Guid>((char *)&v86[1] + 8);
      *((_QWORD *)&v86[5] + 1) = 0;
      LODWORD(v86[6]) = 0;
      v82 = (__int64 *)&v86[6] + 1;
      DWORD2(v86[6]) = 0;
      v86[7] = 0;
      v38 = operator new(0x80u);
      *v38 = v38;
      v38[1] = v38;
      *(_QWORD *)&v86[7] = v38;
      memset(&v86[8], 0, 24);
      *((_QWORD *)&v86[9] + 1) = 7;
      *(_QWORD *)&v86[10] = 8;
      DWORD2(v86[6]) = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
        &v86[8],
        16,
        v38);
      LOBYTE(v86[11]) = 0;
      v82 = (__int64 *)&v86[11] + 1;
      DWORD2(v86[11]) = 0;
      v86[12] = 0;
      v39 = operator new(0x40u);
      *v39 = v39;
      v39[1] = v39;
      *(_QWORD *)&v86[12] = v39;
      memset(&v86[13], 0, 24);
      *((_QWORD *)&v86[14] + 1) = 7;
      *(_QWORD *)&v86[15] = 8;
      DWORD2(v86[11]) = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
        &v86[13],
        16,
        v39);
      asg::SemanticRegistry::from_json(v37, v86);
      v4 = v4 & 0xFFFFFFF3 | 4;
      asg::SemanticRegistry::RegistrySchema::InsertVectorSpace(
        (asg::SemanticRegistry::RegistrySchema *)v2,
        (const struct asg::SemanticRegistry::VectorSpaceSchema *)v86);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v86[13]);
      std::list<std::pair<std::string const,asg::SemanticRegistry::RecallSensitivityThresholds>>::~list<std::pair<std::string const,asg::SemanticRegistry::RecallSensitivityThresholds>>(&v86[12]);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v86[8]);
      std::list<asg::SemanticRegistry::ModelSchema>::~list<asg::SemanticRegistry::ModelSchema>(&v86[7]);
      std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v86[3]);
      v40 = *(_QWORD ***)&v86[2];
      **(_QWORD **)(*(_QWORD *)&v86[2] + 8LL) = 0;
      v41 = *v40;
      if ( v41 )
      {
        do
        {
          v42 = (_QWORD *)*v41;
          operator delete(v41);
          v41 = v42;
        }
        while ( v42 );
      }
      std::_Deallocate<16>(*(_QWORD *)&v86[2], 32);
      nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::operator++(&v89);
    }
    std::basic_string<char8_t>::_Tidy_deallocate(&v101);
    std::basic_string<char8_t>::_Tidy_deallocate(&v99);
    std::basic_string<char8_t>::_Tidy_deallocate(&v94);
    std::basic_string<char8_t>::_Tidy_deallocate(&v92);
  }
  if ( *(_BYTE *)v3 != 1 )
    goto LABEL_83;
  v43 = v3[1];
  v44 = *(__int64 **)v43;
  for ( j = *(__int64 **)(*(_QWORD *)v43 + 8LL); !*((_BYTE *)j + 25); j = (__int64 *)*j )
  {
    v46 = j[6];
    v47 = j + 4;
    if ( (unsigned __int64)j[7] > 0xF )
      v47 = (_QWORD *)*v47;
    v48 = j[6];
    if ( v46 > 0x22 )
      v48 = 34;
    v49 = memcmp(v47, "vectorSpaceCombinationCoefficients", v48);
    if ( v49 )
    {
      if ( v49 < 0 )
      {
LABEL_87:
        j += 2;
        continue;
      }
    }
    else if ( v46 < 0x22 )
    {
      goto LABEL_87;
    }
    v44 = j;
  }
  if ( *((_BYTE *)v44 + 25) )
    goto LABEL_83;
  v50 = v44 + 4;
  v51 = v44[6];
  if ( (unsigned __int64)v44[7] > 0xF )
    v50 = (_QWORD *)*v50;
  v52 = v44[6];
  if ( v51 > 0x22 )
    v52 = 34;
  v53 = memcmp(v50, "vectorSpaceCombinationCoefficients", v52);
  if ( v53 )
  {
    if ( v53 >= 0 )
      goto LABEL_83;
  }
  else if ( v51 > 0x22 )
  {
    goto LABEL_83;
  }
  v55 = (__int64 **)v3[1];
  v56 = *v55;
  if ( v44 == *v55 )
  {
LABEL_83:
    BYTE8(v79[1]) = 0;
    Src = v79[0];
    v81 = v79[1];
    result = asg::details::_asg_Log<std::integral_constant<bool,0>>(
               pExceptionObject,
               &Src,
               3,
               L"No vectorSpaceCombinationCoefficients in registry");
    if ( v84 )
      return std::basic_string<char16_t>::_Tidy_deallocate(pExceptionObject);
    return result;
  }
  v78 = 0;
  std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find<char [13],std::less<void>,0>(
    v55,
    &v78,
    (__int64)"vectorSpaceCombinationCoefficients");
  if ( v78 == v56 )
  {
    v74 = std::string::string(v79, "vectorSpaceCombinationCoefficients", v57);
    v75 = nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[6],std::string,char const (&)[12]>(
            &Src,
            (__int64)"key '",
            v74,
            (__int64)"' not found");
    nlohmann::json_abi_v3_11_2::detail::out_of_range::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
      (__int64)pExceptionObject,
      403,
      (__int64)v75);
    throw (nlohmann::json_abi_v3_11_2::detail::out_of_range *)pExceptionObject;
  }
  v58 = v78 + 8;
  memset(v79, 0, 32);
  nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::begin(
    v78 + 8,
    v79);
  Src = 0;
  v81 = 0;
  nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::end(
    v58,
    &Src);
  v60 = *(_BYTE **)&v79[0];
  if ( *(_QWORD *)&v79[0] != (_QWORD)Src )
  {
    std::string::string(v79, "cannot compare iterators of different containers", v59);
    nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
      (__int64)pExceptionObject,
      212,
      (__int64)v79);
    throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)pExceptionObject;
  }
  v61 = *((_QWORD *)&v81 + 1);
  v62 = *((_QWORD *)&v79[1] + 1);
  v63 = *(_BYTE **)&v79[1];
  k = (__int64 *)*((_QWORD *)&v79[0] + 1);
  while ( 1 )
  {
    switch ( *v60 )
    {
      case 1:
        v65 = k == *((__int64 **)&Src + 1);
        break;
      case 2:
        v65 = v63 == (_BYTE *)v81;
        break;
      default:
        v65 = v62 == v61;
        break;
    }
    result = !v65;
    if ( v65 )
      break;
    switch ( *v60 )
    {
      case 0:
        std::string::string(v79, "cannot get value", 0x180000000uLL);
        nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
          (__int64)pExceptionObject,
          214,
          (__int64)v79);
        throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)pExceptionObject;
      case 1:
        v66 = k + 8;
        break;
      case 2:
        v66 = v63;
        break;
      default:
        if ( v62 )
        {
          std::string::string(v79, "cannot get value", 0x180000000uLL);
          nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
            (__int64)pExceptionObject,
            214,
            (__int64)v79);
          throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)pExceptionObject;
        }
        v66 = v60;
        break;
    }
    memset(v79, 0, 40);
    asg::SemanticRegistry::from_json(v66, v79);
    v67 = v2[17];
    if ( v67 == v2[18] )
    {
      std::vector<asg::SemanticRegistry::VectorSpaceSimilarityScoreMergeCoefficients>::_Emplace_reallocate<asg::SemanticRegistry::VectorSpaceSimilarityScoreMergeCoefficients>(
        v2 + 16,
        (_BYTE *)v67,
        (__int64)v79);
    }
    else
    {
      *(_OWORD *)v67 = v79[0];
      *(_OWORD *)(v67 + 16) = v79[1];
      *(_QWORD *)(v67 + 32) = *(_QWORD *)&v79[2];
      v2[17] += 40;
    }
    switch ( *v60 )
    {
      case 1:
        v68 = k;
        k = (__int64 *)k[2];
        if ( *((_BYTE *)k + 25) )
        {
          for ( k = (__int64 *)v68[1]; !*((_BYTE *)k + 25); k = (__int64 *)k[1] )
          {
            if ( v68 != (__int64 *)k[2] )
              break;
            v68 = k;
          }
        }
        else
        {
          v69 = (__int64 *)*k;
          if ( !*(_BYTE *)(*k + 25) )
          {
            do
            {
              k = v69;
              v69 = (__int64 *)*v69;
            }
            while ( !*((_BYTE *)v69 + 25) );
          }
        }
        break;
      case 2:
        v63 += 16;
        break;
      default:
        ++v62;
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180093d40  mov     [rsp-8+arg_10], rbx
0x180093d45  push    rbp
0x180093d46  push    rsi
0x180093d47  push    rdi
0x180093d48  push    r12
0x180093d4a  push    r13
0x180093d4c  push    r14
0x180093d4e  push    r15
0x180093d50  lea     rbp, [rsp-1F0h]
0x180093d58  sub     rsp, 2F0h
0x180093d5f  mov     rax, cs:__security_cookie
0x180093d66  xor     rax, rsp
0x180093d69  mov     [rbp+220h+var_40], rax
0x180093d70  mov     r13, rdx
0x180093d73  mov     [rsp+320h+var_2E8], rdx
0x180093d78  mov     r14, rcx
0x180093d7b  mov     [rbp+220h+var_290], rcx
0x180093d7f  xor     r12d, r12d
0x180093d82  mov     esi, r12d
0x180093d85  mov     [rsp+320h+var_2F0], r12d
0x180093d8a  mov     [rsp+320h+var_300], r12d
0x180093d8f  cmp     byte ptr [rcx], 1
0x180093d92  jnz     loc_180094326
0x180093d98  mov     rbx, [rcx+8]
0x180093d9c  lea     r8, aSources; "sources"
0x180093da3  lea     rdx, [rbp+220h+var_250]
0x180093da7  mov     rcx, rbx
0x180093daa  call    ??$find@$$BY07DU?$less@X@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@std@@@std@@@1@AEAY07$$CBD@Z; std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>>>,0>>::find<char [8],std::less<void>,0>(char const (&)[8])
0x180093daf  mov     rdi, [rbx]
0x180093db2  cmp     [rax], rdi
0x180093db5  jz      loc_180094326
0x180093dbb  mov     [rsp+320h+var_2F8], r12
0x180093dc0  lea     r8, aSources; "sources"
0x180093dc7  lea     rdx, [rsp+320h+var_2F8]
0x180093dcc  mov     rcx, rbx
0x180093dcf  call    ??$find@$$BY07DU?$less@X@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@std@@@std@@@1@AEAY07$$CBD@Z; std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>>>,0>>::find<char [8],std::less<void>,0>(char const (&)[8])
0x180093dd4  mov     rax, [rsp+320h+var_2F8]
0x180093dd9  cmp     rax, rdi
0x180093ddc  jz      loc_180094A87
0x180093de2  add     rax, 40h ; '@'
0x180093de6  mov     [rsp+320h+var_2F8], rax
0x180093deb  xorps   xmm0, xmm0
0x180093dee  movups  [rbp+220h+var_120], xmm0
0x180093df5  movups  [rbp+220h+var_110], xmm0
0x180093dfc  movups  [rbp+220h+var_100], xmm0
0x180093e03  movups  [rbp+220h+var_F0], xmm0
0x180093e0a  movups  [rbp+220h+var_E0], xmm0
0x180093e11  movups  [rbp+220h+var_D0], xmm0
0x180093e18  movups  [rbp+220h+var_C0], xmm0
0x180093e1f  lea     rdx, [rbp+220h+var_120]
0x180093e26  lea     rcx, [rsp+320h+var_2F8]
0x180093e2b  call    ?begin@?$iteration_proxy@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@QEBA?AV?$iteration_proxy_value@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@@234@XZ; nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>>::begin(void)
0x180093e30  nop
0x180093e31  xorps   xmm0, xmm0
0x180093e34  movups  [rbp+220h+var_B0], xmm0
0x180093e3b  movups  [rbp+220h+var_A0], xmm0
0x180093e42  movups  [rbp+220h+var_90], xmm0
0x180093e49  movups  [rbp+220h+var_80], xmm0
0x180093e50  movups  [rbp+220h+var_70], xmm0
0x180093e57  movups  [rbp+220h+var_60], xmm0
0x180093e5e  movups  [rbp+220h+var_50], xmm0
0x180093e65  lea     rdx, [rbp+220h+var_B0]
0x180093e6c  lea     rcx, [rsp+320h+var_2F8]
0x180093e71  call    ?end@?$iteration_proxy@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@QEBA?AV?$iteration_proxy_value@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@@234@XZ; nlohmann::json_abi_v3_11_2::detail::iteration_proxy<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>>::end(void)
0x180093e76  nop
0x180093e77  lea     rdx, [rbp+220h+var_B0]
0x180093e7e  lea     rcx, [rbp+220h+var_120]
0x180093e85  call    ??$?9V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@$0A@@?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@QEBA_NAEBV0123@@Z; nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>::operator!=<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>,0>(nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const> const &)
0x180093e8a  test    al, al
0x180093e8c  jz      loc_1800942F3
0x180093e92  mov     r15, 8000000000000000h
0x180093e9c  lea     rcx, [rbp+220h+var_120]
0x180093ea3  call    ??$get@$0A@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@$0A@@detail@json_abi_v3_11_2@nlohmann@@YAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$iteration_proxy_value@V?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@@012@@Z; nlohmann::json_abi_v3_11_2::detail::get<0,nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>,0>(nlohmann::json_abi_v3_11_2::detail::iteration_proxy_value<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>> const &)
0x180093ea8  mov     rbx, rax
0x180093eab  lea     rcx, [rbp+220h+var_120]
0x180093eb2  call    ??D?$iter_impl@$$CBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@detail@json_abi_v3_11_2@nlohmann@@QEBAAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@23@XZ; nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const>::operator*(void)
0x180093eb7  mov     r13, rax
0x180093eba  mov     [rbp+220h+var_250], rax
0x180093ebe  mov     rcx, rbx
0x180093ec1  call    ?StringToSourceName@SemanticRegistry@asg@@YA?AW4SourceName@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; asg::SemanticRegistry::StringToSourceName(std::string const &)
0x180093ec6  mov     dword ptr [rsp+320h+var_2F8], eax
0x180093eca  xorps   xmm0, xmm0
0x180093ecd  movdqu  [rsp+320h+Src+8], xmm0
0x180093ed3  xorps   xmm1, xmm1
0x180093ed6  movdqu  [rbp+220h+var_2A0], xmm1
0x180093edb  mov     rdi, r15
0x180093ede  movzx   edx, byte ptr [r13+0]
0x180093ee3  lea     r8, cs:180000000h
0x180093eea  cmp     edx, 9; switch 10 cases
0x180093eed  ja      short def_180093EFD; jumptable 0000000180093EFD default case
0x180093eef  movsxd  rax, edx
0x180093ef2  mov     ecx, ds:(jpt_180093EFD - 180000000h)[r8+rax*4]
0x180093efa  add     rcx, r8
0x180093efd  jmp     rcx; switch jump
0x180093eff  mov     ecx, ds:(jpt_180093F0A - 180000000h)[r8+rdx*4]; jumptable 0000000180093EFD cases 0,3-9
0x180093f07  add     rcx, r8
0x180093f0a  jmp     rcx; switch jump
0x180093f0c  mov     edi, 1; jumptable 0000000180093F0A case 0
0x180093f11  jmp     short loc_180093F2F
0x180093f13  mov     rax, [r13+8]; jumptable 0000000180093EFD case 1
0x180093f17  mov     rbx, [rax]
0x180093f1a  mov     rbx, [rbx]
0x180093f1d  jmp     short loc_180093F34
0x180093f1f  mov     r14, [r13+8]; jumptable 0000000180093EFD case 2
0x180093f23  mov     r14, [r14]
0x180093f26  mov     rbx, qword ptr [rsp+320h+Src+8]
0x180093f2b  jmp     short loc_180093F38
0x180093f2d  xor     edi, edi; jumptable 0000000180093EFD default case
0x180093f2f  mov     rbx, qword ptr [rsp+320h+Src+8]
0x180093f34  mov     r14, qword ptr [rbp+220h+var_2A0]
0x180093f38  movdqu  [rsp+320h+var_2E0+8], xmm0
0x180093f3e  movdqu  [rsp+320h+var_2D0], xmm1
0x180093f44  mov     rsi, r15
0x180093f47  movzx   edx, byte ptr [r13+0]
0x180093f4c  cmp     edx, 9; switch 10 cases
0x180093f4f  ja      short def_180093F5F; jumptable 0000000180093F5F default case
0x180093f51  movsxd  rax, edx
0x180093f54  mov     ecx, ds:(jpt_180093F5F - 180000000h)[r8+rax*4]
0x180093f5c  add     rcx, r8
0x180093f5f  jmp     rcx; switch jump
0x180093f61  cmp     edx, 9; jumptable 0000000180093F5F cases 0,3-9
0x180093f64  ja      short def_180093F5F; jumptable 0000000180093F5F default case
0x180093f66  mov     ecx, ds:(jpt_180093F71 - 180000000h)[r8+rdx*4]
0x180093f6e  add     rcx, r8
0x180093f71  jmp     rcx; switch jump
0x180093f73  mov     r15, [r13+8]; jumptable 0000000180093F5F case 1
0x180093f77  mov     r15, [r15]
0x180093f7a  jmp     short loc_180093F96
0x180093f7c  mov     r12, [r13+8]; jumptable 0000000180093F5F case 2
0x180093f80  mov     r12, [r12+8]
0x180093f85  mov     r15, qword ptr [rsp+320h+var_2E0+8]
0x180093f8a  jmp     short loc_180093FA0
0x180093f8c  mov     esi, 1; jumptable 0000000180093F5F default case
0x180093f91  mov     r15, qword ptr [rsp+320h+var_2E0+8]
0x180093f96  mov     r12, qword ptr [rsp+320h+var_2D0]
0x180093f9b  nop     dword ptr [rax+rax+00h]
0x180093fa0  movzx   edx, byte ptr [r13+0]
0x180093fa5  cmp     edx, 9; switch 10 cases
0x180093fa8  ja      short def_180093FB8; jumptable 0000000180093FB8 default case, cases 0,3-9
0x180093faa  movsxd  rax, edx
0x180093fad  mov     ecx, ds:(jpt_180093FB8 - 180000000h)[r8+rax*4]
0x180093fb5  add     rcx, r8
0x180093fb8  jmp     rcx; switch jump
0x180093fba  cmp     rbx, r15; jumptable 0000000180093FB8 case 1
0x180093fbd  jmp     short loc_180093FC7
0x180093fbf  cmp     r14, r12; jumptable 0000000180093FB8 case 2
0x180093fc2  jmp     short loc_180093FC7
0x180093fc4  cmp     rdi, rsi; jumptable 0000000180093FB8 default case, cases 0,3-9
0x180093fc7  setnz   al
0x180093fca  test    al, al
0x180093fcc  jz      loc_1800942B5
0x180093fd2  cmp     edx, 9; switch 10 cases
0x180093fd5  ja      short def_180093FE2; jumptable 0000000180093FE2 default case, cases 3-9
0x180093fd7  mov     ecx, ds:(jpt_180093FE2 - 180000000h)[r8+rdx*4]
0x180093fdf  add     rcx, r8
0x180093fe2  jmp     rcx; switch jump
0x180093fe4  lea     r13, [rbx+40h]; jumptable 0000000180093FE2 case 1
0x180093fe8  jmp     short loc_180093FF8
0x180093fea  mov     r13, r14; jumptable 0000000180093FE2 case 2
0x180093fed  jmp     short loc_180093FF8
0x180093fef  test    rdi, rdi; jumptable 0000000180093FE2 default case, cases 3-9
0x180093ff2  jnz     loc_180094B13
0x180093ff8  xor     edx, edx; Val
0x180093ffa  mov     r8d, 0B0h; Size
0x180094000  lea     rcx, [rbp+220h+var_230]; void *
0x180094004  call    memset
0x180094009  xorps   xmm0, xmm0
0x18009400c  movups  [rbp+220h+var_240], xmm0
0x180094010  xorps   xmm1, xmm1
0x180094013  movdqa  [rbp+220h+var_230], xmm1
0x180094018  mov     r8d, 3
0x18009401e  lea     rdx, a10; "1.0"
0x180094025  lea     rcx, [rbp+220h+var_240]
0x180094029  call    ??$_Construct@$00PEB_Q@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXQEB_Q_K@Z; std::basic_string<char8_t>::_Construct<1,char8_t const *>(char8_t const * const,unsigned __int64)
0x18009402e  nop
0x18009402f  xorps   xmm0, xmm0
0x180094032  movups  [rbp+220h+var_220], xmm0
0x180094036  xorps   xmm1, xmm1
0x180094039  movdqa  [rbp+220h+var_210], xmm1
0x18009403e  mov     r8d, 0Ah
0x180094044  lea     rdx, a19700101; "1970-01-01"
0x18009404b  lea     rcx, [rbp+220h+var_220]
0x18009404f  call    ??$_Construct@$00PEB_Q@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXQEB_Q_K@Z; std::basic_string<char8_t>::_Construct<1,char8_t const *>(char8_t const * const,unsigned __int64)
0x180094054  nop
0x180094055  lea     rcx, [rbp+220h+var_200]
0x180094059  call    ??0?$unordered_set@UGuid@asg@@U?$hash@UGuid@asg@@@std@@U?$equal_to@UGuid@asg@@@4@V?$allocator@UGuid@asg@@@4@@std@@QEAA@XZ; std::unordered_set<asg::Guid>::unordered_set<asg::Guid>(void)
0x18009405e  nop
0x18009405f  lea     rcx, [rbp+220h+Block]
0x180094063  call    ??0?$unordered_set@UQueryDistance@DiskAnn@SemanticIndex@asg@@U?$hash@UQueryDistance@DiskAnn@SemanticIndex@asg@@@std@@U?$equal_to@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@V?$allocator@UQueryDistance@DiskAnn@SemanticIndex@asg@@@6@@std@@QEAA@XZ; std::unordered_set<asg::SemanticIndex::DiskAnn::QueryDistance>::unordered_set<asg::SemanticIndex::DiskAnn::QueryDistance>(void)
0x180094068  nop
0x180094069  mov     eax, [rsp+320h+var_2F0]
0x18009406d  or      eax, 2
0x180094070  mov     [rsp+320h+var_300], eax
0x180094074  mov     [rsp+320h+var_2F0], eax
0x180094078  lea     rdx, [rbp+220h+var_240]
0x18009407c  mov     rcx, r13
0x18009407f  call    ?from_json@SemanticRegistry@asg@@YAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@AEAUSourceDescriptionSchema@12@@Z; asg::SemanticRegistry::from_json(nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const &,asg::SemanticRegistry::SourceDescriptionSchema &)
0x180094084  mov     eax, [rsp+320h+var_2F0]
0x180094088  and     eax, 0FFFFFFFDh
0x18009408b  or      eax, 1
0x18009408e  mov     [rsp+320h+var_2F0], eax
0x180094092  mov     [rsp+320h+var_300], eax
0x180094096  lfence
0x180094099  mov     ecx, dword ptr [rsp+320h+var_2F8]
0x18009409d  movzx   edx, cl
0x1800940a0  mov     rax, 0CBF29CE484222325h
0x1800940aa  xor     rdx, rax
0x1800940ad  mov     r8, 100000001B3h
0x1800940b7  imul    rdx, r8
0x1800940bb  movzx   eax, byte ptr [rsp+320h+var_2F8+1]
0x1800940c0  xor     rdx, rax
0x1800940c3  imul    rdx, r8
0x1800940c7  movzx   eax, byte ptr [rsp+320h+var_2F8+2]
0x1800940cc  xor     rdx, rax
0x1800940cf  imul    rdx, r8
0x1800940d3  movzx   eax, byte ptr [rsp+320h+var_2F8+3]
0x1800940d8  xor     rdx, rax
0x1800940db  imul    rdx, r8
0x1800940df  mov     r9, [rsp+320h+var_2E8]
0x1800940e4  and     rdx, [r9+70h]
0x1800940e8  add     rdx, rdx
0x1800940eb  mov     r8, [r9+58h]
0x1800940ef  mov     rax, [r8+rdx*8+8]
0x1800940f4  cmp     rax, [r9+48h]
0x1800940f8  jz      short loc_180094117
0x1800940fa  mov     rdx, [r8+rdx*8]
0x1800940fe  cmp     ecx, [rax+10h]
0x180094101  jz      short loc_180094111
0x180094103  cmp     rax, rdx
0x180094106  jz      short loc_180094117
0x180094108  mov     rax, [rax+8]
0x18009410c  cmp     ecx, [rax+10h]
0x18009410f  jnz     short loc_180094103
0x180094111  lea     r13, [r9+40h]
0x180094115  jmp     short loc_180094140
0x180094117  lea     r13, [r9+40h]
0x18009411b  lea     r8, [rsp+320h+var_2F8]
0x180094120  lea     rdx, [rbp+220h+var_130]
0x180094127  mov     rcx, r13
0x18009412a  call    ??$_Try_emplace@AEBW4SourceName@SemanticRegistry@asg@@$$V@?$_Hash@V?$_Umap_traits@W4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@V?$_Uhash_compare@W4SourceName@SemanticRegistry@asg@@U?$hash@W4SourceName@SemanticRegistry@asg@@@std@@U?$equal_to@W4SourceName@SemanticRegistry@asg@@@5@@5@V?$allocator@U?$pair@$$CBW4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBW4SourceName@SemanticRegistry@asg@@@Z; std::_Hash<std::_Umap_traits<asg::SemanticRegistry::SourceName,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>,std::_Uhash_compare<asg::SemanticRegistry::SourceName,std::hash<asg::SemanticRegistry::SourceName>,std::equal_to<asg::SemanticRegistry::SourceName>>,std::allocator<std::pair<asg::SemanticRegistry::SourceName const,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>>>,0>>::_Try_emplace<asg::SemanticRegistry::SourceName const &,>(asg::SemanticRegistry::SourceName const &)
0x18009412f  mov     rcx, [rax]
0x180094132  add     rcx, 18h
0x180094136  xor     r8d, r8d
0x180094139  xor     edx, edx
0x18009413b  call    ??$_Assign_counted_range@PEBUSourceDescriptionSchema@SemanticRegistry@asg@@@?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@AEAAXPEBUSourceDescriptionSchema@SemanticRegistry@asg@@_K@Z; std::vector<asg::SemanticRegistry::SourceDescriptionSchema>::_Assign_counted_range<asg::SemanticRegistry::SourceDescriptionSchema const *>(asg::SemanticRegistry::SourceDescriptionSchema const *,unsigned __int64)
0x180094140  lea     r8, [rsp+320h+var_2F8]
0x180094145  lea     rdx, [rbp+220h+var_140]
0x18009414c  mov     rcx, r13
0x18009414f  call    ??$_Try_emplace@AEBW4SourceName@SemanticRegistry@asg@@$$V@?$_Hash@V?$_Umap_traits@W4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@V?$_Uhash_compare@W4SourceName@SemanticRegistry@asg@@U?$hash@W4SourceName@SemanticRegistry@asg@@@std@@U?$equal_to@W4SourceName@SemanticRegistry@asg@@@5@@5@V?$allocator@U?$pair@$$CBW4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4SourceName@SemanticRegistry@asg@@V?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBW4SourceName@SemanticRegistry@asg@@@Z; std::_Hash<std::_Umap_traits<asg::SemanticRegistry::SourceName,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>,std::_Uhash_compare<asg::SemanticRegistry::SourceName,std::hash<asg::SemanticRegistry::SourceName>,std::equal_to<asg::SemanticRegistry::SourceName>>,std::allocator<std::pair<asg::SemanticRegistry::SourceName const,std::vector<asg::SemanticRegistry::SourceDescriptionSchema>>>,0>>::_Try_emplace<asg::SemanticRegistry::SourceName const &,>(asg::SemanticRegistry::SourceName const &)
0x180094154  mov     r13, [rax]
0x180094157  mov     rax, [r13+20h]
0x18009415b  cmp     rax, [r13+28h]
0x18009415f  jz      short loc_180094177
0x180094161  lea     rdx, [rbp+220h+var_240]; struct asg::SemanticRegistry::SourceDescriptionSchema *
0x180094165  mov     rcx, rax; this
0x180094168  call    ??0SourceDescriptionSchema@SemanticRegistry@asg@@QEAA@AEBU012@@Z; asg::SemanticRegistry::SourceDescriptionSchema::SourceDescriptionSchema(asg::SemanticRegistry::SourceDescriptionSchema const &)
0x18009416d  add     qword ptr [r13+20h], 0C0h
0x180094175  jmp     short loc_180094188
0x180094177  lea     r8, [rbp+220h+var_240]
0x18009417b  mov     rdx, rax
0x18009417e  lea     rcx, [r13+18h]
0x180094182  call    ??$_Emplace_reallocate@AEBUSourceDescriptionSchema@SemanticRegistry@asg@@@?$vector@USourceDescriptionSchema@SemanticRegistry@asg@@V?$allocator@USourceDescriptionSchema@SemanticRegistry@asg@@@std@@@std@@AEAAPEAUSourceDescriptionSchema@SemanticRegistry@asg@@QEAU234@AEBU234@@Z; std::vector<asg::SemanticRegistry::SourceDescriptionSchema>::_Emplace_reallocate<asg::SemanticRegistry::SourceDescriptionSchema const &>(asg::SemanticRegistry::SourceDescriptionSchema * const,asg::SemanticRegistry::SourceDescriptionSchema const &)
0x180094187  nop
0x180094188  lea     rcx, [rbp+220h+var_1A8]
0x18009418c  call    ?_Tidy@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<uint,uint>>::_Tidy(void)
0x180094191  mov     rcx, [rbp+220h+Block+8]
0x180094195  mov     rax, [rcx+8]
0x180094199  mov     qword ptr [rax], 0
0x1800941a0  mov     rcx, [rcx]; Block
0x1800941a3  test    rcx, rcx
0x1800941a6  jz      short loc_1800941C5
0x1800941a8  nop     dword ptr [rax+rax+00000000h]
0x1800941b0  mov     r13, [rcx]
0x1800941b3  mov     edx, 18h
0x1800941b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800941bd  mov     rcx, r13
0x1800941c0  test    r13, r13
0x1800941c3  jnz     short loc_1800941B0
0x1800941c5  mov     edx, 18h
0x1800941ca  mov     rcx, [rbp+220h+Block+8]; Block
0x1800941ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800941d3  lea     rcx, [rbp+220h+var_1E8]
0x1800941d7  call    ?_Tidy@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<uint,uint>>::_Tidy(void)
0x1800941dc  mov     rcx, [rbp+220h+var_1F8]
0x1800941e0  mov     rax, [rcx+8]
0x1800941e4  mov     qword ptr [rax], 0
0x1800941eb  mov     rcx, [rcx]; Block
0x1800941ee  test    rcx, rcx
0x1800941f1  jz      short loc_180094208
0x1800941f3  mov     r13, [rcx]
0x1800941f6  mov     edx, 20h ; ' '
0x1800941fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094200  mov     rcx, r13
0x180094203  test    r13, r13
0x180094206  jnz     short loc_1800941F3
0x180094208  mov     edx, 20h ; ' '
0x18009420d  mov     rcx, [rbp+220h+var_1F8]; Block
0x180094211  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180094216  lea     rcx, [rbp+220h+var_220]; void *
0x18009421a  call    ?_Tidy_deallocate@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAXXZ; std::basic_string<char8_t>::_Tidy_deallocate(void)
  ... truncated ...
```

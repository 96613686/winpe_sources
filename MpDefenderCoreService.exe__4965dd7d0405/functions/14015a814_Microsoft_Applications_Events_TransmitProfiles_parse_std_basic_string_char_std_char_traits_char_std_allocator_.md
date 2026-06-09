# Microsoft::Applications::Events::TransmitProfiles::parse(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x14015a814`
- end: `0x14015bd25`
- name: `?parse@TransmitProfiles@Events@Applications@Microsoft@@SA_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `5393`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140113ff0`

## callees

- `0x14003a5c0`
- `0x14003c78c`
- `0x14007e088`
- `0x14007fb68`
- `0x140084a18`
- `0x14009d4d0`
- `0x1400c0b34`
- `0x1400ff188`
- `0x1401048f8`
- `0x140105fbc`
- `0x1401066d0`
- `0x140109c24`
- `0x14010aa28`
- `0x14010ae68`
- `0x14012ce2c`
- `0x14013f7a0`
- `0x140140d38`
- `0x140140e14`
- `0x140140f8c`
- `0x140158608`
- `0x140158824`
- `0x140158e58`
- `0x140158f54`
- `0x1401591f8`
- `0x1401592c4`
- `0x140159834`
- `0x140159e78`
- `0x140159f38`
- `0x14015a814`

## string_xrefs

- `0x14015b708`: `cannot compare iterators of different containers`
- `0x14015b790`: `cannot compare iterators of different containers`
- `0x14015ba7c`: `cannot compare iterators of different containers`
- `0x14015b6ac`: `JSON parsing failed miserably! Please check your config to fix above errors.`
- `0x14015b68b`: `JSON parsing completed successfully [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall Microsoft::Applications::Events::TransmitProfiles::parse(_QWORD *a1)
{
  int v1; // esi
  __int64 v2; // rbx
  __int64 v3; // rdx
  unsigned __int64 v4; // r9
  _BYTE *v5; // rbx
  unsigned __int64 v6; // rax
  __m128i si128; // xmm6
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  unsigned int v10; // r10d
  bool v11; // zf
  unsigned int v12; // r10d
  _BYTE *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  Microsoft::Applications::Events::TransmitProfileRule *v22; // rbx
  Microsoft::Applications::Events::TransmitProfileRule *v23; // rdi
  _BYTE *v24; // r15
  unsigned __int64 v25; // rdi
  _QWORD *v26; // r12
  _QWORD *v27; // rbx
  unsigned __int64 v28; // r11
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  unsigned int v31; // r9d
  bool v32; // zf
  _BYTE *v33; // rax
  unsigned int v34; // r9d
  __int64 v35; // rcx
  __int64 v36; // r8
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned __int8 *v39; // r8
  unsigned __int64 v40; // rsi
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  __int64 v43; // r8
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  _BYTE *v46; // rsi
  _BYTE *v47; // rax
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  __int64 v53; // rcx
  __int64 v54; // r8
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned __int8 *v57; // r8
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  __int64 v60; // r8
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  _BYTE *v63; // rsi
  _BYTE *v64; // rax
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // rax
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  __int64 v70; // rax
  __int64 v71; // r8
  unsigned __int8 *v72; // r9
  unsigned __int64 v73; // rax
  __int64 v74; // rbx
  _QWORD *v75; // rdi
  __int64 v76; // rdx
  bool v77; // zf
  int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // rdx
  int v82; // [rsp+30h] [rbp-738h]
  _QWORD *v83; // [rsp+38h] [rbp-730h] BYREF
  __int128 v84; // [rsp+40h] [rbp-728h] BYREF
  __int128 v85; // [rsp+50h] [rbp-718h]
  _BYTE *v86; // [rsp+60h] [rbp-708h] BYREF
  __int128 v87; // [rsp+68h] [rbp-700h]
  unsigned __int64 v88; // [rsp+78h] [rbp-6F0h]
  _BYTE *v89; // [rsp+80h] [rbp-6E8h] BYREF
  __int128 v90; // [rsp+88h] [rbp-6E0h]
  unsigned __int64 v91; // [rsp+98h] [rbp-6D0h]
  _BYTE v92[8]; // [rsp+A0h] [rbp-6C8h] BYREF
  _BYTE v93[8]; // [rsp+A8h] [rbp-6C0h] BYREF
  int v94; // [rsp+B0h] [rbp-6B8h] BYREF
  int v95; // [rsp+B4h] [rbp-6B4h]
  int v96; // [rsp+B8h] [rbp-6B0h]
  int v97; // [rsp+BCh] [rbp-6ACh]
  __int128 v98; // [rsp+C0h] [rbp-6A8h] BYREF
  __int64 v99; // [rsp+D0h] [rbp-698h]
  __int128 v100; // [rsp+D8h] [rbp-690h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-680h]
  __int64 v102; // [rsp+F0h] [rbp-678h]
  __int64 v103; // [rsp+F8h] [rbp-670h]
  _BYTE v104[8]; // [rsp+100h] [rbp-668h] BYREF
  _BYTE v105[8]; // [rsp+108h] [rbp-660h] BYREF
  _BYTE v106[56]; // [rsp+110h] [rbp-658h] BYREF
  __int64 v107; // [rsp+148h] [rbp-620h]
  _BYTE v108[56]; // [rsp+150h] [rbp-618h] BYREF
  _BYTE v109[56]; // [rsp+188h] [rbp-5E0h] BYREF
  _BYTE v110[56]; // [rsp+1C0h] [rbp-5A8h] BYREF
  _BYTE v111[56]; // [rsp+1F8h] [rbp-570h] BYREF
  _BYTE v112[56]; // [rsp+230h] [rbp-538h] BYREF
  _BYTE v113[56]; // [rsp+268h] [rbp-500h] BYREF
  _BYTE v114[56]; // [rsp+2A0h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+2D8h] [rbp-490h] BYREF
  _BYTE v116[56]; // [rsp+310h] [rbp-458h] BYREF
  _BYTE v117[56]; // [rsp+348h] [rbp-420h] BYREF
  _BYTE v118[56]; // [rsp+380h] [rbp-3E8h] BYREF
  _BYTE v119[56]; // [rsp+3F0h] [rbp-378h] BYREF
  _BYTE v120[56]; // [rsp+428h] [rbp-340h] BYREF
  _BYTE v121[56]; // [rsp+460h] [rbp-308h] BYREF
  _BYTE v122[56]; // [rsp+498h] [rbp-2D0h] BYREF
  _BYTE v123[56]; // [rsp+4D0h] [rbp-298h] BYREF
  _BYTE v124[56]; // [rsp+508h] [rbp-260h] BYREF
  _BYTE v125[56]; // [rsp+540h] [rbp-228h] BYREF
  _BYTE v126[56]; // [rsp+578h] [rbp-1F0h] BYREF
  _BYTE v127[56]; // [rsp+5B0h] [rbp-1B8h] BYREF
  _BYTE v128[56]; // [rsp+5E8h] [rbp-180h] BYREF
  _BYTE v129[56]; // [rsp+620h] [rbp-148h] BYREF
  unsigned __int8 *v130; // [rsp+658h] [rbp-110h] BYREF
  _BYTE v131[24]; // [rsp+660h] [rbp-108h] BYREF
  _OWORD v132[2]; // [rsp+678h] [rbp-F0h] BYREF
  _BYTE v133[8]; // [rsp+698h] [rbp-D0h] BYREF
  __int64 *v134; // [rsp+6A0h] [rbp-C8h] BYREF
  _BYTE v135[8]; // [rsp+6A8h] [rbp-C0h] BYREF
  __int64 v136; // [rsp+6B0h] [rbp-B8h] BYREF
  Microsoft::Applications::Events::TransmitProfileRules *v137[2]; // [rsp+6B8h] [rbp-B0h] BYREF
  Microsoft::Applications::Events::TransmitProfileRules *v138; // [rsp+6C8h] [rbp-A0h]
  _OWORD v139[2]; // [rsp+6D0h] [rbp-98h] BYREF
  Microsoft::Applications::Events::TransmitProfileRule *v140[2]; // [rsp+6F0h] [rbp-78h] BYREF
  Microsoft::Applications::Events::TransmitProfileRule *v141; // [rsp+700h] [rbp-68h]
  _BYTE v142[8]; // [rsp+708h] [rbp-60h] BYREF
  __int64 v143; // [rsp+710h] [rbp-58h] BYREF
  _QWORD v144[4]; // [rsp+718h] [rbp-50h] BYREF

  v1 = 0;
  v2 = 0;
  v103 = 0;
  *(_OWORD *)v137 = 0;
  v138 = 0;
  v107 = 0;
  if ( a1[3] > 0xFu )
    a1 = (_QWORD *)*a1;
  v83 = a1;
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::parse<char const *>(
    v133,
    &v83,
    v106);
  if ( v133[0] == 2 )
  {
    v4 = (v134[1] - *v134) >> 4;
    if ( v4 > 0x14 )
    {
      LOBYTE(v3) = 2;
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
        &v134,
        v3);
      goto LABEL_238;
    }
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    {
      _mm_lfence();
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(4, "MATSDK", "got %u profiles", v4);
    }
    v5 = v133;
    v89 = v133;
    v90 = 0u;
    v6 = 0x8000000000000000uLL;
    v91 = 0x8000000000000000uLL;
    if ( v133[0] <= 4u )
    {
      if ( !v133[0] )
      {
        v6 = 1;
LABEL_18:
        v91 = v6;
        goto LABEL_19;
      }
      if ( v133[0] == 1 )
        goto LABEL_15;
      if ( v133[0] == 2 )
      {
LABEL_14:
        *((_QWORD *)&v90 + 1) = *v134;
LABEL_19:
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        while ( 1 )
        {
          memset(v131, 0, sizeof(v131));
          v8 = 0x8000000000000000uLL;
          if ( v133[0] <= 4u && v133[0] )
          {
            if ( v133[0] == 1 )
              goto LABEL_29;
            if ( v133[0] == 2 )
              goto LABEL_28;
          }
          if ( v133[0] > 4u || !v133[0] )
            goto LABEL_30;
          if ( v133[0] == 1 )
          {
LABEL_29:
            v9 = *v134;
            v3 = *(_QWORD *)&v131[8];
            goto LABEL_32;
          }
          if ( v133[0] == 2 )
          {
LABEL_28:
            v3 = v134[1];
          }
          else
          {
LABEL_30:
            v8 = 1;
            v3 = *(_QWORD *)&v131[8];
          }
          v9 = *(_QWORD *)v131;
LABEL_32:
          if ( v5 != v133 )
          {
            std::string::string(v144, "cannot compare iterators of different containers", v8);
            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
              (__int64)pExceptionObject,
              212,
              (__int64)v144);
            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)pExceptionObject;
          }
          v10 = (unsigned __int8)*v5;
          if ( v10 <= 4 && *v5 )
          {
            if ( v10 == 1 )
            {
              v11 = (_QWORD)v90 == v9;
              goto LABEL_40;
            }
            if ( v10 == 2 )
            {
              v11 = *((_QWORD *)&v90 + 1) == v3;
              goto LABEL_40;
            }
          }
          v11 = v6 == v8;
LABEL_40:
          if ( v11 )
            goto LABEL_235;
          v139[0] = 0;
          v139[1] = si128;
          LOBYTE(v139[0]) = 0;
          *(_OWORD *)v140 = 0;
          v141 = 0;
          if ( v10 <= 4 )
          {
            if ( !v10 )
            {
              std::string::string(v144, "cannot get value", v8);
              nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                (__int64)v116,
                214,
                (__int64)v144);
              throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v116;
            }
            v12 = v10 - 1;
            if ( !v12 )
            {
              v5 = (_BYTE *)(v90 + 64);
              goto LABEL_48;
            }
            if ( v12 == 1 )
            {
              v5 = (_BYTE *)*((_QWORD *)&v90 + 1);
              goto LABEL_48;
            }
          }
          if ( v6 )
          {
            std::string::string(v144, "cannot get value", v8);
            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
              (__int64)v112,
              214,
              (__int64)v144);
            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v112;
          }
LABEL_48:
          nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
            v92,
            v5);
          if ( v92[0] == 1 )
          {
            v100 = 0;
            v101 = 0;
            v102 = 0;
            std::string::_Construct<1,char const *>(&v100, "name", 4u);
            v13 = (_BYTE *)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                             v92,
                             &v100);
            nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
              v13,
              v144,
              v14,
              v15);
            v1 |= 1u;
            v82 = v1;
            std::string::operator=(v139);
            v84 = 0;
            v85 = 0u;
            std::string::_Construct<1,char const *>(&v84, "rules", 5u);
            v16 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                    v92,
                    &v84);
            nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
              v135,
              v16);
            if ( v135[0] == 2 )
            {
              v19 = (__int64)(*(_QWORD *)(v136 + 8) - *(_QWORD *)v136) >> 4;
              if ( v19 > 0x10 )
              {
                if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
                {
                  _mm_lfence();
                  Microsoft::Applications::Events::PlatformAbstraction::detail::log(
                    1,
                    "MATSDK",
                    "Exceeded max transmit rules %d>%d for profile",
                    v19,
                    16);
                }
                LOBYTE(v17) = v135[0];
                nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
                  &v136,
                  v17);
                std::string::_Tidy_deallocate(v144);
                LOBYTE(v20) = v92[0];
                nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
                  v93,
                  v20);
                std::vector<Microsoft::Applications::Events::TransmitProfileRule>::_Tidy(v140);
                std::string::_Tidy_deallocate(v139);
                LOBYTE(v21) = v133[0];
                nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
                  &v134,
                  v21);
                v2 = v103;
                goto LABEL_238;
              }
              v22 = v140[0];
              v23 = v140[1];
              if ( v140[0] != v140[1] )
              {
                do
                {
                  std::vector<int>::_Tidy((char *)v22 + 16);
                  v22 = (Microsoft::Applications::Events::TransmitProfileRule *)((char *)v22 + 40);
                }
                while ( v22 != v23 );
                v140[1] = v140[0];
              }
              v24 = v135;
              v86 = v135;
              v87 = 0u;
              v25 = 0x8000000000000000uLL;
              v88 = 0x8000000000000000uLL;
              if ( v135[0] > 4u )
                goto LABEL_66;
              if ( !v135[0] )
              {
                v25 = 1;
                v88 = 1;
                goto LABEL_67;
              }
              if ( v135[0] == 1 )
                goto LABEL_64;
              if ( v135[0] == 2 )
                goto LABEL_63;
              if ( v135[0] == 1 )
              {
LABEL_64:
                v27 = **(_QWORD ***)v136;
                *(_QWORD *)&v87 = v27;
                v26 = (_QWORD *)*((_QWORD *)&v87 + 1);
              }
              else
              {
                if ( v135[0] == 2 )
                {
LABEL_63:
                  v26 = *(_QWORD **)v136;
                  *((_QWORD *)&v87 + 1) = *(_QWORD *)v136;
                  goto LABEL_68;
                }
LABEL_66:
                v25 = 0;
                v88 = 0;
LABEL_67:
                v26 = (_QWORD *)*((_QWORD *)&v87 + 1);
LABEL_68:
                v27 = (_QWORD *)v87;
              }
              v28 = 0x8000000000000000uLL;
              while ( 2 )
              {
                memset(v131, 0, sizeof(v131));
                v17 = v28;
                if ( v135[0] <= 4u )
                {
                  v18 = v135[0];
                  if ( v135[0] )
                  {
                    v18 = (unsigned int)v135[0] - 1;
                    if ( v135[0] != 1 )
                    {
                      v18 = (unsigned int)v135[0] - 2;
                      if ( v135[0] != 2 )
                        break;
LABEL_78:
                      v29 = *(_QWORD **)(v136 + 8);
LABEL_81:
                      v30 = *(_QWORD **)v131;
LABEL_82:
                      if ( v24 != v135 )
                      {
                        std::string::string(v132, "cannot compare iterators of different containers", v18);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v114,
                          212,
                          (__int64)v132);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v114;
                      }
                      v31 = (unsigned __int8)*v24;
                      if ( v31 > 4 || !*v24 )
                        goto LABEL_89;
                      if ( v31 == 1 )
                      {
                        v32 = v27 == v30;
                      }
                      else
                      {
                        if ( v31 == 2 )
                        {
                          v32 = v26 == v29;
                          goto LABEL_90;
                        }
LABEL_89:
                        v32 = v25 == v17;
                      }
LABEL_90:
                      if ( v32 )
                        goto LABEL_230;
                      if ( v31 > 4 )
                        goto LABEL_97;
                      if ( !*v24 )
                      {
                        std::string::string(v132, "cannot get value", v18);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v118,
                          214,
                          (__int64)v132);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v118;
                      }
                      if ( v31 == 1 )
                      {
                        v33 = v27 + 8;
                      }
                      else
                      {
                        if ( v31 == 2 )
                        {
                          v33 = v26;
                          goto LABEL_99;
                        }
LABEL_97:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v18);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v111,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v111;
                        }
                        v33 = v24;
                      }
LABEL_99:
                      if ( *v33 != 1 )
                        goto LABEL_229;
                      v94 = -1;
                      v95 = -1;
                      v96 = -1;
                      v97 = 0;
                      v98 = 0;
                      v99 = 0;
                      v84 = 0;
                      v85 = 0;
                      if ( v31 > 4 )
                        goto LABEL_105;
                      v34 = v31 - 1;
                      if ( v34 )
                      {
                        if ( v34 == 1 )
                        {
                          v35 = (__int64)v26;
                          goto LABEL_107;
                        }
LABEL_105:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v18);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v110,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v110;
                        }
                        v35 = (__int64)v24;
                      }
                      else
                      {
                        v35 = (__int64)(v27 + 8);
                      }
LABEL_107:
                      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[8],0>(
                        v35,
                        (unsigned __int8 **)&v84);
                      v37 = (unsigned __int8)*v24;
                      if ( v37 > 4 )
                        goto LABEL_113;
                      if ( !*v24 )
                      {
                        std::string::string(v132, "cannot get value", v36);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v119,
                          214,
                          (__int64)v132);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v119;
                      }
                      v38 = v37 - 1;
                      if ( !v38 )
                      {
                        v39 = (unsigned __int8 *)(v27 + 8);
                        goto LABEL_115;
                      }
                      if ( v38 == 1 )
                      {
                        v39 = (unsigned __int8 *)v26;
                      }
                      else
                      {
LABEL_113:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v36);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v109,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v109;
                        }
                        v39 = v24;
                      }
LABEL_115:
                      v130 = v39;
                      *(_OWORD *)v131 = 0u;
                      v40 = 0x8000000000000000uLL;
                      *(_QWORD *)&v131[16] = 0x8000000000000000uLL;
                      v41 = *v39;
                      if ( v41 > 4 || !*v39 )
                        goto LABEL_123;
                      if ( v41 == 1 )
                        goto LABEL_122;
                      if ( v41 == 2 )
                        goto LABEL_121;
                      v42 = v41 - 1;
                      if ( !v42 )
                      {
LABEL_122:
                        *(_QWORD *)v131 = **((_QWORD **)v39 + 1);
                      }
                      else
                      {
                        if ( v42 == 1 )
                        {
LABEL_121:
                          *(_QWORD *)&v131[8] = *(_QWORD *)(*((_QWORD *)v39 + 1) + 8LL);
                          goto LABEL_124;
                        }
LABEL_123:
                        *(_QWORD *)&v131[16] = 1;
                      }
LABEL_124:
                      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
                             &v130,
                             (unsigned __int8 **)&v84) )
                      {
                        v44 = (unsigned __int8)*v24;
                        if ( v44 > 4 )
                          goto LABEL_131;
                        if ( !*v24 )
                        {
                          std::string::string(v132, "cannot get value", v43);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v120,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v120;
                        }
                        v45 = v44 - 1;
                        if ( v45 )
                        {
                          if ( v45 == 1 )
                          {
                            v46 = v26;
                            goto LABEL_133;
                          }
LABEL_131:
                          if ( v25 )
                          {
                            std::string::string(v132, "cannot get value", v43);
                            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                              (__int64)v117,
                              214,
                              (__int64)v132);
                            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v117;
                          }
                          v46 = v24;
                        }
                        else
                        {
                          v46 = v27 + 8;
                        }
LABEL_133:
                        v84 = 0;
                        v85 = 0u;
                        std::string::_Construct<1,char const *>(&v84, "netCost", 7u);
                        v47 = (_BYTE *)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                                         v46,
                                         &v84);
                        nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                          v47,
                          &v130,
                          v48,
                          v49);
                        v82 |= 2u;
                        v50 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::string,Microsoft::Applications::Events::WinInetRequestWrapper *,std::less<std::string>,std::allocator<std::pair<std::string const,Microsoft::Applications::Events::WinInetRequestWrapper *>>,0>>::find(
                                           &qword_1401E7280,
                                           v104,
                                           &v130);
                        if ( v50 != qword_1401E7280 )
                          v94 = *(_DWORD *)(v50 + 64);
                        std::string::_Tidy_deallocate(&v130);
                        v40 = 0x8000000000000000uLL;
                      }
                      memset(v132, 0, sizeof(v132));
                      v51 = (unsigned __int8)*v24;
                      if ( v51 > 4 )
                        goto LABEL_142;
                      if ( !*v24 )
                      {
                        std::string::string(v132, "cannot get value", v43);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v121,
                          214,
                          (__int64)v132);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v121;
                      }
                      v52 = v51 - 1;
                      if ( v52 )
                      {
                        if ( v52 == 1 )
                        {
                          v53 = (__int64)v26;
                          goto LABEL_144;
                        }
LABEL_142:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v43);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v113,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v113;
                        }
                        v53 = (__int64)v24;
                      }
                      else
                      {
                        v53 = (__int64)(v27 + 8);
                      }
LABEL_144:
                      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[11],0>(
                        v53,
                        (unsigned __int8 **)v132);
                      v55 = (unsigned __int8)*v24;
                      if ( v55 > 4 )
                        goto LABEL_150;
                      if ( !*v24 )
                      {
                        std::string::string(v132, "cannot get value", v54);
                        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                          (__int64)v122,
                          214,
                          (__int64)v132);
                        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v122;
                      }
                      v56 = v55 - 1;
                      if ( !v56 )
                      {
                        v57 = (unsigned __int8 *)(v27 + 8);
                        goto LABEL_152;
                      }
                      if ( v56 == 1 )
                      {
                        v57 = (unsigned __int8 *)v26;
                      }
                      else
                      {
LABEL_150:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v54);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v129,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v129;
                        }
                        v57 = v24;
                      }
LABEL_152:
                      v130 = v57;
                      *(_OWORD *)v131 = 0u;
                      *(_QWORD *)&v131[16] = 0x8000000000000000uLL;
                      v58 = *v57;
                      if ( v58 > 4 || !*v57 )
                        goto LABEL_160;
                      if ( v58 == 1 )
                        goto LABEL_159;
                      if ( v58 == 2 )
                        goto LABEL_158;
                      v59 = v58 - 1;
                      if ( !v59 )
                      {
LABEL_159:
                        *(_QWORD *)v131 = **((_QWORD **)v57 + 1);
                      }
                      else
                      {
                        if ( v59 == 1 )
                        {
LABEL_158:
                          *(_QWORD *)&v131[8] = *(_QWORD *)(*((_QWORD *)v57 + 1) + 8LL);
                          goto LABEL_161;
                        }
LABEL_160:
                        *(_QWORD *)&v131[16] = 1;
                      }
LABEL_161:
                      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
                             &v130,
                             (unsigned __int8 **)v132) )
                      {
                        v61 = (unsigned __int8)*v24;
                        if ( v61 > 4 )
                          goto LABEL_168;
                        if ( !*v24 )
                        {
                          std::string::string(&v100, "cannot get value", v60);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v123,
                            214,
                            (__int64)&v100);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v123;
                        }
                        v62 = v61 - 1;
                        if ( v62 )
                        {
                          if ( v62 == 1 )
                          {
                            v63 = v26;
                            goto LABEL_170;
                          }
LABEL_168:
                          if ( v25 )
                          {
                            std::string::string(&v100, "cannot get value", v60);
                            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                              (__int64)v124,
                              214,
                              (__int64)&v100);
                            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v124;
                          }
                          v63 = v24;
                        }
                        else
                        {
                          v63 = v27 + 8;
                        }
LABEL_170:
                        v84 = 0;
                        v85 = 0u;
                        std::string::_Construct<1,char const *>(&v84, "powerState", 0xAu);
                        v64 = (_BYTE *)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                                         v63,
                                         &v84);
                        nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                          v64,
                          v132,
                          v65,
                          v66);
                        v82 |= 4u;
                        v67 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::string,Microsoft::Applications::Events::WinInetRequestWrapper *,std::less<std::string>,std::allocator<std::pair<std::string const,Microsoft::Applications::Events::WinInetRequestWrapper *>>,0>>::find(
                                           &qword_1401E7270,
                                           v105,
                                           v132);
                        if ( v67 != qword_1401E7270 )
                          v95 = *(_DWORD *)(v67 + 64);
                        std::string::_Tidy_deallocate(v132);
                        v40 = 0x8000000000000000uLL;
                      }
                      v68 = (unsigned __int8)*v24;
                      if ( v68 > 4 )
                      {
LABEL_177:
                        if ( v25 )
                        {
                          std::string::string(v132, "cannot get value", v60);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v128,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v128;
                        }
                        v26 = v24;
                      }
                      else
                      {
                        if ( !*v24 )
                        {
                          std::string::string(v132, "cannot get value", v60);
                          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                            (__int64)v125,
                            214,
                            (__int64)v132);
                          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v125;
                        }
                        v69 = v68 - 1;
                        if ( v69 )
                        {
                          if ( v69 != 1 )
                            goto LABEL_177;
                        }
                        else
                        {
                          v26 = v27 + 8;
                        }
                      }
                      v84 = 0;
                      v85 = 0u;
                      std::string::_Construct<1,char const *>(&v84, "timers", 6u);
                      v70 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::operator[](
                              v26,
                              &v84);
                      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
                        v142,
                        v70);
                      v72 = v142;
                      v130 = v142;
                      *(_OWORD *)v131 = 0u;
                      v73 = 0x8000000000000000uLL;
                      *(_QWORD *)&v131[16] = 0x8000000000000000uLL;
                      if ( v142[0] > 4u )
                        goto LABEL_189;
                      v71 = v142[0];
                      if ( v142[0] )
                      {
                        v71 = (unsigned int)v142[0] - 1;
                        if ( v142[0] == 1 )
                          goto LABEL_187;
                        v71 = (unsigned int)v142[0] - 2;
                        if ( v142[0] == 2 )
                          goto LABEL_185;
                        if ( v142[0] == 1 )
                        {
LABEL_187:
                          *(_QWORD *)v131 = **(_QWORD **)v143;
                          goto LABEL_191;
                        }
                        if ( v142[0] == 2 )
                        {
LABEL_185:
                          *(_QWORD *)&v131[8] = *(_QWORD *)v143;
LABEL_191:
                          *((_QWORD *)&v84 + 1) = 0;
                          v85 = 0;
                          if ( v142[0] <= 4u )
                          {
                            v71 = v142[0];
                            if ( v142[0] )
                            {
                              v71 = (unsigned int)v142[0] - 1;
                              if ( v142[0] == 1 )
                                goto LABEL_200;
                              v71 = (unsigned int)v142[0] - 2;
                              if ( v142[0] == 2 )
                                goto LABEL_199;
                            }
                          }
                          v40 = 0x8000000000000000uLL;
                          if ( v142[0] > 4u || !v142[0] )
                            goto LABEL_201;
                          if ( v142[0] == 1 )
                          {
LABEL_200:
                            v75 = *(_QWORD **)v143;
                            v74 = v85;
                            goto LABEL_203;
                          }
                          if ( v142[0] == 2 )
                          {
LABEL_199:
                            v74 = *(_QWORD *)(v143 + 8);
                          }
                          else
                          {
LABEL_201:
                            v40 = 1;
                            v74 = v85;
                          }
                          v75 = (_QWORD *)*((_QWORD *)&v84 + 1);
LABEL_203:
                          if ( v72 != v142 )
                          {
                            std::string::string(v132, "cannot compare iterators of different containers", v71);
                            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                              (__int64)v108,
                              212,
                              (__int64)v132);
                            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v108;
                          }
                          v76 = *v72;
                          if ( (unsigned int)v76 > 4 )
                            goto LABEL_210;
                          v71 = *v72;
                          if ( !*v72 )
                            goto LABEL_210;
                          v71 = (unsigned int)(v76 - 1);
                          if ( (_DWORD)v76 == 1 )
                          {
                            v77 = *(_QWORD *)v131 == (_QWORD)v75;
                          }
                          else
                          {
                            v71 = (unsigned int)(v76 - 2);
                            if ( (_DWORD)v76 == 2 )
                            {
                              v77 = *(_QWORD *)&v131[8] == v74;
                              goto LABEL_211;
                            }
LABEL_210:
                            v77 = v73 == v40;
                          }
LABEL_211:
                          if ( v77 )
                          {
                            if ( v140[1] == v141 )
                            {
                              std::vector<Microsoft::Applications::Events::TransmitProfileRule>::_Emplace_reallocate<Microsoft::Applications::Events::TransmitProfileRule const &>(
                                v140,
                                v140[1],
                                &v94);
                            }
                            else
                            {
                              Microsoft::Applications::Events::TransmitProfileRule::TransmitProfileRule(
                                v140[1],
                                (const struct Microsoft::Applications::Events::TransmitProfileRule *)&v94);
                              v140[1] = (Microsoft::Applications::Events::TransmitProfileRule *)((char *)v140[1] + 40);
                            }
                            LOBYTE(v79) = v142[0];
                            nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
                              &v143,
                              v79);
                            std::vector<int>::_Tidy(&v98);
                            v1 = v82;
LABEL_229:
                            nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator++(&v86);
                            v25 = v88;
                            v26 = (_QWORD *)*((_QWORD *)&v87 + 1);
                            v27 = (_QWORD *)v87;
                            v24 = v86;
                            continue;
                          }
                          if ( (unsigned int)v76 <= 4 )
                          {
                            if ( !*v72 )
                            {
                              std::string::string(v132, "cannot get value", v71);
                              nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                                (__int64)v126,
                                214,
                                (__int64)v132);
                              throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v126;
                            }
                            v76 = (unsigned int)(v76 - 1);
                            if ( !(_DWORD)v76 )
                            {
                              v72 = (unsigned __int8 *)(*(_QWORD *)v131 + 64LL);
LABEL_219:
                              if ( *v72 == 5 || (unsigned __int8)(*v72 - 6) <= 1u )
                              {
                                v78 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<int,int>(
                                        v72,
                                        v76,
                                        v71);
                                LODWORD(v83) = v78;
                                if ( *((_QWORD *)&v98 + 1) == v99 )
                                {
                                  std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(
                                    &v98,
                                    *((_QWORD *)&v98 + 1),
                                    &v83);
                                }
                                else
                                {
                                  **((_DWORD **)&v98 + 1) = v78;
                                  *((_QWORD *)&v98 + 1) += 4LL;
                                }
                              }
                              nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator++(&v130);
                              v73 = *(_QWORD *)&v131[16];
                              v72 = v130;
                              goto LABEL_203;
                            }
                            v76 = (unsigned int)(v76 - 1);
                            if ( !(_DWORD)v76 )
                            {
                              v72 = *(unsigned __int8 **)&v131[8];
                              goto LABEL_219;
                            }
                          }
                          if ( v73 )
                          {
                            std::string::string(v132, "cannot get value", v71);
                            nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
                              (__int64)v127,
                              214,
                              (__int64)v132);
                            throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v127;
                          }
                          goto LABEL_219;
                        }
LABEL_189:
                        v73 = 0;
                      }
                      else
                      {
                        v73 = 1;
                      }
                      *(_QWORD *)&v131[16] = v73;
                      goto LABEL_191;
                    }
LABEL_79:
                    v30 = *(_QWORD **)v136;
                    v29 = *(_QWORD **)&v131[8];
                    goto LABEL_82;
                  }
                }
                break;
              }
              if ( v135[0] <= 4u && v135[0] )
              {
                if ( v135[0] == 1 )
                  goto LABEL_79;
                if ( v135[0] == 2 )
                  goto LABEL_78;
              }
              v17 = 1;
              v29 = *(_QWORD **)&v131[8];
              goto LABEL_81;
            }
LABEL_230:
            LOBYTE(v17) = v135[0];
            nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
              &v136,
              v17);
            std::string::_Tidy_deallocate(v144);
          }
          if ( v137[1] == v138 )
          {
            std::vector<Microsoft::Applications::Events::TransmitProfileRules>::_Emplace_reallocate<Microsoft::Applications::Events::TransmitProfileRules const &>(
              v137,
              v137[1],
              v139);
          }
          else
          {
            Microsoft::Applications::Events::TransmitProfileRules::TransmitProfileRules(
              v137[1],
              (const struct Microsoft::Applications::Events::TransmitProfileRules *)v139);
            v137[1] = (Microsoft::Applications::Events::TransmitProfileRules *)((char *)v137[1] + 56);
          }
          LOBYTE(v80) = v92[0];
          nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
            v93,
            v80);
          std::vector<Microsoft::Applications::Events::TransmitProfileRule>::_Tidy(v140);
          std::string::_Tidy_deallocate(v139);
          nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator++(&v89);
          v6 = v91;
          v5 = v89;
        }
      }
      if ( v133[0] == 1 )
      {
LABEL_15:
        *(_QWORD *)&v90 = *(_QWORD *)*v134;
        goto LABEL_19;
      }
      if ( v133[0] == 2 )
        goto LABEL_14;
    }
    v6 = 0;
    goto LABEL_18;
  }
LABEL_235:
  LOBYTE(v3) = v133[0];
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
    &v134,
    v3);
  v2 = 0x6DB6DB6DB6DB6DB7LL * ((v137[1] - v137[0]) >> 3);
  Microsoft::Applications::Events::TransmitProfiles::UpdateProfiles(v137);
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 3 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      3,
      "MATSDK",
      "JSON parsing completed successfully [%d]",
      v2);
  if ( !v2 )
  {
LABEL_238:
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK",
        "JSON parsing failed miserably! Please check your config to fix above errors.");
  }
  std::vector<Microsoft::Applications::Events::TransmitProfileRules>::_Tidy(v137);
  return v2;
}

```

## disassembly

```asm
0x14015a814  mov     r11, rsp
0x14015a817  mov     [r11+10h], rbx
0x14015a81b  mov     [r11+18h], rsi
0x14015a81f  mov     [r11+20h], rdi
0x14015a823  push    r12
0x14015a825  push    r14
0x14015a827  push    r15
0x14015a829  sub     rsp, 750h
0x14015a830  movaps  xmmword ptr [r11-28h], xmm6
0x14015a835  mov     rax, cs:__security_cookie
0x14015a83c  xor     rax, rsp
0x14015a83f  mov     [rsp+768h+var_30], rax
0x14015a847  xor     r14d, r14d
0x14015a84a  mov     esi, r14d
0x14015a84d  mov     [rsp+768h+var_738], r14d
0x14015a852  mov     ebx, r14d
0x14015a855  mov     [rsp+768h+var_670], rbx
0x14015a85d  xorps   xmm1, xmm1
0x14015a860  movdqu  xmmword ptr [rsp+768h+var_B0], xmm1
0x14015a869  mov     [r11-0A0h], r14
0x14015a870  mov     [r11-620h], r14
0x14015a877  cmp     qword ptr [rcx+18h], 0Fh
0x14015a87c  jbe     short loc_14015A881
0x14015a87e  mov     rcx, [rcx]
0x14015a881  mov     [rsp+768h+var_730], rcx
0x14015a886  lea     r8, [rsp+768h+var_658]
0x14015a88e  lea     rdx, [rsp+768h+var_730]
0x14015a893  lea     rcx, [rsp+768h+var_D0]
0x14015a89b  call    ??$parse@PEBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@SA?AV012@$$QEAPEBDV?$function@$$A6A_NHW4parse_event_t@detail@json_abi_v3_11_3@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@34@@Z@std@@_N2@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::parse<char const *>(char const * &&,std::function<bool (int,nlohmann::json_abi_v3_11_3::detail::parse_event_t,nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> &)>,bool,bool)
0x14015a8a0  nop
0x14015a8a1  cmp     [rsp+768h+var_D0], 2
0x14015a8a9  jnz     loc_14015B637
0x14015a8af  mov     rax, [rsp+768h+var_C8]
0x14015a8b7  mov     r9, [rax+8]
0x14015a8bb  sub     r9, [rax]
0x14015a8be  sar     r9, 4
0x14015a8c2  cmp     r9, 14h
0x14015a8c6  jbe     short loc_14015A8DD
0x14015a8c8  mov     dl, 2
0x14015a8ca  lea     rcx, [rsp+768h+var_C8]
0x14015a8d2  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14015a8d7  nop
0x14015a8d8  jmp     loc_14015B6A3
0x14015a8dd  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14015a8e4  jl      short loc_14015A901
0x14015a8e6  lfence
0x14015a8e9  lea     r8, aGotUProfiles; "got %u profiles"
0x14015a8f0  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14015a8f7  mov     ecx, 4
0x14015a8fc  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14015a901  lea     rbx, [rsp+768h+var_D0]
0x14015a909  mov     [rsp+768h+var_6E8], rbx
0x14015a911  xorps   xmm0, xmm0
0x14015a914  movdqu  [rsp+768h+var_6E0], xmm0
0x14015a91d  xorps   xmm1, xmm1
0x14015a920  movdqu  [rsp+768h+var_6E0+8], xmm1
0x14015a929  mov     r12, 8000000000000000h
0x14015a933  mov     rax, r12
0x14015a936  mov     [rsp+768h+var_6D0], rax
0x14015a93e  movzx   edx, byte ptr [rbx]
0x14015a941  cmp     edx, 5
0x14015a944  ja      short loc_14015A995
0x14015a946  jz      short loc_14015A995
0x14015a948  mov     r8d, edx
0x14015a94b  test    edx, edx
0x14015a94d  jz      short loc_14015A98E
0x14015a94f  sub     r8d, 1
0x14015a953  jz      short loc_14015A97A
0x14015a955  sub     r8d, 1
0x14015a959  jz      short loc_14015A969
0x14015a95b  test    edx, edx
0x14015a95d  jz      short loc_14015A98E
0x14015a95f  sub     edx, 1
0x14015a962  jz      short loc_14015A97A
0x14015a964  sub     edx, 1
0x14015a967  jnz     short loc_14015A995
0x14015a969  mov     rcx, [rbx+8]
0x14015a96d  mov     rdx, [rcx]
0x14015a970  mov     qword ptr [rsp+768h+var_6E0+8], rdx
0x14015a978  jmp     short loc_14015A9A0
0x14015a97a  mov     rcx, [rbx+8]
0x14015a97e  mov     rdx, [rcx]
0x14015a981  mov     rcx, [rdx]
0x14015a984  mov     qword ptr [rsp+768h+var_6E0], rcx
0x14015a98c  jmp     short loc_14015A9A0
0x14015a98e  mov     eax, 1
0x14015a993  jmp     short loc_14015A998
0x14015a995  mov     rax, r14
0x14015a998  mov     [rsp+768h+var_6D0], rax
0x14015a9a0  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x14015a9a8  lea     r10, [rsp+768h+var_D0]
0x14015a9b0  xorps   xmm0, xmm0
0x14015a9b3  movdqu  [rsp+768h+var_108], xmm0
0x14015a9bc  xorps   xmm1, xmm1
0x14015a9bf  movdqu  [rsp+768h+var_108+8], xmm1
0x14015a9c8  mov     r8, r12
0x14015a9cb  movzx   edx, byte ptr [r10]
0x14015a9cf  cmp     edx, 5
0x14015a9d2  ja      short loc_14015A9E9
0x14015a9d4  jz      short loc_14015A9E9
0x14015a9d6  mov     r9d, edx
0x14015a9d9  test    edx, edx
0x14015a9db  jz      short loc_14015A9E9
0x14015a9dd  sub     r9d, 1
0x14015a9e1  jz      short loc_14015AA06
0x14015a9e3  sub     r9d, 1
0x14015a9e7  jz      short loc_14015A9FC
0x14015a9e9  cmp     edx, 4
0x14015a9ec  ja      short loc_14015AA17
0x14015a9ee  test    edx, edx
0x14015a9f0  jz      short loc_14015AA17
0x14015a9f2  sub     edx, 1
0x14015a9f5  jz      short loc_14015AA06
0x14015a9f7  sub     edx, 1
0x14015a9fa  jnz     short loc_14015AA17
0x14015a9fc  mov     rdx, [r10+8]
0x14015aa00  mov     rdx, [rdx+8]
0x14015aa04  jmp     short loc_14015AA25
0x14015aa06  mov     rcx, [r10+8]
0x14015aa0a  mov     rcx, [rcx]
0x14015aa0d  mov     rdx, qword ptr [rsp+768h+var_108+8]
0x14015aa15  jmp     short loc_14015AA2D
0x14015aa17  mov     r8d, 1
0x14015aa1d  mov     rdx, qword ptr [rsp+768h+var_108+8]
0x14015aa25  mov     rcx, qword ptr [rsp+768h+var_108]
0x14015aa2d  cmp     rbx, r10
0x14015aa30  jnz     loc_14015B708
0x14015aa36  movzx   r10d, byte ptr [rbx]
0x14015aa3a  cmp     r10d, 5
0x14015aa3e  ja      short loc_14015AA6A
0x14015aa40  jz      short loc_14015AA6A
0x14015aa42  mov     r11d, r10d
0x14015aa45  test    r10d, r10d
0x14015aa48  jz      short loc_14015AA6A
0x14015aa4a  sub     r11d, 1
0x14015aa4e  jz      short loc_14015AA60
0x14015aa50  sub     r11d, 1
0x14015aa54  jnz     short loc_14015AA6A
0x14015aa56  cmp     qword ptr [rsp+768h+var_6E0+8], rdx
0x14015aa5e  jmp     short loc_14015AA6D
0x14015aa60  cmp     qword ptr [rsp+768h+var_6E0], rcx
0x14015aa68  jmp     short loc_14015AA6D
0x14015aa6a  cmp     rax, r8
0x14015aa6d  setz    cl
0x14015aa70  test    cl, cl
0x14015aa72  jnz     loc_14015B637
0x14015aa78  movups  [rsp+768h+var_98], xmm0
0x14015aa80  movdqu  [rsp+768h+var_88], xmm6
0x14015aa89  mov     byte ptr [rsp+768h+var_98], r14b
0x14015aa91  movdqu  xmmword ptr [rsp+768h+var_78], xmm0
0x14015aa9a  mov     [rsp+768h+var_68], r14
0x14015aaa2  cmp     r10d, 4
0x14015aaa6  ja      short loc_14015AAD5
0x14015aaa8  test    r10d, r10d
0x14015aaab  jz      loc_14015B74C
0x14015aab1  sub     r10d, 1
0x14015aab5  jz      short loc_14015AAC7
0x14015aab7  sub     r10d, 1
0x14015aabb  jnz     short loc_14015AAD5
0x14015aabd  mov     rbx, qword ptr [rsp+768h+var_6E0+8]
0x14015aac5  jmp     short loc_14015AADE
0x14015aac7  mov     rbx, qword ptr [rsp+768h+var_6E0]
0x14015aacf  add     rbx, 40h ; '@'
0x14015aad3  jmp     short loc_14015AADE
0x14015aad5  test    rax, rax
0x14015aad8  jnz     loc_14015BCE0
0x14015aade  mov     rdx, rbx
0x14015aae1  lea     rcx, [rsp+768h+var_6C8]
0x14015aae9  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA@AEBV012@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>(nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> const &)
0x14015aaee  nop
0x14015aaef  cmp     [rsp+768h+var_6C8], 1
0x14015aaf7  jnz     loc_14015B5A0
0x14015aafd  xorps   xmm0, xmm0
0x14015ab00  movups  [rsp+768h+var_690], xmm0
0x14015ab08  mov     [rsp+768h+var_680], r14
0x14015ab10  mov     [rsp+768h+var_678], r14
0x14015ab18  mov     r8d, 4
0x14015ab1e  lea     rdx, aName_0; "name"
0x14015ab25  lea     rcx, [rsp+768h+var_690]
0x14015ab2d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14015ab32  lea     rdx, [rsp+768h+var_690]
0x14015ab3a  lea     rcx, [rsp+768h+var_6C8]
0x14015ab42  call    ??A?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAAEAV012@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::operator[](std::string)
0x14015ab47  lea     rdx, [rsp+768h+var_50]
0x14015ab4f  mov     rcx, rax
0x14015ab52  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::get<std::string,std::string>(void)
0x14015ab57  or      esi, 1
0x14015ab5a  mov     [rsp+768h+var_738], esi
0x14015ab5e  lea     rdx, [rsp+768h+var_50]
0x14015ab66  lea     rcx, [rsp+768h+var_98]; void *
0x14015ab6e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x14015ab73  xorps   xmm0, xmm0
0x14015ab76  movups  [rsp+768h+var_728], xmm0
0x14015ab7b  mov     qword ptr [rsp+768h+var_718], r14
0x14015ab80  mov     qword ptr [rsp+768h+var_718+8], r14
0x14015ab85  mov     r8d, 5
0x14015ab8b  lea     rdx, aRules; "rules"
0x14015ab92  lea     rcx, [rsp+768h+var_728]
0x14015ab97  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14015ab9c  lea     rdx, [rsp+768h+var_728]
0x14015aba1  lea     rcx, [rsp+768h+var_6C8]
0x14015aba9  call    ??A?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAAEAV012@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::operator[](std::string)
0x14015abae  mov     rdx, rax
0x14015abb1  lea     rcx, [rsp+768h+var_C0]
0x14015abb9  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA@AEBV012@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>(nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> const &)
0x14015abbe  nop
0x14015abbf  cmp     [rsp+768h+var_C0], 2
0x14015abc7  jnz     loc_14015B57E
0x14015abcd  mov     rax, [rsp+768h+var_B8]
0x14015abd5  mov     r9, [rax+8]
0x14015abd9  sub     r9, [rax]
0x14015abdc  sar     r9, 4
0x14015abe0  cmp     r9, 10h
0x14015abe4  jbe     loc_14015AC8D
0x14015abea  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14015abf1  jl      short loc_14015AC18
0x14015abf3  lfence
0x14015abf6  mov     [rsp+768h+var_748], 10h
0x14015abff  lea     r8, aExceededMaxTra; "Exceeded max transmit rules %d>%d for p"...
0x14015ac06  lea     rdx, a0123456789abcd_2+10h; "MATSDK"
0x14015ac0d  mov     ecx, 1
0x14015ac12  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14015ac17  nop
0x14015ac18  mov     dl, [rsp+768h+var_C0]
0x14015ac1f  lea     rcx, [rsp+768h+var_B8]
0x14015ac27  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14015ac2c  nop
0x14015ac2d  lea     rcx, [rsp+768h+var_50]
0x14015ac35  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14015ac3a  nop
0x14015ac3b  mov     dl, [rsp+768h+var_6C8]
0x14015ac42  lea     rcx, [rsp+768h+var_6C0]
0x14015ac4a  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14015ac4f  nop
0x14015ac50  lea     rcx, [rsp+768h+var_78]
0x14015ac58  call    ?_Tidy@?$vector@UTransmitProfileRule@Events@Applications@Microsoft@@V?$allocator@UTransmitProfileRule@Events@Applications@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Applications::Events::TransmitProfileRule>::_Tidy(void)
0x14015ac5d  lea     rcx, [rsp+768h+var_98]
0x14015ac65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14015ac6a  nop
0x14015ac6b  mov     dl, [rsp+768h+var_D0]
0x14015ac72  lea     rcx, [rsp+768h+var_C8]
0x14015ac7a  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14015ac7f  nop
0x14015ac80  mov     rbx, [rsp+768h+var_670]
0x14015ac88  jmp     loc_14015B6A3
0x14015ac8d  mov     rbx, [rsp+768h+var_78]
0x14015ac95  mov     rdi, [rsp+768h+var_78+8]
0x14015ac9d  cmp     rbx, rdi
0x14015aca0  jz      short loc_14015ACC4
0x14015aca2  lea     rcx, [rbx+10h]
0x14015aca6  call    ?_Tidy@?$vector@HV?$allocator@H@std@@@std@@AEAAXXZ; std::vector<int>::_Tidy(void)
0x14015acab  add     rbx, 28h ; '('
0x14015acaf  cmp     rbx, rdi
0x14015acb2  jnz     short loc_14015ACA2
0x14015acb4  mov     rax, [rsp+768h+var_78]
0x14015acbc  mov     [rsp+768h+var_78+8], rax
0x14015acc4  lea     r15, [rsp+768h+var_C0]
0x14015accc  mov     [rsp+768h+var_708], r15
0x14015acd1  xorps   xmm0, xmm0
0x14015acd4  movdqu  [rsp+768h+var_700], xmm0
0x14015acda  xorps   xmm1, xmm1
0x14015acdd  movdqu  [rsp+768h+var_700+8], xmm1
0x14015ace3  mov     rdi, r12
0x14015ace6  mov     [rsp+768h+var_6F0], r12
0x14015aceb  movzx   ecx, byte ptr [r15]
0x14015acef  cmp     ecx, 5
0x14015acf2  ja      short loc_14015AD44
0x14015acf4  jz      short loc_14015AD44
0x14015acf6  mov     edx, ecx
0x14015acf8  test    ecx, ecx
0x14015acfa  jz      short loc_14015AD38
0x14015acfc  sub     edx, 1
0x14015acff  jz      short loc_14015AD22
0x14015ad01  sub     edx, 1
0x14015ad04  jz      short loc_14015AD14
0x14015ad06  test    ecx, ecx
0x14015ad08  jz      short loc_14015AD38
0x14015ad0a  sub     ecx, 1
0x14015ad0d  jz      short loc_14015AD22
0x14015ad0f  sub     ecx, 1
0x14015ad12  jnz     short loc_14015AD44
0x14015ad14  mov     rax, [r15+8]
0x14015ad18  mov     r12, [rax]
0x14015ad1b  mov     qword ptr [rsp+768h+var_700+8], r12
0x14015ad20  jmp     short loc_14015AD51
0x14015ad22  mov     rax, [r15+8]
0x14015ad26  mov     rbx, [rax]
0x14015ad29  mov     rbx, [rbx]
0x14015ad2c  mov     qword ptr [rsp+768h+var_700], rbx
0x14015ad31  mov     r12, qword ptr [rsp+768h+var_700+8]
0x14015ad36  jmp     short loc_14015AD56
0x14015ad38  mov     edi, 1
0x14015ad3d  mov     [rsp+768h+var_6F0], rdi
0x14015ad42  jmp     short loc_14015AD4C
0x14015ad44  mov     rdi, r14
0x14015ad47  mov     [rsp+768h+var_6F0], r14
0x14015ad4c  mov     r12, qword ptr [rsp+768h+var_700+8]
0x14015ad51  mov     rbx, qword ptr [rsp+768h+var_700]
0x14015ad56  mov     r11, 8000000000000000h
0x14015ad60  lea     r9, [rsp+768h+var_C0]
  ... truncated ...
```

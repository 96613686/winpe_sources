# Microsoft::Applications::Experimentation::ECS::ECSConfigCache::_LoadConfig(void)

- ea: `0x14014ca34`
- end: `0x14014d961`
- name: `?_LoadConfig@ECSConfigCache@ECS@Experimentation@Applications@Microsoft@@AEAA_NXZ`
- size: `3885`
- prototype: `bool __fastcall(Microsoft::Applications::Experimentation::ECS::ECSConfigCache *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140148980`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a130`
- `0x14003a5c0`
- `0x14003c78c`
- `0x14007f0f4`
- `0x14007fb68`
- `0x140084a18`
- `0x1400fe950`
- `0x1400fedd4`
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
- `0x140140d38`
- `0x140140e14`
- `0x140145880`
- `0x14014baa0`
- `0x14014bb9c`
- `0x14014bc98`
- `0x14014bd94`
- `0x14014c308`
- `0x14014ca34`
- `0x140166250`
- `0x1401662d0`

## string_xrefs

- `0x14014d895`: `cannot compare iterators of different containers`
- `0x14014d91d`: `cannot compare iterators of different containers`
- `0x14014cb14`: `[ECSClient]: Failed to load config from local cache`
- `0x14014ca80`: `[ECSClient]: loading configs from local cache [%s]`
- `0x14014d7c5`: `[ECSClient]: Parsed config is of wrong format`
- `0x14014cc0e`: `[ECSClient]: Config loaded from local cache has successfully parsed`
- `0x14014cb3f`: `[ECSClient]: No config found in local cache`
- `0x14014cfa8`: `[ECSClient]: No RequestName found in this config, skip it.`
- `0x14014d78d`: `[ECSClient]: Done loading %u configs from offline storage [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall Microsoft::Applications::Experimentation::ECS::ECSConfigCache::_LoadConfig(
        Microsoft::Applications::Experimentation::ECS::ECSConfigCache *this)
{
  Microsoft::Applications::Experimentation::ECS::ECSConfigCache *v1; // r12
  const char *v2; // r9
  char v3; // di
  __int64 v4; // rcx
  int v5; // eax
  __int64 v7; // rax
  char v8; // dl
  unsigned __int8 **v9; // r8
  unsigned __int8 **v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r10d
  _BYTE *v15; // r14
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdx
  unsigned __int8 *v18; // rcx
  unsigned __int8 *v19; // rax
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  bool v22; // zf
  __int64 v23; // r8
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned __int64 v26; // rbx
  unsigned __int8 *v27; // r12
  __int64 v28; // r13
  unsigned __int8 *v29; // r14
  char v30; // al
  __int64 *v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int8 *v33; // rcx
  unsigned __int8 *v34; // rax
  bool v35; // zf
  _BYTE *v36; // rax
  __int64 v37; // r8
  __int64 v38; // r9
  void **v39; // rbx
  __int64 v40; // rdx
  __int64 v41; // r8
  _BYTE *v42; // rax
  __int64 v43; // rdx
  unsigned __int8 *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  char *v47; // rax
  __int64 v48; // rdx
  Microsoft::Applications::Events::PlatformAbstraction *v49; // rcx
  __int64 v50; // rdx
  _BYTE *v51; // rax
  __int64 v52; // r8
  __int64 v53; // r9
  void **v54; // rbx
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer *v55; // rcx
  __int64 UtcSystemTimeMs; // rax
  signed __int64 v57; // rcx
  signed __int64 v58; // rax
  __int64 v59; // rdx
  _BYTE *v60; // rax
  __int64 v61; // r8
  __int64 v62; // r9
  void **v63; // rbx
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rax
  char v67; // dl
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // rbx
  __int64 v71; // r8
  size_t v72; // r14
  void **v73; // r9
  void *v74; // r12
  _QWORD *v75; // r14
  size_t v76; // r12
  void **v77; // r9
  __int64 v78; // rax
  char v79; // dl
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // r8
  _QWORD *v83; // r14
  size_t v84; // r12
  void **v85; // r9
  __int64 v86; // rdx
  const char *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // [rsp+0h] [rbp-338h] BYREF
  unsigned __int8 *v90[5]; // [rsp+30h] [rbp-308h] BYREF
  _BYTE *v91; // [rsp+58h] [rbp-2E0h] BYREF
  __int128 v92; // [rsp+60h] [rbp-2D8h]
  unsigned __int64 v93; // [rsp+70h] [rbp-2C8h]
  Microsoft::Applications::Experimentation::ECS::ECSConfigCache *v94; // [rsp+78h] [rbp-2C0h]
  __int64 v95; // [rsp+80h] [rbp-2B8h] BYREF
  unsigned __int8 *v96; // [rsp+88h] [rbp-2B0h]
  __int128 v97; // [rsp+90h] [rbp-2A8h]
  _OWORD v98[2]; // [rsp+A0h] [rbp-298h] BYREF
  _QWORD v99[8]; // [rsp+C0h] [rbp-278h] BYREF
  _OWORD v100[2]; // [rsp+100h] [rbp-238h] BYREF
  _OWORD v101[2]; // [rsp+120h] [rbp-218h] BYREF
  _OWORD v102[2]; // [rsp+140h] [rbp-1F8h] BYREF
  _BYTE v103[16]; // [rsp+160h] [rbp-1D8h] BYREF
  _BYTE v104[16]; // [rsp+170h] [rbp-1C8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+180h] [rbp-1B8h] BYREF
  _BYTE v106[56]; // [rsp+1F0h] [rbp-148h] BYREF
  _BYTE v107[56]; // [rsp+228h] [rbp-110h] BYREF
  void *v108; // [rsp+260h] [rbp-D8h] BYREF
  __int64 v109; // [rsp+268h] [rbp-D0h] BYREF
  _BYTE v110[8]; // [rsp+270h] [rbp-C8h] BYREF
  unsigned __int8 **v111; // [rsp+278h] [rbp-C0h] BYREF
  _BYTE v112[8]; // [rsp+280h] [rbp-B8h] BYREF
  unsigned __int8 **v113; // [rsp+288h] [rbp-B0h] BYREF
  void *Src[2]; // [rsp+290h] [rbp-A8h] BYREF
  size_t Size[2]; // [rsp+2A0h] [rbp-98h]
  void *v116[2]; // [rsp+2B0h] [rbp-88h] BYREF
  size_t v117[2]; // [rsp+2C0h] [rbp-78h]
  signed __int64 v118; // [rsp+2D0h] [rbp-68h]
  _BYTE v119[8]; // [rsp+2D8h] [rbp-60h] BYREF
  __int64 v120; // [rsp+2E0h] [rbp-58h] BYREF
  void *v121[2]; // [rsp+2E8h] [rbp-50h] BYREF
  size_t v122[3]; // [rsp+2F8h] [rbp-40h]

  v1 = this;
  v94 = this;
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    v2 = (const char *)this;
    if ( *((_QWORD *)this + 3) > 0xFu )
      v2 = *(const char **)this;
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.ECS",
      "[ECSClient]: loading configs from local cache [%s]",
      v2);
  }
  v3 = 0;
  v108 = 0;
  v109 = 0;
  v90[4] = (unsigned __int8 *)v1 + 56;
  if ( Mtx_lock((Microsoft::Applications::Experimentation::ECS::ECSConfigCache *)((char *)v1 + 56)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v1 + 33) == 0x7FFFFFFF )
  {
    *((_DWORD *)v1 + 33) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v4 = *((_QWORD *)v1 + 4);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, void **, __int64 *, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, &v108, &v109, 0);
    if ( v5 < 0 )
    {
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          1,
          "EventsSDK.ECS",
          "[ECSClient]: Failed to load config from local cache");
LABEL_16:
      Mtx_unlock((Microsoft::Applications::Experimentation::ECS::ECSConfigCache *)((char *)v1 + 56));
      return v3;
    }
    if ( !v5 || !v109 )
    {
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          4,
          "EventsSDK.ECS",
          "[ECSClient]: No config found in local cache");
      v3 = 1;
      goto LABEL_16;
    }
  }
  Mtx_unlock((Microsoft::Applications::Experimentation::ECS::ECSConfigCache *)((char *)v1 + 56));
  *((char *)v108 + v109 - 1) = 0;
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
    v112,
    0);
  try
  {
    v99[7] = 0;
    v7 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::parse<char const *>(
           v110,
           &v108,
           v99);
    v8 = v112[0];
    v112[0] = *(_BYTE *)v7;
    *(_BYTE *)v7 = v8;
    v9 = v113;
    v113 = *(unsigned __int8 ***)(v7 + 8);
    v10 = v113;
    *(_QWORD *)(v7 + 8) = v9;
    LOBYTE(v10) = *(_BYTE *)v7;
    nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
      v7 + 8,
      v10);
    operator delete(v108, v11);
    v108 = 0;
    v14 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    {
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "EventsSDK.ECS",
        "[ECSClient]: Config loaded from local cache has successfully parsed");
      v14 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
    }
  }
  catch ( ... )
  {
    operator delete(v108, (const struct std::nothrow_t *)&v89);
    v108 = 0;
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "EventsSDK.ECS",
        "[ECSClient]: Failed to parse config loaded from local cache");
    LOBYTE(v88) = v112[0];
    nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
      &v113,
      v88);
    return 0;
  }
  if ( v112[0] == 2 )
  {
    v15 = v112;
    v91 = v112;
    v92 = 0u;
    v16 = 0x8000000000000000uLL;
    v93 = 0x8000000000000000uLL;
    *((_QWORD *)&v92 + 1) = *v113;
    while ( 1 )
    {
      memset(&v90[1], 0, 24);
      v17 = 0x8000000000000000uLL;
      if ( v112[0] <= 4u )
      {
        v13 = v112[0];
        if ( v112[0] )
        {
          v13 = (unsigned int)v112[0] - 1;
          if ( v112[0] == 1 )
            goto LABEL_31;
          v13 = (unsigned int)v112[0] - 2;
          if ( v112[0] == 2 )
            goto LABEL_30;
        }
      }
      if ( v112[0] > 4u || !v112[0] )
        goto LABEL_32;
      if ( v112[0] == 1 )
      {
LABEL_31:
        v19 = *v113;
        v18 = v90[2];
        goto LABEL_34;
      }
      if ( v112[0] == 2 )
      {
LABEL_30:
        v18 = v113[1];
      }
      else
      {
LABEL_32:
        v17 = 1;
        v18 = v90[2];
      }
      v19 = v90[1];
LABEL_34:
      if ( v15 != v112 )
      {
        std::string::string(v99, "cannot compare iterators of different containers", v13);
        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
          (__int64)v107,
          212,
          (__int64)v99);
        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v107;
      }
      v20 = (unsigned __int8)*v15;
      if ( v20 > 4 || !*v15 )
      {
LABEL_41:
        v22 = v16 == v17;
        goto LABEL_42;
      }
      v21 = v20 - 1;
      if ( v21 )
      {
        if ( v21 != 1 )
          goto LABEL_41;
        v22 = *((_QWORD *)&v92 + 1) == (_QWORD)v18;
      }
      else
      {
        v22 = (_QWORD)v92 == (_QWORD)v19;
      }
LABEL_42:
      if ( v22 )
      {
        if ( v14 >= 4 )
        {
          v87 = (const char *)v1;
          if ( *((_QWORD *)v1 + 3) > 0xFu )
            v87 = *(const char **)v1;
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            4,
            "EventsSDK.ECS",
            "[ECSClient]: Done loading %u configs from offline storage [%s]",
            *((_QWORD *)v1 + 6),
            v87);
        }
        LOBYTE(v17) = v112[0];
        nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
          &v113,
          v17);
        return 1;
      }
      Microsoft::Applications::Experimentation::ECS::ECSConfig::ECSConfig((Microsoft::Applications::Experimentation::ECS::ECSConfig *)Src);
      v24 = (unsigned __int8)*v15;
      if ( v24 > 4 )
        goto LABEL_49;
      if ( !*v15 )
      {
        std::string::string(v99, "cannot get value", v23);
        nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
          (__int64)pExceptionObject,
          214,
          (__int64)v99);
        throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)pExceptionObject;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v15 = (_BYTE *)(v92 + 64);
        goto LABEL_50;
      }
      if ( v25 == 1 )
      {
        v15 = (_BYTE *)*((_QWORD *)&v92 + 1);
      }
      else
      {
LABEL_49:
        if ( v16 )
        {
          std::string::string(v99, "cannot get value", v23);
          nlohmann::json_abi_v3_11_3::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void> *,0>(
            (__int64)v106,
            214,
            (__int64)v99);
          throw (nlohmann::json_abi_v3_11_3::detail::invalid_iterator *)v106;
        }
      }
LABEL_50:
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
        v110,
        v15);
      v90[0] = v110;
      *(_OWORD *)&v90[1] = 0u;
      v26 = 0x8000000000000000uLL;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] <= 4u && v110[0] )
      {
        if ( v110[0] == 1 )
          goto LABEL_59;
        if ( v110[0] == 2 )
          goto LABEL_58;
      }
      v26 = 0x8000000000000000uLL;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] <= 4u && v110[0] )
      {
        if ( v110[0] == 1 )
        {
LABEL_59:
          v90[1] = *v111;
          goto LABEL_61;
        }
        if ( v110[0] == 2 )
        {
LABEL_58:
          v90[2] = v111[1];
          goto LABEL_61;
        }
      }
      v26 = 1;
      v90[3] = (unsigned __int8 *)1;
LABEL_61:
      if ( v110[0] == 1 )
      {
        v27 = *v111;
        v28 = *((_QWORD *)*v111 + 1);
        HIDWORD(v96) = 0;
        v29 = v27;
        while ( !*(_BYTE *)(v28 + 25) )
        {
          v30 = std::operator<<char>(v28 + 32, "RequestName");
          if ( !v30 )
            v29 = (unsigned __int8 *)v28;
          v31 = (__int64 *)(v28 + 16);
          if ( !v30 )
            v31 = (__int64 *)v28;
          v28 = *v31;
        }
        if ( v29[25] || (unsigned __int8)std::operator<<char>("RequestName", v29 + 32) )
          v29 = v27;
        v90[1] = v29;
        v1 = v94;
      }
      v96 = 0;
      v97 = 0;
      v32 = 0x8000000000000000uLL;
      if ( v110[0] <= 4u && v110[0] )
      {
        if ( v110[0] == 1 )
          goto LABEL_82;
        if ( v110[0] == 2 )
          goto LABEL_81;
      }
      if ( v110[0] > 4u || !v110[0] )
        goto LABEL_83;
      if ( v110[0] != 1 )
      {
        if ( v110[0] == 2 )
        {
LABEL_81:
          v33 = v111[1];
        }
        else
        {
LABEL_83:
          v32 = 1;
          v33 = (unsigned __int8 *)v97;
        }
        v34 = v96;
        goto LABEL_85;
      }
LABEL_82:
      v34 = *v111;
      v33 = (unsigned __int8 *)v97;
LABEL_85:
      if ( v110[0] <= 4u && v110[0] )
      {
        if ( v110[0] == 1 )
        {
          v35 = v34 == v90[1];
          goto LABEL_92;
        }
        if ( v110[0] == 2 )
        {
          v35 = v33 == v90[2];
          goto LABEL_92;
        }
      }
      v35 = v32 == v26;
LABEL_92:
      if ( v35 )
      {
        if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 2 )
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            2,
            "EventsSDK.ECS",
            "[ECSClient]: No RequestName found in this config, skip it.");
        goto LABEL_180;
      }
      v36 = (_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                       v90,
                       v32);
      v39 = (void **)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                       v36,
                       &v95,
                       v37,
                       v38);
      if ( Src != v39 )
      {
        std::string::_Tidy_deallocate(Src);
        *(_OWORD *)Src = *(_OWORD *)v39;
        *(_OWORD *)Size = *((_OWORD *)v39 + 1);
        v39[2] = 0;
        v39[3] = (void *)15;
        *(_BYTE *)v39 = 0;
      }
      std::string::_Tidy_deallocate(&v95);
      v118 = 0;
      memset(v100, 0, sizeof(v100));
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[19],0>(
        (__int64)v110,
        (unsigned __int8 **)v100);
      v90[0] = v110;
      *(_OWORD *)&v90[1] = 0u;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] > 4u || !v110[0] )
      {
LABEL_106:
        v90[3] = (unsigned __int8 *)1;
        goto LABEL_107;
      }
      if ( v110[0] == 1 )
      {
LABEL_105:
        v90[1] = *v111;
        goto LABEL_107;
      }
      if ( v110[0] != 2 )
      {
        if ( v110[0] == 1 )
          goto LABEL_105;
        if ( v110[0] != 2 )
          goto LABEL_106;
      }
      v90[2] = v111[1];
LABEL_107:
      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
             v90,
             (unsigned __int8 **)v100) )
      {
        v42 = (_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                         v100,
                         v40);
        if ( *v42 == 5 || *v42 == 6 )
        {
          v44 = (unsigned __int8 *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                                     v100,
                                     v43);
          v118 = (int)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<int,int>(
                        v44,
                        v45,
                        v46);
        }
      }
      if ( v122[1] < 4 )
      {
        std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v121, 4, v41, "test");
      }
      else
      {
        v47 = (char *)v121;
        if ( v122[1] > 0xF )
          v47 = (char *)v121[0];
        v122[0] = 4;
        strcpy(v47, "test");
      }
      memset(v98, 0, sizeof(v98));
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[14],0>(
        (__int64)v110,
        (unsigned __int8 **)v98);
      v90[0] = v110;
      *(_OWORD *)&v90[1] = 0u;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] > 4u || !v110[0] )
      {
LABEL_124:
        v90[3] = (unsigned __int8 *)1;
        goto LABEL_125;
      }
      if ( v110[0] == 1 )
      {
LABEL_123:
        v90[1] = *v111;
        goto LABEL_125;
      }
      if ( v110[0] != 2 )
      {
        if ( v110[0] == 1 )
          goto LABEL_123;
        if ( v110[0] != 2 )
          goto LABEL_124;
      }
      v90[2] = v111[1];
LABEL_125:
      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
             v90,
             (unsigned __int8 **)v98)
        && *(_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                       v98,
                       v48) == 3 )
      {
        v51 = (_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                         v98,
                         v50);
        v54 = (void **)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                         v51,
                         v99,
                         v52,
                         v53);
        if ( v121 != v54 )
        {
          std::string::_Tidy_deallocate(v121);
          *(_OWORD *)v121 = *(_OWORD *)v54;
          *(_OWORD *)v122 = *((_OWORD *)v54 + 1);
          v54[2] = 0;
          v54[3] = (void *)15;
          *(_BYTE *)v54 = 0;
        }
        std::string::_Tidy_deallocate(v99);
      }
      Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v49);
      UtcSystemTimeMs = Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::getUtcSystemTimeMs(v55);
      v57 = ((__int64)((unsigned __int128)(UtcSystemTimeMs * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 7)
          + 86400
          + ((unsigned __int64)((unsigned __int128)(UtcSystemTimeMs * (__int128)0x20C49BA5E353F7CFLL) >> 64) >> 63);
      v58 = v118;
      if ( v118 > v57 )
        v58 = v57;
      v118 = v58;
      memset(v101, 0, sizeof(v101));
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[5],0>(
        (__int64)v110,
        (unsigned __int8 **)v101);
      v90[0] = v110;
      *(_OWORD *)&v90[1] = 0u;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] <= 4u && v110[0] )
      {
        if ( v110[0] == 1 )
          goto LABEL_139;
        if ( v110[0] == 2 )
          goto LABEL_138;
        if ( v110[0] == 1 )
        {
LABEL_139:
          v90[1] = *v111;
          goto LABEL_141;
        }
        if ( v110[0] == 2 )
        {
LABEL_138:
          v90[2] = v111[1];
          goto LABEL_141;
        }
      }
      v90[3] = (unsigned __int8 *)1;
LABEL_141:
      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
             v90,
             (unsigned __int8 **)v101) )
      {
        v60 = (_BYTE *)nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                         v101,
                         v59);
        v63 = (void **)nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::get<std::string,std::string>(
                         v60,
                         v98,
                         v61,
                         v62);
        if ( v116 != v63 )
        {
          std::string::_Tidy_deallocate(v116);
          *(_OWORD *)v116 = *(_OWORD *)v63;
          *(_OWORD *)v117 = *((_OWORD *)v63 + 1);
          v63[2] = 0;
          v63[3] = (void *)15;
          *(_BYTE *)v63 = 0;
        }
        std::string::_Tidy_deallocate(v98);
      }
      memset(v102, 0, sizeof(v102));
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::find<char const (&)[15],0>(
        (__int64)v110,
        (unsigned __int8 **)v102);
      v90[0] = v110;
      *(_OWORD *)&v90[1] = 0u;
      v90[3] = (unsigned __int8 *)0x8000000000000000LL;
      if ( v110[0] > 4u || !v110[0] )
      {
LABEL_153:
        v90[3] = (unsigned __int8 *)1;
        goto LABEL_154;
      }
      if ( v110[0] == 1 )
      {
LABEL_152:
        v90[1] = *v111;
        goto LABEL_154;
      }
      if ( v110[0] != 2 )
      {
        if ( v110[0] == 1 )
          goto LABEL_152;
        if ( v110[0] != 2 )
          goto LABEL_153;
      }
      v90[2] = v111[1];
LABEL_154:
      if ( nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator!=<nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>,0>(
             v90,
             (unsigned __int8 **)v102) )
      {
        v65 = nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator*(
                v102,
                v64);
        v66 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
                v103,
                v65);
        v67 = v119[0];
        v119[0] = *(_BYTE *)v66;
        *(_BYTE *)v66 = v67;
        v68 = v120;
        v120 = *(_QWORD *)(v66 + 8);
        v69 = v120;
        *(_QWORD *)(v66 + 8) = v68;
        LOBYTE(v69) = *(_BYTE *)v66;
        nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
          v66 + 8,
          v69);
      }
      v70 = std::map<std::string,Microsoft::Applications::Experimentation::ECS::ECSConfig>::operator[](
              (char *)v1 + 40,
              Src);
      if ( (void **)v70 != Src )
      {
        v72 = Size[0];
        v73 = Src;
        if ( Size[1] > 0xF )
          v73 = (void **)Src[0];
        if ( Size[0] > *(_QWORD *)(v70 + 24) )
        {
          _mm_lfence();
          std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(v70, Size[0], v71, v73);
        }
        else
        {
          v74 = (void *)v70;
          if ( *(_QWORD *)(v70 + 24) > 0xFu )
            v74 = *(void **)v70;
          *(_QWORD *)(v70 + 16) = Size[0];
          memmove(v74, v73, v72);
          *((_BYTE *)v74 + v72) = 0;
        }
      }
      v75 = (_QWORD *)(v70 + 32);
      if ( (void **)(v70 + 32) != v116 )
      {
        v76 = v117[0];
        v77 = v116;
        if ( v117[1] > 0xF )
          v77 = (void **)v116[0];
        if ( v117[0] > *(_QWORD *)(v70 + 56) )
        {
          _mm_lfence();
          std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
            v70 + 32,
            v117[0],
            v71,
            v77);
        }
        else
        {
          if ( *(_QWORD *)(v70 + 56) > 0xFu )
            v75 = (_QWORD *)*v75;
          *(_QWORD *)(v70 + 48) = v117[0];
          memmove(v75, v77, v76);
          *((_BYTE *)v75 + v76) = 0;
        }
      }
      *(_QWORD *)(v70 + 64) = v118;
      v78 = nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>(
              v104,
              v119);
      v79 = *(_BYTE *)(v70 + 72);
      *(_BYTE *)(v70 + 72) = *(_BYTE *)v78;
      *(_BYTE *)v78 = v79;
      v80 = *(_QWORD *)(v70 + 80);
      v81 = *(_QWORD *)(v78 + 8);
      *(_QWORD *)(v70 + 80) = v81;
      *(_QWORD *)(v78 + 8) = v80;
      LOBYTE(v81) = *(_BYTE *)v78;
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
        v78 + 8,
        v81);
      v83 = (_QWORD *)(v70 + 88);
      if ( (void **)(v70 + 88) != v121 )
      {
        v84 = v122[0];
        v85 = v121;
        if ( v122[1] > 0xF )
          v85 = (void **)v121[0];
        if ( v122[0] > *(_QWORD *)(v70 + 112) )
        {
          _mm_lfence();
          std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
            v70 + 88,
            v122[0],
            v82,
            v85);
        }
        else
        {
          if ( *(_QWORD *)(v70 + 112) > 0xFu )
            v83 = (_QWORD *)*v83;
          *(_QWORD *)(v70 + 104) = v122[0];
          memmove(v83, v85, v84);
          *((_BYTE *)v83 + v84) = 0;
        }
      }
LABEL_180:
      LOBYTE(v32) = v110[0];
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
        &v111,
        v32);
      std::string::_Tidy_deallocate(v121);
      LOBYTE(v86) = v119[0];
      nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
        &v120,
        v86);
      std::string::_Tidy_deallocate(v116);
      std::string::_Tidy_deallocate(Src);
      nlohmann::json_abi_v3_11_3::detail::iter_impl<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::operator++(&v91);
      v16 = v93;
      v15 = v91;
      v14 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
      v1 = v94;
    }
  }
  if ( v14 >= 1 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      1,
      "EventsSDK.ECS",
      "[ECSClient]: Parsed config is of wrong format");
  LOBYTE(v12) = v112[0];
  nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>::json_value::destroy(
    &v113,
    v12);
  return 0;
}

```

## disassembly

```asm
0x14014ca34  mov     [rsp+arg_8], rbx
0x14014ca39  mov     [rsp+arg_10], rdi
0x14014ca3e  mov     [rsp+arg_18], r12
0x14014ca43  push    r13
0x14014ca45  push    r14
0x14014ca47  push    r15
0x14014ca49  sub     rsp, 320h
0x14014ca50  mov     rax, cs:__security_cookie
0x14014ca57  xor     rax, rsp
0x14014ca5a  mov     [rsp+338h+var_28], rax
0x14014ca62  mov     r12, rcx
0x14014ca65  mov     [rsp+338h+var_2C0], rcx
0x14014ca6a  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014ca71  jl      short loc_14014CA9D
0x14014ca73  mov     r9, rcx
0x14014ca76  cmp     qword ptr [rcx+18h], 0Fh
0x14014ca7b  jbe     short loc_14014CA80
0x14014ca7d  mov     r9, [rcx]
0x14014ca80  lea     r8, aEcsclientLoadi; "[ECSClient]: loading configs from local"...
0x14014ca87  lea     r13, ?digits_to_99@?1???$dump_integer@_K$0A@@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@AEAAX_K@Z@4V?$array@V?$array@D$01@std@@$0GE@@std@@B+0C8h; "EventsSDK.ECS"
0x14014ca8e  mov     rdx, r13
0x14014ca91  mov     ecx, 4
0x14014ca96  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14014ca9b  jmp     short loc_14014CAA4
0x14014ca9d  lea     r13, ?digits_to_99@?1???$dump_integer@_K$0A@@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@AEAAX_K@Z@4V?$array@V?$array@D$01@std@@$0GE@@std@@B+0C8h; "EventsSDK.ECS"
0x14014caa4  xor     edi, edi
0x14014caa6  mov     [rsp+338h+var_D8], rdi
0x14014caae  mov     [rsp+338h+var_D0], rdi
0x14014cab6  lea     rbx, [r12+38h]
0x14014cabb  mov     [rsp+338h+var_2E8], rbx
0x14014cac0  mov     rcx, rbx; _Mtx_t
0x14014cac3  call    _Mtx_lock
0x14014cac8  test    eax, eax
0x14014caca  jnz     loc_14014D836
0x14014cad0  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x14014cad7  jz      loc_14014D83F
0x14014cadd  mov     rcx, [r12+20h]
0x14014cae2  test    rcx, rcx
0x14014cae5  jz      short loc_14014CB66
0x14014cae7  mov     rax, [rcx]
0x14014caea  xor     r9d, r9d
0x14014caed  lea     r8, [rsp+338h+var_D0]
0x14014caf5  lea     rdx, [rsp+338h+var_D8]
0x14014cafd  mov     rax, [rax+28h]
0x14014cb01  call    cs:__guard_dispatch_icall_fptr
0x14014cb07  test    eax, eax
0x14014cb09  jns     short loc_14014CB2A
0x14014cb0b  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014cb12  jl      short loc_14014CB56
0x14014cb14  lea     r8, aEcsclientFaile_1; "[ECSClient]: Failed to load config from"...
0x14014cb1b  mov     rdx, r13
0x14014cb1e  mov     ecx, 1
0x14014cb23  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14014cb28  jmp     short loc_14014CB56
0x14014cb2a  jz      short loc_14014CB36
0x14014cb2c  cmp     [rsp+338h+var_D0], rdi
0x14014cb34  jnz     short loc_14014CB66
0x14014cb36  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014cb3d  jl      short loc_14014CB53
0x14014cb3f  lea     r8, aEcsclientNoCon; "[ECSClient]: No config found in local c"...
0x14014cb46  mov     rdx, r13
0x14014cb49  mov     ecx, 4
0x14014cb4e  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14014cb53  mov     dil, 1
0x14014cb56  mov     rcx, rbx; _Mtx_t
0x14014cb59  call    _Mtx_unlock
0x14014cb5e  mov     al, dil
0x14014cb61  jmp     loc_14014D808
0x14014cb66  mov     rcx, rbx; _Mtx_t
0x14014cb69  call    _Mtx_unlock
0x14014cb6e  mov     rcx, [rsp+338h+var_D8]
0x14014cb76  mov     rax, [rsp+338h+var_D0]
0x14014cb7e  mov     [rax+rcx-1], dil
0x14014cb83  xor     edx, edx
0x14014cb85  lea     rcx, [rsp+338h+var_B8]
0x14014cb8d  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA@W4value_t@detail@12@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14014cb92  nop
0x14014cb93  mov     [rsp+338h+var_240], rdi
0x14014cb9b  lea     r8, [rsp+338h+var_278]
0x14014cba3  lea     rdx, [rsp+338h+var_D8]
0x14014cbab  lea     rcx, [rsp+338h+var_C8]
0x14014cbb3  call    ??$parse@PEBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@SA?AV012@$$QEAPEBDV?$function@$$A6A_NHW4parse_event_t@detail@json_abi_v3_11_3@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@34@@Z@std@@_N2@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::parse<char const *>(char const * &&,std::function<bool (int,nlohmann::json_abi_v3_11_3::detail::parse_event_t,nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> &)>,bool,bool)
0x14014cbb8  mov     dl, [rsp+338h+var_B8]
0x14014cbbf  mov     cl, [rax]
0x14014cbc1  mov     [rsp+338h+var_B8], cl
0x14014cbc8  mov     [rax], dl
0x14014cbca  lea     rcx, [rax+8]
0x14014cbce  mov     r8, [rsp+338h+var_B0]
0x14014cbd6  mov     rdx, [rcx]
0x14014cbd9  mov     [rsp+338h+var_B0], rdx
0x14014cbe1  mov     [rcx], r8
0x14014cbe4  mov     dl, [rax]
0x14014cbe6  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::json_value::destroy(nlohmann::json_abi_v3_11_3::detail::value_t)
0x14014cbeb  nop
0x14014cbec  mov     rcx, [rsp+338h+var_D8]; void *
0x14014cbf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14014cbf9  mov     [rsp+338h+var_D8], rdi
0x14014cc01  mov     r10d, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014cc08  cmp     r10d, 4
0x14014cc0c  jl      short loc_14014CC29
0x14014cc0e  lea     r8, aEcsclientConfi; "[ECSClient]: Config loaded from local c"...
0x14014cc15  mov     rdx, r13
0x14014cc18  mov     ecx, 4
0x14014cc1d  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14014cc22  mov     r10d, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014cc29  cmp     [rsp+338h+var_B8], 2
0x14014cc31  jnz     loc_14014D7BF
0x14014cc37  lea     r14, [rsp+338h+var_B8]
0x14014cc3f  mov     [rsp+338h+var_2E0], r14
0x14014cc44  xorps   xmm0, xmm0
0x14014cc47  movdqu  [rsp+338h+var_2D8], xmm0
0x14014cc4d  xorps   xmm1, xmm1
0x14014cc50  movdqu  [rsp+338h+var_2D8+8], xmm1
0x14014cc56  mov     r13, 8000000000000000h
0x14014cc60  mov     rbx, r13
0x14014cc63  mov     [rsp+338h+var_2C8], rbx
0x14014cc68  movzx   ecx, byte ptr [r14]
0x14014cc6c  mov     r15d, 5
0x14014cc72  cmp     ecx, r15d
0x14014cc75  ja      short loc_14014CCBD
0x14014cc77  jz      short loc_14014CCBD
0x14014cc79  mov     edx, ecx
0x14014cc7b  test    ecx, ecx
0x14014cc7d  jz      short loc_14014CCB6
0x14014cc7f  sub     edx, 1
0x14014cc82  jz      short loc_14014CCA5
0x14014cc84  sub     edx, 1
0x14014cc87  jz      short loc_14014CC97
0x14014cc89  test    ecx, ecx
0x14014cc8b  jz      short loc_14014CCB6
0x14014cc8d  sub     ecx, 1
0x14014cc90  jz      short loc_14014CCA5
0x14014cc92  sub     ecx, 1
0x14014cc95  jnz     short loc_14014CCBD
0x14014cc97  mov     rax, [r14+8]
0x14014cc9b  mov     rcx, [rax]
0x14014cc9e  mov     qword ptr [rsp+338h+var_2D8+8], rcx
0x14014cca3  jmp     short loc_14014CCC5
0x14014cca5  mov     rax, [r14+8]
0x14014cca9  mov     rcx, [rax]
0x14014ccac  mov     rax, [rcx]
0x14014ccaf  mov     qword ptr [rsp+338h+var_2D8], rax
0x14014ccb4  jmp     short loc_14014CCC5
0x14014ccb6  mov     ebx, 1
0x14014ccbb  jmp     short loc_14014CCC0
0x14014ccbd  mov     rbx, rdi
0x14014ccc0  mov     [rsp+338h+var_2C8], rbx
0x14014ccc5  lea     r9, [rsp+338h+var_B8]
0x14014cccd  xorps   xmm0, xmm0
0x14014ccd0  movdqu  [rsp+338h+var_300], xmm0
0x14014ccd6  xorps   xmm1, xmm1
0x14014ccd9  movdqu  [rsp+338h+var_300+8], xmm1
0x14014ccdf  mov     rdx, r13
0x14014cce2  movzx   ecx, byte ptr [r9]
0x14014cce6  cmp     ecx, r15d
0x14014cce9  ja      short loc_14014CD00
0x14014cceb  jz      short loc_14014CD00
0x14014cced  mov     r8d, ecx
0x14014ccf0  test    ecx, ecx
0x14014ccf2  jz      short loc_14014CD00
0x14014ccf4  sub     r8d, 1
0x14014ccf8  jz      short loc_14014CD1D
0x14014ccfa  sub     r8d, 1
0x14014ccfe  jz      short loc_14014CD13
0x14014cd00  cmp     ecx, 4
0x14014cd03  ja      short loc_14014CD2B
0x14014cd05  test    ecx, ecx
0x14014cd07  jz      short loc_14014CD2B
0x14014cd09  sub     ecx, 1
0x14014cd0c  jz      short loc_14014CD1D
0x14014cd0e  sub     ecx, 1
0x14014cd11  jnz     short loc_14014CD2B
0x14014cd13  mov     rcx, [r9+8]
0x14014cd17  mov     rcx, [rcx+8]
0x14014cd1b  jmp     short loc_14014CD35
0x14014cd1d  mov     rax, [r9+8]
0x14014cd21  mov     rax, [rax]
0x14014cd24  mov     rcx, qword ptr [rsp+338h+var_300+8]
0x14014cd29  jmp     short loc_14014CD3A
0x14014cd2b  mov     edx, 1
0x14014cd30  mov     rcx, qword ptr [rsp+338h+var_300+8]
0x14014cd35  mov     rax, qword ptr [rsp+338h+var_300]
0x14014cd3a  cmp     r14, r9
0x14014cd3d  jnz     loc_14014D91D
0x14014cd43  movzx   r9d, byte ptr [r14]
0x14014cd47  cmp     r9d, r15d
0x14014cd4a  ja      short loc_14014CD6D
0x14014cd4c  jz      short loc_14014CD6D
0x14014cd4e  test    r9d, r9d
0x14014cd51  jz      short loc_14014CD6D
0x14014cd53  sub     r9d, 1
0x14014cd57  jz      short loc_14014CD66
0x14014cd59  sub     r9d, 1
0x14014cd5d  jnz     short loc_14014CD6D
0x14014cd5f  cmp     qword ptr [rsp+338h+var_2D8+8], rcx
0x14014cd64  jmp     short loc_14014CD70
0x14014cd66  cmp     qword ptr [rsp+338h+var_2D8], rax
0x14014cd6b  jmp     short loc_14014CD70
0x14014cd6d  cmp     rbx, rdx
0x14014cd70  setz    al
0x14014cd73  test    al, al
0x14014cd75  jnz     loc_14014D76E
0x14014cd7b  lea     rcx, [rsp+338h+Src]; this
0x14014cd83  call    ??0ECSConfig@ECS@Experimentation@Applications@Microsoft@@QEAA@XZ; Microsoft::Applications::Experimentation::ECS::ECSConfig::ECSConfig(void)
0x14014cd88  nop
0x14014cd89  movzx   ecx, byte ptr [r14]
0x14014cd8d  cmp     ecx, r15d
0x14014cd90  ja      short loc_14014CDB8
0x14014cd92  jz      short loc_14014CDB8
0x14014cd94  test    ecx, ecx
0x14014cd96  jz      loc_14014D851
0x14014cd9c  sub     ecx, 1
0x14014cd9f  jz      short loc_14014CDAD
0x14014cda1  sub     ecx, 1
0x14014cda4  jnz     short loc_14014CDB8
0x14014cda6  mov     r14, qword ptr [rsp+338h+var_2D8+8]
0x14014cdab  jmp     short loc_14014CDC1
0x14014cdad  mov     r14, qword ptr [rsp+338h+var_2D8]
0x14014cdb2  add     r14, 40h ; '@'
0x14014cdb6  jmp     short loc_14014CDC1
0x14014cdb8  test    rbx, rbx
0x14014cdbb  jnz     loc_14014D8D9
0x14014cdc1  mov     rdx, r14
0x14014cdc4  lea     rcx, [rsp+338h+var_C8]
0x14014cdcc  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@QEAA@AEBV012@@Z; nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>(nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> const &)
0x14014cdd1  nop
0x14014cdd2  lea     r10, [rsp+338h+var_C8]
0x14014cdda  mov     [rsp+338h+var_308], r10
0x14014cddf  xorps   xmm0, xmm0
0x14014cde2  movdqu  [rsp+338h+var_300], xmm0
0x14014cde8  xorps   xmm1, xmm1
0x14014cdeb  movdqu  [rsp+338h+var_300+8], xmm1
0x14014cdf1  mov     rbx, r13
0x14014cdf4  mov     [rsp+338h+var_2F0], rbx
0x14014cdf9  movzx   ecx, byte ptr [r10]
0x14014cdfd  cmp     ecx, r15d
0x14014ce00  ja      short loc_14014CE14
0x14014ce02  jz      short loc_14014CE14
0x14014ce04  mov     edx, ecx
0x14014ce06  test    ecx, ecx
0x14014ce08  jz      short loc_14014CE14
0x14014ce0a  sub     edx, 1
0x14014ce0d  jz      short loc_14014CE3E
0x14014ce0f  sub     edx, 1
0x14014ce12  jz      short loc_14014CE2F
0x14014ce14  mov     rbx, r13
0x14014ce17  mov     [rsp+338h+var_2F0], rbx
0x14014ce1c  cmp     ecx, 4
0x14014ce1f  ja      short loc_14014CE4C
0x14014ce21  test    ecx, ecx
0x14014ce23  jz      short loc_14014CE4C
0x14014ce25  sub     ecx, 1
0x14014ce28  jz      short loc_14014CE3E
0x14014ce2a  sub     ecx, 1
0x14014ce2d  jnz     short loc_14014CE4C
0x14014ce2f  mov     rax, [r10+8]
0x14014ce33  mov     rcx, [rax+8]
0x14014ce37  mov     qword ptr [rsp+338h+var_300+8], rcx
0x14014ce3c  jmp     short loc_14014CE56
0x14014ce3e  mov     rax, [r10+8]
0x14014ce42  mov     rcx, [rax]
0x14014ce45  mov     qword ptr [rsp+338h+var_300], rcx
0x14014ce4a  jmp     short loc_14014CE56
0x14014ce4c  mov     ebx, 1
0x14014ce51  mov     [rsp+338h+var_2F0], rbx
0x14014ce56  cmp     [rsp+338h+var_C8], 1
0x14014ce5e  jnz     short loc_14014CEDE
0x14014ce60  mov     rax, [rsp+338h+var_C0]
0x14014ce68  mov     r12, [rax]
0x14014ce6b  mov     r13, [r12+8]
0x14014ce70  xor     eax, eax
0x14014ce72  mov     [rsp+338h+var_2AC], eax
0x14014ce79  mov     r14, r12
0x14014ce7c  jmp     short loc_14014CE9F
0x14014ce7e  lea     rcx, [r13+20h]
0x14014ce82  lea     rdx, aRequestname_0; "RequestName"
0x14014ce89  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD@Z; std::operator<<char>(std::string const &,char const * const)
0x14014ce8e  test    al, al
0x14014ce90  cmovz   r14, r13
0x14014ce94  lea     rcx, [r13+10h]
0x14014ce98  cmovz   rcx, r13
0x14014ce9c  mov     r13, [rcx]
0x14014ce9f  cmp     [r13+19h], dil
0x14014cea3  jz      short loc_14014CE7E
0x14014cea5  cmp     [r14+19h], dil
0x14014cea9  jnz     short loc_14014CEBF
0x14014ceab  lea     rdx, [r14+20h]; Buf1
0x14014ceaf  lea     rcx, aRequestname_0; "RequestName"
0x14014ceb6  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NQEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<char>(char const * const,std::string const &)
0x14014cebb  test    al, al
0x14014cebd  jz      short loc_14014CEC2
0x14014cebf  mov     r14, r12
0x14014cec2  mov     qword ptr [rsp+338h+var_300], r14
0x14014cec7  mov     r12, [rsp+338h+var_2C0]
0x14014cecc  lea     r10, [rsp+338h+var_C8]
0x14014ced4  mov     r13, 8000000000000000h
0x14014cede  lea     r8, [rsp+338h+var_C8]
0x14014cee6  xorps   xmm0, xmm0
0x14014cee9  movdqu  xmmword ptr [rsp+88h], xmm0
0x14014cef2  xorps   xmm1, xmm1
  ... truncated ...
```

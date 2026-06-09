# Microsoft::Applications::Experimentation::ECS::ECSConfigCache::_SaveConfig(Microsoft::Applications::Experimentation::ECS::ECSConfig const &)

- ea: `0x14014d964`
- end: `0x14014e03d`
- name: `?_SaveConfig@ECSConfigCache@ECS@Experimentation@Applications@Microsoft@@AEAA_NAEBUECSConfig@2345@@Z`
- size: `1753`
- prototype: `bool __fastcall(Microsoft::Applications::Experimentation::ECS::ECSConfigCache *__hidden this, const struct Microsoft::Applications::Experimentation::ECS::ECSConfig *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14014c708`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14001d848`
- `0x14003a0f4`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007fb9c`
- `0x140084a18`
- `0x140084b00`
- `0x140084b3c`
- `0x1400858b4`
- `0x140085a00`
- `0x1400bead4`
- `0x1400ddbfc`
- `0x1400de1f0`
- `0x1400ff188`
- `0x1401454bc`
- `0x140149e08`
- `0x14014b6bc`
- `0x14014c130`
- `0x14014d964`
- `0x140166250`
- `0x140166990`

## string_xrefs

- `0x14014d9bf`: `[ECSClient]: Saving configs to offline storage [%s]`
- `0x14014dfb9`: `[ECSClient]: Done saving %u configs to offline storage`
- `0x14014df59`: `[ECSClient]: Failed to save configs to offline storage, error=%d).`
- `0x14014df78`: `[ECSClient]: Failed to clean-up existing configs, abort saving configs.`
- `0x14014db8b`: `,"configSettings":`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char __fastcall Microsoft::Applications::Experimentation::ECS::ECSConfigCache::_SaveConfig(
        Microsoft::Applications::Experimentation::ECS::ECSConfigCache *this,
        const struct Microsoft::Applications::Experimentation::ECS::ECSConfig *a2)
{
  const char *v4; // r9
  size_t v5; // rcx
  __int64 i; // rdi
  __int64 v7; // r12
  char v8; // r15
  char v9; // bl
  volatile signed __int32 *v10; // rsi
  __int64 v11; // r8
  int v12; // r8d
  volatile signed __int32 *v13; // rbx
  size_t v14; // rcx
  void **v15; // rax
  void **Src; // rcx
  __int64 v17; // rax
  __int128 v18; // xmm7
  __int128 v19; // xmm6
  int v20; // edi
  void **v21; // rdx
  int v22; // eax
  __int128 v24; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-B0h]
  __int128 v26; // [rsp+68h] [rbp-A0h] BYREF
  void *v27[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v28; // [rsp+88h] [rbp-80h] BYREF
  __int64 v29; // [rsp+98h] [rbp-70h]
  __int64 v30; // [rsp+A0h] [rbp-68h]
  void *v31[2]; // [rsp+A8h] [rbp-60h] BYREF
  size_t v32[2]; // [rsp+B8h] [rbp-50h]
  volatile signed __int32 *v33; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-28h]
  _QWORD v36[32]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v37[82]; // [rsp+1E8h] [rbp+E0h] BYREF

  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    v4 = (const char *)this;
    if ( *((_QWORD *)this + 3) > 0xFu )
      v4 = *(const char **)this;
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.ECS",
      "[ECSClient]: Saving configs to offline storage [%s]",
      v4);
  }
  v34 = 0;
  v35 = 0;
  std::vector<Microsoft::Applications::Experimentation::ECS::ECSConfig>::_Emplace_reallocate<Microsoft::Applications::Experimentation::ECS::ECSConfig const &>(
    &v34,
    0,
    (__int64)a2);
  *(_OWORD *)v31 = 0;
  v5 = 0;
  v32[0] = 0;
  v32[1] = 15;
  LOBYTE(v31[0]) = 0;
  for ( i = v34 + 56; i - 56 != *((_QWORD *)&v34 + 1); i += 120 )
  {
    v28 = 0;
    v29 = 0;
    v30 = 15;
    LOBYTE(v28) = 0;
    std::string::append(&v28);
    std::string::append(&v28);
    std::string::append(&v28);
    if ( *(_QWORD *)(i - 8) )
    {
      if ( v29 )
        std::string::append(&v28);
      std::string::append(&v28);
      std::string::append(&v28);
      std::string::append(&v28);
    }
    std::string::append(&v28);
    std::to_string(&v24, *(_QWORD *)(i + 8));
    std::string::append(&v28);
    std::string::_Tidy_deallocate(&v24);
    std::string::append(&v28);
    std::string::append(&v28);
    std::string::append(&v28);
    std::string::append(&v28);
    std::string::append(&v28);
    memset(v36, 0, 0xF8u);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v36);
    v7 = *(_QWORD *)((char *)&v36[7] + *(int *)(v36[2] + 4LL));
    if ( v7 <= 0 )
    {
      v8 = 0;
      LODWORD(v7) = 0;
    }
    else
    {
      v8 = 1;
    }
    *(_QWORD *)((char *)&v36[7] + *(int *)(v36[2] + 4LL)) = 0;
    memset(v37, 0, 0x288u);
    v9 = *((_BYTE *)&v36[13] + *(int *)(v36[2] + 4LL));
    v10 = (volatile signed __int32 *)operator new(0x20u);
    v33 = v10;
    *(_OWORD *)v10 = 0;
    *((_DWORD *)v10 + 2) = 1;
    *((_DWORD *)v10 + 3) = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<nlohmann::json_abi_v3_11_3::detail::output_stream_adapter<char>>::`vftable';
    *((_QWORD *)v10 + 2) = &nlohmann::json_abi_v3_11_3::detail::output_stream_adapter<char>::`vftable';
    *((_QWORD *)v10 + 3) = &v36[2];
    v27[0] = (void *)(v10 + 4);
    v27[1] = (void *)v10;
    v26 = 0;
    _InterlockedIncrement(v10 + 2);
    *(_QWORD *)&v26 = v10 + 4;
    *((_QWORD *)&v26 + 1) = v10;
    LOBYTE(v11) = v9;
    nlohmann::json_abi_v3_11_3::detail::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>(
      v37,
      &v26,
      v11);
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    LOBYTE(v12) = v8;
    nlohmann::json_abi_v3_11_3::detail::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<unsigned char>,void>>::dump(
      (unsigned int)v37,
      i + 16,
      v12,
      0,
      v7,
      0);
    std::string::_Tidy_deallocate(&v37[76]);
    v13 = (volatile signed __int32 *)v37[1];
    if ( v37[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v37[1] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    std::stringbuf::str(&v36[3], &v24);
    std::string::append(&v28);
    std::string::_Tidy_deallocate(&v24);
    std::string::append(&v28);
    v14 = v32[0];
    if ( v32[0] )
    {
      if ( v32[0] >= v32[1] )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v31);
      }
      else
      {
        ++v32[0];
        v15 = v31;
        if ( v32[1] > 0xF )
          v15 = (void **)v31[0];
        *(_WORD *)((char *)v15 + v14) = 44;
      }
    }
    std::string::append(v31);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v36[19]);
    v36[19] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v36[19]);
    std::string::_Tidy_deallocate(&v28);
    v5 = v32[0];
  }
  if ( 0x7FFFFFFFFFFFFFFFLL == v5 )
    std::_Xlen_string();
  _mm_lfence();
  Src = v31;
  if ( v32[1] > 0xF )
    Src = (void **)v31[0];
  std::string::string(&v28, 1u, Src, v32[0]);
  v17 = std::string::append(&v28);
  v24 = *(_OWORD *)v17;
  v18 = v24;
  v25 = *(_OWORD *)(v17 + 16);
  v19 = v25;
  *(_QWORD *)(v17 + 16) = 0;
  *(_QWORD *)(v17 + 24) = 15;
  *(_BYTE *)v17 = 0;
  std::string::_Tidy_deallocate(v31);
  *(_OWORD *)v31 = v18;
  *(_OWORD *)v32 = v19;
  *(_QWORD *)&v25 = 0;
  *((_QWORD *)&v25 + 1) = 15;
  LOBYTE(v24) = 0;
  std::string::_Tidy_deallocate(&v24);
  std::string::_Tidy_deallocate(&v28);
  *(_QWORD *)&v26 = (char *)this + 56;
  if ( Mtx_lock((Microsoft::Applications::Experimentation::ECS::ECSConfigCache *)((char *)this + 56)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 33) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 33) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_QWORD *)this + 4) )
  {
    v27[0] = 0;
    v33 = 0;
    while ( 1 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, void **, volatile signed __int32 **, _QWORD))(**((_QWORD **)this + 4)
                                                                                           + 40LL))(
              *((_QWORD *)this + 4),
              v27,
              &v33,
              0);
      if ( v27[0] )
      {
        operator delete(v27[0], (const struct std::nothrow_t *)1);
        v27[0] = 0;
        v33 = 0;
      }
      if ( v20 < 0 )
        break;
      if ( !v20 )
      {
        v21 = v31;
        if ( v32[1] > 0xF )
          v21 = (void **)v31[0];
        v22 = (*(__int64 (__fastcall **)(_QWORD, void **, size_t, _QWORD))(**((_QWORD **)this + 4) + 32LL))(
                *((_QWORD *)this + 4),
                v21,
                v32[0] + 1,
                0);
        if ( v22 && Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
          Microsoft::Applications::Events::PlatformAbstraction::detail::log(
            1,
            "EventsSDK.ECS",
            "[ECSClient]: Failed to save configs to offline storage, error=%d).",
            v22);
        goto LABEL_46;
      }
    }
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "EventsSDK.ECS",
        "[ECSClient]: Failed to clean-up existing configs, abort saving configs.");
  }
LABEL_46:
  Mtx_unlock((Microsoft::Applications::Experimentation::ECS::ECSConfigCache *)((char *)this + 56));
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.ECS",
      "[ECSClient]: Done saving %u configs to offline storage",
      -286331153 * ((__int64)(*((_QWORD *)&v34 + 1) - v34) >> 3));
  std::string::_Tidy_deallocate(v31);
  std::vector<Microsoft::Applications::Experimentation::ECS::ECSConfig>::~vector<Microsoft::Applications::Experimentation::ECS::ECSConfig>(&v34);
  return 1;
}

```

## disassembly

```asm
0x14014d964  mov     rax, rsp
0x14014d967  mov     [rax+18h], rbx
0x14014d96b  push    rbp
0x14014d96c  push    rsi
0x14014d96d  push    rdi
0x14014d96e  push    r12
0x14014d970  push    r13
0x14014d972  push    r14
0x14014d974  push    r15
0x14014d976  lea     rbp, [rax-3D8h]
0x14014d97d  sub     rsp, 4A0h
0x14014d984  movaps  xmmword ptr [rax-48h], xmm6
0x14014d988  movaps  xmmword ptr [rax-58h], xmm7
0x14014d98c  mov     rax, cs:__security_cookie
0x14014d993  xor     rax, rsp
0x14014d996  mov     [rbp+3D0h+var_60], rax
0x14014d99d  mov     rbx, rdx
0x14014d9a0  mov     r14, rcx
0x14014d9a3  xor     r13d, r13d
0x14014d9a6  lea     r15d, [r13+0Fh]
0x14014d9aa  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14014d9b1  jl      short loc_14014D9D7
0x14014d9b3  mov     r9, rcx
0x14014d9b6  cmp     [rcx+18h], r15
0x14014d9ba  jbe     short loc_14014D9BF
0x14014d9bc  mov     r9, [rcx]
0x14014d9bf  lea     r8, aEcsclientSavin; "[ECSClient]: Saving configs to offline "...
0x14014d9c6  lea     rdx, ?digits_to_99@?1???$dump_integer@_K$0A@@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@AEAAX_K@Z@4V?$array@V?$array@D$01@std@@$0GE@@std@@B+0C8h; "EventsSDK.ECS"
0x14014d9cd  mov     ecx, 4
0x14014d9d2  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x14014d9d7  xorps   xmm1, xmm1
0x14014d9da  movdqu  [rbp+3D0h+var_408], xmm1
0x14014d9df  mov     [rbp+3D0h+var_3F8], r13
0x14014d9e3  mov     r8, rbx
0x14014d9e6  xor     edx, edx
0x14014d9e8  lea     rcx, [rbp+3D0h+var_408]
0x14014d9ec  call    ??$_Emplace_reallocate@AEBUECSConfig@ECS@Experimentation@Applications@Microsoft@@@?$vector@UECSConfig@ECS@Experimentation@Applications@Microsoft@@V?$allocator@UECSConfig@ECS@Experimentation@Applications@Microsoft@@@std@@@std@@AEAAPEAUECSConfig@ECS@Experimentation@Applications@Microsoft@@QEAU23456@AEBU23456@@Z; std::vector<Microsoft::Applications::Experimentation::ECS::ECSConfig>::_Emplace_reallocate<Microsoft::Applications::Experimentation::ECS::ECSConfig const &>(Microsoft::Applications::Experimentation::ECS::ECSConfig * const,Microsoft::Applications::Experimentation::ECS::ECSConfig const &)
0x14014d9f1  xorps   xmm0, xmm0
0x14014d9f4  movups  xmmword ptr [rbp+3D0h+var_430], xmm0
0x14014d9f8  mov     rcx, r13
0x14014d9fb  mov     [rbp+3D0h+var_420], rcx
0x14014d9ff  mov     [rbp+3D0h+var_420+8], r15
0x14014da03  mov     byte ptr [rbp+3D0h+var_430], r13b
0x14014da07  mov     rdi, qword ptr [rbp+3D0h+var_408]
0x14014da0b  add     rdi, 38h ; '8'
0x14014da0f  mov     esi, 1
0x14014da14  lea     rbx, [rdi-38h]
0x14014da18  cmp     rbx, qword ptr [rbp+3D0h+var_408+8]
0x14014da1c  jz      loc_14014DDFB
0x14014da22  xorps   xmm0, xmm0
0x14014da25  movups  [rbp+3D0h+var_450], xmm0
0x14014da29  mov     [rbp+3D0h+var_440], r13
0x14014da2d  mov     [rbp+3D0h+var_438], r15
0x14014da31  mov     byte ptr [rbp+3D0h+var_450], r13b
0x14014da35  mov     r8d, 10h
0x14014da3b  lea     rdx, aRequestname; "{\"RequestName\":\""
0x14014da42  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014da46  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014da4b  cmp     [rdi-20h], r15
0x14014da4f  jbe     short loc_14014DA54
0x14014da51  mov     rbx, [rbx]
0x14014da54  mov     r8, [rdi-28h]
0x14014da58  mov     rdx, rbx
0x14014da5b  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014da5f  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014da64  mov     r8, rsi
0x14014da67  lea     rdx, asc_140194AC4; "\""
0x14014da6e  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014da72  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014da77  cmp     [rdi-8], r13
0x14014da7b  jz      short loc_14014DAE6
0x14014da7d  cmp     [rbp+3D0h+var_440], r13
0x14014da81  jz      short loc_14014DA96
0x14014da83  mov     r8, rsi
0x14014da86  lea     rdx, asc_140194AD4; ","
0x14014da8d  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014da91  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014da96  mov     r8d, 9
0x14014da9c  lea     rdx, aEtag_1; "\"etag\":\"\\"
0x14014daa3  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014daa7  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014daac  mov     r8, [rdi-8]
0x14014dab0  lea     rax, [r8-1]
0x14014dab4  cmp     r8, rax
0x14014dab7  cmovnb  r8, rax
0x14014dabb  lea     rdx, [rdi-18h]
0x14014dabf  cmp     [rdi], r15
0x14014dac2  jbe     short loc_14014DAC7
0x14014dac4  mov     rdx, [rdx]
0x14014dac7  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014dacb  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014dad0  mov     r8d, 2
0x14014dad6  lea     rdx, asc_1401A46D8; "\\\""
0x14014dadd  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014dae1  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014dae6  mov     r8d, 17h
0x14014daec  lea     rdx, aExpiryutctimes; "\",\"expiryUtcTimestamp\":"
0x14014daf3  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014daf7  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014dafc  mov     rdx, [rdi+8]
0x14014db00  lea     rcx, [rsp+4D0h+var_498+8]
0x14014db05  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J@Z; std::to_string(__int64)
0x14014db0a  nop
0x14014db0b  mov     r8, [rax+10h]
0x14014db0f  cmp     [rax+18h], r15
0x14014db13  jbe     short loc_14014DB18
0x14014db15  mov     rax, [rax]
0x14014db18  mov     rdx, rax
0x14014db1b  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db1f  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db24  nop
0x14014db25  lea     rcx, [rsp+4D0h+var_498+8]
0x14014db2a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014db2f  mov     r8d, 11h
0x14014db35  lea     rdx, aClientversion_1; ",\"clientVersion\":"
0x14014db3c  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db40  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db45  mov     r8, rsi
0x14014db48  lea     rdx, asc_140194AC4; "\""
0x14014db4f  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db53  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db58  lea     rdx, [rdi+20h]
0x14014db5c  cmp     [rdi+38h], r15
0x14014db60  jbe     short loc_14014DB65
0x14014db62  mov     rdx, [rdx]
0x14014db65  mov     r8, [rdi+30h]
0x14014db69  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db6d  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db72  mov     r8, rsi
0x14014db75  lea     rdx, asc_140194AC4; "\""
0x14014db7c  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db80  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db85  mov     r8d, 12h
0x14014db8b  lea     rdx, aConfigsettings; ",\"configSettings\":"
0x14014db92  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014db96  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014db9b  xor     edx, edx; Val
0x14014db9d  mov     r8d, 0F8h; Size
0x14014dba3  lea     rcx, [rbp+3D0h+var_3F0]; void *
0x14014dba7  call    memset
0x14014dbac  lea     rcx, [rbp+3D0h+var_3F0]
0x14014dbb0  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14014dbb5  nop
0x14014dbb6  mov     rax, [rbp+3D0h+var_3E0]
0x14014dbba  movsxd  rcx, dword ptr [rax+4]
0x14014dbbe  mov     r12, [rbp+rcx+3D0h+var_3B8]
0x14014dbc3  test    r12, r12
0x14014dbc6  jle     short loc_14014DBCD
0x14014dbc8  mov     r15b, sil
0x14014dbcb  jmp     short loc_14014DBD3
0x14014dbcd  mov     r15b, r13b
0x14014dbd0  mov     r12, r13
0x14014dbd3  mov     [rbp+rcx+3D0h+var_3B8], r13
0x14014dbd8  xor     edx, edx; Val
0x14014dbda  mov     r8d, 288h; Size
0x14014dbe0  lea     rcx, [rbp+3D0h+var_2F0]; void *
0x14014dbe7  call    memset
0x14014dbec  mov     rax, [rbp+3D0h+var_3E0]
0x14014dbf0  movsxd  rcx, dword ptr [rax+4]
0x14014dbf4  mov     bl, [rbp+rcx+3D0h+var_388]
0x14014dbf8  mov     ecx, 20h ; ' '; Size
0x14014dbfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14014dc02  mov     rsi, rax
0x14014dc05  mov     [rbp+3D0h+var_410], rax
0x14014dc09  xorps   xmm0, xmm0
0x14014dc0c  movups  xmmword ptr [rax], xmm0
0x14014dc0f  mov     dword ptr [rax+8], 1
0x14014dc16  mov     dword ptr [rax+0Ch], 1
0x14014dc1d  lea     rax, ??_7?$_Ref_count_obj2@V?$output_stream_adapter@D@detail@json_abi_v3_11_3@nlohmann@@@std@@6B@; const std::_Ref_count_obj2<nlohmann::json_abi_v3_11_3::detail::output_stream_adapter<char>>::`vftable'
0x14014dc24  mov     [rsi], rax
0x14014dc27  lea     rax, [rsi+10h]
0x14014dc2b  lea     rcx, ??_7?$output_stream_adapter@D@detail@json_abi_v3_11_3@nlohmann@@6B@; const nlohmann::json_abi_v3_11_3::detail::output_stream_adapter<char>::`vftable'
0x14014dc32  mov     [rax], rcx
0x14014dc35  lea     rcx, [rbp+3D0h+var_3E0]
0x14014dc39  mov     [rax+8], rcx
0x14014dc3d  mov     [rsp+4D0h+var_460], rax
0x14014dc42  mov     [rsp+4D0h+var_458], rsi
0x14014dc47  movdqu  [rsp+4D0h+var_478+8], xmm0
0x14014dc4d  lock inc dword ptr [rsi+8]
0x14014dc51  mov     qword ptr [rsp+4D0h+var_478+8], rax
0x14014dc56  mov     [rsp+4D0h+var_468], rsi
0x14014dc5b  mov     r8b, bl
0x14014dc5e  lea     rdx, [rsp+4D0h+var_478+8]
0x14014dc63  lea     rcx, [rbp+3D0h+var_2F0]
0x14014dc6a  call    ??0?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEAA@V?$shared_ptr@U?$output_adapter_protocol@D@detail@json_abi_v3_11_3@nlohmann@@@std@@DW4error_handler_t@123@@Z; nlohmann::json_abi_v3_11_3::detail::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>(std::shared_ptr<nlohmann::json_abi_v3_11_3::detail::output_adapter_protocol<char>>,char,nlohmann::json_abi_v3_11_3::detail::error_handler_t)
0x14014dc6f  nop
0x14014dc70  or      ebx, 0FFFFFFFFh
0x14014dc73  mov     eax, ebx
0x14014dc75  lock xadd [rsi+8], eax
0x14014dc7a  add     eax, ebx
0x14014dc7c  jnz     short loc_14014DCA8
0x14014dc7e  mov     rax, [rsi]
0x14014dc81  mov     rcx, rsi
0x14014dc84  mov     rax, [rax]
0x14014dc87  call    cs:__guard_dispatch_icall_fptr
0x14014dc8d  mov     eax, ebx
0x14014dc8f  lock xadd [rsi+0Ch], eax
0x14014dc94  add     eax, ebx
0x14014dc96  jnz     short loc_14014DCA8
0x14014dc98  mov     rax, [rsi]
0x14014dc9b  mov     rcx, rsi
0x14014dc9e  mov     rax, [rax+8]
0x14014dca2  call    cs:__guard_dispatch_icall_fptr
0x14014dca8  lea     rdx, [rdi+10h]
0x14014dcac  mov     dword ptr [rsp+4D0h+Src], r13d
0x14014dcb1  mov     dword ptr [rsp+4D0h+Size], r12d
0x14014dcb6  xor     r9d, r9d
0x14014dcb9  mov     r8b, r15b
0x14014dcbc  lea     rcx, [rbp+3D0h+var_2F0]
0x14014dcc3  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@34@_N1II@Z; nlohmann::json_abi_v3_11_3::detail::serializer<nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void>>::dump(nlohmann::json_abi_v3_11_3::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_3::adl_serializer,std::vector<uchar>,void> const &,bool,bool,uint,uint)
0x14014dcc8  nop
0x14014dcc9  lea     rcx, [rbp+3D0h+var_90]
0x14014dcd0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014dcd5  mov     rbx, [rbp+3D0h+var_2E8]
0x14014dcdc  test    rbx, rbx
0x14014dcdf  jz      short loc_14014DD1E
0x14014dce1  or      r12d, 0FFFFFFFFh
0x14014dce5  mov     eax, r12d
0x14014dce8  lock xadd [rbx+8], eax
0x14014dced  add     eax, r12d
0x14014dcf0  jnz     short loc_14014DD1E
0x14014dcf2  mov     rax, [rbx]
0x14014dcf5  mov     rcx, rbx
0x14014dcf8  mov     rax, [rax]
0x14014dcfb  call    cs:__guard_dispatch_icall_fptr
0x14014dd01  mov     eax, r12d
0x14014dd04  lock xadd [rbx+0Ch], eax
0x14014dd09  add     eax, r12d
0x14014dd0c  jnz     short loc_14014DD1E
0x14014dd0e  mov     rax, [rbx]
0x14014dd11  mov     rcx, rbx
0x14014dd14  mov     rax, [rax+8]
0x14014dd18  call    cs:__guard_dispatch_icall_fptr
0x14014dd1e  lea     rdx, [rsp+4D0h+var_498+8]
0x14014dd23  lea     rcx, [rbp+3D0h+var_3D8]
0x14014dd27  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x14014dd2c  nop
0x14014dd2d  lea     rdx, [rsp+4D0h+var_498+8]
0x14014dd32  mov     r15d, 0Fh
0x14014dd38  cmp     qword ptr [rsp+4D0h+var_478], r15
0x14014dd3d  cmova   rdx, qword ptr [rsp+4D0h+var_498+8]
0x14014dd43  mov     r8, qword ptr [rsp+4D0h+var_488+8]
0x14014dd48  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014dd4c  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014dd51  nop
0x14014dd52  lea     rcx, [rsp+4D0h+var_498+8]
0x14014dd57  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014dd5c  lea     esi, [r15-0Eh]
0x14014dd60  mov     r8d, esi
0x14014dd63  lea     rdx, asc_140194AD0; "}"
0x14014dd6a  lea     rcx, [rbp+3D0h+var_450]; Src
0x14014dd6e  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014dd73  mov     rcx, [rbp+3D0h+var_420]
0x14014dd77  test    rcx, rcx
0x14014dd7a  jz      short loc_14014DDAB
0x14014dd7c  cmp     rcx, [rbp+3D0h+var_420+8]
0x14014dd80  jnb     short loc_14014DD9F
0x14014dd82  lea     rax, [rcx+1]
0x14014dd86  mov     [rbp+3D0h+var_420], rax
0x14014dd8a  lea     rax, [rbp+3D0h+var_430]
0x14014dd8e  cmp     [rbp+3D0h+var_420+8], r15
0x14014dd92  cmova   rax, [rbp+3D0h+var_430]
0x14014dd97  mov     word ptr [rax+rcx], 2Ch ; ','
0x14014dd9d  jmp     short loc_14014DDAB
0x14014dd9f  mov     r9b, 2Ch ; ','
0x14014dda2  lea     rcx, [rbp+3D0h+var_430]; Src
0x14014dda6  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x14014ddab  lea     rdx, [rbp+3D0h+var_450]
0x14014ddaf  cmp     [rbp+3D0h+var_438], r15
0x14014ddb3  cmova   rdx, qword ptr [rbp+3D0h+var_450]
0x14014ddb8  mov     r8, [rbp+3D0h+var_440]
0x14014ddbc  lea     rcx, [rbp+3D0h+var_430]; Src
0x14014ddc0  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x14014ddc5  nop
0x14014ddc6  lea     rcx, [rbp+3D0h+var_358]
0x14014ddca  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x14014ddcf  nop
0x14014ddd0  lea     rax, ??_7ios_base@std@@6B@; const std::ios_base::`vftable'
0x14014ddd7  mov     [rbp+3D0h+var_358], rax
0x14014dddb  lea     rcx, [rbp+3D0h+var_358]; this
0x14014dddf  call    ?_Ios_base_dtor@ios_base@std@@CAXPEAV12@@Z; std::ios_base::_Ios_base_dtor(std::ios_base *)
0x14014dde4  nop
0x14014dde5  lea     rcx, [rbp+3D0h+var_450]
0x14014dde9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014ddee  add     rdi, 78h ; 'x'
0x14014ddf2  mov     rcx, [rbp+3D0h+var_420]
0x14014ddf6  jmp     loc_14014DA14
0x14014ddfb  mov     rax, 7FFFFFFFFFFFFFFFh
0x14014de05  sub     rax, rcx
0x14014de08  cmp     rax, rsi
0x14014de0b  jb      loc_14014E02C
0x14014de11  lfence
0x14014de14  lea     rcx, [rbp+3D0h+var_430]
0x14014de18  cmp     [rbp+3D0h+var_420+8], r15
0x14014de1c  cmova   rcx, [rbp+3D0h+var_430]
0x14014de21  mov     rax, [rbp+3D0h+var_420]
0x14014de25  mov     [rsp+4D0h+var_4A0], rax; size_t
0x14014de2a  mov     [rsp+4D0h+Src], rcx; Src
0x14014de2f  mov     [rsp+4D0h+Size], rsi; Size
0x14014de34  lea     r9, asc_140194ACC; "["
  ... truncated ...
```

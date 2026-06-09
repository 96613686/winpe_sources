# Spectre::Utils::JsonConfigurationManager::LoadConfiguration(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Spectre::Utils::IConfigurationManager::LoadPolicy)

- ea: `0x1804b7680`
- end: `0x1804b8cdd`
- name: `?LoadConfiguration@JsonConfigurationManager@Utils@Spectre@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4LoadPolicy@IConfigurationManager@23@@Z`
- size: `5725`
- prototype: ``
- caller_count: `0`
- callee_count: `51`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180014a60`
- `0x180014b00`
- `0x1800166bc`
- `0x180017040`
- `0x1800170e0`
- `0x180017670`
- `0x180021570`
- `0x180029b60`
- `0x180029bd0`
- `0x180029f10`
- `0x18002b780`
- `0x18002e6b0`
- `0x1800385d0`
- `0x18003d030`
- `0x18003eb90`
- `0x180185a00`
- `0x1801872c0`
- `0x1801b51d0`
- `0x1801cd2a0`
- `0x1801cd320`
- `0x1801f0af0`
- `0x180215c70`
- `0x180216570`
- `0x18024a670`
- `0x18024b580`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x18039f900`
- `0x18039f920`
- `0x18039fab0`
- `0x18039fad0`
- `0x1803a1060`
- `0x1804b19a0`
- `0x1804b1ab0`
- `0x1804b2890`
- `0x1804b3430`
- `0x1804b5bf0`
- `0x1804b6f20`
- `0x1804b75a0`
- `0x1804b7680`
- `0x1804b9920`
- `0x1804b9e70`
- `0x1804bc540`
- `0x1804bc620`
- `0x1804bc780`
- `0x1804bc910`
- `0x1804bc930`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7b94`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7bfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7f66`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b82f4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b8451`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b84dd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b853f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b859f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b86d1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7b94`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7bfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b7f66`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b82f4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b8451`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b84dd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b853f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b859f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804b86d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b8b8a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b8bd0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b8b8a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804b8bd0`

## string_xrefs

- `0x1804b8c5d`: `Error parsing configuration: Parse error code `
- `0x1804b839a`: `> has no value. Property has been replaced with loaded value.\n`
- `0x1804b83bd`: `> has no value. Property has been replaced with loaded value.\n`
- `0x1804b831b`: `WARNING: Object stored in ConfigurationManager with key<`
- `0x1804b85d4`: `WARNING: Object stored in ConfigurationManager with key<`
- `0x1804b861d`: `> was not replaced by loaded configuration due to an error.\n`
- `0x1804b863b`: `> was not replaced by loaded configuration due to an error.\n`
- `0x1804b8949`: `WARNING: Unknown property stored in serialized configuration with name <`
- `0x1804b89ce`: `> is already in configuration and load policy is 'Add', so the new value was not loaded\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void __fastcall Spectre::Utils::JsonConfigurationManager::LoadConfiguration(__int64 a1, _QWORD *a2, int a3)
{
  _OWORD *v5; // rax
  _QWORD *v6; // rax
  struct _Mtx_internal_imp_t *v7; // r14
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rsi
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r13
  unsigned __int64 v15; // r9
  __int64 v16; // r15
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int16 v19; // r12
  __int64 v20; // r8
  __int16 v21; // dx
  int v22; // ecx
  __int128 *v23; // rcx
  __int128 *v24; // rdx
  __int128 *v25; // rax
  __int64 v26; // rbx
  __int64 v27; // r15
  _QWORD *v28; // rdi
  __int64 inserted; // rbx
  __int64 v30; // r12
  _QWORD *v31; // rbx
  __int64 v32; // rdi
  void *v33; // rcx
  void *v34; // rcx
  bool HasKey; // al
  int v36; // r15d
  __int64 v37; // r8
  const struct Spectre::Utils::ConfigurationValue *Content; // r12
  __int64 v39; // rax
  unsigned int *v40; // r15
  char IsSameValueType; // al
  __int16 v42; // dx
  __int64 v43; // r8
  char v44; // bl
  __int64 v45; // r8
  void **v46; // rcx
  __int64 v47; // rax
  unsigned int *v48; // rbx
  __int64 v49; // rax
  __int64 v50; // r8
  void *v51; // rcx
  void **v52; // rdx
  __int64 v53; // rbx
  void **v54; // rdi
  __int64 v55; // r15
  __int64 v56; // rdx
  const struct Spectre::Utils::ConfigurationValue *v57; // rax
  __int64 v58; // rax
  __int64 v59; // rbx
  void **v60; // rdi
  __int64 v61; // r15
  __int64 v62; // rdx
  __int64 v63; // r8
  size_t v64; // r15
  void **v65; // r13
  size_t v66; // r12
  unsigned __int64 v67; // rdi
  _QWORD *v68; // rbx
  size_t v69; // rcx
  void *v70; // rax
  int v71; // edi
  __int64 v72; // rcx
  void **v73; // rbx
  _BYTE *v74; // rbx
  void **v75; // rax
  void *v76; // rcx
  void **v77; // r9
  void *v78; // rcx
  void *v79; // rcx
  _QWORD *v80; // rdi
  __int64 v81; // rcx
  unsigned __int64 v82; // rdx
  _QWORD *v83; // rax
  char *v84; // rbx
  void *v85; // rcx
  void **v86; // r9
  unsigned __int64 v87; // r8
  void *v88; // rdx
  void **v89; // rcx
  __int64 v90; // r8
  __int64 v91; // r8
  __int64 v92; // r8
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  void **v97; // r9
  _QWORD *v98; // rdi
  _QWORD *v99; // rbx
  __int64 v100; // rsi
  void *v101; // rdi
  _QWORD *v102; // rcx
  _QWORD *v103; // rbx
  _QWORD *v104; // rax
  struct OSpectre::IConfigManager *ConfigManager; // rdx
  __int64 v106; // rdi
  __int64 v107; // r8
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  unsigned int *v111; // [rsp+38h] [rbp-2D0h] BYREF
  int v112; // [rsp+40h] [rbp-2C8h]
  void *v113[2]; // [rsp+48h] [rbp-2C0h] BYREF
  __int64 v114; // [rsp+58h] [rbp-2B0h]
  unsigned __int64 v115; // [rsp+60h] [rbp-2A8h]
  int v116; // [rsp+68h] [rbp-2A0h]
  __int64 v117; // [rsp+70h] [rbp-298h]
  __int64 i; // [rsp+78h] [rbp-290h]
  __int64 v119; // [rsp+80h] [rbp-288h]
  char v120[16]; // [rsp+88h] [rbp-280h] BYREF
  char v121[16]; // [rsp+98h] [rbp-270h] BYREF
  _BYTE v122[136]; // [rsp+A8h] [rbp-260h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+130h] [rbp-1D8h] BYREF
  __int64 v124; // [rsp+170h] [rbp-198h] BYREF
  void *v125[2]; // [rsp+178h] [rbp-190h] BYREF
  __int128 v126; // [rsp+188h] [rbp-180h]
  void *Src[2]; // [rsp+198h] [rbp-170h] BYREF
  __int128 v128; // [rsp+1A8h] [rbp-160h]
  __int128 v129; // [rsp+1C0h] [rbp-148h] BYREF
  void *Block[2]; // [rsp+1D0h] [rbp-138h] BYREF
  size_t Size; // [rsp+1E0h] [rbp-128h]
  unsigned __int64 v132; // [rsp+1E8h] [rbp-120h]
  void *v133[2]; // [rsp+1F0h] [rbp-118h] BYREF
  __int64 v134; // [rsp+200h] [rbp-108h]
  unsigned __int64 v135; // [rsp+208h] [rbp-100h]
  _QWORD *v136; // [rsp+210h] [rbp-F8h] BYREF
  _QWORD *v137; // [rsp+218h] [rbp-F0h]
  _DWORD v138[2]; // [rsp+220h] [rbp-E8h] BYREF
  _QWORD v139[2]; // [rsp+228h] [rbp-E0h] BYREF
  __int64 v140; // [rsp+238h] [rbp-D0h] BYREF
  __int128 v141; // [rsp+240h] [rbp-C8h]
  __int64 v142; // [rsp+250h] [rbp-B8h]
  __int64 v143; // [rsp+258h] [rbp-B0h]
  __int128 v144; // [rsp+260h] [rbp-A8h] BYREF
  void *v145[2]; // [rsp+270h] [rbp-98h]
  void *v146[2]; // [rsp+280h] [rbp-88h]
  __int128 v147; // [rsp+290h] [rbp-78h]
  __m128i si128; // [rsp+2A0h] [rbp-68h]
  int v149; // [rsp+2B0h] [rbp-58h]
  int v150; // [rsp+2B4h] [rbp-54h]
  __int64 v151; // [rsp+2B8h] [rbp-50h]

  try
  {
    v116 = a3;
    v117 = a1;
    v112 = 0;
    v150 = 0;
    v144 = 0;
    HIWORD(v144) = 0;
    *(_OWORD *)v145 = 0;
    *(_OWORD *)v146 = 0;
    v147 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v149 = 0;
    v151 = 0;
    v5 = operator new(0x28u);
    i = (__int64)v5;
    if ( v5 )
    {
      *v5 = 0;
      v5[1] = 0;
      *(_QWORD *)v5 = 0;
      *((_QWORD *)v5 + 1) = 0x10000;
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
    }
    else
    {
      v5 = 0;
    }
    v145[0] = v5;
    v145[1] = v5;
    v138[1] = 0;
    v139[1] = 0;
    v6 = operator new(0x30u);
    *v6 = v6;
    v6[1] = v6;
    v139[0] = v6;
    v140 = 0;
    v141 = 0;
    v142 = 7;
    v143 = 8;
    *(float *)v138 = FLOAT_1_0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(
      &v140,
      16,
      v6);
    if ( a2[3] >= 8u )
      a2 = (_QWORD *)*a2;
    v136 = a2;
    v137 = a2;
    Spectre::rapidjson::GenericDocument<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>,Spectre::rapidjson::CrtAllocator>::ParseStream<0,Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::GenericStringStream<Spectre::rapidjson::UTF16<wchar_t>>>(
      &v144,
      &v136);
    if ( v149 )
    {
      Spectre::rapidjson::GenericDocument<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>,Spectre::rapidjson::CrtAllocator>::GetParseError(&v144);
      ConfigManager = OSpectre::Babylon::Factory::GetConfigManager((OSpectre::Babylon::Factory *)&v144);
      v106 = std::to_string(v133, ConfigManager);
      v107 = std::to_string(Block);
      v108 = std::operator+<char>(v125, "Error parsing configuration: Parse error code ", v107);
      v109 = std::operator+<char>(Src, v108, " at input offset ");
      v110 = std::operator+<char>(v113, v109, v106);
      Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v110, 0);
      throw (Spectre::Utils::SpectreException *)pExceptionObject;
    }
    v7 = (struct _Mtx_internal_imp_t *)(a1 + 64);
    v119 = a1 + 64;
    v8 = Mtx_lock_0((_Mtx_t)(a1 + 64));
    if ( v8 )
    {
      std::_Throw_C_error(v8);
      goto LABEL_220;
    }
    v9 = *((_QWORD *)&v144 + 1);
    v10 = *((_QWORD *)&v144 + 1) & 0xFFFFFFFFFFFFLL;
    v11 = v144;
    v12 = (*((_QWORD *)&v144 + 1) & 0xFFFFFFFFFFFFLL) + 32LL * (unsigned int)v144;
    for ( i = v12; ; v12 = i )
    {
      v13 = -1;
      if ( v10 == v12 )
        break;
      if ( (*(_WORD *)(v10 + 14) & 0x1000) != 0 )
        v14 = v10;
      else
        v14 = *(_QWORD *)(v10 + 8) & 0xFFFFFFFFFFFFLL;
      v124 = v14;
      v129 = 0;
      HIWORD(v129) = 1029;
      v15 = v14 | *((_QWORD *)&v129 + 1) & 0xFFFF000000000000uLL;
      v111 = (unsigned int *)v15;
      *((_QWORD *)&v129 + 1) = v15;
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(v14 + 2 * v16) );
      LODWORD(v129) = v16;
      v17 = v9 & 0xFFFFFFFFFFFFLL;
      v18 = v17 + 32LL * v11;
      if ( v17 == v18 )
      {
LABEL_37:
        `Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>::operator[]<Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>'::`6'::buffer = 0;
        v25 = &`Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>::operator[]<Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>'::`6'::buffer;
        goto LABEL_38;
      }
      v19 = HIWORD(v15) & 0x1000;
      do
      {
        if ( v19 )
          v20 = 6 - (unsigned int)WORD6(v129);
        else
          v20 = (unsigned int)v16;
        v21 = *(_WORD *)(v17 + 14) & 0x1000;
        if ( v21 )
          v22 = 6 - *(unsigned __int16 *)(v17 + 12);
        else
          v22 = *(_DWORD *)v17;
        if ( (_DWORD)v20 != v22 )
          goto LABEL_34;
        v23 = v19 ? &v129 : (__int128 *)(v15 & 0xFFFFFFFFFFFFLL);
        v24 = (__int128 *)(v21 ? v17 : *(_QWORD *)(v17 + 8) & 0xFFFFFFFFFFFFLL);
        if ( v23 == v24 || !memcmp_0(v23, v24, 2 * v20) )
          break;
        v15 = (unsigned __int64)v111;
LABEL_34:
        v17 += 32;
      }
      while ( v17 != v18 );
      v13 = -1;
      if ( v17 == v18 )
        goto LABEL_37;
      v25 = (__int128 *)(v17 + 16);
LABEL_38:
      v111 = (unsigned int *)v25;
      v125[0] = 0;
      *(_QWORD *)&v126 = 0;
      *((_QWORD *)&v126 + 1) = 7;
      do
        ++v13;
      while ( *(_WORD *)(v14 + 2 * v13) );
      std::wstring::assign(v125);
      v26 = v117;
      v27 = (*(__int64 (__fastcall **)(__int64, void **, void **))(*(_QWORD *)v117 + 56LL))(v117, Block, v125);
      v28 = (_QWORD *)(v26 + 144);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<NMR::CModelMetaData>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<NMR::CModelMetaData>>>,0>>::_Find_lower_bound<std::wstring>(
        v26 + 144,
        v113,
        v27);
      inserted = v114;
      if ( *(_BYTE *)(v114 + 25) || (unsigned __int8)std::less<std::wstring>::operator()(v28, v27, v114 + 32) )
      {
        if ( v28[1] != 0x155555555555555LL )
        {
          v30 = *v28;
          v136 = v28;
          v137 = 0;
          v31 = operator new(0xC0u);
          v137 = v31;
          *(_QWORD *)&v129 = v31 + 4;
          v31[4] = 0;
          v31[6] = 0;
          v31[7] = 0;
          *((_OWORD *)v31 + 2) = *(_OWORD *)v27;
          *((_OWORD *)v31 + 3) = *(_OWORD *)(v27 + 16);
          *(_QWORD *)(v27 + 16) = 0;
          *(_QWORD *)(v27 + 24) = 7;
          *(_WORD *)v27 = 0;
          Spectre::Utils::ConfigurationValue::ConfigurationValue((Spectre::Utils::ConfigurationValue *)(v31 + 8));
          *v31 = v30;
          v31[1] = v30;
          v31[2] = v30;
          *((_WORD *)v31 + 12) = 0;
          v137 = 0;
          v129 = *(_OWORD *)v113;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(
                       v28,
                       &v129,
                       v31);
          goto LABEL_44;
        }
LABEL_220:
        std::_Throw_tree_length_error();
      }
LABEL_44:
      v32 = inserted + 64;
      if ( v132 >= 8 )
      {
        v33 = Block[0];
        if ( 2 * v132 + 2 >= 0x1000 )
        {
          v33 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v33 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v33);
      }
      Size = 0;
      v132 = 7;
      LOWORD(Block[0]) = 0;
      if ( *((_QWORD *)&v126 + 1) >= 8u )
      {
        v34 = v125[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v126 + 1) + 2) >= 0x1000 )
        {
          v34 = (void *)*((_QWORD *)v125[0] - 1);
          if ( (unsigned __int64)((char *)v125[0] - (char *)v34 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v34);
      }
      *(_QWORD *)&v126 = 0;
      *((_QWORD *)&v126 + 1) = 7;
      LOWORD(v125[0]) = 0;
      HasKey = Spectre::Utils::ConfigurationValue::HasKey(
                 (Spectre::Utils::ConfigurationValue *)(inserted + 64),
                 (const wchar_t *)v14);
      v36 = v116;
      if ( HasKey && v116 != 2 )
      {
        v113[0] = 0;
        v114 = 0;
        v115 = 7;
        v37 = -1;
        do
          ++v37;
        while ( *(_WORD *)(v14 + 2 * v37) );
        std::wstring::assign(v113);
        Content = (const struct Spectre::Utils::ConfigurationValue *)Spectre::Utils::ConfigurationValue::GetContent(
                                                                       v32,
                                                                       v113);
        v39 = Spectre::Utils::ConfigurationValue::ConfigurationValue(
                (Spectre::Utils::ConfigurationValue *)v122,
                Content);
        v40 = v111;
        IsSameValueType = Spectre::Utils::IsSameValueType(v111, v39);
        v42 = *((_WORD *)v40 + 7);
        if ( IsSameValueType )
        {
          if ( (v42 & 0x20) != 0 && Spectre::Utils::ConfigurationValue::IsDouble(Content) )
          {
            Src[0] = 0;
            *(_QWORD *)&v128 = 0;
            *((_QWORD *)&v128 + 1) = 7;
            v43 = -1;
            do
              ++v43;
            while ( *(_WORD *)(v14 + 2 * v43) );
            std::wstring::assign(Src);
            Spectre::Utils::ConfigurationValue::SetValue<double>(v32, Src);
            v44 = 0;
          }
          else
          {
            Src[0] = 0;
            *(_QWORD *)&v128 = 0;
            *((_QWORD *)&v128 + 1) = 7;
            v45 = -1;
            do
              ++v45;
            while ( *(_WORD *)(v14 + 2 * v45) );
            std::wstring::assign(Src);
            Spectre::Utils::SetObjectValue(v40, v32, Src);
            v44 = 0;
          }
          goto LABEL_161;
        }
        if ( v42 != 3 && !Spectre::Utils::ConfigurationValue::IsObject(Content) )
        {
          v44 = 1;
          goto LABEL_161;
        }
        if ( *((_WORD *)v40 + 7) == 3 )
        {
          Src[0] = 0;
          *(_QWORD *)&v128 = 0;
          *((_QWORD *)&v128 + 1) = 7;
          std::wstring::assign(Src);
          v111 = 0;
          v46 = Src;
          if ( *((_QWORD *)&v128 + 1) >= 8u )
            v46 = (void **)Src[0];
          v129 = 0;
          HIWORD(v129) = 1029;
          *((_QWORD *)&v129 + 1) = (unsigned __int64)v46 | *((_QWORD *)&v129 + 1) & 0xFFFF000000000000uLL;
          v47 = -1;
          do
            ++v47;
          while ( *((_WORD *)v46 + v47) );
          LODWORD(v129) = v47;
          Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>::FindMember<Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>(
            v40,
            &v111,
            &v129);
          v48 = v111;
          if ( v111 == (unsigned int *)(32LL * *v40 + (*((_QWORD *)v40 + 1) & 0xFFFFFFFFFFFFLL))
            || (v49 = Spectre::Utils::ConfigurationValue::ConfigurationValue(
                        (Spectre::Utils::ConfigurationValue *)v122,
                        Content),
                !(unsigned __int8)Spectre::Utils::IsSameValueType(v48 + 4, v49)) )
          {
            v44 = 1;
          }
          else
          {
            v113[0] = 0;
            v114 = 0;
            v115 = 7;
            v50 = -1;
            do
              ++v50;
            while ( *(_WORD *)(v14 + 2 * v50) );
            std::wstring::assign(v113);
            Spectre::Utils::SetObjectValue(v40, v32, v113);
            v44 = 0;
          }
          if ( *((_QWORD *)&v128 + 1) >= 8u )
          {
            v51 = Src[0];
            if ( (unsigned __int64)(2LL * *((_QWORD *)&v128 + 1) + 2) >= 0x1000 )
            {
              v51 = (void *)*((_QWORD *)Src[0] - 1);
              if ( (unsigned __int64)((char *)Src[0] - (char *)v51 - 8) > 0x1F )
                _invalid_parameter_noinfo_noreturn();
            }
            goto LABEL_85;
          }
LABEL_161:
          if ( v44 )
          {
            Spectre::Utils::LexicalCast<std::string,wchar_t const *>(Block, &v124);
            v80 = (_QWORD *)std::operator+<char>(v133);
            v81 = v80[2];
            v82 = v80[3];
            if ( v82 - v81 < 0x3C )
            {
              v80 = (_QWORD *)std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(
                                v80,
                                0x3Cu);
            }
            else
            {
              v80[2] = v81 + 60;
              v83 = v80;
              if ( v82 >= 0x10 )
                v83 = (_QWORD *)*v80;
              v84 = (char *)v83 + v81;
              memmove_0((char *)v83 + v81, "> was not replaced by loaded configuration due to an error.\n", 0x3Cu);
              v84[60] = 0;
            }
            Src[0] = 0;
            v128 = 0u;
            *(_OWORD *)Src = *(_OWORD *)v80;
            v128 = *((_OWORD *)v80 + 1);
            v80[2] = 0;
            v80[3] = 15;
            *(_BYTE *)v80 = 0;
            v112 |= 4u;
            if ( v135 >= 0x10 )
            {
              v85 = v133[0];
              if ( v135 + 1 >= 0x1000 )
              {
                v85 = (void *)*((_QWORD *)v133[0] - 1);
                if ( (unsigned __int64)((char *)v133[0] - (char *)v85 - 8) > 0x1F )
                  _invalid_parameter_noinfo_noreturn();
              }
              operator delete(v85);
            }
            v134 = 0;
            v135 = 15;
            LOBYTE(v133[0]) = 0;
            v86 = Src;
            if ( *((_QWORD *)&v128 + 1) >= 0x10u )
              v86 = (void **)Src[0];
            Trace::LevelSettingsWrapper::Output(&gTraceLevelsConfigurationManager, 3, "%s", (const char *)v86);
            if ( *((_QWORD *)&v128 + 1) >= 0x10u )
              std::allocator<unsigned char>::deallocate(Src, Src[0], *((_QWORD *)&v128 + 1) + 1LL);
            *(_QWORD *)&v128 = 0;
            *((_QWORD *)&v128 + 1) = 15;
            LOBYTE(Src[0]) = 0;
            v87 = v132;
            if ( v132 >= 0x10 )
            {
              v88 = Block[0];
              v89 = Block;
              goto LABEL_204;
            }
            goto LABEL_205;
          }
          v125[0] = 0;
          *(_QWORD *)&v126 = 0;
          *((_QWORD *)&v126 + 1) = 7;
          v90 = -1;
          do
            ++v90;
          while ( *(_WORD *)(v14 + 2 * v90) );
          std::wstring::assign(v125);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
            v138,
            v120,
            v125);
LABEL_187:
          if ( *((_QWORD *)&v126 + 1) >= 8u )
            std::allocator<wchar_t>::deallocate(v125, v125[0], *((_QWORD *)&v126 + 1) + 1LL);
          goto LABEL_205;
        }
        if ( !Spectre::Utils::ConfigurationValue::IsObject(Content) )
        {
          v44 = 0;
          goto LABEL_161;
        }
        Src[0] = 0;
        *(_QWORD *)&v128 = 0;
        *((_QWORD *)&v128 + 1) = 7;
        std::wstring::assign(Src);
        v52 = Src;
        if ( *((_QWORD *)&v128 + 1) >= 8u )
          v52 = (void **)Src[0];
        if ( Spectre::Utils::ConfigurationValue::HasKey(Content, (const wchar_t *)v52) )
        {
          v125[0] = 0;
          v126 = 0u;
          v53 = v128;
          v54 = Src;
          if ( *((_QWORD *)&v128 + 1) >= 8u )
            v54 = (void **)Src[0];
          if ( (unsigned __int64)v128 >= 8 )
          {
            v55 = v128 | 7;
            if ( ((unsigned __int64)v128 | 7) > 0x7FFFFFFFFFFFFFFELL )
              v55 = 0x7FFFFFFFFFFFFFFELL;
            v56 = v55 + 1;
            if ( v55 == -1 )
              v56 = -1;
            v125[0] = (void *)std::allocator<wchar_t>::allocate(v125, v56);
            memcpy_0(v125[0], v54, 2 * v53 + 2);
            *((_QWORD *)&v126 + 1) = v55;
            v40 = v111;
          }
          else
          {
            *(_OWORD *)v125 = *(_OWORD *)v54;
            *((_QWORD *)&v126 + 1) = 7;
          }
          *(_QWORD *)&v126 = v53;
          v57 = (const struct Spectre::Utils::ConfigurationValue *)Spectre::Utils::ConfigurationValue::GetContent(
                                                                     Content,
                                                                     v125);
          v58 = Spectre::Utils::ConfigurationValue::ConfigurationValue((Spectre::Utils::ConfigurationValue *)v122, v57);
          if ( (unsigned __int8)Spectre::Utils::IsSameValueType(v40, v58) )
          {
            v125[0] = 0;
            v126 = 0u;
            v59 = v128;
            v60 = Src;
            if ( *((_QWORD *)&v128 + 1) >= 8u )
              v60 = (void **)Src[0];
            if ( (unsigned __int64)v128 >= 8 )
            {
              v61 = v128 | 7;
              if ( ((unsigned __int64)v128 | 7) > 0x7FFFFFFFFFFFFFFELL )
                v61 = 0x7FFFFFFFFFFFFFFELL;
              v62 = v61 + 1;
              if ( v61 == -1 )
                v62 = -1;
              v125[0] = (void *)std::allocator<wchar_t>::allocate(v125, v62);
              memcpy_0(v125[0], v60, 2 * v59 + 2);
              *((_QWORD *)&v126 + 1) = v61;
              v40 = v111;
            }
            else
            {
              *(_OWORD *)v125 = *(_OWORD *)v60;
              *((_QWORD *)&v126 + 1) = 7;
            }
            *(_QWORD *)&v126 = v59;
            Spectre::Utils::SetObjectValue(v40, Content, v125);
            goto LABEL_155;
          }
          v44 = 1;
        }
        else
        {
          v133[0] = 0;
          v134 = 0;
          v135 = 7;
          v63 = -1;
          do
            ++v63;
          while ( *(_WORD *)(v14 + 2 * v63) );
          std::wstring::assign(v133);
          Spectre::Utils::SetObjectValue(v40, Content, v133);
          Spectre::Utils::LexicalCast<std::string,wchar_t const *>(Block, &v124);
          v64 = Size;
          if ( 0x7FFFFFFFFFFFFFFFLL - Size < 0x38 )
            std::_Xlen_string();
          v65 = Block;
          if ( v132 >= 0x10 )
            v65 = (void **)Block[0];
          v113[0] = 0;
          v114 = 0;
          v115 = 0;
          v66 = Size + 56;
          v67 = 15;
          v68 = v113;
          if ( Size + 56 > 0xF )
          {
            v67 = v66 | 0xF;
            if ( (v66 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
            {
              if ( v67 < 0x16 )
                v67 = 22;
            }
            else
            {
              v67 = 0x7FFFFFFFFFFFFFFFLL;
            }
            v69 = v67 + 1;
            if ( v67 == -1 )
              v69 = -1;
            if ( v69 < 0x1000 )
            {
              if ( v69 )
                v68 = operator new(v69);
              else
                v68 = 0;
            }
            else
            {
              if ( v69 + 39 < v69 )
                __scrt_throw_std_bad_array_new_length();
              v70 = operator new(v69 + 39);
              if ( !v70 )
                _invalid_parameter_noinfo_noreturn();
              v68 = (_QWORD *)(((unsigned __int64)v70 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v68 - 1) = v70;
            }
            v113[0] = v68;
          }
          v114 = v64 + 56;
          v115 = v67;
          qmemcpy(v68, "WARNING: Object stored in ConfigurationManager with key<", 56);
          memcpy_0(v68 + 7, v65, v64);
          *((_BYTE *)v68 + v66) = 0;
          v71 = v112 | 1;
          v72 = v114;
          if ( v115 - v114 < 0x3E )
          {
            v75 = (void **)std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(
                             v113,
                             0x3Eu);
          }
          else
          {
            v114 += 62;
            v73 = v113;
            if ( v115 >= 0x10 )
              v73 = (void **)v113[0];
            v74 = (char *)v73 + v72;
            memmove_0(v74, "> has no value. Property has been replaced with loaded value.\n", 0x3Eu);
            v74[62] = 0;
            v75 = v113;
          }
          v125[0] = 0;
          v126 = 0u;
          *(_OWORD *)v125 = *(_OWORD *)v75;
          v126 = *((_OWORD *)v75 + 1);
          v75[2] = 0;
          v75[3] = (void *)15;
          *(_BYTE *)v75 = 0;
          v112 = v71 | 2;
          if ( v115 >= 0x10 )
          {
            v76 = v113[0];
            if ( v115 + 1 >= 0x1000 )
            {
              v76 = (void *)*((_QWORD *)v113[0] - 1);
              if ( (unsigned __int64)((char *)v113[0] - (char *)v76 - 8) > 0x1F )
                _invalid_parameter_noinfo_noreturn();
            }
            operator delete(v76);
          }
          v114 = 0;
          v115 = 15;
          LOBYTE(v113[0]) = 0;
          v77 = v125;
          if ( *((_QWORD *)&v126 + 1) >= 0x10u )
            v77 = (void **)v125[0];
          Trace::LevelSettingsWrapper::Output(&gTraceLevelsConfigurationManager, 3, "%s", (const char *)v77);
          if ( *((_QWORD *)&v126 + 1) >= 0x10u )
          {
            v78 = v125[0];
            if ( (unsigned __int64)(*((_QWORD *)&v126 + 1) + 1LL) >= 0x1000 )
            {
              v78 = (void *)*((_QWORD *)v125[0] - 1);
              if ( (unsigned __int64)((char *)v125[0] - (char *)v78 - 8) > 0x1F )
                _invalid_parameter_noinfo_noreturn();
            }
            operator delete(v78);
          }
          *(_QWORD *)&v126 = 0;
          *((_QWORD *)&v126 + 1) = 15;
          LOBYTE(v125[0]) = 0;
          if ( v132 >= 0x10 )
          {
            v79 = Block[0];
            if ( v132 + 1 >= 0x1000 )
            {
              v79 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v79 - 8) > 0x1F )
                _invalid_parameter_noinfo_noreturn();
            }
            operator delete(v79);
          }
          v14 = v124;
LABEL_155:
          v44 = 0;
        }
        if ( *((_QWORD *)&v128 + 1) < 8u )
          goto LABEL_161;
        v51 = Src[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v128 + 1) + 2) >= 0x1000 )
        {
          v51 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v51 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
LABEL_85:
        operator delete(v51);
        goto LABEL_161;
      }
      if ( v116 == 1 )
      {
        v133[0] = 0;
        v134 = 0;
        v135 = 7;
        v91 = -1;
        do
          ++v91;
        while ( *(_WORD *)(v14 + 2 * v91) );
        std::wstring::assign(v133);
        Spectre::Utils::SetObjectValue(v111, v32, v133);
        v125[0] = 0;
        *(_QWORD *)&v126 = 0;
        *((_QWORD *)&v126 + 1) = 7;
        v92 = -1;
        do
          ++v92;
        while ( *(_WORD *)(v14 + 2 * v92) );
        std::wstring::assign(v125);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
          v138,
          v121,
          v125);
        goto LABEL_187;
      }
      Spectre::Utils::LexicalCast<std::string,wchar_t const *>(v133, &v124);
      Src[0] = 0;
      *(_QWORD *)&v128 = 0;
      *((_QWORD *)&v128 + 1) = 15;
      if ( v36 )
      {
        v95 = std::operator+<char>(v125);
        v96 = std::operator+<char>(
                Block,
                v95,
                "> is already in configuration and load policy is 'Add', so the new value was not loaded\n");
        std::string::operator=(Src, v96);
        if ( v132 >= 0x10 )
          std::allocator<unsigned char>::deallocate(Block, Block[0], v132 + 1);
        Size = 0;
        v132 = 15;
        LOBYTE(Block[0]) = 0;
      }
      else
      {
        v93 = std::operator+<char>(v125);
        v94 = std::operator+<char>(
                Block,
                v93,
                "> was ignored because load policy is 'Modify' rather than 'Add' or 'ModifyAdd'\n");
        std::string::operator=(Src, v94);
        if ( v132 >= 0x10 )
          std::allocator<unsigned char>::deallocate(Block, Block[0], v132 + 1);
        Size = 0;
        v132 = 15;
        LOBYTE(Block[0]) = 0;
      }
      if ( *((_QWORD *)&v126 + 1) >= 0x10u )
        std::allocator<unsigned char>::deallocate(v125, v125[0], *((_QWORD *)&v126 + 1) + 1LL);
      v97 = Src;
      if ( *((_QWORD *)&v128 + 1) >= 0x10u )
        v97 = (void **)Src[0];
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsConfigurationManager, 3, "%s", (const char *)v97);
      if ( *((_QWORD *)&v128 + 1) >= 0x10u )
        std::allocator<unsigned char>::deallocate(Src, Src[0], *((_QWORD *)&v128 + 1) + 1LL);
      *(_QWORD *)&v128 = 0;
      *((_QWORD *)&v128 + 1) = 15;
      LOBYTE(Src[0]) = 0;
      v87 = v135;
      if ( v135 >= 0x10 )
      {
        v88 = v133[0];
        v89 = v133;
LABEL_204:
        std::allocator<unsigned char>::deallocate(v89, v88, v87 + 1);
      }
LABEL_205:
      v10 += 32;
      v9 = *((_QWORD *)&v144 + 1);
      v11 = v144;
    }
    Mtx_unlock_0(v7);
    v98 = (_QWORD *)v139[0];
    v99 = *(_QWORD **)v139[0];
    v100 = v117;
    while ( v99 != v98 )
    {
      Spectre::Utils::JsonConfigurationManager::TriggerHandlers(v100, v99 + 2);
      v99 = (_QWORD *)*v99;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Spectre::Utils::ConfigurationValue>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Spectre::Utils::ConfigurationValue>>>>>>(&v140);
    std::list<std::wstring>::~list<std::wstring>(v139);
    v101 = v145[1];
    if ( v145[1] )
    {
      v102 = *(_QWORD **)v145[1];
      if ( *(_QWORD *)v145[1] )
      {
        do
        {
          if ( v102 == *((_QWORD **)v101 + 2) )
            break;
          v103 = (_QWORD *)v102[2];
          free(v102);
          *(_QWORD *)v101 = v103;
          v102 = v103;
        }
        while ( v103 );
      }
      v104 = *(_QWORD **)v101;
      if ( *(_QWORD *)v101 && v104 == *((_QWORD **)v101 + 2) )
        v104[1] = 0;
      operator delete(*((void **)v101 + 4));
      operator delete(v101);
    }
    free((void *)v147);
    operator delete(v146[1]);
  }
  catch ( ... )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsConfigurationManager,
      3,
      "Failed to deserialise the JSON configuration. Check the configuration format.");
    throw;
  }
}

```

## disassembly

```asm
0x1804b7680  mov     r11, rsp
0x1804b7683  mov     [r11+10h], rbx
0x1804b7687  mov     [r11+18h], rsi
0x1804b768b  push    rdi
0x1804b768c  push    r12
0x1804b768e  push    r13
0x1804b7690  push    r14
0x1804b7692  push    r15
0x1804b7694  sub     rsp, 2E0h
0x1804b769b  movaps  xmmword ptr [r11-38h], xmm6
0x1804b76a0  mov     rax, cs:__security_cookie
0x1804b76a7  xor     rax, rsp
0x1804b76aa  mov     [rsp+308h+var_48], rax
0x1804b76b2  mov     [rsp+308h+var_2A0], r8d
0x1804b76b7  mov     rbx, rdx
0x1804b76ba  mov     rsi, rcx
0x1804b76bd  mov     [rsp+308h+var_298], rcx
0x1804b76c2  xor     r12d, r12d
0x1804b76c5  mov     [rsp+308h+var_2C8], r12d
0x1804b76ca  xorps   xmm0, xmm0
0x1804b76cd  movups  xmmword ptr [r11-58h], xmm0
0x1804b76d2  movups  [rsp+308h+var_A8], xmm0
0x1804b76da  mov     [r11-9Ah], r12w
0x1804b76e2  movdqa  xmmword ptr [rsp+308h+var_98], xmm0
0x1804b76eb  xorps   xmm1, xmm1
0x1804b76ee  movdqa  xmmword ptr [rsp+308h+var_88], xmm1
0x1804b76f7  movdqa  xmmword ptr [r11-78h], xmm0
0x1804b76fd  movdqa  xmm1, cs:__xmm@00000000000004000000000000000000
0x1804b7705  movdqa  xmmword ptr [r11-68h], xmm1
0x1804b770b  mov     [r11-58h], r12d
0x1804b770f  mov     [r11-50h], r12
0x1804b7713  lea     ecx, [r12+28h]; Size
0x1804b7718  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804b771d  mov     [rsp+308h+var_290], rax
0x1804b7722  test    rax, rax
0x1804b7725  jz      short loc_1804B774A
0x1804b7727  xorps   xmm0, xmm0
0x1804b772a  movups  xmmword ptr [rax], xmm0
0x1804b772d  movups  xmmword ptr [rax+10h], xmm0
0x1804b7731  mov     [rax], r12
0x1804b7734  mov     qword ptr [rax+8], 10000h
0x1804b773c  mov     [rax+10h], r12
0x1804b7740  mov     [rax+18h], r12
0x1804b7744  mov     [rax+20h], r12
0x1804b7748  jmp     short loc_1804B774D
0x1804b774a  mov     rax, r12
0x1804b774d  mov     [rsp+308h+var_98], rax
0x1804b7755  mov     [rsp+308h+var_98+8], rax
0x1804b775d  xorps   xmm0, xmm0
0x1804b7760  movups  [rsp+308h+var_E8], xmm0
0x1804b7768  movups  [rsp+308h+var_D8], xmm0
0x1804b7770  movups  [rsp+308h+var_C8], xmm0
0x1804b7778  movups  [rsp+308h+var_B8], xmm0
0x1804b7780  movss   dword ptr [rsp+308h+var_E8], xmm0
0x1804b7789  mov     qword ptr [rsp+308h+var_E8+8], r12
0x1804b7791  mov     qword ptr [rsp+308h+var_D8], r12
0x1804b7799  mov     ecx, 30h ; '0'; Size
0x1804b779e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804b77a3  mov     [rax], rax
0x1804b77a6  mov     [rax+8], rax
0x1804b77aa  mov     qword ptr [rsp+308h+var_E8+8], rax
0x1804b77b2  mov     qword ptr [rsp+308h+var_D8+8], r12
0x1804b77ba  xorps   xmm0, xmm0
0x1804b77bd  movdqa  [rsp+308h+var_C8], xmm0
0x1804b77c6  mov     qword ptr [rsp+308h+var_B8], 7
0x1804b77d2  mov     qword ptr [rsp+308h+var_B8+8], 8
0x1804b77de  movss   xmm0, cs:__real@3f800000
0x1804b77e6  movss   dword ptr [rsp+308h+var_E8], xmm0
0x1804b77ef  mov     r8, rax
0x1804b77f2  mov     edx, 10h
0x1804b77f7  lea     rcx, [rsp+308h+var_D8+8]
0x1804b77ff  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>)
0x1804b7804  nop
0x1804b7805  cmp     qword ptr [rbx+18h], 8
0x1804b780a  jb      short loc_1804B780F
0x1804b780c  mov     rbx, [rbx]
0x1804b780f  mov     [rsp+308h+var_F8], rbx
0x1804b7817  mov     [rsp+308h+var_F0], rbx
0x1804b781f  lea     rdx, [rsp+308h+var_F8]
0x1804b7827  lea     rcx, [rsp+308h+var_A8]
0x1804b782f  call    ??$ParseStream@$0A@U?$UTF16@_W@rapidjson@Spectre@@U?$GenericStringStream@U?$UTF16@_W@rapidjson@Spectre@@@23@@?$GenericDocument@U?$UTF16@_W@rapidjson@Spectre@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@Spectre@@@23@VCrtAllocator@23@@rapidjson@Spectre@@QEAAAEAV012@AEAU?$GenericStringStream@U?$UTF16@_W@rapidjson@Spectre@@@12@@Z; Spectre::rapidjson::GenericDocument<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>,Spectre::rapidjson::CrtAllocator>::ParseStream<0,Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::GenericStringStream<Spectre::rapidjson::UTF16<wchar_t>>>(Spectre::rapidjson::GenericStringStream<Spectre::rapidjson::UTF16<wchar_t>> &)
0x1804b7834  cmp     [rsp+308h+var_58], 0
0x1804b783c  jnz     loc_1804B8C1B
0x1804b7842  lea     r14, [rsi+40h]
0x1804b7846  mov     [rsp+308h+var_288], r14
0x1804b784e  mov     rcx, r14; _Mtx_t
0x1804b7851  call    _Mtx_lock_0
0x1804b7856  test    eax, eax
0x1804b7858  jnz     loc_1804B8CC3
0x1804b785e  mov     r10, 0FFFFFFFFFFFFh
0x1804b7868  mov     rbx, qword ptr [rsp+308h+var_A8+8]
0x1804b7870  mov     rsi, rbx
0x1804b7873  and     rsi, r10
0x1804b7876  mov     eax, dword ptr [rsp+308h+var_A8]
0x1804b787d  mov     ecx, eax
0x1804b787f  shl     rcx, 5
0x1804b7883  add     rcx, rsi
0x1804b7886  mov     [rsp+308h+var_290], rcx
0x1804b788b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1804b7892  mov     r11d, 405h
0x1804b7898  mov     rdi, 0FFFF000000000000h
0x1804b78a2  mov     edx, 1000h
0x1804b78a7  cmp     rsi, rcx
0x1804b78aa  jz      loc_1804B8B1F
0x1804b78b0  test    [rsi+0Eh], dx
0x1804b78b4  jz      short loc_1804B78BB
0x1804b78b6  mov     r13, rsi
0x1804b78b9  jmp     short loc_1804B78C2
0x1804b78bb  mov     r13, [rsi+8]
0x1804b78bf  and     r13, r10
0x1804b78c2  mov     [rsp+308h+var_198], r13
0x1804b78ca  xorps   xmm0, xmm0
0x1804b78cd  movups  [rsp+308h+var_148], xmm0
0x1804b78d5  mov     word ptr [rsp+308h+var_148+0Eh], r11w
0x1804b78de  mov     r9, qword ptr [rsp+308h+var_148+8]
0x1804b78e6  and     r9, rdi
0x1804b78e9  or      r9, r13
0x1804b78ec  mov     [rsp+308h+var_2D0], r9
0x1804b78f1  mov     qword ptr [rsp+308h+var_148+8], r9
0x1804b78f9  mov     r12, r9
0x1804b78fc  shr     r12, 30h
0x1804b7900  mov     r15, r8
0x1804b7903  inc     r15
0x1804b7906  cmp     word ptr [r13+r15*2+0], 0
0x1804b790d  jnz     short loc_1804B7903
0x1804b790f  mov     dword ptr [rsp+308h+var_148], r15d
0x1804b7917  and     rbx, r10
0x1804b791a  mov     edi, eax
0x1804b791c  shl     rdi, 5
0x1804b7920  add     rdi, rbx
0x1804b7923  cmp     rbx, rdi
0x1804b7926  jz      loc_1804B79D6
0x1804b792c  and     r12w, dx
0x1804b7930  test    r12w, r12w
0x1804b7934  jz      short loc_1804B7949
0x1804b7936  movzx   eax, word ptr [rsp+308h+var_148+0Ch]
0x1804b793e  mov     r8d, 6
0x1804b7944  sub     r8d, eax
0x1804b7947  jmp     short loc_1804B794C
0x1804b7949  mov     r8d, r15d
0x1804b794c  and     dx, [rbx+0Eh]
0x1804b7950  jz      short loc_1804B795F
0x1804b7952  movzx   eax, word ptr [rbx+0Ch]
0x1804b7956  mov     ecx, 6
0x1804b795b  sub     ecx, eax
0x1804b795d  jmp     short loc_1804B7961
0x1804b795f  mov     ecx, [rbx]
0x1804b7961  cmp     r8d, ecx
0x1804b7964  jnz     short loc_1804B79B2
0x1804b7966  test    r12w, r12w
0x1804b796a  jz      short loc_1804B7976
0x1804b796c  lea     rcx, [rsp+308h+var_148]
0x1804b7974  jmp     short loc_1804B797C
0x1804b7976  mov     rcx, r9
0x1804b7979  and     rcx, r10; Buf1
0x1804b797c  test    dx, dx
0x1804b797f  jz      short loc_1804B7986
0x1804b7981  mov     rdx, rbx
0x1804b7984  jmp     short loc_1804B798D
0x1804b7986  mov     rdx, [rbx+8]
0x1804b798a  and     rdx, r10; Buf2
0x1804b798d  cmp     rcx, rdx
0x1804b7990  jz      short loc_1804B79C4
0x1804b7992  add     r8, r8; Size
0x1804b7995  call    memcmp_0
0x1804b799a  test    eax, eax
0x1804b799c  setz    al
0x1804b799f  test    al, al
0x1804b79a1  jnz     short loc_1804B79C4
0x1804b79a3  mov     r9, [rsp+308h+var_2D0]
0x1804b79a8  mov     r10, 0FFFFFFFFFFFFh
0x1804b79b2  add     rbx, 20h ; ' '
0x1804b79b6  cmp     rbx, rdi
0x1804b79b9  mov     edx, 1000h
0x1804b79be  jnz     loc_1804B7930
0x1804b79c4  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1804b79cb  cmp     rbx, rdi
0x1804b79ce  jz      short loc_1804B79D6
0x1804b79d0  lea     rax, [rbx+10h]
0x1804b79d4  jmp     short loc_1804B79E7
0x1804b79d6  xorps   xmm0, xmm0
0x1804b79d9  movups  cs:?buffer@?5???$?AV?$MemoryPoolAllocator@VCrtAllocator@rapidjson@Spectre@@@rapidjson@Spectre@@@?$GenericValue@U?$UTF16@_W@rapidjson@Spectre@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@Spectre@@@23@@rapidjson@Spectre@@QEAAAEAV123@AEBV123@@Z@4PADA, xmm0; char near * `Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>::operator[]<Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>(Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>> const &)'::`6'::buffer
0x1804b79e0  lea     rax, ?buffer@?5???$?AV?$MemoryPoolAllocator@VCrtAllocator@rapidjson@Spectre@@@rapidjson@Spectre@@@?$GenericValue@U?$UTF16@_W@rapidjson@Spectre@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@Spectre@@@23@@rapidjson@Spectre@@QEAAAEAV123@AEBV123@@Z@4PADA; char near * `Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>::operator[]<Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>>(Spectre::rapidjson::GenericValue<Spectre::rapidjson::UTF16<wchar_t>,Spectre::rapidjson::MemoryPoolAllocator<Spectre::rapidjson::CrtAllocator>> const &)'::`6'::buffer
0x1804b79e7  mov     [rsp+308h+var_2D0], rax
0x1804b79ec  xor     r12d, r12d
0x1804b79ef  mov     [rsp+308h+var_190], r12
0x1804b79f7  mov     qword ptr [rsp+308h+var_180], r12
0x1804b79ff  mov     qword ptr [rsp+308h+var_180+8], 7
0x1804b7a0b  mov     word ptr [rsp+308h+var_190], r12w
0x1804b7a14  inc     r8
0x1804b7a17  cmp     [r13+r8*2+0], r12w
0x1804b7a1d  jnz     short loc_1804B7A14
0x1804b7a1f  mov     rdx, r13
0x1804b7a22  lea     rcx, [rsp+308h+var_190]; void *
0x1804b7a2a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1804b7a2f  nop
0x1804b7a30  mov     rbx, [rsp+308h+var_298]
0x1804b7a35  mov     rax, [rbx]
0x1804b7a38  lea     r8, [rsp+308h+var_190]
0x1804b7a40  lea     rdx, [rsp+308h+Block]
0x1804b7a48  mov     rcx, rbx
0x1804b7a4b  mov     rax, [rax+38h]
0x1804b7a4f  call    cs:__guard_dispatch_icall_fptr
0x1804b7a55  mov     r15, rax
0x1804b7a58  lea     rdi, [rbx+90h]
0x1804b7a5f  mov     r8, rax
0x1804b7a62  lea     rdx, [rsp+308h+var_2C0]
0x1804b7a67  mov     rcx, rdi
0x1804b7a6a  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VCModelMetaData@NMR@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VCModelMetaData@NMR@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VCModelMetaData@NMR@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<NMR::CModelMetaData>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<NMR::CModelMetaData>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1804b7a6f  mov     rbx, [rsp+308h+var_2B0]
0x1804b7a74  cmp     byte ptr [rbx+19h], 0
0x1804b7a78  jnz     short loc_1804B7A91
0x1804b7a7a  lea     r8, [rbx+20h]
0x1804b7a7e  mov     rdx, r15
0x1804b7a81  mov     rcx, rdi
0x1804b7a84  call    ??R?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@0@Z; std::less<std::wstring>::operator()(std::wstring const &,std::wstring const &)
0x1804b7a89  test    al, al
0x1804b7a8b  jz      loc_1804B7B51
0x1804b7a91  mov     rax, 155555555555555h
0x1804b7a9b  cmp     [rdi+8], rax
0x1804b7a9f  jz      loc_1804B8CCB
0x1804b7aa5  mov     r12, [rdi]
0x1804b7aa8  mov     [rsp+308h+var_F8], rdi
0x1804b7ab0  xor     ebx, ebx
0x1804b7ab2  mov     [rsp+308h+var_F0], rbx
0x1804b7aba  mov     ecx, 0C0h; Size
0x1804b7abf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804b7ac4  mov     rbx, rax
0x1804b7ac7  mov     [rsp+308h+var_F0], rax
0x1804b7acf  lea     rcx, [rax+20h]
0x1804b7ad3  mov     qword ptr [rsp+308h+var_148], rcx
0x1804b7adb  xor     eax, eax
0x1804b7add  mov     [rcx], rax
0x1804b7ae0  mov     [rcx+10h], rax
0x1804b7ae4  mov     [rcx+18h], rax
0x1804b7ae8  movups  xmm0, xmmword ptr [r15]
0x1804b7aec  movups  xmmword ptr [rcx], xmm0
0x1804b7aef  movups  xmm1, xmmword ptr [r15+10h]
0x1804b7af4  movups  xmmword ptr [rcx+10h], xmm1
0x1804b7af8  mov     [r15+10h], rax
0x1804b7afc  mov     qword ptr [r15+18h], 7
0x1804b7b04  mov     [r15], ax
0x1804b7b08  add     rcx, 20h ; ' '; this
0x1804b7b0c  call    ??0ConfigurationValue@Utils@Spectre@@QEAA@XZ; Spectre::Utils::ConfigurationValue::ConfigurationValue(void)
0x1804b7b11  nop
0x1804b7b12  mov     [rbx], r12
0x1804b7b15  mov     [rbx+8], r12
0x1804b7b19  mov     [rbx+10h], r12
0x1804b7b1d  mov     word ptr [rbx+18h], 0
0x1804b7b23  xor     r12d, r12d
0x1804b7b26  mov     [rsp+308h+var_F0], r12
0x1804b7b2e  movups  xmm0, xmmword ptr [rsp+308h+var_2C0]
0x1804b7b33  movaps  [rsp+308h+var_148], xmm0
0x1804b7b3b  mov     r8, rbx
0x1804b7b3e  lea     rdx, [rsp+308h+var_148]
0x1804b7b46  mov     rcx, rdi
0x1804b7b49  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> *>,std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> * const)
0x1804b7b4e  mov     rbx, rax
0x1804b7b51  lea     rdi, [rbx+40h]
0x1804b7b55  mov     rdx, [rsp+308h+var_120]
0x1804b7b5d  cmp     rdx, 8
0x1804b7b61  jb      short loc_1804B7BA0
0x1804b7b63  lea     rdx, ds:2[rdx*2]
0x1804b7b6b  mov     rcx, [rsp+308h+Block]; Block
0x1804b7b73  mov     rax, rcx
0x1804b7b76  cmp     rdx, 1000h
0x1804b7b7d  jb      short loc_1804B7B9B
0x1804b7b7f  add     rdx, 27h ; '''
0x1804b7b83  mov     rcx, [rcx-8]
0x1804b7b87  sub     rax, rcx
0x1804b7b8a  add     rax, 0FFFFFFFFFFFFFFF8h
0x1804b7b8e  cmp     rax, 1Fh
0x1804b7b92  jbe     short loc_1804B7B9B
0x1804b7b94  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1804b7b9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1804b7ba0  mov     [rsp+308h+Size], r12
0x1804b7ba8  mov     [rsp+308h+var_120], 7
0x1804b7bb4  mov     word ptr [rsp+308h+Block], r12w
0x1804b7bbd  mov     rdx, qword ptr [rsp+308h+var_180+8]
0x1804b7bc5  cmp     rdx, 8
0x1804b7bc9  jb      short loc_1804B7C08
0x1804b7bcb  lea     rdx, ds:2[rdx*2]
0x1804b7bd3  mov     rcx, [rsp+308h+var_190]; Block
0x1804b7bdb  mov     rax, rcx
0x1804b7bde  cmp     rdx, 1000h
0x1804b7be5  jb      short loc_1804B7C03
0x1804b7be7  add     rdx, 27h ; '''
0x1804b7beb  mov     rcx, [rcx-8]
0x1804b7bef  sub     rax, rcx
0x1804b7bf2  add     rax, 0FFFFFFFFFFFFFFF8h
0x1804b7bf6  cmp     rax, 1Fh
0x1804b7bfa  jbe     short loc_1804B7C03
0x1804b7bfc  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1804b7c03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1804b7c08  mov     qword ptr [rsp+308h+var_180], r12
0x1804b7c10  mov     qword ptr [rsp+308h+var_180+8], 7
0x1804b7c1c  mov     word ptr [rsp+308h+var_190], r12w
0x1804b7c25  mov     rdx, r13; wchar_t *
0x1804b7c28  mov     rcx, rdi; this
0x1804b7c2b  call    ?HasKey@ConfigurationValue@Utils@Spectre@@QEBA_NPEB_W@Z; Spectre::Utils::ConfigurationValue::HasKey(wchar_t const *)
  ... truncated ...
```

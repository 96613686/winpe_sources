# _expandlocale

- ea: `0x1801989a0`
- end: `0x180199488`
- name: `_expandlocale`
- size: `2792`
- prototype: `__int64 __fastcall(Microsoft::glTF::Document *this)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801986c0`

## callees

- `0x1800154a0`
- `0x180016430`
- `0x180021570`
- `0x180027ff0`
- `0x18002b950`
- `0x18002bd50`
- `0x18002f9a0`
- `0x18002fa70`
- `0x18002fb40`
- `0x18002fbf0`
- `0x18002fcc0`
- `0x18002fd90`
- `0x18002fe60`
- `0x180030150`
- `0x180030220`
- `0x1800302f0`
- `0x1800305c0`
- `0x180030690`
- `0x180189290`
- `0x180189670`
- `0x180189fd0`
- `0x18018a2f0`
- `0x18018a640`
- `0x18018a770`
- `0x18018ab30`
- `0x18018ae30`
- `0x18018b150`
- `0x18018b410`
- `0x18018b6d0`
- `0x18018b960`
- `0x18018bce0`
- `0x1801930c0`
- `0x180197300`
- `0x1801989a0`
- `0x180199a00`
- `0x18019be10`
- `0x18019f9a0`
- `0x1801b66a0`
- `0x1801b7820`
- `0x1801cb390`
- `0x18039e5b0`
- `0x18039ebb0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180198a8c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180199241`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180199481`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180198a8c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180199241`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180199481`

## string_xrefs

- `0x1801989f9`: `glTF.schema.json`
- `0x18019924d`: `extensionsUsed`
- `0x180199357`: `extensionsRequired`
- `0x180198b7b`: `accessors`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Microsoft::glTF::Document *__fastcall expandlocale(
        Microsoft::glTF::Document *this,
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // r8
  __int64 *DefaultSchemaLocator; // rcx
  __int64 v10; // rax
  void *v11; // rcx
  __int64 v12; // rdi
  _QWORD *v13; // rbx
  _QWORD *v14; // rbx
  _QWORD *v15; // rbx
  _QWORD *v16; // rbx
  _QWORD *v17; // rbx
  _QWORD *v18; // rbx
  _QWORD *v19; // rbx
  _QWORD *v20; // rbx
  _QWORD *v21; // rbx
  _QWORD *v22; // rbx
  _QWORD *v23; // rbx
  _QWORD *v24; // rbx
  _QWORD *v25; // rbx
  __int64 v26; // rax
  void *v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // r8
  void *v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rdi
  __int64 v35; // rdx
  __int64 v36; // r8
  void *v37; // rcx
  _QWORD v39[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v40; // [rsp+40h] [rbp-C0h]
  _BYTE v41[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v42[64]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v44[2]; // [rsp+A8h] [rbp-58h] BYREF
  void *v45[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v47; // [rsp+D0h] [rbp-30h]
  void *Block[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v50; // [rsp+F0h] [rbp-10h]
  _BYTE v51[304]; // [rsp+100h] [rbp+0h] BYREF

  v44[1] = this;
  v40 = 0;
  Block[0] = 0;
  v49 = 0;
  v50 = 15;
  v8 = -1;
  do
    ++v8;
  while ( aGltfSchemaJson_1[v8] );
  std::string::assign(Block);
  DefaultSchemaLocator = (__int64 *)Microsoft::glTF::GetDefaultSchemaLocator(v44, a4);
  v10 = *DefaultSchemaLocator;
  *DefaultSchemaLocator = 0;
  v43 = v10;
  Microsoft::glTF::ValidateDocumentAgainstSchema(a2, Block, &v43);
  if ( v44[0] )
    (**(void (__fastcall ***)(_QWORD, __int64))v44[0])(v44[0], 1);
  if ( v50 >= 0x10 )
  {
    v11 = Block[0];
    if ( v50 + 1 >= 0x1000 )
    {
      v11 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v11);
  }
  v49 = 0;
  v50 = 15;
  LOBYTE(Block[0]) = 0;
  Microsoft::glTF::Document::Document(this);
  v40 = 1;
  Microsoft::glTF::rapidjson::GenericValue<Microsoft::glTF::rapidjson::UTF8<char>,Microsoft::glTF::rapidjson::MemoryPoolAllocator<Microsoft::glTF::rapidjson::CrtAllocator>>::FindMember(
    a2,
    v39,
    "asset");
  if ( v39[0] != (*((_QWORD *)a2 + 1) & 0xFFFFFFFFFFFFLL) + 32LL * *a2 )
  {
    v12 = sub_18019BE10(v51, v39[0] + 16LL, a3);
    Microsoft::glTF::glTFProperty::operator=((char *)this + 168, v12);
    std::string::operator=((char *)this + 336, v12 + 168);
    std::string::operator=((char *)this + 368, v12 + 200);
    std::string::operator=((char *)this + 400, v12 + 232);
    std::string::operator=((char *)this + 432, v12 + 264);
    Microsoft::glTF::Asset::~Asset((Microsoft::glTF::Asset *)v51);
  }
  v13 = (_QWORD *)sub_180189290((unsigned int)v41, (unsigned int)"accessors", (_DWORD)a2, a3, (__int64)sub_18019A4C0);
  if ( (_QWORD *)((char *)this + 464) != v13 )
  {
    std::vector<Microsoft::glTF::Accessor>::_Tidy((char *)this + 464);
    *((_QWORD *)this + 58) = *v13;
    *((_QWORD *)this + 59) = v13[1];
    *((_QWORD *)this + 60) = v13[2];
    *v13 = 0;
    v13[1] = 0;
    v13[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 488, v13 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Accessor>::_Tidy(v41);
  v14 = (_QWORD *)sub_180189670((unsigned int)v41, (unsigned int)"animations", (_DWORD)a2, a3, (__int64)sub_18019B060);
  if ( (_QWORD *)((char *)this + 552) != v14 )
  {
    std::vector<Microsoft::glTF::Animation>::_Tidy((char *)this + 552);
    *((_QWORD *)this + 69) = *v14;
    *((_QWORD *)this + 70) = v14[1];
    *((_QWORD *)this + 71) = v14[2];
    *v14 = 0;
    v14[1] = 0;
    v14[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 576, v14 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Animation>::_Tidy(v41);
  v15 = (_QWORD *)sub_180189FD0((unsigned int)v41, (unsigned int)"buffers", (_DWORD)a2, a3, (__int64)sub_18019C210);
  if ( (_QWORD *)((char *)this + 640) != v15 )
  {
    std::vector<Microsoft::glTF::Buffer>::_Tidy((char *)this + 640);
    *((_QWORD *)this + 80) = *v15;
    *((_QWORD *)this + 81) = v15[1];
    *((_QWORD *)this + 82) = v15[2];
    *v15 = 0;
    v15[1] = 0;
    v15[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 664, v15 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Buffer>::_Tidy(v41);
  v16 = (_QWORD *)sub_18018A2F0((unsigned int)v41, (unsigned int)"bufferViews", (_DWORD)a2, a3, (__int64)sub_18019C3B0);
  if ( (_QWORD *)((char *)this + 728) != v16 )
  {
    std::vector<Microsoft::glTF::BufferView>::_Tidy((char *)this + 728);
    *((_QWORD *)this + 91) = *v16;
    *((_QWORD *)this + 92) = v16[1];
    *((_QWORD *)this + 93) = v16[2];
    *v16 = 0;
    v16[1] = 0;
    v16[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 752, v16 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::BufferView>::_Tidy(v41);
  v17 = (_QWORD *)sub_18018A640((unsigned int)v41, (unsigned int)"cameras", (_DWORD)a2, a3, (__int64)sub_18019C700);
  if ( (_QWORD *)((char *)this + 816) != v17 )
  {
    std::vector<Microsoft::glTF::Camera>::_Tidy((char *)this + 816);
    *((_QWORD *)this + 102) = *v17;
    *((_QWORD *)this + 103) = v17[1];
    *((_QWORD *)this + 104) = v17[2];
    *v17 = 0;
    v17[1] = 0;
    v17[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 840, v17 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Camera>::_Tidy(v41);
  v18 = (_QWORD *)sub_18018A770((unsigned int)v41, (unsigned int)"images", (_DWORD)a2, a3, (__int64)sub_18019D2F0);
  if ( (_QWORD *)((char *)this + 904) != v18 )
  {
    std::vector<Microsoft::glTF::Image>::_Tidy((char *)this + 904);
    *((_QWORD *)this + 113) = *v18;
    *((_QWORD *)this + 114) = v18[1];
    *((_QWORD *)this + 115) = v18[2];
    *v18 = 0;
    v18[1] = 0;
    v18[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 928, v18 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Image>::_Tidy(v41);
  v19 = (_QWORD *)sub_18018AB30((unsigned int)v41, (unsigned int)"materials", (_DWORD)a2, a3, (__int64)sub_18019D6E0);
  if ( (_QWORD *)((char *)this + 992) != v19 )
  {
    std::vector<Microsoft::glTF::Material>::_Tidy((char *)this + 992);
    *((_QWORD *)this + 124) = *v19;
    *((_QWORD *)this + 125) = v19[1];
    *((_QWORD *)this + 126) = v19[2];
    *v19 = 0;
    v19[1] = 0;
    v19[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1016, v19 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Material>::_Tidy(v41);
  v20 = (_QWORD *)sub_18018AE30((unsigned int)v41, (unsigned int)"meshes", (_DWORD)a2, a3, (__int64)setlocale_set_cat);
  if ( (_QWORD *)((char *)this + 1080) != v20 )
  {
    std::vector<Microsoft::glTF::Mesh>::_Tidy((char *)this + 1080);
    *((_QWORD *)this + 135) = *v20;
    *((_QWORD *)this + 136) = v20[1];
    *((_QWORD *)this + 137) = v20[2];
    *v20 = 0;
    v20[1] = 0;
    v20[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1104, v20 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Mesh>::_Tidy(v41);
  v21 = (_QWORD *)sub_18018B150((unsigned int)v41, (unsigned int)"nodes", (_DWORD)a2, a3, (__int64)sub_18019EDB0);
  if ( (_QWORD *)((char *)this + 1168) != v21 )
  {
    std::vector<Microsoft::glTF::Node>::_Tidy((char *)this + 1168);
    *((_QWORD *)this + 146) = *v21;
    *((_QWORD *)this + 147) = v21[1];
    *((_QWORD *)this + 148) = v21[2];
    *v21 = 0;
    v21[1] = 0;
    v21[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1192, v21 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Node>::_Tidy(v41);
  v22 = (_QWORD *)sub_18018B410((unsigned int)v41, (unsigned int)"samplers", (_DWORD)a2, a3, (__int64)sub_18019FA70);
  if ( (_QWORD *)((char *)this + 1256) != v22 )
  {
    std::vector<Microsoft::glTF::Scene>::_Tidy((char *)this + 1256);
    *((_QWORD *)this + 157) = *v22;
    *((_QWORD *)this + 158) = v22[1];
    *((_QWORD *)this + 159) = v22[2];
    *v22 = 0;
    v22[1] = 0;
    v22[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1280, v22 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Scene>::_Tidy(v41);
  v23 = (_QWORD *)sub_18018B6D0((unsigned int)v41, (unsigned int)"scenes", (_DWORD)a2, a3, (__int64)sub_18019FDA0);
  if ( (_QWORD *)((char *)this + 1344) != v23 )
  {
    std::vector<Microsoft::glTF::Scene>::_Tidy((char *)this + 1344);
    *((_QWORD *)this + 168) = *v23;
    *((_QWORD *)this + 169) = v23[1];
    *((_QWORD *)this + 170) = v23[2];
    *v23 = 0;
    v23[1] = 0;
    v23[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1368, v23 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Scene>::_Tidy(v41);
  v24 = (_QWORD *)sub_18018B960((unsigned int)v41, (unsigned int)"skins", (_DWORD)a2, a3, (__int64)sub_18019FFD0);
  if ( (_QWORD *)((char *)this + 1432) != v24 )
  {
    std::vector<Microsoft::glTF::Skin>::_Tidy((char *)this + 1432);
    *((_QWORD *)this + 179) = *v24;
    *((_QWORD *)this + 180) = v24[1];
    *((_QWORD *)this + 181) = v24[2];
    *v24 = 0;
    v24[1] = 0;
    v24[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1456, v24 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Skin>::_Tidy(v41);
  v25 = (_QWORD *)sub_18018BCE0((unsigned int)v41, (unsigned int)"textures", (_DWORD)a2, a3, (__int64)sub_1801A0B30);
  if ( (_QWORD *)((char *)this + 1520) != v25 )
  {
    std::vector<Microsoft::glTF::Texture>::_Tidy((char *)this + 1520);
    *((_QWORD *)this + 190) = *v25;
    *((_QWORD *)this + 191) = v25[1];
    *((_QWORD *)this + 192) = v25[2];
    *v25 = 0;
    v25[1] = 0;
    v25[2] = 0;
  }
  std::unordered_map<std::string,unsigned __int64>::operator=((char *)this + 1544, v25 + 3);
  std::unordered_set<std::string>::~unordered_set<std::string,std::hash<std::string>,std::equal_to<std::string>,std::allocator<std::string>>(v42);
  std::vector<Microsoft::glTF::Texture>::_Tidy(v41);
  sub_18019F9A0(a2, this, a3);
  Microsoft::glTF::rapidjson::GenericValue<Microsoft::glTF::rapidjson::UTF8<char>,Microsoft::glTF::rapidjson::MemoryPoolAllocator<Microsoft::glTF::rapidjson::CrtAllocator>>::FindMember(
    a2,
    v39,
    "scene");
  if ( v39[0] != (*((_QWORD *)a2 + 1) & 0xFFFFFFFFFFFFLL) + 32LL * *a2 )
  {
    v26 = std::to_string(v45, *(unsigned int *)(v39[0] + 16LL));
    std::string::operator=((char *)this + 1736, v26);
    if ( v47 >= 0x10 )
    {
      v27 = v45[0];
      if ( v47 + 1 >= 0x1000 )
      {
        v27 = (void *)*((_QWORD *)v45[0] - 1);
        if ( (unsigned __int64)((char *)v45[0] - (char *)v27 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v27);
    }
  }
  Microsoft::glTF::rapidjson::GenericValue<Microsoft::glTF::rapidjson::UTF8<char>,Microsoft::glTF::rapidjson::MemoryPoolAllocator<Microsoft::glTF::rapidjson::CrtAllocator>>::FindMember(
    a2,
    v39,
    "extensionsUsed");
  v28 = v39[0];
  if ( v39[0] != (*((_QWORD *)a2 + 1) & 0xFFFFFFFFFFFFLL) + 32LL * *a2 )
  {
    v29 = *(_QWORD *)(v39[0] + 24LL) & 0xFFFFFFFFFFFFLL;
    if ( v29 != v29 + 16LL * *(unsigned int *)(v39[0] + 16LL) )
    {
      do
      {
        if ( (*(_WORD *)(v29 + 14) & 0x1000) != 0 )
          v30 = v29;
        else
          v30 = *(_QWORD *)(v29 + 8) & 0xFFFFFFFFFFFFLL;
        v45[0] = 0;
        v46 = 0;
        v47 = 15;
        v31 = -1;
        do
          ++v31;
        while ( *(_BYTE *)(v30 + v31) );
        std::string::assign(v45);
        std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::emplace<std::string>(
          (char *)this + 1608,
          v39,
          v45);
        if ( v47 >= 0x10 )
        {
          v32 = v45[0];
          if ( v47 + 1 >= 0x1000 )
          {
            v32 = (void *)*((_QWORD *)v45[0] - 1);
            if ( (unsigned __int64)((char *)v45[0] - (char *)v32 - 8) > 0x1F )
LABEL_69:
              _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v32);
        }
        v29 += 16;
      }
      while ( v29 != (*(_QWORD *)(v28 + 24) & 0xFFFFFFFFFFFFLL) + 16LL * *(unsigned int *)(v28 + 16) );
    }
  }
  Microsoft::glTF::rapidjson::GenericValue<Microsoft::glTF::rapidjson::UTF8<char>,Microsoft::glTF::rapidjson::MemoryPoolAllocator<Microsoft::glTF::rapidjson::CrtAllocator>>::FindMember(
    a2,
    v39,
    "extensionsRequired");
  v33 = v39[0];
  if ( v39[0] != (*((_QWORD *)a2 + 1) & 0xFFFFFFFFFFFFLL) + 32LL * *a2 )
  {
    v34 = *(_QWORD *)(v39[0] + 24LL) & 0xFFFFFFFFFFFFLL;
    if ( v34 != v34 + 16LL * *(unsigned int *)(v39[0] + 16LL) )
    {
      do
      {
        if ( (*(_WORD *)(v34 + 14) & 0x1000) != 0 )
          v35 = v34;
        else
          v35 = *(_QWORD *)(v34 + 8) & 0xFFFFFFFFFFFFLL;
        v45[0] = 0;
        v46 = 0;
        v47 = 15;
        v36 = -1;
        do
          ++v36;
        while ( *(_BYTE *)(v35 + v36) );
        std::string::assign(v45);
        std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::emplace<std::string>(
          (char *)this + 1672,
          v39,
          v45);
        if ( v47 >= 0x10 )
        {
          v37 = v45[0];
          if ( v47 + 1 >= 0x1000 )
          {
            v37 = (void *)*((_QWORD *)v45[0] - 1);
            if ( (unsigned __int64)((char *)v45[0] - (char *)v37 - 8) > 0x1F )
              goto LABEL_69;
          }
          operator delete(v37);
        }
        v34 += 16;
      }
      while ( v34 != (*(_QWORD *)(v33 + 24) & 0xFFFFFFFFFFFFLL) + 16LL * *(unsigned int *)(v33 + 16) );
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801989a0  push    rbp
0x1801989a2  push    rbx
0x1801989a3  push    rsi
0x1801989a4  push    rdi
0x1801989a5  push    r12
0x1801989a7  push    r13
0x1801989a9  push    r14
0x1801989ab  push    r15
0x1801989ad  lea     rbp, [rsp-148h]
0x1801989b5  sub     rsp, 248h
0x1801989bc  mov     rax, cs:__security_cookie
0x1801989c3  xor     rax, rsp
0x1801989c6  mov     [rbp+180h+var_50], rax
0x1801989cd  mov     rbx, r9
0x1801989d0  mov     rsi, r8
0x1801989d3  mov     r14, rdx
0x1801989d6  mov     r15, rcx
0x1801989d9  mov     [rbp+180h+var_1D0], rcx
0x1801989dd  xor     r12d, r12d
0x1801989e0  mov     [rsp+280h+var_240], r12d
0x1801989e5  mov     [rbp+180h+Block], r12
0x1801989e9  mov     [rbp+180h+var_198], r12
0x1801989ed  mov     [rbp+180h+var_190], 0Fh
0x1801989f5  mov     byte ptr [rbp+180h+Block], r12b
0x1801989f9  lea     rdx, aGltfSchemaJson_1
0x180198a00  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180198a07  inc     r8
0x180198a0a  cmp     [rdx+r8], r12b
0x180198a0e  jnz     short loc_180198A07
0x180198a10  lea     rcx, [rbp+180h+Block]; void *
0x180198a14  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z
0x180198a19  nop
0x180198a1a  mov     rdx, rbx
0x180198a1d  lea     rcx, [rbp+180h+var_1D8]
0x180198a21  call    ?GetDefaultSchemaLocator@glTF@Microsoft@@YA?AV?$unique_ptr@$$CBVISchemaLocator@glTF@Microsoft@@U?$default_delete@$$CBVISchemaLocator@glTF@Microsoft@@@std@@@std@@W4SchemaFlags@12@@Z
0x180198a26  mov     rcx, rax
0x180198a29  mov     rax, [rax]
0x180198a2c  mov     [rcx], r12
0x180198a2f  mov     [rbp+180h+var_1E0], rax
0x180198a33  lea     r8, [rbp+180h+var_1E0]
0x180198a37  lea     rdx, [rbp+180h+Block]
0x180198a3b  mov     rcx, r14
0x180198a3e  call    ?ValidateDocumentAgainstSchema@glTF@Microsoft@@YAXAEBV?$GenericDocument@U?$UTF8@D@rapidjson@glTF@Microsoft@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@glTF@Microsoft@@@234@VCrtAllocator@234@@rapidjson@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$unique_ptr@$$CBVISchemaLocator@glTF@Microsoft@@U?$default_delete@$$CBVISchemaLocator@glTF@Microsoft@@@std@@@6@@Z
0x180198a43  nop
0x180198a44  mov     rcx, [rbp+180h+var_1D8]
0x180198a48  test    rcx, rcx
0x180198a4b  jz      short loc_180198A58
0x180198a4d  mov     rax, [rcx]
0x180198a50  mov     edx, 1
0x180198a55  call    qword ptr [rax]
0x180198a57  nop
0x180198a58  mov     r8d, 1000h
0x180198a5e  mov     rdx, [rbp+180h+var_190]
0x180198a62  cmp     rdx, 10h
0x180198a66  jb      short loc_180198A98
0x180198a68  inc     rdx
0x180198a6b  mov     rcx, [rbp+180h+Block]; Block
0x180198a6f  mov     rax, rcx
0x180198a72  cmp     rdx, r8
0x180198a75  jb      short loc_180198A93
0x180198a77  add     rdx, 27h ; '''
0x180198a7b  mov     rcx, [rcx-8]
0x180198a7f  sub     rax, rcx
0x180198a82  add     rax, 0FFFFFFFFFFFFFFF8h
0x180198a86  cmp     rax, 1Fh
0x180198a8a  jbe     short loc_180198A93
0x180198a8c  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180198a93  call    ??3@YAXPEAX_K@Z
0x180198a98  mov     [rbp+180h+var_198], r12
0x180198a9c  mov     [rbp+180h+var_190], 0Fh
0x180198aa4  mov     byte ptr [rbp+180h+Block], 0
0x180198aa8  mov     rcx, r15; this
0x180198aab  call    ??0Document@glTF@Microsoft@@QEAA@XZ
0x180198ab0  mov     [rsp+280h+var_240], 1
0x180198ab8  lea     r8, aAsset_0
0x180198abf  lea     rdx, [rsp+280h+var_250]
0x180198ac4  mov     rcx, r14
0x180198ac7  call    ?FindMember@?$GenericValue@U?$UTF8@D@rapidjson@glTF@Microsoft@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@glTF@Microsoft@@@234@@rapidjson@glTF@Microsoft@@QEBA?AV?$GenericMemberIterator@$00U?$UTF8@D@rapidjson@glTF@Microsoft@@V?$MemoryPoolAllocator@VCrtAllocator@rapidjson@glTF@Microsoft@@@234@@234@PEBD@Z
0x180198acc  mov     eax, [r14]
0x180198acf  shl     rax, 5
0x180198ad3  mov     rcx, [r14+8]
0x180198ad7  mov     r13, 0FFFFFFFFFFFFh
0x180198ae1  and     rcx, r13
0x180198ae4  add     rax, rcx
0x180198ae7  mov     rdx, [rsp+280h+var_250]
0x180198aec  cmp     rdx, rax
0x180198aef  jz      short loc_180198B69
0x180198af1  add     rdx, 10h
0x180198af5  mov     r8, rsi
0x180198af8  lea     rcx, [rbp+180h+var_180]
0x180198afc  call    sub_18019BE10
0x180198b01  mov     rdi, rax
0x180198b04  mov     rdx, rax
0x180198b07  lea     rcx, [r15+0A8h]
0x180198b0e  call    ??4glTFProperty@glTF@Microsoft@@IEAAAEAU012@AEBU012@@Z
0x180198b13  lea     rdx, [rdi+0A8h]
0x180198b1a  lea     rcx, [r15+150h]
0x180198b21  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198b26  lea     rdx, [rdi+0C8h]
0x180198b2d  lea     rcx, [r15+170h]
0x180198b34  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198b39  lea     rdx, [rdi+0E8h]
0x180198b40  lea     rcx, [r15+190h]
0x180198b47  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198b4c  lea     rdx, [rdi+108h]
0x180198b53  lea     rcx, [r15+1B0h]
0x180198b5a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198b5f  nop
0x180198b60  lea     rcx, [rbp+180h+var_180]; this
0x180198b64  call    ??1Asset@glTF@Microsoft@@UEAA@XZ
0x180198b69  lea     rax, sub_18019A4C0
0x180198b70  mov     [rsp+280h+var_260], rax
0x180198b75  mov     r9, rsi
0x180198b78  mov     r8, r14
0x180198b7b  lea     rdx, aAccessors
0x180198b82  lea     rcx, [rsp+280h+var_238]
0x180198b87  call    sub_180189290
0x180198b8c  mov     rbx, rax
0x180198b8f  lea     rdi, [r15+1D0h]
0x180198b96  cmp     rdi, rax
0x180198b99  jz      short loc_180198BC4
0x180198b9b  mov     rcx, rdi
0x180198b9e  call    ?_Tidy@?$vector@UAccessor@glTF@Microsoft@@V?$allocator@UAccessor@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198ba3  mov     rax, [rbx]
0x180198ba6  mov     [rdi], rax
0x180198ba9  mov     rax, [rbx+8]
0x180198bad  mov     [rdi+8], rax
0x180198bb1  mov     rax, [rbx+10h]
0x180198bb5  mov     [rdi+10h], rax
0x180198bb9  mov     [rbx], r12
0x180198bbc  mov     [rbx+8], r12
0x180198bc0  mov     [rbx+10h], r12
0x180198bc4  lea     rdx, [rbx+18h]
0x180198bc8  lea     rcx, [rdi+18h]
0x180198bcc  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198bd1  lea     rcx, [rsp+280h+var_220]
0x180198bd6  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198bdb  lea     rcx, [rsp+280h+var_238]
0x180198be0  call    ?_Tidy@?$vector@UAccessor@glTF@Microsoft@@V?$allocator@UAccessor@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198be5  lea     rax, sub_18019B060
0x180198bec  mov     [rsp+280h+var_260], rax
0x180198bf1  mov     r9, rsi
0x180198bf4  mov     r8, r14
0x180198bf7  lea     rdx, aAnimations
0x180198bfe  lea     rcx, [rsp+280h+var_238]
0x180198c03  call    sub_180189670
0x180198c08  mov     rbx, rax
0x180198c0b  lea     rdi, [r15+228h]
0x180198c12  cmp     rdi, rax
0x180198c15  jz      short loc_180198C40
0x180198c17  mov     rcx, rdi
0x180198c1a  call    ?_Tidy@?$vector@UAnimation@glTF@Microsoft@@V?$allocator@UAnimation@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198c1f  mov     rax, [rbx]
0x180198c22  mov     [rdi], rax
0x180198c25  mov     rax, [rbx+8]
0x180198c29  mov     [rdi+8], rax
0x180198c2d  mov     rax, [rbx+10h]
0x180198c31  mov     [rdi+10h], rax
0x180198c35  mov     [rbx], r12
0x180198c38  mov     [rbx+8], r12
0x180198c3c  mov     [rbx+10h], r12
0x180198c40  lea     rdx, [rbx+18h]
0x180198c44  lea     rcx, [rdi+18h]
0x180198c48  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198c4d  lea     rcx, [rsp+280h+var_220]
0x180198c52  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198c57  lea     rcx, [rsp+280h+var_238]
0x180198c5c  call    ?_Tidy@?$vector@UAnimation@glTF@Microsoft@@V?$allocator@UAnimation@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198c61  lea     rax, sub_18019C210
0x180198c68  mov     [rsp+280h+var_260], rax
0x180198c6d  mov     r9, rsi
0x180198c70  mov     r8, r14
0x180198c73  lea     rdx, aBuffers
0x180198c7a  lea     rcx, [rsp+280h+var_238]
0x180198c7f  call    sub_180189FD0
0x180198c84  mov     rbx, rax
0x180198c87  lea     rdi, [r15+280h]
0x180198c8e  cmp     rdi, rax
0x180198c91  jz      short loc_180198CBC
0x180198c93  mov     rcx, rdi
0x180198c96  call    ?_Tidy@?$vector@UBuffer@glTF@Microsoft@@V?$allocator@UBuffer@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198c9b  mov     rax, [rbx]
0x180198c9e  mov     [rdi], rax
0x180198ca1  mov     rax, [rbx+8]
0x180198ca5  mov     [rdi+8], rax
0x180198ca9  mov     rax, [rbx+10h]
0x180198cad  mov     [rdi+10h], rax
0x180198cb1  mov     [rbx], r12
0x180198cb4  mov     [rbx+8], r12
0x180198cb8  mov     [rbx+10h], r12
0x180198cbc  lea     rdx, [rbx+18h]
0x180198cc0  lea     rcx, [rdi+18h]
0x180198cc4  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198cc9  lea     rcx, [rsp+280h+var_220]
0x180198cce  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198cd3  lea     rcx, [rsp+280h+var_238]
0x180198cd8  call    ?_Tidy@?$vector@UBuffer@glTF@Microsoft@@V?$allocator@UBuffer@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198cdd  lea     rax, sub_18019C3B0
0x180198ce4  mov     [rsp+280h+var_260], rax
0x180198ce9  mov     r9, rsi
0x180198cec  mov     r8, r14
0x180198cef  lea     rdx, aBufferviews
0x180198cf6  lea     rcx, [rsp+280h+var_238]
0x180198cfb  call    sub_18018A2F0
0x180198d00  mov     rbx, rax
0x180198d03  lea     rdi, [r15+2D8h]
0x180198d0a  cmp     rdi, rax
0x180198d0d  jz      short loc_180198D38
0x180198d0f  mov     rcx, rdi
0x180198d12  call    ?_Tidy@?$vector@UBufferView@glTF@Microsoft@@V?$allocator@UBufferView@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198d17  mov     rax, [rbx]
0x180198d1a  mov     [rdi], rax
0x180198d1d  mov     rax, [rbx+8]
0x180198d21  mov     [rdi+8], rax
0x180198d25  mov     rax, [rbx+10h]
0x180198d29  mov     [rdi+10h], rax
0x180198d2d  mov     [rbx], r12
0x180198d30  mov     [rbx+8], r12
0x180198d34  mov     [rbx+10h], r12
0x180198d38  lea     rdx, [rbx+18h]
0x180198d3c  lea     rcx, [rdi+18h]
0x180198d40  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198d45  lea     rcx, [rsp+280h+var_220]
0x180198d4a  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198d4f  lea     rcx, [rsp+280h+var_238]
0x180198d54  call    ?_Tidy@?$vector@UBufferView@glTF@Microsoft@@V?$allocator@UBufferView@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198d59  lea     rax, sub_18019C700
0x180198d60  mov     [rsp+280h+var_260], rax
0x180198d65  mov     r9, rsi
0x180198d68  mov     r8, r14
0x180198d6b  lea     rdx, aCameras_0
0x180198d72  lea     rcx, [rsp+280h+var_238]
0x180198d77  call    sub_18018A640
0x180198d7c  mov     rbx, rax
0x180198d7f  lea     rdi, [r15+330h]
0x180198d86  cmp     rdi, rax
0x180198d89  jz      short loc_180198DB4
0x180198d8b  mov     rcx, rdi
0x180198d8e  call    ?_Tidy@?$vector@UCamera@glTF@Microsoft@@V?$allocator@UCamera@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198d93  mov     rax, [rbx]
0x180198d96  mov     [rdi], rax
0x180198d99  mov     rax, [rbx+8]
0x180198d9d  mov     [rdi+8], rax
0x180198da1  mov     rax, [rbx+10h]
0x180198da5  mov     [rdi+10h], rax
0x180198da9  mov     [rbx], r12
0x180198dac  mov     [rbx+8], r12
0x180198db0  mov     [rbx+10h], r12
0x180198db4  lea     rdx, [rbx+18h]
0x180198db8  lea     rcx, [rdi+18h]
0x180198dbc  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198dc1  lea     rcx, [rsp+280h+var_220]
0x180198dc6  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198dcb  lea     rcx, [rsp+280h+var_238]
0x180198dd0  call    ?_Tidy@?$vector@UCamera@glTF@Microsoft@@V?$allocator@UCamera@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198dd5  lea     rax, sub_18019D2F0
0x180198ddc  mov     [rsp+280h+var_260], rax
0x180198de1  mov     r9, rsi
0x180198de4  mov     r8, r14
0x180198de7  lea     rdx, aImages
0x180198dee  lea     rcx, [rsp+280h+var_238]
0x180198df3  call    sub_18018A770
0x180198df8  mov     rbx, rax
0x180198dfb  lea     rdi, [r15+388h]
0x180198e02  cmp     rdi, rax
0x180198e05  jz      short loc_180198E30
0x180198e07  mov     rcx, rdi
0x180198e0a  call    ?_Tidy@?$vector@UImage@glTF@Microsoft@@V?$allocator@UImage@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198e0f  mov     rax, [rbx]
0x180198e12  mov     [rdi], rax
0x180198e15  mov     rax, [rbx+8]
0x180198e19  mov     [rdi+8], rax
0x180198e1d  mov     rax, [rbx+10h]
0x180198e21  mov     [rdi+10h], rax
0x180198e25  mov     [rbx], r12
0x180198e28  mov     [rbx+8], r12
0x180198e2c  mov     [rbx+10h], r12
0x180198e30  lea     rdx, [rbx+18h]
0x180198e34  lea     rcx, [rdi+18h]
0x180198e38  call    ??4?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z
0x180198e3d  lea     rcx, [rsp+280h+var_220]
0x180198e42  call    ??1?$unordered_set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@XZ
0x180198e47  lea     rcx, [rsp+280h+var_238]
0x180198e4c  call    ?_Tidy@?$vector@UImage@glTF@Microsoft@@V?$allocator@UImage@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198e51  lea     rax, sub_18019D6E0
0x180198e58  mov     [rsp+280h+var_260], rax
0x180198e5d  mov     r9, rsi
0x180198e60  mov     r8, r14
0x180198e63  lea     rdx, aMaterials
0x180198e6a  lea     rcx, [rsp+280h+var_238]
0x180198e6f  call    sub_18018AB30
0x180198e74  mov     rbx, rax
0x180198e77  lea     rdi, [r15+3E0h]
0x180198e7e  cmp     rdi, rax
0x180198e81  jz      short loc_180198EAC
0x180198e83  mov     rcx, rdi
0x180198e86  call    ?_Tidy@?$vector@UMaterial@glTF@Microsoft@@V?$allocator@UMaterial@glTF@Microsoft@@@std@@@std@@AEAAXXZ
0x180198e8b  mov     rax, [rbx]
0x180198e8e  mov     [rdi], rax
0x180198e91  mov     rax, [rbx+8]
  ... truncated ...
```

# Spectre::Transcoder::Asset3DToGLTFConverter::PopulateDocument(Spectre::Transcoder::IGLTFWriter &)

- ea: `0x180380360`
- end: `0x180380add`
- name: `?PopulateDocument@Asset3DToGLTFConverter@Transcoder@Spectre@@AEAAXAEAUIGLTFWriter@23@@Z`
- size: `1917`
- prototype: `void __fastcall(Spectre::Transcoder::Asset3DToGLTFConverter *__hidden this, struct Spectre::Transcoder::IGLTFWriter *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180381060`

## callees

- `0x180015770`
- `0x1800157b0`
- `0x180016430`
- `0x180021570`
- `0x180029b60`
- `0x18002b7a0`
- `0x18002bc30`
- `0x18002e6b0`
- `0x18002f250`
- `0x18002f3c0`
- `0x18002f6b0`
- `0x18003eb90`
- `0x180191970`
- `0x180196e00`
- `0x1801a2500`
- `0x1801b7350`
- `0x1801f0af0`
- `0x1801f5240`
- `0x1801f7330`
- `0x1802b5930`
- `0x180372bd0`
- `0x180374e90`
- `0x180375090`
- `0x180376660`
- `0x180378030`
- `0x180379a20`
- `0x18037c8b0`
- `0x180380360`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803804f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803806c4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18038097f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803809f5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803804f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803806c4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18038097f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1803809f5`

## string_xrefs

- `0x180380495`: `glTF::Extensions_root`
- `0x180380668`: `glTF::Extensions_scene_default`
- `0x180380aa5`: ` already exists in IndexedContainer`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall Spectre::Transcoder::Asset3DToGLTFConverter::PopulateDocument(
        Spectre::Transcoder::Asset3DToGLTFConverter *this,
        struct Spectre::Transcoder::IGLTFWriter *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  void *v6; // rcx
  unsigned int v7; // r8d
  _BYTE *v8; // r9
  void *v9; // rcx
  void *v10; // rcx
  __int64 v11; // rdi
  _QWORD *v12; // rsi
  _QWORD *v13; // rbx
  _DWORD *v14; // xmm6_8
  __int128 v15; // xmm7
  __int128 v16; // xmm8
  const struct Node *v17; // r12
  const struct Node *i; // rbx
  _QWORD *v19; // rdi
  bool v20; // si
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  _BYTE *v24; // rcx
  __int64 (__fastcall *v25)(struct Spectre::Transcoder::IGLTFWriter *); // rax
  struct Microsoft::glTF::BufferBuilder *v26; // rax
  struct Microsoft::glTF::BufferBuilder *v27; // rax
  _BYTE *v28; // rcx
  __int64 v29; // rax
  _QWORD *v30; // rax
  void *Block[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v33; // [rsp+50h] [rbp-B8h]
  __int64 j; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+78h] [rbp-90h]
  _DWORD *v37; // [rsp+88h] [rbp-80h]
  _DWORD v38[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v39[2]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE *v40; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v41; // [rsp+B8h] [rbp-50h]
  __int64 v42; // [rsp+C8h] [rbp-40h]
  __int64 v43; // [rsp+D0h] [rbp-38h]
  _DWORD v44[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD *v45; // [rsp+E0h] [rbp-28h]
  __int64 v46; // [rsp+E8h] [rbp-20h]
  __int64 v47; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v48; // [rsp+F8h] [rbp-10h]
  __int128 v49; // [rsp+108h] [rbp+0h]
  void **v50; // [rsp+118h] [rbp+10h] BYREF
  char v51[64]; // [rsp+120h] [rbp+18h] BYREF
  __int64 v52; // [rsp+160h] [rbp+58h]
  __int64 v53; // [rsp+170h] [rbp+68h]
  __int64 v54; // [rsp+178h] [rbp+70h]
  char v55[64]; // [rsp+180h] [rbp+78h] BYREF
  _QWORD v56[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v57; // [rsp+200h] [rbp+F8h] BYREF
  __int128 v58; // [rsp+208h] [rbp+100h]
  _BYTE *v59; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int64 v60; // [rsp+230h] [rbp+128h]
  _BYTE v61[168]; // [rsp+238h] [rbp+130h] BYREF
  _QWORD Src[2]; // [rsp+2E0h] [rbp+1D8h] BYREF
  __int64 v63; // [rsp+2F0h] [rbp+1E8h]
  unsigned __int64 v64; // [rsp+2F8h] [rbp+1F0h]
  _BYTE pExceptionObject[21]; // [rsp+418h] [rbp+310h] BYREF
  _BYTE v66[3]; // [rsp+42Dh] [rbp+325h] BYREF

  v49 = 0;
  v44[1] = 0;
  v46 = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  v45 = v4;
  v47 = 0;
  v48 = 0;
  *(_QWORD *)&v49 = 7;
  *((_QWORD *)&v49 + 1) = 8;
  v44[0] = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(
    &v47,
    16,
    v4);
  v38[1] = 0;
  v39[1] = 0;
  v5 = operator new(0x210u);
  *v5 = v5;
  v5[1] = v5;
  v39[0] = v5;
  v40 = 0;
  v41 = 0;
  v42 = 7;
  v43 = 8;
  v38[0] = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(
    &v40,
    16,
    v5);
  Block[0] = 0;
  v32 = 0;
  v33 = 15;
  std::string::assign(Block);
  sub_18037C8B0(*(_QWORD *)this, *((_QWORD *)this + 11), *((_QWORD *)this + 11), Block);
  if ( v33 >= 0x10 )
  {
    v6 = Block[0];
    if ( v33 + 1 >= 0x1000 )
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v6);
  }
  v50 = (void **)&Microsoft::glTF::glTFProperty::`vftable';
  std::unordered_map<std::string,std::string>::unordered_map<std::string,std::string>(v51);
  v52 = 0;
  v53 = 0;
  v54 = 15;
  std::unordered_map<std::type_index,std::unique_ptr<Microsoft::glTF::Extension>>::unordered_map<std::type_index,std::unique_ptr<Microsoft::glTF::Extension>>(v55);
  v56[0] = 0;
  v56[2] = 0;
  v56[3] = 15;
  v56[4] = 0;
  v56[6] = 0;
  v56[7] = 15;
  v50 = &Microsoft::glTF::Scene::`vftable';
  v57 = 0;
  v58 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)this + 8LL);
  v8 = v66;
  do
  {
    *--v8 = v7 % 0xA + 48;
    v7 /= 0xAu;
  }
  while ( v7 );
  Block[0] = 0;
  v32 = 0;
  v33 = 15;
  if ( v8 != v66 )
    std::string::assign(Block);
  std::string::operator=(v56, Block);
  if ( v33 >= 0x10 )
  {
    v9 = Block[0];
    if ( v33 + 1 >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
LABEL_17:
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v9);
  }
  Block[0] = 0;
  v32 = 0;
  v33 = 15;
  std::string::assign(Block);
  sub_18037C8B0(*(_QWORD *)this, *((_QWORD *)this + 11), &v50, Block);
  if ( v33 >= 0x10 )
  {
    v10 = Block[0];
    if ( v33 + 1 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        goto LABEL_17;
    }
    operator delete(v10);
  }
  *(_QWORD *)&v35 = this;
  *((_QWORD *)&v35 + 1) = &v50;
  *(_QWORD *)&v36 = v38;
  *((_QWORD *)&v36 + 1) = a2;
  v37 = v44;
  v11 = *(_QWORD *)this;
  sub_180375090(&v35, *(_QWORD *)this, 0);
  v12 = *(_QWORD **)(v11 + 200);
  v13 = *(_QWORD **)(v11 + 192);
  if ( v13 != v12 )
  {
    v14 = v37;
    v15 = v36;
    v16 = v35;
    do
    {
      v35 = v16;
      v36 = v15;
      v37 = v14;
      sub_180372BD0(*v13, &v35, v11);
      v13 += 2;
    }
    while ( v13 != v12 );
  }
  v17 = (const struct Node *)v39[0];
  for ( i = *(const struct Node **)v39[0]; i != v17; i = (const struct Node *)i->lpVtbl )
  {
    std::string::string(&v59, &i[2]);
    Microsoft::glTF::Node::Node((Microsoft::glTF::Node *)v61, i + 6);
    v19 = (_QWORD *)(*((_QWORD *)this + 11) + 1168LL);
    v20 = v63 == 0;
    if ( !v63 )
    {
      std::string::string(&v35, "key is an empty string");
      Microsoft::glTF::GLTFException::GLTFException((__int64)Block, &v35);
      throw (Microsoft::glTF::GLTFException *)Block;
    }
    for ( j = (*(_QWORD *)(*((_QWORD *)this + 11) + 1176LL) - *(_QWORD *)(*((_QWORD *)this + 11) + 1168LL)) / 480LL;
          !*(_BYTE *)(std::_Hash<std::_Umap_traits<std::string,unsigned __int64,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned __int64>>,0>>::emplace<std::string &,unsigned __int64>(
                        v19 + 3,
                        pExceptionObject,
                        Src,
                        &j)
                    + 8);
          j = (v19[1] - *v19) / 480LL )
    {
      if ( !v20 )
      {
        v29 = std::operator+<char>(&v35);
        v30 = (_QWORD *)std::operator+<char>(Block, v29, " already exists in IndexedContainer");
        Microsoft::glTF::GLTFException::GLTFException((__int64)pExceptionObject, v30);
        throw (Microsoft::glTF::GLTFException *)pExceptionObject;
      }
      v21 = v63;
      if ( v64 == v63 )
      {
        std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(
          Src,
          1u);
      }
      else
      {
        ++v63;
        v22 = Src;
        if ( v64 >= 0x10 )
          v22 = (_QWORD *)Src[0];
        *(_WORD *)((char *)v22 + v21) = 43;
      }
    }
    v23 = v19[1];
    if ( v23 == v19[2] )
    {
      std::vector<Microsoft::glTF::Node>::_Emplace_reallocate<Microsoft::glTF::Node>(v19, v23, v61);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<Microsoft::glTF::Node>>::construct<Microsoft::glTF::Node,Microsoft::glTF::Node>(
        v19,
        v23,
        v61);
      v19[1] += 480LL;
    }
    Microsoft::glTF::Node::~Node((Microsoft::glTF::Node *)v61);
    if ( v60 >= 0x10 )
    {
      v24 = v59;
      if ( v60 + 1 >= 0x1000 )
      {
        v24 = (_BYTE *)*((_QWORD *)v59 - 1);
        if ( (unsigned __int64)(v59 - v24 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v24);
    }
  }
  Microsoft::glTF::Document::SetDefaultScene(*((_QWORD *)this + 11), &v50, 0);
  v25 = *(__int64 (__fastcall **)(struct Spectre::Transcoder::IGLTFWriter *))(*(_QWORD *)a2 + 24LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 408LL) )
  {
    v27 = (struct Microsoft::glTF::BufferBuilder *)v25(a2);
    Spectre::Transcoder::Asset3DToGLTFConverter::AddGLTFChannelAnimations(this, v27);
  }
  else
  {
    v26 = (struct Microsoft::glTF::BufferBuilder *)v25(a2);
    Spectre::Transcoder::Asset3DToGLTFConverter::AddAnimationsAndSkeletons(this, v26);
  }
  Spectre::Transcoder::Asset3DToGLTFConverter::AddMaterials((__int64)this, (__int64)a2, (__int64)v44);
  std::vector<std::string>::_Tidy(&v57);
  Microsoft::glTF::glTFChildOfRootProperty::~glTFChildOfRootProperty((Microsoft::glTF::glTFChildOfRootProperty *)&v50);
  v28 = v40;
  if ( (unsigned __int64)(8 * ((__int64)(v41 - (_QWORD)v40) >> 3)) >= 0x1000 )
  {
    v28 = (_BYTE *)*((_QWORD *)v40 - 1);
    if ( (unsigned __int64)(v40 - v28 - 8) > 0x1F )
      _invalid_parameter_noinfo_noreturn();
  }
  operator delete(v28);
  v40 = 0;
  v41 = 0;
  std::list<std::pair<std::string const,Microsoft::glTF::Node>>::~list<std::pair<std::string const,Microsoft::glTF::Node>>(v39);
  std::_Hash<std::_Umap_traits<unsigned int,Spectre::Transcoder::MaterialDescriptor *,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Spectre::Transcoder::MaterialDescriptor *>>,0>>::~_Hash<std::_Umap_traits<unsigned int,Spectre::Transcoder::MaterialDescriptor *,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Spectre::Transcoder::MaterialDescriptor *>>,0>>(v44);
}

```

## disassembly

```asm
0x180380360  mov     rax, rsp
0x180380363  mov     [rax+18h], rbx
0x180380367  push    rbp
0x180380368  push    rsi
0x180380369  push    rdi
0x18038036a  push    r12
0x18038036c  push    r13
0x18038036e  push    r14
0x180380370  push    r15
0x180380372  lea     rbp, [rax-398h]
0x180380379  sub     rsp, 460h
0x180380380  movaps  xmmword ptr [rax-48h], xmm6
0x180380384  movaps  xmmword ptr [rax-58h], xmm7
0x180380388  movaps  xmmword ptr [rax-68h], xmm8
0x18038038d  mov     rax, cs:__security_cookie
0x180380394  xor     rax, rsp
0x180380397  mov     [rbp+390h+var_68], rax
0x18038039e  mov     r13, rdx
0x1803803a1  mov     r15, rcx
0x1803803a4  xorps   xmm0, xmm0
0x1803803a7  movups  [rbp+390h+var_3C0], xmm0
0x1803803ab  movups  [rbp+390h+var_3B0], xmm0
0x1803803af  movups  [rbp+390h+var_3A0], xmm0
0x1803803b3  movups  [rbp+390h+var_390], xmm0
0x1803803b7  mov     dword ptr [rbp+390h+var_3C0], 0
0x1803803be  xor     r14d, r14d
0x1803803c1  mov     qword ptr [rbp+390h+var_3C0+8], r14
0x1803803c5  mov     qword ptr [rbp+390h+var_3B0], r14
0x1803803c9  lea     ecx, [r14+20h]; Size
0x1803803cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1803803d2  mov     [rax], rax
0x1803803d5  mov     [rax+8], rax
0x1803803d9  mov     qword ptr [rbp+390h+var_3C0+8], rax
0x1803803dd  mov     qword ptr [rbp+390h+var_3B0+8], r14
0x1803803e1  xorps   xmm0, xmm0
0x1803803e4  movdqa  [rbp+390h+var_3A0], xmm0
0x1803803e9  mov     qword ptr [rbp+390h+var_390], 7
0x1803803f1  mov     qword ptr [rbp+390h+var_390+8], 8
0x1803803f9  mov     dword ptr [rbp+390h+var_3C0], 3F800000h
0x180380400  mov     r8, rax
0x180380403  lea     edx, [r14+10h]
0x180380407  lea     rcx, [rbp+390h+var_3B0+8]
0x18038040b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>)
0x180380410  nop
0x180380411  xorps   xmm0, xmm0
0x180380414  movups  [rbp+390h+var_400], xmm0
0x180380418  movups  xmmword ptr [rbp+390h+var_3F0], xmm0
0x18038041c  movups  [rbp+390h+var_3E0], xmm0
0x180380420  movups  [rbp+390h+var_3D0], xmm0
0x180380424  mov     dword ptr [rbp+390h+var_400], r14d
0x180380428  mov     qword ptr [rbp+390h+var_400+8], r14
0x18038042c  mov     [rbp+390h+var_3F0], r14
0x180380430  mov     ecx, 210h; Size
0x180380435  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18038043a  mov     [rax], rax
0x18038043d  mov     [rax+8], rax
0x180380441  mov     qword ptr [rbp+390h+var_400+8], rax
0x180380445  mov     [rbp+390h+var_3F0+8], r14
0x180380449  xorps   xmm0, xmm0
0x18038044c  movdqa  [rbp+390h+var_3E0], xmm0
0x180380451  mov     qword ptr [rbp+390h+var_3D0], 7
0x180380459  mov     qword ptr [rbp+390h+var_3D0+8], 8
0x180380461  mov     dword ptr [rbp+390h+var_400], 3F800000h
0x180380468  mov     r8, rax
0x18038046b  lea     edx, [r14+10h]
0x18038046f  lea     rcx, [rbp+390h+var_3F0+8]
0x180380473  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$shared_ptr@$$CBVMaterial@Engine@Spectre@@@std@@UWriterMapInfo@Impl@GLTFSerializerWriterBase@Engine@Spectre@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::shared_ptr<Spectre::Engine::Material const> const,Spectre::Engine::GLTFSerializerWriterBase::Impl::WriterMapInfo>>>>)
0x180380478  nop
0x180380479  mov     [rsp+490h+Block], r14
0x18038047e  mov     [rsp+490h+var_450], r14
0x180380483  mov     [rsp+490h+var_448], 0Fh
0x18038048c  mov     byte ptr [rsp+490h+Block], r14b
0x180380491  lea     r8d, [r14+15h]
0x180380495  lea     rdx, aGltfExtensions; "glTF::Extensions_root"
0x18038049c  lea     rcx, [rsp+490h+Block]; void *
0x1803804a1  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1803804a6  nop
0x1803804a7  mov     rdx, [r15+58h]
0x1803804ab  lea     r9, [rsp+490h+Block]
0x1803804b0  mov     r8, rdx
0x1803804b3  mov     rcx, [r15]
0x1803804b6  call    sub_18037C8B0
0x1803804bb  nop
0x1803804bc  mov     rdx, [rsp+490h+var_448]
0x1803804c1  cmp     rdx, 10h
0x1803804c5  jb      short loc_1803804FC
0x1803804c7  inc     rdx
0x1803804ca  mov     rcx, [rsp+490h+Block]; Block
0x1803804cf  mov     rax, rcx
0x1803804d2  cmp     rdx, 1000h
0x1803804d9  jb      short loc_1803804F7
0x1803804db  add     rdx, 27h ; '''
0x1803804df  mov     rcx, [rcx-8]
0x1803804e3  sub     rax, rcx
0x1803804e6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1803804ea  cmp     rax, 1Fh
0x1803804ee  jbe     short loc_1803804F7
0x1803804f0  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1803804f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1803804fc  lea     rax, ??_7glTFProperty@glTF@Microsoft@@6B@; const Microsoft::glTF::glTFProperty::`vftable'
0x180380503  mov     [rbp+390h+var_380], rax
0x180380507  lea     rcx, [rbp+390h+var_378]
0x18038050b  call    ??0?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::string,std::string>::unordered_map<std::string,std::string>(void)
0x180380510  nop
0x180380511  mov     [rbp+390h+var_338], r14
0x180380515  mov     [rbp+390h+var_328], r14
0x180380519  mov     [rbp+390h+var_320], 0Fh
0x180380521  mov     byte ptr [rbp+390h+var_338], 0
0x180380525  lea     rcx, [rbp+390h+var_318]
0x180380529  call    ??0?$unordered_map@Vtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@U?$hash@Vtype_index@std@@@2@U?$equal_to@Vtype_index@std@@@2@V?$allocator@U?$pair@$$CBVtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::type_index,std::unique_ptr<Microsoft::glTF::Extension>>::unordered_map<std::type_index,std::unique_ptr<Microsoft::glTF::Extension>>(void)
0x18038052e  nop
0x18038052f  mov     [rbp+390h+var_2D8], r14
0x180380536  mov     [rbp+390h+var_2C8], r14
0x18038053d  mov     [rbp+390h+var_2C0], 0Fh
0x180380548  mov     byte ptr [rbp+390h+var_2D8], 0
0x18038054f  mov     [rbp+390h+var_2B8], r14
0x180380556  mov     [rbp+390h+var_2A8], r14
0x18038055d  mov     [rbp+390h+var_2A0], 0Fh
0x180380568  mov     byte ptr [rbp+390h+var_2B8], 0
0x18038056f  lea     rax, ??_7Scene@glTF@Microsoft@@6B@; const Microsoft::glTF::Scene::`vftable'
0x180380576  mov     [rbp+390h+var_380], rax
0x18038057a  mov     [rbp+390h+var_298], r14
0x180380581  xorps   xmm0, xmm0
0x180380584  movdqa  [rbp+390h+var_290], xmm0
0x18038058c  mov     rax, [r15]
0x18038058f  mov     r8d, [rax+8]
0x180380593  lea     r9, [rbp+390h+var_6B]
0x18038059a  nop     word ptr [rax+rax+00h]
0x1803805a0  dec     r9
0x1803805a3  mov     eax, 0CCCCCCCDh
0x1803805a8  mul     r8d
0x1803805ab  shr     edx, 3
0x1803805ae  movzx   eax, dl
0x1803805b1  shl     al, 2
0x1803805b4  lea     ecx, [rax+rdx]
0x1803805b7  add     cl, cl
0x1803805b9  sub     r8b, cl
0x1803805bc  add     r8b, 30h ; '0'
0x1803805c0  mov     [r9], r8b
0x1803805c3  mov     r8d, edx
0x1803805c6  test    edx, edx
0x1803805c8  jnz     short loc_1803805A0
0x1803805ca  mov     [rsp+490h+Block], r14
0x1803805cf  mov     [rsp+490h+var_450], r14
0x1803805d4  mov     [rsp+490h+var_448], 0Fh
0x1803805dd  lea     rax, [rbp+390h+var_6B]
0x1803805e4  cmp     r9, rax
0x1803805e7  jz      short loc_180380600
0x1803805e9  lea     r8, [rbp+390h+var_6B]
0x1803805f0  sub     r8, r9
0x1803805f3  mov     rdx, r9
0x1803805f6  lea     rcx, [rsp+490h+Block]; void *
0x1803805fb  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180380600  lea     rdx, [rsp+490h+Block]
0x180380605  lea     rcx, [rbp+390h+var_2D8]
0x18038060c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180380611  mov     rdx, [rsp+490h+var_448]
0x180380616  cmp     rdx, 10h
0x18038061a  jb      short loc_18038064A
0x18038061c  inc     rdx
0x18038061f  mov     rcx, [rsp+490h+Block]
0x180380624  mov     rax, rcx
0x180380627  cmp     rdx, 1000h
0x18038062e  jb      short loc_180380645
0x180380630  add     rdx, 27h ; '''
0x180380634  mov     rcx, [rcx-8]; Block
0x180380638  sub     rax, rcx
0x18038063b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18038063f  cmp     rax, 1Fh
0x180380643  ja      short loc_1803806C4
0x180380645  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18038064a  mov     [rsp+490h+Block], r14
0x18038064f  mov     [rsp+490h+var_450], r14
0x180380654  mov     [rsp+490h+var_448], 0Fh
0x18038065d  mov     byte ptr [rsp+490h+Block], 0
0x180380662  mov     r8d, 1Eh
0x180380668  lea     rdx, aGltfExtensions_0; "glTF::Extensions_scene_default"
0x18038066f  lea     rcx, [rsp+490h+Block]; void *
0x180380674  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180380679  nop
0x18038067a  lea     r9, [rsp+490h+Block]
0x18038067f  lea     r8, [rbp+390h+var_380]
0x180380683  mov     rdx, [r15+58h]
0x180380687  mov     rcx, [r15]
0x18038068a  call    sub_18037C8B0
0x18038068f  nop
0x180380690  mov     rdx, [rsp+490h+var_448]
0x180380695  cmp     rdx, 10h
0x180380699  jb      short loc_1803806D0
0x18038069b  inc     rdx
0x18038069e  mov     rcx, [rsp+490h+Block]; Block
0x1803806a3  mov     rax, rcx
0x1803806a6  cmp     rdx, 1000h
0x1803806ad  jb      short loc_1803806CB
0x1803806af  add     rdx, 27h ; '''
0x1803806b3  mov     rcx, [rcx-8]
0x1803806b7  sub     rax, rcx
0x1803806ba  add     rax, 0FFFFFFFFFFFFFFF8h
0x1803806be  cmp     rax, 1Fh
0x1803806c2  jbe     short loc_1803806CB
0x1803806c4  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1803806cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1803806d0  mov     qword ptr [rsp+490h+var_438+8], r15
0x1803806d5  lea     rax, [rbp+390h+var_380]
0x1803806d9  mov     qword ptr [rsp+490h+var_428], rax
0x1803806de  lea     rax, [rbp+390h+var_400]
0x1803806e2  mov     qword ptr [rsp+490h+var_428+8], rax
0x1803806e7  mov     [rsp+490h+var_418], r13
0x1803806ec  lea     rax, [rbp+390h+var_3C0]
0x1803806f0  mov     [rbp+390h+var_410], rax
0x1803806f4  mov     rdi, [r15]
0x1803806f7  xor     r8d, r8d
0x1803806fa  mov     rdx, rdi
0x1803806fd  lea     rcx, [rsp+490h+var_438+8]
0x180380702  call    sub_180375090
0x180380707  mov     rsi, [rdi+0C8h]
0x18038070e  mov     rbx, [rdi+0C0h]
0x180380715  cmp     rbx, rsi
0x180380718  jz      short loc_180380759
0x18038071a  movsd   xmm6, [rbp+390h+var_410]
0x18038071f  movaps  xmm7, [rsp+490h+var_428+8]
0x180380724  movaps  xmm8, [rsp+490h+var_438+8]
0x18038072a  nop     word ptr [rax+rax+00h]
0x180380730  movaps  [rsp+490h+var_438+8], xmm8
0x180380736  movaps  [rsp+490h+var_428+8], xmm7
0x18038073b  movsd   [rbp+390h+var_410], xmm6
0x180380740  mov     r8, rdi
0x180380743  lea     rdx, [rsp+490h+var_438+8]
0x180380748  mov     rcx, [rbx]
0x18038074b  call    sub_180372BD0
0x180380750  add     rbx, 10h
0x180380754  cmp     rbx, rsi
0x180380757  jnz     short loc_180380730
0x180380759  mov     r12, qword ptr [rbp+390h+var_400+8]
0x18038075d  mov     rbx, [r12]
0x180380761  cmp     rbx, r12
0x180380764  jz      loc_180380941
0x18038076a  mov     r14, 8888888888888889h
0x180380774  lea     rdx, [rbx+10h]
0x180380778  lea     rcx, [rbp+390h+var_280]
0x18038077f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180380784  nop
0x180380785  lea     rdx, [rbx+30h]; struct Node *
0x180380789  lea     rcx, [rbp+390h+var_260]; this
0x180380790  call    ??0Node@glTF@Microsoft@@QEAA@AEBU012@@Z; Microsoft::glTF::Node::Node(Microsoft::glTF::Node const &)
0x180380795  nop
0x180380796  mov     rdi, [r15+58h]
0x18038079a  add     rdi, 490h
0x1803807a1  mov     rax, [rbp+390h+var_1A8]
0x1803807a8  test    rax, rax
0x1803807ab  setz    sil
0x1803807af  test    rax, rax
0x1803807b2  jz      loc_180380A59
0x1803807b8  mov     rcx, [rdi+8]
0x1803807bc  sub     rcx, [rdi]
0x1803807bf  mov     rax, r14
0x1803807c2  imul    rcx
0x1803807c5  add     rdx, rcx
0x1803807c8  sar     rdx, 8
0x1803807cc  mov     rax, rdx
0x1803807cf  shr     rax, 3Fh
0x1803807d3  add     rdx, rax
0x1803807d6  mov     [rsp+490h+var_440], rdx
0x1803807db  lea     r9, [rsp+490h+var_440]
0x1803807e0  lea     r8, [rbp+390h+Src]
0x1803807e7  lea     rdx, [rbp+390h+pExceptionObject]
0x1803807ee  lea     rcx, [rdi+18h]
0x1803807f2  call    ??$emplace@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEA_K@Z; std::_Hash<std::_Umap_traits<std::string,unsigned __int64,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned __int64>>,0>>::emplace<std::string &,unsigned __int64>(std::string &,unsigned __int64 &&)
0x1803807f7  cmp     byte ptr [rax+8], 0
0x1803807fb  jnz     loc_1803808BD
0x180380801  test    sil, sil
0x180380804  jz      loc_180380A8C
0x18038080a  mov     rcx, [rbp+390h+var_1A8]
0x180380811  mov     rdx, [rbp+390h+var_1A0]
0x180380818  mov     rax, rdx
0x18038081b  sub     rax, rcx
0x18038081e  cmp     rax, 1
0x180380822  jb      short loc_18038084A
0x180380824  lea     rax, [rcx+1]
0x180380828  mov     [rbp+390h+var_1A8], rax
0x18038082f  lea     rax, [rbp+390h+Src]
0x180380836  cmp     rdx, 10h
0x18038083a  cmovnb  rax, [rbp+390h+Src]
0x180380842  mov     word ptr [rax+rcx], 2Bh ; '+'
0x180380848  jmp     short loc_18038086D
0x18038084a  mov     [rsp+490h+Size], 1; Size
0x180380853  lea     r9, asc_1806B0A30; "+"
0x18038085a  xor     r8d, r8d
0x18038085d  lea     edx, [r8+1]
0x180380861  lea     rcx, [rbp+390h+Src]; Src
0x180380868  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x18038086d  mov     rcx, [rdi+8]
0x180380871  sub     rcx, [rdi]
0x180380874  mov     rax, 8888888888888889h
0x18038087e  imul    rcx
0x180380881  add     rdx, rcx
0x180380884  sar     rdx, 8
0x180380888  mov     rax, rdx
0x18038088b  shr     rax, 3Fh
0x18038088f  add     rdx, rax
  ... truncated ...
```

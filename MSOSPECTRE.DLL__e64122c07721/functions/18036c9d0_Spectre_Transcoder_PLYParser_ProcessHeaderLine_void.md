# Spectre::Transcoder::PLYParser::ProcessHeaderLine(void)

- ea: `0x18036c9d0`
- end: `0x18036d078`
- name: `?ProcessHeaderLine@PLYParser@Transcoder@Spectre@@AEAA_NXZ`
- size: `1704`
- prototype: `char __fastcall(Spectre::Transcoder::PLYParser *this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18036ba70`

## callees

- `0x180015770`
- `0x1800157b0`
- `0x180016430`
- `0x1801cc6d0`
- `0x1801cd2a0`
- `0x1801cd320`
- `0x180288bc0`
- `0x18029f2f0`
- `0x1803531a0`
- `0x1803677d0`
- `0x180367fb0`
- `0x180368300`
- `0x1803684f0`
- `0x18036c9d0`
- `0x18036d170`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039ebc0`
- `0x18039f8e0`
- `0x18039f910`
- `0x18039f920`
- `0x180490890`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036cd48`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036cd48`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18036ccc8`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18036ccc8`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18036ccab`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18036cd39`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18036ccab`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18036cd39`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cbcf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cfef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cff6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cbcf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cfef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036cff6`

## string_xrefs

- `0x18036d044`: `Failed to read the entire stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Spectre::Transcoder::PLYParser::ProcessHeaderLine(Spectre::Transcoder::PLYParser *this)
{
  __int64 v2; // rsi
  _DWORD *v3; // rdi
  __int64 v5; // rcx
  void **v6; // r9
  void *v7; // rcx
  _QWORD *v8; // rdi
  const void *v9; // rcx
  const char *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 *v13; // rax
  __int64 *v14; // rcx
  unsigned __int64 v15; // r14
  void *v16; // rax
  void *v17; // rbx
  _DWORD *v18; // rax
  _DWORD *v19; // rbx
  _DWORD *v20; // r13
  __int64 v21; // rsi
  void **v22; // r14
  unsigned __int64 v23; // rdx
  _QWORD *v24; // rcx
  unsigned __int64 v25; // rdx
  void *v26; // rcx
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rsi
  volatile signed __int32 *v29; // rsi
  volatile signed __int32 *v30; // rbx
  _DWORD *v31; // [rsp+48h] [rbp-C0h] BYREF
  __m256i v32; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v33[16]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v34; // [rsp+80h] [rbp-88h]
  char v35[24]; // [rsp+90h] [rbp-78h] BYREF
  void *Block; // [rsp+A8h] [rbp-60h] BYREF
  void *pExceptionObject[2]; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-40h]
  int v39; // [rsp+D8h] [rbp-30h]
  __int64 v40; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-20h]
  _QWORD v42[3]; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int64 v43; // [rsp+110h] [rbp+8h]
  _DWORD *v44; // [rsp+118h] [rbp+10h]
  _DWORD *v45; // [rsp+120h] [rbp+18h]
  __int128 v46; // [rsp+128h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this + 12);
  if ( (unsigned __int64)(*((_QWORD *)this + 13) - v2) < 0x20 )
    return 0;
  std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(
    &Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator,
    v33,
    *((_QWORD *)this + 12));
  v3 = (_DWORD *)v34;
  if ( *(_BYTE *)(v34 + 25)
    || (unsigned __int8)std::less<std::string>::operator()(
                          &Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator,
                          v2,
                          v34 + 32)
    || v3 == Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator )
  {
    return 0;
  }
  switch ( v3[16] )
  {
    case 2:
      Spectre::Transcoder::PLYParser::AddFileType(this, (char *)this + 96);
      return 0;
    case 3:
      v8 = (_QWORD *)*((_QWORD *)this + 12);
      if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 13) - (_QWORD)v8) >> 5) < 3 )
        return 0;
      v9 = v8 + 4;
      if ( v8[7] >= 0x10u )
        v9 = (const void *)v8[4];
      if ( v8[6] != 11 || memcmp_0(v9, "TextureFile", 0xBu) )
        return 0;
      std::string::string(v42, v8 + 8);
      v10 = (const char *)v42;
      if ( v43 >= 0x10 )
        v10 = (const char *)v42[0];
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsPLYParser, 3, "Texture Reference: %s", v10);
      if ( !v42[2] )
        goto LABEL_75;
      v11 = *((_QWORD *)this + 2);
      if ( !v11 )
        goto LABEL_75;
      v46 = 0;
      (*(void (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)v11 + 8LL))(v11, &v46, v42);
      v12 = v46;
      if ( !(_QWORD)v46 )
      {
LABEL_71:
        v30 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
        if ( *((_QWORD *)&v46 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
LABEL_75:
        if ( v43 < 0x10 )
          return 0;
        v7 = (void *)v42[0];
        if ( v43 + 1 >= 0x1000 )
        {
          v7 = *(void **)(v42[0] - 8LL);
          if ( (unsigned __int64)(v42[0] - (_QWORD)v7 - 8LL) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
LABEL_80:
        operator delete(v7);
        return 0;
      }
      Block = 0;
      std::istream::seekg(v46, 0, 2);
      memset(&v32.m256i_u64[1], 0, 24);
      v13 = (__int64 *)std::istream::tellg(v12, v35);
      v14 = &v32.m256i_i64[1];
      if ( *v13 + v13[1] >= _mm_srli_si128((__m128i)0LL, 8).m128i_i64[0] )
        v14 = v13;
      v15 = *v14 + v14[1];
      v16 = operator new[](v15);
      v17 = v16;
      if ( v16 )
        memset_0(v16, 0, v15);
      else
        v17 = 0;
      std::istream::seekg(v12, 0, 0);
      std::istream::read(v12, v17, v15);
      if ( *(_QWORD *)(v12 + 8) != v15 )
      {
        std::string::string(v33, "Failed to read the entire stream");
        Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v33, 0);
        throw (Spectre::Utils::SpectreException *)pExceptionObject;
      }
      Block = v17;
      v18 = operator new(0x98u);
      v19 = v18;
      v31 = v18;
      if ( v18 )
      {
        *(_OWORD *)v18 = 0;
        v18[2] = 1;
        v18[3] = 1;
        *(_QWORD *)v18 = &std::_Ref_count_obj2<Spectre::Transcoder::TextureDescriptor>::`vftable';
        Spectre::Transcoder::TextureDescriptor::TextureDescriptor(
          (__int64)(v18 + 4),
          (Spectre::ImagingV2::ImagingComponent **)&Block,
          v15);
      }
      else
      {
        v19 = 0;
      }
      v20 = v19 + 4;
      v44 = v19 + 4;
      v45 = v19;
      v21 = std::string::string(pExceptionObject, v42);
      v22 = (void **)(v19 + 20);
      if ( v19 + 20 != (_DWORD *)v21 )
      {
        v23 = *((_QWORD *)v19 + 13);
        if ( v23 >= 0x10 )
        {
          v24 = *v22;
          if ( v23 + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)v24 - *(v24 - 1) - 8 > 0x1F )
              goto LABEL_79;
            v24 = (_QWORD *)*(v24 - 1);
          }
          operator delete(v24);
        }
        *((_QWORD *)v19 + 12) = 0;
        *((_QWORD *)v19 + 13) = 15;
        *(_BYTE *)v22 = 0;
        *(_OWORD *)v22 = *(_OWORD *)v21;
        *((_OWORD *)v19 + 6) = *(_OWORD *)(v21 + 16);
        *(_QWORD *)(v21 + 16) = 0;
        *(_QWORD *)(v21 + 24) = 15;
        *(_BYTE *)v21 = 0;
      }
      v25 = *(_QWORD *)(v21 + 24);
      if ( v25 < 0x10 )
      {
LABEL_55:
        *(_QWORD *)(v21 + 16) = 0;
        *(_QWORD *)(v21 + 24) = 15;
        *(_BYTE *)v21 = 0;
        v27 = *(_QWORD *)Spectre::Transcoder::MaterialDescriptor::GetOrAddLayer(*((_QWORD *)this + 33), &v31, 0);
        if ( v19 )
        {
          _InterlockedIncrement(v19 + 2);
          v20 = v44;
        }
        *(_QWORD *)(v27 + 24) = v20;
        v28 = *(volatile signed __int32 **)(v27 + 32);
        *(_QWORD *)(v27 + 32) = v19;
        if ( v28 )
        {
          if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
            if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          }
        }
        v29 = (volatile signed __int32 *)v32.m256i_i64[0];
        if ( v32.m256i_i64[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32.m256i_i64[0] + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
            if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
          }
        }
        if ( v19 )
        {
          if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(_DWORD *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        if ( Block )
          operator delete(Block);
        goto LABEL_71;
      }
      v26 = *(void **)v21;
      if ( v25 + 1 < 0x1000 )
      {
LABEL_54:
        operator delete(v26);
        goto LABEL_55;
      }
      if ( (unsigned __int64)v26 - *((_QWORD *)v26 - 1) - 8 <= 0x1F )
      {
        v26 = (void *)*((_QWORD *)v26 - 1);
        goto LABEL_54;
      }
LABEL_79:
      _invalid_parameter_noinfo_noreturn();
    case 4:
      v5 = *((_QWORD *)this + 12);
      if ( (unsigned __int64)((*((_QWORD *)this + 13) - v5) >> 5) < 3 )
        return 0;
      pExceptionObject[0] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v40 = 0;
      v41 = 0;
      if ( pExceptionObject != (void **)(v5 + 32) )
      {
        std::string::assign(pExceptionObject);
        v5 = *((_QWORD *)this + 12);
      }
      v39 = sub_18036D170((char *)(v5 + 64));
      if ( *((_QWORD *)this + 18) == *((_QWORD *)this + 19) )
      {
        std::vector<Spectre::Transcoder::PlyElement>::_Emplace_reallocate<Spectre::Transcoder::PlyElement const &>(
          (char *)this + 136,
          *((_QWORD *)this + 18),
          pExceptionObject);
      }
      else
      {
        Spectre::Transcoder::PlyElement::PlyElement(
          *((Spectre::Transcoder::PlyElement **)this + 18),
          (const struct Spectre::Transcoder::PlyElement *)pExceptionObject);
        *((_QWORD *)this + 18) += 64LL;
      }
      v6 = pExceptionObject;
      if ( si128.m128i_i64[1] >= 0x10uLL )
        v6 = (void **)pExceptionObject[0];
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsPLYParser, 3, "Element : %s - %d", (const char *)v6, v39);
      std::vector<Spectre::Transcoder::PlyProperty>::_Tidy(&v40);
      if ( si128.m128i_i64[1] < 0x10uLL )
        return 0;
      v7 = pExceptionObject[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v7 = (void *)*((_QWORD *)pExceptionObject[0] - 1);
        if ( (unsigned __int64)((char *)pExceptionObject[0] - (char *)v7 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      goto LABEL_80;
    case 5:
      Spectre::Transcoder::PLYParser::AddProperty(this, (char *)this + 96);
      break;
    case 7:
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18036c9d0  mov     rax, rsp
0x18036c9d3  mov     [rax+10h], rbx
0x18036c9d7  mov     [rax+18h], rsi
0x18036c9db  mov     [rax+20h], rdi
0x18036c9df  push    rbp
0x18036c9e0  push    r12
0x18036c9e2  push    r13
0x18036c9e4  push    r14
0x18036c9e6  push    r15
0x18036c9e8  lea     rbp, [rax-78h]
0x18036c9ec  sub     rsp, 150h
0x18036c9f3  movaps  xmmword ptr [rax-38h], xmm6
0x18036c9f7  mov     rax, cs:__security_cookie
0x18036c9fe  xor     rax, rsp
0x18036ca01  mov     [rbp+70h+var_40], rax
0x18036ca05  mov     r15, rcx
0x18036ca08  xor     r12d, r12d
0x18036ca0b  mov     dword ptr [rsp+170h+var_140], r12d
0x18036ca10  mov     rsi, [rcx+60h]
0x18036ca14  mov     rax, [rcx+68h]
0x18036ca18  sub     rax, rsi
0x18036ca1b  cmp     rax, 20h ; ' '
0x18036ca1f  jb      loc_18036D010
0x18036ca25  mov     r8, rsi
0x18036ca28  lea     rdx, [rsp+170h+var_108]
0x18036ca2d  lea     rcx, ?m_headerLineTypeTranslator@PLYParser@Transcoder@Spectre@@0V?$LineTypeTranslator@W4PLYHeaderLineType@Transcoder@Spectre@@@23@B; Spectre::Transcoder::LineTypeTranslator<Spectre::Transcoder::PLYHeaderLineType> const Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator
0x18036ca34  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@USamplerChannelData@GLTFChannelAnimations@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,GLTFChannelAnimations::SamplerChannelData,std::less<std::string>,std::allocator<std::pair<std::string const,GLTFChannelAnimations::SamplerChannelData>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18036ca39  mov     rdi, [rsp+170h+var_F8]
0x18036ca3e  cmp     [rdi+19h], r12b
0x18036ca42  jnz     loc_18036D010
0x18036ca48  lea     r8, [rdi+20h]
0x18036ca4c  mov     rdx, rsi
0x18036ca4f  lea     rcx, ?m_headerLineTypeTranslator@PLYParser@Transcoder@Spectre@@0V?$LineTypeTranslator@W4PLYHeaderLineType@Transcoder@Spectre@@@23@B; Spectre::Transcoder::LineTypeTranslator<Spectre::Transcoder::PLYHeaderLineType> const Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator
0x18036ca56  call    ??R?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::less<std::string>::operator()(std::string const &,std::string const &)
0x18036ca5b  test    al, al
0x18036ca5d  jnz     loc_18036D010
0x18036ca63  cmp     rdi, cs:?m_headerLineTypeTranslator@PLYParser@Transcoder@Spectre@@0V?$LineTypeTranslator@W4PLYHeaderLineType@Transcoder@Spectre@@@23@B; Spectre::Transcoder::LineTypeTranslator<Spectre::Transcoder::PLYHeaderLineType> const Spectre::Transcoder::PLYParser::m_headerLineTypeTranslator
0x18036ca6a  jz      loc_18036D010
0x18036ca70  mov     ecx, [rdi+40h]
0x18036ca73  sub     ecx, 2
0x18036ca76  jz      loc_18036D004
0x18036ca7c  sub     ecx, 1
0x18036ca7f  jz      loc_18036CBD6
0x18036ca85  sub     ecx, 1
0x18036ca88  jz      short loc_18036CAB0
0x18036ca8a  sub     ecx, 1
0x18036ca8d  jz      short loc_18036CA9F
0x18036ca8f  cmp     ecx, 2
0x18036ca92  jnz     loc_18036D010
0x18036ca98  mov     al, 1
0x18036ca9a  jmp     loc_18036D012
0x18036ca9f  lea     rdx, [r15+60h]
0x18036caa3  mov     rcx, r15
0x18036caa6  call    ?AddProperty@PLYParser@Transcoder@Spectre@@QEAAXAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; Spectre::Transcoder::PLYParser::AddProperty(std::vector<std::string> const &)
0x18036caab  jmp     loc_18036D010
0x18036cab0  mov     rcx, [r15+60h]
0x18036cab4  mov     rax, [r15+68h]
0x18036cab8  sub     rax, rcx
0x18036cabb  sar     rax, 5
0x18036cabf  cmp     rax, 3
0x18036cac3  jb      loc_18036D010
0x18036cac9  mov     [rbp+70h+pExceptionObject], r12
0x18036cacd  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18036cad5  movdqa  [rbp+70h+var_B0], xmm0
0x18036cada  mov     byte ptr [rbp+70h+pExceptionObject], r12b
0x18036cade  mov     [rbp+70h+var_98], r12
0x18036cae2  xorps   xmm0, xmm0
0x18036cae5  movdqa  [rbp+70h+var_90], xmm0
0x18036caea  lea     r8, [rcx+20h]
0x18036caee  lea     rax, [rbp+70h+pExceptionObject]
0x18036caf2  cmp     rax, r8
0x18036caf5  jz      short loc_18036CB15
0x18036caf7  mov     rdx, r8
0x18036cafa  cmp     qword ptr [r8+18h], 10h
0x18036caff  jb      short loc_18036CB04
0x18036cb01  mov     rdx, [r8]
0x18036cb04  mov     r8, [r8+10h]
0x18036cb08  lea     rcx, [rbp+70h+pExceptionObject]; void *
0x18036cb0c  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18036cb11  mov     rcx, [r15+60h]
0x18036cb15  add     rcx, 40h ; '@'; String
0x18036cb19  call    sub_18036D170
0x18036cb1e  mov     [rbp+70h+var_A0], eax
0x18036cb21  mov     rax, [r15+90h]
0x18036cb28  cmp     rax, [r15+98h]
0x18036cb2f  jz      short loc_18036CB47
0x18036cb31  lea     rdx, [rbp+70h+pExceptionObject]; struct Spectre::Transcoder::PlyElement *
0x18036cb35  mov     rcx, rax; this
0x18036cb38  call    ??0PlyElement@Transcoder@Spectre@@QEAA@AEBU012@@Z; Spectre::Transcoder::PlyElement::PlyElement(Spectre::Transcoder::PlyElement const &)
0x18036cb3d  add     qword ptr [r15+90h], 40h ; '@'
0x18036cb45  jmp     short loc_18036CB5A
0x18036cb47  lea     r8, [rbp+70h+pExceptionObject]
0x18036cb4b  mov     rdx, rax
0x18036cb4e  lea     rcx, [r15+88h]
0x18036cb55  call    ??$_Emplace_reallocate@AEBUPlyElement@Transcoder@Spectre@@@?$vector@UPlyElement@Transcoder@Spectre@@V?$allocator@UPlyElement@Transcoder@Spectre@@@std@@@std@@QEAAPEAUPlyElement@Transcoder@Spectre@@QEAU234@AEBU234@@Z; std::vector<Spectre::Transcoder::PlyElement>::_Emplace_reallocate<Spectre::Transcoder::PlyElement const &>(Spectre::Transcoder::PlyElement * const,Spectre::Transcoder::PlyElement const &)
0x18036cb5a  lea     r9, [rbp+70h+pExceptionObject]
0x18036cb5e  cmp     qword ptr [rbp+70h+var_B0+8], 10h
0x18036cb63  cmovnb  r9, [rbp+70h+pExceptionObject]
0x18036cb68  mov     eax, [rbp+70h+var_A0]
0x18036cb6b  mov     [rsp+170h+var_150], eax
0x18036cb6f  lea     r8, aElementSD; "Element : %s - %d"
0x18036cb76  mov     edx, 3
0x18036cb7b  lea     rcx, ?gTraceLevelsPLYParser@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsPLYParser
0x18036cb82  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x18036cb87  nop
0x18036cb88  lea     rcx, [rbp+70h+var_98]
0x18036cb8c  call    ?_Tidy@?$vector@UPlyProperty@Transcoder@Spectre@@V?$allocator@UPlyProperty@Transcoder@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Transcoder::PlyProperty>::_Tidy(void)
0x18036cb91  mov     rdx, qword ptr [rbp+70h+var_B0+8]
0x18036cb95  cmp     rdx, 10h
0x18036cb99  jb      loc_18036D010
0x18036cb9f  inc     rdx
0x18036cba2  mov     rcx, [rbp+70h+pExceptionObject]; Block
0x18036cba6  mov     rax, rcx
0x18036cba9  cmp     rdx, 1000h
0x18036cbb0  jb      loc_18036CFFD
0x18036cbb6  add     rdx, 27h ; '''
0x18036cbba  mov     rcx, [rcx-8]
0x18036cbbe  sub     rax, rcx
0x18036cbc1  add     rax, 0FFFFFFFFFFFFFFF8h
0x18036cbc5  cmp     rax, 1Fh
0x18036cbc9  jbe     loc_18036CFFD
0x18036cbcf  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18036cbd6  mov     rdi, [r15+60h]
0x18036cbda  mov     rax, [r15+68h]
0x18036cbde  sub     rax, rdi
0x18036cbe1  sar     rax, 5
0x18036cbe5  cmp     rax, 3
0x18036cbe9  jb      loc_18036D010
0x18036cbef  lea     rcx, [rdi+20h]
0x18036cbf3  cmp     qword ptr [rdi+38h], 10h
0x18036cbf8  jb      short loc_18036CBFE
0x18036cbfa  mov     rcx, [rdi+20h]; Buf1
0x18036cbfe  cmp     qword ptr [rdi+30h], 0Bh
0x18036cc03  jnz     loc_18036D010
0x18036cc09  mov     r8d, 0Bh; Size
0x18036cc0f  lea     rdx, aTexturefile; "TextureFile"
0x18036cc16  call    memcmp_0
0x18036cc1b  test    eax, eax
0x18036cc1d  jnz     loc_18036D010
0x18036cc23  lea     rdx, [rdi+40h]
0x18036cc27  lea     rcx, [rbp+70h+var_80]
0x18036cc2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18036cc30  nop
0x18036cc31  lea     r9, [rbp+70h+var_80]
0x18036cc35  cmp     [rbp+70h+var_68], 10h
0x18036cc3a  cmovnb  r9, [rbp+70h+var_80]
0x18036cc3f  lea     r8, aTextureReferen; "Texture Reference: %s"
0x18036cc46  mov     edx, 3
0x18036cc4b  lea     rcx, ?gTraceLevelsPLYParser@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsPLYParser
0x18036cc52  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x18036cc57  cmp     [rbp+70h+var_70], 0
0x18036cc5c  jz      loc_18036CFBD
0x18036cc62  mov     rcx, [r15+10h]
0x18036cc66  test    rcx, rcx
0x18036cc69  jz      loc_18036CFBD
0x18036cc6f  xorps   xmm0, xmm0
0x18036cc72  movups  [rbp+70h+var_50], xmm0
0x18036cc76  mov     rax, [rcx]
0x18036cc79  lea     r8, [rbp+70h+var_80]
0x18036cc7d  lea     rdx, [rbp+70h+var_50]
0x18036cc81  mov     rax, [rax+8]
0x18036cc85  call    cs:__guard_dispatch_icall_fptr
0x18036cc8b  nop
0x18036cc8c  mov     edi, 0FFFFFFFFh
0x18036cc91  mov     rsi, qword ptr [rbp+70h+var_50]
0x18036cc95  test    rsi, rsi
0x18036cc98  jz      loc_18036CF7E
0x18036cc9e  mov     [rbp+70h+Block], r12
0x18036cca2  xor     edx, edx
0x18036cca4  lea     r8d, [rdi+3]
0x18036cca8  mov     rcx, rsi
0x18036ccab  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18036ccb1  xorps   xmm6, xmm6
0x18036ccb4  movdqu  xmmword ptr [rsp+170h+var_128+8], xmm6
0x18036ccba  xor     eax, eax
0x18036ccbc  mov     [rsp+170h+var_110], rax
0x18036ccc1  lea     rdx, [rbp+70h+var_E8]
0x18036ccc5  mov     rcx, rsi
0x18036ccc8  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18036ccce  mov     r9, [rax+8]
0x18036ccd2  add     r9, [rax]
0x18036ccd5  xorps   xmm0, xmm0
0x18036ccd8  psrldq  xmm0, 8
0x18036ccdd  movq    r8, xmm0
0x18036cce2  movq    rcx, xmm6
0x18036cce7  add     r8, rcx
0x18036ccea  lea     rcx, [rsp+170h+var_128+8]
0x18036ccef  cmp     r9, r8
0x18036ccf2  cmovge  rcx, rax
0x18036ccf6  mov     r14, [rcx+8]
0x18036ccfa  add     r14, [rcx]
0x18036ccfd  mov     [rsp+170h+var_138], r12
0x18036cd02  mov     rcx, r14; unsigned __int64
0x18036cd05  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18036cd0a  mov     rbx, rax
0x18036cd0d  test    rax, rax
0x18036cd10  jz      short loc_18036CD21
0x18036cd12  mov     r8, r14; Size
0x18036cd15  xor     edx, edx; Val
0x18036cd17  mov     rcx, rax; void *
0x18036cd1a  call    memset_0
0x18036cd1f  jmp     short loc_18036CD24
0x18036cd21  mov     rbx, r12
0x18036cd24  mov     [rsp+170h+var_138], rbx
0x18036cd29  mov     dword ptr [rsp+170h+var_140], 3
0x18036cd31  xor     r8d, r8d
0x18036cd34  xor     edx, edx
0x18036cd36  mov     rcx, rsi
0x18036cd39  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18036cd3f  mov     r8, r14
0x18036cd42  mov     rdx, rbx
0x18036cd45  mov     rcx, rsi
0x18036cd48  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036cd4e  cmp     [rsi+8], r14
0x18036cd52  jnz     loc_18036D044
0x18036cd58  mov     [rbp+70h+Block], rbx
0x18036cd5c  mov     ecx, 98h; Size
0x18036cd61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18036cd66  mov     rbx, rax
0x18036cd69  mov     [rsp+170h+var_130], rax
0x18036cd6e  test    rax, rax
0x18036cd71  jz      short loc_18036CDA3
0x18036cd73  xorps   xmm0, xmm0
0x18036cd76  movups  xmmword ptr [rax], xmm0
0x18036cd79  mov     dword ptr [rax+8], 1
0x18036cd80  mov     dword ptr [rax+0Ch], 1
0x18036cd87  lea     rax, ??_7?$_Ref_count_obj2@VTextureDescriptor@Transcoder@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Transcoder::TextureDescriptor>::`vftable'
0x18036cd8e  mov     [rbx], rax
0x18036cd91  lea     rcx, [rbx+10h]
0x18036cd95  mov     r8, r14
0x18036cd98  lea     rdx, [rbp+70h+Block]
0x18036cd9c  call    ??0TextureDescriptor@Transcoder@Spectre@@QEAA@$$QEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@_K@Z; Spectre::Transcoder::TextureDescriptor::TextureDescriptor(std::unique_ptr<uchar [0]> &&,unsigned __int64)
0x18036cda1  jmp     short loc_18036CDA6
0x18036cda3  mov     rbx, r12
0x18036cda6  xorps   xmm0, xmm0
0x18036cda9  movups  [rbp+70h+var_60], xmm0
0x18036cdad  lea     r13, [rbx+10h]
0x18036cdb1  mov     qword ptr [rbp+70h+var_60], r13
0x18036cdb5  mov     qword ptr [rbp+70h+var_60+8], rbx
0x18036cdb9  lea     rdx, [rbp+70h+var_80]
0x18036cdbd  lea     rcx, [rbp+70h+pExceptionObject]
0x18036cdc1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18036cdc6  mov     rsi, rax
0x18036cdc9  lea     r14, [r13+40h]
0x18036cdcd  cmp     r14, rax
0x18036cdd0  jz      short loc_18036CE3B
0x18036cdd2  mov     rdx, [r14+18h]
0x18036cdd6  cmp     rdx, 10h
0x18036cdda  jb      short loc_18036CE0C
0x18036cddc  mov     rcx, [r14]
0x18036cddf  inc     rdx
0x18036cde2  cmp     rdx, 1000h
0x18036cde9  jb      short loc_18036CE07
0x18036cdeb  add     rdx, 27h ; '''
0x18036cdef  mov     r8, [rcx-8]
0x18036cdf3  sub     rcx, r8
0x18036cdf6  lea     rax, [rcx-8]
0x18036cdfa  cmp     rax, 1Fh
0x18036cdfe  ja      loc_18036CFF6
0x18036ce04  mov     rcx, r8; Block
0x18036ce07  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18036ce0c  mov     [r14+10h], r12
0x18036ce10  mov     qword ptr [r14+18h], 0Fh
0x18036ce18  mov     byte ptr [r14], 0
0x18036ce1c  movups  xmm0, xmmword ptr [rsi]
0x18036ce1f  movups  xmmword ptr [r14], xmm0
0x18036ce23  movups  xmm1, xmmword ptr [rsi+10h]
0x18036ce27  movups  xmmword ptr [r14+10h], xmm1
0x18036ce2c  mov     [rsi+10h], r12
0x18036ce30  mov     qword ptr [rsi+18h], 0Fh
0x18036ce38  mov     byte ptr [rsi], 0
0x18036ce3b  mov     rdx, [rsi+18h]
0x18036ce3f  cmp     rdx, 10h
0x18036ce43  jb      short loc_18036CE75
0x18036ce45  mov     rcx, [rsi]
0x18036ce48  inc     rdx
0x18036ce4b  cmp     rdx, 1000h
0x18036ce52  jb      short loc_18036CE70
0x18036ce54  add     rdx, 27h ; '''
0x18036ce58  mov     r8, [rcx-8]
0x18036ce5c  sub     rcx, r8
0x18036ce5f  lea     rax, [rcx-8]
0x18036ce63  cmp     rax, 1Fh
0x18036ce67  ja      loc_18036CFF6
0x18036ce6d  mov     rcx, r8; Block
0x18036ce70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18036ce75  mov     [rsi+10h], r12
0x18036ce79  mov     qword ptr [rsi+18h], 0Fh
0x18036ce81  mov     byte ptr [rsi], 0
0x18036ce84  xor     r8d, r8d
0x18036ce87  lea     rdx, [rsp+170h+var_130]
0x18036ce8c  mov     rcx, [r15+108h]
0x18036ce93  call    ?GetOrAddLayer@MaterialDescriptor@Transcoder@Spectre@@QEAA?AV?$shared_ptr@UMaterialLayer@Transcoder@Spectre@@@std@@W4TextureMaterialLayer@Framework@3@@Z; Spectre::Transcoder::MaterialDescriptor::GetOrAddLayer(Spectre::Framework::TextureMaterialLayer)
0x18036ce98  mov     rcx, [rax]
0x18036ce9b  test    rbx, rbx
0x18036ce9e  jz      short loc_18036CEA8
0x18036cea0  lock inc dword ptr [rbx+8]
0x18036cea4  mov     r13, qword ptr [rbp+70h+var_60]
0x18036cea8  mov     [rcx+18h], r13
0x18036ceac  mov     rsi, [rcx+20h]
  ... truncated ...
```

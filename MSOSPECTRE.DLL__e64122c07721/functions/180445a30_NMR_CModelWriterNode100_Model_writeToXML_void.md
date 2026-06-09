# NMR::CModelWriterNode100_Model::writeToXML(void)

- ea: `0x180445a30`
- end: `0x180446094`
- name: `?writeToXML@CModelWriterNode100_Model@NMR@@UEAAXXZ`
- size: `1636`
- prototype: `void __fastcall(NMR::CModelWriterNode100_Model *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180435250`
- `0x180435390`

## callees

- `0x180016350`
- `0x18003d030`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x18041d820`
- `0x180420360`
- `0x180420a70`
- `0x1804421a0`
- `0x180442ed0`
- `0x1804434e0`
- `0x1804443c0`
- `0x180445a30`
- `0x18044dd00`
- `0x18044dd20`
- `0x18044dfa0`
- `0x18044e280`
- `0x18044e2c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445bfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445c86`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445d7d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445e07`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445efe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445f88`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180446010`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180446063`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445bfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445c86`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445d7d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445e07`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445efe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180445f88`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180446010`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180446063`

## string_xrefs

- `0x180445c9c`: `http://schemas.microsoft.com/3dmanufacturing/beamlattice/2017/02`
- `0x180445ccf`: `http://schemas.microsoft.com/3dmanufacturing/beamlattice/2017/02`
- `0x180445e1d`: `http://schemas.microsoft.com/3dmanufacturing/slice/2015/07`
- `0x180445e50`: `http://schemas.microsoft.com/3dmanufacturing/slice/2015/07`
- `0x180445b1b`: `http://schemas.microsoft.com/3dmanufacturing/production/2015/06`
- `0x180445c08`: `http://schemas.microsoft.com/3dmanufacturing/production/2015/06`
- `0x180445b02`: `xmlns`
- `0x180445b29`: `xmlns`
- `0x180445caa`: `xmlns`
- `0x180445e2b`: `xmlns`
- `0x180445a6b`: `http://schemas.microsoft.com/3dmanufacturing/core/2015/02`
- `0x180445af4`: `http://schemas.microsoft.com/3dmanufacturing/material/2015/02`
- `0x180445fa9`: `requiredextensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NMR::CModelWriterNode100_Model::writeToXML(NMR::CModelWriterNode100_Model *this)
{
  __int64 UnitString; // rax
  const wchar_t *v3; // r9
  __int64 v4; // rdi
  void *v5; // rcx
  __int64 v6; // rdi
  void *v7; // rcx
  __int64 v8; // rdi
  void *v9; // rcx
  __int64 v10; // rdi
  void *v11; // rcx
  __int64 v12; // rdi
  void *v13; // rcx
  __int64 v14; // rdi
  void *v15; // rcx
  const wchar_t *v16; // r8
  wchar_t *v17; // rcx
  wchar_t *v18; // rcx
  void *Block[2]; // [rsp+20h] [rbp-19h] BYREF
  __int64 v20; // [rsp+30h] [rbp-9h]
  unsigned __int64 v21; // [rsp+38h] [rbp-1h]
  wchar_t *Src[2]; // [rsp+48h] [rbp+Fh] BYREF
  __int128 v23; // [rsp+58h] [rbp+1Fh]
  wchar_t *v24[3]; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp+47h]

  NMR::CModel::getLanguage(*((_QWORD *)this + 1), v24);
  NMR::CModelWriterNode::writeStartElementWithNamespace(
    this,
    L"model",
    L"http://schemas.microsoft.com/3dmanufacturing/core/2015/02");
  UnitString = NMR::CModel::getUnitString(*((_QWORD *)this + 1), Block);
  NMR::CModelWriterNode::writeStringAttribute(this, L"unit", UnitString);
  v3 = (const wchar_t *)v24;
  if ( v25 >= 8 )
    v3 = v24[0];
  NMR::CModelWriterNode::writeConstPrefixedStringAttribute(this, L"xml", L"lang", v3);
  Src[0] = 0;
  *(_QWORD *)&v23 = 0;
  *((_QWORD *)&v23 + 1) = 7;
  std::wstring::assign(Src);
  if ( *((_BYTE *)this + 68) )
    NMR::CModelWriterNode::writeConstPrefixedStringAttribute(
      this,
      L"xmlns",
      L"m",
      L"http://schemas.microsoft.com/3dmanufacturing/material/2015/02");
  if ( *((_BYTE *)this + 69) )
  {
    NMR::CModelWriterNode::writeConstPrefixedStringAttribute(
      this,
      L"xmlns",
      L"p",
      L"http://schemas.microsoft.com/3dmanufacturing/production/2015/06");
    Block[0] = 0;
    v20 = 0;
    v21 = 7;
    std::wstring::assign(Block);
    if ( (unsigned __int8)NMR::CModel::RequireExtension(*((_QWORD *)this + 1), Block) )
    {
      if ( (_QWORD)v23 )
      {
        v4 = std::operator+<wchar_t>(Block, Src, L" ");
        if ( Src != (wchar_t **)v4 )
        {
          std::wstring::_Tidy_deallocate(Src);
          *(_OWORD *)Src = *(_OWORD *)v4;
          v23 = *(_OWORD *)(v4 + 16);
          *(_QWORD *)(v4 + 16) = 0;
          *(_QWORD *)(v4 + 24) = 7;
          *(_WORD *)v4 = 0;
        }
        if ( v21 >= 8 )
        {
          v5 = Block[0];
          if ( 2 * v21 + 2 >= 0x1000 )
          {
            v5 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v5 - 8) > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v5);
        }
      }
      v6 = std::operator+<wchar_t>(
             Block,
             Src,
             (void *)L"http://schemas.microsoft.com/3dmanufacturing/production/2015/06");
      if ( Src != (wchar_t **)v6 )
      {
        std::wstring::_Tidy_deallocate(Src);
        *(_OWORD *)Src = *(_OWORD *)v6;
        v23 = *(_OWORD *)(v6 + 16);
        *(_QWORD *)(v6 + 16) = 0;
        *(_QWORD *)(v6 + 24) = 7;
        *(_WORD *)v6 = 0;
      }
      if ( v21 >= 8 )
      {
        v7 = Block[0];
        if ( 2 * v21 + 2 >= 0x1000 )
        {
          v7 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v7 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v7);
      }
    }
  }
  if ( *((_BYTE *)this + 70) )
  {
    NMR::CModelWriterNode::writeConstPrefixedStringAttribute(
      this,
      L"xmlns",
      L"b",
      L"http://schemas.microsoft.com/3dmanufacturing/beamlattice/2017/02");
    Block[0] = 0;
    v20 = 0;
    v21 = 7;
    std::wstring::assign(Block);
    if ( (unsigned __int8)NMR::CModel::RequireExtension(*((_QWORD *)this + 1), Block) )
    {
      if ( (_QWORD)v23 )
      {
        v8 = std::operator+<wchar_t>(Block, Src, L" ");
        if ( Src != (wchar_t **)v8 )
        {
          std::wstring::_Tidy_deallocate(Src);
          *(_OWORD *)Src = *(_OWORD *)v8;
          v23 = *(_OWORD *)(v8 + 16);
          *(_QWORD *)(v8 + 16) = 0;
          *(_QWORD *)(v8 + 24) = 7;
          *(_WORD *)v8 = 0;
        }
        if ( v21 >= 8 )
        {
          v9 = Block[0];
          if ( 2 * v21 + 2 >= 0x1000 )
          {
            v9 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v9);
        }
      }
      v10 = std::operator+<wchar_t>(Block, Src, (void *)L"b");
      if ( Src != (wchar_t **)v10 )
      {
        std::wstring::_Tidy_deallocate(Src);
        *(_OWORD *)Src = *(_OWORD *)v10;
        v23 = *(_OWORD *)(v10 + 16);
        *(_QWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 7;
        *(_WORD *)v10 = 0;
      }
      if ( v21 >= 8 )
      {
        v11 = Block[0];
        if ( 2 * v21 + 2 >= 0x1000 )
        {
          v11 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v11);
      }
    }
  }
  if ( *((_BYTE *)this + 71) )
  {
    NMR::CModelWriterNode::writeConstPrefixedStringAttribute(
      this,
      L"xmlns",
      L"s",
      L"http://schemas.microsoft.com/3dmanufacturing/slice/2015/07");
    Block[0] = 0;
    v20 = 0;
    v21 = 7;
    std::wstring::assign(Block);
    if ( (unsigned __int8)NMR::CModel::RequireExtension(*((_QWORD *)this + 1), Block) )
    {
      if ( (_QWORD)v23 )
      {
        v12 = std::operator+<wchar_t>(Block, Src, L" ");
        if ( Src != (wchar_t **)v12 )
        {
          std::wstring::_Tidy_deallocate(Src);
          *(_OWORD *)Src = *(_OWORD *)v12;
          v23 = *(_OWORD *)(v12 + 16);
          *(_QWORD *)(v12 + 16) = 0;
          *(_QWORD *)(v12 + 24) = 7;
          *(_WORD *)v12 = 0;
        }
        if ( v21 >= 8 )
        {
          v13 = Block[0];
          if ( 2 * v21 + 2 >= 0x1000 )
          {
            v13 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v13);
        }
      }
      v14 = std::operator+<wchar_t>(Block, Src, (void *)L"s");
      if ( Src != (wchar_t **)v14 )
      {
        std::wstring::_Tidy_deallocate(Src);
        *(_OWORD *)Src = *(_OWORD *)v14;
        v23 = *(_OWORD *)(v14 + 16);
        *(_QWORD *)(v14 + 16) = 0;
        *(_QWORD *)(v14 + 24) = 7;
        *(_WORD *)v14 = 0;
      }
      if ( v21 >= 8 )
      {
        v15 = Block[0];
        if ( 2 * v21 + 2 >= 0x1000 )
        {
          v15 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v15 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v15);
      }
    }
  }
  if ( (_QWORD)v23 )
  {
    v16 = (const wchar_t *)Src;
    if ( *((_QWORD *)&v23 + 1) >= 8u )
      v16 = Src[0];
    NMR::CModelWriterNode::writeConstStringAttribute(this, L"requiredextensions", v16);
  }
  NMR::CModelWriterNode100_Model::writeMetaData(this);
  NMR::CModelWriterNode100_Model::writeResources(this);
  NMR::CModelWriterNode100_Model::writeBuild(this);
  NMR::CModelWriterNode::writeFullEndElement(this);
  if ( *((_QWORD *)&v23 + 1) >= 8u )
  {
    v17 = Src[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v23 + 1) + 2) >= 0x1000 )
    {
      v17 = (wchar_t *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v17 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v17);
  }
  *(_QWORD *)&v23 = 0;
  *((_QWORD *)&v23 + 1) = 7;
  LOWORD(Src[0]) = 0;
  if ( v25 >= 8 )
  {
    v18 = v24[0];
    if ( 2 * v25 + 2 >= 0x1000 )
    {
      v18 = (wchar_t *)*((_QWORD *)v24[0] - 1);
      if ( (unsigned __int64)((char *)v24[0] - (char *)v18 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v18);
  }
}

```

## disassembly

```asm
0x180445a30  mov     [rsp-8+arg_8], rbx
0x180445a35  mov     [rsp-8+arg_10], rsi
0x180445a3a  mov     [rsp-8+arg_18], rdi
0x180445a3f  push    rbp
0x180445a40  lea     rbp, [rsp-57h]
0x180445a45  sub     rsp, 90h
0x180445a4c  mov     rax, cs:__security_cookie
0x180445a53  xor     rax, rsp
0x180445a56  mov     [rbp+57h+var_8], rax
0x180445a5a  mov     rbx, rcx
0x180445a5d  lea     rdx, [rbp+57h+var_28]
0x180445a61  mov     rcx, [rcx+8]
0x180445a65  call    ?getLanguage@CModel@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::CModel::getLanguage(void)
0x180445a6a  nop
0x180445a6b  lea     r8, aHttpSchemasMic_4; "http://schemas.microsoft.com/3dmanufact"...
0x180445a72  lea     rdx, aModel_1; "model"
0x180445a79  mov     rcx, rbx; this
0x180445a7c  call    ?writeStartElementWithNamespace@CModelWriterNode@NMR@@IEAAXPEB_W0@Z; NMR::CModelWriterNode::writeStartElementWithNamespace(wchar_t const *,wchar_t const *)
0x180445a81  lea     rdx, [rbp+57h+Block]
0x180445a85  mov     rcx, [rbx+8]
0x180445a89  call    ?getUnitString@CModel@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::CModel::getUnitString(void)
0x180445a8e  mov     r8, rax
0x180445a91  lea     rdx, aUnit; "unit"
0x180445a98  mov     rcx, rbx
0x180445a9b  call    ?writeStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::CModelWriterNode::writeStringAttribute(wchar_t const *,std::wstring)
0x180445aa0  lea     r9, [rbp+57h+var_28]
0x180445aa4  cmp     [rbp+57h+var_10], 8
0x180445aa9  cmovnb  r9, [rbp+57h+var_28]; wchar_t *
0x180445aae  lea     r8, aLang; "lang"
0x180445ab5  lea     rdx, aXml; "xml"
0x180445abc  mov     rcx, rbx; this
0x180445abf  call    ?writeConstPrefixedStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_W00@Z; NMR::CModelWriterNode::writeConstPrefixedStringAttribute(wchar_t const *,wchar_t const *,wchar_t const *)
0x180445ac4  xor     esi, esi
0x180445ac6  mov     [rbp+57h+Src], rsi
0x180445aca  mov     qword ptr [rbp+57h+var_38], rsi
0x180445ace  mov     qword ptr [rbp+57h+var_38+8], 7
0x180445ad6  mov     word ptr [rbp+57h+Src], si
0x180445ada  xor     r8d, r8d
0x180445add  lea     rdx, qword_1806B12B0
0x180445ae4  lea     rcx, [rbp+57h+Src]; void *
0x180445ae8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180445aed  nop
0x180445aee  cmp     [rbx+44h], sil
0x180445af2  jz      short loc_180445B11
0x180445af4  lea     r9, aHttpSchemasMic_1; "http://schemas.microsoft.com/3dmanufact"...
0x180445afb  lea     r8, aM; "m"
0x180445b02  lea     rdx, aXmlns_0; "xmlns"
0x180445b09  mov     rcx, rbx; this
0x180445b0c  call    ?writeConstPrefixedStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_W00@Z; NMR::CModelWriterNode::writeConstPrefixedStringAttribute(wchar_t const *,wchar_t const *,wchar_t const *)
0x180445b11  cmp     byte ptr [rbx+45h], 0
0x180445b15  jz      loc_180445C92
0x180445b1b  lea     r9, aHttpSchemasMic_2; "http://schemas.microsoft.com/3dmanufact"...
0x180445b22  lea     r8, aP; "p"
0x180445b29  lea     rdx, aXmlns_0; "xmlns"
0x180445b30  mov     rcx, rbx; this
0x180445b33  call    ?writeConstPrefixedStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_W00@Z; NMR::CModelWriterNode::writeConstPrefixedStringAttribute(wchar_t const *,wchar_t const *,wchar_t const *)
0x180445b38  mov     [rbp+57h+Block], rsi
0x180445b3c  mov     [rbp+57h+var_60], rsi
0x180445b40  mov     [rbp+57h+var_58], 7
0x180445b48  mov     r8d, 1
0x180445b4e  lea     rdx, aP; "p"
0x180445b55  lea     rcx, [rbp+57h+Block]; void *
0x180445b59  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180445b5e  lea     rdx, [rbp+57h+Block]
0x180445b62  mov     rcx, [rbx+8]
0x180445b66  call    ?RequireExtension@CModel@NMR@@QEAA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::CModel::RequireExtension(std::wstring)
0x180445b6b  test    al, al
0x180445b6d  jz      loc_180445C92
0x180445b73  cmp     qword ptr [rbp+57h+var_38], 0
0x180445b78  jbe     loc_180445C08
0x180445b7e  lea     r8, asc_180613F78; " "
0x180445b85  lea     rdx, [rbp+57h+Src]; Src
0x180445b89  lea     rcx, [rbp+57h+Block]; void *
0x180445b8d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445b92  mov     rdi, rax
0x180445b95  lea     rax, [rbp+57h+Src]
0x180445b99  cmp     rax, rdi
0x180445b9c  jz      short loc_180445BC5
0x180445b9e  lea     rcx, [rbp+57h+Src]
0x180445ba2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445ba7  movups  xmm0, xmmword ptr [rdi]
0x180445baa  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445bae  movups  xmm1, xmmword ptr [rdi+10h]
0x180445bb2  movups  [rbp+57h+var_38], xmm1
0x180445bb6  mov     [rdi+10h], rsi
0x180445bba  mov     qword ptr [rdi+18h], 7
0x180445bc2  mov     [rdi], si
0x180445bc5  mov     rdx, [rbp+57h+var_58]
0x180445bc9  cmp     rdx, 8
0x180445bcd  jb      short loc_180445C08
0x180445bcf  lea     rdx, ds:2[rdx*2]
0x180445bd7  mov     rcx, [rbp+57h+Block]; Block
0x180445bdb  mov     rax, rcx
0x180445bde  cmp     rdx, 1000h
0x180445be5  jb      short loc_180445C03
0x180445be7  add     rdx, 27h ; '''
0x180445beb  mov     rcx, [rcx-8]
0x180445bef  sub     rax, rcx
0x180445bf2  add     rax, 0FFFFFFFFFFFFFFF8h
0x180445bf6  cmp     rax, 1Fh
0x180445bfa  jbe     short loc_180445C03
0x180445bfc  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180445c03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180445c08  lea     r8, aHttpSchemasMic_2; "http://schemas.microsoft.com/3dmanufact"...
0x180445c0f  lea     rdx, [rbp+57h+Src]; Src
0x180445c13  lea     rcx, [rbp+57h+Block]; void *
0x180445c17  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445c1c  mov     rdi, rax
0x180445c1f  lea     rax, [rbp+57h+Src]
0x180445c23  cmp     rax, rdi
0x180445c26  jz      short loc_180445C4F
0x180445c28  lea     rcx, [rbp+57h+Src]
0x180445c2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445c31  movups  xmm0, xmmword ptr [rdi]
0x180445c34  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445c38  movups  xmm1, xmmword ptr [rdi+10h]
0x180445c3c  movups  [rbp+57h+var_38], xmm1
0x180445c40  mov     [rdi+10h], rsi
0x180445c44  mov     qword ptr [rdi+18h], 7
0x180445c4c  mov     [rdi], si
0x180445c4f  mov     rdx, [rbp+57h+var_58]
0x180445c53  cmp     rdx, 8
0x180445c57  jb      short loc_180445C92
0x180445c59  lea     rdx, ds:2[rdx*2]
0x180445c61  mov     rcx, [rbp+57h+Block]; Block
0x180445c65  mov     rax, rcx
0x180445c68  cmp     rdx, 1000h
0x180445c6f  jb      short loc_180445C8D
0x180445c71  add     rdx, 27h ; '''
0x180445c75  mov     rcx, [rcx-8]
0x180445c79  sub     rax, rcx
0x180445c7c  add     rax, 0FFFFFFFFFFFFFFF8h
0x180445c80  cmp     rax, 1Fh
0x180445c84  jbe     short loc_180445C8D
0x180445c86  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180445c8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180445c92  cmp     byte ptr [rbx+46h], 0
0x180445c96  jz      loc_180445E13
0x180445c9c  lea     r9, aHttpSchemasMic_0; "http://schemas.microsoft.com/3dmanufact"...
0x180445ca3  lea     r8, aB_1; "b"
0x180445caa  lea     rdx, aXmlns_0; "xmlns"
0x180445cb1  mov     rcx, rbx; this
0x180445cb4  call    ?writeConstPrefixedStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_W00@Z; NMR::CModelWriterNode::writeConstPrefixedStringAttribute(wchar_t const *,wchar_t const *,wchar_t const *)
0x180445cb9  mov     [rbp+57h+Block], rsi
0x180445cbd  mov     [rbp+57h+var_60], rsi
0x180445cc1  mov     [rbp+57h+var_58], 7
0x180445cc9  mov     r8d, 40h ; '@'
0x180445ccf  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/3dmanufact"...
0x180445cd6  lea     rcx, [rbp+57h+Block]; void *
0x180445cda  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180445cdf  lea     rdx, [rbp+57h+Block]
0x180445ce3  mov     rcx, [rbx+8]
0x180445ce7  call    ?RequireExtension@CModel@NMR@@QEAA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::CModel::RequireExtension(std::wstring)
0x180445cec  test    al, al
0x180445cee  jz      loc_180445E13
0x180445cf4  cmp     qword ptr [rbp+57h+var_38], 0
0x180445cf9  jbe     loc_180445D89
0x180445cff  lea     r8, asc_180613F78; " "
0x180445d06  lea     rdx, [rbp+57h+Src]; Src
0x180445d0a  lea     rcx, [rbp+57h+Block]; void *
0x180445d0e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445d13  mov     rdi, rax
0x180445d16  lea     rax, [rbp+57h+Src]
0x180445d1a  cmp     rax, rdi
0x180445d1d  jz      short loc_180445D46
0x180445d1f  lea     rcx, [rbp+57h+Src]
0x180445d23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445d28  movups  xmm0, xmmword ptr [rdi]
0x180445d2b  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445d2f  movups  xmm1, xmmword ptr [rdi+10h]
0x180445d33  movups  [rbp+57h+var_38], xmm1
0x180445d37  mov     [rdi+10h], rsi
0x180445d3b  mov     qword ptr [rdi+18h], 7
0x180445d43  mov     [rdi], si
0x180445d46  mov     rdx, [rbp+57h+var_58]
0x180445d4a  cmp     rdx, 8
0x180445d4e  jb      short loc_180445D89
0x180445d50  lea     rdx, ds:2[rdx*2]
0x180445d58  mov     rcx, [rbp+57h+Block]; Block
0x180445d5c  mov     rax, rcx
0x180445d5f  cmp     rdx, 1000h
0x180445d66  jb      short loc_180445D84
0x180445d68  add     rdx, 27h ; '''
0x180445d6c  mov     rcx, [rcx-8]
0x180445d70  sub     rax, rcx
0x180445d73  add     rax, 0FFFFFFFFFFFFFFF8h
0x180445d77  cmp     rax, 1Fh
0x180445d7b  jbe     short loc_180445D84
0x180445d7d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180445d84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180445d89  lea     r8, aB_1; "b"
0x180445d90  lea     rdx, [rbp+57h+Src]; Src
0x180445d94  lea     rcx, [rbp+57h+Block]; void *
0x180445d98  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445d9d  mov     rdi, rax
0x180445da0  lea     rax, [rbp+57h+Src]
0x180445da4  cmp     rax, rdi
0x180445da7  jz      short loc_180445DD0
0x180445da9  lea     rcx, [rbp+57h+Src]
0x180445dad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445db2  movups  xmm0, xmmword ptr [rdi]
0x180445db5  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445db9  movups  xmm1, xmmword ptr [rdi+10h]
0x180445dbd  movups  [rbp+57h+var_38], xmm1
0x180445dc1  mov     [rdi+10h], rsi
0x180445dc5  mov     qword ptr [rdi+18h], 7
0x180445dcd  mov     [rdi], si
0x180445dd0  mov     rdx, [rbp+57h+var_58]
0x180445dd4  cmp     rdx, 8
0x180445dd8  jb      short loc_180445E13
0x180445dda  lea     rdx, ds:2[rdx*2]
0x180445de2  mov     rcx, [rbp+57h+Block]; Block
0x180445de6  mov     rax, rcx
0x180445de9  cmp     rdx, 1000h
0x180445df0  jb      short loc_180445E0E
0x180445df2  add     rdx, 27h ; '''
0x180445df6  mov     rcx, [rcx-8]
0x180445dfa  sub     rax, rcx
0x180445dfd  add     rax, 0FFFFFFFFFFFFFFF8h
0x180445e01  cmp     rax, 1Fh
0x180445e05  jbe     short loc_180445E0E
0x180445e07  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180445e0e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180445e13  cmp     byte ptr [rbx+47h], 0
0x180445e17  jz      loc_180445F94
0x180445e1d  lea     r9, aHttpSchemasMic_7; "http://schemas.microsoft.com/3dmanufact"...
0x180445e24  lea     r8, aS_2; "s"
0x180445e2b  lea     rdx, aXmlns_0; "xmlns"
0x180445e32  mov     rcx, rbx; this
0x180445e35  call    ?writeConstPrefixedStringAttribute@CModelWriterNode@NMR@@IEAAXPEB_W00@Z; NMR::CModelWriterNode::writeConstPrefixedStringAttribute(wchar_t const *,wchar_t const *,wchar_t const *)
0x180445e3a  mov     [rbp+57h+Block], rsi
0x180445e3e  mov     [rbp+57h+var_60], rsi
0x180445e42  mov     [rbp+57h+var_58], 7
0x180445e4a  mov     r8d, 3Ah ; ':'
0x180445e50  lea     rdx, aHttpSchemasMic_7; "http://schemas.microsoft.com/3dmanufact"...
0x180445e57  lea     rcx, [rbp+57h+Block]; void *
0x180445e5b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180445e60  lea     rdx, [rbp+57h+Block]
0x180445e64  mov     rcx, [rbx+8]
0x180445e68  call    ?RequireExtension@CModel@NMR@@QEAA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::CModel::RequireExtension(std::wstring)
0x180445e6d  test    al, al
0x180445e6f  jz      loc_180445F94
0x180445e75  cmp     qword ptr [rbp+57h+var_38], 0
0x180445e7a  jbe     loc_180445F0A
0x180445e80  lea     r8, asc_180613F78; " "
0x180445e87  lea     rdx, [rbp+57h+Src]; Src
0x180445e8b  lea     rcx, [rbp+57h+Block]; void *
0x180445e8f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445e94  mov     rdi, rax
0x180445e97  lea     rax, [rbp+57h+Src]
0x180445e9b  cmp     rax, rdi
0x180445e9e  jz      short loc_180445EC7
0x180445ea0  lea     rcx, [rbp+57h+Src]
0x180445ea4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445ea9  movups  xmm0, xmmword ptr [rdi]
0x180445eac  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445eb0  movups  xmm1, xmmword ptr [rdi+10h]
0x180445eb4  movups  [rbp+57h+var_38], xmm1
0x180445eb8  mov     [rdi+10h], rsi
0x180445ebc  mov     qword ptr [rdi+18h], 7
0x180445ec4  mov     [rdi], si
0x180445ec7  mov     rdx, [rbp+57h+var_58]
0x180445ecb  cmp     rdx, 8
0x180445ecf  jb      short loc_180445F0A
0x180445ed1  lea     rdx, ds:2[rdx*2]
0x180445ed9  mov     rcx, [rbp+57h+Block]; Block
0x180445edd  mov     rax, rcx
0x180445ee0  cmp     rdx, 1000h
0x180445ee7  jb      short loc_180445F05
0x180445ee9  add     rdx, 27h ; '''
0x180445eed  mov     rcx, [rcx-8]
0x180445ef1  sub     rax, rcx
0x180445ef4  add     rax, 0FFFFFFFFFFFFFFF8h
0x180445ef8  cmp     rax, 1Fh
0x180445efc  jbe     short loc_180445F05
0x180445efe  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180445f05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180445f0a  lea     r8, aS_2; "s"
0x180445f11  lea     rdx, [rbp+57h+Src]; Src
0x180445f15  lea     rcx, [rbp+57h+Block]; void *
0x180445f19  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180445f1e  mov     rdi, rax
0x180445f21  lea     rax, [rbp+57h+Src]
0x180445f25  cmp     rax, rdi
0x180445f28  jz      short loc_180445F51
0x180445f2a  lea     rcx, [rbp+57h+Src]
0x180445f2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180445f33  movups  xmm0, xmmword ptr [rdi]
0x180445f36  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180445f3a  movups  xmm1, xmmword ptr [rdi+10h]
0x180445f3e  movups  [rbp+57h+var_38], xmm1
0x180445f42  mov     [rdi+10h], rsi
0x180445f46  mov     qword ptr [rdi+18h], 7
0x180445f4e  mov     [rdi], si
0x180445f51  mov     rdx, [rbp+57h+var_58]
0x180445f55  cmp     rdx, 8
0x180445f59  jb      short loc_180445F94
0x180445f5b  lea     rdx, ds:2[rdx*2]
0x180445f63  mov     rcx, [rbp+57h+Block]; Block
0x180445f67  mov     rax, rcx
  ... truncated ...
```

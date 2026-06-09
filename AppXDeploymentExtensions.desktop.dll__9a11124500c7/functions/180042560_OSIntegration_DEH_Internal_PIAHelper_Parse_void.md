# OSIntegration::DEH::Internal::PIAHelper::Parse(void)

- ea: `0x180042560`
- end: `0x180043ae6`
- name: `?Parse@PIAHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `5510`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::PIAHelper *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006970`
- `0x1800090cc`
- `0x180012fc8`
- `0x180014260`
- `0x180017640`
- `0x180017ba0`
- `0x18001adb4`
- `0x1800353c0`
- `0x180042560`
- `0x180061ca8`
- `0x180069eb4`
- `0x18007e124`
- `0x180082fcc`
- `0x180083000`
- `0x18008306c`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800af220`
- `0x1800af6f8`
- `0x1800ba45d`
- `0x1800ba475`
- `0x1800c1468`
- `0x1800e58b8`
- `0x1800e5a0c`
- `0x1800e5c70`
- `0x1801ac010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180042d76`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180042d76`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180042d29`
- `OLEAUT32!__imp_SysFreeString` at `0x180042e7b`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x180042613`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x180042666`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x180042613`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x180042666`

## string_xrefs

- `0x180042d16`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180042dfc`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180042715`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180042746`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x1800425a1`: `Microsoft.classicAppCompat_8wekyb3d8bbwe`
- `0x180043666`: `onecore\admin\appmodel\Common\Utilities.hpp`
- `0x180043799`: `onecore\admin\appmodel\Common\Utilities.hpp`
- `0x180042680`: `onecore\admin\appmodel\common\metadata.cpp`
- `0x18004301c`: `FolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::Internal::PIAHelper::Parse(OSIntegration::DEH::Internal::PIAHelper *this)
{
  int v2; // eax
  signed int AttributeValueStringFromQuery; // ebx
  __int64 v5; // rsi
  int SystemMetadataPathForPackage; // eax
  void *v7; // rdi
  unsigned int v8; // eax
  const struct std::nothrow_t *v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  __int64 v11; // rdx
  signed int *v12; // r12
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // r13
  wil::details::in1diag3 *v17; // rcx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  unsigned __int64 v21; // r9
  const struct std::nothrow_t *v22; // rdx
  void *v23; // r9
  __int64 v24; // rcx
  _WORD *v25; // rax
  unsigned int v26; // r15d
  __int64 v27; // r13
  wil::details::in1diag3 *v28; // rcx
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rdx
  int v32; // eax
  signed int v33; // r8d
  int v34; // eax
  unsigned __int16 *v35; // rsi
  __int64 v36; // rdx
  unsigned __int16 *v37; // r13
  __int64 v38; // rdx
  unsigned __int16 *v39; // r12
  __int64 v40; // rdx
  unsigned __int16 *v41; // r15
  __int64 v42; // rdx
  unsigned __int16 *v43; // r14
  __int64 v44; // rdx
  __int64 v45; // rdx
  unsigned __int16 *v46; // rdi
  int PIAFiles; // eax
  struct IXMLDOMNodeListVtbl *v48; // rbx
  wil::details::in1diag3 *v49; // rcx
  __int64 v50; // r9
  __int64 v51; // rdx
  __int64 v52; // rcx
  const OLECHAR *v53; // rax
  signed int v54; // eax
  __int64 (__fastcall *v55)(_QWORD, struct IXMLDOMNodeListVtbl *, unsigned __int64 *); // rdi
  int v56; // eax
  wil::details::in1diag3 *v57; // rcx
  __int64 v58; // rdx
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rcx
  __int64 v61; // rdx
  unsigned __int16 *v62; // rcx
  unsigned __int16 *v63; // rcx
  unsigned __int16 *v64; // rcx
  unsigned __int16 *v65; // rcx
  unsigned __int16 *v66; // rcx
  int v67; // eax
  int v68; // ecx
  struct IXMLDOMElement **v69; // r9
  int ElementFromNodeList; // eax
  int PolicyManifestAttribute; // eax
  OSIntegration::DEH::Internal::PIAHelper *v72; // rcx
  int v73; // eax
  OSIntegration::DEH::Internal::PIAHelper *v74; // rcx
  signed int v75; // r13d
  int v76; // eax
  OSIntegration::DEH::Internal::PIAHelper *v77; // rcx
  signed int v78; // r12d
  int v79; // eax
  OSIntegration::DEH::Internal::PIAHelper *v80; // rcx
  signed int v81; // r15d
  int v82; // eax
  OSIntegration::DEH::Internal::PIAHelper *v83; // rcx
  signed int v84; // r14d
  int v85; // eax
  signed int v86; // edi
  int PolicyFiles; // eax
  const struct std::nothrow_t *v88; // rdx
  __int64 v89; // rdx
  const struct std::nothrow_t *v90; // rdx
  const struct std::nothrow_t *v91; // rdx
  const struct std::nothrow_t *v92; // rdx
  const struct std::nothrow_t *v93; // rdx
  const struct std::nothrow_t *v94; // rdx
  const struct std::nothrow_t *v95; // rdx
  OSIntegration::DEH::Internal::PIAHelper *v96; // rbx
  unsigned __int64 v97; // rdx
  unsigned __int64 v98; // rcx
  unsigned __int64 v99; // rax
  OSIntegration::DEH::Internal::PIAHelper *v100; // rax
  const void *v101; // rdx
  const struct std::nothrow_t *v102; // rdx
  __int64 v103; // rcx
  const struct std::nothrow_t *v104; // rdx
  void *v105; // rcx
  void *v106; // rcx
  void *v107; // rcx
  void *v108; // rcx
  void *v109; // rcx
  void *v110; // rcx
  void *v111; // rcx
  void *v112; // rcx
  void *v113; // rcx
  void *v114; // rcx
  const struct std::nothrow_t *v115; // rdx
  unsigned int v116; // [rsp+28h] [rbp-E0h]
  int v117; // [rsp+28h] [rbp-E0h]
  int v118; // [rsp+28h] [rbp-E0h]
  int v119; // [rsp+28h] [rbp-E0h]
  int v120; // [rsp+28h] [rbp-E0h]
  int v121; // [rsp+28h] [rbp-E0h]
  int v122; // [rsp+28h] [rbp-E0h]
  int v123; // [rsp+28h] [rbp-E0h]
  int v124; // [rsp+28h] [rbp-E0h]
  int v125; // [rsp+28h] [rbp-E0h]
  int v126; // [rsp+28h] [rbp-E0h]
  int v127; // [rsp+28h] [rbp-E0h]
  int v128; // [rsp+28h] [rbp-E0h]
  int v129; // [rsp+28h] [rbp-E0h]
  int *v130; // [rsp+30h] [rbp-D8h]
  int *v131; // [rsp+30h] [rbp-D8h]
  int *v132; // [rsp+30h] [rbp-D8h]
  int *v133; // [rsp+30h] [rbp-D8h]
  int *v134; // [rsp+30h] [rbp-D8h]
  int *v135; // [rsp+30h] [rbp-D8h]
  struct IXMLDOMNodeList v136; // [rsp+58h] [rbp-B0h] BYREF
  int v137[2]; // [rsp+60h] [rbp-A8h] BYREF
  void *Src; // [rsp+68h] [rbp-A0h]
  __int128 v139; // [rsp+78h] [rbp-90h] BYREF
  int v140; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v141[2]; // [rsp+98h] [rbp-70h] BYREF
  int v142; // [rsp+A8h] [rbp-60h]
  unsigned __int16 *v143[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v144; // [rsp+C0h] [rbp-48h]
  unsigned __int16 *v145[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v146; // [rsp+D8h] [rbp-30h]
  unsigned __int16 *v147[2]; // [rsp+E0h] [rbp-28h] BYREF
  int v148; // [rsp+F0h] [rbp-18h]
  void **v149; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int *v150; // [rsp+100h] [rbp-8h]
  char *v151; // [rsp+108h] [rbp+0h]
  unsigned __int16 *v152[2]; // [rsp+110h] [rbp+8h] BYREF
  int v153; // [rsp+120h] [rbp+18h]
  __int128 v154; // [rsp+128h] [rbp+20h] BYREF
  int v155; // [rsp+138h] [rbp+30h]
  __int128 v156; // [rsp+140h] [rbp+38h]
  int v157; // [rsp+150h] [rbp+48h]
  __int128 v158; // [rsp+158h] [rbp+50h]
  int v159; // [rsp+168h] [rbp+60h]
  __int128 v160; // [rsp+170h] [rbp+68h]
  int v161; // [rsp+180h] [rbp+78h]
  __int128 v162; // [rsp+188h] [rbp+80h]
  int v163; // [rsp+198h] [rbp+90h]
  _QWORD v164[3]; // [rsp+1A0h] [rbp+98h] BYREF
  char v165; // [rsp+1B8h] [rbp+B0h]
  _QWORD v166[3]; // [rsp+1C0h] [rbp+B8h] BYREF
  char v167; // [rsp+1D8h] [rbp+D0h]
  unsigned __int16 *v168[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  int v169; // [rsp+1F8h] [rbp+F0h]
  __int128 v170; // [rsp+208h] [rbp+100h] BYREF
  int v171; // [rsp+218h] [rbp+110h]
  __int128 v172; // [rsp+220h] [rbp+118h]
  int v173; // [rsp+230h] [rbp+128h]
  __int128 v174; // [rsp+238h] [rbp+130h]
  int v175; // [rsp+248h] [rbp+140h]
  __int128 v176; // [rsp+250h] [rbp+148h]
  int v177; // [rsp+260h] [rbp+158h]
  __int128 v178; // [rsp+268h] [rbp+160h]
  int v179; // [rsp+278h] [rbp+170h]
  __int128 v180; // [rsp+288h] [rbp+180h] BYREF
  int v181; // [rsp+298h] [rbp+190h]
  __int128 v182; // [rsp+2A0h] [rbp+198h]
  int v183; // [rsp+2B0h] [rbp+1A8h]
  __int128 v184; // [rsp+2B8h] [rbp+1B0h]
  int v185; // [rsp+2C8h] [rbp+1C0h]
  __int128 v186; // [rsp+2D0h] [rbp+1C8h]
  int v187; // [rsp+2E0h] [rbp+1D8h]
  __int128 v188; // [rsp+2E8h] [rbp+1E0h]
  int v189; // [rsp+2F8h] [rbp+1F0h]
  wil::details::in1diag3 *retaddr; // [rsp+3A0h] [rbp+298h]
  OSIntegration::DEH::Internal::PIAHelper *v192; // [rsp+3A8h] [rbp+2A0h]
  OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *v193; // [rsp+3B0h] [rbp+2A8h] BYREF
  int v194; // [rsp+3B8h] [rbp+2B0h] BYREF
  unsigned __int64 v195; // [rsp+3C0h] [rbp+2B8h] BYREF

  *(_QWORD *)&v139 = L"Microsoft.classicAppCompat_8wekyb3d8bbwe";
  *((_QWORD *)&v139 + 1) = 40;
  v2 = OSIntegration::Package::EnforceCustomCapabilityForPackageRuntimeFamily(*((OSIntegration::Package **)this + 3));
  AttributeValueStringFromQuery = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)v2,
      v116);
    return (unsigned int)AttributeValueStringFromQuery;
  }
  Src = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 3) + 224LL);
  LODWORD(v193) = 0;
  SystemMetadataPathForPackage = GetSystemMetadataPathForPackage(v5, &v193, 0);
  AttributeValueStringFromQuery = SystemMetadataPathForPackage;
  if ( SystemMetadataPathForPackage == 122 )
  {
    v7 = operator new[](saturated_mul((unsigned int)v193, 2u));
    v8 = GetSystemMetadataPathForPackage(v5, &v193, v7);
    if ( !v8 )
    {
      Src = v7;
      operator delete(0, v9);
      goto LABEL_12;
    }
    AttributeValueStringFromQuery = wil::details::in1diag3::Return_Win32(
                                      retaddr,
                                      (void *)0x26,
                                      (unsigned int)"onecore\\admin\\appmodel\\common\\metadata.cpp",
                                      (const char *)v8,
                                      v116);
    operator delete(v7, v10);
  }
  else if ( SystemMetadataPathForPackage > 0 )
  {
    AttributeValueStringFromQuery = (unsigned __int16)SystemMetadataPathForPackage | 0x80070000;
  }
  if ( AttributeValueStringFromQuery < 0 )
  {
    v11 = 403;
LABEL_32:
    v21 = (unsigned int)AttributeValueStringFromQuery;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)v21,
      v116);
    goto LABEL_314;
  }
LABEL_12:
  v12 = (signed int *)((char *)this + 64);
  v150 = (unsigned int *)((char *)this + 64);
  v149 = &Common::StringBufferBuilder::`vftable';
  v151 = (char *)this + 64;
  v13 = 0x3FFFFFFF;
  v14 = L"\\\\?\\";
  while ( 1 )
  {
    LODWORD(v193) = -2147024809;
    if ( !*v14 )
      break;
    ++v14;
    if ( !--v13 )
    {
      v15 = 0;
      AttributeValueStringFromQuery = -2147024809;
      goto LABEL_17;
    }
  }
  AttributeValueStringFromQuery = 0;
  v15 = 0x3FFFFFFF - v13;
LABEL_17:
  if ( AttributeValueStringFromQuery < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v116);
LABEL_31:
    v11 = 406;
    goto LABEL_32;
  }
  v16 = (unsigned int)*v12;
  AttributeValueStringFromQuery = ~v15 < (unsigned int)v16 ? 0x80070216 : 0;
  v17 = retaddr;
  if ( (unsigned int)v16 > ~v15 )
  {
    v18 = (unsigned int)AttributeValueStringFromQuery;
    v19 = 263;
LABEL_21:
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v18,
      v116);
    goto LABEL_27;
  }
  if ( v15 + (unsigned int)v16 <= 0x3FFFFFFF )
  {
    v20 = Common::StringBufferBuilder::SetLength((Common::StringBufferBuilder *)&v149, v15 + (unsigned int)v16);
    AttributeValueStringFromQuery = v20;
    v17 = retaddr;
    if ( v20 < 0 )
    {
      v18 = (unsigned int)v20;
      v19 = 269;
      goto LABEL_21;
    }
    AttributeValueStringFromQuery = 0;
  }
  else
  {
    AttributeValueStringFromQuery = -2147023613;
  }
LABEL_27:
  if ( AttributeValueStringFromQuery >= 0 )
  {
    memcpy_0((void *)(*((_QWORD *)v150 + 1) + 2 * v16), L"\\\\?\\", 2LL * v15);
    AttributeValueStringFromQuery = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v116);
  }
  if ( AttributeValueStringFromQuery < 0 )
    goto LABEL_31;
  v23 = Src;
  if ( !Src )
  {
    AttributeValueStringFromQuery = -2147024809;
LABEL_43:
    v26 = 0;
    goto LABEL_44;
  }
  v24 = 0x3FFFFFFF;
  v25 = Src;
  while ( *v25 )
  {
    ++v25;
    if ( !--v24 )
    {
      AttributeValueStringFromQuery = -2147024809;
      v26 = 0;
      goto LABEL_40;
    }
  }
  AttributeValueStringFromQuery = 0;
  v26 = 0x3FFFFFFF - v24;
LABEL_40:
  if ( AttributeValueStringFromQuery < 0 )
    goto LABEL_43;
LABEL_44:
  if ( AttributeValueStringFromQuery < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v116);
LABEL_59:
    v11 = 407;
    goto LABEL_32;
  }
  v27 = *v150;
  AttributeValueStringFromQuery = ~v26 < (unsigned int)v27 ? 0x80070216 : 0;
  v28 = retaddr;
  if ( (unsigned int)v27 <= ~v26 )
  {
    v31 = v26 + (unsigned int)v27;
    if ( (unsigned int)v31 > 0x3FFFFFFF )
    {
      AttributeValueStringFromQuery = -2147023613;
      goto LABEL_55;
    }
    v32 = ((__int64 (__fastcall *)(void ***, __int64, __int64))*v149)(&v149, v31, 0x3FFFFFFF);
    AttributeValueStringFromQuery = v32;
    v28 = retaddr;
    if ( v32 >= 0 )
    {
      AttributeValueStringFromQuery = 0;
      goto LABEL_54;
    }
    v29 = (unsigned int)v32;
    v30 = 269;
  }
  else
  {
    v29 = (unsigned int)AttributeValueStringFromQuery;
    v30 = 263;
  }
  wil::details::in1diag3::_Log_Hr(
    v28,
    (void *)v30,
    (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)v29,
    v116);
LABEL_54:
  v23 = Src;
LABEL_55:
  if ( AttributeValueStringFromQuery >= 0 )
  {
    memcpy_0((void *)(*((_QWORD *)v150 + 1) + 2 * v27), v23, 2LL * v26);
    AttributeValueStringFromQuery = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v116);
  }
  if ( AttributeValueStringFromQuery < 0 )
    goto LABEL_59;
  v33 = *v12;
  do
  {
    if ( --v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)0x80070057LL,
        v116);
      operator delete(Src, v115);
      return 2147942487LL;
    }
  }
  while ( *(_WORD *)(*((_QWORD *)this + 9) + 2LL * v33) != 92 );
  v34 = Common::StringBuffer::SetValue(
          (OSIntegration::DEH::Internal::PIAHelper *)((char *)this + 88),
          *((const unsigned __int16 **)this + 9),
          v33);
  AttributeValueStringFromQuery = v34;
  if ( v34 < 0 )
  {
    v21 = (unsigned int)v34;
    v11 = 412;
    goto LABEL_33;
  }
  *(_OWORD *)v168 = 0;
  v169 = 0;
  *(_OWORD *)v141 = 0;
  v142 = 0;
  *(_OWORD *)v145 = 0;
  v146 = 0;
  *(_OWORD *)v147 = 0;
  v148 = 0;
  *(_OWORD *)v152 = 0;
  v153 = 0;
  *(_OWORD *)v143 = 0;
  v144 = 0;
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C91A0,
                                    (const unsigned __int16 *)v168,
                                    (struct Common::StringBuffer *)&v195,
                                    v130);
  v35 = v168[1];
  if ( AttributeValueStringFromQuery < 0 )
  {
    v36 = 379;
    goto LABEL_302;
  }
  if ( !(_DWORD)v195 || !v168[1] )
  {
    AttributeValueStringFromQuery = -2146958844;
    v36 = 380;
LABEL_302:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v117);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v129);
    v111 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v111 )
      operator delete(v111, v22);
    v112 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v112 )
      operator delete(v112, v22);
    v113 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v113 )
      operator delete(v113, v22);
    v114 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v114 )
      operator delete(v114, v22);
    v66 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v66 )
    {
LABEL_312:
      if ( v35 )
        operator delete(v35, v22);
      goto LABEL_314;
    }
LABEL_311:
    operator delete(v66, v22);
    goto LABEL_312;
  }
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C9180,
                                    (const unsigned __int16 *)v141,
                                    (struct Common::StringBuffer *)&v195,
                                    v131);
  v37 = v141[1];
  if ( AttributeValueStringFromQuery < 0 )
  {
    v38 = 379;
    goto LABEL_293;
  }
  if ( !(_DWORD)v195 || !v141[1] )
  {
    AttributeValueStringFromQuery = -2146958844;
    v38 = 380;
LABEL_293:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v118);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v128);
    v108 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v108 )
      operator delete(v108, v22);
    v109 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v109 )
      operator delete(v109, v22);
    v110 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v110 )
      operator delete(v110, v22);
    v65 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v65 )
      goto LABEL_138;
    goto LABEL_137;
  }
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C9168,
                                    (const unsigned __int16 *)v145,
                                    (struct Common::StringBuffer *)&v195,
                                    v132);
  v39 = v145[1];
  if ( AttributeValueStringFromQuery < 0 )
  {
    v40 = 379;
    goto LABEL_286;
  }
  if ( !(_DWORD)v195 || !v145[1] )
  {
    AttributeValueStringFromQuery = -2146958844;
    v40 = 380;
LABEL_286:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v119);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v127);
    v106 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v106 )
      operator delete(v106, v22);
    v107 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v107 )
      operator delete(v107, v22);
    v64 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v64 )
      goto LABEL_135;
    goto LABEL_134;
  }
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C9128,
                                    (const unsigned __int16 *)v147,
                                    (struct Common::StringBuffer *)&v195,
                                    v133);
  v41 = v147[1];
  if ( AttributeValueStringFromQuery < 0 )
  {
    v42 = 379;
    goto LABEL_281;
  }
  if ( !(_DWORD)v195 || !v147[1] )
  {
    AttributeValueStringFromQuery = -2146958844;
    v42 = 380;
LABEL_281:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v120);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v126);
    v105 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v105 )
      operator delete(v105, v22);
    v63 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v63 )
      goto LABEL_132;
    goto LABEL_131;
  }
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C9140,
                                    (const unsigned __int16 *)v152,
                                    (struct Common::StringBuffer *)&v195,
                                    v134);
  v43 = v152[1];
  if ( AttributeValueStringFromQuery < 0 )
  {
    v44 = 379;
    goto LABEL_279;
  }
  if ( !(_DWORD)v195 || !v152[1] )
  {
    AttributeValueStringFromQuery = -2146958844;
    v44 = 380;
LABEL_279:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v121);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v125);
    v62 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    goto LABEL_276;
  }
  LODWORD(v195) = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"*[local-name()='PrimaryInteropAssemblies']",
                                    *((const unsigned __int16 **)this + 2),
                                    (struct IXMLDOMElement *)&stru_1801C90B8,
                                    (const unsigned __int16 *)v143,
                                    (struct Common::StringBuffer *)&v195,
                                    v135);
  if ( AttributeValueStringFromQuery < 0 )
  {
    v45 = 379;
    goto LABEL_275;
  }
  if ( !(_DWORD)v195 || (v46 = v143[1]) == 0 )
  {
    AttributeValueStringFromQuery = -2146958844;
    v45 = 380;
LABEL_275:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v122);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v124);
    v62 = v143[1];
LABEL_276:
    if ( !v62 )
      goto LABEL_129;
    goto LABEL_128;
  }
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  memset(v164, 0, sizeof(v164));
  v165 = 1;
  memset(v166, 0, sizeof(v166));
  v167 = 1;
  PIAFiles = OSIntegration::DEH::Internal::PIAHelper::GeneratePIAFiles(
               this,
               v35,
               v37,
               v39,
               v41,
               v43,
               v143[1],
               (struct OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v154);
  LODWORD(v195) = PIAFiles;
  if ( PIAFiles < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
      (const char *)(unsigned int)PIAFiles,
      v123);
LABEL_91:
    OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
    if ( v46 )
      operator delete(v46, v22);
    if ( v43 )
      operator delete(v43, v22);
    if ( v41 )
      operator delete(v41, v22);
    if ( v39 )
      operator delete(v39, v22);
    if ( v37 )
      operator delete(v37, v22);
    if ( v35 )
      operator delete(v35, v22);
    AttributeValueStringFromQuery = v195;
    goto LABEL_314;
  }
  v194 = 0;
  *(_QWORD *)v137 = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
  *(_QWORD *)&v139 = *((_QWORD *)this + 2);
  v48 = 0;
  v136.lpVtbl = 0;
  v195 = 0;
  if ( !(_QWORD)v139 )
  {
    v49 = retaddr;
    v50 = 2147942487LL;
    v51 = 36;
    goto LABEL_106;
  }
  SysFreeString(0);
  v48 = 0;
  v136.lpVtbl = 0;
  v52 = 0x7FFFFFFF;
  v53 = L"*[local-name()='PrimaryInteropAssemblies']/*[local-name()='Redirect']";
  while ( *v53 )
  {
    ++v53;
    if ( !--v52 )
      goto LABEL_110;
  }
  if ( (unsigned int)(0x7FFFFFFF - v52) > 0x3FFFFFFF )
  {
LABEL_110:
    v54 = -2147024809;
    goto LABEL_113;
  }
  v48 = (struct IXMLDOMNodeListVtbl *)SysAllocStringLen(
                                        L"*[local-name()='PrimaryInteropAssemblies']/*[local-name()='Redirect']",
                                        0x7FFFFFFF - (int)v52);
  v136.lpVtbl = v48;
  v54 = v48 == 0 ? 0x8007000E : 0;
LABEL_113:
  LODWORD(v193) = v54;
  v49 = retaddr;
  if ( v54 >= 0 )
  {
    v55 = *(__int64 (__fastcall **)(_QWORD, struct IXMLDOMNodeListVtbl *, unsigned __int64 *))(*(_QWORD *)v139 + 288LL);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v195);
    v56 = v55(v139, v48, &v195);
    LODWORD(v193) = v56;
    v57 = retaddr;
    if ( v56 >= 0 )
    {
      v56 = (*(__int64 (__fastcall **)(unsigned __int64, int *))(*(_QWORD *)v195 + 64LL))(v195, &v194);
      LODWORD(v193) = v56;
      v57 = retaddr;
      if ( v56 >= 0 )
      {
        v59 = v195;
        v195 = 0;
        *(_QWORD *)v137 = v59;
        goto LABEL_121;
      }
      v58 = 45;
    }
    else
    {
      v58 = 43;
    }
    wil::details::in1diag3::_Log_Hr(
      v57,
      (void *)v58,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v56,
      v123);
LABEL_121:
    v46 = v143[1];
    goto LABEL_122;
  }
  v50 = (unsigned int)v54;
  v51 = 39;
LABEL_106:
  wil::details::in1diag3::_Log_Hr(
    v49,
    (void *)v51,
    (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
    (const char *)v50,
    v123);
LABEL_122:
  v60 = v195;
  if ( v195 )
  {
    v195 = 0;
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  SysFreeString((BSTR)v48);
  AttributeValueStringFromQuery = (int)v193;
  if ( (int)v193 < 0 )
  {
    v61 = 446;
    goto LABEL_126;
  }
  v67 = v194;
  if ( v194 <= 0 )
  {
LABEL_240:
    v193 = (OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)operator new(0xB8u);
    v193 = (OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::AssemblyInfo(
                                                                      v193,
                                                                      &v154);
    if ( !v193 )
    {
      AttributeValueStringFromQuery = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\admin\\appmodel\\Common\\Utilities.hpp",
        (const char *)0x8007000ELL,
        v123);
LABEL_273:
      v61 = 483;
LABEL_126:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)AttributeValueStringFromQuery,
        v123);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
      if ( !v46 )
        goto LABEL_129;
      v62 = v46;
LABEL_128:
      operator delete(v62, v22);
LABEL_129:
      if ( !v43 )
      {
LABEL_132:
        if ( !v41 )
        {
LABEL_135:
          if ( !v39 )
          {
LABEL_138:
            if ( !v37 )
              goto LABEL_312;
            v66 = v37;
            goto LABEL_311;
          }
          v65 = v39;
LABEL_137:
          operator delete(v65, v22);
          goto LABEL_138;
        }
        v64 = v41;
LABEL_134:
        operator delete(v64, v22);
        goto LABEL_135;
      }
      v63 = v43;
LABEL_131:
      operator delete(v63, v22);
      goto LABEL_132;
    }
    v96 = this;
    v97 = *((_QWORD *)this + 16) + 1LL;
    v98 = *((_QWORD *)this + 15);
    if ( v97 > v98 )
    {
      if ( v98 == 0x3FFFFFFF )
      {
        AttributeValueStringFromQuery = -2147483637;
LABEL_253:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"onecore\\admin\\appmodel\\Common\\Utilities.hpp",
          (const char *)(unsigned int)AttributeValueStringFromQuery,
          v123);
        OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::`scalar deleting destructor'(v193, 1u);
        goto LABEL_273;
      }
      if ( v98 )
        v99 = ((3 * v98) >> 1) + 1;
      else
        v99 = 16;
      if ( v97 > v99 )
        v99 = *((_QWORD *)this + 16) + 1LL;
      if ( v99 > 0x3FFFFFFF )
        v99 = 0x3FFFFFFF;
      v195 = v99;
      v100 = (OSIntegration::DEH::Internal::PIAHelper *)operator new[](
                                                          8 * v99,
                                                          (const struct std::nothrow_t *)&std::nothrow);
      v192 = v100;
      if ( !v100 )
      {
        AttributeValueStringFromQuery = -2147024882;
        goto LABEL_253;
      }
      v101 = (const void *)*((_QWORD *)v96 + 14);
      if ( v101 )
      {
        memmove_0(v100, v101, 8LL * *((_QWORD *)v96 + 16));
        operator delete(*((void **)v96 + 14), v102);
        v100 = v192;
      }
      *((_QWORD *)v96 + 14) = v100;
      *((_QWORD *)v96 + 15) = v195;
    }
    *(_QWORD *)(*((_QWORD *)v96 + 14) + 8LL * (*((_QWORD *)v96 + 16))++) = v193;
    v103 = *(_QWORD *)v137;
    if ( *(_QWORD *)v137 )
    {
      *(_QWORD *)v137 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
    }
    Common::Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>(v166);
    Common::Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>(v164);
    OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles::~AssemblyFiles((OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v154);
    if ( v46 )
      operator delete(v46, v104);
    if ( v43 )
      operator delete(v43, v104);
    if ( v41 )
      operator delete(v41, v104);
    if ( v39 )
      operator delete(v39, v104);
    if ( v37 )
      operator delete(v37, v104);
    if ( v35 )
      operator delete(v35, v104);
    operator delete(Src, v104);
    return 0;
  }
  v68 = 0;
  while ( 1 )
  {
    LODWORD(v193) = v68;
    if ( v68 >= v67 )
      goto LABEL_240;
    v136.lpVtbl = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
    ElementFromNodeList = Common::Xml::GetElementFromNodeList((Common::Xml *)(unsigned int)v193, v137[0], &v136, v69);
    LODWORD(v195) = ElementFromNodeList;
    if ( ElementFromNodeList < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)ElementFromNodeList,
        v123);
      goto LABEL_239;
    }
    v139 = 0;
    v140 = 0;
    PolicyManifestAttribute = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
                                0,
                                (struct IXMLDOMElement *)v136.lpVtbl,
                                L"Version",
                                (struct Common::StringBuffer *)&v139);
    LODWORD(v195) = PolicyManifestAttribute;
    if ( PolicyManifestAttribute < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)PolicyManifestAttribute,
        v123);
      goto LABEL_158;
    }
    v73 = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
            v72,
            (struct IXMLDOMElement *)v136.lpVtbl,
            (const unsigned __int16 *)&stru_1801C9180,
            (struct Common::StringBuffer *)v141);
    v75 = v73;
    if ( v73 < 0 )
      break;
    v76 = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
            v74,
            (struct IXMLDOMElement *)v136.lpVtbl,
            (const unsigned __int16 *)&stru_1801C9168,
            (struct Common::StringBuffer *)v145);
    v78 = v76;
    if ( v76 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)v76,
        v123);
      if ( *((_QWORD *)&v139 + 1) )
        operator delete(*((void **)&v139 + 1), v94);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
      if ( v46 )
        operator delete(v46, v22);
      if ( v43 )
        operator delete(v43, v22);
      if ( v41 )
        operator delete(v41, v22);
      if ( v145[1] )
        operator delete(v145[1], v22);
      if ( v141[1] )
        operator delete(v141[1], v22);
      if ( v35 )
        operator delete(v35, v22);
      AttributeValueStringFromQuery = v78;
      goto LABEL_314;
    }
    v79 = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
            v77,
            (struct IXMLDOMElement *)v136.lpVtbl,
            (const unsigned __int16 *)&stru_1801C9128,
            (struct Common::StringBuffer *)v147);
    v81 = v79;
    if ( v79 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)v79,
        v123);
      if ( *((_QWORD *)&v139 + 1) )
        operator delete(*((void **)&v139 + 1), v93);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
      if ( v46 )
        operator delete(v46, v22);
      if ( v43 )
        operator delete(v43, v22);
      if ( v147[1] )
        operator delete(v147[1], v22);
      if ( v145[1] )
        operator delete(v145[1], v22);
      if ( v141[1] )
        operator delete(v141[1], v22);
      if ( v35 )
        operator delete(v35, v22);
      AttributeValueStringFromQuery = v81;
      goto LABEL_314;
    }
    v82 = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
            v80,
            (struct IXMLDOMElement *)v136.lpVtbl,
            (const unsigned __int16 *)&stru_1801C9140,
            (struct Common::StringBuffer *)v152);
    v84 = v82;
    if ( v82 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)v82,
        v123);
      if ( *((_QWORD *)&v139 + 1) )
        operator delete(*((void **)&v139 + 1), v92);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
      if ( v46 )
        operator delete(v46, v22);
      if ( v152[1] )
        operator delete(v152[1], v22);
      if ( v147[1] )
        operator delete(v147[1], v22);
      if ( v145[1] )
        operator delete(v145[1], v22);
      if ( v141[1] )
        operator delete(v141[1], v22);
      if ( v35 )
        operator delete(v35, v22);
      AttributeValueStringFromQuery = v84;
      goto LABEL_314;
    }
    v85 = OSIntegration::DEH::Internal::PIAHelper::GetPolicyManifestAttribute(
            v83,
            (struct IXMLDOMElement *)v136.lpVtbl,
            L"FolderPath",
            (struct Common::StringBuffer *)v143);
    v86 = v85;
    if ( v85 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)v85,
        v123);
      if ( *((_QWORD *)&v139 + 1) )
        operator delete(*((void **)&v139 + 1), v91);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
      if ( v143[1] )
        operator delete(v143[1], v22);
      if ( v152[1] )
        operator delete(v152[1], v22);
      if ( v147[1] )
        operator delete(v147[1], v22);
      if ( v145[1] )
        operator delete(v145[1], v22);
      if ( v141[1] )
        operator delete(v141[1], v22);
      if ( v35 )
        operator delete(v35, v22);
      AttributeValueStringFromQuery = v86;
      goto LABEL_314;
    }
    v180 = 0;
    v181 = 0;
    v182 = 0;
    v183 = 0;
    v184 = 0;
    v185 = 0;
    v186 = 0;
    v187 = 0;
    v188 = 0;
    v189 = 0;
    v170 = 0;
    v171 = 0;
    v172 = 0;
    v173 = 0;
    v174 = 0;
    v175 = 0;
    v176 = 0;
    v177 = 0;
    v178 = 0;
    v179 = 0;
    v46 = v143[1];
    v43 = v152[1];
    v41 = v147[1];
    v39 = v145[1];
    v37 = v141[1];
    PolicyFiles = OSIntegration::DEH::Internal::PIAHelper::GeneratePolicyFiles(
                    this,
                    v35,
                    *((const unsigned __int16 **)&v139 + 1),
                    v141[1],
                    v145[1],
                    v147[1],
                    v152[1],
                    v143[1],
                    (struct OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v180,
                    (struct OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v170);
    LODWORD(v195) = PolicyFiles;
    if ( PolicyFiles < 0 )
    {
      v89 = 477;
LABEL_157:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v89,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
        (const char *)(unsigned int)PolicyFiles,
        v123);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles::~AssemblyFiles((OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v170);
      OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles::~AssemblyFiles((OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v180);
LABEL_158:
      if ( *((_QWORD *)&v139 + 1) )
        operator delete(*((void **)&v139 + 1), v90);
LABEL_239:
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
      goto LABEL_91;
    }
    PolicyFiles = Common::ArrayAdd<Common::Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>(
                    v164,
                    &v180);
    LODWORD(v195) = PolicyFiles;
    if ( PolicyFiles < 0 )
    {
      v89 = 478;
      goto LABEL_157;
    }
    PolicyFiles = Common::ArrayAdd<Common::Array<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::ContainerOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>,Common::ArrayOperations<OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles,Common::NoKey>>,OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles>(
                    v166,
                    &v170);
    LODWORD(v195) = PolicyFiles;
    if ( PolicyFiles < 0 )
    {
      v89 = 479;
      goto LABEL_157;
    }
    OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles::~AssemblyFiles((OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v170);
    OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles::~AssemblyFiles((OSIntegration::DEH::Internal::PIAHelper::AssemblyFiles *)&v180);
    if ( *((_QWORD *)&v139 + 1) )
      operator delete(*((void **)&v139 + 1), v88);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
    v68 = (_DWORD)v193 + 1;
    v67 = v194;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1CC,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\pia\\piahelper.cpp",
    (const char *)(unsigned int)v73,
    v123);
  if ( *((_QWORD *)&v139 + 1) )
    operator delete(*((void **)&v139 + 1), v95);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v136);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v137);
  OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo::~AssemblyInfo((OSIntegration::DEH::Internal::PIAHelper::AssemblyInfo *)&v154);
  if ( v46 )
    operator delete(v46, v22);
  if ( v43 )
    operator delete(v43, v22);
  if ( v41 )
    operator delete(v41, v22);
  if ( v39 )
    operator delete(v39, v22);
  if ( v141[1] )
    operator delete(v141[1], v22);
  if ( v35 )
    operator delete(v35, v22);
  AttributeValueStringFromQuery = v75;
LABEL_314:
  operator delete(Src, v22);
  return (unsigned int)AttributeValueStringFromQuery;
}

```

## disassembly

```asm
0x180042560  mov     rax, rsp
0x180042563  mov     [rax+8], rcx
0x180042567  push    rbp
0x180042568  push    rbx
0x180042569  push    rsi
0x18004256a  push    rdi
0x18004256b  push    r12
0x18004256d  push    r13
0x18004256f  push    r14
0x180042571  push    r15
0x180042573  lea     rbp, [rax-298h]
0x18004257a  sub     rsp, 358h
0x180042581  movaps  xmmword ptr [rax-58h], xmm6
0x180042585  movaps  xmmword ptr [rax-68h], xmm7
0x180042589  movaps  xmmword ptr [rax-78h], xmm8
0x18004258e  movaps  xmmword ptr [rax-88h], xmm9
0x180042596  movaps  xmmword ptr [rax-98h], xmm10
0x18004259e  mov     r14, rcx
0x1800425a1  lea     rax, aMicrosoftClass_0; "Microsoft.classicAppCompat_8wekyb3d8bbw"...
0x1800425a8  mov     qword ptr [rsp+390h+var_328+8], rax
0x1800425ad  mov     [rsp+390h+var_318], 28h ; '('
0x1800425b6  lea     rdx, [rsp+390h+var_328+8]
0x1800425bb  mov     rcx, [rcx+18h]; this
0x1800425bf  call    ?EnforceCustomCapabilityForPackageRuntimeFamily@Package@OSIntegration@@QEBAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; OSIntegration::Package::EnforceCustomCapabilityForPackageRuntimeFamily(std::basic_string_view<ushort>)
0x1800425c4  mov     ebx, eax
0x1800425c6  xor     r13d, r13d
0x1800425c9  test    eax, eax
0x1800425cb  jns     short loc_1800425EF
0x1800425cd  mov     rcx, [rbp+298h]; this
0x1800425d4  mov     r9d, eax; char *
0x1800425d7  lea     r8, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800425de  mov     edx, 18Fh; void *
0x1800425e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800425e8  mov     eax, ebx
0x1800425ea  jmp     loc_180043AB4
0x1800425ef  mov     [rsp+390h+Src], r13
0x1800425f4  mov     rax, [r14+18h]
0x1800425f8  mov     rsi, [rax+0E0h]
0x1800425ff  mov     dword ptr [rbp+290h+arg_8], r13d
0x180042606  xor     r8d, r8d
0x180042609  lea     rdx, [rbp+290h+arg_8]
0x180042610  mov     rcx, rsi
0x180042613  call    cs:__imp_GetSystemMetadataPathForPackage
0x18004261a  nop     dword ptr [rax+rax+00h]
0x18004261f  mov     ebx, eax
0x180042621  cmp     eax, 7Ah ; 'z'
0x180042624  jz      short loc_180042635
0x180042626  test    eax, eax
0x180042628  jle     short loc_18004269B
0x18004262a  movzx   ebx, ax
0x18004262d  or      ebx, 80070000h
0x180042633  jmp     short loc_18004269B
0x180042635  mov     edx, dword ptr [rbp+290h+arg_8]
0x18004263b  mov     eax, 2
0x180042640  mul     rdx
0x180042643  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004264a  cmovb   rax, rcx
0x18004264e  mov     rcx, rax; unsigned __int64
0x180042651  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180042656  mov     rdi, rax
0x180042659  mov     r8, rax
0x18004265c  lea     rdx, [rbp+290h+arg_8]
0x180042663  mov     rcx, rsi
0x180042666  call    cs:__imp_GetSystemMetadataPathForPackage
0x18004266d  nop     dword ptr [rax+rax+00h]
0x180042672  test    eax, eax
0x180042674  jz      short loc_1800426A9
0x180042676  mov     rcx, [rbp+298h]; this
0x18004267d  mov     r9d, eax; char *
0x180042680  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\common\\metad"...
0x180042687  mov     edx, 26h ; '&'; void *
0x18004268c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042691  mov     ebx, eax
0x180042693  mov     rcx, rdi; void *
0x180042696  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004269b  test    ebx, ebx
0x18004269d  jns     short loc_1800426B5
0x18004269f  mov     edx, 193h
0x1800426a4  jmp     loc_1800427E0
0x1800426a9  mov     [rsp+390h+Src], rdi
0x1800426ae  xor     ecx, ecx; void *
0x1800426b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800426b5  lea     r12, [r14+40h]
0x1800426b9  mov     [rbp+290h+var_298], r12
0x1800426bd  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800426c4  mov     [rbp+290h+var_2A0], rax
0x1800426c8  mov     [rbp+290h+var_290], r12
0x1800426cc  mov     r8d, 3FFFFFFFh
0x1800426d2  mov     ecx, r8d
0x1800426d5  lea     rax, Src; "\\\\?\\"
0x1800426dc  mov     edi, 80070057h
0x1800426e1  mov     dword ptr [rbp+290h+arg_8], edi
0x1800426e7  cmp     [rax], r13w
0x1800426eb  jz      short loc_1800426FE
0x1800426ed  add     rax, 2
0x1800426f1  sub     rcx, 1
0x1800426f5  jnz     short loc_1800426DC
0x1800426f7  mov     r15, r13
0x1800426fa  mov     ebx, edi
0x1800426fc  jmp     short loc_180042707
0x1800426fe  mov     ebx, r13d
0x180042701  mov     r15, r8
0x180042704  sub     r15, rcx
0x180042707  mov     rcx, [rbp+298h]; this
0x18004270e  test    ebx, ebx
0x180042710  jns     short loc_18004272B
0x180042712  mov     r9d, ebx; char *
0x180042715  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\string"...
0x18004271c  mov     edx, 35h ; '5'; void *
0x180042721  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042726  jmp     loc_1800427DB
0x18004272b  mov     r13d, [r12]
0x18004272f  mov     eax, r15d
0x180042732  not     eax
0x180042734  cmp     eax, r13d
0x180042737  sbb     ebx, ebx
0x180042739  and     ebx, 80070216h
0x18004273f  mov     rcx, [rbp+298h]; this
0x180042746  lea     rsi, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\string"...
0x18004274d  cmp     r13d, eax
0x180042750  jbe     short loc_180042764
0x180042752  mov     r9d, ebx; char *
0x180042755  mov     edx, 107h; void *
0x18004275a  mov     r8, rsi; unsigned int
0x18004275d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042762  jmp     short loc_180042796
0x180042764  lea     edx, [r15+r13]; unsigned int
0x180042768  cmp     edx, r8d
0x18004276b  jbe     short loc_180042774
0x18004276d  mov     ebx, 80070503h
0x180042772  jmp     short loc_180042796
0x180042774  lea     rcx, [rbp+290h+var_2A0]; this
0x180042778  call    ?SetLength@StringBufferBuilder@Common@@UEAAJK@Z; Common::StringBufferBuilder::SetLength(ulong)
0x18004277d  mov     ebx, eax
0x18004277f  mov     rcx, [rbp+298h]
0x180042786  test    eax, eax
0x180042788  jns     short loc_180042794
0x18004278a  mov     r9d, eax
0x18004278d  mov     edx, 10Dh
0x180042792  jmp     short loc_18004275A
0x180042794  xor     ebx, ebx
0x180042796  mov     rcx, [rbp+298h]; this
0x18004279d  test    ebx, ebx
0x18004279f  jns     short loc_1800427B5
0x1800427a1  mov     r9d, ebx; char *
0x1800427a4  mov     r8, rsi; unsigned int
0x1800427a7  mov     edx, 79h ; 'y'; void *
0x1800427ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800427b1  xor     edx, edx
0x1800427b3  jmp     short loc_1800427D7
0x1800427b5  mov     r8d, r15d
0x1800427b8  add     r8, r8; Size
0x1800427bb  mov     rax, [rbp+290h+var_298]
0x1800427bf  mov     rcx, [rax+8]
0x1800427c3  lea     rcx, [rcx+r13*2]; void *
0x1800427c7  lea     rdx, Src; "\\\\?\\"
0x1800427ce  call    memcpy_0
0x1800427d3  xor     edx, edx
0x1800427d5  mov     ebx, edx
0x1800427d7  test    ebx, ebx
0x1800427d9  jns     short loc_1800427FB
0x1800427db  mov     edx, 196h; void *
0x1800427e0  mov     r9d, ebx; char *
0x1800427e3  lea     r8, aOnecoreAdminAp_29; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800427ea  mov     rcx, [rbp+298h]; this
0x1800427f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800427f6  jmp     loc_180043A7D
0x1800427fb  mov     r9, [rsp+390h+Src]
0x180042800  mov     r8d, 3FFFFFFFh
0x180042806  test    r9, r9
0x180042809  jz      short loc_180042835
0x18004280b  mov     ecx, r8d
0x18004280e  mov     rax, r9
0x180042811  cmp     [rax], dx
0x180042814  jz      short loc_180042827
0x180042816  add     rax, 2
0x18004281a  sub     rcx, 1
0x18004281e  jnz     short loc_180042811
0x180042820  mov     ebx, edi
0x180042822  mov     r15, rdx
0x180042825  jmp     short loc_18004282F
0x180042827  mov     ebx, edx
0x180042829  mov     r15, r8
0x18004282c  sub     r15, rcx
0x18004282f  test    ebx, ebx
0x180042831  js      short loc_180042837
0x180042833  jmp     short loc_18004283A
0x180042835  mov     ebx, edi
0x180042837  mov     r15, rdx
0x18004283a  mov     rcx, [rbp+298h]; this
0x180042841  test    ebx, ebx
0x180042843  jns     short loc_18004285A
0x180042845  mov     r9d, ebx; char *
0x180042848  mov     r8, rsi; unsigned int
0x18004284b  mov     edx, 35h ; '5'; void *
0x180042850  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042855  jmp     loc_18004290E
0x18004285a  mov     rax, [rbp+290h+var_298]
0x18004285e  mov     r13d, [rax]
0x180042861  mov     eax, r15d
0x180042864  not     eax
0x180042866  cmp     eax, r13d
0x180042869  sbb     ebx, ebx
0x18004286b  and     ebx, 80070216h
0x180042871  mov     rcx, [rbp+298h]; this
0x180042878  cmp     r13d, eax
0x18004287b  jbe     short loc_18004288F
0x18004287d  mov     r9d, ebx; char *
0x180042880  mov     edx, 107h; void *
0x180042885  mov     r8, rsi; unsigned int
0x180042888  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004288d  jmp     short loc_1800428CC
0x18004288f  lea     edx, [r15+r13]
0x180042893  cmp     edx, r8d
0x180042896  jbe     short loc_18004289F
0x180042898  mov     ebx, 80070503h
0x18004289d  jmp     short loc_1800428D1
0x18004289f  mov     rax, [rbp+290h+var_2A0]
0x1800428a3  lea     rcx, [rbp+290h+var_2A0]
0x1800428a7  mov     rax, [rax]
0x1800428aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428af  mov     ebx, eax
0x1800428b1  mov     rcx, [rbp+298h]
0x1800428b8  xor     r9d, r9d
0x1800428bb  test    eax, eax
0x1800428bd  jns     short loc_1800428C9
0x1800428bf  mov     r9d, eax
0x1800428c2  mov     edx, 10Dh
0x1800428c7  jmp     short loc_180042885
0x1800428c9  mov     ebx, r9d
0x1800428cc  mov     r9, [rsp+390h+Src]
0x1800428d1  mov     rcx, [rbp+298h]; this
0x1800428d8  test    ebx, ebx
0x1800428da  jns     short loc_1800428EE
0x1800428dc  mov     r9d, ebx; char *
0x1800428df  mov     r8, rsi; unsigned int
0x1800428e2  mov     edx, 79h ; 'y'; void *
0x1800428e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800428ec  jmp     short loc_18004290A
0x1800428ee  mov     r8d, r15d
0x1800428f1  add     r8, r8; Size
0x1800428f4  mov     rax, [rbp+290h+var_298]
0x1800428f8  mov     rcx, [rax+8]
0x1800428fc  lea     rcx, [rcx+r13*2]; void *
0x180042900  mov     rdx, r9; Src
0x180042903  call    memcpy_0
0x180042908  xor     ebx, ebx
0x18004290a  test    ebx, ebx
0x18004290c  jns     short loc_180042918
0x18004290e  mov     edx, 197h
0x180042913  jmp     loc_1800427E0
0x180042918  mov     r8d, [r12]
0x18004291c  dec     r8d; unsigned int
0x18004291f  test    r8d, r8d
0x180042922  js      loc_180043A8C
0x180042928  movsxd  rcx, r8d
0x18004292b  mov     rax, [r12+8]
0x180042930  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180042935  jnz     short loc_18004291C
0x180042937  lea     rcx, [r14+58h]; this
0x18004293b  mov     rdx, [r14+48h]; unsigned __int16 *
0x18004293f  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180042944  mov     ebx, eax
0x180042946  xor     edi, edi
0x180042948  test    eax, eax
0x18004294a  jns     short loc_180042959
0x18004294c  mov     r9d, eax
0x18004294f  mov     edx, 19Ch
0x180042954  jmp     loc_1800427E3
0x180042959  xorps   xmm0, xmm0
0x18004295c  movups  xmmword ptr [rbp+290h+var_1B0], xmm0
0x180042963  mov     [rbp+290h+var_1A0], edi
0x180042969  xorps   xmm10, xmm10
0x18004296d  movups  xmmword ptr [rbp+290h+var_300], xmm10
0x180042972  mov     [rbp+290h+var_2F0], edi
0x180042975  xorps   xmm9, xmm9
0x180042979  movups  xmmword ptr [rbp+290h+var_2D0], xmm9
0x18004297e  mov     [rbp+290h+var_2C0], edi
0x180042981  xorps   xmm8, xmm8
0x180042985  movups  xmmword ptr [rbp+290h+var_2B8], xmm8
0x18004298a  mov     [rbp+290h+var_2A8], edi
0x18004298d  xorps   xmm6, xmm6
0x180042990  movups  xmmword ptr [rbp+290h+var_288], xmm6
0x180042994  mov     [rbp+290h+var_278], edi
0x180042997  xorps   xmm7, xmm7
0x18004299a  movups  xmmword ptr [rbp+290h+var_2E8], xmm7
0x18004299e  mov     [rbp+290h+var_2D8], edi
0x1800429a1  mov     dword ptr [rbp+290h+arg_18], edi
0x1800429a7  lea     rax, [rbp+290h+arg_18]
0x1800429ae  mov     [rsp+390h+var_370], rax; int
0x1800429b3  lea     r9, [rbp+290h+var_1B0]; unsigned __int16 *
0x1800429ba  lea     r8, stru_1801C91A0; struct IXMLDOMElement *
0x1800429c1  mov     rdx, [r14+10h]; unsigned __int16 *
0x1800429c5  lea     r15, aLocalNamePrima_0; "*[local-name()='PrimaryInteropAssemblie"...
0x1800429cc  mov     rcx, r15; strIn
0x1800429cf  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@0AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800429d4  mov     ebx, eax
0x1800429d6  mov     rsi, [rbp+290h+var_1B0+8]
0x1800429dd  test    eax, eax
0x1800429df  jns     short loc_1800429EB
  ... truncated ...
```

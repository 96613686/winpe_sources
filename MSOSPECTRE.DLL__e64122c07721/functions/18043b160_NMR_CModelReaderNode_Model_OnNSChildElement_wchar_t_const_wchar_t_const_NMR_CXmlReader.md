# NMR::CModelReaderNode_Model::OnNSChildElement(wchar_t const *,wchar_t const *,NMR::CXmlReader *)

- ea: `0x18043b160`
- end: `0x18043c180`
- name: `?OnNSChildElement@CModelReaderNode_Model@NMR@@MEAAXPEB_W0PEAVCXmlReader@2@@Z`
- size: `4128`
- prototype: `void __fastcall(NMR::CModelReaderNode_Model *__hidden this, const wchar_t *, const wchar_t *, struct NMR::CXmlReader *)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180014a60`
- `0x180014b00`
- `0x180015630`
- `0x18003d030`
- `0x180052260`
- `0x180184da0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f890`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x18039f900`
- `0x1804169c0`
- `0x18041e0d0`
- `0x180420b40`
- `0x180422a90`
- `0x180424bf0`
- `0x180424f50`
- `0x18042eab0`
- `0x18042eb00`
- `0x18042ec60`
- `0x18043b160`
- `0x18043c4b0`
- `0x180446a10`
- `0x180447d80`
- `0x1804485b0`
- `0x1804488a0`
- `0x1804488c0`
- `0x180449390`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043b8e4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043b932`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bbfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bc4a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bcd5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bd38`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043b8e4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043b932`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bbfc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bc4a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bcd5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043bd38`

## string_xrefs

- `0x18043b196`: `http://schemas.microsoft.com/3dmanufacturing/core/2015/02`
- `0x18043ba66`: `Copyright`
- `0x18043bd98`: `http://schemas.microsoft.com/3dmanufacturing/2013/01`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall NMR::CModelReaderNode_Model::OnNSChildElement(
        NMR::CModelReaderNode_Model *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct NMR::CXmlReader *a4)
{
  __int64 v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  NMR::CProgressMonitor *v10; // rcx
  _QWORD *v11; // rdi
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  wchar_t v17; // ax
  __int64 v18; // rcx
  _DWORD *v19; // rax
  _DWORD *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  char *v24; // rcx
  _DWORD *v25; // rax
  _DWORD *v26; // r12
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // r8
  void **v31; // rcx
  __int64 v32; // rax
  unsigned __int64 v33; // rbx
  void **v34; // r13
  unsigned __int64 v35; // rcx
  void **v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rdi
  void **v39; // rbx
  void **v40; // rax
  void *v41; // rcx
  void *v42; // rcx
  void **v43; // rdx
  const wchar_t *v44; // r8
  __int64 v45; // rcx
  __int16 v46; // ax
  __int64 v47; // rbx
  __int64 v48; // r8
  __int64 v49; // rax
  void **v50; // rdx
  __int64 v51; // rcx
  void **v52; // rdx
  __int64 v53; // rcx
  void **v54; // rdx
  __int64 v55; // rcx
  void **v56; // rdx
  __int64 v57; // rcx
  void **v58; // rdx
  __int64 v59; // rcx
  __int16 v60; // ax
  void **v61; // rdx
  __int64 v62; // rcx
  void **v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rax
  void *v66; // rcx
  void *v67; // rcx
  void *v68; // rcx
  void *v69; // rcx
  __int64 v70; // rsi
  __int64 v71; // rcx
  __int64 v72; // rcx
  _DWORD *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  wchar_t v76; // ax
  _DWORD *v77; // rax
  __int64 v78; // rdx
  wchar_t v79; // ax
  __int64 v80; // rax
  __int64 v81; // [rsp+30h] [rbp-D0h]
  __int64 v82; // [rsp+38h] [rbp-C8h]
  void *Block[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v84; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v85; // [rsp+60h] [rbp-A0h]
  __int128 v86; // [rsp+68h] [rbp-98h] BYREF
  __int128 v87; // [rsp+78h] [rbp-88h] BYREF
  __int128 v88; // [rsp+88h] [rbp-78h] BYREF
  __int128 v89; // [rsp+98h] [rbp-68h] BYREF
  __int128 v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B8h] [rbp-48h]
  void **v92; // [rsp+C0h] [rbp-40h]
  __int128 v93; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v94; // [rsp+D8h] [rbp-28h]
  __int128 v95; // [rsp+E8h] [rbp-18h]
  __int128 v96; // [rsp+F8h] [rbp-8h]
  _QWORD v97[4]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v98; // [rsp+128h] [rbp+28h]
  __int128 v99; // [rsp+138h] [rbp+38h]
  _QWORD v100[4]; // [rsp+148h] [rbp+48h] BYREF
  void **v101; // [rsp+168h] [rbp+68h] BYREF
  char v102[24]; // [rsp+170h] [rbp+70h] BYREF
  void **v103; // [rsp+188h] [rbp+88h] BYREF
  char v104; // [rsp+190h] [rbp+90h] BYREF
  void **v105; // [rsp+1A8h] [rbp+A8h] BYREF
  char v106; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v108[16]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v109[32]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v110[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v111[32]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v112[32]; // [rsp+258h] [rbp+158h] BYREF
  char v113[32]; // [rsp+278h] [rbp+178h] BYREF
  char v114[32]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v115[32]; // [rsp+2B8h] [rbp+1B8h] BYREF
  char v116[32]; // [rsp+2D8h] [rbp+1D8h] BYREF
  char v117[32]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v118[32]; // [rsp+318h] [rbp+218h] BYREF
  void *v119[2]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v120; // [rsp+348h] [rbp+248h]
  unsigned __int64 v121; // [rsp+350h] [rbp+250h]
  void *v122[2]; // [rsp+358h] [rbp+258h] BYREF
  __int64 v123; // [rsp+368h] [rbp+268h]
  unsigned __int64 v124; // [rsp+370h] [rbp+270h]
  void *Src[2]; // [rsp+378h] [rbp+278h] BYREF
  __int64 v126; // [rsp+388h] [rbp+288h]
  unsigned __int64 v127; // [rsp+390h] [rbp+290h]
  void *v128[3]; // [rsp+398h] [rbp+298h] BYREF
  unsigned __int64 v129; // [rsp+3B0h] [rbp+2B0h]
  void *v130[3]; // [rsp+3B8h] [rbp+2B8h] BYREF
  unsigned __int64 v131; // [rsp+3D0h] [rbp+2D0h]
  _DWORD *v132; // [rsp+3D8h] [rbp+2D8h]
  _DWORD *v133; // [rsp+3E0h] [rbp+2E0h]

  v6 = 0;
  v7 = 0;
  while ( a3[v7] == aHttpSchemasMic_4[v7] && a3[v7 + 1] == aHttpSchemasMic_4[v7 + 1] )
  {
    v7 += 2;
    if ( v7 == 58 )
    {
      v8 = 0;
      while ( a2[v8] == aResources[v8] && a2[v8 + 1] == aResources[v8 + 1] )
      {
        v8 += 2;
        if ( v8 == 10 )
        {
          *((_BYTE *)this + 162) = 0;
          v9 = *((_QWORD *)this + 6);
          if ( v9 && !(unsigned __int8)NMR::CProgressMonitor::Progress(v9, a2, 7) )
          {
            NMR::CNMRException::CNMRException((NMR::CNMRException *)v109, 1);
            throw (NMR::CNMRException *)v109;
          }
          v10 = (NMR::CProgressMonitor *)*((_QWORD *)this + 6);
          if ( v10 )
            NMR::CProgressMonitor::PushLevel(v10, 0.2, 0.9);
          v95 = 0;
          v11 = (_QWORD *)((char *)this + 128);
          if ( *((_QWORD *)this + 19) >= 8u )
            v11 = (_QWORD *)*v11;
          v12 = operator new(0xA8u);
          v13 = v12;
          if ( v12 )
          {
            *(_OWORD *)v12 = 0;
            v12[2] = 1;
            v12[3] = 1;
            *(_QWORD *)v12 = &std::_Ref_count_obj2<NMR::CModelReaderNode100_Resources>::`vftable';
            v86 = 0;
            v14 = *((_QWORD *)this + 8);
            if ( v14 )
            {
              _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
              v14 = *((_QWORD *)this + 8);
            }
            *(_QWORD *)&v86 = *((_QWORD *)this + 7);
            *((_QWORD *)&v86 + 1) = v14;
            NMR::CModelReaderNode100_Resources::CModelReaderNode100_Resources(
              (_DWORD)v12 + 16,
              *((_QWORD *)this + 9),
              (unsigned int)&v86,
              (_DWORD)v11,
              *((_QWORD *)this + 6));
          }
          else
          {
            v13 = 0;
          }
          *(_QWORD *)&v95 = v13 + 4;
          *((_QWORD *)&v95 + 1) = v13;
          if ( *((_BYTE *)this + 160) )
          {
            NMR::CNMRException::CNMRException((NMR::CNMRException *)v110, 32871);
            throw (NMR::CNMRException *)v110;
          }
          (*(void (__fastcall **)(_DWORD *, struct NMR::CXmlReader *))(*((_QWORD *)v13 + 2) + 40LL))(v13 + 4, a4);
          v15 = *((_QWORD *)this + 6);
          if ( v15 )
            NMR::CProgressMonitor::PopLevel(v15, v108);
          *((_BYTE *)this + 160) = 1;
          goto LABEL_187;
        }
      }
      v16 = 0;
      do
      {
        v17 = a2[v16++];
        if ( v17 != aBuild[v16 - 1] )
        {
          v22 = -1;
          do
          {
            if ( a2[v22 + 1] != aMetadata_0[v22 + 1] )
              break;
            v22 += 2;
            if ( v22 == 9 )
            {
              *((_BYTE *)this + 162) = 0;
              v25 = operator new(0x98u);
              v26 = v25;
              if ( v25 )
              {
                *(_OWORD *)v25 = 0;
                v25[2] = 1;
                v25[3] = 1;
                *(_QWORD *)v25 = &std::_Ref_count_obj2<NMR::CModelReaderNode100_MetaData>::`vftable';
                v88 = 0;
                v27 = *((_QWORD *)this + 8);
                if ( v27 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
                  v27 = *((_QWORD *)this + 8);
                }
                *(_QWORD *)&v88 = *((_QWORD *)this + 7);
                *((_QWORD *)&v88 + 1) = v27;
                NMR::CModelReaderNode100_MetaData::CModelReaderNode100_MetaData(v25 + 4, &v88);
              }
              else
              {
                v26 = 0;
              }
              v132 = v26 + 4;
              v133 = v26;
              (*(void (__fastcall **)(_DWORD *, struct NMR::CXmlReader *))(*((_QWORD *)v26 + 2) + 40LL))(v26 + 4, a4);
              NMR::CModelReaderNode100_MetaData::getName(v26 + 4, v119);
              NMR::CModelReaderNode100_MetaData::getValue(v26 + 4, v130);
              if ( v120 )
              {
                v29 = std::wstring::wstring(v113, v119, v28);
                if ( (unsigned __int8)NMR::CModel::hasMetaData(*((_QWORD *)this + 9), v29) )
                {
                  v100[0] = 0;
                  v100[2] = 0;
                  v100[3] = 7;
                  std::wstring::assign(v100);
                  NMR::CModelReaderWarnings::addWarning(*((_QWORD *)this + 7), v100, 32860, 3);
                }
                v128[0] = 0;
                v128[2] = 0;
                v129 = 7;
                v122[0] = 0;
                v123 = 0;
                v124 = 7;
                if ( (unsigned __int8)NMR::decomposeIntoNamespaceAndName(v119, v128, v122) )
                {
                  Src[0] = 0;
                  v126 = 0;
                  v127 = 7;
                  if ( !(*(unsigned __int8 (__fastcall **)(struct NMR::CXmlReader *, void **, void **))(*(_QWORD *)a4 + 16LL))(
                          a4,
                          v128,
                          Src) )
                  {
                    NMR::CNMRException::CNMRException((NMR::CNMRException *)v115, 32942);
                    throw (NMR::CNMRException *)v115;
                  }
                  v81 = std::wstring::wstring(v114, v130, v30);
                  v82 = v126;
                  if ( v126 == 0x7FFFFFFFFFFFFFFELL )
                    std::_Xlen_string();
                  v31 = Src;
                  if ( v127 >= 8 )
                    v31 = (void **)Src[0];
                  v92 = v31;
                  Block[0] = 0;
                  v84 = 0;
                  v85 = 0;
                  v32 = v126 + 1;
                  v91 = v126 + 1;
                  v33 = 7;
                  v34 = Block;
                  if ( (unsigned __int64)(v126 + 1) > 7 )
                  {
                    v33 = v32 | 7;
                    if ( (v32 | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
                    {
                      if ( v33 < 0xA )
                        v33 = 10;
                    }
                    else
                    {
                      v33 = 0x7FFFFFFFFFFFFFFELL;
                    }
                    v35 = v33 + 1;
                    if ( v33 == -1 )
                      v35 = -1;
                    if ( v35 > 0x7FFFFFFFFFFFFFFFLL )
                      __scrt_throw_std_bad_array_new_length();
                    _mm_lfence();
                    v34 = (void **)std::_Allocate<16,std::_Default_allocate_traits,0>(2 * v35);
                    Block[0] = v34;
                    v32 = v91;
                    v31 = v92;
                  }
                  v84 = v32;
                  v85 = v33;
                  memcpy_0(v34, v31, 2 * v82);
                  *((_WORD *)v34 + v82) = 58;
                  *((_WORD *)v34 + v82 + 1) = 0;
                  v36 = v122;
                  if ( v124 >= 8 )
                    v36 = (void **)v122[0];
                  v37 = v84;
                  if ( v123 > v85 - v84 )
                  {
                    _mm_lfence();
                    v40 = (void **)std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
                                     Block,
                                     v123);
                  }
                  else
                  {
                    v38 = v84 + v123;
                    v84 += v123;
                    v39 = Block;
                    if ( v85 >= 8 )
                      v39 = (void **)Block[0];
                    memmove_0((char *)v39 + 2 * v37, v36, 2 * v123);
                    *((_WORD *)v39 + v38) = 0;
                    v40 = Block;
                  }
                  *(_QWORD *)&v93 = 0;
                  v94 = 0u;
                  v93 = *(_OWORD *)v40;
                  v94 = *((_OWORD *)v40 + 1);
                  v40[2] = 0;
                  v40[3] = (void *)7;
                  *(_WORD *)v40 = 0;
                  NMR::CModel::addMetaData(*((_QWORD *)this + 9), &v93, v81);
                  if ( v85 >= 8 )
                  {
                    v41 = Block[0];
                    if ( 2 * v85 + 2 >= 0x1000 )
                    {
                      v41 = (void *)*((_QWORD *)Block[0] - 1);
                      if ( (unsigned __int64)((char *)Block[0] - (char *)v41 - 8) > 0x1F )
                        _invalid_parameter_noinfo_noreturn();
                    }
                    operator delete(v41);
                  }
                  if ( v127 >= 8 )
                  {
                    v42 = Src[0];
                    if ( 2 * v127 + 2 >= 0x1000 )
                    {
                      v42 = (void *)*((_QWORD *)Src[0] - 1);
                      if ( (unsigned __int64)((char *)Src[0] - (char *)v42 - 8) > 0x1F )
                        _invalid_parameter_noinfo_noreturn();
                    }
                    operator delete(v42);
                  }
                }
                else
                {
                  v43 = v119;
                  v44 = (const wchar_t *)v119[0];
                  if ( v121 >= 8 )
                    v43 = (void **)v119[0];
                  v45 = 0;
                  while ( 1 )
                  {
                    v46 = *((_WORD *)v43 + v45++);
                    if ( v46 != aTitle[v45 - 1] )
                      break;
                    if ( v45 == 6 )
                    {
LABEL_91:
                      v47 = std::wstring::wstring(v116, v130, v44);
                      v49 = std::wstring::wstring(v117, v119, v48);
                      NMR::CModel::addMetaData(*((_QWORD *)this + 9), v49, v47);
                      goto LABEL_137;
                    }
                  }
                  v50 = v119;
                  if ( v121 >= 8 )
                    v50 = (void **)v119[0];
                  v51 = -1;
                  do
                  {
                    if ( *((_WORD *)v50 + v51 + 1) != aDesigner[v51 + 1] )
                      break;
                    v51 += 2;
                    if ( v51 == 9 )
                      goto LABEL_91;
                  }
                  while ( *((_WORD *)v50 + v51) == aDesigner[v51] );
                  v52 = v119;
                  if ( v121 >= 8 )
                    v52 = (void **)v119[0];
                  v53 = 0;
                  while ( *((_WORD *)v52 + v53) == aDescription[v53]
                       && *((_WORD *)v52 + v53 + 1) == aDescription[v53 + 1] )
                  {
                    v53 += 2;
                    if ( v53 == 12 )
                      goto LABEL_91;
                  }
                  v54 = v119;
                  if ( v121 >= 8 )
                    v54 = (void **)v119[0];
                  v55 = 0;
                  while ( *((_WORD *)v54 + v55) == aCopyright_0[v55]
                       && *((_WORD *)v54 + v55 + 1) == aCopyright_0[v55 + 1] )
                  {
                    v55 += 2;
                    if ( v55 == 10 )
                      goto LABEL_91;
                  }
                  v56 = v119;
                  if ( v121 >= 8 )
                    v56 = (void **)v119[0];
                  v57 = -1;
                  do
                  {
                    if ( *((_WORD *)v56 + v57 + 1) != aLicenseterms[v57 + 1] )
                      break;
                    v57 += 2;
                    if ( v57 == 13 )
                      goto LABEL_91;
                  }
                  while ( *((_WORD *)v56 + v57) == aLicenseterms[v57] );
                  v58 = v119;
                  if ( v121 >= 8 )
                    v58 = (void **)v119[0];
                  v59 = 0;
                  while ( 1 )
                  {
                    v60 = *((_WORD *)v58 + v59++);
                    if ( v60 != aRating[v59 - 1] )
                      break;
                    if ( v59 == 7 )
                      goto LABEL_91;
                  }
                  v61 = v119;
                  if ( v121 >= 8 )
                    v61 = (void **)v119[0];
                  v62 = -1;
                  do
                  {
                    if ( *((_WORD *)v61 + v62 + 1) != aCreationdate[v62 + 1] )
                      break;
                    v62 += 2;
                    if ( v62 == 13 )
                      goto LABEL_91;
                  }
                  while ( *((_WORD *)v61 + v62) == aCreationdate[v62] );
                  v63 = v119;
                  if ( v121 >= 8 )
                    v63 = (void **)v119[0];
                  v44 = L"ModificationDate";
                  v64 = -1;
                  do
                  {
                    if ( *((_WORD *)v63 + v64 + 1) != aModificationda[v64 + 1] )
                      break;
                    v64 += 2;
                    if ( v64 == 17 )
                      goto LABEL_91;
                  }
                  while ( *((_WORD *)v63 + v64) == aModificationda[v64] );
                  v65 = NMR::CNMRException::CNMRException((NMR::CNMRException *)&v101, 32946);
                  NMR::CModelReaderWarnings::addException(*((_QWORD *)this + 7), v65, 3);
                  v101 = &std::exception::`vftable';
                  _std_exception_destroy_0(v102);
                }
LABEL_137:
                if ( v124 >= 8 )
                {
                  v66 = v122[0];
                  if ( 2 * v124 + 2 >= 0x1000 )
                  {
                    v66 = (void *)*((_QWORD *)v122[0] - 1);
                    if ( (unsigned __int64)((char *)v122[0] - (char *)v66 - 8) > 0x1F )
                      _invalid_parameter_noinfo_noreturn();
                  }
                  operator delete(v66);
                }
                if ( v129 >= 8 )
                {
                  v67 = v128[0];
                  if ( 2 * v129 + 2 >= 0x1000 )
                  {
                    v67 = (void *)*((_QWORD *)v128[0] - 1);
                    if ( (unsigned __int64)((char *)v128[0] - (char *)v67 - 8) > 0x1F )
                      _invalid_parameter_noinfo_noreturn();
                  }
                  operator delete(v67);
                }
              }
              else
              {
                v97[0] = 0;
                v97[2] = 0;
                v97[3] = 7;
                std::wstring::assign(v97);
                NMR::CModelReaderWarnings::addWarning(*((_QWORD *)this + 7), v97, 32861, 3);
              }
              if ( v131 >= 8 )
              {
                v68 = v130[0];
                if ( 2 * v131 + 2 >= 0x1000 )
                {
                  v68 = (void *)*((_QWORD *)v130[0] - 1);
                  if ( (unsigned __int64)((char *)v130[0] - (char *)v68 - 8) > 0x1F )
                    _invalid_parameter_noinfo_noreturn();
                }
                operator delete(v68);
              }
              v130[2] = 0;
              v131 = 7;
              LOWORD(v130[0]) = 0;
              if ( v121 >= 8 )
              {
                v69 = v119[0];
                if ( 2 * v121 + 2 >= 0x1000 )
                {
                  v69 = (void *)*((_QWORD *)v119[0] - 1);
                  if ( (unsigned __int64)((char *)v119[0] - (char *)v69 - 8) > 0x1F )
                    _invalid_parameter_noinfo_noreturn();
                }
                operator delete(v69);
              }
              v120 = 0;
              v121 = 7;
              LOWORD(v119[0]) = 0;
              if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(_DWORD *))v26)(v26);
                if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v26 + 8LL))(v26);
              }
              return;
            }
          }
          while ( a2[v22] == aMetadata_0[v22] );
          if ( *((_BYTE *)this + 162) )
            return;
          v23 = NMR::CNMRException::CNMRException((NMR::CNMRException *)&v103, 32934);
          NMR::CModelReaderWarnings::addException(*((_QWORD *)this + 7), v23, 3);
          v103 = &std::exception::`vftable';
          v24 = &v104;
          goto LABEL_197;
        }
      }
      while ( v16 != 6 );
      if ( *((_BYTE *)this + 161) )
      {
        NMR::CNMRException::CNMRException((NMR::CNMRException *)v111, 32872);
        throw (NMR::CNMRException *)v111;
      }
      if ( *((_BYTE *)this + 163) )
      {
        *((_BYTE *)this + 162) = 1;
      }
      else
      {
        *((_BYTE *)this + 162) = 0;
        v18 = *((_QWORD *)this + 6);
        if ( v18 && !(unsigned __int8)NMR::CProgressMonitor::Progress(v18, a2, 10) )
        {
          NMR::CNMRException::CNMRException((NMR::CNMRException *)v112, 1);
          throw (NMR::CNMRException *)v112;
        }
        v96 = 0;
        v19 = operator new(0x70u);
        v20 = v19;
        if ( v19 )
        {
          *(_OWORD *)v19 = 0;
          v19[2] = 1;
          v19[3] = 1;
          *(_QWORD *)v19 = &std::_Ref_count_obj2<NMR::CModelReaderNode100_Build>::`vftable';
          v87 = 0;
          v21 = *((_QWORD *)this + 8);
          if ( v21 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
            v21 = *((_QWORD *)this + 8);
          }
          *(_QWORD *)&v87 = *((_QWORD *)this + 7);
          *((_QWORD *)&v87 + 1) = v21;
          NMR::CModelReaderNode100_Build::CModelReaderNode100_Build(v19 + 4, *((_QWORD *)this + 9), &v87);
        }
        else
        {
          v20 = 0;
        }
        *(_QWORD *)&v96 = v20 + 4;
        *((_QWORD *)&v96 + 1) = v20;
        (*(void (__fastcall **)(_DWORD *, struct NMR::CXmlReader *))(*((_QWORD *)v20 + 2) + 40LL))(v20 + 4, a4);
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(_DWORD *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 8LL))(v20);
            *((_BYTE *)this + 161) = 1;
            return;
          }
        }
      }
      *((_BYTE *)this + 161) = 1;
      return;
    }
  }
  v70 = -1;
  v71 = -1;
  do
  {
    if ( a3[v71 + 1] != aHttpSchemasMic[v71 + 1] )
      break;
    v71 += 2;
    if ( v71 == 53 )
      goto LABEL_166;
  }
  while ( a3[v71] == aHttpSchemasMic[v71] );
  if ( *a3 )
    return;
LABEL_166:
  v72 = 0;
  while ( a2[v72] == aResources[v72] && a2[v72 + 1] == aResources[v72 + 1] )
  {
    v72 += 2;
    if ( v72 == 10 )
    {
      v98 = 0;
      v73 = operator new(0x80u);
      v13 = v73;
      if ( v73 )
      {
        *(_OWORD *)v73 = 0;
        v73[2] = 1;
        v73[3] = 1;
        *(_QWORD *)v73 = &std::_Ref_count_obj2<NMR::CModelReaderNode093_Resources>::`vftable';
        v89 = 0;
        v74 = *((_QWORD *)this + 8);
        if ( v74 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v74 + 8));
          v74 = *((_QWORD *)this + 8);
        }
        *(_QWORD *)&v89 = *((_QWORD *)this + 7);
        *((_QWORD *)&v89 + 1) = v74;
        NMR::CModelReaderNode093_Resources::CModelReaderNode093_Resources(v73 + 4, *((_QWORD *)this + 9), &v89);
      }
      else
      {
        v13 = 0;
      }
      *(_QWORD *)&v98 = v13 + 4;
      *((_QWORD *)&v98 + 1) = v13;
      if ( *((_BYTE *)this + 160) )
      {
        NMR::CNMRException::CNMRException((NMR::CNMRException *)v118, 32871);
        throw (NMR::CNMRException *)v118;
      }
      (*(void (__fastcall **)(_DWORD *, struct NMR::CXmlReader *))(*((_QWORD *)v13 + 2) + 40LL))(v13 + 4, a4);
      *((_BYTE *)this + 160) = 1;
LABEL_187:
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(_DWORD *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 8LL))(v13);
      }
      return;
    }
  }
  v75 = 0;
  while ( 1 )
  {
    v76 = a2[v75++];
    if ( v76 != aBuild[v75 - 1] )
      break;
    if ( v75 == 6 )
    {
      v99 = 0;
      v77 = operator new(0x60u);
      v13 = v77;
      if ( v77 )
      {
        *(_OWORD *)v77 = 0;
        v77[2] = 1;
        v77[3] = 1;
        *(_QWORD *)v77 = &std::_Ref_count_obj2<NMR::CModelReaderNode093_Build>::`vftable';
        v90 = 0;
        v78 = *((_QWORD *)this + 8);
        if ( v78 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v78 + 8));
          v78 = *((_QWORD *)this + 8);
        }
        *(_QWORD *)&v90 = *((_QWORD *)this + 7);
        *((_QWORD *)&v90 + 1) = v78;
        NMR::CModelReaderNode093_Build::CModelReaderNode093_Build(v77 + 4, *((_QWORD *)this + 9), &v90);
      }
      else
      {
        v13 = 0;
      }
      *(_QWORD *)&v99 = v13 + 4;
      *((_QWORD *)&v99 + 1) = v13;
      if ( *((_BYTE *)this + 161) )
      {
        NMR::CNMRException::CNMRException((NMR::CNMRException *)pExceptionObject, 32872);
        throw (NMR::CNMRException *)pExceptionObject;
      }
      (*(void (__fastcall **)(_DWORD *, struct NMR::CXmlReader *))(*((_QWORD *)v13 + 2) + 40LL))(v13 + 4, a4);
      *((_BYTE *)this + 161) = 1;
      goto LABEL_187;
    }
  }
  while ( 1 )
  {
    if ( a2[v70 + 1] != aMetadata_0[v70 + 1] )
      goto LABEL_193;
    v70 += 2;
    if ( v70 == 9 )
      break;
    if ( a2[v70] != aMetadata_0[v70] )
    {
LABEL_193:
      while ( 1 )
      {
        v79 = a2[v6++];
        if ( v79 != aEntry[v6 - 1] )
          break;
        if ( v6 == 6 )
          return;
      }
      v80 = NMR::CNMRException::CNMRException((NMR::CNMRException *)&v105, 32934);
      NMR::CModelReaderWarnings::addException(*((_QWORD *)this + 7), v80, 3);
      v105 = &std::exception::`vftable';
      v24 = &v106;
LABEL_197:
      _std_exception_destroy_0(v24);
      return;
    }
  }
}

```

## disassembly

```asm
0x18043b160  mov     [rsp-8+arg_8], rbx
0x18043b165  push    rbp
0x18043b166  push    rsi
0x18043b167  push    rdi
0x18043b168  push    r12
0x18043b16a  push    r13
0x18043b16c  push    r14
0x18043b16e  push    r15
0x18043b170  lea     rbp, [rsp-2F0h]
0x18043b178  sub     rsp, 3F0h
0x18043b17f  mov     rax, cs:__security_cookie
0x18043b186  xor     rax, rsp
0x18043b189  mov     [rbp+320h+var_38], rax
0x18043b190  mov     r13, r9
0x18043b193  mov     r15, rcx
0x18043b196  lea     r9, aHttpSchemasMic_4; "http://schemas.microsoft.com/3dmanufact"...
0x18043b19d  mov     r10d, 3Ah ; ':'
0x18043b1a3  xor     r14d, r14d
0x18043b1a6  mov     ecx, r14d
0x18043b1a9  nop     dword ptr [rax+00000000h]
0x18043b1b0  movzx   eax, word ptr [r8+rcx*2]
0x18043b1b5  cmp     ax, [r9+rcx*2]
0x18043b1ba  jnz     loc_18043BD98
0x18043b1c0  movzx   eax, word ptr [r8+rcx*2+2]
0x18043b1c6  cmp     ax, [r9+rcx*2+2]
0x18043b1cc  jnz     loc_18043BD98
0x18043b1d2  add     rcx, 2
0x18043b1d6  cmp     rcx, r10
0x18043b1d9  jnz     short loc_18043B1B0
0x18043b1db  lea     r8, aResources; "resources"
0x18043b1e2  mov     edi, 0Ah
0x18043b1e7  mov     rcx, r14
0x18043b1ea  nop     word ptr [rax+rax+00h]
0x18043b1f0  movzx   eax, word ptr [rdx+rcx*2]
0x18043b1f4  cmp     ax, [r8+rcx*2]
0x18043b1f9  jnz     loc_18043B343
0x18043b1ff  movzx   eax, word ptr [rdx+rcx*2+2]
0x18043b204  cmp     ax, [r8+rcx*2+2]
0x18043b20a  jnz     loc_18043B343
0x18043b210  add     rcx, 2
0x18043b214  cmp     rcx, rdi
0x18043b217  jnz     short loc_18043B1F0
0x18043b219  mov     [r15+0A2h], r14b
0x18043b220  mov     rcx, [r15+30h]
0x18043b224  test    rcx, rcx
0x18043b227  jz      short loc_18043B244
0x18043b229  mov     r8d, 7
0x18043b22f  movsd   xmm1, cs:__real@3fc999999999999a
0x18043b237  call    ?Progress@CProgressMonitor@NMR@@QEAA_NNW4ProgressIdentifier@2@@Z; NMR::CProgressMonitor::Progress(double,NMR::ProgressIdentifier)
0x18043b23c  test    al, al
0x18043b23e  jz      loc_18043C096
0x18043b244  mov     rcx, [r15+30h]; this
0x18043b248  test    rcx, rcx
0x18043b24b  jz      short loc_18043B262
0x18043b24d  movsd   xmm2, cs:__real@3feccccccccccccd; double
0x18043b255  movsd   xmm1, cs:__real@3fc999999999999a; double
0x18043b25d  call    ?PushLevel@CProgressMonitor@NMR@@QEAAXNN@Z; NMR::CProgressMonitor::PushLevel(double,double)
0x18043b262  xorps   xmm0, xmm0
0x18043b265  movups  [rbp+320h+var_338], xmm0
0x18043b269  lea     rdi, [r15+80h]
0x18043b270  cmp     qword ptr [rdi+18h], 8
0x18043b275  jb      short loc_18043B27A
0x18043b277  mov     rdi, [rdi]
0x18043b27a  mov     ecx, 0A8h; Size
0x18043b27f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18043b284  mov     rbx, rax
0x18043b287  mov     [rsp+420h+var_3F0], rax
0x18043b28c  test    rax, rax
0x18043b28f  jz      short loc_18043B2F4
0x18043b291  xorps   xmm0, xmm0
0x18043b294  movups  xmmword ptr [rax], xmm0
0x18043b297  mov     dword ptr [rax+8], 1
0x18043b29e  mov     dword ptr [rax+0Ch], 1
0x18043b2a5  lea     rax, ??_7?$_Ref_count_obj2@VCModelReaderNode100_Resources@NMR@@@std@@6B@; const std::_Ref_count_obj2<NMR::CModelReaderNode100_Resources>::`vftable'
0x18043b2ac  mov     [rbx], rax
0x18043b2af  lea     rcx, [rbx+10h]
0x18043b2b3  movdqu  [rsp+420h+var_3B8], xmm0
0x18043b2b9  mov     rdx, [r15+40h]
0x18043b2bd  test    rdx, rdx
0x18043b2c0  jz      short loc_18043B2CA
0x18043b2c2  lock inc dword ptr [rdx+8]
0x18043b2c6  mov     rdx, [r15+40h]
0x18043b2ca  mov     rax, [r15+38h]
0x18043b2ce  mov     qword ptr [rsp+420h+var_3B8], rax
0x18043b2d3  mov     qword ptr [rsp+420h+var_3B8+8], rdx
0x18043b2d8  mov     rax, [r15+30h]
0x18043b2dc  mov     [rsp+420h+var_400], rax
0x18043b2e1  mov     r9, rdi
0x18043b2e4  lea     r8, [rsp+420h+var_3B8]
0x18043b2e9  mov     rdx, [r15+48h]
0x18043b2ed  call    ??0CModelReaderNode100_Resources@NMR@@QEAA@PEAVCModel@1@V?$shared_ptr@VCModelReaderWarnings@NMR@@@std@@PEB_WPEAVCProgressMonitor@1@@Z; NMR::CModelReaderNode100_Resources::CModelReaderNode100_Resources(NMR::CModel *,std::shared_ptr<NMR::CModelReaderWarnings>,wchar_t const *,NMR::CProgressMonitor *)
0x18043b2f2  jmp     short loc_18043B2F7
0x18043b2f4  mov     rbx, r14
0x18043b2f7  lea     rcx, [rbx+10h]
0x18043b2fb  mov     qword ptr [rbp+320h+var_338], rcx
0x18043b2ff  mov     qword ptr [rbp+320h+var_338+8], rbx
0x18043b303  cmp     byte ptr [r15+0A0h], 0
0x18043b30b  jnz     loc_18043C0BB
0x18043b311  mov     rax, [rcx]
0x18043b314  mov     rdx, r13
0x18043b317  call    qword ptr [rax+28h]
0x18043b31a  mov     rcx, [r15+30h]
0x18043b31e  test    rcx, rcx
0x18043b321  jz      short loc_18043B32F
0x18043b323  lea     rdx, [rbp+320h+var_238]
0x18043b32a  call    ?PopLevel@CProgressMonitor@NMR@@QEAA?AU?$pair@NN@std@@XZ; NMR::CProgressMonitor::PopLevel(void)
0x18043b32f  mov     byte ptr [r15+0A0h], 1
0x18043b337  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18043b33e  jmp     loc_18043BF88
0x18043b343  mov     rcx, r14
0x18043b346  lea     r8, aBuild; "build"
0x18043b34d  nop     dword ptr [rax]
0x18043b350  movzx   eax, word ptr [rdx+rcx*2]
0x18043b354  inc     rcx
0x18043b357  cmp     ax, [r8+rcx*2-2]
0x18043b35d  jnz     loc_18043B487
0x18043b363  cmp     rcx, 6
0x18043b367  jnz     short loc_18043B350
0x18043b369  cmp     [r15+0A1h], r14b
0x18043b370  jnz     loc_18043C0E0
0x18043b376  cmp     [r15+0A3h], r14b
0x18043b37d  jnz     loc_18043B472
0x18043b383  mov     [r15+0A2h], r14b
0x18043b38a  mov     rcx, [r15+30h]
0x18043b38e  test    rcx, rcx
0x18043b391  jz      short loc_18043B3AB
0x18043b393  mov     r8d, edi
0x18043b396  movsd   xmm1, cs:__real@3feccccccccccccd
0x18043b39e  call    ?Progress@CProgressMonitor@NMR@@QEAA_NNW4ProgressIdentifier@2@@Z; NMR::CProgressMonitor::Progress(double,NMR::ProgressIdentifier)
0x18043b3a3  test    al, al
0x18043b3a5  jz      loc_18043C105
0x18043b3ab  xorps   xmm0, xmm0
0x18043b3ae  movups  [rbp+320h+var_328], xmm0
0x18043b3b2  mov     ecx, 70h ; 'p'; Size
0x18043b3b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18043b3bc  mov     rbx, rax
0x18043b3bf  mov     [rsp+420h+var_3F0], rax
0x18043b3c4  test    rax, rax
0x18043b3c7  jz      short loc_18043B41F
0x18043b3c9  xorps   xmm0, xmm0
0x18043b3cc  movups  xmmword ptr [rax], xmm0
0x18043b3cf  mov     dword ptr [rax+8], 1
0x18043b3d6  mov     dword ptr [rax+0Ch], 1
0x18043b3dd  lea     rax, ??_7?$_Ref_count_obj2@VCModelReaderNode100_Build@NMR@@@std@@6B@; const std::_Ref_count_obj2<NMR::CModelReaderNode100_Build>::`vftable'
0x18043b3e4  mov     [rbx], rax
0x18043b3e7  lea     rcx, [rbx+10h]
0x18043b3eb  movdqu  [rsp+420h+var_3A8], xmm0
0x18043b3f1  mov     rdx, [r15+40h]
0x18043b3f5  test    rdx, rdx
0x18043b3f8  jz      short loc_18043B402
0x18043b3fa  lock inc dword ptr [rdx+8]
0x18043b3fe  mov     rdx, [r15+40h]
0x18043b402  mov     rax, [r15+38h]
0x18043b406  mov     qword ptr [rsp+420h+var_3A8], rax
0x18043b40b  mov     qword ptr [rbp+320h+var_3A8+8], rdx
0x18043b40f  lea     r8, [rsp+420h+var_3A8]
0x18043b414  mov     rdx, [r15+48h]
0x18043b418  call    ??0CModelReaderNode100_Build@NMR@@QEAA@PEAVCModel@1@V?$shared_ptr@VCModelReaderWarnings@NMR@@@std@@@Z; NMR::CModelReaderNode100_Build::CModelReaderNode100_Build(NMR::CModel *,std::shared_ptr<NMR::CModelReaderWarnings>)
0x18043b41d  jmp     short loc_18043B422
0x18043b41f  mov     rbx, r14
0x18043b422  lea     rcx, [rbx+10h]
0x18043b426  mov     qword ptr [rbp+320h+var_328], rcx
0x18043b42a  mov     qword ptr [rbp+320h+var_328+8], rbx
0x18043b42e  mov     rax, [rcx]
0x18043b431  mov     rdx, r13
0x18043b434  call    qword ptr [rax+28h]
0x18043b437  nop
0x18043b438  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18043b43f  mov     eax, esi
0x18043b441  lock xadd [rbx+8], eax
0x18043b446  cmp     eax, 1
0x18043b449  jnz     short loc_18043B47A
0x18043b44b  mov     rax, [rbx]
0x18043b44e  mov     rcx, rbx
0x18043b451  call    qword ptr [rax]
0x18043b453  lock xadd [rbx+0Ch], esi
0x18043b458  cmp     esi, 1
0x18043b45b  jnz     short loc_18043B47A
0x18043b45d  mov     rax, [rbx]
0x18043b460  mov     rcx, rbx
0x18043b463  call    qword ptr [rax+8]
0x18043b466  mov     [r15+0A1h], sil
0x18043b46d  jmp     loc_18043C047
0x18043b472  mov     byte ptr [r15+0A2h], 1
0x18043b47a  mov     byte ptr [r15+0A1h], 1
0x18043b482  jmp     loc_18043C047
0x18043b487  lea     r8, aMetadata_0; "metadata"
0x18043b48e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18043b495  mov     rcx, rsi
0x18043b498  nop     dword ptr [rax+rax+00000000h]
0x18043b4a0  movzx   eax, word ptr [rdx+rcx*2+2]
0x18043b4a5  cmp     ax, [r8+rcx*2+2]
0x18043b4ab  jnz     short loc_18043B4C2
0x18043b4ad  add     rcx, 2
0x18043b4b1  cmp     rcx, 9
0x18043b4b5  jz      short loc_18043B50E
0x18043b4b7  movzx   eax, word ptr [rdx+rcx*2]
0x18043b4bb  cmp     ax, [r8+rcx*2]
0x18043b4c0  jz      short loc_18043B4A0
0x18043b4c2  cmp     [r15+0A2h], r14b
0x18043b4c9  jnz     loc_18043C047
0x18043b4cf  mov     edx, 80A6h; int
0x18043b4d4  lea     rcx, [rbp+320h+var_298]; this
0x18043b4db  call    ??0CNMRException@NMR@@QEAA@H@Z; NMR::CNMRException::CNMRException(int)
0x18043b4e0  nop
0x18043b4e1  mov     r8d, 3
0x18043b4e7  mov     rdx, rax
0x18043b4ea  mov     rcx, [r15+38h]
0x18043b4ee  call    ?addException@CModelReaderWarnings@NMR@@QEAAXAEBVCNMRException@2@W4_eModelReaderWarningLevel@2@@Z; NMR::CModelReaderWarnings::addException(NMR::CNMRException const &,NMR::_eModelReaderWarningLevel)
0x18043b4f3  nop
0x18043b4f4  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18043b4fb  mov     [rbp+320h+var_298], rax
0x18043b502  lea     rcx, [rbp+320h+var_290]
0x18043b509  jmp     loc_18043C042
0x18043b50e  mov     [r15+0A2h], r14b
0x18043b515  mov     ecx, 98h; Size
0x18043b51a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18043b51f  mov     r12, rax
0x18043b522  mov     [rsp+420h+var_3F0], rax
0x18043b527  test    rax, rax
0x18043b52a  jz      short loc_18043B57D
0x18043b52c  xorps   xmm0, xmm0
0x18043b52f  movups  xmmword ptr [rax], xmm0
0x18043b532  mov     dword ptr [rax+8], 1
0x18043b539  mov     dword ptr [rax+0Ch], 1
0x18043b540  lea     rax, ??_7?$_Ref_count_obj2@VCModelReaderNode100_MetaData@NMR@@@std@@6B@; const std::_Ref_count_obj2<NMR::CModelReaderNode100_MetaData>::`vftable'
0x18043b547  mov     [r12], rax
0x18043b54b  lea     rcx, [r12+10h]
0x18043b550  movdqu  [rbp+320h+var_398], xmm0
0x18043b555  mov     rdx, [r15+40h]
0x18043b559  test    rdx, rdx
0x18043b55c  jz      short loc_18043B566
0x18043b55e  lock inc dword ptr [rdx+8]
0x18043b562  mov     rdx, [r15+40h]
0x18043b566  mov     rax, [r15+38h]
0x18043b56a  mov     qword ptr [rbp+320h+var_398], rax
0x18043b56e  mov     qword ptr [rbp+320h+var_398+8], rdx
0x18043b572  lea     rdx, [rbp+320h+var_398]
0x18043b576  call    ??0CModelReaderNode100_MetaData@NMR@@QEAA@V?$shared_ptr@VCModelReaderWarnings@NMR@@@std@@@Z; NMR::CModelReaderNode100_MetaData::CModelReaderNode100_MetaData(std::shared_ptr<NMR::CModelReaderWarnings>)
0x18043b57b  jmp     short loc_18043B580
0x18043b57d  mov     r12, r14
0x18043b580  xorps   xmm0, xmm0
0x18043b583  movups  [rbp+320h+var_48], xmm0
0x18043b58a  lea     rbx, [r12+10h]
0x18043b58f  mov     qword ptr [rbp+320h+var_48], rbx
0x18043b596  mov     qword ptr [rbp+320h+var_48+8], r12
0x18043b59d  mov     rax, [rbx]
0x18043b5a0  mov     rdx, r13
0x18043b5a3  mov     rcx, rbx
0x18043b5a6  call    qword ptr [rax+28h]
0x18043b5a9  lea     rdx, [rbp+320h+var_E8]
0x18043b5b0  mov     rcx, rbx
0x18043b5b3  call    ?getName@CModelReaderNode100_MetaData@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::CModelReaderNode100_MetaData::getName(void)
0x18043b5b8  nop
0x18043b5b9  lea     rdx, [rbp+320h+var_68]
0x18043b5c0  mov     rcx, rbx
0x18043b5c3  call    ?getValue@CModelReaderNode100_MetaData@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::CModelReaderNode100_MetaData::getValue(void)
0x18043b5c8  nop
0x18043b5c9  cmp     [rbp+320h+var_D8], 0
0x18043b5d1  jbe     loc_18043BC58
0x18043b5d7  lea     rdx, [rbp+320h+var_E8]
0x18043b5de  lea     rcx, [rbp+320h+var_1A8]
0x18043b5e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18043b5ea  mov     rdx, rax
0x18043b5ed  mov     rcx, [r15+48h]
0x18043b5f1  call    ?hasMetaData@CModel@NMR@@QEAA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::CModel::hasMetaData(std::wstring)
0x18043b5f6  test    al, al
0x18043b5f8  jz      short loc_18043B639
0x18043b5fa  mov     [rbp+320h+var_2D8], r14
0x18043b5fe  mov     [rbp+320h+var_2C8], r14
0x18043b602  mov     [rbp+320h+var_2C0], 7
0x18043b60a  mov     r8d, 18h
0x18043b610  lea     rdx, aDuplicateModel_0; "duplicate model metadata"
0x18043b617  lea     rcx, [rbp+320h+var_2D8]; void *
0x18043b61b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18043b620  mov     r9d, 3
0x18043b626  mov     r8d, 805Ch
0x18043b62c  lea     rdx, [rbp+320h+var_2D8]
0x18043b630  mov     rcx, [r15+38h]
0x18043b634  call    ?addWarning@CModelReaderWarnings@NMR@@QEAAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HW4_eModelReaderWarningLevel@2@@Z; NMR::CModelReaderWarnings::addWarning(std::wstring,int,NMR::_eModelReaderWarningLevel)
0x18043b639  mov     [rbp+320h+var_88], r14
0x18043b640  mov     [rbp+320h+var_78], r14
0x18043b647  mov     [rbp+320h+var_70], 7
0x18043b652  mov     word ptr [rbp+320h+var_88], r14w
0x18043b65a  mov     [rbp+320h+var_C8], r14
0x18043b661  mov     [rbp+320h+var_B8], r14
0x18043b668  mov     [rbp+320h+var_B0], 7
0x18043b673  mov     word ptr [rbp+320h+var_C8], r14w
0x18043b67b  lea     r8, [rbp+320h+var_C8]
0x18043b682  lea     rdx, [rbp+320h+var_88]
0x18043b689  lea     rcx, [rbp+320h+var_E8]
0x18043b690  call    ?decomposeIntoNamespaceAndName@NMR@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@1@Z; NMR::decomposeIntoNamespaceAndName(std::wstring const &,std::wstring &,std::wstring &)
0x18043b695  test    al, al
0x18043b697  jz      loc_18043B943
0x18043b69d  mov     [rbp+320h+Src], r14
0x18043b6a4  mov     [rbp+320h+var_98], r14
0x18043b6ab  mov     [rbp+320h+var_90], 7
0x18043b6b6  mov     word ptr [rbp+320h+Src], r14w
0x18043b6be  mov     rax, [r13+0]
0x18043b6c2  lea     r8, [rbp+320h+Src]
  ... truncated ...
```

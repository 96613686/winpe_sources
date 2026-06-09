# NMR::CModelReaderNode_Model::CheckRequiredExtensions(void)

- ea: `0x18043a2b0`
- end: `0x18043acff`
- name: `?CheckRequiredExtensions@CModelReaderNode_Model@NMR@@MEAAXXZ`
- size: `2639`
- prototype: `void __fastcall(NMR::CModelReaderNode_Model *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180014a60`
- `0x180015630`
- `0x180016350`
- `0x180017670`
- `0x18003d030`
- `0x180184da0`
- `0x1801b51d0`
- `0x18021ecb0`
- `0x180265a20`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x18039f910`
- `0x1804169c0`
- `0x180424f50`
- `0x180439b00`
- `0x180439cd0`
- `0x18043a2b0`

## import_xrefs

- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18043ac98`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18043ac98`
- `MSVCP140!??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x18043a31f`
- `MSVCP140!??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ` at `0x18043a31f`
- `MSVCP140!??0?$basic_istream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z` at `0x18043a342`
- `MSVCP140!??0?$basic_istream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z` at `0x18043a342`
- `MSVCP140!??1?$basic_istream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18043ac8b`
- `MSVCP140!??1?$basic_istream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18043ac8b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043abc9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043abd0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043ac32`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043abc9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043abd0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18043ac32`

## string_xrefs

- `0x18043aabc`: `http://schemas.microsoft.com/3dmanufacturing/beamlattice/2017/02`
- `0x18043aa6d`: `http://schemas.microsoft.com/3dmanufacturing/slice/2015/07`
- `0x18043aa29`: `http://schemas.microsoft.com/3dmanufacturing/production/2015/06`
- `0x18043a9a2`: `http://schemas.microsoft.com/3dmanufacturing/core/2015/02`
- `0x18043a9e9`: `http://schemas.microsoft.com/3dmanufacturing/material/2015/02`
- `0x18043aafb`: `A required extension is not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall NMR::CModelReaderNode_Model::CheckRequiredExtensions(NMR::CModelReaderNode_Model *this)
{
  NMR::CModelReaderNode_Model *v1; // rsi
  __int64 v2; // rax
  __int64 v3; // r8
  bool v4; // zf
  _QWORD *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // r12
  _QWORD *v11; // rbx
  unsigned __int64 v12; // rbx
  _OWORD *v13; // rdi
  unsigned __int64 v14; // r15
  __int64 *v15; // r14
  __int64 *v16; // rdi
  __int64 *v17; // r10
  char *v18; // r13
  void **v19; // rax
  __int64 *v20; // r9
  unsigned __int64 v21; // r11
  unsigned __int64 v22; // rcx
  __int64 v23; // r9
  unsigned __int16 v24; // dx
  bool v25; // cf
  int v26; // eax
  char *v27; // rax
  void **v28; // r9
  unsigned __int64 v29; // r10
  unsigned __int64 v30; // rcx
  signed __int64 v31; // r9
  unsigned __int16 v32; // dx
  bool v33; // cf
  int v34; // eax
  char v35; // al
  __int64 v36; // rsi
  __int64 v37; // r10
  __int64 inserted; // rdi
  void **v39; // rax
  __int64 v40; // r9
  unsigned __int64 v41; // r11
  unsigned __int64 v42; // rcx
  __int64 v43; // r9
  unsigned __int16 v44; // dx
  bool v45; // cf
  int v46; // eax
  char *v47; // rax
  void **v48; // r9
  unsigned __int64 v49; // r10
  unsigned __int64 v50; // rcx
  signed __int64 v51; // r9
  unsigned __int16 v52; // dx
  bool v53; // cf
  int v54; // eax
  __int64 *v55; // rdi
  __int64 v56; // r8
  _QWORD *v57; // rbx
  unsigned __int64 v58; // rdi
  unsigned __int64 v59; // rsi
  void *v60; // r14
  void **v61; // rdx
  __int64 v62; // rcx
  void **v63; // rdx
  __int64 v64; // rcx
  void **v65; // rdx
  __int64 v66; // rcx
  void **v67; // rdx
  __int64 v68; // rcx
  void **v69; // rdx
  __int64 v70; // rcx
  _BYTE *v71; // rax
  char *v72; // rax
  char *v73; // rax
  _QWORD *v74; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v76; // [rsp+48h] [rbp-B8h]
  _QWORD *v77; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v78[32]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v79; // [rsp+78h] [rbp-88h]
  _QWORD v80[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v81; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v82; // [rsp+B0h] [rbp-50h]
  __int128 v83; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v84; // [rsp+E0h] [rbp-20h]
  __int64 v85; // [rsp+E8h] [rbp-18h]
  _QWORD v86[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v87; // [rsp+110h] [rbp+10h]
  _BYTE v88[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+138h] [rbp+38h] BYREF
  void *Src[2]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE *v91; // [rsp+168h] [rbp+68h]
  void *v92[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v93; // [rsp+180h] [rbp+80h]
  unsigned __int64 v94; // [rsp+188h] [rbp+88h]
  void *Block[2]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v96; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v97; // [rsp+1A8h] [rbp+A8h]
  _QWORD v98[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v99[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v100[120]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v101[96]; // [rsp+240h] [rbp+140h] BYREF

  v1 = this;
  memset_0(v98, 0, 0xF0u);
  v98[0] = std::wistringstream::`vbtable';
  std::wios::wios(v101);
  std::wistream::wistream(v98, v99, 0, 0);
  *(_QWORD *)((char *)v98 + *(int *)(v98[0] + 4LL)) = &std::wistringstream::`vftable';
  *(_DWORD *)((char *)&v97 + *(int *)(v98[0] + 4LL) + 4) = *(_DWORD *)(v98[0] + 4LL) - 144;
  std::wstringbuf::wstringbuf(v99, (char *)v1 + 80, 1);
  *(_OWORD *)Src = 0;
  v91 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 7;
  v79 = v98;
  v80[0] = 0;
  v80[2] = 0;
  v80[3] = 7;
  v2 = std::operator>><wchar_t>(v98, v80);
  v4 = (*(_BYTE *)(*(int *)(*(_QWORD *)v2 + 4LL) + v2 + 16) & 6) == 0;
  v5 = v98;
  if ( !v4 )
    v5 = 0;
  v79 = v5;
  *(_OWORD *)Src = 0;
  v91 = 0;
  v87 = (_QWORD *)v83;
  std::wstring::wstring(v88, (char *)&v83 + 8, v3);
  v77 = v79;
  std::wstring::wstring(v78, v80, v6);
  *(_QWORD *)&v81 = &v77;
  if ( v77 != v87 )
  {
    do
    {
      if ( Src[1] == v91 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(Src, Src[1], v78);
      }
      else
      {
        std::wstring::wstring(Src[1], v78, v7);
        Src[1] = (char *)Src[1] + 32;
      }
      v8 = std::operator>><wchar_t>(v77, v78);
      if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v8 + 4LL) + v8 + 16) & 6) != 0 )
      {
        v77 = 0;
        v9 = 0;
      }
      else
      {
        v9 = v77;
      }
    }
    while ( v9 != v87 );
  }
  std::wstring::_Tidy_deallocate(v78);
  std::wstring::_Tidy_deallocate(v88);
  std::wstring::_Tidy_deallocate(v80);
  std::wstring::_Tidy_deallocate((char *)&v83 + 8);
  v10 = Src[0];
  v11 = Src[1];
  v74 = Src[1];
  if ( Src[0] != Src[1] )
  {
    while ( 1 )
    {
      v92[0] = 0;
      v93 = 0;
      v94 = 0;
      v12 = v10[2];
      v13 = v10;
      if ( v10[3] >= 8u )
        v13 = (_OWORD *)*v10;
      if ( v12 >= 8 )
      {
        v14 = v12 | 7;
        if ( (v12 | 7) > 0x7FFFFFFFFFFFFFFELL )
          v14 = 0x7FFFFFFFFFFFFFFELL;
        if ( v14 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
        _mm_lfence();
        v92[0] = (void *)std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v14 + 1));
        memcpy_0(v92[0], v13, 2 * v12 + 2);
      }
      else
      {
        *(_OWORD *)v92 = *v13;
        v14 = 7;
      }
      v94 = v14;
      v93 = v12;
      v15 = (__int64 *)((char *)v1 + 112);
      v16 = (__int64 *)*((_QWORD *)v1 + 14);
      v17 = (__int64 *)v16[1];
      v18 = (char *)v92[0];
      while ( !*((_BYTE *)v17 + 25) )
      {
        v19 = v92;
        if ( v14 >= 8 )
          v19 = (void **)v92[0];
        v20 = v17 + 4;
        if ( (unsigned __int64)v17[7] >= 8 )
          v20 = (__int64 *)v17[4];
        v21 = v17[6];
        v22 = v21;
        if ( v12 < v21 )
          v22 = v12;
        if ( v22 )
        {
          v23 = (char *)v20 - (char *)v19;
          while ( 1 )
          {
            v24 = *(_WORD *)((char *)v19 + v23);
            v25 = v24 < *(_WORD *)v19;
            if ( v24 != *(_WORD *)v19 )
              break;
            v19 = (void **)((char *)v19 + 2);
            if ( !--v22 )
              goto LABEL_31;
          }
          v26 = 1;
          if ( v25 )
            v26 = -1;
        }
        else
        {
LABEL_31:
          if ( v21 >= v12 )
            v26 = v21 > v12;
          else
            v26 = -1;
        }
        if ( v26 >= 0 )
        {
          v16 = v17;
          v17 = (__int64 *)*v17;
        }
        else
        {
          v17 = (__int64 *)v17[2];
        }
      }
      if ( *((_BYTE *)v16 + 25) )
        goto LABEL_60;
      v27 = (char *)(v16 + 4);
      if ( (unsigned __int64)v16[7] >= 8 )
        v27 = (char *)v16[4];
      v28 = v92;
      if ( v14 >= 8 )
        v28 = (void **)v92[0];
      v29 = v16[6];
      v30 = v12;
      if ( v29 < v12 )
        v30 = v16[6];
      if ( v30 )
      {
        v31 = (char *)v28 - v27;
        while ( 1 )
        {
          v32 = *(_WORD *)&v27[v31];
          v33 = v32 < *(_WORD *)v27;
          if ( v32 != *(_WORD *)v27 )
            break;
          v27 += 2;
          if ( !--v30 )
            goto LABEL_52;
        }
        v34 = 1;
        if ( v33 )
          v34 = -1;
      }
      else
      {
LABEL_52:
        v34 = v12 >= v29 ? v12 > v29 : -1;
      }
      if ( v34 < 0 )
LABEL_60:
        v35 = 0;
      else
        v35 = 1;
      if ( !v35 )
      {
        NMR::CNMRException::CNMRException((NMR::CNMRException *)pExceptionObject, 32913);
        throw (NMR::CNMRException *)pExceptionObject;
      }
      v36 = *v15;
      v37 = *(_QWORD *)(*v15 + 8);
      *(_QWORD *)&v82 = v37;
      DWORD2(v82) = 0;
      inserted = v36;
      while ( !*(_BYTE *)(v37 + 25) )
      {
        *(_QWORD *)&v82 = v37;
        v39 = v92;
        if ( v14 >= 8 )
          v39 = (void **)v92[0];
        v40 = v37 + 32;
        if ( *(_QWORD *)(v37 + 56) >= 8u )
          v40 = *(_QWORD *)(v37 + 32);
        v41 = *(_QWORD *)(v37 + 48);
        v42 = v41;
        if ( v12 < v41 )
          v42 = v12;
        if ( v42 )
        {
          v43 = v40 - (_QWORD)v39;
          while ( 1 )
          {
            v44 = *(_WORD *)((char *)v39 + v43);
            v45 = v44 < *(_WORD *)v39;
            if ( v44 != *(_WORD *)v39 )
              break;
            v39 = (void **)((char *)v39 + 2);
            if ( !--v42 )
              goto LABEL_73;
          }
          v46 = 1;
          if ( v45 )
            v46 = -1;
        }
        else
        {
LABEL_73:
          if ( v41 >= v12 )
            v46 = v41 > v12;
          else
            v46 = -1;
        }
        if ( v46 >= 0 )
        {
          DWORD2(v82) = 1;
          inserted = v37;
          v37 = *(_QWORD *)v37;
        }
        else
        {
          DWORD2(v82) = 0;
          v37 = *(_QWORD *)(v37 + 16);
        }
      }
      if ( *(_BYTE *)(inserted + 25) )
        goto LABEL_101;
      v47 = (char *)(inserted + 32);
      if ( *(_QWORD *)(inserted + 56) >= 8u )
        v47 = *(char **)(inserted + 32);
      v48 = v92;
      if ( v14 >= 8 )
        v48 = (void **)v92[0];
      v49 = *(_QWORD *)(inserted + 48);
      v50 = v12;
      if ( v49 < v12 )
        v50 = *(_QWORD *)(inserted + 48);
      if ( v50 )
      {
        v51 = (char *)v48 - v47;
        while ( 1 )
        {
          v52 = *(_WORD *)&v47[v51];
          v53 = v52 < *(_WORD *)v47;
          if ( v52 != *(_WORD *)v47 )
            break;
          v47 += 2;
          if ( !--v50 )
            goto LABEL_94;
        }
        v54 = 1;
        if ( v53 )
          v54 = -1;
      }
      else
      {
LABEL_94:
        v54 = v12 >= v49 ? v12 > v49 : -1;
      }
      if ( v54 < 0 )
      {
LABEL_101:
        if ( v15[1] == 0x2AAAAAAAAAAAAAALL )
          std::_Throw_tree_length_error();
        v76 = 0;
        _mm_lfence();
        v55 = (__int64 *)operator new((unsigned int)v76 + 96);
        std::wstring::wstring(v55 + 4, v92, v56);
        v55[8] = 0;
        v55[10] = 0;
        v55[11] = 7;
        *v55 = v36;
        v55[1] = v36;
        v55[2] = v36;
        *((_WORD *)v55 + 12) = 0;
        v81 = v82;
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(
                     v15,
                     &v81,
                     v55);
        v14 = v94;
        v18 = (char *)v92[0];
      }
      v57 = (_QWORD *)(inserted + 64);
      Block[0] = 0;
      v96 = 0;
      v97 = 0;
      v58 = *(_QWORD *)(inserted + 80);
      if ( v57[3] >= 8u )
        v57 = (_QWORD *)*v57;
      if ( v58 >= 8 )
      {
        v59 = v58 | 7;
        if ( (v58 | 7) > 0x7FFFFFFFFFFFFFFELL )
          v59 = 0x7FFFFFFFFFFFFFFELL;
        if ( v59 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
        _mm_lfence();
        v60 = (void *)std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v59 + 1));
        Block[0] = v60;
        memcpy_0(v60, v57, 2 * v58 + 2);
        v14 = v94;
        v18 = (char *)v92[0];
      }
      else
      {
        *(_OWORD *)Block = *(_OWORD *)v57;
        v59 = 7;
        v60 = Block[0];
      }
      v97 = v59;
      v96 = v58;
      v61 = Block;
      if ( v59 >= 8 )
        v61 = (void **)v60;
      v62 = 0;
      while ( *((_WORD *)v61 + v62) == aHttpSchemasMic_4[v62] && *((_WORD *)v61 + v62 + 1) == aHttpSchemasMic_4[v62 + 1] )
      {
        v62 += 2;
        if ( v62 == 58 )
          goto LABEL_145;
      }
      v63 = Block;
      if ( v59 >= 8 )
        v63 = (void **)v60;
      v64 = 0;
      while ( *((_WORD *)v63 + v64) == aHttpSchemasMic_1[v64] && *((_WORD *)v63 + v64 + 1) == aHttpSchemasMic_1[v64 + 1] )
      {
        v64 += 2;
        if ( v64 == 62 )
          goto LABEL_145;
      }
      v65 = Block;
      if ( v59 >= 8 )
        v65 = (void **)v60;
      v66 = 0;
      while ( *((_WORD *)v65 + v66) == aHttpSchemasMic_2[v66] && *((_WORD *)v65 + v66 + 1) == aHttpSchemasMic_2[v66 + 1] )
      {
        v66 += 2;
        if ( v66 == 64 )
          goto LABEL_145;
      }
      v67 = Block;
      if ( v59 >= 8 )
        v67 = (void **)v60;
      v68 = -1;
      do
      {
        if ( *((_WORD *)v67 + v68 + 1) != aHttpSchemasMic_7[v68 + 1] )
          break;
        v68 += 2;
        if ( v68 == 59 )
          goto LABEL_145;
      }
      while ( *((_WORD *)v67 + v68) == aHttpSchemasMic_7[v68] );
      v69 = Block;
      if ( v59 >= 8 )
        v69 = (void **)v60;
      v70 = -1;
      do
      {
        if ( *((_WORD *)v69 + v70 + 1) != aHttpSchemasMic_0[v70 + 1] )
          break;
        v70 += 2;
        if ( v70 == 65 )
          goto LABEL_145;
      }
      while ( *((_WORD *)v69 + v70) == aHttpSchemasMic_0[v70] );
      v86[0] = 0;
      v86[2] = 0;
      v86[3] = 7;
      std::wstring::assign(v86);
      NMR::CModelReaderWarnings::addWarning(*((_QWORD *)this + 7), v86, 32914, 1);
      v14 = v94;
      v18 = (char *)v92[0];
LABEL_145:
      if ( v59 >= 8 )
      {
        v71 = v60;
        if ( 2 * v59 + 2 >= 0x1000 )
        {
          v60 = (void *)*((_QWORD *)v60 - 1);
          if ( (unsigned __int64)(v71 - (_BYTE *)v60 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v60);
        v14 = v94;
        v18 = (char *)v92[0];
      }
      LOWORD(Block[0]) = 0;
      if ( v14 >= 8 )
      {
        v72 = v18;
        if ( 2 * v14 + 2 >= 0x1000 )
        {
          v18 = (char *)*((_QWORD *)v18 - 1);
          if ( (unsigned __int64)(v72 - v18 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v18);
      }
      v10 += 4;
      if ( v10 == v74 )
        break;
      v1 = this;
    }
    v11 = Src[1];
    v10 = Src[0];
  }
  if ( v10 )
  {
    if ( v10 != v11 )
    {
      do
      {
        std::wstring::_Tidy_deallocate(v10);
        v10 += 4;
      }
      while ( v10 != v11 );
      v10 = Src[0];
    }
    v73 = (char *)v10;
    if ( ((v91 - (_BYTE *)v10) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
    {
      v10 = (_QWORD *)*(v10 - 1);
      if ( (unsigned __int64)(v73 - (char *)v10 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v10);
    *(_OWORD *)Src = 0;
    v91 = 0;
  }
  *(_QWORD *)((char *)v98 + *(int *)(v98[0] + 4LL)) = &std::wistringstream::`vftable';
  *(_DWORD *)((char *)&v97 + *(int *)(v98[0] + 4LL) + 4) = *(_DWORD *)(v98[0] + 4LL) - 144;
  std::wstringbuf::~wstringbuf(v99);
  std::wistream::~wistream<wchar_t,std::char_traits<wchar_t>>(v100);
  std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v101);
}

```

## disassembly

```asm
0x18043a2b0  mov     [rsp-8+arg_8], rbx
0x18043a2b5  mov     [rsp-8+arg_10], rsi
0x18043a2ba  mov     [rsp-8+arg_18], rdi
0x18043a2bf  push    rbp
0x18043a2c0  push    r12
0x18043a2c2  push    r13
0x18043a2c4  push    r14
0x18043a2c6  push    r15
0x18043a2c8  lea     rbp, [rsp-1B0h]
0x18043a2d0  sub     rsp, 2B0h
0x18043a2d7  mov     rax, cs:__security_cookie
0x18043a2de  xor     rax, rsp
0x18043a2e1  mov     [rbp+1D0h+var_30], rax
0x18043a2e8  mov     rsi, rcx
0x18043a2eb  mov     [rsp+2D0h+var_298], rcx
0x18043a2f0  xor     edi, edi
0x18043a2f2  mov     dword ptr [rsp+2D0h+var_2A0], edi
0x18043a2f6  xor     edx, edx; Val
0x18043a2f8  mov     r8d, 0F0h; Size
0x18043a2fe  lea     rcx, [rbp+1D0h+var_120]; void *
0x18043a305  call    memset_0
0x18043a30a  lea     rax, ??_8?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B@; const std::wistringstream::`vbtable'
0x18043a311  mov     [rbp+1D0h+var_120], rax
0x18043a318  lea     rcx, [rbp+1D0h+var_90]
0x18043a31f  call    cs:__imp_??0?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAA@XZ; std::wios::wios(void)
0x18043a325  nop
0x18043a326  mov     dword ptr [rsp+2D0h+var_2A0], 1
0x18043a32e  xor     r9d, r9d
0x18043a331  xor     r8d, r8d
0x18043a334  lea     rdx, [rbp+1D0h+var_110]
0x18043a33b  lea     rcx, [rbp+1D0h+var_120]
0x18043a342  call    cs:__imp_??0?$basic_istream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@_N@Z; std::wistream::wistream(std::wstreambuf *,bool)
0x18043a348  nop
0x18043a349  mov     rax, [rbp+1D0h+var_120]
0x18043a350  movsxd  rcx, dword ptr [rax+4]
0x18043a354  lea     r14, ??_7?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wistringstream::`vftable'
0x18043a35b  mov     [rbp+rcx+1D0h+var_120], r14
0x18043a363  mov     rax, [rbp+1D0h+var_120]
0x18043a36a  movsxd  rcx, dword ptr [rax+4]
0x18043a36e  lea     edx, [rcx-90h]
0x18043a374  mov     [rbp+rcx+1D0h+var_124], edx
0x18043a37b  lea     rdx, [rsi+50h]
0x18043a37f  lea     r8d, [rdi+1]
0x18043a383  lea     rcx, [rbp+1D0h+var_110]
0x18043a38a  call    ??0?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wstringbuf::wstringbuf(std::wstring const &,int)
0x18043a38f  nop
0x18043a390  xorps   xmm0, xmm0
0x18043a393  xor     eax, eax
0x18043a395  movups  xmmword ptr [rbp+1D0h+Src], xmm0
0x18043a399  mov     [rbp+1D0h+var_168], rax
0x18043a39d  lea     rax, [rbp+1D0h+var_208]
0x18043a3a1  mov     [rsp+2D0h+var_2A8], rax
0x18043a3a6  lea     rax, [rsp+2D0h+var_258]
0x18043a3ab  mov     [rsp+2D0h+var_2B0], rax
0x18043a3b0  movdqu  [rbp+1D0h+var_208], xmm0
0x18043a3b5  mov     [rbp+1D0h+var_1F0], rdi
0x18043a3b9  mov     [rbp+1D0h+var_1E8], 7
0x18043a3c1  lea     rax, [rbp+1D0h+var_208]
0x18043a3c5  mov     [rsp+2D0h+var_2A0], rax
0x18043a3ca  lea     rax, [rbp+1D0h+var_120]
0x18043a3d1  mov     [rsp+2D0h+var_258], rax
0x18043a3d6  mov     [rbp+1D0h+var_250], rdi
0x18043a3da  mov     [rbp+1D0h+var_240], rdi
0x18043a3de  mov     [rbp+1D0h+var_238], 7
0x18043a3e6  lea     rdx, [rbp+1D0h+var_250]
0x18043a3ea  lea     rcx, [rbp+1D0h+var_120]
0x18043a3f1  call    ??$?5_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@$$QEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator>><wchar_t>(std::wistream &&,std::wstring &)
0x18043a3f6  mov     rcx, [rax]
0x18043a3f9  movsxd  rdx, dword ptr [rcx+4]
0x18043a3fd  test    byte ptr [rdx+rax+10h], 6
0x18043a402  mov     rax, [rsp+2D0h+var_258]
0x18043a407  cmovnz  rax, rdi
0x18043a40b  mov     [rsp+2D0h+var_258], rax
0x18043a410  lea     rax, [rsp+2D0h+var_258]
0x18043a415  mov     [rsp+2D0h+var_2A8], rax
0x18043a41a  xorps   xmm0, xmm0
0x18043a41d  movdqu  xmmword ptr [rbp+1D0h+Src], xmm0
0x18043a422  mov     [rbp+1D0h+var_168], rdi
0x18043a426  lea     rax, [rbp+1D0h+var_1C0]
0x18043a42a  mov     [rsp+2D0h+var_2B0], rax
0x18043a42f  mov     rax, qword ptr [rbp+1D0h+var_208]
0x18043a433  mov     [rbp+1D0h+var_1C0], rax
0x18043a437  lea     rdx, [rbp+1D0h+var_208+8]
0x18043a43b  lea     rcx, [rbp+1D0h+var_1B8]
0x18043a43f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18043a444  lea     rax, [rbp+1D0h+var_1C0]
0x18043a448  mov     [rsp+2D0h+var_290], rax
0x18043a44d  mov     rax, [rsp+2D0h+var_258]
0x18043a452  mov     [rsp+2D0h+var_280], rax
0x18043a457  lea     rdx, [rbp+1D0h+var_250]
0x18043a45b  lea     rcx, [rsp+2D0h+var_278]
0x18043a460  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18043a465  lea     rax, [rsp+2D0h+var_280]
0x18043a46a  mov     qword ptr [rbp+1D0h+var_230], rax
0x18043a46e  lea     rax, [rbp+1D0h+Src]
0x18043a472  mov     [rsp+2D0h+var_2B0], rax
0x18043a477  mov     rax, [rbp+1D0h+var_1C0]
0x18043a47b  cmp     [rsp+2D0h+var_280], rax
0x18043a480  jz      short loc_18043A4E3
0x18043a482  mov     rax, [rbp+1D0h+Src+8]
0x18043a486  cmp     rax, [rbp+1D0h+var_168]
0x18043a48a  jz      short loc_18043A4A0
0x18043a48c  lea     rdx, [rsp+2D0h+var_278]
0x18043a491  mov     rcx, rax
0x18043a494  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18043a499  add     [rbp+1D0h+Src+8], 20h ; ' '
0x18043a49e  jmp     short loc_18043A4B1
0x18043a4a0  lea     r8, [rsp+2D0h+var_278]
0x18043a4a5  mov     rdx, rax
0x18043a4a8  lea     rcx, [rbp+1D0h+Src]
0x18043a4ac  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18043a4b1  lea     rdx, [rsp+2D0h+var_278]
0x18043a4b6  mov     rcx, [rsp+2D0h+var_280]
0x18043a4bb  call    ??$?5_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@$$QEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator>><wchar_t>(std::wistream &&,std::wstring &)
0x18043a4c0  mov     rcx, [rax]
0x18043a4c3  movsxd  rdx, dword ptr [rcx+4]
0x18043a4c7  test    byte ptr [rdx+rax+10h], 6
0x18043a4cc  jz      short loc_18043A4D8
0x18043a4ce  mov     [rsp+2D0h+var_280], rdi
0x18043a4d3  mov     rax, rdi
0x18043a4d6  jmp     short loc_18043A4DD
0x18043a4d8  mov     rax, [rsp+2D0h+var_280]
0x18043a4dd  cmp     rax, [rbp+1D0h+var_1C0]
0x18043a4e1  jnz     short loc_18043A482
0x18043a4e3  lea     rcx, [rsp+2D0h+var_278]
0x18043a4e8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18043a4ed  nop
0x18043a4ee  lea     rcx, [rbp+1D0h+var_1B8]
0x18043a4f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18043a4f7  nop
0x18043a4f8  lea     rcx, [rbp+1D0h+var_250]
0x18043a4fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18043a501  nop
0x18043a502  lea     rcx, [rbp+1D0h+var_208+8]
0x18043a506  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18043a50b  nop
0x18043a50c  mov     r12, [rbp+1D0h+Src]
0x18043a510  mov     rbx, [rbp+1D0h+Src+8]
0x18043a514  mov     [rsp+2D0h+var_2A8], rbx
0x18043a519  cmp     r12, rbx
0x18043a51c  jz      loc_18043ABE6
0x18043a522  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a529  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18043a533  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18043a53d  mov     [rbp+1D0h+var_160], rdi
0x18043a541  mov     [rbp+1D0h+var_150], rdi
0x18043a548  mov     [rbp+1D0h+var_148], rdi
0x18043a54f  mov     rbx, [r12+10h]
0x18043a554  mov     rdi, r12
0x18043a557  cmp     qword ptr [r12+18h], 8
0x18043a55d  jb      short loc_18043A563
0x18043a55f  mov     rdi, [r12]
0x18043a563  cmp     rbx, 8
0x18043a567  jnb     short loc_18043A578
0x18043a569  movups  xmm0, xmmword ptr [rdi]
0x18043a56c  movups  xmmword ptr [rbp+1D0h+var_160], xmm0
0x18043a570  mov     r15d, 7
0x18043a576  jmp     short loc_18043A5BC
0x18043a578  mov     r15, rbx
0x18043a57b  or      r15, 7
0x18043a57f  cmp     r15, rcx
0x18043a582  cmova   r15, rcx
0x18043a586  lea     rcx, [r15+1]
0x18043a58a  cmp     rcx, rdx
0x18043a58d  ja      loc_18043ACCE
0x18043a593  lfence
0x18043a596  add     rcx, rcx
0x18043a599  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x18043a59e  mov     [rbp+1D0h+var_160], rax
0x18043a5a2  lea     r8, ds:2[rbx*2]; Size
0x18043a5aa  mov     rdx, rdi; Src
0x18043a5ad  mov     rcx, rax; void *
0x18043a5b0  call    memcpy_0
0x18043a5b5  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a5bc  mov     [rbp+1D0h+var_148], r15
0x18043a5c3  mov     [rbp+1D0h+var_150], rbx
0x18043a5ca  lea     r14, [rsi+70h]
0x18043a5ce  mov     rdi, [r14]
0x18043a5d1  mov     r10, [rdi+8]
0x18043a5d5  mov     r13, [rbp+1D0h+var_160]
0x18043a5d9  cmp     byte ptr [r10+19h], 0
0x18043a5de  jnz     loc_18043A685
0x18043a5e4  nop     dword ptr [rax+00h]
0x18043a5e8  nop     dword ptr [rax+rax+00000000h]
0x18043a5f0  lea     rax, [rbp+1D0h+var_160]
0x18043a5f4  cmp     r15, 8
0x18043a5f8  cmovnb  rax, r13
0x18043a5fc  lea     r9, [r10+20h]
0x18043a600  cmp     qword ptr [r10+38h], 8
0x18043a605  jb      short loc_18043A60B
0x18043a607  mov     r9, [r10+20h]
0x18043a60b  mov     r11, [r10+30h]
0x18043a60f  mov     rcx, r11
0x18043a612  cmp     rbx, r11
0x18043a615  cmovb   rcx, rbx
0x18043a619  test    rcx, rcx
0x18043a61c  jz      short loc_18043A635
0x18043a61e  sub     r9, rax
0x18043a621  movzx   edx, word ptr [r9+rax]
0x18043a626  cmp     dx, [rax]
0x18043a629  jnz     short loc_18043A646
0x18043a62b  add     rax, 2
0x18043a62f  sub     rcx, 1
0x18043a633  jnz     short loc_18043A621
0x18043a635  cmp     r11, rbx
0x18043a638  jnb     short loc_18043A658
0x18043a63a  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a641  mov     eax, r11d
0x18043a644  jmp     short loc_18043A667
0x18043a646  mov     eax, 1
0x18043a64b  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a652  cmovb   eax, r11d
0x18043a656  jmp     short loc_18043A667
0x18043a658  xor     eax, eax
0x18043a65a  cmp     r11, rbx
0x18043a65d  setnbe  al
0x18043a660  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a667  shr     eax, 1Fh
0x18043a66a  test    al, al
0x18043a66c  jz      short loc_18043A674
0x18043a66e  mov     r10, [r10+10h]
0x18043a672  jmp     short loc_18043A67A
0x18043a674  mov     rdi, r10
0x18043a677  mov     r10, [r10]
0x18043a67a  cmp     byte ptr [r10+19h], 0
0x18043a67f  jz      loc_18043A5F0
0x18043a685  cmp     byte ptr [rdi+19h], 0
0x18043a689  jnz     short loc_18043A6FC
0x18043a68b  lea     rax, [rdi+20h]
0x18043a68f  cmp     qword ptr [rdi+38h], 8
0x18043a694  jb      short loc_18043A69A
0x18043a696  mov     rax, [rdi+20h]
0x18043a69a  lea     r9, [rbp+1D0h+var_160]
0x18043a69e  cmp     r15, 8
0x18043a6a2  cmovnb  r9, r13
0x18043a6a6  mov     r10, [rdi+30h]
0x18043a6aa  mov     rcx, rbx
0x18043a6ad  cmp     r10, rbx
0x18043a6b0  cmovb   rcx, r10
0x18043a6b4  test    rcx, rcx
0x18043a6b7  jz      short loc_18043A6D4
0x18043a6b9  sub     r9, rax
0x18043a6bc  nop     dword ptr [rax+00h]
0x18043a6c0  movzx   edx, word ptr [r9+rax]
0x18043a6c5  cmp     dx, [rax]
0x18043a6c8  jnz     short loc_18043A6DE
0x18043a6ca  add     rax, 2
0x18043a6ce  sub     rcx, 1
0x18043a6d2  jnz     short loc_18043A6C0
0x18043a6d4  cmp     rbx, r10
0x18043a6d7  jnb     short loc_18043A6E9
0x18043a6d9  mov     eax, r11d
0x18043a6dc  jmp     short loc_18043A6F1
0x18043a6de  mov     eax, 1
0x18043a6e3  cmovb   eax, r11d
0x18043a6e7  jmp     short loc_18043A6F1
0x18043a6e9  xor     eax, eax
0x18043a6eb  cmp     rbx, r10
0x18043a6ee  setnbe  al
0x18043a6f1  shr     eax, 1Fh
0x18043a6f4  test    al, al
0x18043a6f6  jnz     short loc_18043A6FC
0x18043a6f8  mov     al, 1
0x18043a6fa  jmp     short loc_18043A6FE
0x18043a6fc  xor     al, al
0x18043a6fe  cmp     al, 1
0x18043a700  jb      loc_18043ACE0
0x18043a706  mov     rsi, [r14]
0x18043a709  mov     r10, [rsi+8]
0x18043a70d  mov     qword ptr [rbp+1D0h+var_220], r10
0x18043a711  mov     dword ptr [rbp+1D0h+var_220+8], 0
0x18043a718  mov     rdi, rsi
0x18043a71b  cmp     byte ptr [r10+19h], 0
0x18043a720  jnz     loc_18043A7D7
0x18043a726  nop     word ptr [rax+rax+00000000h]
0x18043a730  mov     qword ptr [rbp+1D0h+var_220], r10
0x18043a734  lea     rax, [rbp+1D0h+var_160]
0x18043a738  cmp     r15, 8
0x18043a73c  cmovnb  rax, r13
0x18043a740  lea     r9, [r10+20h]
0x18043a744  cmp     qword ptr [r10+38h], 8
0x18043a749  jb      short loc_18043A74F
0x18043a74b  mov     r9, [r10+20h]
0x18043a74f  mov     r11, [r10+30h]
0x18043a753  mov     rcx, r11
0x18043a756  cmp     rbx, r11
0x18043a759  cmovb   rcx, rbx
0x18043a75d  test    rcx, rcx
0x18043a760  jz      short loc_18043A779
0x18043a762  sub     r9, rax
0x18043a765  movzx   edx, word ptr [r9+rax]
0x18043a76a  cmp     dx, [rax]
0x18043a76d  jnz     short loc_18043A78A
0x18043a76f  add     rax, 2
0x18043a773  sub     rcx, 1
0x18043a777  jnz     short loc_18043A765
0x18043a779  cmp     r11, rbx
0x18043a77c  jnb     short loc_18043A79C
0x18043a77e  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18043a785  mov     eax, r11d
  ... truncated ...
```

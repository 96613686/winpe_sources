# Spectre::Transcoder::PLYParser::GetElement(Spectre::Transcoder::PlyElement &,std::function<void (std::basic_string<char,std::char_traits<char>,std::allocator<char>>,__int64,unsigned __int64,float)>,std::function<void (std::basic_string<char,std::char_traits<char>,std::allocator<char>>,unsigned __int64,__int64,unsigned __int64,float)>,std::function<void (std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)>)

- ea: `0x180368e80`
- end: `0x180369a3e`
- name: `?GetElement@PLYParser@Transcoder@Spectre@@AEAAXAEAUPlyElement@23@V?$function@$$A6AXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_J_KM@Z@std@@V?$function@$$A6AXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_J1M@Z@6@V?$function@$$A6AXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z@6@@Z`
- size: `3006`
- prototype: `__int64 __fastcall(_QWORD **, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callers

- `0x18036ba70`

## callees

- `0x180014a60`
- `0x180014b80`
- `0x1800157b0`
- `0x180016430`
- `0x180040860`
- `0x1801a2500`
- `0x180368190`
- `0x180368200`
- `0x180368280`
- `0x180368e80`
- `0x18036d080`
- `0x18036d260`
- `0x18036d6e0`
- `0x18036d980`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8f0`
- `0x18039f910`
- `0x18039faa0`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180369806`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180369806`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1803692de`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180369346`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1803692de`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180369346`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180368fce`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180369974`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036997b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180369982`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180368fce`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180369974`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036997b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180369982`

## pseudocode

```c
__int64 __fastcall Spectre::Transcoder::PLYParser::GetElement(
        _QWORD **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rdx
  _QWORD *v11; // rbx
  _QWORD *v12; // rsi
  char *v13; // rbx
  char *v14; // rdi
  unsigned __int64 v15; // rdx
  _QWORD *v16; // rcx
  char *v17; // rax
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rdi
  __int64 result; // rax
  size_t v21; // r15
  __int64 v22; // r8
  __int64 v23; // rcx
  _DWORD *v24; // rbx
  int v25; // ecx
  __int64 v26; // rbx
  __int64 v27; // rax
  unsigned __int64 v28; // r13
  int v29; // r15d
  __int64 v30; // r12
  __int64 v31; // rax
  void *v32; // rcx
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // r8
  char v36; // r14
  _QWORD *v37; // rax
  __int64 v38; // r15
  __int64 v39; // r13
  __int64 v40; // rcx
  _QWORD *v41; // rax
  _DWORD *v42; // rbx
  int v43; // ecx
  volatile signed __int32 *v44; // rcx
  __int64 v45; // rsi
  _QWORD *v46; // rbx
  __int64 v47; // rcx
  volatile signed __int32 *v48; // rcx
  size_t v49; // r14
  int i; // ebx
  volatile signed __int32 *v51; // rcx
  _QWORD *v52; // rsi
  __int64 v53; // rcx
  void *v54; // rcx
  __int64 v55; // rcx
  volatile signed __int32 *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  size_t v59; // rsi
  void *v60; // rax
  void *v61; // rcx
  _QWORD *v62; // rax
  char *v63; // rbx
  void **v64; // r14
  unsigned __int64 v65; // rsi
  __int64 v66; // rbx
  void *v67; // rax
  void *v68; // rcx
  _QWORD *v69; // rax
  void *v70; // rcx
  __int64 v71; // rdi
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  char v75; // [rsp+40h] [rbp-C0h]
  int v76; // [rsp+50h] [rbp-B0h] BYREF
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v78; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+68h] [rbp-98h] BYREF
  __int64 v80; // [rsp+70h] [rbp-90h]
  _QWORD *v81; // [rsp+78h] [rbp-88h]
  unsigned __int64 v82; // [rsp+80h] [rbp-80h]
  __int64 v83; // [rsp+88h] [rbp-78h]
  __int64 v84; // [rsp+90h] [rbp-70h]
  __int64 v85; // [rsp+98h] [rbp-68h]
  __int64 v86; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v87; // [rsp+A8h] [rbp-58h]
  void *Block; // [rsp+B0h] [rbp-50h] BYREF
  char *v89; // [rsp+B8h] [rbp-48h]
  __int64 v90; // [rsp+C0h] [rbp-40h]
  __int128 v91; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v92; // [rsp+E0h] [rbp-20h]
  __int64 v93; // [rsp+E8h] [rbp-18h]
  __int128 v94; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v95; // [rsp+100h] [rbp+0h] BYREF
  __int128 v96; // [rsp+110h] [rbp+10h] BYREF
  __int128 v97; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v98[7]; // [rsp+130h] [rbp+30h] BYREF
  char v99[32]; // [rsp+168h] [rbp+68h] BYREF
  char v100[32]; // [rsp+188h] [rbp+88h] BYREF
  char v101[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v102[24]; // [rsp+1C8h] [rbp+C8h] BYREF
  void **p_Block; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v104; // [rsp+1E8h] [rbp+E8h]
  char *v105; // [rsp+1F8h] [rbp+F8h]
  int v106; // [rsp+200h] [rbp+100h] BYREF
  int v107; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int64 v108; // [rsp+210h] [rbp+110h] BYREF
  void *Src[2]; // [rsp+218h] [rbp+118h] BYREF
  unsigned __int64 v110; // [rsp+228h] [rbp+128h]
  unsigned __int64 v111; // [rsp+230h] [rbp+130h]
  int v112; // [rsp+238h] [rbp+138h]
  int v113; // [rsp+23Ch] [rbp+13Ch]
  int v114; // [rsp+240h] [rbp+140h]
  int v115; // [rsp+244h] [rbp+144h]
  int v116; // [rsp+248h] [rbp+148h]
  unsigned __int64 v117; // [rsp+250h] [rbp+150h] BYREF
  size_t v118; // [rsp+258h] [rbp+158h] BYREF
  size_t v119; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v120[3]; // [rsp+268h] [rbp+168h] BYREF
  unsigned __int64 v121; // [rsp+280h] [rbp+180h]
  int v122; // [rsp+288h] [rbp+188h]
  int v123; // [rsp+28Ch] [rbp+18Ch]
  int v124; // [rsp+290h] [rbp+190h]
  int v125; // [rsp+294h] [rbp+194h]
  int v126; // [rsp+298h] [rbp+198h]

  v5 = a4;
  v80 = a4;
  v86 = a3;
  v6 = a2;
  v84 = a2;
  v98[6] = a3;
  v98[5] = a4;
  v8 = a5;
  v98[4] = a5;
  Spectre::Transcoder::PLYParser::UpdateProgressAndCheckCancellation((Spectre::Transcoder::PLYParser *)a1);
  v9 = *((_DWORD *)a1 + 32);
  if ( v9 )
  {
    v36 = v9 == 1;
    v75 = v9 == 1;
    v37 = (_QWORD *)std::istream::tellg(**a1, &Block);
    v38 = *v37 + v37[1];
    v39 = (*a1)[2];
    v87 = 0;
    v40 = *(_QWORD *)(v84 + 48) - *(_QWORD *)(v84 + 40);
    result = (unsigned __int64)((unsigned __int128)(v40 * (__int128)0x4924924924924925LL) >> 64) >> 63;
    v10 = v40 / 56;
    if ( !(v40 / 56) )
      goto LABEL_107;
    v85 = 0;
    while ( 1 )
    {
      if ( v38 == v39 )
        goto LABEL_107;
      v41 = (_QWORD *)std::istream::tellg(**a1, v102);
      v38 = *v41 + v41[1];
      Size = 0;
      v78 = 0;
      v76 = 0;
      v42 = (_DWORD *)(*(_QWORD *)(v84 + 40) + v85);
      std::string::string(Src, v42);
      v43 = v42[8];
      v112 = v43;
      v113 = v42[9];
      v114 = v42[10];
      v115 = v42[11];
      v116 = v42[12];
      if ( !v43 )
        break;
      if ( v43 == 1 )
      {
        v94 = 0;
        v48 = (volatile signed __int32 *)a1[1];
        if ( v48 )
        {
          _InterlockedIncrement(v48 + 2);
          v48 = (volatile signed __int32 *)a1[1];
        }
        *(_QWORD *)&v94 = *a1;
        *((_QWORD *)&v94 + 1) = v48;
        Spectre::Transcoder::get_binary_item(&v94, v36, (__int64)&v78, (__int64)&Size, (__int64)&v76);
        v49 = Size;
        for ( i = 1; i <= v49; ++i )
        {
          if ( v38 == v39 )
            break;
          v96 = 0;
          v51 = (volatile signed __int32 *)a1[1];
          if ( v51 )
          {
            _InterlockedIncrement(v51 + 2);
            v51 = (volatile signed __int32 *)a1[1];
          }
          *(_QWORD *)&v96 = *a1;
          *((_QWORD *)&v96 + 1) = v51;
          Spectre::Transcoder::get_binary_item(&v96, v75, (__int64)&v78, (__int64)&Size, (__int64)&v76);
          if ( *(_QWORD *)(v5 + 56) )
          {
            v52 = (_QWORD *)std::string::string(v101, Src);
            v81 = v52;
            v106 = v76;
            v119 = Size;
            v108 = v78;
            p_Block = (void **)i;
            v53 = *(_QWORD *)(v80 + 56);
            if ( !v53 )
              goto LABEL_116;
            (*(void (__fastcall **)(__int64, _QWORD *, void ***, unsigned __int64 *, size_t *, int *))(*(_QWORD *)v53 + 16LL))(
              v53,
              v52,
              &p_Block,
              &v108,
              &v119,
              &v106);
            std::string::~string(v52);
            v5 = v80;
          }
        }
        v36 = v75;
LABEL_61:
        v8 = a5;
        goto LABEL_62;
      }
      v8 = a5;
      if ( v43 == 2 && *(_QWORD *)(a5 + 56) )
      {
        v97 = 0;
        v56 = (volatile signed __int32 *)a1[1];
        if ( v56 )
        {
          _InterlockedIncrement(v56 + 2);
          v56 = (volatile signed __int32 *)a1[1];
        }
        *(_QWORD *)&v97 = *a1;
        *((_QWORD *)&v97 + 1) = v56;
        Spectre::Transcoder::get_binary_item(&v97, v36, (__int64)&v78, (__int64)&Size, (__int64)&v76);
        if ( *(_QWORD *)(a5 + 56) )
        {
          v104 = 0;
          v105 = 0;
          v59 = Size;
          if ( Size )
          {
            if ( Size > 0x7FFFFFFFFFFFFFFFLL )
              std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(v58, v57);
            if ( Size < 0x1000 )
            {
              v62 = operator new(Size);
            }
            else
            {
              if ( Size + 39 < Size )
                goto LABEL_117;
              v60 = operator new(Size + 39);
              v61 = v60;
              if ( !v60 )
LABEL_103:
                _invalid_parameter_noinfo_noreturn();
              v62 = (_QWORD *)(((unsigned __int64)v60 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v62 - 1) = v61;
            }
            *(_QWORD *)&v104 = v62;
            v63 = (char *)v62 + v59;
            v105 = (char *)v62 + v59;
            memset_0(v62, 0, v59);
            *((_QWORD *)&v104 + 1) = v63;
            v8 = a5;
          }
          std::istream::read(**a1, v104, v59);
          v81 = v98;
          v98[0] = 0;
          v98[2] = 0;
          v98[3] = 15;
          if ( (_QWORD)v104 != *((_QWORD *)&v104 + 1) )
            std::string::assign(v98);
          *(_QWORD *)&v91 = 0;
          v92 = 0;
          v93 = 0;
          v64 = Src;
          if ( v111 >= 0x10 )
            v64 = (void **)Src[0];
          v65 = v110;
          if ( v110 >= 0x10 )
          {
            v66 = v110 | 0xF;
            if ( (v110 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
              v66 = 0x7FFFFFFFFFFFFFFFLL;
            if ( (unsigned __int64)(v66 + 1) < 0x1000 )
            {
              if ( v66 == -1 )
                v69 = 0;
              else
                v69 = operator new(v66 + 1);
            }
            else
            {
              if ( v66 + 40 < (unsigned __int64)(v66 + 1) )
                __scrt_throw_std_bad_array_new_length();
              v67 = operator new(v66 + 40);
              v68 = v67;
              if ( !v67 )
                _invalid_parameter_noinfo_noreturn();
              v69 = (_QWORD *)(((unsigned __int64)v67 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v69 - 1) = v68;
            }
            *(_QWORD *)&v91 = v69;
            memcpy_0(v69, v64, v65 + 1);
            v93 = v66;
            v8 = a5;
          }
          else
          {
            v91 = *(_OWORD *)v64;
            v93 = 15;
          }
          v92 = v65;
          std::_Func_class<void,std::string,std::string>::operator()(v8, &v91, v98);
          v70 = (void *)v104;
          if ( (_QWORD)v104 )
          {
            if ( (unsigned __int64)&v105[-v104] >= 0x1000 )
            {
              v70 = *(void **)(v104 - 8);
              if ( (unsigned __int64)(v104 - (_QWORD)v70 - 8) > 0x1F )
                goto LABEL_103;
            }
            operator delete(v70);
            v104 = 0;
            v105 = 0;
          }
          v36 = v75;
        }
      }
LABEL_62:
      if ( v111 >= 0x10 )
      {
        v54 = Src[0];
        if ( v111 + 1 >= 0x1000 )
        {
          v54 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v54 - 8) > 0x1F )
LABEL_104:
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v54);
      }
      ++v87;
      v85 += 56;
      v55 = *(_QWORD *)(v84 + 48) - *(_QWORD *)(v84 + 40);
      result = (unsigned __int64)((unsigned __int128)(v55 * (__int128)0x4924924924924925LL) >> 64) >> 63;
      v10 = v55 / 56;
      if ( v87 >= v55 / 56 )
        goto LABEL_106;
      v5 = v80;
    }
    v95 = 0;
    v44 = (volatile signed __int32 *)a1[1];
    if ( v44 )
    {
      _InterlockedIncrement(v44 + 2);
      v44 = (volatile signed __int32 *)a1[1];
    }
    *(_QWORD *)&v95 = *a1;
    *((_QWORD *)&v95 + 1) = v44;
    Spectre::Transcoder::get_binary_item(&v95, v36, (__int64)&v78, (__int64)&Size, (__int64)&v76);
    v45 = v86;
    if ( *(_QWORD *)(v86 + 56) )
    {
      v46 = (_QWORD *)std::string::string(v100, Src);
      v81 = v46;
      v107 = v76;
      v118 = Size;
      v117 = v78;
      v47 = *(_QWORD *)(v45 + 56);
      if ( !v47 )
      {
        std::_Xbad_function_call();
LABEL_116:
        std::_Xbad_function_call();
LABEL_117:
        __scrt_throw_std_bad_array_new_length();
      }
      (*(void (__fastcall **)(__int64, _QWORD *, unsigned __int64 *, size_t *, int *))(*(_QWORD *)v47 + 16LL))(
        v47,
        v46,
        &v117,
        &v118,
        &v107);
      std::string::~string(v46);
    }
    goto LABEL_61;
  }
  v11 = (_QWORD *)Spectre::Transcoder::PLYParser::ReadTokens(a1, &Block);
  v12 = a1 + 12;
  if ( a1 + 12 != v11 )
  {
    std::vector<std::string>::_Tidy(a1 + 12);
    *v12 = *v11;
    a1[13] = (_QWORD *)v11[1];
    a1[14] = (_QWORD *)v11[2];
    *v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
  }
  v13 = (char *)Block;
  if ( Block )
  {
    v14 = v89;
    if ( Block != v89 )
    {
      do
      {
        v15 = *((_QWORD *)v13 + 3);
        if ( v15 >= 0x10 )
        {
          v16 = *(_QWORD **)v13;
          if ( v15 + 1 >= 0x1000 )
          {
            if ( (unsigned __int64)v16 - *(v16 - 1) - 8 > 0x1F )
              goto LABEL_15;
            v16 = (_QWORD *)*(v16 - 1);
          }
          operator delete(v16);
        }
        *((_QWORD *)v13 + 2) = 0;
        *((_QWORD *)v13 + 3) = 15;
        *v13 = 0;
        v13 += 32;
      }
      while ( v13 != v14 );
      v13 = (char *)Block;
    }
    v17 = v13;
    if ( ((v90 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFE0uLL) >= 0x1000 )
    {
      v13 = (char *)*((_QWORD *)v13 - 1);
      if ( (unsigned __int64)(v17 - v13 - 8) > 0x1F )
LABEL_15:
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v13);
  }
  v18 = 0;
  v78 = 0;
  v19 = 0;
  result = (__int64)(v12[1] - *v12) >> 5;
  if ( result )
  {
    v21 = 0;
    Size = 0;
    while ( 1 )
    {
      v22 = *(_QWORD *)(v6 + 40);
      v23 = *(_QWORD *)(v6 + 48) - v22;
      result = (unsigned __int64)((unsigned __int128)(v23 * (__int128)0x4924924924924925LL) >> 64) >> 63;
      v10 = v23 / 56;
      if ( v18 >= v23 / 56 )
        goto LABEL_105;
      v82 = 0;
      v83 = 0;
      LODWORD(v79) = 0;
      v24 = (_DWORD *)(v21 + v22);
      std::string::string(v120, v21 + v22);
      v25 = v24[8];
      v122 = v25;
      v123 = v24[9];
      v124 = v24[10];
      v125 = v24[11];
      v126 = v24[12];
      if ( !v25 )
        break;
      if ( v25 == 1 )
      {
        if ( *(_QWORD *)(v80 + 56) )
        {
          Spectre::Transcoder::get_ascii_item((char *)(*v12 + 32 * v19), (__int64)&v79);
          v28 = v82;
          ++v19;
          v29 = 0;
          if ( v19 < (__int64)(v12[1] - *v12) >> 5 )
          {
            v30 = 32 * v19;
            do
            {
              if ( v29 >= v28 )
                break;
              Spectre::Transcoder::get_ascii_item((char *)(v30 + *v12), (__int64)&v79);
              v31 = std::string::string(&Block, v120);
              std::_Func_class<void,std::string,unsigned __int64,__int64,unsigned __int64,float>::operator()(
                v80,
                v31,
                v29++,
                v83,
                v82,
                v79);
              ++v19;
              v30 += 32;
            }
            while ( v19 < (__int64)(v12[1] - *v12) >> 5 );
          }
          v18 = v78;
          v21 = Size;
        }
        goto LABEL_30;
      }
      if ( v25 != 2 )
        goto LABEL_30;
      v8 = a5;
      if ( *(_QWORD *)(a5 + 56) )
      {
        p_Block = &Block;
        v33 = std::string::string(&Block, *v12 + 32 * v19);
        v34 = std::string::string(v99, v120);
        v35 = v33;
        v8 = a5;
        std::_Func_class<void,std::string,std::string>::operator()(a5, v34, v35);
        ++v19;
      }
LABEL_31:
      v10 = v121;
      if ( v121 >= 0x10 )
      {
        v32 = (void *)v120[0];
        if ( v121 + 1 >= 0x1000 )
        {
          v32 = *(void **)(v120[0] - 8LL);
          if ( (unsigned __int64)(v120[0] - (_QWORD)v32 - 8LL) > 0x1F )
            goto LABEL_104;
        }
        operator delete(v32);
      }
      v78 = ++v18;
      v21 += 56LL;
      Size = v21;
      v6 = v84;
      result = 0x4924924924924925LL;
      if ( v19 >= (__int64)(v12[1] - *v12) >> 5 )
        goto LABEL_106;
    }
    v26 = v86;
    if ( *(_QWORD *)(v86 + 56) )
    {
      Spectre::Transcoder::get_ascii_item((char *)(*v12 + 32 * v19++), (__int64)&v79);
      v27 = std::string::string(&Block, v120);
      std::_Func_class<void,std::string,__int64,unsigned __int64,float>::operator()(v26, v27, v83, v82, v79);
    }
LABEL_30:
    v8 = a5;
    goto LABEL_31;
  }
LABEL_105:
  v8 = a5;
LABEL_106:
  v5 = v80;
LABEL_107:
  v71 = v86;
  v72 = *(_QWORD *)(v86 + 56);
  if ( v72 )
  {
    LOBYTE(v10) = v72 != v86;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 32LL))(v72, v10);
    *(_QWORD *)(v71 + 56) = 0;
  }
  v73 = *(_QWORD *)(v5 + 56);
  if ( v73 )
  {
    LOBYTE(v10) = v73 != v5;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 32LL))(v73, v10);
    *(_QWORD *)(v5 + 56) = 0;
  }
  v74 = *(_QWORD *)(v8 + 56);
  if ( v74 )
  {
    LOBYTE(v10) = v74 != v8;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 32LL))(v74, v10);
    *(_QWORD *)(v8 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180368e80  push    rbp
0x180368e82  push    rbx
0x180368e83  push    rsi
0x180368e84  push    rdi
0x180368e85  push    r12
0x180368e87  push    r13
0x180368e89  push    r14
0x180368e8b  push    r15
0x180368e8d  lea     rbp, [rsp-1B8h]
0x180368e95  sub     rsp, 2B8h
0x180368e9c  mov     rax, cs:__security_cookie
0x180368ea3  xor     rax, rsp
0x180368ea6  mov     [rbp+1F0h+var_50], rax
0x180368ead  mov     rsi, r9
0x180368eb0  mov     [rsp+2F0h+var_280], r9
0x180368eb5  mov     rax, r8
0x180368eb8  mov     [rbp+1F0h+var_250], rax
0x180368ebc  mov     r14, rdx
0x180368ebf  mov     [rbp+1F0h+var_260], rdx
0x180368ec3  mov     rdi, rcx
0x180368ec6  mov     [rbp+1F0h+var_190], rax
0x180368eca  mov     [rbp+1F0h+var_198], r9
0x180368ece  mov     rbx, [rbp+1F0h+arg_20]
0x180368ed5  mov     [rsp+2F0h+var_2A8], rbx
0x180368eda  mov     [rbp+1F0h+var_1A0], rbx
0x180368ede  call    ?UpdateProgressAndCheckCancellation@PLYParser@Transcoder@Spectre@@AEAAXXZ; Spectre::Transcoder::PLYParser::UpdateProgressAndCheckCancellation(void)
0x180368ee3  mov     eax, [rdi+80h]
0x180368ee9  lea     rdx, [rbp+1F0h+Block]
0x180368eed  test    eax, eax
0x180368eef  jnz     loc_1803692CC
0x180368ef5  mov     rcx, rdi
0x180368ef8  call    ?ReadTokens@PLYParser@Transcoder@Spectre@@AEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; Spectre::Transcoder::PLYParser::ReadTokens(void)
0x180368efd  mov     rbx, rax
0x180368f00  lea     rsi, [rdi+60h]
0x180368f04  xor     r12d, r12d
0x180368f07  cmp     rsi, rax
0x180368f0a  jz      short loc_180368F35
0x180368f0c  mov     rcx, rsi
0x180368f0f  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x180368f14  mov     rcx, [rbx]
0x180368f17  mov     [rsi], rcx
0x180368f1a  mov     rcx, [rbx+8]
0x180368f1e  mov     [rsi+8], rcx
0x180368f22  mov     rax, [rbx+10h]
0x180368f26  mov     [rsi+10h], rax
0x180368f2a  mov     [rbx], r12
0x180368f2d  mov     [rbx+8], r12
0x180368f31  mov     [rbx+10h], r12
0x180368f35  mov     rbx, [rbp+1F0h+Block]
0x180368f39  test    rbx, rbx
0x180368f3c  jz      loc_180368FDD
0x180368f42  mov     rdi, [rbp+1F0h+var_238]
0x180368f46  cmp     rbx, rdi
0x180368f49  jz      short loc_180368FA2
0x180368f4b  nop     dword ptr [rax+rax+00h]
0x180368f50  mov     rdx, [rbx+18h]
0x180368f54  cmp     rdx, 10h
0x180368f58  jb      short loc_180368F86
0x180368f5a  mov     rcx, [rbx]
0x180368f5d  inc     rdx
0x180368f60  cmp     rdx, 1000h
0x180368f67  jb      short loc_180368F81
0x180368f69  add     rdx, 27h ; '''
0x180368f6d  mov     r8, [rcx-8]
0x180368f71  sub     rcx, r8
0x180368f74  lea     rax, [rcx-8]
0x180368f78  cmp     rax, 1Fh
0x180368f7c  ja      short loc_180368FCE
0x180368f7e  mov     rcx, r8; Block
0x180368f81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180368f86  mov     [rbx+10h], r12
0x180368f8a  mov     qword ptr [rbx+18h], 0Fh
0x180368f92  mov     [rbx], r12b
0x180368f95  add     rbx, 20h ; ' '
0x180368f99  cmp     rbx, rdi
0x180368f9c  jnz     short loc_180368F50
0x180368f9e  mov     rbx, [rbp+1F0h+Block]
0x180368fa2  mov     rdx, [rbp+1F0h+var_230]
0x180368fa6  sub     rdx, rbx
0x180368fa9  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180368fad  mov     rax, rbx
0x180368fb0  cmp     rdx, 1000h
0x180368fb7  jb      short loc_180368FD5
0x180368fb9  add     rdx, 27h ; '''
0x180368fbd  mov     rbx, [rbx-8]
0x180368fc1  sub     rax, rbx
0x180368fc4  add     rax, 0FFFFFFFFFFFFFFF8h
0x180368fc8  cmp     rax, 1Fh
0x180368fcc  jbe     short loc_180368FD5
0x180368fce  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180368fd5  mov     rcx, rbx; Block
0x180368fd8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180368fdd  mov     r13, r12
0x180368fe0  mov     [rsp+2F0h+var_290], r12
0x180368fe5  mov     rdi, r12
0x180368fe8  mov     rax, [rsi+8]
0x180368fec  sub     rax, [rsi]
0x180368fef  sar     rax, 5
0x180368ff3  test    rax, rax
0x180368ff6  jz      loc_180369989
0x180368ffc  mov     r15, r12
0x180368fff  mov     [rsp+2F0h+Size], r12
0x180369004  mov     rax, 4924924924924925h
0x18036900e  xchg    ax, ax
0x180369010  mov     r8, [r14+28h]
0x180369014  mov     rcx, [r14+30h]
0x180369018  sub     rcx, r8
0x18036901b  imul    rcx
0x18036901e  sar     rdx, 4
0x180369022  mov     rax, rdx
0x180369025  shr     rax, 3Fh
0x180369029  add     rdx, rax
0x18036902c  cmp     r13, rdx
0x18036902f  jnb     loc_180369989
0x180369035  mov     [rbp+1F0h+var_270], r12
0x180369039  mov     [rbp+1F0h+var_268], r12
0x18036903d  mov     dword ptr [rsp+2F0h+var_288], 0
0x180369045  lea     rbx, [r15+r8]
0x180369049  mov     rdx, rbx
0x18036904c  lea     rcx, [rbp+1F0h+var_88]
0x180369053  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180369058  mov     ecx, [rbx+20h]
0x18036905b  mov     [rbp+1F0h+var_68], ecx
0x180369061  mov     r14d, [rbx+24h]
0x180369065  mov     [rbp+1F0h+var_64], r14d
0x18036906c  mov     eax, [rbx+28h]
0x18036906f  mov     [rbp+1F0h+var_60], eax
0x180369075  mov     edx, [rbx+2Ch]
0x180369078  mov     [rbp+1F0h+var_5C], edx
0x18036907e  mov     eax, [rbx+30h]
0x180369081  mov     [rbp+1F0h+var_58], eax
0x180369087  test    ecx, ecx
0x180369089  jnz     short loc_1803690F5
0x18036908b  mov     rbx, [rbp+1F0h+var_250]
0x18036908f  cmp     qword ptr [rbx+38h], 0
0x180369094  jz      loc_1803691E8
0x18036909a  mov     rcx, rdi
0x18036909d  shl     rcx, 5
0x1803690a1  add     rcx, [rsi]; String
0x1803690a4  lea     rax, [rsp+2F0h+var_288]
0x1803690a9  mov     [rsp+2F0h+var_2D0], rax; __int64
0x1803690ae  lea     r9, [rbp+1F0h+var_270]
0x1803690b2  lea     r8, [rbp+1F0h+var_268]
0x1803690b6  mov     edx, r14d
0x1803690b9  call    ?get_ascii_item@Transcoder@Spectre@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4PLYDataType@12@PEA_JPEA_KPEAM@Z; Spectre::Transcoder::get_ascii_item(std::string const &,Spectre::Transcoder::PLYDataType,__int64 *,unsigned __int64 *,float *)
0x1803690be  inc     rdi
0x1803690c1  lea     rdx, [rbp+1F0h+var_88]
0x1803690c8  lea     rcx, [rbp+1F0h+Block]
0x1803690cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1803690d1  movss   xmm0, dword ptr [rsp+2F0h+var_288]
0x1803690d7  movss   dword ptr [rsp+2F0h+var_2D0], xmm0
0x1803690dd  mov     r9, [rbp+1F0h+var_270]
0x1803690e1  mov     r8, [rbp+1F0h+var_268]
0x1803690e5  mov     rdx, rax
0x1803690e8  mov     rcx, rbx
0x1803690eb  call    ??R?$_Func_class@XV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_J_KM@std@@QEBAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_J_KM@Z; std::_Func_class<void,std::string,__int64,unsigned __int64,float>::operator()(std::string,__int64,unsigned __int64,float)
0x1803690f0  jmp     loc_1803691E8
0x1803690f5  cmp     ecx, 1
0x1803690f8  jnz     loc_180369266
0x1803690fe  mov     rax, [rsp+2F0h+var_280]
0x180369103  cmp     qword ptr [rax+38h], 0
0x180369108  jz      loc_1803691E8
0x18036910e  mov     rcx, rdi
0x180369111  shl     rcx, 5
0x180369115  add     rcx, [rsi]; String
0x180369118  lea     rax, [rsp+2F0h+var_288]
0x18036911d  mov     [rsp+2F0h+var_2D0], rax; __int64
0x180369122  lea     r9, [rbp+1F0h+var_270]
0x180369126  lea     r8, [rbp+1F0h+var_268]
0x18036912a  call    ?get_ascii_item@Transcoder@Spectre@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4PLYDataType@12@PEA_JPEA_KPEAM@Z; Spectre::Transcoder::get_ascii_item(std::string const &,Spectre::Transcoder::PLYDataType,__int64 *,unsigned __int64 *,float *)
0x18036912f  mov     r13, [rbp+1F0h+var_270]
0x180369133  inc     rdi
0x180369136  mov     r15d, r12d
0x180369139  mov     rax, [rsi+8]
0x18036913d  sub     rax, [rsi]
0x180369140  sar     rax, 5
0x180369144  cmp     rdi, rax
0x180369147  jnb     loc_1803691DE
0x18036914d  mov     r12, rdi
0x180369150  shl     r12, 5
0x180369154  movsxd  rbx, r15d
0x180369157  cmp     rbx, r13
0x18036915a  jnb     short loc_1803691DB
0x18036915c  mov     rcx, [rsi]
0x18036915f  add     rcx, r12; String
0x180369162  lea     rax, [rsp+2F0h+var_288]
0x180369167  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18036916c  lea     r9, [rbp+1F0h+var_270]
0x180369170  lea     r8, [rbp+1F0h+var_268]
0x180369174  mov     edx, r14d
0x180369177  call    ?get_ascii_item@Transcoder@Spectre@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4PLYDataType@12@PEA_JPEA_KPEAM@Z; Spectre::Transcoder::get_ascii_item(std::string const &,Spectre::Transcoder::PLYDataType,__int64 *,unsigned __int64 *,float *)
0x18036917c  lea     rdx, [rbp+1F0h+var_88]
0x180369183  lea     rcx, [rbp+1F0h+Block]
0x180369187  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18036918c  movss   xmm0, dword ptr [rsp+2F0h+var_288]
0x180369192  movss   dword ptr [rsp+2F0h+var_2C8], xmm0
0x180369198  mov     rcx, [rbp+1F0h+var_270]
0x18036919c  mov     [rsp+2F0h+var_2D0], rcx
0x1803691a1  mov     r9, [rbp+1F0h+var_268]
0x1803691a5  mov     r8, rbx
0x1803691a8  mov     rdx, rax
0x1803691ab  mov     rcx, [rsp+2F0h+var_280]
0x1803691b0  call    ??R?$_Func_class@XV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_J_KM@std@@QEBAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K_J1M@Z; std::_Func_class<void,std::string,unsigned __int64,__int64,unsigned __int64,float>::operator()(std::string,unsigned __int64,__int64,unsigned __int64,float)
0x1803691b5  inc     r15d
0x1803691b8  inc     rdi
0x1803691bb  add     r12, 20h ; ' '
0x1803691bf  mov     rax, [rsi+8]
0x1803691c3  sub     rax, [rsi]
0x1803691c6  sar     rax, 5
0x1803691ca  cmp     rdi, rax
0x1803691cd  jnb     short loc_1803691DB
0x1803691cf  mov     r14d, [rbp+1F0h+var_64]
0x1803691d6  jmp     loc_180369154
0x1803691db  xor     r12d, r12d
0x1803691de  mov     r13, [rsp+2F0h+var_290]
0x1803691e3  mov     r15, [rsp+2F0h+Size]
0x1803691e8  mov     rbx, [rsp+2F0h+var_2A8]
0x1803691ed  mov     rdx, [rbp+1F0h+var_70]
0x1803691f4  cmp     rdx, 10h
0x1803691f8  jb      short loc_18036922E
0x1803691fa  inc     rdx
0x1803691fd  mov     rcx, [rbp+1F0h+var_88]
0x180369204  mov     rax, rcx
0x180369207  cmp     rdx, 1000h
0x18036920e  jb      short loc_180369229
0x180369210  add     rdx, 27h ; '''
0x180369214  mov     rcx, [rcx-8]; Block
0x180369218  sub     rax, rcx
0x18036921b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18036921f  cmp     rax, 1Fh
0x180369223  ja      loc_180369982
0x180369229  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18036922e  inc     r13
0x180369231  mov     [rsp+2F0h+var_290], r13
0x180369236  add     r15, 38h ; '8'
0x18036923a  mov     [rsp+2F0h+Size], r15
0x18036923f  mov     rax, [rsi+8]
0x180369243  sub     rax, [rsi]
0x180369246  sar     rax, 5
0x18036924a  cmp     rdi, rax
0x18036924d  mov     r14, [rbp+1F0h+var_260]
0x180369251  mov     rax, 4924924924924925h
0x18036925b  jb      loc_180369010
0x180369261  jmp     loc_18036998E
0x180369266  cmp     ecx, 2
0x180369269  jnz     loc_1803691E8
0x18036926f  mov     rbx, [rsp+2F0h+var_2A8]
0x180369274  cmp     qword ptr [rbx+38h], 0
0x180369279  jz      loc_1803691ED
0x18036927f  lea     rax, [rbp+1F0h+Block]
0x180369283  mov     [rbp+1F0h+var_110], rax
0x18036928a  mov     rdx, rdi
0x18036928d  shl     rdx, 5
0x180369291  add     rdx, [rsi]
0x180369294  lea     rcx, [rbp+1F0h+Block]
0x180369298  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18036929d  mov     rbx, rax
0x1803692a0  lea     rdx, [rbp+1F0h+var_88]
0x1803692a7  lea     rcx, [rbp+1F0h+var_188]
0x1803692ab  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1803692b0  nop
0x1803692b1  mov     r8, rbx
0x1803692b4  mov     rdx, rax
0x1803692b7  mov     rbx, [rsp+2F0h+var_2A8]
0x1803692bc  mov     rcx, rbx
0x1803692bf  call    ??R?$_Func_class@XV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEBAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@0@Z; std::_Func_class<void,std::string,std::string>::operator()(std::string,std::string)
0x1803692c4  inc     rdi
0x1803692c7  jmp     loc_1803691ED
0x1803692cc  cmp     eax, 1
0x1803692cf  setz    r14b
0x1803692d3  mov     [rsp+2F0h+var_2B0], r14b
0x1803692d8  mov     rcx, [rdi]
0x1803692db  mov     rcx, [rcx]
0x1803692de  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x1803692e4  mov     r15, [rax+8]
0x1803692e8  add     r15, [rax]
0x1803692eb  mov     rax, [rdi]
0x1803692ee  mov     r13, [rax+10h]
0x1803692f2  xor     r12d, r12d
0x1803692f5  mov     [rbp+1F0h+var_248], r12
0x1803692f9  mov     rax, [rbp+1F0h+var_260]
0x1803692fd  mov     rcx, [rax+30h]
0x180369301  sub     rcx, [rax+28h]
0x180369305  mov     rax, 4924924924924925h
0x18036930f  imul    rcx
0x180369312  sar     rdx, 4
0x180369316  mov     rax, rdx
0x180369319  shr     rax, 3Fh
0x18036931d  add     rdx, rax
0x180369320  jz      loc_180369993
0x180369326  mov     [rbp+1F0h+var_258], r12
0x18036932a  nop     word ptr [rax+rax+00h]
0x180369330  cmp     r15, r13
0x180369333  jz      loc_180369993
0x180369339  mov     rcx, [rdi]
0x18036933c  lea     rdx, [rbp+1F0h+var_128]
0x180369343  mov     rcx, [rcx]
0x180369346  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18036934c  mov     r15, [rax+8]
0x180369350  add     r15, [rax]
  ... truncated ...
```

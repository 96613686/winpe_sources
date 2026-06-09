# Mso::RegistryWrapper::ReadFromOrapi(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,type_info const &)

- ea: `0x180068244`
- end: `0x180068b6b`
- name: `?ReadFromOrapi@RegistryWrapper@Mso@@AEAA?AU?$pair@_NVAnyType@Mso@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEBVtype_info@@@Z`
- size: `2343`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068b70`
- `0x180068cd0`

## callees

- `0x180012aa0`
- `0x180013080`
- `0x180017c80`
- `0x180018bc0`
- `0x180037a58`
- `0x180048730`
- `0x180068244`
- `0x18006d960`
- `0x18009bca8`
- `0x18009c4a8`
- `0x18009cd2c`
- `0x1800a14a4`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1800683fe`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800685f0`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800683fe`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800685f0`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068419`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068460`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18006860e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068654`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068419`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068460`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18006860e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180068654`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068788`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068a87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068b08`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068788`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800687e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068a87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180068b08`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180068a80`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180068b01`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180068a80`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180068b01`

## string_xrefs

- `0x1800689f7`: `RegistryWrapper::ReadFromOrapi > Registry read failed, perhaps key not present yet.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall Mso::RegistryWrapper::ReadFromOrapi(void **a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  _QWORD *v5; // rdi
  char *v6; // r13
  __int64 v8; // r12
  _QWORD *v9; // rcx
  __int64 v10; // r9
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8
  int v13; // ecx
  int v14; // ecx
  char v15; // si
  int v16; // ecx
  __int64 v17; // r9
  const struct _orkey *v18; // rdx
  int v19; // eax
  __int64 v20; // rsi
  _QWORD *v21; // rcx
  char *v22; // r14
  char v23; // si
  _QWORD *v24; // r8
  __int64 *v25; // r15
  __int64 v26; // rax
  bool v27; // zf
  __int64 v28; // r9
  int v29; // r14d
  char *v30; // r14
  int v31; // esi
  __int64 *v32; // r15
  __int64 v33; // rax
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  _QWORD *v38; // r8
  __int64 v39; // r9
  int v40; // edx
  int v41; // r9d
  char *v42; // rsi
  int v43; // r9d
  __int64 *v44; // rdi
  __int64 v45; // rax
  __m128i si128; // xmm1
  void **v47; // rax
  void *v48; // rcx
  void *v49; // rcx
  _QWORD *v51; // rax
  void **v52; // rax
  void *v53; // rcx
  __int64 v54; // [rsp+0h] [rbp-1F8h] BYREF
  uintptr_t Reserved; // [rsp+20h] [rbp-1D8h]
  _QWORD *v56; // [rsp+40h] [rbp-1B8h] BYREF
  _QWORD v57[2]; // [rsp+48h] [rbp-1B0h] BYREF
  int v58; // [rsp+58h] [rbp-1A0h]
  const char *v59; // [rsp+60h] [rbp-198h] BYREF
  _QWORD *v60; // [rsp+68h] [rbp-190h] BYREF
  __int16 v61; // [rsp+70h] [rbp-188h]
  _QWORD *v62; // [rsp+78h] [rbp-180h] BYREF
  __int16 v63; // [rsp+80h] [rbp-178h]
  _QWORD *v64; // [rsp+88h] [rbp-170h] BYREF
  __int16 v65; // [rsp+90h] [rbp-168h]
  _QWORD *v66; // [rsp+98h] [rbp-160h] BYREF
  __int16 v67; // [rsp+A0h] [rbp-158h]
  __int128 v68; // [rsp+B0h] [rbp-148h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-138h]
  _OWORD v70[2]; // [rsp+C8h] [rbp-130h] BYREF
  char v71; // [rsp+E8h] [rbp-110h]
  void *Block[2]; // [rsp+F0h] [rbp-108h] BYREF
  _BYTE v73[24]; // [rsp+100h] [rbp-F8h] BYREF
  __int128 v74; // [rsp+118h] [rbp-E0h]
  struct _orkey *v75; // [rsp+128h] [rbp-D0h]
  void **v76; // [rsp+130h] [rbp-C8h] BYREF
  const char *v77; // [rsp+138h] [rbp-C0h]
  void **v78; // [rsp+140h] [rbp-B8h]
  __int16 v79; // [rsp+148h] [rbp-B0h]
  void *v80[2]; // [rsp+150h] [rbp-A8h]
  __m128i v81; // [rsp+160h] [rbp-98h]
  void **v82; // [rsp+170h] [rbp-88h] BYREF
  const char *v83; // [rsp+178h] [rbp-80h]
  _QWORD *v84; // [rsp+180h] [rbp-78h]
  __int16 v85; // [rsp+188h] [rbp-70h]
  __int128 v86; // [rsp+190h] [rbp-68h] BYREF
  __m128i v87; // [rsp+1A0h] [rbp-58h]

  v5 = a3;
  v6 = (char *)a2;
  v59 = (const char *)a2;
  v56 = a3;
  *(_OWORD *)(a2 + 8) = 0;
  v58 = 1;
  *(_BYTE *)a2 = 0;
  v8 = (*((__int64 (__fastcall **)(void **))*a1 + 6))(a1);
  v57[0] = v8;
  v9 = v5;
  if ( v5[3] > 7u )
    v9 = (_QWORD *)*v5;
  v10 = 0xCBF29CE484222325uLL;
  v11 = 0;
  v12 = 2LL * v5[2];
  if ( v12 )
  {
    do
      v10 = 0x100000001B3LL * (*((unsigned __int8 *)v9 + v11++) ^ (unsigned __int64)v10);
    while ( v11 < v12 );
  }
  if ( *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                     a1 + 23,
                     Block,
                     v5,
                     v10)
                 + 8) )
    v13 = *(_DWORD *)std::unordered_map<std::wstring,unsigned long>::operator[](a1 + 23, v5);
  else
    v13 = 1;
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = 3;
    v16 = v14 - 3;
    if ( v16 )
    {
      if ( v16 != 7 )
        CrashWithRecovery(0x235DF191u, 0);
      if ( v5[3] > 7u )
        v5 = (_QWORD *)*v5;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)v5 + v17) );
      *(_OWORD *)Block = 0;
      memset(v73, 0, sizeof(v73));
      LOBYTE(v75) = 0;
      v74 = (unsigned __int64)Block;
      LODWORD(Reserved) = 11;
      DynamicMsorid::InitForValue(Block, v8);
      v57[0] = 0;
      LOBYTE(v18) = (_BYTE)v75;
      if ( ((unsigned __int64)&v73[8] & -(__int64)((_BYTE)v75 != 0)) == 0 )
        goto LABEL_68;
      LODWORD(v56) = 8;
      if ( !(unsigned int)sub_18009BCA8((unsigned __int64)&v73[8] & -(__int64)((_BYTE)v75 != 0), v57, &v56) )
      {
        v19 = __std_type_info_compare(a4 + 8, &qword_1806A3C70);
        v20 = v57[0];
        if ( v19 )
        {
          v65 = 0;
          v24 = malloc(0x10u);
          if ( v24 )
          {
            *v24 = &Mso::AnyType::Any<__int64>::`vftable';
            v24[1] = v20;
            v64 = v24;
          }
          else
          {
            v24 = 0;
            v64 = 0;
          }
          v22 = (char *)&v64;
          v23 = 17;
          v21 = v60;
        }
        else
        {
          v61 = 0;
          v21 = malloc(0x10u);
          if ( v21 )
          {
            *v21 = &Mso::AnyType::Any<unsigned __int64>::`vftable';
            v21[1] = v20;
            v60 = v21;
          }
          else
          {
            v21 = 0;
            v60 = 0;
          }
          v22 = (char *)&v60;
          v23 = 9;
          v24 = v64;
        }
        v25 = (__int64 *)(v6 + 8);
        if ( v6 + 8 != v22 )
        {
          if ( *v25 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)*v25 + 40LL))(*v25, 1, v24);
          *((_WORD *)v6 + 8) = *((_WORD *)v22 + 4);
          if ( *(_QWORD *)v22 )
            v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)v22 + 16LL))(
                    *(_QWORD *)v22,
                    0,
                    v24);
          else
            v26 = 0;
          *v25 = v26;
          *(_QWORD *)v22 = 0;
          v21 = v60;
          v24 = v64;
        }
        if ( (v23 & 0x10) != 0 )
        {
          v23 &= ~0x10u;
          if ( v24 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))(*v24 + 40LL))(v24, 1);
            v21 = v60;
          }
        }
        v27 = (v23 & 8) == 0;
LABEL_63:
        if ( !v27 && v21 )
          (*(void (__fastcall **)(_QWORD *, __int64, _QWORD *))(*v21 + 40LL))(v21, 1, v24);
        *v6 = 1;
        LOBYTE(v18) = (_BYTE)v75;
        goto LABEL_68;
      }
    }
    else
    {
      if ( v5[3] > 7u )
        v5 = (_QWORD *)*v5;
      v28 = -1;
      do
        ++v28;
      while ( *((_WORD *)v5 + v28) );
      *(_OWORD *)Block = 0;
      memset(v73, 0, sizeof(v73));
      LOBYTE(v75) = 0;
      v74 = (unsigned __int64)Block;
      LODWORD(Reserved) = 4;
      DynamicMsorid::InitForValue(Block, v57[0]);
      LODWORD(v56) = 0;
      LOBYTE(v18) = (_BYTE)v75;
      if ( ((unsigned __int64)&v73[8] & -(__int64)((_BYTE)v75 != 0)) == 0 )
        goto LABEL_68;
      LODWORD(v57[0]) = 4;
      if ( !(unsigned int)sub_18009BCA8((unsigned __int64)&v73[8] & -(__int64)((_BYTE)v75 != 0), &v56, v57) )
      {
        if ( (unsigned int)__std_type_info_compare(a4 + 8, &qword_1806A3C58) )
        {
          v31 = (int)v56;
          v67 = 0;
          v24 = malloc(0x10u);
          if ( v24 )
          {
            *v24 = &Mso::AnyType::Any<int>::`vftable';
            *((_DWORD *)v24 + 2) = v31;
            v66 = v24;
          }
          else
          {
            v24 = 0;
            v66 = 0;
          }
          v30 = (char *)&v66;
          v15 = 5;
          v21 = v62;
        }
        else
        {
          v29 = (int)v56;
          v63 = 0;
          v21 = malloc(0x10u);
          if ( v21 )
          {
            *v21 = &Mso::AnyType::Any<unsigned int>::`vftable';
            *((_DWORD *)v21 + 2) = v29;
            v62 = v21;
          }
          else
          {
            v21 = 0;
            v62 = 0;
          }
          v30 = (char *)&v62;
          v24 = v66;
        }
        v32 = (__int64 *)(v6 + 8);
        if ( v6 + 8 != v30 )
        {
          if ( *v32 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)*v32 + 40LL))(*v32, 1, v24);
          *((_WORD *)v6 + 8) = *((_WORD *)v30 + 4);
          if ( *(_QWORD *)v30 )
            v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)v30 + 16LL))(
                    *(_QWORD *)v30,
                    0,
                    v24);
          else
            v33 = 0;
          *v32 = v33;
          *(_QWORD *)v30 = 0;
          v21 = v62;
          v24 = v66;
        }
        if ( (v15 & 4) != 0 )
        {
          v15 &= ~4u;
          if ( v24 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))(*v24 + 40LL))(v24, 1);
            v21 = v62;
          }
        }
        v27 = (v15 & 2) == 0;
        goto LABEL_63;
      }
    }
    LOBYTE(v18) = (_BYTE)v75;
LABEL_68:
    if ( (_BYTE)v18 )
    {
      if ( byte_1806BA6E8 )
        Mso::Orapi::KeyCache::RemoveKey((Mso::Orapi::KeyCache *)v74, v18);
      v34 = Block[0];
      v27 = Block[0] == 0;
      Block[0] = 0;
      if ( !v27 )
        free(v34);
      v35 = *(void **)&v73[8];
      v27 = *(_QWORD *)&v73[8] == 0;
      *(_QWORD *)&v73[8] = 0;
      if ( !v27 )
        free(v35);
      LOBYTE(v75) = 0;
    }
    v36 = *(void **)&v73[8];
    v27 = *(_QWORD *)&v73[8] == 0;
    *(_QWORD *)&v73[8] = 0;
    if ( !v27 )
      free(v36);
    v37 = Block[0];
    Block[0] = 0;
    if ( v37 )
      free(v37);
    return v6;
  }
  v38 = v5;
  if ( v5[3] > 7u )
    v38 = (_QWORD *)*v5;
  v39 = -1;
  do
    ++v39;
  while ( *((_WORD *)v38 + v39) );
  v68 = 0;
  v69 = 0;
  v70[0] = 0;
  v71 = 0;
  v70[1] = (unsigned __int64)&v68;
  LODWORD(Reserved) = 1;
  DynamicMsorid::InitForValue(&v68, v8);
  *(_OWORD *)Block = 0;
  *(__m128i *)v73 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  if ( (unsigned __int8)Mso::Orapi::Read((struct _msoreg *)((unsigned __int64)v70 & -(__int64)(v71 != 0)), Block) )
  {
    try
    {
      v42 = (char *)Mso::Deserialize(v57, Block);
      v44 = (__int64 *)(v6 + 8);
      if ( v6 + 8 != v42 )
      {
        if ( *v44 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v44 + 40LL))(*v44, 1);
        *((_WORD *)v6 + 8) = *((_WORD *)v42 + 4);
        if ( *(_QWORD *)v42 )
          v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v42 + 16LL))(*(_QWORD *)v42, 0);
        else
          v45 = 0;
        *v44 = v45;
        *(_QWORD *)v42 = 0;
      }
      if ( v57[0] )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v57[0] + 40LL))(v57[0], 1);
      *v6 = 1;
    }
    catch ( std::invalid_argument )
    {
      v51 = v56;
      if ( v56[3] > 7u )
        v51 = (_QWORD *)*v56;
      v82 = &Mso::Http::Logging::Structured::Status::`vftable';
      v83 = "Key";
      v84 = v51;
      v85 = 4;
      v86 = 0;
      v87.m128i_i64[0] = 0;
      v87.m128i_i64[1] = 7;
      LOWORD(v86) = 0;
      v52 = Block;
      if ( *(_QWORD *)&v73[8] > 7u )
        v52 = (void **)Block[0];
      v76 = &Mso::Http::Logging::Structured::Status::`vftable';
      v77 = "value";
      v78 = v52;
      v79 = 4;
      *(_OWORD *)v80 = 0;
      v81.m128i_i64[0] = 0;
      v81.m128i_i64[1] = 7;
      LOWORD(v80[0]) = 0;
      v57[0] = "RegistryWrapper::ReadFromOrapi > Deserialzed failed. Perhaps no callback for type.";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        593359251,
        (unsigned int)&v54,
        50,
        v43,
        (__int64)v57,
        (__int64)&v76,
        (__int64)&v82);
      if ( v81.m128i_i64[1] > 7uLL )
      {
        v53 = v80[0];
        if ( (unsigned __int64)(2 * v81.m128i_i64[1] + 2) >= 0x1000 )
        {
          if ( (unsigned __int64)v80[0] - *((_QWORD *)v80[0] - 1) - 8 > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
          v53 = (void *)*((_QWORD *)v80[0] - 1);
        }
        free(v53);
      }
      v80[0] = (void *)19937;
      v81.m128i_i64[0] = 0;
      v81.m128i_i64[1] = 15;
      std::wstring::~wstring(&v86);
      v6 = (char *)v59;
    }
  }
  else
  {
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    v82 = &Mso::Http::Logging::Structured::Status::`vftable';
    v83 = "Key";
    v84 = v5;
    v85 = 4;
    v86 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v87 = si128;
    LOWORD(v86) = 0;
    v47 = a1 + 1;
    if ( (unsigned __int64)a1[4] > 7 )
      v47 = (void **)*v47;
    v76 = &Mso::Http::Logging::Structured::Status::`vftable';
    v77 = "Path";
    v78 = v47;
    v79 = 4;
    *(_OWORD *)v80 = 0;
    v81 = si128;
    LOWORD(v80[0]) = 0;
    v59 = "RegistryWrapper::ReadFromOrapi > Registry read failed, perhaps key not present yet.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      593359250,
      v40,
      50,
      v41,
      (__int64)&v59,
      (__int64)&v76,
      (__int64)&v82);
    if ( v81.m128i_i64[1] > 7uLL )
    {
      v48 = v80[0];
      if ( (unsigned __int64)(2 * v81.m128i_i64[1] + 2) >= 0x1000 )
      {
        v48 = (void *)*((_QWORD *)v80[0] - 1);
        if ( (unsigned __int64)((char *)v80[0] - (char *)v48 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v48);
    }
    v80[0] = (void *)19937;
    v81 = _mm_load_si128((const __m128i *)&_xmm);
    std::wstring::~wstring(&v86);
  }
  if ( *(_QWORD *)&v73[8] > 7u )
  {
    v49 = Block[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&v73[8] + 2) >= 0x1000 )
    {
      v49 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v49 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v49);
  }
  Block[0] = (void *)19937;
  *(__m128i *)v73 = _mm_load_si128((const __m128i *)&_xmm);
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v68);
  return v6;
}

```

## disassembly

```asm
0x180068244  push    rbx
0x180068246  push    rsi
0x180068247  push    rdi
0x180068248  push    r12
0x18006824a  push    r13
0x18006824c  push    r14
0x18006824e  push    r15
0x180068250  sub     rsp, 1C0h
0x180068257  mov     rax, cs:__security_cookie
0x18006825e  xor     rax, rsp
0x180068261  mov     [rsp+1F8h+var_48], rax
0x180068269  mov     r14, r9
0x18006826c  mov     rdi, r8
0x18006826f  mov     r13, rdx
0x180068272  mov     r15, rcx
0x180068275  mov     [rsp+1F8h+var_198], rdx
0x18006827a  mov     [rsp+1F8h+var_1B8], r8
0x18006827f  xor     ebx, ebx
0x180068281  mov     [rsp+1F8h+var_1A0], ebx
0x180068285  xorps   xmm0, xmm0
0x180068288  movups  xmmword ptr [rdx+8], xmm0
0x18006828c  mov     [rsp+1F8h+var_1A0], 1
0x180068294  mov     [rdx], bl
0x180068296  mov     rax, [rcx]
0x180068299  mov     rax, [rax+30h]
0x18006829d  call    cs:__guard_dispatch_icall_fptr
0x1800682a3  mov     r12, rax
0x1800682a6  mov     [rsp+1F8h+var_1B0], rax
0x1800682ab  lea     rsi, [r15+0B8h]
0x1800682b2  mov     r8, [rdi+10h]
0x1800682b6  mov     rcx, rdi
0x1800682b9  cmp     qword ptr [rdi+18h], 7
0x1800682be  jbe     short loc_1800682C3
0x1800682c0  mov     rcx, [rdi]
0x1800682c3  mov     r9, 0CBF29CE484222325h
0x1800682cd  mov     rdx, rbx
0x1800682d0  add     r8, r8
0x1800682d3  jz      short loc_1800682F2
0x1800682d5  movzx   eax, byte ptr [rdx+rcx]
0x1800682d9  xor     r9, rax
0x1800682dc  mov     r10, 100000001B3h
0x1800682e6  imul    r9, r10
0x1800682ea  inc     rdx
0x1800682ed  cmp     rdx, r8
0x1800682f0  jb      short loc_1800682D5
0x1800682f2  mov     r8, rdi
0x1800682f5  lea     rdx, [rsp+1F8h+Block]
0x1800682fd  mov     rcx, rsi
0x180068300  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180068305  cmp     [rax+8], rbx
0x180068309  jz      short loc_18006831A
0x18006830b  mov     rdx, rdi
0x18006830e  mov     rcx, rsi
0x180068311  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@std@@QEAAAEAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,ulong>::operator[](std::wstring const &)
0x180068316  mov     ecx, [rax]
0x180068318  jmp     short loc_18006831F
0x18006831a  mov     ecx, 1
0x18006831f  sub     ecx, 1
0x180068322  jz      loc_1800687EF
0x180068328  mov     esi, 3
0x18006832d  sub     ecx, esi
0x18006832f  jz      loc_18006852F
0x180068335  cmp     ecx, 7
0x180068338  jnz     loc_180068B5E
0x18006833e  cmp     qword ptr [rdi+18h], 7
0x180068343  jbe     short loc_180068348
0x180068345  mov     rdi, [rdi]
0x180068348  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006834c  inc     r9
0x18006834f  cmp     [rdi+r9*2], bx
0x180068354  jnz     short loc_18006834C
0x180068356  xorps   xmm0, xmm0
0x180068359  xor     eax, eax
0x18006835b  movups  xmmword ptr [rsp+1F8h+Block], xmm0
0x180068363  mov     qword ptr [rsp+1F8h+var_F8], rax
0x18006836b  xorps   xmm1, xmm1
0x18006836e  movups  xmmword ptr [rsp+1F8h+var_F8+8], xmm1
0x180068376  movups  [rsp+1F8h+var_E0], xmm1
0x18006837e  mov     byte ptr [rsp+1F8h+var_D0], bl
0x180068385  lea     rax, [rsp+1F8h+Block]
0x18006838d  mov     qword ptr [rsp+1F8h+var_E0], rax
0x180068395  mov     dword ptr [rsp+1F8h+Reserved], 0Bh
0x18006839d  mov     r8, rdi
0x1800683a0  mov     rdx, r12
0x1800683a3  lea     rcx, [rsp+1F8h+Block]
0x1800683ab  call    ?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1800683b0  mov     [rsp+1F8h+var_1B0], rbx
0x1800683b5  mov     dl, byte ptr [rsp+1F8h+var_D0]
0x1800683bc  mov     al, dl
0x1800683be  neg     al
0x1800683c0  sbb     rcx, rcx
0x1800683c3  lea     rax, [rsp+1F8h+var_F8+8]
0x1800683cb  and     rcx, rax
0x1800683ce  jz      loc_18006874C
0x1800683d4  mov     dword ptr [rsp+1F8h+var_1B8], 8
0x1800683dc  lea     r8, [rsp+1F8h+var_1B8]
0x1800683e1  lea     rdx, [rsp+1F8h+var_1B0]
0x1800683e6  call    sub_18009BCA8
0x1800683eb  test    eax, eax
0x1800683ed  jnz     loc_180068745
0x1800683f3  lea     rcx, [r14+8]
0x1800683f7  lea     rdx, qword_1806A3C70
0x1800683fe  call    cs:__imp___std_type_info_compare
0x180068404  mov     rsi, [rsp+1F8h+var_1B0]
0x180068409  mov     edi, 10h
0x18006840e  mov     ecx, edi; Size
0x180068410  test    eax, eax
0x180068412  jnz     short loc_180068458
0x180068414  mov     [rsp+1F8h+var_188], bx
0x180068419  call    cs:__imp_malloc
0x18006841f  mov     rcx, rax
0x180068422  test    rax, rax
0x180068425  jz      short loc_18006843C
0x180068427  lea     rax, ??_7?$Any@_K@AnyType@Mso@@6B@; const Mso::AnyType::Any<unsigned __int64>::`vftable'
0x18006842e  mov     [rcx], rax
0x180068431  mov     [rcx+8], rsi
0x180068435  mov     [rsp+1F8h+var_190], rcx
0x18006843a  jmp     short loc_180068444
0x18006843c  mov     rcx, rbx
0x18006843f  mov     [rsp+1F8h+var_190], rbx
0x180068444  lea     r14, [rsp+1F8h+var_190]
0x180068449  mov     esi, 9
0x18006844e  mov     r8, [rsp+1F8h+var_170]
0x180068456  jmp     short loc_1800684A3
0x180068458  mov     [rsp+1F8h+var_168], bx
0x180068460  call    cs:__imp_malloc
0x180068466  mov     r8, rax
0x180068469  test    rax, rax
0x18006846c  jz      short loc_180068486
0x18006846e  lea     rax, ??_7?$Any@_J@AnyType@Mso@@6B@; const Mso::AnyType::Any<__int64>::`vftable'
0x180068475  mov     [r8], rax
0x180068478  mov     [r8+8], rsi
0x18006847c  mov     [rsp+1F8h+var_170], r8
0x180068484  jmp     short loc_180068491
0x180068486  mov     r8, rbx
0x180068489  mov     [rsp+1F8h+var_170], rbx
0x180068491  lea     r14, [rsp+1F8h+var_170]
0x180068499  mov     esi, 11h
0x18006849e  mov     rcx, [rsp+1F8h+var_190]
0x1800684a3  lea     r15, [r13+8]
0x1800684a7  cmp     r15, r14
0x1800684aa  jz      short loc_1800684FF
0x1800684ac  mov     rcx, [r15]
0x1800684af  test    rcx, rcx
0x1800684b2  jz      short loc_1800684C6
0x1800684b4  mov     rax, [rcx]
0x1800684b7  mov     edx, 1
0x1800684bc  mov     rax, [rax+28h]
0x1800684c0  call    cs:__guard_dispatch_icall_fptr
0x1800684c6  movzx   eax, word ptr [r14+8]
0x1800684cb  mov     [r15+8], ax
0x1800684d0  mov     rcx, [r14]
0x1800684d3  test    rcx, rcx
0x1800684d6  jz      short loc_1800684E9
0x1800684d8  mov     rax, [rcx]
0x1800684db  xor     edx, edx
0x1800684dd  mov     rax, [rax+10h]
0x1800684e1  call    cs:__guard_dispatch_icall_fptr
0x1800684e7  jmp     short loc_1800684EC
0x1800684e9  mov     rax, rbx
0x1800684ec  mov     [r15], rax
0x1800684ef  mov     [r14], rbx
0x1800684f2  mov     rcx, [rsp+1F8h+var_190]
0x1800684f7  mov     r8, [rsp+1F8h+var_170]
0x1800684ff  test    dil, sil
0x180068502  jz      short loc_180068526
0x180068504  and     esi, 0FFFFFFEFh
0x180068507  test    r8, r8
0x18006850a  jz      short loc_180068526
0x18006850c  mov     rax, [r8]
0x18006850f  mov     edx, 1
0x180068514  mov     rcx, r8
0x180068517  mov     rax, [rax+28h]
0x18006851b  call    cs:__guard_dispatch_icall_fptr
0x180068521  mov     rcx, [rsp+1F8h+var_190]
0x180068526  test    sil, 8
0x18006852a  jmp     loc_18006871E
0x18006852f  cmp     qword ptr [rdi+18h], 7
0x180068534  jbe     short loc_180068539
0x180068536  mov     rdi, [rdi]
0x180068539  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006853d  inc     r9
0x180068540  cmp     [rdi+r9*2], bx
0x180068545  jnz     short loc_18006853D
0x180068547  xorps   xmm0, xmm0
0x18006854a  xor     eax, eax
0x18006854c  movups  xmmword ptr [rsp+1F8h+Block], xmm0
0x180068554  mov     qword ptr [rsp+1F8h+var_F8], rax
0x18006855c  xorps   xmm1, xmm1
0x18006855f  movups  xmmword ptr [rsp+1F8h+var_F8+8], xmm1
0x180068567  movups  [rsp+1F8h+var_E0], xmm1
0x18006856f  mov     byte ptr [rsp+1F8h+var_D0], bl
0x180068576  lea     rax, [rsp+1F8h+Block]
0x18006857e  mov     qword ptr [rsp+1F8h+var_E0], rax
0x180068586  mov     r12d, 4
0x18006858c  mov     dword ptr [rsp+1F8h+Reserved], r12d
0x180068591  mov     r8, rdi
0x180068594  mov     rdx, [rsp+1F8h+var_1B0]
0x180068599  lea     rcx, [rsp+1F8h+Block]
0x1800685a1  call    ?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1800685a6  mov     dword ptr [rsp+1F8h+var_1B8], ebx
0x1800685aa  mov     dl, byte ptr [rsp+1F8h+var_D0]
0x1800685b1  mov     al, dl
0x1800685b3  neg     al
0x1800685b5  sbb     rcx, rcx
0x1800685b8  lea     rax, [rsp+1F8h+var_F8+8]
0x1800685c0  and     rcx, rax
0x1800685c3  jz      loc_18006874C
0x1800685c9  mov     dword ptr [rsp+1F8h+var_1B0], r12d
0x1800685ce  lea     r8, [rsp+1F8h+var_1B0]
0x1800685d3  lea     rdx, [rsp+1F8h+var_1B8]
0x1800685d8  call    sub_18009BCA8
0x1800685dd  test    eax, eax
0x1800685df  jnz     loc_180068745
0x1800685e5  lea     rcx, [r14+8]
0x1800685e9  lea     rdx, qword_1806A3C58
0x1800685f0  call    cs:__imp___std_type_info_compare
0x1800685f6  lea     edi, [r12+0Ch]
0x1800685fb  mov     ecx, edi; Size
0x1800685fd  test    eax, eax
0x1800685ff  jnz     short loc_180068648
0x180068601  mov     r14d, dword ptr [rsp+1F8h+var_1B8]
0x180068606  mov     [rsp+1F8h+var_178], bx
0x18006860e  call    cs:__imp_malloc
0x180068614  mov     rcx, rax
0x180068617  test    rax, rax
0x18006861a  jz      short loc_180068631
0x18006861c  lea     rax, ??_7?$Any@I@AnyType@Mso@@6B@; const Mso::AnyType::Any<uint>::`vftable'
0x180068623  mov     [rcx], rax
0x180068626  mov     [rcx+8], r14d
0x18006862a  mov     [rsp+1F8h+var_180], rcx
0x18006862f  jmp     short loc_180068639
0x180068631  mov     rcx, rbx
0x180068634  mov     [rsp+1F8h+var_180], rbx
0x180068639  lea     r14, [rsp+1F8h+var_180]
0x18006863e  mov     r8, [rsp+1F8h+var_160]
0x180068646  jmp     short loc_180068697
0x180068648  mov     esi, dword ptr [rsp+1F8h+var_1B8]
0x18006864c  mov     [rsp+1F8h+var_158], bx
0x180068654  call    cs:__imp_malloc
0x18006865a  mov     r8, rax
0x18006865d  test    rax, rax
0x180068660  jz      short loc_18006867A
0x180068662  lea     rax, ??_7?$Any@H@AnyType@Mso@@6B@; const Mso::AnyType::Any<int>::`vftable'
0x180068669  mov     [r8], rax
0x18006866c  mov     [r8+8], esi
0x180068670  mov     [rsp+1F8h+var_160], r8
0x180068678  jmp     short loc_180068685
0x18006867a  mov     r8, rbx
0x18006867d  mov     [rsp+1F8h+var_160], rbx
0x180068685  lea     r14, [rsp+1F8h+var_160]
0x18006868d  mov     esi, 5
0x180068692  mov     rcx, [rsp+1F8h+var_180]
0x180068697  lea     r15, [r13+8]
0x18006869b  cmp     r15, r14
0x18006869e  jz      short loc_1800686F3
0x1800686a0  mov     rcx, [r15]
0x1800686a3  test    rcx, rcx
0x1800686a6  jz      short loc_1800686BA
0x1800686a8  mov     rax, [rcx]
0x1800686ab  mov     edx, 1
0x1800686b0  mov     rax, [rax+28h]
0x1800686b4  call    cs:__guard_dispatch_icall_fptr
0x1800686ba  movzx   eax, word ptr [r14+8]
0x1800686bf  mov     [r15+8], ax
0x1800686c4  mov     rcx, [r14]
0x1800686c7  test    rcx, rcx
0x1800686ca  jz      short loc_1800686DD
0x1800686cc  mov     rax, [rcx]
0x1800686cf  xor     edx, edx
0x1800686d1  mov     rax, [rax+10h]
0x1800686d5  call    cs:__guard_dispatch_icall_fptr
0x1800686db  jmp     short loc_1800686E0
0x1800686dd  mov     rax, rbx
0x1800686e0  mov     [r15], rax
0x1800686e3  mov     [r14], rbx
0x1800686e6  mov     rcx, [rsp+1F8h+var_180]
0x1800686eb  mov     r8, [rsp+1F8h+var_160]
0x1800686f3  test    r12b, sil
0x1800686f6  jz      short loc_18006871A
0x1800686f8  and     esi, 0FFFFFFFBh
0x1800686fb  test    r8, r8
0x1800686fe  jz      short loc_18006871A
0x180068700  mov     rax, [r8]
0x180068703  mov     edx, 1
0x180068708  mov     rcx, r8
0x18006870b  mov     rax, [rax+28h]
0x18006870f  call    cs:__guard_dispatch_icall_fptr
0x180068715  mov     rcx, [rsp+1F8h+var_180]
0x18006871a  test    sil, 2
0x18006871e  jz      short loc_180068737
0x180068720  test    rcx, rcx
0x180068723  jz      short loc_180068737
0x180068725  mov     rax, [rcx]
0x180068728  mov     edx, 1
0x18006872d  mov     rax, [rax+28h]
0x180068731  call    cs:__guard_dispatch_icall_fptr
0x180068737  mov     byte ptr [r13+0], 1
0x18006873c  mov     dl, byte ptr [rsp+1F8h+var_D0]
0x180068743  jmp     short loc_180068751
  ... truncated ...
```

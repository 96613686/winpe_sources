# win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____

- ea: `0x1800119a4`
- end: `0x180012526`
- name: `win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____`
- size: `2946`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180022648`

## callees

- `0x1800016b0`
- `0x180006024`
- `0x180010f4c`
- `0x1800113a4`
- `0x1800114d8`
- `0x1800116a0`
- `0x1800119a4`
- `0x18001252c`
- `0x18001278c`
- `0x180012fa0`
- `0x180015114`
- `0x180015a68`
- `0x1800208b0`
- `0x1800229fc`
- `0x18002587c`
- `0x18004f4c4`
- `0x1800517a0`
- `0x18009987c`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800d5fe4`
- `0x180117716`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011c42`
- `msvcrt!memcpy_s` at `0x180011dbb`
- `msvcrt!memcpy_s` at `0x18001207c`
- `msvcrt!memcpy_s` at `0x180011c42`
- `msvcrt!memcpy_s` at `0x180011dbb`
- `msvcrt!memcpy_s` at `0x18001207c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012193`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012193`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a38`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 v5; // r15
  __int64 v7; // rdi
  bool v8; // dl
  int v9; // ecx
  win_dox *v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // r10d
  unsigned __int8 v13; // cl
  int v14; // edx
  volatile signed __int32 *v15; // rcx
  win_scope::counted_strong_weak_base *v16; // rdx
  __int64 v17; // r13
  __int64 *v18; // rbx
  __int64 *v19; // rsi
  size_t v20; // r15
  const void *v21; // rdx
  size_t v22; // r8
  _QWORD *v23; // rcx
  int v24; // eax
  _QWORD *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // r14
  volatile signed __int32 *v28; // rcx
  win_scope::counted_strong_weak_base *v29; // rdx
  rsize_t v30; // r13
  rsize_t v31; // rdx
  rsize_t v32; // rbx
  rsize_t v33; // r12
  _QWORD *v34; // r8
  void **v35; // rcx
  void **v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v39; // r8d
  rsize_t v40; // rbx
  void **v41; // r8
  void **v42; // rcx
  void **v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 *v46; // rbx
  __int64 *v47; // rsi
  _QWORD *v48; // rdx
  size_t v49; // r14
  size_t v50; // r8
  void **v51; // rcx
  int v52; // eax
  char v53; // r15
  __int64 *v54; // rsi
  __int64 *i; // rax
  size_t v56; // r14
  void **v57; // rdx
  size_t v58; // r8
  _QWORD *v59; // rcx
  int v60; // eax
  int v61; // ecx
  _QWORD *v62; // r15
  volatile signed __int32 *v63; // rcx
  win_scope::counted_strong_weak_base *v64; // rdx
  __int64 v65; // r14
  __int64 v66; // rcx
  __int64 v67; // rbx
  __int128 v68; // xmm6
  __int128 v69; // xmm7
  __int128 v70; // xmm8
  __int128 v71; // xmm9
  __int64 v72; // xmm10_8
  unsigned int v73; // esi
  _QWORD *v74; // rbx
  void **v75; // rcx
  void **v76; // rax
  __int64 v77; // rcx
  __int64 v78; // rbx
  _QWORD *v79; // rax
  __int64 v80; // rbx
  __int64 *v81; // rcx
  __int64 v82; // rax
  void **v83; // rdx
  signed int v84; // esi
  __int64 result; // rax
  _QWORD *v87; // rbx
  __int64 v88; // rcx
  _QWORD *v89; // rax
  int v90; // eax
  __int64 v91; // r9
  __int64 j; // rax
  __int64 v93; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v94; // [rsp+50h] [rbp-B8h] BYREF
  win_scope::counted_strong_weak_base *v95[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v96; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v97; // [rsp+70h] [rbp-98h] BYREF
  __int64 v98; // [rsp+78h] [rbp-90h] BYREF
  __int64 v99; // [rsp+80h] [rbp-88h]
  char v100[8]; // [rsp+88h] [rbp-80h] BYREF
  void *Destination[2]; // [rsp+90h] [rbp-78h] BYREF
  rsize_t v102; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v103; // [rsp+A8h] [rbp-60h]
  _QWORD *v104; // [rsp+B0h] [rbp-58h]
  _QWORD *v105; // [rsp+B8h] [rbp-50h]
  win_scope::counted_strong_weak_base **v106; // [rsp+C0h] [rbp-48h]
  __int64 v107; // [rsp+C8h] [rbp-40h]
  __int64 v108; // [rsp+D0h] [rbp-38h]
  _QWORD *v109; // [rsp+D8h] [rbp-30h]
  _QWORD *v110; // [rsp+E0h] [rbp-28h]
  __int64 v111; // [rsp+E8h] [rbp-20h]
  win_scope::counted_strong_weak_base **v112; // [rsp+F0h] [rbp-18h]
  char v113[8]; // [rsp+F8h] [rbp-10h] BYREF
  void *Buf1[2]; // [rsp+100h] [rbp-8h] BYREF
  size_t Size; // [rsp+110h] [rbp+8h]
  rsize_t DestinationSize; // [rsp+118h] [rbp+10h]
  __int128 v117; // [rsp+120h] [rbp+18h] BYREF
  char v118[8]; // [rsp+130h] [rbp+28h] BYREF
  void *Block[2]; // [rsp+138h] [rbp+30h] BYREF
  rsize_t v120; // [rsp+148h] [rbp+40h]
  unsigned __int64 v121; // [rsp+150h] [rbp+48h]
  void *Source[2]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v123; // [rsp+168h] [rbp+60h]
  __m256i v124; // [rsp+178h] [rbp+70h] BYREF
  __int64 v125; // [rsp+198h] [rbp+90h]
  _BYTE pExceptionObject[160]; // [rsp+1A8h] [rbp+A0h] BYREF
  wchar_t v127[512]; // [rsp+248h] [rbp+140h] BYREF

  v107 = -2;
  v105 = a4;
  v97 = a3;
  v5 = a2;
  v94 = a2;
  v104 = (_QWORD *)a1;
  v108 = a1;
  v109 = a3;
  v110 = a4;
  LODWORD(v93) = 0;
  v7 = *(_QWORD *)(a1 + 8) + 40LL;
  v111 = v7;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  v9 = *(_DWORD *)(v7 + 44);
  *(_DWORD *)(v7 + 44) = v9 + 1;
  if ( !v9 )
    *(_DWORD *)(v7 + 40) = GetCurrentThreadId();
  v10 = *(win_dox **)(a1 + 8);
  LOBYTE(v10) = *((_BYTE *)v10 + 96);
  win_dox::ThrowIfFailed(v10, v8);
  v11 = a3[1];
  v99 = v11 + 216;
  v12 = 1;
  if ( *(_DWORD *)(v11 + 408) )
  {
    v13 = *(_BYTE *)(v11 + 420);
    v14 = v13 != 11 ? 2 : 0;
    if ( v13 <= 0x14u )
    {
      v88 = *(_QWORD *)(v11 + 248);
      if ( v88 )
      {
        v89 = (_QWORD *)(v11 + 232);
        if ( *(_QWORD *)(v11 + 256) >= 0x10u )
          v89 = (_QWORD *)*v89;
        if ( *((_BYTE *)v89 + v88 - 1) == 47 )
          v14 = 1;
      }
    }
    *(_DWORD *)(v11 + 336) = v14;
  }
  else
  {
    v99 = v11 + 8;
    if ( !*(_DWORD *)(v11 + 200) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1B1u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"Can't add file without header.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  if ( *(_DWORD *)(a3[1] + 200LL) )
  {
    v90 = win_musl::consumption::ZipFileContext::DetermineDesignation();
    *(_DWORD *)(v91 + 128) = v90;
  }
  *(_OWORD *)v95 = 0;
  v15 = (volatile signed __int32 *)*a3;
  if ( *a3 )
  {
    v16 = (win_scope::counted_strong_weak_base *)a3[1];
    if ( v12 + _InterlockedExchangeAdd(v15 + 2, v12) == v12 )
      _InterlockedAdd(v15 + 3, v12);
    v95[0] = (win_scope::counted_strong_weak_base *)v15;
    v95[1] = v16;
  }
  win_musl::consumption::ZipFileContext::TestValidity(v95);
  v17 = *(_QWORD *)(a1 + 8);
  v18 = *(__int64 **)(*(_QWORD *)(v17 + 24) + 8LL);
  v19 = *(__int64 **)(v17 + 24);
  if ( *((_BYTE *)v18 + 81) )
  {
LABEL_27:
    v19 = *(__int64 **)(v17 + 24);
    goto LABEL_28;
  }
  v20 = *(_QWORD *)(v5 + 24);
  do
  {
    if ( *(_QWORD *)(v94 + 32) < 0x10u )
      v21 = (const void *)(v94 + 8);
    else
      v21 = *(const void **)(v94 + 8);
    v22 = v20;
    if ( v18[6] < v20 )
      v22 = v18[6];
    v23 = v18 + 4;
    if ( (unsigned __int64)v18[7] >= 0x10 )
      v23 = (_QWORD *)*v23;
    v24 = memcmp_0(v23, v21, v22);
    if ( v24 )
    {
      if ( v24 < 0 )
        goto LABEL_22;
    }
    else if ( v18[6] < v20 )
    {
LABEL_22:
      v18 = (__int64 *)v18[2];
      continue;
    }
    v19 = v18;
    v18 = (__int64 *)*v18;
  }
  while ( !*((_BYTE *)v18 + 81) );
  v5 = v94;
  if ( v19 == *(__int64 **)(v17 + 24) || (int)std::string::compare(v94, v19 + 3) < 0 )
    goto LABEL_27;
LABEL_28:
  v25 = v104;
  v26 = v104[1];
  if ( v19 != *(__int64 **)(v26 + 24) )
  {
    v62 = v97;
    goto LABEL_139;
  }
  v27 = v26 + 16;
  v98 = v26 + 16;
  v112 = v95;
  *(_OWORD *)v95 = 0;
  v28 = (volatile signed __int32 *)*v97;
  if ( *v97 )
  {
    v29 = (win_scope::counted_strong_weak_base *)v97[1];
    if ( _InterlockedIncrement(v28 + 2) == 1 )
      _InterlockedAdd(v28 + 3, 1u);
    v95[0] = (win_scope::counted_strong_weak_base *)v28;
    v95[1] = v29;
  }
  v106 = v95;
  v30 = 15;
  v31 = 15;
  v103 = 15;
  v102 = 0;
  LOBYTE(Destination[0]) = 0;
  v32 = *(_QWORD *)(v5 + 24);
  v33 = -1;
  if ( v100 == (char *)v5 )
  {
    std::string::erase(v100, *(_QWORD *)(v5 + 24), -1);
    std::string::erase(v100, 0, 0);
  }
  else
  {
    if ( v32 == -1 )
      std::_String_base::_Xlen();
    if ( v32 > 0xF )
    {
      std::string::_Copy(v100, *(_QWORD *)(v5 + 24), 0);
      v31 = v103;
LABEL_37:
      v34 = (_QWORD *)(v5 + 8);
      if ( *(_QWORD *)(v5 + 32) >= 0x10u )
        v34 = (_QWORD *)*v34;
      v35 = Destination;
      if ( v31 >= 0x10 )
        v35 = (void **)Destination[0];
      memcpy_s(v35, v31, v34, v32);
      v36 = Destination;
      if ( v103 >= 0x10 )
        v36 = (void **)Destination[0];
      v102 = v32;
      *((_BYTE *)v36 + v32) = 0;
    }
    else
    {
      if ( v32 )
        goto LABEL_37;
      v102 = 0;
      LOBYTE(Destination[0]) = 0;
    }
  }
  v96 = (__int64 *)v100;
  std::string::string(Source, v100);
  *(_OWORD *)&v124.m256i_u64[1] = 0;
  if ( v95[0] )
  {
    win_scope::counted_strong_weak_base::AddRef(v95[0]);
    v124.m256i_i64[1] = v37;
    v124.m256i_i64[2] = v38;
  }
  LODWORD(v93) = 1;
  if ( v103 >= 0x10 )
    operator delete(Destination[0]);
  v103 = 15;
  v102 = 0;
  LOBYTE(Destination[0]) = 0;
  win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(v95);
  DestinationSize = 15;
  v39 = 0;
  Size = 0;
  LOBYTE(Buf1[0]) = 0;
  v40 = *((_QWORD *)&v123 + 1);
  if ( *((_QWORD *)&v123 + 1) == -1 )
    std::_String_base::_Xlen();
  if ( DestinationSize < *((_QWORD *)&v123 + 1) )
  {
    std::string::_Copy(v113, *((_QWORD *)&v123 + 1), Size);
    v39 = 0;
    if ( v40 )
    {
LABEL_57:
      v41 = &Source[1];
      if ( v124.m256i_i64[0] >= 0x10uLL )
        v41 = (void **)Source[1];
      v42 = Buf1;
      if ( DestinationSize >= 0x10 )
        v42 = (void **)Buf1[0];
      memcpy_s(v42, DestinationSize, v41, v40);
      v43 = Buf1;
      if ( DestinationSize >= 0x10 )
        v43 = (void **)Buf1[0];
      Size = v40;
      v39 = 0;
      *((_BYTE *)v43 + v40) = 0;
    }
  }
  else
  {
    if ( *((_QWORD *)&v123 + 1) )
      goto LABEL_57;
    Size = 0;
    LOBYTE(Buf1[0]) = 0;
  }
  v117 = 0;
  v44 = v124.m256i_i64[1];
  if ( v124.m256i_i64[1] )
  {
    v45 = v124.m256i_i64[2];
    if ( _InterlockedIncrement((volatile signed __int32 *)(v124.m256i_i64[1] + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v44 + 12), 1u);
    *(_QWORD *)&v117 = v44;
    *((_QWORD *)&v117 + 1) = v45;
  }
  v46 = *(__int64 **)(v27 + 8);
  v47 = (__int64 *)v46[1];
  if ( *((_BYTE *)v47 + 81) )
  {
    v53 = 1;
    v54 = *(__int64 **)(v27 + 8);
LABEL_81:
    if ( v54 != **(__int64 ***)(v27 + 8) )
    {
      if ( *((_BYTE *)v54 + 81) )
      {
        v46 = (__int64 *)v54[2];
      }
      else if ( *(_BYTE *)(*v54 + 81) )
      {
        for ( i = (__int64 *)v54[1]; !*((_BYTE *)i + 81) && v46 == (__int64 *)*i; i = (__int64 *)i[1] )
          v46 = i;
        if ( !*((_BYTE *)v46 + 81) )
          v46 = i;
      }
      else
      {
        v46 = (__int64 *)*v54;
        for ( j = *(_QWORD *)(*v54 + 16); !*(_BYTE *)(j + 81); j = v46[2] )
          v46 = (__int64 *)v46[2];
      }
      goto LABEL_89;
    }
    LOBYTE(v39) = 1;
    v61 = v27;
    goto LABEL_98;
  }
  while ( 2 )
  {
    v46 = v47;
    v48 = v47 + 4;
    v49 = Size;
    if ( (unsigned __int64)v47[7] >= 0x10 )
      v48 = (_QWORD *)*v48;
    v50 = v47[6];
    if ( Size < v50 )
      v50 = Size;
    v51 = Buf1;
    if ( DestinationSize >= 0x10 )
      v51 = (void **)Buf1[0];
    v52 = memcmp_0(v51, v48, v50);
    v39 = 0;
    if ( v52 )
    {
      if ( v52 >= 0 )
        goto LABEL_77;
LABEL_147:
      v53 = 1;
      v47 = (__int64 *)*v47;
    }
    else
    {
      if ( v49 < v47[6] )
        goto LABEL_147;
LABEL_77:
      v53 = 0;
      v47 = (__int64 *)v47[2];
    }
    if ( !*((_BYTE *)v47 + 81) )
      continue;
    break;
  }
  v54 = v46;
  if ( v53 )
  {
    v27 = v98;
    goto LABEL_81;
  }
LABEL_89:
  v56 = Size;
  v57 = Buf1;
  if ( DestinationSize >= 0x10 )
    v57 = (void **)Buf1[0];
  v58 = Size;
  if ( v46[6] < Size )
    v58 = v46[6];
  v59 = v46 + 4;
  if ( (unsigned __int64)v46[7] >= 0x10 )
    v59 = (_QWORD *)*v59;
  v60 = memcmp_0(v59, v57, v58);
  if ( !v60 )
  {
    if ( v46[6] >= v56 )
      goto LABEL_99;
LABEL_97:
    LOBYTE(v39) = v53;
    v61 = v98;
LABEL_98:
    std::_Tree<std::_Tmap_traits<std::string,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>,std::less<std::string>,std::allocator<std::pair<std::string const,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>>>,0>>::_Insert(
      v61,
      (unsigned int)&v96,
      v39,
      (_DWORD)v54,
      (__int64)v113);
    goto LABEL_99;
  }
  if ( v60 < 0 )
    goto LABEL_97;
LABEL_99:
  win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(&v117);
  if ( DestinationSize >= 0x10 )
    operator delete(Buf1[0]);
  DestinationSize = 15;
  Size = 0;
  LOBYTE(Buf1[0]) = 0;
  win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(&v124.m256i_u64[1]);
  if ( v124.m256i_i64[0] >= 0x10uLL )
    operator delete(Source[1]);
  *(_OWORD *)v95 = 0;
  v62 = v97;
  v63 = (volatile signed __int32 *)*v97;
  if ( *v97 )
  {
    v64 = (win_scope::counted_strong_weak_base *)v97[1];
    if ( _InterlockedIncrement(v63 + 2) == 1 )
      _InterlockedIncrement(v63 + 3);
    v95[0] = (win_scope::counted_strong_weak_base *)v63;
    v95[1] = v64;
  }
  win_musl::consumption::ZipFileContext::AdvanceState(v95, 5);
  v65 = *(_QWORD *)(v104[1] + 8LL);
  v96 = &v93;
  v66 = 0;
  v93 = 0;
  v67 = *v105;
  if ( *v105 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v67 + 8LL))(*v105);
    v66 = v93;
  }
  v93 = v67;
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  v106 = (win_scope::counted_strong_weak_base **)&v93;
  v68 = *(_OWORD *)(v99 + 128);
  v69 = *(_OWORD *)(v99 + 144);
  v70 = *(_OWORD *)(v99 + 160);
  v71 = *(_OWORD *)(v99 + 176);
  v72 = *(_QWORD *)(v99 + 192);
  v73 = *(_DWORD *)(v99 + 120);
  v74 = (_QWORD *)(v94 + 8);
  if ( *(_QWORD *)(v94 + 32) >= 0x10u )
    v74 = (_QWORD *)*v74;
  v121 = 15;
  v120 = 0;
  LOBYTE(Block[0]) = 0;
  do
    ++v33;
  while ( *((_BYTE *)v74 + v33) );
  if ( v33 == -1 )
    std::_String_base::_Xlen();
  if ( v33 > 0xF )
  {
    std::string::_Copy(v118, v33, 0);
    v30 = v121;
LABEL_118:
    v75 = Block;
    if ( v30 >= 0x10 )
      v75 = (void **)Block[0];
    memcpy_s(v75, v30, v74, v33);
    v76 = Block;
    if ( v121 >= 0x10 )
      v76 = (void **)Block[0];
    v120 = v33;
    *((_BYTE *)v76 + v33) = 0;
  }
  else
  {
    if ( v33 )
      goto LABEL_118;
    v120 = 0;
    LOBYTE(Block[0]) = 0;
  }
  v99 = 0;
  v77 = 0;
  v94 = 0;
  v78 = v93;
  if ( v93 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 8LL))(v93);
    v77 = v94;
  }
  else
  {
    v78 = 0;
  }
  v94 = v78;
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  v79 = (_QWORD *)win_musl::UnknownOnly_win_musl::detail::SendCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_musl::ZipFileReceiver_win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_musl::InnerCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_scope::report_policy_throw____win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_mp_lib::null_type_::CreateInstance_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____(
                    &v97,
                    &v94);
  v99 = 0;
  win_musl::com_object_cast_win_scope::scope_IWin7ZipFileSender___win_scope::const_policies_win_scope::com_policies____win_musl::detail::SendCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_musl::ZipFileReceiver_win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_musl::InnerCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_scope::report_policy_throw____win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_mp_lib::null_type_(
    &v98,
    *v79);
  v80 = v98;
  v99 = v98;
  if ( v97 )
    (*(void (__fastcall **)(_QWORD *))(*v97 + 16LL))(v97);
  v81 = *(__int64 **)(v65 + 16);
  v82 = *v81;
  v83 = Block;
  if ( v121 >= 0x10 )
    v83 = (void **)Block[0];
  *(_OWORD *)Source = v68;
  v123 = v69;
  *(_OWORD *)v124.m256i_i8 = v70;
  *(_OWORD *)&v124.m256i_u64[2] = v71;
  v125 = v72;
  v84 = (*(__int64 (__fastcall **)(__int64 *, void **, _QWORD, void **, __int64))(v82 + 56))(v81, v83, v73, Source, v80);
  if ( v84 < 0 )
  {
    memset_0(v127, 0, sizeof(v127));
    StringCchPrintfW(v127, 0x200u, L"Call to AddFile failed with HResult 0x%X.", (unsigned int)v84);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x3Du,
      v84,
      (struct win_musl::TStringEllipseBase *)v127);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  if ( v93 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    v93 = 0;
  }
  if ( v121 >= 0x10 )
    operator delete(Block[0]);
  v25 = v104;
LABEL_139:
  if ( (*(_DWORD *)(v7 + 44))-- == 1 )
    *(_DWORD *)(v7 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  if ( *v25 && v25[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v25);
    *v25 = 0;
    v25[1] = 0;
  }
  result = win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(v62);
  v87 = v105;
  if ( *v105 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v105 + 16LL))(*v105);
    *v87 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800119a4  mov     rax, rsp
0x1800119a7  push    rbp
0x1800119a8  push    rbx
0x1800119a9  push    rsi
0x1800119aa  push    rdi
0x1800119ab  push    r12
0x1800119ad  push    r13
0x1800119af  push    r14
0x1800119b1  push    r15
0x1800119b3  lea     rbp, [rax-5E8h]
0x1800119ba  sub     rsp, 6A8h
0x1800119c1  mov     [rbp+5E0h+var_620], 0FFFFFFFFFFFFFFFEh
0x1800119c9  movaps  xmmword ptr [rax-58h], xmm6
0x1800119cd  movaps  xmmword ptr [rax-68h], xmm7
0x1800119d1  movaps  xmmword ptr [rax-78h], xmm8
0x1800119d6  movaps  xmmword ptr [rax-88h], xmm9
0x1800119de  movaps  xmmword ptr [rax-98h], xmm10
0x1800119e6  mov     rax, cs:__security_cookie
0x1800119ed  xor     rax, rsp
0x1800119f0  mov     [rbp+5E0h+var_A0], rax
0x1800119f7  mov     rax, r9
0x1800119fa  mov     [rbp+5E0h+var_630], rax
0x1800119fe  mov     rsi, r8
0x180011a01  mov     [rsp+6E0h+var_678], r8
0x180011a06  mov     r15, rdx
0x180011a09  mov     [rsp+6E0h+var_698], rdx
0x180011a0e  mov     rbx, rcx
0x180011a11  mov     [rbp+5E0h+var_638], rcx
0x180011a15  mov     [rbp+5E0h+var_618], rcx
0x180011a19  mov     [rbp+5E0h+var_610], r8
0x180011a1d  mov     [rbp+5E0h+var_608], rax
0x180011a21  xor     r12d, r12d
0x180011a24  mov     dword ptr [rsp+6E0h+var_6A0], r12d
0x180011a29  mov     rdi, [rcx+8]
0x180011a2d  add     rdi, 28h ; '('
0x180011a31  mov     [rbp+5E0h+var_600], rdi
0x180011a35  mov     rcx, rdi; lpCriticalSection
0x180011a38  call    cs:__imp_EnterCriticalSection
0x180011a3e  mov     ecx, [rdi+2Ch]
0x180011a41  lea     eax, [rcx+1]
0x180011a44  mov     [rdi+2Ch], eax
0x180011a47  test    ecx, ecx
0x180011a49  jnz     short loc_180011A54
0x180011a4b  call    cs:__imp_GetCurrentThreadId
0x180011a51  mov     [rdi+28h], eax
0x180011a54  mov     rcx, [rbx+8]
0x180011a58  mov     cl, [rcx+60h]; this
0x180011a5b  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180011a60  mov     r8, [rsi+8]
0x180011a64  lea     rax, [r8+0D8h]
0x180011a6b  mov     [rsp+6E0h+var_668], rax
0x180011a70  mov     r10d, 1
0x180011a76  cmp     [rax+0C0h], r12d
0x180011a7d  jz      loc_180011C88
0x180011a83  mov     cl, [r8+1A4h]
0x180011a8a  lea     eax, [rcx-0Bh]
0x180011a8d  neg     al
0x180011a8f  sbb     edx, edx
0x180011a91  and     edx, 2
0x180011a94  cmp     cl, 14h
0x180011a97  jbe     loc_180012306
0x180011a9d  mov     [r8+150h], edx
0x180011aa4  mov     r9, [rsi+8]
0x180011aa8  lea     rcx, [r9+8]
0x180011aac  cmp     [rcx+0C0h], r12d
0x180011ab3  jnz     loc_180012403
0x180011ab9  xorps   xmm0, xmm0
0x180011abc  movdqu  xmmword ptr [rsp+6E0h+var_698+8], xmm0
0x180011ac2  mov     rcx, [rsi]
0x180011ac5  test    rcx, rcx
0x180011ac8  jz      short loc_180011AEC
0x180011aca  mov     rdx, [rsi+8]
0x180011ace  mov     eax, r10d
0x180011ad1  lock xadd [rcx+8], eax
0x180011ad6  add     eax, r10d
0x180011ad9  cmp     eax, r10d
0x180011adc  jz      loc_180012223
0x180011ae2  mov     [rsp+6E0h+var_698+8], rcx
0x180011ae7  mov     [rsp+6E0h+var_688], rdx
0x180011aec  lea     rcx, [rsp+6E0h+var_698+8]
0x180011af1  call    ?TestValidity@ZipFileContext@consumption@win_musl@@SAXV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::ZipFileContext::TestValidity(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>)
0x180011af6  mov     r13, [rbx+8]
0x180011afa  mov     r14, [r13+18h]
0x180011afe  mov     rbx, [r14+8]
0x180011b02  mov     rsi, r14
0x180011b05  cmp     [rbx+51h], r12b
0x180011b09  jnz     short loc_180011B70
0x180011b0b  mov     r15, [r15+18h]
0x180011b0f  mov     r14, [rsp+6E0h+var_698]
0x180011b14  cmp     qword ptr [r14+20h], 10h
0x180011b19  jb      loc_180011C63
0x180011b1f  mov     rdx, [r14+8]; Buf2
0x180011b23  mov     r8, r15
0x180011b26  cmp     [rbx+30h], r15
0x180011b2a  cmovb   r8, [rbx+30h]; Size
0x180011b2f  lea     rcx, [rbx+20h]
0x180011b33  cmp     qword ptr [rbx+38h], 10h
0x180011b38  jb      short loc_180011B3D
0x180011b3a  mov     rcx, [rcx]; Buf1
0x180011b3d  call    memcmp_0
0x180011b42  test    eax, eax
0x180011b44  jz      short loc_180011B4E
0x180011b46  jns     short loc_180011B54
0x180011b48  mov     rbx, [rbx+10h]
0x180011b4c  jmp     short loc_180011B5A
0x180011b4e  cmp     [rbx+30h], r15
0x180011b52  jb      short loc_180011B48
0x180011b54  mov     rsi, rbx
0x180011b57  mov     rbx, [rbx]
0x180011b5a  cmp     byte ptr [rbx+51h], 0
0x180011b5e  jz      short loc_180011B14
0x180011b60  mov     r15, r14
0x180011b63  cmp     rsi, [r13+18h]
0x180011b67  jnz     loc_180011C6C
0x180011b6d  xor     r12d, r12d
0x180011b70  mov     rsi, [r13+18h]
0x180011b74  mov     rbx, [rbp+5E0h+var_638]
0x180011b78  mov     rax, [rbx+8]
0x180011b7c  cmp     rsi, [rax+18h]
0x180011b80  jnz     loc_180012352
0x180011b86  lea     r14, [rax+10h]
0x180011b8a  mov     [rsp+6E0h+var_670], r14
0x180011b8f  lea     rax, [rsp+6E0h+var_698+8]
0x180011b94  mov     [rbp+5E0h+var_5F8], rax
0x180011b98  xorps   xmm0, xmm0
0x180011b9b  movdqu  xmmword ptr [rsp+6E0h+var_698+8], xmm0
0x180011ba1  mov     rdx, [rsp+6E0h+var_678]
0x180011ba6  mov     rcx, [rdx]
0x180011ba9  mov     esi, 1
0x180011bae  test    rcx, rcx
0x180011bb1  jz      short loc_180011BD2
0x180011bb3  mov     rdx, [rdx+8]
0x180011bb7  mov     eax, esi
0x180011bb9  lock xadd [rcx+8], eax
0x180011bbe  add     eax, esi
0x180011bc0  cmp     eax, esi
0x180011bc2  jz      loc_180012276
0x180011bc8  mov     [rsp+6E0h+var_698+8], rcx
0x180011bcd  mov     [rsp+6E0h+var_688], rdx
0x180011bd2  lea     rax, [rsp+6E0h+var_698+8]
0x180011bd7  mov     [rbp+5E0h+var_628], rax
0x180011bdb  mov     r13d, 0Fh
0x180011be1  mov     edx, r13d; DestinationSize
0x180011be4  mov     [rbp+5E0h+var_640], rdx
0x180011be8  mov     r8, r12
0x180011beb  mov     [rbp+5E0h+var_648], r12
0x180011bef  mov     byte ptr [rbp+5E0h+Destination], r12b
0x180011bf3  mov     rbx, [r15+18h]
0x180011bf7  lea     rax, [rbp+5E0h+var_660]
0x180011bfb  or      r12, 0FFFFFFFFFFFFFFFFh
0x180011bff  cmp     rax, r15
0x180011c02  jz      loc_180012423
0x180011c08  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x180011c0c  ja      loc_180012445
0x180011c12  cmp     rdx, rbx
0x180011c15  jb      loc_180011CE8
0x180011c1b  test    rbx, rbx
0x180011c1e  jz      loc_18001239B
0x180011c24  lea     r8, [r15+8]
0x180011c28  cmp     qword ptr [r15+20h], 10h
0x180011c2d  jb      short loc_180011C32
0x180011c2f  mov     r8, [r8]; Source
0x180011c32  lea     rcx, [rbp+5E0h+Destination]
0x180011c36  cmp     rdx, 10h
0x180011c3a  cmovnb  rcx, [rbp+5E0h+Destination]; Destination
0x180011c3f  mov     r9, rbx; SourceSize
0x180011c42  call    cs:__imp_memcpy_s
0x180011c48  lea     rax, [rbp+5E0h+Destination]
0x180011c4c  cmp     [rbp+5E0h+var_640], 10h
0x180011c51  cmovnb  rax, [rbp+5E0h+Destination]
0x180011c56  mov     [rbp+5E0h+var_648], rbx
0x180011c5a  mov     byte ptr [rax+rbx], 0
0x180011c5e  jmp     loc_180011D01
0x180011c63  lea     rdx, [r14+8]
0x180011c67  jmp     loc_180011B23
0x180011c6c  lea     rdx, [rsi+18h]
0x180011c70  mov     rcx, r14
0x180011c73  call    ?compare@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEBAHAEBV12@@Z; std::string::compare(std::string const &)
0x180011c78  xor     r12d, r12d
0x180011c7b  test    eax, eax
0x180011c7d  jns     loc_180011B74
0x180011c83  jmp     loc_180011B70
0x180011c88  lea     rax, [r8+8]
0x180011c8c  mov     [rsp+6E0h+var_668], rax
0x180011c91  cmp     [rax+0C0h], r12d
0x180011c98  jnz     loc_180011AA4
0x180011c9e  lea     rax, aCanTAddFileWit; "Can't add file without header."
0x180011ca5  mov     [rsp+6E0h+var_6B0], rax; struct win_musl::TStringEllipseBase *
0x180011caa  mov     [rsp+6E0h+var_6B8], 8000FFFFh; unsigned int
0x180011cb2  mov     [rsp+6E0h+var_6C0], 1B1h; unsigned int
0x180011cba  lea     r9, word_18013A0B6
0x180011cc1  lea     r8, aNoFilename; "(no filename)"
0x180011cc8  lea     rcx, [rbp+5E0h+pExceptionObject]; this
0x180011ccf  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180011cd4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180011cdb  lea     rcx, [rbp+5E0h+pExceptionObject]; pExceptionObject
0x180011ce2  call    _CxxThrowException_0
0x180011ce8  mov     rdx, rbx
0x180011ceb  lea     rcx, [rbp+5E0h+var_660]
0x180011cef  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180011cf4  mov     rdx, [rbp+5E0h+var_640]
0x180011cf8  test    rbx, rbx
0x180011cfb  jnz     loc_180011C24
0x180011d01  lea     rax, [rbp+5E0h+var_660]
0x180011d05  mov     [rsp+6E0h+var_680], rax
0x180011d0a  lea     rdx, [rbp+5E0h+var_660]
0x180011d0e  lea     rcx, [rbp+5E0h+Source]
0x180011d12  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180011d17  nop
0x180011d18  xorps   xmm0, xmm0
0x180011d1b  movdqu  [rbp+5E0h+var_570+8], xmm0
0x180011d20  mov     rcx, [rsp+6E0h+var_698+8]; this
0x180011d25  test    rcx, rcx
0x180011d28  jz      short loc_180011D3F
0x180011d2a  mov     rdx, [rsp+6E0h+var_688]
0x180011d2f  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180011d34  mov     qword ptr [rbp+5E0h+var_570+8], rcx
0x180011d38  mov     qword ptr [rbp+5E0h+var_560], rdx
0x180011d3f  mov     dword ptr [rsp+6E0h+var_6A0], esi
0x180011d43  cmp     [rbp+5E0h+var_640], 10h
0x180011d48  jnb     loc_1800122CE
0x180011d4e  mov     [rbp+5E0h+var_640], r13
0x180011d52  mov     [rbp+5E0h+var_648], 0
0x180011d5a  mov     byte ptr [rbp+5E0h+Destination], 0
0x180011d5e  lea     rcx, [rsp+6E0h+var_698+8]
0x180011d63  call    ??$destruct@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@?$scope_helper@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@2@@Z; win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>> *)
0x180011d68  nop
0x180011d69  mov     [rbp+5E0h+DestinationSize], r13
0x180011d6d  xor     r8d, r8d
0x180011d70  mov     [rbp+5E0h+Size], r8
0x180011d74  mov     byte ptr [rbp+5E0h+Buf1], r8b
0x180011d78  mov     rbx, [rbp+5E0h+SourceSize]
0x180011d7c  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x180011d80  ja      loc_180012457
0x180011d86  cmp     [rbp+5E0h+DestinationSize], rbx
0x180011d8a  jb      loc_18001235C
0x180011d90  test    rbx, rbx
0x180011d93  jz      loc_1800123B8
0x180011d99  lea     r8, [rbp+5E0h+Source+8]
0x180011d9d  cmp     qword ptr [rbp+5E0h+var_570], 10h
0x180011da2  cmovnb  r8, [rbp+5E0h+Source+8]; Source
0x180011da7  mov     rdx, [rbp+5E0h+DestinationSize]; DestinationSize
0x180011dab  lea     rcx, [rbp+5E0h+Buf1]
0x180011daf  cmp     rdx, 10h
0x180011db3  cmovnb  rcx, [rbp+5E0h+Buf1]; Destination
0x180011db8  mov     r9, rbx; SourceSize
0x180011dbb  call    cs:__imp_memcpy_s
0x180011dc1  lea     rax, [rbp+5E0h+Buf1]
0x180011dc5  cmp     [rbp+5E0h+DestinationSize], 10h
0x180011dca  cmovnb  rax, [rbp+5E0h+Buf1]
0x180011dcf  mov     [rbp+5E0h+Size], rbx
0x180011dd3  xor     r8d, r8d
0x180011dd6  mov     [rax+rbx], r8b
0x180011dda  xorps   xmm0, xmm0
0x180011ddd  movdqu  [rbp+5E0h+var_5C8], xmm0
0x180011de2  mov     rcx, qword ptr [rbp+5E0h+var_570+8]
0x180011de6  test    rcx, rcx
0x180011de9  jz      short loc_180011E0B
0x180011deb  mov     rdx, qword ptr [rbp+5E0h+var_560]
0x180011df2  mov     eax, esi
0x180011df4  lock xadd [rcx+8], eax
0x180011df9  add     eax, esi
0x180011dfb  cmp     eax, esi
0x180011dfd  jz      loc_18001227F
0x180011e03  mov     qword ptr [rbp+5E0h+var_5C8], rcx
0x180011e07  mov     qword ptr [rbp+5E0h+var_5C8+8], rdx
0x180011e0b  mov     rbx, [r14+8]
0x180011e0f  mov     rsi, [rbx+8]
0x180011e13  cmp     [rsi+51h], r8b
0x180011e17  jnz     loc_180012338
0x180011e1d  mov     rbx, rsi
0x180011e20  lea     rdx, [rsi+20h]
0x180011e24  mov     r14, [rbp+5E0h+Size]
0x180011e28  cmp     qword ptr [rsi+38h], 10h
0x180011e2d  jb      short loc_180011E32
0x180011e2f  mov     rdx, [rdx]; Buf2
0x180011e32  mov     r8, [rsi+30h]
0x180011e36  cmp     r14, r8
0x180011e39  cmovb   r8, r14; Size
0x180011e3d  lea     rcx, [rbp+5E0h+Buf1]
0x180011e41  cmp     [rbp+5E0h+DestinationSize], 10h
0x180011e46  cmovnb  rcx, [rbp+5E0h+Buf1]; Buf1
0x180011e4b  call    memcmp_0
0x180011e50  xor     r8d, r8d
0x180011e53  test    eax, eax
0x180011e55  jz      loc_180012343
0x180011e5b  js      loc_180012218
0x180011e61  mov     r15b, r8b
0x180011e64  mov     rsi, [rsi+10h]
0x180011e68  cmp     [rsi+51h], r8b
0x180011e6c  jz      short loc_180011E1D
0x180011e6e  mov     rsi, rbx
0x180011e71  test    r15b, r15b
0x180011e74  jz      short loc_180011EBA
0x180011e76  mov     r14, [rsp+6E0h+var_670]
0x180011e7b  mov     rax, [r14+8]
0x180011e7f  cmp     rsi, [rax]
0x180011e82  jz      loc_1800122C3
0x180011e88  cmp     [rsi+51h], r8b
0x180011e8c  jnz     loc_1800123FA
  ... truncated ...
```

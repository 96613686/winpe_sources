# inverted::CInvertedIndex::_CheckMerge(bool,bool)

- ea: `0x180088248`
- end: `0x180088b2b`
- name: `?_CheckMerge@CInvertedIndex@inverted@@AEAAX_N0@Z`
- size: `2275`
- prototype: `void __fastcall(inverted::CInvertedIndex *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x1800785dc`
- `0x180087940`
- `0x18021a9d0`

## callees

- `0x18002a3e0`
- `0x18002a3f8`
- `0x18002ca28`
- `0x18002d30c`
- `0x1800324c8`
- `0x180036d60`
- `0x180047e78`
- `0x180048890`
- `0x180048b10`
- `0x18004d9d8`
- `0x180050858`
- `0x18005b8c8`
- `0x18007aca0`
- `0x180088248`
- `0x180088bc8`
- `0x180088c84`
- `0x180088d18`
- `0x180088d80`
- `0x180089084`
- `0x1800de9a4`
- `0x1800eaa2c`
- `0x1800ef1a0`
- `0x1801183f0`
- `0x1801470d4`
- `0x180147190`
- `0x18015708c`
- `0x18016d8d4`
- `0x18016f9fc`
- `0x18017787c`
- `0x180178344`
- `0x180188d90`
- `0x180188dc0`
- `0x180189cce`
- `0x1802173a4`
- `0x1802185dc`
- `0x18021d780`
- `0x180294310`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800888cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800888cd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800885ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180088638`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800885ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180088638`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008884c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008884c`

## string_xrefs

- `0x18008860d`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180088656`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall inverted::CInvertedIndex::_CheckMerge(inverted::CInvertedIndex *this, char a2, char a3)
{
  char *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int *v11; // r13
  unsigned __int64 v12; // rax
  unsigned int **v13; // rbx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  __int64 *v16; // r8
  __int64 *v17; // rcx
  __int64 *v18; // rdx
  unsigned int v19; // ebx
  unsigned int **v20; // r14
  unsigned int v21; // edx
  unsigned int *v22; // rax
  unsigned int *v23; // r12
  __int64 v24; // r15
  __int64 v25; // rax
  void **v26; // rax
  void *v27; // rbx
  unsigned int *v28; // r15
  unsigned __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  unsigned int v32; // r15d
  unsigned int v33; // edx
  _QWORD *v34; // r12
  __int64 v35; // r14
  __int64 v36; // rax
  void **v37; // rax
  void *v38; // rbx
  unsigned __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // r8
  void *v43; // rax
  const char *v44; // r9
  __int64 v45; // r8
  void *v46; // rax
  const char *v47; // r9
  unsigned int v48; // r14d
  unsigned int **v49; // r12
  char IndicesToMerge; // r15
  unsigned int v51; // eax
  char *v52; // rcx
  __int64 v53; // rax
  __int64 *v54; // r10
  __int64 v55; // rbx
  char *v56; // rax
  unsigned int v57; // edx
  int v58; // ecx
  __int64 v59; // rbx
  _QWORD *v60; // rdx
  unsigned __int64 v61; // rdx
  _QWORD *v62; // rdx
  unsigned __int64 v63; // rdx
  __int64 v64; // rbx
  __int64 v65; // r13
  __int64 v66; // rcx
  __int64 v67; // r8
  unsigned int *v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // r9
  char v73[8]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int *v74; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v75; // [rsp+30h] [rbp-D0h]
  void *v76; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v77; // [rsp+40h] [rbp-C0h]
  unsigned int *v78; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v79; // [rsp+50h] [rbp-B0h]
  unsigned int v80; // [rsp+54h] [rbp-ACh]
  __int64 v81; // [rsp+58h] [rbp-A8h]
  unsigned int **v82; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v83; // [rsp+68h] [rbp-98h]
  __int64 v84; // [rsp+70h] [rbp-90h]
  char *v85; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v86; // [rsp+80h] [rbp-80h]
  unsigned __int64 v87; // [rsp+88h] [rbp-78h] BYREF
  __int64 v88; // [rsp+90h] [rbp-70h] BYREF
  __int64 v89; // [rsp+98h] [rbp-68h]
  __int64 v90; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v91; // [rsp+B0h] [rbp-50h]
  _DWORD v92[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v93; // [rsp+D0h] [rbp-30h]
  unsigned int v94; // [rsp+D4h] [rbp-2Ch]
  int v95; // [rsp+D8h] [rbp-28h]
  int v96; // [rsp+E8h] [rbp-18h]
  int v97; // [rsp+ECh] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+1508h] [rbp+1408h]

  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30), &v90, 0);
  v6 = (char *)(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v90 + 8LL))(v90);
  inverted::CInvertedIndex::_RestartPausedMerges(this);
  if ( a2 )
  {
    LOBYTE(v7) = a3;
    if ( (unsigned __int8)inverted::CInvertedIndex::_CheckMasterMerge(this, v7, &v90) )
    {
      *((_BYTE *)this + 624) = 0;
      if ( *((_QWORD *)this + 77) <= 1u )
        MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10);
      v74 = (unsigned int *)*((_QWORD *)this + 76);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned int>>,std::_Iterator_base0>::operator--(&v74);
      v55 = *v54;
      v56 = (char *)operator new(0x20u);
      v85 = v56;
      *(_OWORD *)v56 = 0;
      *((_DWORD *)v56 + 2) = 1;
      *((_DWORD *)v56 + 3) = 1;
      *(_QWORD *)v56 = &std::_Ref_count_obj2<inverted::SMergeData>::`vftable';
      v57 = v74[7];
      v58 = *(_DWORD *)(v55 + 28);
      *((_WORD *)v56 + 8) = 1;
      *((_DWORD *)v56 + 5) = v58;
      *((_DWORD *)v56 + 6) = v57;
      *((_DWORD *)v56 + 7) = -1;
      v85 = v56 + 16;
      v86 = (std::_Ref_count_base *)v56;
      std::shared_ptr<inverted::CQueryOperator>::operator=<inverted::CNoneOperator,0>((char *)this + 520, &v85);
      if ( v86 )
        std::_Ref_count_base::_Decref(v86);
      std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::clear((char *)this + 608);
      *((_BYTE *)this + 481) = 1;
      SubmitThreadpoolWork(*((PTP_WORK *)this + 59));
      goto LABEL_58;
    }
  }
  if ( *((_BYTE *)this + 624) )
    goto LABEL_58;
  v85 = v6;
  v78 = 0;
  v79 = -1;
  v80 = -1;
  v81 = 0;
  dynamic_sparse_bit<unsigned __int64>::Empty(&v78);
  v11 = (unsigned int *)((char *)this + 904);
  v78 = (unsigned int *)((char *)this + 904);
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v82);
  v12 = (unsigned int)(*((_DWORD *)this + 93) - 1);
  v13 = v82;
  v14 = 0xAAAAAAAAAAAAAAABuLL * ((v83 - (__int64)v82) >> 3);
  if ( v12 < v14 )
  {
    v59 = (__int64)&v82[3 * v12];
    std::_Destroy_range<std::allocator<dynamic_sparse_bit<unsigned __int64>>>(v59, v83);
    v83 = v59;
LABEL_8:
    v13 = v82;
    goto LABEL_9;
  }
  if ( v12 > v14 )
  {
    if ( v12 <= 0xAAAAAAAAAAAAAAABuLL * ((v84 - (__int64)v82) >> 3) )
      v83 = std::_Uninitialized_value_construct_n<std::allocator<dynamic_sparse_bit<unsigned __int64>>>(v83, v12 - v14);
    else
      std::vector<dynamic_sparse_bit<unsigned __int64>>::_Resize_reallocate<std::_Value_init_tag>(&v82);
    goto LABEL_8;
  }
LABEL_9:
  while ( v13 != (unsigned int **)v83 )
  {
    dynamic_sparse_bit<unsigned __int64>::Empty(v13);
    *v13 = v11;
    v13 += 3;
  }
  LODWORD(v15) = 0;
  v87 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      memset_0(v92, 0, 0x13F0u);
      v92[0] = -1;
      v92[3] = 1;
      v93 = -1;
      v94 = -1;
      v95 = 0;
      v96 = -1;
      v97 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v90 + 16LL))(v90, (unsigned int)v15, v92);
      if ( v94 != 17 && v94 < *((_DWORD *)this + 93) - 1 && v93 == -1 )
      {
        v16 = (__int64 *)*((_QWORD *)this + 76);
        v17 = (__int64 *)v16[1];
        HIDWORD(v89) = 0;
        v18 = v16;
        while ( !*((_BYTE *)v17 + 25) )
        {
          if ( *((_DWORD *)v17 + 7) < v92[0] )
          {
            v17 = (__int64 *)v17[2];
          }
          else
          {
            v18 = v17;
            v17 = (__int64 *)*v17;
          }
        }
        if ( !*((_BYTE *)v18 + 25) )
        {
          v19 = v92[0];
          v75 = v92[0];
          if ( v18 != v16 && v92[0] >= *((_DWORD *)v18 + 7) )
          {
            v20 = &v82[3 * v94];
            v21 = v92[0] >> (*v20)[5];
            if ( v21 < *((_DWORD *)v20 + 2) )
            {
              v22 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v82[3 * v94]);
            }
            else if ( v21 >= *((_DWORD *)v20 + 3) )
            {
              v22 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v82[3 * v94]);
            }
            else
            {
              v22 = &v20[2][2 * (v21 - *((_DWORD *)v20 + 2))];
            }
            v74 = v22;
            if ( *(_QWORD *)v22 )
            {
              v28 = v74;
            }
            else
            {
              v23 = *v20;
              v24 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*v20 + 12);
              v25 = *(_QWORD *)(v24 + 24);
              if ( *(_QWORD *)(v24 + 16) == v25 )
              {
                v45 = *(unsigned int *)(v24 + 8);
                if ( (unsigned int)v45 < v23[7] )
                {
                  v27 = (void *)(*(_QWORD *)v24 + 8 * v45);
                  *(_DWORD *)(v24 + 8) = v45 + v23[2];
                }
                else
                {
                  v46 = _aligned_malloc(8LL * v23[7], v23[8]);
                  v27 = v46;
                  v76 = v46;
                  if ( !v46 )
                    wil::details::in1diag3::_Throw_NullAlloc(
                      retaddr,
                      (void *)0x430,
                      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                      v47);
                  v62 = *(_QWORD **)(v24 + 48);
                  if ( v62 == *(_QWORD **)(v24 + 56) )
                  {
                    std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                      v24 + 40,
                      v62,
                      &v76);
                    v27 = v76;
                  }
                  else
                  {
                    *v62 = v46;
                    *(_QWORD *)(v24 + 48) += 8LL;
                  }
                  v63 = v23[6] * ((__int64)(*(_QWORD *)(v24 + 48) - *(_QWORD *)(v24 + 40)) >> 3);
                  v76 = (void *)v63;
                  if ( v63 > (__int64)(*(_QWORD *)(v24 + 32) - *(_QWORD *)(v24 + 16)) >> 3 )
                  {
                    if ( v63 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_77:
                      std::_Xlength_error("vector too long");
                    std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v24 + 16, &v76);
                  }
                  *(_QWORD *)v24 = v27;
                  *(_DWORD *)(v24 + 8) = v23[2];
                  v11 = v78;
                }
              }
              else
              {
                v26 = (void **)(v25 - 8);
                v27 = *v26;
                *(_QWORD *)(v24 + 24) = v26;
              }
              v28 = v74;
              *(_QWORD *)v74 = v27;
              memset_0(v27, 0, v23[1]);
              v19 = v75;
            }
            v29 = ((unsigned __int64)v19 >> 6) & (*v20)[4];
            v30 = 1LL << (v19 & 0x3F);
            v31 = *(_QWORD *)(*(_QWORD *)v28 + 8 * v29);
            if ( (v31 & v30) == 0 )
              *(_QWORD *)(*(_QWORD *)v28 + 8 * v29) = v30 | v31;
          }
        }
      }
      v32 = v92[0];
      v75 = v92[0];
      v33 = v92[0] >> v11[5];
      if ( v33 < v79 )
        break;
      if ( v33 >= v80 )
      {
        v53 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v78);
        goto LABEL_62;
      }
      v34 = (_QWORD *)(v81 + 8LL * (v33 - v79));
LABEL_34:
      if ( !*v34 )
      {
        v35 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v11 + 12);
        v36 = *(_QWORD *)(v35 + 24);
        if ( *(_QWORD *)(v35 + 16) == v36 )
        {
          v42 = *(unsigned int *)(v35 + 8);
          if ( (unsigned int)v42 < v11[7] )
          {
            v38 = (void *)(*(_QWORD *)v35 + 8 * v42);
            *(_DWORD *)(v35 + 8) = v42 + v11[2];
          }
          else
          {
            v43 = _aligned_malloc(8LL * v11[7], v11[8]);
            v38 = v43;
            v76 = v43;
            if ( !v43 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v44);
            v60 = *(_QWORD **)(v35 + 48);
            if ( v60 == *(_QWORD **)(v35 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v35 + 40,
                v60,
                &v76);
              v38 = v76;
            }
            else
            {
              *v60 = v43;
              *(_QWORD *)(v35 + 48) += 8LL;
            }
            v61 = v11[6] * ((__int64)(*(_QWORD *)(v35 + 48) - *(_QWORD *)(v35 + 40)) >> 3);
            v76 = (void *)v61;
            if ( v61 > (__int64)(*(_QWORD *)(v35 + 32) - *(_QWORD *)(v35 + 16)) >> 3 )
            {
              if ( v61 > 0x1FFFFFFFFFFFFFFFLL )
                goto LABEL_77;
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v35 + 16, &v76);
            }
            *(_QWORD *)v35 = v38;
            *(_DWORD *)(v35 + 8) = v11[2];
            v32 = v75;
          }
        }
        else
        {
          v37 = (void **)(v36 - 8);
          v38 = *v37;
          *(_QWORD *)(v35 + 24) = v37;
        }
        *v34 = v38;
        memset_0(v38, 0, v11[1]);
      }
      v39 = ((unsigned __int64)v32 >> 6) & v11[4];
      v40 = 1LL << (v32 & 0x3F);
      v41 = *(_QWORD *)(*v34 + 8 * v39);
      if ( (v41 & v40) == 0 )
        *(_QWORD *)(*v34 + 8 * v39) = v40 | v41;
      v15 = v87 + 1;
      v87 = v15;
      if ( v15 >= (unsigned __int64)v85 )
        goto LABEL_51;
    }
    v53 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v78);
LABEL_62:
    v11 = v78;
    v34 = (_QWORD *)v53;
    goto LABEL_34;
  }
LABEL_51:
  v48 = 0;
  if ( *((_DWORD *)this + 93) != 1 )
  {
    do
    {
      v49 = &v82[3 * v48];
      IndicesToMerge = 1;
      while ( 1 )
      {
        v51 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(v49);
        v52 = (char *)this + 368;
        if ( !*((_BYTE *)this + 340) )
          v52 = (char *)this + 364;
        if ( v51 < *(_DWORD *)v52 || !IndicesToMerge )
          break;
        std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v88);
        IndicesToMerge = inverted::CInvertedIndex::_GetIndicesToMerge(v71, v49, &v78, &v88);
        if ( (unsigned __int64)((v89 - v88) >> 2) > 1 )
        {
          LOBYTE(v72) = 0;
          std::_Sort_unchecked<unsigned int *,std::less<void>>(v88, v89, (v89 - v88) >> 2, v72);
          v64 = v88;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::find(
            (char *)this + 608,
            &v85,
            v88);
          v65 = v89;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::find(
            (char *)this + 608,
            &v74,
            v89 - 4);
          v68 = (unsigned int *)*((_QWORD *)this + 76);
          if ( v74 == v68 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v66, v68, v67);
            v65 = v89;
            v64 = v88;
          }
          v73[0] = 0;
          ((void (__fastcall *)(void **, __int64, __int64, char *))std::make_shared<inverted::SMergeData,unsigned int &,unsigned int &,bool>)(
            &v76,
            v64,
            v65 - 4,
            v73);
          if ( (unsigned __int8)inverted::MergeAllowed(v76, (char *)this + 536)
            && (unsigned __int8)inverted::MergeAllowed(v76, (char *)this + 560) )
          {
            v70 = *((_QWORD *)this + 71);
            if ( v70 == *((_QWORD *)this + 72) )
            {
              std::vector<std::shared_ptr<inverted::SMergeData>>::_Emplace_reallocate<std::shared_ptr<inverted::SMergeData> const &>(
                (char *)this + 560,
                *((_QWORD *)this + 71),
                &v76);
            }
            else
            {
              std::shared_ptr<inverted::IInvertedQueryProps>::shared_ptr<inverted::IInvertedQueryProps>(v70, &v76, v69);
              *((_QWORD *)this + 71) += 16LL;
            }
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<long const,unsigned long>>>,std::_Iterator_base0>::operator++(&v74);
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::erase(
              (char *)this + 608,
              &v87,
              v85,
              v74);
            CThreadPoolWork::SubmitThreadpoolWork((inverted::CInvertedIndex *)((char *)this + 472), 1u);
          }
          if ( v77 )
            std::_Ref_count_base::_Decref(v77);
        }
        else
        {
          IndicesToMerge = 0;
        }
        std::vector<enum inverted::DateField>::~vector<enum inverted::DateField>(&v88);
      }
      ++v48;
    }
    while ( v48 < *((_DWORD *)this + 93) - 1 );
  }
  std::vector<dynamic_sparse_bit<unsigned __int64>>::_Tidy(&v82);
  _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::clear(&v78);
LABEL_58:
  if ( v91 )
    std::_Ref_count_base::_Decref(v91);
}

```

## disassembly

```asm
0x180088248  push    rbp
0x18008824a  push    rbx
0x18008824b  push    rsi
0x18008824c  push    rdi
0x18008824d  push    r12
0x18008824f  push    r13
0x180088251  push    r14
0x180088253  push    r15
0x180088255  lea     rbp, [rsp-13C8h]
0x18008825d  mov     eax, 14C8h
0x180088262  call    _alloca_probe
0x180088267  sub     rsp, rax
0x18008826a  mov     rax, cs:__security_cookie
0x180088271  xor     rax, rsp
0x180088274  mov     [rbp+1400h+var_50], rax
0x18008827b  mov     sil, r8b
0x18008827e  mov     bl, dl
0x180088280  mov     rdi, rcx
0x180088283  xor     r12d, r12d
0x180088286  mov     rcx, [rcx+0F0h]
0x18008828d  mov     rax, [rcx]
0x180088290  xor     r8d, r8d
0x180088293  lea     rdx, [rbp+1400h+var_1458]
0x180088297  mov     rax, [rax+30h]
0x18008829b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800882a0  nop
0x1800882a1  mov     rcx, [rbp+1400h+var_1458]
0x1800882a5  mov     rax, [rcx]
0x1800882a8  mov     rax, [rax+8]
0x1800882ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800882b1  mov     r14d, eax
0x1800882b4  mov     rcx, rdi; this
0x1800882b7  call    ?_RestartPausedMerges@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_RestartPausedMerges(void)
0x1800882bc  test    bl, bl
0x1800882be  jz      short loc_1800882D7
0x1800882c0  lea     r8, [rbp+1400h+var_1458]
0x1800882c4  mov     dl, sil
0x1800882c7  mov     rcx, rdi
0x1800882ca  call    ?_CheckMasterMerge@CInvertedIndex@inverted@@AEAA_N_NAEAV?$shared_ptr@UIIndexStorageSnapshot@inverted@@@std@@@Z; inverted::CInvertedIndex::_CheckMasterMerge(bool,std::shared_ptr<inverted::IIndexStorageSnapshot> &)
0x1800882cf  test    al, al
0x1800882d1  jnz     loc_180088791
0x1800882d7  cmp     [rdi+270h], r12b
0x1800882de  jnz     loc_180088719
0x1800882e4  mov     r15, r14
0x1800882e7  mov     [rsp+1500h+var_1488], r14
0x1800882ec  mov     [rsp+1500h+var_14B8], r12
0x1800882f1  or      r14d, 0FFFFFFFFh
0x1800882f5  mov     [rsp+1500h+var_14B0], r14d
0x1800882fa  mov     [rsp+1500h+var_14AC], r14d
0x1800882ff  mov     [rsp+1500h+var_14A8], r12
0x180088304  lea     rcx, [rsp+1500h+var_14B8]
0x180088309  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x18008830e  lea     r13, [rdi+388h]
0x180088315  mov     [rsp+1500h+var_14B8], r13
0x18008831a  lea     rcx, [rsp+1500h+var_14A0]; void *
0x18008831f  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x180088324  nop
0x180088325  mov     eax, [rdi+174h]
0x18008832b  mov     esi, 1
0x180088330  sub     eax, esi
0x180088332  mov     edx, eax
0x180088334  mov     r8, [rsp+1500h+var_1498]
0x180088339  mov     rcx, r8
0x18008833c  mov     rbx, [rsp+1500h+var_14A0]
0x180088341  sub     rcx, rbx
0x180088344  sar     rcx, 3
0x180088348  mov     r9, 0AAAAAAAAAAAAAAABh
0x180088352  imul    rcx, r9
0x180088356  cmp     rdx, rcx
0x180088359  jb      loc_180088857
0x18008835f  jbe     short loc_180088389
0x180088361  mov     rax, [rsp+1500h+var_1490]
0x180088366  sub     rax, rbx
0x180088369  sar     rax, 3
0x18008836d  imul    rax, r9
0x180088371  cmp     rdx, rax
0x180088374  jbe     loc_180088A86
0x18008837a  lea     rcx, [rsp+1500h+var_14A0]
0x18008837f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U?$dynamic_sparse_bit@_K@@V?$allocator@U?$dynamic_sparse_bit@_K@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<dynamic_sparse_bit<unsigned __int64>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180088384  mov     rbx, [rsp+1500h+var_14A0]
0x180088389  cmp     rbx, [rsp+1500h+var_1498]
0x18008838e  jnz     loc_180088697
0x180088394  mov     rbx, r12
0x180088397  mov     [rbp+1400h+var_1478], rbx
0x18008839b  test    r15, r15
0x18008839e  jz      loc_1800886AE
0x1800883a4  xor     edx, edx; Val
0x1800883a6  mov     r8d, 13F0h; Size
0x1800883ac  lea     rcx, [rbp+1400h+var_1440]; void *
0x1800883b0  call    memset_0
0x1800883b5  mov     [rbp+1400h+var_1440], r14d
0x1800883b9  mov     [rbp+1400h+var_1434], esi
0x1800883bc  mov     [rbp+1400h+var_1430], r14d
0x1800883c0  mov     [rbp+1400h+var_142C], r14d
0x1800883c4  mov     [rbp+1400h+var_1428], r12d
0x1800883c8  mov     [rbp+1400h+var_1418], r14d
0x1800883cc  mov     [rbp+1400h+var_1414], r12d
0x1800883d0  mov     rcx, [rbp+1400h+var_1458]
0x1800883d4  mov     rax, [rcx]
0x1800883d7  mov     edx, ebx
0x1800883d9  lea     r8, [rbp+1400h+var_1440]
0x1800883dd  mov     rax, [rax+10h]
0x1800883e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800883e6  mov     r9d, [rbp+1400h+var_142C]
0x1800883ea  cmp     r9d, 11h
0x1800883ee  jz      loc_180088517
0x1800883f4  mov     eax, [rdi+174h]
0x1800883fa  sub     eax, esi
0x1800883fc  cmp     r9d, eax
0x1800883ff  jnb     loc_180088517
0x180088405  cmp     [rbp+1400h+var_1430], r14d
0x180088409  jnz     loc_180088517
0x18008840f  mov     r8, [rdi+260h]
0x180088416  mov     rcx, [r8+8]
0x18008841a  xor     eax, eax
0x18008841c  mov     [rbp+1400h+var_1464], eax
0x18008841f  mov     rdx, r8
0x180088422  jmp     short loc_180088428
0x180088424  mov     rcx, [rcx+10h]
0x180088428  cmp     [rcx+19h], r12b
0x18008842c  jnz     short loc_18008843E
0x18008842e  mov     eax, [rbp+1400h+var_1440]
0x180088431  cmp     [rcx+1Ch], eax
0x180088434  jb      short loc_180088424
0x180088436  mov     rdx, rcx
0x180088439  mov     rcx, [rcx]
0x18008843c  jmp     short loc_180088428
0x18008843e  cmp     [rdx+19h], r12b
0x180088442  jnz     loc_180088517
0x180088448  mov     ebx, [rbp+1400h+var_1440]
0x18008844b  mov     [rsp+1500h+var_14D0], ebx
0x18008844f  cmp     rdx, r8
0x180088452  jz      loc_180088517
0x180088458  cmp     ebx, [rdx+1Ch]
0x18008845b  jb      loc_180088517
0x180088461  lea     rcx, [r9+r9*2]
0x180088465  mov     rax, [rsp+1500h+var_14A0]
0x18008846a  lea     r14, [rax+rcx*8]
0x18008846e  mov     rcx, [r14]
0x180088471  mov     ecx, [rcx+14h]
0x180088474  mov     edx, ebx
0x180088476  shr     edx, cl
0x180088478  cmp     edx, [r14+8]
0x18008847c  jb      loc_180088761
0x180088482  cmp     edx, [r14+0Ch]
0x180088486  jnb     loc_18008877A
0x18008848c  sub     edx, [r14+8]
0x180088490  mov     rax, [r14+10h]
0x180088494  lea     rax, [rax+rdx*8]
0x180088498  mov     [rsp+1500h+var_14D8], rax
0x18008849d  cmp     [rax], r12
0x1800884a0  jnz     loc_180088787
0x1800884a6  mov     r12, [r14]
0x1800884a9  lea     rcx, [r12+30h]
0x1800884ae  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800884b3  mov     r15, rax
0x1800884b6  mov     rax, [rax+18h]
0x1800884ba  cmp     [r15+10h], rax
0x1800884be  jz      loc_18008861F
0x1800884c4  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800884c8  mov     rbx, [rax]
0x1800884cb  mov     [r15+18h], rax
0x1800884cf  mov     r15, [rsp+1500h+var_14D8]
0x1800884d4  mov     [r15], rbx
0x1800884d7  mov     r8d, [r12+4]; Size
0x1800884dc  xor     edx, edx; Val
0x1800884de  mov     rcx, rbx; void *
0x1800884e1  call    memset_0
0x1800884e6  mov     ebx, [rsp+1500h+var_14D0]
0x1800884ea  mov     rax, [r14]
0x1800884ed  mov     edx, [rax+10h]
0x1800884f0  mov     eax, ebx
0x1800884f2  shr     rax, 6
0x1800884f6  and     rdx, rax
0x1800884f9  mov     r9, [r15]
0x1800884fc  and     ebx, 3Fh
0x1800884ff  mov     r8, rsi
0x180088502  mov     cl, bl
0x180088504  shl     r8, cl
0x180088507  mov     rax, [r9+rdx*8]
0x18008850b  test    r8, rax
0x18008850e  jnz     short loc_180088517
0x180088510  or      rax, r8
0x180088513  mov     [r9+rdx*8], rax
0x180088517  mov     r15d, [rbp+1400h+var_1440]
0x18008851b  mov     [rsp+1500h+var_14D0], r15d
0x180088520  mov     ecx, [r13+14h]
0x180088524  mov     edx, r15d
0x180088527  shr     edx, cl
0x180088529  cmp     edx, [rsp+1500h+var_14B0]
0x18008852d  jb      loc_18008874A
0x180088533  cmp     edx, [rsp+1500h+var_14AC]
0x180088537  jnb     loc_18008876E
0x18008853d  sub     edx, [rsp+1500h+var_14B0]
0x180088541  mov     rax, [rsp+1500h+var_14A8]
0x180088546  lea     r12, [rax+rdx*8]
0x18008854a  cmp     qword ptr [r12], 0
0x18008854f  jnz     short loc_180088584
0x180088551  lea     rcx, [r13+30h]
0x180088555  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x18008855a  mov     r14, rax
0x18008855d  mov     rax, [rax+18h]
0x180088561  cmp     [r14+10h], rax
0x180088565  jz      short loc_1800885D5
0x180088567  add     rax, 0FFFFFFFFFFFFFFF8h
0x18008856b  mov     rbx, [rax]
0x18008856e  mov     [r14+18h], rax
0x180088572  mov     [r12], rbx
0x180088576  mov     r8d, [r13+4]; Size
0x18008857a  xor     edx, edx; Val
0x18008857c  mov     rcx, rbx; void *
0x18008857f  call    memset_0
0x180088584  mov     edx, [r13+10h]
0x180088588  mov     eax, r15d
0x18008858b  shr     rax, 6
0x18008858f  and     rdx, rax
0x180088592  mov     r9, [r12]
0x180088596  and     r15d, 3Fh
0x18008859a  mov     r8, rsi
0x18008859d  mov     cl, r15b
0x1800885a0  shl     r8, cl
0x1800885a3  mov     rax, [r9+rdx*8]
0x1800885a7  test    r8, rax
0x1800885aa  jnz     short loc_1800885B3
0x1800885ac  or      rax, r8
0x1800885af  mov     [r9+rdx*8], rax
0x1800885b3  mov     rbx, [rbp+1400h+var_1478]
0x1800885b7  add     rbx, rsi
0x1800885ba  mov     [rbp+1400h+var_1478], rbx
0x1800885be  cmp     rbx, [rsp+1500h+var_1488]
0x1800885c3  jnb     loc_1800886AB
0x1800885c9  or      r14d, 0FFFFFFFFh
0x1800885cd  xor     r12d, r12d
0x1800885d0  jmp     loc_1800883A4
0x1800885d5  mov     r8d, [r14+8]
0x1800885d9  cmp     r8d, [r13+1Ch]
0x1800885dd  jb      loc_180088668
0x1800885e3  mov     edx, [r13+20h]; Alignment
0x1800885e7  mov     ecx, [r13+1Ch]
0x1800885eb  shl     rcx, 3; Size
0x1800885ef  call    cs:__imp__aligned_malloc
0x1800885f5  mov     rbx, rax
0x1800885f8  mov     [rsp+1500h+var_14C8], rax
0x1800885fd  mov     rcx, [rbp+1408h]; this
0x180088604  test    rax, rax
0x180088607  jnz     loc_180088874
0x18008860d  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180088614  mov     edx, 430h; void *
0x180088619  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18008861f  mov     r8d, [r15+8]
0x180088623  cmp     r8d, [r12+1Ch]
0x180088628  jb      short loc_18008867F
0x18008862a  mov     edx, [r12+20h]; Alignment
0x18008862f  mov     ecx, [r12+1Ch]
0x180088634  shl     rcx, 3; Size
0x180088638  call    cs:__imp__aligned_malloc
0x18008863e  mov     rbx, rax
0x180088641  mov     [rsp+1500h+var_14C8], rax
0x180088646  mov     rcx, [rbp+1408h]; this
0x18008864d  test    rax, rax
0x180088650  jnz     loc_1800888F3
0x180088656  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008865d  mov     edx, 430h; void *
0x180088662  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180088668  mov     rcx, [r14]
0x18008866b  lea     rbx, [rcx+r8*8]
0x18008866f  mov     ecx, [r13+8]
0x180088673  add     ecx, r8d
0x180088676  mov     [r14+8], ecx
0x18008867a  jmp     loc_180088572
0x18008867f  mov     rcx, [r15]
0x180088682  lea     rbx, [rcx+r8*8]
0x180088686  mov     ecx, [r12+8]
0x18008868b  add     ecx, r8d
0x18008868e  mov     [r15+8], ecx
0x180088692  jmp     loc_1800884CF
0x180088697  mov     rcx, rbx
0x18008869a  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x18008869f  mov     [rbx], r13
0x1800886a2  add     rbx, 18h
0x1800886a6  jmp     loc_180088389
0x1800886ab  xor     r12d, r12d
0x1800886ae  mov     r14d, r12d
0x1800886b1  cmp     [rdi+174h], esi
0x1800886b7  jz      short loc_180088703
0x1800886b9  mov     eax, r14d
0x1800886bc  lea     rcx, [rax+rax*2]
0x1800886c0  mov     rax, [rsp+1500h+var_14A0]
0x1800886c5  lea     r12, [rax+rcx*8]
0x1800886c9  mov     r15b, sil
0x1800886cc  mov     rcx, r12
0x1800886cf  call    ?size@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAKAEBU?$dynamic_sparse_bit@_K@@@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(dynamic_sparse_bit<unsigned __int64> const &)
0x1800886d4  cmp     byte ptr [rdi+154h], 0
0x1800886db  lea     rcx, [rdi+170h]
0x1800886e2  jnz     short loc_1800886EB
0x1800886e4  lea     rcx, [rdi+16Ch]
0x1800886eb  cmp     eax, [rcx]
0x1800886ed  jnb     loc_180088ACB
0x1800886f3  add     r14d, esi
0x1800886f6  mov     eax, [rdi+174h]
  ... truncated ...
```

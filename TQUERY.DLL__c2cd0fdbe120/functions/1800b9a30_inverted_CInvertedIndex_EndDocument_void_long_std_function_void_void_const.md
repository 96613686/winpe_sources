# inverted::CInvertedIndex::EndDocument(void *,long,std::function<void (void)> const &)

- ea: `0x1800b9a30`
- end: `0x1800ba8a4`
- name: `?EndDocument@CInvertedIndex@inverted@@UEAAXPEAXJAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `3700`
- prototype: `__int64 __fastcall(inverted::CInvertedIndex *this, inverted::SIndexingDocument *)`
- caller_count: `0`
- callee_count: `50`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002a3e0`
- `0x18002be24`
- `0x18002f284`
- `0x18002f6e0`
- `0x180030230`
- `0x1800302f4`
- `0x180030a84`
- `0x1800324c8`
- `0x180036d60`
- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x180050c58`
- `0x18005166c`
- `0x1800516b8`
- `0x180076e30`
- `0x1800791ac`
- `0x1800791d8`
- `0x180087674`
- `0x180088214`
- `0x180088bc8`
- `0x18008904c`
- `0x180089458`
- `0x1800ae484`
- `0x1800b8c2c`
- `0x1800b9034`
- `0x1800b9064`
- `0x1800b9a30`
- `0x1800ba918`
- `0x1800ba944`
- `0x1800ba9a0`
- `0x1800baac4`
- `0x1800babc8`
- `0x1800bac7c`
- `0x1800bacbc`
- `0x1800bad24`
- `0x1800bad80`
- `0x1800e40a4`
- `0x1800e9920`
- `0x1801183f0`
- `0x18013d1e4`
- `0x18013e868`
- `0x1801470d4`
- `0x180147190`
- `0x18015708c`
- `0x180170000`
- `0x180188dc0`
- `0x180189cce`
- `0x180217258`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9c5b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9f7a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba403`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9c5b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9f7a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba403`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9bbe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9eda`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800ba36b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9bbe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9eda`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800ba36b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ba87e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ba87e`
- `cryptdll!MD5Final` at `0x1800ba196`
- `cryptdll!MD5Final` at `0x1800ba196`

## string_xrefs

- `0x1800b9bd9`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800b9ef5`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800ba386`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800ba699`: `Partial Item Update Commited - Updated PIDs:`
- `0x1800b9db5`: `PID deleted by omission: %d`
- `0x1800ba1e2`: `MD5 Unchanged - Not commiting the following properties:`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall inverted::CInvertedIndex::EndDocument(
        inverted::CInvertedIndex *this,
        inverted::SIndexingDocument *a2,
        int a3,
        __int64 a4)
{
  int v4; // r15d
  bool v7; // di
  RTL_SRWLOCK *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  struct inverted::PROPERTYVALUE *OldProp; // rax
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  char *v15; // r15
  unsigned int v16; // edi
  unsigned int v17; // edx
  _QWORD *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  void *v24; // rdi
  const char *v25; // r9
  _QWORD *v26; // rax
  _QWORD *v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rax
  int *j; // rdi
  unsigned __int16 *v33; // rbx
  __int64 v34; // rdx
  unsigned int v35; // eax
  unsigned int v36; // ecx
  __int64 v37; // r9
  __int64 v38; // rax
  inverted::PROPERTYVALUE *v39; // rcx
  unsigned int **v40; // r8
  unsigned int v41; // ebx
  unsigned int v42; // edx
  unsigned __int16 **v43; // rax
  unsigned int *v44; // rbx
  __int64 v45; // r15
  __int64 v46; // rax
  __int64 v47; // rdx
  unsigned __int16 *v48; // rbx
  const char *v49; // r9
  _QWORD *v50; // rax
  unsigned __int16 **v51; // rdx
  unsigned __int64 v52; // rdx
  void **v53; // rax
  unsigned __int16 **v54; // r15
  unsigned __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rax
  unsigned __int16 *v58; // rbx
  __int64 v59; // rdx
  char *v60; // rax
  inverted::PROPERTYVALUE *v61; // rcx
  unsigned int BitGE; // ebx
  __int64 v63; // rdx
  char *v64; // r15
  unsigned int v65; // edx
  unsigned __int16 **v66; // rax
  __int64 v67; // rdi
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rcx
  __int64 v71; // r8
  unsigned __int16 *v72; // rdi
  __int64 v73; // rdx
  unsigned __int16 *v74; // rax
  const char *v75; // r9
  unsigned __int16 **v76; // rdx
  unsigned __int64 v77; // rcx
  unsigned __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  unsigned __int64 v81; // r8
  __int64 v82; // r9
  unsigned __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  unsigned int k; // ebx
  __int64 v87; // rcx
  int v88; // eax
  int *v89; // rbx
  char *v90; // rdx
  int v91; // ecx
  __int64 v92; // rbx
  __int64 v93; // rax
  unsigned int v94; // [rsp+30h] [rbp-E8h]
  unsigned int v95; // [rsp+30h] [rbp-E8h]
  unsigned int v96; // [rsp+30h] [rbp-E8h]
  unsigned int *v97; // [rsp+38h] [rbp-E0h]
  unsigned __int16 **v98; // [rsp+38h] [rbp-E0h]
  unsigned int v99; // [rsp+38h] [rbp-E0h]
  unsigned __int16 **v100; // [rsp+38h] [rbp-E0h]
  _QWORD *v101; // [rsp+40h] [rbp-D8h]
  unsigned int *v102; // [rsp+40h] [rbp-D8h]
  __int64 v103; // [rsp+40h] [rbp-D8h]
  unsigned __int16 *v104; // [rsp+48h] [rbp-D0h] BYREF
  char *v105; // [rsp+50h] [rbp-C8h]
  char *v106; // [rsp+58h] [rbp-C0h]
  unsigned __int16 *i; // [rsp+60h] [rbp-B8h] BYREF
  std::_Ref_count_base *v108; // [rsp+68h] [rbp-B0h]
  void *v109; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int v110; // [rsp+78h] [rbp-A0h]
  int v111; // [rsp+80h] [rbp-98h] BYREF
  __int64 v112; // [rsp+88h] [rbp-90h]
  __int64 v113; // [rsp+90h] [rbp-88h]
  std::_Ref_count_base *v114[2]; // [rsp+98h] [rbp-80h] BYREF
  __int64 v115; // [rsp+A8h] [rbp-70h] BYREF
  int v116; // [rsp+B0h] [rbp-68h] BYREF
  char *v117; // [rsp+B8h] [rbp-60h]
  __int64 v118; // [rsp+C0h] [rbp-58h]
  std::_Ref_count_base *v119[2]; // [rsp+C8h] [rbp-50h]
  char *v120; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  __int64 v123; // [rsp+128h] [rbp+10h] BYREF
  int v124; // [rsp+130h] [rbp+18h]
  __int64 v125; // [rsp+138h] [rbp+20h]

  v125 = a4;
  v124 = a3;
  v4 = a3;
  v7 = 0;
  LOBYTE(v123) = 0;
  v8 = (RTL_SRWLOCK *)((char *)this + 680);
  v120 = (char *)this + 680;
  CSRWLock::AcquireExclusive((inverted::CInvertedIndex *)((char *)this + 680));
  inverted::CInvertedIndex::_ThrowIfShutdown(this);
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<inverted::SIndexingDocument>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<inverted::SIndexingDocument>>>,0>>::find(
    (char *)this + 824,
    &v115,
    a2);
  if ( v115 == *((_QWORD *)this + 103) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11);
  try
  {
    if ( v4 < 0 )
      goto LABEL_175;
    if ( *((_DWORD *)a2 + 2) == 2 )
    {
      OldProp = inverted::SIndexingDocument::FindOldProp(a2, *((_DWORD *)this + 83));
      if ( OldProp )
      {
        v13 = (unsigned __int16 *)*((_QWORD *)OldProp + 1);
        v14 = &v13[*((_QWORD *)OldProp + 2) >> 1];
        for ( i = v14; ; v14 = i )
        {
          v104 = v13;
          if ( v13 >= v14 )
            break;
          if ( (*((_BYTE *)a2 + 12) & 1) == 0 )
            inverted::SIndexingDocument::SetPropSeen(a2, *v13, 1);
          v15 = (char *)a2 + 312;
          v16 = *v13;
          v94 = v16;
          v17 = v16 >> *(_DWORD *)(*((_QWORD *)a2 + 39) + 20LL);
          if ( v17 < *((_DWORD *)a2 + 80) )
          {
            v18 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 312);
            v101 = v18;
          }
          else
          {
            if ( v17 >= *((_DWORD *)a2 + 81) )
              v18 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 312);
            else
              v18 = (_QWORD *)(*((_QWORD *)a2 + 41) + 8LL * (v17 - *((_DWORD *)a2 + 80)));
            v101 = v18;
          }
          if ( !*v18 )
          {
            v19 = *(_QWORD *)v15;
            v97 = *(unsigned int **)v15;
            v20 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v15 + 48LL);
            v21 = v20;
            v22 = *(_QWORD *)(v20 + 24);
            if ( *(_QWORD *)(v20 + 16) == v22 )
            {
              v23 = *(unsigned int *)(v20 + 8);
              if ( (unsigned int)v23 >= *(_DWORD *)(v19 + 28) )
              {
                v24 = _aligned_malloc(8LL * *(unsigned int *)(v19 + 28), *(unsigned int *)(v19 + 32));
                v109 = v24;
                if ( !v24 )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x430,
                    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                    v25);
                v26 = (_QWORD *)(v21 + 40);
                v27 = *(_QWORD **)(v21 + 48);
                if ( v27 == *(_QWORD **)(v21 + 56) )
                {
                  std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                    v26,
                    v27,
                    &v109);
                  v24 = v109;
                  v26 = (_QWORD *)(v21 + 40);
                }
                else
                {
                  *v27 = v24;
                  *(_QWORD *)(v21 + 48) += 8LL;
                }
                v28 = v97[6] * ((__int64)(v26[1] - *v26) >> 3);
                v109 = (void *)v28;
                if ( v28 > (__int64)(*(_QWORD *)(v21 + 32) - *(_QWORD *)(v21 + 16)) >> 3 )
                {
                  if ( v28 > 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector too long");
                  std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v21 + 16, &v109);
                }
                *(_QWORD *)v21 = v24;
                *(_DWORD *)(v21 + 8) = v97[2];
              }
              else
              {
                v24 = (void *)(*(_QWORD *)v20 + 8 * v23);
                *(_DWORD *)(v20 + 8) = v23 + v97[2];
              }
            }
            else
            {
              v24 = *(void **)(v22 - 8);
              *(_QWORD *)(v20 + 24) = v22 - 8;
            }
            *v101 = v24;
            memset_0(v24, 0, v97[1]);
            v13 = v104;
            v16 = v94;
          }
          v29 = *(unsigned int *)(*(_QWORD *)v15 + 16LL) & ((unsigned __int64)v16 >> 6);
          v30 = 1LL << (v16 & 0x3F);
          v31 = *(_QWORD *)(*v101 + 8 * v29);
          if ( (v31 & v30) == 0 )
            *(_QWORD *)(*v101 + 8 * v29) = v30 | v31;
          ++v13;
        }
      }
      for ( j = (int *)*((_QWORD *)a2 + 2); ; j += 10 )
      {
        if ( j == *((int **)a2 + 3) )
          goto LABEL_75;
        if ( *j != (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30)) )
        {
          std::_Tree<std::_Tmap_traits<unsigned int,unsigned short,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned short>>,0>>::find(
            (char *)this + 760,
            &i,
            j);
          v33 = i;
          if ( i != *((unsigned __int16 **)this + 95) )
          {
            v34 = *((_QWORD *)a2 + 36);
            v35 = i[16] >> *(_DWORD *)(v34 + 20);
            v36 = *((_DWORD *)a2 + 74);
            if ( v35 < v36
              || v35 >= *((_DWORD *)a2 + 75)
              || (v37 = *(_QWORD *)(*((_QWORD *)a2 + 38) + 8LL * (v35 - v36))) == 0
              || (v38 = *(_QWORD *)(v37 + 8 * (((unsigned __int64)i[16] >> 6) & *(unsigned int *)(v34 + 16))),
                  !_bittest64(&v38, i[16] & 0x3F)) )
            {
              if ( (*((_BYTE *)a2 + 12) & 1) == 0 )
                break;
            }
          }
        }
LABEL_74:
        ;
      }
      ETWLog::Log(L"PID deleted by omission: %d", i[16]);
      v112 = 0;
      v113 = 0;
      *(_OWORD *)v114 = 0;
      v111 = *j;
      v39 = (inverted::PROPERTYVALUE *)*((_QWORD *)a2 + 6);
      if ( v39 == *((inverted::PROPERTYVALUE **)a2 + 7) )
      {
        std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(
          (char *)a2 + 40,
          *((_QWORD *)a2 + 6),
          &v111);
      }
      else
      {
        inverted::PROPERTYVALUE::PROPERTYVALUE(v39, (const struct inverted::PROPERTYVALUE *)&v111);
        *((_QWORD *)a2 + 6) += 40LL;
      }
      v40 = (unsigned int **)((char *)a2 + 264);
      v41 = v33[16];
      v95 = v41;
      v42 = v41 >> *(_DWORD *)(*((_QWORD *)a2 + 33) + 20LL);
      if ( v42 < *((_DWORD *)a2 + 68) )
      {
        v43 = (unsigned __int16 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 264);
        v98 = v43;
      }
      else
      {
        if ( v42 < *((_DWORD *)a2 + 69) )
        {
          v43 = (unsigned __int16 **)(*((_QWORD *)a2 + 35) + 8LL * (v42 - *((_DWORD *)a2 + 68)));
          v98 = v43;
LABEL_53:
          if ( *v43 )
          {
            v54 = v98;
          }
          else
          {
            v44 = *v40;
            v102 = *v40;
            v45 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*v40 + 12);
            v46 = *(_QWORD *)(v45 + 24);
            if ( *(_QWORD *)(v45 + 16) == v46 )
            {
              v47 = *(unsigned int *)(v45 + 8);
              if ( (unsigned int)v47 >= v44[7] )
              {
                v48 = (unsigned __int16 *)_aligned_malloc(8LL * v44[7], v44[8]);
                v104 = v48;
                if ( !v48 )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x430,
                    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                    v49);
                v50 = (_QWORD *)(v45 + 40);
                v51 = *(unsigned __int16 ***)(v45 + 48);
                if ( v51 == *(unsigned __int16 ***)(v45 + 56) )
                {
                  std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                    v50,
                    v51,
                    &v104);
                  v48 = v104;
                  v50 = (_QWORD *)(v45 + 40);
                }
                else
                {
                  *v51 = v48;
                  *(_QWORD *)(v45 + 48) += 8LL;
                }
                v52 = v102[6] * ((__int64)(v50[1] - *v50) >> 3);
                v104 = (unsigned __int16 *)v52;
                if ( v52 > (__int64)(*(_QWORD *)(v45 + 32) - *(_QWORD *)(v45 + 16)) >> 3 )
                {
                  if ( v52 > 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector too long");
                  std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v45 + 16, &v104);
                }
                *(_QWORD *)v45 = v48;
                *(_DWORD *)(v45 + 8) = v102[2];
              }
              else
              {
                v48 = (unsigned __int16 *)(*(_QWORD *)v45 + 8 * v47);
                *(_DWORD *)(v45 + 8) = v47 + v102[2];
              }
            }
            else
            {
              v53 = (void **)(v46 - 8);
              v48 = (unsigned __int16 *)*v53;
              *(_QWORD *)(v45 + 24) = v53;
            }
            v54 = v98;
            *v98 = v48;
            memset_0(v48, 0, v102[1]);
            v41 = v95;
          }
          v55 = *(unsigned int *)(*((_QWORD *)a2 + 33) + 16LL) & ((unsigned __int64)v41 >> 6);
          v56 = 1LL << (v41 & 0x3F);
          v57 = *(_QWORD *)&(*v54)[4 * v55];
          if ( (v57 & v56) == 0 )
            *(_QWORD *)&(*v54)[4 * v55] = v56 | v57;
          if ( v114[1] )
            std::_Ref_count_base::_Decref(v114[1]);
          goto LABEL_74;
        }
        v43 = (unsigned __int16 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 264);
        v98 = v43;
      }
      v40 = (unsigned int **)((char *)a2 + 264);
      goto LABEL_53;
    }
LABEL_75:
    v112 = 0;
    v113 = 0;
    *(_OWORD *)v114 = 0;
    v99 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size((char *)a2 + 312);
    v111 = *((_DWORD *)this + 83);
    v58 = (unsigned __int16 *)operator new(0x20u);
    i = v58;
    *((_DWORD *)v58 + 2) = 1;
    *((_DWORD *)v58 + 3) = 1;
    *(_QWORD *)v58 = &std::_Ref_count_obj2<inverted::CBuffer>::`vftable';
    inverted::CBuffer::CBuffer((inverted::CBuffer *)(v58 + 8), 2 * v99);
    i = v58 + 8;
    v108 = (std::_Ref_count_base *)v58;
    std::shared_ptr<inverted::ICatalogStorage>::operator=(v114, &i);
    if ( v108 )
      std::_Ref_count_base::_Decref(v108);
    v112 = *(_QWORD *)v114[0];
    v113 = 2LL * v99;
    dynamic_sparse_bit<unsigned __int64>::CopyTo<unsigned short *>((char *)a2 + 312, v59, v112, v113 + v112);
    if ( *((_DWORD *)a2 + 2) != 2
      || !inverted::SIndexingDocument::IdenticalOldPropExists(a2, (const struct inverted::PROPERTYVALUE *)&v111) )
    {
      std::vector<inverted::PROPERTYVALUE>::push_back((char *)a2 + 40, &v111);
    }
    v116 = -1;
    v117 = 0;
    v118 = 0;
    *(_OWORD *)v119 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateCryptoAPIs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdateCryptoAPIs>::GetImpl'::`2'::impl) )
    {
      CngRsa32Compat_MD5Final((char *)a2 + 440);
      v116 = *((_DWORD *)this + 84);
      v60 = (char *)a2 + 448;
    }
    else
    {
      MD5Final((char *)a2 + 336);
      v116 = *((_DWORD *)this + 84);
      v60 = (char *)a2 + 424;
    }
    v118 = 16;
    v117 = v60;
    if ( *((_DWORD *)a2 + 2) == 2
      && inverted::SIndexingDocument::IdenticalOldPropExists(a2, (const struct inverted::PROPERTYVALUE *)&v116) )
    {
      ETWLog::Log(L"MD5 Unchanged - Not commiting the following properties:");
      inverted::LogBitVector(L"pids", (char *)a2 + 312);
      dynamic_sparse_bit<unsigned __int64>::Difference((char *)a2 + 264, (char *)a2 + 312);
    }
    else
    {
      v61 = (inverted::PROPERTYVALUE *)*((_QWORD *)a2 + 6);
      if ( v61 == *((inverted::PROPERTYVALUE **)a2 + 7) )
      {
        std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(
          (char *)a2 + 40,
          *((_QWORD *)a2 + 6),
          &v116);
      }
      else
      {
        inverted::PROPERTYVALUE::PROPERTYVALUE(v61, (const struct inverted::PROPERTYVALUE *)&v116);
        *((_QWORD *)a2 + 6) += 40LL;
      }
    }
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_129;
    dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &v109);
    BitGE = v110;
    v96 = v110;
    while ( BitGE != -1 )
    {
      v63 = *((_QWORD *)this + 89);
      if ( BitGE >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 90) - v63) >> 2)
        || (*(_BYTE *)(v63 + 12LL * BitGE + 2) & 1) != 0
        || inverted::CInvertedIndex::_HasValueIndexForProperty(this, BitGE) )
      {
        goto LABEL_120;
      }
      v64 = (char *)a2 + 264;
      v65 = BitGE >> *(_DWORD *)(*((_QWORD *)a2 + 33) + 20LL);
      if ( v65 < *((_DWORD *)a2 + 68) )
      {
        v66 = (unsigned __int16 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 264);
        v100 = v66;
      }
      else
      {
        if ( v65 >= *((_DWORD *)a2 + 69) )
          v66 = (unsigned __int16 **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 264);
        else
          v66 = (unsigned __int16 **)(*((_QWORD *)a2 + 35) + 8LL * (v65 - *((_DWORD *)a2 + 68)));
        v100 = v66;
      }
      if ( !*v66 )
      {
        v67 = *(_QWORD *)v64;
        v103 = *(_QWORD *)v64;
        v68 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v64 + 48LL);
        v69 = v68;
        v70 = *(_QWORD *)(v68 + 24);
        if ( *(_QWORD *)(v68 + 16) == v70 )
        {
          v71 = *(unsigned int *)(v68 + 8);
          if ( (unsigned int)v71 < *(_DWORD *)(v67 + 28) )
          {
            v72 = (unsigned __int16 *)(*(_QWORD *)v68 + 8 * v71);
            v73 = v103;
            *(_DWORD *)(v68 + 8) = v71 + *(_DWORD *)(v103 + 8);
LABEL_117:
            *v100 = v72;
            memset_0(v72, 0, *(unsigned int *)(v73 + 4));
            BitGE = v96;
            goto LABEL_118;
          }
          v74 = (unsigned __int16 *)_aligned_malloc(8LL * *(unsigned int *)(v67 + 28), *(unsigned int *)(v67 + 32));
          v72 = v74;
          v104 = v74;
          if ( !v74 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v75);
          v76 = *(unsigned __int16 ***)(v69 + 48);
          if ( v76 == *(unsigned __int16 ***)(v69 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v69 + 40,
              v76,
              &v104);
            v72 = v104;
          }
          else
          {
            *v76 = v74;
            *(_QWORD *)(v69 + 48) += 8LL;
          }
          v77 = *(unsigned int *)(v103 + 24) * ((__int64)(*(_QWORD *)(v69 + 48) - *(_QWORD *)(v69 + 40)) >> 3);
          i = (unsigned __int16 *)v77;
          if ( v77 > (__int64)(*(_QWORD *)(v69 + 32) - *(_QWORD *)(v69 + 16)) >> 3 )
          {
            if ( v77 > 0x1FFFFFFFFFFFFFFFLL )
              std::_Xlength_error("vector too long");
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v69 + 16, &i);
          }
          *(_QWORD *)v69 = v72;
          *(_DWORD *)(v69 + 8) = *(_DWORD *)(v103 + 8);
          v64 = (char *)a2 + 264;
        }
        else
        {
          v72 = *(unsigned __int16 **)(v70 - 8);
          *(_QWORD *)(v68 + 24) = v70 - 8;
        }
        v73 = v103;
        goto LABEL_117;
      }
LABEL_118:
      v78 = *(unsigned int *)(*(_QWORD *)v64 + 16LL) & ((unsigned __int64)BitGE >> 6);
      v79 = *(_QWORD *)&(*v100)[4 * v78];
      if ( (v79 & (1LL << BitGE)) != 0 )
        *(_QWORD *)&(*v100)[4 * v78] = (1LL << BitGE) ^ v79;
LABEL_120:
      BitGE = dynamic_sparse_bit<unsigned __int64>::NextBitGE(v109, BitGE + 1);
      v96 = BitGE;
    }
    dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &i);
    while ( 1 )
    {
      if ( (_DWORD)v108 == -1 )
      {
        dynamic_sparse_bit<unsigned __int64>::Empty((char *)a2 + 264);
        std::vector<inverted::PROPERTYVALUE>::clear((char *)a2 + 40);
        goto LABEL_129;
      }
      v81 = inverted::CInvertedIndex::_PidIndexToProperty(this, (unsigned __int16)v108);
      v82 = *((_QWORD *)this + 89);
      v83 = 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 90) - v82) >> 2);
      if ( v81 >= v83 )
        break;
      v83 = 256;
      if ( (*(_WORD *)(v82 + 12 * v81 + 2) & 0x100) == 0 )
        break;
      _sparse_bit_iterator<dynamic_sparse_bit<unsigned __int64>>::operator++(&i, &v104);
    }
    if ( (unsigned __int16)v81 >= 0x4000u )
      MicrosoftTelemetryAssertTriggeredNoArgs(v83, v80, v81);
LABEL_129:
    v84 = *((_QWORD *)a2 + 5);
    v85 = *((_QWORD *)a2 + 6);
    if ( v84 != v85 )
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int64))(**((_QWORD **)this + 30) + 88LL))(
        *((_QWORD *)this + 30),
        *(unsigned int *)a2,
        v84,
        0xCCCCCCCCCCCCCCCDuLL * ((v85 - v84) >> 3));
    if ( *((_DWORD *)a2 + 2) != 2
      || (unsigned __int8)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::HasAtLeast((char *)a2 + 264, 1) )
    {
      std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v104);
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &i);
        for ( k = (unsigned int)v108; k != -1; k = dynamic_sparse_bit<unsigned __int64>::NextBitGE(i, k + 1) )
        {
          v87 = *((_QWORD *)a2 + 58);
          if ( k < (unsigned __int64)((*((_QWORD *)a2 + 59) - v87) >> 2) )
          {
            v88 = *(_DWORD *)(v87 + 4LL * k);
            if ( v88 )
            {
              LOWORD(v123) = k;
              HIDWORD(v123) = v88;
              if ( v105 == v106 )
              {
                std::vector<std::pair<unsigned int,unsigned int>>::_Emplace_reallocate<std::pair<unsigned int,unsigned int>>(
                  &v104,
                  v105,
                  &v123);
              }
              else
              {
                *(_QWORD *)v105 = v123;
                v105 += 8;
              }
            }
          }
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, char *, signed __int64, unsigned __int16 *))(***((_QWORD ***)this + 99)
                                                                                           + 64LL))(
          **((_QWORD **)this + 99),
          *((unsigned int *)a2 + 1),
          (char *)a2 + 264,
          (v105 - (char *)v104) >> 3,
          v104);
        ++*((_DWORD *)this + 104);
        ETWLog::Log(L"Partial Item Update Commited - Updated PIDs:");
        inverted::LogBitVector(L"pids", (char *)a2 + 312);
      }
      else
      {
        v89 = (int *)*((_QWORD *)a2 + 58);
        v90 = v105;
        while ( v89 != *((int **)a2 + 59) )
        {
          v91 = *v89;
          if ( *v89 )
          {
            LOWORD(v123) = (__int64)(unsigned int)((_DWORD)v89 - *((_DWORD *)a2 + 116)) >> 2;
            HIDWORD(v123) = v91;
            if ( v90 == v106 )
            {
              std::vector<std::pair<unsigned int,unsigned int>>::_Emplace_reallocate<std::pair<unsigned int,unsigned int>>(
                &v104,
                v90,
                &v123);
              v90 = v105;
            }
            else
            {
              *(_QWORD *)v90 = v123;
              v90 = v105 + 8;
              v105 += 8;
            }
          }
          ++v89;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, signed __int64))(***((_QWORD ***)this + 99) + 72LL))(
          **((_QWORD **)this + 99),
          *((unsigned int *)a2 + 1),
          (v90 - (char *)v104) >> 3);
        ++*((_DWORD *)this + 106);
      }
      v92 = *((_QWORD *)this + 99);
      if ( *(_QWORD *)(v92 + 24) == *(_QWORD *)(v92 + 32) )
      {
        std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)> const &>(
          v92 + 16,
          *(_QWORD *)(v92 + 24),
          v125);
      }
      else
      {
        std::function<void (void)>::function<void (void)>(*(_QWORD *)(v92 + 24), v125);
        *(_QWORD *)(v92 + 24) += 64LL;
      }
      std::shared_ptr<inverted::IInvertedIndex>::reset((char *)this + 888);
      v7 = *(_QWORD *)(*((_QWORD *)this + 99) + 24LL) - *(_QWORD *)(*((_QWORD *)this + 99) + 16LL) == 64;
      if ( v104 )
        std::_Deallocate<16>(v104, (v106 - (char *)v104) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      ++*((_DWORD *)this + 105);
      std::_Func_class<void,>::operator()(v125);
      v7 = v123;
    }
    if ( v119[1] )
      std::_Ref_count_base::_Decref(v119[1]);
    if ( v114[1] )
      std::_Ref_count_base::_Decref(v114[1]);
    v4 = v124;
  }
  catch ( ... )
  {
    inverted::CInvertedIndex::_EndDocument(this, v115);
    throw;
  }
LABEL_175:
  ((void (*)(void))inverted::CInvertedIndex::_EndDocument)();
  if ( v4 < 0
    && !*((_QWORD *)this + 104)
    && !(*(unsigned int (__fastcall **)(_QWORD))(***((_QWORD ***)this + 99) + 16LL))(**((_QWORD **)this + 99)) )
  {
    v93 = std::make_shared<inverted::SWordListData,>(&i);
    std::shared_ptr<inverted::ICatalogStorage>::operator=((char *)this + 792, v93);
    if ( v108 )
      std::_Ref_count_base::_Decref(v108);
  }
  inverted::CInvertedIndex::_CheckWordList(this, 0);
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  if ( v7 )
    inverted::CInvertedIndex::_SendStatsChangeNoLock(this);
}

```

## disassembly

```asm
0x1800b9a30  mov     rax, rsp
0x1800b9a33  mov     [rax+20h], r9
0x1800b9a37  mov     [rax+18h], r8d
0x1800b9a3b  mov     [rax+8], rcx
0x1800b9a3f  push    rbx
0x1800b9a40  push    rsi
0x1800b9a41  push    rdi
0x1800b9a42  push    r12
0x1800b9a44  push    r13
0x1800b9a46  push    r14
0x1800b9a48  push    r15
0x1800b9a4a  sub     rsp, 0E0h
0x1800b9a51  mov     r15d, r8d
0x1800b9a54  mov     r12, rdx
0x1800b9a57  mov     r13, rcx
0x1800b9a5a  xor     dil, dil
0x1800b9a5d  mov     byte ptr [rsp+118h+arg_8], dil
0x1800b9a65  lea     rsi, [rcx+2A8h]
0x1800b9a6c  mov     [rax-40h], rsi
0x1800b9a70  mov     rcx, rsi; this
0x1800b9a73  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x1800b9a78  nop
0x1800b9a79  mov     rcx, r13; this
0x1800b9a7c  call    ?_ThrowIfShutdown@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_ThrowIfShutdown(void)
0x1800b9a81  lea     rbx, [r13+338h]
0x1800b9a88  mov     r8, r12
0x1800b9a8b  lea     rdx, [rsp+118h+var_70]
0x1800b9a93  mov     rcx, rbx
0x1800b9a96  call    ?find@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@USIndexingDocument@inverted@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@USIndexingDocument@inverted@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@USIndexingDocument@inverted@@@std@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<inverted::SIndexingDocument>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<inverted::SIndexingDocument>>>,0>>::find(uint const &)
0x1800b9a9b  mov     r14, [rsp+118h+var_70]
0x1800b9aa3  cmp     r14, [rbx]
0x1800b9aa6  jnz     short loc_1800B9AAE
0x1800b9aa8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b9aad  nop
0x1800b9aae  test    r15d, r15d
0x1800b9ab1  js      loc_1800BA810
0x1800b9ab7  cmp     dword ptr [r12+8], 2
0x1800b9abd  jnz     loc_1800BA01C
0x1800b9ac3  mov     edx, [r13+14Ch]; unsigned int
0x1800b9aca  mov     rcx, r12; this
0x1800b9acd  call    ?FindOldProp@SIndexingDocument@inverted@@QEAAPEAUPROPERTYVALUE@2@I@Z; inverted::SIndexingDocument::FindOldProp(uint)
0x1800b9ad2  test    rax, rax
0x1800b9ad5  jz      loc_1800B9CF2
0x1800b9adb  mov     rbx, [rax+8]
0x1800b9adf  mov     rax, [rax+10h]
0x1800b9ae3  shr     rax, 1
0x1800b9ae6  lea     rax, [rbx+rax*2]
0x1800b9aea  mov     [rsp+118h+var_B8], rax
0x1800b9aef  mov     [rsp+118h+var_D0], rbx
0x1800b9af4  cmp     rbx, rax
0x1800b9af7  jnb     loc_1800B9CF2
0x1800b9afd  test    byte ptr [r12+0Ch], 1
0x1800b9b03  jnz     short loc_1800B9B13
0x1800b9b05  mov     r8b, 1; bool
0x1800b9b08  movzx   edx, word ptr [rbx]; unsigned __int16
0x1800b9b0b  mov     rcx, r12; this
0x1800b9b0e  call    ?SetPropSeen@SIndexingDocument@inverted@@QEAAXG_N@Z; inverted::SIndexingDocument::SetPropSeen(ushort,bool)
0x1800b9b13  lea     r15, [r12+138h]
0x1800b9b1b  movzx   edi, word ptr [rbx]
0x1800b9b1e  mov     [rsp+118h+var_E8], edi
0x1800b9b22  mov     rcx, [r15]
0x1800b9b25  mov     ecx, [rcx+14h]
0x1800b9b28  mov     edx, edi
0x1800b9b2a  shr     edx, cl
0x1800b9b2c  cmp     edx, [r15+8]
0x1800b9b30  jb      short loc_1800B9B5A
0x1800b9b32  cmp     edx, [r15+0Ch]
0x1800b9b36  jnb     short loc_1800B9B4B
0x1800b9b38  sub     edx, [r15+8]
0x1800b9b3c  mov     rax, [r15+10h]
0x1800b9b40  lea     rax, [rax+rdx*8]
0x1800b9b44  mov     [rsp+118h+var_D8], rax
0x1800b9b49  jmp     short loc_1800B9B67
0x1800b9b4b  mov     rcx, r15
0x1800b9b4e  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9b53  mov     [rsp+118h+var_D8], rax
0x1800b9b58  jmp     short loc_1800B9B67
0x1800b9b5a  mov     rcx, r15
0x1800b9b5d  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9b62  mov     [rsp+118h+var_D8], rax
0x1800b9b67  cmp     qword ptr [rax], 0
0x1800b9b6b  jnz     loc_1800B9CAE
0x1800b9b71  mov     rdi, [r15]
0x1800b9b74  mov     [rsp+118h+var_E0], rdi
0x1800b9b79  lea     rcx, [rdi+30h]
0x1800b9b7d  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b9b82  mov     rbx, rax
0x1800b9b85  mov     rcx, [rax+18h]
0x1800b9b89  cmp     [rax+10h], rcx
0x1800b9b8d  jnz     loc_1800B9C7F
0x1800b9b93  mov     edx, [rax+8]
0x1800b9b96  cmp     edx, [rdi+1Ch]
0x1800b9b99  jnb     short loc_1800B9BB4
0x1800b9b9b  mov     rax, [rax]
0x1800b9b9e  lea     rdi, [rax+rdx*8]
0x1800b9ba2  mov     rax, [rsp+118h+var_E0]
0x1800b9ba7  mov     ecx, [rax+8]
0x1800b9baa  add     ecx, edx
0x1800b9bac  mov     [rbx+8], ecx
0x1800b9baf  jmp     loc_1800B9C8A
0x1800b9bb4  mov     edx, [rdi+20h]; Alignment
0x1800b9bb7  mov     ecx, [rdi+1Ch]
0x1800b9bba  shl     rcx, 3; Size
0x1800b9bbe  call    cs:__imp__aligned_malloc
0x1800b9bc4  mov     rdi, rax
0x1800b9bc7  mov     [rsp+118h+var_A8], rax
0x1800b9bcc  mov     rcx, [rsp+118h]; this
0x1800b9bd4  test    rax, rax
0x1800b9bd7  jnz     short loc_1800B9BEA
0x1800b9bd9  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b9be0  mov     edx, 430h; void *
0x1800b9be5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b9bea  lea     rax, [rbx+28h]
0x1800b9bee  mov     rdx, [rax+8]
0x1800b9bf2  cmp     rdx, [rax+10h]
0x1800b9bf6  jz      short loc_1800B9C02
0x1800b9bf8  mov     [rdx], rdi
0x1800b9bfb  add     qword ptr [rax+8], 8
0x1800b9c00  jmp     short loc_1800B9C18
0x1800b9c02  lea     r8, [rsp+118h+var_A8]
0x1800b9c07  mov     rcx, rax
0x1800b9c0a  call    ??$_Emplace_reallocate@U?$pair@KK@std@@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAPEAU?$pair@KK@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<ulong,ulong>>::_Emplace_reallocate<std::pair<ulong,ulong>>(std::pair<ulong,ulong> * const,std::pair<ulong,ulong> &&)
0x1800b9c0f  mov     rdi, [rsp+118h+var_A8]
0x1800b9c14  lea     rax, [rbx+28h]
0x1800b9c18  mov     rcx, [rax+8]
0x1800b9c1c  sub     rcx, [rax]
0x1800b9c1f  sar     rcx, 3
0x1800b9c23  mov     rax, [rsp+118h+var_E0]
0x1800b9c28  mov     eax, [rax+18h]
0x1800b9c2b  imul    rcx, rax
0x1800b9c2f  mov     [rsp+118h+var_A8], rcx
0x1800b9c34  mov     rax, [rbx+20h]
0x1800b9c38  sub     rax, [rbx+10h]
0x1800b9c3c  sar     rax, 3
0x1800b9c40  cmp     rcx, rax
0x1800b9c43  jbe     short loc_1800B9C6F
0x1800b9c45  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800b9c4f  cmp     rcx, rax
0x1800b9c52  jbe     short loc_1800B9C61
0x1800b9c54  lea     rcx, aVectorTooLong; "vector too long"
0x1800b9c5b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b9c61  lea     rdx, [rsp+118h+var_A8]
0x1800b9c66  lea     rcx, [rbx+10h]
0x1800b9c6a  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800b9c6f  mov     [rbx], rdi
0x1800b9c72  mov     rax, [rsp+118h+var_E0]
0x1800b9c77  mov     eax, [rax+8]
0x1800b9c7a  mov     [rbx+8], eax
0x1800b9c7d  jmp     short loc_1800B9C8A
0x1800b9c7f  lea     rax, [rcx-8]
0x1800b9c83  mov     rdi, [rax]
0x1800b9c86  mov     [rbx+18h], rax
0x1800b9c8a  mov     rax, [rsp+118h+var_D8]
0x1800b9c8f  mov     [rax], rdi
0x1800b9c92  mov     rax, [rsp+118h+var_E0]
0x1800b9c97  mov     r8d, [rax+4]; Size
0x1800b9c9b  xor     edx, edx; Val
0x1800b9c9d  mov     rcx, rdi; void *
0x1800b9ca0  call    memset_0
0x1800b9ca5  mov     rbx, [rsp+118h+var_D0]
0x1800b9caa  mov     edi, [rsp+118h+var_E8]
0x1800b9cae  mov     r8d, edi
0x1800b9cb1  shr     r8, 6
0x1800b9cb5  mov     rax, [r15]
0x1800b9cb8  mov     edx, [rax+10h]
0x1800b9cbb  and     r8, rdx
0x1800b9cbe  mov     rax, [rsp+118h+var_D8]
0x1800b9cc3  mov     r9, [rax]
0x1800b9cc6  and     edi, 3Fh
0x1800b9cc9  mov     edx, 1
0x1800b9cce  mov     cl, dil
0x1800b9cd1  shl     rdx, cl
0x1800b9cd4  mov     rax, [r9+r8*8]
0x1800b9cd8  test    rdx, rax
0x1800b9cdb  jnz     short loc_1800B9CE4
0x1800b9cdd  or      rax, rdx
0x1800b9ce0  mov     [r9+r8*8], rax
0x1800b9ce4  add     rbx, 2
0x1800b9ce8  mov     rax, [rsp+118h+var_B8]
0x1800b9ced  jmp     loc_1800B9AEF
0x1800b9cf2  mov     rdi, [r12+10h]
0x1800b9cf7  cmp     rdi, [r12+18h]
0x1800b9cfc  jz      loc_1800BA01C
0x1800b9d02  mov     rcx, [r13+0F0h]
0x1800b9d09  mov     rax, [rcx]
0x1800b9d0c  mov     rax, [rax+50h]
0x1800b9d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d15  cmp     [rdi], eax
0x1800b9d17  jz      loc_1800BA013
0x1800b9d1d  lea     r15, [r13+2F8h]
0x1800b9d24  mov     r8, rdi
0x1800b9d27  lea     rdx, [rsp+118h+var_B8]
0x1800b9d2c  mov     rcx, r15
0x1800b9d2f  call    ?find@?$_Tree@V?$_Tmap_traits@IGU?$less@I@std@@V?$allocator@U?$pair@$$CBIG@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIG@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,ushort,std::less<uint>,std::allocator<std::pair<uint const,ushort>>,0>>::find(uint const &)
0x1800b9d34  mov     rbx, [rsp+118h+var_B8]
0x1800b9d39  cmp     rbx, [r15]
0x1800b9d3c  jz      loc_1800BA013
0x1800b9d42  movzx   r8d, word ptr [rbx+20h]
0x1800b9d47  mov     rdx, [r12+120h]
0x1800b9d4f  mov     ecx, [rdx+14h]
0x1800b9d52  mov     eax, r8d
0x1800b9d55  shr     eax, cl
0x1800b9d57  mov     ecx, [r12+128h]
0x1800b9d5f  cmp     eax, ecx
0x1800b9d61  jb      short loc_1800B9DA6
0x1800b9d63  cmp     eax, [r12+12Ch]
0x1800b9d6b  jnb     short loc_1800B9DA6
0x1800b9d6d  sub     eax, ecx
0x1800b9d6f  mov     ecx, eax
0x1800b9d71  mov     rax, [r12+130h]
0x1800b9d79  mov     r9, [rax+rcx*8]
0x1800b9d7d  test    r9, r9
0x1800b9d80  jz      short loc_1800B9DA6
0x1800b9d82  mov     edx, [rdx+10h]
0x1800b9d85  mov     eax, r8d
0x1800b9d88  shr     rax, 6
0x1800b9d8c  and     rdx, rax
0x1800b9d8f  mov     eax, r8d
0x1800b9d92  and     eax, 3Fh
0x1800b9d95  movzx   ecx, al
0x1800b9d98  mov     rax, [r9+rdx*8]
0x1800b9d9c  bt      rax, rcx
0x1800b9da0  jb      loc_1800BA013
0x1800b9da6  test    byte ptr [r12+0Ch], 1
0x1800b9dac  jnz     loc_1800BA013
0x1800b9db2  mov     edx, r8d
0x1800b9db5  lea     rcx, aPidDeletedByOm; "PID deleted by omission: %d"
0x1800b9dbc  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800b9dc1  mov     [rsp+118h+var_90], 0
0x1800b9dcd  mov     [rsp+118h+var_88], 0
0x1800b9dd9  xorps   xmm0, xmm0
0x1800b9ddc  movdqu  xmmword ptr [rsp+118h+var_80], xmm0
0x1800b9de5  mov     eax, [rdi]
0x1800b9de7  mov     [rsp+118h+var_98], eax
0x1800b9dee  mov     rcx, [r12+30h]; this
0x1800b9df3  cmp     rcx, [r12+38h]
0x1800b9df8  jz      short loc_1800B9E0F
0x1800b9dfa  lea     rdx, [rsp+118h+var_98]; struct inverted::PROPERTYVALUE *
0x1800b9e02  call    ??0PROPERTYVALUE@inverted@@QEAA@AEBU01@@Z; inverted::PROPERTYVALUE::PROPERTYVALUE(inverted::PROPERTYVALUE const &)
0x1800b9e07  add     qword ptr [r12+30h], 28h ; '('
0x1800b9e0d  jmp     short loc_1800B9E24
0x1800b9e0f  lea     r8, [rsp+118h+var_98]
0x1800b9e17  mov     rdx, rcx
0x1800b9e1a  lea     rcx, [r12+28h]
0x1800b9e1f  call    ??$_Emplace_reallocate@AEBUPROPERTYVALUE@inverted@@@?$vector@UPROPERTYVALUE@inverted@@V?$allocator@UPROPERTYVALUE@inverted@@@std@@@std@@AEAAPEAUPROPERTYVALUE@inverted@@QEAU23@AEBU23@@Z; std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(inverted::PROPERTYVALUE * const,inverted::PROPERTYVALUE const &)
0x1800b9e24  lea     r8, [r12+108h]
0x1800b9e2c  movzx   ebx, word ptr [rbx+20h]
0x1800b9e30  mov     [rsp+118h+var_E8], ebx
0x1800b9e34  mov     rcx, [r8]
0x1800b9e37  mov     ecx, [rcx+14h]
0x1800b9e3a  mov     edx, ebx
0x1800b9e3c  shr     edx, cl
0x1800b9e3e  cmp     edx, [r8+8]
0x1800b9e42  jb      short loc_1800B9E6C
0x1800b9e44  cmp     edx, [r8+0Ch]
0x1800b9e48  jnb     short loc_1800B9E5D
0x1800b9e4a  sub     edx, [r8+8]
0x1800b9e4e  mov     rax, [r8+10h]
0x1800b9e52  lea     rax, [rax+rdx*8]
0x1800b9e56  mov     [rsp+118h+var_E0], rax
0x1800b9e5b  jmp     short loc_1800B9E81
0x1800b9e5d  mov     rcx, r8
0x1800b9e60  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9e65  mov     [rsp+118h+var_E0], rax
0x1800b9e6a  jmp     short loc_1800B9E79
0x1800b9e6c  mov     rcx, r8
0x1800b9e6f  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9e74  mov     [rsp+118h+var_E0], rax
0x1800b9e79  lea     r8, [r12+108h]
0x1800b9e81  cmp     qword ptr [rax], 0
0x1800b9e85  jnz     loc_1800B9FC7
0x1800b9e8b  mov     rbx, [r8]
0x1800b9e8e  mov     [rsp+118h+var_D8], rbx
0x1800b9e93  lea     rcx, [rbx+30h]
0x1800b9e97  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b9e9c  mov     r15, rax
0x1800b9e9f  mov     rax, [rax+18h]
0x1800b9ea3  cmp     [r15+10h], rax
0x1800b9ea7  jnz     loc_1800B9F9B
0x1800b9ead  mov     edx, [r15+8]
0x1800b9eb1  cmp     edx, [rbx+1Ch]
0x1800b9eb4  jnb     short loc_1800B9ED0
0x1800b9eb6  mov     rax, [r15]
0x1800b9eb9  lea     rbx, [rax+rdx*8]
0x1800b9ebd  mov     rax, [rsp+118h+var_D8]
0x1800b9ec2  mov     ecx, [rax+8]
0x1800b9ec5  add     ecx, edx
0x1800b9ec7  mov     [r15+8], ecx
0x1800b9ecb  jmp     loc_1800B9FA6
0x1800b9ed0  mov     edx, [rbx+20h]; Alignment
0x1800b9ed3  mov     ecx, [rbx+1Ch]
0x1800b9ed6  shl     rcx, 3; Size
0x1800b9eda  call    cs:__imp__aligned_malloc
0x1800b9ee0  mov     rbx, rax
0x1800b9ee3  mov     [rsp+118h+var_D0], rax
0x1800b9ee8  mov     rcx, [rsp+118h]; this
0x1800b9ef0  test    rax, rax
0x1800b9ef3  jnz     short loc_1800B9F06
0x1800b9ef5  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b9efc  mov     edx, 430h; void *
  ... truncated ...
```

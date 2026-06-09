# asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(std::function<std::any (void)>,std::function<void (asg::SemanticIndex::ApplicationDbWriteTransaction const &,std::any &&)>)

- ea: `0x18019f0a0`
- end: `0x1801a0170`
- name: `?BeginWriteTransaction@ApplicationDb@SemanticIndex@asg@@AEAA?AV?$shared_ptr@VApplicationDbWriteTransaction@SemanticIndex@asg@@@std@@V?$function@$$A6A?AVany@std@@XZ@5@V?$function@$$A6AXAEBVApplicationDbWriteTransaction@SemanticIndex@asg@@$$QEAVany@std@@@Z@5@@Z`
- size: `4304`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18018ffd0`
- `0x1801a21c0`

## callees

- `0x1800040f0`
- `0x1800085c0`
- `0x18001db40`
- `0x180030790`
- `0x180046a10`
- `0x180078ed0`
- `0x18018e000`
- `0x180199f20`
- `0x18019a920`
- `0x18019c800`
- `0x18019f0a0`
- `0x1801a6a60`
- `0x1801d3160`
- `0x1801d32f0`
- `0x1801f7110`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180242860`

## string_xrefs

- `0x1801a00a7`: `Current thread already has the current write transaction`
- `0x1801a0147`: `Current thread already has the current write transaction`
- `0x18019f89c`: `class std::shared_ptr<class asg::SemanticIndex::ApplicationDbWriteTransaction> __cdecl asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(class std::function<class std::any __cdecl(void)>,class std::function<void __cdecl(class asg::SemanticIndex::ApplicationDbWriteTransaction const &,class std::any &&)>)`
- `0x1801a0058`: `class std::shared_ptr<class asg::SemanticIndex::ApplicationDbWriteTransaction> __cdecl asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(class std::function<class std::any __cdecl(void)>,class std::function<void __cdecl(class asg::SemanticIndex::ApplicationDbWriteTransaction const &,class std::any &&)>)`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 **__fastcall asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(
        __int64 *a1,
        __int64 **a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  __int64 v9; // r12
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  volatile signed __int32 *v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int128 *v15; // rcx
  char v16; // bl
  _OWORD *v17; // rcx
  __int128 *v18; // rcx
  __int64 *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 *v23; // rax
  int v24; // esi
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 **v27; // rax
  __int64 *v28; // rcx
  volatile signed __int32 *v29; // r13
  volatile signed __int32 *v30; // rsi
  __int64 v31; // rdx
  signed __int32 v32; // eax
  signed __int32 v33; // ett
  __int64 v34; // rax
  volatile signed __int32 *v35; // rsi
  volatile signed __int32 *v36; // r12
  __int64 v37; // r15
  volatile signed __int32 *v38; // r8
  __m128i v39; // kr20_16
  __int64 *v40; // rsi
  __int64 v41; // r15
  __int64 v42; // rdx
  volatile signed __int32 *v43; // rsi
  __m128i v44; // xmm1
  signed __int32 v45; // eax
  signed __int32 v46; // ett
  volatile signed __int32 *v47; // xmm1_8
  __int64 *v48; // rcx
  __int64 **v49; // r14
  __int128 *v50; // rcx
  __int64 v51; // rbx
  __int64 v52; // rcx
  _OWORD *v53; // rbx
  _OWORD *v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int128 *v58; // rcx
  char v59; // si
  _OWORD *v60; // rcx
  __int128 *v61; // rcx
  __int64 *v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  void *v67; // rax
  int v68; // ebx
  __int64 v69; // rax
  __int64 v70; // rax
  _QWORD *v71; // rax
  __int64 v72; // r13
  __int64 *v73; // rcx
  volatile signed __int32 *v74; // rbx
  __m128i v75; // xmm1
  __int64 v76; // rax
  unsigned __int64 v77; // rcx
  unsigned __int64 v78; // xmm0_8
  volatile signed __int32 *v79; // rbx
  __int64 *v80; // r12
  __int64 v81; // r13
  volatile signed __int32 *v82; // r12
  __int64 v83; // rdx
  __int128 *v84; // rcx
  __int64 v85; // rbx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v89; // [rsp+38h] [rbp-290h]
  __int64 *v90; // [rsp+38h] [rbp-290h]
  __int64 *v91; // [rsp+38h] [rbp-290h]
  _OWORD v92[4]; // [rsp+40h] [rbp-288h] BYREF
  __int64 *v93; // [rsp+80h] [rbp-248h]
  __m128i v94; // [rsp+90h] [rbp-238h] BYREF
  __m128i v95; // [rsp+A0h] [rbp-228h] BYREF
  __int128 v96; // [rsp+B0h] [rbp-218h] BYREF
  __int128 v97; // [rsp+C0h] [rbp-208h]
  __int128 *v98; // [rsp+D8h] [rbp-1F0h]
  void (__fastcall **v99)(__int128 *); // [rsp+E0h] [rbp-1E8h]
  __int64 v100; // [rsp+E8h] [rbp-1E0h]
  _OWORD *v101; // [rsp+F0h] [rbp-1D8h]
  __m128i v102; // [rsp+100h] [rbp-1C8h]
  __int64 *v103; // [rsp+110h] [rbp-1B8h]
  __int128 v104; // [rsp+118h] [rbp-1B0h]
  __int64 **v105; // [rsp+128h] [rbp-1A0h]
  __int64 v106; // [rsp+130h] [rbp-198h]
  __int128 v107; // [rsp+140h] [rbp-188h] BYREF
  __int64 v108; // [rsp+150h] [rbp-178h]
  __int64 v109; // [rsp+160h] [rbp-168h] BYREF
  __int64 *v110; // [rsp+168h] [rbp-160h]
  __int64 *v111; // [rsp+198h] [rbp-130h]
  __int64 **v112; // [rsp+1A0h] [rbp-128h]
  _BYTE v113[24]; // [rsp+1A8h] [rbp-120h] BYREF
  _BYTE v114[24]; // [rsp+1C0h] [rbp-108h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+1D8h] [rbp-F0h] BYREF
  __int64 v116; // [rsp+218h] [rbp-B0h]
  __int64 v117; // [rsp+220h] [rbp-A8h]
  __m128i v118; // [rsp+230h] [rbp-98h]
  __int128 v119; // [rsp+240h] [rbp-88h] BYREF
  __int128 v120; // [rsp+250h] [rbp-78h]
  __int128 v121; // [rsp+260h] [rbp-68h]
  __int128 v122; // [rsp+270h] [rbp-58h]

  v101 = (_OWORD *)a4;
  v106 = a3;
  v105 = a2;
  v102.m128i_i64[0] = (__int64)a1;
  v112 = a2;
  v116 = a3;
  v117 = a4;
  if ( (unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>() )
  {
    asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>();
    if ( *((_BYTE *)a1 + 136) )
    {
      asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
        pExceptionObject,
        "ApplicationDb is closed",
        25);
      throw (asg::SemanticIndex::SemanticIndexException *)pExceptionObject;
    }
    v7 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((int)a1 + 152);
    v8 = (volatile signed __int32 *)v7;
    v9 = a1[18];
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 12));
    if ( (_InterlockedExchange64(a1 + 19, v7) & 3) == 2 )
      _std_atomic_notify_all_direct(a1 + 19);
    v118 = 0;
    if ( v8 && (v10 = *((_DWORD *)v8 + 2)) != 0 )
    {
      while ( 1 )
      {
        v11 = v10;
        v10 = _InterlockedCompareExchange(v8 + 2, v10 + 1, v10);
        if ( v11 == v10 )
          break;
        if ( !v10 )
          goto LABEL_11;
      }
      v118.m128i_i64[0] = v9;
      v12 = v8;
      v118.m128i_i64[1] = (__int64)v8;
    }
    else
    {
LABEL_11:
      v12 = (volatile signed __int32 *)v118.m128i_i64[1];
      v9 = v118.m128i_i64[0];
    }
    if ( v8 && _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( v9 && *(_DWORD *)(v9 + 496) == Thrd_id() )
    {
      std::logic_error::logic_error(
        (std::logic_error *)v113,
        "Current thread already has the current write transaction");
      throw (std::logic_error *)v113;
    }
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    std::counting_semaphore<1>::acquire((_DWORD)a1 + 168);
    v14 = *(_QWORD *)(a3 + 56);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 16LL))(v14, &v96);
      v15 = &v96;
      v16 = -127;
    }
    else
    {
      memset(v92, 0, sizeof(v92));
      v15 = v92;
      v16 = 2;
    }
    v119 = 0;
    v120 = 0;
    v121 = 0;
    v122 = 0;
    *((_QWORD *)&v122 + 1) = *((_QWORD *)v15 + 7);
    if ( (BYTE8(v122) & 3) != 0 )
    {
      if ( (BYTE8(v122) & 3) == 1 )
      {
        *(_QWORD *)&v122 = *((_QWORD *)v15 + 6);
        *((_QWORD *)&v121 + 1) = *((_QWORD *)v15 + 5);
        *((_QWORD *)v15 + 7) = 0;
        goto LABEL_32;
      }
      if ( (BYTE8(v122) & 3) == 2 )
      {
        *(_QWORD *)&v122 = *((_QWORD *)v15 + 6);
        (*(void (__fastcall **)(__int128 *, __int128 *))(v122 + 16))(&v119, v15);
        goto LABEL_32;
      }
    }
    v119 = *v15;
    v120 = v15[1];
    v121 = v15[2];
    *(_QWORD *)&v122 = *((_QWORD *)v15 + 6);
LABEL_32:
    if ( (v16 & 2) == 0 )
      goto LABEL_39;
    v16 &= ~2u;
    if ( (BYTE8(v92[3]) & 3) == 1 )
    {
      v17 = (_OWORD *)*((_QWORD *)&v92[2] + 1);
    }
    else
    {
      if ( (BYTE8(v92[3]) & 3) != 2 )
      {
LABEL_38:
        *((_QWORD *)&v92[3] + 1) = 0;
LABEL_39:
        if ( (v16 & 1) == 0 )
        {
LABEL_46:
          if ( a1 + 22 != (__int64 *)a4 )
          {
            v19 = (__int64 *)a1[29];
            if ( v19 )
            {
              LOBYTE(v13) = v19 != a1 + 22;
              (*(void (__fastcall **)(__int64 *, __int64))(*v19 + 32))(v19, v13);
              a1[29] = 0;
            }
            v20 = *(_QWORD *)(a4 + 56);
            if ( v20 )
            {
              if ( v20 == a4 )
              {
                a1[29] = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 8LL))(v20, a1 + 22);
                v22 = *(_QWORD *)(a4 + 56);
                if ( !v22 )
                  goto LABEL_201;
                LOBYTE(v21) = v22 != a4;
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 32LL))(v22, v21);
              }
              else
              {
                a1[29] = v20;
              }
              *(_QWORD *)(a4 + 56) = 0;
            }
          }
LABEL_201:
          try
          {
            v95 = 0;
            v23 = (__int64 *)operator new(0x1F8u);
            v24 = (int)v23;
            v103 = v23;
            if ( !v23 )
            {
              v26 = 0;
LABEL_66:
              v27 = (__int64 **)std::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>(
                                  &v96,
                                  v26);
              v93 = *v27;
              v28 = v93;
              v103 = v27[1];
              v29 = (volatile signed __int32 *)v103;
              *v27 = 0;
              v27[1] = 0;
              v95.m128i_i64[0] = (__int64)v28;
              v95.m128i_i64[1] = (__int64)v29;
              v30 = (volatile signed __int32 *)*((_QWORD *)&v96 + 1);
              if ( *((_QWORD *)&v96 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v96 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
                  if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
                }
              }
              v102 = 0;
              if ( v29 )
              {
                v102 = v95;
                _InterlockedIncrement(v29 + 3);
              }
              goto LABEL_203;
            }
            memset(v23, 0, 0x1F8u);
            v93 = &v109;
            v109 = (__int64)___7___Func_impl_no_alloc_V_lambda_1___8__BeginWriteTransaction_ApplicationDb_SemanticIndex_asg__AEAA_AV__shared_ptr_VApplicationDbWriteTransaction_SemanticIndex_asg___std__V__function___A6A_AVany_std__XZ_7_V__function___A6AXAEBVApplicationDbWriteTransaction_SemanticIndex_asg____QEAVany_std___Z_7__Z_XAEAVDbTransaction_Sqlite_5_Vany_7__std__6B_;
            v110 = a1;
            v111 = &v109;
            memset(v92, 0, 56);
            *((_QWORD *)&v92[3] + 1) = *((_QWORD *)&v122 + 1);
            if ( (BYTE8(v122) & 3) != 0 )
            {
              if ( (BYTE8(v122) & 3) == 1 )
              {
                *(_QWORD *)&v92[3] = v122;
                *((_QWORD *)&v92[2] + 1) = *((_QWORD *)&v121 + 1);
                *((_QWORD *)&v122 + 1) = 0;
                goto LABEL_62;
              }
              if ( (BYTE8(v122) & 3) == 2 )
              {
                *(_QWORD *)&v92[3] = v122;
                (*(void (__fastcall **)(_OWORD *, __int128 *))(v122 + 16))(v92, &v119);
LABEL_62:
                *(_QWORD *)&v104 = &v94;
                v94 = 0;
                v25 = a1[14];
                if ( v25 )
                  _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
                v94 = *(__m128i *)(a1 + 13);
                std::enable_shared_from_this<asg::SemanticIndex::ApplicationDb>::shared_from_this(a1, &v107);
                v26 = asg::SemanticIndex::ApplicationDbWriteTransaction::ApplicationDbWriteTransaction(
                        v24,
                        (struct std::any *)v92,
                        (__int64)&v109);
                goto LABEL_66;
              }
            }
            v92[0] = v119;
            v92[1] = v120;
            v92[2] = v121;
            *(_QWORD *)&v92[3] = v122;
            goto LABEL_62;
          }
          catch ( ... )
          {
            std::counting_semaphore<1>::release(v102.m128i_i64[0] + 168, 1);
            throw;
          }
LABEL_203:
          v104 = 0;
          v31 = a1[1];
          if ( !v31 || (v32 = *(_DWORD *)(v31 + 8)) == 0 )
LABEL_197:
            std::_Throw_bad_weak_ptr();
          while ( 1 )
          {
            v33 = v32;
            v32 = _InterlockedCompareExchange((volatile signed __int32 *)(v31 + 8), v32 + 1, v32);
            if ( v33 == v32 )
              break;
            if ( !v32 )
              goto LABEL_197;
          }
          v34 = *a1;
          v89 = *a1;
          v35 = (volatile signed __int32 *)a1[1];
          v104 = 0;
          if ( v35 )
          {
            *(_QWORD *)&v104 = v34;
            v36 = v35;
            *((_QWORD *)&v104 + 1) = v35;
            v37 = (__int64)(v35 + 3);
            _InterlockedIncrement(v35 + 3);
          }
          else
          {
            v37 = 12;
            v36 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
            v89 = v104;
          }
          if ( v35 )
          {
            if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
            }
          }
          v96 = 0;
          if ( v36 )
          {
            v38 = v36;
            _InterlockedIncrement(v36 + 3);
          }
          else
          {
            v38 = (volatile signed __int32 *)*((_QWORD *)&v96 + 1);
            v89 = v96;
          }
          v39 = v102;
          v102 = 0;
          *(_QWORD *)&v92[0] = ___7___Func_impl_no_alloc_V_lambda_2___4__BeginWriteTransaction_ApplicationDb_SemanticIndex_asg__AEAA_AV__shared_ptr_VApplicationDbWriteTransaction_SemanticIndex_asg___std__V__function___A6A_AVany_std__XZ_7_V__function___A6AXAEBVApplicationDbWriteTransaction_SemanticIndex_asg____QEAVany_std___Z_7__Z_XAEAVDbTransaction_Sqlite_5__std__6B_;
          *((_QWORD *)&v92[0] + 1) = v89;
          *(_QWORD *)&v92[1] = v38;
          v96 = 0;
          *(__m128i *)((char *)&v92[1] + 8) = v39;
          v97 = 0;
          *((_QWORD *)&v92[3] + 1) = v92;
          v40 = v93;
          asg::Event<asg::Sqlite::DbTransaction &>::operator+=(v93 + 42, v92);
          v90 = 0;
          v41 = 0;
          if ( v29 )
          {
            v90 = v40;
            _InterlockedIncrement(v29 + 3);
            v41 = (__int64)v29;
          }
          v94 = 0;
          v43 = (volatile signed __int32 *)std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((int)a1 + 152);
          v94.m128i_i64[1] = (__int64)v43;
          v94.m128i_i64[0] = a1[18];
          a1[18] = (__int64)v90;
          if ( (_InterlockedExchange64(a1 + 19, v41) & 3) == 2 )
            _std_atomic_notify_all_direct(a1 + 19);
          v44 = 0;
          v118 = 0;
          if ( v43 )
          {
            v45 = *((_DWORD *)v43 + 2);
            if ( v45 )
            {
              while ( 1 )
              {
                v46 = v45;
                v45 = _InterlockedCompareExchange(v43 + 2, v45 + 1, v45);
                if ( v46 == v45 )
                  break;
                if ( !v45 )
                  goto LABEL_97;
              }
              v44 = v94;
              v118 = v94;
            }
          }
LABEL_97:
          *(_QWORD *)&v96 = 0xD000005CBLL;
          *((_QWORD *)&v96 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
          *(_QWORD *)&v97 = "class std::shared_ptr<class asg::SemanticIndex::ApplicationDbWriteTransaction> __cdecl asg::"
                            "SemanticIndex::ApplicationDb::BeginWriteTransaction(class std::function<class std::any __cde"
                            "cl(void)>,class std::function<void __cdecl(class asg::SemanticIndex::ApplicationDbWriteTrans"
                            "action const &,class std::any &&)>)";
          if ( v44.m128i_i64[0] )
          {
            v107 = v96;
            v108 = v97;
            asg::details::AsgAssertFail(&v107);
          }
          v47 = (volatile signed __int32 *)_mm_srli_si128(v44, 8).m128i_u64[0];
          if ( v47 )
          {
            if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
              if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
            }
          }
          if ( v43 && _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          v48 = v93;
          if ( _InterlockedExchange64(a1 + 20, (__int64)v93) )
          {
            *(_QWORD *)&v96 = 0xD000005CCLL;
            *((_QWORD *)&v96 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
            *(_QWORD *)&v97 = "class std::shared_ptr<class asg::SemanticIndex::ApplicationDbWriteTransaction> __cdecl asg"
                              "::SemanticIndex::ApplicationDb::BeginWriteTransaction(class std::function<class std::any _"
                              "_cdecl(void)>,class std::function<void __cdecl(class asg::SemanticIndex::ApplicationDbWrit"
                              "eTransaction const &,class std::any &&)>)";
            asg::details::AsgAssertFail(&v96);
          }
          v49 = v105;
          *v105 = v48;
          v49[1] = v103;
          if ( v36 && _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          if ( (BYTE8(v122) & 3) == 1 )
          {
            v50 = (__int128 *)*((_QWORD *)&v121 + 1);
          }
          else
          {
            if ( (BYTE8(v122) & 3) != 2 )
            {
LABEL_114:
              *((_QWORD *)&v122 + 1) = 0;
              v51 = v106;
              v52 = *(_QWORD *)(v106 + 56);
              if ( v52 )
              {
                LOBYTE(v42) = v52 != v106;
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 32LL))(v52, v42);
                *(_QWORD *)(v51 + 56) = 0;
              }
              v53 = v101;
              v54 = (_OWORD *)*((_QWORD *)v101 + 7);
              if ( v54 )
              {
                LOBYTE(v42) = v54 != v101;
                (*(void (__fastcall **)(_OWORD *, __int64))(*(_QWORD *)v54 + 32LL))(v54, v42);
                *((_QWORD *)v53 + 7) = 0;
              }
              return v49;
            }
            v50 = &v119;
          }
          (*(void (__fastcall **)(__int128 *))v122)(v50);
          goto LABEL_114;
        }
        if ( (v100 & 3) == 1 )
        {
          v18 = v98;
        }
        else
        {
          if ( (v100 & 3) != 2 )
          {
LABEL_45:
            v100 = 0;
            goto LABEL_46;
          }
          v18 = &v96;
        }
        (*v99)(v18);
        goto LABEL_45;
      }
      v17 = v92;
    }
    (**(void (__fastcall ***)(_OWORD *))&v92[3])(v17);
    goto LABEL_38;
  }
  v55 = a1[20];
  if ( v55 && *(_DWORD *)(v55 + 496) == Thrd_id() )
  {
    std::logic_error::logic_error((std::logic_error *)v114, "Current thread already has the current write transaction");
    throw (std::logic_error *)v114;
  }
  std::counting_semaphore<1>::acquire((_DWORD)a1 + 168);
  v57 = *(_QWORD *)(a3 + 56);
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v57 + 16LL))(v57, &v96);
    v58 = &v96;
    v59 = 72;
  }
  else
  {
    memset(v92, 0, sizeof(v92));
    v58 = v92;
    v59 = 16;
  }
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  *((_QWORD *)&v122 + 1) = *((_QWORD *)v58 + 7);
  if ( (BYTE8(v122) & 3) != 0 )
  {
    if ( (BYTE8(v122) & 3) == 1 )
    {
      *(_QWORD *)&v122 = *((_QWORD *)v58 + 6);
      *((_QWORD *)&v121 + 1) = *((_QWORD *)v58 + 5);
      *((_QWORD *)v58 + 7) = 0;
      goto LABEL_129;
    }
    if ( (BYTE8(v122) & 3) == 2 )
    {
      *(_QWORD *)&v122 = *((_QWORD *)v58 + 6);
      (*(void (__fastcall **)(__int128 *, __int128 *))(v122 + 16))(&v119, v58);
      goto LABEL_129;
    }
  }
  v119 = *v58;
  v120 = v58[1];
  v121 = v58[2];
  *(_QWORD *)&v122 = *((_QWORD *)v58 + 6);
LABEL_129:
  if ( (v59 & 0x10) == 0 )
    goto LABEL_136;
  v59 &= ~0x10u;
  if ( (BYTE8(v92[3]) & 3) == 1 )
  {
    v60 = (_OWORD *)*((_QWORD *)&v92[2] + 1);
    goto LABEL_134;
  }
  if ( (BYTE8(v92[3]) & 3) == 2 )
  {
    v60 = v92;
LABEL_134:
    (**(void (__fastcall ***)(_OWORD *))&v92[3])(v60);
  }
  *((_QWORD *)&v92[3] + 1) = 0;
LABEL_136:
  if ( (v59 & 8) != 0 )
  {
    if ( (v100 & 3) == 1 )
    {
      v61 = v98;
    }
    else
    {
      if ( (v100 & 3) != 2 )
      {
LABEL_142:
        v100 = 0;
        goto LABEL_143;
      }
      v61 = &v96;
    }
    (*v99)(v61);
    goto LABEL_142;
  }
LABEL_143:
  if ( a1 + 22 != (__int64 *)a4 )
  {
    v62 = (__int64 *)a1[29];
    if ( v62 )
    {
      LOBYTE(v56) = v62 != a1 + 22;
      (*(void (__fastcall **)(__int64 *, __int64))(*v62 + 32))(v62, v56);
      a1[29] = 0;
    }
    v63 = *(_QWORD *)(a4 + 56);
    if ( v63 )
    {
      if ( v63 == a4 )
      {
        v64 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 8LL))(v63, a1 + 22);
        a1[29] = v64;
        v66 = *(_QWORD *)(a4 + 56);
        if ( !v66 )
          goto LABEL_206;
        LOBYTE(v65) = v66 != a4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 32LL))(v66, v65);
      }
      else
      {
        a1[29] = v63;
      }
      *(_QWORD *)(a4 + 56) = 0;
    }
  }
LABEL_206:
  try
  {
    v94 = 0;
    v67 = operator new(0x1F8u);
    v68 = (int)v67;
    v118.m128i_i64[0] = (__int64)v67;
    if ( !v67 )
    {
      v70 = 0;
LABEL_163:
      v71 = std::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>(
              &v107,
              v70);
      v101 = (_OWORD *)*v71;
      v72 = (__int64)v101;
      v91 = (__int64 *)v71[1];
      v73 = v91;
      *v71 = 0;
      v71[1] = 0;
      v94.m128i_i64[0] = v72;
      v94.m128i_i64[1] = (__int64)v91;
      v74 = (volatile signed __int32 *)*((_QWORD *)&v107 + 1);
      if ( *((_QWORD *)&v107 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v107 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
        v73 = v91;
      }
      v75 = 0;
      v95 = 0;
      if ( v73 )
      {
        v75 = v94;
        v95 = v94;
        _InterlockedIncrement((volatile signed __int32 *)v73 + 3);
      }
      v76 = 0;
      v77 = 0;
      v78 = _mm_srli_si128(v75, 8).m128i_u64[0];
      v79 = (volatile signed __int32 *)v78;
      if ( v78 )
      {
        v80 = (__int64 *)v75.m128i_i64[0];
        v76 = v75.m128i_i64[0];
        _InterlockedIncrement((volatile signed __int32 *)(v78 + 12));
        v77 = v78;
      }
      else
      {
        v80 = (__int64 *)v95.m128i_i64[0];
      }
      goto LABEL_208;
    }
    memset(v67, 0, 0x1F8u);
    *(_QWORD *)&v104 = &v109;
    v109 = (__int64)___7___Func_impl_no_alloc_V_lambda_3___BA___BeginWriteTransaction_ApplicationDb_SemanticIndex_asg__AEAA_AV__shared_ptr_VApplicationDbWriteTransaction_SemanticIndex_asg___std__V__function___A6A_AVany_std__XZ_7_V__function___A6AXAEBVApplicationDbWriteTransaction_SemanticIndex_asg____QEAVany_std___Z_7__Z_XAEAVDbTransaction_Sqlite_5_Vany_7__std__6B_;
    v110 = a1;
    v111 = &v109;
    v101 = v92;
    memset(v92, 0, 56);
    *((_QWORD *)&v92[3] + 1) = *((_QWORD *)&v122 + 1);
    if ( (BYTE8(v122) & 3) != 0 )
    {
      if ( (BYTE8(v122) & 3) == 1 )
      {
        *(_QWORD *)&v92[3] = v122;
        *((_QWORD *)&v92[2] + 1) = *((_QWORD *)&v121 + 1);
        *((_QWORD *)&v122 + 1) = 0;
        goto LABEL_159;
      }
      if ( (BYTE8(v122) & 3) == 2 )
      {
        *(_QWORD *)&v92[3] = v122;
        (*(void (__fastcall **)(_OWORD *, __int128 *))(v122 + 16))(v92, &v119);
LABEL_159:
        v103 = (__int64 *)&v95;
        v95 = 0;
        v69 = a1[14];
        if ( v69 )
          _InterlockedIncrement((volatile signed __int32 *)(v69 + 8));
        v95 = *(__m128i *)(a1 + 13);
        std::enable_shared_from_this<asg::SemanticIndex::ApplicationDb>::shared_from_this(a1, &v96);
        v70 = asg::SemanticIndex::ApplicationDbWriteTransaction::ApplicationDbWriteTransaction(
                v68,
                (struct std::any *)v92,
                (__int64)&v109);
        goto LABEL_163;
      }
    }
    v92[0] = v119;
    v92[1] = v120;
    v92[2] = v121;
    *(_QWORD *)&v92[3] = v122;
    goto LABEL_159;
  }
  catch ( ... )
  {
    std::counting_semaphore<1>::release(v102.m128i_i64[0] + 168, 1);
    throw;
  }
LABEL_208:
  *(_QWORD *)&v92[0] = ___7___Func_impl_no_alloc_V_lambda_4___M___BeginWriteTransaction_ApplicationDb_SemanticIndex_asg__AEAA_AV__shared_ptr_VApplicationDbWriteTransaction_SemanticIndex_asg___std__V__function___A6A_AVany_std__XZ_7_V__function___A6AXAEBVApplicationDbWriteTransaction_SemanticIndex_asg____QEAVany_std___Z_7__Z_XAEAVDbTransaction_Sqlite_5__std__6B_;
  *((_QWORD *)&v92[0] + 1) = v76;
  *(_QWORD *)&v92[1] = v77;
  v96 = 0;
  *((_QWORD *)&v92[3] + 1) = v92;
  asg::Event<asg::Sqlite::DbTransaction &>::operator+=(v72 + 336, v92);
  if ( _InterlockedExchange64(a1 + 20, v72) )
  {
    *(_QWORD *)&v96 = 0xD0000060BLL;
    *((_QWORD *)&v96 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
    *(_QWORD *)&v97 = "class std::shared_ptr<class asg::SemanticIndex::ApplicationDbWriteTransaction> __cdecl asg::Semant"
                      "icIndex::ApplicationDb::BeginWriteTransaction(class std::function<class std::any __cdecl(void)>,cl"
                      "ass std::function<void __cdecl(class asg::SemanticIndex::ApplicationDbWriteTransaction const &,cla"
                      "ss std::any &&)>)";
    asg::details::AsgAssertFail(&v96);
  }
  v93 = 0;
  v81 = 0;
  if ( v79 )
  {
    v93 = v80;
    _InterlockedIncrement(v79 + 3);
    v81 = (__int64)v79;
  }
  v82 = (volatile signed __int32 *)std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((int)a1 + 152);
  v83 = a1[18];
  a1[18] = (__int64)v93;
  if ( (_InterlockedExchange64(a1 + 19, v81) & 3) == 2 )
    _std_atomic_notify_all_direct(a1 + 19);
  if ( v82 && _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v82 + 8LL))(v82, v83);
  v49 = v105;
  *v105 = (__int64 *)v101;
  v49[1] = v91;
  if ( v79 && _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v79 + 8LL))(v79, v83);
  if ( (BYTE8(v122) & 3) == 1 )
  {
    v84 = (__int128 *)*((_QWORD *)&v121 + 1);
    goto LABEL_188;
  }
  if ( (BYTE8(v122) & 3) == 2 )
  {
    v84 = &v119;
LABEL_188:
    (*(void (__fastcall **)(__int128 *))v122)(v84);
  }
  *((_QWORD *)&v122 + 1) = 0;
  v85 = v106;
  v86 = *(_QWORD *)(v106 + 56);
  if ( v86 )
  {
    LOBYTE(v83) = v86 != v106;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 32LL))(v86, v83);
    *(_QWORD *)(v85 + 56) = 0;
  }
  v87 = *(_QWORD *)(a4 + 56);
  if ( v87 )
  {
    LOBYTE(v83) = v87 != a4;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 32LL))(v87, v83);
    *(_QWORD *)(a4 + 56) = 0;
  }
  return v49;
}

```

## disassembly

```asm
0x18019f0a0  push    rbx
0x18019f0a2  push    rsi
0x18019f0a3  push    rdi
0x18019f0a4  push    r12
0x18019f0a6  push    r13
0x18019f0a8  push    r14
0x18019f0aa  push    r15
0x18019f0ac  sub     rsp, 290h
0x18019f0b3  mov     rax, cs:__security_cookie
0x18019f0ba  xor     rax, rsp
0x18019f0bd  mov     [rsp+2C8h+var_48], rax
0x18019f0c5  mov     r15, r9
0x18019f0c8  mov     [rsp+2C8h+var_1D8], r9
0x18019f0d0  mov     r13, r8
0x18019f0d3  mov     [rsp+2C8h+var_198], r8
0x18019f0db  mov     [rsp+2C8h+var_1A0], rdx
0x18019f0e3  mov     r14, rcx
0x18019f0e6  mov     qword ptr [rsp+2C8h+var_1C8], rcx
0x18019f0ee  mov     [rsp+2C8h+var_128], rdx
0x18019f0f6  mov     [rsp+2C8h+var_B0], r8
0x18019f0fe  mov     [rsp+2C8h+var_A8], r9
0x18019f106  xor     r12d, r12d
0x18019f109  mov     [rsp+2C8h+var_298], r12d
0x18019f10e  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_56532199@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>(void)
0x18019f113  test    al, al
0x18019f115  jz      loc_18019F9F0
0x18019f11b  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_56532199@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_56532199>>(void)
0x18019f120  movzx   eax, byte ptr [r14+88h]
0x18019f128  nop
0x18019f129  test    al, al
0x18019f12b  jnz     loc_1801A0078
0x18019f131  lea     rcx, [r14+98h]; int
0x18019f138  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18019f13d  mov     rbx, rax
0x18019f140  mov     r12, [r14+90h]
0x18019f147  test    rax, rax
0x18019f14a  jz      short loc_18019F150
0x18019f14c  lock inc dword ptr [rax+0Ch]
0x18019f150  mov     rcx, rbx
0x18019f153  xchg    rcx, [r14+98h]
0x18019f15a  and     cl, 3
0x18019f15d  cmp     cl, 2
0x18019f160  jnz     short loc_18019F16E
0x18019f162  lea     rcx, [r14+98h]
0x18019f169  call    __std_atomic_notify_all_direct
0x18019f16e  xorps   xmm1, xmm1
0x18019f171  movdqu  [rsp+2C8h+var_98], xmm1
0x18019f17a  test    rbx, rbx
0x18019f17d  jz      short loc_18019F194
0x18019f17f  mov     eax, [rbx+8]
0x18019f182  test    eax, eax
0x18019f184  jz      short loc_18019F194
0x18019f186  lea     ecx, [rax+1]
0x18019f189  lock cmpxchg [rbx+8], ecx
0x18019f18e  jz      short loc_18019F1DD
0x18019f190  test    eax, eax
0x18019f192  jnz     short loc_18019F186
0x18019f194  mov     r12, qword ptr [rsp+2C8h+var_98]
0x18019f19c  mov     rsi, qword ptr [rsp+2C8h+var_98+8]
0x18019f1a4  mov     edi, 0FFFFFFFFh
0x18019f1a9  test    rbx, rbx
0x18019f1ac  jz      short loc_18019F1C3
0x18019f1ae  mov     eax, edi
0x18019f1b0  lock xadd [rbx+0Ch], eax
0x18019f1b5  cmp     eax, 1
0x18019f1b8  jnz     short loc_18019F1C3
0x18019f1ba  mov     rax, [rbx]
0x18019f1bd  mov     rcx, rbx
0x18019f1c0  call    qword ptr [rax+8]
0x18019f1c3  test    r12, r12
0x18019f1c6  jz      short loc_18019F1F2
0x18019f1c8  call    _Thrd_id
0x18019f1cd  cmp     [r12+1F0h], eax
0x18019f1d5  jz      loc_1801A00A7
0x18019f1db  jmp     short loc_18019F1F2
0x18019f1dd  mov     qword ptr [rsp+2C8h+var_98], r12
0x18019f1e5  mov     rsi, rbx
0x18019f1e8  mov     qword ptr [rsp+2C8h+var_98+8], rbx
0x18019f1f0  jmp     short loc_18019F1A4
0x18019f1f2  test    rsi, rsi
0x18019f1f5  jz      short loc_18019F220
0x18019f1f7  mov     eax, edi
0x18019f1f9  lock xadd [rsi+8], eax
0x18019f1fe  cmp     eax, 1
0x18019f201  jnz     short loc_18019F220
0x18019f203  mov     rax, [rsi]
0x18019f206  mov     rcx, rsi
0x18019f209  call    qword ptr [rax]
0x18019f20b  mov     eax, edi
0x18019f20d  lock xadd [rsi+0Ch], eax
0x18019f212  cmp     eax, 1
0x18019f215  jnz     short loc_18019F220
0x18019f217  mov     rax, [rsi]
0x18019f21a  mov     rcx, rsi
0x18019f21d  call    qword ptr [rax+8]
0x18019f220  lea     rcx, [r14+0A8h]; int
0x18019f227  call    ?acquire@?$counting_semaphore@$00@std@@QEAAXXZ; std::counting_semaphore<1>::acquire(void)
0x18019f22c  mov     rcx, [r13+38h]
0x18019f230  test    rcx, rcx
0x18019f233  jz      short loc_18019F252
0x18019f235  mov     rax, [rcx]
0x18019f238  lea     rdx, [rsp+2C8h+var_218]
0x18019f240  call    qword ptr [rax+10h]
0x18019f243  lea     rcx, [rsp+2C8h+var_218]
0x18019f24b  mov     ebx, 81h
0x18019f250  jmp     short loc_18019F273
0x18019f252  xorps   xmm0, xmm0
0x18019f255  movups  [rsp+2C8h+var_288], xmm0
0x18019f25a  movups  [rsp+2C8h+var_278], xmm0
0x18019f25f  movups  [rsp+2C8h+var_268], xmm0
0x18019f264  movups  [rsp+2C8h+var_258], xmm0
0x18019f269  lea     rcx, [rsp+2C8h+var_288]
0x18019f26e  mov     ebx, 2
0x18019f273  mov     [rsp+2C8h+var_298], ebx
0x18019f277  xorps   xmm0, xmm0
0x18019f27a  movups  [rsp+2C8h+var_88], xmm0
0x18019f282  movups  [rsp+2C8h+var_78], xmm0
0x18019f28a  movups  [rsp+2C8h+var_68], xmm0
0x18019f292  movups  [rsp+2C8h+var_58], xmm0
0x18019f29a  mov     rax, [rcx+38h]
0x18019f29e  mov     qword ptr [rsp+2C8h+var_58+8], rax
0x18019f2a6  and     eax, 3
0x18019f2a9  jz      short loc_18019F2F8
0x18019f2ab  sub     rax, 1
0x18019f2af  jz      short loc_18019F2D7
0x18019f2b1  cmp     rax, 1
0x18019f2b5  jnz     short loc_18019F2F8
0x18019f2b7  mov     rax, [rcx+30h]
0x18019f2bb  mov     qword ptr [rsp+2C8h+var_58], rax
0x18019f2c3  mov     r8, [rax+10h]
0x18019f2c7  mov     rdx, rcx
0x18019f2ca  lea     rcx, [rsp+2C8h+var_88]
0x18019f2d2  call    r8
0x18019f2d5  jmp     short loc_18019F329
0x18019f2d7  mov     rax, [rcx+30h]
0x18019f2db  mov     qword ptr [rsp+2C8h+var_58], rax
0x18019f2e3  mov     rax, [rcx+28h]
0x18019f2e7  mov     qword ptr [rsp+2C8h+var_68+8], rax
0x18019f2ef  xor     r12d, r12d
0x18019f2f2  mov     [rcx+38h], r12
0x18019f2f6  jmp     short loc_18019F32C
0x18019f2f8  movups  xmm0, xmmword ptr [rcx]
0x18019f2fb  movaps  [rsp+2C8h+var_88], xmm0
0x18019f303  movups  xmm1, xmmword ptr [rcx+10h]
0x18019f307  movaps  [rsp+2C8h+var_78], xmm1
0x18019f30f  movups  xmm0, xmmword ptr [rcx+20h]
0x18019f313  movaps  [rsp+2C8h+var_68], xmm0
0x18019f31b  movsd   xmm1, qword ptr [rcx+30h]
0x18019f320  movsd   qword ptr [rsp+2C8h+var_58], xmm1
0x18019f329  xor     r12d, r12d
0x18019f32c  test    bl, 2
0x18019f32f  jz      short loc_18019F367
0x18019f331  and     ebx, 0FFFFFFFDh
0x18019f334  mov     [rsp+2C8h+var_298], ebx
0x18019f338  mov     rax, qword ptr [rsp+2C8h+var_258+8]
0x18019f33d  and     eax, 3
0x18019f340  sub     rax, 1
0x18019f344  jz      short loc_18019F353
0x18019f346  cmp     rax, 1
0x18019f34a  jnz     short loc_18019F362
0x18019f34c  lea     rcx, [rsp+2C8h+var_288]
0x18019f351  jmp     short loc_18019F358
0x18019f353  mov     rcx, qword ptr [rsp+2C8h+var_268+8]
0x18019f358  mov     rax, qword ptr [rsp+2C8h+var_258]
0x18019f35d  mov     rdx, [rax]
0x18019f360  call    rdx
0x18019f362  mov     qword ptr [rsp+2C8h+var_258+8], r12
0x18019f367  test    bl, 1
0x18019f36a  jz      short loc_18019F3B1
0x18019f36c  and     ebx, 0FFFFFFFEh
0x18019f36f  mov     [rsp+2C8h+var_298], ebx
0x18019f373  mov     rax, [rsp+2C8h+var_1E0]
0x18019f37b  and     eax, 3
0x18019f37e  sub     rax, 1
0x18019f382  jz      short loc_18019F394
0x18019f384  cmp     rax, 1
0x18019f388  jnz     short loc_18019F3A9
0x18019f38a  lea     rcx, [rsp+2C8h+var_218]
0x18019f392  jmp     short loc_18019F39C
0x18019f394  mov     rcx, [rsp+2C8h+var_1F0]
0x18019f39c  mov     rax, [rsp+2C8h+var_1E8]
0x18019f3a4  mov     rdx, [rax]
0x18019f3a7  call    rdx
0x18019f3a9  mov     [rsp+2C8h+var_1E0], r12
0x18019f3b1  lea     rsi, [r14+0B0h]
0x18019f3b8  cmp     rsi, r15
0x18019f3bb  jz      short loc_18019F410
0x18019f3bd  mov     rcx, [rsi+38h]
0x18019f3c1  test    rcx, rcx
0x18019f3c4  jz      short loc_18019F3D6
0x18019f3c6  cmp     rcx, rsi
0x18019f3c9  setnz   dl
0x18019f3cc  mov     rax, [rcx]
0x18019f3cf  call    qword ptr [rax+20h]
0x18019f3d2  mov     [rsi+38h], r12
0x18019f3d6  mov     rcx, [r15+38h]
0x18019f3da  test    rcx, rcx
0x18019f3dd  jz      short loc_18019F410
0x18019f3df  cmp     rcx, r15
0x18019f3e2  jnz     short loc_18019F408
0x18019f3e4  mov     rax, [rcx]
0x18019f3e7  mov     rdx, rsi
0x18019f3ea  call    qword ptr [rax+8]
0x18019f3ed  mov     [rsi+38h], rax
0x18019f3f1  mov     rcx, [r15+38h]
0x18019f3f5  test    rcx, rcx
0x18019f3f8  jz      short loc_18019F410
0x18019f3fa  cmp     rcx, r15
0x18019f3fd  setnz   dl
0x18019f400  mov     rax, [rcx]
0x18019f403  call    qword ptr [rax+20h]
0x18019f406  jmp     short loc_18019F40C
0x18019f408  mov     [rsi+38h], rcx
0x18019f40c  mov     [r15+38h], r12
0x18019f410  xorps   xmm1, xmm1
0x18019f413  movdqa  [rsp+2C8h+var_228], xmm1
0x18019f41c  mov     ecx, 1F8h; Size
0x18019f421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019f426  mov     rsi, rax
0x18019f429  mov     [rsp+2C8h+var_1B8], rax
0x18019f431  test    rax, rax
0x18019f434  jz      loc_18019F5C4
0x18019f43a  xor     edx, edx; Val
0x18019f43c  mov     r8d, 1F8h; Size
0x18019f442  mov     rcx, rax; void *
0x18019f445  call    memset
0x18019f44a  lea     rax, [rsp+2C8h+var_168]
0x18019f452  mov     [rsp+2C8h+var_248], rax
0x18019f45a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?8??BeginWriteTransaction@ApplicationDb@SemanticIndex@asg@@AEAA?AV?$shared_ptr@VApplicationDbWriteTransaction@SemanticIndex@asg@@@std@@V?$function@$$A6A?AVany@std@@XZ@7@V?$function@$$A6AXAEBVApplicationDbWriteTransaction@SemanticIndex@asg@@$$QEAVany@std@@@Z@7@@Z@XAEAVDbTransaction@Sqlite@5@Vany@7@@std@@6B@; const std::_Func_impl_no_alloc<`asg::SemanticIndex::ApplicationDb::BeginWriteTransaction(std::function<std::any (void)>,std::function<void (asg::SemanticIndex::ApplicationDbWriteTransaction const &,std::any &&)>)'::`9'::_lambda_1_,void,asg::Sqlite::DbTransaction &,std::any>::`vftable'
0x18019f461  mov     [rsp+2C8h+var_168], rax
0x18019f469  mov     [rsp+2C8h+var_160], r14
0x18019f471  lea     rax, [rsp+2C8h+var_168]
0x18019f479  mov     [rsp+2C8h+var_130], rax
0x18019f481  lea     rax, [rsp+2C8h+var_288]
0x18019f486  mov     [rsp+2C8h+var_290], rax
0x18019f48b  mov     qword ptr [rsp+2C8h+var_288], r12
0x18019f490  xorps   xmm0, xmm0
0x18019f493  movdqu  [rsp+2C8h+var_288+8], xmm0
0x18019f499  xorps   xmm1, xmm1
0x18019f49c  movdqu  [rsp+2C8h+var_278+8], xmm1
0x18019f4a2  movdqu  [rsp+2C8h+var_268+8], xmm0
0x18019f4a8  mov     rax, qword ptr [rsp+2C8h+var_58+8]
0x18019f4b0  mov     qword ptr [rsp+2C8h+var_258+8], rax
0x18019f4b5  and     eax, 3
0x18019f4b8  jz      short loc_18019F50D
0x18019f4ba  sub     rax, 1
0x18019f4be  jz      short loc_18019F4E9
0x18019f4c0  cmp     rax, 1
0x18019f4c4  jnz     short loc_18019F50D
0x18019f4c6  mov     rax, qword ptr [rsp+2C8h+var_58]
0x18019f4ce  mov     qword ptr [rsp+2C8h+var_258], rax
0x18019f4d3  mov     r8, [rax+10h]
0x18019f4d7  lea     rdx, [rsp+2C8h+var_88]
0x18019f4df  lea     rcx, [rsp+2C8h+var_288]
0x18019f4e4  call    r8
0x18019f4e7  jmp     short loc_18019F543
0x18019f4e9  mov     rax, qword ptr [rsp+2C8h+var_58]
0x18019f4f1  mov     qword ptr [rsp+2C8h+var_258], rax
0x18019f4f6  mov     rax, qword ptr [rsp+2C8h+var_68+8]
0x18019f4fe  mov     qword ptr [rsp+2C8h+var_268+8], rax
0x18019f503  mov     qword ptr [rsp+2C8h+var_58+8], r12
0x18019f50b  jmp     short loc_18019F543
0x18019f50d  movaps  xmm0, [rsp+2C8h+var_88]
0x18019f515  movups  [rsp+2C8h+var_288], xmm0
0x18019f51a  movaps  xmm1, [rsp+2C8h+var_78]
0x18019f522  movups  [rsp+2C8h+var_278], xmm1
0x18019f527  movaps  xmm0, [rsp+2C8h+var_68]
0x18019f52f  movups  [rsp+2C8h+var_268], xmm0
0x18019f534  movsd   xmm1, qword ptr [rsp+2C8h+var_58]
0x18019f53d  movsd   qword ptr [rsp+2C8h+var_258], xmm1
0x18019f543  lea     rax, [rsp+2C8h+var_238]
0x18019f54b  mov     qword ptr [rsp+2C8h+var_1B0], rax
0x18019f553  xorps   xmm0, xmm0
0x18019f556  movdqu  [rsp+2C8h+var_238], xmm0
0x18019f55f  mov     rax, [r14+70h]
0x18019f563  test    rax, rax
0x18019f566  jz      short loc_18019F56C
0x18019f568  lock inc dword ptr [rax+8]
0x18019f56c  mov     rax, [r14+68h]
0x18019f570  mov     qword ptr [rsp+2C8h+var_238], rax
0x18019f578  mov     rax, [r14+70h]
0x18019f57c  mov     qword ptr [rsp+2C8h+var_238+8], rax
0x18019f584  lea     rdx, [rsp+2C8h+var_188]
0x18019f58c  mov     rcx, r14
0x18019f58f  call    ?shared_from_this@?$enable_shared_from_this@VApplicationDb@SemanticIndex@asg@@@std@@QEAA?AV?$shared_ptr@VApplicationDb@SemanticIndex@asg@@@2@XZ; std::enable_shared_from_this<asg::SemanticIndex::ApplicationDb>::shared_from_this(void)
0x18019f594  nop
0x18019f595  lea     rcx, [rsp+2C8h+var_168]
0x18019f59d  mov     [rsp+2C8h+var_2A0], rcx; __int64
0x18019f5a2  lea     rcx, [rsp+2C8h+var_288]
0x18019f5a7  mov     [rsp+2C8h+var_2A8], rcx; struct std::any *
0x18019f5ac  xor     r9d, r9d
0x18019f5af  lea     r8, [rsp+2C8h+var_238]
0x18019f5b7  mov     rdx, rax
0x18019f5ba  mov     rcx, rsi; int
0x18019f5bd  call    ??0ApplicationDbWriteTransaction@SemanticIndex@asg@@IEAA@V?$shared_ptr@VApplicationDb@SemanticIndex@asg@@@std@@V?$shared_ptr@UDbConnection@Sqlite@asg@@@4@_NVany@4@V?$function@$$A6AXAEAVDbTransaction@Sqlite@asg@@Vany@std@@@Z@4@@Z; asg::SemanticIndex::ApplicationDbWriteTransaction::ApplicationDbWriteTransaction(std::shared_ptr<asg::SemanticIndex::ApplicationDb>,std::shared_ptr<asg::Sqlite::DbConnection>,bool,std::any,std::function<void (asg::Sqlite::DbTransaction &,std::any)>)
0x18019f5c2  jmp     short loc_18019F5C7
0x18019f5c4  mov     rax, r12
0x18019f5c7  mov     rdx, rax
0x18019f5ca  lea     rcx, [rsp+2C8h+var_218]
0x18019f5d2  call    ??$?0VApplicationDbWriteTransaction@SemanticIndex@asg@@$0A@@?$shared_ptr@VApplicationDbWriteTransaction@SemanticIndex@asg@@@std@@QEAA@PEAVApplicationDbWriteTransaction@SemanticIndex@asg@@@Z; std::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>::shared_ptr<asg::SemanticIndex::ApplicationDbWriteTransaction>(asg::SemanticIndex::ApplicationDbWriteTransaction *)
  ... truncated ...
```

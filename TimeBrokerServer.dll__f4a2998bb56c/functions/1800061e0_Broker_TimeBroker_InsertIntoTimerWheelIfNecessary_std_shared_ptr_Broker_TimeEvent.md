# Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x1800061e0`
- end: `0x1800074b1`
- name: `?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `4817`
- prototype: `void __fastcall(Broker::TimeBroker *, _QWORD *, __int64)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000215c`
- `0x180003868`
- `0x180005d10`
- `0x18000fa10`
- `0x18000fe70`

## callees

- `0x180006070`
- `0x1800061e0`
- `0x180007830`
- `0x180007c60`
- `0x180008230`
- `0x180008280`
- `0x1800082e0`
- `0x18000b990`
- `0x180012df4`
- `0x1800131e4`
- `0x18001c010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000747a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007488`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007496`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000747a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007488`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180007496`

## pseudocode

```c
void __fastcall Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(Broker::TimeBroker *a1, _QWORD *a2, __int64 a3)
{
  _QWORD **v3; // rdi
  _DWORD *v5; // rcx
  char v6; // r13
  Broker::TimeBroker *v7; // r8
  __int64 **v8; // r14
  volatile signed __int32 *v9; // rax
  volatile signed __int32 *v10; // rcx
  __int64 **v11; // rdx
  __int64 *v12; // r12
  __m128i v13; // xmm6
  __int64 v14; // rbx
  __int64 *v15; // r15
  _BYTE *v16; // rcx
  __int64 *v17; // rax
  __int64 **v18; // rsi
  volatile signed __int32 *v19; // rdi
  volatile signed __int32 *v20; // xmm6_8
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 *v23; // rsi
  __int64 **v24; // rdx
  __int64 *v25; // r11
  __int64 v26; // rax
  int v27; // ecx
  __int64 *v28; // r9
  __int64 *v29; // r8
  __int64 *v30; // rax
  __int64 *v31; // rcx
  __int64 *v32; // r8
  __int64 *v33; // rax
  _QWORD *v34; // r8
  __int64 v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  _QWORD *v38; // r8
  _QWORD *v39; // rax
  __int64 j; // rax
  __int64 v41; // rax
  __int64 **v42; // r8
  __int64 ***v43; // rax
  __int64 v44; // rax
  _QWORD *v45; // rax
  volatile signed __int32 *v46; // rbx
  __int64 **v47; // r8
  __int64 v48; // r14
  __int64 **v49; // r14
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 **v52; // rdx
  __int64 *v53; // r12
  __m128i v54; // xmm6
  __int64 v55; // rbx
  __int64 *v56; // r15
  __int64 *k; // rax
  __int64 *v58; // rcx
  __int64 **v59; // rsi
  volatile signed __int32 *v60; // rdi
  volatile signed __int32 *v61; // xmm6_8
  __int64 v62; // rbx
  __int64 v63; // rdi
  __int64 *v64; // rsi
  __int64 **v65; // rdx
  __int64 *v66; // r9
  __int64 v67; // rax
  int v68; // ecx
  __int64 *v69; // r10
  __int64 *v70; // r8
  __int64 *v71; // rax
  __int64 *v72; // rcx
  __int64 *v73; // r8
  __int64 *v74; // rax
  _QWORD *v75; // r8
  __int64 v76; // rax
  _QWORD *v77; // rax
  _QWORD *v78; // rcx
  _QWORD *v79; // r8
  _QWORD *v80; // rax
  __int64 v81; // rax
  __int64 **v82; // r8
  __int64 ***v83; // rax
  __int64 v84; // rax
  _QWORD *v85; // rax
  volatile signed __int32 *v86; // rbx
  volatile signed __int32 *v87; // rbx
  __int64 **v88; // r14
  __int64 v89; // rax
  __int64 v90; // rcx
  __int64 **v91; // rdx
  __int64 *v92; // r12
  __m128i v93; // xmm6
  __int64 v94; // rbx
  __int64 *v95; // r15
  __int64 *i; // rax
  __int64 *v97; // rcx
  __int64 **v98; // rsi
  volatile signed __int32 *v99; // rdi
  volatile signed __int32 *v100; // xmm6_8
  __int64 v101; // rbx
  __int64 v102; // rsi
  __int64 *v103; // rdi
  __int64 **v104; // rdx
  __int64 *v105; // r9
  __int64 v106; // rax
  int v107; // r11d
  __int64 *v108; // r8
  __int64 *v109; // rcx
  __int64 *v110; // rax
  __int64 *v111; // rcx
  __int64 *v112; // r8
  __int64 *v113; // rax
  _QWORD *v114; // r8
  __int64 v115; // rax
  _QWORD *v116; // rax
  _QWORD *v117; // rcx
  _QWORD *v118; // r8
  _QWORD *v119; // rax
  char v120; // al
  int v121; // r8d
  const wchar_t *v122; // rcx
  __int64 v123; // rax
  __int64 **v124; // r8
  __int64 ***v125; // rax
  __int64 v126; // rax
  _QWORD *v127; // rax
  volatile signed __int32 *v128; // rbx
  _QWORD *v129; // rax
  __int64 v130; // r8
  _QWORD *v131; // rax
  __int64 v132; // r8
  __m128i v133; // [rsp+30h] [rbp-98h] BYREF
  __int64 **v134; // [rsp+40h] [rbp-88h] BYREF
  __int64 **v135; // [rsp+48h] [rbp-80h]
  __int64 *v136; // [rsp+50h] [rbp-78h]
  __int128 v137; // [rsp+58h] [rbp-70h] BYREF

  v3 = (_QWORD **)a2;
  v5 = (_DWORD *)*a2;
  if ( (unsigned int)(*(_DWORD *)(*a2 + 88LL) - 1) > 1 )
    goto LABEL_147;
  if ( v5[18] == 2 )
  {
    v88 = (__int64 **)((char *)a1 + 64);
    v133 = 0;
    v89 = a2[1];
    if ( v89 )
      _InterlockedIncrement((volatile signed __int32 *)(v89 + 8));
    v133.m128i_i64[0] = *a2;
    v90 = a2[1];
    v133.m128i_i64[1] = v90;
    v91 = (__int64 **)&v133;
    v92 = *(__int64 **)(v133.m128i_i64[0] + 24);
    if ( v90 )
      _InterlockedIncrement((volatile signed __int32 *)(v90 + 8));
    v93 = v133;
    v94 = **v88;
    v95 = (__int64 *)v133.m128i_i64[0];
    while ( (__int64 *)v94 != *v88 )
    {
      v91 = (__int64 **)v94;
      a3 = v94;
      i = *(__int64 **)(v94 + 16);
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = *(__int64 **)(v94 + 8); !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
        {
          if ( v94 != i[2] )
            break;
          v94 = (__int64)i;
        }
      }
      else
      {
        v97 = (__int64 *)*i;
        if ( !*(_BYTE *)(*i + 25) )
        {
          do
          {
            v94 = (__int64)v97;
            v97 = (__int64 *)*v97;
          }
          while ( !*((_BYTE *)v97 + 25) );
          goto LABEL_164;
        }
      }
      v94 = (__int64)i;
LABEL_164:
      if ( v91[5] == v95 )
      {
        v98 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
                v88,
                v91);
        v99 = (volatile signed __int32 *)v98[6];
        if ( v99 )
        {
          if ( _InterlockedExchangeAdd(v99 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
            if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
          }
        }
        operator delete(v98);
      }
    }
    v100 = (volatile signed __int32 *)_mm_srli_si128(v93, 8).m128i_u64[0];
    if ( v100 )
    {
      if ( _InterlockedExchangeAdd(v100 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v100)(v100);
        if ( _InterlockedExchangeAdd(v100 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v100 + 8LL))(v100);
      }
    }
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__guid_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v91, a3, *(_QWORD *)(v133.m128i_i64[0] + 248), v92);
    v136 = v92;
    v101 = v133.m128i_i64[1];
    if ( v133.m128i_i64[1] )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v133.m128i_i64[1] + 8));
      v101 = v133.m128i_i64[1];
    }
    v102 = v133.m128i_i64[0];
    *(_QWORD *)&v137 = v133.m128i_i64[0];
    *((_QWORD *)&v137 + 1) = v101;
    v103 = *v88;
    v134 = v88;
    v135 = 0;
    v104 = (__int64 **)operator new(0x38u);
    v135 = v104;
    v104[4] = v92;
    v104[5] = (__int64 *)v102;
    v104[6] = (__int64 *)v101;
    v137 = 0;
    *v104 = v103;
    v104[1] = v103;
    v104[2] = v103;
    *((_WORD *)v104 + 12) = 0;
    v105 = *v88;
    v106 = (*v88)[1];
    v107 = 0;
    if ( *(_BYTE *)(v106 + 25) )
    {
      v109 = (__int64 *)(*v88)[1];
      v108 = v109;
    }
    else
    {
      do
      {
        v108 = (__int64 *)v106;
        v109 = (__int64 *)v106;
        if ( (__int64)v92 < *(_QWORD *)(v106 + 32) )
        {
          v107 = 1;
          v106 = *(_QWORD *)v106;
        }
        else
        {
          v107 = 0;
          v106 = *(_QWORD *)(v106 + 16);
        }
      }
      while ( !*(_BYTE *)(v106 + 25) );
    }
    v110 = v88[1];
    if ( v110 == (__int64 *)0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v88[1] = (__int64 *)((char *)v110 + 1);
    v104[1] = v108;
    if ( v109 == v105 )
    {
      *v105 = (__int64)v104;
      v105[1] = (__int64)v104;
      v105[2] = (__int64)v104;
      *((_BYTE *)v104 + 24) = 1;
    }
    else
    {
      if ( v107 )
      {
        *v108 = (__int64)v104;
        if ( v109 == (__int64 *)*v105 )
          *v105 = (__int64)v104;
      }
      else
      {
        v108[2] = (__int64)v104;
        if ( v109 == (__int64 *)v105[2] )
          v105[2] = (__int64)v104;
      }
      while ( !*((_BYTE *)v104[1] + 24) )
      {
        v111 = v104[1];
        v112 = (__int64 *)v111[1];
        v113 = (__int64 *)*v112;
        if ( v111 == (__int64 *)*v112 )
        {
          v123 = v112[2];
          if ( !*(_BYTE *)(v123 + 24) )
          {
            *((_BYTE *)v111 + 24) = 1;
            *(_BYTE *)(v123 + 24) = 1;
            *(_BYTE *)(v104[1][1] + 24) = 0;
            v104 = (__int64 **)v104[1][1];
            continue;
          }
          v124 = (__int64 **)v111[2];
          if ( v104 == v124 )
          {
            v104 = (__int64 **)v104[1];
            v111[2] = (__int64)*v124;
            if ( !*((_BYTE *)*v124 + 25) )
              (*v124)[1] = (__int64)v111;
            v124[1] = (__int64 *)v111[1];
            if ( v111 == (__int64 *)(*v88)[1] )
            {
              (*v88)[1] = (__int64)v124;
            }
            else
            {
              v125 = (__int64 ***)v111[1];
              if ( v111 == (__int64 *)*v125 )
                *v125 = v124;
              else
                v125[2] = v124;
            }
            *v124 = v111;
            v111[1] = (__int64)v124;
          }
          *((_BYTE *)v104[1] + 24) = 1;
          *(_BYTE *)(v104[1][1] + 24) = 0;
          v117 = (_QWORD *)v104[1][1];
          v118 = (_QWORD *)*v117;
          *v117 = *(_QWORD *)(*v117 + 16LL);
          v126 = v118[2];
          if ( !*(_BYTE *)(v126 + 25) )
            *(_QWORD *)(v126 + 8) = v117;
          v118[1] = v117[1];
          if ( v117 == (_QWORD *)(*v88)[1] )
          {
            (*v88)[1] = (__int64)v118;
          }
          else
          {
            v127 = (_QWORD *)v117[1];
            if ( v117 == (_QWORD *)v127[2] )
              v127[2] = v118;
            else
              *v127 = v118;
          }
          v118[2] = v117;
        }
        else
        {
          if ( !*((_BYTE *)v113 + 24) )
          {
            *((_BYTE *)v111 + 24) = 1;
            *((_BYTE *)v113 + 24) = 1;
            *(_BYTE *)(v104[1][1] + 24) = 0;
            v104 = (__int64 **)v104[1][1];
            continue;
          }
          v114 = (_QWORD *)*v111;
          if ( v104 == (__int64 **)*v111 )
          {
            v104 = (__int64 **)v104[1];
            *v111 = v114[2];
            v115 = v114[2];
            if ( !*(_BYTE *)(v115 + 25) )
              *(_QWORD *)(v115 + 8) = v111;
            v114[1] = v111[1];
            if ( v111 == (__int64 *)(*v88)[1] )
            {
              (*v88)[1] = (__int64)v114;
            }
            else
            {
              v116 = (_QWORD *)v111[1];
              if ( v111 == (__int64 *)v116[2] )
                v116[2] = v114;
              else
                *v116 = v114;
            }
            v114[2] = v111;
            v111[1] = (__int64)v114;
          }
          *((_BYTE *)v104[1] + 24) = 1;
          *(_BYTE *)(v104[1][1] + 24) = 0;
          v117 = (_QWORD *)v104[1][1];
          v118 = (_QWORD *)v117[2];
          v117[2] = *v118;
          if ( !*(_BYTE *)(*v118 + 25LL) )
            *(_QWORD *)(*v118 + 8LL) = v117;
          v118[1] = v117[1];
          if ( v117 == (_QWORD *)(*v88)[1] )
          {
            (*v88)[1] = (__int64)v118;
            *v118 = v117;
          }
          else
          {
            v119 = (_QWORD *)v117[1];
            if ( v117 == (_QWORD *)*v119 )
              *v119 = v118;
            else
              v119[2] = v118;
            *v118 = v117;
          }
        }
        v117[1] = v118;
      }
      *(_BYTE *)(v105[1] + 24) = 1;
    }
    std::shared_ptr<Broker::TimeEvent>::~shared_ptr<Broker::TimeEvent>((__int64)&v137);
    v128 = (volatile signed __int32 *)v133.m128i_i64[1];
    if ( v133.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v133.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v128)(v128);
        if ( _InterlockedExchangeAdd(v128 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v128 + 8LL))(v128);
      }
    }
    v3 = (_QWORD **)a2;
    *(_QWORD *)(*a2 + 224LL) = v88;
    goto LABEL_147;
  }
  v6 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 48LL))(v5);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v120 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**v3 + 48LL))(*v3, **v3);
    v122 = L"wake";
    if ( !v120 )
      v122 = L"non-wake";
    WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)L"non-wake", v121, (*v3)[31], (__int64)v122);
  }
  v7 = (Broker::TimeBroker *)(*v3)[28];
  if ( v7 && v7 != (Broker::TimeBroker *)((char *)a1 + (v6 != 0 ? 0x10 : 0)) )
  {
    v131 = std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v134, v3);
    Broker::TimerWheel::Remove(v132, v131);
  }
  v8 = (__int64 **)((char *)a1 + (v6 != 0 ? 0x10 : 0));
  v133 = 0;
  v9 = (volatile signed __int32 *)v3[1];
  if ( v9 )
    _InterlockedIncrement(v9 + 2);
  v133.m128i_i64[0] = (__int64)*v3;
  v10 = (volatile signed __int32 *)v3[1];
  v133.m128i_i64[1] = (__int64)v10;
  v11 = (__int64 **)&v133;
  v12 = *(__int64 **)(v133.m128i_i64[0] + 24);
  if ( v10 )
    _InterlockedIncrement(v10 + 2);
  v13 = v133;
  v14 = **v8;
  v15 = (__int64 *)v133.m128i_i64[0];
  while ( (__int64 *)v14 != *v8 )
  {
    v11 = (__int64 **)v14;
    v7 = (Broker::TimeBroker *)v14;
    v16 = *(_BYTE **)(v14 + 16);
    if ( v16[25] )
    {
      for ( j = *(_QWORD *)(v14 + 8); !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
      {
        if ( v14 != *(_QWORD *)(j + 16) )
          break;
        v14 = j;
      }
      v14 = j;
    }
    else
    {
      v17 = *(__int64 **)v16;
      if ( *(_BYTE *)(*(_QWORD *)v16 + 25LL) )
      {
        v14 = *(_QWORD *)(v14 + 16);
      }
      else
      {
        do
        {
          v14 = (__int64)v17;
          v17 = (__int64 *)*v17;
        }
        while ( !*((_BYTE *)v17 + 25) );
      }
    }
    if ( v11[5] == v15 )
    {
      v18 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
              v8,
              v11);
      v19 = (volatile signed __int32 *)v18[6];
      if ( v19 && _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
      operator delete(v18);
    }
  }
  v20 = (volatile signed __int32 *)_mm_srli_si128(v13, 8).m128i_u64[0];
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v7, *(_QWORD *)(v133.m128i_i64[0] + 248), v12);
  v136 = v12;
  v21 = v133.m128i_i64[1];
  if ( v133.m128i_i64[1] )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v133.m128i_i64[1] + 8));
    v21 = v133.m128i_i64[1];
  }
  v22 = v133.m128i_i64[0];
  *(_QWORD *)&v137 = v133.m128i_i64[0];
  *((_QWORD *)&v137 + 1) = v21;
  v23 = *v8;
  v134 = v8;
  v135 = 0;
  v24 = (__int64 **)operator new(0x38u);
  v135 = v24;
  v24[4] = v12;
  v24[5] = (__int64 *)v22;
  v24[6] = (__int64 *)v21;
  v137 = 0;
  *v24 = v23;
  v24[1] = v23;
  v24[2] = v23;
  *((_WORD *)v24 + 12) = 0;
  v25 = *v8;
  v26 = (*v8)[1];
  v27 = 0;
  if ( *(_BYTE *)(v26 + 25) )
  {
    v29 = (__int64 *)(*v8)[1];
    v28 = v29;
  }
  else
  {
    do
    {
      v28 = (__int64 *)v26;
      v29 = (__int64 *)v26;
      if ( (__int64)v12 >= *(_QWORD *)(v26 + 32) )
      {
        v27 = 0;
        v26 = *(_QWORD *)(v26 + 16);
      }
      else
      {
        v27 = 1;
        v26 = *(_QWORD *)v26;
      }
    }
    while ( !*(_BYTE *)(v26 + 25) );
  }
  v30 = v8[1];
  if ( v30 == (__int64 *)0x492492492492492LL )
    std::_Xlength_error("map/set too long");
  v8[1] = (__int64 *)((char *)v30 + 1);
  v24[1] = v28;
  if ( v29 == v25 )
  {
    *v25 = (__int64)v24;
    v25[1] = (__int64)v24;
    v25[2] = (__int64)v24;
    *((_BYTE *)v24 + 24) = 1;
  }
  else
  {
    if ( v27 )
    {
      *v28 = (__int64)v24;
      if ( v29 == (__int64 *)*v25 )
        *v25 = (__int64)v24;
    }
    else
    {
      v28[2] = (__int64)v24;
      if ( v29 == (__int64 *)v25[2] )
        v25[2] = (__int64)v24;
    }
    while ( !*((_BYTE *)v24[1] + 24) )
    {
      v31 = v24[1];
      v32 = (__int64 *)v31[1];
      v33 = (__int64 *)*v32;
      if ( v31 == (__int64 *)*v32 )
      {
        v41 = v32[2];
        if ( !*(_BYTE *)(v41 + 24) )
        {
          *((_BYTE *)v31 + 24) = 1;
          *(_BYTE *)(v41 + 24) = 1;
          *(_BYTE *)(v24[1][1] + 24) = 0;
          v24 = (__int64 **)v24[1][1];
          continue;
        }
        v42 = (__int64 **)v31[2];
        if ( v24 == v42 )
        {
          v24 = (__int64 **)v24[1];
          v31[2] = (__int64)*v42;
          if ( !*((_BYTE *)*v42 + 25) )
            (*v42)[1] = (__int64)v31;
          v42[1] = (__int64 *)v31[1];
          if ( v31 == (__int64 *)(*v8)[1] )
          {
            (*v8)[1] = (__int64)v42;
          }
          else
          {
            v43 = (__int64 ***)v31[1];
            if ( v31 == (__int64 *)*v43 )
              *v43 = v42;
            else
              v43[2] = v42;
          }
          *v42 = v31;
          v31[1] = (__int64)v42;
        }
        *((_BYTE *)v24[1] + 24) = 1;
        *(_BYTE *)(v24[1][1] + 24) = 0;
        v37 = (_QWORD *)v24[1][1];
        v38 = (_QWORD *)*v37;
        *v37 = *(_QWORD *)(*v37 + 16LL);
        v44 = v38[2];
        if ( !*(_BYTE *)(v44 + 25) )
          *(_QWORD *)(v44 + 8) = v37;
        v38[1] = v37[1];
        if ( v37 == (_QWORD *)(*v8)[1] )
        {
          (*v8)[1] = (__int64)v38;
        }
        else
        {
          v45 = (_QWORD *)v37[1];
          if ( v37 == (_QWORD *)v45[2] )
            v45[2] = v38;
          else
            *v45 = v38;
        }
        v38[2] = v37;
      }
      else
      {
        if ( !*((_BYTE *)v33 + 24) )
        {
          *((_BYTE *)v31 + 24) = 1;
          *((_BYTE *)v33 + 24) = 1;
          *(_BYTE *)(v24[1][1] + 24) = 0;
          v24 = (__int64 **)v24[1][1];
          continue;
        }
        v34 = (_QWORD *)*v31;
        if ( v24 == (__int64 **)*v31 )
        {
          v24 = (__int64 **)v24[1];
          *v31 = v34[2];
          v35 = v34[2];
          if ( !*(_BYTE *)(v35 + 25) )
            *(_QWORD *)(v35 + 8) = v31;
          v34[1] = v31[1];
          if ( v31 == (__int64 *)(*v8)[1] )
          {
            (*v8)[1] = (__int64)v34;
          }
          else
          {
            v36 = (_QWORD *)v31[1];
            if ( v31 == (__int64 *)v36[2] )
              v36[2] = v34;
            else
              *v36 = v34;
          }
          v34[2] = v31;
          v31[1] = (__int64)v34;
        }
        *((_BYTE *)v24[1] + 24) = 1;
        *(_BYTE *)(v24[1][1] + 24) = 0;
        v37 = (_QWORD *)v24[1][1];
        v38 = (_QWORD *)v37[2];
        v37[2] = *v38;
        if ( !*(_BYTE *)(*v38 + 25LL) )
          *(_QWORD *)(*v38 + 8LL) = v37;
        v38[1] = v37[1];
        if ( v37 == (_QWORD *)(*v8)[1] )
        {
          (*v8)[1] = (__int64)v38;
          *v38 = v37;
        }
        else
        {
          v39 = (_QWORD *)v37[1];
          if ( v37 == (_QWORD *)*v39 )
            *v39 = v38;
          else
            v39[2] = v38;
          *v38 = v37;
        }
      }
      v37[1] = v38;
    }
    *(_BYTE *)(v25[1] + 24) = 1;
  }
  v46 = (volatile signed __int32 *)v133.m128i_i64[1];
  if ( v133.m128i_i64[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v133.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  *(_QWORD *)(*a2 + 224LL) = v8;
  v47 = *(__int64 ***)(*a2 + 232LL);
  if ( v47 && v47 != v8 + 4 )
  {
    v129 = std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v134, a2);
    Broker::TimerWheel::Remove(v130, v129);
  }
  v48 = 32;
  if ( v6 )
    v48 = 48;
  v49 = (__int64 **)((char *)a1 + v48);
  v133 = 0;
  v50 = a2[1];
  if ( v50 )
    _InterlockedIncrement((volatile signed __int32 *)(v50 + 8));
  v133.m128i_i64[0] = *a2;
  v51 = a2[1];
  v133.m128i_i64[1] = v51;
  v52 = (__int64 **)&v133;
  v53 = *(__int64 **)(v133.m128i_i64[0] + 32);
  if ( v51 )
    _InterlockedIncrement((volatile signed __int32 *)(v51 + 8));
  v54 = v133;
  v55 = **v49;
  v56 = (__int64 *)v133.m128i_i64[0];
  while ( (__int64 *)v55 != *v49 )
  {
    v52 = (__int64 **)v55;
    v47 = (__int64 **)v55;
    k = *(__int64 **)(v55 + 16);
    if ( *((_BYTE *)k + 25) )
    {
      for ( k = *(__int64 **)(v55 + 8); !*((_BYTE *)k + 25); k = (__int64 *)k[1] )
      {
        if ( v55 != k[2] )
          break;
        v55 = (__int64)k;
      }
    }
    else
    {
      v58 = (__int64 *)*k;
      if ( !*(_BYTE *)(*k + 25) )
      {
        do
        {
          v55 = (__int64)v58;
          v58 = (__int64 *)*v58;
        }
        while ( !*((_BYTE *)v58 + 25) );
        goto LABEL_86;
      }
    }
    v55 = (__int64)k;
LABEL_86:
    if ( v52[5] == v56 )
    {
      v59 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
              v49,
              v52);
      v60 = (volatile signed __int32 *)v59[6];
      if ( v60 )
      {
        if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
          if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
        }
      }
      operator delete(v59);
    }
  }
  v61 = (volatile signed __int32 *)_mm_srli_si128(v54, 8).m128i_u64[0];
  if ( v61 )
  {
    if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
      if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
    }
  }
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v52, v47, *(_QWORD *)(v133.m128i_i64[0] + 248), v53);
  v136 = v53;
  v62 = v133.m128i_i64[1];
  if ( v133.m128i_i64[1] )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v133.m128i_i64[1] + 8));
    v62 = v133.m128i_i64[1];
  }
  v63 = v133.m128i_i64[0];
  *(_QWORD *)&v137 = v133.m128i_i64[0];
  *((_QWORD *)&v137 + 1) = v62;
  v64 = *v49;
  v134 = v49;
  v135 = 0;
  v65 = (__int64 **)operator new(0x38u);
  v135 = v65;
  v65[4] = v53;
  v65[5] = (__int64 *)v63;
  v65[6] = (__int64 *)v62;
  v137 = 0;
  *v65 = v64;
  v65[1] = v64;
  v65[2] = v64;
  *((_WORD *)v65 + 12) = 0;
  v66 = *v49;
  v67 = (*v49)[1];
  v68 = 0;
  if ( *(_BYTE *)(v67 + 25) )
  {
    v70 = (__int64 *)(*v49)[1];
    v69 = v70;
  }
  else
  {
    do
    {
      v69 = (__int64 *)v67;
      v70 = (__int64 *)v67;
      if ( (__int64)v53 >= *(_QWORD *)(v67 + 32) )
      {
        v68 = 0;
        v67 = *(_QWORD *)(v67 + 16);
      }
      else
      {
        v68 = 1;
        v67 = *(_QWORD *)v67;
      }
    }
    while ( !*(_BYTE *)(v67 + 25) );
  }
  v71 = v49[1];
  if ( v71 == (__int64 *)0x492492492492492LL )
    std::_Xlength_error("map/set too long");
  v49[1] = (__int64 *)((char *)v71 + 1);
  v65[1] = v69;
  if ( v70 == v66 )
  {
    *v66 = (__int64)v65;
    v66[1] = (__int64)v65;
    v66[2] = (__int64)v65;
    *((_BYTE *)v65 + 24) = 1;
  }
  else
  {
    if ( v68 )
    {
      *v69 = (__int64)v65;
      if ( v70 == (__int64 *)*v66 )
        *v66 = (__int64)v65;
    }
    else
    {
      v69[2] = (__int64)v65;
      if ( v70 == (__int64 *)v66[2] )
        v66[2] = (__int64)v65;
    }
    while ( !*((_BYTE *)v65[1] + 24) )
    {
      v72 = v65[1];
      v73 = (__int64 *)v72[1];
      v74 = (__int64 *)*v73;
      if ( v72 == (__int64 *)*v73 )
      {
        v81 = v73[2];
        if ( !*(_BYTE *)(v81 + 24) )
        {
          *((_BYTE *)v72 + 24) = 1;
          *(_BYTE *)(v81 + 24) = 1;
          *(_BYTE *)(v65[1][1] + 24) = 0;
          v65 = (__int64 **)v65[1][1];
          continue;
        }
        v82 = (__int64 **)v72[2];
        if ( v65 == v82 )
        {
          v65 = (__int64 **)v65[1];
          v72[2] = (__int64)*v82;
          if ( !*((_BYTE *)*v82 + 25) )
            (*v82)[1] = (__int64)v72;
          v82[1] = (__int64 *)v72[1];
          if ( v72 == (__int64 *)(*v49)[1] )
          {
            (*v49)[1] = (__int64)v82;
          }
          else
          {
            v83 = (__int64 ***)v72[1];
            if ( v72 == (__int64 *)*v83 )
              *v83 = v82;
            else
              v83[2] = v82;
          }
          *v82 = v72;
          v72[1] = (__int64)v82;
        }
        *((_BYTE *)v65[1] + 24) = 1;
        *(_BYTE *)(v65[1][1] + 24) = 0;
        v78 = (_QWORD *)v65[1][1];
        v79 = (_QWORD *)*v78;
        *v78 = *(_QWORD *)(*v78 + 16LL);
        v84 = v79[2];
        if ( !*(_BYTE *)(v84 + 25) )
          *(_QWORD *)(v84 + 8) = v78;
        v79[1] = v78[1];
        if ( v78 == (_QWORD *)(*v49)[1] )
        {
          (*v49)[1] = (__int64)v79;
        }
        else
        {
          v85 = (_QWORD *)v78[1];
          if ( v78 == (_QWORD *)v85[2] )
            v85[2] = v79;
          else
            *v85 = v79;
        }
        v79[2] = v78;
      }
      else
      {
        if ( !*((_BYTE *)v74 + 24) )
        {
          *((_BYTE *)v72 + 24) = 1;
          *((_BYTE *)v74 + 24) = 1;
          *(_BYTE *)(v65[1][1] + 24) = 0;
          v65 = (__int64 **)v65[1][1];
          continue;
        }
        v75 = (_QWORD *)*v72;
        if ( v65 == (__int64 **)*v72 )
        {
          v65 = (__int64 **)v65[1];
          *v72 = v75[2];
          v76 = v75[2];
          if ( !*(_BYTE *)(v76 + 25) )
            *(_QWORD *)(v76 + 8) = v72;
          v75[1] = v72[1];
          if ( v72 == (__int64 *)(*v49)[1] )
          {
            (*v49)[1] = (__int64)v75;
          }
          else
          {
            v77 = (_QWORD *)v72[1];
            if ( v72 == (__int64 *)v77[2] )
              v77[2] = v75;
            else
              *v77 = v75;
          }
          v75[2] = v72;
          v72[1] = (__int64)v75;
        }
        *((_BYTE *)v65[1] + 24) = 1;
        *(_BYTE *)(v65[1][1] + 24) = 0;
        v78 = (_QWORD *)v65[1][1];
        v79 = (_QWORD *)v78[2];
        v78[2] = *v79;
        if ( !*(_BYTE *)(*v79 + 25LL) )
          *(_QWORD *)(*v79 + 8LL) = v78;
        v79[1] = v78[1];
        if ( v78 == (_QWORD *)(*v49)[1] )
        {
          (*v49)[1] = (__int64)v79;
          *v79 = v78;
        }
        else
        {
          v80 = (_QWORD *)v78[1];
          if ( v78 == (_QWORD *)*v80 )
            *v80 = v79;
          else
            v80[2] = v79;
          *v79 = v78;
        }
      }
      v78[1] = v79;
    }
    *(_BYTE *)(v66[1] + 24) = 1;
  }
  v86 = (volatile signed __int32 *)v133.m128i_i64[1];
  if ( v133.m128i_i64[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v133.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
      if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
    }
  }
  v3 = (_QWORD **)a2;
  *(_QWORD *)(*a2 + 232LL) = v49;
  Broker::TimeBroker::SetSytemTimer(a1);
LABEL_147:
  v87 = (volatile signed __int32 *)v3[1];
  if ( v87 )
  {
    if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
      if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
    }
  }
}

```

## disassembly

```asm
0x1800061e0  mov     [rsp+arg_8], rdx
0x1800061e5  mov     [rsp+arg_0], rcx
0x1800061ea  push    rbx
0x1800061eb  push    rsi
0x1800061ec  push    rdi
0x1800061ed  push    r12
0x1800061ef  push    r13
0x1800061f1  push    r14
0x1800061f3  push    r15
0x1800061f5  sub     rsp, 90h
0x1800061fc  movaps  [rsp+0C8h+var_48], xmm6
0x180006204  mov     rdi, rdx
0x180006207  mov     rbx, rcx
0x18000620a  mov     rcx, [rdx]
0x18000620d  mov     eax, [rcx+58h]
0x180006210  dec     eax
0x180006212  cmp     eax, 1
0x180006215  ja      loc_180006B07
0x18000621b  cmp     dword ptr [rcx+48h], 2
0x18000621f  jz      loc_180006B97
0x180006225  mov     rax, [rcx]
0x180006228  mov     rax, [rax+30h]
0x18000622c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006231  movzx   r13d, al
0x180006235  mov     rcx, cs:WPP_GLOBAL_Control
0x18000623c  test    dword ptr [rcx+1Ch], 100h
0x180006243  jnz     loc_180006EB6
0x180006249  mov     rax, [rdi]
0x18000624c  mov     r8, [rax+0E0h]
0x180006253  test    r8, r8
0x180006256  jnz     loc_18000722B
0x18000625c  movzx   eax, r13b
0x180006260  neg     al
0x180006262  sbb     rcx, rcx
0x180006265  and     ecx, 10h
0x180006268  lea     r14, [rcx+rbx]
0x18000626c  xorps   xmm0, xmm0
0x18000626f  movdqa  [rsp+0C8h+var_98], xmm0
0x180006275  mov     rax, [rdi+8]
0x180006279  test    rax, rax
0x18000627c  jz      short loc_180006282
0x18000627e  lock inc dword ptr [rax+8]
0x180006282  mov     rax, [rdi]
0x180006285  mov     qword ptr [rsp+0C8h+var_98], rax
0x18000628a  mov     rcx, [rdi+8]
0x18000628e  mov     qword ptr [rsp+0C8h+var_98+8], rcx
0x180006293  lea     rdx, [rsp+0C8h+var_98]
0x180006298  mov     [rsp+0C8h+arg_10], rdx
0x1800062a0  mov     r12, [rax+18h]
0x1800062a4  test    rcx, rcx
0x1800062a7  jz      short loc_1800062AD
0x1800062a9  lock inc dword ptr [rcx+8]
0x1800062ad  movaps  xmm6, [rsp+0C8h+var_98]
0x1800062b2  mov     rbx, [r14]
0x1800062b5  mov     rbx, [rbx]
0x1800062b8  movq    r15, xmm6
0x1800062bd  nop     dword ptr [rax]
0x1800062c0  cmp     rbx, [r14]
0x1800062c3  jz      short loc_18000633B
0x1800062c5  mov     rdx, rbx
0x1800062c8  mov     r8, rbx
0x1800062cb  mov     rcx, [rbx+10h]
0x1800062cf  cmp     byte ptr [rcx+19h], 0
0x1800062d3  jnz     loc_180006537
0x1800062d9  mov     rax, [rcx]
0x1800062dc  cmp     byte ptr [rax+19h], 0
0x1800062e0  jnz     loc_1800072E8
0x1800062e6  nop     word ptr [rax+rax+00000000h]
0x1800062f0  mov     rbx, rax
0x1800062f3  mov     rcx, [rax]
0x1800062f6  mov     rax, rcx
0x1800062f9  cmp     byte ptr [rcx+19h], 0
0x1800062fd  jz      short loc_1800062F0
0x1800062ff  cmp     [rdx+28h], r15
0x180006303  jnz     short loc_1800062C0
0x180006305  mov     rcx, r14
0x180006308  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)
0x18000630d  mov     rsi, rax
0x180006310  mov     rdi, [rax+30h]
0x180006314  test    rdi, rdi
0x180006317  jz      short loc_18000632C
0x180006319  mov     ecx, 0FFFFFFFFh
0x18000631e  lock xadd [rdi+8], ecx
0x180006323  cmp     ecx, 1
0x180006326  jz      loc_180006567
0x18000632c  mov     edx, 38h ; '8'; unsigned __int64
0x180006331  mov     rcx, rsi; void *
0x180006334  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006339  jmp     short loc_1800062C0
0x18000633b  psrldq  xmm6, 8
0x180006340  movq    rbx, xmm6
0x180006345  test    rbx, rbx
0x180006348  jz      short loc_18000635F
0x18000634a  mov     edi, 0FFFFFFFFh
0x18000634f  mov     eax, edi
0x180006351  lock xadd [rbx+8], eax
0x180006356  cmp     eax, 1
0x180006359  jz      loc_180006F6B
0x18000635f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006366  test    byte ptr [rcx+1Ch], 80h
0x18000636a  jnz     loc_18000716D
0x180006370  mov     [rsp+0C8h+var_78], r12
0x180006375  mov     rbx, qword ptr [rsp+0C8h+var_98+8]
0x18000637a  test    rbx, rbx
0x18000637d  jz      short loc_180006388
0x18000637f  lock inc dword ptr [rbx+8]
0x180006383  mov     rbx, qword ptr [rsp+0C8h+var_98+8]
0x180006388  mov     rdi, qword ptr [rsp+0C8h+var_98]
0x18000638d  mov     qword ptr [rsp+0C8h+var_70], rdi
0x180006392  mov     qword ptr [rsp+0C8h+var_70+8], rbx
0x180006397  mov     rsi, [r14]
0x18000639a  mov     [rsp+0C8h+var_88], r14
0x18000639f  mov     [rsp+0C8h+var_80], 0
0x1800063a8  mov     ecx, 38h ; '8'; Size
0x1800063ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063b2  mov     rdx, rax
0x1800063b5  mov     [rsp+0C8h+var_80], rax
0x1800063ba  mov     [rax+20h], r12
0x1800063be  mov     [rax+28h], rdi
0x1800063c2  mov     [rax+30h], rbx
0x1800063c6  xorps   xmm0, xmm0
0x1800063c9  movdqu  [rsp+0C8h+var_70], xmm0
0x1800063cf  mov     [rax], rsi
0x1800063d2  mov     [rax+8], rsi
0x1800063d6  mov     [rax+10h], rsi
0x1800063da  mov     word ptr [rax+18h], 0
0x1800063e0  mov     r11, [r14]
0x1800063e3  mov     rax, [r11+8]
0x1800063e7  xor     ecx, ecx
0x1800063e9  cmp     [rax+19h], cl
0x1800063ec  jnz     loc_1800070DA
0x1800063f2  nop     dword ptr [rax+00h]
0x1800063f6  nop     word ptr [rax+rax+00000000h]
0x180006400  mov     r9, rax
0x180006403  mov     r8, rax
0x180006406  cmp     r12, [rax+20h]
0x18000640a  jge     loc_18000655C
0x180006410  mov     ecx, 1
0x180006415  mov     rax, [rax]
0x180006418  cmp     byte ptr [rax+19h], 0
0x18000641c  jz      short loc_180006400
0x18000641e  mov     rax, [r14+8]
0x180006422  mov     r10, 492492492492492h
0x18000642c  cmp     rax, r10
0x18000642f  jz      loc_180007473
0x180006435  inc     rax
0x180006438  mov     [r14+8], rax
0x18000643c  mov     [rdx+8], r9
0x180006440  cmp     r8, r11
0x180006443  jz      loc_1800072F0
0x180006449  test    ecx, ecx
0x18000644b  jz      loc_180006B69
0x180006451  mov     [r9], rdx
0x180006454  cmp     r8, [r11]
0x180006457  jnz     short loc_18000645C
0x180006459  mov     [r11], rdx
0x18000645c  mov     rax, [rdx+8]
0x180006460  cmp     byte ptr [rax+18h], 0
0x180006464  jnz     loc_180006666
0x18000646a  mov     rcx, [rdx+8]
0x18000646e  mov     r8, [rcx+8]
0x180006472  mov     rax, [r8]
0x180006475  cmp     rcx, rax
0x180006478  jz      loc_18000659C
0x18000647e  cmp     byte ptr [rax+18h], 0
0x180006482  jz      loc_1800071E9
0x180006488  mov     r8, [rcx]
0x18000648b  cmp     rdx, r8
0x18000648e  jnz     short loc_1800064D6
0x180006490  mov     rdx, rcx
0x180006493  mov     rax, [r8+10h]
0x180006497  mov     [rcx], rax
0x18000649a  mov     rax, [r8+10h]
0x18000649e  cmp     byte ptr [rax+19h], 0
0x1800064a2  jz      loc_1800073A2
0x1800064a8  mov     rax, [rcx+8]
0x1800064ac  mov     [r8+8], rax
0x1800064b0  mov     rax, [r14]
0x1800064b3  cmp     rcx, [rax+8]
0x1800064b7  jz      loc_1800073E7
0x1800064bd  mov     rax, [rcx+8]
0x1800064c1  cmp     rcx, [rax+10h]
0x1800064c5  jz      loc_1800073F9
0x1800064cb  mov     [rax], r8
0x1800064ce  mov     [r8+10h], rcx
0x1800064d2  mov     [rcx+8], r8
0x1800064d6  mov     rax, [rdx+8]
0x1800064da  mov     byte ptr [rax+18h], 1
0x1800064de  mov     rax, [rdx+8]
0x1800064e2  mov     rcx, [rax+8]
0x1800064e6  mov     byte ptr [rcx+18h], 0
0x1800064ea  mov     rax, [rdx+8]
0x1800064ee  mov     rcx, [rax+8]
0x1800064f2  mov     r8, [rcx+10h]
0x1800064f6  mov     rax, [r8]
0x1800064f9  mov     [rcx+10h], rax
0x1800064fd  mov     rax, [r8]
0x180006500  cmp     byte ptr [rax+19h], 0
0x180006504  jnz     short loc_18000650A
0x180006506  mov     [rax+8], rcx
0x18000650a  mov     rax, [rcx+8]
0x18000650e  mov     [r8+8], rax
0x180006512  mov     rax, [r14]
0x180006515  cmp     rcx, [rax+8]
0x180006519  jz      loc_1800073BD
0x18000651f  mov     rax, [rcx+8]
0x180006523  cmp     rcx, [rax]
0x180006526  jnz     loc_18000732A
0x18000652c  mov     [rax], r8
0x18000652f  mov     [r8], rcx
0x180006532  jmp     loc_180006654
0x180006537  mov     rax, [rbx+8]
0x18000653b  cmp     byte ptr [rax+19h], 0
0x18000653f  jnz     short loc_180006554
0x180006541  cmp     rbx, [rax+10h]
0x180006545  jnz     short loc_180006554
0x180006547  mov     rbx, rax
0x18000654a  mov     rax, [rax+8]
0x18000654e  cmp     byte ptr [rax+19h], 0
0x180006552  jz      short loc_180006541
0x180006554  mov     rbx, rax
0x180006557  jmp     loc_1800062FF
0x18000655c  xor     ecx, ecx
0x18000655e  mov     rax, [rax+10h]
0x180006562  jmp     loc_180006418
0x180006567  mov     rdx, [rdi]
0x18000656a  mov     rcx, rdi
0x18000656d  mov     rax, [rdx]
0x180006570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006575  mov     eax, 0FFFFFFFFh
0x18000657a  lock xadd [rdi+0Ch], eax
0x18000657f  cmp     eax, 1
0x180006582  jnz     loc_18000632C
0x180006588  mov     rax, [rdi]
0x18000658b  mov     rcx, rdi
0x18000658e  mov     rax, [rax+8]
0x180006592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006597  jmp     loc_18000632C
0x18000659c  mov     rax, [r8+10h]
0x1800065a0  cmp     byte ptr [rax+18h], 0
0x1800065a4  jz      loc_180007260
0x1800065aa  mov     r8, [rcx+10h]
0x1800065ae  cmp     rdx, r8
0x1800065b1  jnz     short loc_1800065F6
0x1800065b3  mov     rdx, rcx
0x1800065b6  mov     rax, [r8]
0x1800065b9  mov     [rcx+10h], rax
0x1800065bd  mov     rax, [r8]
0x1800065c0  cmp     byte ptr [rax+19h], 0
0x1800065c4  jnz     short loc_1800065CA
0x1800065c6  mov     [rax+8], rcx
0x1800065ca  mov     rax, [rcx+8]
0x1800065ce  mov     [r8+8], rax
0x1800065d2  mov     rax, [r14]
0x1800065d5  cmp     rcx, [rax+8]
0x1800065d9  jz      loc_1800073D5
0x1800065df  mov     rax, [rcx+8]
0x1800065e3  cmp     rcx, [rax]
0x1800065e6  jnz     loc_18000736F
0x1800065ec  mov     [rax], r8
0x1800065ef  mov     [r8], rcx
0x1800065f2  mov     [rcx+8], r8
0x1800065f6  mov     rax, [rdx+8]
0x1800065fa  mov     byte ptr [rax+18h], 1
0x1800065fe  mov     rax, [rdx+8]
0x180006602  mov     rcx, [rax+8]
0x180006606  mov     byte ptr [rcx+18h], 0
0x18000660a  mov     rax, [rdx+8]
0x18000660e  mov     rcx, [rax+8]
0x180006612  mov     r8, [rcx]
0x180006615  mov     rax, [r8+10h]
0x180006619  mov     [rcx], rax
0x18000661c  mov     rax, [r8+10h]
0x180006620  cmp     byte ptr [rax+19h], 0
0x180006624  jz      loc_1800072A2
0x18000662a  mov     rax, [rcx+8]
0x18000662e  mov     [r8+8], rax
0x180006632  mov     rax, [r14]
0x180006635  cmp     rcx, [rax+8]
0x180006639  jz      loc_180007318
0x18000663f  mov     rax, [rcx+8]
0x180006643  cmp     rcx, [rax+10h]
0x180006647  jz      loc_18000733C
0x18000664d  mov     [rax], r8
0x180006650  mov     [r8+10h], rcx
0x180006654  mov     [rcx+8], r8
0x180006658  mov     rax, [rdx+8]
0x18000665c  cmp     byte ptr [rax+18h], 0
0x180006660  jz      loc_18000646A
0x180006666  mov     rax, [r11+8]
0x18000666a  mov     byte ptr [rax+18h], 1
0x18000666e  mov     rbx, qword ptr [rsp+0C8h+var_98+8]
0x180006673  test    rbx, rbx
0x180006676  jz      short loc_18000668D
0x180006678  mov     edi, 0FFFFFFFFh
0x18000667d  mov     eax, edi
0x18000667f  lock xadd [rbx+8], eax
0x180006684  cmp     eax, 1
0x180006687  jz      loc_180006F07
0x18000668d  mov     rbx, [rsp+0C8h+arg_8]
  ... truncated ...
```

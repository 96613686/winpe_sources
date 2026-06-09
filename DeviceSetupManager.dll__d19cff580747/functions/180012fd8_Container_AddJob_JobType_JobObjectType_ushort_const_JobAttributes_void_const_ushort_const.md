# Container::_AddJob(JobType,JobObjectType,ushort const *,JobAttributes,void const *,ushort const *)

- ea: `0x180012fd8`
- end: `0x180013703`
- name: `?_AddJob@Container@@AEAAXW4JobType@@W4JobObjectType@@PEBGW4JobAttributes@@PEBX2@Z`
- size: `1835`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002fc30`
- `0x180030268`

## callees

- `0x18000a9c0`
- `0x180011cbc`
- `0x180011fdc`
- `0x180012a08`
- `0x180012cbc`
- `0x180012d54`
- `0x180012d90`
- `0x180012fd8`
- `0x18001370c`
- `0x180013744`
- `0x1800137fc`
- `0x180013864`
- `0x180013898`
- `0x1800138e0`
- `0x180013900`
- `0x180013958`
- `0x180013c1c`
- `0x180013d38`
- `0x180017334`
- `0x18001af70`
- `0x18001baa8`
- `0x180026874`
- `0x180028ac8`
- `0x180028ba4`
- `0x1800292c8`
- `0x18002f50c`
- `0x18002f89c`
- `0x180030598`
- `0x180030c98`
- `0x180030cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800136d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013032`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013032`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001331d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001331d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013480`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013480`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013259`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013259`

## string_xrefs

- `0x180013096`: `onecoreuap\base\devices\setup\dsm\service\container.cpp`
- `0x18001320b`: `onecoreuap\base\devices\setup\dsm\service\container.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Container::_AddJob(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int16 *a7)
{
  char v9; // r15
  __int64 v10; // rbx
  int v11; // edi
  __int64 v12; // r12
  int v13; // r14d
  int v14; // r8d
  __int64 v15; // r8
  std::_Ref_count_base **v16; // rax
  __int64 v17; // rcx
  std::_Ref_count_base *v18; // rdi
  __int64 *v19; // rbx
  unsigned __int16 *v20; // rcx
  int v21; // eax
  __int64 *v22; // rdi
  __int64 *v23; // rax
  __int64 v24; // r15
  int v25; // eax
  int v26; // r9d
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // r9
  unsigned int i; // ebx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r9
  _QWORD *v34; // rax
  std::_Ref_count_base *v35; // rdi
  __int64 v36; // rdi
  __int64 v37; // rcx
  _QWORD *v38; // rbx
  _QWORD *v39; // r15
  _QWORD *v40; // r15
  __int64 v41; // rdx
  float v42; // xmm0_4
  __int64 v43; // rcx
  float v44; // xmm1_4
  __int64 v45; // rax
  __int64 v46; // rax
  _QWORD *v47; // rcx
  __int64 v48; // rdi
  __int64 v49; // rax
  _QWORD *v50; // rdx
  std::_Ref_count_base *v51; // rcx
  int v52; // r9d
  int v53; // ebx
  int bIgnoreCase; // [rsp+20h] [rbp-A1h]
  int v55; // [rsp+40h] [rbp-81h] BYREF
  __int64 *v56; // [rsp+48h] [rbp-79h] BYREF
  _QWORD *v57; // [rsp+50h] [rbp-71h]
  unsigned __int16 *Src; // [rsp+58h] [rbp-69h] BYREF
  std::_Ref_count_base *v59; // [rsp+60h] [rbp-61h]
  int v60; // [rsp+68h] [rbp-59h]
  std::_Ref_count_base *v61[2]; // [rsp+70h] [rbp-51h] BYREF
  char v62[16]; // [rsp+80h] [rbp-41h] BYREF
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-31h]
  __int64 v64; // [rsp+98h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-19h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v55 = a2;
  v9 = a5;
  v60 = a5;
  *(_QWORD *)v62 = a6;
  Src = a7;
  v10 = a1 + 144;
  SRWLock = (PSRWLOCK)(a1 + 144);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 144));
  v64 = v10;
  if ( *(_BYTE *)(a1 + 484) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_LS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_e4da29ff9f693f33f1216703bf495596_Traceguids,
        a1 + 16,
        v55,
        a4);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\container.cpp",
      (const char *)0x80004004LL,
      bIgnoreCase);
  }
  v11 = v55;
  if ( v55 == 1 )
  {
    *(_BYTE *)(a1 + 484) = 1;
    Container::_CancelJobs((Container *)a1);
    v11 = v55;
  }
  *(_OWORD *)v61 = 0;
  v12 = -1;
  v13 = 2;
  if ( v11 == 2 )
  {
    std::wstring::wstring(pvar, a4);
    std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(
      a1 + 240,
      &v56,
      pvar);
    std::wstring::~wstring(pvar);
    if ( v56 == *(__int64 **)(a1 + 248) )
    {
LABEL_34:
      v11 = v55;
LABEL_35:
      v25 = std::enable_shared_from_this<Container>::shared_from_this(a1, &v56);
      Job::Create((unsigned int)&Src, v25, v11, v26, a4, v9, v62[0], (__int64)Src);
      v27 = *(_QWORD *)(a1 + 152) + 24LL * (unsigned int)Container::_MapJobTypeToLevel((unsigned int)v55);
      v28 = *(_QWORD *)(v27 + 8);
      if ( v28 == *(_QWORD *)(v27 + 16) )
      {
        std::vector<std::shared_ptr<Job>>::_Emplace_reallocate<std::shared_ptr<Job> const &>(
          v27,
          *(_QWORD *)(v27 + 8),
          &Src);
      }
      else
      {
        std::shared_ptr<Container>::shared_ptr<Container>(v28, &Src);
        *(_QWORD *)(v29 + 8) += 16LL;
      }
      if ( v55 != 2 )
      {
        if ( v55 == 3 )
        {
          std::wstring::wstring(pvar, a4);
          v34 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Job>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Job>>>,0>>::_Try_emplace<std::wstring,>(
                            a1 + 304,
                            v62,
                            pvar);
          std::shared_ptr<Job>::operator=(*v34 + 48LL, &Src);
          std::wstring::~wstring(pvar);
        }
        else
        {
          v31 = std::_Hash<std::_Umap_traits<enum JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<enum JobType,std::hash<enum JobType>,std::equal_to<enum JobType>>,std::allocator<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::_Try_emplace<enum JobType const &,>(
                  a1 + 368,
                  v62,
                  &v55);
          v32 = *(_QWORD *)(*(_QWORD *)v31 + 32LL);
          if ( v32 == *(_QWORD *)(*(_QWORD *)v31 + 40LL) )
          {
            std::vector<std::shared_ptr<Job>>::_Emplace_reallocate<std::shared_ptr<Job> const &>(
              *(_QWORD *)v31 + 24LL,
              *(_QWORD *)(*(_QWORD *)v31 + 32LL),
              &Src);
          }
          else
          {
            std::shared_ptr<Container>::shared_ptr<Container>(v32, &Src);
            *(_QWORD *)(v33 + 32) += 16LL;
          }
        }
        v35 = v59;
LABEL_85:
        ++*(_DWORD *)(a1 + 432);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_LS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_e4da29ff9f693f33f1216703bf495596_Traceguids,
            a1 + 16,
            v55,
            a4);
        }
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
        goto LABEL_101;
      }
      *(_OWORD *)pvar = 0;
      v66 = 0;
      do
        ++v12;
      while ( *(_WORD *)(a4 + 2 * v12) );
      std::wstring::_Construct<1,unsigned short const *>(pvar, a4);
      v36 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)pvar);
      v37 = *(_QWORD *)(a1 + 264);
      v38 = *(_QWORD **)(v37 + 16 * (*(_QWORD *)(a1 + 288) & v36) + 8);
      v39 = *(_QWORD **)(a1 + 248);
      if ( v38 != v39 )
      {
        v40 = *(_QWORD **)(v37 + 16 * (*(_QWORD *)(a1 + 288) & v36));
        while ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                                   v37,
                                   pvar,
                                   v38 + 2) )
        {
          if ( v38 == v40 )
          {
            v39 = v38;
            goto LABEL_62;
          }
          v38 = (_QWORD *)v38[1];
        }
        goto LABEL_79;
      }
LABEL_62:
      if ( *(_QWORD *)(a1 + 256) == 0x3FFFFFFFFFFFFFFLL )
        std::_Xlength_error("unordered_map/set too long");
      v56 = (__int64 *)(a1 + 248);
      v57 = 0;
      v38 = operator new(0x40u);
      v57 = v38;
      *(_QWORD *)v62 = pvar;
      ____0V__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std__V__tuple___V_1__0A___Z_S___pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__shared_ptr_VDriverRecoveryRecord___2__std__AEAA_AEAV__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
        v38 + 2,
        v62);
      v41 = *(_QWORD *)(a1 + 256) + 1LL;
      if ( v41 < 0 )
        v42 = (float)(v41 & 1 | (unsigned int)((unsigned __int64)v41 >> 1))
            + (float)(v41 & 1 | (unsigned int)((unsigned __int64)v41 >> 1));
      else
        v42 = (float)(int)v41;
      v43 = *(_QWORD *)(a1 + 296);
      if ( v43 < 0 )
      {
        v45 = *(_QWORD *)(a1 + 296) & 1LL | ((unsigned __int64)v43 >> 1);
        v44 = (float)(int)v45 + (float)(int)v45;
      }
      else
      {
        v44 = (float)(int)v43;
      }
      if ( (float)(v42 / v44) > *(float *)(a1 + 240) )
      {
        v46 = std::_Hash<std::_Umap_traits<std::wstring,enum TASK_COMPLETION_STATUS,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum TASK_COMPLETION_STATUS>>,0>>::_Desired_grow_bucket_count(a1 + 240);
        std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Job>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Job>>>,0>>::_Forced_rehash(
          a1 + 240,
          v46);
        v39 = *(_QWORD **)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Job>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Job>>>,0>>::_Find_last<std::wstring>(
                            a1 + 240,
                            &v64,
                            v38 + 2,
                            v36);
      }
      v57 = 0;
      v47 = (_QWORD *)v39[1];
      ++*(_QWORD *)(a1 + 256);
      *v38 = v39;
      v38[1] = v47;
      *v47 = v38;
      v39[1] = v38;
      v48 = 2 * (*(_QWORD *)(a1 + 288) & v36);
      v49 = *(_QWORD *)(a1 + 264);
      v50 = *(_QWORD **)(v49 + 8 * v48);
      if ( v50 == *(_QWORD **)(a1 + 248) )
      {
        *(_QWORD *)(v49 + 8 * v48) = v38;
LABEL_77:
        *(_QWORD *)(v49 + 8 * v48 + 8) = v38;
        goto LABEL_78;
      }
      if ( v50 == v39 )
      {
        *(_QWORD *)(v49 + 8 * v48) = v38;
      }
      else if ( *(_QWORD **)(v49 + 8 * v48 + 8) == v47 )
      {
        goto LABEL_77;
      }
LABEL_78:
      std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<Job>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<Job>>,void *>>>(&v56);
LABEL_79:
      v35 = v59;
      if ( v59 )
        _InterlockedIncrement((volatile signed __int32 *)v59 + 2);
      v38[6] = Src;
      v51 = (std::_Ref_count_base *)v38[7];
      v38[7] = v35;
      if ( v51 )
        std::_Ref_count_base::_Decref(v51);
      if ( *((_QWORD *)&v66 + 1) > 7u )
        std::_Deallocate<16>(pvar[0], 2LL * *((_QWORD *)&v66 + 1) + 2);
      goto LABEL_85;
    }
    std::shared_ptr<Job>::operator=(v61, v56 + 6);
    goto LABEL_32;
  }
  if ( v11 != 3 )
  {
    std::_Hash<std::_Umap_traits<enum JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<enum JobType,std::hash<enum JobType>,std::equal_to<enum JobType>>,std::allocator<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::find(
      a1 + 368,
      &v56,
      &v55);
    v19 = v56;
    if ( v56 == *(__int64 **)(a1 + 376) )
      goto LABEL_35;
    *(_OWORD *)pvar = 0;
    *(_QWORD *)&v66 = 0;
    v20 = Src;
    if ( Src )
    {
      v21 = MultiSzToPropVariant(Src, (struct tagPROPVARIANT *)pvar);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\container.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCase);
      v20 = Src;
    }
    v22 = (__int64 *)v19[3];
    v23 = (__int64 *)v19[4];
    v56 = v23;
    while ( v22 != v23 )
    {
      v24 = *v22;
      if ( v20 )
      {
        if ( *(_WORD *)(v24 + 80) )
        {
          if ( LODWORD(pvar[1]) == *(_DWORD *)(v24 + 88) )
          {
            for ( i = 0; i < LODWORD(pvar[1]); ++i )
            {
              if ( CompareStringOrdinal(
                     *(LPCWCH *)(v66 + 8LL * i),
                     -1,
                     *(LPCWCH *)(*(_QWORD *)(v24 + 96) + 8LL * i),
                     -1,
                     1) != 2 )
              {
                v20 = Src;
                goto LABEL_44;
              }
            }
LABEL_30:
            std::shared_ptr<Job>::operator=(v61, v22);
            break;
          }
LABEL_44:
          v23 = v56;
        }
      }
      else if ( *(_BYTE *)(v24 + 104) )
      {
        goto LABEL_30;
      }
      v22 += 2;
    }
    PropVariantClear(pvar);
    v9 = v60;
LABEL_32:
    v18 = v61[0];
    goto LABEL_33;
  }
  *(_OWORD *)pvar = 0;
  v66 = 0;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(a4 + 2 * v15) );
  std::wstring::_Construct<1,unsigned short const *>(pvar, a4);
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(
    a1 + 304,
    &v56,
    pvar);
  if ( *((_QWORD *)&v66 + 1) > 7u )
    std::_Deallocate<16>(pvar[0], 2LL * *((_QWORD *)&v66 + 1) + 2);
  v16 = (std::_Ref_count_base **)v56;
  if ( v56 == *(__int64 **)(a1 + 312) )
    goto LABEL_34;
  v17 = v56[7];
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
  v18 = v16[6];
  v61[0] = v18;
  v61[1] = v16[7];
LABEL_33:
  if ( !v18 )
    goto LABEL_34;
  v52 = *((_DWORD *)v18 + 6);
  if ( (((unsigned __int8)v52 | (unsigned __int8)v9) & 2) == 0 )
    v13 = (((unsigned __int8)v52 | (unsigned __int8)v9) & 1) != 0;
  v53 = v13 | 0x10;
  if ( ((unsigned __int8)v52 & (unsigned __int8)v9 & 0x10) == 0 )
    v53 = v13;
  if ( v53 != v52 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_LL_guid_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), a1 + 16, v14, v52, v53, a1 + 16, v55, a4);
    }
    *((_DWORD *)v18 + 6) = v53;
  }
LABEL_101:
  if ( v61[1] )
    std::_Ref_count_base::_Decref(v61[1]);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x180012fd8  mov     [rsp-8+arg_10], rbx
0x180012fdd  push    rbp
0x180012fde  push    rsi
0x180012fdf  push    rdi
0x180012fe0  push    r12
0x180012fe2  push    r13
0x180012fe4  push    r14
0x180012fe6  push    r15
0x180012fe8  lea     rbp, [rsp-0Fh]
0x180012fed  sub     rsp, 0D0h
0x180012ff4  mov     rax, cs:__security_cookie
0x180012ffb  xor     rax, rsp
0x180012ffe  mov     [rbp+3Fh+var_38], rax
0x180013002  mov     r13, r9
0x180013005  mov     rsi, rcx
0x180013008  mov     [rsp+100h+var_C0], edx
0x18001300c  mov     r15d, [rbp+3Fh+arg_20]
0x180013010  mov     [rbp+3Fh+var_98], r15d
0x180013014  mov     rax, [rbp+3Fh+arg_28]
0x180013018  mov     qword ptr [rbp+3Fh+var_80], rax
0x18001301c  mov     rax, [rbp+3Fh+arg_30]
0x180013020  mov     [rbp+3Fh+Src], rax
0x180013024  lea     rbx, [rcx+90h]
0x18001302b  mov     [rbp+3Fh+SRWLock], rbx
0x18001302f  mov     rcx, rbx; SRWLock
0x180013032  call    cs:__imp_AcquireSRWLockExclusive
0x180013038  mov     [rbp+3Fh+var_68], rbx
0x18001303c  xor     ebx, ebx
0x18001303e  cmp     [rsi+1E4h], bl
0x180013044  jz      short loc_1800130A8
0x180013046  lea     rax, WPP_GLOBAL_Control
0x18001304d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013054  cmp     rcx, rax
0x180013057  jz      short loc_18001308C
0x180013059  test    dword ptr [rcx+1Ch], 200h
0x180013060  jz      short loc_18001308C
0x180013062  cmp     byte ptr [rcx+19h], 4
0x180013066  jb      short loc_18001308C
0x180013068  lea     r9, [rsi+10h]
0x18001306c  lea     edx, [rbx+11h]
0x18001306f  mov     [rsp+100h+var_D8], r13
0x180013074  mov     eax, [rsp+100h+var_C0]
0x180013078  mov     [rsp+100h+bIgnoreCase], eax; int
0x18001307c  lea     r8, WPP_e4da29ff9f693f33f1216703bf495596_Traceguids
0x180013083  mov     rcx, [rcx+10h]
0x180013087  call    WPP_SF__guid_LS
0x18001308c  mov     rcx, [rbp+47h]; this
0x180013090  mov     r9d, 80004004h; char *
0x180013096  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001309d  mov     edx, 204h; void *
0x1800130a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800130a8  mov     edi, [rsp+100h+var_C0]
0x1800130ac  cmp     edi, 1
0x1800130af  jnz     short loc_1800130C4
0x1800130b1  mov     [rsi+1E4h], dil
0x1800130b8  mov     rcx, rsi; this
0x1800130bb  call    ?_CancelJobs@Container@@AEAAXXZ; Container::_CancelJobs(void)
0x1800130c0  mov     edi, [rsp+100h+var_C0]
0x1800130c4  xorps   xmm0, xmm0
0x1800130c7  movdqu  xmmword ptr [rbp+3Fh+var_90], xmm0
0x1800130cc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800130d0  lea     r14d, [r12+3]
0x1800130d5  cmp     edi, r14d
0x1800130d8  jnz     short loc_180013126
0x1800130da  mov     rdx, r13
0x1800130dd  lea     rcx, [rbp+3Fh+pvar]
0x1800130e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800130e6  lea     rcx, [rsi+0F0h]
0x1800130ed  lea     r8, [rbp+3Fh+pvar]
0x1800130f1  lea     rdx, [rbp+3Fh+var_B8]
0x1800130f5  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(std::wstring const &)
0x1800130fa  lea     rcx, [rbp+3Fh+pvar]
0x1800130fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013103  mov     rdx, [rbp+3Fh+var_B8]
0x180013107  cmp     rdx, [rsi+0F8h]
0x18001310e  jz      loc_180013272
0x180013114  add     rdx, 30h ; '0'
0x180013118  lea     rcx, [rbp+3Fh+var_90]
0x18001311c  call    ??4?$shared_ptr@VJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Job>::operator=(std::shared_ptr<Job> const &)
0x180013121  jmp     loc_180013265
0x180013126  cmp     edi, 3
0x180013129  jnz     loc_1800131B7
0x18001312f  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x180013133  xorps   xmm1, xmm1
0x180013136  movdqu  [rbp+3Fh+var_48], xmm1
0x18001313b  mov     r8, r12
0x18001313e  inc     r8
0x180013141  cmp     [r13+r8*2+0], bx
0x180013147  jnz     short loc_18001313E
0x180013149  mov     rdx, r13
0x18001314c  lea     rcx, [rbp+3Fh+pvar]
0x180013150  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013155  lea     rcx, [rsi+130h]
0x18001315c  lea     r8, [rbp+3Fh+pvar]
0x180013160  lea     rdx, [rbp+3Fh+var_B8]
0x180013164  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::find(std::wstring const &)
0x180013169  mov     rdx, qword ptr [rbp+3Fh+var_48+8]
0x18001316d  cmp     rdx, 7
0x180013171  jbe     short loc_180013184
0x180013173  lea     rdx, ds:2[rdx*2]
0x18001317b  mov     rcx, [rbp+3Fh+pvar]
0x18001317f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013184  mov     rax, [rbp+3Fh+var_B8]
0x180013188  cmp     rax, [rsi+138h]
0x18001318f  jz      loc_180013272
0x180013195  mov     rcx, [rax+38h]
0x180013199  test    rcx, rcx
0x18001319c  jz      short loc_1800131A2
0x18001319e  lock inc dword ptr [rcx+8]
0x1800131a2  mov     rdi, [rax+30h]
0x1800131a6  mov     [rbp+3Fh+var_90], rdi
0x1800131aa  mov     rcx, [rax+38h]
0x1800131ae  mov     [rbp+3Fh+var_90+8], rcx
0x1800131b2  jmp     loc_180013269
0x1800131b7  lea     rcx, [rsi+170h]
0x1800131be  lea     r8, [rsp+100h+var_C0]
0x1800131c3  lea     rdx, [rbp+3Fh+var_B8]
0x1800131c7  call    ?find@?$_Hash@V?$_Umap_traits@W4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@V?$_Uhash_compare@W4JobType@@U?$hash@W4JobType@@@std@@U?$equal_to@W4JobType@@@3@@3@V?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBW4JobType@@@Z; std::_Hash<std::_Umap_traits<JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<JobType,std::hash<JobType>,std::equal_to<JobType>>,std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::find(JobType const &)
0x1800131cc  mov     rbx, [rbp+3Fh+var_B8]
0x1800131d0  cmp     rbx, [rsi+178h]
0x1800131d7  jnz     short loc_1800131E0
0x1800131d9  xor     ebx, ebx
0x1800131db  jmp     loc_180013276
0x1800131e0  xor     eax, eax
0x1800131e2  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800131e6  mov     qword ptr [rbp+3Fh+var_48], rax
0x1800131ea  mov     rcx, [rbp+3Fh+Src]; Src
0x1800131ee  xor     edx, edx
0x1800131f0  test    rcx, rcx
0x1800131f3  jz      short loc_180013221
0x1800131f5  lea     rdx, [rbp+3Fh+pvar]; struct tagPROPVARIANT *
0x1800131f9  call    ?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z; MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)
0x1800131fe  mov     rcx, [rbp+47h]; this
0x180013202  xor     edx, edx
0x180013204  test    eax, eax
0x180013206  jns     short loc_18001321D
0x180013208  mov     r9d, eax; char *
0x18001320b  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180013212  mov     edx, 22Fh; void *
0x180013217  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001321d  mov     rcx, [rbp+3Fh+Src]
0x180013221  mov     rdi, [rbx+18h]
0x180013225  mov     rax, [rbx+20h]
0x180013229  mov     [rbp+3Fh+var_B8], rax
0x18001322d  cmp     rdi, rax
0x180013230  jz      short loc_180013255
0x180013232  mov     r15, [rdi]
0x180013235  test    rcx, rcx
0x180013238  jnz     loc_1800132E2
0x18001323e  cmp     [r15+68h], dl
0x180013242  jz      loc_180013336
0x180013248  mov     rdx, rdi
0x18001324b  lea     rcx, [rbp+3Fh+var_90]
0x18001324f  call    ??4?$shared_ptr@VJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Job>::operator=(std::shared_ptr<Job> const &)
0x180013254  nop
0x180013255  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180013259  call    cs:__imp_PropVariantClear
0x18001325f  mov     r15d, [rbp+3Fh+var_98]
0x180013263  xor     ebx, ebx
0x180013265  mov     rdi, [rbp+3Fh+var_90]
0x180013269  test    rdi, rdi
0x18001326c  jnz     loc_18001363F
0x180013272  mov     edi, [rsp+100h+var_C0]
0x180013276  lea     rdx, [rbp+3Fh+var_B8]
0x18001327a  mov     rcx, rsi
0x18001327d  call    ?shared_from_this@?$enable_shared_from_this@VContainer@@@std@@QEAA?AV?$shared_ptr@VContainer@@@2@XZ; std::enable_shared_from_this<Container>::shared_from_this(void)
0x180013282  mov     rcx, [rbp+3Fh+Src]
0x180013286  mov     [rsp+100h+var_C8], rcx
0x18001328b  mov     rcx, qword ptr [rbp+3Fh+var_80]
0x18001328f  mov     [rsp+100h+var_D0], rcx
0x180013294  mov     dword ptr [rsp+100h+var_D8], r15d
0x180013299  mov     qword ptr [rsp+100h+bIgnoreCase], r13
0x18001329e  mov     r8d, edi
0x1800132a1  mov     rdx, rax
0x1800132a4  lea     rcx, [rbp+3Fh+Src]
0x1800132a8  call    ?Create@Job@@SA?AV?$shared_ptr@VJob@@@std@@V?$shared_ptr@VContainer@@@3@W4JobType@@W4JobObjectType@@PEBGW4JobAttributes@@PEBX3@Z; Job::Create(std::shared_ptr<Container>,JobType,JobObjectType,ushort const *,JobAttributes,void const *,ushort const *)
0x1800132ad  nop
0x1800132ae  mov     ecx, [rsp+100h+var_C0]
0x1800132b2  call    ?_MapJobTypeToLevel@Container@@CAKW4JobType@@@Z; Container::_MapJobTypeToLevel(JobType)
0x1800132b7  mov     eax, eax
0x1800132b9  lea     rcx, [rax+rax*2]
0x1800132bd  mov     rax, [rsi+98h]
0x1800132c4  lea     r9, [rax+rcx*8]
0x1800132c8  mov     rcx, [r9+8]
0x1800132cc  cmp     rcx, [r9+10h]
0x1800132d0  jz      short loc_18001333F
0x1800132d2  lea     rdx, [rbp+3Fh+Src]
0x1800132d6  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x1800132db  add     qword ptr [r9+8], 10h
0x1800132e0  jmp     short loc_18001334E
0x1800132e2  cmp     [r15+50h], dx
0x1800132e7  jz      short loc_180013336
0x1800132e9  mov     eax, [r15+58h]
0x1800132ed  cmp     dword ptr [rbp+3Fh+pvar+8], eax
0x1800132f0  jnz     short loc_180013332
0x1800132f2  mov     ebx, edx
0x1800132f4  cmp     ebx, dword ptr [rbp+3Fh+pvar+8]
0x1800132f7  jnb     loc_180013248
0x1800132fd  mov     eax, ebx
0x1800132ff  mov     r8, [r15+60h]
0x180013303  mov     [rsp+100h+bIgnoreCase], 1; bIgnoreCase
0x18001330b  mov     r9d, r12d; cchCount2
0x18001330e  mov     r8, [r8+rax*8]; lpString2
0x180013312  mov     edx, r12d; cchCount1
0x180013315  mov     rcx, qword ptr [rbp+3Fh+var_48]
0x180013319  mov     rcx, [rcx+rax*8]; lpString1
0x18001331d  call    cs:__imp_CompareStringOrdinal
0x180013323  cmp     eax, r14d
0x180013326  jnz     short loc_18001332C
0x180013328  inc     ebx
0x18001332a  jmp     short loc_1800132F4
0x18001332c  mov     rcx, [rbp+3Fh+Src]
0x180013330  xor     edx, edx
0x180013332  mov     rax, [rbp+3Fh+var_B8]
0x180013336  add     rdi, 10h
0x18001333a  jmp     loc_18001322D
0x18001333f  lea     r8, [rbp+3Fh+Src]
0x180013343  mov     rdx, rcx
0x180013346  mov     rcx, r9
0x180013349  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VJob@@@std@@@?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VJob@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Job>>::_Emplace_reallocate<std::shared_ptr<Job> const &>(std::shared_ptr<Job> * const,std::shared_ptr<Job> const &)
0x18001334e  mov     ecx, [rsp+100h+var_C0]
0x180013352  sub     ecx, r14d
0x180013355  jz      loc_1800133E8
0x18001335b  cmp     ecx, 1
0x18001335e  jz      short loc_1800133A4
0x180013360  lea     rcx, [rsi+170h]
0x180013367  lea     r8, [rsp+100h+var_C0]
0x18001336c  lea     rdx, [rbp+3Fh+var_80]
0x180013370  call    ??$_Try_emplace@AEBW4JobType@@$$V@?$_Hash@V?$_Umap_traits@W4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@V?$_Uhash_compare@W4JobType@@U?$hash@W4JobType@@@std@@U?$equal_to@W4JobType@@@3@@3@V?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEBW4JobType@@@Z; std::_Hash<std::_Umap_traits<JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<JobType,std::hash<JobType>,std::equal_to<JobType>>,std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::_Try_emplace<JobType const &,>(JobType const &)
0x180013375  mov     r9, [rax]
0x180013378  mov     rcx, [r9+20h]
0x18001337c  cmp     rcx, [r9+28h]
0x180013380  jz      short loc_180013392
0x180013382  lea     rdx, [rbp+3Fh+Src]
0x180013386  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x18001338b  add     qword ptr [r9+20h], 10h
0x180013390  jmp     short loc_1800133DF
0x180013392  lea     r8, [rbp+3Fh+Src]
0x180013396  mov     rdx, rcx
0x180013399  lea     rcx, [r9+18h]
0x18001339d  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VJob@@@std@@@?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VJob@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Job>>::_Emplace_reallocate<std::shared_ptr<Job> const &>(std::shared_ptr<Job> * const,std::shared_ptr<Job> const &)
0x1800133a2  jmp     short loc_1800133DF
0x1800133a4  mov     rdx, r13
0x1800133a7  lea     rcx, [rbp+3Fh+pvar]
0x1800133ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800133b0  nop
0x1800133b1  lea     rcx, [rsi+130h]
0x1800133b8  lea     r8, [rbp+3Fh+pvar]
0x1800133bc  lea     rdx, [rbp+3Fh+var_80]
0x1800133c0  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Job>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Job>>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800133c5  mov     rcx, [rax]
0x1800133c8  add     rcx, 30h ; '0'
0x1800133cc  lea     rdx, [rbp+3Fh+Src]
0x1800133d0  call    ??4?$shared_ptr@VJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Job>::operator=(std::shared_ptr<Job> const &)
0x1800133d5  nop
0x1800133d6  lea     rcx, [rbp+3Fh+pvar]
0x1800133da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800133df  mov     rdi, [rbp+3Fh+var_A0]
0x1800133e3  jmp     loc_1800135DD
0x1800133e8  lea     r14, [rsi+0F0h]
0x1800133ef  xorps   xmm0, xmm0
0x1800133f2  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800133f6  xorps   xmm1, xmm1
0x1800133f9  movdqu  [rbp+3Fh+var_48], xmm1
0x1800133fe  inc     r12
0x180013401  cmp     [r13+r12*2+0], bx
0x180013407  jnz     short loc_1800133FE
0x180013409  mov     r8, r12
0x18001340c  mov     rdx, r13
0x18001340f  lea     rcx, [rbp+3Fh+pvar]
0x180013413  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013418  nop
0x180013419  lea     rcx, [rbp+3Fh+pvar]; unsigned __int8 *
0x18001341d  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180013422  mov     rdi, rax
0x180013425  and     rax, [r14+30h]
0x180013429  add     rax, rax
0x18001342c  mov     rcx, [r14+18h]
0x180013430  mov     rbx, [rcx+rax*8+8]
0x180013435  lea     r12, [r14+8]
0x180013439  mov     r15, [r12]
0x18001343d  cmp     rbx, r15
0x180013440  jz      short loc_180013469
0x180013442  mov     r15, [rcx+rax*8]
0x180013446  lea     r8, [rbx+10h]
0x18001344a  lea     rdx, [rbp+3Fh+pvar]
0x18001344e  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180013453  test    al, al
0x180013455  jz      loc_18001359A
0x18001345b  cmp     rbx, r15
0x18001345e  jz      short loc_180013466
0x180013460  mov     rbx, [rbx+8]
0x180013464  jmp     short loc_180013446
0x180013466  mov     r15, rbx
0x180013469  mov     rax, 3FFFFFFFFFFFFFFh
0x180013473  cmp     [r14+10h], rax
0x180013477  jnz     short loc_180013487
0x180013479  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180013480  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180013487  mov     [rbp+3Fh+var_B8], r12
  ... truncated ...
```

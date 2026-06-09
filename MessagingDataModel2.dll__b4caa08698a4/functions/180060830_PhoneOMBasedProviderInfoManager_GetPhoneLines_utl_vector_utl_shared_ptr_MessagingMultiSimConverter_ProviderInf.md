# PhoneOMBasedProviderInfoManager::_GetPhoneLines(utl::vector<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>,utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>> &)

- ea: `0x180060830`
- end: `0x180060eef`
- name: `?_GetPhoneLines@PhoneOMBasedProviderInfoManager@@MEAAJAEAV?$vector@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@V?$allocator@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@@2@@utl@@@Z`
- size: `1727`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000163c`
- `0x180001c4c`
- `0x180002128`
- `0x1800065c8`
- `0x180056c9c`
- `0x180056d1c`
- `0x180056df0`
- `0x1800595d4`
- `0x18005f244`
- `0x18005f2fc`
- `0x18005f374`
- `0x18005f48c`
- `0x18006004c`
- `0x180060830`
- `0x1800c68f6`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180060d33`
- `msvcrt!memcpy_s` at `0x180060d33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060a70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060bf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060e11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060a70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060bf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060e11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060d8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060d8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006089a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800608de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060ee1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006089a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800608de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060ee1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060d15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060d15`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180060993`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180060993`
- `PhoneOm!PhoneGetCellularApiComponentInfo` at `0x180060c92`
- `PhoneOm!PhoneGetCellularApiComponentInfo` at `0x180060c92`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x18006096b`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x18006096b`
- `PhoneOm!PhoneGetLines` at `0x1800608b0`
- `PhoneOm!PhoneGetLines` at `0x1800608b0`

## pseudocode

```c
__int64 __fastcall PhoneOMBasedProviderInfoManager::_GetPhoneLines(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdi
  __int64 v5; // r8
  int Lines; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v12; // rbx
  unsigned int v13; // r12d
  __int128 *v14; // rbx
  int ProviderLineInfo; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  utl::_RefCountBase *v19; // r13
  int v20; // ecx
  utl::_RefCountBase *v21; // rcx
  struct _RTL_CRITICAL_SECTION *v22; // rdi
  __int64 v23; // rsi
  __int64 v24; // rbx
  utl::_RefCountBase *v25; // rcx
  struct IUnknown **v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  __int128 v29; // xmm0
  __int64 v30; // rsi
  __int64 v31; // rcx
  __int64 v32; // rcx
  int i; // ebx
  int v34; // r11d
  __int128 v35; // xmm0
  _OWORD *v36; // rax
  __m128i v37; // xmm0
  unsigned __int64 v38; // xmm0_8
  utl::_RefCountBase *v39; // rsi
  int CellularApiComponentInfo; // eax
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdi
  HLOCAL v45; // rax
  HLOCAL v46; // rbx
  void *v47; // rcx
  __int128 v48; // xmm0
  int v49; // ecx
  struct _RTL_CRITICAL_SECTION *v50; // r13
  __int64 v51; // rdi
  __int64 v52; // rbx
  struct IUnknown **v53; // rax
  __int128 v54; // xmm0
  __int64 v55; // rcx
  _OWORD *v56; // rax
  __m128i v57; // xmm0
  unsigned __int64 v58; // xmm0_8
  char v59[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v60; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v61; // [rsp+48h] [rbp-B8h]
  unsigned int v62; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v63[16]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v64[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v65[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v66[24]; // [rsp+88h] [rbp-78h] BYREF
  int v67; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v68; // [rsp+A4h] [rbp-5Ch]
  int v69; // [rsp+C4h] [rbp-3Ch]
  int v70; // [rsp+C8h] [rbp-38h]
  _BYTE Source[12]; // [rsp+CCh] [rbp-34h] BYREF
  SIZE_T uBytes; // [rsp+D8h] [rbp-28h]
  utl::_RefCountBase *v73[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v74; // [rsp+140h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+148h] [rbp+48h] BYREF
  __int128 v76; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v77[148]; // [rsp+160h] [rbp+60h] BYREF
  int v78; // [rsp+1F4h] [rbp+F4h]
  _BYTE v79[1320]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE Buf2[276]; // [rsp+7C8h] [rbp+6C8h] BYREF
  int v81; // [rsp+8DCh] [rbp+7DCh]

  v61 = a1;
  v3 = *a2;
  v4 = a1;
  hMem = 0;
  v74 = 0;
  v5 = a2[1] - v3;
  a2[1] = v3;
  utl::_RangeDestroyApc<utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>>(a1, v3, v5 >> 4);
  if ( hMem )
    LocalFree(hMem);
  hMem = 0;
  Lines = PhoneGetLines(&hMem, &v74);
  v10 = Lines;
  if ( Lines < 0 )
  {
    Log_HREvent_35(Lines);
    if ( hMem )
      LocalFree(hMem);
    return v10;
  }
  if ( (unsigned int)dword_1800FD5F0 > 4 )
  {
    v62 = v74;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (int)byte_1800EC6B3,
      v8,
      v9,
      (__int64)&v62);
  }
  v12 = 0;
  v62 = 0;
  if ( !v74 )
  {
LABEL_30:
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  v13 = -2147024882;
  while ( 1 )
  {
    memset_0(v79, 0, 0x650u);
    memset_0(v77, 0, 0x13Cu);
    v14 = (__int128 *)((char *)hMem + 16 * v12);
    *(_QWORD *)&v60 = v14;
    ProviderLineInfo = PhoneGetProviderLineInfo(v14, v79);
    if ( ProviderLineInfo >= 0 )
    {
      ProviderLineInfo = PhoneGetProviderLineServiceInfo(v14, v77);
      if ( ProviderLineInfo >= 0 )
        break;
    }
    Log_HREvent_35(ProviderLineInfo);
LABEL_29:
    v12 = v62 + 1;
    v62 = v12;
    if ( (unsigned int)v12 >= v74 )
      goto LABEL_30;
  }
  if ( memcmp_0(CellularLineType, Buf2, 0x10u) )
  {
    if ( (unsigned int)dword_1800FD5F0 > 4 )
    {
      *(_QWORD *)&v60 = Buf2;
      *(_QWORD *)&v76 = "CellularLineType != lineInfo.lineType";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v16,
        (int)&unk_1800EC658,
        v17,
        v18,
        (const unsigned __int16 **)&v76,
        (__int64 *)&v60);
    }
    goto LABEL_29;
  }
  if ( v81 == -1 && v78 == 4 )
  {
    v59[0] = 0;
    *(_OWORD *)v73 = 0;
    utl::make_shared<MessagingMultiSimConverter::ProviderInfo,_GUID const &,bool>(v73, v14, v59);
    v19 = v73[0];
    if ( !v73[0] )
    {
LABEL_18:
      v20 = -2147024882;
LABEL_19:
      Log_HREvent_35(v20);
      goto LABEL_20;
    }
    v22 = (struct _RTL_CRITICAL_SECTION *)(v4 + 64);
    v76 = *v14;
    EnterCriticalSection(v22);
    v23 = v61 + 456;
    *(_QWORD *)&v60 = 0;
    utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::find<void>(
      v61 + 456,
      (void ***)&v60,
      &v76);
    v24 = v60;
    if ( v23 == (_QWORD)v60 )
    {
LABEL_24:
      LeaveCriticalSection(v22);
    }
    else
    {
      v26 = *(struct IUnknown ***)(v60 + 40);
      if ( *((struct IUnknown **)v19 + 6) != *v26 )
        ATL::AtlComPtrAssign((struct IUnknown **)v19 + 6, *v26);
      v27 = *(_QWORD *)(v24 + 40);
      v28 = v61;
      *(_QWORD *)&v60 = 0;
      v29 = *(_OWORD *)(v27 + 8);
      v30 = v61 + 520;
      v31 = v61 + 520;
      *(_OWORD *)((char *)v19 + 72) = v29;
      v76 = v29;
      utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::find<void>(
        v31,
        (void ***)&v60,
        &v76);
      if ( (_QWORD)v60 == v30 )
      {
        v32 = v28 + 488;
        LODWORD(v76) = 101;
        for ( i = 101; ; ++i )
        {
          *(_QWORD *)&v60 = 0;
          utl::_Tree<unsigned long,utl::pair<unsigned long const,_GUID>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,_GUID>>,0>::find<void>(
            v32,
            &v60,
            &v76);
          if ( (_QWORD)v60 == v32 )
            break;
          LODWORD(v76) = i + 1;
          if ( (unsigned int)(i + 1) > 0xC8 )
            goto LABEL_24;
        }
        *((_DWORD *)v19 + 22) = v34;
        v60 = *(_OWORD *)((char *)v19 + 72);
        utl::_Tree<unsigned long,utl::pair<unsigned long const,_GUID>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,_GUID>>,0>::emplace<unsigned long &,_GUID,0>(
          v32,
          v63,
          &v76,
          &v60);
        v60 = *(_OWORD *)((char *)v19 + 72);
        utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::emplace<_GUID,unsigned long,0>(
          v30,
          (__int64)v64,
          &v60,
          &v76);
      }
      else
      {
        *((_DWORD *)v19 + 22) = *(_DWORD *)(v60 + 40);
      }
      v35 = *(_OWORD *)((char *)v19 + 72);
      LODWORD(v76) = *((_DWORD *)v19 + 22);
      v60 = v35;
      utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::emplace<_GUID,unsigned long,0>(
        v30,
        (__int64)v65,
        &v60,
        &v76);
      LeaveCriticalSection(v22);
      v36 = (_OWORD *)a2[1];
      if ( v36 != (_OWORD *)a2[2] )
      {
        v37 = *(__m128i *)v73;
        *v36 = *(_OWORD *)v73;
        v38 = _mm_srli_si128(v37, 8).m128i_u64[0];
        v25 = (utl::_RefCountBase *)v38;
        if ( v38 )
          _InterlockedIncrement((volatile signed __int32 *)(v38 + 8));
        a2[1] += 16;
        goto LABEL_26;
      }
      if ( !(unsigned __int8)utl::vector<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>,utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>>::_PushBackOne2<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo> const &>(
                               a2,
                               v73) )
        goto LABEL_77;
    }
    v25 = v73[1];
LABEL_26:
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
    v4 = v61;
    goto LABEL_29;
  }
  v59[0] = 1;
  *(_OWORD *)v73 = 0;
  utl::make_shared<MessagingMultiSimConverter::ProviderInfo,_GUID const &,bool>(v73, v14, v59);
  v39 = v73[0];
  if ( !v73[0] )
    goto LABEL_18;
  memset_0(&v67, 0, 0x8Cu);
  CellularApiComponentInfo = PhoneGetCellularApiComponentInfo(v14, &v67);
  if ( CellularApiComponentInfo < 0 )
  {
    v20 = CellularApiComponentInfo;
    goto LABEL_19;
  }
  if ( (v67 & 7) != 7 )
  {
    if ( (unsigned int)dword_1800FD5F0 > 4 )
    {
      LODWORD(v76) = v67;
      LODWORD(v60) = 7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v41,
        (int)&unk_1800EC5F0,
        v42,
        v43,
        (__int64)&v60,
        (__int64)&v76);
    }
    v20 = -2147024875;
    goto LABEL_19;
  }
  if ( (v67 & 8) == 0 )
  {
LABEL_61:
    v48 = v68;
    *((_DWORD *)v39 + 4) = v70;
    *(_OWORD *)v39 = v48;
    v49 = v70;
    if ( v70 )
      v49 = v70 + 9;
    *((_DWORD *)v39 + 22) = v49;
    v50 = (struct _RTL_CRITICAL_SECTION *)(v4 + 64);
    *((_DWORD *)v39 + 10) = v69;
    v76 = *v14;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 64));
    v51 = v4 + 456;
    *(_QWORD *)&v60 = 0;
    utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::find<void>(
      v51,
      (void ***)&v60,
      &v76);
    v52 = v60;
    if ( v51 == (_QWORD)v60 )
    {
      v4 = v61;
    }
    else
    {
      v53 = *(struct IUnknown ***)(v60 + 40);
      if ( *((struct IUnknown **)v39 + 6) != *v53 )
        ATL::AtlComPtrAssign((struct IUnknown **)v39 + 6, *v53);
      v4 = v61;
      v54 = *(_OWORD *)(*(_QWORD *)(v52 + 40) + 8LL);
      v55 = v61 + 520;
      *(_OWORD *)((char *)v39 + 72) = v54;
      LODWORD(v60) = *((_DWORD *)v39 + 22);
      v76 = v54;
      utl::_Tree<_GUID,utl::pair<_GUID const,unsigned long>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,unsigned long>>,0>::emplace<_GUID,unsigned long,0>(
        v55,
        (__int64)v66,
        &v76,
        &v60);
    }
    LeaveCriticalSection(v50);
    v56 = (_OWORD *)a2[1];
    if ( v56 != (_OWORD *)a2[2] )
    {
      v57 = *(__m128i *)v73;
      *v56 = *(_OWORD *)v73;
      v58 = _mm_srli_si128(v57, 8).m128i_u64[0];
      v21 = (utl::_RefCountBase *)v58;
      if ( v58 )
        _InterlockedIncrement((volatile signed __int32 *)(v58 + 8));
      a2[1] += 16;
      goto LABEL_21;
    }
    if ( !(unsigned __int8)utl::vector<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>,utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>>::_PushBackOne2<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo> const &>(
                             a2,
                             v73) )
      goto LABEL_77;
LABEL_20:
    v21 = v73[1];
LABEL_21:
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    goto LABEL_29;
  }
  v44 = (unsigned int)uBytes;
  if ( (_DWORD)uBytes )
  {
    v45 = LocalAlloc(0, (unsigned int)uBytes);
    v46 = v45;
    if ( !v45 )
      goto LABEL_77;
    memcpy_s(v45, (unsigned int)v44, Source, (unsigned int)v44);
    v47 = (void *)*((_QWORD *)v39 + 3);
    *((_QWORD *)v39 + 3) = v46;
    *((_QWORD *)v39 + 4) = v44;
    if ( v47 )
      LocalFree(v47);
    v4 = v61;
    v14 = (__int128 *)v60;
    goto LABEL_61;
  }
  v13 = -2147024809;
LABEL_77:
  Log_HREvent_35(v13);
  if ( v73[1] )
    utl::_RefCountBase::_DecStrong(v73[1]);
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x180060830  mov     [rsp-8+arg_10], rbx
0x180060835  push    rbp
0x180060836  push    rsi
0x180060837  push    rdi
0x180060838  push    r12
0x18006083a  push    r13
0x18006083c  push    r14
0x18006083e  push    r15
0x180060840  lea     rbp, [rsp-800h]
0x180060848  sub     rsp, 900h
0x18006084f  mov     rax, cs:__security_cookie
0x180060856  xor     rax, rsp
0x180060859  mov     [rbp+830h+var_40], rax
0x180060860  mov     r15, rdx
0x180060863  mov     [rsp+930h+var_8E8], rcx
0x180060868  mov     rdx, [rdx]
0x18006086b  mov     rdi, rcx
0x18006086e  mov     [rbp+830h+hMem], 0
0x180060876  mov     [rbp+830h+var_7F0], 0
0x18006087d  mov     r8, [r15+8]
0x180060881  sub     r8, rdx
0x180060884  mov     [r15+8], rdx
0x180060888  sar     r8, 4
0x18006088c  call    ??$_RangeDestroyApc@V?$allocator@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@@0@PEAV?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>>(utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>> &,utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo> *,unsigned __int64)
0x180060891  mov     rcx, [rbp+830h+hMem]; hMem
0x180060895  test    rcx, rcx
0x180060898  jz      short loc_1800608A0
0x18006089a  call    cs:__imp_LocalFree
0x1800608a0  lea     rdx, [rbp+830h+var_7F0]
0x1800608a4  mov     [rbp+830h+hMem], 0
0x1800608ac  lea     rcx, [rbp+830h+hMem]
0x1800608b0  call    cs:__imp_PhoneGetLines
0x1800608b6  mov     ebx, eax
0x1800608b8  test    eax, eax
0x1800608ba  jns     short loc_1800608EB
0x1800608bc  mov     r9d, 16Dh
0x1800608c2  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800608c9  mov     edx, 1
0x1800608ce  mov     ecx, eax; int
0x1800608d0  call    Log_HREvent_35
0x1800608d5  mov     rcx, [rbp+830h+hMem]; hMem
0x1800608d9  test    rcx, rcx
0x1800608dc  jz      short loc_1800608E4
0x1800608de  call    cs:__imp_LocalFree
0x1800608e4  mov     eax, ebx
0x1800608e6  jmp     loc_180060AAD
0x1800608eb  mov     eax, cs:dword_1800FD5F0
0x1800608f1  cmp     eax, 4
0x1800608f4  jbe     short loc_180060913
0x1800608f6  mov     eax, [rbp+830h+var_7F0]
0x1800608f9  lea     rdx, byte_1800EC6B3
0x180060900  mov     [rsp+930h+var_8E0], eax
0x180060904  lea     rax, [rsp+930h+var_8E0]
0x180060909  mov     [rsp+930h+var_910], rax
0x18006090e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180060913  xor     ebx, ebx
0x180060915  mov     [rsp+930h+var_8E0], ebx
0x180060919  cmp     [rbp+830h+var_7F0], ebx
0x18006091c  jbe     loc_180060A9C
0x180060922  lea     r14, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\messagingom"...
0x180060929  mov     r12d, 8007000Eh
0x18006092f  xor     edx, edx; Val
0x180060931  lea     rcx, [rbp+830h+var_690]; void *
0x180060938  mov     r8d, 650h; Size
0x18006093e  call    memset_0
0x180060943  xor     edx, edx; Val
0x180060945  lea     rcx, [rbp+830h+var_7D0]; void *
0x180060949  mov     r8d, 13Ch; Size
0x18006094f  call    memset_0
0x180060954  shl     rbx, 4
0x180060958  lea     rdx, [rbp+830h+var_690]
0x18006095f  add     rbx, [rbp+830h+hMem]
0x180060963  mov     rcx, rbx
0x180060966  mov     qword ptr [rsp+930h+var_8F8], rbx
0x18006096b  call    cs:__imp_PhoneGetProviderLineInfo
0x180060971  test    eax, eax
0x180060973  jns     short loc_18006098C
0x180060975  mov     r9d, 17Dh
0x18006097b  mov     r8, r14
0x18006097e  xor     edx, edx
0x180060980  mov     ecx, eax; int
0x180060982  call    Log_HREvent_35
0x180060987  jmp     loc_180060A89
0x18006098c  lea     rdx, [rbp+830h+var_7D0]
0x180060990  mov     rcx, rbx
0x180060993  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x180060999  test    eax, eax
0x18006099b  jns     short loc_1800609A5
0x18006099d  mov     r9d, 185h
0x1800609a3  jmp     short loc_18006097B
0x1800609a5  mov     r8d, 10h; Size
0x1800609ab  lea     rdx, [rbp+830h+Buf2]; Buf2
0x1800609b2  lea     rcx, CellularLineType; Buf1
0x1800609b9  call    memcmp_0
0x1800609be  test    eax, eax
0x1800609c0  jnz     loc_180060E64
0x1800609c6  cmp     [rbp+830h+var_54], 0FFFFFFFFh
0x1800609cd  jnz     loc_180060C49
0x1800609d3  cmp     [rbp+830h+var_73C], 4
0x1800609da  jnz     loc_180060C49
0x1800609e0  xorps   xmm0, xmm0
0x1800609e3  mov     [rsp+930h+var_900], al
0x1800609e7  lea     r8, [rsp+930h+var_900]
0x1800609ec  mov     rdx, rbx
0x1800609ef  lea     rcx, [rbp+830h+var_800]
0x1800609f3  movups  xmmword ptr [rbp+830h+var_800], xmm0
0x1800609f7  call    ??$make_shared@VProviderInfo@MessagingMultiSimConverter@@AEBU_GUID@@_N@utl@@YA?AV?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@0@AEBU_GUID@@$$QEA_N@Z; utl::make_shared<MessagingMultiSimConverter::ProviderInfo,_GUID const &,bool>(_GUID const &,bool &&)
0x1800609fc  mov     r13, [rbp+830h+var_800]
0x180060a00  test    r13, r13
0x180060a03  jnz     short loc_180060A28
0x180060a05  mov     r9d, 19Dh
0x180060a0b  xor     edx, edx
0x180060a0d  mov     ecx, r12d; int
0x180060a10  mov     r8, r14
0x180060a13  call    Log_HREvent_35
0x180060a18  mov     rcx, [rbp+830h+var_800+8]; this
0x180060a1c  test    rcx, rcx
0x180060a1f  jz      short loc_180060A89
0x180060a21  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180060a26  jmp     short loc_180060A89
0x180060a28  movups  xmm0, xmmword ptr [rbx]
0x180060a2b  add     rdi, 40h ; '@'
0x180060a2f  mov     rcx, rdi; lpCriticalSection
0x180060a32  movdqu  [rbp+830h+var_7E0], xmm0
0x180060a37  call    cs:__imp_EnterCriticalSection
0x180060a3d  mov     rsi, [rsp+930h+var_8E8]
0x180060a42  lea     r8, [rbp+830h+var_7E0]
0x180060a46  add     rsi, 1C8h
0x180060a4d  mov     qword ptr [rsp+930h+var_8F8], 0
0x180060a56  mov     rcx, rsi
0x180060a59  lea     rdx, [rsp+930h+var_8F8]
0x180060a5e  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@K@utl@@UGuidComparator@MessagingMultiSimConverter@@V?$allocator@U?$pair@$$CBU_GUID@@K@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@K@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,ulong>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,ulong>>,0>::find<void>(_GUID const &)
0x180060a63  mov     rbx, qword ptr [rsp+930h+var_8F8]
0x180060a68  cmp     rsi, rbx
0x180060a6b  jnz     short loc_180060AD7
0x180060a6d  mov     rcx, rdi; lpCriticalSection
0x180060a70  call    cs:__imp_LeaveCriticalSection
0x180060a76  mov     rcx, [rbp+830h+var_800+8]; this
0x180060a7a  test    rcx, rcx
0x180060a7d  jz      short loc_180060A84
0x180060a7f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180060a84  mov     rdi, [rsp+930h+var_8E8]
0x180060a89  mov     ebx, [rsp+930h+var_8E0]
0x180060a8d  inc     ebx
0x180060a8f  mov     [rsp+930h+var_8E0], ebx
0x180060a93  cmp     ebx, [rbp+830h+var_7F0]
0x180060a96  jb      loc_18006092F
0x180060a9c  mov     rcx, [rbp+830h+hMem]; hMem
0x180060aa0  test    rcx, rcx
0x180060aa3  jz      short loc_180060AAB
0x180060aa5  call    cs:__imp_LocalFree
0x180060aab  xor     eax, eax
0x180060aad  mov     rcx, [rbp+830h+var_40]
0x180060ab4  xor     rcx, rsp; StackCookie
0x180060ab7  call    __security_check_cookie
0x180060abc  mov     rbx, [rsp+930h+arg_10]
0x180060ac4  add     rsp, 900h
0x180060acb  pop     r15
0x180060acd  pop     r14
0x180060acf  pop     r13
0x180060ad1  pop     r12
0x180060ad3  pop     rdi
0x180060ad4  pop     rsi
0x180060ad5  pop     rbp
0x180060ad6  retn
0x180060ad7  mov     rax, [rbx+28h]
0x180060adb  lea     rcx, [r13+30h]; struct IUnknown **
0x180060adf  mov     rdx, [rax]; struct IUnknown *
0x180060ae2  cmp     [rcx], rdx
0x180060ae5  jz      short loc_180060AEC
0x180060ae7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180060aec  mov     rax, [rbx+28h]
0x180060af0  lea     r8, [rbp+830h+var_7E0]
0x180060af4  mov     rbx, [rsp+930h+var_8E8]
0x180060af9  lea     rdx, [rsp+930h+var_8F8]
0x180060afe  mov     qword ptr [rsp+930h+var_8F8], 0
0x180060b07  movups  xmm0, xmmword ptr [rax+8]
0x180060b0b  lea     rsi, [rbx+208h]
0x180060b12  mov     rcx, rsi
0x180060b15  movdqu  xmmword ptr [r13+48h], xmm0
0x180060b1b  movdqa  [rbp+830h+var_7E0], xmm0
0x180060b20  call    ??$find@X@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@K@utl@@UGuidComparator@MessagingMultiSimConverter@@V?$allocator@U?$pair@$$CBU_GUID@@K@utl@@@3@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBU_GUID@@K@utl@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,ulong>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,ulong>>,0>::find<void>(_GUID const &)
0x180060b25  mov     rax, qword ptr [rsp+930h+var_8F8]
0x180060b2a  cmp     rax, rsi
0x180060b2d  jz      short loc_180060B3B
0x180060b2f  mov     ecx, [rax+28h]
0x180060b32  mov     [r13+58h], ecx
0x180060b36  jmp     loc_180060BCA
0x180060b3b  mov     eax, 65h ; 'e'
0x180060b40  lea     rcx, [rbx+1E8h]
0x180060b47  mov     r11d, eax
0x180060b4a  mov     dword ptr [rbp+830h+var_7E0], eax
0x180060b4d  mov     ebx, eax
0x180060b4f  lea     r8, [rbp+830h+var_7E0]
0x180060b53  mov     qword ptr [rsp+930h+var_8F8], 0
0x180060b5c  lea     rdx, [rsp+930h+var_8F8]
0x180060b61  call    ??$find@X@?$_Tree@KU?$pair@$$CBKU_GUID@@@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKU_GUID@@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBKU_GUID@@@utl@@@1@AEBK@Z; utl::_Tree<ulong,utl::pair<ulong const,_GUID>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,_GUID>>,0>::find<void>(ulong const &)
0x180060b66  cmp     qword ptr [rsp+930h+var_8F8], rcx
0x180060b6b  jz      short loc_180060B87
0x180060b6d  lea     r11d, [rbx+1]
0x180060b71  mov     dword ptr [rbp+830h+var_7E0], r11d
0x180060b75  cmp     r11d, 0C8h
0x180060b7c  ja      loc_180060A6D
0x180060b82  mov     ebx, r11d
0x180060b85  jmp     short loc_180060B4F
0x180060b87  mov     [r13+58h], r11d
0x180060b8b  lea     r9, [rsp+930h+var_8F8]
0x180060b90  movups  xmm0, xmmword ptr [r13+48h]
0x180060b95  lea     r8, [rbp+830h+var_7E0]
0x180060b99  lea     rdx, [rsp+930h+var_8D8]
0x180060b9e  movdqu  [rsp+930h+var_8F8], xmm0
0x180060ba4  call    ??$emplace@AEAKU_GUID@@$0A@@?$_Tree@KU?$pair@$$CBKU_GUID@@@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBKU_GUID@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBKU_GUID@@@utl@@@utl@@_N@1@AEAK$$QEAU_GUID@@@Z; utl::_Tree<ulong,utl::pair<ulong const,_GUID>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,_GUID>>,0>::emplace<ulong &,_GUID,0>(ulong &,_GUID &&)
0x180060ba9  movups  xmm0, xmmword ptr [r13+48h]
0x180060bae  lea     r9, [rbp+830h+var_7E0]
0x180060bb2  mov     rcx, rsi
0x180060bb5  lea     r8, [rsp+930h+var_8F8]
0x180060bba  lea     rdx, [rsp+930h+var_8C8]
0x180060bbf  movdqu  [rsp+930h+var_8F8], xmm0
0x180060bc5  call    ??$emplace@U_GUID@@K$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@K@utl@@UGuidComparator@MessagingMultiSimConverter@@V?$allocator@U?$pair@$$CBU_GUID@@K@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@K@utl@@@utl@@_N@1@$$QEAU_GUID@@$$QEAK@Z; utl::_Tree<_GUID,utl::pair<_GUID const,ulong>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,ulong>>,0>::emplace<_GUID,ulong,0>(_GUID &&,ulong &&)
0x180060bca  movups  xmm0, xmmword ptr [r13+48h]
0x180060bcf  mov     eax, [r13+58h]
0x180060bd3  lea     r9, [rbp+830h+var_7E0]
0x180060bd7  lea     r8, [rsp+930h+var_8F8]
0x180060bdc  mov     dword ptr [rbp+830h+var_7E0], eax
0x180060bdf  lea     rdx, [rsp+930h+var_8B8]
0x180060be4  mov     rcx, rsi
0x180060be7  movdqu  [rsp+930h+var_8F8], xmm0
0x180060bed  call    ??$emplace@U_GUID@@K$0A@@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@K@utl@@UGuidComparator@MessagingMultiSimConverter@@V?$allocator@U?$pair@$$CBU_GUID@@K@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBU_GUID@@K@utl@@@utl@@_N@1@$$QEAU_GUID@@$$QEAK@Z; utl::_Tree<_GUID,utl::pair<_GUID const,ulong>,MessagingMultiSimConverter::GuidComparator,utl::allocator<utl::pair<_GUID const,ulong>>,0>::emplace<_GUID,ulong,0>(_GUID &&,ulong &&)
0x180060bf2  mov     rcx, rdi; lpCriticalSection
0x180060bf5  call    cs:__imp_LeaveCriticalSection
0x180060bfb  mov     rax, [r15+8]
0x180060bff  cmp     rax, [r15+10h]
0x180060c03  jz      short loc_180060C2A
0x180060c05  movups  xmm0, xmmword ptr [rbp+830h+var_800]
0x180060c09  movdqu  xmmword ptr [rax], xmm0
0x180060c0d  psrldq  xmm0, 8
0x180060c12  movq    rcx, xmm0
0x180060c17  test    rcx, rcx
0x180060c1a  jz      short loc_180060C20
0x180060c1c  lock inc dword ptr [rcx+8]
0x180060c20  add     qword ptr [r15+8], 10h
0x180060c25  jmp     loc_180060A7A
0x180060c2a  lea     rdx, [rbp+830h+var_800]
0x180060c2e  mov     rcx, r15
0x180060c31  call    ??$_PushBackOne2@AEBV?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@@?$vector@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@V?$allocator@V?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@utl@@@2@@utl@@AEAA_NAEBV?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@1@@Z; utl::vector<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>,utl::allocator<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo>>>::_PushBackOne2<utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo> const &>(utl::shared_ptr<MessagingMultiSimConverter::ProviderInfo> const &)
0x180060c36  test    al, al
0x180060c38  jnz     loc_180060A76
0x180060c3e  mov     r9d, 1D4h
0x180060c44  jmp     loc_180060E60
0x180060c49  xorps   xmm0, xmm0
0x180060c4c  mov     [rsp+930h+var_900], 1
0x180060c51  lea     r8, [rsp+930h+var_900]
0x180060c56  mov     rdx, rbx
0x180060c59  lea     rcx, [rbp+830h+var_800]
0x180060c5d  movups  xmmword ptr [rbp+830h+var_800], xmm0
0x180060c61  call    ??$make_shared@VProviderInfo@MessagingMultiSimConverter@@AEBU_GUID@@_N@utl@@YA?AV?$shared_ptr@VProviderInfo@MessagingMultiSimConverter@@@0@AEBU_GUID@@$$QEA_N@Z; utl::make_shared<MessagingMultiSimConverter::ProviderInfo,_GUID const &,bool>(_GUID const &,bool &&)
0x180060c66  mov     rsi, [rbp+830h+var_800]
0x180060c6a  xor     edx, edx; Val
0x180060c6c  test    rsi, rsi
0x180060c6f  jnz     short loc_180060C7C
0x180060c71  mov     r9d, 1DDh
0x180060c77  jmp     loc_180060A0D
0x180060c7c  mov     r8d, 8Ch; Size
0x180060c82  lea     rcx, [rbp+830h+var_890]; void *
0x180060c86  call    memset_0
0x180060c8b  lea     rdx, [rbp+830h+var_890]
0x180060c8f  mov     rcx, rbx
0x180060c92  call    cs:__imp_PhoneGetCellularApiComponentInfo
0x180060c98  test    eax, eax
0x180060c9a  jns     short loc_180060CAB
0x180060c9c  mov     r9d, 1E7h
0x180060ca2  xor     edx, edx
0x180060ca4  mov     ecx, eax
0x180060ca6  jmp     loc_180060A10
0x180060cab  mov     eax, [rbp+830h+var_890]
0x180060cae  and     eax, 7
0x180060cb1  cmp     al, 7
0x180060cb3  jz      short loc_180060CFF
0x180060cb5  mov     eax, cs:dword_1800FD5F0
0x180060cbb  cmp     eax, 4
0x180060cbe  jbe     short loc_180060CED
0x180060cc0  mov     eax, [rbp+830h+var_890]
0x180060cc3  lea     rdx, unk_1800EC5F0
0x180060cca  mov     dword ptr [rbp+830h+var_7E0], eax
0x180060ccd  lea     rax, [rbp+830h+var_7E0]
0x180060cd1  mov     [rsp+930h+var_908], rax
0x180060cd6  lea     rax, [rsp+930h+var_8F8]
0x180060cdb  mov     [rsp+930h+var_910], rax
0x180060ce0  mov     dword ptr [rsp+930h+var_8F8], 7
0x180060ce8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180060ced  mov     r9d, 1F4h
0x180060cf3  xor     edx, edx
0x180060cf5  mov     ecx, 80070015h
0x180060cfa  jmp     loc_180060A10
0x180060cff  test    byte ptr [rbp+830h+var_890], 8
0x180060d03  jz      short loc_180060D5A
0x180060d05  mov     edi, dword ptr [rbp+830h+uBytes]
0x180060d08  test    rdi, rdi
0x180060d0b  jz      loc_180060EAE
0x180060d11  mov     edx, edi; uBytes
  ... truncated ...
```

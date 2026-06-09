# CTemplateCacheManager::Load(int,ushort const *,ulong,CHitObj *,CTemplate * *,int *)

- ea: `0x1800108d0`
- end: `0x180011553`
- name: `?Load@CTemplateCacheManager@@QEAAJHPEBGKPEAVCHitObj@@PEAPEAVCTemplate@@PEAH@Z`
- size: `3203`
- prototype: `int(CTemplateCacheManager *__hidden this, int, const unsigned __int16 *, unsigned int, struct CHitObj *, struct CTemplate **, int *)`
- caller_count: `3`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ca50`
- `0x1800444b8`
- `0x180045ffc`

## callees

- `0x1800076e0`
- `0x1800108d0`
- `0x180011800`
- `0x1800121c0`
- `0x180012810`
- `0x180012a20`
- `0x180012b70`
- `0x1800133f8`
- `0x180013450`
- `0x1800134f0`
- `0x180013604`
- `0x180019e7c`
- `0x180019f44`
- `0x18001a600`
- `0x18001a768`
- `0x180034900`
- `0x180034a54`
- `0x180034bd0`
- `0x180034db8`
- `0x180034ebc`
- `0x180034fc0`
- `0x18003525c`
- `0x1800495c0`
- `0x18005b608`
- `0x180060094`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010c43`
- `KERNEL32!HeapFree` at `0x1800113b3`
- `KERNEL32!HeapFree` at `0x180010c43`
- `KERNEL32!HeapFree` at `0x1800113b3`
- `KERNEL32!LeaveCriticalSection` at `0x180010cd2`
- `KERNEL32!LeaveCriticalSection` at `0x180010cf6`
- `KERNEL32!LeaveCriticalSection` at `0x180010da9`
- `KERNEL32!LeaveCriticalSection` at `0x180010f5f`
- `KERNEL32!LeaveCriticalSection` at `0x180010f90`
- `KERNEL32!LeaveCriticalSection` at `0x180011030`
- `KERNEL32!LeaveCriticalSection` at `0x1800112cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800112d8`
- `KERNEL32!LeaveCriticalSection` at `0x180011406`
- `KERNEL32!LeaveCriticalSection` at `0x1800114df`
- `KERNEL32!LeaveCriticalSection` at `0x180010cd2`
- `KERNEL32!LeaveCriticalSection` at `0x180010cf6`
- `KERNEL32!LeaveCriticalSection` at `0x180010da9`
- `KERNEL32!LeaveCriticalSection` at `0x180010f5f`
- `KERNEL32!LeaveCriticalSection` at `0x180010f90`
- `KERNEL32!LeaveCriticalSection` at `0x180011030`
- `KERNEL32!LeaveCriticalSection` at `0x1800112cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800112d8`
- `KERNEL32!LeaveCriticalSection` at `0x180011406`
- `KERNEL32!LeaveCriticalSection` at `0x1800114df`
- `KERNEL32!EnterCriticalSection` at `0x1800109b1`
- `KERNEL32!EnterCriticalSection` at `0x180010d59`
- `KERNEL32!EnterCriticalSection` at `0x180010edf`
- `KERNEL32!EnterCriticalSection` at `0x180010fe3`
- `KERNEL32!EnterCriticalSection` at `0x18001103d`
- `KERNEL32!EnterCriticalSection` at `0x1800111c6`
- `KERNEL32!EnterCriticalSection` at `0x1800111d3`
- `KERNEL32!EnterCriticalSection` at `0x180011492`
- `KERNEL32!EnterCriticalSection` at `0x1800109b1`
- `KERNEL32!EnterCriticalSection` at `0x180010d59`
- `KERNEL32!EnterCriticalSection` at `0x180010edf`
- `KERNEL32!EnterCriticalSection` at `0x180010fe3`
- `KERNEL32!EnterCriticalSection` at `0x18001103d`
- `KERNEL32!EnterCriticalSection` at `0x1800111c6`
- `KERNEL32!EnterCriticalSection` at `0x1800111d3`
- `KERNEL32!EnterCriticalSection` at `0x180011492`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010d03`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010d03`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180010aac`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001117c`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180010aac`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001117c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180010a35`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180010a35`

## pseudocode

```c
__int64 __fastcall CTemplateCacheManager::Load(
        CTemplateCacheManager *this,
        int a2,
        unsigned __int16 *a3,
        int a4,
        struct CIsapiReqInfo **a5,
        struct CTemplate **a6,
        int *a7)
{
  struct CHitObj *v7; // rbx
  __int64 (__fastcall *v8)(CTemplate *, void **); // r15
  struct CIsapiReqInfo *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int (__fastcall *v15)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v16; // rdx
  int v17; // edi
  struct CTemplate *v18; // rcx
  CTemplate **v19; // rsi
  CTemplate *v20; // rax
  char *v21; // rdx
  unsigned int v22; // r8d
  CTemplateCacheManager::CTemplateHashTable *v23; // r15
  volatile signed __int32 *v24; // rax
  volatile signed __int32 *v25; // rax
  CTemplate *v26; // rbx
  int Key; // eax
  volatile signed __int32 *v28; // rax
  CTemplate *v29; // rcx
  CPerfData *v30; // rcx
  CPerfData *v31; // rcx
  volatile signed __int32 *v32; // rax
  CTemplate *v33; // rcx
  int v34; // eax
  char *v35; // rbx
  char *v36; // rdi
  char *v37; // rsi
  CTemplate *v38; // rax
  CTemplate *v39; // rax
  CTemplate *v40; // rdi
  int v41; // ebx
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int (__fastcall *v44)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v45; // rdx
  int v46; // eax
  signed int TransServiceConfig; // r13d
  const struct _GUID *v48; // rdx
  const struct _GUID *v49; // rdx
  const struct _GUID *v50; // rdx
  CTemplate *v51; // rcx
  CTemplateCacheManager::CTemplateHashTable *v52; // rcx
  struct CHitObj *v53; // r12
  CTemplate *v54; // rcx
  char *v55; // rdx
  int v56; // r15d
  CTemplateCacheManager::CTemplateHashTable *v57; // rdi
  __int64 v58; // rsi
  __int64 v59; // rcx
  CPerfData *v60; // rcx
  bool v61; // zf
  unsigned int v62; // edx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r14
  __int64 v67; // rax
  _QWORD *v68; // rcx
  __int64 v69; // rbx
  unsigned __int16 *v70; // rax
  __int64 v71; // r9
  int v72; // edx
  int v73; // r8d
  CPerfData *v74; // rcx
  struct CLruLinkElem *v75; // rbx
  struct CLruLinkElem *v76; // rdi
  unsigned __int16 *v77; // rax
  __int64 v78; // r8
  int v79; // ecx
  int v80; // edx
  CPerfData *v81; // rcx
  CPerfData *v82; // rcx
  CActiveScriptEngine *v83; // r11
  int v84; // eax
  char *v85; // rbx
  char *v86; // rsi
  char *v87; // r14
  CTemplateCacheManager *v88; // rcx
  struct CTemplate **v89; // rsi
  CTemplate *v90; // rbx
  __int64 v91; // rdi
  CTemplate *v92; // rcx
  __int64 v93; // rdx
  __int64 (__fastcall *v95)(CTemplate *, void **); // [rsp+30h] [rbp-30h]
  CTemplate *v96; // [rsp+38h] [rbp-28h] BYREF
  GUID *v97; // [rsp+40h] [rbp-20h] BYREF
  __int128 v98; // [rsp+48h] [rbp-18h]
  int v99; // [rsp+A0h] [rbp+40h] BYREF
  int v100; // [rsp+A4h] [rbp+44h]
  int v101; // [rsp+A8h] [rbp+48h]

  v101 = a2;
  v100 = HIDWORD(this);
  v7 = (struct CHitObj *)a5;
  v8 = 0;
  v99 = 0;
  v12 = 0;
  if ( a5 )
  {
    v12 = a5[8];
    if ( v12 )
    {
      v13 = *((_QWORD *)v12 + 1);
      v97 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v14 = *(_QWORD *)(v13 + 8);
      v15 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v13 + 184);
      v98 = 0;
      if ( v15(v14, 1044, &v97, 0, 0) )
      {
        if ( DWORD2(v98) && DWORD1(v98) >= 4 )
          AspReqEvents::ASP_START_CACHE_ACCESS::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1), v16, a3);
      }
    }
  }
  v17 = 0;
  if ( a2 )
  {
    v18 = *(struct CTemplate **)(*((_QWORD *)v7 + 3) + 136LL);
    if ( v18 )
    {
      v19 = a6;
      *a6 = v18;
      goto LABEL_60;
    }
  }
  else
  {
    v20 = (CTemplate *)*((_QWORD *)v7 + 28);
    if ( v20 )
    {
      v19 = a6;
      *((_QWORD *)v7 + 28) = 0;
      *v19 = v20;
      goto LABEL_60;
    }
  }
  EnterCriticalSection(&stru_180079DF0);
  v23 = lpParameter;
  v17 = 1;
  v97 = (GUID *)a3;
  LODWORD(v98) = a4;
  if ( (dword_18007CB28 & 1) != 0 )
    v24 = (volatile signed __int32 *)(qword_18007CB88 + 148);
  else
    v24 = (volatile signed __int32 *)byte_18007CC28;
  _InterlockedIncrement(v24);
  if ( (dword_18007CB28 & 1) != 0 )
    v25 = (volatile signed __int32 *)(qword_18007CB88 + 112);
  else
    v25 = &dword_18007CC04;
  _InterlockedIncrement(v25);
  v19 = a6;
  if ( !a6 )
  {
    v26 = (CTemplate *)MEMORY[0];
    goto LABEL_33;
  }
  *a6 = 0;
  v96 = 0;
  Key = CLKRHashTable::FindKey(v23, &v97, &v96);
  v26 = v96;
  *v19 = v96;
  if ( Key )
  {
LABEL_33:
    if ( v26 && (*((_BYTE *)v26 + 392) & 2) != 0 )
    {
      v33 = (CTemplate *)*((unsigned int *)v26 + 125);
      v34 = dword_180079E20;
      if ( (_DWORD)v33 != dword_180079E20 )
      {
        *((_DWORD *)v26 + 122) = 1;
        v34 = dword_180079E20;
      }
      if ( *((_DWORD *)v26 + 122)
        && !*((_DWORD *)v26 + 123)
        && ((_DWORD)v33 != v34 && !g_fLazyContentPropDisabled
         || (unsigned int)CTemplate::CheckTTLTimingWindow(v33, *((_DWORD *)v26 + 124), v22)) )
      {
        *((_DWORD *)v26 + 123) = 1;
        v99 = 1;
      }
    }
    v35 = (char *)*((_QWORD *)v23 + 13);
    v36 = (char *)v23 + 96;
    if ( v35 != (char *)v23 + 96 )
    {
      while ( 1 )
      {
        if ( !*((_QWORD *)v35 + 8) )
        {
LABEL_57:
          v19 = a6;
          break;
        }
        v37 = (char *)*((_QWORD *)v35 + 1);
        if ( *((_DWORD *)v35 + 19) == 1 )
        {
          if ( *((_DWORD *)v35 + 20) == 1 )
          {
            ++g_nScavengedPurged;
            goto LABEL_50;
          }
          if ( (unsigned int)CTemplate::PersistData((CTemplate *)v35, v21) )
          {
            ++g_nScavengedPersistFailed;
LABEL_50:
            if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(v23, v35, 0, 0) )
            {
              if ( (v35[392] & 1) != 0 )
                (*(void (__fastcall **)(char *))(*((_QWORD *)v35 + 3) + 16LL))(v35 + 24);
              else
                CTemplate::End((CTemplate *)v35);
            }
            goto LABEL_56;
          }
          ++g_nScavengedPersisted;
          HeapFree(CTemplate::sm_hLargeHeap, 0, *((LPVOID *)v35 + 8));
          *((_QWORD *)v35 + 8) = 0;
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)v35 + 2) + 8LL) = v37;
          *(_QWORD *)(*((_QWORD *)v35 + 1) + 16LL) = *((_QWORD *)v35 + 2);
          *((_QWORD *)v35 + 1) = v35;
          *((_QWORD *)v35 + 2) = v36;
          *((_QWORD *)v35 + 1) = *((_QWORD *)v23 + 13);
          *(_QWORD *)(*((_QWORD *)v23 + 13) + 16LL) = v35;
          *((_QWORD *)v23 + 13) = v35;
        }
LABEL_56:
        v35 = v37;
        if ( v37 == v36 )
          goto LABEL_57;
      }
    }
    v17 = 1;
    v8 = 0;
    goto LABEL_59;
  }
  if ( (dword_18007CB28 & 1) != 0 )
    v28 = (volatile signed __int32 *)(qword_18007CB88 + 108);
  else
    v28 = (volatile signed __int32 *)byte_18007CC00;
  _InterlockedIncrement(v28);
  v29 = *v19;
  if ( (*((_DWORD *)*v19 + 98) & 0x1000) == 0 )
  {
    if ( (dword_18007CB28 & 1) != 0 )
      v32 = (volatile signed __int32 *)(qword_18007CB88 + 144);
    else
      v32 = &dword_18007CC24;
    _InterlockedIncrement(v32);
    goto LABEL_32;
  }
  *(_QWORD *)(*((_QWORD *)v29 + 2) + 8LL) = *((_QWORD *)v29 + 1);
  *(_QWORD *)(*((_QWORD *)v29 + 1) + 16LL) = *((_QWORD *)v29 + 2);
  *((_QWORD *)v29 + 1) = v29;
  *((_QWORD *)v29 + 2) = v29;
  --*((_DWORD *)v23 + 31);
  if ( !(unsigned int)CTemplate::UnPersistData(v29) )
  {
    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v30, 34));
    ++*((_DWORD *)v23 + 30);
LABEL_32:
    v26 = *v19;
    v21 = (char *)v23 + 72;
    *(_QWORD *)(*((_QWORD *)*v19 + 2) + 8LL) = *((_QWORD *)*v19 + 1);
    *(_QWORD *)(*((_QWORD *)v26 + 1) + 16LL) = *((_QWORD *)v26 + 2);
    *((_QWORD *)v26 + 1) = v26;
    *((_QWORD *)v26 + 2) = (char *)v23 + 72;
    *((_QWORD *)v26 + 1) = *((_QWORD *)v23 + 10);
    *(_QWORD *)(*((_QWORD *)v23 + 10) + 16LL) = v26;
    *((_QWORD *)v23 + 10) = v26;
    goto LABEL_33;
  }
  CLKRHashTable::DeleteRecord(v23, *v19);
  (*(void (__fastcall **)(__int64))(*((_QWORD *)*v19 + 3) + 16LL))((__int64)*v19 + 24);
  v8 = 0;
  *v19 = 0;
  _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v31, 25));
LABEL_59:
  v7 = (struct CHitObj *)a5;
LABEL_60:
  if ( *v19 )
  {
    (*(void (__fastcall **)(__int64))(*((_QWORD *)*v19 + 3) + 8LL))((__int64)*v19 + 24);
    *a7 = 1;
    _InterlockedIncrement((volatile signed __int32 *)*v19 + 20);
    if ( v17 )
      LeaveCriticalSection(&stru_180079DF0);
    v8 = (__int64 (__fastcall *)(CTemplate *, void **))CTemplate::Deliver;
    v95 = (__int64 (__fastcall *)(CTemplate *, void **))CTemplate::Deliver;
    goto LABEL_70;
  }
  *a7 = 0;
  LeaveCriticalSection(&stru_180079DF0);
  v38 = (CTemplate *)ALLOC_CACHE_HANDLER::Alloc(CTemplate::sm_pach);
  if ( v38 && (v39 = CTemplate::CTemplate(v38), (v40 = v39) != 0) )
  {
    v95 = 0;
    v97 = (GUID *)a3;
    LODWORD(v98) = a4;
    v41 = CTemplate::Init(v39, v7, v101 != 0, (const struct CTemplateKey *)&v97);
    if ( v41 >= 0 )
    {
      EnterCriticalSection(&stru_180079DF0);
      v97 = (GUID *)a3;
      LODWORD(v98) = a4;
      CTemplateCacheManager::CTemplateHashTable::FindTemplate(lpParameter, &v97, v19, &v99);
      if ( !*v19 )
      {
        CScriptManager::FlushCache(0, a3);
        v52 = lpParameter;
        *v19 = v40;
        CTemplateCacheManager::CTemplateHashTable::InsertTemplate(v52, v40);
        (*(void (__fastcall **)(__int64))(*((_QWORD *)*v19 + 3) + 8LL))((__int64)*v19 + 24);
        if ( !dword_180079F80 )
          *((_DWORD *)*v19 + 98) |= 0x20u;
        LeaveCriticalSection(&stru_180079DF0);
        v8 = CTemplate::Compile;
        v95 = CTemplate::Compile;
LABEL_70:
        if ( v12 )
        {
          v42 = *((_QWORD *)v12 + 1);
          v97 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v43 = *(_QWORD *)(v42 + 8);
          v44 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v42 + 184);
          v98 = 0;
          if ( v44(v43, 1044, &v97, 0, 0) )
          {
            if ( DWORD2(v98) && DWORD1(v98) >= 4 )
              AspReqEvents::ASP_START_COMPILE::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1), v45, a3);
          }
        }
        v46 = v8(*v19, (void **)a5);
        TransServiceConfig = v46;
        if ( v8 == CTemplate::Compile )
        {
          if ( v12 )
          {
            if ( v46 < 0
              && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1),
                                 2u) )
            {
              AspReqEvents::ASP_COMPILE_FAILED::RaiseEvent(
                *((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1),
                v48,
                a3,
                TransServiceConfig);
            }
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1),
                                 4u) )
              AspReqEvents::ASP_END_COMPILE::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1), v49);
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1),
                                 4u) )
              AspReqEvents::ASP_END_CACHE_ACCESS::RaiseEvent(
                *((struct _EXTENSION_CONTROL_BLOCK **)v12 + 1),
                v50,
                TransServiceConfig,
                TransServiceConfig >= 0);
          }
          if ( v8 == CTemplate::Compile && (*((_BYTE *)*v19 + 392) & 4) != 0 )
          {
            EnterCriticalSection(&stru_180079DF0);
            if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(lpParameter, *v19, 0, 1) )
            {
              v51 = *v19;
              if ( (*((_BYTE *)*v19 + 392) & 1) != 0 )
                (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v51 + 3) + 16LL))((_QWORD *)v51 + 3);
              else
                CTemplate::End(v51);
            }
            LeaveCriticalSection(&stru_180079DF0);
            (*(void (__fastcall **)(__int64))(*((_QWORD *)*v19 + 3) + 16LL))((__int64)*v19 + 24);
            *v19 = 0;
            if ( TransServiceConfig >= 0 )
              TransServiceConfig = -2147430395;
          }
        }
        v53 = (struct CHitObj *)a5;
        if ( v99 && *v19 && !CTemplate::ValidateSourceFiles(*v19, a5[8]) )
        {
          EnterCriticalSection(&stru_180079DF0);
          if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(lpParameter, *v19, 0, 1) )
          {
            v54 = *v19;
            if ( (*((_BYTE *)*v19 + 392) & 1) != 0 )
              (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v54 + 3) + 16LL))((_QWORD *)v54 + 3);
            else
              CTemplate::End(v54);
          }
          LeaveCriticalSection(&stru_180079DF0);
        }
        EnterCriticalSection(&stru_180079DF0);
        v56 = 0;
        while ( 1 )
        {
          v57 = lpParameter;
          if ( (CTemplateCacheManager::CTemplateHashTable *)((char *)lpParameter + 72) == *((CTemplateCacheManager::CTemplateHashTable **)lpParameter
                                                                                          + 10)
            || *((_DWORD *)lpParameter + 30) <= (unsigned int)dword_180079F80 )
          {
            break;
          }
          v58 = *((_QWORD *)lpParameter + 11);
          v59 = *(_QWORD *)(v58 + 8);
          if ( v58 != v59 && *(CTemplateCacheManager::CTemplateHashTable **)(v58 + 472) == lpParameter )
          {
            *(_QWORD *)(*(_QWORD *)(v58 + 16) + 8LL) = v59;
            v60 = *(CPerfData **)(v58 + 8);
            *((_QWORD *)v60 + 2) = *(_QWORD *)(v58 + 16);
            v61 = (*(_DWORD *)(v58 + 392) & 0x1000) == 0;
            *(_QWORD *)(v58 + 8) = v58;
            *(_QWORD *)(v58 + 16) = v58;
            if ( v61 )
            {
              if ( (dword_18007CB28 & 1) != 0 )
                _InterlockedDecrement((volatile signed __int32 *)(qword_18007CB88 + 140));
              else
                _InterlockedDecrement((volatile signed __int32 *)byte_18007CC20);
              --*((_DWORD *)v57 + 30);
            }
            else
            {
              --*((_DWORD *)v57 + 31);
            }
            if ( !dword_180079FB8
              || CTemplateCacheManager::m_fFailedToInitPersistCache == 1
              || (v60 = (CPerfData *)*(unsigned int *)(v58 + 392), ((unsigned __int16)v60 & 0x100) != 0)
              || ((unsigned __int16)v60 & 0x4000) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v60, 25));
              CLKRHashTable::DeleteRecord(v57, v58);
            }
            else
            {
              v62 = *((_DWORD *)v57 + 31);
              if ( v62 >= dword_180079FB8 )
                CTemplateCacheManager::CTemplateHashTable::TrimPersistCache(v57, v62 - dword_180079FB8 + 1);
              v63 = *(_QWORD *)(v58 + 8);
              v55 = (char *)v57 + 96;
              v64 = *(_QWORD *)(v58 + 16);
              *(_DWORD *)(v58 + 392) |= 0x1000u;
              *(_QWORD *)(v64 + 8) = v63;
              *(_QWORD *)(*(_QWORD *)(v58 + 8) + 16LL) = *(_QWORD *)(v58 + 16);
              *(_QWORD *)(v58 + 8) = v58;
              *(_QWORD *)(v58 + 16) = (char *)v57 + 96;
              *(_QWORD *)(v58 + 8) = *((_QWORD *)v57 + 13);
              *(_QWORD *)(*((_QWORD *)v57 + 13) + 16LL) = v58;
              ++*((_DWORD *)v57 + 31);
              *((_QWORD *)v57 + 13) = v58;
            }
          }
          v56 = 1;
          if ( (*(_BYTE *)(v58 + 392) & 2) != 0 )
          {
            v65 = *(_QWORD *)(v58 + 272);
            if ( v65 && *(_QWORD *)v65 )
              v66 = *(_QWORD *)(*(_QWORD *)v65 + 8LL);
            else
              v66 = 0;
            if ( byte_18007CC48 )
            {
              EnterCriticalSection(&stru_18007CEA8);
              EnterCriticalSection(&stru_18007CD68);
              v67 = xmmword_18007CDA0;
              if ( (_QWORD)xmmword_18007CDA0 )
              {
                do
                {
                  v68 = *(_QWORD **)(v67 + 64);
                  v69 = *(_QWORD *)(v67 + 32);
                  v70 = (unsigned __int16 *)v68[8];
                  v71 = v66 - (_QWORD)v70;
                  do
                  {
                    v72 = *(unsigned __int16 *)((char *)v70 + v71);
                    v73 = *v70 - v72;
                    if ( v73 )
                      break;
                    ++v70;
                  }
                  while ( v72 );
                  if ( !v73 )
                  {
                    (*(void (__fastcall **)(_QWORD *))(*v68 + 64LL))(v68);
                    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v74, 39));
                  }
                  v67 = v69;
                }
                while ( v69 );
              }
              v75 = xmmword_18007CC60;
              if ( xmmword_18007CC60 )
              {
                do
                {
                  v76 = (struct CLruLinkElem *)*((_QWORD *)v75 + 4);
                  v77 = *(unsigned __int16 **)(*((_QWORD *)v75 + 8) + 64LL);
                  v78 = v66 - (_QWORD)v77;
                  do
                  {
                    v79 = *(unsigned __int16 *)((char *)v77 + v78);
                    v80 = *v77 - v79;
                    if ( v80 )
                      break;
                    ++v77;
                  }
                  while ( v79 );
                  if ( !v80 )
                  {
                    CLinkHash::RemoveElem((CLinkHash *)&qword_18007CC50, v75);
                    _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v81, 20));
                    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v82, 39));
                    CActiveScriptEngine::FinalRelease(v83);
                    (**(void (__fastcall ***)(struct CLruLinkElem *, __int64))v75)(v75, 1);
                  }
                  v75 = v76;
                }
                while ( v76 );
              }
              LeaveCriticalSection(&stru_18007CD68);
              LeaveCriticalSection(&stru_18007CEA8);
            }
          }
          v84 = *(_DWORD *)(v58 + 392);
          if ( (v84 & 0x1000) == 0 )
          {
            if ( (v84 & 1) != 0 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v58 + 24) + 16LL))(v58 + 24);
            else
              CTemplate::End((CTemplate *)v58);
          }
        }
        if ( v56 )
        {
          v85 = (char *)*((_QWORD *)lpParameter + 13);
          v86 = (char *)lpParameter + 96;
          if ( v85 != (char *)lpParameter + 96 )
          {
            do
            {
              if ( !*((_QWORD *)v85 + 8) )
                break;
              v87 = (char *)*((_QWORD *)v85 + 1);
              if ( *((_DWORD *)v85 + 19) == 1 )
              {
                if ( *((_DWORD *)v85 + 20) == 1 )
                {
                  ++g_nScavengedPurged;
                  goto LABEL_155;
                }
                if ( (unsigned int)CTemplate::PersistData((CTemplate *)v85, v55) )
                {
                  ++g_nScavengedPersistFailed;
LABEL_155:
                  if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(v57, v85, 0, 0) )
                  {
                    if ( (v85[392] & 1) != 0 )
                      (*(void (__fastcall **)(char *))(*((_QWORD *)v85 + 3) + 16LL))(v85 + 24);
                    else
                      CTemplate::End((CTemplate *)v85);
                  }
                  goto LABEL_161;
                }
                ++g_nScavengedPersisted;
                HeapFree(CTemplate::sm_hLargeHeap, 0, *((LPVOID *)v85 + 8));
                *((_QWORD *)v85 + 8) = 0;
              }
              else
              {
                *(_QWORD *)(*((_QWORD *)v85 + 2) + 8LL) = v87;
                *(_QWORD *)(*((_QWORD *)v85 + 1) + 16LL) = *((_QWORD *)v85 + 2);
                *((_QWORD *)v85 + 1) = v85;
                *((_QWORD *)v85 + 2) = v86;
                *((_QWORD *)v85 + 1) = *((_QWORD *)v57 + 13);
                *(_QWORD *)(*((_QWORD *)v57 + 13) + 16LL) = v85;
                *((_QWORD *)v57 + 13) = v85;
              }
LABEL_161:
              v85 = v87;
            }
            while ( v87 != v86 );
          }
        }
        LeaveCriticalSection(&stru_180079DF0);
        v89 = a6;
        if ( TransServiceConfig >= 0 )
        {
          v90 = *a6;
          if ( *a6 )
          {
            if ( v101 )
            {
              v91 = *((_QWORD *)v53 + 3);
              if ( !*(_QWORD *)(v91 + 136) )
              {
                (*(void (__fastcall **)(__int64))(*((_QWORD *)v90 + 3) + 8LL))((__int64)v90 + 24);
                *(_QWORD *)(v91 + 136) = v90;
              }
            }
          }
        }
        if ( g_fShutDownInProgress || !*v89 )
          return (unsigned int)TransServiceConfig;
        if ( v95 == CTemplate::Compile )
        {
          if ( TransServiceConfig < 0 )
            return (unsigned int)TransServiceConfig;
          if ( !CTemplateCacheManager::RegisterTemplateForChangeNotification(v88, *v89, *((struct CAppln **)v53 + 3)) )
          {
            EnterCriticalSection(&stru_180079DF0);
            if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(lpParameter, *v89, 0, 1) )
            {
              v92 = *v89;
              if ( (*((_BYTE *)*v89 + 392) & 1) != 0 )
                (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v92 + 3) + 16LL))((_QWORD *)v92 + 3);
              else
                CTemplate::End(v92);
            }
            LeaveCriticalSection(&stru_180079DF0);
          }
          v93 = *((_QWORD *)v53 + 29);
          if ( !v93 )
            v93 = *(_QWORD *)(*((_QWORD *)v53 + 3) + 152LL);
          TransServiceConfig = CTemplate::CreateTransServiceConfig((LPVOID *)*v89, *(_DWORD *)(v93 + 120));
        }
        if ( TransServiceConfig >= 0 && (*((_BYTE *)*v89 + 392) & 1) != 0 && (*((_BYTE *)v53 + 8) & 0x10) != 0 )
          CTemplateCacheManager::RegisterApplicationForChangeNotification(v88, *v89, *((struct CAppln **)v53 + 3));
        return (unsigned int)TransServiceConfig;
      }
      (*(void (__fastcall **)(__int64))(*((_QWORD *)*v19 + 3) + 8LL))((__int64)*v19 + 24);
      _InterlockedIncrement((volatile signed __int32 *)*v19 + 20);
      LeaveCriticalSection(&stru_180079DF0);
      v8 = (__int64 (__fastcall *)(CTemplate *, void **))CTemplate::Deliver;
      v95 = (__int64 (__fastcall *)(CTemplate *, void **))CTemplate::Deliver;
    }
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v40 + 3) + 16LL))((__int64)v40 + 24);
    if ( v41 >= 0 )
      goto LABEL_70;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x1800108d0  mov     [rsp-38h+arg_10], rbx
0x1800108d5  mov     [rsp-38h+arg_8], edx
0x1800108d9  mov     [rsp-38h+arg_0], rcx
0x1800108de  push    rbp
0x1800108df  push    rsi
0x1800108e0  push    rdi
0x1800108e1  push    r12
0x1800108e3  push    r13
0x1800108e5  push    r14
0x1800108e7  push    r15
0x1800108e9  mov     rbp, rsp
0x1800108ec  sub     rsp, 60h
0x1800108f0  mov     rbx, [rbp+arg_20]
0x1800108f4  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800108fb  xor     r15d, r15d
0x1800108fe  mov     r13d, r9d
0x180010901  mov     dword ptr [rbp+arg_0], r15d
0x180010905  mov     r12, r8
0x180010908  mov     esi, edx
0x18001090a  mov     r14d, r15d
0x18001090d  test    rbx, rbx
0x180010910  jz      short loc_180010968
0x180010912  mov     r14, [rbx+40h]
0x180010916  test    r14, r14
0x180010919  jz      short loc_180010968
0x18001091b  mov     rax, [r14+8]
0x18001091f  lea     r8, [rbp+var_20]
0x180010923  mov     [rbp+var_20], rcx
0x180010927  xorps   xmm0, xmm0
0x18001092a  xor     r9d, r9d
0x18001092d  mov     [rsp+60h+var_40], r15
0x180010932  mov     edx, 414h
0x180010937  mov     rcx, [rax+8]
0x18001093b  mov     rax, [rax+0B8h]
0x180010942  movdqu  [rbp+var_18], xmm0
0x180010947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001094c  test    eax, eax
0x18001094e  jz      short loc_180010968
0x180010950  cmp     dword ptr [rbp+var_18+8], r15d
0x180010954  jz      short loc_180010968
0x180010956  cmp     dword ptr [rbp+var_18+4], 4
0x18001095a  jb      short loc_180010968
0x18001095c  mov     rcx, [r14+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180010960  mov     r8, r12; unsigned __int16 *
0x180010963  call    ?RaiseEvent@ASP_START_CACHE_ACCESS@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@PEBG@Z; AspReqEvents::ASP_START_CACHE_ACCESS::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ushort const *)
0x180010968  mov     edi, r15d
0x18001096b  test    esi, esi
0x18001096d  jz      short loc_18001098B
0x18001096f  mov     rax, [rbx+18h]
0x180010973  mov     rcx, [rax+88h]
0x18001097a  test    rcx, rcx
0x18001097d  jz      short loc_1800109AA
0x18001097f  mov     rsi, [rbp+arg_28]
0x180010983  mov     [rsi], rcx
0x180010986  jmp     loc_180010C9D
0x18001098b  mov     rax, [rbx+0E0h]
0x180010992  test    rax, rax
0x180010995  jz      short loc_1800109AA
0x180010997  mov     rsi, [rbp+arg_28]
0x18001099b  mov     [rbx+0E0h], r15
0x1800109a2  mov     [rsi], rax
0x1800109a5  jmp     loc_180010C9D
0x1800109aa  lea     rcx, stru_180079DF0; lpCriticalSection
0x1800109b1  call    cs:__imp_EnterCriticalSection
0x1800109b7  mov     r15, cs:lpParameter
0x1800109be  mov     edi, 1
0x1800109c3  test    byte ptr cs:dword_18007CB28, dil
0x1800109ca  mov     dword ptr [rbp+var_30], edi
0x1800109cd  mov     [rbp+var_20], r12
0x1800109d1  mov     dword ptr [rbp+var_18], r13d
0x1800109d5  jz      short loc_1800109E6
0x1800109d7  mov     rax, cs:qword_18007CB88
0x1800109de  add     rax, 94h
0x1800109e4  jmp     short loc_1800109ED
0x1800109e6  lea     rax, byte_18007CC28
0x1800109ed  lock inc dword ptr [rax]
0x1800109f0  test    byte ptr cs:dword_18007CB28, dil
0x1800109f7  jz      short loc_180010A06
0x1800109f9  mov     rax, cs:qword_18007CB88
0x180010a00  add     rax, 70h ; 'p'
0x180010a04  jmp     short loc_180010A0D
0x180010a06  lea     rax, dword_18007CC04
0x180010a0d  lock inc dword ptr [rax]
0x180010a10  mov     rsi, [rbp+arg_28]
0x180010a14  test    rsi, rsi
0x180010a17  jnz     short loc_180010A21
0x180010a19  mov     rbx, [rsi]
0x180010a1c  jmp     loc_180010B4D
0x180010a21  xor     eax, eax
0x180010a23  lea     r8, [rbp+var_28]
0x180010a27  lea     rdx, [rbp+var_20]
0x180010a2b  mov     [rsi], rax
0x180010a2e  mov     rcx, r15
0x180010a31  mov     [rbp+var_28], rax
0x180010a35  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180010a3b  mov     rbx, [rbp+var_28]
0x180010a3f  mov     [rsi], rbx
0x180010a42  test    eax, eax
0x180010a44  jnz     loc_180010B4D
0x180010a4a  test    byte ptr cs:dword_18007CB28, dil
0x180010a51  jz      short loc_180010A60
0x180010a53  mov     rax, cs:qword_18007CB88
0x180010a5a  add     rax, 6Ch ; 'l'
0x180010a5e  jmp     short loc_180010A67
0x180010a60  lea     rax, byte_18007CC00
0x180010a67  lock inc dword ptr [rax]
0x180010a6a  mov     rcx, [rsi]; this
0x180010a6d  test    dword ptr [rcx+188h], 1000h
0x180010a77  jz      short loc_180010AF0
0x180010a79  mov     rdx, [rcx+10h]
0x180010a7d  mov     rax, [rcx+8]
0x180010a81  mov     [rdx+8], rax
0x180010a85  mov     rdx, [rcx+8]
0x180010a89  mov     rax, [rcx+10h]
0x180010a8d  mov     [rdx+10h], rax
0x180010a91  mov     [rcx+8], rcx
0x180010a95  mov     [rcx+10h], rcx
0x180010a99  dec     dword ptr [r15+7Ch]
0x180010a9d  call    ?UnPersistData@CTemplate@@QEAAJXZ; CTemplate::UnPersistData(void)
0x180010aa2  test    eax, eax
0x180010aa4  jz      short loc_180010ADD
0x180010aa6  mov     rdx, [rsi]
0x180010aa9  mov     rcx, r15
0x180010aac  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180010ab2  mov     rcx, [rsi]
0x180010ab5  add     rcx, 18h
0x180010ab9  mov     rax, [rcx]
0x180010abc  mov     rax, [rax+10h]
0x180010ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac5  xor     r15d, r15d
0x180010ac8  mov     edx, 19h; int
0x180010acd  mov     [rsi], r15
0x180010ad0  call    ?PDWCounter@CPerfData@@QEAAPEAKH@Z; CPerfData::PDWCounter(int)
0x180010ad5  lock dec dword ptr [rax]
0x180010ad8  jmp     loc_180010C99
0x180010add  mov     edx, 22h ; '"'; int
0x180010ae2  call    ?PDWCounter@CPerfData@@QEAAPEAKH@Z; CPerfData::PDWCounter(int)
0x180010ae7  lock inc dword ptr [rax]
0x180010aea  inc     dword ptr [r15+78h]
0x180010aee  jmp     short loc_180010B12
0x180010af0  test    byte ptr cs:dword_18007CB28, dil
0x180010af7  jz      short loc_180010B08
0x180010af9  mov     rax, cs:qword_18007CB88
0x180010b00  add     rax, 90h
0x180010b06  jmp     short loc_180010B0F
0x180010b08  lea     rax, dword_18007CC24
0x180010b0f  lock inc dword ptr [rax]
0x180010b12  mov     rbx, [rsi]
0x180010b15  lea     rdx, [r15+48h]
0x180010b19  mov     rax, [rbx+8]
0x180010b1d  mov     rcx, [rbx+10h]
0x180010b21  mov     [rcx+8], rax
0x180010b25  mov     rcx, [rbx+8]
0x180010b29  mov     rax, [rbx+10h]
0x180010b2d  mov     [rcx+10h], rax
0x180010b31  mov     [rbx+8], rbx
0x180010b35  mov     [rbx+10h], rdx
0x180010b39  mov     rax, [rdx+8]
0x180010b3d  mov     [rbx+8], rax
0x180010b41  mov     rax, [rdx+8]
0x180010b45  mov     [rax+10h], rbx
0x180010b49  mov     [rdx+8], rbx
0x180010b4d  test    rbx, rbx
0x180010b50  jz      short loc_180010BAE
0x180010b52  test    byte ptr [rbx+188h], 2
0x180010b59  jz      short loc_180010BAE
0x180010b5b  mov     ecx, [rbx+1F4h]; this
0x180010b61  mov     eax, cs:dword_180079E20
0x180010b67  cmp     ecx, eax
0x180010b69  jz      short loc_180010B77
0x180010b6b  mov     [rbx+1E8h], edi
0x180010b71  mov     eax, cs:dword_180079E20
0x180010b77  cmp     dword ptr [rbx+1E8h], 0
0x180010b7e  jz      short loc_180010BAE
0x180010b80  cmp     dword ptr [rbx+1ECh], 0
0x180010b87  jnz     short loc_180010BAE
0x180010b89  cmp     ecx, eax
0x180010b8b  jz      short loc_180010B96
0x180010b8d  cmp     cs:?g_fLazyContentPropDisabled@@3HA, 0; int g_fLazyContentPropDisabled
0x180010b94  jz      short loc_180010BA5
0x180010b96  mov     edx, [rbx+1F0h]; unsigned int
0x180010b9c  call    ?CheckTTLTimingWindow@CTemplate@@QEAAHKK@Z; CTemplate::CheckTTLTimingWindow(ulong,ulong)
0x180010ba1  test    eax, eax
0x180010ba3  jz      short loc_180010BAE
0x180010ba5  mov     [rbx+1ECh], edi
0x180010bab  mov     dword ptr [rbp+arg_0], edi
0x180010bae  mov     rbx, [r15+68h]
0x180010bb2  lea     rdi, [r15+60h]
0x180010bb6  cmp     rbx, rdi
0x180010bb9  jz      loc_180010C93
0x180010bbf  nop
0x180010bc0  cmp     qword ptr [rbx+40h], 0
0x180010bc5  jz      loc_180010C8F
0x180010bcb  cmp     dword ptr [rbx+4Ch], 1
0x180010bcf  mov     rsi, [rbx+8]
0x180010bd3  jnz     short loc_180010C53
0x180010bd5  cmp     dword ptr [rbx+50h], 1
0x180010bd9  jnz     short loc_180010BE3
0x180010bdb  inc     cs:?g_nScavengedPurged@@3KA; ulong g_nScavengedPurged
0x180010be1  jmp     short loc_180010BF5
0x180010be3  mov     rcx, rbx; this
0x180010be6  call    ?PersistData@CTemplate@@QEAAJPEAD@Z; CTemplate::PersistData(char *)
0x180010beb  test    eax, eax
0x180010bed  jz      short loc_180010C30
0x180010bef  inc     cs:?g_nScavengedPersistFailed@@3KA; ulong g_nScavengedPersistFailed
0x180010bf5  xor     r9d, r9d
0x180010bf8  xor     r8d, r8d
0x180010bfb  mov     rdx, rbx
0x180010bfe  mov     rcx, r15
0x180010c01  call    ?RemoveTemplate@CTemplateHashTable@CTemplateCacheManager@@QEAA?AW4LK_RETCODE@@PEAVCTemplate@@HH@Z; CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(CTemplate *,int,int)
0x180010c06  test    eax, eax
0x180010c08  jnz     short loc_180010C83
0x180010c0a  test    byte ptr [rbx+188h], 1
0x180010c11  jnz     short loc_180010C1D
0x180010c13  mov     rcx, rbx; this
0x180010c16  call    ?End@CTemplate@@QEAAKXZ; CTemplate::End(void)
0x180010c1b  jmp     short loc_180010C83
0x180010c1d  mov     rax, [rbx+18h]
0x180010c21  lea     rcx, [rbx+18h]
0x180010c25  mov     rax, [rax+10h]
0x180010c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c2e  jmp     short loc_180010C83
0x180010c30  inc     cs:?g_nScavengedPersisted@@3KA; ulong g_nScavengedPersisted
0x180010c36  xor     edx, edx; dwFlags
0x180010c38  mov     r8, [rbx+40h]; lpMem
0x180010c3c  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x180010c43  call    cs:__imp_HeapFree
0x180010c49  mov     qword ptr [rbx+40h], 0
0x180010c51  jmp     short loc_180010C83
0x180010c53  mov     rax, [rbx+10h]
0x180010c57  mov     [rax+8], rsi
0x180010c5b  mov     rcx, [rbx+8]
0x180010c5f  mov     rax, [rbx+10h]
0x180010c63  mov     [rcx+10h], rax
0x180010c67  mov     [rbx+8], rbx
0x180010c6b  mov     [rbx+10h], rdi
0x180010c6f  mov     rax, [rdi+8]
0x180010c73  mov     [rbx+8], rax
0x180010c77  mov     rax, [rdi+8]
0x180010c7b  mov     [rax+10h], rbx
0x180010c7f  mov     [rdi+8], rbx
0x180010c83  mov     rbx, rsi
0x180010c86  cmp     rsi, rdi
0x180010c89  jnz     loc_180010BC0
0x180010c8f  mov     rsi, [rbp+arg_28]
0x180010c93  mov     edi, dword ptr [rbp+var_30]
0x180010c96  xor     r15d, r15d
0x180010c99  mov     rbx, [rbp+arg_20]
0x180010c9d  mov     rcx, [rsi]
0x180010ca0  test    rcx, rcx
0x180010ca3  jz      short loc_180010CE8
0x180010ca5  mov     rax, [rcx+18h]
0x180010ca9  add     rcx, 18h
0x180010cad  mov     rax, [rax+8]
0x180010cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cb6  mov     rax, [rbp+arg_30]
0x180010cba  mov     dword ptr [rax], 1
0x180010cc0  mov     rax, [rsi]
0x180010cc3  lock inc dword ptr [rax+50h]
0x180010cc7  test    edi, edi
0x180010cc9  jz      short loc_180010CD8
0x180010ccb  lea     rcx, stru_180079DF0; lpCriticalSection
0x180010cd2  call    cs:__imp_LeaveCriticalSection
0x180010cd8  lea     r15, ?Deliver@CTemplate@@QEAAJPEAVCHitObj@@@Z; CTemplate::Deliver(CHitObj *)
0x180010cdf  mov     [rbp+var_30], r15
0x180010ce3  jmp     loc_180010DD3
0x180010ce8  mov     rax, [rbp+arg_30]
0x180010cec  lea     rcx, stru_180079DF0; lpCriticalSection
0x180010cf3  mov     [rax], r15d
0x180010cf6  call    cs:__imp_LeaveCriticalSection
0x180010cfc  mov     rcx, cs:?sm_pach@CTemplate@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CTemplate::sm_pach
0x180010d03  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180010d09  test    rax, rax
0x180010d0c  jz      loc_180011534
0x180010d12  mov     rcx, rax; this
0x180010d15  call    ??0CTemplate@@QEAA@XZ; CTemplate::CTemplate(void)
0x180010d1a  mov     rdi, rax
0x180010d1d  test    rax, rax
0x180010d20  jz      loc_180011534
0x180010d26  xor     r8d, r8d
0x180010d29  mov     [rbp+var_30], r15
0x180010d2d  cmp     [rbp+arg_8], r8d
0x180010d31  lea     r9, [rbp+var_20]; struct CTemplateKey *
0x180010d35  mov     rdx, rbx; struct CHitObj *
0x180010d38  mov     [rbp+var_20], r12
0x180010d3c  setnz   r8b; int
0x180010d40  mov     dword ptr [rbp+var_18], r13d
0x180010d44  mov     rcx, rax; this
0x180010d47  call    ?Init@CTemplate@@QEAAJPEAVCHitObj@@HAEBUCTemplateKey@@@Z; CTemplate::Init(CHitObj *,int,CTemplateKey const &)
0x180010d4c  mov     ebx, eax
0x180010d4e  test    eax, eax
0x180010d50  js      short loc_180010DBA
0x180010d52  lea     rcx, stru_180079DF0; lpCriticalSection
0x180010d59  call    cs:__imp_EnterCriticalSection
0x180010d5f  mov     rcx, cs:lpParameter
0x180010d66  lea     r9, [rbp+arg_0]
0x180010d6a  mov     r8, rsi
0x180010d6d  mov     [rbp+var_20], r12
0x180010d71  lea     rdx, [rbp+var_20]
0x180010d75  mov     dword ptr [rbp+var_18], r13d
  ... truncated ...
```

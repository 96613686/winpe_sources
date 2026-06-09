# Broker::SebBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x180006360`
- end: `0x180006c48`
- name: `?OnEnableEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `2280`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x180005cc0`
- `0x180006360`
- `0x180006d90`
- `0x1800076a0`
- `0x180008630`
- `0x180013920`
- `0x180027010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180006534`
- `ntdll!RtlEqualSid` at `0x180006786`
- `ntdll!RtlEqualSid` at `0x1800068c1`
- `ntdll!RtlEqualSid` at `0x180006a32`
- `ntdll!RtlEqualSid` at `0x180006534`
- `ntdll!RtlEqualSid` at `0x180006786`
- `ntdll!RtlEqualSid` at `0x1800068c1`
- `ntdll!RtlEqualSid` at `0x180006a32`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000659a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000659a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000648e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000648e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800066d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000680f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006986`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800066d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000680f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006986`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000664a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000664a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000698c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006815`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000698c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Broker::SebBroker::OnEnableEvent(__int64 a1, __int64 a2, __int64 a3, Broker::SebEvent **a4)
{
  __int128 v7; // xmm0
  ULONG v8; // edi
  volatile signed __int32 *v9; // rbx
  __int64 v11; // rsi
  void *v12; // r15
  int v13; // r12d
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 **v16; // rax
  __int64 *j; // rax
  __int64 v18; // rcx
  __int64 v19; // rsi
  volatile signed __int32 *v20; // rdi
  Broker::SebEvent **v21; // rdx
  Broker::SebEvent *v22; // r10
  __int64 v23; // r8
  int v24; // ebx
  int v25; // edi
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  Broker::SebEvent *v29; // rax
  void *v30; // r12
  __int64 v31; // r13
  __int64 *v32; // rbx
  std::_Ref_count_base *v33; // r15
  __int64 v34; // r14
  __int64 v35; // rax
  __int64 **v36; // rcx
  __int64 *m; // rcx
  __int64 v38; // rcx
  __int64 v39; // rsi
  volatile signed __int32 *v40; // rdi
  std::_Ref_count_base *v41; // rcx
  void *v42; // r13
  __int64 v43; // r12
  __int64 *v44; // rbx
  __int64 v45; // r14
  __int64 v46; // rax
  __int64 **v47; // rcx
  __int64 *ii; // rcx
  __int64 v49; // rcx
  __int64 v50; // rsi
  volatile signed __int32 *v51; // rdi
  std::_Ref_count_base *v52; // rcx
  void *v53; // r12
  __int64 *v54; // rbx
  __int64 v55; // r14
  __int64 v56; // rax
  __int64 **v57; // rcx
  __int64 *kk; // rcx
  __int64 v59; // rcx
  __int64 v60; // rsi
  volatile signed __int32 *v61; // rdi
  std::_Ref_count_base *v62; // rcx
  __int64 *i; // rax
  __int64 *k; // rax
  __int64 *n; // rax
  __int64 *jj; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  int v69; // [rsp+30h] [rbp-A8h]
  __int64 v70; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v71; // [rsp+40h] [rbp-98h]
  __int64 v72; // [rsp+48h] [rbp-90h] BYREF
  char v73; // [rsp+50h] [rbp-88h]
  DWORD CurrentThreadId; // [rsp+54h] [rbp-84h]
  Broker::SebEvent **v75; // [rsp+58h] [rbp-80h]
  std::_Ref_count_base *v76[2]; // [rsp+60h] [rbp-78h]
  __int128 v77; // [rsp+70h] [rbp-68h]
  __int64 v78; // [rsp+80h] [rbp-58h]
  char v79; // [rsp+88h] [rbp-50h]
  Broker::BILayer::Failure *v80; // [rsp+90h] [rbp-48h] BYREF
  Broker::Win32Error *v81; // [rsp+98h] [rbp-40h] BYREF
  Broker::EventInternalError *v82; // [rsp+A0h] [rbp-38h] BYREF
  Broker::BrokerCommonException *v83; // [rsp+A8h] [rbp-30h] BYREF

  v75 = a4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  if ( Broker::SebBroker::Instance && *(_BYTE *)Broker::SebBroker::Instance )
  {
    if ( *(&Broker::SebBroker::Instance + 1) )
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::SebBroker::Instance + 1) + 2);
    v7 = *(_OWORD *)&Broker::SebBroker::Instance;
  }
  else
  {
    v7 = 0;
  }
  v77 = v7;
  if ( !a2 || !a3 || !a4 )
  {
    v8 = 87;
    goto LABEL_11;
  }
  v11 = v7;
  v71 = v7;
  if ( !(_QWORD)v7 )
  {
    v8 = 21;
    goto LABEL_11;
  }
  if ( *(_QWORD *)(v7 + 136) != a2 )
  {
    v8 = 5;
    goto LABEL_11;
  }
  v78 = v7 + 8;
  RtlAcquireSRWLockShared(v7 + 8);
  v79 = 1;
  v12 = (void *)*((_QWORD *)*a4 + 1);
  v13 = -1;
  v69 = -1;
  v14 = **(__int64 ***)(v7 + 16);
  while ( v14 != *(__int64 **)(v11 + 16) )
  {
    v15 = **(_QWORD **)v14[5];
    v70 = v15;
    while ( v15 != *(_QWORD *)v14[5] )
    {
      if ( *(_QWORD *)(v15 + 40) )
      {
        v18 = *(_QWORD *)(v15 + 48);
        if ( v18 )
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
        v19 = *(_QWORD *)(v15 + 40);
        v20 = *(volatile signed __int32 **)(v15 + 48);
        if ( RtlEqualSid(*(PSID *)v19, v12) )
        {
          v13 = *(_DWORD *)(v19 + 40);
          v69 = v13;
        }
        if ( v20 )
        {
          if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v70);
      v15 = v70;
    }
    v16 = (__int64 **)v14[2];
    if ( *((_BYTE *)v16 + 25) )
    {
      for ( i = (__int64 *)v14[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v14 != (__int64 *)i[2] )
          break;
        v14 = i;
      }
      v14 = i;
      v11 = v71;
    }
    else
    {
      v14 = (__int64 *)v14[2];
      for ( j = *v16; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v14 = j;
      v11 = v71;
    }
  }
  RtlReleaseSRWLockShared(v7 + 8);
  v79 = 0;
  v21 = v75;
  v22 = *v75;
  v23 = *((int *)*v75 + 24);
  v24 = 0;
  v70 = 0;
  v25 = 0;
  v26 = (unsigned int)(v23 - 14);
  if ( (unsigned int)v26 <= 0x3D )
  {
    v27 = 0x3FD7D87934DC09DBLL;
    if ( _bittest64(&v27, v26) )
      goto LABEL_55;
  }
  switch ( (_DWORD)v23 )
  {
    case 0xD:
LABEL_59:
      v30 = (void *)*((_QWORD *)v22 + 1);
      v31 = v11 + 8;
      v72 = v11 + 8;
      RtlAcquireSRWLockExclusive(v11 + 8);
      CurrentThreadId = GetCurrentThreadId();
      v73 = 1;
      *(_OWORD *)v76 = 0;
      v32 = **(__int64 ***)(v11 + 16);
      v33 = 0;
      v34 = 0;
      while ( v32 != *(__int64 **)(v11 + 16) )
      {
        v35 = **(_QWORD **)v32[5];
        v70 = v35;
        while ( v35 != *(_QWORD *)v32[5] )
        {
          if ( *(_QWORD *)(v35 + 40) )
          {
            v38 = *(_QWORD *)(v35 + 48);
            if ( v38 )
              _InterlockedIncrement((volatile signed __int32 *)(v38 + 8));
            v39 = *(_QWORD *)(v35 + 40);
            v40 = *(volatile signed __int32 **)(v35 + 48);
            if ( *(_DWORD *)(v39 + 40) == v69 && RtlEqualSid(*(PSID *)v39, v30) )
            {
              if ( v40 )
                _InterlockedIncrement(v40 + 2);
              v34 = v39;
              v41 = v33;
              v33 = (std::_Ref_count_base *)v40;
              if ( v41 )
                std::_Ref_count_base::_Decref(v41);
            }
            if ( v40 )
            {
              if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
                if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
              }
            }
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v70);
          v35 = v70;
        }
        v36 = (__int64 **)v32[2];
        if ( *((_BYTE *)v36 + 25) )
        {
          for ( k = (__int64 *)v32[1]; !*((_BYTE *)k + 25); k = (__int64 *)k[1] )
          {
            if ( v32 != (__int64 *)k[2] )
              break;
            v32 = k;
          }
          v32 = k;
          v11 = v71;
        }
        else
        {
          v32 = (__int64 *)v32[2];
          for ( m = *v36; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v32 = m;
          v11 = v71;
        }
      }
      if ( v34 )
      {
        v24 = *(_DWORD *)(v34 + 64);
        v25 = *(_DWORD *)(v34 + 68);
LABEL_49:
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        v28 = v31;
        goto LABEL_52;
      }
      if ( v33 )
        goto LABEL_149;
      break;
    case 3:
LABEL_81:
      v42 = (void *)*((_QWORD *)v22 + 1);
      v43 = v11 + 8;
      v72 = v11 + 8;
      RtlAcquireSRWLockExclusive(v11 + 8);
      CurrentThreadId = GetCurrentThreadId();
      v73 = 1;
      *(_OWORD *)v76 = 0;
      v44 = **(__int64 ***)(v11 + 16);
      v33 = 0;
      v45 = 0;
      while ( v44 != *(__int64 **)(v11 + 16) )
      {
        v46 = **(_QWORD **)v44[5];
        v70 = v46;
        while ( v46 != *(_QWORD *)v44[5] )
        {
          if ( *(_QWORD *)(v46 + 40) )
          {
            v49 = *(_QWORD *)(v46 + 48);
            if ( v49 )
              _InterlockedIncrement((volatile signed __int32 *)(v49 + 8));
            v50 = *(_QWORD *)(v46 + 40);
            v51 = *(volatile signed __int32 **)(v46 + 48);
            if ( *(_DWORD *)(v50 + 40) == v69 && RtlEqualSid(*(PSID *)v50, v42) )
            {
              if ( v51 )
                _InterlockedIncrement(v51 + 2);
              v45 = v50;
              v52 = v33;
              v33 = (std::_Ref_count_base *)v51;
              if ( v52 )
                std::_Ref_count_base::_Decref(v52);
            }
            if ( v51 )
            {
              if ( _InterlockedExchangeAdd(v51 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
                if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
              }
            }
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v70);
          v46 = v70;
        }
        v47 = (__int64 **)v44[2];
        if ( *((_BYTE *)v47 + 25) )
        {
          for ( n = (__int64 *)v44[1]; !*((_BYTE *)n + 25); n = (__int64 *)n[1] )
          {
            if ( v44 != (__int64 *)n[2] )
              break;
            v44 = n;
          }
          v44 = n;
          v11 = v71;
        }
        else
        {
          v44 = (__int64 *)v44[2];
          for ( ii = *v47; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
            v44 = ii;
          v11 = v71;
        }
      }
      if ( v45 )
      {
        v24 = *(_DWORD *)(v45 + 80);
        v25 = *(_DWORD *)(v45 + 84);
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        v28 = v43;
LABEL_52:
        RtlReleaseSRWLockExclusive(v28);
LABEL_53:
        if ( !v24 && !v25 )
          goto LABEL_189;
        v21 = v75;
        goto LABEL_55;
      }
      if ( v33 )
LABEL_149:
        std::_Ref_count_base::_Decref(v33);
      break;
    case 9:
LABEL_55:
      if ( v24 || v25 )
      {
        v29 = *v21;
        *((_DWORD *)v29 + 31) = v24;
        *((_DWORD *)v29 + 32) = v25;
      }
      goto LABEL_189;
    default:
      switch ( (int)v23 )
      {
        case 0:
          Broker::SebBroker::GetSessionStateName(v11, v13, *((void **)v22 + 1), 0, &v70);
          v25 = HIDWORD(v70);
          v24 = v70;
          goto LABEL_53;
        case 1:
        case 2:
          goto LABEL_81;
        case 11:
        case 12:
          goto LABEL_59;
        case 23:
          v53 = (void *)*((_QWORD *)v22 + 1);
          v31 = v11 + 8;
          v72 = v11 + 8;
          RtlAcquireSRWLockExclusive(v11 + 8);
          CurrentThreadId = GetCurrentThreadId();
          v73 = 1;
          *(_OWORD *)v76 = 0;
          v54 = **(__int64 ***)(v11 + 16);
          v33 = 0;
          v55 = 0;
          while ( v54 != *(__int64 **)(v11 + 16) )
          {
            v56 = **(_QWORD **)v54[5];
            v70 = v56;
            while ( v56 != *(_QWORD *)v54[5] )
            {
              if ( *(_QWORD *)(v56 + 40) )
              {
                v59 = *(_QWORD *)(v56 + 48);
                if ( v59 )
                  _InterlockedIncrement((volatile signed __int32 *)(v59 + 8));
                v60 = *(_QWORD *)(v56 + 40);
                v61 = *(volatile signed __int32 **)(v56 + 48);
                if ( *(_DWORD *)(v60 + 40) == v69 && RtlEqualSid(*(PSID *)v60, v53) )
                {
                  if ( v61 )
                    _InterlockedIncrement(v61 + 2);
                  v55 = v60;
                  v62 = v33;
                  v33 = (std::_Ref_count_base *)v61;
                  if ( v62 )
                    std::_Ref_count_base::_Decref(v62);
                }
                if ( v61 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v61);
              }
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v70);
              v56 = v70;
            }
            v57 = (__int64 **)v54[2];
            if ( *((_BYTE *)v57 + 25) )
            {
              for ( jj = (__int64 *)v54[1]; !*((_BYTE *)jj + 25); jj = (__int64 *)jj[1] )
              {
                if ( v54 != (__int64 *)jj[2] )
                  break;
                v54 = jj;
              }
              v54 = jj;
              v11 = v71;
            }
            else
            {
              v54 = (__int64 *)v54[2];
              for ( kk = *v57; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
                v54 = kk;
              v11 = v71;
            }
          }
          if ( v55 )
          {
            v24 = *(_DWORD *)(v55 + 56);
            v25 = *(_DWORD *)(v55 + 60);
            goto LABEL_49;
          }
          if ( v33 )
            goto LABEL_149;
          goto LABEL_147;
        default:
          v70 = qword_180035118[6 * v23];
          v25 = HIDWORD(v70);
          v24 = v70;
          goto LABEL_55;
      }
  }
LABEL_147:
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v72);
LABEL_189:
  try
  {
    Broker::SebEvent::OnEnable(*v75);
    v8 = 0;
  }
  catch ( std::bad_alloc )
  {
    v8 = 14;
  }
  catch ( Broker::NotFound )
  {
    v8 = 2;
  }
  catch ( Broker::AccessDenied )
  {
    v8 = 5;
  }
  catch ( Broker::BILayer::Failure *v80 )
  {
    v8 = RtlNtStatusToDosError(*((_DWORD *)v80 + 8));
  }
  catch ( Broker::Win32Error *v81 )
  {
    v8 = *((_DWORD *)v81 + 8);
  }
  catch ( Broker::EventInternalError *v82 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v67 = (*(__int64 (__fastcall **)(Broker::EventInternalError *))(*(_QWORD *)v82 + 8LL))(v82);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v67);
    }
    v8 = 1359;
  }
  catch ( Broker::BrokerCommonException *v83 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v68 = (*(__int64 (__fastcall **)(Broker::BrokerCommonException *))(*(_QWORD *)v83 + 8LL))(v83);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v68);
    }
    v8 = 1359;
  }
  catch ( ... )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v8 = 1359;
  }
LABEL_11:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v8);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
  if ( *((_QWORD *)&v77 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180006360  mov     [rsp+arg_0], rbx
0x180006365  mov     [rsp+arg_8], rsi
0x18000636a  push    rdi
0x18000636b  push    r12
0x18000636d  push    r13
0x18000636f  push    r14
0x180006371  push    r15
0x180006373  sub     rsp, 0B0h
0x18000637a  mov     r14, r9
0x18000637d  mov     [rsp+0D8h+var_80], r9
0x180006382  mov     rdi, r8
0x180006385  mov     rbx, rdx
0x180006388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000638f  test    byte ptr [rcx+1Ch], 1
0x180006393  jz      short loc_18000639F
0x180006395  cmp     byte ptr [rcx+19h], 4
0x180006399  jnb     loc_180006685
0x18000639f  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800063a6  test    rax, rax
0x1800063a9  jz      loc_180006621
0x1800063af  cmp     byte ptr [rax], 0
0x1800063b2  jz      loc_180006621
0x1800063b8  mov     rax, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800063bf  test    rax, rax
0x1800063c2  jz      short loc_1800063C8
0x1800063c4  lock inc dword ptr [rax+8]
0x1800063c8  movups  xmm0, cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x1800063cf  movdqu  [rsp+0D8h+var_68], xmm0
0x1800063d5  test    rbx, rbx
0x1800063d8  jnz     short loc_180006451
0x1800063da  mov     edi, 57h ; 'W'
0x1800063df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063e6  test    byte ptr [rcx+1Ch], 1
0x1800063ea  jnz     loc_18000669F
0x1800063f0  mov     rbx, qword ptr [rsp+0D8h+var_68+8]
0x1800063f5  test    rbx, rbx
0x1800063f8  jz      short loc_180006432
0x1800063fa  mov     esi, 0FFFFFFFFh
0x1800063ff  mov     eax, esi
0x180006401  lock xadd [rbx+8], eax
0x180006406  cmp     eax, 1
0x180006409  jnz     short loc_180006432
0x18000640b  mov     rax, [rbx]
0x18000640e  mov     rcx, rbx
0x180006411  mov     rax, [rax]
0x180006414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006419  lock xadd [rbx+0Ch], esi
0x18000641e  cmp     esi, 1
0x180006421  jnz     short loc_180006432
0x180006423  mov     rdx, [rbx]
0x180006426  mov     rcx, rbx
0x180006429  mov     rax, [rdx+8]
0x18000642d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006432  mov     eax, edi
0x180006434  lea     r11, [rsp+0D8h+var_28]
0x18000643c  mov     rbx, [r11+30h]
0x180006440  mov     rsi, [r11+38h]
0x180006444  mov     rsp, r11
0x180006447  pop     r15
0x180006449  pop     r14
0x18000644b  pop     r13
0x18000644d  pop     r12
0x18000644f  pop     rdi
0x180006450  retn
0x180006451  test    rdi, rdi
0x180006454  jz      short loc_1800063DA
0x180006456  test    r14, r14
0x180006459  jz      loc_1800063DA
0x18000645f  movq    rsi, xmm0
0x180006464  mov     [rsp+0D8h+var_98], rsi
0x180006469  test    rsi, rsi
0x18000646c  jz      loc_180006B7A
0x180006472  cmp     [rsi+88h], rbx
0x180006479  jnz     loc_180006B84
0x18000647f  lea     r13, [rsi+8]
0x180006483  mov     [rsp+0D8h+var_58], r13
0x18000648b  mov     rcx, r13
0x18000648e  call    cs:__imp_RtlAcquireSRWLockShared
0x180006494  mov     [rsp+0D8h+var_50], 1
0x18000649c  mov     rax, [r14]
0x18000649f  mov     r15, [rax+8]
0x1800064a3  mov     r12d, 0FFFFFFFFh
0x1800064a9  mov     [rsp+0D8h+var_A8], r12d
0x1800064ae  mov     rbx, [rsi+10h]
0x1800064b2  mov     rbx, [rbx]
0x1800064b5  mov     r14d, 0FFFFFFFFh
0x1800064bb  nop     dword ptr [rax+rax+00h]
0x1800064c0  cmp     rbx, [rsi+10h]
0x1800064c4  jz      loc_180006597
0x1800064ca  mov     rax, [rbx+28h]
0x1800064ce  mov     rax, [rax]
0x1800064d1  mov     rax, [rax]
0x1800064d4  mov     [rsp+0D8h+var_A0], rax
0x1800064d9  mov     rcx, [rbx+28h]
0x1800064dd  cmp     rax, [rcx]
0x1800064e0  jnz     short loc_180006512
0x1800064e2  mov     rax, [rbx+10h]
0x1800064e6  cmp     byte ptr [rax+19h], 0
0x1800064ea  jnz     loc_180006A8F
0x1800064f0  mov     rbx, rax
0x1800064f3  mov     rax, [rax]
0x1800064f6  cmp     byte ptr [rax+19h], 0
0x1800064fa  jnz     short loc_18000650B
0x1800064fc  mov     rbx, rax
0x1800064ff  mov     rcx, [rax]
0x180006502  mov     rax, rcx
0x180006505  cmp     byte ptr [rcx+19h], 0
0x180006509  jz      short loc_1800064FC
0x18000650b  mov     rsi, [rsp+0D8h+var_98]
0x180006510  jmp     short loc_1800064C0
0x180006512  cmp     qword ptr [rax+28h], 0
0x180006517  jz      short loc_180006583
0x180006519  mov     rcx, [rax+30h]
0x18000651d  test    rcx, rcx
0x180006520  jz      short loc_180006526
0x180006522  lock inc dword ptr [rcx+8]
0x180006526  mov     rsi, [rax+28h]
0x18000652a  mov     rdi, [rax+30h]
0x18000652e  mov     rdx, r15; Sid2
0x180006531  mov     rcx, [rsi]; Sid1
0x180006534  call    cs:__imp_RtlEqualSid
0x18000653a  test    al, al
0x18000653c  jz      short loc_180006547
0x18000653e  mov     r12d, [rsi+28h]
0x180006542  mov     [rsp+0D8h+var_A8], r12d
0x180006547  test    rdi, rdi
0x18000654a  jz      short loc_180006583
0x18000654c  mov     eax, r14d
0x18000654f  lock xadd [rdi+8], eax
0x180006554  cmp     eax, 1
0x180006557  jnz     short loc_180006583
0x180006559  mov     rax, [rdi]
0x18000655c  mov     rcx, rdi
0x18000655f  mov     rax, [rax]
0x180006562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006567  mov     eax, r14d
0x18000656a  lock xadd [rdi+0Ch], eax
0x18000656f  cmp     eax, 1
0x180006572  jnz     short loc_180006583
0x180006574  mov     rax, [rdi]
0x180006577  mov     rcx, rdi
0x18000657a  mov     rax, [rax+8]
0x18000657e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006583  lea     rcx, [rsp+0D8h+var_A0]
0x180006588  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x18000658d  mov     rax, [rsp+0D8h+var_A0]
0x180006592  jmp     loc_1800064D9
0x180006597  mov     rcx, r13
0x18000659a  call    cs:__imp_RtlReleaseSRWLockShared
0x1800065a0  mov     [rsp+0D8h+var_50], 0
0x1800065a8  mov     rdx, [rsp+0D8h+var_80]
0x1800065ad  mov     r10, [rdx]
0x1800065b0  movsxd  r8, dword ptr [r10+60h]
0x1800065b4  xor     ebx, ebx
0x1800065b6  mov     [rsp+0D8h+var_A0], rbx
0x1800065bb  xor     edi, edi
0x1800065bd  lea     eax, [r8-0Eh]
0x1800065c1  cmp     eax, 3Dh ; '='
0x1800065c4  ja      short loc_1800065DA
0x1800065c6  mov     rcx, 3FD7D87934DC09DBh
0x1800065d0  bt      rcx, rax
0x1800065d4  jb      loc_18000665D
0x1800065da  cmp     r8d, 0Dh
0x1800065de  jz      loc_1800066C6; jumptable 0000000180006974 cases 11,12
0x1800065e4  cmp     r8d, 3
0x1800065e8  jz      loc_1800067FF; jumptable 0000000180006974 cases 1,2
0x1800065ee  cmp     r8d, 9
0x1800065f2  jz      short loc_18000665D
0x1800065f4  lea     r9, __ImageBase
0x1800065fb  cmp     r8d, 17h; switch 24 cases
0x1800065ff  jbe     loc_180006960
0x180006605  lea     rax, [r8+r8*2]; jumptable 0000000180006974 default case, cases 3-10,13-22
0x180006609  add     rax, rax
0x18000660c  mov     rax, rva qword_180035118[r9+rax*8]
0x180006614  mov     [rsp+0D8h+var_A0], rax
0x180006619  mov     edi, dword ptr [rsp+0D8h+var_A0+4]
0x18000661d  mov     ebx, eax
0x18000661f  jmp     short loc_18000665D
0x180006621  xorps   xmm0, xmm0
0x180006624  jmp     loc_1800063CF
0x180006629  test    r14, r14
0x18000662c  jz      loc_180006B50
0x180006632  mov     ebx, [r14+40h]
0x180006636  mov     edi, [r14+44h]
0x18000663a  test    r15, r15
0x18000663d  jz      short loc_180006647
0x18000663f  mov     rcx, r15; this
0x180006642  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180006647  mov     rcx, r13
0x18000664a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180006650  test    ebx, ebx
0x180006652  jz      loc_180006BB7
0x180006658  mov     rdx, [rsp+0D8h+var_80]
0x18000665d  test    ebx, ebx
0x18000665f  jz      loc_180006BC4
0x180006665  mov     rax, [rdx]
0x180006668  mov     [rax+7Ch], ebx
0x18000666b  mov     [rax+80h], edi
0x180006671  mov     rax, [rsp+0D8h+var_80]
0x180006676  mov     rcx, [rax]; this
0x180006679  call    ?OnEnable@SebEvent@Broker@@QEAAXXZ; Broker::SebEvent::OnEnable(void)
0x18000667e  xor     edi, edi
0x180006680  jmp     loc_1800063DF
0x180006685  mov     edx, 83h
0x18000668a  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x180006691  mov     rcx, [rcx+10h]
0x180006695  call    WPP_SF_
0x18000669a  jmp     loc_18000639F
0x18000669f  cmp     byte ptr [rcx+19h], 4
0x1800066a3  jb      loc_1800063F0
0x1800066a9  mov     edx, 87h
0x1800066ae  mov     r9d, edi
0x1800066b1  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x1800066b8  mov     rcx, [rcx+10h]
0x1800066bc  call    WPP_SF_d
0x1800066c1  jmp     loc_1800063F0
0x1800066c6  mov     r12, [r10+8]; jumptable 0000000180006974 cases 11,12
0x1800066ca  lea     r13, [rsi+8]
0x1800066ce  mov     [rsp+0D8h+var_90], r13
0x1800066d3  mov     rcx, r13
0x1800066d6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800066dc  call    cs:__imp_GetCurrentThreadId
0x1800066e2  mov     [rsp+0D8h+var_84], eax
0x1800066e6  mov     [rsp+0D8h+var_88], 1
0x1800066eb  xorps   xmm0, xmm0
0x1800066ee  movdqu  xmmword ptr [rsp+0D8h+var_78], xmm0
0x1800066f4  mov     rbx, [rsi+10h]
0x1800066f8  mov     rbx, [rbx]
0x1800066fb  mov     r15, [rsp+0D8h+var_78+8]
0x180006700  mov     r14, [rsp+0D8h+var_78]
0x180006705  cmp     rbx, [rsi+10h]
0x180006709  jz      loc_180006629
0x18000670f  mov     rax, [rbx+28h]
0x180006713  mov     rax, [rax]
0x180006716  mov     rax, [rax]
0x180006719  mov     [rsp+0D8h+var_A0], rax
0x18000671e  mov     rcx, [rbx+28h]
0x180006722  cmp     rax, [rcx]
0x180006725  jnz     short loc_180006757
0x180006727  mov     rcx, [rbx+10h]
0x18000672b  cmp     byte ptr [rcx+19h], 0
0x18000672f  jnz     loc_180006AC0
0x180006735  mov     rbx, rcx
0x180006738  mov     rcx, [rcx]
0x18000673b  cmp     byte ptr [rcx+19h], 0
0x18000673f  jnz     short loc_180006750
0x180006741  mov     rbx, rcx
0x180006744  mov     rax, [rcx]
0x180006747  mov     rcx, rax
0x18000674a  cmp     byte ptr [rax+19h], 0
0x18000674e  jz      short loc_180006741
0x180006750  mov     rsi, [rsp+0D8h+var_98]
0x180006755  jmp     short loc_180006705
0x180006757  cmp     qword ptr [rax+28h], 0
0x18000675c  jz      loc_1800067EB
0x180006762  mov     rcx, [rax+30h]
0x180006766  test    rcx, rcx
0x180006769  jz      short loc_18000676F
0x18000676b  lock inc dword ptr [rcx+8]
0x18000676f  mov     rsi, [rax+28h]
0x180006773  mov     rdi, [rax+30h]
0x180006777  mov     eax, [rsp+0D8h+var_A8]
0x18000677b  cmp     [rsi+28h], eax
0x18000677e  jnz     short loc_1800067AC
0x180006780  mov     rdx, r12; Sid2
0x180006783  mov     rcx, [rsi]; Sid1
0x180006786  call    cs:__imp_RtlEqualSid
0x18000678c  test    al, al
0x18000678e  jz      short loc_1800067AC
0x180006790  test    rdi, rdi
0x180006793  jz      short loc_180006799
0x180006795  lock inc dword ptr [rdi+8]
0x180006799  mov     r14, rsi
0x18000679c  mov     rcx, r15; this
0x18000679f  mov     r15, rdi
0x1800067a2  test    rcx, rcx
0x1800067a5  jz      short loc_1800067AC
0x1800067a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800067ac  test    rdi, rdi
0x1800067af  jz      short loc_1800067EB
0x1800067b1  mov     esi, 0FFFFFFFFh
0x1800067b6  mov     eax, esi
0x1800067b8  lock xadd [rdi+8], eax
0x1800067bd  cmp     eax, 1
0x1800067c0  jnz     short loc_1800067EB
0x1800067c2  mov     rax, [rdi]
0x1800067c5  mov     rcx, rdi
0x1800067c8  mov     rax, [rax]
0x1800067cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d0  mov     eax, esi
0x1800067d2  lock xadd [rdi+0Ch], eax
0x1800067d7  cmp     eax, 1
0x1800067da  jnz     short loc_1800067EB
0x1800067dc  mov     rax, [rdi]
0x1800067df  mov     rcx, rdi
0x1800067e2  mov     rax, [rax+8]
0x1800067e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067eb  lea     rcx, [rsp+0D8h+var_A0]
0x1800067f0  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x1800067f5  mov     rax, [rsp+0D8h+var_A0]
  ... truncated ...
```

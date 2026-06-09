# CHitObj::AssignSessionToBrowserRequest(int *,int *,int *)

- ea: `0x18000c4f0`
- end: `0x18000ca42`
- name: `?AssignSessionToBrowserRequest@CHitObj@@QEAAJPEAH00@Z`
- size: `1362`
- prototype: `__int64 __fastcall(CHitObj *__hidden this, int *, int *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a9d0`

## callees

- `0x18000b470`
- `0x18000c4f0`
- `0x180019e7c`
- `0x18001a804`
- `0x18001a908`
- `0x18001c998`
- `0x180023dd0`
- `0x180031fa0`
- `0x180046b48`
- `0x180046eb0`
- `0x180047ac8`
- `0x180047be0`
- `0x1800587b8`
- `0x1800591d0`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000c8ba`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000c8ba`
- `comsvcs!CoCreateActivity` at `0x18000c95f`
- `comsvcs!CoCreateActivity` at `0x18000c95f`
- `KERNEL32!GetACP` at `0x18002894f`
- `KERNEL32!GetACP` at `0x18002894f`
- `KERNEL32!LeaveCriticalSection` at `0x18000c682`
- `KERNEL32!LeaveCriticalSection` at `0x18000c79d`
- `KERNEL32!LeaveCriticalSection` at `0x18000c909`
- `KERNEL32!LeaveCriticalSection` at `0x1800286da`
- `KERNEL32!LeaveCriticalSection` at `0x1800287c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800287f1`
- `KERNEL32!LeaveCriticalSection` at `0x18002886f`
- `KERNEL32!LeaveCriticalSection` at `0x18000c682`
- `KERNEL32!LeaveCriticalSection` at `0x18000c79d`
- `KERNEL32!LeaveCriticalSection` at `0x18000c909`
- `KERNEL32!LeaveCriticalSection` at `0x1800286da`
- `KERNEL32!LeaveCriticalSection` at `0x1800287c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800287f1`
- `KERNEL32!LeaveCriticalSection` at `0x18002886f`
- `KERNEL32!EnterCriticalSection` at `0x18000c585`
- `KERNEL32!EnterCriticalSection` at `0x18000c8ee`
- `KERNEL32!EnterCriticalSection` at `0x1800287a3`
- `KERNEL32!EnterCriticalSection` at `0x18000c585`
- `KERNEL32!EnterCriticalSection` at `0x18000c8ee`
- `KERNEL32!EnterCriticalSection` at `0x1800287a3`
- `KERNEL32!GetTickCount` at `0x18000c89e`
- `KERNEL32!GetTickCount` at `0x18000c89e`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000c83a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000c83a`

## pseudocode

```c
__int64 __fastcall CHitObj::AssignSessionToBrowserRequest(CHitObj *this, int *a2, int *a3, int *a4)
{
  CSessionMgr *v5; // rcx
  CSession *v6; // rbx
  int v7; // r12d
  struct CSessionId *v8; // rsi
  unsigned int v9; // eax
  BOOL v10; // edi
  __int64 v11; // rax
  HRESULT IdAndCookie; // r15d
  __int64 v13; // r13
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  unsigned __int16 *v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rax
  CSessionMgr *v21; // rcx
  unsigned __int16 *v22; // r13
  struct CIdHashArray *v23; // rcx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rdx
  unsigned __int16 *v28; // rdi
  int v29; // r13d
  __int64 *v30; // rdi
  __int64 *v31; // rsi
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  UINT ACP; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // ecx
  bool v39; // zf
  int *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  unsigned int (__fastcall *v44)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int (__fastcall *v49)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  __int64 v50; // rax
  unsigned int v51; // ecx
  CSession *v52; // rax
  __int64 v53; // rsi
  volatile signed __int32 *v54; // rax
  volatile signed __int32 *v55; // rax
  int v56; // edi
  __int64 v57; // rax
  struct CIdHashArray *v58; // rax
  int v59; // edx
  __int64 v60; // rax
  __int64 v61; // rcx
  unsigned int v62; // ecx
  unsigned int v63; // r8d
  unsigned int v64; // edx
  const struct _GUID *v65; // rdx
  __int64 v66; // rax
  unsigned int v67; // ecx
  unsigned int v68; // r8d
  unsigned int v69; // edx
  const struct _GUID *v70; // rdx
  int v71; // eax
  int v72; // eax
  unsigned __int16 *v73; // r12
  __int64 v74; // rax
  unsigned int v75; // ecx
  CIdHashArray *v76; // rax
  CIdHashArray *v77; // r13
  unsigned int v78; // ecx
  unsigned int v79; // r8d
  unsigned int v80; // edx
  const struct _GUID *v81; // rdx
  int v82; // [rsp+30h] [rbp-69h]
  int v83; // [rsp+34h] [rbp-65h]
  int v84; // [rsp+38h] [rbp-61h]
  CSessionMgr *v85; // [rsp+40h] [rbp-59h] BYREF
  int v86; // [rsp+48h] [rbp-51h]
  __int64 v87; // [rsp+50h] [rbp-49h]
  GUID *v88; // [rsp+58h] [rbp-41h] BYREF
  __int128 v89; // [rsp+60h] [rbp-39h]
  int *v90; // [rsp+70h] [rbp-29h]
  int *v91; // [rsp+78h] [rbp-21h]
  int *v92; // [rsp+80h] [rbp-19h]
  char v93[32]; // [rsp+88h] [rbp-11h] BYREF

  v90 = a4;
  v5 = 0;
  v92 = a3;
  v91 = a2;
  v6 = 0;
  v82 = 0;
  v7 = 1;
  v8 = (CHitObj *)((char *)this + 140);
  v83 = 0;
  v9 = *((_DWORD *)this + 35);
  v85 = 0;
  v10 = v9 <= dword_18007D034 && v9 > dword_18007D030;
  v11 = *((_QWORD *)this + 3);
  IdAndCookie = 0;
  v84 = v10;
  v86 = 0;
  v13 = *(_QWORD *)(v11 + 144);
  v87 = v13;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v10 )
        goto LABEL_59;
      v14 = (struct _RTL_CRITICAL_SECTION *)(v13 + 48);
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
      v85 = 0;
      v15 = *(unsigned __int16 **)(v13 + 32);
      if ( !v15 )
      {
LABEL_11:
        v21 = 0;
        v85 = 0;
LABEL_12:
        if ( v21 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
          goto LABEL_59;
        }
        goto LABEL_13;
      }
      v16 = *v15;
      v17 = *(unsigned int *)v8;
      if ( v16 == 499 )
        LODWORD(v18) = *(_DWORD *)v8 % 0x1F3u;
      else
        v18 = v17 % v16;
      v19 = &v15[8 * (unsigned int)v18];
      v20 = *((_QWORD *)v19 + 1);
      v21 = (CSessionMgr *)*((_QWORD *)v19 + 2);
      if ( v20 == v17 )
      {
        v85 = v21;
      }
      else
      {
        if ( !v21 || v20 || (unsigned int)CIdHashArray::Find(v21, *(unsigned int *)v8, (void **)&v85) )
          goto LABEL_11;
        v21 = v85;
      }
      if ( (*((_DWORD *)v21 + 8) & 0x300) != 0
        || *((_DWORD *)v21 + 19) != *((_DWORD *)this + 36)
        || (v59 = 0, *((_DWORD *)v21 + 20) != *((_DWORD *)this + 37)) )
      {
        v59 = 1;
      }
      if ( v59 )
        goto LABEL_12;
      if ( v21 )
      {
        v31 = (__int64 *)((char *)this + 232);
        v60 = *((_QWORD *)this + 29);
        if ( !v60 )
        {
          v60 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
          v21 = v85;
        }
        if ( !*(_DWORD *)(v60 + 44) || (*((_DWORD *)this + 2) & 0x8000) == 0 || (*((_DWORD *)v21 + 8) & 0x1000) != 0 )
        {
          v7 = v83;
LABEL_115:
          _InterlockedIncrement((volatile signed __int32 *)v21 + 23);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
          v30 = (__int64 *)((char *)this + 16);
          v29 = 0;
          *((_QWORD *)this + 2) = v85;
          goto LABEL_112;
        }
        IdAndCookie = CSessionMgr::GenerateIdAndCookie(v21, (CHitObj *)((char *)this + 140), (char *)this + 112);
        if ( IdAndCookie >= 0 )
        {
          IdAndCookie = CSessionMgr::ChangeSessionId((CSessionMgr *)v13, v85, (CHitObj *)((char *)this + 140));
          if ( IdAndCookie >= 0 )
          {
            *((_DWORD *)v85 + 8) |= 0x1000u;
            v61 = *((_QWORD *)this + 8);
            if ( v61
              && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *(struct _EXTENSION_CONTROL_BLOCK **)(v61 + 8),
                                 4u) )
            {
              v62 = *((_DWORD *)this + 35);
              v63 = *((_DWORD *)this + 37);
              v64 = *((_DWORD *)this + 36);
              memset(v93, 0, 28);
              EncodeSessionIdCookie(v62, v64, v63, v93);
              AspReqEvents::ASP_SECURE_SESSION_ID_SET::RaiseEvent(
                *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)this + 8) + 8LL),
                v65,
                v93);
            }
            v21 = v85;
            goto LABEL_115;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 48));
LABEL_106:
        v29 = 0;
LABEL_107:
        v7 = 0;
        if ( IdAndCookie == -2146367464 )
          CAppln::LogSWCError(*((_QWORD *)this + 3), 0);
        goto LABEL_109;
      }
LABEL_13:
      v22 = (unsigned __int16 *)(v13 + 24);
      if ( v6 )
      {
        v23 = (struct CIdHashArray *)*((_QWORD *)v22 + 1);
        v24 = *((unsigned int *)v6 + 18);
        if ( !v23 )
        {
          v58 = CIdHashArray::Alloc(*v22);
          *((_QWORD *)v22 + 1) = v58;
          v23 = v58;
          if ( !v58 )
          {
            IdAndCookie = -2147024882;
            goto LABEL_20;
          }
        }
        v25 = *(unsigned __int16 *)v23;
        v26 = v24;
        if ( v25 == 499 )
          v27 = v24 % 0x1F3;
        else
          v27 = v24 % v25;
        v28 = (unsigned __int16 *)((char *)v23 + 16 * (unsigned int)v27);
        if ( !*((_QWORD *)v28 + 2) )
        {
          *((_QWORD *)v28 + 1) = v26;
          *((_QWORD *)v28 + 2) = v6;
          ++*((_WORD *)v23 + 1);
          IdAndCookie = 0;
LABEL_19:
          _InterlockedIncrement((volatile signed __int32 *)v6 + 23);
          v82 = 1;
          goto LABEL_20;
        }
        v73 = v22 + 1;
        v74 = *((_QWORD *)v28 + 1);
        if ( !*v22 )
          v73 = v22;
        if ( v74 )
        {
          if ( v74 == v26 )
          {
            IdAndCookie = -2147024809;
            goto LABEL_20;
          }
          v75 = *v73;
          if ( !*v73 )
            v75 = v25 + 1;
          v76 = CIdHashArray::Alloc(v75);
          v77 = v76;
          if ( !v76 )
          {
            IdAndCookie = -2147024882;
            goto LABEL_20;
          }
          IdAndCookie = CIdHashArray::Add(v76, *((_QWORD *)v28 + 1), *((void **)v28 + 2), v73);
          if ( IdAndCookie < 0 )
          {
LABEL_20:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v87 + 48));
            v29 = v82;
            if ( v82 )
            {
              v30 = (__int64 *)((char *)this + 16);
              v7 = v83;
              v31 = (__int64 *)((char *)this + 232);
              v32 = *((_DWORD *)this + 2) >> 3;
              *((_QWORD *)this + 2) = v6;
              *((_DWORD *)v6 + 8) ^= (*((_DWORD *)v6 + 8) ^ v32) & 0x1000;
              goto LABEL_22;
            }
            goto LABEL_107;
          }
          *((_QWORD *)v28 + 1) = 0;
          *((_QWORD *)v28 + 2) = v77;
        }
        IdAndCookie = CIdHashArray::Add(*((CIdHashArray **)v28 + 2), v26, v6, v73);
        if ( IdAndCookie >= 0 )
          goto LABEL_19;
        goto LABEL_20;
      }
      LeaveCriticalSection(v14);
      if ( (*((_DWORD *)this + 2) & 0x8000) == 0 )
      {
        v13 = v87;
LABEL_39:
        v10 = v84;
        goto LABEL_40;
      }
      v66 = *((_QWORD *)this + 29);
      if ( !v66 )
        v66 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
      v13 = v87;
      if ( !*(_DWORD *)(v66 + 44) )
        goto LABEL_39;
LABEL_59:
      IdAndCookie = CSessionMgr::GenerateIdAndCookie(v5, v8, (char *)this + 112);
      if ( IdAndCookie < 0 )
        goto LABEL_106;
      v10 = 1;
      v84 = 1;
      v83 = 1;
LABEL_40:
      v46 = *((_QWORD *)this + 8);
      if ( v46 )
      {
        v47 = *(_QWORD *)(v46 + 8);
        v88 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v48 = *(_QWORD *)(v47 + 8);
        v49 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v47 + 184);
        v89 = 0;
        if ( v49(v48, 1044, &v88, 0, 0) )
        {
          if ( DWORD2(v89) && DWORD1(v89) >= 4 )
          {
            v67 = *(_DWORD *)v8;
            v68 = *((_DWORD *)this + 37);
            v69 = *((_DWORD *)this + 36);
            memset(v93, 0, 28);
            EncodeSessionIdCookie(v67, v69, v68, v93);
            AspReqEvents::ASP_NEW_SESSION_CREATED::RaiseEvent(
              *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)this + 8) + 8LL),
              v70,
              v93);
            v86 = 1;
          }
        }
      }
      if ( !v6 )
        break;
      *((_QWORD *)v6 + 9) = *(_QWORD *)v8;
      *((_DWORD *)v6 + 20) = *((_DWORD *)v8 + 2);
    }
    v50 = *((_QWORD *)this + 29);
    if ( !v50 )
      v50 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
    v51 = *(_DWORD *)(v50 + 88);
    if ( v51 - 1 <= 0xFFFFFFFD && *(_DWORD *)(*((_QWORD *)this + 3) + 84LL) >= v51 )
      break;
    v52 = (CSession *)ALLOC_CACHE_HANDLER::Alloc(CSession::sm_pach);
    if ( !v52 || (v6 = CSession::CSession(v52)) == 0 )
    {
      IdAndCookie = -2147024882;
      goto LABEL_129;
    }
    v53 = *(_QWORD *)(v13 + 16);
    _InterlockedIncrement((volatile signed __int32 *)&g_nSessions);
    if ( (dword_18007CB28 & 1) != 0 )
      v54 = (volatile signed __int32 *)(qword_18007CB88 + 92);
    else
      v54 = (volatile signed __int32 *)&qword_18007CBF0;
    _InterlockedIncrement(v54);
    if ( (dword_18007CB28 & 1) != 0 )
      v55 = (volatile signed __int32 *)(qword_18007CB88 + 100);
    else
      v55 = (volatile signed __int32 *)&qword_18007CBF8;
    _InterlockedIncrement(v55);
    *((_DWORD *)v6 + 32) = GetTickCount();
    if ( !*((_QWORD *)v6 + 126) )
    {
      IdAndCookie = CoCreateFreeThreadedMarshaler((LPUNKNOWN)v6, (LPUNKNOWN *)v6 + 126);
      if ( IdAndCookie < 0 )
        goto LABEL_127;
    }
    *((_QWORD *)v6 + 5) = v53;
    *((_QWORD *)v6 + 9) = *(_QWORD *)((char *)this + 140);
    *((_DWORD *)v6 + 20) = *((_DWORD *)this + 37);
    EnterCriticalSection(&stru_18007D040);
    v56 = ++dword_18007D06C;
    LeaveCriticalSection(&stru_18007D040);
    if ( v56 == -1 )
    {
      EnterCriticalSection(&stru_18007D040);
      v71 = dword_18007D06C;
      if ( dword_18007D06C == -1 )
        v71 = dword_18007D068;
      dword_18007D06C = v71 + 1;
      LeaveCriticalSection(&stru_18007D040);
      v56 = dword_18007D06C;
    }
    v57 = *((_QWORD *)v6 + 5);
    *((_DWORD *)v6 + 21) = v56;
    _InterlockedIncrement((volatile signed __int32 *)(v57 + 84));
    *((_DWORD *)v6 + 25) = *(_DWORD *)(*(_QWORD *)(v53 + 152) + 52LL);
    *((_DWORD *)v6 + 26) = *(_DWORD *)(*(_QWORD *)(v53 + 152) + 96LL);
    *((_DWORD *)v6 + 27) = *(_DWORD *)(*(_QWORD *)(v53 + 152) + 60LL);
    IdAndCookie = CoCreateActivity(*(IUnknown **)(v53 + 192), &IID_IServiceActivity, (void **)v6 + 93);
    if ( IdAndCookie < 0 )
    {
LABEL_127:
      CSession::UnInit((LPUNKNOWN)v6);
      (*(void (__fastcall **)(CSession *))(*(_QWORD *)v6 + 16LL))(v6);
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v13 + 16) + 84LL));
LABEL_129:
      v6 = 0;
      v29 = 0;
      goto LABEL_107;
    }
    v10 = v84;
    v8 = (CHitObj *)((char *)this + 140);
    *((_DWORD *)v6 + 188) = 1;
    *((_DWORD *)v6 + 8) |= 1u;
    IdAndCookie = 0;
  }
  v29 = 0;
  IdAndCookie = -2147467259;
LABEL_109:
  v39 = v7 == 0;
  v30 = (__int64 *)((char *)this + 16);
  v7 = v83;
  v31 = (__int64 *)((char *)this + 232);
  v72 = 4016;
  if ( v39 )
    v72 = 4007;
  *v90 = v72;
LABEL_112:
  if ( v6 )
  {
    CSession::UnInit((LPUNKNOWN)v6);
    (*(void (__fastcall **)(CSession *))(*(_QWORD *)v6 + 16LL))(v6);
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 3) + 84LL));
  }
LABEL_22:
  v33 = *v30;
  if ( *v30 && (*(_DWORD *)(v33 + 32) & 0x2000) != 0 )
  {
    ACP = *(_DWORD *)(v33 + 100);
    if ( !ACP )
      ACP = GetACP();
  }
  else
  {
    v34 = *v31;
    if ( !*v31 )
      v34 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
    ACP = *(_DWORD *)(v34 + 52);
  }
  *((_DWORD *)this + 41) = ACP;
  v36 = *v30;
  if ( *v30 && (*(_DWORD *)(v36 + 32) & 0x4000) != 0 )
  {
    v38 = *(_DWORD *)(v36 + 104);
  }
  else
  {
    v37 = *v31;
    if ( !*v31 )
      v37 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
    v38 = *(_DWORD *)(v37 + 96);
  }
  v39 = v86 == 0;
  v40 = v91;
  *((_DWORD *)this + 42) = v38;
  *v40 = v29;
  *v92 = v7;
  if ( v39 )
  {
    v41 = *((_QWORD *)this + 8);
    if ( v41 )
    {
      v42 = *(_QWORD *)(v41 + 8);
      v88 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v43 = *(_QWORD *)(v42 + 8);
      v44 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v42 + 184);
      v89 = 0;
      if ( v44(v43, 1044, &v88, 0, 0) )
      {
        if ( DWORD2(v89) && DWORD1(v89) >= 4 )
        {
          v78 = *((_DWORD *)this + 35);
          v79 = *((_DWORD *)this + 37);
          v80 = *((_DWORD *)this + 36);
          memset(v93, 0, 28);
          EncodeSessionIdCookie(v78, v80, v79, v93);
          AspReqEvents::ASP_NEW_SESSION_CREATED::RaiseEvent(
            *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)this + 8) + 8LL),
            v81,
            v93);
        }
      }
    }
  }
  return (unsigned int)IdAndCookie;
}

```

## disassembly

```asm
0x18000c4f0  push    rbp
0x18000c4f2  push    rbx
0x18000c4f3  push    rsi
0x18000c4f4  push    rdi
0x18000c4f5  push    r12
0x18000c4f7  push    r13
0x18000c4f9  push    r14
0x18000c4fb  push    r15
0x18000c4fd  lea     rbp, [rsp-1Fh]
0x18000c502  sub     rsp, 0B8h
0x18000c509  mov     rax, cs:__security_cookie
0x18000c510  xor     rax, rsp
0x18000c513  mov     [rbp+57h+var_48], rax
0x18000c517  mov     r14, rcx
0x18000c51a  mov     [rbp+57h+var_80], r9
0x18000c51e  xor     ecx, ecx; this
0x18000c520  mov     [rbp+57h+var_70], r8
0x18000c524  mov     [rbp+57h+var_78], rdx
0x18000c528  mov     ebx, ecx
0x18000c52a  mov     [rbp+57h+var_C0], ecx
0x18000c52d  mov     r12d, 1
0x18000c533  lea     rsi, [r14+8Ch]
0x18000c53a  mov     [rbp+57h+var_BC], ecx
0x18000c53d  mov     eax, [rsi]
0x18000c53f  cmp     eax, cs:dword_18007D034
0x18000c545  mov     [rbp+57h+var_B0], rcx
0x18000c549  ja      loc_18000C98D
0x18000c54f  cmp     eax, cs:dword_18007D030
0x18000c555  jbe     loc_18000C98D
0x18000c55b  mov     edi, r12d
0x18000c55e  mov     rax, [r14+18h]
0x18000c562  mov     r15d, ecx
0x18000c565  mov     [rbp+57h+var_B8], edi
0x18000c568  mov     [rbp+57h+var_A8], ecx
0x18000c56b  mov     r13, [rax+90h]
0x18000c572  mov     [rbp+57h+var_A0], r13
0x18000c576  test    edi, edi
0x18000c578  jz      loc_18000C994
0x18000c57e  lea     rdi, [r13+30h]
0x18000c582  mov     rcx, rdi; lpCriticalSection
0x18000c585  call    cs:__imp_EnterCriticalSection
0x18000c58b  mov     [rbp+57h+var_B0], 0
0x18000c593  mov     rcx, [r13+20h]
0x18000c597  test    rcx, rcx
0x18000c59a  jz      short loc_18000C5F1
0x18000c59c  movzx   r8d, word ptr [rcx]
0x18000c5a0  mov     r9d, [rsi]
0x18000c5a3  cmp     r8, 1F3h
0x18000c5aa  jnz     loc_18000C9BB
0x18000c5b0  mov     rax, 8355ACE3C897DB1h
0x18000c5ba  mul     r9
0x18000c5bd  shr     rdx, 4
0x18000c5c1  imul    rax, rdx, 1F3h
0x18000c5c8  mov     edx, r9d
0x18000c5cb  sub     rdx, rax
0x18000c5ce  mov     eax, edx
0x18000c5d0  shl     rax, 4
0x18000c5d4  add     rcx, rax
0x18000c5d7  mov     rax, [rcx+8]
0x18000c5db  mov     rcx, [rcx+10h]; this
0x18000c5df  cmp     rax, r9
0x18000c5e2  jz      loc_1800285A2
0x18000c5e8  test    rcx, rcx
0x18000c5eb  jnz     loc_1800285A8
0x18000c5f1  xor     ecx, ecx
0x18000c5f3  mov     [rbp+57h+var_B0], rcx
0x18000c5f7  test    rcx, rcx
0x18000c5fa  jnz     loc_1800286D7
0x18000c600  add     r13, 18h
0x18000c604  test    rbx, rbx
0x18000c607  jz      loc_18000C79A
0x18000c60d  mov     rcx, [r13+8]
0x18000c611  mov     edi, [rbx+48h]
0x18000c614  test    rcx, rcx
0x18000c617  jz      loc_18000C9C8
0x18000c61d  movzx   r8d, word ptr [rcx]
0x18000c621  mov     rsi, rdi
0x18000c624  cmp     r8, 1F3h
0x18000c62b  jnz     loc_18000C9E7
0x18000c631  mov     rax, 8355ACE3C897DB1h
0x18000c63b  mul     rsi
0x18000c63e  shr     rdx, 4
0x18000c642  imul    rax, rdx, 1F3h
0x18000c649  mov     rdx, rdi
0x18000c64c  sub     rdx, rax
0x18000c64f  mov     edi, edx
0x18000c651  shl     rdi, 4
0x18000c655  add     rdi, rcx
0x18000c658  cmp     qword ptr [rdi+10h], 0
0x18000c65d  jnz     loc_180028891
0x18000c663  mov     [rdi+8], rsi
0x18000c667  mov     [rdi+10h], rbx
0x18000c66b  inc     word ptr [rcx+2]
0x18000c66f  xor     r15d, r15d
0x18000c672  lock inc dword ptr [rbx+5Ch]
0x18000c676  mov     [rbp+57h+var_C0], r12d
0x18000c67a  mov     rcx, [rbp+57h+var_A0]
0x18000c67e  add     rcx, 30h ; '0'; lpCriticalSection
0x18000c682  call    cs:__imp_LeaveCriticalSection
0x18000c688  mov     r13d, [rbp+57h+var_C0]
0x18000c68c  test    r13d, r13d
0x18000c68f  jz      loc_1800287FB
0x18000c695  mov     ecx, [r14+8]
0x18000c699  lea     rdi, [r14+10h]
0x18000c69d  mov     r12d, [rbp+57h+var_BC]
0x18000c6a1  lea     rsi, [r14+0E8h]
0x18000c6a8  shr     ecx, 3
0x18000c6ab  mov     [rdi], rbx
0x18000c6ae  xor     ecx, [rbx+20h]
0x18000c6b1  and     ecx, 1000h
0x18000c6b7  xor     [rbx+20h], ecx
0x18000c6ba  mov     rax, [rdi]
0x18000c6bd  test    rax, rax
0x18000c6c0  jz      short loc_18000C6CF
0x18000c6c2  test    dword ptr [rax+20h], 2000h
0x18000c6c9  jnz     loc_180028944
0x18000c6cf  mov     rax, [rsi]
0x18000c6d2  test    rax, rax
0x18000c6d5  jz      loc_18002895B
0x18000c6db  mov     eax, [rax+34h]
0x18000c6de  mov     [r14+0A4h], eax
0x18000c6e5  mov     rax, [rdi]
0x18000c6e8  test    rax, rax
0x18000c6eb  jz      short loc_18000C6FA
0x18000c6ed  test    dword ptr [rax+20h], 4000h
0x18000c6f4  jnz     loc_18002896B
0x18000c6fa  mov     rax, [rsi]
0x18000c6fd  test    rax, rax
0x18000c700  jz      loc_180028973
0x18000c706  mov     ecx, [rax+60h]
0x18000c709  cmp     [rbp+57h+var_A8], 0
0x18000c70d  mov     rax, [rbp+57h+var_78]
0x18000c711  mov     [r14+0A8h], ecx
0x18000c718  mov     [rax], r13d
0x18000c71b  mov     rax, [rbp+57h+var_70]
0x18000c71f  mov     [rax], r12d
0x18000c722  jnz     short loc_18000C777
0x18000c724  mov     rax, [r14+40h]
0x18000c728  test    rax, rax
0x18000c72b  jz      short loc_18000C777
0x18000c72d  mov     rax, [rax+8]
0x18000c731  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c738  mov     [rbp+57h+var_98], rcx
0x18000c73c  lea     r8, [rbp+57h+var_98]
0x18000c740  xorps   xmm0, xmm0
0x18000c743  mov     [rsp+0F0h+var_D0], 0
0x18000c74c  xor     r9d, r9d
0x18000c74f  mov     edx, 414h
0x18000c754  mov     rcx, [rax+8]
0x18000c758  mov     rax, [rax+0B8h]
0x18000c75f  movdqu  [rbp+57h+var_90], xmm0
0x18000c764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c769  test    eax, eax
0x18000c76b  jz      short loc_18000C777
0x18000c76d  cmp     dword ptr [rbp+57h+var_90+8], 0
0x18000c771  jnz     loc_180028983
0x18000c777  mov     eax, r15d
0x18000c77a  mov     rcx, [rbp+57h+var_48]
0x18000c77e  xor     rcx, rsp; StackCookie
0x18000c781  call    __security_check_cookie
0x18000c786  add     rsp, 0B8h
0x18000c78d  pop     r15
0x18000c78f  pop     r14
0x18000c791  pop     r13
0x18000c793  pop     r12
0x18000c795  pop     rdi
0x18000c796  pop     rsi
0x18000c797  pop     rbx
0x18000c798  pop     rbp
0x18000c799  retn
0x18000c79a  mov     rcx, rdi; lpCriticalSection
0x18000c79d  call    cs:__imp_LeaveCriticalSection
0x18000c7a3  test    dword ptr [r14+8], 8000h
0x18000c7ab  jnz     loc_1800286E6
0x18000c7b1  mov     r13, [rbp+57h+var_A0]
0x18000c7b5  mov     edi, [rbp+57h+var_B8]
0x18000c7b8  mov     rax, [r14+40h]
0x18000c7bc  test    rax, rax
0x18000c7bf  jz      short loc_18000C80B
0x18000c7c1  mov     rax, [rax+8]
0x18000c7c5  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c7cc  mov     [rbp+57h+var_98], rcx
0x18000c7d0  lea     r8, [rbp+57h+var_98]
0x18000c7d4  xorps   xmm0, xmm0
0x18000c7d7  mov     [rsp+0F0h+var_D0], 0
0x18000c7e0  xor     r9d, r9d
0x18000c7e3  mov     edx, 414h
0x18000c7e8  mov     rcx, [rax+8]
0x18000c7ec  mov     rax, [rax+0B8h]
0x18000c7f3  movdqu  [rbp+57h+var_90], xmm0
0x18000c7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7fd  test    eax, eax
0x18000c7ff  jz      short loc_18000C80B
0x18000c801  cmp     dword ptr [rbp+57h+var_90+8], 0
0x18000c805  jnz     loc_180028710
0x18000c80b  test    rbx, rbx
0x18000c80e  jnz     loc_1800287DA
0x18000c814  mov     rax, [r14+0E8h]
0x18000c81b  test    rax, rax
0x18000c81e  jz      loc_180028758
0x18000c824  mov     ecx, [rax+58h]
0x18000c827  lea     eax, [rcx-1]
0x18000c82a  cmp     eax, 0FFFFFFFDh
0x18000c82d  jbe     loc_180028768
0x18000c833  mov     rcx, cs:?sm_pach@CSession@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CSession::sm_pach
0x18000c83a  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000c840  test    rax, rax
0x18000c843  jz      loc_180028934
0x18000c849  mov     rcx, rax; this
0x18000c84c  call    ??0CSession@@QEAA@XZ; CSession::CSession(void)
0x18000c851  mov     rbx, rax
0x18000c854  test    rax, rax
0x18000c857  jz      loc_180028934
0x18000c85d  mov     rsi, [r13+10h]
0x18000c861  lock inc cs:?g_nSessions@@3KA; ulong g_nSessions
0x18000c868  test    byte ptr cs:dword_18007CB28, r12b
0x18000c86f  jz      loc_180028784
0x18000c875  mov     rax, cs:qword_18007CB88
0x18000c87c  add     rax, 5Ch ; '\'
0x18000c880  lock inc dword ptr [rax]
0x18000c883  test    byte ptr cs:dword_18007CB28, r12b
0x18000c88a  jz      loc_180028790
0x18000c890  mov     rax, cs:qword_18007CB88
0x18000c897  add     rax, 64h ; 'd'
0x18000c89b  lock inc dword ptr [rax]
0x18000c89e  call    cs:__imp_GetTickCount
0x18000c8a4  lea     rdx, [rbx+3F0h]; ppunkMarshal
0x18000c8ab  mov     [rbx+80h], eax
0x18000c8b1  cmp     qword ptr [rdx], 0
0x18000c8b5  jnz     short loc_18000C8CB
0x18000c8b7  mov     rcx, rbx; punkOuter
0x18000c8ba  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000c8c0  mov     r15d, eax
0x18000c8c3  test    eax, eax
0x18000c8c5  js      loc_180028913
0x18000c8cb  mov     [rbx+28h], rsi
0x18000c8cf  lea     rcx, stru_18007D040; lpCriticalSection
0x18000c8d6  movsd   xmm0, qword ptr [r14+8Ch]
0x18000c8df  movsd   qword ptr [rbx+48h], xmm0
0x18000c8e4  mov     eax, [r14+94h]
0x18000c8eb  mov     [rbx+50h], eax
0x18000c8ee  call    cs:__imp_EnterCriticalSection
0x18000c8f4  mov     edi, cs:dword_18007D06C
0x18000c8fa  lea     rcx, stru_18007D040; lpCriticalSection
0x18000c901  inc     edi
0x18000c903  mov     cs:dword_18007D06C, edi
0x18000c909  call    cs:__imp_LeaveCriticalSection
0x18000c90f  cmp     edi, 0FFFFFFFFh
0x18000c912  jz      loc_18002879C
0x18000c918  mov     rax, [rbx+28h]
0x18000c91c  mov     [rbx+54h], edi
0x18000c91f  lock inc dword ptr [rax+54h]
0x18000c923  mov     rax, [rsi+98h]
0x18000c92a  lea     r8, [rbx+2E8h]; ppObj
0x18000c931  mov     edx, [rax+34h]
0x18000c934  mov     [rbx+64h], edx
0x18000c937  mov     rax, [rsi+98h]
0x18000c93e  mov     edx, [rax+60h]
0x18000c941  mov     [rbx+68h], edx
0x18000c944  mov     rax, [rsi+98h]
0x18000c94b  mov     edx, [rax+3Ch]
0x18000c94e  mov     [rbx+6Ch], edx
0x18000c951  lea     rdx, IID_IServiceActivity; riid
0x18000c958  mov     rcx, [rsi+0C0h]; pIUnknown
0x18000c95f  call    cs:__imp_CoCreateActivity
0x18000c965  mov     r15d, eax
0x18000c968  test    eax, eax
0x18000c96a  js      loc_180028913
0x18000c970  mov     edi, [rbp+57h+var_B8]
0x18000c973  lea     rsi, [r14+8Ch]
0x18000c97a  mov     [rbx+2F0h], r12d
0x18000c981  or      [rbx+20h], r12d
0x18000c985  xor     r15d, r15d
0x18000c988  jmp     loc_18000C576
0x18000c98d  mov     edi, ecx
0x18000c98f  jmp     loc_18000C55E
0x18000c994  lea     r8, [r14+70h]; char *
0x18000c998  mov     rdx, rsi; struct CSessionId *
0x18000c99b  call    ?GenerateIdAndCookie@CSessionMgr@@QEAAJPEAUCSessionId@@PEAD@Z; CSessionMgr::GenerateIdAndCookie(CSessionId *,char *)
0x18000c9a0  mov     r15d, eax
0x18000c9a3  test    eax, eax
0x18000c9a5  js      loc_1800287F7
0x18000c9ab  mov     edi, r12d
0x18000c9ae  mov     [rbp+57h+var_B8], r12d
0x18000c9b2  mov     [rbp+57h+var_BC], r12d
0x18000c9b6  jmp     loc_18000C7B8
0x18000c9bb  xor     edx, edx
0x18000c9bd  mov     rax, r9
0x18000c9c0  div     r8
0x18000c9c3  jmp     loc_18000C5CE
0x18000c9c8  movzx   ecx, word ptr [r13+0]; unsigned int
0x18000c9cd  call    ?Alloc@CIdHashArray@@SAPEAU1@K@Z; CIdHashArray::Alloc(ulong)
0x18000c9d2  mov     [r13+8], rax
0x18000c9d6  mov     rcx, rax
0x18000c9d9  test    rax, rax
0x18000c9dc  jnz     loc_18000C61D
0x18000c9e2  jmp     loc_180028886
0x18000c9e7  xor     edx, edx
0x18000c9e9  mov     rax, rsi
0x18000c9ec  div     r8
  ... truncated ...
```

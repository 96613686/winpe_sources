# CScriptManager::GetEngine(ulong,_GUID &,ushort const *,CHitObj *,CScriptEngine * *,tagSCRIPTSTATE *,CTemplate *,ulong)

- ea: `0x180008470`
- end: `0x180008ee4`
- name: `?GetEngine@CScriptManager@@QEAAJKAEAU_GUID@@PEBGPEAVCHitObj@@PEAPEAVCScriptEngine@@PEAW4tagSCRIPTSTATE@@PEAVCTemplate@@K@Z`
- size: `2676`
- prototype: `int(CScriptManager *__hidden this, unsigned int, struct _GUID *, const unsigned __int16 *, struct CHitObj *, struct CScriptEngine **, enum tagSCRIPTSTATE *, struct CTemplate *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1800099a0`

## callees

- `0x1800071b0`
- `0x1800072e8`
- `0x180007538`
- `0x1800075e0`
- `0x180008470`
- `0x180008ef0`
- `0x180008f30`
- `0x180011970`
- `0x180012470`
- `0x180016a48`
- `0x180023d62`
- `0x180023dd0`
- `0x180064010`

## import_xrefs

- `msvcrt!atoi` at `0x180026de5`
- `msvcrt!atoi` at `0x180026de5`
- `msvcrt!time` at `0x180008b07`
- `msvcrt!time` at `0x180008b07`
- `KERNEL32!LeaveCriticalSection` at `0x180008712`
- `KERNEL32!LeaveCriticalSection` at `0x180008728`
- `KERNEL32!LeaveCriticalSection` at `0x1800087ff`
- `KERNEL32!LeaveCriticalSection` at `0x180008815`
- `KERNEL32!LeaveCriticalSection` at `0x180008aff`
- `KERNEL32!LeaveCriticalSection` at `0x180008c12`
- `KERNEL32!LeaveCriticalSection` at `0x180008dcc`
- `KERNEL32!LeaveCriticalSection` at `0x180008e7d`
- `KERNEL32!LeaveCriticalSection` at `0x180008e8f`
- `KERNEL32!LeaveCriticalSection` at `0x180008712`
- `KERNEL32!LeaveCriticalSection` at `0x180008728`
- `KERNEL32!LeaveCriticalSection` at `0x1800087ff`
- `KERNEL32!LeaveCriticalSection` at `0x180008815`
- `KERNEL32!LeaveCriticalSection` at `0x180008aff`
- `KERNEL32!LeaveCriticalSection` at `0x180008c12`
- `KERNEL32!LeaveCriticalSection` at `0x180008dcc`
- `KERNEL32!LeaveCriticalSection` at `0x180008e7d`
- `KERNEL32!LeaveCriticalSection` at `0x180008e8f`
- `KERNEL32!EnterCriticalSection` at `0x18000852a`
- `KERNEL32!EnterCriticalSection` at `0x180008585`
- `KERNEL32!EnterCriticalSection` at `0x180008735`
- `KERNEL32!EnterCriticalSection` at `0x180008773`
- `KERNEL32!EnterCriticalSection` at `0x1800089f0`
- `KERNEL32!EnterCriticalSection` at `0x18000852a`
- `KERNEL32!EnterCriticalSection` at `0x180008585`
- `KERNEL32!EnterCriticalSection` at `0x180008735`
- `KERNEL32!EnterCriticalSection` at `0x180008773`
- `KERNEL32!EnterCriticalSection` at `0x1800089f0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008825`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008966`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008de1`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008825`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008966`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008de1`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180026da2`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180026da2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026ddc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026ddc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180026dfd`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180026dfd`
- `iisutil!PuDbgPrint` at `0x180026f15`
- `iisutil!PuDbgPrint` at `0x180026f15`

## string_xrefs

- `0x180026ef5`: `[CScriptManager] Zombie template found.\n`

## pseudocode

```c
__int64 __fastcall CScriptManager::GetEngine(
        CScriptManager *this,
        __int64 a2,
        struct _GUID *a3,
        const unsigned __int8 *a4,
        struct CHitObj *a5,
        struct CScriptEngine **a6,
        enum tagSCRIPTSTATE *a7,
        struct CTemplate *a8,
        unsigned int a9)
{
  CIsapiReqInfo *v11; // rdi
  volatile signed __int32 *v12; // rax
  struct _GUID v13; // xmm6
  __int64 v14; // rbp
  __int64 v15; // rbx
  bool v16; // zf
  __int64 v17; // rdi
  int v18; // r15d
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rbx
  struct CLinkElem *v23; // rdi
  size_t v24; // r8
  int v25; // ecx
  __int64 v26; // r14
  struct _GUID v27; // xmm6
  __int64 v28; // rbx
  __int64 v29; // r14
  int v30; // r15d
  __int64 v31; // rdx
  unsigned int v32; // eax
  unsigned int v33; // ecx
  __int64 v34; // rbx
  __int64 v35; // r14
  CActiveScriptEngine *v36; // rax
  CActiveScriptEngine *v37; // rbx
  struct CTemplate *v38; // r15
  CActiveScriptEngine *v39; // rcx
  struct _GUID *v40; // rax
  __int64 result; // rax
  int Clone; // r14d
  int v43; // eax
  struct CScriptEngine **v44; // rsi
  struct CLinkElem *v45; // rax
  __int64 v46; // rax
  __int64 v47; // rsi
  __int64 v48; // rdx
  const unsigned __int8 *v49; // rcx
  unsigned int v50; // eax
  unsigned int v51; // ecx
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rcx
  __int16 v55; // ax
  __int64 v56; // rax
  struct CLinkElem *v57; // rax
  volatile signed __int32 *v58; // rax
  volatile signed __int32 *v59; // rcx
  __int64 v60; // r8
  const void *v61; // rdx
  __int64 v63; // r13
  __int64 v64; // rcx
  __int64 v65; // rcx
  int v66; // ebx
  CActiveScriptEngine *v67; // rax
  CActiveScriptEngine *v68; // rax
  int ServerVariable; // eax
  const char *Ptr; // rax
  int v71; // eax
  unsigned int v72; // [rsp+50h] [rbp-E8h]
  struct _GUID Buf2; // [rsp+60h] [rbp-D8h] BYREF
  struct CTemplate *v74; // [rsp+70h] [rbp-C8h]
  struct _GUID Buf1; // [rsp+80h] [rbp-B8h] BYREF
  struct _GUID *v76; // [rsp+90h] [rbp-A8h]
  struct CHitObj *v77; // [rsp+98h] [rbp-A0h]
  enum tagSCRIPTSTATE *v78; // [rsp+A0h] [rbp-98h]
  struct CScriptEngine **v79; // [rsp+A8h] [rbp-90h]
  _BYTE v80[48]; // [rsp+B0h] [rbp-88h] BYREF

  v79 = a6;
  v11 = (CIsapiReqInfo *)*((_QWORD *)a5 + 8);
  v76 = a3;
  v77 = a5;
  v78 = a7;
  v74 = a8;
  if ( v11 )
  {
    if ( (*((_DWORD *)v11 + 13) & 0x100) == 0 )
    {
      BUFFER::BUFFER((BUFFER *)v80);
      ServerVariable = CIsapiReqInfo::InternalGetServerVariable(v11, "INSTANCE_ID", (struct BUFFER *)v80);
      *((_DWORD *)v11 + 13) ^= (*((_DWORD *)v11 + 13) ^ (ServerVariable << 8)) & 0x100;
      if ( (ServerVariable & 1) != 0 )
      {
        Ptr = (const char *)BUFFER::QueryPtr((BUFFER *)v80);
        v71 = atoi(Ptr);
      }
      else
      {
        v71 = 1;
      }
      *((_DWORD *)v11 + 14) = v71;
      BUFFER::~BUFFER((BUFFER *)v80);
    }
    v72 = *((_DWORD *)v11 + 14);
  }
  else
  {
    v72 = 0;
  }
  (*(void (__fastcall **)(__int64 *))g_ScriptManager)(&g_ScriptManager);
  EnterCriticalSection(&stru_18007CD68);
  if ( (dword_18007CB28 & 1) != 0 )
    v12 = (volatile signed __int32 *)(qword_18007CB88 + 156);
  else
    v12 = (volatile signed __int32 *)&qword_18007CC30;
  _InterlockedIncrement(v12);
  v13 = *a3;
  (*(void (__fastcall **)(__int64 *))g_ScriptManager)(&g_ScriptManager);
  v14 = -1;
  v15 = -1;
  do
    v16 = *(_WORD *)&a4[2 * v15++ + 2] == 0;
  while ( !v16 );
  EnterCriticalSection(&stru_18007CD68);
  v17 = qword_18007CC70;
  Buf1 = v13;
  if ( !qword_18007CC70 || !a4 )
  {
    v23 = 0;
    LeaveCriticalSection(&stru_18007CD68);
LABEL_27:
    LeaveCriticalSection(&stru_18007CD68);
    goto LABEL_28;
  }
  v18 = 2 * v15;
  v19 = (unsigned int)(2 * v15);
  if ( (unsigned int (__fastcall *)(const unsigned __int8 *, int))qword_18007CC78 == DefaultHash )
  {
    v20 = DefaultHash(a4, v19);
  }
  else
  {
    v20 = ((__int64 (__fastcall *)(const unsigned __int8 *, __int64))qword_18007CC78)(a4, v19);
    v17 = qword_18007CC70;
  }
  if ( (_DWORD)qword_18007CC80 == 57 )
    v21 = v20 % 0x39;
  else
    v21 = v20 % (unsigned int)qword_18007CC80;
  v22 = *(_QWORD *)(v17 + 8LL * v21);
  v23 = 0;
  if ( v22 )
  {
    while ( 1 )
    {
      v24 = *(int *)(v22 + 16);
      if ( (int (*)(CHashTable *__hidden, const void *, int, const void *, int))*qword_18007CC50 == CHashTable::FIsEqual )
        v25 = (_DWORD)v24 == v18 && memcmp_0(*(const void **)(v22 + 8), a4, v24) == 0;
      else
        v25 = ((__int64 (__fastcall *)(void *, _QWORD, size_t, const unsigned __int8 *, int))*qword_18007CC50)(
                &qword_18007CC50,
                *(_QWORD *)(v22 + 8),
                v24,
                a4,
                v18);
      if ( v25 )
      {
        v26 = *(_QWORD *)(v22 + 64);
        Buf2 = *(struct _GUID *)(v26 + 204);
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) && v72 == *(_DWORD *)(v26 + 72) && (*(_BYTE *)(v26 + 276) & 0xC) == 0xC )
          break;
      }
      if ( *(__int16 *)(v22 + 20) > 0 )
      {
        v22 = *(_QWORD *)(v22 + 32);
        if ( v22 )
          continue;
      }
      goto LABEL_26;
    }
    v23 = (struct CLinkElem *)v22;
    *(_QWORD *)(*(_QWORD *)(v22 + 56) + 8LL) = *(_QWORD *)(v22 + 48);
    *(_QWORD *)(*(_QWORD *)(v22 + 48) + 16LL) = *(_QWORD *)(v22 + 56);
    *(_QWORD *)(v22 + 48) = v22 + 40;
    *(_QWORD *)(v22 + 56) = &qword_18007CD50;
    *(_QWORD *)(v22 + 48) = qword_18007CD58;
    *(_QWORD *)(qword_18007CD58 + 16) = v22 + 40;
    qword_18007CD58 = v22 + 40;
  }
LABEL_26:
  LeaveCriticalSection(&stru_18007CD68);
  if ( !v23 || !*((_QWORD *)v23 + 8) )
    goto LABEL_27;
  v57 = CHashTable::RemoveElem((CHashTable *)&qword_18007CC50, v23);
  if ( v57 )
  {
    *(_QWORD *)(*((_QWORD *)v57 + 7) + 8LL) = *((_QWORD *)v57 + 6);
    *(_QWORD *)(*((_QWORD *)v57 + 6) + 16LL) = *((_QWORD *)v57 + 7);
    *((_QWORD *)v57 + 6) = (char *)v57 + 40;
    *((_QWORD *)v57 + 7) = (char *)v57 + 40;
  }
  if ( (dword_18007CB28 & 1) != 0 )
    v58 = (volatile signed __int32 *)(qword_18007CB88 + 84);
  else
    v58 = (volatile signed __int32 *)byte_18007CBE8;
  _InterlockedDecrement(v58);
  LeaveCriticalSection(&stru_18007CD68);
  v37 = (CActiveScriptEngine *)*((_QWORD *)v23 + 8);
  v38 = v74;
  result = CActiveScriptEngine::ReuseEngine(v37, a5, v74, a9, v72);
  Clone = result;
  if ( (int)result >= 0 )
  {
    if ( (dword_18007CB28 & 1) != 0 )
      v59 = (volatile signed __int32 *)(qword_18007CB88 + 152);
    else
      v59 = &dword_18007CC2C;
    _InterlockedIncrement(v59);
    if ( v37 )
    {
LABEL_77:
      v43 = 5;
      goto LABEL_42;
    }
LABEL_28:
    EnterCriticalSection(&stru_18007CEA8);
    v27 = *a3;
    (*(void (__fastcall **)(__int64 *))g_ScriptManager)(&g_ScriptManager);
    v28 = -1;
    do
      v16 = *(_WORD *)&a4[2 * v28++ + 2] == 0;
    while ( !v16 );
    EnterCriticalSection(&stru_18007CEA8);
    v29 = qword_18007CDB0;
    Buf2 = v27;
    if ( qword_18007CDB0 && a4 )
    {
      v30 = 2 * v28;
      v31 = (unsigned int)(2 * v28);
      if ( (unsigned int (__fastcall *)(const unsigned __int8 *, int))qword_18007CDB8 == DefaultHash )
      {
        v32 = DefaultHash(a4, v31);
      }
      else
      {
        v32 = ((__int64 (__fastcall *)(const unsigned __int8 *, __int64))qword_18007CDB8)(a4, v31);
        v29 = qword_18007CDB0;
      }
      if ( (_DWORD)qword_18007CDC0 == 3 )
        v33 = v32 % 3;
      else
        v33 = v32 % (unsigned int)qword_18007CDC0;
      v34 = *(_QWORD *)(v29 + 8LL * v33);
      v35 = 0;
      if ( v34 )
      {
        while ( 1 )
        {
          v60 = *(unsigned int *)(v34 + 16);
          v61 = *(const void **)(v34 + 8);
          if ( (int (*)(CHashTable *__hidden, const void *, int, const void *, int))*qword_18007CD90 == CHashTable::FIsEqual
             ? CHashTable::FIsEqual((CHashTable *)&qword_18007CD90, v61, v60, a4, v30)
             : ((__int64 (__fastcall *)(void *, const void *, __int64, const unsigned __int8 *, int))*qword_18007CD90)(
                 &qword_18007CD90,
                 v61,
                 v60,
                 a4,
                 v30) )
          {
            v63 = *(_QWORD *)(v34 + 64);
            Buf1 = *(struct _GUID *)(v63 + 204);
            if ( !memcmp_0(&Buf2, &Buf1, 0x10u) && v72 == *(_DWORD *)(v63 + 72) && (*(_BYTE *)(v63 + 276) & 0xC) == 0xC )
              break;
          }
          if ( *(__int16 *)(v34 + 20) > 0 )
          {
            v34 = *(_QWORD *)(v34 + 32);
            if ( v34 )
              continue;
          }
          goto LABEL_37;
        }
        v35 = v34;
        *(_QWORD *)(*(_QWORD *)(v34 + 56) + 8LL) = *(_QWORD *)(v34 + 48);
        *(_QWORD *)(*(_QWORD *)(v34 + 48) + 16LL) = *(_QWORD *)(v34 + 56);
        *(_QWORD *)(v34 + 48) = v34 + 40;
        *(_QWORD *)(v34 + 56) = &qword_18007CE90;
        *(_QWORD *)(v34 + 48) = qword_18007CE98;
        *(_QWORD *)(qword_18007CE98 + 16) = v34 + 40;
        qword_18007CE98 = v34 + 40;
      }
LABEL_37:
      LeaveCriticalSection(&stru_18007CEA8);
      if ( v35 )
      {
        v64 = *(_QWORD *)(v35 + 64);
        if ( v64 )
        {
          if ( (*(_DWORD *)(v64 + 276) & 0x202) == 0 )
          {
            v65 = *(_QWORD *)(v64 + 224);
            *(_QWORD *)&Buf2.Data1 = 0;
            v66 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v65 + 120LL))(v65, &Buf2);
            LeaveCriticalSection(&stru_18007CEA8);
            if ( v66 >= 0 )
            {
              v67 = (CActiveScriptEngine *)ALLOC_CACHE_HANDLER::Alloc(CActiveScriptEngine::sm_pach);
              if ( !v67 || (v68 = CActiveScriptEngine::CActiveScriptEngine(v67), (v37 = v68) == 0) )
              {
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Buf2.Data1 + 16LL))(*(_QWORD *)&Buf2.Data1);
                return 2147942414LL;
              }
              v38 = v74;
              Buf1 = *v76;
              Clone = CActiveScriptEngine::MakeClone(
                        v68,
                        &Buf1,
                        (const unsigned __int16 *)a4,
                        0x800u,
                        v77,
                        v74,
                        a9,
                        v72,
                        *(struct IActiveScript **)&Buf2.Data1);
              if ( Clone < 0 )
              {
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Buf2.Data1 + 16LL))(*(_QWORD *)&Buf2.Data1);
                return (unsigned int)Clone;
              }
              goto LABEL_77;
            }
LABEL_39:
            v36 = (CActiveScriptEngine *)ALLOC_CACHE_HANDLER::Alloc(CActiveScriptEngine::sm_pach);
            v37 = v36;
            if ( !v36 )
              return 2147942414LL;
            *((_DWORD *)v36 + 69) &= 0xFFFFFC00;
            v38 = v74;
            *(_QWORD *)v36 = &CActiveScriptEngine::`vftable'{for `CScriptEngine'};
            *((_DWORD *)v36 + 10) = 1;
            *((_QWORD *)v36 + 1) = &CActiveScriptEngine::`vftable'{for `IActiveScriptSite'};
            *((_QWORD *)v36 + 6) = 0;
            *((_QWORD *)v36 + 2) = &CActiveScriptEngine::`vftable'{for `IActiveScriptSiteDebug64'};
            v39 = v36;
            *((_QWORD *)v36 + 7) = 0;
            *((_QWORD *)v36 + 3) = &CActiveScriptEngine::`vftable'{for `IHostInfoProvider'};
            *((_QWORD *)v36 + 4) = &CActiveScriptEngine::`vftable'{for `IActiveScriptSiteTraceInfo'};
            v40 = v76;
            *((_QWORD *)v37 + 8) = 0;
            *((_DWORD *)v37 + 18) = 195948557;
            *((_DWORD *)v37 + 55) = 2048;
            *((_QWORD *)v37 + 28) = 0;
            *((_QWORD *)v37 + 29) = 0;
            *((_QWORD *)v37 + 30) = 0;
            *((_QWORD *)v37 + 31) = 0;
            *((_QWORD *)v37 + 33) = 0;
            *((_DWORD *)v37 + 68) = 195948557;
            *((_QWORD *)v37 + 35) = 0;
            Buf1 = *v40;
            result = CActiveScriptEngine::Init(v39, &Buf1, (const unsigned __int16 *)a4, 2048, v77, v38, a9);
            Clone = result;
            if ( (int)result < 0 )
              return result;
            v43 = 0;
LABEL_42:
            *v78 = v43;
            (*(void (__fastcall **)(CActiveScriptEngine *))(*(_QWORD *)v37 + 136LL))(v37);
            v44 = v79;
            *v79 = v37;
            if ( v23 )
              goto LABEL_48;
            v45 = (struct CLinkElem *)ALLOC_CACHE_HANDLER::Alloc(CASEElem::sm_pach);
            v23 = v45;
            if ( v45 )
            {
              *((_QWORD *)v45 + 1) = 0;
              *((_DWORD *)v45 + 4) = 0;
              *((_WORD *)v45 + 10) = 0;
              *((_QWORD *)v45 + 3) = 0;
              *((_QWORD *)v45 + 4) = 0;
              *(_QWORD *)v45 = &CASEElem::`vftable'{for `CLinkElem'};
              *((_QWORD *)v45 + 5) = &CASEElem::`vftable'{for `CDblLink'};
              *((_QWORD *)v45 + 7) = (char *)v45 + 40;
              *((_QWORD *)v45 + 6) = (char *)v45 + 40;
              *((_QWORD *)v45 + 8) = 0;
              v46 = *((_QWORD *)v37 + 8);
              if ( !v46 )
                goto LABEL_119;
              do
                v16 = *(_WORD *)(v46 + 2 * v14++ + 2) == 0;
              while ( !v16 );
              if ( !(2 * (_DWORD)v14) )
              {
LABEL_119:
                ((void (__fastcall *)(struct CLinkElem *, __int64))CASEElem::`vftable'{for `CLinkElem'})(v23, 1);
                return 2147500037LL;
              }
              *((_QWORD *)v23 + 1) = v46;
              Clone = 0;
              *((_DWORD *)v23 + 4) = 2 * v14;
              *((_QWORD *)v23 + 8) = v37;
LABEL_48:
              EnterCriticalSection(&stru_18007CEA8);
              if ( (*((_DWORD *)v38 + 98) & 0x200) != 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\cmp\\asp\\scrptmgr.cpp",
                    3298,
                    "CScriptManager::GetEngine",
                    "[CScriptManager] Zombie template found.\n");
                (*(void (__fastcall **)(struct CScriptEngine *))(*(_QWORD *)*v44 + 64LL))(*v44);
              }
              v47 = qword_18007CDB0;
              if ( !qword_18007CDB0 )
              {
                if ( (int)CHashTable::AllocateBuckets((CHashTable *)&qword_18007CD90) < 0 )
                  goto LABEL_60;
                v47 = qword_18007CDB0;
              }
              if ( !v23 )
              {
LABEL_60:
                LeaveCriticalSection(&stru_18007CEA8);
                *((_QWORD *)v37 + 32) = time(0);
                return (unsigned int)Clone;
              }
              v48 = *((unsigned int *)v23 + 4);
              v49 = (const unsigned __int8 *)*((_QWORD *)v23 + 1);
              if ( (unsigned int (__fastcall *)(const unsigned __int8 *, int))qword_18007CDB8 == DefaultHash )
              {
                v50 = DefaultHash(v49, v48);
              }
              else
              {
                v50 = ((__int64 (__fastcall *)(const unsigned __int8 *, __int64))qword_18007CDB8)(v49, v48);
                v47 = qword_18007CDB0;
              }
              if ( (_DWORD)qword_18007CDC0 == 3 )
                v51 = v50 % 3;
              else
                v51 = v50 % (unsigned int)qword_18007CDC0;
              v52 = 8LL * v51;
              v53 = *(_QWORD *)(v47 + v52);
              if ( !v53 )
                goto LABEL_56;
              do
              {
                if ( *(__int16 *)(v53 + 20) <= 0 )
                  break;
                v53 = *(_QWORD *)(v53 + 32);
              }
              while ( v53 );
              if ( v53 )
              {
                v54 = *(_QWORD *)(v47 + 8LL * v51);
                *(_QWORD *)(v47 + v52) = v23;
                v55 = *(_WORD *)(v54 + 20) + 1;
                *((_QWORD *)v23 + 4) = v54;
                *((_WORD *)v23 + 10) = v55;
                *((_QWORD *)v23 + 3) = *(_QWORD *)(v54 + 24);
                *(_QWORD *)(v54 + 24) = v23;
                v56 = *((_QWORD *)v23 + 3);
                if ( v56 )
                {
                  *(_QWORD *)(v56 + 32) = v23;
                  goto LABEL_59;
                }
              }
              else
              {
LABEL_56:
                *(_QWORD *)(v47 + 8LL * v51) = v23;
                *((_QWORD *)v23 + 3) = 0;
                *((_QWORD *)v23 + 4) = xmmword_18007CDA0;
                *((_WORD *)v23 + 10) = 0;
                if ( (_QWORD)xmmword_18007CDA0 )
                  *(_QWORD *)(xmmword_18007CDA0 + 24) = v23;
                else
                  *((_QWORD *)&xmmword_18007CDA0 + 1) = v23;
              }
              *(_QWORD *)&xmmword_18007CDA0 = v23;
LABEL_59:
              ++HIDWORD(qword_18007CDC0);
              *(_QWORD *)(*((_QWORD *)v23 + 7) + 8LL) = *((_QWORD *)v23 + 6);
              *(_QWORD *)(*((_QWORD *)v23 + 6) + 16LL) = *((_QWORD *)v23 + 7);
              *((_QWORD *)v23 + 6) = (char *)v23 + 40;
              *((_QWORD *)v23 + 7) = &qword_18007CE90;
              *((_QWORD *)v23 + 6) = qword_18007CE98;
              *(_QWORD *)(qword_18007CE98 + 16) = (char *)v23 + 40;
              qword_18007CE98 = (__int64)v23 + 40;
              goto LABEL_60;
            }
            return 2147942414LL;
          }
        }
      }
    }
    else
    {
      LeaveCriticalSection(&stru_18007CEA8);
    }
    LeaveCriticalSection(&stru_18007CEA8);
    goto LABEL_39;
  }
  return result;
}

```

## disassembly

```asm
0x180008470  mov     [rsp+arg_0], rbx
0x180008475  push    rbp
0x180008476  push    rsi
0x180008477  push    rdi
0x180008478  push    r12
0x18000847a  push    r13
0x18000847c  push    r14
0x18000847e  push    r15
0x180008480  sub     rsp, 100h
0x180008487  movaps  [rsp+138h+var_48], xmm6
0x18000848f  mov     rax, cs:__security_cookie
0x180008496  xor     rax, rsp
0x180008499  mov     [rsp+138h+var_58], rax
0x1800084a1  mov     r13, [rsp+138h+arg_20]
0x1800084a9  mov     rsi, r9
0x1800084ac  mov     rax, [rsp+138h+arg_28]
0x1800084b4  mov     r12, r8
0x1800084b7  mov     r15, [rsp+138h+arg_38]
0x1800084bf  mov     [rsp+138h+var_90], rax
0x1800084c7  mov     rdi, [r13+40h]
0x1800084cb  mov     rax, [rsp+138h+arg_30]
0x1800084d3  mov     [rsp+138h+var_A8], r8
0x1800084db  mov     [rsp+138h+var_A0], r13
0x1800084e3  mov     [rsp+138h+var_98], rax
0x1800084eb  mov     [rsp+138h+var_C8], r15
0x1800084f0  test    rdi, rdi
0x1800084f3  jz      loc_180026E09
0x1800084f9  test    dword ptr [rdi+34h], 100h
0x180008500  jz      loc_180026D9A
0x180008506  mov     ebx, [rdi+38h]
0x180008509  mov     [rsp+138h+var_E8], ebx
0x18000850d  mov     rax, cs:?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x180008514  lea     rcx, ?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x18000851b  mov     rax, [rax]
0x18000851e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008523  lea     rcx, stru_18007CD68; lpCriticalSection
0x18000852a  call    cs:__imp_EnterCriticalSection
0x180008530  test    byte ptr cs:dword_18007CB28, 1
0x180008537  jz      loc_180026E16
0x18000853d  mov     rax, cs:qword_18007CB88
0x180008544  add     rax, 9Ch
0x18000854a  lock inc dword ptr [rax]
0x18000854d  mov     rax, cs:?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x180008554  lea     rcx, ?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x18000855b  movups  xmm6, xmmword ptr [r12]
0x180008560  mov     rax, [rax]
0x180008563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008568  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000856f  mov     rbx, rbp
0x180008572  cmp     word ptr [rsi+rbx*2+2], 0
0x180008578  lea     rbx, [rbx+1]
0x18000857c  jnz     short loc_180008572
0x18000857e  lea     rcx, stru_18007CD68; lpCriticalSection
0x180008585  call    cs:__imp_EnterCriticalSection
0x18000858b  mov     rdi, cs:qword_18007CC70
0x180008592  lea     rcx, ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x180008599  movdqa  [rsp+138h+Buf1], xmm6
0x1800085a2  lea     r14, ?FIsEqual@CHashTable@@MEAAHPEBXH0H@Z; CHashTable::FIsEqual(void const *,int,void const *,int)
0x1800085a9  test    rdi, rdi
0x1800085ac  jz      loc_180008E74
0x1800085b2  test    rsi, rsi
0x1800085b5  jz      loc_180008E74
0x1800085bb  mov     rax, cs:qword_18007CC78
0x1800085c2  lea     r15d, [rbx+rbx]
0x1800085c6  cmp     rax, rcx
0x1800085c9  mov     edx, r15d; int
0x1800085cc  mov     rcx, rsi; unsigned __int8 *
0x1800085cf  jnz     loc_180026E22
0x1800085d5  call    ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x1800085da  mov     r8d, dword ptr cs:qword_18007CC80
0x1800085e1  mov     ecx, eax
0x1800085e3  cmp     r8d, 39h ; '9'
0x1800085e7  jnz     loc_180008E9A
0x1800085ed  mov     eax, 1F7047DDh
0x1800085f2  mul     ecx
0x1800085f4  mov     eax, ecx
0x1800085f6  sub     eax, edx
0x1800085f8  shr     eax, 1
0x1800085fa  add     eax, edx
0x1800085fc  shr     eax, 5
0x1800085ff  imul    eax, 39h ; '9'
0x180008602  sub     ecx, eax
0x180008604  mov     eax, ecx
0x180008606  mov     rbx, [rdi+rax*8]
0x18000860a  xor     edi, edi
0x18000860c  test    rbx, rbx
0x18000860f  jz      loc_18000870B
0x180008615  nop     word ptr [rax+rax+00000000h]
0x180008620  mov     rax, cs:qword_18007CC50
0x180008627  movsxd  r8, dword ptr [rbx+10h]; Size
0x18000862b  mov     rcx, [rbx+8]; Buf1
0x18000862f  mov     rax, [rax]
0x180008632  cmp     rax, r14
0x180008635  jnz     loc_180026E33
0x18000863b  cmp     r8d, r15d
0x18000863e  jnz     loc_180008B4A
0x180008644  mov     rdx, rsi; Buf2
0x180008647  call    memcmp_0
0x18000864c  xor     ecx, ecx
0x18000864e  test    eax, eax
0x180008650  setz    cl
0x180008653  test    ecx, ecx
0x180008655  jnz     short loc_18000866F
0x180008657  cmp     [rbx+14h], di
0x18000865b  jle     loc_18000870B
0x180008661  mov     rbx, [rbx+20h]
0x180008665  test    rbx, rbx
0x180008668  jnz     short loc_180008620
0x18000866a  jmp     loc_18000870B
0x18000866f  mov     r14, [rbx+40h]
0x180008673  lea     rdx, [rsp+138h+Buf2]; Buf2
0x180008678  mov     r8d, 10h; Size
0x18000867e  lea     rcx, [rsp+138h+Buf1]; Buf1
0x180008686  movups  xmm0, xmmword ptr [r14+0CCh]
0x18000868e  movups  [rsp+138h+Buf2], xmm0
0x180008693  call    memcmp_0
0x180008698  test    eax, eax
0x18000869a  jnz     loc_180026E51
0x1800086a0  mov     eax, [rsp+138h+var_E8]
0x1800086a4  cmp     eax, [r14+48h]
0x1800086a8  jnz     loc_180026E51
0x1800086ae  mov     eax, [r14+114h]
0x1800086b5  and     eax, 0Ch
0x1800086b8  cmp     al, 0Ch
0x1800086ba  jnz     loc_180026E51
0x1800086c0  mov     rax, [rbx+30h]
0x1800086c4  lea     rdx, [rbx+28h]
0x1800086c8  mov     rcx, [rdx+10h]
0x1800086cc  mov     rdi, rbx
0x1800086cf  mov     [rcx+8], rax
0x1800086d3  mov     rcx, [rdx+8]
0x1800086d7  mov     rax, [rdx+10h]
0x1800086db  mov     [rcx+10h], rax
0x1800086df  lea     rax, qword_18007CD50
0x1800086e6  mov     [rdx+8], rdx
0x1800086ea  mov     [rdx+10h], rax
0x1800086ee  mov     rax, cs:qword_18007CD58
0x1800086f5  mov     [rdx+8], rax
0x1800086f9  mov     rax, cs:qword_18007CD58
0x180008700  mov     [rax+10h], rdx
0x180008704  mov     cs:qword_18007CD58, rdx
0x18000870b  lea     rcx, stru_18007CD68; lpCriticalSection
0x180008712  call    cs:__imp_LeaveCriticalSection
0x180008718  test    rdi, rdi
0x18000871b  jnz     loc_180008BAD
0x180008721  lea     rcx, stru_18007CD68; lpCriticalSection
0x180008728  call    cs:__imp_LeaveCriticalSection
0x18000872e  lea     rcx, stru_18007CEA8; lpCriticalSection
0x180008735  call    cs:__imp_EnterCriticalSection
0x18000873b  mov     rax, cs:?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x180008742  lea     rcx, ?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x180008749  movups  xmm6, xmmword ptr [r12]
0x18000874e  mov     rax, [rax]
0x180008751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008756  mov     rbx, rbp
0x180008759  nop     dword ptr [rax+00000000h]
0x180008760  cmp     word ptr [rsi+rbx*2+2], 0
0x180008766  lea     rbx, [rbx+1]
0x18000876a  jnz     short loc_180008760
0x18000876c  lea     rcx, stru_18007CEA8; lpCriticalSection
0x180008773  call    cs:__imp_EnterCriticalSection
0x180008779  mov     r14, cs:qword_18007CDB0
0x180008780  lea     r12, qword_18007CE90
0x180008787  movdqa  [rsp+138h+Buf2], xmm6
0x18000878d  test    r14, r14
0x180008790  jz      loc_180008E88
0x180008796  test    rsi, rsi
0x180008799  jz      loc_180008E88
0x18000879f  mov     rax, cs:qword_18007CDB8
0x1800087a6  lea     rcx, ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x1800087ad  lea     r15d, [rbx+rbx]
0x1800087b1  cmp     rax, rcx
0x1800087b4  mov     rcx, rsi; unsigned __int8 *
0x1800087b7  mov     edx, r15d; int
0x1800087ba  jnz     loc_180026E75
0x1800087c0  call    ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x1800087c5  mov     r8d, dword ptr cs:qword_18007CDC0
0x1800087cc  mov     ecx, eax
0x1800087ce  cmp     r8d, 3
0x1800087d2  jnz     loc_180008EA8
0x1800087d8  mov     eax, 0AAAAAAABh
0x1800087dd  mul     ecx
0x1800087df  shr     edx, 1
0x1800087e1  lea     eax, [rdx+rdx*2]
0x1800087e4  sub     ecx, eax
0x1800087e6  mov     eax, ecx
0x1800087e8  mov     rbx, [r14+rax*8]
0x1800087ec  xor     r14d, r14d
0x1800087ef  test    rbx, rbx
0x1800087f2  jnz     loc_180008C90
0x1800087f8  lea     rcx, stru_18007CEA8; lpCriticalSection
0x1800087ff  call    cs:__imp_LeaveCriticalSection
0x180008805  test    r14, r14
0x180008808  jnz     loc_180008D86
0x18000880e  lea     rcx, stru_18007CEA8; lpCriticalSection
0x180008815  call    cs:__imp_LeaveCriticalSection
0x18000881b  xor     r13d, r13d
0x18000881e  mov     rcx, cs:?sm_pach@CActiveScriptEngine@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CActiveScriptEngine::sm_pach
0x180008825  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000882b  mov     rbx, rax
0x18000882e  test    rax, rax
0x180008831  jz      loc_180026EBB
0x180008837  and     dword ptr [rbx+114h], 0FFFFFC00h
0x180008841  lea     rax, ??_7CActiveScriptEngine@@6BCScriptEngine@@@; const CActiveScriptEngine::`vftable'{for `CScriptEngine'}
0x180008848  mov     r15, [rsp+138h+var_C8]
0x18000884d  lea     rdx, [rsp+138h+Buf1]; struct _GUID
0x180008855  mov     [rbx], rax
0x180008858  mov     r9d, 800h; unsigned int
0x18000885e  lea     rax, ??_7CActiveScriptEngine@@6BIActiveScriptSite@@@; const CActiveScriptEngine::`vftable'{for `IActiveScriptSite'}
0x180008865  mov     dword ptr [rbx+28h], 1
0x18000886c  mov     [rbx+8], rax
0x180008870  mov     r8, rsi; unsigned __int16 *
0x180008873  lea     rax, ??_7CActiveScriptEngine@@6BIActiveScriptSiteDebug64@@@; const CActiveScriptEngine::`vftable'{for `IActiveScriptSiteDebug64'}
0x18000887a  mov     [rbx+30h], r13
0x18000887e  mov     [rbx+10h], rax
0x180008882  mov     rcx, rbx; this
0x180008885  lea     rax, ??_7CActiveScriptEngine@@6BIHostInfoProvider@@@; const CActiveScriptEngine::`vftable'{for `IHostInfoProvider'}
0x18000888c  mov     [rbx+38h], r13
0x180008890  mov     [rbx+18h], rax
0x180008894  lea     rax, ??_7CActiveScriptEngine@@6BIActiveScriptSiteTraceInfo@@@; const CActiveScriptEngine::`vftable'{for `IActiveScriptSiteTraceInfo'}
0x18000889b  mov     [rbx+20h], rax
0x18000889f  mov     rax, [rsp+138h+var_A8]
0x1800088a7  mov     [rbx+40h], r13
0x1800088ab  mov     dword ptr [rbx+48h], 0BADF00Dh
0x1800088b2  mov     dword ptr [rbx+0DCh], 800h
0x1800088bc  mov     [rbx+0E0h], r13
0x1800088c3  mov     [rbx+0E8h], r13
0x1800088ca  mov     [rbx+0F0h], r13
0x1800088d1  mov     [rbx+0F8h], r13
0x1800088d8  mov     [rbx+108h], r13
0x1800088df  mov     dword ptr [rbx+110h], 0BADF00Dh
0x1800088e9  mov     qword ptr [rbx+118h], 0
0x1800088f4  movups  xmm0, xmmword ptr [rax]
0x1800088f7  mov     eax, [rsp+138h+arg_40]
0x1800088fe  mov     [rsp+138h+var_108], eax; unsigned int
0x180008902  mov     rax, [rsp+138h+var_A0]
0x18000890a  mov     [rsp+138h+var_110], r15; struct CTemplate *
0x18000890f  mov     [rsp+138h+var_118], rax; struct CHitObj *
0x180008914  movaps  [rsp+138h+Buf1], xmm0
0x18000891c  call    ?Init@CActiveScriptEngine@@QEAAJU_GUID@@PEBGKPEAVCHitObj@@PEAVCTemplate@@K@Z; CActiveScriptEngine::Init(_GUID,ushort const *,ulong,CHitObj *,CTemplate *,ulong)
0x180008921  mov     r14d, eax
0x180008924  test    eax, eax
0x180008926  js      loc_180008B17
0x18000892c  mov     eax, r13d
0x18000892f  mov     rcx, [rsp+138h+var_98]
0x180008937  mov     [rcx], eax
0x180008939  mov     rcx, rbx
0x18000893c  mov     rax, [rbx]
0x18000893f  mov     rax, [rax+88h]
0x180008946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000894b  mov     rsi, [rsp+138h+var_90]
0x180008953  mov     [rsi], rbx
0x180008956  test    rdi, rdi
0x180008959  jnz     loc_1800089E9
0x18000895f  mov     rcx, cs:?sm_pach@CASEElem@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CASEElem::sm_pach
0x180008966  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000896c  mov     rdi, rax
0x18000896f  test    rax, rax
0x180008972  jz      loc_180026EBB
0x180008978  lea     rcx, [rax+28h]
0x18000897c  mov     [rax+8], r13
0x180008980  mov     [rax+10h], r13d
0x180008984  mov     [rax+14h], r13w
0x180008989  mov     [rax+18h], r13
0x18000898d  mov     [rax+20h], r13
0x180008991  lea     rax, ??_7CASEElem@@6BCLinkElem@@@; const CASEElem::`vftable'{for `CLinkElem'}
0x180008998  mov     [rdi], rax
0x18000899b  lea     rax, ??_7CASEElem@@6BCDblLink@@@; const CASEElem::`vftable'{for `CDblLink'}
0x1800089a2  mov     [rcx], rax
0x1800089a5  mov     [rcx+10h], rcx
0x1800089a9  mov     [rcx+8], rcx
0x1800089ad  mov     [rdi+40h], r13
0x1800089b1  mov     rax, [rbx+40h]
0x1800089b5  test    rax, rax
0x1800089b8  jz      loc_180026EC5
0x1800089be  xchg    ax, ax
0x1800089c0  cmp     word ptr [rax+rbp*2+2], 0
0x1800089c6  lea     rbp, [rbp+1]
0x1800089ca  jnz     short loc_1800089C0
0x1800089cc  lea     ecx, ds:0[rbp*2]
0x1800089d3  test    ecx, ecx
0x1800089d5  jz      loc_180026EC5
0x1800089db  mov     [rdi+8], rax
0x1800089df  mov     r14d, r13d
0x1800089e2  mov     [rdi+10h], ecx
0x1800089e5  mov     [rdi+40h], rbx
0x1800089e9  lea     rcx, stru_18007CEA8; lpCriticalSection
0x1800089f0  call    cs:__imp_EnterCriticalSection
0x1800089f6  test    dword ptr [r15+188h], 200h
0x180008a01  jnz     loc_180026EE5
0x180008a07  mov     rsi, cs:qword_18007CDB0
0x180008a0e  test    rsi, rsi
0x180008a11  jz      loc_180008EB6
0x180008a17  test    rdi, rdi
0x180008a1a  jz      loc_180008AF8
0x180008a20  mov     rax, cs:qword_18007CDB8
0x180008a27  lea     r8, ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x180008a2e  mov     edx, [rdi+10h]; int
0x180008a31  mov     rcx, [rdi+8]; unsigned __int8 *
0x180008a35  cmp     rax, r8
  ... truncated ...
```

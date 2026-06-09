# ExecuteRequest(CTemplate *,CHitObj *,CIntrinsicObjects const &,ActiveEngineInfo *)

- ea: `0x18000c1a0`
- end: `0x18000c4e7`
- name: `?ExecuteRequest@@YAJPEAVCTemplate@@PEAVCHitObj@@AEBVCIntrinsicObjects@@PEAUActiveEngineInfo@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(struct CTemplate *, struct CHitObj *, const struct CIntrinsicObjects *, struct ActiveEngineInfo *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000faa0`

## callees

- `0x180007ea0`
- `0x1800095f0`
- `0x1800099a0`
- `0x180009f90`
- `0x18000c1a0`
- `0x180019e7c`
- `0x18001a600`
- `0x18004197c`
- `0x1800437dc`
- `0x180043894`
- `0x180044ab0`
- `0x180044f5c`
- `0x1800450dc`
- `0x18004519c`
- `0x180045478`
- `0x18005b1e0`
- `0x18005e020`
- `0x180064010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18000c44d`
- `ADVAPI32!SetThreadToken` at `0x18000c44d`
- `ADVAPI32!RevertToSelf` at `0x18000c3e5`
- `ADVAPI32!RevertToSelf` at `0x18000c3e5`
- `ADVAPI32!OpenThreadToken` at `0x18000c3d7`
- `ADVAPI32!OpenThreadToken` at `0x18000c3d7`
- `ole32!CoGetObjectContext` at `0x180028340`
- `ole32!CoGetObjectContext` at `0x180028340`
- `comsvcs!CoEnterServiceDomain` at `0x1800281ef`
- `comsvcs!CoEnterServiceDomain` at `0x1800281ef`
- `comsvcs!CoLeaveServiceDomain` at `0x180028357`
- `comsvcs!CoLeaveServiceDomain` at `0x180028561`
- `comsvcs!CoLeaveServiceDomain` at `0x180028357`
- `comsvcs!CoLeaveServiceDomain` at `0x180028561`
- `KERNEL32!HeapFree` at `0x180028553`
- `KERNEL32!HeapFree` at `0x180028553`
- `KERNEL32!HeapAlloc` at `0x1800281ad`
- `KERNEL32!HeapAlloc` at `0x1800281ad`
- `KERNEL32!CloseHandle` at `0x18000c457`
- `KERNEL32!CloseHandle` at `0x18000c457`
- `KERNEL32!GetCurrentThread` at `0x18000c3bf`
- `KERNEL32!GetCurrentThread` at `0x18000c3bf`

## string_xrefs

- `0x18002841b`: `OnTransactionCommit`

## pseudocode

```c
__int64 __fastcall ExecuteRequest(
        struct CTemplate *a1,
        struct CHitObj *a2,
        CScriptingNamespace **a3,
        struct ActiveEngineInfo *a4)
{
  CScriptingNamespace **v6; // rdi
  int v7; // r13d
  __int64 v9; // rax
  void (__fastcall *v10)(struct CHitObj *); // rax
  CPerfData *v11; // rcx
  struct IDispatch *v12; // rdx
  IUnknown *v13; // rcx
  HRESULT Engines; // r15d
  struct CAppln *v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int (__fastcall *v19)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v20; // rdx
  __int64 v21; // rdx
  int v22; // r13d
  CActiveScriptEngine *v23; // r12
  __int64 (__fastcall *v24)(CActiveScriptEngine *__hidden, const unsigned __int16 *); // rax
  HRESULT v25; // eax
  GUID *v26; // r13
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned int (__fastcall *v29)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v30; // rdx
  CPerfData *v31; // rcx
  struct CAppln *v32; // r12
  HANDLE CurrentThread; // rax
  unsigned __int16 v34; // di
  char *v35; // rdx
  CPerfData *v36; // rcx
  CPerfData *v38; // rcx
  IUnknown *v39; // rax
  __int64 v40; // rax
  IUnknown *v41; // rdx
  IUnknown *v42; // rcx
  CPerfData *v43; // rcx
  int v44; // eax
  int v45; // r12d
  int v46; // r8d
  HRESULT v47; // eax
  const struct _GUID *v48; // rdx
  int v49; // edx
  HRESULT v50; // eax
  const struct _GUID *v51; // rdx
  HANDLE TokenHandle; // [rsp+48h] [rbp-39h] BYREF
  int v53; // [rsp+50h] [rbp-31h]
  GUID *v54; // [rsp+58h] [rbp-29h] BYREF
  __int128 v55; // [rsp+60h] [rbp-21h]
  LPVOID ppv; // [rsp+70h] [rbp-11h] BYREF
  CASPObjectContext *v57; // [rsp+78h] [rbp-9h]
  __int64 v58; // [rsp+80h] [rbp-1h]
  _QWORD v59[3]; // [rsp+88h] [rbp+7h] BYREF
  char v60; // [rsp+E8h] [rbp+67h]
  bool v61; // [rsp+F0h] [rbp+6Fh]

  v6 = a3;
  v7 = 0;
  v9 = *(_QWORD *)a2;
  v61 = 0;
  v53 = 0;
  v57 = 0;
  v10 = *(void (__fastcall **)(struct CHitObj *))(v9 + 8);
  v58 = 0;
  ppv = 0;
  v60 = 0;
  v10(a2);
  v12 = (struct IDispatch *)*((_QWORD *)a1 + 54);
  if ( v12 )
    CHitObj::SetTypeLibWrapper(a2, v12);
  if ( *((_DWORD *)a1 + 99) )
  {
    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v11, 32));
    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v38, 31));
    v60 = 1;
    v39 = (IUnknown *)HeapAlloc(g_hDenaliHeap, 0, 0x38u);
    if ( v39 )
    {
      v57 = CASPObjectContext::CASPObjectContext(v39);
      if ( v57 )
      {
        v40 = *((_QWORD *)a2 + 7);
        *((_QWORD *)a2 + 7) = v57;
        v58 = v40;
        goto LABEL_4;
      }
    }
    else
    {
      v57 = 0;
    }
    Engines = -2147024882;
    goto LABEL_25;
  }
LABEL_4:
  v13 = (IUnknown *)*((_QWORD *)a1 + 60);
  if ( v13 )
  {
    Engines = CoEnterServiceDomain(v13);
    if ( Engines < 0 )
      goto LABEL_25;
    v7 = 1;
    v53 = 1;
  }
  Engines = AllocAndLoadEngines(a2, a1, a4, v6[4], 0);
  if ( Engines < 0 )
  {
    *((_DWORD *)a2 + 2) |= 0x80u;
  }
  else
  {
    v15 = (struct CAppln *)*((_QWORD *)a2 + 3);
    if ( (*((_BYTE *)v15 + 72) & 0x20) != 0 )
    {
      CTemplate::AttachTo(a1, v15);
      v61 = (int)CTemplate::NotifyDebuggerOnPageEvent(a1, 1) >= 0;
    }
    if ( *((_WORD *)a1 + 88) )
    {
      v16 = *((_QWORD *)a2 + 8);
      LODWORD(TokenHandle) = 0;
      if ( v16 )
      {
        v17 = *(_QWORD *)(v16 + 8);
        v54 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v18 = *(_QWORD *)(v17 + 8);
        v19 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v17 + 184);
        v55 = 0;
        if ( v19(v18, 1044, &v54, 0, 0) )
        {
          if ( DWORD2(v55) && DWORD1(v55) >= 4 )
            AspReqEvents::ASP_START_SCRIPT_EXECUTION::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8), v20);
        }
      }
      v21 = *((_QWORD *)a4 + 1);
      v22 = 0;
      v54 = (GUID *)*((_QWORD *)a2 + 7);
      v23 = *(CActiveScriptEngine **)(v21 + 16);
      if ( *(_DWORD *)(v21 + 56) && v23 )
      {
        (*(void (__fastcall **)(CActiveScriptEngine *, __int64))(*(_QWORD *)v23 + 120LL))(v23, v21 + 40);
        v22 = 1;
      }
      v24 = *(__int64 (__fastcall **)(CActiveScriptEngine *__hidden, const unsigned __int16 *))(*(_QWORD *)v23 + 24LL);
      if ( v24 == CActiveScriptEngine::Call )
        v25 = CActiveScriptEngine::Call(v23, 0);
      else
        v25 = v24(v23, 0);
      Engines = v25;
      if ( v22 )
        (*(void (__fastcall **)(CActiveScriptEngine *))(*(_QWORD *)v23 + 128LL))(v23);
      v26 = v54;
      if ( v54 && Engines >= 0 )
      {
        if ( !(*(unsigned int (__fastcall **)(CActiveScriptEngine *))(*(_QWORD *)v23 + 80LL))(v23)
          && !(*(unsigned int (__fastcall **)(CActiveScriptEngine *))(*(_QWORD *)v23 + 88LL))(v23)
          || (Engines = (*(__int64 (__fastcall **)(GUID *))(*(_QWORD *)&v26->Data1 + 64LL))(v26), Engines >= 0) )
        {
          if ( !*(_DWORD *)&v26[2].Data4[4] )
            Engines = (*(__int64 (__fastcall **)(GUID *))(*(_QWORD *)&v26->Data1 + 56LL))(v26);
        }
      }
      if ( v16 )
      {
        v27 = *(_QWORD *)(v16 + 8);
        v54 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v28 = *(_QWORD *)(v27 + 8);
        v29 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v27 + 184);
        v55 = 0;
        if ( v29(v28, 1044, &v54, 0, 0) )
        {
          if ( DWORD2(v55) && DWORD1(v55) >= 4 )
            AspReqEvents::ASP_END_SCRIPT_EXECUTION::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8), v30);
        }
      }
      v7 = v53;
      if ( v53 )
      {
        CoGetObjectContext(&IID_IUnknown, &ppv);
        v41 = (IUnknown *)*((_QWORD *)a2 + 7);
        v42 = v41 + 4;
        if ( !v41 )
          v42 = 0;
        CoLeaveServiceDomain(v42);
        v7 = 0;
      }
      v31 = (CPerfData *)*((unsigned int *)a1 + 99);
      if ( Engines < 0 )
      {
        if ( ((Engines + 2147164153) & 0xFFFFFFF7) == 0 )
          HandleErrorMissingFilename(0xBBBu, a2, 0);
      }
      else if ( (_DWORD)v31 )
      {
        _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v31, 33));
        v44 = *((_DWORD *)a4 + 1);
        v45 = 0;
        Engines = -2147467259;
        if ( v46 )
        {
          if ( v44 > 0 )
          {
            do
            {
              v47 = CallScriptFunctionOfEngine(a4, v45, L"OnTransactionAbort", 0);
              Engines = v47;
              if ( v47 != -2147352573 && v47 != -2147352570 )
                break;
              ++v45;
            }
            while ( v45 < *((_DWORD *)a4 + 1) );
          }
          if ( v16
            && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8),
                               2u) )
          {
            AspReqEvents::ASP_TRANSACTION_ABORTED::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8), v48);
          }
          v49 = 29;
        }
        else
        {
          if ( v44 > 0 )
          {
            do
            {
              v50 = CallScriptFunctionOfEngine(a4, v45, L"OnTransactionCommit", 0);
              Engines = v50;
              if ( v50 != -2147352573 && v50 != -2147352570 )
                break;
              ++v45;
            }
            while ( v45 < *((_DWORD *)a4 + 1) );
          }
          if ( v16
            && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8),
                               4u) )
          {
            AspReqEvents::ASP_TRANSACTION_COMMITED::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v16 + 8), v51);
          }
          v49 = 30;
        }
        _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v43, v49));
        if ( Engines == -2147352570 || Engines == -2147352573 )
          Engines = 0;
      }
      v6 = a3;
    }
  }
LABEL_25:
  v32 = (struct CAppln *)*((_QWORD *)a2 + 3);
  if ( ppv )
  {
    v59[0] = a4;
    *(_QWORD *)&v55 = v59;
    v59[1] = v32;
    v59[2] = v6;
    v54 = 0;
    TokenHandle = 0;
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, HANDLE *))ppv)(ppv, &IID_IContextCallback, &TokenHandle) >= 0
      && TokenHandle )
    {
      Engines = (*(__int64 (__fastcall **)(HANDLE, __int64 (__fastcall *)(struct tagComCallData *), GUID **, GUID *, int, _QWORD))(*(_QWORD *)TokenHandle + 24LL))(
                  TokenHandle,
                  DeAllocAndFreeEnginesCallback,
                  &v54,
                  &IID_IEnterActivityWithNoLock,
                  4,
                  0);
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
    }
    else
    {
      Engines = -2147467259;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    TokenHandle = (HANDLE)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      RevertToSelf();
    else
      TokenHandle = (HANDLE)-1LL;
    if ( *((int *)a4 + 1) > 0 && *((_QWORD *)a4 + 1) )
    {
      v34 = 0;
      do
      {
        CScriptManager::ReturnEngineToCache(
          (CScriptManager *)((unsigned __int64)v34 << 6),
          (struct CScriptEngine **)(((unsigned __int64)v34 << 6) + *((_QWORD *)a4 + 1) + 16LL),
          v32);
        ++v34;
      }
      while ( v34 < *((int *)a4 + 1) );
      *((_DWORD *)a4 + 1) = 0;
    }
    if ( *(int *)a4 > 1 )
      HeapFree(g_hDenaliHeap, 0, *((LPVOID *)a4 + 1));
    v35 = (char *)TokenHandle;
    *(_DWORD *)a4 = 0;
    *((_QWORD *)a4 + 1) = 0;
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SetThreadToken(0, v35);
      CloseHandle(TokenHandle);
    }
    CScriptingNamespace::UnInit(a3[4]);
  }
  if ( v7 )
    CoLeaveServiceDomain(0);
  if ( v60 )
    _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v36, 31));
  if ( v61 )
    CTemplate::NotifyDebuggerOnPageEvent(a1, 0);
  if ( v58 )
    *((_QWORD *)a2 + 7) = v58;
  if ( v57 )
    (*(void (__fastcall **)(CASPObjectContext *))(*(_QWORD *)v57 + 16LL))(v57);
  return (unsigned int)Engines;
}

```

## disassembly

```asm
0x18000c1a0  mov     rax, rsp
0x18000c1a3  mov     [rax+18h], r8
0x18000c1a7  push    rbp
0x18000c1a8  lea     rbp, [rax-5Fh]
0x18000c1ac  sub     rsp, 0D0h
0x18000c1b3  mov     [rax+20h], rbx
0x18000c1b7  mov     rbx, r9
0x18000c1ba  mov     [rax-10h], rsi
0x18000c1be  mov     rsi, rdx
0x18000c1c1  mov     [rax-18h], rdi
0x18000c1c5  mov     rdi, r8
0x18000c1c8  mov     [rax-20h], r12
0x18000c1cc  xor     r12d, r12d
0x18000c1cf  mov     [rax-28h], r13
0x18000c1d3  xor     r13d, r13d
0x18000c1d6  mov     [rax-30h], r14
0x18000c1da  mov     r14, rcx
0x18000c1dd  mov     rax, [rdx]
0x18000c1e0  mov     rcx, rdx
0x18000c1e3  mov     byte ptr [rbp+57h+arg_8], 0
0x18000c1e7  mov     [rbp+57h+var_88], r13d
0x18000c1eb  mov     [rbp+57h+var_60], r12
0x18000c1ef  mov     rax, [rax+8]
0x18000c1f3  mov     [rbp+57h+var_58], r12
0x18000c1f7  mov     [rbp+57h+ppv], r12
0x18000c1fb  mov     [rbp+57h+arg_0], r12b
0x18000c1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c204  mov     rdx, [r14+1B0h]; struct IDispatch *
0x18000c20b  test    rdx, rdx
0x18000c20e  jnz     loc_180028172
0x18000c214  mov     [rsp+0D0h+var_30], r15
0x18000c21c  cmp     [r14+18Ch], r12d
0x18000c223  jnz     loc_180028180
0x18000c229  mov     rcx, [r14+1E0h]; pConfigObject
0x18000c230  test    rcx, rcx
0x18000c233  jnz     loc_1800281EF
0x18000c239  mov     r9, [rdi+20h]; struct CScriptingNamespace *
0x18000c23d  mov     r8, rbx; struct ActiveEngineInfo *
0x18000c240  mov     rdx, r14; struct CTemplate *
0x18000c243  mov     [rsp+0D0h+var_B0], r12d; int
0x18000c248  mov     rcx, rsi; struct CHitObj *
0x18000c24b  call    ?AllocAndLoadEngines@@YAJPEAVCHitObj@@PEAVCTemplate@@PEAUActiveEngineInfo@@PEAVCScriptingNamespace@@H@Z; AllocAndLoadEngines(CHitObj *,CTemplate *,ActiveEngineInfo *,CScriptingNamespace *,int)
0x18000c250  mov     r15d, eax
0x18000c253  test    eax, eax
0x18000c255  js      loc_18002820F
0x18000c25b  mov     rdx, [rsi+18h]; struct CAppln *
0x18000c25f  test    byte ptr [rdx+48h], 20h
0x18000c263  jnz     loc_18002821B
0x18000c269  cmp     r12w, [r14+0B0h]
0x18000c271  jz      loc_18000C3A6
0x18000c277  mov     rdi, [rsi+40h]
0x18000c27b  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c282  mov     dword ptr [rbp+57h+TokenHandle], r12d
0x18000c286  test    rdi, rdi
0x18000c289  jz      short loc_18000C2CA
0x18000c28b  mov     rax, [rdi+8]
0x18000c28f  lea     r8, [rbp+57h+var_80]
0x18000c293  mov     [rbp+57h+var_80], rcx
0x18000c297  xorps   xmm0, xmm0
0x18000c29a  xor     r9d, r9d
0x18000c29d  mov     qword ptr [rsp+0D0h+var_B0], r12
0x18000c2a2  mov     edx, 414h
0x18000c2a7  mov     rcx, [rax+8]
0x18000c2ab  mov     rax, [rax+0B8h]
0x18000c2b2  movdqu  [rbp+57h+var_78], xmm0
0x18000c2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2bc  test    eax, eax
0x18000c2be  jz      short loc_18000C2CA
0x18000c2c0  cmp     dword ptr [rbp+57h+var_78+8], 0
0x18000c2c4  jnz     loc_180028248
0x18000c2ca  mov     rdx, [rbx+8]
0x18000c2ce  mov     r13d, r12d
0x18000c2d1  mov     rax, [rsi+38h]
0x18000c2d5  mov     [rbp+57h+var_80], rax
0x18000c2d9  cmp     dword ptr [rdx+38h], 0
0x18000c2dd  mov     r12, [rdx+10h]
0x18000c2e1  jnz     loc_180028261
0x18000c2e7  mov     rax, [r12]
0x18000c2eb  lea     rcx, ?Call@CActiveScriptEngine@@UEAAJPEBG@Z; CActiveScriptEngine::Call(ushort const *)
0x18000c2f2  xor     edx, edx; unsigned __int16 *
0x18000c2f4  mov     rax, [rax+18h]
0x18000c2f8  cmp     rax, rcx
0x18000c2fb  mov     rcx, r12; this
0x18000c2fe  jnz     loc_180028289
0x18000c304  call    ?Call@CActiveScriptEngine@@UEAAJPEBG@Z; CActiveScriptEngine::Call(ushort const *)
0x18000c309  mov     r15d, eax
0x18000c30c  test    r13d, r13d
0x18000c30f  jnz     loc_180028294
0x18000c315  mov     r13, [rbp+57h+var_80]
0x18000c319  test    r13, r13
0x18000c31c  jnz     loc_1800282AD
0x18000c322  test    rdi, rdi
0x18000c325  jz      short loc_18000C371
0x18000c327  mov     rax, [rdi+8]
0x18000c32b  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c332  mov     [rbp+57h+var_80], rcx
0x18000c336  lea     r8, [rbp+57h+var_80]
0x18000c33a  xorps   xmm0, xmm0
0x18000c33d  mov     qword ptr [rsp+0D0h+var_B0], 0
0x18000c346  xor     r9d, r9d
0x18000c349  mov     edx, 414h
0x18000c34e  mov     rcx, [rax+8]
0x18000c352  mov     rax, [rax+0B8h]
0x18000c359  movdqu  [rbp+57h+var_78], xmm0
0x18000c35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c363  test    eax, eax
0x18000c365  jz      short loc_18000C371
0x18000c367  cmp     dword ptr [rbp+57h+var_78+8], 0
0x18000c36b  jnz     loc_18002831C
0x18000c371  mov     r13d, [rbp+57h+var_88]
0x18000c375  test    r13d, r13d
0x18000c378  jnz     loc_180028335
0x18000c37e  mov     ecx, [r14+18Ch]; this
0x18000c385  test    ecx, ecx
0x18000c387  jnz     loc_180028365
0x18000c38d  mov     r8d, dword ptr [rbp+57h+TokenHandle]
0x18000c391  test    r15d, r15d
0x18000c394  js      loc_180028372
0x18000c39a  test    ecx, ecx
0x18000c39c  jnz     loc_18002839A
0x18000c3a2  mov     rdi, [rbp+57h+arg_10]
0x18000c3a6  mov     rcx, [rbp+57h+ppv]
0x18000c3aa  mov     r12, [rsi+18h]
0x18000c3ae  test    rcx, rcx
0x18000c3b1  jnz     loc_180028492
0x18000c3b7  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000c3bf  call    cs:__imp_GetCurrentThread
0x18000c3c5  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000c3c9  mov     edx, 4; DesiredAccess
0x18000c3ce  mov     rcx, rax; ThreadHandle
0x18000c3d1  mov     r8d, 1; OpenAsSelf
0x18000c3d7  call    cs:__imp_OpenThreadToken
0x18000c3dd  test    eax, eax
0x18000c3df  jz      loc_180028539
0x18000c3e5  call    cs:__imp_RevertToSelf
0x18000c3eb  cmp     dword ptr [rbx+4], 0
0x18000c3ef  jle     short loc_18000C426
0x18000c3f1  cmp     qword ptr [rbx+8], 0
0x18000c3f6  jz      short loc_18000C426
0x18000c3f8  xor     edi, edi
0x18000c3fa  mov     rdx, [rbx+8]
0x18000c3fe  mov     r8, r12; struct CAppln *
0x18000c401  add     rdx, 10h
0x18000c405  movzx   ecx, di
0x18000c408  shl     rcx, 6; this
0x18000c40c  add     rdx, rcx; struct CScriptEngine **
0x18000c40f  call    ?ReturnEngineToCache@CScriptManager@@QEAAJPEAPEAVCScriptEngine@@PEAVCAppln@@@Z; CScriptManager::ReturnEngineToCache(CScriptEngine * *,CAppln *)
0x18000c414  inc     di
0x18000c417  movzx   eax, di
0x18000c41a  cmp     eax, [rbx+4]
0x18000c41d  jl      short loc_18000C3FA
0x18000c41f  mov     dword ptr [rbx+4], 0
0x18000c426  cmp     dword ptr [rbx], 1
0x18000c429  jg      loc_180028546
0x18000c42f  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000c433  mov     dword ptr [rbx], 0
0x18000c439  mov     qword ptr [rbx+8], 0
0x18000c441  lea     rax, [rdx-1]
0x18000c445  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c449  ja      short loc_18000C45D
0x18000c44b  xor     ecx, ecx; Thread
0x18000c44d  call    cs:__imp_SetThreadToken
0x18000c453  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000c457  call    cs:__imp_CloseHandle
0x18000c45d  mov     rcx, [rbp+57h+arg_10]
0x18000c461  mov     rcx, [rcx+20h]; this
0x18000c465  call    ?UnInit@CScriptingNamespace@@QEAAJXZ; CScriptingNamespace::UnInit(void)
0x18000c46a  mov     r12, [rsp+0D0h+var_18]
0x18000c472  test    r13d, r13d
0x18000c475  mov     r13, [rsp+0D0h+var_20]
0x18000c47d  mov     rdi, [rsp+0D0h+var_10]
0x18000c485  mov     rbx, [rsp+0D0h+arg_18]
0x18000c48d  jnz     loc_18002855F
0x18000c493  cmp     [rbp+57h+arg_0], 0
0x18000c497  jnz     loc_18002856D
0x18000c49d  cmp     byte ptr [rbp+57h+arg_8], 0
0x18000c4a1  jnz     loc_18002857F
0x18000c4a7  mov     rax, [rbp+57h+var_58]
0x18000c4ab  mov     r14, [rsp+0D0h+var_28]
0x18000c4b3  test    rax, rax
0x18000c4b6  jnz     short loc_18000C4E1
0x18000c4b8  mov     rcx, [rbp+57h+var_60]
0x18000c4bc  mov     rsi, [rsp+0C8h]
0x18000c4c4  test    rcx, rcx
0x18000c4c7  jnz     loc_18002858F
0x18000c4cd  mov     eax, r15d
0x18000c4d0  mov     r15, [rsp+0D0h+var_30]
0x18000c4d8  add     rsp, 0D0h
0x18000c4df  pop     rbp
0x18000c4e0  retn
0x18000c4e1  mov     [rsi+38h], rax
0x18000c4e5  jmp     short loc_18000C4B8
0x180028172  mov     rcx, rsi; this
0x180028175  call    ?SetTypeLibWrapper@CHitObj@@QEAAXPEAUIDispatch@@@Z; CHitObj::SetTypeLibWrapper(IDispatch *)
0x18002817a  nop
0x18002817b  jmp     loc_18000C214
0x180028180  mov     edx, 20h ; ' '; int
0x180028185  call    ?PDWCounter@CPerfData@@QEAAPEAKH@Z; CPerfData::PDWCounter(int)
0x18002818a  lock inc dword ptr [rax]
0x18002818d  mov     edx, 1Fh; int
0x180028192  call    ?PDWCounter@CPerfData@@QEAAPEAKH@Z; CPerfData::PDWCounter(int)
0x180028197  lock inc dword ptr [rax]
0x18002819a  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800281a1  xor     edx, edx; dwFlags
0x1800281a3  mov     r8d, 38h ; '8'; dwBytes
0x1800281a9  mov     [rbp+57h+arg_0], 1
0x1800281ad  call    cs:__imp_HeapAlloc
0x1800281b3  test    rax, rax
0x1800281b6  jz      short loc_1800281E0
0x1800281b8  mov     rcx, rax; punkOuter
0x1800281bb  call    ??0CASPObjectContext@@QEAA@XZ; CASPObjectContext::CASPObjectContext(void)
0x1800281c0  mov     [rbp+57h+var_60], rax
0x1800281c4  mov     r12, rax
0x1800281c7  test    rax, rax
0x1800281ca  jz      short loc_1800281E4
0x1800281cc  mov     rax, [rsi+38h]
0x1800281d0  mov     [rsi+38h], r12
0x1800281d4  xor     r12d, r12d
0x1800281d7  mov     [rbp+57h+var_58], rax
0x1800281db  jmp     loc_18000C229
0x1800281e0  mov     [rbp+57h+var_60], r12
0x1800281e4  mov     r15d, 8007000Eh
0x1800281ea  jmp     loc_18000C3A6
0x1800281ef  call    cs:__imp_CoEnterServiceDomain
0x1800281f5  mov     r15d, eax
0x1800281f8  test    eax, eax
0x1800281fa  js      loc_18000C3A6
0x180028200  mov     r13d, 1
0x180028206  mov     [rbp+57h+var_88], r13d
0x18002820a  jmp     loc_18000C239
0x18002820f  or      dword ptr [rsi+8], 80h
0x180028216  jmp     loc_18000C3A6
0x18002821b  mov     rcx, r14; this
0x18002821e  call    ?AttachTo@CTemplate@@QEAAJPEAVCAppln@@@Z; CTemplate::AttachTo(CAppln *)
0x180028223  mov     edx, 1; int
0x180028228  mov     rcx, r14; this
0x18002822b  call    ?NotifyDebuggerOnPageEvent@CTemplate@@QEAAJH@Z; CTemplate::NotifyDebuggerOnPageEvent(int)
0x180028230  mov     ecx, [rbp+57h+arg_8]
0x180028233  test    eax, eax
0x180028235  movzx   ecx, cl
0x180028238  mov     eax, 1
0x18002823d  cmovns  ecx, eax
0x180028240  mov     [rbp+57h+arg_8], ecx
0x180028243  jmp     loc_18000C269
0x180028248  cmp     dword ptr [rbp+57h+var_78+4], 4
0x18002824c  jb      loc_18000C2CA
0x180028252  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180028256  call    ?RaiseEvent@ASP_START_SCRIPT_EXECUTION@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_START_SCRIPT_EXECUTION::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x18002825b  nop
0x18002825c  jmp     loc_18000C2CA
0x180028261  test    r12, r12
0x180028264  jz      loc_18000C2E7
0x18002826a  mov     rax, [r12]
0x18002826e  add     rdx, 28h ; '('
0x180028272  mov     rcx, r12
0x180028275  mov     rax, [rax+78h]
0x180028279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002827e  mov     r13d, 1
0x180028284  jmp     loc_18000C2E7
0x180028289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002828e  nop
0x18002828f  jmp     loc_18000C309
0x180028294  mov     rax, [r12]
0x180028298  mov     rcx, r12
0x18002829b  mov     rax, [rax+80h]
0x1800282a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282a7  nop
0x1800282a8  jmp     loc_18000C315
0x1800282ad  test    r15d, r15d
0x1800282b0  js      loc_18000C322
0x1800282b6  mov     rax, [r12]
0x1800282ba  mov     rcx, r12
0x1800282bd  mov     rax, [rax+50h]
0x1800282c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282c6  test    eax, eax
0x1800282c8  jnz     short loc_1800282DE
0x1800282ca  mov     rax, [r12]
0x1800282ce  mov     rcx, r12
0x1800282d1  mov     rax, [rax+58h]
0x1800282d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282da  test    eax, eax
0x1800282dc  jz      short loc_1800282F9
0x1800282de  mov     rax, [r13+0]
0x1800282e2  mov     rcx, r13
0x1800282e5  mov     rax, [rax+40h]
0x1800282e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282ee  mov     r15d, eax
0x1800282f1  test    eax, eax
0x1800282f3  js      loc_18000C322
0x1800282f9  cmp     dword ptr [r13+2Ch], 0
0x1800282fe  jnz     loc_18000C322
0x180028304  mov     rax, [r13+0]
0x180028308  mov     rcx, r13
0x18002830b  mov     rax, [rax+38h]
0x18002830f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028314  mov     r15d, eax
0x180028317  jmp     loc_18000C322
0x18002831c  cmp     dword ptr [rbp+57h+var_78+4], 4
0x180028320  jb      loc_18000C371
0x180028326  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
  ... truncated ...
```

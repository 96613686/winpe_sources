# CHitObj::AssignApplnToBrowserRequest(int *)

- ea: `0x180009180`
- end: `0x1800095e3`
- name: `?AssignApplnToBrowserRequest@CHitObj@@QEAAJPEAH@Z`
- size: `1123`
- prototype: `__int64 __fastcall(CHitObj *__hidden this, int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18000a9d0`

## callees

- `0x180001400`
- `0x1800069d4`
- `0x180006c80`
- `0x180006d14`
- `0x180007034`
- `0x180008ef0`
- `0x180008f30`
- `0x180009180`
- `0x180016b50`
- `0x180018974`
- `0x180019e7c`
- `0x180023dd0`
- `0x180031628`
- `0x180032514`
- `0x180032708`
- `0x180034264`
- `0x180046744`
- `0x180046804`
- `0x180046908`
- `0x1800469c8`
- `0x180046a88`
- `0x18004706c`
- `0x180064010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000948e`
- `msvcrt!wcsncpy_s` at `0x18000948e`
- `msvcrt!wcscpy_s` at `0x1800094d1`
- `msvcrt!wcscpy_s` at `0x1800094d1`
- `msvcrt!_wcsupr` at `0x180009257`
- `msvcrt!_wcsupr` at `0x180009257`
- `USER32!CharPrevW` at `0x1800094a8`
- `USER32!CharPrevW` at `0x1800094a8`
- `ADVAPI32!SetThreadToken` at `0x1800271ab`
- `ADVAPI32!SetThreadToken` at `0x1800271ab`
- `ADVAPI32!RevertToSelf` at `0x180027178`
- `ADVAPI32!RevertToSelf` at `0x180027178`
- `KERNEL32!HeapFree` at `0x1800095b8`
- `KERNEL32!HeapFree` at `0x1800270e9`
- `KERNEL32!HeapFree` at `0x18002710f`
- `KERNEL32!HeapFree` at `0x1800095b8`
- `KERNEL32!HeapFree` at `0x1800270e9`
- `KERNEL32!HeapFree` at `0x18002710f`
- `KERNEL32!LeaveCriticalSection` at `0x18000936f`
- `KERNEL32!LeaveCriticalSection` at `0x180027023`
- `KERNEL32!LeaveCriticalSection` at `0x18002705d`
- `KERNEL32!LeaveCriticalSection` at `0x1800270aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800270d7`
- `KERNEL32!LeaveCriticalSection` at `0x1800270fd`
- `KERNEL32!LeaveCriticalSection` at `0x18000936f`
- `KERNEL32!LeaveCriticalSection` at `0x180027023`
- `KERNEL32!LeaveCriticalSection` at `0x18002705d`
- `KERNEL32!LeaveCriticalSection` at `0x1800270aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800270d7`
- `KERNEL32!LeaveCriticalSection` at `0x1800270fd`
- `KERNEL32!SetLastError` at `0x180026f6f`
- `KERNEL32!SetLastError` at `0x180026f6f`
- `KERNEL32!EnterCriticalSection` at `0x180009264`
- `KERNEL32!EnterCriticalSection` at `0x180027071`
- `KERNEL32!EnterCriticalSection` at `0x180009264`
- `KERNEL32!EnterCriticalSection` at `0x180027071`
- `KERNEL32!GetLastError` at `0x180009520`
- `KERNEL32!GetLastError` at `0x180026f4a`
- `KERNEL32!GetLastError` at `0x180009520`
- `KERNEL32!GetLastError` at `0x180026f4a`
- `KERNEL32!GetCurrentThread` at `0x180027197`
- `KERNEL32!GetCurrentThread` at `0x180027197`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800091dc`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800091dc`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180026f60`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180026f60`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800091ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800091f4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009232`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026f8a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800091ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800091f4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009232`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026f8a`
- `iisutil!WriteRefTraceLog` at `0x180027228`
- `iisutil!WriteRefTraceLog` at `0x180027228`

## string_xrefs

- `0x180009206`: `UNICODE_APPL_MD_PATH`
- `0x180026f9c`: `UNICODE_APPL_MD_PATH`

## pseudocode

```c
__int64 __fastcall CHitObj::AssignApplnToBrowserRequest(CHitObj *this, int *a2)
{
  CAppln *v2; // r15
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(_QWORD, const char *, void *, int *); // rbx
  void *Ptr; // rax
  int v6; // ebx
  wchar_t *v7; // rax
  unsigned __int8 *v8; // rbx
  __int64 v9; // r13
  __int64 v10; // rax
  bool v11; // zf
  __int64 v12; // rdi
  unsigned int v13; // r12d
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rsi
  __int64 v17; // rdi
  CAppln *v18; // rdi
  __int64 v19; // r8
  signed __int32 v20; // r14d
  __int64 v22; // r8
  const void *v23; // rdx
  int v24; // eax
  int updated; // esi
  unsigned __int16 *SzAppPhysicalPath; // rsi
  struct _EXTENSION_CONTROL_BLOCK **v27; // rcx
  const struct _GUID *v28; // rdx
  int v29; // ebx
  __int64 v30; // rcx
  const struct _GUID *v31; // rdx
  int FileAttributes; // eax
  BOOL v33; // ebx
  struct _EXTENSION_CONTROL_BLOCK **v34; // rcx
  const struct _GUID *v35; // rdx
  __int64 v36; // rcx
  const struct _GUID *v37; // rdx
  __int64 (__fastcall *v38)(_QWORD, const char *, void *, int *); // rbx
  void *v39; // rax
  struct CIsapiReqInfo *v40; // rdx
  CApplnMgr *v41; // rcx
  CTemplateCacheManager *v42; // rcx
  __int64 v43; // rcx
  const struct _GUID *v44; // rdx
  int v45; // ebx
  HANDLE CurrentThread; // rax
  void *v47; // rdx
  const struct _GUID *v48; // rdx
  int Size; // [rsp+30h] [rbp-D0h] BYREF
  CAppln *v50; // [rsp+38h] [rbp-C8h] BYREF
  int v51; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Thread; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Destination[520]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  v2 = this;
  v3 = *((_QWORD *)this + 8);
  Thread = a2;
  v50 = this;
  if ( (*(_BYTE *)(v3 + 52) & 2) == 0 )
  {
    *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v3 + 376)) = 0;
    Size = BUFFER::QuerySize((BUFFER *)(v3 + 376));
    v4 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v3 + 8) + 160LL);
    Ptr = BUFFER::QueryPtr((BUFFER *)(v3 + 376));
    v6 = v4(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL), "UNICODE_APPL_MD_PATH", Ptr, &Size);
    if ( !v6 && GetLastError() == 122 )
    {
      if ( BUFFER::Resize((BUFFER *)(v3 + 376), Size) )
      {
        v38 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v3 + 8) + 160LL);
        v39 = BUFFER::QueryPtr((BUFFER *)(v3 + 376));
        v6 = v38(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL), "UNICODE_APPL_MD_PATH", v39, &Size);
      }
      else
      {
        SetLastError(0xEu);
        v6 = 0;
      }
    }
    *(_DWORD *)(v3 + 52) ^= (*(_DWORD *)(v3 + 52) ^ (2 * v6)) & 2;
  }
  v7 = (wchar_t *)BUFFER::QueryPtr((BUFFER *)(v3 + 376));
  v8 = (unsigned __int8 *)v7;
  if ( !v7 )
    return 2147500037LL;
  _wcsupr(v7);
  EnterCriticalSection(&stru_180079B28);
  v9 = -1;
  v10 = -1;
  do
    v11 = *(_WORD *)&v8[2 * v10++ + 2] == 0;
  while ( !v11 );
  v12 = qword_180079A40;
  if ( !qword_180079A40 )
    goto LABEL_27;
  v13 = 2 * v10;
  if ( (unsigned int (__fastcall *)(const unsigned __int8 *, int))qword_180079A48 == DefaultHash )
  {
    v14 = DefaultHash(v8, 2 * v10);
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(unsigned __int8 *, _QWORD))qword_180079A48)(v8, v13);
    v12 = qword_180079A40;
  }
  if ( (_DWORD)qword_180079A50 == 17 )
    v15 = v14 % 0x11;
  else
    v15 = v14 % (unsigned int)qword_180079A50;
  v16 = 0;
  v17 = *(_QWORD *)(v12 + 8LL * v15);
  if ( v17 )
  {
    while ( !v16 )
    {
      v22 = *(unsigned int *)(v17 + 16);
      v23 = *(const void **)(v17 + 8);
      if ( *(int (**)(CHashTable *__hidden, const void *, int, const void *, int))g_ApplnMgr == CHashTable::FIsEqual )
        v24 = CHashTable::FIsEqual((CHashTable *)&g_ApplnMgr, v23, v22, v8, v13);
      else
        v24 = (*(__int64 (__fastcall **)(__int64 *, const void *, __int64, unsigned __int8 *, unsigned int))g_ApplnMgr)(
                &g_ApplnMgr,
                v23,
                v22,
                v8,
                v13);
      if ( v24 )
      {
        v16 = v17;
      }
      else
      {
        if ( *(__int16 *)(v17 + 20) <= 0 )
          break;
        v17 = *(_QWORD *)(v17 + 32);
      }
      if ( !v17 )
        break;
    }
    v2 = v50;
  }
  if ( !v16 )
  {
LABEL_27:
    v18 = 0;
    updated = 1;
    v50 = 0;
LABEL_28:
    if ( !updated )
      goto LABEL_18;
    goto LABEL_29;
  }
  v11 = (*(_BYTE *)(v16 + 40) & 4) == 0;
  v18 = (CAppln *)(v16 - 32);
  v50 = (CAppln *)(v16 - 32);
  if ( !v11 )
  {
LABEL_70:
    *(_DWORD *)Thread = 1;
    goto LABEL_71;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v18 + 19) + 8LL) )
    goto LABEL_18;
  v40 = (struct CIsapiReqInfo *)*((_QWORD *)v2 + 8);
  Size = 0;
  v51 = 0;
  updated = CAppln::UpdateConfig((CAppln *)(v16 - 32), v40, &Size, &v51);
  if ( updated < 0 )
  {
    LeaveCriticalSection(&stru_180079B28);
    return (unsigned int)updated;
  }
  if ( !Size )
    goto LABEL_28;
  CAppln::Restart(v18, 1);
  v50 = 0;
  if ( v51 )
  {
    LeaveCriticalSection(&stru_180079B28);
    CTemplateCacheManager::FlushAll(v42, 0);
    EnterCriticalSection(&stru_180079B28);
  }
  if ( !(unsigned int)CApplnMgr::FindAppln(v41, (unsigned __int16 *)v8, &v50) )
  {
    v18 = v50;
    if ( (*((_BYTE *)v50 + 72) & 4) == 0 )
      goto LABEL_18;
    goto LABEL_70;
  }
LABEL_29:
  SzAppPhysicalPath = CHitObj::GetSzAppPhysicalPath(v2);
  if ( !SzAppPhysicalPath )
  {
LABEL_71:
    LeaveCriticalSection(&stru_180079B28);
    return 2147500037LL;
  }
  v27 = (struct _EXTENSION_CONTROL_BLOCK **)*((_QWORD *)v2 + 8);
  if ( v27 && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(v27[1], 4u) )
    AspReqEvents::ASP_FIRST_REQUEST_FOR_APPLICATION::RaiseEvent(
      *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
      v28,
      SzAppPhysicalPath);
  v29 = CApplnMgr::AddAppln(
          (CApplnMgr *)v27,
          (unsigned __int16 *)v8,
          SzAppPhysicalPath,
          *((struct CIsapiReqInfo **)v2 + 8),
          &v50);
  if ( v29 < 0 )
  {
    LeaveCriticalSection(&stru_180079B28);
    HeapFree(g_hDenaliHeap, 0, SzAppPhysicalPath);
    return (unsigned int)v29;
  }
  do
    ++v9;
  while ( SzAppPhysicalPath[v9] );
  if ( (unsigned int)v9 > 0x104 )
  {
    LeaveCriticalSection(&stru_180079B28);
    HeapFree(g_hDenaliHeap, 0, SzAppPhysicalPath);
    return 2147500037LL;
  }
  wcsncpy_s(Destination, 0x208u, SzAppPhysicalPath, (unsigned int)(v9 + 1));
  if ( *CharPrevW(Destination, &Destination[(unsigned int)v9]) != 92 )
  {
    Destination[(unsigned int)v9] = 92;
    LODWORD(v9) = v9 + 1;
  }
  wcscpy_s(&Destination[(unsigned int)v9], 520LL - (unsigned int)v9, L"GLOBAL.ASA");
  v30 = *((_QWORD *)v2 + 8);
  if ( v30
    && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                       *(struct _EXTENSION_CONTROL_BLOCK **)(v30 + 8),
                       4u) )
  {
    AspReqEvents::ASP_START_GLOBAL_ASA_CHECK::RaiseEvent(
      *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
      v31,
      Destination);
  }
  FileAttributes = AspGetFileAttributes(Destination, 0, 0, 0, 0);
  v18 = v50;
  if ( FileAttributes >= 0 )
    goto LABEL_79;
  v33 = 0;
  if ( GetLastError() == 5 )
  {
    v43 = *((_QWORD *)v2 + 8);
    if ( v43
      && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                         *(struct _EXTENSION_CONTROL_BLOCK **)(v43 + 8),
                         2u) )
    {
      AspReqEvents::ASP_GLOBAL_ASA_ACCESS_DENIED::RaiseEvent(
        *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
        v44);
    }
    if ( *((_QWORD *)v2 + 12) )
    {
      RevertToSelf();
      v45 = AspGetFileAttributes(Destination, 0, 0, 0, 0);
      CurrentThread = GetCurrentThread();
      v47 = (void *)*((_QWORD *)v2 + 12);
      Thread = CurrentThread;
      SetThreadToken(&Thread, v47);
      v33 = v45 >= 0;
    }
  }
  if ( v33 )
  {
LABEL_79:
    CAppln::SetGlobalAsa(v18, Destination);
    v34 = (struct _EXTENSION_CONTROL_BLOCK **)*((_QWORD *)v2 + 8);
    if ( v34 && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(v34[1], 4u) )
      AspReqEvents::ASP_GLOBAL_ASA_ACCESS_SUCCESS::RaiseEvent(
        *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
        v48);
  }
  else
  {
    v34 = (struct _EXTENSION_CONTROL_BLOCK **)*((_QWORD *)v2 + 8);
    if ( v34 && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(v34[1], 4u) )
      AspReqEvents::ASP_GLOBAL_ASA_DOES_NOT_EXIST::RaiseEvent(
        *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
        v35);
  }
  CFileApplicationMap::AddFileApplication((CFileApplicationMap *)v34, Destination, v18);
  v50 = 0;
  if ( (unsigned int)RegisterASPDirMonitorEntry(SzAppPhysicalPath, &v50, 1) )
    CAppln::AddDirMonitorEntry(v18, v50);
  v36 = *((_QWORD *)v2 + 8);
  if ( v36
    && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                       *(struct _EXTENSION_CONTROL_BLOCK **)(v36 + 8),
                       4u) )
  {
    AspReqEvents::ASP_END_GLOBAL_ASA_CHECK::RaiseEvent(
      *(struct _EXTENSION_CONTROL_BLOCK **)(*((_QWORD *)v2 + 8) + 8LL),
      v37);
  }
  HeapFree(g_hDenaliHeap, 0, SzAppPhysicalPath);
  CAppln::UpdateConfig(v18, *((struct CIsapiReqInfo **)v2 + 8), 0, 0);
LABEL_18:
  *((_QWORD *)v2 + 3) = v18;
  v19 = *((_QWORD *)v18 + 19);
  *((_QWORD *)v2 + 29) = v19;
  v20 = _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 224), 1u);
  if ( CAppConfig::gm_pTraceLog )
    WriteRefTraceLog(CAppConfig::gm_pTraceLog, (unsigned int)(v20 + 1));
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v2 + 3) + 80LL));
  LeaveCriticalSection(&stru_180079B28);
  return 0;
}

```

## disassembly

```asm
0x180009180  push    rbp
0x180009182  push    rbx
0x180009183  push    rsi
0x180009184  push    rdi
0x180009185  push    r15
0x180009187  lea     rbp, [rsp-380h]
0x18000918f  sub     rsp, 480h
0x180009196  mov     rax, cs:__security_cookie
0x18000919d  xor     rax, rsp
0x1800091a0  mov     [rbp+3A0h+var_40], rax
0x1800091a7  mov     dword ptr [rdx], 0
0x1800091ad  mov     r15, rcx
0x1800091b0  mov     rdi, [rcx+40h]
0x1800091b4  mov     [rsp+4A0h+Thread], rdx
0x1800091b9  mov     [rsp+4A0h+var_468], rcx
0x1800091be  test    byte ptr [rdi+34h], 2
0x1800091c2  lea     rsi, [rdi+178h]
0x1800091c9  jnz     short loc_18000922F
0x1800091cb  mov     rcx, rsi
0x1800091ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800091d4  xor     ecx, ecx
0x1800091d6  mov     [rax], cx
0x1800091d9  mov     rcx, rsi
0x1800091dc  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800091e2  mov     [rsp+4A0h+var_470], eax
0x1800091e6  mov     rcx, rsi
0x1800091e9  mov     rax, [rdi+8]
0x1800091ed  mov     rbx, [rax+0A0h]
0x1800091f4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800091fa  mov     rcx, [rdi+8]
0x1800091fe  lea     r9, [rsp+4A0h+var_470]
0x180009203  mov     r8, rax
0x180009206  lea     rdx, aUnicodeApplMdP; "UNICODE_APPL_MD_PATH"
0x18000920d  mov     rax, rbx
0x180009210  mov     rcx, [rcx+8]
0x180009214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009219  mov     ebx, eax
0x18000921b  test    eax, eax
0x18000921d  jz      loc_180026F4A
0x180009223  lea     edx, [rbx+rbx]
0x180009226  xor     edx, [rdi+34h]
0x180009229  and     edx, 2
0x18000922c  xor     [rdi+34h], edx
0x18000922f  mov     rcx, rsi
0x180009232  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009238  mov     rbx, rax
0x18000923b  test    rax, rax
0x18000923e  jz      loc_180026FB6
0x180009244  mov     [rsp+4A0h+var_28], r13
0x18000924c  mov     rcx, rax; String
0x18000924f  mov     [rsp+4A0h+var_30], r14
0x180009257  call    cs:__imp__wcsupr
0x18000925d  lea     rcx, stru_180079B28; lpCriticalSection
0x180009264  call    cs:__imp_EnterCriticalSection
0x18000926a  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180009271  mov     rax, r13
0x180009274  cmp     word ptr [rbx+rax*2+2], 0
0x18000927a  lea     rax, [rax+1]
0x18000927e  jnz     short loc_180009274
0x180009280  mov     rdi, cs:qword_180079A40
0x180009287  mov     r14d, 1
0x18000928d  mov     [rsp+4A0h+arg_10], r12
0x180009295  test    rdi, rdi
0x180009298  jz      loc_1800093F4
0x18000929e  lea     r12d, [rax+rax]
0x1800092a2  mov     rax, cs:qword_180079A48
0x1800092a9  lea     rcx, ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x1800092b0  mov     edx, r12d; int
0x1800092b3  cmp     rax, rcx
0x1800092b6  mov     rcx, rbx; unsigned __int8 *
0x1800092b9  jnz     loc_180026FC0
0x1800092bf  call    ?DefaultHash@@YAKPEBEH@Z; DefaultHash(uchar const *,int)
0x1800092c4  mov     r8d, dword ptr cs:qword_180079A50
0x1800092cb  mov     ecx, eax
0x1800092cd  cmp     r8d, 11h
0x1800092d1  jnz     loc_1800095D5
0x1800092d7  mov     eax, 0F0F0F0F1h
0x1800092dc  mul     ecx
0x1800092de  shr     edx, 4
0x1800092e1  imul    eax, edx, 11h
0x1800092e4  sub     ecx, eax
0x1800092e6  mov     eax, ecx
0x1800092e8  xor     esi, esi
0x1800092ea  mov     rdi, [rdi+rax*8]
0x1800092ee  test    rdi, rdi
0x1800092f1  jz      short loc_180009308
0x1800092f3  lea     r15, ?FIsEqual@CHashTable@@MEAAHPEBXH0H@Z; CHashTable::FIsEqual(void const *,int,void const *,int)
0x1800092fa  test    rsi, rsi
0x1800092fd  jz      loc_1800093AC
0x180009303  mov     r15, [rsp+4A0h+var_468]
0x180009308  test    rsi, rsi
0x18000930b  jz      loc_1800093F4
0x180009311  test    byte ptr [rsi+28h], 4
0x180009315  lea     rdi, [rsi-20h]
0x180009319  mov     [rsp+4A0h+var_468], rdi
0x18000931e  jnz     loc_18002709B
0x180009324  mov     rax, [rdi+98h]
0x18000932b  cmp     dword ptr [rax+8], 0
0x18000932f  jnz     loc_180026FF0
0x180009335  mov     [r15+18h], rdi
0x180009339  mov     r8, [rdi+98h]
0x180009340  mov     [r15+0E8h], r8
0x180009347  lock xadd [r8+0E0h], r14d
0x180009350  mov     rcx, cs:?gm_pTraceLog@CAppConfig@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CAppConfig::gm_pTraceLog
0x180009357  test    rcx, rcx
0x18000935a  jnz     loc_180027224
0x180009360  mov     rax, [r15+18h]
0x180009364  lock inc dword ptr [rax+50h]
0x180009368  lea     rcx, stru_180079B28; lpCriticalSection
0x18000936f  call    cs:__imp_LeaveCriticalSection
0x180009375  xor     eax, eax
0x180009377  mov     r12, [rsp+4A0h+arg_10]
0x18000937f  mov     r13, [rsp+4A0h+var_28]
0x180009387  mov     r14, [rsp+4A0h+var_30]
0x18000938f  mov     rcx, [rbp+3A0h+var_40]
0x180009396  xor     rcx, rsp; StackCookie
0x180009399  call    __security_check_cookie
0x18000939e  add     rsp, 480h
0x1800093a5  pop     r15
0x1800093a7  pop     rdi
0x1800093a8  pop     rsi
0x1800093a9  pop     rbx
0x1800093aa  pop     rbp
0x1800093ab  retn
0x1800093ac  mov     rax, cs:?g_ApplnMgr@@3VCApplnMgr@@A; CApplnMgr g_ApplnMgr
0x1800093b3  lea     rcx, ?g_ApplnMgr@@3VCApplnMgr@@A; this
0x1800093ba  mov     r8d, [rdi+10h]; int
0x1800093be  mov     r9, rbx; void *
0x1800093c1  mov     rdx, [rdi+8]; void *
0x1800093c5  mov     dword ptr [rsp+4A0h+var_480], r12d; int
0x1800093ca  mov     rax, [rax]
0x1800093cd  cmp     rax, r15
0x1800093d0  jnz     loc_180026FD1
0x1800093d6  call    ?FIsEqual@CHashTable@@MEAAHPEBXH0H@Z; CHashTable::FIsEqual(void const *,int,void const *,int)
0x1800093db  test    eax, eax
0x1800093dd  jz      loc_180026FDC
0x1800093e3  mov     rsi, rdi
0x1800093e6  test    rdi, rdi
0x1800093e9  jnz     loc_1800092FA
0x1800093ef  jmp     loc_180009303
0x1800093f4  xor     edi, edi
0x1800093f6  mov     esi, r14d
0x1800093f9  mov     [rsp+4A0h+var_468], rdi
0x1800093fe  test    esi, esi
0x180009400  jz      loc_180009335
0x180009406  mov     rcx, r15; this
0x180009409  call    ?GetSzAppPhysicalPath@CHitObj@@QEAAPEAGXZ; CHitObj::GetSzAppPhysicalPath(void)
0x18000940e  mov     rsi, rax
0x180009411  test    rax, rax
0x180009414  jz      loc_1800270A3
0x18000941a  mov     rcx, [r15+40h]
0x18000941e  test    rcx, rcx
0x180009421  jz      short loc_180009439
0x180009423  mov     rcx, [rcx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180009427  mov     edx, 4; unsigned int
0x18000942c  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180009431  test    eax, eax
0x180009433  jnz     loc_1800270BA
0x180009439  mov     r9, [r15+40h]; struct CIsapiReqInfo *
0x18000943d  lea     rax, [rsp+4A0h+var_468]
0x180009442  mov     r8, rsi; unsigned __int16 *
0x180009445  mov     [rsp+4A0h+var_480], rax; struct CAppln **
0x18000944a  mov     rdx, rbx; unsigned __int16 *
0x18000944d  call    ?AddAppln@CApplnMgr@@QEAAJPEAG0PEAVCIsapiReqInfo@@PEAPEAVCAppln@@@Z; CApplnMgr::AddAppln(ushort *,ushort *,CIsapiReqInfo *,CAppln * *)
0x180009452  mov     ebx, eax
0x180009454  test    eax, eax
0x180009456  js      loc_1800270D0
0x18000945c  nop     dword ptr [rax+00h]
0x180009460  inc     r13
0x180009463  cmp     word ptr [rsi+r13*2], 0
0x180009469  jnz     short loc_180009460
0x18000946b  cmp     r13d, 104h
0x180009472  ja      loc_1800270F6
0x180009478  lea     edi, [r13+1]
0x18000947c  mov     ebx, 208h
0x180009481  mov     r9d, edi; MaxCount
0x180009484  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180009489  mov     edx, ebx; SizeInWords
0x18000948b  mov     r8, rsi; Source
0x18000948e  call    cs:__imp_wcsncpy_s
0x180009494  mov     eax, r13d
0x180009497  lea     r12, [rsp+4A0h+Destination]
0x18000949c  lea     rcx, [rsp+4A0h+Destination]; lpszStart
0x1800094a1  lea     r12, [r12+rax*2]
0x1800094a5  mov     rdx, r12; lpszCurrent
0x1800094a8  call    cs:__imp_CharPrevW
0x1800094ae  cmp     word ptr [rax], 5Ch ; '\'
0x1800094b2  jnz     loc_18002711F
0x1800094b8  mov     eax, r13d
0x1800094bb  lea     rcx, [rsp+4A0h+Destination]
0x1800094c0  sub     rbx, rax
0x1800094c3  lea     r8, aGlobalAsa_0; "GLOBAL.ASA"
0x1800094ca  mov     rdx, rbx; SizeInWords
0x1800094cd  lea     rcx, [rcx+rax*2]; Destination
0x1800094d1  call    cs:__imp_wcscpy_s
0x1800094d7  mov     rcx, [r15+40h]
0x1800094db  test    rcx, rcx
0x1800094de  jz      short loc_1800094F6
0x1800094e0  mov     rcx, [rcx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x1800094e4  mov     edx, 4; unsigned int
0x1800094e9  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x1800094ee  test    eax, eax
0x1800094f0  jnz     loc_18002712E
0x1800094f6  xor     r9d, r9d; unsigned int *
0x1800094f9  mov     [rsp+4A0h+var_480], 0; unsigned int *
0x180009502  xor     r8d, r8d; struct _FILETIME *
0x180009505  lea     rcx, [rsp+4A0h+Destination]; unsigned __int16 *
0x18000950a  xor     edx, edx; void *
0x18000950c  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x180009511  mov     rdi, [rsp+4A0h+var_468]
0x180009516  test    eax, eax
0x180009518  jns     loc_1800271CE
0x18000951e  xor     ebx, ebx
0x180009520  call    cs:__imp_GetLastError
0x180009526  cmp     eax, 5
0x180009529  jz      loc_180027146
0x18000952f  test    ebx, ebx
0x180009531  jnz     loc_1800271CE
0x180009537  mov     rcx, [r15+40h]
0x18000953b  test    rcx, rcx
0x18000953e  jz      short loc_180009556
0x180009540  mov     rcx, [rcx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180009544  mov     edx, 4; unsigned int
0x180009549  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x18000954e  test    eax, eax
0x180009550  jnz     loc_1800271BB
0x180009556  mov     r8, rdi; struct CAppln *
0x180009559  lea     rdx, [rsp+4A0h+Destination]; unsigned __int16 *
0x18000955e  call    ?AddFileApplication@CFileApplicationMap@@QEAAJPEBGPEAVCAppln@@@Z; CFileApplicationMap::AddFileApplication(ushort const *,CAppln *)
0x180009563  mov     r8d, r14d; int
0x180009566  mov     [rsp+4A0h+var_468], 0
0x18000956f  lea     rdx, [rsp+4A0h+var_468]; struct CASPDirMonitorEntry **
0x180009574  mov     rcx, rsi; unsigned __int16 *
0x180009577  call    ?RegisterASPDirMonitorEntry@@YAHPEBGPEAPEAVCASPDirMonitorEntry@@H@Z; RegisterASPDirMonitorEntry(ushort const *,CASPDirMonitorEntry * *,int)
0x18000957c  test    eax, eax
0x18000957e  jz      short loc_18000958D
0x180009580  mov     rdx, [rsp+4A0h+var_468]; struct CDirMonitorEntry *
0x180009585  mov     rcx, rdi; this
0x180009588  call    ?AddDirMonitorEntry@CAppln@@QEAAJPEAVCDirMonitorEntry@@@Z; CAppln::AddDirMonitorEntry(CDirMonitorEntry *)
0x18000958d  mov     rcx, [r15+40h]
0x180009591  test    rcx, rcx
0x180009594  jz      short loc_1800095AC
0x180009596  mov     rcx, [rcx+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18000959a  mov     edx, 4; unsigned int
0x18000959f  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x1800095a4  test    eax, eax
0x1800095a6  jnz     loc_180027211
0x1800095ac  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800095b3  mov     r8, rsi; lpMem
0x1800095b6  xor     edx, edx; dwFlags
0x1800095b8  call    cs:__imp_HeapFree
0x1800095be  mov     rdx, [r15+40h]; struct CIsapiReqInfo *
0x1800095c2  xor     r9d, r9d; int *
0x1800095c5  xor     r8d, r8d; int *
0x1800095c8  mov     rcx, rdi; this
0x1800095cb  call    ?UpdateConfig@CAppln@@QEAAJPEAVCIsapiReqInfo@@PEAH1@Z; CAppln::UpdateConfig(CIsapiReqInfo *,int *,int *)
0x1800095d0  jmp     loc_180009335
0x1800095d5  mov     eax, ecx
0x1800095d7  xor     edx, edx
0x1800095d9  div     r8d
0x1800095dc  mov     ecx, edx
0x1800095de  jmp     loc_1800092E6
0x180026f4a  call    cs:__imp_GetLastError
0x180026f50  cmp     eax, 7Ah ; 'z'
0x180026f53  jnz     loc_180009223
0x180026f59  mov     edx, [rsp+4A0h+var_470]
0x180026f5d  mov     rcx, rsi
0x180026f60  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180026f66  test    al, al
0x180026f68  jnz     short loc_180026F7C
0x180026f6a  mov     ecx, 0Eh; dwErrCode
0x180026f6f  call    cs:__imp_SetLastError
0x180026f75  xor     ebx, ebx
0x180026f77  jmp     loc_180009223
0x180026f7c  mov     rax, [rdi+8]
0x180026f80  mov     rcx, rsi
0x180026f83  mov     rbx, [rax+0A0h]
0x180026f8a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180026f90  mov     rcx, [rdi+8]
0x180026f94  lea     r9, [rsp+4A0h+var_470]
0x180026f99  mov     r8, rax
0x180026f9c  lea     rdx, aUnicodeApplMdP; "UNICODE_APPL_MD_PATH"
0x180026fa3  mov     rax, rbx
0x180026fa6  mov     rcx, [rcx+8]
0x180026faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026faf  mov     ebx, eax
0x180026fb1  jmp     loc_180009223
0x180026fb6  mov     eax, 80004005h
0x180026fbb  jmp     loc_18000938F
0x180026fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fc5  mov     rdi, cs:qword_180079A40
0x180026fcc  jmp     loc_1800092C4
0x180026fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fd6  nop
0x180026fd7  jmp     loc_1800093DB
0x180026fdc  cmp     word ptr [rdi+14h], 0
0x180026fe1  jle     loc_180009303
0x180026fe7  mov     rdi, [rdi+20h]
0x180026feb  jmp     loc_1800093E6
0x180026ff0  mov     rdx, [r15+40h]; struct CIsapiReqInfo *
  ... truncated ...
```

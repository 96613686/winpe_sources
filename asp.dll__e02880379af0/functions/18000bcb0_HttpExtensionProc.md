# HttpExtensionProc

- ea: `0x18000bcb0`
- end: `0x18000c197`
- name: `HttpExtensionProc`
- size: `1255`
- prototype: `DWORD __stdcall(EXTENSION_CONTROL_BLOCK *pECB)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callees

- `0x18000243c`
- `0x180002ae8`
- `0x180003314`
- `0x180007e20`
- `0x18000a160`
- `0x18000a9d0`
- `0x18000bcb0`
- `0x180012628`
- `0x180019e7c`
- `0x18001a600`
- `0x180023dd0`
- `0x18003e9d8`
- `0x18003ead0`
- `0x18003f600`
- `0x180040f7c`
- `0x180043218`
- `0x180046c44`
- `0x180046d04`
- `0x180046fac`
- `0x180064010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180027fd4`
- `msvcrt!strcpy_s` at `0x180027fd4`
- `KERNEL32!GetACP` at `0x18000c021`
- `KERNEL32!GetACP` at `0x18000c021`
- `KERNEL32!LeaveCriticalSection` at `0x18000beb2`
- `KERNEL32!LeaveCriticalSection` at `0x18000c152`
- `KERNEL32!LeaveCriticalSection` at `0x180027f1d`
- `KERNEL32!LeaveCriticalSection` at `0x18000beb2`
- `KERNEL32!LeaveCriticalSection` at `0x18000c152`
- `KERNEL32!LeaveCriticalSection` at `0x180027f1d`
- `KERNEL32!SetLastError` at `0x180028161`
- `KERNEL32!SetLastError` at `0x180028161`
- `KERNEL32!EnterCriticalSection` at `0x18000be8b`
- `KERNEL32!EnterCriticalSection` at `0x18000c13c`
- `KERNEL32!EnterCriticalSection` at `0x180027efa`
- `KERNEL32!EnterCriticalSection` at `0x18000be8b`
- `KERNEL32!EnterCriticalSection` at `0x18000c13c`
- `KERNEL32!EnterCriticalSection` at `0x180027efa`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000c18c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000c18c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000bcd6`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000bf6c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000bcd6`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000bf6c`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bcfc`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd20`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd2d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd6e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd7b`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bcfc`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd20`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd2d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd6e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bd7b`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd13`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd47`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd61`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd13`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd47`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000bd61`
- `iisutil!PuDbgPrint` at `0x180027fa4`
- `iisutil!PuDbgPrint` at `0x18002803a`
- `iisutil!PuDbgPrint` at `0x180027fa4`
- `iisutil!PuDbgPrint` at `0x18002803a`

## pseudocode

```c
DWORD __stdcall HttpExtensionProc(EXTENSION_CONTROL_BLOCK *pECB)
{
  char *v2; // rax
  char *v3; // rdi
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  const struct _GUID *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // ebx
  int *v12; // rax
  int v13; // ebp
  unsigned int v14; // r14d
  volatile signed __int32 *v15; // rax
  signed __int32 v16; // ebx
  CPerfData *v17; // rcx
  _QWORD *v18; // rbx
  signed int v19; // ebp
  int v20; // r12d
  int v21; // r15d
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned int (__fastcall *v24)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v25; // rdx
  int HitInit; // eax
  int v28; // edx
  const struct _GUID *v29; // rdx
  const struct _GUID *v30; // rdx
  const struct _GUID *v31; // rdx
  void (__fastcall **v32)(void *, __int64); // rax
  int v33; // [rsp+30h] [rbp-258h] BYREF
  GUID *v34; // [rsp+38h] [rbp-250h] BYREF
  __int128 v35; // [rsp+40h] [rbp-248h]
  char Destination[512]; // [rsp+50h] [rbp-238h] BYREF

  v2 = (char *)ALLOC_CACHE_HANDLER::Alloc(CIsapiReqInfo::sm_pach);
  v3 = v2;
  if ( !v2 )
  {
    SetLastError(0xEu);
    return 4;
  }
  BUFFER::BUFFER((BUFFER *)(v2 + 72));
  BUFFER::BUFFER((BUFFER *)(v3 + 376), (unsigned __int8 *)v3 + 120, 0x100u);
  BUFFER::BUFFER((BUFFER *)(v3 + 424));
  BUFFER::BUFFER((BUFFER *)(v3 + 472));
  BUFFER::BUFFER((BUFFER *)(v3 + 776), (unsigned __int8 *)v3 + 520, 0x100u);
  BUFFER::BUFFER((BUFFER *)(v3 + 1080), (unsigned __int8 *)v3 + 824, 0x100u);
  BUFFER::BUFFER((BUFFER *)(v3 + 1128));
  BUFFER::BUFFER((BUFFER *)(v3 + 1176));
  *((_DWORD *)v3 + 13) &= 0xFFFFF000;
  *(_DWORD *)v3 = 1;
  *((_DWORD *)v3 + 14) = 0;
  *(_QWORD *)(v3 + 60) = 1;
  *((_QWORD *)v3 + 2) = -1;
  *((_QWORD *)v3 + 3) = -1;
  *((_QWORD *)v3 + 4) = -1;
  *((_QWORD *)v3 + 5) = -1;
  *((_DWORD *)v3 + 12) = -1;
  *((_DWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 157) = 0;
  *((_QWORD *)v3 + 156) = 0;
  *((_QWORD *)v3 + 154) = 0;
  *((_QWORD *)v3 + 1) = pECB;
  *((_QWORD *)v3 + 153) = 1;
  *((_QWORD *)v3 + 155) = 0;
  *((_QWORD *)v3 + 158) = 0;
  *((_QWORD *)v3 + 159) = 0;
  ConnID = pECB->ConnID;
  v34 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  ServerSupportFunction = pECB->ServerSupportFunction;
  v35 = 0;
  if ( ((unsigned int (__fastcall *)(HCONN, __int64, GUID **, _QWORD, _QWORD))ServerSupportFunction)(
         ConnID,
         1044,
         &v34,
         0,
         0)
    && DWORD2(v35) )
  {
    AspReqEvents::ASP_START_REQUEST::RaiseEvent(
      *((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1),
      v6,
      *(const char **)(*((_QWORD *)v3 + 1) + 128LL));
  }
  LODWORD(v7) = *((_DWORD *)v3 + 4);
  if ( (_DWORD)v7 == -1 )
  {
    v8 = *(_QWORD *)(*((_QWORD *)v3 + 1) + 112LL);
    if ( v8 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_BYTE *)(v8 + v7) );
    }
    else
    {
      LODWORD(v7) = 0;
    }
    *((_DWORD *)v3 + 4) = v7;
  }
  v9 = *((_QWORD *)v3 + 1);
  v10 = -1;
  do
    ++v10;
  while ( *(_BYTE *)(*(_QWORD *)(v9 + 128) + v10) );
  v11 = v7 + v10 + *(_DWORD *)(v9 + 136);
  EnterCriticalSection(&stru_18007CB60);
  if ( (dword_18007CB28 & 1) != 0 )
    v12 = (int *)(qword_18007CB88 + 24);
  else
    v12 = &dword_18007CBAC;
  *v12 += v11;
  LeaveCriticalSection(&stru_18007CB60);
  if ( g_fFirstHit )
  {
    EnterCriticalSection(&g_csFirstHitLock);
    if ( g_fFirstHit )
    {
      HitInit = FirstHitInit((struct CIsapiReqInfo *)v3);
      g_fFirstHit = 0;
      if ( !HitInit )
        MSG_Error(0x74u);
    }
    LeaveCriticalSection(&g_csFirstHitLock);
  }
  if ( g_fFirstHitFailed )
  {
    Handle500Error(0xFABu, (struct CIsapiReqInfo *)v3);
    goto LABEL_34;
  }
  v13 = 0;
  v14 = 0;
  if ( (dword_18007CB28 & 1) != 0 )
    v15 = (volatile signed __int32 *)(qword_18007CB88 + 76);
  else
    v15 = (volatile signed __int32 *)byte_18007CBE0;
  v16 = _InterlockedExchangeAdd(v15, 1u);
  if ( (_BYTE)dword_180079F78 )
  {
    EnterCriticalSection(&stru_180079FC0);
    if ( dword_180079F78 )
    {
      dword_180079F78 = 0;
      ReadConfigFromSystem(0, v28);
    }
    LeaveCriticalSection(&stru_180079FC0);
  }
  if ( g_fShutDownInProgress )
    v13 = -2147467259;
  DoHangDetection((struct CIsapiReqInfo *)v3, v16 + 1);
  if ( g_nOOMErrors && !g_fOOMRecycleDisabled && !_InterlockedExchange(&g_fUnhealthyReported, 1) )
  {
    if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                         *((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1),
                         2u) )
      AspReqEvents::ASP_UNHEALTHY_FAILURE::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1), v29, 0x20u);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        2019,
        "DoOOMDetection",
        "DoOOMDetection: Reporting ill state to ISAPI\n");
    if ( !(unsigned int)CchLoadStringOfId(0x75u, Destination, 512) )
      strcpy_s(Destination, 0x200u, "ASP unhealthy due to an out of memory condition.");
    (*(void (__fastcall **)(_QWORD, __int64, char *, _QWORD, _QWORD))(*((_QWORD *)v3 + 1) + 184LL))(
      *(_QWORD *)(*((_QWORD *)v3 + 1) + 8LL),
      1032,
      Destination,
      0,
      0);
    ++g_nIllStatesReported;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        2033,
        "DoOOMDetection",
        "############################### Ill'ing ##############################\n");
  }
  if ( v13 < 0 )
  {
LABEL_76:
    Handle500Error(v14, (struct CIsapiReqInfo *)v3);
    goto LABEL_34;
  }
  if ( dword_180079FA4 && g_nBrowserRequests >= dword_180079FA4 )
  {
    v14 = 4012;
LABEL_60:
    if ( DWORD1(xmmword_180079F90) && !(unsigned int)SendHtmlSubstitute((struct CIsapiReqInfo *)v3) )
    {
      _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v17, 16));
      goto LABEL_34;
    }
    _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v17, 15));
    goto LABEL_76;
  }
  v33 = 0;
  v18 = ALLOC_CACHE_HANDLER::Alloc(CHitObj::sm_pach);
  if ( !v18 )
    goto LABEL_76;
  v18[1] = 0x100000;
  *v18 = &CHitObj::`vftable';
  v18[2] = 0;
  v18[3] = 0;
  v18[4] = 0;
  v18[5] = 0;
  v18[6] = 0;
  v18[7] = 0;
  v18[8] = 0;
  v18[9] = 0;
  v18[10] = 0;
  v18[11] = 0;
  v18[12] = 0;
  v18[13] = 0;
  *((_DWORD *)v18 + 35) = -1;
  v18[18] = 0;
  v18[19] = 0;
  v18[20] = 0;
  *((_DWORD *)v18 + 42) = 2048;
  v18[22] = 0;
  v18[23] = 0;
  *((_DWORD *)v18 + 48) = 0;
  v18[25] = 0;
  v18[26] = 0;
  v18[27] = 0;
  v18[28] = 0;
  v18[29] = 0;
  *((_DWORD *)v18 + 41) = GetACP();
  v19 = CHitObj::BrowserRequestInit((CHitObj *)v18, (struct CIsapiReqInfo *)v3, &v33);
  v14 = 4012;
  if ( v19 < 0 )
  {
    v21 = 0;
    if ( v33 == 4012 )
    {
      v21 = 1;
      if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                           *((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1),
                           2u) )
        AspReqEvents::ASP_SERVER_TOO_BUSY_TO_QUEUE::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1), v31);
    }
    goto LABEL_72;
  }
  v20 = 0;
  if ( (v18[1] & 0x800) != 0 )
  {
    v20 = 1;
    (*(void (__fastcall **)(_QWORD *, __int64))*v18)(v18, 1);
    v18 = 0;
  }
  v21 = 0;
  if ( !v20 )
  {
    v22 = *((_QWORD *)v3 + 1);
    v34 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v23 = *(_QWORD *)(v22 + 8);
    v24 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v22 + 184);
    v35 = 0;
    if ( v24(v23, 1044, &v34, 0, 0) && DWORD2(v35) && DWORD1(v35) >= 4 )
      AspReqEvents::ASP_QUEUE_REQUEST::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1), v25);
    v19 = CHitObj::PostViperAsyncCall((CHitObj *)v18);
    if ( v19 < 0 )
    {
      v21 = 1;
      if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                           *((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1),
                           2u) )
        AspReqEvents::ASP_QUEUE_REQUEST_FAILED::RaiseEvent(*((struct _EXTENSION_CONTROL_BLOCK **)v3 + 1), v30, v19);
      if ( v18 )
      {
LABEL_72:
        v32 = (void (__fastcall **)(void *, __int64))*v18;
        *((_DWORD *)v18 + 2) |= 0x1000u;
        (*v32)(v18, 1);
      }
    }
  }
  if ( v19 < 0 )
  {
    if ( !v21 )
    {
      v14 = v33;
      goto LABEL_76;
    }
    goto LABEL_60;
  }
LABEL_34:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
  {
    CIsapiReqInfo::~CIsapiReqInfo((CIsapiReqInfo *)v3);
    if ( CIsapiReqInfo::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CIsapiReqInfo::sm_pach, v3);
  }
  return 3;
}

```

## disassembly

```asm
0x18000bcb0  push    rbx
0x18000bcb2  push    rdi
0x18000bcb3  sub     rsp, 278h
0x18000bcba  mov     rax, cs:__security_cookie
0x18000bcc1  xor     rax, rsp
0x18000bcc4  mov     [rsp+288h+var_38], rax
0x18000bccc  mov     rbx, rcx
0x18000bccf  mov     rcx, cs:?sm_pach@CIsapiReqInfo@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CIsapiReqInfo::sm_pach
0x18000bcd6  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000bcdc  mov     rdi, rax
0x18000bcdf  test    rax, rax
0x18000bce2  jz      loc_18002815C
0x18000bce8  mov     [rsp+288h+arg_8], rsi
0x18000bcf0  lea     rcx, [rax+48h]
0x18000bcf4  mov     [rsp+288h+var_18], r13
0x18000bcfc  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bd02  lea     rdx, [rdi+78h]
0x18000bd06  mov     r8d, 100h
0x18000bd0c  lea     rcx, [rdi+178h]
0x18000bd13  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000bd19  lea     rcx, [rdi+1A8h]
0x18000bd20  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bd26  lea     rcx, [rdi+1D8h]
0x18000bd2d  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bd33  lea     rdx, [rdi+208h]
0x18000bd3a  mov     r8d, 100h
0x18000bd40  lea     rcx, [rdi+308h]
0x18000bd47  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000bd4d  lea     rdx, [rdi+338h]
0x18000bd54  mov     r8d, 100h
0x18000bd5a  lea     rcx, [rdi+438h]
0x18000bd61  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000bd67  lea     rcx, [rdi+468h]
0x18000bd6e  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bd74  lea     rcx, [rdi+498h]
0x18000bd7b  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bd81  and     dword ptr [rdi+34h], 0FFFFF000h
0x18000bd88  lea     rax, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000bd8f  xor     r13d, r13d
0x18000bd92  mov     dword ptr [rdi], 1
0x18000bd98  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000bd9f  mov     [rdi+38h], r13d
0x18000bda3  mov     qword ptr [rdi+3Ch], 1
0x18000bdab  lea     r8, [rsp+288h+var_250]
0x18000bdb0  mov     [rdi+10h], rsi
0x18000bdb4  xorps   xmm0, xmm0
0x18000bdb7  mov     [rdi+18h], rsi
0x18000bdbb  xor     r9d, r9d
0x18000bdbe  mov     [rdi+20h], rsi
0x18000bdc2  mov     edx, 414h
0x18000bdc7  mov     [rdi+28h], rsi
0x18000bdcb  mov     [rdi+30h], esi
0x18000bdce  mov     [rdi+44h], r13d
0x18000bdd2  mov     [rdi+4E8h], r13
0x18000bdd9  mov     [rdi+4E0h], r13
0x18000bde0  mov     [rdi+4D0h], r13
0x18000bde7  mov     [rdi+8], rbx
0x18000bdeb  mov     qword ptr [rdi+4C8h], 1
0x18000bdf6  mov     [rdi+4D8h], r13
0x18000bdfd  mov     [rdi+4F0h], r13
0x18000be04  mov     [rdi+4F8h], r13
0x18000be0b  mov     rcx, [rbx+8]
0x18000be0f  mov     [rsp+288h+var_250], rax
0x18000be14  mov     rax, [rbx+0B8h]
0x18000be1b  movdqu  [rsp+288h+var_248], xmm0
0x18000be21  mov     [rsp+288h+var_268], r13
0x18000be26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2b  test    eax, eax
0x18000be2d  jz      short loc_18000BE3A
0x18000be2f  cmp     dword ptr [rsp+288h+var_248+8], r13d
0x18000be34  jnz     loc_180027EA6
0x18000be3a  mov     eax, [rdi+10h]
0x18000be3d  cmp     eax, esi
0x18000be3f  jnz     short loc_18000BE61
0x18000be41  mov     rax, [rdi+8]
0x18000be45  mov     rcx, [rax+70h]
0x18000be49  test    rcx, rcx
0x18000be4c  jz      loc_180027EBC
0x18000be52  mov     rax, rsi
0x18000be55  inc     rax
0x18000be58  cmp     [rcx+rax], r13b
0x18000be5c  jnz     short loc_18000BE55
0x18000be5e  mov     [rdi+10h], eax
0x18000be61  mov     r8, [rdi+8]
0x18000be65  mov     rdx, rsi
0x18000be68  mov     rcx, [r8+80h]
0x18000be6f  nop
0x18000be70  inc     rdx
0x18000be73  cmp     [rcx+rdx], r13b
0x18000be77  jnz     short loc_18000BE70
0x18000be79  mov     ebx, [r8+88h]
0x18000be80  lea     rcx, stru_18007CB60; lpCriticalSection
0x18000be87  add     ebx, edx
0x18000be89  add     ebx, eax
0x18000be8b  call    cs:__imp_EnterCriticalSection
0x18000be91  test    byte ptr cs:dword_18007CB28, 1
0x18000be98  jz      loc_18000C129
0x18000be9e  mov     rax, cs:qword_18007CB88
0x18000bea5  add     rax, 18h
0x18000bea9  add     [rax], ebx
0x18000beab  lea     rcx, stru_18007CB60; lpCriticalSection
0x18000beb2  call    cs:__imp_LeaveCriticalSection
0x18000beb8  cmp     cs:?g_fFirstHit@@3HA, r13d; int g_fFirstHit
0x18000bebf  jnz     loc_18000C135
0x18000bec5  cmp     cs:?g_fFirstHitFailed@@3KA, r13d; ulong g_fFirstHitFailed
0x18000becc  jnz     loc_180027ED4
0x18000bed2  test    byte ptr cs:dword_18007CB28, 1
0x18000bed9  mov     [rsp+288h+arg_0], rbp
0x18000bee1  mov     ebp, r13d
0x18000bee4  mov     [rsp+288h+var_20], r14
0x18000beec  mov     r14d, r13d
0x18000beef  jz      loc_180027EE7
0x18000bef5  mov     rax, cs:qword_18007CB88
0x18000befc  add     rax, 4Ch ; 'L'
0x18000bf00  mov     ebx, 1
0x18000bf05  lock xadd [rax], ebx
0x18000bf09  cmp     byte ptr cs:dword_180079F78, bpl
0x18000bf10  jnz     loc_180027EF3
0x18000bf16  cmp     cs:?g_fShutDownInProgress@@3HA, ebp; int g_fShutDownInProgress
0x18000bf1c  jnz     loc_180027F29
0x18000bf22  lea     edx, [rbx+1]; unsigned int
0x18000bf25  mov     rcx, rdi; struct CIsapiReqInfo *
0x18000bf28  call    ?DoHangDetection@@YAXPEAVCIsapiReqInfo@@K@Z; DoHangDetection(CIsapiReqInfo *,ulong)
0x18000bf2d  cmp     cs:?g_nOOMErrors@@3JA, r13d; long g_nOOMErrors
0x18000bf34  jnz     loc_180027F33
0x18000bf3a  mov     [rsp+288h+var_28], r15
0x18000bf42  test    ebp, ebp
0x18000bf44  js      loc_18002814B
0x18000bf4a  mov     eax, cs:dword_180079FA4
0x18000bf50  test    eax, eax
0x18000bf52  jz      short loc_18000BF60
0x18000bf54  cmp     cs:?g_nBrowserRequests@@3KA, eax; ulong g_nBrowserRequests
0x18000bf5a  jnb     loc_180028046
0x18000bf60  mov     rcx, cs:?sm_pach@CHitObj@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CHitObj::sm_pach
0x18000bf67  mov     [rsp+288h+var_258], r13d
0x18000bf6c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000bf72  mov     rbx, rax
0x18000bf75  test    rax, rax
0x18000bf78  jz      loc_18002814B
0x18000bf7e  lea     rax, ??_7CHitObj@@6B@; const CHitObj::`vftable'
0x18000bf85  mov     qword ptr [rbx+8], 100000h
0x18000bf8d  mov     [rbx], rax
0x18000bf90  mov     [rbx+10h], r13
0x18000bf94  mov     [rbx+18h], r13
0x18000bf98  mov     [rbx+20h], r13
0x18000bf9c  mov     [rbx+28h], r13
0x18000bfa0  mov     [rbx+30h], r13
0x18000bfa4  mov     [rbx+38h], r13
0x18000bfa8  mov     [rbx+40h], r13
0x18000bfac  mov     [rbx+48h], r13
0x18000bfb0  mov     [rbx+50h], r13
0x18000bfb4  mov     [rbx+58h], r13
0x18000bfb8  mov     [rbx+60h], r13
0x18000bfbc  mov     [rbx+68h], r13
0x18000bfc0  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x18000bfca  mov     [rbx+90h], r13
0x18000bfd1  mov     [rbx+98h], r13
0x18000bfd8  mov     [rbx+0A0h], r13
0x18000bfdf  mov     dword ptr [rbx+0A8h], 800h
0x18000bfe9  mov     [rbx+0B0h], r13
0x18000bff0  mov     [rbx+0B8h], r13
0x18000bff7  mov     [rbx+0C0h], r13d
0x18000bffe  mov     [rbx+0C8h], r13
0x18000c005  mov     [rbx+0D0h], r13
0x18000c00c  mov     [rbx+0D8h], r13
0x18000c013  mov     [rbx+0E0h], r13
0x18000c01a  mov     [rbx+0E8h], r13
0x18000c021  call    cs:__imp_GetACP
0x18000c027  lea     r8, [rsp+288h+var_258]; int *
0x18000c02c  mov     rdx, rdi; struct CIsapiReqInfo *
0x18000c02f  mov     rcx, rbx; this
0x18000c032  mov     [rbx+0A4h], eax
0x18000c038  call    ?BrowserRequestInit@CHitObj@@QEAAJPEAVCIsapiReqInfo@@PEAH@Z; CHitObj::BrowserRequestInit(CIsapiReqInfo *,int *)
0x18000c03d  mov     ebp, eax
0x18000c03f  mov     r14d, 0FACh
0x18000c045  test    eax, eax
0x18000c047  js      loc_1800280E3
0x18000c04d  test    dword ptr [rbx+8], 800h
0x18000c054  mov     [rsp+288h+arg_10], r12
0x18000c05c  mov     r12d, r13d
0x18000c05f  jnz     loc_18002807B
0x18000c065  test    r12d, r12d
0x18000c068  mov     r15d, r13d
0x18000c06b  mov     r12, [rsp+288h+arg_10]
0x18000c073  jnz     short loc_18000C0D1
0x18000c075  mov     rax, [rdi+8]
0x18000c079  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c080  mov     [rsp+288h+var_250], rcx
0x18000c085  lea     r8, [rsp+288h+var_250]
0x18000c08a  xorps   xmm0, xmm0
0x18000c08d  mov     [rsp+288h+var_268], r13
0x18000c092  xor     r9d, r9d
0x18000c095  mov     edx, 414h
0x18000c09a  mov     rcx, [rax+8]
0x18000c09e  mov     rax, [rax+0B8h]
0x18000c0a5  movdqu  [rsp+288h+var_248], xmm0
0x18000c0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0b0  test    eax, eax
0x18000c0b2  jz      short loc_18000C0BF
0x18000c0b4  cmp     dword ptr [rsp+288h+var_248+8], r13d
0x18000c0b9  jnz     loc_18002809A
0x18000c0bf  mov     rcx, rbx; this
0x18000c0c2  call    ?PostViperAsyncCall@CHitObj@@QEAAJXZ; CHitObj::PostViperAsyncCall(void)
0x18000c0c7  mov     ebp, eax
0x18000c0c9  test    eax, eax
0x18000c0cb  js      loc_1800280B4
0x18000c0d1  test    ebp, ebp
0x18000c0d3  js      loc_18002812E
0x18000c0d9  mov     r15, [rsp+288h+var_28]
0x18000c0e1  mov     rbp, [rsp+288h+arg_0]
0x18000c0e9  mov     r14, [rsp+288h+var_20]
0x18000c0f1  lock xadd [rdi], esi
0x18000c0f5  mov     r13, [rsp+288h+var_18]
0x18000c0fd  cmp     esi, 1
0x18000c100  mov     rsi, [rsp+288h+arg_8]
0x18000c108  jz      short loc_18000C175
0x18000c10a  mov     eax, 3
0x18000c10f  mov     rcx, [rsp+288h+var_38]
0x18000c117  xor     rcx, rsp; StackCookie
0x18000c11a  call    __security_check_cookie
0x18000c11f  add     rsp, 278h
0x18000c126  pop     rdi
0x18000c127  pop     rbx
0x18000c128  retn
0x18000c129  lea     rax, dword_18007CBAC
0x18000c130  jmp     loc_18000BEA9
0x18000c135  lea     rcx, ?g_csFirstHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c13c  call    cs:__imp_EnterCriticalSection
0x18000c142  cmp     cs:?g_fFirstHit@@3HA, r13d; int g_fFirstHit
0x18000c149  jnz     short loc_18000C15D
0x18000c14b  lea     rcx, ?g_csFirstHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c152  call    cs:__imp_LeaveCriticalSection
0x18000c158  jmp     loc_18000BEC5
0x18000c15d  mov     rcx, rdi; struct CIsapiReqInfo *
0x18000c160  call    ?FirstHitInit@@YAHPEAVCIsapiReqInfo@@@Z; FirstHitInit(CIsapiReqInfo *)
0x18000c165  mov     cs:?g_fFirstHit@@3HA, r13d; int g_fFirstHit
0x18000c16c  test    eax, eax
0x18000c16e  jnz     short loc_18000C14B
0x18000c170  jmp     loc_180027EC4
0x18000c175  mov     rcx, rdi; this
0x18000c178  call    ??1CIsapiReqInfo@@QEAA@XZ; CIsapiReqInfo::~CIsapiReqInfo(void)
0x18000c17d  mov     rcx, cs:?sm_pach@CIsapiReqInfo@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CIsapiReqInfo::sm_pach
0x18000c184  test    rcx, rcx
0x18000c187  jz      short loc_18000C10A
0x18000c189  mov     rdx, rdi
0x18000c18c  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000c192  jmp     loc_18000C10A
0x180027ea6  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180027eaa  mov     r8, [rcx+80h]; char *
0x180027eb1  call    ?RaiseEvent@ASP_START_REQUEST@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@PEBD@Z; AspReqEvents::ASP_START_REQUEST::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,char const *)
0x180027eb6  nop
0x180027eb7  jmp     loc_18000BE3A
0x180027ebc  mov     rax, r13
0x180027ebf  jmp     loc_18000BE5E
0x180027ec4  mov     ecx, 74h ; 't'; uID
0x180027ec9  call    ?MSG_Error@@YAXI@Z; MSG_Error(uint)
0x180027ece  nop
0x180027ecf  jmp     loc_18000C14B
0x180027ed4  mov     rdx, rdi; struct CIsapiReqInfo *
0x180027ed7  mov     ecx, 0FABh; unsigned int
0x180027edc  call    ?Handle500Error@@YAJIPEAVCIsapiReqInfo@@@Z; Handle500Error(uint,CIsapiReqInfo *)
0x180027ee1  nop
0x180027ee2  jmp     loc_18000C0F1
0x180027ee7  lea     rax, byte_18007CBE0
0x180027eee  jmp     loc_18000BF00
0x180027ef3  lea     rcx, stru_180079FC0; lpCriticalSection
0x180027efa  call    cs:__imp_EnterCriticalSection
0x180027f00  cmp     cs:dword_180079F78, ebp
0x180027f06  jz      short loc_180027F16
0x180027f08  xor     ecx, ecx; this
0x180027f0a  mov     cs:dword_180079F78, r13d
0x180027f11  call    ?ReadConfigFromSystem@@YAJPEAVCAppConfig@@H@Z; ReadConfigFromSystem(CAppConfig *,int)
0x180027f16  lea     rcx, stru_180079FC0; lpCriticalSection
0x180027f1d  call    cs:__imp_LeaveCriticalSection
0x180027f23  nop
0x180027f24  jmp     loc_18000BF16
0x180027f29  mov     ebp, 80004005h
0x180027f2e  jmp     loc_18000BF22
0x180027f33  cmp     cs:?g_fOOMRecycleDisabled@@3HA, r13d; int g_fOOMRecycleDisabled
0x180027f3a  jnz     loc_18000BF3A
0x180027f40  mov     eax, 1
0x180027f45  xchg    eax, cs:?g_fUnhealthyReported@@3JA; long g_fUnhealthyReported
0x180027f4b  test    eax, eax
0x180027f4d  jnz     loc_18000BF3A
0x180027f53  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180027f57  mov     edx, 2; unsigned int
0x180027f5c  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180027f61  test    eax, eax
0x180027f63  jz      short loc_180027F74
0x180027f65  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180027f69  mov     r8d, 20h ; ' '; unsigned int
0x180027f6f  call    ?RaiseEvent@ASP_UNHEALTHY_FAILURE@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@K@Z; AspReqEvents::ASP_UNHEALTHY_FAILURE::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ulong)
0x180027f74  test    byte ptr cs:g_dwDebugFlags, 3
0x180027f7b  jz      short loc_180027FAA
0x180027f7d  mov     rcx, cs:g_pDebug
0x180027f84  lea     rax, aDooomdetection_0; "DoOOMDetection: Reporting ill state to "...
0x180027f8b  lea     r9, aDooomdetection; "DoOOMDetection"
0x180027f92  mov     [rsp+288h+var_268], rax
0x180027f97  mov     r8d, 7E3h
0x180027f9d  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
  ... truncated ...
```

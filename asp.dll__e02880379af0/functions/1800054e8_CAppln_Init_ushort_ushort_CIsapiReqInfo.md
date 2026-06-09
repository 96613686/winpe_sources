# CAppln::Init(ushort *,ushort *,CIsapiReqInfo *)

- ea: `0x1800054e8`
- end: `0x180005d93`
- name: `?Init@CAppln@@QEAAJPEAG0PEAVCIsapiReqInfo@@@Z`
- size: `2219`
- prototype: `__int64 __fastcall(CAppln *__hidden this, unsigned __int16 *Src, unsigned __int16 *, struct CIsapiReqInfo *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006c80`

## callees

- `0x18000268c`
- `0x180002864`
- `0x1800033e8`
- `0x180003424`
- `0x1800054e8`
- `0x180005d9c`
- `0x180005df0`
- `0x1800060ec`
- `0x180006244`
- `0x180006310`
- `0x180006698`
- `0x1800066d0`
- `0x18000673c`
- `0x180006920`
- `0x180013090`
- `0x180013230`
- `0x1800132bc`
- `0x18001bb58`
- `0x180023d6e`
- `0x180023dd0`
- `0x1800311a0`
- `0x180033e78`
- `0x18003c470`
- `0x18003c960`
- `0x180040b18`
- `0x1800626ac`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000556e`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000556e`
- `KERNEL32!HeapAlloc` at `0x1800056d2`
- `KERNEL32!HeapAlloc` at `0x180005745`
- `KERNEL32!HeapAlloc` at `0x1800057fe`
- `KERNEL32!HeapAlloc` at `0x180005866`
- `KERNEL32!HeapAlloc` at `0x180005aa2`
- `KERNEL32!HeapAlloc` at `0x180005c96`
- `KERNEL32!HeapAlloc` at `0x1800056d2`
- `KERNEL32!HeapAlloc` at `0x180005745`
- `KERNEL32!HeapAlloc` at `0x1800057fe`
- `KERNEL32!HeapAlloc` at `0x180005866`
- `KERNEL32!HeapAlloc` at `0x180005aa2`
- `KERNEL32!HeapAlloc` at `0x180005c96`
- `KERNEL32!DeleteCriticalSection` at `0x180005643`
- `KERNEL32!DeleteCriticalSection` at `0x180005643`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetLastError` at `0x1800055f0`
- `KERNEL32!GetLastError` at `0x180005591`
- `KERNEL32!GetLastError` at `0x1800055f0`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800058d7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005947`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005993`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005be9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800058d7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005947`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005993`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180005be9`
- `iisutil!PuDbgPrint` at `0x180005685`
- `iisutil!PuDbgPrint` at `0x1800057bf`
- `iisutil!PuDbgPrint` at `0x180005d1f`
- `iisutil!PuDbgPrint` at `0x180005685`
- `iisutil!PuDbgPrint` at `0x1800057bf`
- `iisutil!PuDbgPrint` at `0x180005d1f`
- `iisutil!IISInitializeCriticalSection` at `0x180005587`
- `iisutil!IISInitializeCriticalSection` at `0x1800055e6`
- `iisutil!IISInitializeCriticalSection` at `0x180005587`
- `iisutil!IISInitializeCriticalSection` at `0x1800055e6`

## string_xrefs

- `0x180005798`: `New Application Failed to FindApplicationPath(), hr = %#08x\n`
- `0x1800058be`: `New Application Failed: Could not Init the AppConfig, hr = %#08x\n`
- `0x18000592e`: `New Application Failed: Could not Init the Component Collection, hr = %#08x\n`
- `0x1800059f7`: `New Application Failed: Could not Init ServicesConfig, hr = %#08x\n`
- `0x180005a83`: `New Application Failed: Could not CreateApplicationNode(), hr = %#08x\n`
- `0x180005c46`: `New Application Failed: Could not create global debug activity, hr = %#08x\n`

## pseudocode

```c
__int64 __fastcall CAppln::Init(
        CAppln *this,
        struct IDebugApplicationNode *Src,
        struct IDebugApplicationNode *a3,
        struct CIsapiReqInfo *a4)
{
  int FreeThreadedMarshaler; // esi
  signed int LastError; // eax
  signed int v8; // eax
  CFileNode *v9; // r14
  __int64 v10; // r12
  SIZE_T v11; // rax
  void *v12; // rax
  unsigned __int16 *ConfigPathFromMBPath; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r13
  SIZE_T v16; // rax
  void *v17; // rax
  int ApplicationPath; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int v21; // esi
  SIZE_T v22; // rax
  unsigned __int64 v23; // kr00_8
  unsigned __int16 *v24; // rax
  CAppConfig *v25; // rax
  CAppConfig *v26; // rax
  int v27; // eax
  CComponentCollection *v28; // rax
  CComponentCollection *v29; // rax
  int v30; // eax
  CApplnVariants *v31; // rax
  CApplnVariants *v32; // rsi
  CApplnVariants *v33; // rax
  CApplnVariants *v34; // rsi
  int inited; // eax
  int ServerDebugRoot; // eax
  _QWORD *v37; // r15
  int v38; // eax
  WCHAR *v39; // rax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  CTemplateCacheManager *v43; // rcx
  struct CViperActivity *v44; // rdx
  _QWORD *v45; // rax
  int v46; // eax
  int v47; // eax
  CSessionMgr *v48; // rax
  CSessionMgr *v49; // rax
  int v50; // eax
  void *v52; // [rsp+38h] [rbp-6B0h]
  struct IDebugApplicationNode *v55[4]; // [rsp+50h] [rbp-698h] BYREF
  HANDLE TokenHandle[2]; // [rsp+70h] [rbp-678h] BYREF
  char *v57; // [rsp+80h] [rbp-668h] BYREF
  char v58; // [rsp+88h] [rbp-660h] BYREF
  int v59; // [rsp+288h] [rbp-460h]
  unsigned __int16 v60[256]; // [rsp+290h] [rbp-458h] BYREF
  unsigned __int16 v61[264]; // [rsp+490h] [rbp-258h] BYREF

  v55[1] = (struct IDebugApplicationNode *)this;
  v55[2] = Src;
  v55[3] = a3;
  TokenHandle[0] = (HANDLE)-1LL;
  v57 = &v58;
  v59 = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_nApplications);
  v55[0] = 0;
  if ( !*((_QWORD *)this + 49) )
  {
    FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this, (LPUNKNOWN *)this + 49);
    if ( FreeThreadedMarshaler < 0 )
      goto LABEL_112;
  }
  FreeThreadedMarshaler = 0;
  if ( !(unsigned int)IISInitializeCriticalSection((char *)this + 200) )
  {
    LastError = GetLastError();
    FreeThreadedMarshaler = LastError;
    if ( LastError > 0 )
      FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
  }
  if ( FreeThreadedMarshaler < 0 )
    goto LABEL_12;
  FreeThreadedMarshaler = 0;
  if ( !(unsigned int)IISInitializeCriticalSection((char *)this + 240) )
  {
    v8 = GetLastError();
    FreeThreadedMarshaler = v8;
    if ( v8 > 0 )
      FreeThreadedMarshaler = (unsigned __int16)v8 | 0x80070000;
  }
  if ( FreeThreadedMarshaler < 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
LABEL_12:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
        892,
        "CAppln::Init",
        "New Application Failed to acquire Critical Section, hr = %08x\n",
        FreeThreadedMarshaler);
    goto LABEL_112;
  }
  v9 = 0;
  *((_DWORD *)this + 18) |= 0xC0u;
  AspDoRevertHack(TokenHandle);
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)&Src->lpVtbl + v10) );
  v11 = 4LL * (unsigned int)(v10 + 1);
  if ( !is_mul_ok(2LL * (unsigned int)(v10 + 1), 2u) )
    v11 = -1;
  v12 = HeapAlloc(g_hDenaliHeap, 0, v11);
  *((_QWORD *)this + 12) = v12;
  if ( !v12 )
    goto LABEL_103;
  memcpy_0(v12, Src, 2LL * (unsigned int)(v10 + 1));
  ConfigPathFromMBPath = CAppln::GetConfigPathFromMBPath(this, *((unsigned __int16 **)this + 12));
  *((_QWORD *)this + 13) = ConfigPathFromMBPath;
  if ( !ConfigPathFromMBPath )
    goto LABEL_103;
  v52 = (void *)*((_QWORD *)this + 12);
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)&a3->lpVtbl + v14) );
  v15 = 2LL * (unsigned int)(v14 + 1);
  v16 = 4LL * (unsigned int)(v14 + 1);
  if ( !is_mul_ok(v15, 2u) )
    v16 = -1;
  v17 = HeapAlloc(g_hDenaliHeap, 0, v16);
  *((_QWORD *)this + 14) = v17;
  if ( !v17 )
    goto LABEL_103;
  memcpy_0(v17, a3, v15);
  ApplicationPath = FindApplicationPath(a4, v61, 520);
  FreeThreadedMarshaler = ApplicationPath;
  if ( ApplicationPath < 0 )
  {
    if ( (g_dwDebugFlags & 7) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
        928,
        "CAppln::Init",
        "New Application Failed to FindApplicationPath(), hr = %#08x\n",
        ApplicationPath);
    goto LABEL_105;
  }
  v19 = -1;
  do
    ++v19;
  while ( v61[v19] );
  v20 = (unsigned int)(v19 + 1);
  v21 = v20;
  v23 = 2 * v20;
  v22 = 4 * v20;
  if ( !is_mul_ok(v23, 2u) )
    v22 = -1;
  v24 = (unsigned __int16 *)HeapAlloc(g_hDenaliHeap, 0, v22);
  *((_QWORD *)this + 15) = v24;
  if ( !v24 )
    goto LABEL_103;
  FreeThreadedMarshaler = StringCchCopyW(v24, v21, v61);
  if ( FreeThreadedMarshaler >= 0 )
  {
    CAppln::InitSessionCookieNames(this);
    if ( (int)CLinkElem::Init((CAppln *)((char *)this + 32), v52, 2 * (int)v10) >= 0 )
    {
      *((_QWORD *)this + 10) = 0;
      v25 = (CAppConfig *)HeapAlloc(g_hDenaliHeap, 0, 0xE8u);
      v26 = v25 ? CAppConfig::CAppConfig(v25) : 0LL;
      *((_QWORD *)this + 19) = v26;
      if ( *((_QWORD *)this + 19) )
      {
        v27 = CAppConfig::Init(*((CAppConfig **)this + 19), a4, this);
        FreeThreadedMarshaler = v27;
        if ( v27 < 0 )
        {
          if ( (g_dwDebugFlags & 7) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
              962,
              "CAppln::Init",
              "New Application Failed: Could not Init the AppConfig, hr = %#08x\n",
              v27);
          goto LABEL_105;
        }
        v28 = (CComponentCollection *)ALLOC_CACHE_HANDLER::Alloc(CComponentCollection::sm_pach);
        v29 = v28 ? CComponentCollection::CComponentCollection(v28) : 0LL;
        *((_QWORD *)this + 20) = v29;
        if ( v29 )
        {
          v30 = CComponentCollection::Init(v29, 1u, *(_DWORD *)(*((_QWORD *)this + 19) + 92LL));
          FreeThreadedMarshaler = v30;
          if ( v30 < 0 )
          {
            if ( (g_dwDebugFlags & 7) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                974,
                "CAppln::Init",
                "New Application Failed: Could not Init the Component Collection, hr = %#08x\n",
                v30);
            goto LABEL_105;
          }
          v31 = (CApplnVariants *)ALLOC_CACHE_HANDLER::Alloc(CApplnVariants::sm_pach);
          v32 = v31 ? CApplnVariants::CApplnVariants(v31) : 0LL;
          *((_QWORD *)this + 21) = v32;
          if ( v32 )
          {
            (*(void (__fastcall **)(CAppln *))(*(_QWORD *)this + 8LL))(this);
            *((_QWORD *)v32 + 5) = this;
            *((_DWORD *)v32 + 12) = 2;
            v33 = (CApplnVariants *)ALLOC_CACHE_HANDLER::Alloc(CApplnVariants::sm_pach);
            v34 = v33 ? CApplnVariants::CApplnVariants(v33) : 0LL;
            *((_QWORD *)this + 22) = v34;
            if ( v34 )
            {
              (*(void (__fastcall **)(CAppln *))(*(_QWORD *)this + 8LL))(this);
              *((_QWORD *)v34 + 5) = this;
              *((_DWORD *)v34 + 12) = 1;
              inited = CAppln::InitServicesConfig(this);
              FreeThreadedMarshaler = inited;
              if ( inited < 0 )
              {
                if ( (g_dwDebugFlags & 7) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                    1004,
                    "CAppln::Init",
                    "New Application Failed: Could not Init ServicesConfig, hr = %#08x\n",
                    inited);
                goto LABEL_105;
              }
              if ( !g_pPDM )
              {
LABEL_96:
                v48 = (CSessionMgr *)HeapAlloc(g_hDenaliHeap, 0, 0x78u);
                if ( v48 )
                  v49 = CSessionMgr::CSessionMgr(v48);
                else
                  v49 = 0;
                *((_QWORD *)this + 18) = v49;
                if ( v49 )
                {
                  v50 = CSessionMgr::Init(v49, this);
                  FreeThreadedMarshaler = v50;
                  if ( v50 < 0 && (g_dwDebugFlags & 7) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                      1119,
                      "CAppln::Init",
                      "New Application Failed: Could not Init session manager, hr = %#08x\n",
                      v50);
                  goto LABEL_105;
                }
                goto LABEL_103;
              }
              ServerDebugRoot = GetServerDebugRoot(a4, v55);
              FreeThreadedMarshaler = ServerDebugRoot;
              if ( ServerDebugRoot < 0 )
              {
                if ( (g_dwDebugFlags & 7) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                    1022,
                    "CAppln::Init",
                    "New Application Failed: Could not GetServerDebugRoot(), hr = %#08x\n",
                    ServerDebugRoot);
                goto LABEL_105;
              }
              v37 = (_QWORD *)((char *)this + 384);
              v38 = ((__int64 (__fastcall *)(struct IDebugApplication64 *, char *))g_pDebugApp->lpVtbl->CreateApplicationNode)(
                      g_pDebugApp,
                      (char *)this + 384);
              FreeThreadedMarshaler = v38;
              if ( v38 < 0 )
              {
                if ( (g_dwDebugFlags & 7) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                    1029,
                    "CAppln::Init",
                    "New Application Failed: Could not CreateApplicationNode(), hr = %#08x\n",
                    v38);
                goto LABEL_105;
              }
              v9 = (CFileNode *)HeapAlloc(g_hDenaliHeap, 0, 0x18u);
              if ( v9 )
              {
                *(_QWORD *)v9 = &CFileNode::`vftable';
                *((_QWORD *)v9 + 1) = 1;
                *((_QWORD *)v9 + 2) = 0;
              }
              else
              {
                v9 = 0;
              }
              if ( v9 )
              {
                v39 = strcpyExW(v60, *((const unsigned __int16 **)this + 15));
                if ( *(_DWORD *)(*((_QWORD *)this + 19) + 32LL) )
                {
                  *((_DWORD *)this + 18) |= 0x20u;
                }
                else
                {
                  CwchLoadStringOfId(0x19Du, v39, v61 - v39);
                  *((_DWORD *)this + 18) &= ~0x20u;
                }
                v40 = CFileNode::Init(v9, v60);
                FreeThreadedMarshaler = v40;
                if ( v40 < 0 )
                {
                  if ( (g_dwDebugFlags & 7) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                      1066,
                      "CAppln::Init",
                      "New Application Failed: Cannot Init CFileNode, hr = %#08x\n",
                      v40);
                  goto LABEL_105;
                }
                v41 = (*(__int64 (__fastcall **)(_QWORD, CFileNode *))(*(_QWORD *)*v37 + 64LL))(*v37, v9);
                FreeThreadedMarshaler = v41;
                if ( v41 < 0 )
                {
                  if ( (g_dwDebugFlags & 7) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                      1072,
                      "CAppln::Init",
                      "New Application Failed: SetDocumentProvider failed, hr = %#08x\n",
                      v41);
                  goto LABEL_105;
                }
                v42 = (*(__int64 (__fastcall **)(_QWORD, struct IDebugApplicationNode *))(*(_QWORD *)*v37 + 80LL))(
                        *v37,
                        v55[0]);
                FreeThreadedMarshaler = v42;
                if ( v42 < 0 )
                {
                  if ( (g_dwDebugFlags & 7) != 0 )
                    PuDbgPrint(
                      g_pDebug,
                      "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                      1079,
                      "CAppln::Init",
                      "New Application Failed: Could not Attach to debugger, hr = %#08x\n",
                      v42);
                  goto LABEL_105;
                }
                if ( (*((_BYTE *)this + 72) & 0x20) != 0 )
                {
                  CTemplateCacheManager::AddApplicationToDebuggerUI(v43, this);
                  if ( !g_pDebugActivity )
                  {
                    v45 = ALLOC_CACHE_HANDLER::Alloc(CViperActivity::sm_pach);
                    if ( v45 )
                    {
                      *v45 = &CViperActivity::`vftable';
                      v45[1] = 0;
                      *((_DWORD *)v45 + 4) = 0;
                    }
                    else
                    {
                      v45 = 0;
                    }
                    g_pDebugActivity = (CViperActivity *)v45;
                    if ( !v45 )
                    {
                      FreeThreadedMarshaler = -2147024882;
                      goto LABEL_105;
                    }
                    v46 = CViperActivity::Init((CViperActivity *)v45, *((struct IUnknown **)this + 24));
                    FreeThreadedMarshaler = v46;
                    if ( v46 < 0 )
                    {
                      if ( (g_dwDebugFlags & 7) != 0 )
                        PuDbgPrint(
                          g_pDebug,
                          "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                          1098,
                          "CAppln::Init",
                          "New Application Failed: Could not create global debug activity, hr = %#08x\n",
                          v46);
                      goto LABEL_105;
                    }
                  }
                  v47 = CAppln::BindToActivity(this, v44);
                  FreeThreadedMarshaler = v47;
                  if ( v47 < 0 )
                  {
                    if ( (g_dwDebugFlags & 7) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
                        1106,
                        "CAppln::Init",
                        "New Application Failed: Could not bind application to debugging activity, hr = %#08x\n",
                        v47);
                    goto LABEL_105;
                  }
                }
                goto LABEL_96;
              }
            }
          }
        }
      }
    }
LABEL_103:
    FreeThreadedMarshaler = -2147024882;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.cpp",
        1141,
        "CAppln::Init",
        "New Application Failed: E_OUTOFMEMORY\n");
  }
LABEL_105:
  if ( v9 )
    (*(void (__fastcall **)(CFileNode *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v55[0] )
    ((void (__fastcall *)(struct IDebugApplicationNode *))v55[0]->lpVtbl->Release)(v55[0]);
  if ( FreeThreadedMarshaler >= 0 )
    *((_DWORD *)this + 18) |= 1u;
  AspUndoRevertHack(TokenHandle);
LABEL_112:
  CMBCSToWChar::~CMBCSToWChar((CMBCSToWChar *)&v57);
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x1800054e8  push    rbx
0x1800054ea  push    rsi
0x1800054eb  push    rdi
0x1800054ec  push    r12
0x1800054ee  push    r13
0x1800054f0  push    r14
0x1800054f2  push    r15
0x1800054f4  sub     rsp, 6B0h
0x1800054fb  mov     rax, cs:__security_cookie
0x180005502  xor     rax, rsp
0x180005505  mov     [rsp+6E8h+var_48], rax
0x18000550d  mov     [rsp+6E8h+var_6A0], r9
0x180005512  mov     r14, r8
0x180005515  mov     [rsp+6E8h+Src], r8
0x18000551a  mov     r13, rdx
0x18000551d  mov     rdi, rcx
0x180005520  mov     [rsp+6E8h+var_690], rcx
0x180005525  mov     [rsp+6E8h+var_688], rdx
0x18000552a  mov     [rsp+6E8h+var_680], r8
0x18000552f  mov     [rsp+6E8h+var_6B0], r9
0x180005534  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005538  mov     [rsp+6E8h+TokenHandle], r15
0x18000553d  lea     rax, [rsp+6E8h+var_660]
0x180005545  mov     [rsp+6E8h+var_668], rax
0x18000554d  xor     ebx, ebx
0x18000554f  mov     [rsp+6E8h+var_460], ebx
0x180005556  lock inc cs:?g_nApplications@@3KA; ulong g_nApplications
0x18000555d  mov     [rsp+6E8h+var_698], rbx
0x180005562  lea     rdx, [rcx+188h]; ppunkMarshal
0x180005569  cmp     [rdx], rbx
0x18000556c  jnz     short loc_18000557E
0x18000556e  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180005574  mov     esi, eax
0x180005576  test    eax, eax
0x180005578  js      loc_180005D61
0x18000557e  mov     esi, ebx
0x180005580  lea     rcx, [rdi+0C8h]
0x180005587  call    cs:__imp_IISInitializeCriticalSection
0x18000558d  test    eax, eax
0x18000558f  jnz     short loc_1800055AA
0x180005591  call    cs:__imp_GetLastError
0x180005597  mov     esi, eax
0x180005599  test    eax, eax
0x18000559b  jle     short loc_1800055A6
0x18000559d  movzx   esi, ax
0x1800055a0  or      esi, 80070000h
0x1800055a6  mov     [rsp+6E8h+var_6B8], esi
0x1800055aa  jmp     short loc_1800055D9
0x1800055ac  mov     esi, 8000FFFFh
0x1800055b1  mov     [rsp+6E8h+var_6B8], esi
0x1800055b5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800055b9  xor     ebx, ebx
0x1800055bb  mov     rdi, [rsp+6E8h+var_690]
0x1800055c0  mov     r13, [rsp+6E8h+var_688]
0x1800055c5  mov     r14, [rsp+6E8h+var_680]
0x1800055ca  mov     [rsp+6E8h+Src], r14
0x1800055cf  mov     r14, [rsp+6E8h+var_6B0]
0x1800055d4  mov     [rsp+6E8h+var_6A0], r14
0x1800055d9  test    esi, esi
0x1800055db  js      short loc_18000564D
0x1800055dd  mov     esi, ebx
0x1800055df  lea     rcx, [rdi+0F0h]
0x1800055e6  call    cs:__imp_IISInitializeCriticalSection
0x1800055ec  test    eax, eax
0x1800055ee  jnz     short loc_180005609
0x1800055f0  call    cs:__imp_GetLastError
0x1800055f6  mov     esi, eax
0x1800055f8  test    eax, eax
0x1800055fa  jle     short loc_180005605
0x1800055fc  movzx   esi, ax
0x1800055ff  or      esi, 80070000h
0x180005605  mov     [rsp+6E8h+var_6B8], esi
0x180005609  jmp     short loc_180005638
0x18000560b  mov     esi, 8000FFFFh
0x180005610  mov     [rsp+6E8h+var_6B8], esi
0x180005614  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005618  xor     ebx, ebx
0x18000561a  mov     rdi, [rsp+6E8h+var_690]
0x18000561f  mov     r13, [rsp+6E8h+var_688]
0x180005624  mov     rax, [rsp+6E8h+var_680]
0x180005629  mov     [rsp+6E8h+Src], rax
0x18000562e  mov     rcx, [rsp+6E8h+var_6B0]
0x180005633  mov     [rsp+6E8h+var_6A0], rcx
0x180005638  test    esi, esi
0x18000563a  jns     short loc_180005690
0x18000563c  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180005643  call    cs:__imp_DeleteCriticalSection
0x180005649  test    esi, esi
0x18000564b  jns     short loc_180005690
0x18000564d  test    byte ptr cs:g_dwDebugFlags, 3
0x180005654  jz      loc_180005D61
0x18000565a  mov     [rsp+6E8h+var_6C0], esi
0x18000565e  lea     rax, aNewApplication_3; "New Application Failed to acquire Criti"...
0x180005665  mov     [rsp+6E8h+var_6C8], rax
0x18000566a  lea     r9, aCapplnInit; "CAppln::Init"
0x180005671  mov     r8d, 37Ch
0x180005677  lea     rdx, aInetsrvIisSvcs_7; "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.c"...
0x18000567e  mov     rcx, cs:g_pDebug
0x180005685  call    cs:__imp_PuDbgPrint
0x18000568b  jmp     loc_180005D61
0x180005690  mov     r14, rbx
0x180005693  or      dword ptr [rdi+48h], 0C0h
0x18000569a  lea     rcx, [rsp+6E8h+TokenHandle]; TokenHandle
0x18000569f  call    ?AspDoRevertHack@@YAXPEAPEAX@Z; AspDoRevertHack(void * *)
0x1800056a4  mov     r12, r15
0x1800056a7  inc     r12
0x1800056aa  cmp     [r13+r12*2+0], bx
0x1800056b0  jnz     short loc_1800056A7
0x1800056b2  lea     esi, [r12+1]
0x1800056b7  add     rsi, rsi
0x1800056ba  mov     eax, 2
0x1800056bf  mul     rsi
0x1800056c2  cmovb   rax, r15
0x1800056c6  mov     r8, rax; dwBytes
0x1800056c9  xor     edx, edx; dwFlags
0x1800056cb  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800056d2  call    cs:__imp_HeapAlloc
0x1800056d8  mov     [rdi+60h], rax
0x1800056dc  test    rax, rax
0x1800056df  jz      loc_180005CEA
0x1800056e5  mov     r8, rsi; Size
0x1800056e8  mov     rdx, r13; Src
0x1800056eb  mov     rcx, rax; void *
0x1800056ee  call    memcpy_0
0x1800056f3  mov     rdx, [rdi+60h]; unsigned __int16 *
0x1800056f7  mov     rcx, rdi; this
0x1800056fa  call    ?GetConfigPathFromMBPath@CAppln@@QEAAPEAGPEAG@Z; CAppln::GetConfigPathFromMBPath(ushort *)
0x1800056ff  mov     [rdi+68h], rax
0x180005703  test    rax, rax
0x180005706  jz      loc_180005CEA
0x18000570c  mov     rax, [rdi+60h]
0x180005710  mov     [rsp+6E8h+var_6B0], rax
0x180005715  mov     rax, r15
0x180005718  mov     rsi, [rsp+6E8h+Src]
0x18000571d  inc     rax
0x180005720  cmp     [rsi+rax*2], bx
0x180005724  jnz     short loc_18000571D
0x180005726  lea     r13d, [rax+1]
0x18000572a  add     r13, r13
0x18000572d  mov     eax, 2
0x180005732  mul     r13
0x180005735  cmovb   rax, r15
0x180005739  mov     r8, rax; dwBytes
0x18000573c  xor     edx, edx; dwFlags
0x18000573e  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180005745  call    cs:__imp_HeapAlloc
0x18000574b  mov     [rdi+70h], rax
0x18000574f  test    rax, rax
0x180005752  jz      loc_180005CEA
0x180005758  mov     r8, r13; Size
0x18000575b  mov     rdx, rsi; Src
0x18000575e  mov     rcx, rax; void *
0x180005761  call    memcpy_0
0x180005766  mov     r8d, 208h; int
0x18000576c  lea     rdx, [rsp+6E8h+var_258]; unsigned __int16 *
0x180005774  mov     r13, [rsp+6E8h+var_6A0]
0x180005779  mov     rcx, r13; struct CIsapiReqInfo *
0x18000577c  call    ?FindApplicationPath@@YAJPEAVCIsapiReqInfo@@PEAGH@Z; FindApplicationPath(CIsapiReqInfo *,ushort *,int)
0x180005781  mov     esi, eax
0x180005783  test    eax, eax
0x180005785  jns     short loc_1800057CA
0x180005787  test    byte ptr cs:g_dwDebugFlags, 7
0x18000578e  jz      loc_180005D25
0x180005794  mov     [rsp+6E8h+var_6C0], eax
0x180005798  lea     rax, aNewApplication_11; "New Application Failed to FindApplicati"...
0x18000579f  mov     r8d, 3A0h
0x1800057a5  lea     r9, aCapplnInit; "CAppln::Init"
0x1800057ac  mov     [rsp+6E8h+var_6C8], rax
0x1800057b1  lea     rdx, aInetsrvIisSvcs_7; "inetsrv\\iis\\svcs\\cmp\\asp\\applmgr.c"...
0x1800057b8  mov     rcx, cs:g_pDebug
0x1800057bf  call    cs:__imp_PuDbgPrint
0x1800057c5  jmp     loc_180005D25
0x1800057ca  lea     rcx, [rsp+6E8h+var_258]
0x1800057d2  mov     rax, r15
0x1800057d5  inc     rax
0x1800057d8  cmp     [rcx+rax*2], bx
0x1800057dc  jnz     short loc_1800057D5
0x1800057de  inc     eax
0x1800057e0  mov     esi, eax
0x1800057e2  lea     rcx, [rax+rax]
0x1800057e6  mov     eax, 2
0x1800057eb  mul     rcx
0x1800057ee  cmovb   rax, r15
0x1800057f2  mov     r8, rax; dwBytes
0x1800057f5  xor     edx, edx; dwFlags
0x1800057f7  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800057fe  call    cs:__imp_HeapAlloc
0x180005804  mov     [rdi+78h], rax
0x180005808  test    rax, rax
0x18000580b  jz      loc_180005CEA
0x180005811  lea     r8, [rsp+6E8h+var_258]; unsigned __int16 *
0x180005819  mov     edx, esi; unsigned __int64
0x18000581b  mov     rcx, rax; unsigned __int16 *
0x18000581e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005823  mov     esi, eax
0x180005825  test    eax, eax
0x180005827  js      loc_180005D25
0x18000582d  mov     rcx, rdi; this
0x180005830  call    ?InitSessionCookieNames@CAppln@@AEAAXXZ; CAppln::InitSessionCookieNames(void)
0x180005835  lea     r8d, [r12+r12]; int
0x180005839  lea     rcx, [rdi+20h]; this
0x18000583d  mov     rdx, [rsp+6E8h+var_6B0]; void *
0x180005842  call    ?Init@CLinkElem@@QEAAJPEAXH@Z; CLinkElem::Init(void *,int)
0x180005847  test    eax, eax
0x180005849  js      loc_180005CEA
0x18000584f  mov     qword ptr [rdi+50h], 0
0x180005857  xor     edx, edx; dwFlags
0x180005859  mov     r8d, 0E8h; dwBytes
0x18000585f  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180005866  call    cs:__imp_HeapAlloc
0x18000586c  test    rax, rax
0x18000586f  jz      short loc_18000587B
0x180005871  mov     rcx, rax; this
0x180005874  call    ??0CAppConfig@@QEAA@XZ; CAppConfig::CAppConfig(void)
0x180005879  jmp     short loc_18000587E
0x18000587b  mov     rax, rbx
0x18000587e  mov     [rdi+98h], rax
0x180005885  mov     rax, [rdi+98h]
0x18000588c  test    rax, rax
0x18000588f  jz      loc_180005CEA
0x180005895  mov     rcx, [rdi+98h]; this
0x18000589c  mov     r8, rdi; struct CAppln *
0x18000589f  mov     rdx, r13; struct CIsapiReqInfo *
0x1800058a2  call    ?Init@CAppConfig@@QEAAJPEAVCIsapiReqInfo@@PEAVCAppln@@@Z; CAppConfig::Init(CIsapiReqInfo *,CAppln *)
0x1800058a7  mov     esi, eax
0x1800058a9  test    eax, eax
0x1800058ab  jns     short loc_1800058D0
0x1800058ad  test    byte ptr cs:g_dwDebugFlags, 7
0x1800058b4  jz      loc_180005D25
0x1800058ba  mov     [rsp+6E8h+var_6C0], eax
0x1800058be  lea     rax, aNewApplication_5; "New Application Failed: Could not Init "...
0x1800058c5  mov     r8d, 3C2h
0x1800058cb  jmp     loc_1800057A5
0x1800058d0  mov     rcx, cs:?sm_pach@CComponentCollection@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CComponentCollection::sm_pach
0x1800058d7  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800058dd  test    rax, rax
0x1800058e0  jz      short loc_1800058EC
0x1800058e2  mov     rcx, rax; this
0x1800058e5  call    ??0CComponentCollection@@QEAA@XZ; CComponentCollection::CComponentCollection(void)
0x1800058ea  jmp     short loc_1800058EF
0x1800058ec  mov     rax, rbx
0x1800058ef  mov     [rdi+0A0h], rax
0x1800058f6  test    rax, rax
0x1800058f9  jz      loc_180005CEA
0x1800058ff  mov     r8, [rdi+98h]
0x180005906  mov     r8d, [r8+5Ch]; int
0x18000590a  mov     edx, 1; unsigned int
0x18000590f  mov     rcx, rax; this
0x180005912  call    ?Init@CComponentCollection@@QEAAJKH@Z; CComponentCollection::Init(ulong,int)
0x180005917  mov     esi, eax
0x180005919  test    eax, eax
0x18000591b  jns     short loc_180005940
0x18000591d  test    byte ptr cs:g_dwDebugFlags, 7
0x180005924  jz      loc_180005D25
0x18000592a  mov     [rsp+6E8h+var_6C0], eax
0x18000592e  lea     rax, aNewApplication_9; "New Application Failed: Could not Init "...
0x180005935  mov     r8d, 3CEh
0x18000593b  jmp     loc_1800057A5
0x180005940  mov     rcx, cs:?sm_pach@CApplnVariants@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CApplnVariants::sm_pach
0x180005947  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000594d  test    rax, rax
0x180005950  jz      short loc_18000595F
0x180005952  mov     rcx, rax; this
0x180005955  call    ??0CApplnVariants@@QEAA@XZ; CApplnVariants::CApplnVariants(void)
0x18000595a  mov     rsi, rax
0x18000595d  jmp     short loc_180005962
0x18000595f  mov     rsi, rbx
0x180005962  mov     [rdi+0A8h], rsi
0x180005969  test    rsi, rsi
0x18000596c  jz      loc_180005CEA
0x180005972  mov     rax, [rdi]
0x180005975  mov     rcx, rdi
0x180005978  mov     rax, [rax+8]
0x18000597c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005981  mov     [rsi+28h], rdi
0x180005985  mov     dword ptr [rsi+30h], 2
0x18000598c  mov     rcx, cs:?sm_pach@CApplnVariants@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CApplnVariants::sm_pach
0x180005993  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180005999  test    rax, rax
0x18000599c  jz      short loc_1800059AB
0x18000599e  mov     rcx, rax; this
0x1800059a1  call    ??0CApplnVariants@@QEAA@XZ; CApplnVariants::CApplnVariants(void)
0x1800059a6  mov     rsi, rax
0x1800059a9  jmp     short loc_1800059AE
0x1800059ab  mov     rsi, rbx
0x1800059ae  mov     [rdi+0B0h], rsi
0x1800059b5  test    rsi, rsi
0x1800059b8  jz      loc_180005CEA
0x1800059be  mov     rax, [rdi]
0x1800059c1  mov     rcx, rdi
0x1800059c4  mov     rax, [rax+8]
0x1800059c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059cd  mov     [rsi+28h], rdi
0x1800059d1  mov     dword ptr [rsi+30h], 1
0x1800059d8  mov     rcx, rdi; this
0x1800059db  call    ?InitServicesConfig@CAppln@@AEAAJXZ; CAppln::InitServicesConfig(void)
0x1800059e0  mov     esi, eax
0x1800059e2  test    eax, eax
0x1800059e4  jns     short loc_180005A09
0x1800059e6  test    byte ptr cs:g_dwDebugFlags, 7
  ... truncated ...
```

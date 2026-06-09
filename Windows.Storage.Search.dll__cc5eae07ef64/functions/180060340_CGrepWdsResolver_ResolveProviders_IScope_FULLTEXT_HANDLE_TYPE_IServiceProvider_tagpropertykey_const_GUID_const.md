# CGrepWdsResolver::ResolveProviders(IScope *,FULLTEXT_HANDLE_TYPE,IServiceProvider *,_tagpropertykey const &,_GUID const &,void * *)

- ea: `0x180060340`
- end: `0x180060615`
- name: `?ResolveProviders@CGrepWdsResolver@@UEAAJPEAUIScope@@W4FULLTEXT_HANDLE_TYPE@@PEAUIServiceProvider@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z`
- size: `725`
- prototype: `int __high(struct IScope *, enum FULLTEXT_HANDLE_TYPE, struct IServiceProvider *, const struct _tagpropertykey *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015588`
- `0x18001db40`
- `0x180021b70`
- `0x18003da00`
- `0x18005b3e0`
- `0x18005ec20`
- `0x18006028c`
- `0x1800602e4`
- `0x180060340`
- `0x1800616c0`
- `0x180070088`
- `0x18009a718`
- `0x18009b0d0`
- `0x18009c00c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180060514`
- `SHCORE!IUnknown_QueryService` at `0x180060514`
- `Windows.Storage!SHGetIDListFromObject` at `0x18006052e`
- `Windows.Storage!SHGetIDListFromObject` at `0x18006052e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605bb`
- `ext-ms-win-search-folder-l1-1-0!GetAggregateQueryError` at `0x18006057b`
- `ext-ms-win-search-folder-l1-1-0!GetAggregateQueryError` at `0x18006057b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGrepWdsResolver::ResolveProviders(
        __int64 a1,
        struct IScope *a2,
        int a3,
        struct IUnknown *a4,
        __int64 a5,
        struct _GUID *a6,
        void **a7)
{
  void **v10; // r12
  char *v11; // r14
  int RootItemInfo; // esi
  int v13; // ebx
  __int64 v14; // r9
  int v15; // eax
  unsigned int v16; // edx
  const struct _EVENT_DESCRIPTOR *v17; // rcx
  BOOL v18; // ebx
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-40h]
  __int64 *v22; // [rsp+20h] [rbp-40h]
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-10h] BYREF
  LPITEMIDLIST v26; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 v28; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+B0h] [rbp+50h]

  v29 = a3;
  v10 = a7;
  *a7 = 0;
  v11 = (char *)(a1 + 56);
  RootItemInfo = CGrepWdsResolver::_GetRootItemInfo((CGrepWdsResolver *)a1, a2, (enum SCOPE_ITEM_FLAGS *)(a1 + 56));
  if ( RootItemInfo < 0 )
    return (unsigned int)RootItemInfo;
  v13 = 0;
  LODWORD(a7) = 0;
  if ( (*v11 & 1) == 0 )
  {
    RootItemInfo = (*(__int64 (__fastcall **)(struct IScope *, __int64, GUID *, __int64))(*(_QWORD *)a2 + 64LL))(
                     a2,
                     4096,
                     &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                     a1 + 24);
    if ( RootItemInfo < 0 )
      return (unsigned int)RootItemInfo;
    RootItemInfo = CGrepWdsResolver::_TryResolveToWDS(
                     (CGrepWdsResolver *)a1,
                     (*(_DWORD *)v11 >> 6) & 2,
                     a2,
                     v14,
                     &a7,
                     a6,
                     v10);
    if ( RootItemInfo < 0 )
      return (unsigned int)RootItemInfo;
    v13 = (int)a7;
    if ( (_DWORD)a7 )
    {
      if ( *v11 >= 0 )
      {
        FileExplorerTelemetry::IndexerSearchRequested();
        v15 = FileExplorerSessionWatcher::RecordEventThroughSite(a4, 14);
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x477,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\grepwdsproviderresolver.cpp",
            (const char *)(unsigned int)v15,
            v21);
      }
    }
    else if ( (*(_DWORD *)v11 & 0x40) != 0 )
    {
      RootItemInfo = -2147023727;
      if ( (*(_DWORD *)v11 & 0x80u) == 0 )
        FileExplorerTelemetry::NoGrepRequested();
      return (unsigned int)RootItemInfo;
    }
  }
  if ( !v13 )
  {
    RootItemInfo = QueryContinueOnSite(a4);
    if ( RootItemInfo >= 0 )
    {
      RootItemInfo = CGrepWdsResolver::_TryResolveToGrep(
                       a1,
                       (IUnknown *)a2,
                       v29,
                       *(_DWORD *)v11,
                       v21,
                       &a7,
                       (__int64)a6,
                       v10);
      if ( RootItemInfo >= 0 )
      {
        if ( *(_DWORD *)(a1 + 44) )
        {
          if ( (*v11 & 1) == 0 && (*v11 & 0x10) == 0 && !*(_DWORD *)(a1 + 40) )
          {
            pv = 0;
            if ( (*(int (__fastcall **)(_QWORD, __int64, LPVOID *))(**(_QWORD **)(a1 + 32) + 40LL))(
                   *(_QWORD *)(a1 + 32),
                   2147647488LL,
                   &pv) >= 0 )
            {
              if ( !(unsigned int)PathIsRemovable((const unsigned __int16 *)pv) )
              {
                ppvOut = 0;
                if ( IUnknown_QueryService(a4, &IID_IInfoBarHost, &GUID_e38fe0f3_3db0_47ee_a314_25cf7f4bf521, &ppvOut) >= 0 )
                {
                  ppidl = 0;
                  if ( SHGetIDListFromObject(*(IUnknown **)(a1 + 32), &ppidl) >= 0
                    && (*(_DWORD *)(a1 + 48) || !*(_DWORD *)(a1 + 52)) )
                  {
                    v18 = *(_DWORD *)(a1 + 52) == 0;
                    SHTraceSQMCount(v17, v16);
                    v26 = ppidl;
                    v28 = 0;
                    v22 = &v28;
                    if ( (int)GetAggregateQueryError(v18, &v26, 1, &GUID_b38db1eb_acc8_4259_a7de_3d17290c43a1) >= 0 )
                      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppvOut + 24LL))(ppvOut, v28);
                    ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v28);
                  }
                  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
                }
                ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&ppvOut);
              }
              CoTaskMemFree(pv);
            }
          }
        }
        if ( (_DWORD)a7 )
        {
          if ( *v11 >= 0 )
          {
            FileExplorerTelemetry::GrepSearchRequested();
            v19 = FileExplorerSessionWatcher::RecordEventThroughSite(a4, 13);
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x4B3,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\grepwdsproviderresolver.cpp",
                (const char *)(unsigned int)v19,
                (int)v22);
          }
        }
      }
    }
  }
  return (unsigned int)RootItemInfo;
}

```

## disassembly

```asm
0x180060340  mov     [rsp-38h+arg_8], rbx
0x180060345  mov     [rsp-38h+arg_10], r8d
0x18006034a  push    rbp
0x18006034b  push    rsi
0x18006034c  push    rdi
0x18006034d  push    r12
0x18006034f  push    r13
0x180060351  push    r14
0x180060353  push    r15
0x180060355  mov     rbp, rsp
0x180060358  sub     rsp, 60h
0x18006035c  mov     r13, r9
0x18006035f  mov     r15, rdx
0x180060362  mov     rdi, rcx
0x180060365  mov     r12, [rbp+arg_30]
0x180060369  mov     qword ptr [r12], 0
0x180060371  lea     r14, [rcx+38h]
0x180060375  mov     r8, r14; enum SCOPE_ITEM_FLAGS *
0x180060378  call    ?_GetRootItemInfo@CGrepWdsResolver@@AEAAJPEAUIScope@@PEAW4SCOPE_ITEM_FLAGS@@@Z; CGrepWdsResolver::_GetRootItemInfo(IScope *,SCOPE_ITEM_FLAGS *)
0x18006037d  mov     esi, eax
0x18006037f  test    eax, eax
0x180060381  js      loc_1800605FB
0x180060387  xor     ebx, ebx
0x180060389  mov     dword ptr [rbp+arg_30], ebx
0x18006038c  test    byte ptr [r14], 1
0x180060390  jnz     loc_18006044D
0x180060396  mov     rax, [r15]
0x180060399  lea     r9, [rdi+18h]
0x18006039d  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800603a4  mov     edx, 1000h
0x1800603a9  mov     rcx, r15
0x1800603ac  mov     rax, [rax+40h]
0x1800603b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800603b5  mov     esi, eax
0x1800603b7  test    eax, eax
0x1800603b9  js      loc_1800605FB
0x1800603bf  mov     edx, [r14]
0x1800603c2  shr     edx, 6
0x1800603c5  and     edx, 2
0x1800603c8  mov     [rsp+60h+var_30], r12
0x1800603cd  mov     rax, [rbp+arg_28]
0x1800603d1  mov     [rsp+60h+var_38], rax
0x1800603d6  lea     rax, [rbp+arg_30]
0x1800603da  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800603df  mov     r8, r15
0x1800603e2  mov     rcx, rdi
0x1800603e5  call    ?_TryResolveToWDS@CGrepWdsResolver@@AEAAJW4REUSEWHERE_MODE@@PEAUIScope@@PEAUIServiceProvider@@PEAHAEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_TryResolveToWDS(REUSEWHERE_MODE,IScope *,IServiceProvider *,int *,_GUID const &,void * *)
0x1800603ea  mov     esi, eax
0x1800603ec  test    eax, eax
0x1800603ee  js      loc_1800605FB
0x1800603f4  mov     ebx, dword ptr [rbp+arg_30]
0x1800603f7  test    ebx, ebx
0x1800603f9  jnz     short loc_180060419
0x1800603fb  mov     eax, [r14]
0x1800603fe  test    al, 40h
0x180060400  jz      short loc_18006044D
0x180060402  mov     esi, 80070491h
0x180060407  test    al, al
0x180060409  js      loc_1800605FB
0x18006040f  call    ?NoGrepRequested@FileExplorerTelemetry@@SAXXZ; FileExplorerTelemetry::NoGrepRequested(void)
0x180060414  jmp     loc_1800605FB
0x180060419  test    byte ptr [r14], 80h
0x18006041d  jnz     short loc_18006044D
0x18006041f  call    ?IndexerSearchRequested@FileExplorerTelemetry@@SAXXZ; FileExplorerTelemetry::IndexerSearchRequested(void)
0x180060424  mov     edx, 0Eh
0x180060429  mov     rcx, r13
0x18006042c  call    ?RecordEventThroughSite@FileExplorerSessionWatcher@@YAJPEAUIUnknown@@W4SESSION_EVENT_TYPE@1@PEAUSESSION_EVENT_METADATA@@@Z; FileExplorerSessionWatcher::RecordEventThroughSite(IUnknown *,FileExplorerSessionWatcher::SESSION_EVENT_TYPE,SESSION_EVENT_METADATA *)
0x180060431  mov     rcx, [rbp+38h]; this
0x180060435  test    eax, eax
0x180060437  jns     short loc_18006044D
0x180060439  mov     r9d, eax; char *
0x18006043c  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage.sear"...
0x180060443  mov     edx, 477h; void *
0x180060448  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006044d  test    ebx, ebx
0x18006044f  jnz     loc_1800605FB
0x180060455  mov     rcx, r13; struct IUnknown *
0x180060458  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18006045d  mov     esi, eax
0x18006045f  test    eax, eax
0x180060461  js      loc_1800605FB
0x180060467  mov     [rsp+60h+var_28], r12
0x18006046c  mov     rax, [rbp+arg_28]
0x180060470  mov     [rsp+60h+var_30], rax
0x180060475  lea     rax, [rbp+arg_30]
0x180060479  mov     [rsp+60h+var_38], rax
0x18006047e  mov     r9d, [r14]
0x180060481  mov     r8d, [rbp+arg_10]
0x180060485  mov     rdx, r15
0x180060488  mov     rcx, rdi
0x18006048b  call    ?_TryResolveToGrep@CGrepWdsResolver@@AEAAJPEAUIScope@@W4FULLTEXT_HANDLE_TYPE@@W4SCOPE_ITEM_FLAGS@@PEAUIServiceProvider@@PEAHAEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_TryResolveToGrep(IScope *,FULLTEXT_HANDLE_TYPE,SCOPE_ITEM_FLAGS,IServiceProvider *,int *,_GUID const &,void * *)
0x180060490  mov     esi, eax
0x180060492  xor     r15d, r15d
0x180060495  test    eax, eax
0x180060497  js      loc_1800605FB
0x18006049d  cmp     [rdi+2Ch], r15d
0x1800604a1  jz      loc_1800605C1
0x1800604a7  test    byte ptr [r14], 1
0x1800604ab  jnz     loc_1800605C1
0x1800604b1  test    byte ptr [r14], 10h
0x1800604b5  jnz     loc_1800605C1
0x1800604bb  cmp     [rdi+28h], r15d
0x1800604bf  jnz     loc_1800605C1
0x1800604c5  mov     [rbp+pv], r15
0x1800604c9  mov     rcx, [rdi+20h]
0x1800604cd  mov     rax, [rcx]
0x1800604d0  lea     r8, [rbp+pv]
0x1800604d4  mov     edx, 80028000h
0x1800604d9  mov     rax, [rax+28h]
0x1800604dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604e2  test    eax, eax
0x1800604e4  js      loc_1800605C1
0x1800604ea  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800604ee  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1800604f3  test    eax, eax
0x1800604f5  jnz     loc_1800605B7
0x1800604fb  mov     [rbp+ppvOut], r15
0x1800604ff  lea     r9, [rbp+ppvOut]; ppvOut
0x180060503  lea     r8, _GUID_e38fe0f3_3db0_47ee_a314_25cf7f4bf521; riid
0x18006050a  lea     rdx, IID_IInfoBarHost; guidService
0x180060511  mov     rcx, r13; punk
0x180060514  call    cs:__imp_IUnknown_QueryService
0x18006051a  test    eax, eax
0x18006051c  js      loc_1800605AE
0x180060522  mov     [rbp+ppidl], r15
0x180060526  lea     rdx, [rbp+ppidl]; ppidl
0x18006052a  mov     rcx, [rdi+20h]; punk
0x18006052e  call    cs:__imp_SHGetIDListFromObject
0x180060534  test    eax, eax
0x180060536  js      short loc_1800605A4
0x180060538  cmp     [rdi+30h], r15d
0x18006053c  jnz     short loc_180060544
0x18006053e  cmp     [rdi+34h], r15d
0x180060542  jnz     short loc_1800605A4
0x180060544  mov     ebx, r15d
0x180060547  cmp     [rdi+34h], r15d
0x18006054b  setz    bl
0x18006054e  call    ?SHTraceSQMCount@@YAXPEBU_EVENT_DESCRIPTOR@@K@Z; SHTraceSQMCount(_EVENT_DESCRIPTOR const *,ulong)
0x180060553  mov     rax, [rbp+ppidl]
0x180060557  mov     [rbp+var_8], rax
0x18006055b  mov     [rbp+arg_0], r15
0x18006055f  lea     rax, [rbp+arg_0]
0x180060563  mov     qword ptr [rsp+60h+var_40], rax; int
0x180060568  lea     r9, _GUID_b38db1eb_acc8_4259_a7de_3d17290c43a1
0x18006056f  mov     r8d, 1
0x180060575  lea     rdx, [rbp+var_8]
0x180060579  mov     ecx, ebx
0x18006057b  call    cs:__imp_GetAggregateQueryError
0x180060581  test    eax, eax
0x180060583  js      short loc_18006059A
0x180060585  mov     rcx, [rbp+ppvOut]
0x180060589  mov     rax, [rcx]
0x18006058c  mov     rdx, [rbp+arg_0]
0x180060590  mov     rax, [rax+18h]
0x180060594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060599  nop
0x18006059a  lea     rcx, [rbp+arg_0]
0x18006059e  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800605a3  nop
0x1800605a4  lea     rcx, [rbp+ppidl]
0x1800605a8  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800605ad  nop
0x1800605ae  lea     rcx, [rbp+ppvOut]
0x1800605b2  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800605b7  mov     rcx, [rbp+pv]; pv
0x1800605bb  call    cs:__imp_CoTaskMemFree
0x1800605c1  cmp     dword ptr [rbp+arg_30], r15d
0x1800605c5  jz      short loc_1800605FB
0x1800605c7  test    byte ptr [r14], 80h
0x1800605cb  jnz     short loc_1800605FB
0x1800605cd  call    ?GrepSearchRequested@FileExplorerTelemetry@@SAXXZ; FileExplorerTelemetry::GrepSearchRequested(void)
0x1800605d2  mov     edx, 0Dh
0x1800605d7  mov     rcx, r13
0x1800605da  call    ?RecordEventThroughSite@FileExplorerSessionWatcher@@YAJPEAUIUnknown@@W4SESSION_EVENT_TYPE@1@PEAUSESSION_EVENT_METADATA@@@Z; FileExplorerSessionWatcher::RecordEventThroughSite(IUnknown *,FileExplorerSessionWatcher::SESSION_EVENT_TYPE,SESSION_EVENT_METADATA *)
0x1800605df  test    eax, eax
0x1800605e1  jns     short loc_1800605FB
0x1800605e3  mov     rcx, [rbp+38h]; this
0x1800605e7  mov     r9d, eax; char *
0x1800605ea  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage.sear"...
0x1800605f1  mov     edx, 4B3h; void *
0x1800605f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800605fb  mov     eax, esi
0x1800605fd  mov     rbx, [rsp+60h+arg_8]
0x180060605  add     rsp, 60h
0x180060609  pop     r15
0x18006060b  pop     r14
0x18006060d  pop     r13
0x18006060f  pop     r12
0x180060611  pop     rdi
0x180060612  pop     rsi
0x180060613  pop     rbp
0x180060614  retn
```

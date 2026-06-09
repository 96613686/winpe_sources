# CMapi2Handler::CreateAccessorEx(wchar_t const *,_AUTHENTICATION_INFO *,_INCREMENTAL_ACCESS_INFO *,_ITEM_INFO *,tagBLOB const *,IUrlAccessor * *)

- ea: `0x18000f370`
- end: `0x18000f782`
- name: `?CreateAccessorEx@CMapi2Handler@@UEAAJPEB_WPEAU_AUTHENTICATION_INFO@@PEAU_INCREMENTAL_ACCESS_INFO@@PEAU_ITEM_INFO@@PEBUtagBLOB@@PEAPEAUIUrlAccessor@@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(CMapi2Handler *this, const wchar_t *, struct _AUTHENTICATION_INFO *, struct _INCREMENTAL_ACCESS_INFO *, struct _ITEM_INFO *, const struct tagBLOB *, struct IUrlAccessor **)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004c20`
- `0x18000e8ac`
- `0x18000ea5c`
- `0x18000ebac`
- `0x18000ec50`
- `0x18000ec8c`
- `0x18000f370`
- `0x18000f788`
- `0x18000faac`
- `0x18000fd58`
- `0x1800113ac`
- `0x1800113ec`
- `0x18001148c`
- `0x180011530`
- `0x180011884`
- `0x1800119a0`
- `0x18001241c`
- `0x180012554`
- `0x18001269c`
- `0x180016044`
- `0x180029a60`
- `0x180029a98`
- `0x18002e57c`
- `0x18002f4b0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f3c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f3c0`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000f46d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000f5ad`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000f46d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000f5ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f654`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f53c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f53c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5fa`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000f54a`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000f54a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f624`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f624`

## string_xrefs

- `0x18000f4d6`: `Failed to check requirements!Old Outlook version (<10) running or Outlook is not correctly installed.`

## pseudocode

```c
__int64 __fastcall CMapi2Handler::CreateAccessorEx(
        CMapi2Handler *this,
        const wchar_t *a2,
        struct _AUTHENTICATION_INFO *a3,
        struct _INCREMENTAL_ACCESS_INFO *a4,
        struct _ITEM_INFO *a5,
        const struct tagBLOB *a6,
        struct IUrlAccessor **a7)
{
  struct _INCREMENTAL_ACCESS_INFO *v7; // r12
  _QWORD *v10; // rax
  int v11; // ebx
  CMapi2Handler *v12; // rcx
  struct CMapiManager *v13; // rcx
  int v15; // eax
  int MapiManager; // esi
  int v17; // r15d
  HANDLE CurrentProcess; // rax
  char *v19; // rdi
  CMapi2Accessor *v20; // rbx
  HANDLE *v21; // r12
  HANDLE v22; // rdi
  HANDLE v23; // rax
  CMapi2Accessor *v24; // rbx
  struct CSingleLink *v25; // rax
  struct CSingleLink *v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  CMapi2Accessor *v29; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v30[3]; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v31[96]; // [rsp+60h] [rbp-88h] BYREF

  v7 = a4;
  CMapiUrl::CMapiUrl((CMapiUrl *)v31, a2);
  v10 = (_QWORD *)CMapiUrl::Store(v31, v30);
  v11 = _o__wcsicmp(*v10, L"MAPIPH-Shutdown-Notify");
  ATL::CStringData::Release((ATL::CStringData *)(v30[0] - 24LL));
  if ( v11 )
  {
    v15 = CMapi2Handler::ValidateMapiUrl(v12, a2);
    MapiManager = v15;
    if ( v15 < 0 )
    {
      CLogger::Error(v15, L"Invalid MAPI URL!");
      CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
      return (unsigned int)MapiManager;
    }
    if ( *((__int64 *)this + 24) < 0xC000000000000LL )
    {
      v29 = (CMapi2Accessor *)OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
      if ( !(unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v29) )
      {
        CLogger::Info(-2147216890, L"Outlook is not running. Not indexing message or attachment.");
        OutlookSync::~OutlookSync((OutlookSync *)&v29);
        CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
        return 2147750406LL;
      }
      OutlookSync::~OutlookSync((OutlookSync *)&v29);
    }
    v17 = 1;
    *((_DWORD *)this + 44) = 1;
    if ( !*((_DWORD *)this + 46) )
    {
      CLogger::Warning(
        -2147218169,
        L"Failed to check requirements!Old Outlook version (<10) running or Outlook is not correctly installed.");
      CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
      return 2147749127LL;
    }
    if ( *((_DWORD *)this + 45) )
    {
      CLogger::Info(-2147216895, L"Policy to prevent indexing email is set.");
      CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
      return 2147750401LL;
    }
    if ( (unsigned int)UseLowPriorityConfiguration() )
    {
      if ( !*((_DWORD *)this + 54) )
      {
        CurrentProcess = GetCurrentProcess();
        if ( SetPriorityClass(CurrentProcess, 0x200000u) )
          *((_DWORD *)this + 54) = 1;
      }
    }
    v19 = (char *)this + 208;
    if ( !*((_QWORD *)this + 26) )
    {
      MapiManager = CMapiManager::GetMapiManager((struct CMapiManager **)this + 26, 0xAu);
      if ( MapiManager < 0 )
        goto LABEL_29;
      (*(void (__fastcall **)(CMapi2Handler *))(*(_QWORD *)this + 64LL))(this);
    }
    if ( !*(_QWORD *)(*(_QWORD *)v19 + 264LL) )
    {
      v20 = (CMapi2Accessor *)OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
      v29 = v20;
      if ( (unsigned int)OutlookSync::IsOutlookAlive((OutlookSync *)&v29) )
      {
        v21 = (HANDLE *)(*(_QWORD *)v19 + 264LL);
        if ( !*v21
          && !(unsigned __int8)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(
                                 *(_QWORD *)v19 + 280LL,
                                 0,
                                 v30) )
        {
          v22 = GetCurrentProcess();
          v23 = GetCurrentProcess();
          DuplicateHandle(v23, v20, v22, v21, 0, 0, 2u);
        }
        v7 = a4;
      }
      OutlookSync::~OutlookSync((OutlookSync *)&v29);
    }
LABEL_29:
    v24 = 0;
    v29 = 0;
    if ( MapiManager < 0 )
      goto LABEL_40;
    v30[0] = (char *)this + 112;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    v25 = CLnkList::RemoveFirst((CMapi2Handler *)((char *)this + 80));
    v26 = v25;
    if ( v25 )
    {
      v27 = *((_QWORD *)v25 + 1);
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
        v24 = (CMapi2Accessor *)*((_QWORD *)v26 + 1);
        v29 = v24;
        TNoUnkSList<CMapi2Accessor>::DestroyLink(v28, v26);
        v17 = 0;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v30);
    if ( v17 )
    {
      v30[0] = 0;
      MapiManager = ATL::CComObject<CMapi2Accessor>::CreateInstance(v30);
      if ( MapiManager < 0 )
      {
LABEL_38:
        if ( v24 )
        {
          (*(void (__fastcall **)(CMapi2Handler *, CMapi2Accessor *))(*(_QWORD *)this + 40LL))(this, v24);
          goto LABEL_41;
        }
LABEL_40:
        XForegroundTask::End((CMapi2Handler *)((char *)this + 216));
        goto LABEL_41;
      }
      TComPointer<IFilter>::operator=(&v29, v30[0]);
      v24 = v29;
    }
    MapiManager = CMapi2Accessor::Init(v24, this, a2, a6, &v7->ftLastModifiedTime, *((_DWORD *)this + 47));
    if ( MapiManager >= 0 )
    {
      (*(void (__fastcall **)(CMapi2Accessor *))(*(_QWORD *)v24 + 8LL))(v24);
      *a7 = (struct IUrlAccessor *)v24;
LABEL_41:
      TComPointer<CMapi2Accessor>::~TComPointer<CMapi2Accessor>(&v29);
      CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
      return (unsigned int)MapiManager;
    }
    goto LABEL_38;
  }
  CLogger::Info(L"Processing MAPIPH-Shutdown-Notify");
  if ( *((_QWORD *)this + 26) )
  {
    CMapiManager::ReleaseMapiManager(v13);
    *((_QWORD *)this + 26) = 0;
  }
  CLogger::Info(L"MAPI URL for the shutdown notification. Outlook is shutting down.");
  CMapiUrl::~CMapiUrl((CMapiUrl *)v31);
  return 2147750401LL;
}

```

## disassembly

```asm
0x18000f370  mov     rax, rsp
0x18000f373  mov     [rax+10h], rbx
0x18000f377  mov     [rax+18h], rsi
0x18000f37b  mov     [rax+20h], r9
0x18000f37f  mov     [rax+8], rcx
0x18000f383  push    rdi
0x18000f384  push    r12
0x18000f386  push    r13
0x18000f388  push    r14
0x18000f38a  push    r15
0x18000f38c  sub     rsp, 0C0h
0x18000f393  mov     r12, r9
0x18000f396  mov     r13, rdx
0x18000f399  mov     r14, rcx
0x18000f39c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f3a1  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x18000f3a6  nop
0x18000f3a7  lea     rdx, [rsp+0E8h+var_A0]
0x18000f3ac  lea     rcx, [rsp+0E8h+var_88]
0x18000f3b1  call    ?Store@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::Store(void)
0x18000f3b6  lea     rdx, aMapiphShutdown; "MAPIPH-Shutdown-Notify"
0x18000f3bd  mov     rcx, [rax]
0x18000f3c0  call    cs:__imp__o__wcsicmp
0x18000f3c6  mov     ebx, eax
0x18000f3c8  mov     rcx, [rsp+0E8h+var_A0]
0x18000f3cd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f3d1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f3d6  xor     edi, edi
0x18000f3d8  test    ebx, ebx
0x18000f3da  jnz     short loc_18000F41E
0x18000f3dc  lea     rcx, aProcessingMapi; "Processing MAPIPH-Shutdown-Notify"
0x18000f3e3  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18000f3e8  cmp     [r14+0D0h], rdi
0x18000f3ef  jz      short loc_18000F3FD
0x18000f3f1  call    ?ReleaseMapiManager@CMapiManager@@SAJPEAV1@@Z; CMapiManager::ReleaseMapiManager(CMapiManager *)
0x18000f3f6  mov     [r14+0D0h], rdi
0x18000f3fd  lea     rcx, aMapiUrlForTheS; "MAPI URL for the shutdown notification."...
0x18000f404  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18000f409  nop
0x18000f40a  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f40f  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f414  mov     eax, 80041201h
0x18000f419  jmp     loc_18000F764
0x18000f41e  mov     rdx, r13; wchar_t *
0x18000f421  call    ?ValidateMapiUrl@CMapi2Handler@@AEAAJPEB_W@Z; CMapi2Handler::ValidateMapiUrl(wchar_t const *)
0x18000f426  mov     esi, eax
0x18000f428  test    eax, eax
0x18000f42a  jns     short loc_18000F44C
0x18000f42c  lea     rdx, aInvalidMapiUrl; "Invalid MAPI URL!"
0x18000f433  mov     ecx, eax; int
0x18000f435  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18000f43a  nop
0x18000f43b  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f440  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f445  mov     eax, esi
0x18000f447  jmp     loc_18000F764
0x18000f44c  mov     rax, 0C000000000000h
0x18000f456  cmp     [r14+0C0h], rax
0x18000f45d  jge     short loc_18000F4C0
0x18000f45f  lea     r8, Name; "MSSPHTB_Alive"
0x18000f466  xor     edx, edx; bInheritHandle
0x18000f468  mov     ecx, 1F0001h; dwDesiredAccess
0x18000f46d  call    cs:__imp_OpenMutexW
0x18000f473  mov     [rsp+0E8h+var_A8], rax
0x18000f478  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000f47d  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x18000f482  test    eax, eax
0x18000f484  jnz     short loc_18000F4B6
0x18000f486  lea     rdx, aOutlookIsNotRu; "Outlook is not running. Not indexing me"...
0x18000f48d  mov     ebx, 80041206h
0x18000f492  mov     ecx, ebx; int
0x18000f494  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18000f499  nop
0x18000f49a  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000f49f  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x18000f4a4  nop
0x18000f4a5  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f4aa  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f4af  mov     eax, ebx
0x18000f4b1  jmp     loc_18000F764
0x18000f4b6  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000f4bb  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x18000f4c0  mov     r15d, 1
0x18000f4c6  mov     [r14+0B0h], r15d
0x18000f4cd  cmp     [r14+0B8h], edi
0x18000f4d4  jnz     short loc_18000F4FB
0x18000f4d6  lea     rdx, aFailedToCheckR; "Failed to check requirements!Old Outloo"...
0x18000f4dd  mov     ebx, 80040D07h
0x18000f4e2  mov     ecx, ebx; int
0x18000f4e4  call    ?Warning@CLogger@@SAXJPEB_WZZ; CLogger::Warning(long,wchar_t const *,...)
0x18000f4e9  nop
0x18000f4ea  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f4ef  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f4f4  mov     eax, ebx
0x18000f4f6  jmp     loc_18000F764
0x18000f4fb  cmp     [r14+0B4h], edi
0x18000f502  jz      short loc_18000F52A
0x18000f504  lea     rdx, aPolicyToPreven; "Policy to prevent indexing email is set"...
0x18000f50b  mov     ecx, 80041201h; int
0x18000f510  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18000f515  nop
0x18000f516  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f51b  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f520  mov     eax, 80041201h
0x18000f525  jmp     loc_18000F764
0x18000f52a  call    UseLowPriorityConfiguration
0x18000f52f  test    eax, eax
0x18000f531  jz      short loc_18000F55B
0x18000f533  cmp     [r14+0D8h], edi
0x18000f53a  jnz     short loc_18000F55B
0x18000f53c  call    cs:__imp_GetCurrentProcess
0x18000f542  mov     rcx, rax; hProcess
0x18000f545  mov     edx, 200000h; dwPriorityClass
0x18000f54a  call    cs:__imp_SetPriorityClass
0x18000f550  test    eax, eax
0x18000f552  jz      short loc_18000F55B
0x18000f554  mov     [r14+0D8h], r15d
0x18000f55b  lea     rdi, [r14+0D0h]
0x18000f562  cmp     qword ptr [rdi], 0
0x18000f566  jnz     short loc_18000F58E
0x18000f568  mov     edx, 0Ah; unsigned int
0x18000f56d  mov     rcx, rdi; struct CMapiManager **
0x18000f570  call    ?GetMapiManager@CMapiManager@@SAJPEAPEAV1@K@Z; CMapiManager::GetMapiManager(CMapiManager * *,ulong)
0x18000f575  mov     esi, eax
0x18000f577  test    eax, eax
0x18000f579  js      loc_18000F63C
0x18000f57f  mov     rax, [r14]
0x18000f582  mov     rcx, r14
0x18000f585  mov     rax, [rax+40h]
0x18000f589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f58e  mov     rax, [rdi]
0x18000f591  cmp     qword ptr [rax+108h], 0
0x18000f599  jnz     loc_18000F63C
0x18000f59f  lea     r8, Name; "MSSPHTB_Alive"
0x18000f5a6  xor     edx, edx; bInheritHandle
0x18000f5a8  mov     ecx, 1F0001h; dwDesiredAccess
0x18000f5ad  call    cs:__imp_OpenMutexW
0x18000f5b3  mov     rbx, rax
0x18000f5b6  mov     [rsp+0E8h+var_A8], rax
0x18000f5bb  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000f5c0  call    ?IsOutlookAlive@OutlookSync@@QEAAHXZ; OutlookSync::IsOutlookAlive(void)
0x18000f5c5  test    eax, eax
0x18000f5c7  jz      short loc_18000F632
0x18000f5c9  mov     rcx, [rdi]
0x18000f5cc  lea     r12, [rcx+108h]
0x18000f5d3  cmp     qword ptr [r12], 0
0x18000f5d8  jnz     short loc_18000F62A
0x18000f5da  add     rcx, 118h
0x18000f5e1  lea     r8, [rsp+0E8h+var_A0]
0x18000f5e6  xor     edx, edx
0x18000f5e8  call    ?Lookup@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBA_NKAEAPEAVCStoreWatcher@CMapiManager@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(ulong,CMapiManager::CStoreWatcher * &)
0x18000f5ed  test    al, al
0x18000f5ef  jnz     short loc_18000F62A
0x18000f5f1  call    cs:__imp_GetCurrentProcess
0x18000f5f7  mov     rdi, rax
0x18000f5fa  call    cs:__imp_GetCurrentProcess
0x18000f600  mov     [rsp+0E8h+dwOptions], 2; dwOptions
0x18000f608  mov     [rsp+0E8h+bInheritHandle], 0; bInheritHandle
0x18000f610  mov     [rsp+0E8h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f618  mov     r9, r12; lpTargetHandle
0x18000f61b  mov     r8, rdi; hTargetProcessHandle
0x18000f61e  mov     rdx, rbx; hSourceHandle
0x18000f621  mov     rcx, rax; hSourceProcessHandle
0x18000f624  call    cs:__imp_DuplicateHandle
0x18000f62a  mov     r12, [rsp+0E8h+arg_18]
0x18000f632  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000f637  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x18000f63c  xor     ebx, ebx
0x18000f63e  mov     [rsp+0E8h+var_A8], rbx
0x18000f643  test    esi, esi
0x18000f645  js      loc_18000F737
0x18000f64b  lea     rcx, [r14+70h]; lpCriticalSection
0x18000f64f  mov     [rsp+0E8h+var_A0], rcx
0x18000f654  call    cs:__imp_EnterCriticalSection
0x18000f65a  nop
0x18000f65b  lea     rcx, [r14+50h]; this
0x18000f65f  call    ?RemoveFirst@CLnkList@@QEAAPEAVCSingleLink@@XZ; CLnkList::RemoveFirst(void)
0x18000f664  mov     rdi, rax
0x18000f667  test    rax, rax
0x18000f66a  jz      short loc_18000F695
0x18000f66c  mov     rcx, [rax+8]
0x18000f670  test    rcx, rcx
0x18000f673  jz      short loc_18000F695
0x18000f675  mov     rax, [rcx]
0x18000f678  mov     rax, [rax+8]
0x18000f67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f681  mov     rbx, [rdi+8]
0x18000f685  mov     [rsp+0E8h+var_A8], rbx
0x18000f68a  mov     rdx, rdi
0x18000f68d  call    ?DestroyLink@?$TNoUnkSList@VCMapi2Accessor@@@@IEAAXPEAV?$TNoUnkSingleLink@VCMapi2Accessor@@@@@Z; TNoUnkSList<CMapi2Accessor>::DestroyLink(TNoUnkSingleLink<CMapi2Accessor> *)
0x18000f692  xor     r15d, r15d
0x18000f695  lea     rcx, [rsp+0E8h+var_A0]
0x18000f69a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000f69f  test    r15d, r15d
0x18000f6a2  jz      short loc_18000F6D1
0x18000f6a4  mov     [rsp+0E8h+var_A0], 0
0x18000f6ad  lea     rcx, [rsp+0E8h+var_A0]
0x18000f6b2  call    ?CreateInstance@?$CComObject@VCMapi2Accessor@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMapi2Accessor>::CreateInstance(ATL::CComObject<CMapi2Accessor> * *)
0x18000f6b7  mov     esi, eax
0x18000f6b9  test    eax, eax
0x18000f6bb  js      short loc_18000F71E
0x18000f6bd  mov     rdx, [rsp+0E8h+var_A0]
0x18000f6c2  lea     rcx, [rsp+0E8h+var_A8]
0x18000f6c7  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18000f6cc  mov     rbx, [rsp+0E8h+var_A8]
0x18000f6d1  lea     rcx, [r12+4]
0x18000f6d6  mov     eax, [r14+0BCh]
0x18000f6dd  mov     [rsp+0E8h+bInheritHandle], eax; unsigned int
0x18000f6e1  mov     qword ptr [rsp+0E8h+dwDesiredAccess], rcx; struct _FILETIME *
0x18000f6e6  mov     r9, [rsp+0E8h+arg_28]; struct tagBLOB *
0x18000f6ee  mov     r8, r13; wchar_t *
0x18000f6f1  mov     rdx, r14; struct CMapi2Handler *
0x18000f6f4  mov     rcx, rbx; this
0x18000f6f7  call    ?Init@CMapi2Accessor@@QEAAJPEAVCMapi2Handler@@PEB_WPEBUtagBLOB@@AEAU_FILETIME@@K@Z; CMapi2Accessor::Init(CMapi2Handler *,wchar_t const *,tagBLOB const *,_FILETIME &,ulong)
0x18000f6fc  mov     esi, eax
0x18000f6fe  test    eax, eax
0x18000f700  js      short loc_18000F71E
0x18000f702  mov     rax, [rbx]
0x18000f705  mov     rcx, rbx
0x18000f708  mov     rax, [rax+8]
0x18000f70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f711  mov     rax, [rsp+0E8h+arg_30]
0x18000f719  mov     [rax], rbx
0x18000f71c  jmp     short loc_18000F744
0x18000f71e  test    rbx, rbx
0x18000f721  jz      short loc_18000F737
0x18000f723  mov     rax, [r14]
0x18000f726  mov     rdx, rbx
0x18000f729  mov     rcx, r14
0x18000f72c  mov     rax, [rax+28h]
0x18000f730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f735  jmp     short loc_18000F744
0x18000f737  lea     rcx, [r14+0D8h]; this
0x18000f73e  call    ?End@XForegroundTask@@QEAAXXZ; XForegroundTask::End(void)
0x18000f743  nop
0x18000f744  lea     rcx, [rsp+0E8h+var_A8]
0x18000f749  call    ??1?$TComPointer@VCMapi2Accessor@@@@QEAA@XZ; TComPointer<CMapi2Accessor>::~TComPointer<CMapi2Accessor>(void)
0x18000f74e  nop
0x18000f74f  lea     rcx, [rsp+0E8h+var_88]; this
0x18000f754  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18000f759  nop
0x18000f75a  jmp     short loc_18000F762
0x18000f75c  jmp     short $+2
0x18000f75e  mov     esi, dword ptr [rsp+0E8h+var_A8]
0x18000f762  mov     eax, esi
0x18000f764  lea     r11, [rsp+0E8h+var_28]
0x18000f76c  mov     rbx, [r11+38h]
0x18000f770  mov     rsi, [r11+40h]
0x18000f774  mov     rsp, r11
0x18000f777  pop     r15
0x18000f779  pop     r14
0x18000f77b  pop     r13
0x18000f77d  pop     r12
0x18000f77f  pop     rdi
0x18000f780  retn
```

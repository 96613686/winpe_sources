# AddRemovedFoDsToPackagesToCleanup

- ea: `0x1801774fc`
- end: `0x180177971`
- name: `AddRemovedFoDsToPackagesToCleanup`
- size: `1141`
- prototype: `__int64 __fastcall(CCbsSession *this, CCbsStringArray *)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18017ae0c`
- `0x18017b3d4`

## callees

- `0x18000e780`
- `0x180010cc0`
- `0x180012fe4`
- `0x180013018`
- `0x1800132a4`
- `0x180023f30`
- `0x18002c34c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800c0054`
- `0x1800ea8b8`
- `0x1800eb920`
- `0x1801774fc`
- `0x180195edc`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017778e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801777a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801777c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801778d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801778f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017790b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017778e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801777a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801777c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801778d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801778f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017790b`

## string_xrefs

- `0x18017754b`: `Removed FOD Markers`
- `0x1801775c8`: `Maint: Deepclean: Failed to enumerate UninstallRequested capabilities`

## pseudocode

```c
__int64 __fastcall AddRemovedFoDsToPackagesToCleanup(CCbsSession *this, CCbsStringArray *a2)
{
  struct IEnumCbsCapability **InitPointer; // rax
  int v5; // eax
  int v6; // edi
  __int64 v8; // rdi
  unsigned int (__fastcall *v9)(__int64, __int64, __int64, int *); // rbx
  __int64 v10; // rax
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, __int64, __int64, __int64); // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rbx
  __int64 *v18; // r14
  __int64 v19; // rsi
  const wchar_t *v20; // rdx
  const wchar_t *v21; // rax
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-A9h]
  int *v24; // [rsp+20h] [rbp-A9h]
  int v25[2]; // [rsp+40h] [rbp-89h] BYREF
  LPVOID v26; // [rsp+48h] [rbp-81h] BYREF
  LPVOID v27; // [rsp+50h] [rbp-79h] BYREF
  LPVOID v28; // [rsp+58h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-69h] BYREF
  int v30; // [rsp+68h] [rbp-61h] BYREF
  __int64 v31; // [rsp+70h] [rbp-59h] BYREF
  __int64 v32; // [rsp+78h] [rbp-51h] BYREF
  int v33; // [rsp+80h] [rbp-49h] BYREF
  const wchar_t *v34; // [rsp+88h] [rbp-41h] BYREF
  int v35; // [rsp+90h] [rbp-39h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-29h] BYREF
  int v37; // [rsp+A8h] [rbp-21h]
  __int128 v38; // [rsp+B0h] [rbp-19h]
  __int64 v39; // [rsp+C0h] [rbp-9h]
  __int64 *v40; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v36 = 0;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  if ( (int)CCbsSession::GetStoreObject(this, L"Removed FOD Markers", 17, 0, &v36) < 0 )
  {
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v36);
    return 0;
  }
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v36);
  v32 = 0;
  InitPointer = (struct IEnumCbsCapability **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v32);
  v5 = CCbsSession::EnumerateCapabilities(this, 0x200u, 0, 0, 0, 0, 0, InitPointer);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v31 = 0;
    v33 = 0;
    while ( 1 )
    {
      v8 = v32;
      v9 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v32 + 24LL);
      v10 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v31);
      if ( v9(v8, 1, v10, &v33) || v33 != 1 )
        break;
      v11 = v31;
      v28 = 0;
      v27 = 0;
      pv = 0;
      v35 = 0;
      v30 = 0;
      v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v31 + 112LL);
      v13 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
      v14 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v27);
      v15 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v28);
      v24 = &v35;
      v6 = v12(v11, v15, v14, v13);
      if ( v6 < 0 )
      {
        LODWORD(v34) = v6;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get capability");
          *(_QWORD *)v25 = &v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v25);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x969,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsmaintenanceexecutionobject.cpp",
          (const char *)(unsigned int)v6,
          (int)v24);
LABEL_37:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v27 )
        {
          CoTaskMemFree(v27);
          v27 = 0;
        }
        if ( v28 )
        {
          CoTaskMemFree(v28);
          v28 = 0;
        }
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v31);
        goto LABEL_7;
      }
      CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(&v36);
      v6 = CCbsCapabilityManager::EnumerateStoreCapabilityPackagesWithoutSatellites(v16, this, v28, &v36);
      if ( v6 < 0 )
      {
        LODWORD(v34) = v6;
        if ( LogAdapter::g_Logger )
        {
          v26 = v28;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to enumerate stored packages for FOD: {}",
            (__int64)&v26);
          *(_QWORD *)v25 = &v34;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v25);
        }
        v22 = 2414;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsmaintenanceexecutionobject.cpp",
          (const char *)(unsigned int)v6,
          (int)v24);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(&v36);
        goto LABEL_37;
      }
      v17 = v40;
      v18 = &v40[*((_QWORD *)&v38 + 1)];
      while ( v17 != v18 )
      {
        v19 = *v17;
        v20 = &qword_1802EB518;
        if ( *(_QWORD *)(*v17 + 120) )
          v20 = *(const wchar_t **)(v19 + 120);
        v6 = CCbsStringArray::CopyAndAdd(a2, v20);
        if ( v6 < 0 )
        {
          v22 = 2418;
          goto LABEL_30;
        }
        v21 = &qword_1802EB518;
        if ( *(_QWORD *)(v19 + 120) )
          v21 = *(const wchar_t **)(v19 + 120);
        v34 = v21;
        LogAdapter::TraceAtLevel<wchar_t const *>(
          1,
          "Added capability package to list of packages to cleanup: {}",
          &v34);
        ++v17;
      }
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v31);
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(&v36);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v27 )
      {
        CoTaskMemFree(v27);
        v27 = 0;
      }
      if ( v28 )
        CoTaskMemFree(v28);
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  v30 = v5;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Maint: Deepclean: Failed to enumerate UninstallRequested capabilities");
    v27 = &v30;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v27);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x95B,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsmaintenanceexecutionobject.cpp",
    (const char *)(unsigned int)v6,
    v23);
LABEL_7:
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801774fc  mov     [rsp-8+arg_10], rbx
0x180177501  push    rbp
0x180177502  push    rsi
0x180177503  push    rdi
0x180177504  push    r12
0x180177506  push    r13
0x180177508  push    r14
0x18017750a  push    r15
0x18017750c  lea     rbp, [rsp-27h]
0x180177511  sub     rsp, 0F0h
0x180177518  mov     rax, cs:__security_cookie
0x18017751f  xor     rax, rsp
0x180177522  mov     [rbp+57h+var_40], rax
0x180177526  xor     r13d, r13d
0x180177529  lea     rax, [rbp+57h+var_80]
0x18017752d  mov     r12, rdx
0x180177530  mov     [rbp+57h+var_80], r13
0x180177534  xorps   xmm0, xmm0
0x180177537  mov     [rbp+57h+var_78], r13d
0x18017753b  xor     r9d, r9d
0x18017753e  mov     [rbp+57h+var_60], r13
0x180177542  lea     r8d, [r13+11h]
0x180177546  mov     [rsp+120h+var_100], rax
0x18017754b  lea     rdx, aRemovedFodMark; "Removed FOD Markers"
0x180177552  mov     r15, rcx
0x180177555  movdqu  [rbp+57h+var_70], xmm0
0x18017755a  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x18017755f  lea     rcx, [rbp+57h+var_80]; this
0x180177563  test    eax, eax
0x180177565  jns     short loc_180177571
0x180177567  call    ??1CCbsStoreObject@@QEAA@XZ; CCbsStoreObject::~CCbsStoreObject(void)
0x18017756c  jmp     loc_180177947
0x180177571  call    ??1CCbsStoreObject@@QEAA@XZ; CCbsStoreObject::~CCbsStoreObject(void)
0x180177576  lea     rcx, [rbp+57h+var_A8]
0x18017757a  mov     [rbp+57h+var_A8], r13
0x18017757e  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180177583  mov     [rsp+120h+var_E8], rax; struct IEnumCbsCapability **
0x180177588  xor     r9d, r9d; wchar_t *
0x18017758b  mov     [rsp+120h+var_F0], r13d; unsigned int
0x180177590  xor     r8d, r8d; wchar_t *
0x180177593  mov     [rsp+120h+var_F8], r13d; unsigned int
0x180177598  mov     edx, 200h; unsigned int
0x18017759d  mov     rcx, r15; this
0x1801775a0  mov     [rsp+120h+var_100], r13; wchar_t *
0x1801775a5  call    ?EnumerateCapabilities@CCbsSession@@QEAAJIPEB_W00KKPEAPEAUIEnumCbsCapability@@@Z; CCbsSession::EnumerateCapabilities(uint,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,IEnumCbsCapability * *)
0x1801775aa  mov     edi, eax
0x1801775ac  test    eax, eax
0x1801775ae  jns     loc_180177636
0x1801775b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801775bb  mov     [rbp+57h+var_B8], eax
0x1801775be  test    rcx, rcx
0x1801775c1  jz      short loc_180177602
0x1801775c3  mov     ebx, 3
0x1801775c8  lea     r9, aMaintDeepclean_1; "Maint: Deepclean: Failed to enumerate U"...
0x1801775cf  mov     r8d, ebx
0x1801775d2  xor     edx, edx
0x1801775d4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801775d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801775e0  lea     rax, [rbp+57h+var_B8]
0x1801775e4  mov     [rbp+57h+var_D0], rax
0x1801775e8  lea     r9, asc_1802EE7AC; ": {}"
0x1801775ef  lea     rax, [rbp+57h+var_D0]
0x1801775f3  mov     r8d, ebx
0x1801775f6  mov     dl, 1
0x1801775f8  mov     [rsp+120h+var_100], rax; int
0x1801775fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180177602  mov     rcx, [rbp+5Fh]; this
0x180177606  lea     r8, aOnecoreBaseCbs_58; "onecore\\base\\cbs\\core\\cbsmaintenanc"...
0x18017760d  mov     r9d, edi; char *
0x180177610  mov     edx, 95Bh; void *
0x180177615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017761a  mov     rcx, [rbp+57h+var_A8]
0x18017761e  test    rcx, rcx
0x180177621  jz      short loc_18017762F
0x180177623  mov     rax, [rcx]
0x180177626  mov     rax, [rax+10h]
0x18017762a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017762f  mov     eax, edi
0x180177631  jmp     loc_180177949
0x180177636  mov     [rbp+57h+var_B0], r13
0x18017763a  mov     [rbp+57h+var_A0], r13d
0x18017763e  mov     rdi, [rbp+57h+var_A8]
0x180177642  lea     rcx, [rbp+57h+var_B0]
0x180177646  mov     rax, [rdi]
0x180177649  mov     rbx, [rax+18h]
0x18017764d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180177652  mov     r8, rax
0x180177655  lea     r9, [rbp+57h+var_A0]
0x180177659  mov     rax, rbx
0x18017765c  mov     edx, 1
0x180177661  mov     rcx, rdi
0x180177664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177669  test    eax, eax
0x18017766b  jnz     loc_180177929
0x180177671  cmp     [rbp+57h+var_A0], 1
0x180177675  jnz     loc_180177929
0x18017767b  mov     r14, [rbp+57h+var_B0]
0x18017767f  lea     rcx, [rbp+57h+pv]
0x180177683  mov     [rbp+57h+var_C8], r13
0x180177687  mov     [rbp+57h+var_D0], r13
0x18017768b  mov     [rbp+57h+pv], r13
0x18017768f  mov     [rbp+57h+var_90], r13d
0x180177693  mov     [rbp+57h+var_B8], r13d
0x180177697  mov     rax, [r14]
0x18017769a  mov     rsi, [rax+70h]
0x18017769e  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801776a3  lea     rcx, [rbp+57h+var_D0]
0x1801776a7  mov     rdi, rax
0x1801776aa  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801776af  lea     rcx, [rbp+57h+var_C8]
0x1801776b3  mov     rbx, rax
0x1801776b6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801776bb  lea     rcx, [rbp+57h+var_B8]
0x1801776bf  mov     rdx, rax
0x1801776c2  mov     qword ptr [rsp+120h+var_F8], rcx
0x1801776c7  mov     r9, rdi
0x1801776ca  lea     rcx, [rbp+57h+var_90]
0x1801776ce  mov     r8, rbx
0x1801776d1  mov     [rsp+120h+var_100], rcx; int
0x1801776d6  mov     rax, rsi
0x1801776d9  mov     rcx, r14
0x1801776dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801776e1  mov     edi, eax
0x1801776e3  test    eax, eax
0x1801776e5  js      loc_180177868
0x1801776eb  lea     rcx, [rbp+57h+var_80]
0x1801776ef  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801776f4  mov     r8, [rbp+57h+var_C8]
0x1801776f8  lea     r9, [rbp+57h+var_80]
0x1801776fc  mov     rdx, r15
0x1801776ff  call    ?EnumerateStoreCapabilityPackagesWithoutSatellites@CCbsCapabilityManager@@QEBAJPEAVCCbsSession@@QEB_WPEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@Z; CCbsCapabilityManager::EnumerateStoreCapabilityPackagesWithoutSatellites(CCbsSession *,wchar_t const * const,CCbsInterfaceArray<CCbsPackage *> *)
0x180177704  mov     edi, eax
0x180177706  test    eax, eax
0x180177708  js      loc_1801777FB
0x18017770e  mov     rbx, [rbp+57h+var_58]
0x180177712  mov     rax, qword ptr [rbp+57h+var_70+8]
0x180177716  lea     r14, [rbx+rax*8]
0x18017771a  cmp     rbx, r14
0x18017771d  jz      short loc_180177773
0x18017771f  mov     rsi, [rbx]
0x180177722  lea     rdx, qword_1802EB518
0x180177729  mov     rcx, r12; this
0x18017772c  cmp     [rsi+78h], r13
0x180177730  cmovnz  rdx, [rsi+78h]; wchar_t *
0x180177735  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18017773a  mov     edi, eax
0x18017773c  test    eax, eax
0x18017773e  js      loc_1801777D5
0x180177744  cmp     [rsi+78h], r13
0x180177748  lea     rax, qword_1802EB518
0x18017774f  lea     r8, [rbp+57h+var_98]
0x180177753  mov     ecx, 1
0x180177758  cmovnz  rax, [rsi+78h]
0x18017775d  lea     rdx, aAddedCapabilit; "Added capability package to list of pac"...
0x180177764  mov     [rbp+57h+var_98], rax
0x180177768  call    ??$TraceAtLevel@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevel<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18017776d  add     rbx, 8
0x180177771  jmp     short loc_18017771A
0x180177773  lea     rcx, [rbp+57h+var_B0]
0x180177777  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18017777c  lea     rcx, [rbp+57h+var_80]
0x180177780  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x180177785  mov     rcx, [rbp+57h+pv]; pv
0x180177789  test    rcx, rcx
0x18017778c  jz      short loc_18017779E
0x18017778e  call    cs:__imp_CoTaskMemFree
0x180177795  nop     dword ptr [rax+rax+00h]
0x18017779a  mov     [rbp+57h+pv], r13
0x18017779e  mov     rcx, [rbp+57h+var_D0]; pv
0x1801777a2  test    rcx, rcx
0x1801777a5  jz      short loc_1801777B7
0x1801777a7  call    cs:__imp_CoTaskMemFree
0x1801777ae  nop     dword ptr [rax+rax+00h]
0x1801777b3  mov     [rbp+57h+var_D0], r13
0x1801777b7  mov     rcx, [rbp+57h+var_C8]; pv
0x1801777bb  test    rcx, rcx
0x1801777be  jz      loc_18017763E
0x1801777c4  call    cs:__imp_CoTaskMemFree
0x1801777cb  nop     dword ptr [rax+rax+00h]
0x1801777d0  jmp     loc_18017763E
0x1801777d5  mov     edx, 972h; void *
0x1801777da  mov     rcx, [rbp+5Fh]; this
0x1801777de  lea     r8, aOnecoreBaseCbs_58; "onecore\\base\\cbs\\core\\cbsmaintenanc"...
0x1801777e5  mov     r9d, edi; char *
0x1801777e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801777ed  lea     rcx, [rbp+57h+var_80]
0x1801777f1  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801777f6  jmp     loc_1801778D0
0x1801777fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180177802  mov     dword ptr [rbp+57h+var_98], edi
0x180177805  test    rcx, rcx
0x180177808  jz      short loc_18017785E
0x18017780a  mov     rax, [rbp+57h+var_C8]
0x18017780e  lea     r9, aFailedToEnumer_29; "Failed to enumerate stored packages for"...
0x180177815  mov     [rsp+120h+var_D8], rax
0x18017781a  mov     ebx, 3
0x18017781f  lea     rax, [rsp+120h+var_D8]
0x180177824  mov     r8d, ebx
0x180177827  xor     edx, edx
0x180177829  mov     [rsp+120h+var_100], rax
0x18017782e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180177833  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18017783a  lea     rax, [rbp+57h+var_98]
0x18017783e  mov     qword ptr [rsp+120h+var_E0], rax
0x180177843  lea     r9, asc_1802EE7AC; ": {}"
0x18017784a  lea     rax, [rsp+120h+var_E0]
0x18017784f  mov     r8d, ebx
0x180177852  mov     dl, 1
0x180177854  mov     [rsp+120h+var_100], rax
0x180177859  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18017785e  mov     edx, 96Eh
0x180177863  jmp     loc_1801777DA
0x180177868  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18017786f  mov     dword ptr [rbp+57h+var_98], edi
0x180177872  test    rcx, rcx
0x180177875  jz      short loc_1801778B8
0x180177877  mov     ebx, 3
0x18017787c  lea     r9, aFailedToGetCap_1; "Failed to get capability"
0x180177883  mov     r8d, ebx
0x180177886  xor     edx, edx
0x180177888  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18017788d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180177894  lea     rax, [rbp+57h+var_98]
0x180177898  mov     qword ptr [rsp+120h+var_E0], rax
0x18017789d  lea     r9, asc_1802EE7AC; ": {}"
0x1801778a4  lea     rax, [rsp+120h+var_E0]
0x1801778a9  mov     r8d, ebx
0x1801778ac  mov     dl, 1
0x1801778ae  mov     [rsp+120h+var_100], rax; int
0x1801778b3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801778b8  mov     rcx, [rbp+5Fh]; this
0x1801778bc  lea     r8, aOnecoreBaseCbs_58; "onecore\\base\\cbs\\core\\cbsmaintenanc"...
0x1801778c3  mov     r9d, edi; char *
0x1801778c6  mov     edx, 969h; void *
0x1801778cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801778d0  mov     rcx, [rbp+57h+pv]; pv
0x1801778d4  test    rcx, rcx
0x1801778d7  jz      short loc_1801778E9
0x1801778d9  call    cs:__imp_CoTaskMemFree
0x1801778e0  nop     dword ptr [rax+rax+00h]
0x1801778e5  mov     [rbp+57h+pv], r13
0x1801778e9  mov     rcx, [rbp+57h+var_D0]; pv
0x1801778ed  test    rcx, rcx
0x1801778f0  jz      short loc_180177902
0x1801778f2  call    cs:__imp_CoTaskMemFree
0x1801778f9  nop     dword ptr [rax+rax+00h]
0x1801778fe  mov     [rbp+57h+var_D0], r13
0x180177902  mov     rcx, [rbp+57h+var_C8]; pv
0x180177906  test    rcx, rcx
0x180177909  jz      short loc_18017791B
0x18017790b  call    cs:__imp_CoTaskMemFree
0x180177912  nop     dword ptr [rax+rax+00h]
0x180177917  mov     [rbp+57h+var_C8], r13
0x18017791b  lea     rcx, [rbp+57h+var_B0]
0x18017791f  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180177924  jmp     loc_18017761A
0x180177929  lea     rcx, [rbp+57h+var_B0]
0x18017792d  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180177932  mov     rcx, [rbp+57h+var_A8]
0x180177936  test    rcx, rcx
0x180177939  jz      short loc_180177947
0x18017793b  mov     rax, [rcx]
0x18017793e  mov     rax, [rax+10h]
0x180177942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177947  xor     eax, eax
0x180177949  mov     rcx, [rbp+57h+var_40]
0x18017794d  xor     rcx, rsp; StackCookie
0x180177950  call    __security_check_cookie
0x180177955  mov     rbx, [rsp+120h+arg_10]
0x18017795d  add     rsp, 0F0h
0x180177964  pop     r15
0x180177966  pop     r14
0x180177968  pop     r13
0x18017796a  pop     r12
0x18017796c  pop     rdi
0x18017796d  pop     rsi
0x18017796e  pop     rbp
0x18017796f  retn
```

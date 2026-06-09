# EventMap::AddEntry(HWND__ *,IRawElementProviderSimple *,long *)

- ea: `0x1800637c0`
- end: `0x180064104`
- name: `?AddEntry@EventMap@@QEAAJPEAUHWND__@@PEAUIRawElementProviderSimple@@PEAJ@Z`
- size: `2372`
- prototype: `__int64 __fastcall(PVOID Parameter, HWND, struct IRawElementProviderSimple *, int *)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180061b50`
- `0x1800627b0`
- `0x180065900`
- `0x180065aac`
- `0x180065d90`

## callees

- `0x18000b790`
- `0x18002b608`
- `0x18002f580`
- `0x1800313a0`
- `0x180033f40`
- `0x1800637c0`
- `0x180065704`
- `0x1800d2f00`
- `0x180144bb0`
- `0x18015f004`
- `0x180186cd0`
- `0x1801e8344`
- `0x1801e887c`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063c93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063bc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063bc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180063baf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180063baf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180063f6b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180063f6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063973`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063cc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063973`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063cc1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180063a78`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180063a78`

## string_xrefs

- `0x180063f8d`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x1800640e3`: `onecore\windows\accessibletech\uiautomationcore\threading.cpp`
- `0x180063d86`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063df9`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063e38`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063e95`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063ed4`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063fa6`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x180063ffb`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`
- `0x18006407b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaa_eventmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall EventMap::AddEntry(char *Parameter, HWND a2, struct IRawElementProviderSimple *a3, int *a4)
{
  int v7; // r13d
  __int64 v8; // r14
  int v9; // eax
  unsigned int v10; // esi
  int RuntimeId; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // esi
  RefcountBase *v15; // rax
  RefcountBase *v16; // rsi
  HRESULT Instance; // eax
  unsigned int v18; // r15d
  char *v19; // rdx
  int v20; // eax
  struct IGlobalInterfaceTable *v21; // rcx
  void ***v22; // rcx
  struct IGlobalInterfaceTable *v23; // rax
  struct IGlobalInterfaceTable *v24; // rsi
  DWORD CurrentThreadId; // r15d
  int v26; // ecx
  int v27; // eax
  struct IUiaNode *v28; // rcx
  unsigned int v29; // edx
  char *v30; // rsi
  void *v31; // r15
  void *v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  unsigned __int64 v35; // rsi
  __int64 v36; // rcx
  EventMap *v37; // rcx
  struct IGlobalInterfaceTable *v38; // rcx
  void ***v39; // rcx
  void ***v41; // rcx
  struct IUiaNode *v42; // rcx
  void *v43; // rcx
  struct IGlobalInterfaceTable *v44; // rcx
  void *v45; // rcx
  struct IUiaNode *v46; // rcx
  struct IGlobalInterfaceTable *v47; // rcx
  int ppv; // [rsp+20h] [rbp-99h]
  int ppva; // [rsp+20h] [rbp-99h]
  int ppvb; // [rsp+20h] [rbp-99h]
  int ppvc; // [rsp+20h] [rbp-99h]
  void ***v52; // [rsp+40h] [rbp-79h] BYREF
  struct IUiaNode *v53; // [rsp+48h] [rbp-71h] BYREF
  struct IRawElementProviderSimple *v54; // [rsp+50h] [rbp-69h] BYREF
  void *v55[2]; // [rsp+58h] [rbp-61h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v57; // [rsp+70h] [rbp-49h]
  __int128 v58; // [rsp+80h] [rbp-39h] BYREF
  __int64 v59; // [rsp+90h] [rbp-29h]
  int v60; // [rsp+98h] [rbp-21h]
  void *Block[2]; // [rsp+A0h] [rbp-19h]
  __int64 v62; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v65; // [rsp+120h] [rbp+67h] BYREF
  HWND v66; // [rsp+128h] [rbp+6Fh]
  int v67; // [rsp+130h] [rbp+77h] BYREF
  struct IGlobalInterfaceTable *pAptType; // [rsp+138h] [rbp+7Fh] BYREF

  v66 = a2;
  *a4 = 0;
  v7 = *((_DWORD *)Parameter + 1601);
  v58 = 0;
  v59 = 0;
  v60 = 0;
  *(_OWORD *)Block = 0;
  v8 = 0;
  v62 = 0;
  v63 = 0;
  LODWORD(v55[0]) = 0;
  v55[1] = 0;
  v65 = 0;
  v52 = 0;
  v67 = 0;
  v54 = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IRawElementProviderSimple *))a3->lpVtbl->AddRef)(a3);
  if ( !a3 )
    goto LABEL_32;
  v53 = 0;
  v9 = UiaNodeFactory::FromLocalProvider(a3, 0, 0, &v53, 0);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    v42 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v42 + 16LL))(v42);
    }
    ((void (__fastcall *)(struct IRawElementProviderSimple *))a3->lpVtbl->Release)(a3);
    v43 = 0;
    goto LABEL_65;
  }
  RuntimeId = GetRuntimeId(v53, v55);
  v10 = RuntimeId;
  if ( RuntimeId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
      (const char *)(unsigned int)RuntimeId,
      ppv);
    v46 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    ((void (__fastcall *)(struct IRawElementProviderSimple *))a3->lpVtbl->Release)(a3);
    if ( v55[1] )
      operator delete(v55[1]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    v43 = Block[0];
LABEL_65:
    if ( v43 )
      operator delete(v43);
    return v10;
  }
  v65 = 0;
  *(_QWORD *)pAptQualifier = L"IRawElementProviderSimple::get_ProviderOptions";
  v57 = 0;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v12,
      (unsigned int)UiaProviderCallout_Start,
      (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
      0,
      0);
  v14 = ((__int64 (__fastcall *)(struct IRawElementProviderSimple *, int *))a3->lpVtbl->get_ProviderOptions)(a3, &v65);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v13,
      (unsigned int)UiaProviderCallout_Stop,
      (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
      0,
      0);
  if ( v14 >= 0 )
  {
    v67 = 0;
    if ( (v65 & 0x20) == 0 )
      goto LABEL_59;
    v15 = (RefcountBase *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v16 = v15;
    *(_QWORD *)pAptQualifier = v15;
    if ( v15 )
    {
      *(_OWORD *)v15 = 0;
      *((_QWORD *)v15 + 2) = 0;
      *(_QWORD *)v15 = &RefcountBase::`vftable';
      *((_DWORD *)v15 + 2) = 1;
      _InterlockedIncrement(&dword_18039DE7C);
      *(_QWORD *)v15 = &ComInvokerMarshalingTarget::`vftable'{for `RefcountBase'};
      *((_QWORD *)v15 + 2) = &EventMapCrossThreadReleaser::`vftable'{for `IUIAutomationCrossThreadRelease'};
      *(_QWORD *)pAptQualifier = v15;
      pAptType = 0;
      Instance = CoCreateInstance(
                   &CLSID_StdGlobalInterfaceTable,
                   0,
                   1u,
                   &GUID_00000146_0000_0000_c000_000000000046,
                   (LPVOID *)&pAptType);
      v18 = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x289,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
        v47 = pAptType;
        if ( pAptType )
        {
          pAptType = 0;
          ((void (__fastcall *)(struct IGlobalInterfaceTable *))v47->lpVtbl->Release)(v47);
        }
      }
      else
      {
        v19 = (char *)v16 + 16;
        if ( !v16 )
          v19 = 0;
        v20 = ((__int64 (__fastcall *)(struct IGlobalInterfaceTable *, char *, GUID *, int *))pAptType->lpVtbl->RegisterInterfaceInGlobal)(
                pAptType,
                v19,
                &GUID_2ad63a67_f12f_4bd7_b1bf_6213290a552a,
                &v67);
        v18 = v20;
        if ( v20 >= 0 )
        {
          v21 = pAptType;
          if ( pAptType )
          {
            pAptType = 0;
            ((void (__fastcall *)(struct IGlobalInterfaceTable *))v21->lpVtbl->Release)(v21);
          }
          RefcountBase::Release(v16);
          if ( (v65 & 0x20) != 0 )
          {
            v22 = v52;
            if ( v52 )
            {
              v52 = 0;
              ((void (__fastcall *)(void ***))(*v22)[2])(v22);
            }
            v52 = 0;
            v23 = (struct IGlobalInterfaceTable *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
            v24 = v23;
            pAptType = v23;
            if ( v23 )
            {
              v23->lpVtbl = (struct IGlobalInterfaceTableVtbl *)&RefcountBase::`vftable';
              LODWORD(v23[1].lpVtbl) = 1;
              _InterlockedIncrement(&dword_18039DE7C);
              v23->lpVtbl = (struct IGlobalInterfaceTableVtbl *)&ComInvoker::`vftable'{for `RefcountBase'};
              v23[2].lpVtbl = (struct IGlobalInterfaceTableVtbl *)&ComInvoker::`vftable'{for `ITargetContextInvoker'};
              v23[3].lpVtbl = 0;
              v23[4].lpVtbl = 0;
              LODWORD(v23[5].lpVtbl) = 0;
              CurrentThreadId = GetCurrentThreadId();
              LODWORD(pAptType) = 0;
              pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
              if ( CoGetApartmentType((APTTYPE *)&pAptType, pAptQualifier) < 0 )
              {
                v26 = 3;
              }
              else if ( (_DWORD)pAptType == 3 || !(_DWORD)pAptType )
              {
                v26 = 1;
              }
              else
              {
                v26 = (_DWORD)pAptType - 1;
                if ( (_DWORD)pAptType != 1 )
                {
                  if ( (_DWORD)pAptType == 2 )
                    v26 = 2;
                  else
                    v26 = 3;
                }
              }
              HIDWORD(v24[5].lpVtbl) = v26;
              LODWORD(v24[6].lpVtbl) = CurrentThreadId;
              LODWORD(v24[7].lpVtbl) = 0;
              v24[8].lpVtbl = 0;
              v24[9].lpVtbl = 0;
              v24[10].lpVtbl = 0;
              v24[11].lpVtbl = 0;
              v24[12].lpVtbl = 0;
            }
            else
            {
              v24 = 0;
            }
            pAptType = v24;
            if ( v24 )
            {
              v27 = ComInvoker::Init((ComInvoker *)v24);
              v18 = v27;
              if ( v27 >= 0 )
              {
                v52 = (void ***)&v24[2];
LABEL_30:
                v28 = v53;
                if ( v53 )
                {
                  v53 = 0;
                  (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v28 + 16LL))(v28);
                }
LABEL_32:
                EnterCriticalSection(&EventMap::_lock);
                v29 = *((_DWORD *)Parameter + 1600);
                v30 = &Parameter[64 * (unsigned __int64)v29];
                v31 = (void *)*((_QWORD *)v30 + 5);
                if ( v31 )
                {
                  Block[1] = *((void **)v30 + 5);
                  v63 = *((_QWORD *)v30 + 7);
                  v32 = (void *)*((_QWORD *)v30 + 4);
                  if ( v32 )
                    operator delete(v32);
                  *((_DWORD *)v30 + 6) = 0;
                  *((_QWORD *)v30 + 4) = 0;
                  v29 = *((_DWORD *)Parameter + 1600);
                  v33 = (unsigned __int64)v29 << 6;
                  v34 = *(_QWORD *)&Parameter[v33 + 48];
                  if ( v34 )
                  {
                    *(_QWORD *)&Parameter[v33 + 48] = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                    v29 = *((_DWORD *)Parameter + 1600);
                  }
                }
                else
                {
                  v31 = Block[1];
                }
                v54 = 0;
                *(_QWORD *)&Parameter[64 * (unsigned __int64)v29 + 40] = a3;
                *(_QWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600)] = v66;
                *(_DWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600) + 8] = v7;
                *(_QWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600) + 16] = GetTickCount64();
                *(_DWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600) + 60] = GetCurrentThreadId();
                *(_DWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600) + 56] = v67;
                v35 = (unsigned __int64)*((unsigned int *)Parameter + 1600) << 6;
                if ( *(void ****)&Parameter[v35 + 48] != v52 )
                {
                  if ( v52 )
                    ((void (__fastcall *)(void ***))(*v52)[1])(v52);
                  v36 = *(_QWORD *)&Parameter[v35 + 48];
                  *(_QWORD *)&Parameter[v35 + 48] = v52;
                  if ( v36 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
                *(_OWORD *)&Parameter[64 * (unsigned __int64)*((unsigned int *)Parameter + 1600) + 24] = *(_OWORD *)v55;
                LODWORD(v55[0]) = 0;
                v55[1] = 0;
                if ( ++*((_DWORD *)Parameter + 1600) == 100 )
                  *((_DWORD *)Parameter + 1600) = 0;
                if ( ++*((_DWORD *)Parameter + 1601) == 0x7FFFFFFF )
                  *((_DWORD *)Parameter + 1601) = 1;
                if ( !*((_QWORD *)Parameter + 801) )
                  CreateTimerQueueTimer(
                    (PHANDLE)Parameter + 801,
                    0,
                    EventMap::ReleaseCallback,
                    Parameter,
                    0x3A98u,
                    0x3A98u,
                    0);
                LeaveCriticalSection(&EventMap::_lock);
                if ( v31 )
                {
                  pAptType = 0;
                  CoCreateInstance(
                    &CLSID_StdGlobalInterfaceTable,
                    0,
                    1u,
                    &GUID_00000146_0000_0000_c000_000000000046,
                    (LPVOID *)&pAptType);
                  EventMap::ReleaseOneEntry(v37, (struct EventMapEntry *)&v58, pAptType, 0);
                  v38 = pAptType;
                  if ( pAptType )
                  {
                    pAptType = 0;
                    ((void (__fastcall *)(struct IGlobalInterfaceTable *))v38->lpVtbl->Release)(v38);
                  }
                  v8 = v62;
                }
                *a4 = v7;
                v39 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  ((void (__fastcall *)(void ***))(*v39)[2])(v39);
                }
                if ( v8 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
                if ( Block[0] )
                  operator delete(Block[0]);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x383,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
                (const char *)(unsigned int)v27,
                ppva);
              AutoRelease<ComInvoker *>::~AutoRelease<ComInvoker *>(&pAptType);
            }
            else
            {
              v18 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x382,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\threading.cpp",
                (const char *)0x8007000ELL,
                ppva);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD4,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
              (const char *)v18,
              ppvc);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            v45 = v55[1];
            if ( !v55[1] )
            {
LABEL_73:
              EventMap::EventMapEntry::~EventMapEntry((EventMap::EventMapEntry *)&v58);
              return v18;
            }
LABEL_72:
            operator delete(v45);
            goto LABEL_73;
          }
LABEL_59:
          v41 = v52;
          if ( v52 )
          {
            v52 = 0;
            ((void (__fastcall *)(void ***))(*v41)[2])(v41);
          }
          v52 = &_nullInvoker;
          goto LABEL_30;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28B,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
          (const char *)(unsigned int)v20,
          ppva);
        v44 = pAptType;
        if ( pAptType )
        {
          pAptType = 0;
          ((void (__fastcall *)(struct IGlobalInterfaceTable *))v44->lpVtbl->Release)(v44);
        }
      }
      RefcountBase::Release(v16);
    }
    else
    {
      v18 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x286,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
        (const char *)0x8007000ELL,
        ppv);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
      (const char *)v18,
      ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    v45 = v55[1];
    if ( !v55[1] )
      goto LABEL_73;
    goto LABEL_72;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaa_eventmanager.cpp",
    (const char *)(unsigned int)v14,
    ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  if ( v55[1] )
    operator delete(v55[1]);
  EventMap::EventMapEntry::~EventMapEntry((EventMap::EventMapEntry *)&v58);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800637c0  mov     [rsp-8+arg_8], rdx
0x1800637c5  push    rbp
0x1800637c6  push    rbx
0x1800637c7  push    rsi
0x1800637c8  push    rdi
0x1800637c9  push    r12
0x1800637cb  push    r13
0x1800637cd  push    r14
0x1800637cf  push    r15
0x1800637d1  lea     rbp, [rsp-1Fh]
0x1800637d6  sub     rsp, 0D8h
0x1800637dd  movaps  [rsp+110h+var_50], xmm6
0x1800637e5  mov     r12, r9
0x1800637e8  mov     rbx, r8
0x1800637eb  mov     rdi, rcx
0x1800637ee  xor     r15d, r15d
0x1800637f1  mov     [r9], r15d
0x1800637f4  mov     r13d, [rcx+1904h]
0x1800637fb  xor     eax, eax
0x1800637fd  xorps   xmm0, xmm0
0x180063800  movups  [rbp+57h+var_90], xmm0
0x180063804  mov     [rbp+57h+var_80], rax
0x180063808  mov     [rbp+57h+var_78], r15d
0x18006380c  xorps   xmm6, xmm6
0x18006380f  movdqa  xmmword ptr [rbp+57h+Block], xmm6
0x180063814  mov     r14d, r15d
0x180063817  mov     [rbp+57h+var_60], r15
0x18006381b  mov     [rbp+57h+var_58], rax
0x18006381f  mov     dword ptr [rbp+57h+var_B8], r15d
0x180063823  mov     [rbp+57h+var_B8+8], r15
0x180063827  mov     [rbp+57h+arg_0], r15d
0x18006382b  mov     [rbp+57h+var_D0], r15
0x18006382f  mov     [rbp+57h+arg_10], r15d
0x180063833  mov     [rbp+57h+var_C0], rbx
0x180063837  test    r8, r8
0x18006383a  jz      short loc_18006384C
0x18006383c  mov     rax, [r8]
0x18006383f  mov     rcx, rbx
0x180063842  mov     rax, [rax+8]
0x180063846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006384b  nop
0x18006384c  test    rbx, rbx
0x18006384f  jz      loc_180063AFD
0x180063855  mov     [rbp+57h+var_C8], r15
0x180063859  mov     [rsp+110h+ppv], r15; int
0x18006385e  lea     r9, [rbp+57h+var_C8]; struct IUiaNode **
0x180063862  xor     r8d, r8d; struct UiaClientState *
0x180063865  xor     edx, edx; int
0x180063867  mov     rcx, rbx; struct IRawElementProviderSimple *
0x18006386a  call    ?FromLocalProvider@UiaNodeFactory@@SAJPEAUIRawElementProviderSimple@@HPEAVUiaClientState@@PEAPEAVIUiaNode@@PEAH@Z; UiaNodeFactory::FromLocalProvider(IRawElementProviderSimple *,int,UiaClientState *,IUiaNode * *,int *)
0x18006386f  mov     esi, eax
0x180063871  test    eax, eax
0x180063873  js      loc_180063D7F
0x180063879  lea     rdx, [rbp+57h+var_B8]
0x18006387d  mov     rcx, [rbp+57h+var_C8]
0x180063881  call    ?GetRuntimeId@@YAJPEAVIUiaNode@@PEAU?$BasicArrayPair@H@@@Z; GetRuntimeId(IUiaNode *,BasicArrayPair<int> *)
0x180063886  mov     esi, eax
0x180063888  test    eax, eax
0x18006388a  js      loc_180063ECD
0x180063890  mov     [rbp+57h+arg_0], r15d
0x180063894  lea     rax, aIrawelementpro_9; "IRawElementProviderSimple::get_Provider"...
0x18006389b  mov     qword ptr [rbp+57h+pAptQualifier], rax
0x18006389f  mov     [rbp+57h+var_A0], r15
0x1800638a3  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800638aa  jnz     loc_180064038
0x1800638b0  mov     rax, [rbx]
0x1800638b3  lea     rdx, [rbp+57h+arg_0]
0x1800638b7  mov     rcx, rbx
0x1800638ba  mov     rax, [rax+18h]
0x1800638be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638c3  mov     esi, eax
0x1800638c5  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800638cc  jnz     loc_180064054
0x1800638d2  test    esi, esi
0x1800638d4  js      loc_180064074
0x1800638da  mov     [rbp+57h+arg_10], r15d
0x1800638de  mov     eax, [rbp+57h+arg_0]
0x1800638e1  test    al, 20h
0x1800638e3  jz      loc_180063D55
0x1800638e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800638f0  mov     ecx, 18h; unsigned __int64
0x1800638f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800638fa  mov     rsi, rax
0x1800638fd  mov     qword ptr [rbp+57h+pAptQualifier], rax
0x180063901  test    rax, rax
0x180063904  jz      loc_180063E88
0x18006390a  xorps   xmm0, xmm0
0x18006390d  xor     eax, eax
0x18006390f  movups  xmmword ptr [rsi], xmm0
0x180063912  mov     [rsi+10h], rax
0x180063916  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x18006391d  mov     [rsi], rax
0x180063920  mov     dword ptr [rsi+8], 1
0x180063927  lock inc cs:dword_18039DE7C
0x18006392e  lea     rax, ??_7ComInvokerMarshalingTarget@@6BRefcountBase@@@; const ComInvokerMarshalingTarget::`vftable'{for `RefcountBase'}
0x180063935  mov     [rsi], rax
0x180063938  lea     rax, ??_7EventMapCrossThreadReleaser@@6BIUIAutomationCrossThreadRelease@@@; const EventMapCrossThreadReleaser::`vftable'{for `IUIAutomationCrossThreadRelease'}
0x18006393f  mov     [rsi+10h], rax
0x180063943  mov     qword ptr [rbp+57h+pAptQualifier], rsi
0x180063947  test    rsi, rsi
0x18006394a  jz      loc_180063E88
0x180063950  mov     [rbp+57h+pAptType], r15
0x180063954  lea     rax, [rbp+57h+pAptType]
0x180063958  mov     [rsp+110h+ppv], rax; int
0x18006395d  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180063964  xor     edx, edx; pUnkOuter
0x180063966  mov     r8d, 1; dwClsContext
0x18006396c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180063973  call    cs:__imp_CoCreateInstance
0x180063979  mov     r15d, eax
0x18006397c  test    eax, eax
0x18006397e  js      loc_180063FF4
0x180063984  mov     rcx, [rbp+57h+pAptType]
0x180063988  mov     r8, [rcx]
0x18006398b  lea     rdx, [rsi+10h]
0x18006398f  xor     eax, eax
0x180063991  test    rsi, rsi
0x180063994  cmovz   rdx, rax
0x180063998  mov     rax, [r8+18h]
0x18006399c  lea     r9, [rbp+57h+arg_10]
0x1800639a0  lea     r8, _GUID_2ad63a67_f12f_4bd7_b1bf_6213290a552a
0x1800639a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639ac  mov     r15d, eax
0x1800639af  test    eax, eax
0x1800639b1  js      loc_180063DF2
0x1800639b7  mov     rcx, [rbp+57h+pAptType]
0x1800639bb  xor     r15d, r15d
0x1800639be  test    rcx, rcx
0x1800639c1  jz      short loc_1800639D4
0x1800639c3  mov     [rbp+57h+pAptType], r15
0x1800639c7  mov     rax, [rcx]
0x1800639ca  mov     rax, [rax+10h]
0x1800639ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639d3  nop
0x1800639d4  mov     rcx, rsi; this
0x1800639d7  call    ?Release@RefcountBase@@QEAAKXZ; RefcountBase::Release(void)
0x1800639dc  mov     eax, [rbp+57h+arg_0]
0x1800639df  test    al, 20h
0x1800639e1  jz      loc_180063D55
0x1800639e7  mov     rcx, [rbp+57h+var_D0]
0x1800639eb  test    rcx, rcx
0x1800639ee  jz      short loc_180063A01
0x1800639f0  mov     [rbp+57h+var_D0], r15
0x1800639f4  mov     rax, [rcx]
0x1800639f7  mov     rax, [rax+10h]
0x1800639fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a00  nop
0x180063a01  mov     [rbp+57h+var_D0], r15
0x180063a05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063a0c  mov     ecx, 68h ; 'h'; unsigned __int64
0x180063a11  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180063a16  mov     rsi, rax
0x180063a19  mov     [rbp+57h+pAptType], rax
0x180063a1d  test    rax, rax
0x180063a20  jz      loc_1800640D4
0x180063a26  lea     rax, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x180063a2d  mov     [rsi], rax
0x180063a30  mov     dword ptr [rsi+8], 1
0x180063a37  lock inc cs:dword_18039DE7C
0x180063a3e  lea     rax, ??_7ComInvoker@@6BRefcountBase@@@; const ComInvoker::`vftable'{for `RefcountBase'}
0x180063a45  mov     [rsi], rax
0x180063a48  lea     rax, ??_7ComInvoker@@6BITargetContextInvoker@@@; const ComInvoker::`vftable'{for `ITargetContextInvoker'}
0x180063a4f  mov     [rsi+10h], rax
0x180063a53  mov     [rsi+18h], r15
0x180063a57  mov     [rsi+20h], r15
0x180063a5b  mov     [rsi+28h], r15d
0x180063a5f  call    cs:__imp_GetCurrentThreadId
0x180063a65  mov     r15d, eax
0x180063a68  xor     eax, eax
0x180063a6a  mov     dword ptr [rbp+57h+pAptType], eax
0x180063a6d  mov     [rbp+57h+pAptQualifier], eax
0x180063a70  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x180063a74  lea     rcx, [rbp+57h+pAptType]; pAptType
0x180063a78  call    cs:__imp_CoGetApartmentType
0x180063a7e  test    eax, eax
0x180063a80  js      loc_180063F76
0x180063a86  mov     ecx, dword ptr [rbp+57h+pAptType]
0x180063a89  cmp     ecx, 3
0x180063a8c  jnz     loc_180063EA9
0x180063a92  mov     ecx, 1
0x180063a97  mov     [rsi+2Ch], ecx
0x180063a9a  mov     [rsi+30h], r15d
0x180063a9e  xor     ecx, ecx
0x180063aa0  mov     [rsi+38h], ecx
0x180063aa3  mov     [rsi+40h], rcx
0x180063aa7  mov     [rsi+48h], rcx
0x180063aab  mov     [rsi+50h], rcx
0x180063aaf  mov     [rsi+58h], rcx
0x180063ab3  mov     [rsi+60h], rcx
0x180063ab7  mov     [rbp+57h+pAptType], rsi
0x180063abb  test    rsi, rsi
0x180063abe  jz      loc_180063F80
0x180063ac4  mov     rcx, rsi; this
0x180063ac7  call    ?Init@ComInvoker@@QEAAJXZ; ComInvoker::Init(void)
0x180063acc  mov     r15d, eax
0x180063acf  test    eax, eax
0x180063ad1  js      loc_1800640DC
0x180063ad7  lea     rax, [rsi+10h]
0x180063adb  mov     [rbp+57h+var_D0], rax
0x180063adf  mov     rcx, [rbp+57h+var_C8]
0x180063ae3  test    rcx, rcx
0x180063ae6  jz      short loc_180063AFD
0x180063ae8  mov     [rbp+57h+var_C8], 0
0x180063af0  mov     rax, [rcx]
0x180063af3  mov     rax, [rax+10h]
0x180063af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063afc  nop
0x180063afd  lea     rcx, ?_lock@EventMap@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180063b04  call    cs:__imp_EnterCriticalSection
0x180063b0a  mov     edx, [rdi+1900h]
0x180063b10  mov     esi, edx
0x180063b12  shl     rsi, 6
0x180063b16  add     rsi, rdi
0x180063b19  mov     r15, [rsi+28h]
0x180063b1d  test    r15, r15
0x180063b20  jz      loc_180063FE8
0x180063b26  mov     [rbp+57h+Block+8], r15
0x180063b2a  mov     eax, [rsi+38h]
0x180063b2d  mov     dword ptr [rbp+57h+var_58], eax
0x180063b30  mov     eax, [rsi+3Ch]
0x180063b33  mov     dword ptr [rbp+57h+var_58+4], eax
0x180063b36  mov     rcx, [rsi+20h]; Block
0x180063b3a  test    rcx, rcx
0x180063b3d  jz      short loc_180063B44
0x180063b3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063b44  xor     r8d, r8d
0x180063b47  mov     [rsi+18h], r8d
0x180063b4b  mov     [rsi+20h], r8
0x180063b4f  mov     edx, [rdi+1900h]
0x180063b55  mov     eax, edx
0x180063b57  shl     rax, 6
0x180063b5b  mov     rcx, [rax+rdi+30h]
0x180063b60  test    rcx, rcx
0x180063b63  jz      short loc_180063B7F
0x180063b65  mov     [rax+rdi+30h], r8
0x180063b6a  mov     rax, [rcx]
0x180063b6d  mov     rax, [rax+10h]
0x180063b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b76  mov     edx, [rdi+1900h]
0x180063b7c  xor     r8d, r8d
0x180063b7f  mov     [rbp+57h+var_C0], r8
0x180063b83  mov     eax, edx
0x180063b85  shl     rax, 6
0x180063b89  mov     [rax+rdi+28h], rbx
0x180063b8e  mov     eax, [rdi+1900h]
0x180063b94  shl     rax, 6
0x180063b98  mov     rcx, [rbp+57h+arg_8]
0x180063b9c  mov     [rax+rdi], rcx
0x180063ba0  mov     eax, [rdi+1900h]
0x180063ba6  shl     rax, 6
0x180063baa  mov     [rax+rdi+8], r13d
0x180063baf  call    cs:__imp_GetTickCount64
0x180063bb5  mov     ecx, [rdi+1900h]
0x180063bbb  shl     rcx, 6
0x180063bbf  mov     [rcx+rdi+10h], rax
0x180063bc4  call    cs:__imp_GetCurrentThreadId
0x180063bca  mov     ecx, [rdi+1900h]
0x180063bd0  shl     rcx, 6
0x180063bd4  mov     [rcx+rdi+3Ch], eax
0x180063bd8  mov     ecx, [rdi+1900h]
0x180063bde  shl     rcx, 6
0x180063be2  mov     eax, [rbp+57h+arg_10]
0x180063be5  mov     [rcx+rdi+38h], eax
0x180063be9  mov     esi, [rdi+1900h]
0x180063bef  shl     rsi, 6
0x180063bf3  mov     rbx, [rbp+57h+var_D0]
0x180063bf7  cmp     [rsi+rdi+30h], rbx
0x180063bfc  jz      short loc_180063C2F
0x180063bfe  test    rbx, rbx
0x180063c01  jz      short loc_180063C13
0x180063c03  mov     rax, [rbx]
0x180063c06  mov     rcx, rbx
0x180063c09  mov     rax, [rax+8]
0x180063c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c12  nop
0x180063c13  mov     rcx, [rsi+rdi+30h]
0x180063c18  mov     [rsi+rdi+30h], rbx
0x180063c1d  test    rcx, rcx
0x180063c20  jz      short loc_180063C2F
0x180063c22  mov     rax, [rcx]
0x180063c25  mov     rax, [rax+10h]
0x180063c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c2e  nop
0x180063c2f  mov     eax, [rdi+1900h]
0x180063c35  shl     rax, 6
0x180063c39  movups  xmm0, xmmword ptr [rbp+57h+var_B8]
0x180063c3d  movups  xmmword ptr [rax+rdi+18h], xmm0
0x180063c42  xor     ebx, ebx
0x180063c44  mov     dword ptr [rbp+57h+var_B8], ebx
0x180063c47  mov     [rbp+57h+var_B8+8], rbx
0x180063c4b  inc     dword ptr [rdi+1900h]
0x180063c51  cmp     dword ptr [rdi+1900h], 64h ; 'd'
0x180063c58  jnz     short loc_180063C60
0x180063c5a  mov     [rdi+1900h], ebx
0x180063c60  inc     dword ptr [rdi+1904h]
0x180063c66  cmp     dword ptr [rdi+1904h], 7FFFFFFFh
0x180063c70  jnz     short loc_180063C7C
0x180063c72  mov     dword ptr [rdi+1904h], 1
0x180063c7c  lea     rcx, [rdi+1908h]; phNewTimer
0x180063c83  cmp     [rcx], rbx
  ... truncated ...
```

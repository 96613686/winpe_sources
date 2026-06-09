# ActionDialogManager::HandlePromptSync(void *)

- ea: `0x140004f6c`
- end: `0x1400057f3`
- name: `?HandlePromptSync@ActionDialogManager@@SAJPEAX@Z`
- size: `2183`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x140007a78`

## callees

- `0x140001460`
- `0x140002d98`
- `0x1400032f4`
- `0x140003524`
- `0x140003888`
- `0x140004b48`
- `0x140004f6c`
- `0x1400063f0`
- `0x140006734`
- `0x140008124`
- `0x14000a010`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x1400053aa`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400053aa`
- `KERNEL32!CloseHandle` at `0x1400052de`
- `KERNEL32!CloseHandle` at `0x1400054ba`
- `KERNEL32!CloseHandle` at `0x1400055bc`
- `KERNEL32!CloseHandle` at `0x1400056a1`
- `KERNEL32!CloseHandle` at `0x140005737`
- `KERNEL32!CloseHandle` at `0x1400052de`
- `KERNEL32!CloseHandle` at `0x1400054ba`
- `KERNEL32!CloseHandle` at `0x1400055bc`
- `KERNEL32!CloseHandle` at `0x1400056a1`
- `KERNEL32!CloseHandle` at `0x140005737`
- `KERNEL32!GetTickCount64` at `0x14000538d`
- `KERNEL32!GetTickCount64` at `0x14000538d`
- `ole32!CoSetProxyBlanket` at `0x140004fed`
- `ole32!CoSetProxyBlanket` at `0x140004fed`
- `ole32!CoCreateInstance` at `0x140004fb7`
- `ole32!CoCreateInstance` at `0x140004fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000510f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000511a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400051a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400051b3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005241`
- `OLEAUT32!__imp_SysFreeString` at `0x14000524c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400052e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400052f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400054c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400054d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400055c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400055d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400056ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1400056b7`
- `OLEAUT32!__imp_SysFreeString` at `0x140005742`
- `OLEAUT32!__imp_SysFreeString` at `0x14000574d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000510f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000511a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400051a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400051b3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005241`
- `OLEAUT32!__imp_SysFreeString` at `0x14000524c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400052e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400052f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1400054c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400054d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400055c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400055d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400056ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1400056b7`
- `OLEAUT32!__imp_SysFreeString` at `0x140005742`
- `OLEAUT32!__imp_SysFreeString` at `0x14000574d`
- `OLEAUT32!__imp_SysStringLen` at `0x1400053e8`
- `OLEAUT32!__imp_SysStringLen` at `0x140005403`
- `OLEAUT32!__imp_SysStringLen` at `0x1400053e8`
- `OLEAUT32!__imp_SysStringLen` at `0x140005403`

## string_xrefs

- `0x140005797`: `LocationHelper::CreateLocationManagerInternalOutOfProc(pFramework.GetAddressOf())`
- `0x140005029`: `pFramework->PeekActionDialog(pServiceCurrentPrompt.GetAddressOf())`
- `0x1400050e6`: `pServiceCurrentPrompt->get_TitleText(&title)`
- `0x14000517f`: `pServiceCurrentPrompt->get_MessageText(&message)`
- `0x140005218`: `pServiceCurrentPrompt->get_DialogMode(&mode)`
- `0x1400052af`: `GetSessionNotificationHandler(pServiceCurrentPrompt.Get(), &(clientCancelEvent.m_h))`
- `0x14000563c`: `pServiceCurrentPrompt->put_PromptAnswer(provisioningConsentWindow.CheckUserResponse())`

## pseudocode

```c
__int64 __fastcall ActionDialogManager::HandlePromptSync(void *a1)
{
  unsigned int Instance; // ebx
  int v3; // eax
  struct IWindowsActionDialog *v4; // rcx
  IUnknown *v5; // rcx
  IUnknown *v6; // rcx
  int v8; // eax
  struct IWindowsActionDialog *v9; // rcx
  IUnknown *v10; // rcx
  int v11; // eax
  struct IWindowsActionDialog *v12; // rcx
  IUnknown *v13; // rcx
  int v14; // eax
  struct IWindowsActionDialog *v15; // rcx
  IUnknown *v16; // rcx
  int SessionNotificationHandler; // eax
  struct IWindowsActionDialog *v18; // rcx
  IUnknown *v19; // rcx
  _QWORD *v20; // rdx
  UINT v21; // eax
  UINT v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  struct IWindowsActionDialog *v25; // rcx
  IUnknown *v26; // rcx
  HANDLE v27; // rbx
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rcx
  struct IWindowsActionDialog *v33; // rcx
  IUnknown *v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  struct IWindowsActionDialog *v37; // rcx
  IUnknown *v38; // rcx
  __int64 v39; // rcx
  struct IWindowsActionDialog *v40; // rcx
  IUnknown *v41; // rcx
  IUnknown *v42; // rcx
  wil::details *dwImpLevel; // [rsp+28h] [rbp-D8h]
  int pAuthInfo; // [rsp+30h] [rbp-D0h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v46[7]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v47; // [rsp+88h] [rbp-78h]
  int v48; // [rsp+90h] [rbp-70h] BYREF
  struct IWindowsActionDialog *v49; // [rsp+98h] [rbp-68h] BYREF
  IUnknown *pProxy; // [rsp+A0h] [rbp-60h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp-58h] BYREF
  BSTR pbstr; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v53; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v55; // [rsp+C8h] [rbp-38h]
  int v56; // [rsp+CCh] [rbp-34h]
  unsigned __int16 *v57[4]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v58[4]; // [rsp+F0h] [rbp-10h] BYREF
  void **pv; // [rsp+110h] [rbp+10h] BYREF
  int v60; // [rsp+118h] [rbp+18h]
  _BYTE v61[56]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v62; // [rsp+158h] [rbp+58h]
  __int64 v63; // [rsp+160h] [rbp+60h]
  ULONGLONG v64; // [rsp+168h] [rbp+68h]
  __int64 v65; // [rsp+170h] [rbp+70h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+178h] [rbp+78h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1D8h] [rbp+D8h]

  pProxy = 0;
  Instance = CoCreateInstance(
               &GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd,
               0,
               4u,
               &GUID_bb31bcf1_230a_4bea_abef_26a3887f122a,
               (LPVOID *)&pProxy);
  if ( (Instance & 0x80000000) != 0
    || (Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u), (Instance & 0x80000000) != 0) )
  {
    LODWORD(dwImpLevel) = Instance;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "LocationHelper::CreateLocationManagerInternalOutOfProc(pFramework.GetAddressOf())",
      dwImpLevel,
      pAuthInfo);
    v42 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
    }
    return Instance;
  }
  v49 = 0;
  v3 = ((__int64 (__fastcall *)(IUnknown *, struct IWindowsActionDialog **))pProxy->lpVtbl[9].AddRef)(pProxy, &v49);
  Instance = v3;
  if ( v3 < 0 )
  {
    LODWORD(dwImpLevel) = v3;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "pFramework->PeekActionDialog(pServiceCurrentPrompt.GetAddressOf())",
      dwImpLevel,
      pAuthInfo);
    v4 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
    }
    return Instance;
  }
  if ( !v49 )
  {
    v6 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
    }
    return 1;
  }
  pbstr = 0;
  bstrString = 0;
  v53 = 0;
  v48 = 0;
  hObject[0] = 0;
  v8 = (*(__int64 (__fastcall **)(struct IWindowsActionDialog *, BSTR *))(*(_QWORD *)v49 + 40LL))(v49, &pbstr);
  Instance = v8;
  if ( v8 < 0 )
  {
    LODWORD(dwImpLevel) = v8;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "pServiceCurrentPrompt->get_TitleText(&title)",
      dwImpLevel,
      pAuthInfo);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v9 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
    }
    return Instance;
  }
  v11 = (*(__int64 (__fastcall **)(struct IWindowsActionDialog *, BSTR *))(*(_QWORD *)v49 + 32LL))(v49, &bstrString);
  Instance = v11;
  if ( v11 < 0 )
  {
    LODWORD(dwImpLevel) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "pServiceCurrentPrompt->get_MessageText(&message)",
      dwImpLevel,
      pAuthInfo);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v12 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
    }
    return Instance;
  }
  v14 = (*(__int64 (__fastcall **)(struct IWindowsActionDialog *, int *))(*(_QWORD *)v49 + 48LL))(v49, &v48);
  Instance = v14;
  if ( v14 < 0 )
  {
    LODWORD(dwImpLevel) = v14;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "pServiceCurrentPrompt->get_DialogMode(&mode)",
      dwImpLevel,
      pAuthInfo);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v15 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v16->lpVtbl->Release)(v16);
    }
    return Instance;
  }
  SessionNotificationHandler = GetSessionNotificationHandler(v49, hObject);
  Instance = SessionNotificationHandler;
  if ( SessionNotificationHandler < 0 )
  {
    LODWORD(dwImpLevel) = SessionNotificationHandler;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "GetSessionNotificationHandler(pServiceCurrentPrompt.Get(), &(clientCancelEvent.m_h))",
      dwImpLevel,
      pAuthInfo);
    if ( hObject[0] )
      CloseHandle(hObject[0]);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v18 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
    }
    return Instance;
  }
  if ( (*(int (__fastcall **)(struct IWindowsActionDialog *, unsigned int *))(*(_QWORD *)v49 + 56LL))(v49, &v53) < 0 )
    v53 = 30000;
  v46[0] = std::J$$V::Z::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync'::`2'::_lambda_1_,long near * const volatile,void *>::`vftable';
  v46[1] = a1;
  v47 = v46;
  hObject[1] = v46;
  pv = &ResettableTimer::`vftable';
  v60 = 0;
  v62 = 0;
  v63 = 0;
  v64 = GetTickCount64() - 60000;
  v65 = 0;
  InitializeCriticalSectionEx(&CriticalSection, 0, 0);
  std::function<long (void)>::operator=(v61, v46);
  if ( v47 )
  {
    v20 = v46;
    LOBYTE(v20) = v47 != v46;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v47 + 32LL))(v47, v20);
    v47 = 0;
  }
  v21 = SysStringLen(pbstr);
  std::wstring::wstring(v58, pbstr, v21);
  v22 = SysStringLen(bstrString);
  std::wstring::wstring(v57, bstrString, v22);
  v54 = 0;
  v55 = 3;
  v56 = v48;
  v23 = ResettableTimer::SetDueTimeFromNow(&pv, v53);
  Instance = v23;
  if ( v23 < 0 )
  {
    LODWORD(dwImpLevel) = v23;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "_timer.SetDueTimeFromNow(timeoutMs)",
      dwImpLevel,
      pAuthInfo);
    v24 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    std::wstring::~wstring(v57);
    std::wstring::~wstring(v58);
    ResettableTimer::~ResettableTimer((ResettableTimer *)&pv);
    if ( hObject[0] )
      CloseHandle(hObject[0]);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v25 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
    }
    return Instance;
  }
  v27 = hObject[0];
  v28 = (const unsigned __int16 *)v57;
  if ( v57[3] > (unsigned __int16 *)7 )
    v28 = v57[0];
  v29 = (const unsigned __int16 *)v58;
  if ( v58[3] > (unsigned __int16 *)7 )
    v29 = v58[0];
  v30 = CSystemPopupWindow::ShowSystemDialog((CSystemPopupWindow *)&v54, v29, v28, a1, hObject[0]);
  v31 = v30;
  if ( v30 < 0 )
  {
    LODWORD(dwImpLevel) = v30;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "provisioningConsentWindow.ShowSystemDialog(realTitle.c_str(), realMessage.c_str(), timeoutEvent, clientCancelEvent.m_h)",
      dwImpLevel,
      pAuthInfo);
    v32 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    std::wstring::~wstring(v57);
    std::wstring::~wstring(v58);
    ResettableTimer::~ResettableTimer((ResettableTimer *)&pv);
    if ( v27 )
      CloseHandle(v27);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v33 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v34->lpVtbl->Release)(v34);
    }
    return v31;
  }
  v35 = (*(__int64 (__fastcall **)(struct IWindowsActionDialog *, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, v55);
  v31 = v35;
  if ( v35 < 0 )
  {
    LODWORD(dwImpLevel) = v35;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::HandlePromptSync",
      "pServiceCurrentPrompt->put_PromptAnswer(provisioningConsentWindow.CheckUserResponse())",
      dwImpLevel,
      pAuthInfo);
    v36 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    std::wstring::~wstring(v57);
    std::wstring::~wstring(v58);
    ResettableTimer::~ResettableTimer((ResettableTimer *)&pv);
    if ( v27 )
      CloseHandle(v27);
    SysFreeString(bstrString);
    SysFreeString(pbstr);
    v37 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v38->lpVtbl->Release)(v38);
    }
    return v31;
  }
  v39 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  std::wstring::~wstring(v57);
  std::wstring::~wstring(v58);
  ResettableTimer::~ResettableTimer((ResettableTimer *)&pv);
  if ( v27 )
    CloseHandle(v27);
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  v40 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(struct IWindowsActionDialog *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v41->lpVtbl->Release)(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x140004f6c  push    rbp
0x140004f6e  push    rbx
0x140004f6f  push    rsi
0x140004f70  push    rdi
0x140004f71  lea     rbp, [rsp-0B8h]
0x140004f79  sub     rsp, 1B8h
0x140004f80  mov     rax, cs:__security_cookie
0x140004f87  xor     rax, rsp
0x140004f8a  mov     [rbp+0D0h+var_30], rax
0x140004f91  mov     rdi, rcx
0x140004f94  xor     esi, esi
0x140004f96  mov     [rbp+0D0h+pProxy], rsi
0x140004f9a  lea     rax, [rbp+0D0h+pProxy]
0x140004f9e  mov     [rsp+1D0h+ppv], rax; ppv
0x140004fa3  lea     r9, _GUID_bb31bcf1_230a_4bea_abef_26a3887f122a; riid
0x140004faa  xor     edx, edx; pUnkOuter
0x140004fac  lea     r8d, [rsi+4]; dwClsContext
0x140004fb0  lea     rcx, _GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd; rclsid
0x140004fb7  call    cs:__imp_CoCreateInstance
0x140004fbd  mov     ebx, eax
0x140004fbf  test    eax, eax
0x140004fc1  js      loc_14000578C
0x140004fc7  mov     [rsp+1D0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x140004fcf  mov     [rsp+1D0h+pAuthInfo], rsi; int
0x140004fd4  mov     dword ptr [rsp+1D0h+dwImpLevel], 3; dwImpLevel
0x140004fdc  mov     dword ptr [rsp+1D0h+ppv], esi; dwAuthnLevel
0x140004fe0  xor     r9d, r9d; pServerPrincName
0x140004fe3  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x140004fe6  mov     r8d, edx; dwAuthzSvc
0x140004fe9  mov     rcx, [rbp+0D0h+pProxy]; pProxy
0x140004fed  call    cs:__imp_CoSetProxyBlanket
0x140004ff3  mov     ebx, eax
0x140004ff5  test    eax, eax
0x140004ff7  js      loc_14000578C
0x140004ffd  mov     [rbp+0D0h+var_138], rsi
0x140005001  mov     rcx, [rbp+0D0h+pProxy]
0x140005005  mov     rax, [rcx]
0x140005008  lea     rdx, [rbp+0D0h+var_138]
0x14000500c  mov     rax, [rax+0E0h]
0x140005013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005018  mov     ebx, eax
0x14000501a  test    eax, eax
0x14000501c  jns     short loc_140005085
0x14000501e  mov     rcx, [rbp+0D8h]; this
0x140005025  mov     dword ptr [rsp+1D0h+dwImpLevel], eax; wil::details *
0x140005029  lea     rax, aPframeworkPeek; "pFramework->PeekActionDialog(pServiceCu"...
0x140005030  mov     [rsp+1D0h+ppv], rax; char *
0x140005035  lea     r9, aActiondialogma_1; "ActionDialogManager::HandlePromptSync"
0x14000503c  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140005043  lea     edx, [rsi+78h]; void *
0x140005046  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x14000504b  nop
0x14000504c  mov     rcx, [rbp+0D0h+var_138]
0x140005050  test    rcx, rcx
0x140005053  jz      short loc_140005066
0x140005055  mov     [rbp+0D0h+var_138], rsi
0x140005059  mov     rax, [rcx]
0x14000505c  mov     rax, [rax+10h]
0x140005060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005065  nop
0x140005066  mov     rcx, [rbp+0D0h+pProxy]
0x14000506a  test    rcx, rcx
0x14000506d  jz      short loc_140005080
0x14000506f  mov     [rbp+0D0h+pProxy], rsi
0x140005073  mov     rax, [rcx]
0x140005076  mov     rax, [rax+10h]
0x14000507a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000507f  nop
0x140005080  jmp     loc_1400057D6
0x140005085  mov     rcx, [rbp+0D0h+var_138]
0x140005089  test    rcx, rcx
0x14000508c  jnz     short loc_1400050B2
0x14000508e  mov     rcx, [rbp+0D0h+pProxy]
0x140005092  test    rcx, rcx
0x140005095  jz      short loc_1400050A8
0x140005097  mov     [rbp+0D0h+pProxy], rsi
0x14000509b  mov     rax, [rcx]
0x14000509e  mov     rax, [rax+10h]
0x1400050a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050a7  nop
0x1400050a8  mov     eax, 1
0x1400050ad  jmp     loc_1400057D8
0x1400050b2  mov     [rbp+0D0h+pbstr], rsi
0x1400050b6  mov     [rbp+0D0h+bstrString], rsi
0x1400050ba  mov     [rbp+0D0h+var_118], esi
0x1400050bd  mov     [rbp+0D0h+var_140], esi
0x1400050c0  mov     [rsp+1D0h+hObject], rsi
0x1400050c5  mov     rax, [rcx]
0x1400050c8  lea     rdx, [rbp+0D0h+pbstr]
0x1400050cc  mov     rax, [rax+28h]
0x1400050d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050d5  mov     ebx, eax
0x1400050d7  test    eax, eax
0x1400050d9  jns     short loc_14000515A
0x1400050db  mov     rcx, [rbp+0D8h]; this
0x1400050e2  mov     dword ptr [rsp+1D0h+dwImpLevel], eax; wil::details *
0x1400050e6  lea     rax, aPservicecurren_0; "pServiceCurrentPrompt->get_TitleText(&t"...
0x1400050ed  mov     [rsp+1D0h+ppv], rax; char *
0x1400050f2  lea     r9, aActiondialogma_1; "ActionDialogManager::HandlePromptSync"
0x1400050f9  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140005100  mov     edx, 84h; void *
0x140005105  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x14000510a  nop
0x14000510b  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x14000510f  call    cs:__imp_SysFreeString
0x140005115  nop
0x140005116  mov     rcx, [rbp+0D0h+pbstr]; bstrString
0x14000511a  call    cs:__imp_SysFreeString
0x140005120  nop
0x140005121  mov     rcx, [rbp+0D0h+var_138]
0x140005125  test    rcx, rcx
0x140005128  jz      short loc_14000513B
0x14000512a  mov     [rbp+0D0h+var_138], rsi
0x14000512e  mov     rax, [rcx]
0x140005131  mov     rax, [rax+10h]
0x140005135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000513a  nop
0x14000513b  mov     rcx, [rbp+0D0h+pProxy]
0x14000513f  test    rcx, rcx
0x140005142  jz      short loc_140005155
0x140005144  mov     [rbp+0D0h+pProxy], rsi
0x140005148  mov     rax, [rcx]
0x14000514b  mov     rax, [rax+10h]
0x14000514f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005154  nop
0x140005155  jmp     loc_1400057D6
0x14000515a  mov     rcx, [rbp+0D0h+var_138]
0x14000515e  mov     rax, [rcx]
0x140005161  lea     rdx, [rbp+0D0h+bstrString]
0x140005165  mov     rax, [rax+20h]
0x140005169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000516e  mov     ebx, eax
0x140005170  test    eax, eax
0x140005172  jns     short loc_1400051F3
0x140005174  mov     rcx, [rbp+0D8h]; this
0x14000517b  mov     dword ptr [rsp+1D0h+dwImpLevel], eax; wil::details *
0x14000517f  lea     rax, aPservicecurren_2; "pServiceCurrentPrompt->get_MessageText("...
0x140005186  mov     [rsp+1D0h+ppv], rax; char *
0x14000518b  lea     r9, aActiondialogma_1; "ActionDialogManager::HandlePromptSync"
0x140005192  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140005199  mov     edx, 85h; void *
0x14000519e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1400051a3  nop
0x1400051a4  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x1400051a8  call    cs:__imp_SysFreeString
0x1400051ae  nop
0x1400051af  mov     rcx, [rbp+0D0h+pbstr]; bstrString
0x1400051b3  call    cs:__imp_SysFreeString
0x1400051b9  nop
0x1400051ba  mov     rcx, [rbp+0D0h+var_138]
0x1400051be  test    rcx, rcx
0x1400051c1  jz      short loc_1400051D4
0x1400051c3  mov     [rbp+0D0h+var_138], rsi
0x1400051c7  mov     rax, [rcx]
0x1400051ca  mov     rax, [rax+10h]
0x1400051ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051d3  nop
0x1400051d4  mov     rcx, [rbp+0D0h+pProxy]
0x1400051d8  test    rcx, rcx
0x1400051db  jz      short loc_1400051EE
0x1400051dd  mov     [rbp+0D0h+pProxy], rsi
0x1400051e1  mov     rax, [rcx]
0x1400051e4  mov     rax, [rax+10h]
0x1400051e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ed  nop
0x1400051ee  jmp     loc_1400057D6
0x1400051f3  mov     rcx, [rbp+0D0h+var_138]
0x1400051f7  mov     rax, [rcx]
0x1400051fa  lea     rdx, [rbp+0D0h+var_140]
0x1400051fe  mov     rax, [rax+30h]
0x140005202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005207  mov     ebx, eax
0x140005209  test    eax, eax
0x14000520b  jns     short loc_14000528C
0x14000520d  mov     rcx, [rbp+0D8h]; this
0x140005214  mov     dword ptr [rsp+1D0h+dwImpLevel], eax; wil::details *
0x140005218  lea     rax, aPservicecurren; "pServiceCurrentPrompt->get_DialogMode(&"...
0x14000521f  mov     [rsp+1D0h+ppv], rax; char *
0x140005224  lea     r9, aActiondialogma_1; "ActionDialogManager::HandlePromptSync"
0x14000522b  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140005232  mov     edx, 86h; void *
0x140005237  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x14000523c  nop
0x14000523d  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x140005241  call    cs:__imp_SysFreeString
0x140005247  nop
0x140005248  mov     rcx, [rbp+0D0h+pbstr]; bstrString
0x14000524c  call    cs:__imp_SysFreeString
0x140005252  nop
0x140005253  mov     rcx, [rbp+0D0h+var_138]
0x140005257  test    rcx, rcx
0x14000525a  jz      short loc_14000526D
0x14000525c  mov     [rbp+0D0h+var_138], rsi
0x140005260  mov     rax, [rcx]
0x140005263  mov     rax, [rax+10h]
0x140005267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000526c  nop
0x14000526d  mov     rcx, [rbp+0D0h+pProxy]
0x140005271  test    rcx, rcx
0x140005274  jz      short loc_140005287
0x140005276  mov     [rbp+0D0h+pProxy], rsi
0x14000527a  mov     rax, [rcx]
0x14000527d  mov     rax, [rax+10h]
0x140005281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005286  nop
0x140005287  jmp     loc_1400057D6
0x14000528c  lea     rdx, [rsp+1D0h+hObject]; void **
0x140005291  mov     rcx, [rbp+0D0h+var_138]; struct IWindowsActionDialog *
0x140005295  call    ?GetSessionNotificationHandler@@YAJPEAUIWindowsActionDialog@@PEAPEAX@Z; GetSessionNotificationHandler(IWindowsActionDialog *,void * *)
0x14000529a  mov     ebx, eax
0x14000529c  test    eax, eax
0x14000529e  jns     loc_140005334
0x1400052a4  mov     rcx, [rbp+0D8h]; this
0x1400052ab  mov     dword ptr [rsp+1D0h+dwImpLevel], eax; wil::details *
0x1400052af  lea     rax, aGetsessionnoti; "GetSessionNotificationHandler(pServiceC"...
0x1400052b6  mov     [rsp+1D0h+ppv], rax; char *
0x1400052bb  lea     r9, aActiondialogma_1; "ActionDialogManager::HandlePromptSync"
0x1400052c2  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x1400052c9  mov     edx, 87h; void *
0x1400052ce  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1400052d3  nop
0x1400052d4  mov     rcx, [rsp+1D0h+hObject]; hObject
0x1400052d9  test    rcx, rcx
0x1400052dc  jz      short loc_1400052E5
0x1400052de  call    cs:__imp_CloseHandle
0x1400052e4  nop
0x1400052e5  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x1400052e9  call    cs:__imp_SysFreeString
0x1400052ef  nop
0x1400052f0  mov     rcx, [rbp+0D0h+pbstr]; bstrString
0x1400052f4  call    cs:__imp_SysFreeString
0x1400052fa  nop
0x1400052fb  mov     rcx, [rbp+0D0h+var_138]
0x1400052ff  test    rcx, rcx
0x140005302  jz      short loc_140005315
0x140005304  mov     [rbp+0D0h+var_138], rsi
0x140005308  mov     rax, [rcx]
0x14000530b  mov     rax, [rax+10h]
0x14000530f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005314  nop
0x140005315  mov     rcx, [rbp+0D0h+pProxy]
0x140005319  test    rcx, rcx
0x14000531c  jz      short loc_14000532F
0x14000531e  mov     [rbp+0D0h+pProxy], rsi
0x140005322  mov     rax, [rcx]
0x140005325  mov     rax, [rax+10h]
0x140005329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000532e  nop
0x14000532f  jmp     loc_1400057D6
0x140005334  mov     rcx, [rbp+0D0h+var_138]
0x140005338  mov     rax, [rcx]
0x14000533b  lea     rdx, [rbp+0D0h+var_118]
0x14000533f  mov     rax, [rax+38h]
0x140005343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005348  test    eax, eax
0x14000534a  jns     short loc_140005353
0x14000534c  mov     [rbp+0D0h+var_118], 7530h
0x140005353  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??HandlePromptSync@ActionDialogManager@@SAJPEAX@Z@J$$V@std@@6B@; const std::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync(void *)'::`2'::_lambda_1_,long,>::`vftable'
0x14000535a  mov     [rsp+1D0h+var_180], rax
0x14000535f  mov     [rsp+1D0h+var_178], rdi
0x140005364  lea     rax, [rsp+1D0h+var_180]
0x140005369  mov     [rbp+0D0h+var_148], rax
0x14000536d  lea     rax, [rsp+1D0h+var_180]
0x140005372  mov     [rsp+1D0h+var_188], rax
0x140005377  lea     rax, ??_7ResettableTimer@@6B@; const ResettableTimer::`vftable'
0x14000537e  mov     [rbp+0D0h+pv], rax
0x140005382  mov     [rbp+0D0h+var_B8], esi
0x140005385  mov     [rbp+0D0h+var_78], rsi
0x140005389  mov     [rbp+0D0h+var_70], rsi
0x14000538d  call    cs:__imp_GetTickCount64
0x140005393  sub     rax, 0EA60h
0x140005399  mov     [rbp+0D0h+var_68], rax
0x14000539d  mov     [rbp+0D0h+var_60], rsi
0x1400053a1  xor     r8d, r8d; Flags
0x1400053a4  xor     edx, edx; dwSpinCount
0x1400053a6  lea     rcx, [rbp+0D0h+CriticalSection]; lpCriticalSection
0x1400053aa  call    cs:__imp_InitializeCriticalSectionEx
0x1400053b0  nop
0x1400053b1  lea     rdx, [rsp+1D0h+var_180]
0x1400053b6  lea     rcx, [rbp+0D0h+var_B0]
0x1400053ba  call    ??4?$function@$$A6AJXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<long (void)>::operator=(std::function<long (void)> const &)
0x1400053bf  nop
0x1400053c0  mov     rcx, [rbp+0D0h+var_148]
0x1400053c4  test    rcx, rcx
0x1400053c7  jz      short loc_1400053E4
0x1400053c9  mov     rax, [rcx]
0x1400053cc  lea     rdx, [rsp+1D0h+var_180]
0x1400053d1  cmp     rcx, rdx
0x1400053d4  setnz   dl
0x1400053d7  mov     rax, [rax+20h]
0x1400053db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053e0  mov     [rbp+0D0h+var_148], rsi
0x1400053e4  mov     rcx, [rbp+0D0h+pbstr]; pbstr
0x1400053e8  call    cs:__imp_SysStringLen
0x1400053ee  mov     r8d, eax
0x1400053f1  mov     rdx, [rbp+0D0h+pbstr]
0x1400053f5  lea     rcx, [rbp+0D0h+var_E0]
0x1400053f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1400053fe  nop
0x1400053ff  mov     rcx, [rbp+0D0h+bstrString]; pbstr
  ... truncated ...
```

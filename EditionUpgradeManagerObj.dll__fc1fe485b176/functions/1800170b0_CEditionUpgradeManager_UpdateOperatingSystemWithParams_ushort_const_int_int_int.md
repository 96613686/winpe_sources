# CEditionUpgradeManager::UpdateOperatingSystemWithParams(ushort const *,int,int,int)

- ea: `0x1800170b0`
- end: `0x1800178d2`
- name: `?UpdateOperatingSystemWithParams@CEditionUpgradeManager@@UEAAJPEBGHHH@Z`
- size: `2082`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *__hidden this, const unsigned __int16 *, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x1800090dc`
- `0x180009480`
- `0x18000d10c`
- `0x18000d7b4`
- `0x18000dd2c`
- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`
- `0x180011e90`
- `0x180011fac`
- `0x1800166e8`
- `0x1800170b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017728`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017779`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017793`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017779`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017793`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001776b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017784`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001776b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b7`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017550`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017655`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017707`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017550`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017655`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180017707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001788d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001788d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800171ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800171ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800174ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800174ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001789b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001789b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800171bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800171bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800171a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001773c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800171a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001773c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001715a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001715a`
- `SHELL32!ShellExecuteExW` at `0x1800174aa`
- `SHELL32!ShellExecuteExW` at `0x1800174aa`
- `USER32!PostThreadMessageW` at `0x180017668`
- `USER32!PostThreadMessageW` at `0x18001771a`
- `USER32!PostThreadMessageW` at `0x180017668`
- `USER32!PostThreadMessageW` at `0x18001771a`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::UpdateOperatingSystemWithParams(
        CEditionUpgradeManager *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        int a5)
{
  HANDLE v7; // r14
  const WCHAR *v8; // r13
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  unsigned __int64 v12; // rdi
  UINT32 v13; // edx
  const WCHAR *v14; // rcx
  __int64 v15; // rcx
  HSTRING v16; // rdi
  int ActivationFactory; // eax
  signed int v18; // esi
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(__int64, HSTRING, __int64 *); // rsi
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rsi
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rdi
  __int64 v32; // rcx
  int appended; // eax
  void *v34; // rdi
  signed int LastError; // eax
  int v36; // r15d
  unsigned int v37; // edx
  struct _SECURITY_ATTRIBUTES *v38; // rcx
  unsigned int (*v39)(void *); // r8
  _QWORD *v40; // r9
  int v41; // eax
  int v42; // eax
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v45; // rcx
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 (__fastcall *v49)(__int64, HSTRING, __int64 *); // rdi
  int restarted; // eax
  DWORD v51; // eax
  __int64 v52; // rbx
  __int64 v53; // rcx
  __int64 (__fastcall *v54)(__int64, __int64 *); // rdi
  __int64 v55; // rdi
  DWORD ThreadId; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 (__fastcall ***v61)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  unsigned int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+28h] [rbp-D8h]
  unsigned int *v71; // [rsp+30h] [rbp-D0h]
  _BYTE v72[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v73; // [rsp+44h] [rbp-BCh] BYREF
  HSTRING v74; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v77; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v78; // [rsp+70h] [rbp-90h] BYREF
  __int64 v79; // [rsp+78h] [rbp-88h] BYREF
  int v80; // [rsp+80h] [rbp-80h] BYREF
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 v83; // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v87; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v88)(_QWORD, GUID *, __int64 *); // [rsp+C0h] [rbp-40h] BYREF
  int v89; // [rsp+C8h] [rbp-38h]
  HANDLE Thread; // [rsp+D0h] [rbp-30h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp+50h] BYREF
  HSTRING string; // [rsp+168h] [rbp+68h] BYREF

  v89 = a3;
  v76 = a4;
  Thread = 0;
  v77 = 0;
  v86 = 0;
  v79 = 0;
  v7 = 0;
  v85 = 0;
  v82 = 0;
  v8 = 0;
  v81 = 0;
  v88 = 0;
  v84 = 0;
  v83 = 0;
  v80 = 0;
  v73 = 0;
  v72[0] = 0;
  v87 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.System.Licensing.LicensingPolicyManager", 0x2Fu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x1800178D1LL);
  }
  v74 = 0;
  v78 = 0;
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    if ( v12 > 0xFFFFFFFF )
      goto LABEL_9;
    WindowsDeleteString(0);
    v13 = v12;
    v14 = a2;
  }
  else
  {
    WindowsDeleteString(0);
    v13 = 0;
    v14 = &LocaleName;
  }
  v74 = 0;
  WindowsCreateString(v14, v13, &v74);
LABEL_9:
  v15 = v77;
  v16 = string;
  if ( v77 )
  {
    v77 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  ActivationFactory = RoGetActivationFactory(v16, &GUID_65d46056_2e54_4b8f_88a5_ac12065e1fb2, &v77);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  v20 = v77;
  v21 = v86;
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v77 + 48LL);
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  ActivationFactory = v22(v20, v74, &v86);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  v23 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v86;
  v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(v86);
  if ( v18 < 0 )
    goto LABEL_21;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 64LL))(v24, &v79);
  if ( v18 < 0 )
    goto LABEL_21;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v79 + 112LL))(v79, &v73);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  v18 = v73;
  if ( v73 < 0 )
    goto LABEL_21;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v79 + 64LL))(v79, v72);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  if ( !v72[0] )
    goto LABEL_38;
  v25 = v77;
  v26 = v85;
  v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v77 + 64LL);
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  ActivationFactory = v27(v25, v74, &v85);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  v28 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v85;
  v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(v85);
  if ( v18 < 0 )
    goto LABEL_21;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 64LL))(v29, &v82);
  if ( v18 < 0 )
    goto LABEL_21;
  v30 = v82;
  v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v82 + 48LL);
  WindowsDeleteString(v78);
  v78 = 0;
  ActivationFactory = v31(v30, &v78);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
LABEL_12:
    v19 = (unsigned int)ActivationFactory;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
LABEL_89:
    v34 = lpMem[0];
    goto LABEL_90;
  }
  if ( !v78 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v82 + 64LL))(v82, &v73);
    v18 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v18 = v73;
      if ( v73 >= 0 )
        goto LABEL_37;
LABEL_21:
      v19 = (unsigned int)v18;
      goto LABEL_13;
    }
    goto LABEL_12;
  }
LABEL_37:
  WindowsDeleteString(v74);
  v74 = v78;
  v78 = 0;
LABEL_38:
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v79 + 48LL))(v79, &v80);
  v18 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_12;
  if ( v80 != 1 )
  {
    v36 = v76;
    goto LABEL_66;
  }
  if ( !a5 )
  {
    v36 = v76;
    if ( v76 )
    {
      v40 = LocalAlloc(0x40u, 0x10u);
      if ( !v40 )
      {
        v19 = 2147942414LL;
        v18 = -2147024882;
        goto LABEL_13;
      }
      v40[1] = *((_QWORD *)this + 1);
      v41 = SafeThreadCreateEx(v38, v37, v39, v40, v69, v70, v71, &Thread);
      v18 = v41;
      if ( v41 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v41);
        v7 = Thread;
LABEL_86:
        if ( v7 && v18 < 0 )
        {
          ThreadId = GetThreadId(v7);
          PostThreadMessageW(ThreadId, 0x1114u, v18, 0);
          WaitForSingleObject(v7, 0xFFFFFFFF);
        }
        goto LABEL_89;
      }
      v7 = Thread;
      v76 = GetThreadId(Thread);
      v42 = Microsoft::WRL::Details::MakeAndInitialize<ProgressHandler,ProgressHandler,unsigned long>(&v88, &v76);
      v18 = v42;
      if ( v42 < 0 )
        goto LABEL_57;
      v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
      if ( !v88 )
      {
        v43 = 2147942414LL;
        v18 = -2147024882;
        goto LABEL_58;
      }
      v45 = v84;
      v46 = **v88;
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      }
      v42 = v46(v44, &GUID_44825c7c_0da9_5691_b2b4_914f231eeced, &v84);
      v18 = v42;
      if ( v42 < 0 )
      {
LABEL_57:
        v43 = (unsigned int)v42;
LABEL_58:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v43);
        goto LABEL_86;
      }
    }
LABEL_66:
    v47 = v77;
    v48 = v81;
    v49 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v77 + 56LL);
    if ( v81 )
    {
      v81 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    restarted = v49(v47, v74, &v81);
    v18 = restarted;
    if ( restarted >= 0 )
    {
      if ( !v84
        || (restarted = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 48LL))(v81),
            v18 = restarted,
            restarted >= 0) )
      {
        restarted = wil::details::WaitForCompletion<Windows::Foundation::IAsyncActionWithProgress<double> *>(v81);
        v18 = restarted;
        if ( restarted >= 0 )
        {
          if ( v7 )
          {
            v51 = GetThreadId(v7);
            PostThreadMessageW(v51, 0x1129u, 0, 0);
          }
          if ( v80 == 1 && v89 )
          {
            restarted = ChangePKHelper::RestartSystem(v36);
            v18 = restarted;
            if ( restarted >= 0 )
              goto LABEL_86;
          }
          else
          {
            if ( v80 )
              goto LABEL_86;
            v52 = v77;
            v53 = v83;
            v54 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v77 + 72LL);
            if ( v83 )
            {
              v83 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
            }
            restarted = v54(v52, &v83);
            v18 = restarted;
            if ( restarted >= 0 )
            {
              v55 = v83;
              if ( (int)wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>(v83) >= 0 )
                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 64LL))(v55, &v73);
              goto LABEL_86;
            }
          }
        }
      }
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)restarted);
    goto LABEL_86;
  }
  appended = CMiscHelpersT<CEmptyType>::AppendToSystemPath(v32, &v87);
  v18 = appended;
  if ( appended < 0
    || (appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
                     lpMem,
                     L"/ProductKey %s /ParentWindowHandle 0x%x",
                     a2,
                     *((unsigned int *)this + 2)),
        v18 = appended,
        appended < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)appended);
    v8 = v87;
    goto LABEL_89;
  }
  v8 = v87;
  v34 = lpMem[0];
  pExecInfo.lpVerb = L"Open";
  pExecInfo.hwnd = (HWND)*((_QWORD *)this + 1);
  pExecInfo.cbSize = 112;
  pExecInfo.lpFile = v87;
  pExecInfo.lpParameters = (LPCWSTR)lpMem[0];
  pExecInfo.fMask = 64;
  pExecInfo.nShow = 1;
  if ( ShellExecuteExW(&pExecInfo) )
  {
    v18 = 0;
  }
  else
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v18 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
  }
LABEL_90:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v18);
  WindowsDeleteString(0);
  WindowsDeleteString(v78);
  v78 = 0;
  WindowsDeleteString(v74);
  v74 = 0;
  string = 0;
  if ( v34 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v34);
  }
  if ( v8 )
  {
    v58 = GetProcessHeap();
    HeapFree(v58, 0, (LPVOID)(v8 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v59 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  v60 = v84;
  if ( v84 )
  {
    v84 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  v61 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
  if ( v88 )
  {
    v88 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v61)[2])(v61);
  }
  v62 = v81;
  if ( v81 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  }
  v63 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  }
  v64 = v85;
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  v65 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  }
  v66 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  v67 = v77;
  if ( v77 )
  {
    v77 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  }
  if ( v7 )
    CloseHandle(v7);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800170b0  mov     [rsp-8+arg_10], rbx
0x1800170b5  push    rbp
0x1800170b6  push    rsi
0x1800170b7  push    rdi
0x1800170b8  push    r12
0x1800170ba  push    r13
0x1800170bc  push    r14
0x1800170be  push    r15
0x1800170c0  lea     rbp, [rsp-80h]
0x1800170c5  sub     rsp, 180h
0x1800170cc  mov     rax, cs:__security_cookie
0x1800170d3  xor     rax, rsp
0x1800170d6  mov     [rbp+0B0h+var_40], rax
0x1800170da  xor     esi, esi
0x1800170dc  mov     [rbp+0B0h+var_E8], r8d
0x1800170e0  mov     r15, rdx
0x1800170e3  mov     [rsp+1B0h+var_150], r9d
0x1800170e8  mov     r12, rcx
0x1800170eb  mov     [rbp+0B0h+Thread], rsi
0x1800170ef  xor     edx, edx; Val
0x1800170f1  mov     [rsp+1B0h+var_148], rsi
0x1800170f6  lea     r8d, [rsi+70h]; Size
0x1800170fa  mov     [rbp+0B0h+var_100], rsi
0x1800170fe  lea     rcx, [rbp+0B0h+pExecInfo]; void *
0x180017102  mov     [rsp+1B0h+var_138], rsi
0x180017107  mov     r14d, esi
0x18001710a  mov     [rbp+0B0h+var_108], rsi
0x18001710e  mov     [rbp+0B0h+var_120], rsi
0x180017112  mov     r13d, esi
0x180017115  mov     [rbp+0B0h+var_128], rsi
0x180017119  mov     [rbp+0B0h+var_F0], rsi
0x18001711d  mov     [rbp+0B0h+var_110], rsi
0x180017121  mov     [rbp+0B0h+var_118], rsi
0x180017125  mov     [rbp+0B0h+var_130], esi
0x180017128  mov     [rsp+1B0h+var_16C], esi
0x18001712c  mov     [rsp+1B0h+var_170], sil
0x180017131  mov     [rbp+0B0h+var_F8], rsi
0x180017135  mov     [rsp+1B0h+lpMem], rsi
0x18001713a  mov     [rsp+1B0h+var_158], rsi
0x18001713f  call    memset_0
0x180017144  lea     r9, [rbp+0B0h+string]; string
0x180017148  mov     [rbp+0B0h+string], rsi
0x18001714c  lea     r8, [rbp+0B0h+hstringHeader]; hstringHeader
0x180017150  lea     edx, [rsi+2Fh]; length
0x180017153  lea     rcx, ?RuntimeClass_Windows_System_Licensing_LicensingPolicyManager@@3QBGB; "Windows.System.Licensing.LicensingPolic"...
0x18001715a  call    cs:__imp_WindowsCreateStringReference
0x180017160  test    eax, eax
0x180017162  js      loc_1800178CA
0x180017168  mov     [rsp+1B0h+var_168], rsi
0x18001716d  mov     ebx, esi
0x18001716f  mov     [rsp+1B0h+var_140], rsi
0x180017174  mov     eax, 0FFFFFFFFh
0x180017179  test    r15, r15
0x18001717c  jz      short loc_1800171A0
0x18001717e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017182  inc     rdi
0x180017185  cmp     [r15+rdi*2], si
0x18001718a  jnz     short loc_180017182
0x18001718c  cmp     rdi, rax
0x18001718f  ja      short loc_1800171C1
0x180017191  xor     ecx, ecx; string
0x180017193  call    cs:__imp_WindowsDeleteString
0x180017199  mov     edx, edi
0x18001719b  mov     rcx, r15
0x18001719e  jmp     short loc_1800171B1
0x1800171a0  xor     ecx, ecx; string
0x1800171a2  call    cs:__imp_WindowsDeleteString
0x1800171a8  xor     edx, edx; length
0x1800171aa  lea     rcx, LocaleName; sourceString
0x1800171b1  lea     r8, [rsp+1B0h+var_168]; string
0x1800171b6  mov     [rsp+1B0h+var_168], rsi
0x1800171bb  call    cs:__imp_WindowsCreateString
0x1800171c1  mov     rcx, [rsp+1B0h+var_148]
0x1800171c6  mov     rdi, [rbp+0B0h+string]
0x1800171ca  test    rcx, rcx
0x1800171cd  jz      short loc_1800171E0
0x1800171cf  mov     [rsp+1B0h+var_148], rsi
0x1800171d4  mov     rax, [rcx]
0x1800171d7  mov     rax, [rax+10h]
0x1800171db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e0  lea     r8, [rsp+1B0h+var_148]
0x1800171e5  mov     rcx, rdi
0x1800171e8  lea     rdx, _GUID_65d46056_2e54_4b8f_88a5_ac12065e1fb2
0x1800171ef  call    cs:__imp_RoGetActivationFactory
0x1800171f5  mov     esi, eax
0x1800171f7  test    eax, eax
0x1800171f9  jns     short loc_18001720A
0x1800171fb  mov     ecx, eax
0x1800171fd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017202  xor     r12d, r12d
0x180017205  jmp     loc_18001772E
0x18001720a  mov     rdi, [rsp+1B0h+var_148]
0x18001720f  mov     rcx, [rbp+0B0h+var_100]
0x180017213  mov     rax, [rdi]
0x180017216  mov     rsi, [rax+30h]
0x18001721a  test    rcx, rcx
0x18001721d  jz      short loc_18001722F
0x18001721f  mov     [rbp+0B0h+var_100], rbx
0x180017223  mov     rdx, [rcx]
0x180017226  mov     rax, [rdx+10h]
0x18001722a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722f  mov     rdx, [rsp+1B0h+var_168]
0x180017234  lea     r8, [rbp+0B0h+var_100]
0x180017238  mov     rcx, rdi
0x18001723b  mov     rax, rsi
0x18001723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017243  mov     esi, eax
0x180017245  test    eax, eax
0x180017247  js      short loc_1800171FB
0x180017249  mov     rcx, [rsp+1B0h+var_138]
0x18001724e  test    rcx, rcx
0x180017251  jz      short loc_180017264
0x180017253  mov     [rsp+1B0h+var_138], rbx
0x180017258  mov     rax, [rcx]
0x18001725b  mov     rax, [rax+10h]
0x18001725f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017264  mov     rdi, [rbp+0B0h+var_100]
0x180017268  mov     rcx, rdi
0x18001726b  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyProperties@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyProperties *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180017270  mov     esi, eax
0x180017272  test    eax, eax
0x180017274  js      short loc_180017290
0x180017276  mov     rax, [rdi]
0x180017279  lea     rdx, [rsp+1B0h+var_138]
0x18001727e  mov     rcx, rdi
0x180017281  mov     rax, [rax+40h]
0x180017285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001728a  mov     esi, eax
0x18001728c  test    eax, eax
0x18001728e  jns     short loc_180017297
0x180017290  mov     ecx, esi
0x180017292  jmp     loc_1800171FD
0x180017297  mov     rcx, [rsp+1B0h+var_138]
0x18001729c  lea     rdx, [rsp+1B0h+var_16C]
0x1800172a1  mov     rax, [rcx]
0x1800172a4  mov     rax, [rax+70h]
0x1800172a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ad  mov     esi, eax
0x1800172af  test    eax, eax
0x1800172b1  js      loc_1800171FB
0x1800172b7  mov     esi, [rsp+1B0h+var_16C]
0x1800172bb  test    esi, esi
0x1800172bd  js      short loc_180017290
0x1800172bf  mov     rcx, [rsp+1B0h+var_138]
0x1800172c4  lea     rdx, [rsp+1B0h+var_170]
0x1800172c9  mov     rax, [rcx]
0x1800172cc  mov     rax, [rax+40h]
0x1800172d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172d5  mov     esi, eax
0x1800172d7  test    eax, eax
0x1800172d9  js      loc_1800171FB
0x1800172df  cmp     [rsp+1B0h+var_170], bl
0x1800172e3  jz      loc_1800173F9
0x1800172e9  mov     rdi, [rsp+1B0h+var_148]
0x1800172ee  mov     rcx, [rbp+0B0h+var_108]
0x1800172f2  mov     rax, [rdi]
0x1800172f5  mov     rsi, [rax+40h]
0x1800172f9  test    rcx, rcx
0x1800172fc  jz      short loc_18001730E
0x1800172fe  mov     [rbp+0B0h+var_108], rbx
0x180017302  mov     rdx, [rcx]
0x180017305  mov     rax, [rdx+10h]
0x180017309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001730e  mov     rdx, [rsp+1B0h+var_168]
0x180017313  lea     r8, [rbp+0B0h+var_108]
0x180017317  mov     rcx, rdi
0x18001731a  mov     rax, rsi
0x18001731d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017322  mov     esi, eax
0x180017324  test    eax, eax
0x180017326  js      loc_1800171FB
0x18001732c  mov     rcx, [rbp+0B0h+var_120]
0x180017330  test    rcx, rcx
0x180017333  jz      short loc_180017345
0x180017335  mov     [rbp+0B0h+var_120], rbx
0x180017339  mov     rax, [rcx]
0x18001733c  mov     rax, [rax+10h]
0x180017340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017345  mov     rdi, [rbp+0B0h+var_108]
0x180017349  mov     rcx, rdi
0x18001734c  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *>(Windows::Foundation::IAsyncOperation<Windows::System::Licensing::ProductKeyRedemptionResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180017351  mov     esi, eax
0x180017353  test    eax, eax
0x180017355  js      loc_180017290
0x18001735b  mov     rax, [rdi]
0x18001735e  lea     rdx, [rbp+0B0h+var_120]
0x180017362  mov     rcx, rdi
0x180017365  mov     rax, [rax+40h]
0x180017369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001736e  mov     esi, eax
0x180017370  test    eax, eax
0x180017372  js      loc_180017290
0x180017378  mov     rsi, [rbp+0B0h+var_120]
0x18001737c  mov     rcx, [rsp+1B0h+var_140]; string
0x180017381  mov     rax, [rsi]
0x180017384  mov     rdi, [rax+30h]
0x180017388  call    cs:__imp_WindowsDeleteString
0x18001738e  lea     rdx, [rsp+1B0h+var_140]
0x180017393  mov     [rsp+1B0h+var_140], rbx
0x180017398  mov     rcx, rsi
0x18001739b  mov     rax, rdi
0x18001739e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173a3  mov     esi, eax
0x1800173a5  test    eax, eax
0x1800173a7  js      loc_1800171FB
0x1800173ad  cmp     [rsp+1B0h+var_140], rbx
0x1800173b2  jnz     short loc_1800173DF
0x1800173b4  mov     rcx, [rbp+0B0h+var_120]
0x1800173b8  lea     rdx, [rsp+1B0h+var_16C]
0x1800173bd  mov     rax, [rcx]
0x1800173c0  mov     rax, [rax+40h]
0x1800173c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173c9  mov     esi, eax
0x1800173cb  test    eax, eax
0x1800173cd  js      loc_1800171FB
0x1800173d3  mov     esi, [rsp+1B0h+var_16C]
0x1800173d7  test    esi, esi
0x1800173d9  js      loc_180017290
0x1800173df  mov     rcx, [rsp+1B0h+var_168]; string
0x1800173e4  call    cs:__imp_WindowsDeleteString
0x1800173ea  mov     rax, [rsp+1B0h+var_140]
0x1800173ef  mov     [rsp+1B0h+var_168], rax
0x1800173f4  mov     [rsp+1B0h+var_140], rbx
0x1800173f9  mov     rcx, [rsp+1B0h+var_138]
0x1800173fe  lea     rdx, [rbp+0B0h+var_130]
0x180017402  mov     rax, [rcx]
0x180017405  mov     rax, [rax+30h]
0x180017409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001740e  mov     esi, eax
0x180017410  test    eax, eax
0x180017412  js      loc_1800171FB
0x180017418  cmp     [rbp+0B0h+var_130], 1
0x18001741c  jnz     loc_1800175C9
0x180017422  cmp     [rbp+0B0h+arg_20], ebx
0x180017428  jz      loc_1800174E9
0x18001742e  lea     rdx, [rbp+0B0h+var_F8]
0x180017432  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x180017437  mov     esi, eax
0x180017439  test    eax, eax
0x18001743b  jns     short loc_18001744D
0x18001743d  mov     ecx, eax
0x18001743f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017444  mov     r13, [rbp+0B0h+var_F8]
0x180017448  jmp     loc_180017202
0x18001744d  mov     r9d, [r12+8]
0x180017452  lea     rdx, aProductkeySPar; "/ProductKey %s /ParentWindowHandle 0x%x"
0x180017459  mov     r8, r15
0x18001745c  lea     rcx, [rsp+1B0h+lpMem]
0x180017461  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180017466  mov     esi, eax
0x180017468  test    eax, eax
0x18001746a  js      short loc_18001743D
0x18001746c  mov     r13, [rbp+0B0h+var_F8]
0x180017470  lea     rax, aOpen; "Open"
0x180017477  mov     rdi, [rsp+1B0h+lpMem]
0x18001747c  lea     rcx, [rbp+0B0h+pExecInfo]; pExecInfo
0x180017480  mov     [rbp+0B0h+pExecInfo.lpVerb], rax
0x180017484  mov     rax, [r12+8]
0x180017489  mov     [rbp+0B0h+pExecInfo.hwnd], rax
0x18001748d  mov     [rbp+0B0h+pExecInfo.cbSize], 70h ; 'p'
0x180017494  mov     [rbp+0B0h+pExecInfo.lpFile], r13
0x180017498  mov     [rbp+0B0h+pExecInfo.lpParameters], rdi
0x18001749c  mov     [rbp+0B0h+pExecInfo.fMask], 40h ; '@'
0x1800174a3  mov     [rbp+0B0h+pExecInfo.nShow], 1
0x1800174aa  call    cs:__imp_ShellExecuteExW
0x1800174b0  xor     r12d, r12d
0x1800174b3  test    eax, eax
0x1800174b5  jnz     short loc_1800174E1
0x1800174b7  call    cs:__imp_GetLastError
0x1800174bd  mov     esi, eax
0x1800174bf  test    eax, eax
0x1800174c1  jnz     short loc_1800174CA
0x1800174c3  mov     esi, 80004005h
0x1800174c8  jmp     short loc_1800174D5
0x1800174ca  jle     short loc_1800174D5
0x1800174cc  movzx   esi, ax
0x1800174cf  or      esi, 80070000h
0x1800174d5  mov     ecx, esi
0x1800174d7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800174dc  jmp     loc_180017733
0x1800174e1  mov     esi, r12d
0x1800174e4  jmp     loc_180017733
0x1800174e9  mov     r15d, [rsp+1B0h+var_150]
0x1800174ee  test    r15d, r15d
0x1800174f1  jz      loc_1800175CE
0x1800174f7  mov     edx, 10h; uBytes
0x1800174fc  lea     ecx, [rdx+30h]; uFlags
0x1800174ff  call    cs:__imp_LocalAlloc
0x180017505  mov     r9, rax; void *
0x180017508  test    rax, rax
0x18001750b  jnz     short loc_180017519
0x18001750d  mov     ecx, 8007000Eh
0x180017512  mov     esi, ecx
0x180017514  jmp     loc_1800171FD
0x180017519  mov     rax, [r12+8]
0x18001751e  xor     r12d, r12d
0x180017521  mov     [r9+8], rax
0x180017525  lea     rax, [rbp+0B0h+Thread]
0x180017529  mov     [rsp+1B0h+var_178], rax; void **
0x18001752e  call    ?SafeThreadCreateEx@@YAJPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KHPEAKPEAPEAX@Z; SafeThreadCreateEx(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,int,ulong *,void * *)
  ... truncated ...
```

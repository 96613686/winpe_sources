# CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18001597c`
- end: `0x18001605c`
- name: `?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z`
- size: `1760`
- prototype: `int __high(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, enum Windows::Internal::Shell::Experience::ShellExperienceViewState, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013960`
- `0x1800146a0`
- `0x180014b34`
- `0x180014ddc`
- `0x1800152f0`
- `0x1800a1ab0`
- `0x1800c134c`

## callees

- `0x180009dfc`
- `0x18001597c`
- `0x180016064`
- `0x180016078`
- `0x18001608c`
- `0x180016150`
- `0x18001743c`
- `0x18001bbdc`
- `0x1800378dc`
- `0x180037b9c`
- `0x1800eefa4`
- `0x180142e34`
- `0x180151494`
- `0x180151514`
- `0x180151eb4`
- `0x180152010`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800159ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800159ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800159b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001601a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800159b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015b02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001601a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015ea4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180015d50`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180015d50`

## string_xrefs

- `0x180015e8d`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015f22`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015f68`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015f85`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015fa7`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015fcb`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180016004`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CShellExperienceDispatcher::_NotifyListener(__int64 a1, __int64 a2, int a3, HSTRING a4, __int64 a5)
{
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rax
  __int64 v18; // rdi
  HRESULT v19; // eax
  HRESULT v20; // edi
  _QWORD *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // r8
  _QWORD *v25; // rax
  __int64 v26; // rdi
  CShellExperienceViewStateChangedEventArgs *v27; // rax
  CShellExperienceViewStateChangedEventArgs *v28; // rdi
  __int64 v29; // rcx
  HSTRING *v30; // rsi
  HRESULT v31; // eax
  unsigned int v32; // esi
  __int64 v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rdi
  char *v36; // r15
  __int64 v37; // r14
  unsigned int v38; // r12d
  _QWORD *v39; // rax
  _QWORD *v40; // rsi
  char *v41; // rcx
  int v43; // eax
  int v44; // eax
  char *v45; // rcx
  int v46; // [rsp+20h] [rbp-61h]
  int v47; // [rsp+20h] [rbp-61h]
  char *v48; // [rsp+30h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-49h] BYREF
  __int64 v50; // [rsp+40h] [rbp-41h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-39h] BYREF
  HSTRING string; // [rsp+50h] [rbp-31h] BYREF
  __int64 v53; // [rsp+58h] [rbp-29h] BYREF
  char *v54; // [rsp+60h] [rbp-21h] BYREF
  __int64 v55; // [rsp+68h] [rbp-19h] BYREF
  __int64 v56; // [rsp+70h] [rbp-11h] BYREF
  _QWORD v57[10]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]
  __int64 v59; // [rsp+E8h] [rbp+67h] BYREF

  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a2, &string);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v10,
      v46);
    goto LABEL_48;
  }
  v12 = 0;
  v50 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 304));
  v53 = a1 + 304;
  v13 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                    a1 + 240,
                    &StringRawBuffer);
  v15 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                    v14,
                    &v48,
                    *v13);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(
    &v59,
    *v15,
    v16,
    a2);
  v17 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                    a1 + 240,
                    &StringRawBuffer);
  v18 = v59;
  if ( v59 == *v17 )
  {
    v11 = -2147319765;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)0x8002802BLL,
      v46);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v53);
    goto LABEL_65;
  }
  if ( *(_QWORD *)(v59 + 8) )
  {
    newString = 0;
    WindowsDeleteString(0);
    newString = 0;
    v19 = WindowsDuplicateString(*(HSTRING *)(v18 + 8), &newString);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x265,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v19,
        v46);
      WindowsDeleteString(newString);
      newString = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v11 = v20;
      goto LABEL_48;
    }
    v21 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      a1 + 216,
                      &StringRawBuffer);
    v23 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                      v22,
                      &v48,
                      *v21);
    v57[0] = &string;
    v57[1] = &newString;
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceListener_______lambda_753e7ef3057604c3fc660ce988ace198___(
      &v59,
      *v23,
      v24,
      v57);
    v25 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      a1 + 216,
                      &StringRawBuffer);
    if ( v59 == *v25 )
    {
      LODWORD(v59) = 0;
      v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v59);
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v43,
          v46);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LODWORD(v48) = a3;
      ShellExperienceDispatcherTelemetry::NotificationDroppedBecauseNoListenerFound<unsigned int,unsigned int &,unsigned short const *>(
        &v48,
        &v59,
        &StringRawBuffer);
    }
    else
    {
      v26 = *(_QWORD *)(v59 + 16);
      if ( v26 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 8LL))(*(_QWORD *)(v59 + 16));
        v12 = v26;
        v50 = v26;
      }
    }
    WindowsDeleteString(newString);
    newString = 0;
    if ( a1 != -304 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 304));
    if ( !v12 )
      goto LABEL_47;
    v48 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v48 = 0;
    v27 = (CShellExperienceViewStateChangedEventArgs *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
    if ( v27 )
    {
      v28 = CShellExperienceViewStateChangedEventArgs::CShellExperienceViewStateChangedEventArgs(v27);
      v59 = 0;
      if ( *((_QWORD *)v28 + 9) != a2 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
        v29 = *((_QWORD *)v28 + 9);
        *((_QWORD *)v28 + 9) = a2;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      *((_DWORD *)v28 + 24) = a3;
      v30 = (HSTRING *)((char *)v28 + 88);
      if ( a4 && a4 == *v30
        || (WindowsDeleteString(*v30),
            *v30 = 0,
            v31 = WindowsDuplicateString(a4, (HSTRING *)v28 + 11),
            v32 = v31,
            v31 >= 0) )
      {
        v33 = a5;
        if ( *((_QWORD *)v28 + 10) != a5 )
        {
          if ( a5 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
          v34 = *((_QWORD *)v28 + 10);
          *((_QWORD *)v28 + 10) = v33;
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v48 = (char *)v28 + 48;
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v28 + 6) + 8LL))((__int64)v28 + 48);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(v28);
        v35 = (a1 + 160) & -(__int64)(a1 != 0);
        v59 = v35;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))((a1 + 160) & -(__int64)(a1 != 0));
        v36 = v48;
        v54 = v48;
        if ( v48 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 8LL))(v48);
        v55 = v12;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        v37 = (a1 + 160) & -(__int64)(a1 != 0);
        v56 = v37;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))((a1 + 160) & -(__int64)(a1 != 0));
        v38 = *(_DWORD *)(a1 + 312);
        v39 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
        v40 = v39;
        if ( v39 )
        {
          Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v39);
          v40[2] = 0;
          if ( v40 + 2 != &v54 )
          {
            v40[2] = v36;
            v54 = 0;
          }
          v40[3] = 0;
          if ( v40 + 3 != &v55 )
          {
            v40[3] = v12;
            v55 = 0;
          }
          v40[4] = 0;
          if ( v40 + 4 != &v56 )
          {
            v40[4] = v35;
            v37 = 0;
            v56 = 0;
          }
          *v40 = off_1803BC0F0;
        }
        else
        {
          v40 = 0;
        }
        v11 = SHTaskPoolQueueTask(3, 2, v38, 0, v40, 0);
        if ( v40 )
          (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
        if ( v37 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        if ( v54 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v54 + 16LL))(v54);
        if ( v11 >= 0 )
        {
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))((a1 + 160) & -(__int64)(a1 != 0));
          v41 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))(v41);
          }
LABEL_47:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v11 = 0;
          goto LABEL_48;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v11,
          v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_65:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        goto LABEL_48;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\ShellExperienceViewStateChangedEventArgs.h",
        (const char *)(unsigned int)v31,
        v46);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(v28);
      Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(&v59);
    }
    else
    {
      v32 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v32,
      v46);
    v45 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v45 + 16LL))(v45);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v11 = v32;
  }
  else
  {
    LODWORD(v59) = 0;
    v44 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v59);
    if ( v44 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v44,
        v46);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LODWORD(v48) = a3;
    ShellExperienceDispatcherTelemetry::NotificationDroppedDueToNoExperienceSet<unsigned int,unsigned int &,unsigned short const *>(
      &v48,
      &v59,
      &StringRawBuffer);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v11 = 0;
  }
LABEL_48:
  WindowsDeleteString(string);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001597c  push    rbp
0x18001597e  push    rbx
0x18001597f  push    rsi
0x180015980  push    rdi
0x180015981  push    r12
0x180015983  push    r13
0x180015985  push    r14
0x180015987  push    r15
0x180015989  lea     rbp, [rsp-17h]
0x18001598e  sub     rsp, 98h
0x180015995  mov     r14, r9
0x180015998  mov     r12d, r8d
0x18001599b  mov     rsi, rdx
0x18001599e  mov     r13, rcx
0x1800159a1  mov     [rbp+4Fh+string], 0
0x1800159a9  mov     rax, [rdx]
0x1800159ac  mov     rbx, [rax+38h]
0x1800159b0  xor     ecx, ecx; string
0x1800159b2  call    cs:__imp_WindowsDeleteString
0x1800159b9  nop     dword ptr [rax+rax+00h]
0x1800159be  mov     [rbp+4Fh+string], 0
0x1800159c6  lea     rdx, [rbp+4Fh+string]
0x1800159ca  mov     rcx, rsi
0x1800159cd  mov     rax, rbx
0x1800159d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159d5  mov     ebx, eax
0x1800159d7  test    eax, eax
0x1800159d9  js      loc_180015F7E
0x1800159df  xor     ebx, ebx
0x1800159e1  mov     [rbp+4Fh+var_90], rbx
0x1800159e5  lea     r15, [r13+130h]
0x1800159ec  mov     rcx, r15; SRWLock
0x1800159ef  call    cs:__imp_AcquireSRWLockShared
0x1800159f6  nop     dword ptr [rax+rax+00h]
0x1800159fb  mov     [rbp+4Fh+var_78], r15
0x1800159ff  lea     rdi, [r13+0F0h]
0x180015a06  lea     rdx, [rbp+4Fh+var_88]
0x180015a0a  mov     rcx, rdi
0x180015a0d  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180015a12  mov     r8, [rax]
0x180015a15  lea     rdx, [rbp+4Fh+var_A0]
0x180015a19  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180015a1e  mov     r9, rsi
0x180015a21  mov     rdx, [rax]
0x180015a24  lea     rcx, [rbp+4Fh+arg_8]
0x180015a28  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByView@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByView@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView)
0x180015a2d  lea     rdx, [rbp+4Fh+var_88]
0x180015a31  mov     rcx, rdi
0x180015a34  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180015a39  mov     rdi, [rbp+4Fh+arg_8]
0x180015a3d  cmp     rdi, [rax]
0x180015a40  jz      loc_180015F9B
0x180015a46  xor     eax, eax
0x180015a48  cmp     [rdi+8], rax
0x180015a4c  jz      loc_180015E6C
0x180015a52  mov     [rbp+4Fh+newString], rax
0x180015a56  xor     ecx, ecx; string
0x180015a58  call    cs:__imp_WindowsDeleteString
0x180015a5f  nop     dword ptr [rax+rax+00h]
0x180015a64  mov     [rbp+4Fh+newString], rbx
0x180015a68  lea     rdx, [rbp+4Fh+newString]; newString
0x180015a6c  mov     rcx, [rdi+8]; string
0x180015a70  call    cs:__imp_WindowsDuplicateString
0x180015a77  nop     dword ptr [rax+rax+00h]
0x180015a7c  mov     edi, eax
0x180015a7e  test    eax, eax
0x180015a80  js      loc_180015FFD
0x180015a86  lea     rdi, [r13+0D8h]
0x180015a8d  lea     rdx, [rbp+4Fh+var_88]
0x180015a91  mov     rcx, rdi
0x180015a94  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180015a99  mov     r8, [rax]
0x180015a9c  lea     rdx, [rbp+4Fh+var_A0]
0x180015aa0  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180015aa5  lea     rcx, [rbp+4Fh+string]
0x180015aa9  mov     [rbp+4Fh+var_50], rcx
0x180015aad  lea     rcx, [rbp+4Fh+newString]
0x180015ab1  mov     [rbp+4Fh+var_48], rcx
0x180015ab5  lea     r9, [rbp+4Fh+var_50]
0x180015ab9  mov     rdx, [rax]
0x180015abc  lea     rcx, [rbp+4Fh+arg_8]
0x180015ac0  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceListener_______lambda_753e7ef3057604c3fc660ce988ace198___
0x180015ac5  lea     rdx, [rbp+4Fh+var_88]
0x180015ac9  mov     rcx, rdi
0x180015acc  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180015ad1  mov     rcx, [rbp+4Fh+arg_8]
0x180015ad5  cmp     rcx, [rax]
0x180015ad8  jz      loc_180015E16
0x180015ade  mov     rdi, [rcx+10h]
0x180015ae2  test    rdi, rdi
0x180015ae5  jz      short loc_180015AFE
0x180015ae7  mov     rax, [rdi]
0x180015aea  mov     rcx, rdi
0x180015aed  mov     rax, [rax+8]
0x180015af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af6  nop
0x180015af7  mov     rbx, rdi
0x180015afa  mov     [rbp+4Fh+var_90], rbx
0x180015afe  mov     rcx, [rbp+4Fh+newString]; string
0x180015b02  call    cs:__imp_WindowsDeleteString
0x180015b09  nop     dword ptr [rax+rax+00h]
0x180015b0e  mov     [rbp+4Fh+newString], 0
0x180015b16  test    r15, r15
0x180015b19  jz      short loc_180015B2A
0x180015b1b  mov     rcx, r15; SRWLock
0x180015b1e  call    cs:__imp_ReleaseSRWLockShared
0x180015b25  nop     dword ptr [rax+rax+00h]
0x180015b2a  xor     r15d, r15d
0x180015b2d  test    rbx, rbx
0x180015b30  jz      loc_180015DE3
0x180015b36  mov     [rbp+4Fh+var_A0], r15
0x180015b3a  lea     rcx, [rbp+4Fh+var_A0]
0x180015b3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015b43  mov     [rbp+4Fh+var_A0], r15
0x180015b47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015b4e  lea     ecx, [r15+68h]; unsigned __int64
0x180015b52  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015b57  test    rax, rax
0x180015b5a  jz      loc_180015F5E
0x180015b60  mov     rcx, rax; this
0x180015b63  call    ??0CShellExperienceViewStateChangedEventArgs@@QEAA@XZ; CShellExperienceViewStateChangedEventArgs::CShellExperienceViewStateChangedEventArgs(void)
0x180015b68  mov     rdi, rax
0x180015b6b  mov     [rbp+4Fh+arg_8], r15
0x180015b6f  cmp     [rax+48h], rsi
0x180015b73  jz      short loc_180015B9F
0x180015b75  mov     rcx, [rsi]
0x180015b78  mov     rax, [rcx+8]
0x180015b7c  mov     rcx, rsi
0x180015b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b84  nop
0x180015b85  mov     rcx, [rdi+48h]
0x180015b89  mov     [rdi+48h], rsi
0x180015b8d  test    rcx, rcx
0x180015b90  jz      short loc_180015B9F
0x180015b92  mov     rax, [rcx]
0x180015b95  mov     rax, [rax+10h]
0x180015b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b9e  nop
0x180015b9f  mov     [rdi+60h], r12d
0x180015ba3  lea     rsi, [rdi+58h]
0x180015ba7  test    r14, r14
0x180015baa  jnz     loc_180015EE4
0x180015bb0  mov     rcx, [rsi]; string
0x180015bb3  call    cs:__imp_WindowsDeleteString
0x180015bba  nop     dword ptr [rax+rax+00h]
0x180015bbf  mov     [rsi], r15
0x180015bc2  mov     rdx, rsi; newString
0x180015bc5  mov     rcx, r14; string
0x180015bc8  call    cs:__imp_WindowsDuplicateString
0x180015bcf  nop     dword ptr [rax+rax+00h]
0x180015bd4  mov     esi, eax
0x180015bd6  test    eax, eax
0x180015bd8  js      loc_180015EF2
0x180015bde  mov     rsi, [rbp+4Fh+arg_20]
0x180015be2  cmp     [rdi+50h], rsi
0x180015be6  jz      short loc_180015C17
0x180015be8  test    rsi, rsi
0x180015beb  jz      short loc_180015BFD
0x180015bed  mov     rax, [rsi]
0x180015bf0  mov     rcx, rsi
0x180015bf3  mov     rax, [rax+8]
0x180015bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bfc  nop
0x180015bfd  mov     rcx, [rdi+50h]
0x180015c01  mov     [rdi+50h], rsi
0x180015c05  test    rcx, rcx
0x180015c08  jz      short loc_180015C17
0x180015c0a  mov     rax, [rcx]
0x180015c0d  mov     rax, [rax+10h]
0x180015c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c16  nop
0x180015c17  lea     rcx, [rdi+30h]
0x180015c1b  mov     [rbp+4Fh+var_A0], rcx
0x180015c1f  mov     rax, [rcx]
0x180015c22  mov     rax, [rax+8]
0x180015c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c2b  nop
0x180015c2c  mov     rcx, rdi
0x180015c2f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIShellExperienceViewStateChangedEventArgs@Experience@Shell@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(void)
0x180015c34  nop
0x180015c35  mov     rax, r13
0x180015c38  lea     rcx, [r13+0A0h]
0x180015c3f  neg     rax
0x180015c42  sbb     rdi, rdi
0x180015c45  and     rdi, rcx
0x180015c48  mov     [rbp+4Fh+arg_8], rdi
0x180015c4c  jz      short loc_180015C5E
0x180015c4e  mov     rax, [rdi]
0x180015c51  mov     rcx, rdi
0x180015c54  mov     rax, [rax+8]
0x180015c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c5d  nop
0x180015c5e  mov     r15, [rbp+4Fh+var_A0]
0x180015c62  mov     [rbp+4Fh+var_70], r15
0x180015c66  test    r15, r15
0x180015c69  jz      short loc_180015C7B
0x180015c6b  mov     rax, [r15]
0x180015c6e  mov     rcx, r15
0x180015c71  mov     rax, [rax+8]
0x180015c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7a  nop
0x180015c7b  mov     [rbp+4Fh+var_68], rbx
0x180015c7f  test    rbx, rbx
0x180015c82  jz      short loc_180015C94
0x180015c84  mov     rax, [rbx]
0x180015c87  mov     rcx, rbx
0x180015c8a  mov     rax, [rax+8]
0x180015c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c93  nop
0x180015c94  mov     r14, rdi
0x180015c97  mov     [rbp+4Fh+var_60], rdi
0x180015c9b  test    rdi, rdi
0x180015c9e  jz      short loc_180015CB0
0x180015ca0  mov     rax, [rdi]
0x180015ca3  mov     rcx, rdi
0x180015ca6  mov     rax, [rax+8]
0x180015caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015caf  nop
0x180015cb0  mov     r12d, [r13+138h]
0x180015cb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015cbe  mov     ecx, 28h ; '('; unsigned __int64
0x180015cc3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015cc8  mov     rsi, rax
0x180015ccb  test    rax, rax
0x180015cce  jz      loc_180016050
0x180015cd4  mov     rcx, rax
0x180015cd7  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180015cdc  lea     rax, [rsi+10h]
0x180015ce0  mov     qword ptr [rax], 0
0x180015ce7  lea     rcx, [rbp+4Fh+var_70]
0x180015ceb  cmp     rax, rcx
0x180015cee  jz      loc_180016048
0x180015cf4  mov     [rax], r15
0x180015cf7  xor     r15d, r15d
0x180015cfa  mov     [rbp+4Fh+var_70], r15
0x180015cfe  lea     rcx, [rax+8]
0x180015d02  mov     [rcx], r15
0x180015d05  lea     rdx, [rbp+4Fh+var_68]
0x180015d09  cmp     rcx, rdx
0x180015d0c  jz      short loc_180015D15
0x180015d0e  mov     [rcx], rbx
0x180015d11  mov     [rbp+4Fh+var_68], r15
0x180015d15  add     rax, 10h
0x180015d19  mov     [rax], r15
0x180015d1c  lea     rcx, [rbp+4Fh+var_60]
0x180015d20  cmp     rax, rcx
0x180015d23  jz      short loc_180015D2F
0x180015d25  mov     [rax], rdi
0x180015d28  mov     r14, r15
0x180015d2b  mov     [rbp+4Fh+var_60], r15
0x180015d2f  lea     rax, off_1803BC0F0
0x180015d36  mov     [rsi], rax
0x180015d39  mov     [rsp+0D0h+var_A8], r15
0x180015d3e  mov     qword ptr [rsp+0D0h+var_B0], rsi; int
0x180015d43  xor     r9d, r9d
0x180015d46  mov     r8d, r12d
0x180015d49  lea     edx, [r9+2]
0x180015d4d  lea     ecx, [rdx+1]
0x180015d50  call    cs:__imp_SHTaskPoolQueueTask
0x180015d57  nop     dword ptr [rax+rax+00h]
0x180015d5c  mov     ebx, eax
0x180015d5e  test    rsi, rsi
0x180015d61  jz      short loc_180015D73
0x180015d63  mov     rdx, [rsi]
0x180015d66  mov     rcx, rsi
0x180015d69  mov     rax, [rdx+10h]
0x180015d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d72  nop
0x180015d73  test    r14, r14
0x180015d76  jz      short loc_180015D8C
0x180015d78  mov     [rbp+4Fh+var_60], r15
0x180015d7c  mov     rax, [r14]
0x180015d7f  mov     rcx, r14
0x180015d82  mov     rax, [rax+10h]
0x180015d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d8b  nop
0x180015d8c  lea     rcx, [rbp+4Fh+var_68]
0x180015d90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015d95  nop
0x180015d96  mov     rcx, [rbp+4Fh+var_70]
0x180015d9a  test    rcx, rcx
0x180015d9d  jz      short loc_180015DAC
0x180015d9f  mov     rax, [rcx]
0x180015da2  mov     rax, [rax+10h]
0x180015da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dab  nop
0x180015dac  test    ebx, ebx
0x180015dae  js      loc_180015FC4
0x180015db4  test    rdi, rdi
0x180015db7  jz      short loc_180015DC9
0x180015db9  mov     rax, [rdi]
0x180015dbc  mov     rcx, rdi
0x180015dbf  mov     rax, [rax+10h]
0x180015dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dc8  nop
0x180015dc9  mov     rcx, [rbp+4Fh+var_A0]
0x180015dcd  test    rcx, rcx
0x180015dd0  jz      short loc_180015DE3
0x180015dd2  mov     [rbp+4Fh+var_A0], r15
0x180015dd6  mov     rax, [rcx]
  ... truncated ...
```

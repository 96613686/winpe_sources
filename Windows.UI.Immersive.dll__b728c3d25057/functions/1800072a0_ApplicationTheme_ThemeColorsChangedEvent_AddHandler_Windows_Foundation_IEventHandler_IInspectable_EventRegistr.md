# ApplicationTheme::ThemeColorsChangedEvent::AddHandler(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x1800072a0`
- end: `0x180007a66`
- name: `?AddHandler@ThemeColorsChangedEvent@ApplicationTheme@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `1990`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800072a0`
- `0x180007a70`
- `0x180007a90`
- `0x180007af0`
- `0x180007b64`
- `0x180008000`
- `0x18000859c`
- `0x1800085f0`
- `0x1800086e0`
- `0x180008760`
- `0x180015460`
- `0x180026f10`
- `0x180034768`
- `0x180034c6c`
- `0x180034db4`
- `0x18003f1f0`
- `0x180047dd8`
- `0x180050ba0`
- `0x180050f70`
- `0x18005659c`
- `0x1800565c0`
- `0x18006b6bc`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007724`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000753f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000778e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000753f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000778e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800072e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007340`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007517`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800072e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007340`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007517`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007926`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007926`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007870`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007979`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007979`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000767b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000767b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007855`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007855`

## string_xrefs

- `0x180007899`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x18000794f`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007996`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800079e4`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::ThemeColorsChangedEvent::AddHandler(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  RTL_SRWLOCK *v4; // r14
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  RTL_SRWLOCK *v7; // r15
  RTL_SRWLOCK *v8; // r13
  unsigned __int64 v9; // rsi
  char *v10; // rax
  char *v11; // r12
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rax
  unsigned __int64 v16; // rdi
  Microsoft::WRL::AgileRef *v17; // rax
  Microsoft::WRL::AgileRef *v18; // rbx
  unsigned __int64 v19; // rax
  void *v20; // rax
  volatile int *v21; // rdx
  __int64 v22; // rcx
  _QWORD *Ptr; // rax
  _QWORD *v24; // rdi
  __int64 *v25; // r14
  RTL_SRWLOCK *v26; // r13
  __int64 *v27; // rsi
  __int64 v28; // rbx
  __int64 v29; // r15
  __int64 v30; // rcx
  struct IUnknown *v31; // rdx
  void *v32; // r8
  __int64 v33; // rdx
  wil::details::registry_watcher_state **v34; // rsi
  wil::details::registry_watcher_state **v35; // rbx
  wil::details::registry_watcher_state **registry_watcher_nothrow; // rax
  wil::details::registry_watcher_state **v37; // rdi
  wil::details::registry_watcher_state *v38; // rsi
  wil::details::registry_watcher_state **v39; // rbx
  unsigned int v40; // ebx
  wil::details::registry_watcher_state *v41; // r12
  LSTATUS v42; // eax
  bool v43; // sf
  _QWORD *v44; // rax
  _QWORD *v45; // rdi
  wil::details *v46; // rcx
  HANDLE Event; // rbx
  wil::details::registry_watcher_state **v49; // rax
  wil::details::registry_watcher_state **v50; // rdi
  wil::details::registry_watcher_state *v51; // rsi
  int LastErrorFailHr; // eax
  unsigned int v53; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v55; // r9
  struct _TP_WAIT *v56; // r13
  struct _TP_WAIT *v57; // r14
  unsigned int v58; // edx
  void *v59; // rdx
  unsigned int v60; // edx
  unsigned int v61; // edx
  DWORD LastError; // ebx
  DWORD dwOptions; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  void *v66; // [rsp+60h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v67; // [rsp+68h] [rbp-A0h]
  _QWORD *v68; // [rsp+70h] [rbp-98h] BYREF
  Microsoft::WRL::AgileRef *v69; // [rsp+78h] [rbp-90h] BYREF
  __int64 v70; // [rsp+80h] [rbp-88h] BYREF
  RTL_SRWLOCK *v71; // [rsp+88h] [rbp-80h]
  struct IUnknown *v72; // [rsp+90h] [rbp-78h]
  struct IUnknown **v73; // [rsp+98h] [rbp-70h]
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-68h]
  __int64 (__fastcall **v75)(); // [rsp+B0h] [rbp-58h] BYREF
  RTL_SRWLOCK *v76; // [rsp+B8h] [rbp-50h]
  __int64 (__fastcall ***v77)(); // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v4 = a1;
  v67 = a1;
  v73 = a3;
  v72 = a2;
  SRWLock = a1 + 11;
  AcquireSRWLockExclusive(a1 + 11);
  if ( !a2 )
  {
    v40 = -2147024809;
    goto LABEL_56;
  }
  QueryInterface = a2->lpVtbl[1].QueryInterface;
  v7 = v4 + 8;
  v8 = v4 + 10;
  hKey = (HKEY)&v4[8];
  v66 = QueryInterface;
  *a3 = 0;
  v70 = 0;
  v71 = v4 + 10;
  AcquireSRWLockExclusive(v4 + 10);
  if ( v4[8].Ptr )
    v9 = ((__int64)(*((_QWORD *)v4[8].Ptr + 3) - *((_QWORD *)v4[8].Ptr + 2)) >> 3) + 1;
  else
    v9 = 1;
  v10 = (char *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(v10);
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *(_QWORD *)v11 = &Microsoft::WRL::Details::EventTargetArray::`vftable';
    v12 = 8 * v9;
    *((_QWORD *)v11 + 4) = 0;
    if ( !is_mul_ok(v9, 8u) )
      v12 = -1;
    v13 = __CFADD__(v12, 8);
    v14 = v12 + 8;
    if ( v13 )
      v14 = -1;
    v15 = (unsigned __int64 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    if ( v15 )
    {
      *v15 = v9;
      v16 = v9;
      v17 = (Microsoft::WRL::AgileRef *)(v15 + 1);
      v69 = v17;
      v18 = v17;
      if ( v9 )
      {
        do
        {
          Microsoft::WRL::AgileRef::AgileRef(v18);
          v18 = (Microsoft::WRL::AgileRef *)((char *)v18 + 8);
          --v16;
        }
        while ( v16 );
        v17 = v69;
      }
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)v11 + 2) = v17;
    v19 = 8 * v9;
    if ( !is_mul_ok(v9, 8u) )
      v19 = -1;
    v20 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
    v22 = *((_QWORD *)v11 + 2);
    *((_QWORD *)v11 + 4) = v20;
    if ( v22 )
    {
      if ( v20 )
      {
        *((_QWORD *)v11 + 3) = v22;
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v11 + 12), v21);
        v69 = (Microsoft::WRL::AgileRef *)v11;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
        Ptr = v7->Ptr;
        if ( v7->Ptr )
        {
          v24 = (_QWORD *)Ptr[2];
          v25 = (__int64 *)Ptr[4];
          if ( v24 != (_QWORD *)Ptr[3] )
          {
            v26 = v7;
            do
            {
              v27 = (__int64 *)*((_QWORD *)v11 + 3);
              v28 = *v24;
              v29 = *v25;
              if ( *v27 != *v24 )
              {
                if ( v28 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*v24);
                v30 = *v27;
                *v27 = v28;
                if ( v30 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
              ++v25;
              ++v24;
              *(_QWORD *)(*((_QWORD *)v11 + 4) + 8 * ((__int64)(*((_QWORD *)v11 + 3) - *((_QWORD *)v11 + 2)) >> 3)) = v29;
              *((_QWORD *)v11 + 3) += 8LL;
            }
            while ( v24 != *((_QWORD **)v26->Ptr + 3) );
            v8 = v71;
            v7 = (RTL_SRWLOCK *)hKey;
          }
          v4 = v67;
        }
        v31 = v72;
        v32 = v66;
        *v73 = v72;
        Microsoft::WRL::Details::EventTargetArray::AddTail((Microsoft::WRL::Details::EventTargetArray *)v11, v31, v32);
        AcquireSRWLockExclusive(v7 + 1);
        Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v70, v7);
        Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(v7, &v69);
        if ( v7 != (RTL_SRWLOCK *)-8LL )
          ReleaseSRWLockExclusive(v7 + 1);
        if ( v69 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v69);
        if ( v8 )
          ReleaseSRWLockExclusive(v8);
        if ( v70 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v70);
        v34 = (wil::details::registry_watcher_state **)&v4[12];
        if ( v4[12].Ptr )
          goto LABEL_37;
        v76 = v4;
        v75 = off_1800E6AB0;
        v68 = 0;
        v77 = &v75;
        hKey = 0;
        v41 = 0;
        v42 = RegCreateKeyExW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
                0,
                0,
                0,
                0x10u,
                0,
                &hKey,
                0);
        v43 = v42 < 0;
        if ( v42 > 0 )
          v43 = 1;
        if ( v43 )
        {
          if ( !hKey )
            goto LABEL_74;
          goto LABEL_73;
        }
        v44 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
        v45 = v44;
        if ( !v44 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCBB,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)0x8007000ELL,
            dwOptions);
          goto LABEL_72;
        }
        if ( v77 )
        {
          v44[14] = v44 + 1;
          ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v77)[2])(v77);
          ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v77)[3])(v77);
          v77 = 0;
        }
        else
        {
          v44[14] = 0;
        }
        v45[15] = hKey;
        hKey = 0;
        v45[16] = 0;
        v45[17] = 0;
        *((_BYTE *)v45 + 144) = 0;
        *((_DWORD *)v45 + 37) = 1;
        v45[19] = 0;
        Event = CreateEventExW(0, 0, 0, 0x1F0003u);
        if ( Event )
        {
          GetLastError();
          _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
            v45 + 16,
            Event);
        }
        else
        {
          LastErrorFailHr = wil::details::GetLastErrorFailHr(v46);
          if ( LastErrorFailHr < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCBC,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
              (const char *)(unsigned int)LastErrorFailHr,
              dwOptions);
            wil::details::registry_watcher_state::`scalar deleting destructor'(
              (wil::details::registry_watcher_state *)v45,
              v61);
            goto LABEL_72;
          }
        }
        v53 = RegNotifyChangeKeyValue((HKEY)v45[15], *((unsigned __int8 *)v45 + 144), 0x10000005u, (HANDLE)v45[16], 1);
        if ( v53 )
        {
          wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xCC2,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)v53,
            dwOptionsa);
          wil::details::registry_watcher_state::`scalar deleting destructor'(
            (wil::details::registry_watcher_state *)v45,
            v60);
        }
        else
        {
          ThreadpoolWait = CreateThreadpoolWait(
                             wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                             v45,
                             0);
          v56 = (struct _TP_WAIT *)v45[17];
          v57 = ThreadpoolWait;
          if ( v56 )
          {
            LastError = GetLastError();
            wil::details::DestroyThreadPoolWait<0>::Destroy(v56);
            SetLastError(LastError);
          }
          v45[17] = v57;
          if ( v57 )
          {
            v59 = (void *)v45[16];
            v68 = v45;
            v41 = (wil::details::registry_watcher_state *)v45;
            SetThreadpoolWait(v57, v59, 0);
          }
          else
          {
            wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xCC5,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
              v55);
            wil::details::registry_watcher_state::`scalar deleting destructor'(
              (wil::details::registry_watcher_state *)v45,
              v58);
          }
          v4 = v67;
        }
LABEL_72:
        if ( !hKey )
        {
LABEL_74:
          if ( v34 != (wil::details::registry_watcher_state **)&v68 )
          {
            if ( *v34 )
              wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v34);
            *v34 = v41;
            v68 = 0;
          }
          wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v68);
          if ( v77 )
            ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v77)[3])(v77);
LABEL_37:
          v35 = (wil::details::registry_watcher_state **)&v4[14];
          if ( !v4[14].Ptr )
          {
            v76 = v4;
            v75 = off_1800E6AB0;
            v77 = &v75;
            registry_watcher_nothrow = (wil::details::registry_watcher_state **)wil::make_registry_watcher_nothrow(
                                                                                  &v66,
                                                                                  v33,
                                                                                  L"Control Panel\\Colors");
            v37 = registry_watcher_nothrow;
            if ( v35 != registry_watcher_nothrow )
            {
              v38 = *registry_watcher_nothrow;
              if ( *v35 )
                wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v35);
              *v35 = v38;
              *v37 = 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v66);
            if ( v77 )
              ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v77)[3])(v77);
          }
          v39 = (wil::details::registry_watcher_state **)&v4[13];
          if ( v4[13].Ptr )
          {
            v40 = 0;
          }
          else
          {
            v76 = v4;
            v75 = off_1800E6CC8;
            v77 = &v75;
            v49 = (wil::details::registry_watcher_state **)wil::make_registry_watcher_nothrow(
                                                             &v66,
                                                             v33,
                                                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent");
            v50 = v49;
            if ( v39 != v49 )
            {
              v51 = *v49;
              if ( *v39 )
                wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v39);
              *v39 = v51;
              *v50 = 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v66);
            v40 = 0;
            if ( v77 )
              ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v77)[3])(v77);
          }
          goto LABEL_56;
        }
LABEL_73:
        RegCloseKey(hKey);
        goto LABEL_74;
      }
      Microsoft::WRL::ComPtr<IUnknown>::`vector deleting destructor'();
    }
    operator delete(*((void **)v11 + 4), (const struct std::nothrow_t *)v21);
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 4) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
  }
  if ( v4 != (RTL_SRWLOCK *)-80LL )
    ReleaseSRWLockExclusive(v4 + 10);
  v40 = -2147024882;
LABEL_56:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return v40;
}

```

## disassembly

```asm
0x1800072a0  mov     r11, rsp
0x1800072a3  push    rbp
0x1800072a4  push    rbx
0x1800072a5  lea     rbp, [r11-58h]
0x1800072a9  sub     rsp, 148h
0x1800072b0  mov     rax, cs:__security_cookie
0x1800072b7  xor     rax, rsp
0x1800072ba  mov     [rbp+50h+var_38], rax
0x1800072be  mov     [r11-18h], rdi
0x1800072c2  lea     rax, [rcx+58h]
0x1800072c6  mov     [r11-30h], r14
0x1800072ca  mov     rdi, r8
0x1800072cd  mov     r14, rcx
0x1800072d0  mov     [rsp+150h+var_F0], rcx
0x1800072d5  mov     rcx, rax; SRWLock
0x1800072d8  mov     [rbp+50h+var_C0], r8
0x1800072dc  mov     rbx, rdx
0x1800072df  mov     [rbp+50h+var_C8], rdx
0x1800072e3  mov     [rbp+50h+SRWLock], rax
0x1800072e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800072ed  test    rbx, rbx
0x1800072f0  jz      loc_1800079CE
0x1800072f6  mov     rax, [rbx]
0x1800072f9  xor     ebx, ebx
0x1800072fb  mov     [rsp+150h+arg_18], rsi
0x180007303  mov     [rsp+150h+var_18], r12
0x18000730b  mov     [rsp+150h+var_20], r13
0x180007313  mov     rax, [rax+18h]
0x180007317  mov     [rsp+150h+var_30], r15
0x18000731f  lea     r15, [r14+40h]
0x180007323  lea     r13, [r15+10h]
0x180007327  mov     [rsp+150h+hKey], r15
0x18000732c  mov     rcx, r13; SRWLock
0x18000732f  mov     [rsp+150h+var_F8], rax
0x180007334  mov     [rdi], rbx
0x180007337  mov     [rsp+150h+var_D8], rbx
0x18000733c  mov     [rbp+50h+var_D0], r13
0x180007340  call    cs:__imp_AcquireSRWLockExclusive
0x180007346  mov     rax, [r15]
0x180007349  test    rax, rax
0x18000734c  jnz     loc_18000760D
0x180007352  mov     esi, 1
0x180007357  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000735e  mov     ecx, 28h ; '('; unsigned __int64
0x180007363  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007368  mov     r12, rax
0x18000736b  test    rax, rax
0x18000736e  jz      loc_1800079B7
0x180007374  mov     rcx, rax
0x180007377  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(void)
0x18000737c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007383  mov     [r12+10h], rbx
0x180007388  lea     rax, ??_7EventTargetArray@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::EventTargetArray::`vftable'
0x18000738f  mov     [r12+18h], rbx
0x180007394  mov     [r12], rax
0x180007398  mov     eax, 8
0x18000739d  mul     rsi
0x1800073a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800073a7  mov     [r12+20h], rbx
0x1800073ac  cmovb   rax, rcx
0x1800073b0  add     rax, 8
0x1800073b4  cmovb   rax, rcx
0x1800073b8  mov     rcx, rax; unsigned __int64
0x1800073bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800073c0  test    rax, rax
0x1800073c3  jz      loc_1800079D8
0x1800073c9  mov     [rax], rsi
0x1800073cc  mov     rdi, rsi
0x1800073cf  add     rax, 8
0x1800073d3  mov     [rsp+150h+var_E0], rax
0x1800073d8  mov     rbx, rax
0x1800073db  test    rsi, rsi
0x1800073de  jz      short loc_1800073F7
0x1800073e0  mov     rcx, rbx; this
0x1800073e3  call    ??0AgileRef@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::AgileRef::AgileRef(void)
0x1800073e8  add     rbx, 8
0x1800073ec  sub     rdi, 1
0x1800073f0  jnz     short loc_1800073E0
0x1800073f2  mov     rax, [rsp+150h+var_E0]
0x1800073f7  xor     ebx, ebx
0x1800073f9  mov     [r12+10h], rax
0x1800073fe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007405  mov     eax, 8
0x18000740a  mul     rsi
0x18000740d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007414  cmovb   rax, rcx
0x180007418  mov     rcx, rax; unsigned __int64
0x18000741b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007420  mov     rcx, [r12+10h]
0x180007425  mov     [r12+20h], rax
0x18000742a  test    rcx, rcx
0x18000742d  jz      loc_180007A45
0x180007433  test    rax, rax
0x180007436  jz      loc_180007A40
0x18000743c  mov     [r12+18h], rcx
0x180007441  lea     rcx, [r12+0Ch]; this
0x180007446  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000744b  mov     rcx, r12
0x18000744e  mov     [rsp+150h+var_E0], r12
0x180007453  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180007458  mov     rax, [r15]
0x18000745b  test    rax, rax
0x18000745e  jz      loc_1800074F8
0x180007464  mov     rdi, [rax+10h]
0x180007468  mov     r14, [rax+20h]
0x18000746c  cmp     rdi, [rax+18h]
0x180007470  jz      loc_1800074F3
0x180007476  mov     r13, r15
0x180007479  nop     dword ptr [rax+00000000h]
0x180007480  mov     rsi, [r12+18h]
0x180007485  mov     rbx, [rdi]
0x180007488  mov     r15, [r14]
0x18000748b  cmp     [rsi], rbx
0x18000748e  jz      short loc_1800074BB
0x180007490  test    rbx, rbx
0x180007493  jz      short loc_1800074A4
0x180007495  mov     rax, [rbx]
0x180007498  mov     rcx, rbx
0x18000749b  mov     rax, [rax+8]
0x18000749f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a4  mov     rcx, [rsi]
0x1800074a7  mov     [rsi], rbx
0x1800074aa  test    rcx, rcx
0x1800074ad  jz      short loc_1800074BB
0x1800074af  mov     rax, [rcx]
0x1800074b2  mov     rax, [rax+10h]
0x1800074b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074bb  mov     rcx, [r12+18h]
0x1800074c0  add     r14, 8
0x1800074c4  sub     rcx, [r12+10h]
0x1800074c9  add     rdi, 8
0x1800074cd  mov     rax, [r12+20h]
0x1800074d2  sar     rcx, 3
0x1800074d6  mov     [rax+rcx*8], r15
0x1800074da  add     qword ptr [r12+18h], 8
0x1800074e0  mov     rax, [r13+0]
0x1800074e4  cmp     rdi, [rax+18h]
0x1800074e8  jnz     short loc_180007480
0x1800074ea  mov     r13, [rbp+50h+var_D0]
0x1800074ee  mov     r15, [rsp+150h+hKey]
0x1800074f3  mov     r14, [rsp+150h+var_F0]
0x1800074f8  mov     rax, [rbp+50h+var_C0]
0x1800074fc  mov     rcx, r12; this
0x1800074ff  mov     rdx, [rbp+50h+var_C8]; struct IUnknown *
0x180007503  mov     r8, [rsp+150h+var_F8]; void *
0x180007508  mov     [rax], rdx
0x18000750b  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180007510  lea     rbx, [r15+8]
0x180007514  mov     rcx, rbx; SRWLock
0x180007517  call    cs:__imp_AcquireSRWLockExclusive
0x18000751d  mov     rdx, r15
0x180007520  lea     rcx, [rsp+150h+var_D8]
0x180007525  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18000752a  lea     rdx, [rsp+150h+var_E0]
0x18000752f  mov     rcx, r15
0x180007532  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180007537  test    rbx, rbx
0x18000753a  jz      short loc_180007545
0x18000753c  mov     rcx, rbx; SRWLock
0x18000753f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007545  mov     rcx, [rsp+150h+var_E0]
0x18000754a  test    rcx, rcx
0x18000754d  jz      short loc_180007554
0x18000754f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180007554  test    r13, r13
0x180007557  jnz     loc_180007984
0x18000755d  mov     rcx, [rsp+150h+var_D8]
0x180007562  test    rcx, rcx
0x180007565  jz      short loc_18000756C
0x180007567  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000756c  cmp     qword ptr [r14+60h], 0
0x180007571  lea     rsi, [r14+60h]
0x180007575  jz      loc_180007621
0x18000757b  cmp     qword ptr [r14+70h], 0
0x180007580  lea     rbx, [r14+70h]
0x180007584  jnz     short loc_1800075F7
0x180007586  lea     rax, off_1800E6AB0
0x18000758d  mov     [rbp+50h+var_A0], r14
0x180007591  mov     [rbp+50h+var_A8], rax
0x180007595  lea     r8, aControlPanelCo; "Control Panel\\Colors"
0x18000759c  lea     rax, [rbp+50h+var_A8]
0x1800075a0  mov     [rbp+50h+var_40], rax
0x1800075a4  lea     rcx, [rsp+150h+var_F8]
0x1800075a9  lea     rax, [rbp+50h+var_B0]
0x1800075ad  mov     qword ptr [rsp+150h+dwOptions], rax
0x1800075b2  call    ?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800075b7  mov     rdi, rax
0x1800075ba  cmp     rbx, rax
0x1800075bd  jz      short loc_1800075D8
0x1800075bf  mov     rcx, [rbx]; this
0x1800075c2  mov     rsi, [rax]
0x1800075c5  test    rcx, rcx
0x1800075c8  jnz     loc_180007A2C
0x1800075ce  mov     [rbx], rsi
0x1800075d1  mov     qword ptr [rdi], 0
0x1800075d8  lea     rcx, [rsp+150h+var_F8]
0x1800075dd  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x1800075e2  mov     rcx, [rbp+50h+var_40]
0x1800075e6  test    rcx, rcx
0x1800075e9  jz      short loc_1800075F7
0x1800075eb  mov     rax, [rcx]
0x1800075ee  mov     rax, [rax+18h]
0x1800075f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f7  cmp     qword ptr [r14+68h], 0
0x1800075fc  lea     rbx, [r14+68h]
0x180007600  jz      loc_1800077AC
0x180007606  xor     ebx, ebx
0x180007608  jmp     loc_180007755
0x18000760d  mov     rsi, [rax+18h]
0x180007611  sub     rsi, [rax+10h]
0x180007615  sar     rsi, 3
0x180007619  inc     rsi
0x18000761c  jmp     loc_180007357
0x180007621  xor     ebx, ebx
0x180007623  mov     [rbp+50h+var_A0], r14
0x180007627  mov     [rsp+40h], rbx; lpdwDisposition
0x18000762c  lea     rax, off_1800E6AB0
0x180007633  mov     [rbp+50h+var_A8], rax
0x180007637  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000763e  lea     rax, [rbp+50h+var_A8]
0x180007642  mov     [rsp+150h+var_E8], rbx
0x180007647  mov     [rbp+50h+var_40], rax
0x18000764b  xor     r9d, r9d; lpClass
0x18000764e  lea     rax, [rsp+150h+hKey]
0x180007653  mov     [rsp+150h+hKey], rbx
0x180007658  mov     [rsp+150h+phkResult], rax; phkResult
0x18000765d  xor     r8d, r8d; Reserved
0x180007660  mov     [rsp+150h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180007665  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000766c  mov     [rsp+150h+samDesired], 10h; samDesired
0x180007674  mov     r12d, ebx
0x180007677  mov     [rsp+150h+dwOptions], ebx; int
0x18000767b  call    cs:__imp_RegCreateKeyExW
0x180007681  test    eax, eax
0x180007683  jg      loc_18000793C
0x180007689  js      loc_18000796B
0x18000768f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007696  mov     ecx, 0A0h; unsigned __int64
0x18000769b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800076a0  mov     rdi, rax
0x1800076a3  test    rax, rax
0x1800076a6  jz      loc_18000794B
0x1800076ac  cmp     [rbp+50h+var_40], rbx
0x1800076b0  jz      loc_180007933
0x1800076b6  lea     rdx, [rax+8]
0x1800076ba  mov     [rax+70h], rdx
0x1800076be  mov     rcx, [rbp+50h+var_40]
0x1800076c2  mov     rax, [rcx]
0x1800076c5  mov     rax, [rax+10h]
0x1800076c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ce  mov     rcx, [rbp+50h+var_40]
0x1800076d2  mov     rax, [rcx]
0x1800076d5  mov     rax, [rax+18h]
0x1800076d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076de  mov     [rbp+50h+var_40], rbx
0x1800076e2  mov     rax, [rsp+150h+hKey]
0x1800076e7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800076ed  mov     [rdi+78h], rax
0x1800076f1  xor     r8d, r8d; dwFlags
0x1800076f4  mov     [rsp+150h+hKey], rbx
0x1800076f9  xor     eax, eax
0x1800076fb  mov     [rdi+80h], rbx
0x180007702  xor     edx, edx; lpName
0x180007704  mov     [rdi+88h], rbx
0x18000770b  xor     ecx, ecx; lpEventAttributes
0x18000770d  mov     [rdi+90h], bl
0x180007713  mov     dword ptr [rdi+94h], 1
0x18000771d  mov     [rdi+98h], rax
0x180007724  call    cs:__imp_CreateEventExW
0x18000772a  mov     rbx, rax
0x18000772d  test    rax, rax
0x180007730  jz      loc_180007828
0x180007736  call    cs:__imp_GetLastError
0x18000773c  mov     rdx, rbx
0x18000773f  lea     rcx, [rdi+80h]
0x180007746  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000774b  jmp     loc_180007835
0x180007750  mov     ebx, 8007000Eh
0x180007755  mov     r13, [rsp+150h+var_20]
0x18000775d  mov     r12, [rsp+150h+var_18]
0x180007765  mov     rsi, [rsp+150h+arg_18]
0x18000776d  mov     r15, [rsp+150h+var_30]
0x180007775  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x180007779  mov     r14, [rsp+150h+var_28]
0x180007781  mov     rdi, [rsp+140h]
0x180007789  test    rcx, rcx
0x18000778c  jz      short loc_180007794
0x18000778e  call    cs:__imp_ReleaseSRWLockExclusive
0x180007794  mov     eax, ebx
0x180007796  mov     rcx, [rbp+50h+var_38]
0x18000779a  xor     rcx, rsp; StackCookie
0x18000779d  call    __security_check_cookie
0x1800077a2  add     rsp, 148h
0x1800077a9  pop     rbx
0x1800077aa  pop     rbp
0x1800077ab  retn
0x1800077ac  lea     rax, off_1800E6CC8
0x1800077b3  mov     [rbp+50h+var_A0], r14
0x1800077b7  mov     [rbp+50h+var_A8], rax
0x1800077bb  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
  ... truncated ...
```

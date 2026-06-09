# CMapiManager::RunMapiIdleThread(void)

- ea: `0x18002f9cc`
- end: `0x18002fde8`
- name: `?RunMapiIdleThread@CMapiManager@@QEAAKXZ`
- size: `1052`
- prototype: `unsigned int __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ee50`

## callees

- `0x180004c20`
- `0x18000e658`
- `0x18000e6e0`
- `0x1800113ac`
- `0x1800113ec`
- `0x180011884`
- `0x180022a78`
- `0x18002d18c`
- `0x18002d3c8`
- `0x18002d938`
- `0x18002e6dc`
- `0x18002ead4`
- `0x18002eda8`
- `0x18002f28c`
- `0x18002f52c`
- `0x18002f798`
- `0x18002f9cc`
- `0x18002fdf0`
- `0x1800300dc`
- `0x180030a10`
- `0x180031310`
- `0x180036b6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fd1f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fd1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fb33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fc74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd78`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fa74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fa74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd45`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd45`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18002fafb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18002fafb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18002fad7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18002fad7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18002fae1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18002fae1`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18002fba6`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18002fba6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002fa48`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002fa48`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002fda7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002fda7`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIUninitialize` at `0x18002fd8b`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIUninitialize` at `0x18002fd8b`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitIdle` at `0x18002fa5e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIInitIdle` at `0x18002fa5e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIDeinitIdle` at `0x18002fd63`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIDeinitIdle` at `0x18002fd63`

## string_xrefs

- `0x18002fd91`: `   CMapiManager::UninitializeThread() MapiUninitialize() Completed!`
- `0x18002fd7f`: `   CMapiManager::UninitializeThread() MapiUninitialize() Calling...`
- `0x18002f9e8`: `CMapiManager::RunMapiIdleThread() Enter`
- `0x18002fdb4`: `CMapiManager::RunMapiIdleThread() Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMapiManager::RunMapiIdleThread(CMapiManager *this)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  DWORD v4; // edx
  CMapiManager *v5; // rcx
  LONG v6; // eax
  int v7; // ebx
  int v8; // r14d
  int v9; // r13d
  HANDLE *v10; // r15
  DWORD v11; // eax
  int v12; // esi
  HANDLE v13; // rsi
  __int64 v14; // rax
  HANDLE **NextValue; // rax
  HANDLE *v16; // rbx
  __int64 v17; // rsi
  int i; // ebx
  __int64 v19; // rax
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+30h] [rbp-49h] BYREF
  HANDLE *pHandles; // [rsp+38h] [rbp-41h] BYREF
  DWORD nCount[2]; // [rsp+40h] [rbp-39h]
  __int64 v24; // [rsp+48h] [rbp-31h] BYREF
  __int64 v25; // [rsp+50h] [rbp-29h]
  MSG Msg; // [rsp+58h] [rbp-21h] BYREF
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 StartPosition; // [rsp+F0h] [rbp+77h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+F8h] [rbp+7Fh] BYREF

  CLogger::Info(L"CMapiManager::RunMapiIdleThread() Enter");
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v28);
  v2 = 0xC000000000000LL;
  if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v28) )
  {
    v3 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
           &v27,
           &v28);
    v2 = CMapiSupport::ConvertToIntVersion(v3);
  }
  v4 = 2;
  if ( v2 != 0x9000000000000LL )
    v4 = 0;
  CoInitializeEx(0, v4);
  v6 = CMapiManager::InitializeThread(v5);
  v7 = v6;
  LODWORD(v27) = v6;
  if ( v6 >= 0 )
    v6 = MAPIInitIdle(0);
  v8 = v6;
  *((_DWORD *)this + 48) = v6;
  SetEvent(*((HANDLE *)this + 23));
  memset(&Msg, 0, sizeof(Msg));
  if ( v8 >= 0 )
  {
    while ( !*((_DWORD *)this + 33) )
    {
      pHandles = 0;
      *(_QWORD *)nCount = 0;
      if ( !(unsigned int)CMapiManager::PingSessions(this) )
        CMapiManager::SendShutdownNotification(this);
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
        {
          *((_DWORD *)this + 33) = 1;
        }
        else
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, (char *)this + 136);
      ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, (char *)this + 272);
      v21 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 352);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
      v9 = *((_DWORD *)this + 72);
      StartPosition = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 280);
      while ( StartPosition )
      {
        v30 = **(struct _RTL_CRITICAL_SECTION ***)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                                    (char *)this + 280,
                                                    &StartPosition);
        ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(&pHandles, &v30);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
      v10 = pHandles;
      v11 = MsgWaitForMultipleObjects(nCount[0], pHandles, 0, 0x7530u, 0x1CFFu);
      if ( v11 )
      {
        if ( v11 == 1 || (v12 = v11 - (v11 >= 0x80 ? 0x80 : 0), v12 - 2 >= v9) )
        {
          CMapiManager::CleanupStoreWatchers(this, 0);
        }
        else
        {
          v24 = 0;
          v25 = 0;
          v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 352);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
          if ( v12 < 0 || v12 >= (int)nCount[0] )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            break;
          }
          v13 = v10[v12];
          v14 = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 280);
          StartPosition = v14;
          while ( v14 )
          {
            NextValue = (HANDLE **)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                     (char *)this + 280,
                                     &StartPosition);
            v16 = *NextValue;
            if ( v13 == **NextValue )
            {
              ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::operator=(
                &v24,
                v16 + 2);
              ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(v16 + 2);
              CMapiManager::CleanupStoreWatchers(this, 0);
              break;
            }
            v14 = StartPosition;
          }
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
          if ( (int)v25 > 0 )
          {
            v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
            StartPosition = ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition((char *)this + 16);
            while ( StartPosition )
            {
              v17 = *(_QWORD *)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(
                                 (char *)this + 16,
                                 &StartPosition);
              if ( v17 )
              {
                for ( i = 0; i < (int)v25; ++i )
                {
                  v19 = ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](
                          &v24,
                          (unsigned int)i);
                  CMapiSession::ReleaseStore(v17, v19);
                }
              }
            }
            CMapiManager::ReleaseUnusedSessions(this);
            if ( !*((_QWORD *)this + 3) )
              CMapiManager::SendShutdownNotification(this);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
          }
          ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(&v24);
        }
      }
      else
      {
        *((_DWORD *)this + 33) = 1;
      }
      if ( v10 )
      {
        free(v10);
        pHandles = 0;
      }
      *(_QWORD *)nCount = 0;
    }
    v7 = (int)v27;
  }
  *((_DWORD *)this + 40) = 0;
  CMapiManager::Terminate(this);
  if ( v8 >= 0 )
    MAPIDeinitIdle();
  if ( v7 >= 0 )
  {
    v27 = &CMapiManager::s_csMapiIdleThread;
    EnterCriticalSection(&CMapiManager::s_csMapiIdleThread);
    CLogger::Info(L"   CMapiManager::UninitializeThread() MapiUninitialize() Calling...");
    MAPIUninitialize();
    CLogger::Info(L"   CMapiManager::UninitializeThread() MapiUninitialize() Completed!");
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
  }
  CoUninitialize();
  *((_DWORD *)this + 32) = 0;
  CLogger::Info(v8, L"CMapiManager::RunMapiIdleThread() Exit");
  ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002f9cc  push    rbp
0x18002f9ce  push    rbx
0x18002f9cf  push    rsi
0x18002f9d0  push    rdi
0x18002f9d1  push    r12
0x18002f9d3  push    r13
0x18002f9d5  push    r14
0x18002f9d7  push    r15
0x18002f9d9  lea     rbp, [rsp-1Fh]
0x18002f9de  sub     rsp, 98h
0x18002f9e5  mov     rdi, rcx
0x18002f9e8  lea     rcx, aCmapimanagerRu; "CMapiManager::RunMapiIdleThread() Enter"
0x18002f9ef  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002f9f4  lea     rcx, [rbp+57h+arg_8]
0x18002f9f8  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002f9fd  nop
0x18002f9fe  mov     rbx, 0C000000000000h
0x18002fa08  lea     rcx, [rbp+57h+arg_8]
0x18002fa0c  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002fa11  xor     r13d, r13d
0x18002fa14  test    eax, eax
0x18002fa16  jnz     short loc_18002FA30
0x18002fa18  lea     rdx, [rbp+57h+arg_8]
0x18002fa1c  lea     rcx, [rbp+57h+arg_0]
0x18002fa20  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002fa25  mov     rcx, rax
0x18002fa28  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x18002fa2d  mov     rbx, rax
0x18002fa30  mov     edx, 2
0x18002fa35  mov     rax, 9000000000000h
0x18002fa3f  cmp     rbx, rax
0x18002fa42  cmovnz  edx, r13d; dwCoInit
0x18002fa46  xor     ecx, ecx; pvReserved
0x18002fa48  call    cs:__imp_CoInitializeEx
0x18002fa4e  call    ?InitializeThread@CMapiManager@@QEAAJXZ; CMapiManager::InitializeThread(void)
0x18002fa53  mov     ebx, eax
0x18002fa55  mov     dword ptr [rbp+57h+arg_0], eax
0x18002fa58  test    eax, eax
0x18002fa5a  js      short loc_18002FA64
0x18002fa5c  xor     ecx, ecx; lpvReserved
0x18002fa5e  call    cs:__imp_MAPIInitIdle
0x18002fa64  mov     r14d, eax
0x18002fa67  mov     [rdi+0C0h], eax
0x18002fa6d  mov     rcx, [rdi+0B8h]; hEvent
0x18002fa74  call    cs:__imp_SetEvent
0x18002fa7a  xorps   xmm0, xmm0
0x18002fa7d  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18002fa81  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18002fa85  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18002fa89  test    r14d, r14d
0x18002fa8c  js      loc_18002FD4F
0x18002fa92  cmp     [rdi+84h], r13d
0x18002fa99  jnz     loc_18002FD4C
0x18002fa9f  mov     [rbp+57h+pHandles], r13
0x18002faa3  mov     qword ptr [rbp+57h+nCount], 0
0x18002faab  mov     rcx, rdi; this
0x18002faae  call    ?PingSessions@CMapiManager@@QEAAHXZ; CMapiManager::PingSessions(void)
0x18002fab3  test    eax, eax
0x18002fab5  jnz     short loc_18002FAE7
0x18002fab7  mov     rcx, rdi; this
0x18002faba  call    ?SendShutdownNotification@CMapiManager@@AEAAXXZ; CMapiManager::SendShutdownNotification(void)
0x18002fabf  jmp     short loc_18002FAE7
0x18002fac1  cmp     [rbp+57h+Msg.message], 12h
0x18002fac5  jnz     short loc_18002FAD3
0x18002fac7  mov     dword ptr [rdi+84h], 1
0x18002fad1  jmp     short loc_18002FAE7
0x18002fad3  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18002fad7  call    cs:__imp_TranslateMessage
0x18002fadd  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18002fae1  call    cs:__imp_DispatchMessageW
0x18002fae7  mov     [rsp+0D0h+wRemoveMsg], 1; wRemoveMsg
0x18002faef  xor     r9d, r9d; wMsgFilterMax
0x18002faf2  xor     r8d, r8d; wMsgFilterMin
0x18002faf5  xor     edx, edx; hWnd
0x18002faf7  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18002fafb  call    cs:__imp_PeekMessageW
0x18002fb01  test    eax, eax
0x18002fb03  jnz     short loc_18002FAC1
0x18002fb05  lea     rdx, [rdi+88h]
0x18002fb0c  lea     rcx, [rbp+57h+pHandles]
0x18002fb10  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18002fb15  lea     rdx, [rdi+110h]
0x18002fb1c  lea     rcx, [rbp+57h+pHandles]
0x18002fb20  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18002fb25  lea     rbx, [rdi+160h]
0x18002fb2c  mov     [rbp+57h+var_A0], rbx
0x18002fb30  mov     rcx, rbx; lpCriticalSection
0x18002fb33  call    cs:__imp_EnterCriticalSection
0x18002fb39  lea     r12, [rdi+118h]
0x18002fb40  mov     r13d, [rdi+120h]
0x18002fb47  mov     rcx, r12
0x18002fb4a  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x18002fb4f  mov     [rbp+57h+arg_10], rax
0x18002fb53  test    rax, rax
0x18002fb56  jz      short loc_18002FB82
0x18002fb58  lea     rdx, [rbp+57h+arg_10]
0x18002fb5c  mov     rcx, r12
0x18002fb5f  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x18002fb64  mov     rcx, [rax]
0x18002fb67  mov     rax, [rcx]
0x18002fb6a  mov     [rbp+57h+arg_18], rax
0x18002fb6e  lea     rdx, [rbp+57h+arg_18]
0x18002fb72  lea     rcx, [rbp+57h+pHandles]
0x18002fb76  call    ?Add@?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAAHAEBQEAX@Z; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::Add(void * const &)
0x18002fb7b  cmp     [rbp+57h+arg_10], 0
0x18002fb80  jnz     short loc_18002FB58
0x18002fb82  lea     rcx, [rbp+57h+var_A0]
0x18002fb86  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002fb8b  mov     [rsp+0D0h+wRemoveMsg], 1CFFh; dwWakeMask
0x18002fb93  mov     r9d, 7530h; dwMilliseconds
0x18002fb99  xor     r8d, r8d; fWaitAll
0x18002fb9c  mov     r15, [rbp+57h+pHandles]
0x18002fba0  mov     rdx, r15; pHandles
0x18002fba3  mov     ecx, [rbp+57h+nCount]; nCount
0x18002fba6  call    cs:__imp_MsgWaitForMultipleObjects
0x18002fbac  mov     esi, eax
0x18002fbae  mov     eax, 80h
0x18002fbb3  cmp     esi, eax
0x18002fbb5  sbb     ecx, ecx
0x18002fbb7  not     ecx
0x18002fbb9  and     ecx, eax
0x18002fbbb  mov     eax, esi
0x18002fbbd  test    esi, esi
0x18002fbbf  jz      loc_18002FD0A
0x18002fbc5  cmp     eax, 1
0x18002fbc8  jz      loc_18002FCFA
0x18002fbce  sub     esi, ecx
0x18002fbd0  lea     eax, [rsi-2]
0x18002fbd3  cmp     eax, r13d
0x18002fbd6  jge     loc_18002FCFA
0x18002fbdc  xor     r13d, r13d
0x18002fbdf  mov     [rbp+57h+var_88], r13
0x18002fbe3  mov     [rbp+57h+var_80], r13
0x18002fbe7  mov     [rbp+57h+arg_18], rbx
0x18002fbeb  mov     rcx, rbx; lpCriticalSection
0x18002fbee  call    cs:__imp_EnterCriticalSection
0x18002fbf4  nop
0x18002fbf5  test    esi, esi
0x18002fbf7  js      loc_18002FD36
0x18002fbfd  cmp     esi, [rbp+57h+nCount]
0x18002fc00  jge     loc_18002FD36
0x18002fc06  movsxd  rax, esi
0x18002fc09  mov     rsi, [r15+rax*8]
0x18002fc0d  mov     rcx, r12
0x18002fc10  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x18002fc15  mov     [rbp+57h+arg_10], rax
0x18002fc19  test    rax, rax
0x18002fc1c  jz      short loc_18002FC59
0x18002fc1e  lea     rdx, [rbp+57h+arg_10]
0x18002fc22  mov     rcx, r12
0x18002fc25  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x18002fc2a  mov     rbx, [rax]
0x18002fc2d  cmp     rsi, [rbx]
0x18002fc30  jz      short loc_18002FC38
0x18002fc32  mov     rax, [rbp+57h+arg_10]
0x18002fc36  jmp     short loc_18002FC19
0x18002fc38  lea     rdx, [rbx+10h]
0x18002fc3c  lea     rcx, [rbp+57h+var_88]
0x18002fc40  call    ??4?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::operator=(ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>> const &)
0x18002fc45  lea     rcx, [rbx+10h]
0x18002fc49  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002fc4e  xor     edx, edx; int
0x18002fc50  mov     rcx, rdi; this
0x18002fc53  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x18002fc58  nop
0x18002fc59  lea     rcx, [rbp+57h+arg_18]
0x18002fc5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002fc62  cmp     dword ptr [rbp+57h+var_80], r13d
0x18002fc66  jle     loc_18002FCEF
0x18002fc6c  lea     rcx, [rdi+58h]; lpCriticalSection
0x18002fc70  mov     [rbp+57h+arg_18], rcx
0x18002fc74  call    cs:__imp_EnterCriticalSection
0x18002fc7a  nop
0x18002fc7b  lea     rcx, [rdi+10h]
0x18002fc7f  call    ?GetStartPosition@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetStartPosition(void)
0x18002fc84  mov     [rbp+57h+arg_10], rax
0x18002fc88  test    rax, rax
0x18002fc8b  jz      short loc_18002FCCE
0x18002fc8d  lea     rdx, [rbp+57h+arg_10]
0x18002fc91  lea     rcx, [rdi+10h]
0x18002fc95  call    ?GetNextValue@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAAEAPEAVCStoreWatcher@CMapiManager@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::GetNextValue(__POSITION * &)
0x18002fc9a  mov     rsi, [rax]
0x18002fc9d  test    rsi, rsi
0x18002fca0  jz      short loc_18002FCC8
0x18002fca2  mov     ebx, r13d
0x18002fca5  cmp     dword ptr [rbp+57h+var_80], r13d
0x18002fca9  jle     short loc_18002FCC8
0x18002fcab  mov     edx, ebx
0x18002fcad  lea     rcx, [rbp+57h+var_88]
0x18002fcb1  call    ??A?$CSimpleArray@PEAVCMapiStore@@V?$CSimpleArrayEqualHelper@PEAVCMapiStore@@@ATL@@@ATL@@QEAAAEAPEAVCMapiStore@@H@Z; ATL::CSimpleArray<CMapiStore *,ATL::CSimpleArrayEqualHelper<CMapiStore *>>::operator[](int)
0x18002fcb6  mov     rdx, rax
0x18002fcb9  mov     rcx, rsi
0x18002fcbc  call    ?ReleaseStore@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::ReleaseStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002fcc1  inc     ebx
0x18002fcc3  cmp     ebx, dword ptr [rbp+57h+var_80]
0x18002fcc6  jl      short loc_18002FCAB
0x18002fcc8  cmp     [rbp+57h+arg_10], r13
0x18002fccc  jnz     short loc_18002FC8D
0x18002fcce  mov     rcx, rdi; this
0x18002fcd1  call    ?ReleaseUnusedSessions@CMapiManager@@QEAAXXZ; CMapiManager::ReleaseUnusedSessions(void)
0x18002fcd6  cmp     [rdi+18h], r13
0x18002fcda  jnz     short loc_18002FCE5
0x18002fcdc  mov     rcx, rdi; this
0x18002fcdf  call    ?SendShutdownNotification@CMapiManager@@AEAAXXZ; CMapiManager::SendShutdownNotification(void)
0x18002fce4  nop
0x18002fce5  lea     rcx, [rbp+57h+arg_18]
0x18002fce9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002fcee  nop
0x18002fcef  lea     rcx, [rbp+57h+var_88]
0x18002fcf3  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x18002fcf8  jmp     short loc_18002FD17
0x18002fcfa  xor     edx, edx; int
0x18002fcfc  mov     rcx, rdi; this
0x18002fcff  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x18002fd04  nop
0x18002fd05  xor     r13d, r13d
0x18002fd08  jmp     short loc_18002FD17
0x18002fd0a  mov     dword ptr [rdi+84h], 1
0x18002fd14  xor     r13d, r13d
0x18002fd17  test    r15, r15
0x18002fd1a  jz      short loc_18002FD29
0x18002fd1c  mov     rcx, r15; Block
0x18002fd1f  call    cs:__imp_free
0x18002fd25  mov     [rbp+57h+pHandles], r13
0x18002fd29  mov     qword ptr [rbp+57h+nCount], 0
0x18002fd31  jmp     loc_18002FA92
0x18002fd36  xor     r9d, r9d; lpArguments
0x18002fd39  xor     r8d, r8d; nNumberOfArguments
0x18002fd3c  lea     edx, [r9+1]; dwExceptionFlags
0x18002fd40  mov     ecx, 0C000008Ch; dwExceptionCode
0x18002fd45  call    cs:__imp_RaiseException
0x18002fd4b  nop
0x18002fd4c  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18002fd4f  mov     [rdi+0A0h], r13d
0x18002fd56  mov     rcx, rdi; this
0x18002fd59  call    ?Terminate@CMapiManager@@AEAAJXZ; CMapiManager::Terminate(void)
0x18002fd5e  test    r14d, r14d
0x18002fd61  js      short loc_18002FD69
0x18002fd63  call    cs:__imp_MAPIDeinitIdle
0x18002fd69  test    ebx, ebx
0x18002fd6b  js      short loc_18002FDA7
0x18002fd6d  lea     rcx, ?s_csMapiIdleThread@CMapiManager@@0VCriticalSection@@A; lpCriticalSection
0x18002fd74  mov     [rbp+57h+arg_0], rcx
0x18002fd78  call    cs:__imp_EnterCriticalSection
0x18002fd7e  nop
0x18002fd7f  lea     rcx, aCmapimanagerUn_0; "   CMapiManager::UninitializeThread() M"...
0x18002fd86  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002fd8b  call    cs:__imp_MAPIUninitialize
0x18002fd91  lea     rcx, aCmapimanagerUn; "   CMapiManager::UninitializeThread() M"...
0x18002fd98  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002fd9d  nop
0x18002fd9e  lea     rcx, [rbp+57h+arg_0]
0x18002fda2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002fda7  call    cs:__imp_CoUninitialize
0x18002fdad  mov     [rdi+80h], r13d
0x18002fdb4  lea     rdx, aCmapimanagerRu_0; "CMapiManager::RunMapiIdleThread() Exit"
0x18002fdbb  mov     ecx, r14d; int
0x18002fdbe  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002fdc3  nop
0x18002fdc4  mov     rcx, [rbp+57h+arg_8]
0x18002fdc8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fdcc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fdd1  mov     eax, r14d
0x18002fdd4  add     rsp, 98h
0x18002fddb  pop     r15
0x18002fddd  pop     r14
0x18002fddf  pop     r13
0x18002fde1  pop     r12
0x18002fde3  pop     rdi
0x18002fde4  pop     rsi
0x18002fde5  pop     rbx
0x18002fde6  pop     rbp
0x18002fde7  retn
```

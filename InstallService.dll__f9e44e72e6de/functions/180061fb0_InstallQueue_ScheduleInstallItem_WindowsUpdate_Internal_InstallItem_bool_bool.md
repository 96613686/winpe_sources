# InstallQueue::_ScheduleInstallItem(WindowsUpdate::Internal::InstallItem *,bool,bool)

- ea: `0x180061fb0`
- end: `0x18006271e`
- name: `?_ScheduleInstallItem@InstallQueue@@AEAAJPEAVInstallItem@Internal@WindowsUpdate@@_N1@Z`
- size: `1902`
- prototype: `int(InstallQueue *__hidden this, struct WindowsUpdate::Internal::InstallItem *, bool, bool)`
- caller_count: `10`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800555f0`
- `0x180058d80`
- `0x18005906c`
- `0x18005920c`
- `0x18005a9a4`
- `0x18005c338`
- `0x18005c990`
- `0x18005e49c`
- `0x18005fa9c`
- `0x180062724`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x1800123f8`
- `0x180012428`
- `0x18001448c`
- `0x1800144ac`
- `0x18001c414`
- `0x180028cd4`
- `0x18002d98c`
- `0x18004ce5c`
- `0x1800532fc`
- `0x180056bdc`
- `0x18005a910`
- `0x18005b630`
- `0x18005cf90`
- `0x180061fb0`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180062421`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180062421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006203a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800622a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006233e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800625b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006264d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006203a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800622a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006233e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800625b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006264d`

## string_xrefs

- `0x180062075`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800620d7`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180062139`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180062194`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800621a5`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800623a5`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180062054`: `Ignoring work scheduling request. Work Already scheduled with productId = %s, Requested productId = %s`
- `0x180062068`: `InstallQueue::_ScheduleInstallItem`
- `0x18006212c`: `InstallQueue::_ScheduleInstallItem`
- `0x1800621ed`: `InstallQueue::_ScheduleInstallItem`
- `0x18006223e`: `InstallQueue::_ScheduleInstallItem`
- `0x1800622cd`: `InstallQueue::_ScheduleInstallItem`
- `0x18006247d`: `InstallQueue::_ScheduleInstallItem`
- `0x1800625df`: `InstallQueue::_ScheduleInstallItem`
- `0x180062676`: `InstallQueue::_ScheduleInstallItem`
- `0x180062118`: `Ignoring Scheduling request productId = %s. Not ready`
- `0x1800621c3`: `static_cast<InstallItem*>(mapItem.Get()) == pItem`
- `0x180062229`: `Something bad happend. The item in the queue is not the same as the one scheduled. Ignoring scheduling request for productId = %s`
- `0x180062349`: `Ignoring Scheduling request productId = %s. Already in pending queue`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall InstallQueue::_ScheduleInstallItem(
        RTL_SRWLOCK *this,
        struct WindowsUpdate::Internal::InstallItem *a2,
        char a3,
        char a4)
{
  struct WindowsUpdate::Internal::InstallItem *v4; // r15
  RTL_SRWLOCK *v6; // rdi
  PCWSTR v7; // rbx
  PCWSTR v8; // rax
  int IsReady; // eax
  unsigned int v10; // ebx
  HSTRING *v12; // r12
  PCWSTR StringRawBuffer; // rax
  PVOID Ptr; // rdi
  __int64 (__fastcall *v15)(PVOID, HSTRING, HSTRING **); // rbx
  int v16; // eax
  __int64 v17; // rdx
  PCWSTR v18; // rax
  _QWORD *v19; // rcx
  _QWORD *i; // rax
  char v21; // bl
  const unsigned __int16 *v22; // rax
  unsigned int v23; // r8d
  RTL_SRWLOCK *v24; // rdi
  const char *v25; // r9
  const wchar_t *v26; // rax
  unsigned int j; // r13d
  PVOID v28; // rdi
  __int64 (__fastcall *v29)(PVOID, _QWORD, HSTRING **); // rbx
  int v30; // eax
  HSTRING *v31; // rbx
  int v32; // [rsp+20h] [rbp-A8h]
  PCWSTR v33; // [rsp+40h] [rbp-88h]
  const char *v34; // [rsp+48h] [rbp-80h]
  bool v35[4]; // [rsp+50h] [rbp-78h] BYREF
  int v36; // [rsp+54h] [rbp-74h] BYREF
  HSTRING *v37; // [rsp+58h] [rbp-70h] BYREF
  HSTRING *v38; // [rsp+60h] [rbp-68h] BYREF
  struct WindowsUpdate::Internal::InstallItem *v39; // [rsp+68h] [rbp-60h] BYREF
  RTL_SRWLOCK *v40; // [rsp+70h] [rbp-58h]
  char v41[8]; // [rsp+78h] [rbp-50h] BYREF
  ScheduledTask *v42; // [rsp+80h] [rbp-48h] BYREF
  std::_Ref_count_base *v43; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  struct WindowsUpdate::Internal::InstallItem *v46; // [rsp+D8h] [rbp+10h] BYREF
  char v47; // [rsp+E0h] [rbp+18h]
  char v48; // [rsp+E8h] [rbp+20h]

  v48 = a4;
  v47 = a3;
  v46 = a2;
  v4 = a2;
  v6 = this + 24;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&v39, &this[24]);
  v38 = 0;
  v40 = this + 26;
  if ( (int)CollectionHelpers::Find_WindowsUpdate::Internal::IInstallItem__lambda_a46043cc63570498c982afaadbd9fe90___(
              this[26].Ptr,
              &v38,
              v4) < 0 )
  {
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v39);
    v35[0] = 0;
    IsReady = WindowsUpdate::Internal::InstallItem::IsReady(v4, v35);
    v10 = IsReady;
    if ( IsReady < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x548,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)IsReady,
        v32);
      return v10;
    }
    v12 = (HSTRING *)((char *)v4 + 248);
    if ( !v35[0] )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*v12, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x54Cu,
        "InstallQueue::_ScheduleInstallItem",
        -1,
        L"Ignoring Scheduling request productId = %s. Not ready",
        0,
        0,
        StringRawBuffer);
      return 0;
    }
    wil::AcquireSRWLockExclusive(v41, v6);
    v38 = 0;
    Ptr = this[25].Ptr;
    v15 = *(__int64 (__fastcall **)(PVOID, HSTRING, HSTRING **))(*(_QWORD *)Ptr + 48LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    v16 = v15(Ptr, *v12, &v38);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 1364;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v16,
        v32);
      goto LABEL_52;
    }
    if ( v38 != (HSTRING *)v4 )
    {
      v34 = L"Failed";
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x555u,
        "InstallQueue::_ScheduleInstallItem",
        -1,
        L"Assert (%s): %s",
        0,
        0);
      if ( v38 != (HSTRING *)v4 )
      {
        v18 = WindowsGetStringRawBuffer(*v12, 0);
        v10 = -2147418113;
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          0x559u,
          "InstallQueue::_ScheduleInstallItem",
          -2147418113,
          L"Something bad happend. The item in the queue is not the same as the one scheduled. Ignoring scheduling request"
           " for productId = %s",
          0,
          0,
          v18,
          L"Failed");
LABEL_52:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v41);
        return v10;
      }
    }
    v37 = (HSTRING *)((char *)v4 + 248);
    v39 = v4;
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v39);
    v19 = this[27].Ptr;
    for ( i = (_QWORD *)*v19; i != v19; i = (_QWORD *)*i )
    {
      if ( (struct WindowsUpdate::Internal::InstallItem *)i[2] == v4 )
      {
        v21 = 1;
        goto LABEL_19;
      }
    }
    v21 = 0;
LABEL_19:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
    if ( v21 )
    {
      v33 = WindowsGetStringRawBuffer(*v12, 0);
      v22 = L"Ignoring Scheduling request productId = %s. Still Active";
      v23 = 1375;
LABEL_21:
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        v23,
        "InstallQueue::_ScheduleInstallItem",
        -1,
        v22,
        0,
        0,
        v33,
        v34);
      v10 = 0;
      goto LABEL_52;
    }
    v24 = this + 26;
    v39 = (struct WindowsUpdate::Internal::InstallItem *)&this[26];
    v36 = 0;
    v35[0] = 0;
    v16 = (*(__int64 (__fastcall **)(PVOID, struct WindowsUpdate::Internal::InstallItem *, int *, bool *))(*(_QWORD *)this[26].Ptr + 72LL))(
            this[26].Ptr,
            v4,
            &v36,
            v35);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 1382;
      goto LABEL_51;
    }
    if ( v35[0] )
    {
      v33 = WindowsGetStringRawBuffer(*v12, 0);
      v22 = L"Ignoring Scheduling request productId = %s. Already in pending queue";
      v23 = 1385;
      goto LABEL_21;
    }
    try
    {
      InstallServiceTasks::SmartRetry(&v42);
      ScheduledTask::SetTriggerEnabled(v42, L"PostBoot", 1);
      ScheduledTask::CommitChanges(v42);
      if ( v43 )
        std::_Ref_count_base::_Decref(v43);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x573,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        v25);
      v4 = v46;
      v12 = v37;
      v24 = (RTL_SRWLOCK *)v39;
      v40 = (RTL_SRWLOCK *)v39;
    }
    if ( !v47 )
    {
      if ( *((_DWORD *)v4 + 70) != 1 )
      {
LABEL_34:
        _m_prefetchw((char *)v4 + 312);
        if ( (_InterlockedOr((volatile signed __int32 *)v4 + 78, 0) & 1) != 0 )
        {
          LODWORD(v46) = 0;
          v16 = (*(__int64 (__fastcall **)(PVOID, struct WindowsUpdate::Internal::InstallItem **))(*(_QWORD *)v24->Ptr
                                                                                                 + 56LL))(
                  v24->Ptr,
                  &v46);
          v10 = v16;
          if ( v16 >= 0 )
          {
            for ( j = 0; j < (unsigned int)v46; ++j )
            {
              v37 = 0;
              v28 = v24->Ptr;
              v29 = *(__int64 (__fastcall **)(PVOID, _QWORD, HSTRING **))(*(_QWORD *)v28 + 48LL);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
              v30 = v29(v28, j, &v37);
              v10 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x58A,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
                  (const char *)(unsigned int)v30,
                  v32);
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
                goto LABEL_52;
              }
              v31 = v37;
              v39 = (struct WindowsUpdate::Internal::InstallItem *)v37;
              Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v39);
              _m_prefetchw(v31 + 39);
              if ( (_InterlockedOr((volatile signed __int32 *)v31 + 78, 0) & 1) == 0 || *((_DWORD *)v4 + 70) == 1 )
              {
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
                v24 = v40;
                break;
              }
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v37);
              v24 = v40;
            }
            WindowsGetStringRawBuffer(*v12, 0);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
              0x592u,
              "InstallQueue::_ScheduleInstallItem",
              -1,
              L"Scheduling productId = %s. Inserting at Index = %d",
              0,
              0);
            v16 = (*(__int64 (__fastcall **)(PVOID, _QWORD, struct WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v24->Ptr + 88LL))(
                    v24->Ptr,
                    j,
                    v4);
            v10 = v16;
            if ( v16 >= 0 )
              goto LABEL_53;
            v17 = 1427;
          }
          else
          {
            v17 = 1413;
          }
          goto LABEL_51;
        }
LABEL_35:
        WindowsGetStringRawBuffer(*v12, 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          0x57Du,
          "InstallQueue::_ScheduleInstallItem",
          -1,
          L"Scheduling productId = %s. Inserting at the end of the queue",
          0,
          0);
        v16 = (*(__int64 (__fastcall **)(PVOID, struct WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v24->Ptr
                                                                                              + 104LL))(
                v24->Ptr,
                v4);
        v10 = v16;
        if ( v16 < 0 )
        {
          v17 = 1407;
          goto LABEL_51;
        }
LABEL_53:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v41);
        if ( v48 )
          InstallQueue::_ExecuteInstallItems(this);
        return 0;
      }
      _m_prefetchw((char *)v4 + 312);
      if ( (_InterlockedOr((volatile signed __int32 *)v4 + 78, 0) & 0x10) == 0 )
      {
        if ( *((_DWORD *)v4 + 70) == 1 )
        {
          v26 = WindowsGetStringRawBuffer(*v12, 0);
          if ( !wcsstr(L"9WZDNCRFJBMP|9NBLGGH4LS1F", v26) )
            goto LABEL_35;
        }
        goto LABEL_34;
      }
    }
    WindowsGetStringRawBuffer(*v12, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      0x577u,
      "InstallQueue::_ScheduleInstallItem",
      -1,
      L"Scheduling productId = %s. Inserting at the top of the queue",
      0,
      0);
    v16 = (*(__int64 (__fastcall **)(PVOID, _QWORD, struct WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v24->Ptr
                                                                                                  + 88LL))(
            v24->Ptr,
            0,
            v4);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 1401;
      goto LABEL_51;
    }
    goto LABEL_53;
  }
  v7 = WindowsGetStringRawBuffer(*((HSTRING *)v4 + 31), 0);
  v8 = WindowsGetStringRawBuffer(v38[31], 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
    0x542u,
    "InstallQueue::_ScheduleInstallItem",
    -1,
    L"Ignoring work scheduling request. Work Already scheduled with productId = %s, Requested productId = %s",
    0,
    0,
    v8,
    v7);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v39);
  return 0;
}

```

## disassembly

```asm
0x180061fb0  mov     rax, rsp
0x180061fb3  mov     [rax+20h], r9b
0x180061fb7  mov     [rax+18h], r8b
0x180061fbb  mov     [rax+10h], rdx
0x180061fbf  mov     [rax+8], rcx
0x180061fc3  push    rbx
0x180061fc4  push    rsi
0x180061fc5  push    rdi
0x180061fc6  push    r12
0x180061fc8  push    r13
0x180061fca  push    r14
0x180061fcc  push    r15
0x180061fce  sub     rsp, 90h
0x180061fd5  mov     r15, rdx
0x180061fd8  mov     r13, rcx
0x180061fdb  lea     rdi, [rcx+0C0h]
0x180061fe2  mov     rdx, rdi
0x180061fe5  lea     rcx, [rax-60h]
0x180061fe9  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180061fee  nop
0x180061fef  xor     esi, esi
0x180061ff1  mov     [rsp+0C8h+var_68], rsi
0x180061ff6  lea     rcx, [r13+0D0h]
0x180061ffd  mov     [rsp+0C8h+var_58], rcx
0x180062002  mov     r8, r15
0x180062005  lea     rdx, [rsp+0C8h+var_68]
0x18006200a  mov     rcx, [rcx]
0x18006200d  call    CollectionHelpers__Find_WindowsUpdate__Internal__IInstallItem__lambda_a46043cc63570498c982afaadbd9fe90___
0x180062012  test    eax, eax
0x180062014  js      loc_18006209F
0x18006201a  xor     edx, edx; length
0x18006201c  mov     rcx, [r15+0F8h]; string
0x180062023  call    cs:__imp_WindowsGetStringRawBuffer
0x180062029  mov     rbx, rax
0x18006202c  xor     edx, edx; length
0x18006202e  mov     rcx, [rsp+0C8h+var_68]
0x180062033  mov     rcx, [rcx+0F8h]; string
0x18006203a  call    cs:__imp_WindowsGetStringRawBuffer
0x180062040  mov     [rsp+0C8h+var_80], rbx
0x180062045  mov     [rsp+0C8h+var_88], rax
0x18006204a  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x18006204f  mov     [rsp+0C8h+var_98], rsi; char *
0x180062054  lea     rax, aIgnoringWorkSc; "Ignoring work scheduling request. Work "...
0x18006205b  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180062060  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x180062068  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x18006206f  mov     r8d, 542h; unsigned int
0x180062075  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18006207c  lea     ecx, [rsi+3]; unsigned int
0x18006207f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180062084  nop
0x180062085  lea     rcx, [rsp+0C8h+var_68]
0x18006208a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006208f  nop
0x180062090  lea     rcx, [rsp+0C8h+var_60]
0x180062095  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006209a  jmp     loc_180062709
0x18006209f  lea     rcx, [rsp+0C8h+var_68]
0x1800620a4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800620a9  nop
0x1800620aa  lea     rcx, [rsp+0C8h+var_60]
0x1800620af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,0>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800620b4  mov     [rsp+0C8h+var_78], sil
0x1800620b9  lea     rdx, [rsp+0C8h+var_78]; bool *
0x1800620be  mov     rcx, r15; this
0x1800620c1  call    ?IsReady@InstallItem@Internal@WindowsUpdate@@QEAAJPEA_N@Z; WindowsUpdate::Internal::InstallItem::IsReady(bool *)
0x1800620c6  mov     ebx, eax
0x1800620c8  test    eax, eax
0x1800620ca  jns     short loc_1800620EF
0x1800620cc  mov     rcx, [rsp+0C8h]; this
0x1800620d4  mov     r9d, eax; char *
0x1800620d7  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800620de  mov     edx, 548h; void *
0x1800620e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800620e8  mov     eax, ebx
0x1800620ea  jmp     loc_18006270B
0x1800620ef  lea     r12, [r15+0F8h]
0x1800620f6  cmp     [rsp+0C8h+var_78], sil
0x1800620fb  jnz     short loc_18006214F
0x1800620fd  xor     edx, edx; length
0x1800620ff  mov     rcx, [r12]; string
0x180062103  call    cs:__imp_WindowsGetStringRawBuffer
0x180062109  mov     [rsp+0C8h+var_88], rax
0x18006210e  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x180062113  mov     [rsp+0C8h+var_98], rsi; char *
0x180062118  lea     rax, aIgnoringSchedu_0; "Ignoring Scheduling request productId ="...
0x18006211f  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180062124  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x18006212c  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x180062133  mov     r8d, 54Ch; unsigned int
0x180062139  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x180062140  mov     ecx, 3; unsigned int
0x180062145  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18006214a  jmp     loc_180062709
0x18006214f  mov     rdx, rdi
0x180062152  lea     rcx, [rsp+0C8h+var_50]
0x180062157  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18006215c  nop
0x18006215d  mov     [rsp+0C8h+var_68], rsi
0x180062162  mov     rdi, [r13+0C8h]
0x180062169  mov     rax, [rdi]
0x18006216c  mov     rbx, [rax+30h]
0x180062170  lea     rcx, [rsp+0C8h+var_68]
0x180062175  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006217a  lea     r8, [rsp+0C8h+var_68]
0x18006217f  mov     rdx, [r12]
0x180062183  mov     rcx, rdi
0x180062186  mov     rax, rbx
0x180062189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006218e  mov     ebx, eax
0x180062190  test    eax, eax
0x180062192  jns     short loc_1800621A5
0x180062194  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18006219b  mov     edx, 554h
0x1800621a0  jmp     loc_1800626B2
0x1800621a5  lea     r14, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800621ac  cmp     [rsp+0C8h+var_68], r15
0x1800621b1  jz      loc_18006225D
0x1800621b7  lea     rax, aFailed_1; "Failed"
0x1800621be  mov     [rsp+0C8h+var_80], rax
0x1800621c3  lea     rax, aStaticCastInst; "static_cast<InstallItem*>(mapItem.Get()"...
0x1800621ca  mov     [rsp+0C8h+var_88], rax
0x1800621cf  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x1800621d4  mov     [rsp+0C8h+var_98], rsi; char *
0x1800621d9  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800621e0  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x1800621e5  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x1800621ed  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x1800621f4  mov     r8d, 555h; unsigned int
0x1800621fa  mov     rdx, r14; char *
0x1800621fd  mov     ecx, 1; unsigned int
0x180062202  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180062207  cmp     [rsp+0C8h+var_68], r15
0x18006220c  jz      short loc_18006225D
0x18006220e  xor     edx, edx; length
0x180062210  mov     rcx, [r12]; string
0x180062214  call    cs:__imp_WindowsGetStringRawBuffer
0x18006221a  mov     [rsp+0C8h+var_88], rax
0x18006221f  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x180062224  mov     [rsp+0C8h+var_98], rsi; char *
0x180062229  lea     rax, aSomethingBadHa; "Something bad happend. The item in the "...
0x180062230  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180062235  mov     ebx, 8000FFFFh
0x18006223a  mov     [rsp+0C8h+var_A8], ebx; int
0x18006223e  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x180062245  mov     r8d, 559h; unsigned int
0x18006224b  mov     rdx, r14; char *
0x18006224e  mov     ecx, 1; unsigned int
0x180062253  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180062258  jmp     loc_1800626C3
0x18006225d  mov     [rsp+0C8h+var_70], r12
0x180062262  mov     [rsp+0C8h+var_60], r15
0x180062267  lea     rcx, [rsp+0C8h+var_60]
0x18006226c  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x180062271  mov     rcx, [r13+0D8h]
0x180062278  mov     rax, [rcx]
0x18006227b  cmp     rax, rcx
0x18006227e  jz      short loc_18006228F
0x180062280  cmp     [rax+10h], r15
0x180062284  jz      short loc_18006228B
0x180062286  mov     rax, [rax]
0x180062289  jmp     short loc_18006227B
0x18006228b  mov     bl, 1
0x18006228d  jmp     short loc_180062292
0x18006228f  mov     bl, sil
0x180062292  lea     rcx, [rsp+0C8h+var_60]
0x180062297  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18006229c  test    bl, bl
0x18006229e  jz      short loc_1800622F0
0x1800622a0  xor     edx, edx; length
0x1800622a2  mov     rcx, [r12]; string
0x1800622a6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800622ac  mov     [rsp+0C8h+var_88], rax
0x1800622b1  lea     rax, aIgnoringSchedu; "Ignoring Scheduling request productId ="...
0x1800622b8  mov     r8d, 55Fh; unsigned int
0x1800622be  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x1800622c3  mov     [rsp+0C8h+var_98], rsi; char *
0x1800622c8  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x1800622cd  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x1800622d4  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x1800622dc  mov     rdx, r14; char *
0x1800622df  mov     ecx, 3; unsigned int
0x1800622e4  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800622e9  mov     ebx, esi
0x1800622eb  jmp     loc_1800626C3
0x1800622f0  lea     rdi, [r13+0D0h]
0x1800622f7  mov     [rsp+0C8h+var_60], rdi
0x1800622fc  mov     [rsp+0C8h+var_74], esi
0x180062300  mov     [rsp+0C8h+var_78], sil
0x180062305  mov     rcx, [rdi]
0x180062308  mov     rax, [rcx]
0x18006230b  lea     r9, [rsp+0C8h+var_78]
0x180062310  lea     r8, [rsp+0C8h+var_74]
0x180062315  mov     rdx, r15
0x180062318  mov     rax, [rax+48h]
0x18006231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062321  mov     ebx, eax
0x180062323  test    eax, eax
0x180062325  jns     short loc_180062331
0x180062327  mov     edx, 566h
0x18006232c  jmp     loc_1800626AF
0x180062331  cmp     [rsp+0C8h+var_78], sil
0x180062336  jz      short loc_18006235B
0x180062338  xor     edx, edx; length
0x18006233a  mov     rcx, [r12]; string
0x18006233e  call    cs:__imp_WindowsGetStringRawBuffer
0x180062344  mov     [rsp+0C8h+var_88], rax
0x180062349  lea     rax, aIgnoringSchedu_1; "Ignoring Scheduling request productId ="...
0x180062350  mov     r8d, 569h
0x180062356  jmp     loc_1800622BE
0x18006235b  lea     rcx, [rsp+0C8h+var_48]
0x180062363  call    ?SmartRetry@InstallServiceTasks@@YA?AV?$shared_ptr@VScheduledTask@@@std@@XZ; InstallServiceTasks::SmartRetry(void)
0x180062368  nop
0x180062369  mov     r8b, 1; bool
0x18006236c  lea     rdx, aPostboot; "PostBoot"
0x180062373  mov     rcx, [rsp+0C8h+var_48]; this
0x18006237b  call    ?SetTriggerEnabled@ScheduledTask@@QEAAXPEBG_N@Z; ScheduledTask::SetTriggerEnabled(ushort const *,bool)
0x180062380  mov     rcx, [rsp+0C8h+var_48]; this
0x180062388  call    ?CommitChanges@ScheduledTask@@QEAAXXZ; ScheduledTask::CommitChanges(void)
0x18006238d  nop
0x18006238e  mov     rcx, [rsp+0C8h+var_40]; this
0x180062396  test    rcx, rcx
0x180062399  jz      short loc_1800623A1
0x18006239b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800623a0  nop
0x1800623a1  jmp     short loc_1800623C3
0x1800623a3  xor     esi, esi
0x1800623a5  lea     r14, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800623ac  mov     r15, [rsp+0C8h+arg_8]
0x1800623b4  mov     r12, [rsp+0C8h+var_70]
0x1800623b9  mov     rdi, [rsp+0C8h+var_60]
0x1800623be  mov     [rsp+0C8h+var_58], rdi
0x1800623c3  cmp     [rsp+0C8h+arg_10], sil
0x1800623cb  jnz     loc_180062647
0x1800623d1  cmp     dword ptr [r15+118h], 1
0x1800623d9  jnz     short loc_18006242C
0x1800623db  prefetchw byte ptr [r15+138h]
0x1800623e3  mov     eax, [r15+138h]
0x1800623ea  mov     ecx, eax
0x1800623ec  or      ecx, esi
0x1800623ee  lock cmpxchg [r15+138h], ecx
0x1800623f7  jnz     short loc_1800623EA
0x1800623f9  test    al, 10h
0x1800623fb  jnz     loc_180062647
0x180062401  cmp     dword ptr [r15+118h], 1
0x180062409  jnz     short loc_18006242C
0x18006240b  xor     edx, edx; length
0x18006240d  mov     rcx, [r12]; string
0x180062411  call    cs:__imp_WindowsGetStringRawBuffer
0x180062417  mov     rdx, rax; SubStr
0x18006241a  lea     rcx, a9wzdncrfjbmp9n; "9WZDNCRFJBMP|9NBLGGH4LS1F"
0x180062421  call    cs:__imp_wcsstr
0x180062427  test    rax, rax
0x18006242a  jz      short loc_18006244E
0x18006242c  prefetchw byte ptr [r15+138h]
0x180062434  mov     eax, [r15+138h]
0x18006243b  mov     ecx, eax
0x18006243d  or      ecx, esi
0x18006243f  lock cmpxchg [r15+138h], ecx
0x180062448  jnz     short loc_18006243B
0x18006244a  test    al, 1
0x18006244c  jnz     short loc_1800624BD
0x18006244e  xor     edx, edx; length
0x180062450  mov     rcx, [r12]; string
0x180062454  call    cs:__imp_WindowsGetStringRawBuffer
0x18006245a  mov     [rsp+0C8h+var_88], rax
0x18006245f  mov     [rsp+0C8h+var_90], rsi; unsigned __int16 *
0x180062464  mov     [rsp+0C8h+var_98], rsi; char *
0x180062469  lea     rax, aSchedulingProd_0; "Scheduling productId = %s. Inserting at"...
0x180062470  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180062475  mov     [rsp+0C8h+var_A8], 0FFFFFFFFh; int
0x18006247d  lea     r9, aInstallqueueSc; "InstallQueue::_ScheduleInstallItem"
0x180062484  mov     r8d, 57Dh; unsigned int
0x18006248a  mov     rdx, r14; char *
0x18006248d  mov     ecx, 3; unsigned int
0x180062492  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180062497  mov     rcx, [rdi]
0x18006249a  mov     rax, [rcx]
0x18006249d  mov     rdx, r15
0x1800624a0  mov     rax, [rax+68h]
0x1800624a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624a9  mov     ebx, eax
0x1800624ab  test    eax, eax
0x1800624ad  jns     loc_1800626DD
0x1800624b3  mov     edx, 57Fh
0x1800624b8  jmp     loc_1800626AF
0x1800624bd  mov     dword ptr [rsp+0C8h+arg_8], esi
0x1800624c4  mov     rcx, [rdi]
0x1800624c7  mov     rax, [rcx]
0x1800624ca  lea     rdx, [rsp+0C8h+arg_8]
0x1800624d2  mov     rax, [rax+38h]
0x1800624d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624db  mov     ebx, eax
0x1800624dd  test    eax, eax
0x1800624df  jns     short loc_1800624EB
0x1800624e1  mov     edx, 585h
0x1800624e6  jmp     loc_1800626AF
0x1800624eb  mov     r13d, esi
0x1800624ee  cmp     r13d, dword ptr [rsp+0C8h+arg_8]
0x1800624f6  jnb     loc_1800625AB
  ... truncated ...
```

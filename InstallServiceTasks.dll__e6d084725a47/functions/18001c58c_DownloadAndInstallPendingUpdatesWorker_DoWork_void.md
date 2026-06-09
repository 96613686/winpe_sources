# DownloadAndInstallPendingUpdatesWorker::DoWork(void)

- ea: `0x18001c58c`
- end: `0x18001cab2`
- name: `?DoWork@DownloadAndInstallPendingUpdatesWorker@@QEAAXXZ`
- size: `1318`
- prototype: `void __fastcall(DownloadAndInstallPendingUpdatesWorker *__hidden this)`
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800101d0`
- `0x180016044`

## callees

- `0x180003450`
- `0x180003948`
- `0x180005c74`
- `0x18000760c`
- `0x18000b50c`
- `0x18000c520`
- `0x18000d544`
- `0x18000e958`
- `0x18000fd08`
- `0x180010150`
- `0x1800109dc`
- `0x180012118`
- `0x180012f10`
- `0x180013eb4`
- `0x180019f10`
- `0x18001a244`
- `0x18001a264`
- `0x18001a35c`
- `0x18001a4a4`
- `0x18001aba0`
- `0x18001b66c`
- `0x18001ba4c`
- `0x18001babc`
- `0x18001c43c`
- `0x18001c498`
- `0x18001c58c`
- `0x18001d008`
- `0x18001d4e0`
- `0x18001efc4`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Thrd_id` at `0x18001c9cd`
- `msvcp_win!_Thrd_id` at `0x18001c9cd`
- `msvcp_win!_Thrd_join` at `0x18001c9f5`
- `msvcp_win!_Thrd_join` at `0x18001c9f5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c9dd`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ca04`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ca9b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001caab`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001c9dd`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ca04`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001ca9b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001caab`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001c89a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001c89a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001c928`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001c928`

## string_xrefs

- `0x18001c5f6`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c67f`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c6b9`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c712`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c909`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c959`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001c5e9`: `DownloadAndInstallPendingUpdatesWorker::DoWork`
- `0x18001c8fc`: `DownloadAndInstallPendingUpdatesWorker::DoWork`
- `0x18001c94c`: `DownloadAndInstallPendingUpdatesWorker::DoWork`
- `0x18001c5d5`: `No Updates found. Nothing to do`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
void __fastcall DownloadAndInstallPendingUpdatesWorker::DoWork(DownloadAndInstallPendingUpdatesWorker *this)
{
  bool HasUpdates; // bl
  __int64 *v3; // rax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, void **); // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD); // rbx
  int v10; // eax
  _OWORD *v11; // rdi
  int i; // eax
  void *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  AppInstallItemTracker **j; // rsi
  AppInstallItemTracker **v18; // r15
  AppInstallItemTracker *v19; // rbx
  void *v20; // rdx
  bool v21; // al
  int v22; // [rsp+20h] [rbp-E0h]
  _Thrd_t v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  void *v25; // [rsp+68h] [rbp-98h] BYREF
  __int128 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h]
  char v28; // [rsp+89h] [rbp-77h]
  void *v29; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h] BYREF
  _Thrd_t v31; // [rsp+A0h] [rbp-60h] BYREF
  void *v32; // [rsp+B0h] [rbp-50h] BYREF
  int v33; // [rsp+B8h] [rbp-48h]
  __int64 v34; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v36[2]; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v38; // [rsp+F8h] [rbp-8h]
  HANDLE Handles[3]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  HasUpdates = InstallQueueHasUpdates();
  UpdateTaskTriggers(HasUpdates);
  if ( !HasUpdates )
  {
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      0xFCu,
      "DownloadAndInstallPendingUpdatesWorker::DoWork",
      -1,
      L"No Updates found. Nothing to do",
      0,
      0);
    return;
  }
  v28 = 1;
  v3 = (__int64 *)wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(&v23);
  v4 = *v3;
  *v3 = 0;
  v35 = v4;
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v23);
  v25 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v6 = v5(v4, &v25);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v6,
      v22);
  v30 = 0;
  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v4)(
         v4,
         &GUID_20e1713b_cbcc_442d_b441_6440689b8912,
         &v30);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v7,
      v22);
  v8 = v30;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v30 + 48LL);
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"EDUPendingDownload", 0x13u, 0x12u);
  v10 = v9(v8, v38, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
      (const char *)(unsigned int)v10,
      v22);
  v11 = operator new(0x40u);
  v23._Hnd = v11;
  *v11 = 0;
  *((_DWORD *)v11 + 2) = 1;
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<GlobalTrackerWithTimeoutAndCancel>::`vftable';
  std::_Construct_in_place<GlobalTrackerWithTimeoutAndCancel,unsigned long const &>(v11 + 1, "0u");
  v36[0] = v11 + 1;
  v36[1] = v11;
  std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(&v26);
  v23._Hnd = v25;
  v32 = v25;
  v33 = 0;
  v34 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,wil::err_exception_policy>::end(
    &v23,
    &hstringHeader);
  for ( i = v33; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v33 )
  {
    v13 = *(void **)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,wil::err_exception_policy>::vector_iterator::operator*(&v32);
    v23._Hnd = v13;
    if ( v13 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
    v14 = Microsoft::WRL::Details::Make<AppInstallItemTracker,std::shared_ptr<GlobalTrackerWithTimeoutAndCancel> &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem> &>(
            &v24,
            v36,
            &v23);
    if ( *((_QWORD *)&v26 + 1) == v27 )
    {
      std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(
        &v26,
        *((_QWORD *)&v26 + 1),
        v14);
    }
    else
    {
      std::_Construct_in_place<Microsoft::WRL::ComPtr<AppInstallItemTracker>,Microsoft::WRL::ComPtr<AppInstallItemTracker>>(
        *((_QWORD *)&v26 + 1),
        v14);
      *((_QWORD *)&v26 + 1) += 8LL;
    }
    v15 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  LODWORD(v24) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    &v29,
    &v24);
  v16 = operator new(0x10u);
  *v16 = &v26;
  v16[1] = &v29;
  v23._Hnd = v16;
  v31._Hnd = (void *)_o__beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke_std::tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____0_,
                       v16,
                       0,
                       &v31._Id);
  if ( !v31._Hnd )
  {
LABEL_36:
    v31._Id = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18001CAB1LL);
  }
  v23._Hnd = 0;
  std::unique_ptr_std::tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____std::default_delete_std::tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8_______::_unique_ptr_std::tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____std::default_delete_std::tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8_______(&v23);
  Handles[0] = v29;
  Handles[1] = *((HANDLE *)v11 + 6);
  Handles[2] = *((HANDLE *)this + 1);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
    0x127u,
    "DownloadAndInstallPendingUpdatesWorker::DoWork",
    -1,
    L"Waiting for Items to finish or Cancel or Inactivity. Max Timeout in Ms:%d",
    0,
    0,
    1800000);
  WaitForMultipleObjects(3u, Handles, 0, 0x1B7740u);
  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
    0x12Bu,
    "DownloadAndInstallPendingUpdatesWorker::DoWork",
    -1,
    L"Wait Over. Cleaning up and exiting.",
    0,
    0);
  v18 = (AppInstallItemTracker **)*((_QWORD *)&v26 + 1);
  for ( j = (AppInstallItemTracker **)v26; j != v18; ++j )
  {
    v19 = *j;
    if ( *j )
      (*(void (__fastcall **)(AppInstallItemTracker *))(*(_QWORD *)v19 + 8LL))(*j);
    AppInstallItemTracker::Cleanup(v19);
    if ( v19 )
      (*(void (__fastcall **)(AppInstallItemTracker *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  GlobalTrackerWithTimeoutAndCancel::Cleanup((GlobalTrackerWithTimeoutAndCancel *)(v11 + 1));
  wil::details::SetEvent(*((wil::details **)this + 1), v20);
  if ( !v31._Id )
  {
    std::_Throw_Cpp_error(1);
    goto LABEL_36;
  }
  if ( v31._Id == _Thrd_id() )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  v23 = v31;
  if ( _Thrd_join(&v23, 0) )
  {
    std::_Throw_Cpp_error(2);
    __debugbreak();
  }
  v31 = 0;
  std::thread::~thread((std::thread *)&v31);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
  if ( (_QWORD)v26 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<AppInstallItemTracker>>>(v26, *((_QWORD *)&v26 + 1));
    std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
    v26 = 0;
    v27 = 0;
  }
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(&v35);
  v21 = InstallQueueHasUpdates();
  UpdateTaskTriggers(v21);
}

```

## disassembly

```asm
0x18001c58c  push    rbp
0x18001c58e  push    rbx
0x18001c58f  push    rsi
0x18001c590  push    rdi
0x18001c591  push    r12
0x18001c593  push    r13
0x18001c595  push    r14
0x18001c597  push    r15
0x18001c599  lea     rbp, [rsp-28h]
0x18001c59e  sub     rsp, 128h
0x18001c5a5  mov     rax, cs:__security_cookie
0x18001c5ac  xor     rax, rsp
0x18001c5af  mov     [rbp+60h+var_48], rax
0x18001c5b3  mov     r13, rcx
0x18001c5b6  xor     r12d, r12d
0x18001c5b9  call    ?InstallQueueHasUpdates@@YA_NXZ; InstallQueueHasUpdates(void)
0x18001c5be  mov     bl, al
0x18001c5c0  mov     cl, al; bool
0x18001c5c2  call    ?UpdateTaskTriggers@@YAX_N@Z; UpdateTaskTriggers(bool)
0x18001c5c7  test    bl, bl
0x18001c5c9  jnz     short loc_18001C627
0x18001c5cb  mov     [rsp+160h+var_128], r12; unsigned __int16 *
0x18001c5d0  mov     [rsp+160h+var_130], r12; char *
0x18001c5d5  lea     rax, aNoUpdatesFound; "No Updates found. Nothing to do"
0x18001c5dc  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x18001c5e1  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x18001c5e9  lea     r9, aDownloadandins; "DownloadAndInstallPendingUpdatesWorker:"...
0x18001c5f0  mov     r8d, 0FCh; unsigned int
0x18001c5f6  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c5fd  lea     ecx, [r12+3]; unsigned int
0x18001c602  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001c607  mov     rcx, [rbp+60h+var_48]
0x18001c60b  xor     rcx, rsp; StackCookie
0x18001c60e  call    __security_check_cookie
0x18001c613  add     rsp, 128h
0x18001c61a  pop     r15
0x18001c61c  pop     r14
0x18001c61e  pop     r13
0x18001c620  pop     r12
0x18001c622  pop     rdi
0x18001c623  pop     rsi
0x18001c624  pop     rbx
0x18001c625  pop     rbp
0x18001c626  retn
0x18001c627  mov     esi, 1
0x18001c62c  mov     [rbp+60h+var_D7], sil
0x18001c630  lea     rcx, [rsp+160h+var_110]
0x18001c635  call    ??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)
0x18001c63a  mov     rdi, [rax]
0x18001c63d  mov     [rax], r12
0x18001c640  mov     [rbp+60h+var_98], rdi
0x18001c644  lea     rcx, [rsp+160h+var_110]
0x18001c649  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18001c64e  mov     [rsp+160h+var_F8], r12
0x18001c653  mov     rax, [rdi]
0x18001c656  mov     rbx, [rax+30h]
0x18001c65a  lea     rcx, [rsp+160h+var_F8]
0x18001c65f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c664  lea     rdx, [rsp+160h+var_F8]
0x18001c669  mov     rcx, rdi
0x18001c66c  mov     rax, rbx
0x18001c66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c674  mov     rcx, [rbp+68h]; this
0x18001c678  test    eax, eax
0x18001c67a  jns     short loc_18001C691
0x18001c67c  mov     r9d, eax; char *
0x18001c67f  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c686  mov     edx, 104h; void *
0x18001c68b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c691  mov     [rbp+60h+var_C8], r12
0x18001c695  mov     rax, [rdi]
0x18001c698  lea     r8, [rbp+60h+var_C8]
0x18001c69c  lea     rdx, _GUID_20e1713b_cbcc_442d_b441_6440689b8912
0x18001c6a3  mov     rcx, rdi
0x18001c6a6  mov     rax, [rax]
0x18001c6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6ae  mov     rcx, [rbp+68h]; this
0x18001c6b2  test    eax, eax
0x18001c6b4  jns     short loc_18001C6CB
0x18001c6b6  mov     r9d, eax; char *
0x18001c6b9  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c6c0  mov     edx, 107h; void *
0x18001c6c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c6cb  mov     rdi, [rbp+60h+var_C8]
0x18001c6cf  mov     rax, [rdi]
0x18001c6d2  mov     rbx, [rax+30h]
0x18001c6d6  mov     [rbp+60h+var_68], r12
0x18001c6da  mov     r9d, 12h; unsigned int
0x18001c6e0  lea     r8d, [r9+1]; unsigned int
0x18001c6e4  lea     rdx, aEdupendingdown; "EDUPendingDownload"
0x18001c6eb  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18001c6ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c6f4  nop
0x18001c6f5  xor     r8d, r8d
0x18001c6f8  mov     rdx, [rbp+60h+var_68]
0x18001c6fc  mov     rcx, rdi
0x18001c6ff  mov     rax, rbx
0x18001c702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c707  mov     rcx, [rbp+68h]; this
0x18001c70b  test    eax, eax
0x18001c70d  jns     short loc_18001C724
0x18001c70f  mov     r9d, eax; char *
0x18001c712  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c719  mov     edx, 108h; void *
0x18001c71e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c724  mov     ecx, 40h ; '@'; Size
0x18001c729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c72e  mov     rdi, rax
0x18001c731  mov     [rsp+160h+var_110._Hnd], rax
0x18001c736  xorps   xmm0, xmm0
0x18001c739  movups  xmmword ptr [rax], xmm0
0x18001c73c  mov     [rax+8], esi
0x18001c73f  mov     [rax+0Ch], esi
0x18001c742  lea     rax, ??_7?$_Ref_count_obj2@VGlobalTrackerWithTimeoutAndCancel@@@std@@6B@; const std::_Ref_count_obj2<GlobalTrackerWithTimeoutAndCancel>::`vftable'
0x18001c749  mov     [rdi], rax
0x18001c74c  lea     r14, [rdi+10h]
0x18001c750  lea     rdx, a0u; "0u"
0x18001c757  mov     rcx, r14
0x18001c75a  call    ??$_Construct_in_place@VGlobalTrackerWithTimeoutAndCancel@@AEBK@std@@YAXAEAVGlobalTrackerWithTimeoutAndCancel@@AEBK@Z; std::_Construct_in_place<GlobalTrackerWithTimeoutAndCancel,ulong const &>(GlobalTrackerWithTimeoutAndCancel &,ulong const &)
0x18001c75f  nop
0x18001c760  mov     [rbp+60h+var_90], r14
0x18001c764  mov     [rbp+60h+var_88], rdi
0x18001c768  lea     rcx, [rsp+160h+var_F0]
0x18001c76d  call    ??0?$vector@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(void)
0x18001c772  nop
0x18001c773  mov     rax, [rsp+160h+var_F8]
0x18001c778  mov     [rsp+160h+var_110._Hnd], rax
0x18001c77d  mov     [rbp+60h+var_B0], rax
0x18001c781  mov     [rbp+60h+var_A8], r12d
0x18001c785  mov     [rbp+60h+var_A0], r12
0x18001c789  lea     rdx, [rbp+60h+hstringHeader]
0x18001c78d  lea     rcx, [rsp+160h+var_110]
0x18001c792  call    ?end@?$vector_range@U?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,wil::err_exception_policy>::end(void)
0x18001c797  nop
0x18001c798  mov     eax, [rbp+60h+var_A8]
0x18001c79b  cmp     eax, dword ptr [rbp+60h+hstringHeader.Reserved+8]
0x18001c79e  jz      loc_18001C839
0x18001c7a4  lea     rcx, [rbp+60h+var_B0]
0x18001c7a8  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18001c7ad  mov     rcx, [rax]
0x18001c7b0  mov     [rsp+160h+var_110._Hnd], rcx
0x18001c7b5  test    rcx, rcx
0x18001c7b8  jz      short loc_18001C7C7
0x18001c7ba  mov     rax, [rcx]
0x18001c7bd  mov     rax, [rax+8]
0x18001c7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7c6  nop
0x18001c7c7  lea     r8, [rsp+160h+var_110]
0x18001c7cc  lea     rdx, [rbp+60h+var_90]
0x18001c7d0  lea     rcx, [rsp+160h+var_100]
0x18001c7d5  call    ??$Make@VAppInstallItemTracker@@AEAV?$shared_ptr@VGlobalTrackerWithTimeoutAndCancel@@@std@@AEAV?$ComPtr@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppInstallItemTracker@@@12@AEAV?$shared_ptr@VGlobalTrackerWithTimeoutAndCancel@@@std@@AEAV?$ComPtr@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@12@@Z; Microsoft::WRL::Details::Make<AppInstallItemTracker,std::shared_ptr<GlobalTrackerWithTimeoutAndCancel> &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem> &>(std::shared_ptr<GlobalTrackerWithTimeoutAndCancel> &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem> &)
0x18001c7da  mov     rdx, rax
0x18001c7dd  mov     rcx, qword ptr [rsp+160h+var_F0+8]
0x18001c7e2  cmp     rcx, [rbp+60h+var_E0]
0x18001c7e6  jz      short loc_18001C7F5
0x18001c7e8  call    ??$_Construct_in_place@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@V123@@std@@YAXAEAV?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@$$QEAV123@@Z; std::_Construct_in_place<Microsoft::WRL::ComPtr<AppInstallItemTracker>,Microsoft::WRL::ComPtr<AppInstallItemTracker>>(Microsoft::WRL::ComPtr<AppInstallItemTracker> &,Microsoft::WRL::ComPtr<AppInstallItemTracker> &&)
0x18001c7ed  add     qword ptr [rsp+160h+var_F0+8], 8
0x18001c7f3  jmp     short loc_18001C806
0x18001c7f5  mov     r8, rdx
0x18001c7f8  mov     rdx, rcx
0x18001c7fb  lea     rcx, [rsp+160h+var_F0]
0x18001c800  call    ??$_Emplace_reallocate@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VAppInstallItemTracker@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<AppInstallItemTracker>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppInstallItemTracker>>(Microsoft::WRL::ComPtr<AppInstallItemTracker> * const,Microsoft::WRL::ComPtr<AppInstallItemTracker> &&)
0x18001c805  nop
0x18001c806  mov     rcx, [rsp+160h+var_100]
0x18001c80b  test    rcx, rcx
0x18001c80e  jz      short loc_18001C822
0x18001c810  mov     [rsp+160h+var_100], r12
0x18001c815  mov     rax, [rcx]
0x18001c818  mov     rax, [rax+10h]
0x18001c81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c821  nop
0x18001c822  lea     rcx, [rsp+160h+var_110]
0x18001c827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c82c  mov     eax, [rbp+60h+var_A8]
0x18001c82f  add     eax, esi
0x18001c831  mov     [rbp+60h+var_A8], eax
0x18001c834  jmp     loc_18001C79B
0x18001c839  lea     rcx, [rbp+60h+hstringHeader.Reserved+10h]
0x18001c83d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c842  nop
0x18001c843  lea     rcx, [rbp+60h+var_A0]
0x18001c847  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c84c  mov     dword ptr [rsp+160h+var_100], esi
0x18001c850  lea     rdx, [rsp+160h+var_100]
0x18001c855  lea     rcx, [rbp+60h+var_D0]
0x18001c859  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18001c85e  nop
0x18001c85f  mov     ecx, 10h; Size
0x18001c864  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c869  lea     rcx, [rsp+160h+var_F0]
0x18001c86e  mov     [rax], rcx
0x18001c871  lea     rcx, [rbp+60h+var_D0]
0x18001c875  mov     [rax+8], rcx
0x18001c879  mov     [rsp+160h+var_110._Hnd], rax
0x18001c87e  lea     rcx, [rbp+60h+var_C0+8]
0x18001c882  mov     [rsp+160h+var_138], rcx
0x18001c887  mov     [rsp+160h+var_140], r12d
0x18001c88c  mov     r9, rax
0x18001c88f  lea     r8, std__thread___Invoke_std__tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____0_
0x18001c896  xor     edx, edx
0x18001c898  xor     ecx, ecx
0x18001c89a  call    cs:__imp__o__beginthreadex
0x18001c8a0  mov     qword ptr [rbp+60h+var_C0], rax
0x18001c8a4  test    rax, rax
0x18001c8a7  jz      loc_18001CAA2
0x18001c8ad  mov     [rsp+160h+var_110._Hnd], r12
0x18001c8b2  lea     rcx, [rsp+160h+var_110]
0x18001c8b7  call    std__unique_ptr_std__tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____std__default_delete_std__tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8__________unique_ptr_std__tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8____std__default_delete_std__tuple__lambda_09c2963686ccb0ee45f7ad774831f8a8_______
0x18001c8bc  nop
0x18001c8bd  mov     rax, [rbp+60h+var_D0]
0x18001c8c1  mov     [rbp+60h+Handles], rax
0x18001c8c5  mov     rax, [r14+20h]
0x18001c8c9  mov     [rbp+60h+var_58], rax
0x18001c8cd  mov     rax, [r13+8]
0x18001c8d1  mov     [rbp+60h+var_50], rax
0x18001c8d5  mov     esi, 1B7740h
0x18001c8da  mov     [rsp+160h+var_120], esi
0x18001c8de  mov     [rsp+160h+var_128], r12; unsigned __int16 *
0x18001c8e3  mov     [rsp+160h+var_130], r12; char *
0x18001c8e8  lea     rax, aWaitingForItem; "Waiting for Items to finish or Cancel o"...
0x18001c8ef  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x18001c8f4  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x18001c8fc  lea     r9, aDownloadandins; "DownloadAndInstallPendingUpdatesWorker:"...
0x18001c903  mov     r8d, 127h; unsigned int
0x18001c909  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c910  mov     ebx, 3
0x18001c915  mov     ecx, ebx; unsigned int
0x18001c917  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001c91c  mov     r9d, esi; dwMilliseconds
0x18001c91f  xor     r8d, r8d; bWaitAll
0x18001c922  lea     rdx, [rbp+60h+Handles]; lpHandles
0x18001c926  mov     ecx, ebx; nCount
0x18001c928  call    cs:__imp_WaitForMultipleObjects
0x18001c92e  mov     [rsp+160h+var_128], r12; unsigned __int16 *
0x18001c933  mov     [rsp+160h+var_130], r12; char *
0x18001c938  lea     rax, aWaitOverCleani; "Wait Over. Cleaning up and exiting."
0x18001c93f  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x18001c944  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x18001c94c  lea     r9, aDownloadandins; "DownloadAndInstallPendingUpdatesWorker:"...
0x18001c953  mov     r8d, 12Bh; unsigned int
0x18001c959  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c960  mov     ecx, ebx; unsigned int
0x18001c962  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18001c967  mov     rsi, qword ptr [rsp+160h+var_F0]
0x18001c96c  mov     r15, qword ptr [rsp+160h+var_F0+8]
0x18001c971  jmp     short loc_18001C9AD
0x18001c973  mov     rbx, [rsi]
0x18001c976  test    rbx, rbx
0x18001c979  jz      short loc_18001C98B
0x18001c97b  mov     rax, [rbx]
0x18001c97e  mov     rcx, rbx
0x18001c981  mov     rax, [rax+8]
0x18001c985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c98a  nop
0x18001c98b  mov     rcx, rbx; this
0x18001c98e  call    ?Cleanup@AppInstallItemTracker@@QEAAXXZ; AppInstallItemTracker::Cleanup(void)
0x18001c993  nop
0x18001c994  test    rbx, rbx
0x18001c997  jz      short loc_18001C9A9
0x18001c999  mov     rax, [rbx]
0x18001c99c  mov     rcx, rbx
0x18001c99f  mov     rax, [rax+10h]
0x18001c9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9a8  nop
0x18001c9a9  add     rsi, 8
0x18001c9ad  cmp     rsi, r15
0x18001c9b0  jnz     short loc_18001C973
0x18001c9b2  mov     rcx, r14; this
0x18001c9b5  call    ?Cleanup@GlobalTrackerWithTimeoutAndCancel@@QEAAXXZ; GlobalTrackerWithTimeoutAndCancel::Cleanup(void)
0x18001c9ba  mov     rcx, [r13+8]; this
0x18001c9be  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001c9c3  cmp     dword ptr [rbp+60h+var_C0+8], r12d
0x18001c9c7  jz      loc_18001CA96
0x18001c9cd  call    cs:__imp__Thrd_id
0x18001c9d3  cmp     dword ptr [rbp+60h+var_C0+8], eax
0x18001c9d6  jnz     short loc_18001C9E4
0x18001c9d8  mov     ecx, 5
0x18001c9dd  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001c9e3  int     3; Trap to Debugger
0x18001c9e4  movaps  xmm0, [rbp+60h+var_C0]
0x18001c9e8  movdqa  xmmword ptr [rsp+160h+var_110._Hnd], xmm0
0x18001c9ee  xor     edx, edx; int *
0x18001c9f0  lea     rcx, [rsp+160h+var_110]; _Thrd_t
0x18001c9f5  call    cs:__imp__Thrd_join
0x18001c9fb  test    eax, eax
0x18001c9fd  jz      short loc_18001CA0B
0x18001c9ff  mov     ecx, 2
0x18001ca04  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001ca0a  int     3; Trap to Debugger
0x18001ca0b  xorps   xmm0, xmm0
0x18001ca0e  movdqa  [rbp+60h+var_C0], xmm0
0x18001ca13  lea     rcx, [rbp+60h+var_C0]; this
0x18001ca17  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18001ca1c  nop
0x18001ca1d  lea     rcx, [rbp+60h+var_D0]
0x18001ca21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ca26  nop
0x18001ca27  mov     rcx, qword ptr [rsp+160h+var_F0]
0x18001ca2c  test    rcx, rcx
0x18001ca2f  jz      short loc_18001CA5D
  ... truncated ...
```

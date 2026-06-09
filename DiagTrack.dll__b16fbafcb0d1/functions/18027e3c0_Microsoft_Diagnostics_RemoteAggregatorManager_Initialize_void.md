# Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(void)

- ea: `0x18027e3c0`
- end: `0x18027e5ea`
- name: `?Initialize@RemoteAggregatorManager@Diagnostics@Microsoft@@QEAAXXZ`
- size: `554`
- prototype: `void __fastcall(Microsoft::Diagnostics::RemoteAggregatorManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802549f8`

## callees

- `0x18001fd84`
- `0x18002df00`
- `0x1800d13c8`
- `0x1800e8f80`
- `0x18010f7e0`
- `0x18011c2ec`
- `0x1801b2084`
- `0x1801c33dc`
- `0x1801e71c8`
- `0x18020aac0`
- `0x18027dc3c`
- `0x18027e3c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18027e541`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18027e541`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18027e4e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18027e50f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18027e4e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18027e50f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027e3f5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027e419`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027e3f5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18027e419`

## string_xrefs

- `0x18027e59e`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e5be`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e5d8`: `onecore\base\telemetry\utc\service\engine\remoteaggregatormanager.cpp`
- `0x18027e412`: `MissionControlAggregator.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::RemoteAggregatorManager::Initialize(
        Microsoft::Diagnostics::RemoteAggregatorManager *this)
{
  WCHAR *v2; // rbx
  const WCHAR *v3; // rcx
  char v4; // bl
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v6; // r9
  PTP_TIMER v7; // rax
  const char *v8; // r9
  PTP_WAIT ThreadpoolWait; // rax
  const char *v10; // r9
  gsl::details *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  __int128 v14; // [rsp+50h] [rbp-38h] BYREF
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = &Microsoft::Diagnostics::k_inboxAggregatorModulePaths;
  while ( 1 )
  {
    v3 = *((_QWORD *)v2 + 3) <= 7u ? v2 : *(const WCHAR **)v2;
    if ( GetFileAttributesW(v3) != -1 )
      break;
    v2 += 16;
    if ( v2 == (WCHAR *)&`Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array'::`2'::value )
    {
      v4 = 0;
      if ( GetFileAttributesW(L"MissionControlAggregator.dll") == -1 )
        goto LABEL_9;
      break;
    }
  }
  v4 = 1;
LABEL_9:
  v14 = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(v14) = 0;
  v12 = *(_OWORD *)&off_180385098;
  v13 = *(_OWORD *)&off_1803850D8;
  Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, &v13, &v12, &v14);
  if ( !v4 && !v15 )
    *((_BYTE *)this + 1912) = 1;
  std::wstring::_Tidy_deallocate(&v14);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 1144,
    1,
    0,
    0,
    0);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 1152,
    1,
    0,
    0,
    0);
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::RemoteAggregatorManager,{public: void Microsoft::Diagnostics::RemoteAggregatorManager::FlushAsync(void),0}>,
                      this,
                      0);
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v6);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 1688,
    ThreadpoolTimer);
  v7 = CreateThreadpoolTimer(
         Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::RemoteAggregatorManager,{public: void Microsoft::Diagnostics::RemoteAggregatorManager::GetChildProcessToReadyStateAsync(void),0}>,
         this,
         0);
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v8);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 1592,
    v7);
  ThreadpoolWait = CreateThreadpoolWait(
                     Microsoft::Diagnostics::RemoteAggregatorManager::Initialize_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                     this,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 1248,
    ThreadpoolWait);
  if ( !*((_QWORD *)this + 156) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\remoteaggregatormanager.cpp",
      v10);
  Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(this);
  if ( (int)Microsoft::Diagnostics::UtcWrapperBase::Initialize((Microsoft::Diagnostics::RemoteAggregatorManager *)((char *)this + 1496)) < 0 )
    gsl::details::terminate(v11);
  Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(this);
}

```

## disassembly

```asm
0x18027e3c0  mov     [rsp+arg_8], rbx
0x18027e3c5  push    rdi
0x18027e3c6  sub     rsp, 80h
0x18027e3cd  mov     rax, cs:__security_cookie
0x18027e3d4  xor     rax, rsp
0x18027e3d7  mov     [rsp+88h+var_18], rax
0x18027e3dc  mov     rdi, rcx
0x18027e3df  lea     rbx, ?k_inboxAggregatorModulePaths@Diagnostics@Microsoft@@3PAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring near * Microsoft::Diagnostics::k_inboxAggregatorModulePaths
0x18027e3e6  cmp     qword ptr [rbx+18h], 7
0x18027e3eb  jbe     short loc_18027E3F2
0x18027e3ed  mov     rcx, [rbx]
0x18027e3f0  jmp     short loc_18027E3F5
0x18027e3f2  mov     rcx, rbx; lpFileName
0x18027e3f5  call    cs:__imp_GetFileAttributesW
0x18027e3fb  cmp     eax, 0FFFFFFFFh
0x18027e3fe  jnz     short loc_18027E424
0x18027e400  add     rbx, 20h ; ' '
0x18027e404  lea     rax, ?value@?1??_name_array@_data_ConfigurationType@better_enums@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA; char const * near * `Microsoft::Diagnostics::better_enums::_data_ConfigurationType::_name_array(void)'::`2'::value
0x18027e40b  cmp     rbx, rax
0x18027e40e  jnz     short loc_18027E3E6
0x18027e410  xor     bl, bl
0x18027e412  lea     rcx, FileName; "MissionControlAggregator.dll"
0x18027e419  call    cs:__imp_GetFileAttributesW
0x18027e41f  cmp     eax, 0FFFFFFFFh
0x18027e422  jz      short loc_18027E426
0x18027e424  mov     bl, 1
0x18027e426  xorps   xmm0, xmm0
0x18027e429  movups  [rsp+88h+var_38], xmm0
0x18027e42e  mov     [rsp+88h+var_28], 0
0x18027e437  mov     [rsp+88h+var_20], 7
0x18027e440  xor     eax, eax
0x18027e442  mov     word ptr [rsp+88h+var_38], ax
0x18027e447  movups  xmm0, xmmword ptr cs:off_180385098; "TestAggregatorDll"
0x18027e44e  movdqu  [rsp+88h+var_58], xmm0
0x18027e454  movups  xmm1, xmmword ptr cs:off_1803850D8; "%DiagtrackRegistryRoot%\\TestHooks"
0x18027e45b  movdqu  [rsp+88h+var_48], xmm1
0x18027e461  lea     r9, [rsp+88h+var_38]
0x18027e466  lea     r8, [rsp+88h+var_58]
0x18027e46b  lea     rdx, [rsp+88h+var_48]
0x18027e470  mov     rcx, 0FFFFFFFF80000002h
0x18027e477  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x18027e47c  test    bl, bl
0x18027e47e  jnz     short loc_18027E48F
0x18027e480  cmp     [rsp+88h+var_28], 0
0x18027e486  jnz     short loc_18027E48F
0x18027e488  mov     byte ptr [rdi+778h], 1
0x18027e48f  lea     rcx, [rsp+88h+var_38]
0x18027e494  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18027e499  lea     rcx, [rdi+478h]
0x18027e4a0  mov     [rsp+88h+var_68], 0
0x18027e4a9  xor     r9d, r9d
0x18027e4ac  xor     r8d, r8d
0x18027e4af  lea     edx, [r9+1]
0x18027e4b3  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18027e4b8  lea     rcx, [rdi+480h]
0x18027e4bf  mov     [rsp+88h+var_68], 0
0x18027e4c8  xor     r9d, r9d
0x18027e4cb  xor     r8d, r8d
0x18027e4ce  lea     edx, [r9+1]
0x18027e4d2  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18027e4d7  xor     r8d, r8d; pcbe
0x18027e4da  mov     rdx, rdi; pv
0x18027e4dd  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VRemoteAggregatorManager@Diagnostics@Microsoft@@$H?FlushAsync@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18027e4e4  call    cs:__imp_CreateThreadpoolTimer
0x18027e4ea  test    rax, rax
0x18027e4ed  jz      loc_18027E5B6
0x18027e4f3  lea     rcx, [rdi+698h]
0x18027e4fa  mov     rdx, rax
0x18027e4fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18027e502  xor     r8d, r8d; pcbe
0x18027e505  mov     rdx, rdi; pv
0x18027e508  lea     rcx, ??$MethodToTpTimerCallbackAdapter@VRemoteAggregatorManager@Diagnostics@Microsoft@@$H?GetChildProcessToReadyStateAsync@123@QEAAXXZA@@Os@Utils@Diagnostics@Microsoft@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18027e50f  call    cs:__imp_CreateThreadpoolTimer
0x18027e515  test    rax, rax
0x18027e518  jz      loc_18027E5D0
0x18027e51e  lea     rcx, [rdi+638h]
0x18027e525  mov     rdx, rax
0x18027e528  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18027e52d  lea     rbx, [rdi+4E0h]
0x18027e534  xor     r8d, r8d; pcbe
0x18027e537  mov     rdx, rdi; pv
0x18027e53a  lea     rcx, _Microsoft__Diagnostics__RemoteAggregatorManager__Initialize____2____lambda_1____lambda_invoker_cdecl_; pfnwa
0x18027e541  call    cs:__imp_CreateThreadpoolWait
0x18027e547  mov     rdx, rax
0x18027e54a  mov     rcx, rbx
0x18027e54d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18027e552  cmp     qword ptr [rbx], 0
0x18027e556  jz      short loc_18027E596
0x18027e558  mov     rcx, rdi; this
0x18027e55b  call    ?DeserializeControlGroupsFromRegistry@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::DeserializeControlGroupsFromRegistry(void)
0x18027e560  lea     rcx, [rdi+5D8h]; this
0x18027e567  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x18027e56c  test    eax, eax
0x18027e56e  js      short loc_18027E5B0
0x18027e570  mov     rcx, rdi; this
0x18027e573  call    ?ArmStartTimer@RemoteAggregatorManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::RemoteAggregatorManager::ArmStartTimer(void)
0x18027e578  mov     rcx, [rsp+88h+var_18]
0x18027e57d  xor     rcx, rsp; StackCookie
0x18027e580  call    __security_check_cookie
0x18027e585  mov     rbx, [rsp+88h+arg_8]
0x18027e58d  add     rsp, 80h
0x18027e594  pop     rdi
0x18027e595  retn
0x18027e596  mov     rcx, [rsp+88h]; this
0x18027e59e  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e5a5  mov     edx, 5Ah ; 'Z'; void *
0x18027e5aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18027e5b0  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18027e5b6  mov     rcx, [rsp+88h]; this
0x18027e5be  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e5c5  mov     edx, 4Dh ; 'M'; void *
0x18027e5ca  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18027e5d0  mov     rcx, [rsp+88h]; this
0x18027e5d8  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x18027e5df  mov     edx, 52h ; 'R'; void *
0x18027e5e4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

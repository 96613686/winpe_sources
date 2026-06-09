# UiaManagerCrossMachineStub::CreateAutomationConnectionForHwnd(HWND__ *,uint,uint,int,unsigned __int64 *,__int64 *)

- ea: `0x180017600`
- end: `0x180017b90`
- name: `?CreateAutomationConnectionForHwnd@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@IIHPEA_KPEA_J@Z`
- size: `1424`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineStub *this, HWND, unsigned int, unsigned int, int, unsigned __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006edc`
- `0x180016010`
- `0x1800161ec`
- `0x180016c74`
- `0x180017600`
- `0x180018868`
- `0x180018b4c`
- `0x180018bc8`
- `0x180018c44`
- `0x18001d9c4`
- `0x1800205cc`
- `0x180023d0c`
- `0x180024794`
- `0x1800294d0`
- `0x180031540`
- `0x180043680`
- `0x180068514`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180017b1b`
- `msvcp_win!_Mtx_unlock` at `0x180017b1b`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800179f4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180017b5e`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800179f4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180017b5e`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800176a1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800176a1`
- `UIAutomationCore!InitializeChannelBasedConnectionForProviderProxy` at `0x180017aac`
- `UIAutomationCore!InitializeChannelBasedConnectionForProviderProxy` at `0x180017aac`

## string_xrefs

- `0x18001779a`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x18001765d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017680`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800176e4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800177c8`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017863`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800178ff`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017995`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017a1b`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017a4a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017a6a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017a92`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017ac1`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaManagerCrossMachineStub::CreateAutomationConnectionForHwnd(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned __int64 *a6,
        __int64 *a7)
{
  unsigned __int64 v8; // r13
  UiaManagerCrossMachineStub *v10; // rcx
  int PlatformSpecificSecurityAttributes; // eax
  unsigned __int16 *v13; // rcx
  int v14; // eax
  int v15; // ebx
  __int128 *v16; // r9
  unsigned __int16 **v17; // rdx
  int ConnectionSequenceEventName; // eax
  __int128 *v19; // r8
  __int128 *v20; // r9
  unsigned __int16 **v21; // rdx
  int v22; // eax
  __int128 *v23; // r8
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rcx
  std::_Mutex_base *v27; // rbx
  DWORD v28; // [rsp+20h] [rbp-F8h]
  unsigned int v29; // [rsp+20h] [rbp-F8h]
  char *v30; // [rsp+28h] [rbp-F0h]
  DWORD dwProcessId; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v32; // [rsp+38h] [rbp-E0h] BYREF
  char v33; // [rsp+48h] [rbp-D0h] BYREF
  __int16 v34; // [rsp+49h] [rbp-CFh]
  char v35; // [rsp+4Bh] [rbp-CDh]
  unsigned int v36; // [rsp+4Ch] [rbp-CCh]
  UiaManagerCrossMachineStub *v37; // [rsp+58h] [rbp-C0h]
  __int128 v38; // [rsp+60h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES v39; // [rsp+70h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES *v40; // [rsp+88h] [rbp-90h]
  char v41; // [rsp+90h] [rbp-88h]
  __int128 v42; // [rsp+98h] [rbp-80h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-70h]
  unsigned __int16 *v44[2]; // [rsp+B8h] [rbp-60h] BYREF
  unsigned __int64 v45[2]; // [rsp+C8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v8 = a3;
  v37 = this;
  *a7 = 0;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)0x80070057LL,
      v28);
  if ( !a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)0x80070057LL,
      v28);
  dwProcessId = 0;
  GetWindowThreadProcessId(a2, &dwProcessId);
  if ( !dwProcessId )
    return 2147942406LL;
  memset(&v39, 0, sizeof(v39));
  PlatformSpecificSecurityAttributes = UiaManagerCrossMachineStub::GetPlatformSpecificSecurityAttributes(
                                         v10,
                                         dwProcessId,
                                         &v39);
  if ( PlatformSpecificSecurityAttributes < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)PlatformSpecificSecurityAttributes,
      v28);
  v40 = &v39;
  v41 = 1;
  *(_OWORD *)v44 = 0;
  *(__m128i *)v45 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v44[0]) = 0;
  std::wstring::resize(v44, 200);
  v13 = (unsigned __int16 *)v44;
  if ( v45[1] > 7 )
    v13 = v44[0];
  if ( (_DWORD)v8 )
  {
    v28 = dwProcessId;
    v14 = StringCchPrintfW(v13, v45[0], L"%ws_%d_%04Ix", L"%ws");
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
        (const char *)(unsigned int)v14,
        v28);
      goto LABEL_17;
    }
  }
  else if ( v45[0] )
  {
    *v13 = 0;
  }
  v15 = 0;
LABEL_17:
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v15,
      v28);
  v42 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v42) = 0;
  std::wstring::resize(&v42, 260);
  v16 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v16 = (__int128 *)v42;
  v17 = v44;
  if ( v45[1] > 7 )
    v17 = (unsigned __int16 **)v44[0];
  ConnectionSequenceEventName = BasicUiaUtils::GetConnectionSequenceEventName(0, v17, si128.m128i_i64[0], v16);
  if ( ConnectionSequenceEventName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)ConnectionSequenceEventName,
      v28);
  v38 = 0;
  v19 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v19 = (__int128 *)v42;
  _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v38,
    1,
    v19);
  v20 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v20 = (__int128 *)v42;
  v21 = v44;
  if ( v45[1] > 7 )
    v21 = (unsigned __int16 **)v44[0];
  v22 = BasicUiaUtils::GetConnectionSequenceEventName(1, v21, si128.m128i_i64[0], v20);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v22,
      v28);
  v32 = 0;
  v23 = &v42;
  if ( si128.m128i_i64[1] > 7uLL )
    v23 = (__int128 *)v42;
  _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v32,
    1,
    v23);
  v33 = 1;
  v34 = 0;
  v35 = 0;
  v36 = a4;
  if ( a5 )
  {
    v25 = InitializeChannelBasedConnectionForProviderProxy(a2, (unsigned int)v8, a4);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)(unsigned int)v25,
        v28);
  }
  else
  {
    v24 = BasicHwndUtils::UIASendMessageTimeout((const struct UIA_TIMEOUTDATA *)&v33, a2, 0x3Du, v8, -25, a7);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x21E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)(unsigned int)v24,
        v29);
    if ( *a7 != 0x10000 )
    {
      if ( *a7 == 0x100000 )
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x229,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
          (const char *)0x80004005LL,
          (int)"Container provider requested cross machine pipe",
          v30);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v32);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v38);
      std::wstring::_Tidy_deallocate(&v42);
      std::wstring::_Tidy_deallocate(v44);
      if ( v39.lpSecurityDescriptor )
        FreeTransientObjectSecurityDescriptor();
      return 0;
    }
    if ( !(unsigned __int8)_wait___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                             &v38,
                             a4) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x5B4,
        v29);
    if ( *a7 > 0x7FFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x233,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80004005LL,
        v29);
    if ( *a7 < (__int64)0xFFFFFFFF80000000uLL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        (const char *)0x80004005LL,
        v29);
  }
  if ( (_QWORD)v32 )
    v26 = *(_QWORD *)v32;
  else
    v26 = 0;
  *a6 = v26;
  v27 = (UiaManagerCrossMachineStub *)((char *)v37 + 200);
  v37 = v27;
  std::_Mutex_base::lock(v27);
  ___emplace_AEA_KV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil______Hash_V___Umap_traits__KV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__V___Uhash_compare__KU__hash__K_std__U__equal_to__K_2__std__V__allocator_U__pair___CB_KV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___std___4__0A__std___std__QEAA_AU__pair_V___List_iterator_V___List_val_U___List_simple_types_U__pair___CB_KV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___std___std___std___std___N_1_AEA_K__QEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(
    (char *)v27 + 80,
    &v33,
    a6,
    &v32);
  _Mtx_unlock(v27);
  std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v32);
  std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v38);
  std::wstring::_Tidy_deallocate(&v42);
  std::wstring::_Tidy_deallocate(v44);
  if ( v39.lpSecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  return 0;
}

```

## disassembly

```asm
0x180017600  push    rbx
0x180017602  push    rsi
0x180017603  push    rdi
0x180017604  push    r12
0x180017606  push    r13
0x180017608  push    r14
0x18001760a  push    r15
0x18001760c  sub     rsp, 0E0h
0x180017613  mov     rax, cs:__security_cookie
0x18001761a  xor     rax, rsp
0x18001761d  mov     [rsp+118h+var_40], rax
0x180017625  mov     esi, r9d
0x180017628  mov     r13d, r8d
0x18001762b  mov     r14, rdx
0x18001762e  mov     [rsp+118h+var_C0], rcx
0x180017633  mov     r12, [rsp+118h+arg_28]
0x18001763b  mov     rdi, [rsp+118h+arg_30]
0x180017643  mov     qword ptr [rdi], 0
0x18001764a  mov     rcx, [rsp+118h]; this
0x180017652  test    rdx, rdx
0x180017655  jnz     short loc_18001766E
0x180017657  mov     r9d, 80070057h; char *
0x18001765d  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017664  mov     edx, 1E5h; void *
0x180017669  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001766e  mov     rcx, [rsp+118h]; this
0x180017676  test    esi, esi
0x180017678  jnz     short loc_180017691
0x18001767a  mov     r9d, 80070057h; char *
0x180017680  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017687  mov     edx, 1E6h; void *
0x18001768c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017691  mov     [rsp+118h+dwProcessId], 0
0x180017699  lea     rdx, [rsp+118h+dwProcessId]; lpdwProcessId
0x18001769e  mov     rcx, r14; hWnd
0x1800176a1  call    cs:__imp_GetWindowThreadProcessId
0x1800176a7  mov     edx, [rsp+118h+dwProcessId]; unsigned int
0x1800176ab  test    edx, edx
0x1800176ad  jnz     short loc_1800176B9
0x1800176af  mov     eax, 80070006h
0x1800176b4  jmp     loc_180017B6C
0x1800176b9  xorps   xmm0, xmm0
0x1800176bc  xor     eax, eax
0x1800176be  movups  xmmword ptr [rsp+118h+var_A8.nLength], xmm0
0x1800176c3  mov     qword ptr [rsp+118h+var_A8.bInheritHandle], rax
0x1800176cb  lea     r8, [rsp+118h+var_A8]; struct _SECURITY_ATTRIBUTES *
0x1800176d0  call    ?GetPlatformSpecificSecurityAttributes@UiaManagerCrossMachineStub@@AEAAJIPEAU_SECURITY_ATTRIBUTES@@@Z; UiaManagerCrossMachineStub::GetPlatformSpecificSecurityAttributes(uint,_SECURITY_ATTRIBUTES *)
0x1800176d5  mov     rcx, [rsp+118h]; this
0x1800176dd  test    eax, eax
0x1800176df  jns     short loc_1800176F5
0x1800176e1  mov     r9d, eax; char *
0x1800176e4  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800176eb  mov     edx, 1F7h; void *
0x1800176f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800176f5  lea     rax, [rsp+118h+var_A8]
0x1800176fa  mov     [rsp+118h+var_90], rax
0x180017702  mov     [rsp+118h+var_88], 1
0x18001770a  xorps   xmm0, xmm0
0x18001770d  movups  xmmword ptr [rsp+118h+var_60], xmm0
0x180017715  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001771d  movdqu  xmmword ptr [rsp+118h+var_50], xmm1
0x180017726  xor     eax, eax
0x180017728  mov     word ptr [rsp+118h+var_60], ax
0x180017730  mov     edx, 0C8h
0x180017735  lea     rcx, [rsp+118h+var_60]
0x18001773d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180017742  lea     rcx, [rsp+118h+var_60]
0x18001774a  cmp     [rsp+118h+var_50+8], 7
0x180017753  cmova   rcx, [rsp+118h+var_60]; unsigned __int16 *
0x18001775c  mov     rdx, [rsp+118h+var_50]; unsigned __int64
0x180017764  test    r13d, r13d
0x180017767  jz      short loc_1800177AD
0x180017769  mov     eax, [rsp+118h+dwProcessId]
0x18001776d  mov     [rsp+118h+var_F0], r13
0x180017772  mov     [rsp+118h+var_F8], eax; int
0x180017776  lea     r9, aWs; "%ws"
0x18001777d  lea     r8, aWsD04ix; "%ws_%d_%04Ix"
0x180017784  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017789  mov     ebx, eax
0x18001778b  test    eax, eax
0x18001778d  jns     short loc_1800177B7
0x18001778f  mov     rcx, [rsp+118h]; this
0x180017797  mov     r9d, eax; char *
0x18001779a  lea     r8, aOnecoreWindows_6; "onecore\\windows\\accessibletech\\commo"...
0x1800177a1  mov     edx, 62h ; 'b'; void *
0x1800177a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177ab  jmp     short loc_1800177B9
0x1800177ad  test    rdx, rdx
0x1800177b0  jz      short loc_1800177B7
0x1800177b2  xor     eax, eax
0x1800177b4  mov     [rcx], ax
0x1800177b7  xor     ebx, ebx
0x1800177b9  mov     rcx, [rsp+118h]; this
0x1800177c1  test    ebx, ebx
0x1800177c3  jns     short loc_1800177D9
0x1800177c5  mov     r9d, ebx; char *
0x1800177c8  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800177cf  mov     edx, 204h; void *
0x1800177d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800177d9  xorps   xmm0, xmm0
0x1800177dc  movups  [rsp+118h+var_80], xmm0
0x1800177e4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800177ec  movdqu  [rsp+118h+var_70], xmm1
0x1800177f5  xor     eax, eax
0x1800177f7  mov     word ptr [rsp+118h+var_80], ax
0x1800177ff  mov     edx, 104h
0x180017804  lea     rcx, [rsp+118h+var_80]
0x18001780c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180017811  lea     r9, [rsp+118h+var_80]
0x180017819  cmp     qword ptr [rsp+118h+var_70+8], 7
0x180017822  cmova   r9, qword ptr [rsp+118h+var_80]
0x18001782b  lea     rdx, [rsp+118h+var_60]
0x180017833  cmp     [rsp+118h+var_50+8], 7
0x18001783c  cmova   rdx, [rsp+118h+var_60]
0x180017845  mov     r8, qword ptr [rsp+118h+var_70]
0x18001784d  xor     ecx, ecx
0x18001784f  call    ?GetConnectionSequenceEventName@BasicUiaUtils@@SAJW4ConnectionSequenceEventType@1@PEBG_KPEAG_N@Z; BasicUiaUtils::GetConnectionSequenceEventName(BasicUiaUtils::ConnectionSequenceEventType,ushort const *,unsigned __int64,ushort *,bool)
0x180017854  mov     rcx, [rsp+118h]; this
0x18001785c  test    eax, eax
0x18001785e  jns     short loc_180017874
0x180017860  mov     r9d, eax; char *
0x180017863  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18001786a  mov     edx, 209h; void *
0x18001786f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017874  xorps   xmm1, xmm1
0x180017877  movdqu  [rsp+118h+var_B8], xmm1
0x18001787d  lea     r8, [rsp+118h+var_80]
0x180017885  cmp     qword ptr [rsp+118h+var_70+8], 7
0x18001788e  cmova   r8, qword ptr [rsp+118h+var_80]
0x180017897  lea     r9, [rsp+118h+var_A8]
0x18001789c  mov     ebx, 1
0x1800178a1  mov     edx, ebx
0x1800178a3  lea     rcx, [rsp+118h+var_B8]
0x1800178a8  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800178ad  lea     r9, [rsp+118h+var_80]
0x1800178b5  cmp     qword ptr [rsp+118h+var_70+8], 7
0x1800178be  cmova   r9, qword ptr [rsp+118h+var_80]
0x1800178c7  lea     rdx, [rsp+118h+var_60]
0x1800178cf  cmp     [rsp+118h+var_50+8], 7
0x1800178d8  cmova   rdx, [rsp+118h+var_60]
0x1800178e1  mov     r8, qword ptr [rsp+118h+var_70]
0x1800178e9  mov     ecx, ebx
0x1800178eb  call    ?GetConnectionSequenceEventName@BasicUiaUtils@@SAJW4ConnectionSequenceEventType@1@PEBG_KPEAG_N@Z; BasicUiaUtils::GetConnectionSequenceEventName(BasicUiaUtils::ConnectionSequenceEventType,ushort const *,unsigned __int64,ushort *,bool)
0x1800178f0  mov     rcx, [rsp+118h]; this
0x1800178f8  test    eax, eax
0x1800178fa  jns     short loc_180017910
0x1800178fc  mov     r9d, eax; char *
0x1800178ff  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017906  mov     edx, 210h; void *
0x18001790b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017910  xorps   xmm1, xmm1
0x180017913  movdqu  [rsp+118h+var_E0], xmm1
0x180017919  lea     r8, [rsp+118h+var_80]
0x180017921  cmp     qword ptr [rsp+118h+var_70+8], 7
0x18001792a  cmova   r8, qword ptr [rsp+118h+var_80]
0x180017933  lea     r9, [rsp+118h+var_A8]
0x180017938  mov     edx, ebx
0x18001793a  lea     rcx, [rsp+118h+var_E0]
0x18001793f  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180017944  mov     [rsp+118h+var_D0], bl
0x180017948  xor     eax, eax
0x18001794a  mov     [rsp+118h+var_CF], ax
0x18001794f  mov     [rsp+118h+var_CD], al
0x180017953  mov     [rsp+118h+var_CC], esi
0x180017957  cmp     [rsp+118h+arg_20], eax
0x18001795e  jnz     loc_180017AA3
0x180017964  mov     [rsp+118h+var_F0], rdi; char *
0x180017969  mov     qword ptr [rsp+118h+var_F8], 0FFFFFFFFFFFFFFE7h; int
0x180017972  mov     r9, r13; unsigned __int64
0x180017975  lea     r8d, [rax+3Dh]; unsigned int
0x180017979  mov     rdx, r14; HWND
0x18001797c  lea     rcx, [rsp+118h+var_D0]; struct UIA_TIMEOUTDATA *
0x180017981  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180017986  mov     rcx, [rsp+118h]; this
0x18001798e  test    eax, eax
0x180017990  jns     short loc_1800179A6
0x180017992  mov     r9d, eax; char *
0x180017995  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18001799c  mov     edx, 21Eh; void *
0x1800179a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800179a6  cmp     qword ptr [rdi], 10000h
0x1800179ad  jz      short loc_180017A2C
0x1800179af  cmp     qword ptr [rdi], 100000h
0x1800179b6  jz      short loc_180017A01
0x1800179b8  lea     rcx, [rsp+118h+var_E0]
0x1800179bd  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x1800179c2  nop
0x1800179c3  lea     rcx, [rsp+118h+var_B8]
0x1800179c8  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x1800179cd  nop
0x1800179ce  lea     rcx, [rsp+118h+var_80]
0x1800179d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800179db  nop
0x1800179dc  lea     rcx, [rsp+118h+var_60]
0x1800179e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800179e9  nop
0x1800179ea  mov     rcx, [rsp+118h+var_A8.lpSecurityDescriptor]
0x1800179ef  test    rcx, rcx
0x1800179f2  jz      short loc_1800179FA
0x1800179f4  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800179fa  xor     eax, eax
0x1800179fc  jmp     loc_180017B6C
0x180017a01  mov     rcx, [rsp+118h]; this
0x180017a09  lea     rax, aContainerProvi; "Container provider requested cross mach"...
0x180017a10  mov     qword ptr [rsp+118h+var_F8], rax; int
0x180017a15  mov     r9d, 80004005h; char *
0x180017a1b  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017a22  mov     edx, 229h; void *
0x180017a27  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017a2c  mov     edx, esi
0x180017a2e  lea     rcx, [rsp+118h+var_B8]
0x180017a33  call    ?wait@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x180017a38  mov     rcx, [rsp+118h]; this
0x180017a40  test    al, al
0x180017a42  jnz     short loc_180017A5B
0x180017a44  mov     r9d, 5B4h; char *
0x180017a4a  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017a51  mov     edx, 22Fh; void *
0x180017a56  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180017a5b  cmp     qword ptr [rdi], 7FFFFFFFh
0x180017a62  jle     short loc_180017A7B
0x180017a64  mov     r9d, 80004005h; char *
0x180017a6a  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017a71  mov     edx, 233h; void *
0x180017a76  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017a7b  mov     rcx, [rsp+118h]; this
0x180017a83  cmp     qword ptr [rdi], 0FFFFFFFF80000000h
0x180017a8a  jge     short loc_180017AD2
0x180017a8c  mov     r9d, 80004005h; char *
0x180017a92  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017a99  mov     edx, 234h; void *
0x180017a9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017aa3  mov     r8d, esi
0x180017aa6  mov     edx, r13d
0x180017aa9  mov     rcx, r14
0x180017aac  call    cs:__imp_InitializeChannelBasedConnectionForProviderProxy
0x180017ab2  mov     rcx, [rsp+118h]; this
0x180017aba  test    eax, eax
0x180017abc  jns     short loc_180017AD2
0x180017abe  mov     r9d, eax; char *
0x180017ac1  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017ac8  mov     edx, 239h; void *
0x180017acd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017ad2  mov     rax, qword ptr [rsp+118h+var_E0]
0x180017ad7  test    rax, rax
0x180017ada  jz      short loc_180017AE1
0x180017adc  mov     rcx, [rax]
0x180017adf  jmp     short loc_180017AE3
0x180017ae1  xor     ecx, ecx
0x180017ae3  mov     [r12], rcx
0x180017ae7  mov     rbx, [rsp+118h+var_C0]
0x180017aec  add     rbx, 0C8h
0x180017af3  mov     [rsp+118h+var_C0], rbx
0x180017af8  mov     rcx, rbx; this
0x180017afb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180017b00  nop
0x180017b01  lea     rcx, [rbx+50h]
0x180017b05  lea     r9, [rsp+118h+var_E0]
0x180017b0a  mov     r8, r12
0x180017b0d  lea     rdx, [rsp+118h+var_D0]
0x180017b12  call    ??$emplace@AEA_KV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@?$_Hash@V?$_Umap_traits@_KV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEA_K$$QEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x180017b17  nop
0x180017b18  mov     rcx, rbx; _Mtx_t
0x180017b1b  call    cs:__imp__Mtx_unlock
0x180017b21  nop
0x180017b22  lea     rcx, [rsp+118h+var_E0]
0x180017b27  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180017b2c  nop
0x180017b2d  lea     rcx, [rsp+118h+var_B8]
0x180017b32  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180017b37  nop
0x180017b38  lea     rcx, [rsp+118h+var_80]
0x180017b40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017b45  nop
0x180017b46  lea     rcx, [rsp+118h+var_60]
0x180017b4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017b53  nop
0x180017b54  mov     rcx, [rsp+118h+var_A8.lpSecurityDescriptor]
0x180017b59  test    rcx, rcx
0x180017b5c  jz      short loc_180017B64
0x180017b5e  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180017b64  xor     eax, eax
0x180017b66  jmp     short loc_180017B6C
0x180017b68  mov     eax, [rsp+118h+dwProcessId]
0x180017b6c  mov     rcx, [rsp+118h+var_40]
0x180017b74  xor     rcx, rsp; StackCookie
0x180017b77  call    __security_check_cookie
0x180017b7c  add     rsp, 0E0h
0x180017b83  pop     r15
0x180017b85  pop     r14
0x180017b87  pop     r13
0x180017b89  pop     r12
0x180017b8b  pop     rdi
0x180017b8c  pop     rsi
0x180017b8d  pop     rbx
0x180017b8e  retn
```

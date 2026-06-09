# Execution::ActivationManagerShim::ActivateApplicationForContractByAcidAsUserWithHost(HSTRING__ *,HSTRING__ *,IInspectable *,HSTRING__ *,IInspectable *,ACTIVATEOPTIONSINTERNAL,unsigned __int64,ulong *)

- ea: `0x18003fda0`
- end: `0x180040356`
- name: `?ActivateApplicationForContractByAcidAsUserWithHost@ActivationManagerShim@Execution@@UEAAJPEAUHSTRING__@@0PEAUIInspectable@@01W4ACTIVATEOPTIONSINTERNAL@@_KPEAK@Z`
- size: `1462`
- prototype: `int __high(HSTRING, HSTRING, struct IInspectable *, HSTRING, struct IInspectable *, enum ACTIVATEOPTIONSINTERNAL, unsigned __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f520`
- `0x18006d040`
- `0x18006d4a0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180011590`
- `0x180014040`
- `0x1800263e4`
- `0x180029270`
- `0x180033200`
- `0x180036014`
- `0x18003fda0`
- `0x1800462d4`
- `0x18004670c`
- `0x18004c9e8`
- `0x1800501dc`
- `0x18005ae90`
- `0x18005ba40`
- `0x180067e64`
- `0x180069f2c`
- `0x18006a924`
- `0x18006a9c0`
- `0x18006a9e4`
- `0x180070134`
- `0x1800707b8`
- `0x180071ab4`
- `0x180071bec`
- `0x180071cbc`
- `0x18007371c`
- `0x18007eb7c`
- `0x18007ebac`
- `0x18007ec10`
- `0x18007ec78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004001e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004032b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004001e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004032b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fefd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004007d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800400dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004019a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fefd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ff8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004007d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800400dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004019a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040211`
- `combase!__imp_RoGetExtensionRegistration` at `0x18003fe54`
- `combase!__imp_RoGetExtensionRegistration` at `0x18003fe54`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!IsOnDemandRegistrationSupportedForExtensionCategory` at `0x1800401ab`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!IsOnDemandRegistrationSupportedForExtensionCategory` at `0x1800401ab`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionApplicationUserModelId` at `0x18004022f`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionApplicationUserModelId` at `0x18004022f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003fedc`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18003fedc`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Execution::ActivationManagerShim::ActivateApplicationForContractByAcidAsUserWithHost(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        __int64 a4,
        HSTRING string,
        __int64 a6,
        unsigned int a7,
        unsigned __int64 a8,
        unsigned int *a9)
{
  int ExtensionRegistration; // ebx
  __int64 v13; // rbx
  PCWSTR v14; // rax
  __int64 v15; // rax
  PCWSTR v16; // rax
  __int64 v17; // rax
  PCWSTR v18; // rax
  __int64 v19; // rax
  PCWSTR v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  volatile signed __int32 *v23; // rdx
  void *v24; // rcx
  int AppIdForExtensionRegistration; // eax
  int v26; // edi
  __int64 v27; // rbx
  PCWSTR v28; // rax
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // rax
  int v32; // eax
  PCWSTR StringRawBuffer; // r13
  int v34; // eax
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  PCWSTR v37; // rbx
  PCWSTR v38; // rax
  int ExtensionApplicationUserModelId; // eax
  unsigned __int64 v40; // rcx
  int v41; // eax
  unsigned __int16 *v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v48[2]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v49[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  void **v52; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v53[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  char v56; // [rsp+F0h] [rbp-10h]
  LPVOID pv; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v58[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v59[136]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v50 = a4;
  v47 = a1;
  v51 = a6;
  if ( !a9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)0x80004003LL,
      (int)v42);
    return 2147500035LL;
  }
  *a9 = 0;
  v46 = 0;
  v48[1] = 0;
  *(_OWORD *)v49 = 0;
  v48[0] = a3;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v49);
  ExtensionRegistration = RoGetExtensionRegistration(string, a2, a3, v49);
  if ( ExtensionRegistration < 0 )
  {
    LODWORD(v45) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v34 = IsOnDemandRegistrationSupportedForExtensionCategory(StringRawBuffer, &v45);
    v26 = v34;
    if ( v34 >= 0 )
    {
      if ( !(_DWORD)v45 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C1,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
          (const char *)(unsigned int)ExtensionRegistration,
          (int)v42);
        v26 = ExtensionRegistration;
        goto LABEL_32;
      }
      memset_0(v59, 0, 0x104u);
      v37 = WindowsGetStringRawBuffer(a3, 0);
      v38 = WindowsGetStringRawBuffer(a2, 0);
      v42 = v59;
      ExtensionApplicationUserModelId = GetExtensionApplicationUserModelId(v38, StringRawBuffer, v37, 130);
      v26 = ExtensionApplicationUserModelId;
      if ( ExtensionApplicationUserModelId >= 0 )
      {
        v44[0] = 0;
        v40 = -1;
        do
          ++v40;
        while ( v59[v40] );
        v26 = ULongLongToUInt(v40, v44);
        if ( v26 < 0
          || (v26 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v46, v59, v44[0]),
              v26 < 0) )
        {
          v35 = (unsigned int)v26;
          v36 = 967;
          goto LABEL_31;
        }
        goto LABEL_27;
      }
      v35 = (unsigned int)ExtensionApplicationUserModelId;
      v36 = 966;
    }
    else
    {
      v35 = (unsigned int)v34;
      v36 = 960;
    }
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v35,
      (int)v42);
    goto LABEL_32;
  }
  *(_QWORD *)v44 = 0;
  v52 = &tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable';
  v53[0] = 0;
  v53[1] = &v52;
  v53[2] = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,>(&pv);
  tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::data(
    v44,
    &v45);
  v13 = v45;
  *(_DWORD *)(v13 + 276) = GetProfile((unsigned int *)(v45 + 272));
  *(_BYTE *)(v13 + 280) = IsTempProfilePostBootReminderSet();
  *(_BYTE *)(v13 + 281) = IsAuditMode();
  *(_BYTE *)(v13 + 282) = GetSystemMetrics(67) != 0;
  *(_BYTE *)(v13 + 283) = IsRunningOnLocalSystem();
  v14 = WindowsGetStringRawBuffer(string, 0);
  v15 = std::wstring::wstring(v58, v14);
  std::wstring::operator=(v13 + 320, v15);
  std::wstring::_Tidy_deallocate(v58);
  v16 = WindowsGetStringRawBuffer(a2, 0);
  v17 = std::wstring::wstring(v58, v16);
  std::wstring::operator=(v13 + 288, v17);
  std::wstring::_Tidy_deallocate(v58);
  v18 = WindowsGetStringRawBuffer(a3, 0);
  v19 = std::wstring::wstring(v58, v18);
  std::wstring::operator=(v13 + 352, v19);
  std::wstring::_Tidy_deallocate(v58);
  v20 = WindowsGetStringRawBuffer(v48[1], 0);
  v21 = std::wstring::wstring(v58, v20);
  std::wstring::operator=(v13 + 384, v21);
  std::wstring::_Tidy_deallocate(v58);
  tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::close(&v45);
  v22 = tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::start_and_watch_errors(
          v44,
          v58);
  v23 = *(volatile signed __int32 **)(v22 + 56);
  v24 = pv;
  pv = (LPVOID)v23;
  if ( v23 )
    _InterlockedIncrement(v23 + 112);
  if ( v24 )
    tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>::Release(v24);
  wil::details::ThreadFailureCallbackHolder::SetWatching(
    (wil::details::ThreadFailureCallbackHolder *)v53,
    *(_DWORD *)(v22 + 32) != 0);
  tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(v58);
  WindowsDeleteString(v49[1]);
  v49[1] = 0;
  WindowsDeleteString(v46);
  v46 = 0;
  AppIdForExtensionRegistration = GetAppIdForExtensionRegistration(
                                    (struct Windows::Foundation::IExtensionRegistration *)v49[0],
                                    &v46,
                                    &v49[1]);
  v26 = AppIdForExtensionRegistration;
  if ( AppIdForExtensionRegistration < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3AC,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)AppIdForExtensionRegistration,
      (int)v42);
    tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::data(
      v44,
      &v47);
    v27 = v47;
    *(_DWORD *)(v47 + 284) = v26;
    v28 = WindowsGetStringRawBuffer(v46, 0);
    v29 = std::wstring::wstring(v58, v28);
    std::wstring::operator=(v27 + 416, v29);
    std::wstring::_Tidy_deallocate(v58);
    tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::close(&v47);
    v30 = SetPackageStatusMachineRegisterOnRepair(a2);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v30,
        v43);
    v31 = WindowsGetStringRawBuffer(a2, 0);
    v32 = ReRegisterPackageIfNeeded(v31, -2144927148);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v32,
        v43);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B6,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v26,
      v43);
    tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(&v47);
    tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(&v45);
    tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(&v52);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>(v44);
    goto LABEL_32;
  }
  if ( *(_QWORD *)v44 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(*(_QWORD *)v44 + 8LL);
  tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(&v45);
  tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(&v52);
  wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>(v44);
LABEL_27:
  v41 = Execution::ActivationManagerShim::ActivateApplicationForContractCore(
          v47 - 48,
          v46,
          string,
          a8,
          a7,
          v51,
          0,
          (__int64)v48,
          v50,
          0,
          0,
          0,
          a9,
          0);
  v26 = v41;
  if ( v41 < 0 )
  {
    v35 = (unsigned int)v41;
    v36 = 983;
    goto LABEL_31;
  }
  v26 = 0;
LABEL_32:
  ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)v48);
  WindowsDeleteString(v46);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18003fda0  push    rbp
0x18003fda2  push    rbx
0x18003fda3  push    rsi
0x18003fda4  push    rdi
0x18003fda5  push    r12
0x18003fda7  push    r13
0x18003fda9  push    r14
0x18003fdab  push    r15
0x18003fdad  lea     rbp, [rsp-168h]
0x18003fdb5  sub     rsp, 268h
0x18003fdbc  mov     rax, cs:__security_cookie
0x18003fdc3  xor     rax, rsp
0x18003fdc6  mov     [rbp+1A0h+var_50], rax
0x18003fdcd  mov     [rbp+1A0h+var_1F0], r9
0x18003fdd1  mov     r14, r8
0x18003fdd4  mov     rsi, rdx
0x18003fdd7  mov     [rbp+1A0h+var_218], rcx
0x18003fddb  mov     r15, [rbp+1A0h+string]
0x18003fde2  mov     rax, [rbp+1A0h+arg_28]
0x18003fde9  mov     [rbp+1A0h+var_1E8], rax
0x18003fded  mov     r12, [rbp+1A0h+arg_40]
0x18003fdf4  xor     r13d, r13d
0x18003fdf7  test    r12, r12
0x18003fdfa  jnz     short loc_18003FE23
0x18003fdfc  mov     rcx, [rbp+1A8h]; this
0x18003fe03  mov     ebx, 80004003h
0x18003fe08  mov     r9d, ebx; char *
0x18003fe0b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003fe12  mov     edx, 38Ch; void *
0x18003fe17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe1c  mov     eax, ebx
0x18003fe1e  jmp     loc_180040333
0x18003fe23  mov     [r12], r13d
0x18003fe27  mov     [rbp+1A0h+var_220], r13
0x18003fe2b  xorps   xmm0, xmm0
0x18003fe2e  movups  xmmword ptr [rbp+1A0h+var_210], xmm0
0x18003fe32  xorps   xmm1, xmm1
0x18003fe35  movdqu  xmmword ptr [rbp+1A0h+var_200], xmm1
0x18003fe3a  mov     [rbp+1A0h+var_210], r14
0x18003fe3e  lea     rcx, [rbp+1A0h+var_200]
0x18003fe42  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fe47  lea     r9, [rbp+1A0h+var_200]
0x18003fe4b  mov     r8, r14
0x18003fe4e  mov     rdx, rsi
0x18003fe51  mov     rcx, r15
0x18003fe54  call    cs:__imp_RoGetExtensionRegistration
0x18003fe5a  mov     ebx, eax
0x18003fe5c  test    eax, eax
0x18003fe5e  js      loc_180040190
0x18003fe64  mov     qword ptr [rsp+2A0h+var_230], r13
0x18003fe69  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable'
0x18003fe70  mov     [rbp+1A0h+var_1E0], rax
0x18003fe74  mov     [rbp+1A0h+var_1D8], r13
0x18003fe78  lea     rax, [rbp+1A0h+var_1E0]
0x18003fe7c  mov     [rbp+1A0h+var_1D0], rax
0x18003fe80  mov     [rbp+1A0h+var_1C8], r13
0x18003fe84  mov     [rbp+1A0h+var_1C0], r13d
0x18003fe88  mov     [rbp+1A0h+var_1B8], r13
0x18003fe8c  mov     [rbp+1A0h+var_1B0], r13b
0x18003fe90  lea     rcx, [rbp+1A0h+pv]
0x18003fe94  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,>(void)
0x18003fe99  nop
0x18003fe9a  lea     rdx, [rsp+2A0h+var_228]
0x18003fe9f  lea     rcx, [rsp+2A0h+var_230]
0x18003fea4  call    ?data@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::data(void)
0x18003fea9  nop
0x18003feaa  mov     rbx, [rsp+2A0h+var_228]
0x18003feaf  lea     rcx, [rbx+110h]; unsigned int *
0x18003feb6  call    ?GetProfile@@YAJAEAK@Z; GetProfile(ulong &)
0x18003febb  mov     [rbx+114h], eax
0x18003fec1  call    ?IsTempProfilePostBootReminderSet@@YA_NXZ; IsTempProfilePostBootReminderSet(void)
0x18003fec6  mov     [rbx+118h], al
0x18003fecc  call    ?IsAuditMode@@YA_NXZ; IsAuditMode(void)
0x18003fed1  mov     [rbx+119h], al
0x18003fed7  mov     ecx, 43h ; 'C'; nIndex
0x18003fedc  call    cs:__imp_GetSystemMetrics
0x18003fee2  test    eax, eax
0x18003fee4  setnz   al
0x18003fee7  mov     [rbx+11Ah], al
0x18003feed  call    ?IsRunningOnLocalSystem@@YA_NXZ; IsRunningOnLocalSystem(void)
0x18003fef2  mov     [rbx+11Bh], al
0x18003fef8  xor     edx, edx; length
0x18003fefa  mov     rcx, r15; string
0x18003fefd  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ff03  mov     rdx, rax
0x18003ff06  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ff0f  lea     rcx, [rbx+140h]
0x18003ff16  mov     rdx, rax
0x18003ff19  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ff1e  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ff27  xor     edx, edx; length
0x18003ff29  mov     rcx, rsi; string
0x18003ff2c  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ff32  mov     rdx, rax
0x18003ff35  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ff3e  lea     rcx, [rbx+120h]
0x18003ff45  mov     rdx, rax
0x18003ff48  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ff4d  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ff56  xor     edx, edx; length
0x18003ff58  mov     rcx, r14; string
0x18003ff5b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ff61  mov     rdx, rax
0x18003ff64  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ff6d  lea     rcx, [rbx+160h]
0x18003ff74  mov     rdx, rax
0x18003ff77  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ff7c  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ff85  xor     edx, edx; length
0x18003ff87  mov     rcx, [rbp+1A0h+var_210+8]; string
0x18003ff8b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ff91  mov     rdx, rax
0x18003ff94  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ff98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ff9d  lea     rcx, [rbx+180h]
0x18003ffa4  mov     rdx, rax
0x18003ffa7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ffac  lea     rcx, [rbp+1A0h+var_1A0]
0x18003ffb0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ffb5  lea     rcx, [rsp+2A0h+var_228]
0x18003ffba  call    ?close@?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::close(void)
0x18003ffbf  lea     rdx, [rbp+1A0h+var_1A0]
0x18003ffc3  lea     rcx, [rsp+2A0h+var_230]
0x18003ffc8  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::start_and_watch_errors(void)
0x18003ffcd  mov     rbx, rax
0x18003ffd0  mov     rdx, [rax+38h]
0x18003ffd4  mov     rcx, [rbp+1A0h+pv]; pv
0x18003ffd8  mov     [rbp+1A0h+pv], rdx
0x18003ffdc  test    rdx, rdx
0x18003ffdf  jz      short loc_18003FFE8
0x18003ffe1  lock inc dword ptr [rdx+1C0h]
0x18003ffe8  test    rcx, rcx
0x18003ffeb  jz      short loc_18003FFF2
0x18003ffed  call    ?Release@?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>::Release(void)
0x18003fff2  cmp     [rbx+20h], r13d
0x18003fff6  setnz   dl; bool
0x18003fff9  lea     rcx, [rbp+1A0h+var_1D8]; this
0x18003fffd  call    ?SetWatching@ThreadFailureCallbackHolder@details@wil@@QEAAX_N@Z; wil::details::ThreadFailureCallbackHolder::SetWatching(bool)
0x180040002  nop
0x180040003  lea     rcx, [rbp+1A0h+var_1A0]
0x180040007  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x18004000c  mov     rcx, [rbp+1A0h+var_200+8]; string
0x180040010  call    cs:__imp_WindowsDeleteString
0x180040016  mov     [rbp+1A0h+var_200+8], r13
0x18004001a  mov     rcx, [rbp+1A0h+var_220]; string
0x18004001e  call    cs:__imp_WindowsDeleteString
0x180040024  mov     [rbp+1A0h+var_220], r13
0x180040028  lea     r8, [rbp+1A0h+var_200+8]; HSTRING *
0x18004002c  lea     rdx, [rbp+1A0h+var_220]; HSTRING *
0x180040030  mov     rcx, [rbp+1A0h+var_200]; struct Windows::Foundation::IExtensionRegistration *
0x180040034  call    ?GetAppIdForExtensionRegistration@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUHSTRING__@@1@Z; GetAppIdForExtensionRegistration(Windows::Foundation::IExtensionRegistration *,HSTRING__ * *,HSTRING__ * *)
0x180040039  mov     edi, eax
0x18004003b  mov     rcx, [rbp+1A8h]; this
0x180040042  test    eax, eax
0x180040044  jns     loc_180040158
0x18004004a  mov     r9d, eax; char *
0x18004004d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180040054  mov     edx, 3ACh; void *
0x180040059  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004005e  lea     rdx, [rbp+1A0h+var_218]
0x180040062  lea     rcx, [rsp+2A0h+var_230]
0x180040067  call    ?data@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::data(void)
0x18004006c  nop
0x18004006d  mov     rbx, [rbp+1A0h+var_218]
0x180040071  mov     [rbx+11Ch], edi
0x180040077  xor     edx, edx; length
0x180040079  mov     rcx, [rbp+1A0h+var_220]; string
0x18004007d  call    cs:__imp_WindowsGetStringRawBuffer
0x180040083  mov     rdx, rax
0x180040086  lea     rcx, [rbp+1A0h+var_1A0]
0x18004008a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004008f  lea     rcx, [rbx+1A0h]
0x180040096  mov     rdx, rax
0x180040099  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004009e  lea     rcx, [rbp+1A0h+var_1A0]
0x1800400a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800400a7  lea     rcx, [rbp+1A0h+var_218]
0x1800400ab  call    ?close@?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::close(void)
0x1800400b0  mov     rcx, rsi; HSTRING
0x1800400b3  call    ?SetPackageStatusMachineRegisterOnRepair@@YAJPEAUHSTRING__@@@Z; SetPackageStatusMachineRegisterOnRepair(HSTRING__ *)
0x1800400b8  mov     rcx, [rbp+1A8h]; this
0x1800400bf  test    eax, eax
0x1800400c1  jns     short loc_1800400D7
0x1800400c3  mov     r9d, eax; char *
0x1800400c6  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800400cd  mov     edx, 3B4h; void *
0x1800400d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800400d7  xor     edx, edx; length
0x1800400d9  mov     rcx, rsi; string
0x1800400dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800400e2  mov     rcx, rax; unsigned __int16 *
0x1800400e5  mov     edx, 80270254h; int
0x1800400ea  call    ?ReRegisterPackageIfNeeded@@YAJPEBGJ@Z; ReRegisterPackageIfNeeded(ushort const *,long)
0x1800400ef  mov     rcx, [rbp+1A8h]; this
0x1800400f6  test    eax, eax
0x1800400f8  jns     short loc_18004010E
0x1800400fa  mov     r9d, eax; char *
0x1800400fd  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180040104  mov     edx, 3B5h; void *
0x180040109  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004010e  mov     rcx, [rbp+1A8h]; this
0x180040115  mov     r9d, edi; char *
0x180040118  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004011f  mov     edx, 3B6h; void *
0x180040124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040129  nop
0x18004012a  lea     rcx, [rbp+1A0h+var_218]
0x18004012e  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x180040133  nop
0x180040134  lea     rcx, [rsp+2A0h+var_228]
0x180040139  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x18004013e  nop
0x18004013f  lea     rcx, [rbp+1A0h+var_1E0]
0x180040143  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x180040148  nop
0x180040149  lea     rcx, [rsp+2A0h+var_230]
0x18004014e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>(void)
0x180040153  jmp     loc_18004031D
0x180040158  mov     rcx, qword ptr [rsp+2A0h+var_230]
0x18004015d  test    rcx, rcx
0x180040160  jz      short loc_18004016C
0x180040162  add     rcx, 8
0x180040166  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18004016b  nop
0x18004016c  lea     rcx, [rsp+2A0h+var_228]
0x180040171  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x180040176  nop
0x180040177  lea     rcx, [rbp+1A0h+var_1E0]
0x18004017b  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>>(void)
0x180040180  nop
0x180040181  lea     rcx, [rsp+2A0h+var_230]
0x180040186  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath1TipTest>,wil::err_returncode_policy>(void)
0x18004018b  jmp     loc_18004028E
0x180040190  mov     dword ptr [rsp+2A0h+var_228], r13d
0x180040195  xor     edx, edx; length
0x180040197  mov     rcx, r15; string
0x18004019a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800401a0  mov     r13, rax
0x1800401a3  lea     rdx, [rsp+2A0h+var_228]
0x1800401a8  mov     rcx, rax
0x1800401ab  call    cs:__imp_IsOnDemandRegistrationSupportedForExtensionCategory
0x1800401b1  mov     edi, eax
0x1800401b3  test    eax, eax
0x1800401b5  jns     short loc_1800401C4
0x1800401b7  mov     r9d, eax
0x1800401ba  mov     edx, 3C0h
0x1800401bf  jmp     loc_180040309
0x1800401c4  cmp     dword ptr [rsp+2A0h+var_228], 0
0x1800401c9  jnz     short loc_1800401ED
0x1800401cb  mov     rcx, [rbp+1A8h]; this
0x1800401d2  mov     r9d, ebx; char *
0x1800401d5  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800401dc  mov     edx, 3C1h; void *
0x1800401e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401e6  mov     edi, ebx
0x1800401e8  jmp     loc_18004031D
0x1800401ed  xor     edx, edx; Val
0x1800401ef  mov     r8d, 104h; Size
0x1800401f5  lea     rcx, [rbp+1A0h+var_160]; void *
0x1800401f9  call    memset_0
0x1800401fe  xor     edx, edx; length
0x180040200  mov     rcx, r14; string
0x180040203  call    cs:__imp_WindowsGetStringRawBuffer
0x180040209  mov     rbx, rax
0x18004020c  xor     edx, edx; length
0x18004020e  mov     rcx, rsi; string
0x180040211  call    cs:__imp_WindowsGetStringRawBuffer
0x180040217  lea     rcx, [rbp+1A0h+var_160]
0x18004021b  mov     qword ptr [rsp+2A0h+var_280], rcx; int
0x180040220  mov     r9d, 82h
0x180040226  mov     r8, rbx
0x180040229  mov     rdx, r13
0x18004022c  mov     rcx, rax
0x18004022f  call    cs:__imp_GetExtensionApplicationUserModelId
0x180040235  mov     edi, eax
0x180040237  xor     r13d, r13d
0x18004023a  test    eax, eax
0x18004023c  jns     short loc_18004024B
0x18004023e  mov     r9d, eax
0x180040241  mov     edx, 3C6h
0x180040246  jmp     loc_180040309
0x18004024b  mov     [rsp+2A0h+var_230], r13d
0x180040250  lea     rax, [rbp+1A0h+var_160]
0x180040254  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040258  inc     rcx; unsigned __int64
0x18004025b  cmp     [rax+rcx*2], r13w
0x180040260  jnz     short loc_180040258
0x180040262  lea     rdx, [rsp+2A0h+var_230]; unsigned int *
0x180040267  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004026c  mov     edi, eax
0x18004026e  test    eax, eax
0x180040270  js      loc_180040301
0x180040276  mov     r8d, [rsp+2A0h+var_230]; unsigned int
0x18004027b  lea     rdx, [rbp+1A0h+var_160]; unsigned __int16 *
  ... truncated ...
```

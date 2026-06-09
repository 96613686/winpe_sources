# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues(IInspectable * *)

- ea: `0x1800171a0`
- end: `0x18001778e`
- name: `?GetPossibleValues@CPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1518`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002350`
- `0x180002380`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x180010b20`
- `0x180013c78`
- `0x1800171a0`
- `0x18001868c`
- `0x18001879c`
- `0x18001b7e0`
- `0x18001cf10`
- `0x18001de10`
- `0x180025920`
- `0x180025ebc`
- `0x180025f00`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001748f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001764f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800173dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001748f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001764f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017237`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001774e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017237`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001774e`
- `WDSCORE!CurrentIP` at `0x1800171d8`
- `WDSCORE!CurrentIP` at `0x180017700`
- `WDSCORE!CurrentIP` at `0x1800171d8`
- `WDSCORE!CurrentIP` at `0x180017700`

## string_xrefs

- `0x18001758e`: `Failed to create property value for snapshot cadence hourly value`
- `0x1800174ce`: `Failed to create property value for snapshot cadence custom value`
- `0x18001727d`: `Failed to create possible values collection for snapshot cadence setting`
- `0x180017576`: `Failed to copy possible values collection to return parameter`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *this,
        struct IInspectable **a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  void *v6; // rax
  __int64 v7; // rax
  int ResourceStringValue; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  struct IInspectable **v13; // r8
  char v14; // r15
  signed int i; // r14d
  HSTRING *v16; // r8
  unsigned int v17; // edi
  HSTRING v18; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v20; // edi
  __int64 v21; // r9
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v22; // rax
  struct IInspectable *v23; // rcx
  HSTRING *v24; // r8
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v25; // rax
  unsigned int SnapshotCadenceSelectedValue; // edi
  HSTRING v27; // rbx
  const unsigned __int16 *v28; // rax
  __int64 v29; // r9
  struct IInspectable *v30; // rcx
  struct IInspectable *v31; // rcx
  struct IInspectable *v32; // rcx
  struct IInspectable *v33; // rcx
  struct IInspectable *v34; // rcx
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  char *v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+60h] [rbp-A0h]
  struct IInspectable *v40; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v42[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues: Getting PITR "
         "snapshot cadence possible values");
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    615,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues",
    v4,
    LastError,
    0,
    0);
  *a2 = 0;
  v39 = 0;
  v6 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6
    && (v7 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v6)) != 0 )
  {
    ResourceStringValue = 0;
    v39 = v7;
  }
  else
  {
    ResourceStringValue = -2147024882;
  }
  if ( ResourceStringValue < 0 )
  {
    v9 = "Failed to create possible values collection for snapshot cadence setting";
    v10 = 620;
    goto LABEL_7;
  }
  Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  if ( !(unsigned int)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITROn(Current) )
  {
    v40 = 0;
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_DisabledValue",
                            (const unsigned __int16 *)&v40,
                            v13);
    if ( ResourceStringValue >= 0 )
    {
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v39,
        0,
        v40,
        1);
      v34 = v40;
      if ( v40 )
      {
        v40 = 0;
        ((void (__fastcall *)(struct IInspectable *))v34->lpVtbl->Release)(v34);
      }
      goto LABEL_35;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringValue,
      (int)"Failed to get resource string for snapshot cadence disabled value",
      v38);
    v33 = v40;
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(struct IInspectable *))v33->lpVtbl->Release)(v33);
    }
    goto LABEL_8;
  }
  v14 = 0;
  for ( i = 0; (unsigned int)i < 5; ++i )
  {
    WindowsDeleteString(0);
    string[0] = 0;
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringById(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_HourlyValue",
                            string,
                            v16);
    if ( ResourceStringValue < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x277,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)ResourceStringValue,
        (int)"Failed to get resource string for snapshot cadence hourly value",
        v38);
LABEL_45:
      WindowsDeleteString(string[0]);
      goto LABEL_8;
    }
    v17 = *((_DWORD *)qword_18003AAF0 + i);
    v18 = string[0];
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v20 = StringCchPrintfW(v42, 0x104u, StringRawBuffer, v17);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x27B,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)v20,
        (int)"Failed to format snapshot cadence hourly value string",
        v38);
      goto LABEL_41;
    }
    v40 = 0;
    v20 = SystemSettings::DataModel::PropValueHelper::CreateString(v42, &v40);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x27F,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)v20,
        (int)"Failed to create property value for snapshot cadence hourly value",
        v38);
      v32 = v40;
      if ( v40 )
      {
        v40 = 0;
        ((void (__fastcall *)(struct IInspectable *))v32->lpVtbl->Release)(v32);
      }
LABEL_41:
      WindowsDeleteString(v18);
      if ( v39 )
        goto LABEL_42;
      return (unsigned int)v20;
    }
    LOBYTE(v21) = 1;
    Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
      v39,
      0,
      v40,
      v21);
    v22 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
    if ( SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(v22) == 60 * *((_DWORD *)qword_18003AAF0 + i) )
      v14 = 1;
    v23 = v40;
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(struct IInspectable *))v23->lpVtbl->Release)(v23);
    }
    WindowsDeleteString(v18);
  }
  if ( v14 )
    goto LABEL_35;
  WindowsDeleteString(0);
  string[0] = 0;
  ResourceStringValue = SystemSettings::DataModel::GetResourceStringById(
                          (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_CustomValue",
                          string,
                          v24);
  if ( ResourceStringValue < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x291,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringValue,
      (int)"Failed to get resource string for snapshot cadence custom value",
      v38);
    goto LABEL_45;
  }
  v25 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SnapshotCadenceSelectedValue = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(v25);
  v27 = string[0];
  v28 = WindowsGetStringRawBuffer(string[0], 0);
  v20 = StringCchPrintfW(v42, 0x104u, v28, SnapshotCadenceSelectedValue);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x295,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)v20,
      (int)"Failed to format snapshot cadence custom value string",
      v38);
    goto LABEL_26;
  }
  v40 = 0;
  v20 = SystemSettings::DataModel::PropValueHelper::CreateString(v42, &v40);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x299,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)v20,
      (int)"Failed to create property value for snapshot cadence custom value",
      v38);
    v30 = v40;
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(struct IInspectable *))v30->lpVtbl->Release)(v30);
    }
LABEL_26:
    WindowsDeleteString(v27);
    if ( v39 )
LABEL_42:
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
    return (unsigned int)v20;
  }
  LOBYTE(v29) = 1;
  Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
    v39,
    0,
    v40,
    v29);
  v31 = v40;
  if ( v40 )
  {
    v40 = 0;
    ((void (__fastcall *)(struct IInspectable *))v31->lpVtbl->Release)(v31);
  }
  WindowsDeleteString(v27);
LABEL_35:
  ResourceStringValue = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::QueryInterface(
                          v39,
                          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                          a2);
  if ( ResourceStringValue >= 0 )
  {
    v35 = GetLastError();
    v36 = CurrentIP();
    v37 = ConstructPartialMsgW(
            0x4000000u,
            "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues: Exiting...");
    WdsSetupLogMessageW(
      v37,
      0,
      L"D",
      0,
      682,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetPossibleValues",
      v36,
      v35,
      0,
      0);
    if ( v39 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
    return 0;
  }
  else
  {
    v9 = "Failed to copy possible values collection to return parameter";
    v10 = 680;
LABEL_7:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringValue,
      (int)v9,
      v38);
LABEL_8:
    if ( v39 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
    return (unsigned int)ResourceStringValue;
  }
}

```

## disassembly

```asm
0x1800171a0  push    rbp
0x1800171a2  push    rbx
0x1800171a3  push    rsi
0x1800171a4  push    rdi
0x1800171a5  push    r12
0x1800171a7  push    r13
0x1800171a9  push    r14
0x1800171ab  push    r15
0x1800171ad  lea     rbp, [rsp-1A8h]
0x1800171b5  sub     rsp, 2A8h
0x1800171bc  mov     rax, cs:__security_cookie
0x1800171c3  xor     rax, rsp
0x1800171c6  mov     [rbp+1E0h+var_50], rax
0x1800171cd  mov     r13, rdx
0x1800171d0  call    cs:__imp_GetLastError
0x1800171d6  mov     edi, eax
0x1800171d8  call    cs:__imp_CurrentIP
0x1800171de  mov     rbx, rax
0x1800171e1  lea     rdx, aSystemsettings_105; "SystemSettings::PointInTimeRestore::CPo"...
0x1800171e8  mov     ecx, 4000000h; unsigned int
0x1800171ed  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800171f2  xor     r12d, r12d
0x1800171f5  mov     [rsp+2E0h+var_290], r12d
0x1800171fa  mov     [rsp+2E0h+var_298], r12
0x1800171ff  mov     [rsp+2E0h+var_2A0], edi
0x180017203  mov     [rsp+2E0h+var_2A8], rbx
0x180017208  lea     r14, aSystemsettings_71; "SystemSettings::PointInTimeRestore::CPo"...
0x18001720f  mov     [rsp+2E0h+var_2B0], r14
0x180017214  lea     r15, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001721b  mov     [rsp+2E0h+var_2B8], r15; char *
0x180017220  mov     [rsp+2E0h+var_2C0], 267h
0x180017228  xor     r9d, r9d
0x18001722b  lea     r8, aD; "D"
0x180017232  xor     edx, edx
0x180017234  mov     rcx, rax
0x180017237  call    cs:__imp_WdsSetupLogMessageW
0x18001723d  mov     [r13+0], r12
0x180017241  mov     [rsp+2E0h+var_280], r12
0x180017246  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001724d  mov     ecx, 0B8h; unsigned __int64
0x180017252  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017257  test    rax, rax
0x18001725a  jz      short loc_180017274
0x18001725c  mov     rcx, rax
0x18001725f  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x180017264  nop
0x180017265  test    rax, rax
0x180017268  jz      short loc_180017274
0x18001726a  mov     ebx, r12d
0x18001726d  mov     [rsp+2E0h+var_280], rax
0x180017272  jmp     short loc_180017279
0x180017274  mov     ebx, 8007000Eh
0x180017279  test    ebx, ebx
0x18001727b  jns     short loc_1800172C0
0x18001727d  lea     rax, aFailedToCreate_6; "Failed to create possible values collec"...
0x180017284  mov     edx, 26Ch; void *
0x180017289  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017290  mov     r9d, ebx; char *
0x180017293  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017298  mov     rcx, [rbp+1E8h]; this
0x18001729f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800172a4  nop
0x1800172a5  mov     rcx, [rsp+2E0h+var_280]
0x1800172aa  test    rcx, rcx
0x1800172ad  jz      short loc_1800172B9
0x1800172af  mov     [rsp+2E0h+var_280], r12
0x1800172b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x1800172b9  mov     eax, ebx
0x1800172bb  jmp     loc_18001776B
0x1800172c0  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x1800172c5  mov     rcx, rax; this
0x1800172c8  call    ?GetPITROn@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAHXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITROn(void)
0x1800172cd  test    eax, eax
0x1800172cf  jz      loc_18001765A
0x1800172d5  mov     r15b, r12b
0x1800172d8  mov     r14d, r12d
0x1800172db  mov     esi, 1
0x1800172e0  xor     ecx, ecx; string
0x1800172e2  call    cs:__imp_WindowsDeleteString
0x1800172e8  mov     [rsp+2E0h+string], r12
0x1800172ed  lea     rdx, [rsp+2E0h+string]; HSTRING *
0x1800172f2  lea     rcx, aSystemsettings_89; "SystemSettings_Misc_PointInTimeRestore_"...
0x1800172f9  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800172fe  mov     ebx, eax
0x180017300  test    eax, eax
0x180017302  js      loc_180017622
0x180017308  movsxd  r12, r14d
0x18001730b  lea     rax, qword_18003AAF0
0x180017312  mov     edi, [rax+r12*4]
0x180017316  xor     edx, edx; length
0x180017318  mov     rbx, [rsp+2E0h+string]
0x18001731d  mov     rcx, rbx; string
0x180017320  call    cs:__imp_WindowsGetStringRawBuffer
0x180017326  mov     r9d, edi
0x180017329  mov     r8, rax; unsigned __int16 *
0x18001732c  mov     edx, 104h; unsigned __int64
0x180017331  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017335  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001733a  mov     edi, eax
0x18001733c  test    eax, eax
0x18001733e  js      loc_1800175D1
0x180017344  mov     [rsp+2E0h+var_278], 0
0x18001734d  lea     rdx, [rsp+2E0h+var_278]; struct IInspectable **
0x180017352  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017356  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18001735b  mov     edi, eax
0x18001735d  test    eax, eax
0x18001735f  js      loc_180017587
0x180017365  mov     r9b, sil
0x180017368  mov     r8, [rsp+2E0h+var_278]
0x18001736d  xor     edx, edx
0x18001736f  mov     rcx, [rsp+2E0h+var_280]
0x180017374  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180017379  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001737e  mov     rcx, rax; this
0x180017381  call    ?GetSnapshotCadenceSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(void)
0x180017386  lea     rcx, qword_18003AAF0
0x18001738d  imul    ecx, [rcx+r12*4], 3Ch ; '<'
0x180017392  movzx   r15d, r15b
0x180017396  cmp     eax, ecx
0x180017398  cmovz   r15d, esi
0x18001739c  mov     rcx, [rsp+2E0h+var_278]
0x1800173a1  xor     r12d, r12d
0x1800173a4  test    rcx, rcx
0x1800173a7  jz      short loc_1800173BB
0x1800173a9  mov     [rsp+2E0h+var_278], r12
0x1800173ae  mov     rax, [rcx]
0x1800173b1  mov     rax, [rax+10h]
0x1800173b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173ba  nop
0x1800173bb  mov     rcx, rbx; string
0x1800173be  call    cs:__imp_WindowsDeleteString
0x1800173c4  add     r14d, esi
0x1800173c7  cmp     r14d, 5
0x1800173cb  jb      loc_1800172E0
0x1800173d1  test    r15b, r15b
0x1800173d4  jnz     loc_18001754A
0x1800173da  xor     ecx, ecx; string
0x1800173dc  call    cs:__imp_WindowsDeleteString
0x1800173e2  mov     [rsp+2E0h+string], r12
0x1800173e7  lea     rdx, [rsp+2E0h+string]; HSTRING *
0x1800173ec  lea     rcx, aSystemsettings_60; "SystemSettings_Misc_PointInTimeRestore_"...
0x1800173f3  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800173f8  mov     ebx, eax
0x1800173fa  test    eax, eax
0x1800173fc  jns     short loc_18001742B
0x1800173fe  mov     rcx, [rbp+1E8h]; this
0x180017405  lea     rax, aFailedToGetRes_4; "Failed to get resource string for snaps"...
0x18001740c  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017411  mov     r9d, ebx; char *
0x180017414  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x18001741b  mov     edx, 291h; void *
0x180017420  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017425  nop
0x180017426  jmp     loc_18001764A
0x18001742b  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180017430  mov     rcx, rax; this
0x180017433  call    ?GetSnapshotCadenceSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(void)
0x180017438  mov     edi, eax
0x18001743a  xor     edx, edx; length
0x18001743c  mov     rbx, [rsp+2E0h+string]
0x180017441  mov     rcx, rbx; string
0x180017444  call    cs:__imp_WindowsGetStringRawBuffer
0x18001744a  mov     r9d, edi
0x18001744d  mov     r8, rax; unsigned __int16 *
0x180017450  mov     edx, 104h; unsigned __int64
0x180017455  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017459  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001745e  mov     edi, eax
0x180017460  test    eax, eax
0x180017462  jns     short loc_1800174AE
0x180017464  mov     rcx, [rbp+1E8h]; this
0x18001746b  lea     rax, aFailedToFormat_9; "Failed to format snapshot cadence custo"...
0x180017472  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017477  mov     r9d, edi; char *
0x18001747a  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017481  mov     edx, 295h; void *
0x180017486  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001748b  nop
0x18001748c  mov     rcx, rbx; string
0x18001748f  call    cs:__imp_WindowsDeleteString
0x180017495  nop
0x180017496  mov     rcx, [rsp+2E0h+var_280]
0x18001749b  test    rcx, rcx
0x18001749e  jz      loc_18001761B
0x1800174a4  mov     [rsp+2E0h+var_280], r12
0x1800174a9  jmp     loc_180017616
0x1800174ae  mov     [rsp+2E0h+var_278], r12
0x1800174b3  lea     rdx, [rsp+2E0h+var_278]; struct IInspectable **
0x1800174b8  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x1800174bc  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800174c1  mov     edi, eax
0x1800174c3  test    eax, eax
0x1800174c5  jns     short loc_180017510
0x1800174c7  mov     rcx, [rbp+1E8h]; this
0x1800174ce  lea     rax, aFailedToCreate_17; "Failed to create property value for sna"...
0x1800174d5  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800174da  mov     r9d, edi; char *
0x1800174dd  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800174e4  mov     edx, 299h; void *
0x1800174e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800174ee  nop
0x1800174ef  mov     rcx, [rsp+2E0h+var_278]
0x1800174f4  test    rcx, rcx
0x1800174f7  jz      short loc_18001750B
0x1800174f9  mov     [rsp+2E0h+var_278], r12
0x1800174fe  mov     rax, [rcx]
0x180017501  mov     rax, [rax+10h]
0x180017505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001750a  nop
0x18001750b  jmp     loc_18001748C
0x180017510  mov     r9b, sil
0x180017513  mov     r8, [rsp+2E0h+var_278]
0x180017518  xor     edx, edx
0x18001751a  mov     rcx, [rsp+2E0h+var_280]
0x18001751f  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180017524  nop
0x180017525  mov     rcx, [rsp+2E0h+var_278]
0x18001752a  test    rcx, rcx
0x18001752d  jz      short loc_180017541
0x18001752f  mov     [rsp+2E0h+var_278], r12
0x180017534  mov     rax, [rcx]
0x180017537  mov     rax, [rax+10h]
0x18001753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017540  nop
0x180017541  mov     rcx, rbx; string
0x180017544  call    cs:__imp_WindowsDeleteString
0x18001754a  lea     r15, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180017551  lea     r14, aSystemsettings_71; "SystemSettings::PointInTimeRestore::CPo"...
0x180017558  mov     r8, r13
0x18001755b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180017562  mov     rcx, [rsp+2E0h+var_280]
0x180017567  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x18001756c  mov     ebx, eax
0x18001756e  test    eax, eax
0x180017570  jns     loc_1800176F8
0x180017576  lea     rax, aFailedToCopyPo; "Failed to copy possible values collecti"...
0x18001757d  mov     edx, 2A8h
0x180017582  jmp     loc_180017289
0x180017587  mov     rcx, [rbp+1E8h]; this
0x18001758e  lea     rax, aFailedToCreate_10; "Failed to create property value for sna"...
0x180017595  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x18001759a  mov     r9d, edi; char *
0x18001759d  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800175a4  mov     edx, 27Fh; void *
0x1800175a9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800175ae  nop
0x1800175af  mov     rcx, [rsp+2E0h+var_278]
0x1800175b4  test    rcx, rcx
0x1800175b7  jz      short loc_1800175CF
0x1800175b9  mov     [rsp+2E0h+var_278], 0
0x1800175c2  mov     rax, [rcx]
0x1800175c5  mov     rax, [rax+10h]
0x1800175c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ce  nop
0x1800175cf  jmp     short loc_1800175F9
0x1800175d1  mov     rcx, [rbp+1E8h]; this
0x1800175d8  lea     rax, aFailedToFormat_6; "Failed to format snapshot cadence hourl"...
0x1800175df  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800175e4  mov     r9d, edi; char *
0x1800175e7  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800175ee  mov     edx, 27Bh; void *
0x1800175f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800175f8  nop
0x1800175f9  mov     rcx, rbx; string
0x1800175fc  call    cs:__imp_WindowsDeleteString
0x180017602  nop
0x180017603  mov     rcx, [rsp+2E0h+var_280]
0x180017608  test    rcx, rcx
0x18001760b  jz      short loc_18001761B
0x18001760d  mov     [rsp+2E0h+var_280], 0
0x180017616  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x18001761b  mov     eax, edi
0x18001761d  jmp     loc_18001776B
0x180017622  mov     rcx, [rbp+1E8h]; this
0x180017629  lea     rax, aFailedToGetRes_3; "Failed to get resource string for snaps"...
0x180017630  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017635  mov     r9d, ebx; char *
0x180017638  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x18001763f  mov     edx, 277h; void *
0x180017644  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017649  nop
0x18001764a  mov     rcx, [rsp+2E0h+string]; string
0x18001764f  call    cs:__imp_WindowsDeleteString
0x180017655  jmp     loc_1800172A5
0x18001765a  mov     [rsp+2E0h+var_278], r12
0x18001765f  lea     rdx, [rsp+2E0h+var_278]; unsigned __int16 *
0x180017664  lea     rcx, aSystemsettings_29; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001766b  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x180017670  mov     ebx, eax
0x180017672  test    eax, eax
0x180017674  jns     short loc_1800176BF
0x180017676  mov     rcx, [rbp+1E8h]; this
0x18001767d  lea     rax, aFailedToGetRes_7; "Failed to get resource string for snaps"...
0x180017684  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017689  mov     r9d, ebx; char *
0x18001768c  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017693  mov     edx, 2A3h; void *
0x180017698  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001769d  nop
  ... truncated ...
```

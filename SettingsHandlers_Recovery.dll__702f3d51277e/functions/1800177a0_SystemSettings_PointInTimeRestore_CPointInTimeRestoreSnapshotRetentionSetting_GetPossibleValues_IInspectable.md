# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues(IInspectable * *)

- ea: `0x1800177a0`
- end: `0x180017ca6`
- name: `?GetPossibleValues@CPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1286`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002350`
- `0x180002380`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x180010b20`
- `0x180013c78`
- `0x1800177a0`
- `0x18001868c`
- `0x18001b7e0`
- `0x18001cf10`
- `0x18001de10`
- `0x180025920`
- `0x180025f88`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800178ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800178ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001798b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001798b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800179a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017af2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c66`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017837`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017b87`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017837`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017b87`
- `WDSCORE!CurrentIP` at `0x1800177d8`
- `WDSCORE!CurrentIP` at `0x180017b2b`
- `WDSCORE!CurrentIP` at `0x1800177d8`
- `WDSCORE!CurrentIP` at `0x180017b2b`

## string_xrefs

- `0x180017b12`: `Failed to copy possible values collection to return parameter`
- `0x180017bb0`: `Failed to create property value for snapshot retention hourly value`
- `0x180017a7c`: `Failed to create property value for snapshot retention custom value`
- `0x18001787d`: `Failed to create possible values collection for snapshot retention setting`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *this,
        struct IInspectable **a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  void *v6; // rax
  __int64 v7; // rax
  int ResourceStringById; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  char v11; // r14
  signed int i; // esi
  HSTRING *v13; // r8
  unsigned int v14; // edi
  HSTRING v15; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // edi
  __int64 v18; // r9
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  struct IInspectable *v20; // rcx
  HSTRING *v21; // r8
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v22; // rax
  unsigned int SnapshotRetentionSelectedValue; // edi
  const unsigned __int16 *v24; // rax
  struct IInspectable *v25; // rcx
  struct IInspectable *v26; // rcx
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  struct IInspectable *v31; // rcx
  char *v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  struct IInspectable *v34; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues: Getting PIT"
         "R snapshot retention possible values");
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    894,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues",
    v4,
    LastError,
    0,
    0);
  *a2 = 0;
  v33 = 0;
  v6 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6
    && (v7 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v6)) != 0 )
  {
    ResourceStringById = 0;
    v33 = v7;
  }
  else
  {
    ResourceStringById = -2147024882;
  }
  if ( ResourceStringById >= 0 )
  {
    v11 = 0;
    for ( i = 0; (unsigned int)i < 6; ++i )
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_HourlyValue",
                             string,
                             v13);
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x38C,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)"Failed to get resource string for snapshot retention hourly value",
          v32);
        goto LABEL_42;
      }
      v14 = *((_DWORD *)qword_18003AAD0 + i);
      v15 = string[0];
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v17 = StringCchPrintfW(v36, 0x104u, StringRawBuffer, v14);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x390,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to format snapshot retention hourly value string",
          v32);
        goto LABEL_38;
      }
      v34 = 0;
      v17 = SystemSettings::DataModel::PropValueHelper::CreateString(v36, &v34);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x394,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to create property value for snapshot retention hourly value",
          v32);
        v31 = v34;
        if ( v34 )
        {
          v34 = 0;
          ((void (__fastcall *)(struct IInspectable *))v31->lpVtbl->Release)(v31);
        }
        goto LABEL_38;
      }
      LOBYTE(v18) = 1;
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v33,
        0,
        v34,
        v18);
      Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
      if ( SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(Current) == 60 * *((_DWORD *)qword_18003AAD0 + i) )
        v11 = 1;
      v20 = v34;
      if ( v34 )
      {
        v34 = 0;
        ((void (__fastcall *)(struct IInspectable *))v20->lpVtbl->Release)(v20);
      }
      WindowsDeleteString(v15);
    }
    if ( !v11 )
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_CustomValue",
                             string,
                             v21);
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3A6,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)"Failed to get resource string for snapshot retention custom value",
          v32);
LABEL_42:
        WindowsDeleteString(string[0]);
        goto LABEL_43;
      }
      v22 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
      SnapshotRetentionSelectedValue = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(v22);
      v15 = string[0];
      v24 = WindowsGetStringRawBuffer(string[0], 0);
      v17 = StringCchPrintfW(v36, 0x104u, v24, SnapshotRetentionSelectedValue);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3AA,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to format snapshot retention custom value string",
          v32);
LABEL_38:
        WindowsDeleteString(v15);
        if ( v33 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
        return (unsigned int)v17;
      }
      v34 = 0;
      v17 = SystemSettings::DataModel::PropValueHelper::CreateString(v36, &v34);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3AE,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to create property value for snapshot retention custom value",
          v32);
        v25 = v34;
        if ( v34 )
        {
          v34 = 0;
          ((void (__fastcall *)(struct IInspectable *))v25->lpVtbl->Release)(v25);
        }
        goto LABEL_38;
      }
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v33,
        0,
        v34,
        1);
      v26 = v34;
      if ( v34 )
      {
        v34 = 0;
        ((void (__fastcall *)(struct IInspectable *))v26->lpVtbl->Release)(v26);
      }
      WindowsDeleteString(v15);
    }
    ResourceStringById = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::QueryInterface(
                           v33,
                           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                           a2);
    if ( ResourceStringById < 0 )
    {
      v9 = "Failed to copy possible values collection to return parameter";
      v10 = 949;
      goto LABEL_7;
    }
    v27 = GetLastError();
    v28 = CurrentIP();
    v29 = ConstructPartialMsgW(
            0x4000000u,
            "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues: Exiting...");
    WdsSetupLogMessageW(
      v29,
      0,
      L"D",
      0,
      951,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetPossibleValues",
      v28,
      v27,
      0,
      0);
    if ( v33 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
    return 0;
  }
  else
  {
    v9 = "Failed to create possible values collection for snapshot retention setting";
    v10 = 899;
LABEL_7:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v10,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)v9,
      v32);
LABEL_43:
    if ( v33 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
    return (unsigned int)ResourceStringById;
  }
}

```

## disassembly

```asm
0x1800177a0  push    rbp
0x1800177a2  push    rbx
0x1800177a3  push    rsi
0x1800177a4  push    rdi
0x1800177a5  push    r12
0x1800177a7  push    r13
0x1800177a9  push    r14
0x1800177ab  push    r15
0x1800177ad  lea     rbp, [rsp-1A8h]
0x1800177b5  sub     rsp, 2A8h
0x1800177bc  mov     rax, cs:__security_cookie
0x1800177c3  xor     rax, rsp
0x1800177c6  mov     [rbp+1E0h+var_50], rax
0x1800177cd  mov     r12, rdx
0x1800177d0  call    cs:__imp_GetLastError
0x1800177d6  mov     edi, eax
0x1800177d8  call    cs:__imp_CurrentIP
0x1800177de  mov     rbx, rax
0x1800177e1  lea     rdx, aSystemsettings_19; "SystemSettings::PointInTimeRestore::CPo"...
0x1800177e8  mov     ecx, 4000000h; unsigned int
0x1800177ed  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800177f2  xor     r13d, r13d
0x1800177f5  mov     [rsp+2E0h+var_290], r13d
0x1800177fa  mov     [rsp+2E0h+var_298], r13
0x1800177ff  mov     [rsp+2E0h+var_2A0], edi
0x180017803  mov     [rsp+2E0h+var_2A8], rbx
0x180017808  lea     rcx, aSystemsettings_86; "SystemSettings::PointInTimeRestore::CPo"...
0x18001780f  mov     [rsp+2E0h+var_2B0], rcx
0x180017814  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001781b  mov     [rsp+2E0h+var_2B8], rcx; char *
0x180017820  mov     [rsp+2E0h+var_2C0], 37Eh
0x180017828  xor     r9d, r9d
0x18001782b  lea     r8, aD; "D"
0x180017832  xor     edx, edx
0x180017834  mov     rcx, rax
0x180017837  call    cs:__imp_WdsSetupLogMessageW
0x18001783d  mov     [r12], r13
0x180017841  mov     [rsp+2E0h+var_280], r13
0x180017846  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001784d  mov     ecx, 0B8h; unsigned __int64
0x180017852  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017857  test    rax, rax
0x18001785a  jz      short loc_180017874
0x18001785c  mov     rcx, rax
0x18001785f  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x180017864  nop
0x180017865  test    rax, rax
0x180017868  jz      short loc_180017874
0x18001786a  mov     ebx, r13d
0x18001786d  mov     [rsp+2E0h+var_280], rax
0x180017872  jmp     short loc_180017879
0x180017874  mov     ebx, 8007000Eh
0x180017879  test    ebx, ebx
0x18001787b  jns     short loc_1800178A9
0x18001787d  lea     rax, aFailedToCreate_5; "Failed to create possible values collec"...
0x180017884  mov     edx, 383h; void *
0x180017889  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017890  mov     r9d, ebx; char *
0x180017893  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017898  mov     rcx, [rbp+1E8h]; this
0x18001789f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800178a4  jmp     loc_180017C6D
0x1800178a9  mov     r14b, r13b
0x1800178ac  mov     esi, r13d
0x1800178af  xor     ecx, ecx; string
0x1800178b1  call    cs:__imp_WindowsDeleteString
0x1800178b7  mov     [rsp+2E0h+string], r13
0x1800178bc  lea     rdx, [rsp+2E0h+string]; HSTRING *
0x1800178c1  lea     rcx, aSystemsettings_104; "SystemSettings_Misc_PointInTimeRestore_"...
0x1800178c8  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800178cd  mov     ebx, eax
0x1800178cf  test    eax, eax
0x1800178d1  js      loc_180017C39
0x1800178d7  movsxd  r15, esi
0x1800178da  lea     rax, qword_18003AAD0
0x1800178e1  mov     edi, [rax+r15*4]
0x1800178e5  xor     edx, edx; length
0x1800178e7  mov     rbx, [rsp+2E0h+string]
0x1800178ec  mov     rcx, rbx; string
0x1800178ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800178f5  mov     r9d, edi
0x1800178f8  mov     r8, rax; unsigned __int16 *
0x1800178fb  mov     edx, 104h; unsigned __int64
0x180017900  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017904  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017909  mov     edi, eax
0x18001790b  test    eax, eax
0x18001790d  js      loc_180017BEF
0x180017913  mov     [rsp+2E0h+var_278], r13
0x180017918  lea     rdx, [rsp+2E0h+var_278]; struct IInspectable **
0x18001791d  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017921  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180017926  mov     edi, eax
0x180017928  test    eax, eax
0x18001792a  js      loc_180017BA9
0x180017930  mov     edi, 1
0x180017935  mov     r9b, dil
0x180017938  mov     r8, [rsp+2E0h+var_278]
0x18001793d  xor     edx, edx
0x18001793f  mov     rcx, [rsp+2E0h+var_280]
0x180017944  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180017949  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001794e  mov     rcx, rax; this
0x180017951  call    ?GetSnapshotRetentionSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(void)
0x180017956  lea     rcx, qword_18003AAD0
0x18001795d  imul    ecx, [rcx+r15*4], 3Ch ; '<'
0x180017962  movzx   r14d, r14b
0x180017966  cmp     eax, ecx
0x180017968  cmovz   r14d, edi
0x18001796c  mov     rcx, [rsp+2E0h+var_278]
0x180017971  test    rcx, rcx
0x180017974  jz      short loc_180017988
0x180017976  mov     [rsp+2E0h+var_278], r13
0x18001797b  mov     rax, [rcx]
0x18001797e  mov     rax, [rax+10h]
0x180017982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017987  nop
0x180017988  mov     rcx, rbx; string
0x18001798b  call    cs:__imp_WindowsDeleteString
0x180017991  add     esi, edi
0x180017993  cmp     esi, 6
0x180017996  jb      loc_1800178AF
0x18001799c  test    r14b, r14b
0x18001799f  jnz     loc_180017AF8
0x1800179a5  xor     ecx, ecx; string
0x1800179a7  call    cs:__imp_WindowsDeleteString
0x1800179ad  mov     [rsp+2E0h+string], r13
0x1800179b2  lea     rdx, [rsp+2E0h+string]; HSTRING *
0x1800179b7  lea     rcx, aSystemsettings_125; "SystemSettings_Misc_PointInTimeRestore_"...
0x1800179be  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800179c3  mov     ebx, eax
0x1800179c5  test    eax, eax
0x1800179c7  jns     short loc_1800179F6
0x1800179c9  mov     rcx, [rbp+1E8h]; this
0x1800179d0  lea     rax, aFailedToGetRes_2; "Failed to get resource string for snaps"...
0x1800179d7  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x1800179dc  mov     r9d, ebx; char *
0x1800179df  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800179e6  mov     edx, 3A6h; void *
0x1800179eb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800179f0  nop
0x1800179f1  jmp     loc_180017C61
0x1800179f6  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x1800179fb  mov     rcx, rax; this
0x1800179fe  call    ?GetSnapshotRetentionSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(void)
0x180017a03  mov     edi, eax
0x180017a05  xor     edx, edx; length
0x180017a07  mov     rbx, [rsp+2E0h+string]
0x180017a0c  mov     rcx, rbx; string
0x180017a0f  call    cs:__imp_WindowsGetStringRawBuffer
0x180017a15  mov     r9d, edi
0x180017a18  mov     r8, rax; unsigned __int16 *
0x180017a1b  mov     edx, 104h; unsigned __int64
0x180017a20  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017a24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017a29  mov     edi, eax
0x180017a2b  test    eax, eax
0x180017a2d  jns     short loc_180017A5C
0x180017a2f  mov     rcx, [rbp+1E8h]; this
0x180017a36  lea     rax, aFailedToFormat; "Failed to format snapshot retention cus"...
0x180017a3d  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017a42  mov     r9d, edi; char *
0x180017a45  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017a4c  mov     edx, 3AAh; void *
0x180017a51  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017a56  nop
0x180017a57  jmp     loc_180017C17
0x180017a5c  mov     [rsp+2E0h+var_278], r13
0x180017a61  lea     rdx, [rsp+2E0h+var_278]; struct IInspectable **
0x180017a66  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x180017a6a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180017a6f  mov     edi, eax
0x180017a71  test    eax, eax
0x180017a73  jns     short loc_180017ABB
0x180017a75  mov     rcx, [rbp+1E8h]; this
0x180017a7c  lea     rax, aFailedToCreate_8; "Failed to create property value for sna"...
0x180017a83  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017a88  mov     r9d, edi; char *
0x180017a8b  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017a92  mov     edx, 3AEh; void *
0x180017a97  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017a9c  nop
0x180017a9d  mov     rcx, [rsp+2E0h+var_278]
0x180017aa2  test    rcx, rcx
0x180017aa5  jz      short loc_180017AB9
0x180017aa7  mov     [rsp+2E0h+var_278], r13
0x180017aac  mov     rax, [rcx]
0x180017aaf  mov     rax, [rax+10h]
0x180017ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab8  nop
0x180017ab9  jmp     short loc_180017A57
0x180017abb  mov     r9d, 1
0x180017ac1  mov     r8, [rsp+2E0h+var_278]
0x180017ac6  xor     edx, edx
0x180017ac8  mov     rcx, [rsp+2E0h+var_280]
0x180017acd  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180017ad2  nop
0x180017ad3  mov     rcx, [rsp+2E0h+var_278]
0x180017ad8  test    rcx, rcx
0x180017adb  jz      short loc_180017AEF
0x180017add  mov     [rsp+2E0h+var_278], r13
0x180017ae2  mov     rax, [rcx]
0x180017ae5  mov     rax, [rax+10h]
0x180017ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aee  nop
0x180017aef  mov     rcx, rbx; string
0x180017af2  call    cs:__imp_WindowsDeleteString
0x180017af8  mov     r8, r12
0x180017afb  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180017b02  mov     rcx, [rsp+2E0h+var_280]
0x180017b07  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x180017b0c  mov     ebx, eax
0x180017b0e  test    eax, eax
0x180017b10  jns     short loc_180017B23
0x180017b12  lea     rax, aFailedToCopyPo; "Failed to copy possible values collecti"...
0x180017b19  mov     edx, 3B5h
0x180017b1e  jmp     loc_180017889
0x180017b23  call    cs:__imp_GetLastError
0x180017b29  mov     edi, eax
0x180017b2b  call    cs:__imp_CurrentIP
0x180017b31  mov     rbx, rax
0x180017b34  lea     rdx, aSystemsettings_98; "SystemSettings::PointInTimeRestore::CPo"...
0x180017b3b  mov     ecx, 4000000h; unsigned int
0x180017b40  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017b45  mov     [rsp+2E0h+var_290], r13d
0x180017b4a  mov     [rsp+2E0h+var_298], r13
0x180017b4f  mov     [rsp+2E0h+var_2A0], edi
0x180017b53  mov     [rsp+2E0h+var_2A8], rbx
0x180017b58  lea     rcx, aSystemsettings_86; "SystemSettings::PointInTimeRestore::CPo"...
0x180017b5f  mov     [rsp+2E0h+var_2B0], rcx
0x180017b64  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180017b6b  mov     [rsp+2E0h+var_2B8], rcx
0x180017b70  mov     [rsp+2E0h+var_2C0], 3B7h
0x180017b78  xor     r9d, r9d
0x180017b7b  lea     r8, aD; "D"
0x180017b82  xor     edx, edx
0x180017b84  mov     rcx, rax
0x180017b87  call    cs:__imp_WdsSetupLogMessageW
0x180017b8d  nop
0x180017b8e  mov     rcx, [rsp+2E0h+var_280]
0x180017b93  test    rcx, rcx
0x180017b96  jz      short loc_180017BA2
0x180017b98  mov     [rsp+2E0h+var_280], r13
0x180017b9d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x180017ba2  xor     eax, eax
0x180017ba4  jmp     loc_180017C83
0x180017ba9  mov     rcx, [rbp+1E8h]; this
0x180017bb0  lea     rax, aFailedToCreate_15; "Failed to create property value for sna"...
0x180017bb7  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017bbc  mov     r9d, edi; char *
0x180017bbf  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017bc6  mov     edx, 394h; void *
0x180017bcb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017bd0  nop
0x180017bd1  mov     rcx, [rsp+2E0h+var_278]
0x180017bd6  test    rcx, rcx
0x180017bd9  jz      short loc_180017BED
0x180017bdb  mov     [rsp+2E0h+var_278], r13
0x180017be0  mov     rax, [rcx]
0x180017be3  mov     rax, [rax+10h]
0x180017be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bec  nop
0x180017bed  jmp     short loc_180017C17
0x180017bef  mov     rcx, [rbp+1E8h]; this
0x180017bf6  lea     rax, aFailedToFormat_7; "Failed to format snapshot retention hou"...
0x180017bfd  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017c02  mov     r9d, edi; char *
0x180017c05  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017c0c  mov     edx, 390h; void *
0x180017c11  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017c16  nop
0x180017c17  mov     rcx, rbx; string
0x180017c1a  call    cs:__imp_WindowsDeleteString
0x180017c20  nop
0x180017c21  mov     rcx, [rsp+2E0h+var_280]
0x180017c26  test    rcx, rcx
0x180017c29  jz      short loc_180017C35
0x180017c2b  mov     [rsp+2E0h+var_280], r13
0x180017c30  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x180017c35  mov     eax, edi
0x180017c37  jmp     short loc_180017C83
0x180017c39  mov     rcx, [rbp+1E8h]; this
0x180017c40  lea     rax, aFailedToGetRes_5; "Failed to get resource string for snaps"...
0x180017c47  mov     qword ptr [rsp+2E0h+var_2C0], rax; int
0x180017c4c  mov     r9d, ebx; char *
0x180017c4f  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180017c56  mov     edx, 38Ch; void *
0x180017c5b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017c60  nop
0x180017c61  mov     rcx, [rsp+2E0h+string]; string
0x180017c66  call    cs:__imp_WindowsDeleteString
0x180017c6c  nop
0x180017c6d  mov     rcx, [rsp+2E0h+var_280]
0x180017c72  test    rcx, rcx
0x180017c75  jz      short loc_180017C81
0x180017c77  mov     [rsp+2E0h+var_280], r13
0x180017c7c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x180017c81  mov     eax, ebx
0x180017c83  mov     rcx, [rbp+1E0h+var_50]
0x180017c8a  xor     rcx, rsp; StackCookie
  ... truncated ...
```

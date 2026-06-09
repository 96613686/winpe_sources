# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue(IInspectable * *)

- ea: `0x180019c60`
- end: `0x180019f9f`
- name: `?GetValue@CPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `831`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002350`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x180013c78`
- `0x18001868c`
- `0x18001879c`
- `0x180019c60`
- `0x180025920`
- `0x180025ebc`
- `0x180025f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019f45`
- `WDSCORE!WdsSetupLogMessageW` at `0x180019cf0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180019e6b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180019cf0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180019e6b`
- `WDSCORE!CurrentIP` at `0x180019c8d`
- `WDSCORE!CurrentIP` at `0x180019e0f`
- `WDSCORE!CurrentIP` at `0x180019c8d`
- `WDSCORE!CurrentIP` at `0x180019e0f`

## string_xrefs

- `0x180019f19`: `Failed to create property value for snapshot cadence hourly value`
- `0x180019dd0`: `Failed to create property value for snapshot cadence custom value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *this,
        struct IInspectable **a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  struct IInspectable **v7; // r8
  int v8; // ebx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v9; // rax
  __int64 v10; // rbp
  HSTRING *v11; // r8
  int ResourceStringById; // edi
  HSTRING v13; // rbx
  const char *v14; // rax
  __int64 v15; // rdx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v16; // rax
  unsigned int SnapshotCadenceSelectedValue; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  HSTRING *v23; // r8
  unsigned int v24; // edi
  const unsigned __int16 *v25; // rax
  int ResourceStringValue; // ebx
  char *v27; // [rsp+28h] [rbp-2A0h]
  HSTRING string[2]; // [rsp+60h] [rbp-268h] BYREF
  unsigned __int16 v29[264]; // [rsp+70h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue: Getting PITR snapshot "
         "cadence setting value");
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    557,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue",
    v4,
    LastError,
    0,
    0);
  *a2 = 0;
  Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  if ( (unsigned int)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITROn(Current) )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
      v10 = v8;
      if ( 60 * *((_DWORD *)qword_18003AAF0 + v8) == SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(v9) )
        break;
      if ( (unsigned int)++v8 >= 5 )
      {
        WindowsDeleteString(0);
        string[0] = 0;
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                               (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_CustomValue",
                               string,
                               v11);
        v13 = string[0];
        if ( ResourceStringById < 0 )
        {
          v14 = "Failed to get resource string for snapshot cadence custom value";
          v15 = 591;
          goto LABEL_19;
        }
        v16 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
        SnapshotCadenceSelectedValue = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(v16);
        StringRawBuffer = WindowsGetStringRawBuffer(v13, 0);
        ResourceStringById = StringCchPrintfW(v29, 0x104u, StringRawBuffer, SnapshotCadenceSelectedValue);
        if ( ResourceStringById < 0 )
        {
          v14 = "Failed to format snapshot cadence custom value string";
          v15 = 595;
          goto LABEL_19;
        }
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v29, a2);
        if ( ResourceStringById < 0 )
        {
          v14 = "Failed to create property value for snapshot cadence custom value";
          v15 = 598;
          goto LABEL_19;
        }
LABEL_11:
        WindowsDeleteString(v13);
        goto LABEL_12;
      }
    }
    WindowsDeleteString(0);
    string[0] = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_HourlyValue",
                           string,
                           v23);
    v13 = string[0];
    if ( ResourceStringById >= 0 )
    {
      v24 = *((_DWORD *)qword_18003AAF0 + v10);
      v25 = WindowsGetStringRawBuffer(string[0], 0);
      ResourceStringById = StringCchPrintfW(v29, 0x104u, v25, v24);
      if ( ResourceStringById >= 0 )
      {
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v29, a2);
        if ( ResourceStringById >= 0 )
          goto LABEL_11;
        v14 = "Failed to create property value for snapshot cadence hourly value";
        v15 = 581;
      }
      else
      {
        v14 = "Failed to format snapshot cadence hourly value string";
        v15 = 578;
      }
    }
    else
    {
      v14 = "Failed to get resource string for snapshot cadence hourly value";
      v15 = 574;
    }
LABEL_19:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v15,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)v14,
      v27);
    WindowsDeleteString(v13);
    return (unsigned int)ResourceStringById;
  }
  else
  {
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_DisabledValue",
                            (const unsigned __int16 *)a2,
                            v7);
    if ( ResourceStringValue >= 0 )
    {
LABEL_12:
      v19 = GetLastError();
      v20 = CurrentIP();
      v21 = ConstructPartialMsgW(
              0x4000000u,
              "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue: Exiting...");
      WdsSetupLogMessageW(
        v21,
        0,
        L"D",
        0,
        607,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::GetValue",
        v20,
        v19,
        0,
        0);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x25C,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)ResourceStringValue,
        (int)"Failed to get resource string for snapshot cadence disabled value",
        v27);
      return (unsigned int)ResourceStringValue;
    }
  }
}

```

## disassembly

```asm
0x180019c60  push    rbx
0x180019c62  push    rbp
0x180019c63  push    rsi
0x180019c64  push    rdi
0x180019c65  push    r13
0x180019c67  push    r15
0x180019c69  sub     rsp, 298h
0x180019c70  mov     rax, cs:__security_cookie
0x180019c77  xor     rax, rsp
0x180019c7a  mov     [rsp+2C8h+var_48], rax
0x180019c82  mov     rsi, rdx
0x180019c85  call    cs:__imp_GetLastError
0x180019c8b  mov     edi, eax
0x180019c8d  call    cs:__imp_CurrentIP
0x180019c93  mov     rbx, rax
0x180019c96  lea     rdx, aSystemsettings_119; "SystemSettings::PointInTimeRestore::CPo"...
0x180019c9d  mov     ecx, 4000000h; unsigned int
0x180019ca2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180019ca7  mov     [rsp+2C8h+var_278], 0
0x180019caf  mov     [rsp+2C8h+var_280], 0
0x180019cb8  mov     [rsp+2C8h+var_288], edi
0x180019cbc  mov     [rsp+2C8h+var_290], rbx
0x180019cc1  lea     r13, aSystemsettings_9; "SystemSettings::PointInTimeRestore::CPo"...
0x180019cc8  mov     [rsp+2C8h+var_298], r13
0x180019ccd  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180019cd4  mov     [rsp+2C8h+var_2A0], rcx; char *
0x180019cd9  mov     [rsp+2C8h+var_2A8], 22Dh
0x180019ce1  xor     r9d, r9d
0x180019ce4  lea     r8, aD; "D"
0x180019ceb  xor     edx, edx
0x180019ced  mov     rcx, rax
0x180019cf0  call    cs:__imp_WdsSetupLogMessageW
0x180019cf6  mov     qword ptr [rsi], 0
0x180019cfd  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180019d02  mov     rcx, rax; this
0x180019d05  call    ?GetPITROn@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAHXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITROn(void)
0x180019d0a  test    eax, eax
0x180019d0c  jz      loc_180019F57
0x180019d12  xor     ebx, ebx
0x180019d14  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180019d19  mov     rcx, rax; this
0x180019d1c  call    ?GetSnapshotCadenceSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(void)
0x180019d21  movsxd  rbp, ebx
0x180019d24  lea     r15, qword_18003AAF0
0x180019d2b  imul    ecx, [r15+rbp*4], 3Ch ; '<'
0x180019d30  cmp     ecx, eax
0x180019d32  jz      loc_180019E93
0x180019d38  inc     ebx
0x180019d3a  cmp     ebx, 5
0x180019d3d  jb      short loc_180019D14
0x180019d3f  xor     ecx, ecx; string
0x180019d41  call    cs:__imp_WindowsDeleteString
0x180019d47  mov     [rsp+2C8h+string], 0
0x180019d50  lea     rdx, [rsp+2C8h+string]; HSTRING *
0x180019d55  lea     rcx, aSystemsettings_60; "SystemSettings_Misc_PointInTimeRestore_"...
0x180019d5c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180019d61  mov     edi, eax
0x180019d63  mov     rbx, [rsp+2C8h+string]
0x180019d68  test    eax, eax
0x180019d6a  jns     short loc_180019D7A
0x180019d6c  lea     rax, aFailedToGetRes_4; "Failed to get resource string for snaps"...
0x180019d73  mov     edx, 24Fh
0x180019d78  jmp     short loc_180019DDC
0x180019d7a  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180019d7f  mov     rcx, rax; this
0x180019d82  call    ?GetSnapshotCadenceSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotCadenceSelectedValue(void)
0x180019d87  mov     edi, eax
0x180019d89  xor     edx, edx; length
0x180019d8b  mov     rcx, rbx; string
0x180019d8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180019d94  mov     r9d, edi
0x180019d97  mov     r8, rax; unsigned __int16 *
0x180019d9a  mov     edx, 104h; unsigned __int64
0x180019d9f  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019da4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019da9  mov     edi, eax
0x180019dab  test    eax, eax
0x180019dad  jns     short loc_180019DBD
0x180019daf  lea     rax, aFailedToFormat_9; "Failed to format snapshot cadence custo"...
0x180019db6  mov     edx, 253h
0x180019dbb  jmp     short loc_180019DDC
0x180019dbd  mov     rdx, rsi; struct IInspectable **
0x180019dc0  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019dc5  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180019dca  mov     edi, eax
0x180019dcc  test    eax, eax
0x180019dce  jns     short loc_180019DFE
0x180019dd0  lea     rax, aFailedToCreate_17; "Failed to create property value for sna"...
0x180019dd7  mov     edx, 256h; void *
0x180019ddc  mov     qword ptr [rsp+2C8h+var_2A8], rax; int
0x180019de1  mov     r9d, edi; char *
0x180019de4  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180019deb  mov     rcx, [rsp+2C8h]; this
0x180019df3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019df8  nop
0x180019df9  jmp     loc_180019F42
0x180019dfe  mov     rcx, rbx; string
0x180019e01  call    cs:__imp_WindowsDeleteString
0x180019e07  call    cs:__imp_GetLastError
0x180019e0d  mov     edi, eax
0x180019e0f  call    cs:__imp_CurrentIP
0x180019e15  mov     rbx, rax
0x180019e18  lea     rdx, aSystemsettings_21; "SystemSettings::PointInTimeRestore::CPo"...
0x180019e1f  mov     ecx, 4000000h; unsigned int
0x180019e24  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180019e29  mov     [rsp+2C8h+var_278], 0
0x180019e31  mov     [rsp+2C8h+var_280], 0
0x180019e3a  mov     [rsp+2C8h+var_288], edi
0x180019e3e  mov     [rsp+2C8h+var_290], rbx
0x180019e43  mov     [rsp+2C8h+var_298], r13
0x180019e48  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180019e4f  mov     [rsp+2C8h+var_2A0], rcx
0x180019e54  mov     [rsp+2C8h+var_2A8], 25Fh
0x180019e5c  xor     r9d, r9d
0x180019e5f  lea     r8, aD; "D"
0x180019e66  xor     edx, edx
0x180019e68  mov     rcx, rax
0x180019e6b  call    cs:__imp_WdsSetupLogMessageW
0x180019e71  xor     eax, eax
0x180019e73  mov     rcx, [rsp+2C8h+var_48]
0x180019e7b  xor     rcx, rsp; StackCookie
0x180019e7e  call    __security_check_cookie
0x180019e83  add     rsp, 298h
0x180019e8a  pop     r15
0x180019e8c  pop     r13
0x180019e8e  pop     rdi
0x180019e8f  pop     rsi
0x180019e90  pop     rbp
0x180019e91  pop     rbx
0x180019e92  retn
0x180019e93  xor     ecx, ecx; string
0x180019e95  call    cs:__imp_WindowsDeleteString
0x180019e9b  mov     [rsp+2C8h+string], 0
0x180019ea4  lea     rdx, [rsp+2C8h+string]; HSTRING *
0x180019ea9  lea     rcx, aSystemsettings_89; "SystemSettings_Misc_PointInTimeRestore_"...
0x180019eb0  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180019eb5  mov     edi, eax
0x180019eb7  mov     rbx, [rsp+2C8h+string]
0x180019ebc  test    eax, eax
0x180019ebe  jns     short loc_180019ECE
0x180019ec0  lea     rax, aFailedToGetRes_3; "Failed to get resource string for snaps"...
0x180019ec7  mov     edx, 23Eh
0x180019ecc  jmp     short loc_180019F25
0x180019ece  mov     edi, [r15+rbp*4]
0x180019ed2  xor     edx, edx; length
0x180019ed4  mov     rcx, rbx; string
0x180019ed7  call    cs:__imp_WindowsGetStringRawBuffer
0x180019edd  mov     r9d, edi
0x180019ee0  mov     r8, rax; unsigned __int16 *
0x180019ee3  mov     edx, 104h; unsigned __int64
0x180019ee8  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019eed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019ef2  mov     edi, eax
0x180019ef4  test    eax, eax
0x180019ef6  jns     short loc_180019F06
0x180019ef8  lea     rax, aFailedToFormat_6; "Failed to format snapshot cadence hourl"...
0x180019eff  mov     edx, 242h
0x180019f04  jmp     short loc_180019F25
0x180019f06  mov     rdx, rsi; struct IInspectable **
0x180019f09  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180019f0e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180019f13  mov     edi, eax
0x180019f15  test    eax, eax
0x180019f17  jns     short loc_180019F52
0x180019f19  lea     rax, aFailedToCreate_10; "Failed to create property value for sna"...
0x180019f20  mov     edx, 245h; void *
0x180019f25  mov     qword ptr [rsp+2C8h+var_2A8], rax; int
0x180019f2a  mov     r9d, edi; char *
0x180019f2d  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180019f34  mov     rcx, [rsp+2C8h]; this
0x180019f3c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019f41  nop
0x180019f42  mov     rcx, rbx; string
0x180019f45  call    cs:__imp_WindowsDeleteString
0x180019f4b  mov     eax, edi
0x180019f4d  jmp     loc_180019E73
0x180019f52  jmp     loc_180019DFE
0x180019f57  mov     rdx, rsi; unsigned __int16 *
0x180019f5a  lea     rcx, aSystemsettings_29; "SystemSettings_Misc_PointInTimeRestore_"...
0x180019f61  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x180019f66  mov     ebx, eax
0x180019f68  test    eax, eax
0x180019f6a  jns     loc_180019E07
0x180019f70  mov     rcx, [rsp+2C8h]; this
0x180019f78  lea     rax, aFailedToGetRes_7; "Failed to get resource string for snaps"...
0x180019f7f  mov     qword ptr [rsp+2C8h+var_2A8], rax; int
0x180019f84  mov     r9d, ebx; char *
0x180019f87  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180019f8e  mov     edx, 25Ch; void *
0x180019f93  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019f98  mov     eax, ebx
0x180019f9a  jmp     loc_180019E73
```

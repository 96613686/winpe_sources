# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue(IInspectable * *)

- ea: `0x180019fb0`
- end: `0x18001a291`
- name: `?GetValue@CPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `737`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002350`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x180013c78`
- `0x18001868c`
- `0x180019fb0`
- `0x180025920`
- `0x180025f88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a141`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a1fe`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a041`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a268`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a041`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a268`
- `WDSCORE!CurrentIP` at `0x180019fde`
- `WDSCORE!CurrentIP` at `0x18001a20c`
- `WDSCORE!CurrentIP` at `0x180019fde`
- `WDSCORE!CurrentIP` at `0x18001a20c`

## string_xrefs

- `0x18001a1c5`: `Failed to create property value for snapshot retention hourly value`
- `0x18001a10c`: `Failed to create property value for snapshot retention custom value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *this,
        struct IInspectable **a2)
{
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  signed int i; // ebx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  __int64 v8; // rsi
  HSTRING *v9; // r8
  int ResourceStringById; // edi
  HSTRING v11; // rbx
  const char *v12; // rax
  __int64 v13; // rdx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v14; // rax
  unsigned int SnapshotRetentionSelectedValue; // edi
  const unsigned __int16 *v16; // rax
  HSTRING *v17; // r8
  unsigned int v18; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  char *v24; // [rsp+28h] [rbp-2A0h]
  HSTRING string[2]; // [rsp+60h] [rbp-268h] BYREF
  unsigned __int16 v26[264]; // [rsp+70h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue: Getting PITR snapsho"
         "t retention setting value");
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    846,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue",
    v4,
    LastError,
    0,
    0);
  *a2 = 0;
  for ( i = 0; (unsigned int)i < 6; ++i )
  {
    Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
    v8 = i;
    if ( 60 * *((_DWORD *)qword_18003AAD0 + i) == SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(Current) )
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_HourlyValue",
                             string,
                             v17);
      v11 = string[0];
      if ( ResourceStringById < 0 )
      {
        v12 = "Failed to get resource string for snapshot retention hourly value";
        v13 = 860;
        goto LABEL_17;
      }
      v18 = *((_DWORD *)qword_18003AAD0 + v8);
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      ResourceStringById = StringCchPrintfW(v26, 0x104u, StringRawBuffer, v18);
      if ( ResourceStringById < 0 )
      {
        v12 = "Failed to format snapshot retention hourly value string";
        v13 = 864;
        goto LABEL_17;
      }
      ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v26, a2);
      if ( ResourceStringById < 0 )
      {
        v12 = "Failed to create property value for snapshot retention hourly value";
        v13 = 867;
        goto LABEL_17;
      }
      goto LABEL_18;
    }
  }
  WindowsDeleteString(0);
  string[0] = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_CustomValue",
                         string,
                         v9);
  v11 = string[0];
  if ( ResourceStringById < 0 )
  {
    v12 = "Failed to get resource string for snapshot retention custom value";
    v13 = 876;
LABEL_17:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)v12,
      v24);
    WindowsDeleteString(v11);
    return (unsigned int)ResourceStringById;
  }
  v14 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SnapshotRetentionSelectedValue = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(v14);
  v16 = WindowsGetStringRawBuffer(v11, 0);
  ResourceStringById = StringCchPrintfW(v26, 0x104u, v16, SnapshotRetentionSelectedValue);
  if ( ResourceStringById < 0 )
  {
    v12 = "Failed to format snapshot retention custom value string";
    v13 = 880;
    goto LABEL_17;
  }
  ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v26, a2);
  if ( ResourceStringById < 0 )
  {
    v12 = "Failed to create property value for snapshot retention custom value";
    v13 = 883;
    goto LABEL_17;
  }
LABEL_18:
  WindowsDeleteString(v11);
  v21 = GetLastError();
  v22 = CurrentIP();
  v23 = ConstructPartialMsgW(
          0x4000000u,
          "SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue: Exiting...");
  WdsSetupLogMessageW(
    v23,
    0,
    L"D",
    0,
    886,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::GetValue",
    v22,
    v21,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x180019fb0  push    rbx
0x180019fb2  push    rsi
0x180019fb3  push    rdi
0x180019fb4  push    r13
0x180019fb6  push    r14
0x180019fb8  push    r15
0x180019fba  sub     rsp, 298h
0x180019fc1  mov     rax, cs:__security_cookie
0x180019fc8  xor     rax, rsp
0x180019fcb  mov     [rsp+2C8h+var_48], rax
0x180019fd3  mov     r14, rdx
0x180019fd6  call    cs:__imp_GetLastError
0x180019fdc  mov     edi, eax
0x180019fde  call    cs:__imp_CurrentIP
0x180019fe4  mov     rbx, rax
0x180019fe7  lea     rdx, aSystemsettings_126; "SystemSettings::PointInTimeRestore::CPo"...
0x180019fee  mov     ecx, 4000000h; unsigned int
0x180019ff3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180019ff8  mov     [rsp+2C8h+var_278], 0
0x18001a000  mov     [rsp+2C8h+var_280], 0
0x18001a009  mov     [rsp+2C8h+var_288], edi
0x18001a00d  mov     [rsp+2C8h+var_290], rbx
0x18001a012  lea     r13, aSystemsettings_59; "SystemSettings::PointInTimeRestore::CPo"...
0x18001a019  mov     [rsp+2C8h+var_298], r13
0x18001a01e  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001a025  mov     [rsp+2C8h+var_2A0], rcx; char *
0x18001a02a  mov     [rsp+2C8h+var_2A8], 34Eh
0x18001a032  xor     r9d, r9d
0x18001a035  lea     r8, aD; "D"
0x18001a03c  xor     edx, edx
0x18001a03e  mov     rcx, rax
0x18001a041  call    cs:__imp_WdsSetupLogMessageW
0x18001a047  mov     qword ptr [r14], 0
0x18001a04e  xor     ebx, ebx
0x18001a050  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001a055  mov     rcx, rax; this
0x18001a058  call    ?GetSnapshotRetentionSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(void)
0x18001a05d  movsxd  rsi, ebx
0x18001a060  lea     r15, qword_18003AAD0
0x18001a067  imul    ecx, [r15+rsi*4], 3Ch ; '<'
0x18001a06c  cmp     ecx, eax
0x18001a06e  jz      loc_18001A13F
0x18001a074  inc     ebx
0x18001a076  cmp     ebx, 6
0x18001a079  jb      short loc_18001A050
0x18001a07b  xor     ecx, ecx; string
0x18001a07d  call    cs:__imp_WindowsDeleteString
0x18001a083  mov     [rsp+2C8h+string], 0
0x18001a08c  lea     rdx, [rsp+2C8h+string]; HSTRING *
0x18001a091  lea     rcx, aSystemsettings_125; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001a098  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a09d  mov     edi, eax
0x18001a09f  mov     rbx, [rsp+2C8h+string]
0x18001a0a4  test    eax, eax
0x18001a0a6  jns     short loc_18001A0B6
0x18001a0a8  lea     rax, aFailedToGetRes_2; "Failed to get resource string for snaps"...
0x18001a0af  mov     edx, 36Ch
0x18001a0b4  jmp     short loc_18001A118
0x18001a0b6  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001a0bb  mov     rcx, rax; this
0x18001a0be  call    ?GetSnapshotRetentionSelectedValue@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEBAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotRetentionSelectedValue(void)
0x18001a0c3  mov     edi, eax
0x18001a0c5  xor     edx, edx; length
0x18001a0c7  mov     rcx, rbx; string
0x18001a0ca  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a0d0  mov     r9d, edi
0x18001a0d3  mov     r8, rax; unsigned __int16 *
0x18001a0d6  mov     edx, 104h; unsigned __int64
0x18001a0db  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001a0e0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a0e5  mov     edi, eax
0x18001a0e7  test    eax, eax
0x18001a0e9  jns     short loc_18001A0F9
0x18001a0eb  lea     rax, aFailedToFormat; "Failed to format snapshot retention cus"...
0x18001a0f2  mov     edx, 370h
0x18001a0f7  jmp     short loc_18001A118
0x18001a0f9  mov     rdx, r14; struct IInspectable **
0x18001a0fc  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001a101  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18001a106  mov     edi, eax
0x18001a108  test    eax, eax
0x18001a10a  jns     short loc_18001A13A
0x18001a10c  lea     rax, aFailedToCreate_8; "Failed to create property value for sna"...
0x18001a113  mov     edx, 373h; void *
0x18001a118  mov     qword ptr [rsp+2C8h+var_2A8], rax; int
0x18001a11d  mov     r9d, edi; char *
0x18001a120  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x18001a127  mov     rcx, [rsp+2C8h]; this
0x18001a12f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a134  nop
0x18001a135  jmp     loc_18001A1EE
0x18001a13a  jmp     loc_18001A1FB
0x18001a13f  xor     ecx, ecx; string
0x18001a141  call    cs:__imp_WindowsDeleteString
0x18001a147  mov     [rsp+2C8h+string], 0
0x18001a150  lea     rdx, [rsp+2C8h+string]; HSTRING *
0x18001a155  lea     rcx, aSystemsettings_104; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001a15c  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a161  mov     edi, eax
0x18001a163  mov     rbx, [rsp+2C8h+string]
0x18001a168  test    eax, eax
0x18001a16a  jns     short loc_18001A17A
0x18001a16c  lea     rax, aFailedToGetRes_5; "Failed to get resource string for snaps"...
0x18001a173  mov     edx, 35Ch
0x18001a178  jmp     short loc_18001A1D1
0x18001a17a  mov     edi, [r15+rsi*4]
0x18001a17e  xor     edx, edx; length
0x18001a180  mov     rcx, rbx; string
0x18001a183  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a189  mov     r9d, edi
0x18001a18c  mov     r8, rax; unsigned __int16 *
0x18001a18f  mov     edx, 104h; unsigned __int64
0x18001a194  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001a199  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a19e  mov     edi, eax
0x18001a1a0  test    eax, eax
0x18001a1a2  jns     short loc_18001A1B2
0x18001a1a4  lea     rax, aFailedToFormat_7; "Failed to format snapshot retention hou"...
0x18001a1ab  mov     edx, 360h
0x18001a1b0  jmp     short loc_18001A1D1
0x18001a1b2  mov     rdx, r14; struct IInspectable **
0x18001a1b5  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18001a1ba  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18001a1bf  mov     edi, eax
0x18001a1c1  test    eax, eax
0x18001a1c3  jns     short loc_18001A1FB
0x18001a1c5  lea     rax, aFailedToCreate_15; "Failed to create property value for sna"...
0x18001a1cc  mov     edx, 363h; void *
0x18001a1d1  mov     qword ptr [rsp+2C8h+var_2A8], rax; int
0x18001a1d6  mov     r9d, edi; char *
0x18001a1d9  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x18001a1e0  mov     rcx, [rsp+2C8h]; this
0x18001a1e8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a1ed  nop
0x18001a1ee  mov     rcx, rbx; string
0x18001a1f1  call    cs:__imp_WindowsDeleteString
0x18001a1f7  mov     eax, edi
0x18001a1f9  jmp     short loc_18001A270
0x18001a1fb  mov     rcx, rbx; string
0x18001a1fe  call    cs:__imp_WindowsDeleteString
0x18001a204  call    cs:__imp_GetLastError
0x18001a20a  mov     edi, eax
0x18001a20c  call    cs:__imp_CurrentIP
0x18001a212  mov     rbx, rax
0x18001a215  lea     rdx, aSystemsettings_122; "SystemSettings::PointInTimeRestore::CPo"...
0x18001a21c  mov     ecx, 4000000h; unsigned int
0x18001a221  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001a226  mov     [rsp+2C8h+var_278], 0
0x18001a22e  mov     [rsp+2C8h+var_280], 0
0x18001a237  mov     [rsp+2C8h+var_288], edi
0x18001a23b  mov     [rsp+2C8h+var_290], rbx
0x18001a240  mov     [rsp+2C8h+var_298], r13
0x18001a245  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001a24c  mov     [rsp+2C8h+var_2A0], rcx
0x18001a251  mov     [rsp+2C8h+var_2A8], 376h
0x18001a259  xor     r9d, r9d
0x18001a25c  lea     r8, aD; "D"
0x18001a263  xor     edx, edx
0x18001a265  mov     rcx, rax
0x18001a268  call    cs:__imp_WdsSetupLogMessageW
0x18001a26e  xor     eax, eax
0x18001a270  mov     rcx, [rsp+2C8h+var_48]
0x18001a278  xor     rcx, rsp; StackCookie
0x18001a27b  call    __security_check_cookie
0x18001a280  add     rsp, 298h
0x18001a287  pop     r15
0x18001a289  pop     r14
0x18001a28b  pop     r13
0x18001a28d  pop     rdi
0x18001a28e  pop     rsi
0x18001a28f  pop     rbx
0x18001a290  retn
```

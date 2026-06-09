# SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x180016bd0`
- end: `0x180016e90`
- name: `?GetNamedValue@CPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `704`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002350`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x180013c78`
- `0x180016bd0`
- `0x18001868c`
- `0x180025920`
- `0x180025f44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016d01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016d01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016d16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016c21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016c21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016d6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016df2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016de5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016df2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016c9b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016e5c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016c9b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180016e5c`
- `WDSCORE!CurrentIP` at `0x180016c46`
- `WDSCORE!CurrentIP` at `0x180016e07`
- `WDSCORE!CurrentIP` at `0x180016c46`
- `WDSCORE!CurrentIP` at `0x180016e07`

## string_xrefs

- `0x180016db9`: `Failed to create string for maximum disk usage text`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *this,
        HSTRING a2,
        struct IInspectable **a3)
{
  const WCHAR *StringRawBuffer; // rax
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  HSTRING *v8; // r8
  int ResourceStringById; // edi
  HSTRING v10; // rbx
  const char *v11; // rax
  __int64 v12; // rdx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax
  int SnapshotDiskUsageLimit; // ebp
  RTL_SRWLOCK *v15; // rdi
  RTL_SRWLOCK *v16; // rsi
  __int64 Ptr; // rdi
  float v18; // xmm6_4
  float v19; // xmm0_4
  const unsigned __int16 *v20; // rax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-2A8h]
  char *v26; // [rsp+28h] [rbp-2A0h]
  HSTRING string; // [rsp+60h] [rbp-268h] BYREF
  unsigned __int16 v28[264]; // [rsp+70h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"MaximumDiskUsageText", -1, 0) == 2 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(
           0x4000000u,
           "SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue: Getting MaximumDis"
           "kUsageText value");
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      1283,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue",
      v6,
      LastError,
      0,
      0);
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_MaximumDiskUsage_Label",
                           &string,
                           v8);
    v10 = string;
    if ( ResourceStringById < 0 )
    {
      v11 = "Failed to get resource string for maximum disk usage text value";
      v12 = 1287;
LABEL_15:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v12,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)v11,
        v26);
      WindowsDeleteString(v10);
      return (unsigned int)ResourceStringById;
    }
    Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
    SnapshotDiskUsageLimit = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotDiskUsageLimit(Current);
    v15 = (RTL_SRWLOCK *)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
    v16 = v15 + 33;
    AcquireSRWLockShared(v15 + 33);
    Ptr = (__int64)v15[41].Ptr;
    if ( v16 )
      ReleaseSRWLockShared(v16);
    v18 = 0.0;
    if ( Ptr )
    {
      if ( Ptr < 0 )
        v19 = (float)(Ptr & 1 | (unsigned int)((unsigned __int64)Ptr >> 1))
            + (float)(Ptr & 1 | (unsigned int)((unsigned __int64)Ptr >> 1));
      else
        v19 = (float)(int)Ptr;
      v18 = (float)((float)((float)((float)SnapshotDiskUsageLimit * 1024.0) * 1024.0) / v19) * 100.0;
    }
    v20 = WindowsGetStringRawBuffer(v10, 0);
    bIgnoreCase[0] = (unsigned int)SnapshotDiskUsageLimit >> 10;
    ResourceStringById = StringCchPrintfW(v28, 0x104u, v20, v18, *(_QWORD *)bIgnoreCase);
    if ( ResourceStringById < 0 )
    {
      v11 = "Failed to format maximum disk usage text";
      v12 = 1302;
      goto LABEL_15;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v28, a3);
    if ( ResourceStringById < 0 )
    {
      v11 = "Failed to create string for maximum disk usage text";
      v12 = 1305;
      goto LABEL_15;
    }
    WindowsDeleteString(v10);
  }
  v22 = GetLastError();
  v23 = CurrentIP();
  v24 = ConstructPartialMsgW(
          0x4000000u,
          "SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue: Exiting...");
  WdsSetupLogMessageW(
    v24,
    0,
    L"D",
    0,
    1308,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetNamedValue",
    v23,
    v22,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x180016bd0  mov     rax, rsp
0x180016bd3  mov     [rax+8], rbx
0x180016bd7  push    rbp
0x180016bd8  push    rsi
0x180016bd9  push    rdi
0x180016bda  push    r13
0x180016bdc  push    r14
0x180016bde  sub     rsp, 2A0h
0x180016be5  movaps  xmmword ptr [rax-38h], xmm6
0x180016be9  mov     rax, cs:__security_cookie
0x180016bf0  xor     rax, rsp
0x180016bf3  mov     [rsp+2C8h+var_48], rax
0x180016bfb  mov     r14, r8
0x180016bfe  mov     rcx, rdx; string
0x180016c01  xor     edx, edx; length
0x180016c03  call    cs:__imp_WindowsGetStringRawBuffer
0x180016c09  mov     rcx, rax; lpString1
0x180016c0c  mov     [rsp+2C8h+bIgnoreCase], 0; bIgnoreCase
0x180016c14  or      edx, 0FFFFFFFFh; cchCount1
0x180016c17  mov     r9d, edx; cchCount2
0x180016c1a  lea     r8, aMaximumdiskusa; "MaximumDiskUsageText"
0x180016c21  call    cs:__imp_CompareStringOrdinal
0x180016c27  lea     r13, aSystemsettings_77; "SystemSettings::PointInTimeRestore::CPo"...
0x180016c2e  lea     rsi, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180016c35  cmp     eax, 2
0x180016c38  jnz     loc_180016DFF
0x180016c3e  call    cs:__imp_GetLastError
0x180016c44  mov     edi, eax
0x180016c46  call    cs:__imp_CurrentIP
0x180016c4c  mov     rbx, rax
0x180016c4f  lea     rdx, aSystemsettings_12; "SystemSettings::PointInTimeRestore::CPo"...
0x180016c56  mov     ecx, 4000000h; unsigned int
0x180016c5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016c60  mov     [rsp+2C8h+var_278], 0
0x180016c68  mov     [rsp+2C8h+var_280], 0
0x180016c71  mov     [rsp+2C8h+var_288], edi
0x180016c75  mov     [rsp+2C8h+var_290], rbx
0x180016c7a  mov     [rsp+2C8h+var_298], r13
0x180016c7f  mov     [rsp+2C8h+var_2A0], rsi; char *
0x180016c84  mov     [rsp+2C8h+bIgnoreCase], 503h
0x180016c8c  xor     r9d, r9d
0x180016c8f  lea     r8, aD; "D"
0x180016c96  xor     edx, edx
0x180016c98  mov     rcx, rax
0x180016c9b  call    cs:__imp_WdsSetupLogMessageW
0x180016ca1  nop
0x180016ca2  xor     ecx, ecx; string
0x180016ca4  call    cs:__imp_WindowsDeleteString
0x180016caa  mov     [rsp+2C8h+string], 0
0x180016cb3  lea     rdx, [rsp+2C8h+string]; HSTRING *
0x180016cb8  lea     rcx, aSystemsettings_54; "SystemSettings_Misc_PointInTimeRestore_"...
0x180016cbf  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180016cc4  mov     edi, eax
0x180016cc6  mov     rbx, [rsp+2C8h+string]
0x180016ccb  test    eax, eax
0x180016ccd  jns     short loc_180016CE0
0x180016ccf  lea     rax, aFailedToGetRes_0; "Failed to get resource string for maxim"...
0x180016cd6  mov     edx, 507h
0x180016cdb  jmp     loc_180016DC5
0x180016ce0  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180016ce5  mov     rcx, rax; this
0x180016ce8  call    ?GetSnapshotDiskUsageLimit@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAKXZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetSnapshotDiskUsageLimit(void)
0x180016ced  mov     ebp, eax
0x180016cef  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180016cf4  mov     rdi, rax
0x180016cf7  lea     rsi, [rax+108h]
0x180016cfe  mov     rcx, rsi; SRWLock
0x180016d01  call    cs:__imp_AcquireSRWLockShared
0x180016d07  mov     rdi, [rdi+148h]
0x180016d0e  test    rsi, rsi
0x180016d11  jz      short loc_180016D1C
0x180016d13  mov     rcx, rsi; SRWLock
0x180016d16  call    cs:__imp_ReleaseSRWLockShared
0x180016d1c  xorps   xmm6, xmm6
0x180016d1f  test    rdi, rdi
0x180016d22  jz      short loc_180016D66
0x180016d24  cvtsi2ss xmm6, rbp
0x180016d29  mulss   xmm6, cs:__real@44800000
0x180016d31  mulss   xmm6, cs:__real@44800000
0x180016d39  xorps   xmm0, xmm0
0x180016d3c  js      short loc_180016D45
0x180016d3e  cvtsi2ss xmm0, rdi
0x180016d43  jmp     short loc_180016D5A
0x180016d45  mov     rax, rdi
0x180016d48  shr     rax, 1
0x180016d4b  and     edi, 1
0x180016d4e  or      rax, rdi
0x180016d51  cvtsi2ss xmm0, rax
0x180016d56  addss   xmm0, xmm0
0x180016d5a  divss   xmm6, xmm0
0x180016d5e  mulss   xmm6, cs:__real@42c80000
0x180016d66  xor     edx, edx; length
0x180016d68  mov     rcx, rbx; string
0x180016d6b  call    cs:__imp_WindowsGetStringRawBuffer
0x180016d71  shr     ebp, 0Ah
0x180016d74  cvtps2pd xmm3, xmm6
0x180016d77  mov     [rsp+2C8h+bIgnoreCase], ebp
0x180016d7b  movq    r9, xmm3
0x180016d80  mov     r8, rax; unsigned __int16 *
0x180016d83  mov     edx, 104h; unsigned __int64
0x180016d88  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180016d8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016d92  mov     edi, eax
0x180016d94  test    eax, eax
0x180016d96  jns     short loc_180016DA6
0x180016d98  lea     rax, aFailedToFormat_5; "Failed to format maximum disk usage tex"...
0x180016d9f  mov     edx, 516h
0x180016da4  jmp     short loc_180016DC5
0x180016da6  mov     rdx, r14; struct IInspectable **
0x180016da9  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180016dae  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180016db3  mov     edi, eax
0x180016db5  test    eax, eax
0x180016db7  jns     short loc_180016DEF
0x180016db9  lea     rax, aFailedToCreate_11; "Failed to create string for maximum dis"...
0x180016dc0  mov     edx, 519h; void *
0x180016dc5  mov     qword ptr [rsp+2C8h+bIgnoreCase], rax; int
0x180016dca  mov     r9d, edi; char *
0x180016dcd  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180016dd4  mov     rcx, [rsp+2C8h]; this
0x180016ddc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016de1  nop
0x180016de2  mov     rcx, rbx; string
0x180016de5  call    cs:__imp_WindowsDeleteString
0x180016deb  mov     eax, edi
0x180016ded  jmp     short loc_180016E64
0x180016def  mov     rcx, rbx; string
0x180016df2  call    cs:__imp_WindowsDeleteString
0x180016df8  lea     rsi, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180016dff  call    cs:__imp_GetLastError
0x180016e05  mov     edi, eax
0x180016e07  call    cs:__imp_CurrentIP
0x180016e0d  mov     rbx, rax
0x180016e10  lea     rdx, aSystemsettings_22; "SystemSettings::PointInTimeRestore::CPo"...
0x180016e17  mov     ecx, 4000000h; unsigned int
0x180016e1c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180016e21  mov     [rsp+2C8h+var_278], 0
0x180016e29  mov     [rsp+2C8h+var_280], 0
0x180016e32  mov     [rsp+2C8h+var_288], edi
0x180016e36  mov     [rsp+2C8h+var_290], rbx
0x180016e3b  mov     [rsp+2C8h+var_298], r13
0x180016e40  mov     [rsp+2C8h+var_2A0], rsi
0x180016e45  mov     [rsp+2C8h+bIgnoreCase], 51Ch
0x180016e4d  xor     r9d, r9d
0x180016e50  lea     r8, aD; "D"
0x180016e57  xor     edx, edx
0x180016e59  mov     rcx, rax
0x180016e5c  call    cs:__imp_WdsSetupLogMessageW
0x180016e62  xor     eax, eax
0x180016e64  mov     rcx, [rsp+2C8h+var_48]
0x180016e6c  xor     rcx, rsp; StackCookie
0x180016e6f  call    __security_check_cookie
0x180016e74  lea     r11, [rsp+2C8h+var_28]
0x180016e7c  mov     rbx, [r11+30h]
0x180016e80  movaps  xmm6, xmmword ptr [r11-10h]
0x180016e85  mov     rsp, r11
0x180016e88  pop     r14
0x180016e8a  pop     r13
0x180016e8c  pop     rdi
0x180016e8d  pop     rsi
0x180016e8e  pop     rbp
0x180016e8f  retn
```

# SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString(HSTRING__ * *)

- ea: `0x18001a3c0`
- end: `0x18001a77b`
- name: `?GetValueString@CPointInTimeRestoreCurrentDiskUsageSetting@PointInTimeRestore@SystemSettings@@MEAAJPEAPEAUHSTRING__@@@Z`
- size: `955`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002350`
- `0x180009718`
- `0x18000b784`
- `0x18000bef4`
- `0x18001868c`
- `0x18001a3c0`
- `0x180025920`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001a4af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001a4af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a4c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001a6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001a6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a53d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a65c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a53d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a65c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a4fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a4fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a743`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a463`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a735`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a463`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001a735`
- `WDSCORE!CurrentIP` at `0x18001a404`
- `WDSCORE!CurrentIP` at `0x18001a6e0`
- `WDSCORE!CurrentIP` at `0x18001a404`
- `WDSCORE!CurrentIP` at `0x18001a6e0`

## string_xrefs

- `0x18001a6bf`: `Failed to create HSTRING for current disk usage value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *this,
        HSTRING *a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  RTL_SRWLOCK *Current; // rbx
  RTL_SRWLOCK *v8; // rdi
  PVOID Ptr; // rbx
  float v10; // xmm6_4
  float v11; // xmm6_4
  HSTRING *v12; // r8
  HRESULT ResourceStringById; // ebx
  const unsigned __int16 *v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  HSTRING *v17; // r8
  const unsigned __int16 *v18; // rax
  HSTRING *v19; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v21; // rdx
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  char *v26; // [rsp+30h] [rbp-D8h]
  HSTRING string[2]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR sourceString[264]; // [rsp+78h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString: Getting current"
         " disk usage setting value");
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    1068,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString",
    v5,
    LastError,
    0,
    0);
  if ( !*((_DWORD *)this + 64) )
  {
    (*(void (__fastcall **)(SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *, const WCHAR *, SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *))(*(_QWORD *)this + 288LL))(
      this,
      L"Value",
      this);
    *((_DWORD *)this + 64) = 1;
  }
  string[0] = 0;
  Current = (RTL_SRWLOCK *)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  v8 = Current + 33;
  AcquireSRWLockShared(Current + 33);
  Ptr = Current[40].Ptr;
  if ( v8 )
    ReleaseSRWLockShared(v8);
  v10 = (float)(int)Ptr * 0.0009765625;
  if ( v10 <= 1024.0 )
  {
    WindowsDeleteString(0);
    string[0] = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotDiskUsage_KB",
                           string,
                           v19);
    if ( ResourceStringById < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x455,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)"Failed to get resource string for snapshot current disk usage value KB",
        v26);
      goto LABEL_26;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v15 = StringCchPrintfW(sourceString, 0x104u, StringRawBuffer, v10);
    ResourceStringById = v15;
    if ( v15 < 0 )
    {
      v16 = 1110;
      goto LABEL_11;
    }
  }
  else
  {
    v11 = v10 * 0.0009765625;
    if ( v11 <= 1024.0 )
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotDiskUsage_MB",
                             string,
                             v17);
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x44E,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)"Failed to get resource string for snapshot current disk usage value MB",
          v26);
        goto LABEL_26;
      }
      v18 = WindowsGetStringRawBuffer(string[0], 0);
      v15 = StringCchPrintfW(sourceString, 0x104u, v18, v11);
      ResourceStringById = v15;
      if ( v15 < 0 )
      {
        v16 = 1103;
        goto LABEL_11;
      }
    }
    else
    {
      WindowsDeleteString(0);
      string[0] = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotDiskUsage_GB",
                             string,
                             v12);
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x448,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)"Failed to get resource string for snapshot current disk usage value GB",
          v26);
        goto LABEL_26;
      }
      v14 = WindowsGetStringRawBuffer(string[0], 0);
      v15 = StringCchPrintfW(sourceString, 0x104u, v14, (float)(v11 * 0.0009765625));
      ResourceStringById = v15;
      if ( v15 < 0 )
      {
        v16 = 1097;
LABEL_11:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v16,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v15,
          (int)"Failed to format snapshot current disk usage value string",
          v26);
        goto LABEL_26;
      }
    }
  }
  v21 = -1;
  do
    ++v21;
  while ( sourceString[v21] );
  ResourceStringById = WindowsCreateString(sourceString, v21, a2);
  if ( ResourceStringById >= 0 )
  {
    v22 = GetLastError();
    v23 = CurrentIP();
    v24 = ConstructPartialMsgW(
            0x4000000u,
            "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString: Exiting...");
    WdsSetupLogMessageW(
      v24,
      0,
      L"D",
      0,
      1116,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::GetValueString",
      v23,
      v22,
      0,
      0);
    ResourceStringById = 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x45A,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)"Failed to create HSTRING for current disk usage value",
      v26);
  }
LABEL_26:
  WindowsDeleteString(string[0]);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x18001a3c0  mov     rax, rsp
0x18001a3c3  mov     [rax+18h], rbx
0x18001a3c7  mov     [rax+20h], rsi
0x18001a3cb  push    rbp
0x18001a3cc  push    rdi
0x18001a3cd  push    r13
0x18001a3cf  push    r14
0x18001a3d1  push    r15
0x18001a3d3  lea     rbp, [rax-1C8h]
0x18001a3da  sub     rsp, 2A0h
0x18001a3e1  movaps  xmmword ptr [rax-38h], xmm6
0x18001a3e5  mov     rax, cs:__security_cookie
0x18001a3ec  xor     rax, rsp
0x18001a3ef  mov     [rbp+1C0h+var_40], rax
0x18001a3f6  mov     r14, rdx
0x18001a3f9  mov     rsi, rcx
0x18001a3fc  call    cs:__imp_GetLastError
0x18001a402  mov     edi, eax
0x18001a404  call    cs:__imp_CurrentIP
0x18001a40a  mov     rbx, rax
0x18001a40d  lea     rdx, aSystemsettings_66; "SystemSettings::PointInTimeRestore::CPo"...
0x18001a414  mov     ecx, 4000000h; unsigned int
0x18001a419  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001a41e  xor     r15d, r15d
0x18001a421  mov     [rsp+2C0h+var_270], r15d
0x18001a426  mov     qword ptr [rsp+2C0h+var_278], r15
0x18001a42b  mov     dword ptr [rsp+2C0h+var_280], edi
0x18001a42f  mov     qword ptr [rsp+2C0h+var_288], rbx
0x18001a434  lea     r13, aSystemsettings_102; "SystemSettings::PointInTimeRestore::CPo"...
0x18001a43b  mov     [rsp+2C0h+var_290], r13
0x18001a440  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001a447  mov     [rsp+2C0h+var_298], rcx; char *
0x18001a44c  mov     [rsp+2C0h+var_2A0], 42Ch
0x18001a454  xor     r9d, r9d
0x18001a457  lea     r8, aD; "D"
0x18001a45e  xor     edx, edx
0x18001a460  mov     rcx, rax
0x18001a463  call    cs:__imp_WdsSetupLogMessageW
0x18001a469  cmp     [rsi+100h], r15d
0x18001a470  jnz     short loc_18001A498
0x18001a472  mov     rax, [rsi]
0x18001a475  mov     r8, rsi
0x18001a478  lea     rdx, aValue; "Value"
0x18001a47f  mov     rcx, rsi
0x18001a482  mov     rax, [rax+120h]
0x18001a489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a48e  mov     dword ptr [rsi+100h], 1
0x18001a498  mov     [rsp+2C0h+string], r15
0x18001a49d  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x18001a4a2  mov     rbx, rax
0x18001a4a5  lea     rdi, [rax+108h]
0x18001a4ac  mov     rcx, rdi; SRWLock
0x18001a4af  call    cs:__imp_AcquireSRWLockShared
0x18001a4b5  mov     rbx, [rbx+140h]
0x18001a4bc  test    rdi, rdi
0x18001a4bf  jz      short loc_18001A4CA
0x18001a4c1  mov     rcx, rdi; SRWLock
0x18001a4c4  call    cs:__imp_ReleaseSRWLockShared
0x18001a4ca  xorps   xmm6, xmm6
0x18001a4cd  cvtsi2ss xmm6, rbx
0x18001a4d2  mulss   xmm6, cs:__real@3a800000
0x18001a4da  movss   xmm0, cs:__real@44800000
0x18001a4e2  xor     ecx, ecx; string
0x18001a4e4  comiss  xmm6, xmm0
0x18001a4e7  jbe     loc_18001A61A
0x18001a4ed  mulss   xmm6, cs:__real@3a800000
0x18001a4f5  comiss  xmm6, xmm0
0x18001a4f8  jbe     loc_18001A59B
0x18001a4fe  call    cs:__imp_WindowsDeleteString
0x18001a504  mov     [rsp+2C0h+string], r15
0x18001a509  lea     rdx, [rsp+2C0h+string]; HSTRING *
0x18001a50e  lea     rcx, aSystemsettings_23; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001a515  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a51a  mov     ebx, eax
0x18001a51c  test    eax, eax
0x18001a51e  jns     short loc_18001A536
0x18001a520  lea     rax, aFailedToGetRes; "Failed to get resource string for snaps"...
0x18001a527  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001a52c  mov     r9d, ebx
0x18001a52f  mov     edx, 448h
0x18001a534  jmp     short loc_18001A583
0x18001a536  xor     edx, edx; length
0x18001a538  mov     rcx, [rsp+2C0h+string]; string
0x18001a53d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a543  mulss   xmm6, cs:__real@3a800000
0x18001a54b  cvtps2pd xmm3, xmm6
0x18001a54e  movq    r9, xmm3
0x18001a553  mov     r8, rax; unsigned __int16 *
0x18001a556  mov     edx, 104h; unsigned __int64
0x18001a55b  lea     rcx, [rsp+2C0h+sourceString]; unsigned __int16 *
0x18001a560  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a565  mov     ebx, eax
0x18001a567  test    eax, eax
0x18001a569  jns     loc_18001A698
0x18001a56f  lea     rdx, aFailedToFormat_3; "Failed to format snapshot current disk "...
0x18001a576  mov     qword ptr [rsp+2C0h+var_2A0], rdx; int
0x18001a57b  mov     edx, 449h; void *
0x18001a580  mov     r9d, eax; char *
0x18001a583  mov     rcx, [rbp+1C8h]; this
0x18001a58a  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x18001a591  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a596  jmp     loc_18001A73E
0x18001a59b  call    cs:__imp_WindowsDeleteString
0x18001a5a1  mov     [rsp+2C0h+string], r15
0x18001a5a6  lea     rdx, [rsp+2C0h+string]; HSTRING *
0x18001a5ab  lea     rcx, aSystemsettings_24; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001a5b2  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a5b7  mov     ebx, eax
0x18001a5b9  test    eax, eax
0x18001a5bb  jns     short loc_18001A5D3
0x18001a5bd  lea     rax, aFailedToGetRes_8; "Failed to get resource string for snaps"...
0x18001a5c4  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001a5c9  mov     r9d, ebx
0x18001a5cc  mov     edx, 44Eh
0x18001a5d1  jmp     short loc_18001A583
0x18001a5d3  xor     edx, edx; length
0x18001a5d5  mov     rcx, [rsp+2C0h+string]; string
0x18001a5da  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a5e0  cvtps2pd xmm3, xmm6
0x18001a5e3  movq    r9, xmm3
0x18001a5e8  mov     r8, rax; unsigned __int16 *
0x18001a5eb  mov     edx, 104h; unsigned __int64
0x18001a5f0  lea     rcx, [rsp+2C0h+sourceString]; unsigned __int16 *
0x18001a5f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a5fa  mov     ebx, eax
0x18001a5fc  test    eax, eax
0x18001a5fe  jns     loc_18001A698
0x18001a604  lea     rdx, aFailedToFormat_3; "Failed to format snapshot current disk "...
0x18001a60b  mov     qword ptr [rsp+2C0h+var_2A0], rdx
0x18001a610  mov     edx, 44Fh
0x18001a615  jmp     loc_18001A580
0x18001a61a  call    cs:__imp_WindowsDeleteString
0x18001a620  mov     [rsp+2C0h+string], r15
0x18001a625  lea     rdx, [rsp+2C0h+string]; HSTRING *
0x18001a62a  lea     rcx, aSystemsettings_56; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001a631  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a636  mov     ebx, eax
0x18001a638  test    eax, eax
0x18001a63a  jns     short loc_18001A655
0x18001a63c  lea     rax, aFailedToGetRes_1; "Failed to get resource string for snaps"...
0x18001a643  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001a648  mov     r9d, ebx
0x18001a64b  mov     edx, 455h
0x18001a650  jmp     loc_18001A583
0x18001a655  xor     edx, edx; length
0x18001a657  mov     rcx, [rsp+2C0h+string]; string
0x18001a65c  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a662  cvtps2pd xmm3, xmm6
0x18001a665  movq    r9, xmm3
0x18001a66a  mov     r8, rax; unsigned __int16 *
0x18001a66d  mov     edx, 104h; unsigned __int64
0x18001a672  lea     rcx, [rsp+2C0h+sourceString]; unsigned __int16 *
0x18001a677  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a67c  mov     ebx, eax
0x18001a67e  test    eax, eax
0x18001a680  jns     short loc_18001A698
0x18001a682  lea     rdx, aFailedToFormat_3; "Failed to format snapshot current disk "...
0x18001a689  mov     qword ptr [rsp+2C0h+var_2A0], rdx
0x18001a68e  mov     edx, 456h
0x18001a693  jmp     loc_18001A580
0x18001a698  lea     rax, [rsp+2C0h+sourceString]
0x18001a69d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a6a1  inc     rdx; length
0x18001a6a4  cmp     [rax+rdx*2], r15w
0x18001a6a9  jnz     short loc_18001A6A1
0x18001a6ab  mov     r8, r14; string
0x18001a6ae  lea     rcx, [rsp+2C0h+sourceString]; sourceString
0x18001a6b3  call    cs:__imp_WindowsCreateString
0x18001a6b9  mov     ebx, eax
0x18001a6bb  test    eax, eax
0x18001a6bd  jns     short loc_18001A6D8
0x18001a6bf  lea     rax, aFailedToCreate_4; "Failed to create HSTRING for current di"...
0x18001a6c6  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18001a6cb  mov     r9d, ebx
0x18001a6ce  mov     edx, 45Ah
0x18001a6d3  jmp     loc_18001A583
0x18001a6d8  call    cs:__imp_GetLastError
0x18001a6de  mov     edi, eax
0x18001a6e0  call    cs:__imp_CurrentIP
0x18001a6e6  mov     rbx, rax
0x18001a6e9  lea     rdx, aSystemsettings_11; "SystemSettings::PointInTimeRestore::CPo"...
0x18001a6f0  mov     ecx, 4000000h; unsigned int
0x18001a6f5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001a6fa  mov     [rsp+2C0h+var_270], r15d
0x18001a6ff  mov     qword ptr [rsp+2C0h+var_278], r15
0x18001a704  mov     dword ptr [rsp+2C0h+var_280], edi
0x18001a708  mov     qword ptr [rsp+2C0h+var_288], rbx
0x18001a70d  mov     [rsp+2C0h+var_290], r13
0x18001a712  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x18001a719  mov     [rsp+2C0h+var_298], rcx
0x18001a71e  mov     [rsp+2C0h+var_2A0], 45Ch
0x18001a726  xor     r9d, r9d
0x18001a729  lea     r8, aD; "D"
0x18001a730  xor     edx, edx
0x18001a732  mov     rcx, rax
0x18001a735  call    cs:__imp_WdsSetupLogMessageW
0x18001a73b  mov     ebx, r15d
0x18001a73e  mov     rcx, [rsp+2C0h+string]; string
0x18001a743  call    cs:__imp_WindowsDeleteString
0x18001a749  mov     eax, ebx
0x18001a74b  mov     rcx, [rbp+1C0h+var_40]
0x18001a752  xor     rcx, rsp; StackCookie
0x18001a755  call    __security_check_cookie
0x18001a75a  lea     r11, [rsp+2C0h+var_20]
0x18001a762  mov     rbx, [r11+40h]
0x18001a766  mov     rsi, [r11+48h]
0x18001a76a  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a76f  mov     rsp, r11
0x18001a772  pop     r15
0x18001a774  pop     r14
0x18001a776  pop     r13
0x18001a778  pop     rdi
0x18001a779  pop     rbp
0x18001a77a  retn
```

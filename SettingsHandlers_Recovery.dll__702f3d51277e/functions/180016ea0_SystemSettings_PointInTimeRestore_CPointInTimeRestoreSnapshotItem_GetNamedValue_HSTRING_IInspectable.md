# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x180016ea0`
- end: `0x18001718d`
- name: `?GetNamedValue@CPointInTimeRestoreSnapshotItem@PointInTimeRestore@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `749`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002350`
- `0x180009718`
- `0x18000b784`
- `0x180013c78`
- `0x180016ea0`
- `0x18001868c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fe9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016ef5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800170ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016ef5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800170ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800170b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800170e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016ed6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800170b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800170e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170d0`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180016f2e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180016f2e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016f3e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180016f3e`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180016f70`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180016f70`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180016fdf`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180016fdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::GetNamedValue(
        const FILETIME *this,
        HSTRING a2,
        struct IInspectable **a3)
{
  const WCHAR *StringRawBuffer; // rax
  signed int LastError; // eax
  signed int ResourceStringById; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  signed int v12; // eax
  HSTRING *v13; // r8
  const unsigned __int16 *v14; // rax
  const WCHAR *v15; // rax
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-E0h]
  const char *cchDate; // [rsp+28h] [rbp-D8h]
  const char *cchDatea; // [rsp+28h] [rbp-D8h]
  int cchDateb; // [rsp+28h] [rbp-D8h]
  DWORD lpCalendar; // [rsp+30h] [rbp-D0h]
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-C0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TimeStr[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR DateStr[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"SnapshotDateTime", -1, 0) == 2 )
  {
    if ( !this[29].dwLowDateTime )
    {
      WindowsDeleteString(0);
      LocalFileTime = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_NoSnapshotAvailable",
                             (HSTRING *)&LocalFileTime,
                             v13);
      if ( ResourceStringById >= 0 )
      {
        v14 = WindowsGetStringRawBuffer(*(HSTRING *)&LocalFileTime, 0);
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v14, a3);
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5AD,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)"Failed to get resource string for no PITR snapshot available",
          cchDate);
      }
      WindowsDeleteString(*(HSTRING *)&LocalFileTime);
      return (unsigned int)ResourceStringById;
    }
    LocalFileTime = 0;
    SystemTime = 0;
    FileTimeToLocalFileTime(this + 28, &LocalFileTime);
    FileTimeToSystemTime(&LocalFileTime, &SystemTime);
    if ( !GetDateFormatEx(0, 0x40u, &SystemTime, 0, DateStr, 260, 0) )
    {
      LastError = GetLastError();
      ResourceStringById = LastError;
      if ( LastError > 0 )
        ResourceStringById = (unsigned __int16)LastError | 0x80070000;
      if ( ResourceStringById >= 0 )
        return (unsigned int)ResourceStringById;
      v9 = "Failed to format snapshot creation date";
      v10 = 1420;
LABEL_8:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v10,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)v9,
        cchDatea);
      return (unsigned int)ResourceStringById;
    }
    if ( !GetTimeFormatEx(0, 2u, &SystemTime, 0, TimeStr, 260) )
    {
      v12 = GetLastError();
      ResourceStringById = v12;
      if ( v12 > 0 )
        ResourceStringById = (unsigned __int16)v12 | 0x80070000;
      if ( ResourceStringById >= 0 )
        return (unsigned int)ResourceStringById;
      v9 = "Failed to format snapshot creation time";
      v10 = 1432;
      goto LABEL_8;
    }
    ResourceStringById = StringCchPrintfW(v23, 0x104u, L"%s %s", DateStr, TimeStr);
    if ( ResourceStringById < 0 )
    {
      v9 = "Failed to format snapshot date and time";
      v10 = 1443;
      goto LABEL_8;
    }
    return SystemSettings::DataModel::PropValueHelper::CreateString(v23, a3);
  }
  v15 = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(v15, -1, L"SnapshotVersion", -1, 0) == 2 && this[29].dwLowDateTime )
  {
    lpCalendar = this[27].dwHighDateTime;
    cchDateb = this[27].dwLowDateTime;
    bIgnoreCase[0] = this[26].dwHighDateTime;
    ResourceStringById = StringCchPrintfW(
                           v23,
                           0x104u,
                           L"%d.%d.%d.%d",
                           this[26].dwLowDateTime,
                           *(_QWORD *)bIgnoreCase,
                           cchDateb,
                           lpCalendar);
    if ( ResourceStringById < 0 )
    {
      v9 = "Failed to format snapshot version";
      v10 = 1472;
      goto LABEL_8;
    }
    return SystemSettings::DataModel::PropValueHelper::CreateString(v23, a3);
  }
  return 0;
}

```

## disassembly

```asm
0x180016ea0  mov     [rsp-8+arg_18], rbx
0x180016ea5  push    rbp
0x180016ea6  push    rsi
0x180016ea7  push    rdi
0x180016ea8  lea     rbp, [rsp-5A0h]
0x180016eb0  sub     rsp, 6A0h
0x180016eb7  mov     rax, cs:__security_cookie
0x180016ebe  xor     rax, rsp
0x180016ec1  mov     [rbp+5B0h+var_20], rax
0x180016ec8  mov     rdi, r8
0x180016ecb  mov     rsi, rdx
0x180016ece  mov     rbx, rcx
0x180016ed1  xor     edx, edx; length
0x180016ed3  mov     rcx, rsi; string
0x180016ed6  call    cs:__imp_WindowsGetStringRawBuffer
0x180016edc  mov     rcx, rax; lpString1
0x180016edf  mov     [rsp+6B0h+bIgnoreCase], 0; bIgnoreCase
0x180016ee7  or      r9d, 0FFFFFFFFh; cchCount2
0x180016eeb  lea     r8, aSnapshotdateti; "SnapshotDateTime"
0x180016ef2  or      edx, r9d; cchCount1
0x180016ef5  call    cs:__imp_CompareStringOrdinal
0x180016efb  cmp     eax, 2
0x180016efe  jnz     loc_1800170DB
0x180016f04  cmp     dword ptr [rbx+0E8h], 0
0x180016f0b  jz      loc_180017060
0x180016f11  mov     qword ptr [rsp+6B0h+LocalFileTime.dwLowDateTime], 0
0x180016f1a  xorps   xmm0, xmm0
0x180016f1d  movups  xmmword ptr [rsp+6B0h+SystemTime.wYear], xmm0
0x180016f22  lea     rcx, [rbx+0E0h]; lpFileTime
0x180016f29  lea     rdx, [rsp+6B0h+LocalFileTime]; lpLocalFileTime
0x180016f2e  call    cs:__imp_FileTimeToLocalFileTime
0x180016f34  lea     rdx, [rsp+6B0h+SystemTime]; lpSystemTime
0x180016f39  lea     rcx, [rsp+6B0h+LocalFileTime]; lpFileTime
0x180016f3e  call    cs:__imp_FileTimeToSystemTime
0x180016f44  mov     qword ptr [rsp+6B0h+lpCalendar], 0; lpCalendar
0x180016f4d  mov     ebx, 104h
0x180016f52  mov     dword ptr [rsp+6B0h+cchDate], ebx; char *
0x180016f56  lea     rax, [rbp+5B0h+DateStr]
0x180016f5d  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; lpDateStr
0x180016f62  xor     r9d, r9d; lpFormat
0x180016f65  lea     r8, [rsp+6B0h+SystemTime]; lpDate
0x180016f6a  lea     edx, [r9+40h]; dwFlags
0x180016f6e  xor     ecx, ecx; lpLocaleName
0x180016f70  call    cs:__imp_GetDateFormatEx
0x180016f76  test    eax, eax
0x180016f78  jnz     short loc_180016FC1
0x180016f7a  call    cs:__imp_GetLastError
0x180016f80  mov     ebx, eax
0x180016f82  test    eax, eax
0x180016f84  jle     short loc_180016F8F
0x180016f86  movzx   ebx, ax
0x180016f89  or      ebx, 80070000h
0x180016f8f  test    ebx, ebx
0x180016f91  jns     short loc_180016FBA
0x180016f93  lea     rax, aFailedToFormat_1; "Failed to format snapshot creation date"
0x180016f9a  mov     edx, 58Ch; void *
0x180016f9f  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180016fa6  mov     r9d, ebx; char *
0x180016fa9  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; int
0x180016fae  mov     rcx, [rbp+5B8h]; this
0x180016fb5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016fba  mov     eax, ebx
0x180016fbc  jmp     loc_18001716B
0x180016fc1  mov     dword ptr [rsp+6B0h+cchDate], ebx; cchTime
0x180016fc5  lea     rax, [rbp+5B0h+TimeStr]
0x180016fcc  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; lpTimeStr
0x180016fd1  xor     r9d, r9d; lpFormat
0x180016fd4  lea     r8, [rsp+6B0h+SystemTime]; lpTime
0x180016fd9  lea     edx, [r9+2]; dwFlags
0x180016fdd  xor     ecx, ecx; lpLocaleName
0x180016fdf  call    cs:__imp_GetTimeFormatEx
0x180016fe5  test    eax, eax
0x180016fe7  jnz     short loc_180017010
0x180016fe9  call    cs:__imp_GetLastError
0x180016fef  mov     ebx, eax
0x180016ff1  test    eax, eax
0x180016ff3  jle     short loc_180016FFE
0x180016ff5  movzx   ebx, ax
0x180016ff8  or      ebx, 80070000h
0x180016ffe  test    ebx, ebx
0x180017000  jns     short loc_180016FBA
0x180017002  lea     rax, aFailedToFormat_2; "Failed to format snapshot creation time"
0x180017009  mov     edx, 598h
0x18001700e  jmp     short loc_180016F9F
0x180017010  lea     rax, [rbp+5B0h+TimeStr]
0x180017017  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax
0x18001701c  lea     r9, [rbp+5B0h+DateStr]
0x180017023  lea     r8, aSS; "%s %s"
0x18001702a  mov     rdx, rbx; unsigned __int64
0x18001702d  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x180017032  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017037  mov     ebx, eax
0x180017039  test    eax, eax
0x18001703b  jns     short loc_18001704E
0x18001703d  lea     rax, aFailedToFormat_4; "Failed to format snapshot date and time"
0x180017044  mov     edx, 5A3h
0x180017049  jmp     loc_180016F9F
0x18001704e  mov     rdx, rdi; struct IInspectable **
0x180017051  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x180017056  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18001705b  jmp     loc_18001716B
0x180017060  xor     ecx, ecx; string
0x180017062  call    cs:__imp_WindowsDeleteString
0x180017068  mov     qword ptr [rsp+6B0h+LocalFileTime.dwLowDateTime], 0
0x180017071  lea     rdx, [rsp+6B0h+LocalFileTime]; HSTRING *
0x180017076  lea     rcx, aSystemsettings_112; "SystemSettings_Misc_PointInTimeRestore_"...
0x18001707d  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180017082  mov     ebx, eax
0x180017084  test    eax, eax
0x180017086  jns     short loc_1800170B1
0x180017088  mov     rcx, [rbp+5B8h]; this
0x18001708f  lea     rax, aFailedToGetRes_6; "Failed to get resource string for no PI"...
0x180017096  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; int
0x18001709b  mov     r9d, ebx; char *
0x18001709e  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800170a5  mov     edx, 5ADh; void *
0x1800170aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800170af  jmp     short loc_1800170CB
0x1800170b1  xor     edx, edx; length
0x1800170b3  mov     rcx, qword ptr [rsp+6B0h+LocalFileTime.dwLowDateTime]; string
0x1800170b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800170be  mov     rdx, rdi; struct IInspectable **
0x1800170c1  mov     rcx, rax; unsigned __int16 *
0x1800170c4  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800170c9  mov     ebx, eax
0x1800170cb  mov     rcx, qword ptr [rsp+6B0h+LocalFileTime.dwLowDateTime]; string
0x1800170d0  call    cs:__imp_WindowsDeleteString
0x1800170d6  jmp     loc_180016FBA
0x1800170db  xor     edx, edx; length
0x1800170dd  mov     rcx, rsi; string
0x1800170e0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800170e6  mov     rcx, rax; lpString1
0x1800170e9  mov     [rsp+6B0h+bIgnoreCase], 0; bIgnoreCase
0x1800170f1  or      r9d, 0FFFFFFFFh; cchCount2
0x1800170f5  lea     r8, aSnapshotversio; "SnapshotVersion"
0x1800170fc  or      edx, r9d; cchCount1
0x1800170ff  call    cs:__imp_CompareStringOrdinal
0x180017105  cmp     eax, 2
0x180017108  jnz     short loc_180017169
0x18001710a  cmp     dword ptr [rbx+0E8h], 0
0x180017111  jz      short loc_180017169
0x180017113  mov     eax, [rbx+0DCh]
0x180017119  mov     [rsp+6B0h+lpCalendar], eax
0x18001711d  mov     eax, [rbx+0D8h]
0x180017123  mov     dword ptr [rsp+6B0h+cchDate], eax
0x180017127  mov     eax, [rbx+0D4h]
0x18001712d  mov     [rsp+6B0h+bIgnoreCase], eax
0x180017131  mov     r9d, [rbx+0D0h]
0x180017138  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18001713f  mov     edx, 104h; unsigned __int64
0x180017144  lea     rcx, [rsp+6B0h+var_650]; unsigned __int16 *
0x180017149  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001714e  mov     ebx, eax
0x180017150  test    eax, eax
0x180017152  jns     loc_18001704E
0x180017158  lea     rax, aFailedToFormat_0; "Failed to format snapshot version"
0x18001715f  mov     edx, 5C0h
0x180017164  jmp     loc_180016F9F
0x180017169  xor     eax, eax
0x18001716b  mov     rcx, [rbp+5B0h+var_20]
0x180017172  xor     rcx, rsp; StackCookie
0x180017175  call    __security_check_cookie
0x18001717a  mov     rbx, [rsp+6B0h+arg_18]
0x180017182  add     rsp, 6A0h
0x180017189  pop     rdi
0x18001718a  pop     rsi
0x18001718b  pop     rbp
0x18001718c  retn
```

# IsOobeTwoHoursTimeLapsed(void)

- ea: `0x1800176e0`
- end: `0x18001792a`
- name: `?IsOobeTwoHoursTimeLapsed@@YA_NXZ`
- size: `586`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018928`
- `0x180018a10`

## callees

- `0x180003450`
- `0x180012118`
- `0x180012f10`
- `0x1800176e0`
- `0x1800191a4`
- `0x180019660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001774e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001774e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001780e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001780e`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180017744`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180017744`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017804`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001781c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017804`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001781c`

## string_xrefs

- `0x180017783`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800177ce`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180017879`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x18001776e`: `OOBEComplete failed, last error = %d`
- `0x1800177b2`: `ScanForUpdates triggered before OOBE completed`
- `0x18001785f`: `OOBE completion time is : %d/%d/%d %d:%d:%d. \n Current time is : %d/%d/%d %d:%d:%d`

## pseudocode

```c
bool IsOobeTwoHoursTimeLapsed(void)
{
  DWORD LastError; // [rsp+40h] [rbp-89h]
  _BYTE v2[8]; // [rsp+A0h] [rbp-29h] BYREF
  struct _FILETIME FileTime; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v4; // [rsp+B0h] [rbp-19h] BYREF
  struct _FILETIME v5; // [rsp+B8h] [rbp-11h] BYREF
  SYSTEMTIME v6; // [rsp+C0h] [rbp-9h] BYREF
  SYSTEMTIME SystemTime; // [rsp+D0h] [rbp+7h] BYREF

  FileTime = 0;
  v5 = 0;
  SystemTime = 0;
  v2[0] = 0;
  v6 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck>::GetImpl'::`2'::impl) )
  {
    LODWORD(v4) = 0;
    if ( !(unsigned int)OOBEComplete(&v4) )
    {
      LastError = GetLastError();
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
        0x17Fu,
        "IsOobeTwoHoursTimeLapsed",
        -1,
        L"OOBEComplete failed, last error = %d",
        0,
        0,
        LastError);
      return 0;
    }
    if ( !(_DWORD)v4 )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
        0x185u,
        "IsOobeTwoHoursTimeLapsed",
        -1,
        L"ScanForUpdates triggered before OOBE completed",
        0,
        0);
      return 0;
    }
  }
  OOBE::CompleteTime::TryGetTime(v2, &SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  GetSystemTime(&v6);
  SystemTimeToFileTime(&v6, &v5);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
    0x194u,
    "IsOobeTwoHoursTimeLapsed",
    -1,
    L"OOBE completion time is : %d/%d/%d %d:%d:%d. \n Current time is : %d/%d/%d %d:%d:%d",
    0,
    0,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wYear,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    v6.wMonth,
    v6.wDay,
    v6.wYear,
    v6.wHour,
    v6.wMinute,
    v6.wSecond);
  return *(_QWORD *)&v5 - *(_QWORD *)&FileTime >= 0x10C388D000uLL;
}

```

## disassembly

```asm
0x1800176e0  push    rbp
0x1800176e2  push    rbx
0x1800176e3  push    rsi
0x1800176e4  push    rdi
0x1800176e5  push    r14
0x1800176e7  push    r15
0x1800176e9  lea     rbp, [rsp-2Fh]
0x1800176ee  sub     rsp, 0F8h
0x1800176f5  mov     rax, cs:__security_cookie
0x1800176fc  xor     rax, rsp
0x1800176ff  mov     [rbp+57h+var_40], rax
0x180017703  xorps   xmm0, xmm0
0x180017706  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18001770e  xorps   xmm1, xmm1
0x180017711  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], 0
0x180017719  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001771d  mov     [rbp+57h+var_80], 0
0x180017721  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm1
0x180017725  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck>::GetImpl(void)'::`2'::impl
0x18001772c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OOBECompleteCheck>::__private_IsEnabled(void)
0x180017731  test    al, al
0x180017733  jz      loc_1800177EF
0x180017739  lea     rcx, [rbp+57h+var_70]
0x18001773d  mov     dword ptr [rbp+57h+var_70], 0
0x180017744  call    cs:__imp_OOBEComplete
0x18001774a  test    eax, eax
0x18001774c  jnz     short loc_1800177A3
0x18001774e  call    cs:__imp_GetLastError
0x180017754  mov     [rsp+120h+var_E0], eax
0x180017758  lea     r9, aIsoobetwohours; "IsOobeTwoHoursTimeLapsed"
0x18001775f  mov     [rsp+120h+var_E8], 0; unsigned __int16 *
0x180017768  mov     r8d, 17Fh; unsigned int
0x18001776e  lea     rax, aOobecompleteFa; "OOBEComplete failed, last error = %d"
0x180017775  mov     [rsp+120h+var_F0], 0; char *
0x18001777e  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x180017783  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x18001778a  mov     ecx, 2; unsigned int
0x18001778f  mov     [rsp+120h+var_100], 0FFFFFFFFh; int
0x180017797  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001779c  xor     al, al
0x18001779e  jmp     loc_18001790E
0x1800177a3  cmp     dword ptr [rbp+57h+var_70], 0
0x1800177a7  jnz     short loc_1800177EF
0x1800177a9  mov     [rsp+120h+var_E8], 0; unsigned __int16 *
0x1800177b2  lea     rax, aScanforupdates_3; "ScanForUpdates triggered before OOBE co"...
0x1800177b9  mov     [rsp+120h+var_F0], 0; char *
0x1800177c2  lea     r9, aIsoobetwohours; "IsOobeTwoHoursTimeLapsed"
0x1800177c9  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800177ce  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x1800177d5  mov     r8d, 185h; unsigned int
0x1800177db  mov     [rsp+120h+var_100], 0FFFFFFFFh; int
0x1800177e3  mov     ecx, 3; unsigned int
0x1800177e8  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800177ed  jmp     short loc_18001779C
0x1800177ef  lea     rdx, [rbp+57h+SystemTime]
0x1800177f3  lea     rcx, [rbp+57h+var_80]
0x1800177f7  call    OOBE__CompleteTime__TryGetTime
0x1800177fc  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180017800  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180017804  call    cs:__imp_SystemTimeToFileTime
0x18001780a  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18001780e  call    cs:__imp_GetSystemTime
0x180017814  lea     rdx, [rbp+57h+var_68]; lpFileTime
0x180017818  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18001781c  call    cs:__imp_SystemTimeToFileTime
0x180017822  movzx   eax, [rbp+57h+var_60.wSecond]
0x180017826  movzx   ecx, [rbp+57h+var_60.wMinute]
0x18001782a  movzx   edx, [rbp+57h+var_60.wHour]
0x18001782e  movzx   r8d, [rbp+57h+var_60.wYear]
0x180017833  movzx   r9d, [rbp+57h+var_60.wDay]
0x180017838  movzx   r10d, [rbp+57h+var_60.wMonth]
0x18001783d  movzx   r11d, [rbp+57h+SystemTime.wSecond]
0x180017842  movzx   ebx, [rbp+57h+SystemTime.wMinute]
0x180017846  movzx   edi, [rbp+57h+SystemTime.wHour]
0x18001784a  movzx   esi, [rbp+57h+SystemTime.wYear]
0x18001784e  movzx   r14d, [rbp+57h+SystemTime.wDay]
0x180017853  movzx   r15d, [rbp+57h+SystemTime.wMonth]
0x180017858  mov     [rsp+120h+var_88], eax
0x18001785f  lea     rax, aOobeCompletion_0; "OOBE completion time is : %d/%d/%d %d:%"...
0x180017866  mov     [rsp+120h+var_90], ecx
0x18001786d  mov     ecx, 3; unsigned int
0x180017872  mov     [rsp+120h+var_98], edx
0x180017879  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180017880  mov     [rsp+120h+var_A0], r8d
0x180017888  mov     r8d, 194h; unsigned int
0x18001788e  mov     [rsp+120h+var_A8], r9d
0x180017893  lea     r9, aIsoobetwohours; "IsOobeTwoHoursTimeLapsed"
0x18001789a  mov     [rsp+120h+var_B0], r10d
0x18001789f  mov     [rsp+120h+var_B8], r11d
0x1800178a4  mov     [rsp+120h+var_C0], ebx
0x1800178a8  mov     [rsp+120h+var_C8], edi
0x1800178ac  mov     [rsp+120h+var_D0], esi
0x1800178b0  mov     [rsp+120h+var_D8], r14d
0x1800178b5  mov     [rsp+120h+var_E0], r15d
0x1800178ba  mov     [rsp+120h+var_E8], 0; unsigned __int16 *
0x1800178c3  mov     [rsp+120h+var_F0], 0; char *
0x1800178cc  mov     [rsp+120h+var_F8], rax; unsigned __int16 *
0x1800178d1  mov     [rsp+120h+var_100], 0FFFFFFFFh; int
0x1800178d9  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800178de  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x1800178e1  mov     rcx, 10C388D000h
0x1800178eb  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800178ee  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x1800178f1  mov     dword ptr [rbp+57h+var_70], eax
0x1800178f4  mov     eax, [rbp+57h+var_68.dwHighDateTime]
0x1800178f7  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x1800178fa  mov     eax, [rbp+57h+var_68.dwLowDateTime]
0x1800178fd  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180017900  mov     rax, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180017904  sub     rax, [rbp+57h+var_70]
0x180017908  cmp     rax, rcx
0x18001790b  setnb   al
0x18001790e  mov     rcx, [rbp+57h+var_40]
0x180017912  xor     rcx, rsp; StackCookie
0x180017915  call    __security_check_cookie
0x18001791a  add     rsp, 0F8h
0x180017921  pop     r15
0x180017923  pop     r14
0x180017925  pop     rdi
0x180017926  pop     rsi
0x180017927  pop     rbx
0x180017928  pop     rbp
0x180017929  retn
```

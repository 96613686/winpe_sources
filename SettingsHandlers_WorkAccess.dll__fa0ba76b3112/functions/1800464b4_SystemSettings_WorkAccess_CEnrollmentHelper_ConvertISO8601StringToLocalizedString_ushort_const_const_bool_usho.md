# SystemSettings::WorkAccess::CEnrollmentHelper::ConvertISO8601StringToLocalizedString(ushort const * const,bool,ushort * *)

- ea: `0x1800464b4`
- end: `0x18004675f`
- name: `?ConvertISO8601StringToLocalizedString@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJQEBG_NPEAPEAG@Z`
- size: `683`
- prototype: `__int64 __fastcall(const unsigned __int16 *const, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800476b8`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x1800349f0`
- `0x1800464b4`
- `0x18004d248`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046617`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046656`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046691`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046617`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046656`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180046691`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004671b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004671b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800466dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800466dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800466c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800466c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465db`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x180046533`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x180046533`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180046572`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180046572`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800465cb`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800465cb`

## string_xrefs

- `0x180046501`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180046633`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
int __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::ConvertISO8601StringToLocalizedString(
        const unsigned __int16 *a1,
        char a2,
        unsigned __int16 **a3)
{
  signed int v5; // ebx
  __int64 v6; // rdx
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  int lpDateStr; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  SYSTEMTIME Date; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR DateStr[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TimeStr[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  if ( !a1 )
  {
    v5 = -2147024809;
    v6 = 745;
    goto LABEL_3;
  }
  v17 = 0;
  Date = 0;
  v5 = ISO8601StringToSystemTime(a1, 1, &Date, &v17);
  if ( v5 < 0 )
  {
    v6 = 751;
    goto LABEL_3;
  }
  if ( !GetDateFormatEx(0, 0x40u, &Date, 0, DateStr, 260, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      return v5;
    v6 = 752;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v5,
      lpDateStr);
    return v5;
  }
  if ( !GetTimeFormatEx(0, 0, &Date, 0, TimeStr, 260) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 >= 0 )
      return v5;
    v6 = 753;
    goto LABEL_3;
  }
  v10 = _o_wcscat_s(DateStr, 260, L" ");
  if ( v10 )
  {
    v11 = 754;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
             (const char *)v10,
             lpDateStr);
  }
  v10 = _o_wcscat_s(DateStr, 260, TimeStr);
  if ( v10 )
  {
    v11 = 755;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
             (const char *)v10,
             lpDateStr);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc>::GetImpl'::`2'::impl) )
  {
    if ( a2 )
    {
      v10 = _o_wcscat_s(DateStr, 260, L" UTC");
      if ( v10 )
      {
        v11 = 760;
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v11,
                 (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                 (const char *)v10,
                 lpDateStr);
      }
    }
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( DateStr[v13] );
  ProcessHeap = GetProcessHeap();
  v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v13 + 2);
  *a3 = v15;
  if ( !v15 )
  {
    v5 = -2147024882;
    v6 = 764;
    goto LABEL_3;
  }
  do
    ++v12;
  while ( DateStr[v12] );
  v10 = _o_wcscpy_s(v15, v12 + 1, DateStr);
  if ( v10 )
  {
    v11 = 765;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
             (const char *)v10,
             lpDateStr);
  }
  return 0;
}

```

## disassembly

```asm
0x1800464b4  mov     [rsp-8+arg_8], rbx
0x1800464b9  mov     [rsp-8+arg_18], rsi
0x1800464be  push    rbp
0x1800464bf  push    rdi
0x1800464c0  push    r14
0x1800464c2  lea     rbp, [rsp-390h]
0x1800464ca  sub     rsp, 490h
0x1800464d1  mov     rax, cs:__security_cookie
0x1800464d8  xor     rax, rsp
0x1800464db  mov     [rbp+3A0h+var_20], rax
0x1800464e2  xor     r14d, r14d
0x1800464e5  mov     rsi, r8
0x1800464e8  mov     dil, dl
0x1800464eb  test    rcx, rcx
0x1800464ee  jnz     short loc_180046517
0x1800464f0  mov     ebx, 80070057h
0x1800464f5  mov     edx, 2E9h; void *
0x1800464fa  mov     rcx, [rbp+3A8h]; this
0x180046501  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180046508  mov     r9d, ebx; char *
0x18004650b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046510  mov     eax, ebx
0x180046512  jmp     loc_180046737
0x180046517  xorps   xmm0, xmm0
0x18004651a  mov     [rsp+4A0h+var_460], r14d
0x18004651f  lea     r9, [rsp+4A0h+var_460]
0x180046524  mov     edx, 1
0x180046529  lea     r8, [rsp+4A0h+Date]
0x18004652e  movups  xmmword ptr [rsp+4A0h+Date.wYear], xmm0
0x180046533  call    cs:__imp_ISO8601StringToSystemTime
0x18004653a  nop     dword ptr [rax+rax+00h]
0x18004653f  mov     ebx, eax
0x180046541  test    eax, eax
0x180046543  jns     short loc_18004654C
0x180046545  mov     edx, 2EFh
0x18004654a  jmp     short loc_1800464FA
0x18004654c  xor     r9d, r9d; lpFormat
0x18004654f  mov     [rsp+4A0h+lpCalendar], r14; lpCalendar
0x180046554  lea     rax, [rsp+4A0h+DateStr]
0x180046559  mov     ebx, 104h
0x18004655e  mov     [rsp+4A0h+cchDate], ebx; cchDate
0x180046562  lea     r8, [rsp+4A0h+Date]; lpDate
0x180046567  xor     ecx, ecx; lpLocaleName
0x180046569  mov     [rsp+4A0h+lpDateStr], rax; lpDateStr
0x18004656e  lea     edx, [r9+40h]; dwFlags
0x180046572  call    cs:__imp_GetDateFormatEx
0x180046579  nop     dword ptr [rax+rax+00h]
0x18004657e  test    eax, eax
0x180046580  jnz     short loc_1800465AF
0x180046582  call    cs:__imp_GetLastError
0x180046589  nop     dword ptr [rax+rax+00h]
0x18004658e  mov     ebx, eax
0x180046590  test    eax, eax
0x180046592  jle     short loc_18004659D
0x180046594  movzx   ebx, ax
0x180046597  or      ebx, 80070000h
0x18004659d  test    ebx, ebx
0x18004659f  jns     loc_180046510
0x1800465a5  mov     edx, 2F0h
0x1800465aa  jmp     loc_1800464FA
0x1800465af  lea     rax, [rbp+3A0h+TimeStr]
0x1800465b6  mov     [rsp+4A0h+cchDate], ebx; cchTime
0x1800465ba  xor     r9d, r9d; lpFormat
0x1800465bd  mov     [rsp+4A0h+lpDateStr], rax; unsigned int
0x1800465c2  lea     r8, [rsp+4A0h+Date]; lpTime
0x1800465c7  xor     edx, edx; dwFlags
0x1800465c9  xor     ecx, ecx; lpLocaleName
0x1800465cb  call    cs:__imp_GetTimeFormatEx
0x1800465d2  nop     dword ptr [rax+rax+00h]
0x1800465d7  test    eax, eax
0x1800465d9  jnz     short loc_180046608
0x1800465db  call    cs:__imp_GetLastError
0x1800465e2  nop     dword ptr [rax+rax+00h]
0x1800465e7  mov     ebx, eax
0x1800465e9  test    eax, eax
0x1800465eb  jle     short loc_1800465F6
0x1800465ed  movzx   ebx, ax
0x1800465f0  or      ebx, 80070000h
0x1800465f6  test    ebx, ebx
0x1800465f8  jns     loc_180046510
0x1800465fe  mov     edx, 2F1h
0x180046603  jmp     loc_1800464FA
0x180046608  lea     r8, asc_18005ECBC; " "
0x18004660f  mov     rdx, rbx
0x180046612  lea     rcx, [rsp+4A0h+DateStr]
0x180046617  call    cs:__imp__o_wcscat_s
0x18004661e  nop     dword ptr [rax+rax+00h]
0x180046623  test    eax, eax
0x180046625  jz      short loc_180046647
0x180046627  mov     edx, 2F2h; void *
0x18004662c  mov     rcx, [rbp+3A8h]; this
0x180046633  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004663a  mov     r9d, eax; char *
0x18004663d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180046642  jmp     loc_180046737
0x180046647  lea     r8, [rbp+3A0h+TimeStr]
0x18004664e  mov     rdx, rbx
0x180046651  lea     rcx, [rsp+4A0h+DateStr]
0x180046656  call    cs:__imp__o_wcscat_s
0x18004665d  nop     dword ptr [rax+rax+00h]
0x180046662  test    eax, eax
0x180046664  jz      short loc_18004666D
0x180046666  mov     edx, 2F3h
0x18004666b  jmp     short loc_18004662C
0x18004666d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc>::GetImpl(void)'::`2'::impl
0x180046674  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DeviceManagementSettingUxUtc>::__private_IsEnabled(void)
0x180046679  test    al, al
0x18004667b  jz      short loc_1800466A8
0x18004667d  test    dil, dil
0x180046680  jz      short loc_1800466A8
0x180046682  lea     r8, aUtc; " UTC"
0x180046689  mov     rdx, rbx
0x18004668c  lea     rcx, [rsp+4A0h+DateStr]
0x180046691  call    cs:__imp__o_wcscat_s
0x180046698  nop     dword ptr [rax+rax+00h]
0x18004669d  test    eax, eax
0x18004669f  jz      short loc_1800466A8
0x1800466a1  mov     edx, 2F8h
0x1800466a6  jmp     short loc_18004662C
0x1800466a8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800466ac  lea     rax, [rsp+4A0h+DateStr]
0x1800466b1  mov     rbx, rdi
0x1800466b4  inc     rbx
0x1800466b7  cmp     [rax+rbx*2], r14w
0x1800466bc  jnz     short loc_1800466B4
0x1800466be  lea     rbx, ds:2[rbx*2]
0x1800466c6  call    cs:__imp_GetProcessHeap
0x1800466cd  nop     dword ptr [rax+rax+00h]
0x1800466d2  mov     r8, rbx; dwBytes
0x1800466d5  mov     edx, 8; dwFlags
0x1800466da  mov     rcx, rax; hHeap
0x1800466dd  call    cs:__imp_HeapAlloc
0x1800466e4  nop     dword ptr [rax+rax+00h]
0x1800466e9  mov     [rsi], rax
0x1800466ec  test    rax, rax
0x1800466ef  jnz     short loc_180046700
0x1800466f1  mov     ebx, 8007000Eh
0x1800466f6  mov     edx, 2FCh
0x1800466fb  jmp     loc_1800464FA
0x180046700  lea     rcx, [rsp+4A0h+DateStr]
0x180046705  inc     rdi
0x180046708  cmp     [rcx+rdi*2], r14w
0x18004670d  jnz     short loc_180046705
0x18004670f  lea     rdx, [rdi+1]
0x180046713  mov     rcx, rax
0x180046716  lea     r8, [rsp+4A0h+DateStr]
0x18004671b  call    cs:__imp__o_wcscpy_s
0x180046722  nop     dword ptr [rax+rax+00h]
0x180046727  test    eax, eax
0x180046729  jz      short loc_180046735
0x18004672b  mov     edx, 2FDh
0x180046730  jmp     loc_18004662C
0x180046735  xor     eax, eax
0x180046737  mov     rcx, [rbp+3A0h+var_20]
0x18004673e  xor     rcx, rsp; StackCookie
0x180046741  call    __security_check_cookie
0x180046746  lea     r11, [rsp+4A0h+var_10]
0x18004674e  mov     rbx, [r11+28h]
0x180046752  mov     rsi, [r11+38h]
0x180046756  mov     rsp, r11
0x180046759  pop     r14
0x18004675b  pop     rdi
0x18004675c  pop     rbp
0x18004675d  retn
```

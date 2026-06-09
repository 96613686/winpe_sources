# IsLastRenewRecent(ushort const *,int *)

- ea: `0x140030410`
- end: `0x14003095e`
- name: `?IsLastRenewRecent@@YAJPEBGPEAH@Z`
- size: `1358`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002c1b0`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x140009fc4`
- `0x14000a0fc`
- `0x14001d938`
- `0x140030410`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140030455`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140030455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003058a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400306ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003074d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400307ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003058a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400306ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003074d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400307ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003059d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003059d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003064f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003064f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400305c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400305c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400304e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030574`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003068a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400306c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400307c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400308d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030927`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400304e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030574`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030595`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003068a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400306c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400307c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400308d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030927`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14003072f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14003072f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1400306a4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140030743`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1400306a4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140030743`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400307a2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400307a2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003077e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003077e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsLastRenewRecent(const unsigned __int16 *a1, int *a2)
{
  __int64 v4; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // r8
  wchar_t v9; // ax
  unsigned int v10; // ebx
  WCHAR *v11; // rcx
  int v13; // eax
  int v14; // eax
  DWORD LastError; // ebx
  LSTATUS v16; // eax
  LSTATUS ValueW; // eax
  signed int v18; // eax
  FILETIME v19; // rdx
  signed int v20; // eax
  signed int v21; // eax
  int v22; // esi
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int16 *v25; // r9
  unsigned __int16 *v26; // r8
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  PVOID pvDataa; // [rsp+28h] [rbp-D8h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  LPDWORD pcbDataa; // [rsp+30h] [rbp-D0h]
  __int64 v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME v38; // [rsp+58h] [rbp-A8h]
  DWORD v39; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  FILETIME FileTime2; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME v43; // [rsp+80h] [rbp-80h] BYREF
  SYSTEMTIME v44; // [rsp+90h] [rbp-70h] BYREF
  SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[80]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v47[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v48[264]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  hKey = 0;
  v4 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v6 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v6 = &::SubKey;
  v7 = 80;
  v8 = SubKey;
  do
  {
    if ( !v4 )
      break;
    v9 = *v6;
    if ( !*v6 )
      break;
    ++v6;
    *v8++ = v9;
    --v4;
    --v7;
  }
  while ( v7 );
  v10 = v7 == 0 ? 0x8007007A : 0;
  v11 = v8 - 1;
  if ( v7 )
    v11 = v8;
  *v11 = 0;
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1275,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)v10,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  v13 = StringCchCatW(SubKey, 0x50u, c_szEnrollmentsDB);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1278,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v13,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  v14 = StringCchCatW(SubKey, 0x50u, a1);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v14,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v10 = v16;
  if ( v16 > 0 )
    v10 = (unsigned __int16)v16 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)v10,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  SystemTime = 0;
  v39 = 16;
  ValueW = RegGetValueW(hKey, &::SubKey, L"RenewTimeStamp", 8u, 0, &SystemTime, &v39);
  v10 = ValueW;
  if ( ValueW > 0 )
    v10 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)v10,
      (int)phkResultb);
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v18 = GetLastError();
    v10 = v18;
    if ( v18 > 0 )
      v10 = (unsigned __int16)v18 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  v38 = FileTime;
  *(_QWORD *)&v43.wYear = 0;
  if ( is_mul_ok(0xA8C0u, 0x989680u) )
  {
    v19 = (FILETIME)(*(_QWORD *)&v38 + 432000000000LL);
    if ( *(_QWORD *)&v38 + 432000000000LL >= *(unsigned __int64 *)&v38 )
    {
      *(_QWORD *)&v38 += 432000000000LL;
      FileTime2 = v19;
      v44 = 0;
      GetSystemTime(&v44);
      FileTime1 = 0;
      if ( !SystemTimeToFileTime(&v44, &FileTime1) )
      {
        v20 = GetLastError();
        v10 = v20;
        if ( v20 > 0 )
          v10 = (unsigned __int16)v20 | 0x80070000;
        if ( hKey )
          RegCloseKey(hKey);
        return v10;
      }
      if ( CompareFileTime(&FileTime1, &FileTime2) >= 0 )
      {
        *a2 = 0;
        goto LABEL_64;
      }
      *a2 = 1;
      v43 = 0;
      if ( !FileTimeToSystemTime(&FileTime2, &v43) )
      {
        v21 = GetLastError();
        v10 = v21;
        if ( v21 > 0 )
          v10 = (unsigned __int16)v21 | 0x80070000;
        if ( hKey )
          RegCloseKey(hKey);
        return v10;
      }
      memset_0(v48, 0, 0x208u);
      memset_0(v47, 0, 0x208u);
      LODWORD(pcbData) = v44.wHour;
      LODWORD(pvData) = v44.wDay;
      LODWORD(phkResultb) = v44.wMonth;
      v22 = StringCchPrintfW(
              v48,
              0x104u,
              L"%4d-%02d-%02dT%2d:%02d:%02d",
              v44.wYear,
              phkResultb,
              pvData,
              pcbData,
              v44.wMinute,
              v44.wSecond);
      LODWORD(v36) = v43.wSecond;
      LODWORD(v35) = v43.wMinute;
      LODWORD(pcbDataa) = v43.wHour;
      LODWORD(pvDataa) = v43.wDay;
      LODWORD(phkResultc) = v43.wMonth;
      v23 = StringCchPrintfW(
              v47,
              0x104u,
              L"%4d-%02d-%02dT%2d:%02d:%02d",
              v43.wYear,
              phkResultc,
              pvDataa,
              pcbDataa,
              v35,
              v36);
      if ( v22 < 0 || v23 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          v25 = (unsigned __int16 *)&::SubKey;
          v26 = (unsigned __int16 *)&::SubKey;
          goto LABEL_62;
        }
      }
      else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v25 = v47;
        v26 = v48;
LABEL_62:
        McTemplateU0zz_EventWriteTransfer(v24, EnterpriseDiagnosticsEnrollLastRenewIsRecent, v26, v25);
      }
LABEL_64:
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)0x80070216LL,
      (int)phkResultb);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)0x80070216LL,
      (int)phkResultb);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942934LL;
}

```

## disassembly

```asm
0x140030410  mov     [rsp-8+arg_10], rbx
0x140030415  mov     [rsp-8+arg_18], rsi
0x14003041a  push    rbp
0x14003041b  push    rdi
0x14003041c  push    r12
0x14003041e  push    r14
0x140030420  push    r15
0x140030422  lea     rbp, [rsp-480h]
0x14003042a  sub     rsp, 580h
0x140030431  mov     rax, cs:__security_cookie
0x140030438  xor     rax, rsp
0x14003043b  mov     [rbp+4A0h+var_30], rax
0x140030442  mov     rsi, rdx
0x140030445  mov     rdi, rcx
0x140030448  xor     r15d, r15d
0x14003044b  mov     [rsp+5A0h+hKey], r15
0x140030450  mov     ebx, 7FFFFFFEh
0x140030455  call    cs:__imp_RtlIsStateSeparationEnabled
0x14003045b  lea     r12, SubKey
0x140030462  lea     rcx, aOsdata; "OSData\\"
0x140030469  test    al, al
0x14003046b  cmovz   rcx, r12
0x14003046f  lea     r14d, [r15+50h]
0x140030473  mov     edx, r14d
0x140030476  lea     r8, [rbp+4A0h+SubKey]
0x14003047a  test    rbx, rbx
0x14003047d  jz      short loc_14003049C
0x14003047f  movzx   eax, word ptr [rcx]
0x140030482  test    ax, ax
0x140030485  jz      short loc_14003049C
0x140030487  add     rcx, 2
0x14003048b  mov     [r8], ax
0x14003048f  add     r8, 2
0x140030493  dec     rbx
0x140030496  sub     rdx, 1
0x14003049a  jnz     short loc_14003047A
0x14003049c  mov     rax, rdx
0x14003049f  neg     rax
0x1400304a2  sbb     ebx, ebx
0x1400304a4  not     ebx
0x1400304a6  and     ebx, 8007007Ah
0x1400304ac  lea     rcx, [r8-2]
0x1400304b0  test    rdx, rdx
0x1400304b3  cmovnz  rcx, r8
0x1400304b7  mov     [rcx], r15w
0x1400304bb  jnz     short loc_1400304F1
0x1400304bd  mov     rcx, [rbp+4A8h]; this
0x1400304c4  mov     r9d, ebx; char *
0x1400304c7  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400304ce  mov     edx, 1275h; void *
0x1400304d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400304d8  nop
0x1400304d9  mov     rcx, [rsp+5A0h+hKey]; hKey
0x1400304de  test    rcx, rcx
0x1400304e1  jz      short loc_1400304EA
0x1400304e3  call    cs:__imp_RegCloseKey
0x1400304e9  nop
0x1400304ea  mov     eax, ebx
0x1400304ec  jmp     loc_140030933
0x1400304f1  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x1400304f8  mov     rdx, r14; unsigned __int64
0x1400304fb  lea     rcx, [rbp+4A0h+SubKey]; unsigned __int16 *
0x1400304ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140030504  mov     ebx, eax
0x140030506  test    eax, eax
0x140030508  jns     short loc_140030539
0x14003050a  mov     rcx, [rbp+4A8h]; this
0x140030511  mov     r9d, eax; char *
0x140030514  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14003051b  mov     edx, 1278h; void *
0x140030520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030525  nop
0x140030526  mov     rcx, [rsp+5A0h+hKey]; hKey
0x14003052b  test    rcx, rcx
0x14003052e  jz      short loc_140030537
0x140030530  call    cs:__imp_RegCloseKey
0x140030536  nop
0x140030537  jmp     short loc_1400304EA
0x140030539  mov     r8, rdi; unsigned __int16 *
0x14003053c  mov     rdx, r14; unsigned __int64
0x14003053f  lea     rcx, [rbp+4A0h+SubKey]; unsigned __int16 *
0x140030543  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140030548  mov     ebx, eax
0x14003054a  test    eax, eax
0x14003054c  jns     short loc_140030580
0x14003054e  mov     rcx, [rbp+4A8h]; this
0x140030555  mov     r9d, eax; char *
0x140030558  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14003055f  mov     edx, 127Bh; void *
0x140030564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030569  nop
0x14003056a  mov     rcx, [rsp+5A0h+hKey]; hKey
0x14003056f  test    rcx, rcx
0x140030572  jz      short loc_14003057B
0x140030574  call    cs:__imp_RegCloseKey
0x14003057a  nop
0x14003057b  jmp     loc_1400304EA
0x140030580  mov     rdi, [rsp+5A0h+hKey]
0x140030585  test    rdi, rdi
0x140030588  jz      short loc_1400305A4
0x14003058a  call    cs:__imp_GetLastError
0x140030590  mov     ebx, eax
0x140030592  mov     rcx, rdi; hKey
0x140030595  call    cs:__imp_RegCloseKey
0x14003059b  mov     ecx, ebx; dwErrCode
0x14003059d  call    cs:__imp_SetLastError
0x1400305a3  nop
0x1400305a4  mov     [rsp+5A0h+hKey], r15
0x1400305a9  lea     rax, [rsp+5A0h+hKey]
0x1400305ae  mov     [rsp+5A0h+phkResult], rax; int
0x1400305b3  mov     r9d, 20019h; samDesired
0x1400305b9  xor     r8d, r8d; ulOptions
0x1400305bc  lea     rdx, [rbp+4A0h+SubKey]; lpSubKey
0x1400305c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400305c7  call    cs:__imp_RegOpenKeyExW
0x1400305cd  mov     ebx, eax
0x1400305cf  mov     edi, 80070000h
0x1400305d4  test    eax, eax
0x1400305d6  jle     short loc_1400305DD
0x1400305d8  movzx   ebx, ax
0x1400305db  or      ebx, edi
0x1400305dd  test    ebx, ebx
0x1400305df  jns     short loc_140030613
0x1400305e1  mov     rcx, [rbp+4A8h]; this
0x1400305e8  mov     r9d, ebx; char *
0x1400305eb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400305f2  mov     edx, 127Eh; void *
0x1400305f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400305fc  nop
0x1400305fd  mov     rcx, [rsp+5A0h+hKey]; hKey
0x140030602  test    rcx, rcx
0x140030605  jz      short loc_14003060E
0x140030607  call    cs:__imp_RegCloseKey
0x14003060d  nop
0x14003060e  jmp     loc_1400304EA
0x140030613  xorps   xmm0, xmm0
0x140030616  movups  xmmword ptr [rbp+4A0h+SystemTime.wYear], xmm0
0x14003061a  mov     [rsp+5A0h+var_540], 10h
0x140030622  lea     rax, [rsp+5A0h+var_540]
0x140030627  mov     [rsp+5A0h+pcbData], rax; pcbData
0x14003062c  lea     rax, [rbp+4A0h+SystemTime]
0x140030630  mov     [rsp+5A0h+pvData], rax; pvData
0x140030635  mov     [rsp+5A0h+phkResult], r15; int
0x14003063a  mov     r9d, 8; dwFlags
0x140030640  lea     r8, aRenewtimestamp; "RenewTimeStamp"
0x140030647  mov     rdx, r12; lpSubKey
0x14003064a  mov     rcx, [rsp+5A0h+hKey]; hkey
0x14003064f  call    cs:__imp_RegGetValueW
0x140030655  mov     ebx, eax
0x140030657  test    eax, eax
0x140030659  jle     short loc_140030660
0x14003065b  movzx   ebx, ax
0x14003065e  or      ebx, edi
0x140030660  test    ebx, ebx
0x140030662  jns     short loc_140030696
0x140030664  mov     rcx, [rbp+4A8h]; this
0x14003066b  mov     r9d, ebx; char *
0x14003066e  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140030675  mov     edx, 128Ch; void *
0x14003067a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003067f  nop
0x140030680  mov     rcx, [rsp+5A0h+hKey]; hKey
0x140030685  test    rcx, rcx
0x140030688  jz      short loc_140030691
0x14003068a  call    cs:__imp_RegCloseKey
0x140030690  nop
0x140030691  jmp     loc_1400304EA
0x140030696  mov     qword ptr [rsp+5A0h+FileTime.dwLowDateTime], r15
0x14003069b  lea     rdx, [rsp+5A0h+FileTime]; lpFileTime
0x1400306a0  lea     rcx, [rbp+4A0h+SystemTime]; lpSystemTime
0x1400306a4  call    cs:__imp_SystemTimeToFileTime
0x1400306aa  test    eax, eax
0x1400306ac  jnz     short loc_1400306D5
0x1400306ae  call    cs:__imp_GetLastError
0x1400306b4  mov     ebx, eax
0x1400306b6  test    eax, eax
0x1400306b8  jle     short loc_1400306BF
0x1400306ba  movzx   ebx, ax
0x1400306bd  or      ebx, edi
0x1400306bf  mov     rcx, [rsp+5A0h+hKey]; hKey
0x1400306c4  test    rcx, rcx
0x1400306c7  jz      short loc_1400306D0
0x1400306c9  call    cs:__imp_RegCloseKey
0x1400306cf  nop
0x1400306d0  jmp     loc_1400304EA
0x1400306d5  mov     eax, [rsp+5A0h+FileTime.dwHighDateTime]
0x1400306d9  mov     dword ptr [rsp+5A0h+var_548+4], eax
0x1400306dd  mov     eax, [rsp+5A0h+FileTime.dwLowDateTime]
0x1400306e1  mov     dword ptr [rsp+5A0h+var_548], eax
0x1400306e5  mov     qword ptr [rbp+4A0h+var_520.wYear], r15
0x1400306e9  mov     ecx, 0A8C0h
0x1400306ee  mov     eax, 989680h
0x1400306f3  mul     rcx
0x1400306f6  test    rdx, rdx
0x1400306f9  jnz     loc_1400308FE
0x1400306ff  mov     rcx, [rsp+5A0h+var_548]
0x140030704  lea     rdx, [rax+rcx]
0x140030708  cmp     rdx, rcx
0x14003070b  jb      loc_1400308DD
0x140030711  mov     [rsp+5A0h+var_548], rdx
0x140030716  mov     eax, dword ptr [rsp+5A0h+var_548+4]
0x14003071a  mov     [rsp+5A0h+FileTime2.dwHighDateTime], eax
0x14003071e  mov     eax, edx
0x140030720  mov     [rsp+5A0h+FileTime2.dwLowDateTime], edx
0x140030724  xorps   xmm0, xmm0
0x140030727  movups  xmmword ptr [rbp+4A0h+var_510.wYear], xmm0
0x14003072b  lea     rcx, [rbp+4A0h+var_510]; lpSystemTime
0x14003072f  call    cs:__imp_GetSystemTime
0x140030735  mov     qword ptr [rsp+5A0h+FileTime1.dwLowDateTime], r15
0x14003073a  lea     rdx, [rsp+5A0h+FileTime1]; lpFileTime
0x14003073f  lea     rcx, [rbp+4A0h+var_510]; lpSystemTime
0x140030743  call    cs:__imp_SystemTimeToFileTime
0x140030749  test    eax, eax
0x14003074b  jnz     short loc_140030774
0x14003074d  call    cs:__imp_GetLastError
0x140030753  mov     ebx, eax
0x140030755  test    eax, eax
0x140030757  jle     short loc_14003075E
0x140030759  movzx   ebx, ax
0x14003075c  or      ebx, edi
0x14003075e  mov     rcx, [rsp+5A0h+hKey]; hKey
0x140030763  test    rcx, rcx
0x140030766  jz      short loc_14003076F
0x140030768  call    cs:__imp_RegCloseKey
0x14003076e  nop
0x14003076f  jmp     loc_1400304EA
0x140030774  lea     rdx, [rsp+5A0h+FileTime2]; lpFileTime2
0x140030779  lea     rcx, [rsp+5A0h+FileTime1]; lpFileTime1
0x14003077e  call    cs:__imp_CompareFileTime
0x140030784  test    eax, eax
0x140030786  jns     loc_1400308C5
0x14003078c  mov     dword ptr [rsi], 1
0x140030792  xorps   xmm0, xmm0
0x140030795  movups  xmmword ptr [rbp+4A0h+var_520.wYear], xmm0
0x140030799  lea     rdx, [rbp+4A0h+var_520]; lpSystemTime
0x14003079d  lea     rcx, [rsp+5A0h+FileTime2]; lpFileTime
0x1400307a2  call    cs:__imp_FileTimeToSystemTime
0x1400307a8  test    eax, eax
0x1400307aa  jnz     short loc_1400307D3
0x1400307ac  call    cs:__imp_GetLastError
0x1400307b2  mov     ebx, eax
0x1400307b4  test    eax, eax
0x1400307b6  jle     short loc_1400307BD
0x1400307b8  movzx   ebx, ax
0x1400307bb  or      ebx, edi
0x1400307bd  mov     rcx, [rsp+5A0h+hKey]; hKey
0x1400307c2  test    rcx, rcx
0x1400307c5  jz      short loc_1400307CE
0x1400307c7  call    cs:__imp_RegCloseKey
0x1400307cd  nop
0x1400307ce  jmp     loc_1400304EA
0x1400307d3  mov     ebx, 208h
0x1400307d8  mov     r8d, ebx; Size
0x1400307db  xor     edx, edx; Val
0x1400307dd  lea     rcx, [rbp+4A0h+var_240]; void *
0x1400307e4  call    memset_0
0x1400307e9  mov     r8d, ebx; Size
0x1400307ec  xor     edx, edx; Val
0x1400307ee  lea     rcx, [rbp+4A0h+var_450]; void *
0x1400307f2  call    memset_0
0x1400307f7  movzx   eax, [rbp+4A0h+var_510.wSecond]
0x1400307fb  movzx   ecx, [rbp+4A0h+var_510.wMinute]
0x1400307ff  movzx   edx, [rbp+4A0h+var_510.wHour]
0x140030803  movzx   r8d, [rbp+4A0h+var_510.wDay]
0x140030808  movzx   r10d, [rbp+4A0h+var_510.wMonth]
0x14003080d  movzx   r9d, [rbp+4A0h+var_510.wYear]
0x140030812  mov     [rsp+5A0h+var_560], eax
0x140030816  mov     dword ptr [rsp+5A0h+var_568], ecx
0x14003081a  mov     dword ptr [rsp+5A0h+pcbData], edx
0x14003081e  mov     dword ptr [rsp+5A0h+pvData], r8d
0x140030823  mov     dword ptr [rsp+5A0h+phkResult], r10d
0x140030828  lea     r8, a4d02d02dt2d02d; "%4d-%02d-%02dT%2d:%02d:%02d"
0x14003082f  mov     r14d, 104h
0x140030835  mov     edx, r14d; unsigned __int64
0x140030838  lea     rcx, [rbp+4A0h+var_240]; unsigned __int16 *
0x14003083f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030844  mov     esi, eax
0x140030846  movzx   ecx, [rbp+4A0h+var_520.wSecond]
0x14003084a  movzx   r10d, [rbp+4A0h+var_520.wMinute]
0x14003084f  movzx   r11d, [rbp+4A0h+var_520.wHour]
0x140030854  movzx   ebx, [rbp+4A0h+var_520.wDay]
0x140030858  movzx   edi, [rbp+4A0h+var_520.wMonth]
0x14003085c  movzx   r9d, [rbp+4A0h+var_520.wYear]
0x140030861  mov     [rsp+5A0h+var_560], ecx
0x140030865  mov     dword ptr [rsp+5A0h+var_568], r10d
0x14003086a  mov     dword ptr [rsp+5A0h+pcbData], r11d
0x14003086f  mov     dword ptr [rsp+5A0h+pvData], ebx
0x140030873  mov     dword ptr [rsp+5A0h+phkResult], edi
0x140030877  lea     r8, a4d02d02dt2d02d; "%4d-%02d-%02dT%2d:%02d:%02d"
0x14003087e  mov     edx, r14d; unsigned __int64
0x140030881  lea     rcx, [rbp+4A0h+var_450]; unsigned __int16 *
0x140030885  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003088a  test    esi, esi
0x14003088c  js      short loc_1400308A8
0x14003088e  test    eax, eax
0x140030890  js      short loc_1400308A8
0x140030892  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x140030899  jz      short loc_1400308C8
0x14003089b  lea     r9, [rbp+4A0h+var_450]
0x14003089f  lea     r8, [rbp+4A0h+var_240]
  ... truncated ...
```

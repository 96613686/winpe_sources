# Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties(Windows::Compat::Appraiser::PropertyBag &)

- ea: `0x1800530f4`
- end: `0x180053615`
- name: `?AppendArbitraryConfigurationRegkeyProperties@TelemetryScheduler@Appraiser@Compat@Windows@@CAJAEAVPropertyBag@234@@Z`
- size: `1313`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::PropertyBag *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053e24`

## callees

- `0x180008570`
- `0x180011d94`
- `0x180013f90`
- `0x18001a558`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800530f4`
- `0x180068908`
- `0x1800a5d88`
- `0x1802174d8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180053140`
- `KERNEL32!GetProcessHeap` at `0x180053153`
- `KERNEL32!GetProcessHeap` at `0x180053140`
- `KERNEL32!GetProcessHeap` at `0x180053153`
- `KERNEL32!HeapFree` at `0x180053598`
- `KERNEL32!HeapFree` at `0x180053598`
- `ADVAPI32!RegEnumValueW` at `0x180053257`
- `ADVAPI32!RegEnumValueW` at `0x18005344f`
- `ADVAPI32!RegEnumValueW` at `0x180053257`
- `ADVAPI32!RegEnumValueW` at `0x18005344f`
- `ADVAPI32!RegCloseKey` at `0x180053577`
- `ADVAPI32!RegCloseKey` at `0x180053577`
- `ADVAPI32!RegOpenKeyExW` at `0x1800531a5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800531a5`

## string_xrefs

- `0x1800531e6`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryscheduler.cpp`
- `0x180053269`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryscheduler.cpp`
- `0x1800531d8`: `Error reading arbitrary settings from registry: [%d].`
- `0x1800532e0`: `TelemetryConfig_`
- `0x18005336a`: `Duplicate arbitrary config value, named %ls. Ignoring the second.`
- `0x1800531df`: `Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties`
- `0x180053262`: `Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties`
- `0x1800532a8`: `Failed to extract an arbitrary config value from registry: [%d].`
- `0x1800534c8`: `Failed to apply prefix to arbitrary config property: [0x%x].`
- `0x1800535fd`: `Failed to apply prefix to arbitrary config property: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties(
        struct Windows::Compat::Appraiser::PropertyBag *a1)
{
  char *v1; // r13
  unsigned __int64 v2; // rsi
  LSTATUS v3; // eax
  signed int appended; // ebx
  const char *v5; // rax
  char v6; // dl
  LSTATUS v7; // eax
  unsigned __int64 v8; // r14
  unsigned int v9; // esi
  const unsigned __int16 *v10; // rdx
  __int16 v11; // r10
  unsigned __int64 v12; // r8
  char *v13; // rcx
  unsigned __int64 v14; // rax
  char *v15; // rax
  __int64 v16; // r9
  int v17; // ecx
  int v18; // eax
  unsigned __int64 v19; // rsi
  char *v20; // r9
  __int64 v21; // rax
  char *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  const char *phkResult; // [rsp+20h] [rbp-E0h]
  const char *lpData; // [rsp+30h] [rbp-D0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v31; // [rsp+4Ch] [rbp-B4h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hHeap[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34[2]; // [rsp+68h] [rbp-98h]
  LPVOID lpMem[3]; // [rsp+78h] [rbp-88h]
  Windows::Compat::Appraiser::PropertyBag *v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  WCHAR ValueName[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v39[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 Data[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v41[272]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v37 = -2;
  v36 = a1;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  GetProcessHeap();
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  *(_OWORD *)v34 = 0;
  v1 = 0;
  lpMem[1] = 0;
  v2 = 8;
  hHeap[1] = (HANDLE)8;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiserConfiguration,
         0,
         0x20019u,
         &hKey);
  if ( !v3 )
  {
    v31 = 0;
    cchValueName = 260;
    cbData = 520;
    v7 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    v8 = v34[0];
    while ( 1 )
    {
      if ( v7 == 259 )
      {
        v19 = 0;
        if ( !v8 )
        {
LABEL_58:
          appended = 0;
          goto LABEL_59;
        }
        while ( 1 )
        {
          v20 = 0;
          if ( v19 < v8 )
          {
            v21 = (unsigned __int64)hHeap[1] * v19;
            if ( !is_mul_ok((unsigned __int64)hHeap[1], v19) || (v20 = &v1[v21], &v1[v21] < v1) )
              v20 = 0;
          }
          appended = StringCchPrintfW(v41, 0x10Cu, L"ARBTEL_%ls", *(_QWORD *)v20);
          if ( appended < 0 )
            break;
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x28Bu,
              "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
              "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
              "Failed to apply prefix to arbitrary config property: [0x%x].",
              appended);
          v22 = 0;
          if ( v19 < v8 )
          {
            if ( !is_mul_ok((unsigned __int64)hHeap[1], v19) || (v22 = &v1[(unsigned __int64)hHeap[1] * v19], v22 < v1) )
              v22 = 0;
          }
          v23 = *(_QWORD *)v22;
          v24 = -1;
          do
            ++v24;
          while ( *(_WORD *)(v23 + 2 * v24) );
          appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                       v36,
                       v41,
                       (const unsigned __int16 *)(v23 + 2 * (v24 + 1)));
          if ( appended < 0 )
          {
            LODWORD(lpData) = appended;
            v5 = "Error adding init property to bag: [0x%x].";
            v6 = -114;
            goto LABEL_7;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x28Eu,
              "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
              "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
              "Error adding init property to bag: [0x%x].",
              appended);
          if ( ++v19 >= v8 )
            goto LABEL_58;
        }
        LODWORD(lpData) = appended;
        v5 = "Failed to apply prefix to arbitrary config property: [0x%x].";
        v6 = -117;
LABEL_7:
        LODWORD(phkResult) = appended;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v6,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
          "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
          phkResult,
          (int)v5,
          lpData);
        goto LABEL_59;
      }
      if ( v7 )
        break;
      if ( Type == 1 && !wcsncmp_0(ValueName, L"TelemetryConfig_", 0x10u) )
      {
        v11 = *(_WORD *)v39;
        if ( *(_WORD *)v39 )
        {
          v12 = 0;
          if ( v8 )
          {
            while ( 1 )
            {
              v13 = 0;
              if ( v12 < v8 )
              {
                v14 = v2 * v12;
                if ( !is_mul_ok(v2, v12) || (v13 = &v1[v14], &v1[v14] < v1) )
                  v13 = 0;
              }
              v15 = v39;
              v16 = *(_QWORD *)v13 - (_QWORD)v39;
              do
              {
                v17 = *(unsigned __int16 *)&v15[v16];
                v10 = (const unsigned __int16 *)((unsigned int)*(unsigned __int16 *)v15 - v17);
                if ( (_DWORD)v10 )
                  break;
                v15 += 2;
              }
              while ( v17 );
              if ( !(_DWORD)v10 )
                break;
              if ( ++v12 >= v8 )
                goto LABEL_32;
            }
            LODWORD(phkResult) = -2147024809;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              108,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
              "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
              phkResult,
              (int)"Duplicate arbitrary config value, named %ls. Ignoring the second.",
              v39);
            v11 = 0;
            *(_WORD *)v39 = 0;
          }
LABEL_32:
          if ( v11 )
          {
            v18 = RtlNameValueArray::Insert((RtlNameValueArray *)hHeap, v10, (const unsigned __int16 *)v39, Data, v8);
            appended = v18;
            if ( v18 < 0 )
            {
              LODWORD(lpData) = v18;
              v5 = "Failed to append name/value pair: [0x%x].";
              v6 = 126;
              goto LABEL_7;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x27Eu,
                "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
                "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
                "Failed to append name/value pair: [0x%x].",
                v18);
            v8 = v34[0];
            v1 = (char *)lpMem[1];
            goto LABEL_37;
          }
        }
      }
LABEL_38:
      ++v31;
      cchValueName = 260;
      cbData = 520;
      v7 = RegEnumValueW(hKey, v31, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    }
    if ( v7 > 0 )
      v9 = (unsigned __int16)v7 | 0x80070000;
    else
      v9 = v7;
    LODWORD(lpData) = v7;
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      LODWORD(phkResult) = v9;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        76,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
        phkResult,
        (int)"Failed to extract an arbitrary config value from registry: [%d].",
        lpData);
    }
    else
    {
      Windows::Compat::Appraiser::WriteLog(
        0,
        76,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties",
        0,
        (int)"Failed to extract an arbitrary config value from registry: [%d].",
        lpData);
    }
LABEL_37:
    v2 = (unsigned __int64)hHeap[1];
    goto LABEL_38;
  }
  if ( (unsigned int)(v3 - 2) > 1 )
  {
    if ( v3 > 0 )
      appended = (unsigned __int16)v3 | 0x80070000;
    else
      appended = v3;
    LODWORD(lpData) = v3;
    v5 = "Error reading arbitrary settings from registry: [%d].";
    v6 = 46;
    goto LABEL_7;
  }
  appended = 1;
LABEL_59:
  if ( hKey )
    RegCloseKey(hKey);
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800530f4  push    rbp
0x1800530f6  push    rbx
0x1800530f7  push    rsi
0x1800530f8  push    rdi
0x1800530f9  push    r12
0x1800530fb  push    r13
0x1800530fd  push    r14
0x1800530ff  push    r15
0x180053101  lea     rbp, [rsp-5F8h]
0x180053109  sub     rsp, 6F8h
0x180053110  mov     [rbp+630h+var_698], 0FFFFFFFFFFFFFFFEh
0x180053118  mov     rax, cs:__security_cookie
0x18005311f  xor     rax, rsp
0x180053122  mov     [rbp+630h+var_50], rax
0x180053129  mov     [rbp+630h+var_6A0], rcx
0x18005312d  xor     ebx, ebx
0x18005312f  mov     [rsp+730h+hKey], rbx
0x180053134  mov     [rsp+730h+cchValueName], ebx
0x180053138  mov     [rsp+730h+cbData], ebx
0x18005313c  mov     [rsp+730h+Type], ebx
0x180053140  call    cs:__imp_GetProcessHeap
0x180053146  xorps   xmm0, xmm0
0x180053149  movups  xmmword ptr [rsp+730h+hHeap], xmm0
0x18005314e  movups  xmmword ptr [rsp+730h+lpMem], xmm0
0x180053153  call    cs:__imp_GetProcessHeap
0x180053159  mov     [rsp+730h+hHeap], rax
0x18005315e  mov     [rsp+730h+lpMem], 10h
0x180053167  xorps   xmm0, xmm0
0x18005316a  movdqu  xmmword ptr [rsp+730h+var_6C8], xmm0
0x180053170  mov     r13d, ebx
0x180053173  mov     [rbp+630h+lpMem+8], rbx
0x180053177  lea     esi, [rbx+8]
0x18005317a  mov     [rsp+730h+hHeap+8], rsi
0x18005317f  mov     [rsp+730h+hKey], rbx
0x180053184  lea     rax, [rsp+730h+hKey]
0x180053189  mov     [rsp+730h+phkResult], rax; phkResult
0x18005318e  mov     r9d, 20019h; samDesired
0x180053194  xor     r8d, r8d; ulOptions
0x180053197  mov     rdx, cs:?RegistryPathAppraiserConfiguration@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; lpSubKey
0x18005319e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800531a5  call    cs:__imp_RegOpenKeyExW
0x1800531ab  test    eax, eax
0x1800531ad  jz      short loc_18005320E
0x1800531af  lea     ecx, [rax-2]
0x1800531b2  lea     edi, [rbx+1]
0x1800531b5  cmp     ecx, edi
0x1800531b7  jbe     short loc_180053207
0x1800531b9  test    eax, eax
0x1800531bb  jg      short loc_1800531C1
0x1800531bd  mov     ebx, eax
0x1800531bf  jmp     short loc_1800531CA
0x1800531c1  movzx   ebx, ax
0x1800531c4  or      ebx, 80070000h
0x1800531ca  mov     ecx, 80004005h
0x1800531cf  test    ebx, ebx
0x1800531d1  cmovns  ebx, ecx
0x1800531d4  mov     dword ptr [rsp+730h+lpData], eax; char *
0x1800531d8  lea     rax, aErrorReadingAr; "Error reading arbitrary settings from r"...
0x1800531df  lea     r9, aWindowsCompatA_368; "Windows::Compat::Appraiser::TelemetrySc"...
0x1800531e6  lea     r8, aOnecoreBaseApp_78; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800531ed  mov     edx, 22Eh; bool
0x1800531f2  mov     [rsp+730h+lpType], rax; int
0x1800531f7  mov     dword ptr [rsp+730h+phkResult], ebx; char *
0x1800531fb  mov     ecx, edi; this
0x1800531fd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180053202  jmp     loc_18005356D
0x180053207  mov     ebx, edi
0x180053209  jmp     loc_18005356D
0x18005320e  mov     [rsp+730h+var_6E4], ebx
0x180053212  mov     [rsp+730h+cchValueName], 104h
0x18005321a  mov     [rsp+730h+cbData], 208h
0x180053222  lea     rax, [rsp+730h+cbData]
0x180053227  mov     [rsp+730h+lpcbData], rax; lpcbData
0x18005322c  lea     rax, [rbp+630h+Data]
0x180053233  mov     [rsp+730h+lpData], rax; lpData
0x180053238  lea     rax, [rsp+730h+Type]
0x18005323d  mov     [rsp+730h+lpType], rax; lpType
0x180053242  mov     [rsp+730h+phkResult], rbx; lpReserved
0x180053247  lea     r9, [rsp+730h+cchValueName]; lpcchValueName
0x18005324c  lea     r8, [rbp+630h+ValueName]; lpValueName
0x180053250  xor     edx, edx; dwIndex
0x180053252  mov     rcx, [rsp+730h+hKey]; hKey
0x180053257  call    cs:__imp_RegEnumValueW
0x18005325d  mov     edi, 1
0x180053262  lea     r15, aWindowsCompatA_368; "Windows::Compat::Appraiser::TelemetrySc"...
0x180053269  lea     r12, aOnecoreBaseApp_78; "onecore\\base\\appcompat\\appraiser\\he"...
0x180053270  mov     r14, [rsp+730h+var_6C8]
0x180053275  jmp     loc_180053455
0x18005327a  xor     r11d, r11d
0x18005327d  test    ebx, ebx
0x18005327f  jz      short loc_1800532D0
0x180053281  jg      short loc_180053287
0x180053283  mov     esi, ebx
0x180053285  jmp     short loc_180053290
0x180053287  movzx   esi, bx
0x18005328a  or      esi, 80070000h
0x180053290  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x180053295  xor     ecx, ecx
0x180053297  mov     dword ptr [rsp+730h+lpData], ebx; char *
0x18005329b  mov     r9, r15; char *
0x18005329e  mov     r8, r12; unsigned int
0x1800532a1  mov     edx, 24Ch; bool
0x1800532a6  test    al, al
0x1800532a8  lea     rax, aFailedToExtrac_4; "Failed to extract an arbitrary config v"...
0x1800532af  mov     [rsp+730h+lpType], rax; int
0x1800532b4  jz      short loc_1800532C9
0x1800532b6  mov     dword ptr [rsp+730h+phkResult], esi; char *
0x1800532ba  mov     ecx, edi; this
0x1800532bc  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800532c1  xor     r11d, r11d
0x1800532c4  jmp     loc_1800533FB
0x1800532c9  mov     [rsp+730h+phkResult], rcx
0x1800532ce  jmp     short loc_1800532BC
0x1800532d0  cmp     [rsp+730h+Type], edi
0x1800532d4  jnz     loc_180053400
0x1800532da  mov     r8d, 10h; MaxCount
0x1800532e0  lea     rdx, aTelemetryconfi_0; "TelemetryConfig_"
0x1800532e7  lea     rcx, [rbp+630h+ValueName]; String1
0x1800532eb  call    wcsncmp_0
0x1800532f0  xor     r11d, r11d
0x1800532f3  test    eax, eax
0x1800532f5  jnz     loc_180053400
0x1800532fb  movzx   r10d, word ptr [rbp+630h+var_670]
0x180053300  cmp     r11w, r10w
0x180053304  jz      loc_180053400
0x18005330a  mov     r8d, r11d
0x18005330d  test    r14, r14
0x180053310  jz      loc_18005339B
0x180053316  mov     rcx, r11
0x180053319  cmp     r8, r14
0x18005331c  jnb     short loc_180053335
0x18005331e  mov     rax, r8
0x180053321  mul     rsi
0x180053324  test    rdx, rdx
0x180053327  jnz     short loc_180053332
0x180053329  lea     rcx, [rax+r13]
0x18005332d  cmp     rcx, r13
0x180053330  jnb     short loc_180053335
0x180053332  mov     rcx, r11
0x180053335  lea     rax, [rbp+630h+var_670]
0x180053339  mov     r9, [rcx]
0x18005333c  sub     r9, rax
0x18005333f  movzx   edx, word ptr [rax]
0x180053342  movzx   ecx, word ptr [rax+r9]
0x180053347  sub     edx, ecx
0x180053349  jnz     short loc_180053353
0x18005334b  add     rax, 2
0x18005334f  test    ecx, ecx
0x180053351  jnz     short loc_18005333F
0x180053353  test    edx, edx
0x180053355  jz      short loc_180053361
0x180053357  add     r8, rdi
0x18005335a  cmp     r8, r14
0x18005335d  jb      short loc_180053316
0x18005335f  jmp     short loc_18005339B
0x180053361  lea     rax, [rbp+630h+var_670]
0x180053365  mov     [rsp+730h+lpData], rax; char *
0x18005336a  lea     rax, aDuplicateArbit; "Duplicate arbitrary config value, named"...
0x180053371  mov     [rsp+730h+lpType], rax; int
0x180053376  mov     dword ptr [rsp+730h+phkResult], 80070057h; char *
0x18005337e  mov     r9, r15; char *
0x180053381  mov     r8, r12; unsigned int
0x180053384  mov     edx, 26Ch; bool
0x180053389  mov     ecx, edi; this
0x18005338b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180053390  xor     r11d, r11d
0x180053393  mov     r10d, r11d
0x180053396  mov     word ptr [rbp+630h+var_670], r11w
0x18005339b  cmp     r11w, r10w
0x18005339f  jz      short loc_180053400
0x1800533a1  mov     [rsp+730h+phkResult], r14; unsigned __int64
0x1800533a6  lea     r9, [rbp+630h+Data]; unsigned __int16 *
0x1800533ad  lea     r8, [rbp+630h+var_670]; unsigned __int16 *
0x1800533b1  lea     rcx, [rsp+730h+hHeap]; this
0x1800533b6  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800533bb  mov     ebx, eax
0x1800533bd  xor     r11d, r11d
0x1800533c0  test    eax, eax
0x1800533c2  js      loc_1800535C3
0x1800533c8  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800533ce  and     ecx, edi
0x1800533d0  test    cl, cl
0x1800533d2  jz      short loc_1800533F2
0x1800533d4  mov     dword ptr [rsp+730h+phkResult], eax
0x1800533d8  lea     r9, aFailedToAppend_93; "Failed to append name/value pair: [0x%x"...
0x1800533df  mov     r8, r15; char *
0x1800533e2  mov     rdx, r12; char *
0x1800533e5  mov     ecx, 27Eh; unsigned int
0x1800533ea  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800533ef  xor     r11d, r11d
0x1800533f2  mov     r14, [rsp+730h+var_6C8]
0x1800533f7  mov     r13, [rbp+630h+lpMem+8]
0x1800533fb  mov     rsi, [rsp+730h+hHeap+8]
0x180053400  mov     eax, [rsp+730h+var_6E4]
0x180053404  add     eax, edi
0x180053406  mov     [rsp+730h+var_6E4], eax
0x18005340a  mov     [rsp+730h+cchValueName], 104h
0x180053412  mov     [rsp+730h+cbData], 208h
0x18005341a  lea     rcx, [rsp+730h+cbData]
0x18005341f  mov     [rsp+730h+lpcbData], rcx; lpcbData
0x180053424  lea     rcx, [rbp+630h+Data]
0x18005342b  mov     [rsp+730h+lpData], rcx; lpData
0x180053430  lea     rcx, [rsp+730h+Type]
0x180053435  mov     [rsp+730h+lpType], rcx; lpType
0x18005343a  mov     [rsp+730h+phkResult], r11; lpReserved
0x18005343f  lea     r9, [rsp+730h+cchValueName]; lpcchValueName
0x180053444  lea     r8, [rbp+630h+ValueName]; lpValueName
0x180053448  mov     edx, eax; dwIndex
0x18005344a  mov     rcx, [rsp+730h+hKey]; hKey
0x18005344f  call    cs:__imp_RegEnumValueW
0x180053455  cmp     eax, 103h
0x18005345a  mov     ebx, eax
0x18005345c  jnz     loc_18005327A
0x180053462  xor     ecx, ecx
0x180053464  mov     esi, ecx
0x180053466  test    r14, r14
0x180053469  jz      loc_18005356B
0x18005346f  mov     r9, rcx
0x180053472  cmp     rsi, r14
0x180053475  jnb     short loc_180053490
0x180053477  mov     rax, rsi
0x18005347a  mul     [rsp+730h+hHeap+8]
0x18005347f  test    rdx, rdx
0x180053482  jnz     short loc_18005348D
0x180053484  lea     r9, [rax+r13]
0x180053488  cmp     r9, r13
0x18005348b  jnb     short loc_180053490
0x18005348d  mov     r9, rcx
0x180053490  mov     r9, [r9]
0x180053493  lea     r8, aArbtelLs; "ARBTEL_%ls"
0x18005349a  mov     edx, 10Ch; unsigned __int64
0x18005349f  lea     rcx, [rbp+630h+var_270]; unsigned __int16 *
0x1800534a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800534ab  mov     ebx, eax
0x1800534ad  xor     r8d, r8d
0x1800534b0  test    eax, eax
0x1800534b2  js      loc_1800535F9
0x1800534b8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800534be  and     eax, edi
0x1800534c0  test    al, al
0x1800534c2  jz      short loc_1800534E2
0x1800534c4  mov     dword ptr [rsp+730h+phkResult], ebx
0x1800534c8  lea     r9, aFailedToApplyP; "Failed to apply prefix to arbitrary con"...
0x1800534cf  mov     r8, r15; char *
0x1800534d2  mov     rdx, r12; char *
0x1800534d5  mov     ecx, 28Bh; unsigned int
0x1800534da  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800534df  xor     r8d, r8d
0x1800534e2  mov     rax, r8
0x1800534e5  cmp     rsi, r14
0x1800534e8  jnb     short loc_180053502
0x1800534ea  mov     rax, rsi
0x1800534ed  mul     [rsp+730h+hHeap+8]
0x1800534f2  test    rdx, rdx
0x1800534f5  jnz     short loc_1800534FF
0x1800534f7  add     rax, r13
0x1800534fa  cmp     rax, r13
0x1800534fd  jnb     short loc_180053502
0x1800534ff  mov     rax, r8
0x180053502  mov     rcx, [rax]
0x180053505  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053509  inc     rax
0x18005350c  cmp     [rcx+rax*2], r8w
0x180053511  jnz     short loc_180053509
0x180053513  inc     rax
0x180053516  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18005351a  lea     rdx, [rbp+630h+var_270]; unsigned __int16 *
0x180053521  mov     rcx, [rbp+630h+var_6A0]; this
0x180053525  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x18005352a  mov     ebx, eax
0x18005352c  xor     ecx, ecx
0x18005352e  test    eax, eax
0x180053530  js      loc_1800535DE
0x180053536  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18005353c  and     eax, edi
0x18005353e  test    al, al
0x180053540  jz      short loc_18005355F
0x180053542  mov     dword ptr [rsp+730h+phkResult], ebx
0x180053546  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18005354d  mov     r8, r15; char *
0x180053550  mov     rdx, r12; char *
0x180053553  mov     ecx, 28Eh; unsigned int
0x180053558  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18005355d  xor     ecx, ecx
0x18005355f  add     rsi, rdi
0x180053562  cmp     rsi, r14
0x180053565  jb      loc_18005346F
0x18005356b  mov     ebx, ecx
0x18005356d  mov     rcx, [rsp+730h+hKey]; hKey
0x180053572  test    rcx, rcx
0x180053575  jz      short loc_18005357E
0x180053577  call    cs:__imp_RegCloseKey
0x18005357d  nop
0x18005357e  lea     rcx, [rsp+730h+hHeap]; this
0x180053583  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x180053588  mov     r8, [rbp+630h+lpMem+8]; lpMem
0x18005358c  test    r8, r8
0x18005358f  jz      short loc_18005359E
0x180053591  xor     edx, edx; dwFlags
0x180053593  mov     rcx, [rsp+730h+hHeap]; hHeap
  ... truncated ...
```

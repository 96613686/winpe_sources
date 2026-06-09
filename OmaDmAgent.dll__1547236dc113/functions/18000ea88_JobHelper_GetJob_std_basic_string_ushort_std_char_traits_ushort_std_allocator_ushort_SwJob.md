# JobHelper::GetJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_SwJob &)

- ea: `0x18000ea88`
- end: `0x18000f6fd`
- name: `?GetJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SwJob@@@Z`
- size: `3189`
- prototype: ``
- caller_count: `7`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c734`
- `0x18000cb4c`
- `0x18000fa44`
- `0x18000fe4c`
- `0x1800100a4`
- `0x1800102b8`
- `0x180010700`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x1800065f8`
- `0x18000702c`
- `0x1800070e4`
- `0x180008544`
- `0x180008b90`
- `0x180008cec`
- `0x180008fc4`
- `0x180009134`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x18000b74c`
- `0x18000bae8`
- `0x18000bccc`
- `0x18000bd9c`
- `0x18000be18`
- `0x18000e524`
- `0x18000ea88`
- `0x18000f704`
- `0x18000f924`
- `0x18000fdf8`
- `0x18001f3da`
- `0x18001f420`
- `0x18001f4e0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f4a5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000f4a5`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f391`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f391`
- `ADVAPI32!RegEnumKeyExW` at `0x18000f54c`
- `ADVAPI32!RegEnumKeyExW` at `0x18000f54c`
- `KERNEL32!GetLastError` at `0x18000f42c`
- `KERNEL32!GetLastError` at `0x18000f4e4`
- `KERNEL32!GetLastError` at `0x18000f674`
- `KERNEL32!GetLastError` at `0x18000f42c`
- `KERNEL32!GetLastError` at `0x18000f4e4`
- `KERNEL32!GetLastError` at `0x18000f674`
- `KERNEL32!EnterCriticalSection` at `0x18000ec6c`
- `KERNEL32!EnterCriticalSection` at `0x18000ec6c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec04`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec04`

## string_xrefs

- `0x18000f26e`: `BITSId`
- `0x18000f2b6`: `BITSId`
- `0x18000eeb2`: `LicenseXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobHelper::GetJob(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rax
  int JobRegPath; // eax
  signed int JobDependencyHive; // ebx
  _QWORD *v8; // r12
  __int64 v9; // r9
  const unsigned __int16 *v10; // r12
  int Key; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  HKEY v15; // r13
  int RegSZValue; // eax
  LPCWSTR v17; // rcx
  int v18; // edx
  const unsigned __int16 *v19; // r9
  int v20; // r8d
  __int64 v21; // rax
  int v22; // eax
  BYTE *v23; // rdx
  const unsigned __int16 *v24; // r9
  int v25; // rax^4
  int RegDWORDValue; // eax
  const unsigned __int16 *v27; // r9
  int v28; // eax
  int RegBoolValue; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  const WCHAR *v33; // rax
  LSTATUS v34; // eax
  LPCWSTR v35; // rcx
  char LastError; // al
  int v37; // edx
  const WCHAR *v38; // r9
  LSTATUS v39; // eax
  DWORD i; // eax
  __int64 v41; // rbx
  __int64 v42; // rax
  int Dependency; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxSubKeyLena; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxSubKeyLenb; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxSubKeyLenc; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxSubKeyLend; // [rsp+28h] [rbp-D8h]
  unsigned int *lpcbMaxSubKeyLene; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  int v54; // [rsp+6Ch] [rbp-94h]
  int v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+74h] [rbp-8Ch]
  const WCHAR *v57; // [rsp+78h] [rbp-88h]
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h]
  BYTE v63[8]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v64; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v65[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v66; // [rsp+D0h] [rbp-30h]
  _BYTE v67[32]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v68; // [rsp+100h] [rbp+0h]
  LPCWSTR lpSubKey[4]; // [rsp+108h] [rbp+8h] BYREF
  LPCWSTR v70[5]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v71[160]; // [rsp+150h] [rbp+50h] BYREF
  int v72; // [rsp+1F0h] [rbp+F0h]
  WCHAR Name[256]; // [rsp+200h] [rbp+100h] BYREF
  BYTE v74[4096]; // [rsp+400h] [rbp+300h] BYREF
  BYTE v75[131072]; // [rsp+1400h] [rbp+1300h] BYREF

  v62 = a1;
  v68 = a2;
  std::wstring::wstring(v70, &dword_180022F6C);
  memset_0(v74, 0, sizeof(v74));
  memset_0(v75, 0, 0x1FFFEu);
  *(_DWORD *)Data = 0;
  *(_QWORD *)v63 = 0;
  v64 = 0;
  hKey = 0;
  phkResult = 0;
  v5 = std::wstring::wstring(v65, a2);
  JobRegPath = JobHelper::GetJobRegPath(v5, v70);
  JobDependencyHive = JobRegPath;
  if ( JobRegPath >= 0 )
  {
    v10 = (const unsigned __int16 *)v70;
    if ( v70[3] >= (LPCWSTR)8 )
      v10 = v70[0];
    std::wstring::operator=(a3, a2);
    Key = CurrentUserRegKeyHelper::GetKey(&v64, &hKey);
    JobDependencyHive = Key;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)Key);
      goto LABEL_14;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v62 + 128));
    v15 = hKey;
    RegSZValue = ReadRegSZValue(v74, 0x800u, hKey, v10, L"PackageFullName", lpcbMaxSubKeyLen);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 41;
      v19 = L"PackageFullName";
LABEL_20:
      WPP_SF_Sd(
        *((_QWORD *)v17 + 2),
        v18,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (_DWORD)v19,
        RegSZValue);
LABEL_14:
      v8 = a2;
      goto LABEL_15;
    }
    std::wstring::assign(a3 + 32, v74);
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"Status");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 42;
      v19 = L"Status";
      goto LABEL_20;
    }
    v20 = *(_DWORD *)Data;
    LODWORD(hKey) = *(_DWORD *)Data;
    *(_DWORD *)(a3 + 96) = *(_DWORD *)Data;
    *(_DWORD *)(a3 + 152) = v20;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LODWORD(v21) = (_DWORD)a2;
      if ( a2[3] >= 8u )
        v21 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v21,
        v20);
    }
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"Progress");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 44;
      v19 = L"Progress";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 100) = *(_DWORD *)Data;
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"LastError");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 45;
      v19 = L"LastError";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 104) = *(_DWORD *)Data;
    RegSZValue = ReadRegSZValue(v74, 0x800u, v15, v10, L"LastErrorDesc", lpcbMaxSubKeyLena);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 46;
      v19 = L"LastErrorDesc";
      goto LABEL_20;
    }
    std::wstring::assign(a3 + 112, v74);
    v22 = ReadRegSZValue(v75, 0xFFFFu, v15, v10, L"LicenseXml", lpcbMaxSubKeyLenb);
    if ( v22 >= 0 )
    {
      v23 = v75;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)L"LicenseXml",
          v22);
      v23 = (BYTE *)&dword_180022F6C;
    }
    std::wstring::assign(a3 + 160, v23);
    RegSZValue = ReadRegQWORDValue(v63, v15, v10, v24);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 48;
      v19 = L"CreationTime";
      goto LABEL_20;
    }
    v25 = *(_DWORD *)&v63[4];
    *(_DWORD *)(a3 + 144) = *(_DWORD *)v63;
    *(_DWORD *)(a3 + 148) = v25;
    RegSZValue = ReadRegMultiSZValue(v15, v10);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 49;
      v19 = L"UrlList";
      goto LABEL_20;
    }
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"ActionType");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 50;
      v19 = L"ActionType";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 64) = *(_DWORD *)Data;
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"DeployOptions");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 51;
      v19 = L"DeployOptions";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 72) = *(_DWORD *)Data;
    RegDWORDValue = ReadRegDWORDValue(Data, v15, v10, L"JobType");
    if ( RegDWORDValue >= 0 )
    {
      v28 = *(_DWORD *)Data;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)L"JobType",
          RegDWORDValue);
      v28 = 1;
      *(_DWORD *)Data = 1;
    }
    *(_DWORD *)(a3 + 68) = v28;
    RegBoolValue = GetRegBoolValue((bool *)(a3 + 76), v15, v10, v27);
    if ( RegBoolValue < 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)L"IsBundle",
          RegBoolValue);
      *(_BYTE *)(a3 + 76) = 0;
    }
    RegSZValue = ReadRegSZValue(v74, 0x800u, v15, v10, L"ContentLocation", lpcbMaxSubKeyLenc);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 54;
      v19 = L"ContentLocation";
      goto LABEL_20;
    }
    std::wstring::assign(a3 + 192, v74);
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"DeployRetryCount");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 55;
      v19 = L"DeployRetryCount";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 224) = *(_DWORD *)Data;
    RegSZValue = ReadRegDWORDValue(Data, v15, v10, L"CurrentDPIndex");
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 56;
      v19 = L"CurrentDPIndex";
      goto LABEL_20;
    }
    *(_DWORD *)(a3 + 264) = *(_DWORD *)Data;
    RegSZValue = ReadRegSZValue(v74, 0x800u, v15, v10, L"CurrentDPUrl", lpcbMaxSubKeyLend);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 57;
      v19 = L"CurrentDPUrl";
      goto LABEL_20;
    }
    std::wstring::assign(a3 + 272, v74);
    RegSZValue = ReadRegSZValue(v74, 0x800u, v15, v10, L"BITSId", lpcbMaxSubKeyLene);
    JobDependencyHive = RegSZValue;
    if ( RegSZValue < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_14;
      v18 = 58;
      v19 = L"BITSId";
      goto LABEL_20;
    }
    std::wstring::assign(a3 + 232, v74);
    std::wstring::wstring(lpSubKey, &dword_180022F6C);
    v8 = a2;
    v30 = std::wstring::wstring(v65, a2);
    JobDependencyHive = JobHelper::GetJobDependencyHive(v30, lpSubKey);
    if ( JobDependencyHive < 0 )
    {
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_102;
      LODWORD(v32) = (_DWORD)a2;
      if ( a2[3] >= 8u )
        v32 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v32,
        JobDependencyHive);
      goto LABEL_101;
    }
    v55 = 0;
    v54 = 0;
    v56 = 0;
    v33 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] >= (LPCWSTR)8 )
      v33 = lpSubKey[0];
    v57 = v33;
    v34 = RegOpenKeyExW(v15, v33, 0, 0x20019u, &phkResult);
    LOBYTE(v15) = v34;
    if ( v34 == 2 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_110:
        if ( (_DWORD)hKey != 20 )
        {
          if ( (_DWORD)hKey != 40 )
            goto LABEL_157;
          if ( v54 > 0 )
          {
            *(_DWORD *)(a3 + 96) = 30;
            goto LABEL_156;
          }
          if ( v55 <= 0 )
          {
            if ( v56 != *(_QWORD *)(a3 + 312) )
              goto LABEL_157;
            *(_DWORD *)(a3 + 96) = 40;
LABEL_156:
            v35 = WPP_GLOBAL_Control;
LABEL_157:
            if ( v35 == (LPCWSTR)&WPP_GLOBAL_Control || (v35[14] & 1) == 0 )
              goto LABEL_102;
            LODWORD(v45) = (_DWORD)a2;
            if ( a2[3] >= 8u )
              v45 = *a2;
            WPP_SF_Sd(
              *((_QWORD *)v35 + 2),
              65,
              (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
              v45,
              *(_DWORD *)(a3 + 96));
LABEL_101:
            v8 = a2;
LABEL_102:
            LOBYTE(v31) = 1;
            std::wstring::_Tidy(lpSubKey, v31, 0);
            goto LABEL_15;
          }
        }
        *(_DWORD *)(a3 + 96) = 20;
        goto LABEL_156;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
LABEL_109:
      v35 = WPP_GLOBAL_Control;
      goto LABEL_110;
    }
    if ( v34 )
    {
      if ( v34 > 0 )
        JobDependencyHive = (unsigned __int16)v34 | 0x80070000;
      else
        JobDependencyHive = v34;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_102;
      LastError = GetLastError();
      v37 = 61;
      LODWORD(v38) = (_DWORD)v57;
    }
    else
    {
      cSubKeys = 0;
      cchName = 255;
      v39 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      LOBYTE(v15) = v39;
      if ( !v39 )
      {
        for ( i = 0; ; i = (_DWORD)v57 + 1 )
        {
          LODWORD(v57) = i;
          if ( i >= cSubKeys )
            break;
          cchName = 255;
          LODWORD(v15) = RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0);
          if ( (_DWORD)v15 )
          {
            if ( (int)v15 > 0 )
              JobDependencyHive = (unsigned __int16)v15 | 0x80070000;
            else
              JobDependencyHive = (int)v15;
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            {
              LastError = GetLastError();
              v37 = 63;
              goto LABEL_129;
            }
            goto LABEL_102;
          }
          _FrameworkDependency::_FrameworkDependency((_FrameworkDependency *)v71);
          v66 = v65;
          v41 = std::wstring::wstring(v65, Name);
          v42 = std::wstring::wstring(v67, a3);
          Dependency = JobHelper::GetDependency(v62, v42, v41, v71);
          JobDependencyHive = Dependency;
          if ( Dependency < 0 )
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                64,
                (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
                (unsigned int)Name,
                Dependency);
            _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)v71);
            goto LABEL_102;
          }
          if ( v72 != 10 )
          {
            switch ( v72 )
            {
              case 20:
                ++v55;
                break;
              case 30:
                ++v54;
                break;
              case 40:
                ++v56;
                break;
            }
          }
          v44 = std::map<std::wstring,_FrameworkDependency>::operator[](a3 + 304, v71);
          _FrameworkDependency::operator=(v44, v71);
          _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)v71);
        }
        goto LABEL_109;
      }
      if ( v39 > 0 )
        JobDependencyHive = (unsigned __int16)v39 | 0x80070000;
      else
        JobDependencyHive = v39;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_102;
      LastError = GetLastError();
      v37 = 62;
LABEL_129:
      v38 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB";
    }
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v37,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (_DWORD)v38,
      (char)v15,
      LastError);
    goto LABEL_102;
  }
  v8 = a2;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    if ( a2[3] < 8u )
      LODWORD(v9) = (_DWORD)a2;
    else
      v9 = *a2;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      v9,
      JobRegPath);
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v62 + 128));
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)&v64);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v70, v12, 0);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v8, v13, 0);
  return (unsigned int)JobDependencyHive;
}

```

## disassembly

```asm
0x18000ea88  mov     [rsp-8+arg_18], rbx
0x18000ea8d  push    rbp
0x18000ea8e  push    rsi
0x18000ea8f  push    rdi
0x18000ea90  push    r12
0x18000ea92  push    r13
0x18000ea94  push    r14
0x18000ea96  push    r15
0x18000ea98  lea     rbp, [rsp-21310h]
0x18000eaa0  mov     eax, 21410h
0x18000eaa5  call    _alloca_probe
0x18000eaaa  sub     rsp, rax
0x18000eaad  mov     rax, cs:__security_cookie
0x18000eab4  xor     rax, rsp
0x18000eab7  mov     [rbp+21340h+var_40], rax
0x18000eabe  mov     r15, r8
0x18000eac1  mov     rsi, rdx
0x18000eac4  mov     [rsp+21440h+var_213E0], rdx
0x18000eac9  mov     [rbp+21340h+var_213A8], rcx
0x18000eacd  mov     [rbp+21340h+var_21340], rdx
0x18000ead1  lea     rdx, dword_180022F6C
0x18000ead8  lea     rcx, [rbp+21340h+var_21318]
0x18000eadc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000eae1  nop
0x18000eae2  xor     edx, edx; Val
0x18000eae4  mov     r8d, 1000h; Size
0x18000eaea  lea     rcx, [rbp+21340h+var_21040]; void *
0x18000eaf1  call    memset_0
0x18000eaf6  xor     edx, edx; Val
0x18000eaf8  mov     r8d, 1FFFEh; Size
0x18000eafe  lea     rcx, [rbp+21340h+var_20040]; void *
0x18000eb05  call    memset_0
0x18000eb0a  xor     edi, edi
0x18000eb0c  mov     dword ptr [rsp+21440h+Data], edi
0x18000eb10  mov     qword ptr [rbp+21340h+var_213A0], rdi
0x18000eb14  mov     [rbp+21340h+var_21398], rdi
0x18000eb18  mov     [rbp+21340h+hKey], rdi
0x18000eb1c  mov     [rbp+21340h+var_213B0], rdi
0x18000eb20  mov     rdx, rsi
0x18000eb23  lea     rcx, [rbp+21340h+var_21390]
0x18000eb27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000eb2c  lea     rdx, [rbp+21340h+var_21318]
0x18000eb30  mov     rcx, rax
0x18000eb33  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x18000eb38  mov     ebx, eax
0x18000eb3a  test    eax, eax
0x18000eb3c  jns     short loc_18000EB93
0x18000eb3e  lea     rsi, WPP_GLOBAL_Control
0x18000eb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb4c  mov     r12, [rsp+21440h+var_213E0]
0x18000eb51  cmp     rcx, rsi
0x18000eb54  jz      loc_18000EBFC
0x18000eb5a  mov     dil, 4
0x18000eb5d  test    [rcx+1Ch], dil
0x18000eb61  jz      loc_18000EBFC
0x18000eb67  cmp     qword ptr [r12+18h], 8
0x18000eb6d  jb      short loc_18000EB75
0x18000eb6f  mov     r9, [r12]
0x18000eb73  jmp     short loc_18000EB78
0x18000eb75  mov     r9, r12
0x18000eb78  mov     edx, 27h ; '''
0x18000eb7d  mov     dword ptr [rsp+21440h+phkResult], eax
0x18000eb81  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000eb88  mov     rcx, [rcx+10h]
0x18000eb8c  call    WPP_SF_Sd
0x18000eb91  jmp     short loc_18000EBFC
0x18000eb93  lea     r12, [rbp+21340h+var_21318]
0x18000eb97  cmp     [rbp+21340h+var_21300], 8
0x18000eb9c  cmovnb  r12, [rbp+21340h+var_21318]
0x18000eba1  mov     rdx, rsi
0x18000eba4  mov     rcx, r15
0x18000eba7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000ebac  lea     rdx, [rbp+21340h+hKey]; HKEY *
0x18000ebb0  lea     rcx, [rbp+21340h+var_21398]; phkResult
0x18000ebb4  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x18000ebb9  mov     ebx, eax
0x18000ebbb  test    eax, eax
0x18000ebbd  jns     loc_18000EC64
0x18000ebc3  lea     rsi, WPP_GLOBAL_Control
0x18000ebca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebd1  cmp     rcx, rsi
0x18000ebd4  jz      short loc_18000EBF7
0x18000ebd6  mov     dil, 4
0x18000ebd9  test    [rcx+1Ch], dil
0x18000ebdd  jz      short loc_18000EBF7
0x18000ebdf  mov     edx, 28h ; '('
0x18000ebe4  mov     r9d, eax
0x18000ebe7  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000ebee  mov     rcx, [rcx+10h]
0x18000ebf2  call    WPP_SF_d
0x18000ebf7  mov     r12, [rsp+21440h+var_213E0]
0x18000ebfc  mov     rcx, [rbp+21340h+var_213A8]
0x18000ec00  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18000ec04  call    cs:__imp_LeaveCriticalSection
0x18000ec0b  nop     dword ptr [rax+rax+00h]
0x18000ec10  nop
0x18000ec11  lea     rcx, [rbp+21340h+var_21398]; this
0x18000ec15  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18000ec1a  nop
0x18000ec1b  xor     r8d, r8d
0x18000ec1e  mov     dl, 1
0x18000ec20  lea     rcx, [rbp+21340h+var_21318]
0x18000ec24  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ec29  nop
0x18000ec2a  xor     r8d, r8d
0x18000ec2d  mov     dl, 1
0x18000ec2f  mov     rcx, r12
0x18000ec32  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ec37  mov     eax, ebx
0x18000ec39  mov     rcx, [rbp+21340h+var_40]
0x18000ec40  xor     rcx, rsp; StackCookie
0x18000ec43  call    __security_check_cookie
0x18000ec48  mov     rbx, [rsp+21440h+arg_18]
0x18000ec50  add     rsp, 21410h
0x18000ec57  pop     r15
0x18000ec59  pop     r14
0x18000ec5b  pop     r13
0x18000ec5d  pop     r12
0x18000ec5f  pop     rdi
0x18000ec60  pop     rsi
0x18000ec61  pop     rbp
0x18000ec62  retn
0x18000ec64  mov     rcx, [rbp+21340h+var_213A8]
0x18000ec68  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18000ec6c  call    cs:__imp_EnterCriticalSection
0x18000ec73  nop     dword ptr [rax+rax+00h]
0x18000ec78  lea     r14, aPackagefullnam; "PackageFullName"
0x18000ec7f  mov     [rsp+21440h+phkResult], r14; unsigned __int16 *
0x18000ec84  mov     r9, r12; unsigned __int16 *
0x18000ec87  mov     r13, [rbp+21340h+hKey]
0x18000ec8b  mov     r8, r13; HKEY
0x18000ec8e  mov     edx, 800h; unsigned __int64
0x18000ec93  lea     rcx, [rbp+21340h+var_21040]; lpData
0x18000ec9a  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000ec9f  mov     ebx, eax
0x18000eca1  test    eax, eax
0x18000eca3  jns     short loc_18000ECEA
0x18000eca5  lea     rsi, WPP_GLOBAL_Control
0x18000ecac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecb3  cmp     rcx, rsi
0x18000ecb6  jz      loc_18000EBF7
0x18000ecbc  mov     dil, 4
0x18000ecbf  test    [rcx+1Ch], dil
0x18000ecc3  jz      loc_18000EBF7
0x18000ecc9  mov     edx, 29h ; ')'
0x18000ecce  mov     r9, r14
0x18000ecd1  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000ecd8  mov     dword ptr [rsp+21440h+phkResult], eax
0x18000ecdc  mov     rcx, [rcx+10h]
0x18000ece0  call    WPP_SF_Sd
0x18000ece5  jmp     loc_18000EBF7
0x18000ecea  lea     rcx, [r15+20h]
0x18000ecee  lea     rdx, [rbp+21340h+var_21040]
0x18000ecf5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000ecfa  lea     r9, aStatus; "Status"
0x18000ed01  mov     r8, r12; lpSubKey
0x18000ed04  mov     rdx, r13; hKey
0x18000ed07  lea     rcx, [rsp+21440h+Data]; lpData
0x18000ed0c  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x18000ed11  mov     ebx, eax
0x18000ed13  test    eax, eax
0x18000ed15  jns     short loc_18000ED49
0x18000ed17  lea     rsi, WPP_GLOBAL_Control
0x18000ed1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed25  cmp     rcx, rsi
0x18000ed28  jz      loc_18000EBF7
0x18000ed2e  mov     dil, 4
0x18000ed31  test    [rcx+1Ch], dil
0x18000ed35  jz      loc_18000EBF7
0x18000ed3b  mov     edx, 2Ah ; '*'
0x18000ed40  lea     r9, aStatus; "Status"
0x18000ed47  jmp     short loc_18000ECD1
0x18000ed49  mov     r8d, dword ptr [rsp+21440h+Data]
0x18000ed4e  mov     dword ptr [rbp+21340h+hKey], r8d
0x18000ed52  mov     [r15+60h], r8d
0x18000ed56  mov     [r15+98h], r8d
0x18000ed5d  lea     rsi, WPP_GLOBAL_Control
0x18000ed64  lea     r14, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000ed6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed72  cmp     rcx, rsi
0x18000ed75  jz      short loc_18000EDA5
0x18000ed77  test    byte ptr [rcx+1Ch], 1
0x18000ed7b  jz      short loc_18000EDA5
0x18000ed7d  mov     rax, [rsp+21440h+var_213E0]
0x18000ed82  cmp     qword ptr [rax+18h], 8
0x18000ed87  jb      short loc_18000ED8C
0x18000ed89  mov     rax, [rax]
0x18000ed8c  mov     edx, 2Bh ; '+'
0x18000ed91  mov     dword ptr [rsp+21440h+phkResult], r8d
0x18000ed96  mov     r9, rax
0x18000ed99  mov     r8, r14
0x18000ed9c  mov     rcx, [rcx+10h]
0x18000eda0  call    WPP_SF_Sd
0x18000eda5  lea     r9, aProgress; "Progress"
0x18000edac  mov     r8, r12; lpSubKey
0x18000edaf  mov     rdx, r13; hKey
0x18000edb2  lea     rcx, [rsp+21440h+Data]; lpData
0x18000edb7  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x18000edbc  mov     ebx, eax
0x18000edbe  test    eax, eax
0x18000edc0  jns     short loc_18000EDF3
0x18000edc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edc9  cmp     rcx, rsi
0x18000edcc  jz      loc_18000EBF7
0x18000edd2  mov     dil, 4
0x18000edd5  test    [rcx+1Ch], dil
0x18000edd9  jz      loc_18000EBF7
0x18000eddf  mov     edx, 2Ch ; ','
0x18000ede4  lea     r9, aProgress; "Progress"
0x18000edeb  mov     r8, r14
0x18000edee  jmp     loc_18000ECD8
0x18000edf3  mov     eax, dword ptr [rsp+21440h+Data]
0x18000edf7  mov     [r15+64h], eax
0x18000edfb  lea     r9, aLasterror; "LastError"
0x18000ee02  mov     r8, r12; lpSubKey
0x18000ee05  mov     rdx, r13; hKey
0x18000ee08  lea     rcx, [rsp+21440h+Data]; lpData
0x18000ee0d  call    ?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z; ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)
0x18000ee12  mov     ebx, eax
0x18000ee14  test    eax, eax
0x18000ee16  jns     short loc_18000EE43
0x18000ee18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee1f  cmp     rcx, rsi
0x18000ee22  jz      loc_18000EBF7
0x18000ee28  mov     dil, 4
0x18000ee2b  test    [rcx+1Ch], dil
0x18000ee2f  jz      loc_18000EBF7
0x18000ee35  mov     edx, 2Dh ; '-'
0x18000ee3a  lea     r9, aLasterror; "LastError"
0x18000ee41  jmp     short loc_18000EDEB
0x18000ee43  mov     eax, dword ptr [rsp+21440h+Data]
0x18000ee47  mov     [r15+68h], eax
0x18000ee4b  lea     rax, aLasterrordesc; "LastErrorDesc"
0x18000ee52  mov     [rsp+21440h+phkResult], rax; unsigned __int16 *
0x18000ee57  mov     r9, r12; unsigned __int16 *
0x18000ee5a  mov     r8, r13; HKEY
0x18000ee5d  mov     edx, 800h; unsigned __int64
0x18000ee62  lea     rcx, [rbp+21340h+var_21040]; lpData
0x18000ee69  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000ee6e  mov     ebx, eax
0x18000ee70  test    eax, eax
0x18000ee72  jns     short loc_18000EEA2
0x18000ee74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee7b  cmp     rcx, rsi
0x18000ee7e  jz      loc_18000EBF7
0x18000ee84  mov     dil, 4
0x18000ee87  test    [rcx+1Ch], dil
0x18000ee8b  jz      loc_18000EBF7
0x18000ee91  mov     edx, 2Eh ; '.'
0x18000ee96  lea     r9, aLasterrordesc; "LastErrorDesc"
0x18000ee9d  jmp     loc_18000EDEB
0x18000eea2  lea     rcx, [r15+70h]
0x18000eea6  lea     rdx, [rbp+21340h+var_21040]
0x18000eead  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000eeb2  lea     rbx, aLicensexml; "LicenseXml"
0x18000eeb9  mov     [rsp+21440h+phkResult], rbx; unsigned __int16 *
0x18000eebe  mov     r9, r12; unsigned __int16 *
0x18000eec1  mov     r8, r13; HKEY
0x18000eec4  mov     edx, 0FFFFh; unsigned __int64
0x18000eec9  lea     rcx, [rbp+21340h+var_20040]; lpData
0x18000eed0  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000eed5  mov     dil, 4
0x18000eed8  test    eax, eax
0x18000eeda  jns     short loc_18000EF0F
0x18000eedc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eee3  cmp     rcx, rsi
0x18000eee6  jz      short loc_18000EF06
0x18000eee8  test    [rcx+1Ch], dil
0x18000eeec  jz      short loc_18000EF06
0x18000eeee  mov     edx, 2Fh ; '/'
0x18000eef3  mov     dword ptr [rsp+21440h+phkResult], eax
0x18000eef7  mov     r9, rbx
0x18000eefa  mov     r8, r14
0x18000eefd  mov     rcx, [rcx+10h]
0x18000ef01  call    WPP_SF_Sd
0x18000ef06  lea     rdx, dword_180022F6C
0x18000ef0d  jmp     short loc_18000EF16
0x18000ef0f  lea     rdx, [rbp+21340h+var_20040]
0x18000ef16  lea     rcx, [r15+0A0h]
0x18000ef1d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000ef22  mov     r8, r12; lpSubKey
0x18000ef25  mov     rdx, r13; hKey
0x18000ef28  lea     rcx, [rbp+21340h+var_213A0]; lpData
0x18000ef2c  call    ?ReadRegQWORDValue@@YAJPEA_JPEAUHKEY__@@PEBG2@Z; ReadRegQWORDValue(__int64 *,HKEY__ *,ushort const *,ushort const *)
0x18000ef31  mov     ebx, eax
0x18000ef33  test    eax, eax
0x18000ef35  jns     short loc_18000EF62
0x18000ef37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef3e  cmp     rcx, rsi
0x18000ef41  jz      loc_18000EBF7
0x18000ef47  test    [rcx+1Ch], dil
0x18000ef4b  jz      loc_18000EBF7
0x18000ef51  mov     edx, 30h ; '0'
0x18000ef56  lea     r9, aCreationtime; "CreationTime"
0x18000ef5d  jmp     loc_18000EDEB
0x18000ef62  mov     rax, qword ptr [rbp+21340h+var_213A0]
0x18000ef66  mov     [r15+90h], eax
0x18000ef6d  shr     rax, 20h
0x18000ef71  mov     [r15+94h], eax
0x18000ef78  lea     r9, [r15+50h]
  ... truncated ...
```

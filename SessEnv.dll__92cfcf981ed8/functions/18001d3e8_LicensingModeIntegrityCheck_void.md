# LicensingModeIntegrityCheck(void)

- ea: `0x18001d3e8`
- end: `0x18001d7ee`
- name: `?LicensingModeIntegrityCheck@@YAXXZ`
- size: `1030`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d7f4`

## callees

- `0x180001008`
- `0x180001090`
- `0x180001134`
- `0x1800011f8`
- `0x18001d3e8`
- `0x1800258fc`
- `0x1800259b8`
- `0x18004325c`
- `0x18004330c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d72c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d72c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d4e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d4e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d471`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d471`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d7da`

## string_xrefs

- `0x18001d494`: `LicensingModeIntegrityCheck::RegCreateKeyEx failed`
- `0x18001d50b`: `LicensingModeIntegrityCheck::Registry value does not exist. Setting regValueExisting to MAXIMUM_POLICY_ID`
- `0x18001d5fb`: `SessEnv.dll`
- `0x18001d5e4`: `LicensingModeIntegrityCheck::EVD SKU - Licensing Mode is already set`
- `0x18001d6ab`: `LicensingModeIntegrityCheck::Server SKU with RDSH role - Licensing Mode is already set`
- `0x18001d74f`: `LicensingModeIntegrityCheck::Setting registry value failed`

## pseudocode

```c
void LicensingModeIntegrityCheck(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // eax
  unsigned int v2; // edi
  int IsAppServerInstalled; // esi
  int IsAADLicensingAllowed; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // edi
  int v9; // r14d
  char *v10; // rdx
  const char *v11; // rax
  const unsigned __int16 **v12; // rax
  __int16 *v13; // rdx
  const char *v14; // rax
  LSTATUS v15; // eax
  int v16; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-2Ch] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  int v19; // [rsp+5Ch] [rbp-24h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  const unsigned __int16 *v22[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+B0h] [rbp+30h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+40h] BYREF
  const char *v26; // [rsp+C8h] [rbp+48h] BYREF

  hKey = 0;
  dwDisposition = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  v24 = 0;
  LODWORD(v26) = 0;
  v16 = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Licensing Core",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( v0 )
  {
    if ( (unsigned int)dword_180084170 > 3 )
    {
      LODWORD(v26) = v0;
      v20 = "LicensingModeIntegrityCheck::RegCreateKeyEx failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)&dword_180084170,
        (__int64)&dword_180078A9C,
        0,
        0,
        (const unsigned __int16 **)&v20,
        (__int64)&v26);
    }
    goto LABEL_38;
  }
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"LicensingMode", 0, &Type, (LPBYTE)&Data, &cbData);
  v2 = v1;
  if ( v1 == 2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v19 = v2;
      v20 = "LicensingModeIntegrityCheck::Registry value does not exist. Setting regValueExisting to MAXIMUM_POLICY_ID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)&dword_180084170,
        (__int64)&word_180078A6E,
        0,
        0,
        (const unsigned __int16 **)&v20,
        (__int64)&v19);
    }
    Data = 8;
  }
  else if ( v1 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("SessEnv.dll", v1, 0);
    if ( (unsigned int)dword_180084170 <= 3 )
      goto LABEL_38;
    LODWORD(v26) = v2;
    v20 = "LicensingModeIntegrityCheck::RegQueryKeyEx failed";
    v10 = (char *)qword_180078A40;
    v12 = (const unsigned __int16 **)&v20;
    goto LABEL_37;
  }
  IsAppServerInstalled = CSLQuery::IsAppServerInstalled(&v16);
  IsAADLicensingAllowed = CSLQuery::IsAADLicensingAllowed((int *)&v26);
  v7 = (unsigned int)dword_180084170;
  v8 = IsAADLicensingAllowed;
  v9 = (int)v26;
  if ( (unsigned int)dword_180084170 > 5 )
  {
    LODWORD(v26) = IsAADLicensingAllowed;
    v19 = IsAppServerInstalled;
    v22[0] = (const unsigned __int16 *)"LicensingModeIntegrityCheck::bAllowAADLicensing";
    LODWORD(v20) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180084170,
      (__int64)&byte_1800789EF,
      v5,
      v6,
      v22,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v26);
  }
  if ( v8 >= 0 && v9 )
  {
    if ( Data == 6 )
    {
      if ( (unsigned int)dword_180084170 <= 5 )
        goto LABEL_38;
      v10 = &byte_1800789BF;
      LODWORD(v26) = Data;
      v11 = "LicensingModeIntegrityCheck::EVD SKU - Licensing Mode is already set";
LABEL_36:
      v22[0] = (const unsigned __int16 *)v11;
      v12 = v22;
LABEL_37:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)&dword_180084170,
        (__int64)v10,
        0,
        0,
        v12,
        (__int64)&v26);
      goto LABEL_38;
    }
    v24 = 6;
    if ( (unsigned int)dword_180084170 > 4 )
    {
      v13 = word_180078982;
      LODWORD(v26) = v24;
      LODWORD(v20) = Data;
      v14 = "LicensingModeIntegrityCheck::EVD SKU";
LABEL_28:
      v22[0] = (const unsigned __int16 *)v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)v13,
        v5,
        v6,
        v22,
        (__int64)&v20,
        (__int64)&v26);
    }
  }
  else
  {
    if ( IsAppServerInstalled < 0 || !v16 )
    {
      if ( (unsigned int)dword_180084170 <= 5 )
        goto LABEL_38;
      v10 = byte_1800788E5;
      LODWORD(v26) = Data;
      v11 = "LicensingModeIntegrityCheck::Taking no action";
      goto LABEL_36;
    }
    if ( Data <= 7 )
    {
      v7 = 180;
      if ( _bittest((const int *)&v7, Data) )
      {
        if ( (unsigned int)dword_180084170 <= 5 )
          goto LABEL_38;
        v10 = (char *)word_180078952;
        LODWORD(v26) = Data;
        v11 = "LicensingModeIntegrityCheck::Server SKU with RDSH role - Licensing Mode is already set";
        goto LABEL_36;
      }
    }
    v24 = 5;
    if ( (unsigned int)dword_180084170 > 4 )
    {
      v13 = (__int16 *)byte_180078915;
      LODWORD(v26) = v24;
      LODWORD(v20) = Data;
      v14 = "LicensingModeIntegrityCheck::Server SKU with RDSH role";
      goto LABEL_28;
    }
  }
  v15 = RegSetValueExW(hKey, L"LicensingMode", 0, 4u, (const BYTE *)&v24, 4u);
  if ( v15 )
  {
    if ( (unsigned int)dword_180084170 <= 3 )
      goto LABEL_38;
    LODWORD(v26) = v15;
    v10 = &byte_1800788B7;
    v11 = "LicensingModeIntegrityCheck::Setting registry value failed";
    goto LABEL_36;
  }
  if ( (unsigned int)dword_180084170 > 5 )
  {
    v26 = "LicensingModeIntegrityCheck::SetSuccessfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)&dword_180084170,
      (__int64)byte_180078899,
      0,
      0,
      (const unsigned __int16 **)&v26);
  }
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001d3e8  push    rbp
0x18001d3ea  push    rbx
0x18001d3eb  push    rsi
0x18001d3ec  push    rdi
0x18001d3ed  push    r14
0x18001d3ef  mov     rbp, rsp
0x18001d3f2  sub     rsp, 80h
0x18001d3f9  lea     rax, [rbp+dwDisposition]
0x18001d3fd  mov     [rbp+hKey], 0
0x18001d405  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18001d40a  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001d411  lea     rax, [rbp+hKey]
0x18001d415  mov     [rbp+dwDisposition], 0
0x18001d41c  mov     [rsp+80h+phkResult], rax; phkResult
0x18001d421  xor     r9d, r9d; lpClass
0x18001d424  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d42d  xor     r8d, r8d; Reserved
0x18001d430  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18001d438  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d43f  mov     [rsp+80h+dwOptions], 0; dwOptions
0x18001d447  mov     [rbp+Type], 0
0x18001d44e  mov     [rbp+Data], 0
0x18001d455  mov     [rbp+cbData], 0
0x18001d45c  mov     [rbp+arg_8], 0
0x18001d463  mov     dword ptr [rbp+arg_18], 0
0x18001d46a  mov     [rbp+var_30], 0
0x18001d471  call    cs:__imp_RegCreateKeyExW
0x18001d477  test    eax, eax
0x18001d479  jz      short loc_18001D4B8
0x18001d47b  mov     ecx, cs:dword_180084170
0x18001d481  cmp     ecx, 3
0x18001d484  jbe     loc_18001D7D1
0x18001d48a  mov     dword ptr [rbp+arg_18], eax
0x18001d48d  lea     rdx, dword_180078A9C
0x18001d494  lea     rax, aLicensingmodei_8; "LicensingModeIntegrityCheck::RegCreateK"...
0x18001d49b  mov     [rbp+var_20], rax
0x18001d49f  lea     rcx, dword_180084170
0x18001d4a6  lea     rax, [rbp+arg_18]
0x18001d4aa  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d4af  lea     rax, [rbp+var_20]
0x18001d4b3  jmp     loc_18001D7C1
0x18001d4b8  mov     rcx, [rbp+hKey]; hKey
0x18001d4bc  lea     rax, [rbp+cbData]
0x18001d4c0  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18001d4c5  lea     r9, [rbp+Type]; lpType
0x18001d4c9  lea     rax, [rbp+Data]
0x18001d4cd  mov     [rbp+cbData], 4
0x18001d4d4  xor     r8d, r8d; lpReserved
0x18001d4d7  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18001d4dc  lea     rdx, aLicensingmode; "LicensingMode"
0x18001d4e3  call    cs:__imp_RegQueryValueExW
0x18001d4e9  lea     rbx, dword_180084170
0x18001d4f0  mov     edi, eax
0x18001d4f2  cmp     eax, 2
0x18001d4f5  jnz     loc_18001D5F0
0x18001d4fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d500  mov     eax, cs:dword_180084170
0x18001d506  cmp     eax, 3
0x18001d509  jbe     short loc_18001D540
0x18001d50b  lea     rax, aLicensingmodei_7; "LicensingModeIntegrityCheck::Registry v"...
0x18001d512  mov     [rbp+var_24], edi
0x18001d515  mov     [rbp+var_20], rax
0x18001d519  lea     rdx, word_180078A6E
0x18001d520  lea     rax, [rbp+var_24]
0x18001d524  xor     r9d, r9d
0x18001d527  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d52c  xor     r8d, r8d
0x18001d52f  lea     rax, [rbp+var_20]
0x18001d533  mov     rcx, rbx
0x18001d536  mov     qword ptr [rsp+80h+dwOptions], rax
0x18001d53b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001d540  mov     [rbp+Data], 8
0x18001d547  lea     rcx, [rbp+var_30]; int *
0x18001d54b  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18001d550  lea     rcx, [rbp+arg_18]; int *
0x18001d554  mov     esi, eax
0x18001d556  call    ?IsAADLicensingAllowed@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAADLicensingAllowed(int *)
0x18001d55b  mov     ecx, cs:dword_180084170
0x18001d561  mov     edi, eax
0x18001d563  mov     r14d, dword ptr [rbp+arg_18]
0x18001d567  cmp     ecx, 5
0x18001d56a  jbe     short loc_18001D5B1
0x18001d56c  mov     dword ptr [rbp+arg_18], eax
0x18001d56f  lea     rdx, byte_1800789EF
0x18001d576  lea     rax, aLicensingmodei_2; "LicensingModeIntegrityCheck::bAllowAADL"...
0x18001d57d  mov     [rbp+var_24], esi
0x18001d580  mov     [rbp+var_10], rax
0x18001d584  lea     rax, [rbp+arg_18]
0x18001d588  mov     [rsp+80h+phkResult], rax
0x18001d58d  lea     rax, [rbp+var_24]
0x18001d591  mov     [rsp+80h+lpSecurityAttributes], rax
0x18001d596  lea     rax, [rbp+var_20]
0x18001d59a  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d59f  lea     rax, [rbp+var_10]
0x18001d5a3  mov     qword ptr [rsp+80h+dwOptions], rax
0x18001d5a8  mov     dword ptr [rbp+var_20], r14d
0x18001d5ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d5b1  test    edi, edi
0x18001d5b3  js      loc_18001D66B
0x18001d5b9  test    r14d, r14d
0x18001d5bc  jz      loc_18001D66B
0x18001d5c2  cmp     [rbp+Data], 6
0x18001d5c6  mov     eax, cs:dword_180084170
0x18001d5cc  jnz     short loc_18001D63F
0x18001d5ce  cmp     eax, 5
0x18001d5d1  jbe     loc_18001D7D1
0x18001d5d7  mov     eax, [rbp+Data]
0x18001d5da  lea     rdx, byte_1800789BF
0x18001d5e1  mov     dword ptr [rbp+arg_18], eax
0x18001d5e4  lea     rax, aLicensingmodei_1; "LicensingModeIntegrityCheck::EVD SKU - "...
0x18001d5eb  jmp     loc_18001D7AD
0x18001d5f0  test    edi, edi
0x18001d5f2  jz      loc_18001D547
0x18001d5f8  xor     r8d, r8d
0x18001d5fb  lea     rcx, aSessenvDll_0; "SessEnv.dll"
0x18001d602  mov     edx, edi
0x18001d604  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001d609  mov     eax, cs:dword_180084170
0x18001d60f  cmp     eax, 3
0x18001d612  jbe     loc_18001D7D1
0x18001d618  lea     rax, aLicensingmodei; "LicensingModeIntegrityCheck::RegQueryKe"...
0x18001d61f  mov     dword ptr [rbp+arg_18], edi
0x18001d622  mov     [rbp+var_20], rax
0x18001d626  lea     rdx, qword_180078A40
0x18001d62d  lea     rax, [rbp+arg_18]
0x18001d631  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d636  lea     rax, [rbp+var_20]
0x18001d63a  jmp     loc_18001D7BE
0x18001d63f  mov     [rbp+arg_8], 6
0x18001d646  cmp     eax, 4
0x18001d649  jbe     loc_18001D707
0x18001d64f  mov     eax, [rbp+arg_8]
0x18001d652  lea     rdx, word_180078982
0x18001d659  mov     dword ptr [rbp+arg_18], eax
0x18001d65c  mov     eax, [rbp+Data]
0x18001d65f  mov     dword ptr [rbp+var_20], eax
0x18001d662  lea     rax, aLicensingmodei_0; "LicensingModeIntegrityCheck::EVD SKU"
0x18001d669  jmp     short loc_18001D6E3
0x18001d66b  test    esi, esi
0x18001d66d  js      loc_18001D78E
0x18001d673  cmp     [rbp+var_30], 0
0x18001d677  jz      loc_18001D78E
0x18001d67d  mov     eax, [rbp+Data]
0x18001d680  cmp     eax, 7
0x18001d683  ja      short loc_18001D6B7
0x18001d685  mov     ecx, 0B4h
0x18001d68a  bt      ecx, eax
0x18001d68d  jnb     short loc_18001D6B7
0x18001d68f  mov     eax, cs:dword_180084170
0x18001d695  cmp     eax, 5
0x18001d698  jbe     loc_18001D7D1
0x18001d69e  mov     eax, [rbp+Data]
0x18001d6a1  lea     rdx, word_180078952
0x18001d6a8  mov     dword ptr [rbp+arg_18], eax
0x18001d6ab  lea     rax, aLicensingmodei_5; "LicensingModeIntegrityCheck::Server SKU"...
0x18001d6b2  jmp     loc_18001D7AD
0x18001d6b7  mov     eax, cs:dword_180084170
0x18001d6bd  mov     [rbp+arg_8], 5
0x18001d6c4  cmp     eax, 4
0x18001d6c7  jbe     short loc_18001D707
0x18001d6c9  mov     eax, [rbp+arg_8]
0x18001d6cc  lea     rdx, byte_180078915
0x18001d6d3  mov     dword ptr [rbp+arg_18], eax
0x18001d6d6  mov     eax, [rbp+Data]
0x18001d6d9  mov     dword ptr [rbp+var_20], eax
0x18001d6dc  lea     rax, aLicensingmodei_6; "LicensingModeIntegrityCheck::Server SKU"...
0x18001d6e3  mov     [rbp+var_10], rax
0x18001d6e7  lea     rax, [rbp+arg_18]
0x18001d6eb  mov     [rsp+80h+lpSecurityAttributes], rax
0x18001d6f0  lea     rax, [rbp+var_20]
0x18001d6f4  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d6f9  lea     rax, [rbp+var_10]
0x18001d6fd  mov     qword ptr [rsp+80h+dwOptions], rax
0x18001d702  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d707  mov     rcx, [rbp+hKey]; hKey
0x18001d70b  lea     rax, [rbp+arg_8]
0x18001d70f  mov     [rsp+80h+samDesired], 4; cbData
0x18001d717  lea     rdx, aLicensingmode; "LicensingMode"
0x18001d71e  mov     r9d, 4; dwType
0x18001d724  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18001d729  xor     r8d, r8d; Reserved
0x18001d72c  call    cs:__imp_RegSetValueExW
0x18001d732  test    eax, eax
0x18001d734  jz      short loc_18001D758
0x18001d736  mov     ecx, cs:dword_180084170
0x18001d73c  cmp     ecx, 3
0x18001d73f  jbe     loc_18001D7D1
0x18001d745  mov     dword ptr [rbp+arg_18], eax
0x18001d748  lea     rdx, byte_1800788B7
0x18001d74f  lea     rax, aLicensingmodei_3; "LicensingModeIntegrityCheck::Setting re"...
0x18001d756  jmp     short loc_18001D7AD
0x18001d758  mov     eax, cs:dword_180084170
0x18001d75e  cmp     eax, 5
0x18001d761  jbe     short loc_18001D7D1
0x18001d763  lea     rax, aLicensingmodei_4; "LicensingModeIntegrityCheck::SetSuccess"...
0x18001d76a  xor     r9d, r9d
0x18001d76d  mov     [rbp+arg_18], rax
0x18001d771  lea     rdx, byte_180078899
0x18001d778  lea     rax, [rbp+arg_18]
0x18001d77c  xor     r8d, r8d
0x18001d77f  mov     rcx, rbx
0x18001d782  mov     qword ptr [rsp+80h+dwOptions], rax
0x18001d787  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001d78c  jmp     short loc_18001D7D1
0x18001d78e  mov     eax, cs:dword_180084170
0x18001d794  cmp     eax, 5
0x18001d797  jbe     short loc_18001D7D1
0x18001d799  mov     eax, [rbp+Data]
0x18001d79c  lea     rdx, byte_1800788E5
0x18001d7a3  mov     dword ptr [rbp+arg_18], eax
0x18001d7a6  lea     rax, aLicensingmodei_9; "LicensingModeIntegrityCheck::Taking no "...
0x18001d7ad  mov     [rbp+var_10], rax
0x18001d7b1  lea     rax, [rbp+arg_18]
0x18001d7b5  mov     qword ptr [rsp+80h+samDesired], rax
0x18001d7ba  lea     rax, [rbp+var_10]
0x18001d7be  mov     rcx, rbx
0x18001d7c1  xor     r9d, r9d
0x18001d7c4  mov     qword ptr [rsp+80h+dwOptions], rax
0x18001d7c9  xor     r8d, r8d
0x18001d7cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001d7d1  mov     rcx, [rbp+hKey]; hKey
0x18001d7d5  test    rcx, rcx
0x18001d7d8  jz      short loc_18001D7E0
0x18001d7da  call    cs:__imp_RegCloseKey
0x18001d7e0  add     rsp, 80h
0x18001d7e7  pop     r14
0x18001d7e9  pop     rdi
0x18001d7ea  pop     rsi
0x18001d7eb  pop     rbx
0x18001d7ec  pop     rbp
0x18001d7ed  retn
```

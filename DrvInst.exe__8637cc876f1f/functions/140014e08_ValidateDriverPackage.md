# ValidateDriverPackage

- ea: `0x140014e08`
- end: `0x140015f00`
- name: `ValidateDriverPackage`
- size: `4344`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int16, WCHAR *, const WCHAR *, __int64, __int64, int, int, unsigned __int16 *, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013220`

## callees

- `0x1400070bc`
- `0x14000bcbc`
- `0x14000c7a0`
- `0x140014238`
- `0x1400144d0`
- `0x140014e08`
- `0x140015f08`
- `0x14002c9a8`
- `0x14002e700`
- `0x14002ea10`
- `0x14002eaa0`
- `0x14002f084`
- `0x1400346cc`
- `0x140037be4`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1400150b4`
- `ntdll!NtQuerySystemInformation` at `0x1400150b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015392`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140015193`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140015193`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400151ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400151ac`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f0c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f47`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f8a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015073`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001510a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001523c`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400152ae`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001530c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015367`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400153d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400153e9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001547b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015496`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400154c3`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400154fd`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015557`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001557d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001562b`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001564e`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400156b0`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015732`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015744`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015771`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015792`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400157b1`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400157f0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001587b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400158a2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015909`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001593b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015a69`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015a8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ab9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ad9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015af6`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015b24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ccc`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ce9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015da8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015dc8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015de5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015e29`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015e97`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ee4`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f0c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f47`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014f8a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015073`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001510a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001523c`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400152ae`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001530c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015367`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400153d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400153e9`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001547b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015496`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400154c3`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400154fd`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015557`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001557d`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001562b`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001564e`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400156b0`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015732`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015744`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015771`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015792`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400157b1`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400157f0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001587b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400158a2`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015909`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001593b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015a69`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015a8c`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ab9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ad9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015af6`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015b24`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ccc`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ce9`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015da8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015dc8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015de5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015e29`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015e97`
- `DEVRTL!DevRtlWriteTextLog` at `0x140015ee4`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014e9e`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140014e9e`
- `WINTRUST!CryptCATOpen` at `0x140014f5c`
- `WINTRUST!CryptCATOpen` at `0x140014f5c`
- `WINTRUST!CryptCATClose` at `0x140015257`
- `WINTRUST!CryptCATClose` at `0x140015257`

## string_xrefs

- `0x140014f75`: `Unable to pre-open handle to catalog file. Error = 0x%08X`
- `0x140015b06`: `Driver package is test signed in test signing mode, and may not pass hardware certification requirements, but user wants to install anyway.`
- `0x140015b12`: `Driver package is unsigned or test signed, and Code Integrity enforcement is off, and may not pass hardware certification requirements, but user wants to install anyway.`
- `0x140015a62`: `Driver package is test signed in test signing mode, and may not pass hardware certification requirements, and user does not want to install driver package.`
- `0x140015a7e`: `Driver package is unsigned or test signed, and Code Integrity enforcement is off, and may not pass hardware certification requirements, and user does not want to install driver package.`
- `0x14001549c`: `Assuming that user does not want to install driver package.`
- `0x14001574a`: `Assuming that user does not want to install driver package.`
- `0x140015881`: `Assuming that user does not want to install driver package.`
- `0x140015ae4`: `Assuming that user does not want to install driver package.`
- `0x140015dd3`: `Assuming that user does not want to install driver package.`
- `0x140015cf8`: `Driver package does not contain a catalog file, but user wants to install anyway.`
- `0x140015d09`: `Driver package catalog file certificate does not belong to Trusted Root Certificates, but user wants to install anyway.`
- `0x140015d1a`: `Driver package catalog file certificate does not belong to Trusted Test Root Certificates, but user wants to install anyway.`
- `0x140015d2b`: `Driver package catalog file certificate does not chain to a root, but user wants to install anyway.`
- `0x140015d34`: `Driver package does not contain a signature, but user wants to install anyway.`
- `0x140015d43`: `Driver package does not contain a valid catalog file, but user wants to install anyway.`
- `0x140015bff`: `Driver package does not contain a catalog file, and user does not want to install driver package.`
- `0x140015c16`: `Driver package catalog file certificate does not belong to Trusted Root Certificates, and user does not want to install driver package.`
- `0x140015c2d`: `Driver package catalog file certificate does not belong to Trusted Test Root Certificates, and user does not want to install driver package.`
- `0x140015c3e`: `Driver package catalog file certificate does not chain to a root, and user does not want to install driver package.`
- `0x140015c5a`: `Driver package catalog file does not contain a signature, and user does not want to install driver package.`
- `0x140015c66`: `Driver package does not contain a valid catalog file, and user does not want to install driver package.`
- `0x1400155f7`: `Driver package appears to be tampered, but user wants to install it anyway.`
- `0x140015761`: `Driver package appears to be tampered, but user wants to install it anyway.`
- `0x14001572b`: `Driver package appears to be tampered, and user does not want to install it.`
- `0x1400157bc`: `Driver package appears to be tampered, and it will not be installed.`
- `0x1400157fc`: `Driver package is considered unsigned, and Code Integrity is enforced.`
- `0x14001588d`: `Driver package is considered unsigned, but user wants to install driver package anyway.`
- `0x140015868`: `Driver package is considered unsigned, and user does not want to install driver package.`
- `0x140015874`: `Driver package is considered unsigned, and failed to display UI to inform user.`
- `0x1400158b0`: `Driver package is considered unsigned, and failed to inform user. Error = 0x%08X`
- `0x1400158cc`: `Driver package is considered unsigned, but error is ignored in WinPE.`
- `0x1400158d8`: `Driver package is considered unsigned.`

## pseudocode

```c
__int64 __fastcall ValidateDriverPackage(
        unsigned __int16 *a1,
        __int16 a2,
        WCHAR *a3,
        const WCHAR *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        unsigned __int16 *a9,
        _DWORD *a10)
{
  int v10; // ebx
  __int16 v12; // r13
  DWORD LastError; // edi
  __int64 ThreadLogToken; // rax
  __int64 v15; // rsi
  int IsCatalogFileValid; // eax
  int v17; // r13d
  __int64 FileTitle; // rax
  DWORD v19; // eax
  DWORD v20; // eax
  int v21; // eax
  int v22; // r12d
  unsigned int v23; // r14d
  int v24; // eax
  int v25; // r15d
  int v26; // r13d
  int v27; // eax
  int v28; // ecx
  __int64 v30; // rdx
  __int64 v31; // r12
  bool v32; // zf
  WCHAR *v33; // r15
  __int64 v34; // rax
  const WCHAR *i; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // r8
  DWORD v40; // eax
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  unsigned __int16 *v44; // rbx
  __int64 v45; // rax
  const char *v46; // r9
  __int64 v47; // rcx
  const char *v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rax
  int v51; // r8d
  DWORD v52; // eax
  const char *v53; // r9
  __int64 v54; // rax
  __int64 v55; // rax
  DWORD v56; // eax
  const char *v57; // r9
  const char *v58; // r9
  __int64 inited; // rax
  __int64 v60; // r14
  int v61; // ebx
  DWORD dwEncodingType[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwEncodingTypea[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwEncodingTypeb[2]; // [rsp+20h] [rbp-E0h]
  __int64 v65; // [rsp+28h] [rbp-D8h]
  __int64 v66; // [rsp+30h] [rbp-D0h]
  int v67; // [rsp+40h] [rbp-C0h] BYREF
  int v68; // [rsp+44h] [rbp-BCh]
  unsigned __int16 *v69; // [rsp+48h] [rbp-B8h]
  int v70; // [rsp+50h] [rbp-B0h]
  __int64 v71; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h]
  WCHAR *v73; // [rsp+68h] [rbp-98h]
  __int64 SystemInformation; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h]
  int v76; // [rsp+80h] [rbp-80h]
  HANDLE hCatalog; // [rsp+88h] [rbp-78h]
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  int v79; // [rsp+98h] [rbp-68h]
  int v80; // [rsp+9Ch] [rbp-64h]
  __int64 v81; // [rsp+A0h] [rbp-60h]
  __int16 v82; // [rsp+A8h] [rbp-58h]
  __int64 v83; // [rsp+AAh] [rbp-56h]
  __int16 v84; // [rsp+B2h] [rbp-4Eh]
  int v85; // [rsp+C0h] [rbp-40h] BYREF
  char v86[520]; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int16 v87[260]; // [rsp+2CCh] [rbp+1CCh] BYREF
  char v88[520]; // [rsp+4D4h] [rbp+3D4h] BYREF
  int v89; // [rsp+6DCh] [rbp+5DCh]

  v10 = 0;
  v12 = a2;
  v71 = a5;
  LastError = 0;
  v73 = a3;
  LOWORD(v68) = a2;
  v69 = a1;
  v75 = a6;
  lpFileName = a4;
  v70 = 0;
  v76 = 0;
  v67 = 0;
  memset_0(&v85, 0, 0x620u);
  hCatalog = (HANDLE)-1LL;
  ThreadLogToken = DevRtlGetThreadLogToken();
  *a9 = 0;
  v15 = ThreadLogToken;
  *a10 = 0x80000000;
  if ( !a3 )
    goto LABEL_19;
  v10 = pSetupFileExists(a3);
  if ( !v10 )
    goto LABEL_19;
  IsCatalogFileValid = SpSignIsCatalogFileValid(a3);
  v70 = IsCatalogFileValid;
  v17 = IsCatalogFileValid;
  if ( !IsCatalogFileValid )
  {
    LastError = GetLastError();
    FileTitle = pSetupGetFileTitle(a3);
    DevRtlWriteTextLog(
      v15,
      32,
      2,
      "Driver package catalog file is invalid. Catalog = %ws, Error = 0x%08X",
      FileTitle,
      LastError);
    DevRtlWriteTextLog(v15, 32, 2, "Assuming that driver package is not signed.");
LABEL_18:
    v12 = v68;
    goto LABEL_19;
  }
  v70 = IsCatalogFileValid;
  DevRtlWriteTextLog(v15, 32, 4, "Driver package catalog is valid.");
  hCatalog = CryptCATOpen(a3, 0, 0, 0, 0);
  if ( hCatalog == (HANDLE)-1LL )
  {
    v19 = GetLastError();
    DevRtlWriteTextLog(v15, 32, 2, "Unable to pre-open handle to catalog file. Error = 0x%08X", v19);
  }
  LastError = 0;
  if ( !(unsigned int)SpSignIsFileHashInCatalog(v69, a3, hCatalog) )
  {
    LastError = GetLastError();
    v70 = v17;
    goto LABEL_18;
  }
  v12 = v68;
  v82 = v68;
  v81 = 0;
  v83 = 0;
  v84 = 0;
  v79 = 28;
  v80 = 2;
  memset_0(v86, 0, 0x61Cu);
  v85 = 1568;
  if ( (unsigned int)VerifyInfFile(v69) || (v20 = GetLastError(), (LastError = v20) == 0) || v20 + 536870335 <= 1 )
  {
    if ( StringCchCopyW(a9, 0x104u, v87) < 0 )
      *a9 = 0;
    v21 = v89;
    if ( v89 != -16777216 )
      *a10 = v89;
    DevRtlWriteTextLog(
      v15,
      32,
      5,
      "Driver package is digitally signed by '%ws' (%ws). Signer Score = 0x%08X",
      v87,
      v88,
      v21);
  }
  v76 = 1;
LABEL_19:
  v22 = 0;
  SystemInformation = 8;
  if ( NtQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0) >= 0 )
  {
    if ( (SystemInformation & 0x100000000LL) != 0 )
      v23 = (~BYTE4(SystemInformation) & 2 | 4u) >> 1;
    else
      v23 = 1;
  }
  else
  {
    v23 = 0;
  }
  DevRtlWriteTextLog(v15, 32, 6, "Code Integrity State: %ws", pSpSignCodeIntegrityStateNames[v23]);
  if ( v12 && (v12 == 5 || v12 != 6 && v12 != 9) )
  {
    v68 = 1;
LABEL_30:
    LODWORD(SystemInformation) = 1;
    goto LABEL_31;
  }
  v68 = 0;
  v24 = IsExtensionDriverPackage(v69);
  LODWORD(SystemInformation) = 0;
  if ( v24 )
    goto LABEL_30;
LABEL_31:
  if ( ((LastError + 2146762487) & 0xFFFFFFFA) != 0 || (v25 = 1, LastError == -2146762482) )
    v25 = 0;
  phkResult = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &phkResult) )
  {
    if ( !a7 )
    {
      v26 = 1;
      goto LABEL_37;
    }
  }
  else
  {
    v22 = 1;
    RegCloseKey(phkResult);
  }
  v26 = 0;
LABEL_37:
  v27 = v70;
  if ( !v10 || !v70 || LastError == -2146885629 )
    goto LABEL_134;
  if ( LastError + 2146762496 <= 0xD )
  {
    v28 = 9729;
    if ( _bittest(&v28, LastError + 2146762496) )
    {
      v27 = v70;
LABEL_134:
      if ( v23 == 3 )
      {
        if ( !v10 )
        {
          DevRtlWriteTextLog(
            v15,
            32,
            1,
            "Driver package does not contain a catalog file, and Code Integrity is enforced.");
          goto LABEL_137;
        }
        switch ( LastError )
        {
          case 0x800B0109:
            v41 = "Driver package catalog file certificate does not belong to Trusted Root Certificates, and Code Integrity is enforced.";
            goto LABEL_140;
          case 0x800B010D:
            v41 = "Driver package catalog file certificate does not belong to Trusted Test Root Certificates, and Code In"
                  "tegrity is enforced.";
            goto LABEL_140;
          case 0x800B010A:
            v41 = "Driver package catalog file certificate does not chain to a root, and Code Integrity is enforced.";
            goto LABEL_140;
          case 0x800B0100:
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package catalog file does not contain a signature, and Code Integrity is enforced.");
            goto LABEL_47;
        }
        DevRtlWriteTextLog(
          v15,
          32,
          1,
          "Driver package does not contain a valid catalog file, and Code Integrity is enforced.");
LABEL_137:
        LastError = -536870353;
        goto LABEL_47;
      }
      if ( !v26 || !(_DWORD)SystemInformation || !a8 )
        goto LABEL_174;
      if ( v23 < 2 )
      {
LABEL_154:
        v31 = v71;
        v67 = 0;
        v56 = RequestClientSideUi(v71, v75, (_DWORD)v69, v10 != 0 ? (unsigned int)v73 : 0, 50, (__int64)&v67, v15);
        if ( !v56 )
        {
          if ( (unsigned int)(v67 - 1) <= 1 )
          {
            if ( !v25
              || (v48 = "Driver package is test signed in test signing mode, and may not pass hardware certification requ"
                        "irements, but user wants to install anyway.",
                  v23 != 2) )
            {
              v48 = "Driver package is unsigned or test signed, and Code Integrity enforcement is off, and may not pass h"
                    "ardware certification requirements, but user wants to install anyway.";
            }
            goto LABEL_127;
          }
          if ( !v67 )
          {
            if ( v25 && v23 == 2 )
            {
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package is test signed in test signing mode, and may not pass hardware certification requirements"
                ", and user does not want to install driver package.");
              LastError = -2146762483;
            }
            else
            {
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package is unsigned or test signed, and Code Integrity enforcement is off, and may not pass hardw"
                "are certification requirements, and user does not want to install driver package.");
              LastError = -2146762487;
            }
            goto LABEL_47;
          }
          if ( v25 && v23 == 2 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package is test signed in test signing mode, and may not pass hardware certification requirements, "
              "and failed to display UI to inform user.");
            LastError = -2146762483;
          }
          else
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package is unsigned or test signed, and Code Integrity enforcement is off, and may not pass hardwar"
              "e certification requirements, and failed to display UI to inform user.");
            LastError = -2146762487;
          }
LABEL_230:
          DevRtlWriteTextLog(v15, 32, 2, "Assuming that user does not want to install driver package.");
          goto LABEL_231;
        }
        v57 = "Driver package may not pass hardware certification requirements, and failed to inform user. Error = 0x%08X";
        if ( !LastError )
          LastError = v56;
LABEL_227:
        dwEncodingTypeb[0] = v56;
        DevRtlWriteTextLog(v15, 32, 1, v57, *(_QWORD *)dwEncodingTypeb);
        goto LABEL_230;
      }
      if ( v25 )
      {
        if ( v23 == 2 )
          goto LABEL_154;
      }
      else
      {
LABEL_174:
        if ( v23 == 2 )
        {
          if ( !v10 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package does not contain a catalog file, and Code Integrity is in Test Signing mode.");
            goto LABEL_137;
          }
          if ( !v27 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package does not contain a valid catalog file, and Code Integrity is in Test Signing mode.");
            goto LABEL_137;
          }
        }
        if ( !v26 )
        {
          if ( v22 )
          {
            if ( v10 )
            {
              if ( LastError == -2146762496 )
              {
                DevRtlWriteTextLog(v15, 32, 1, "Catalog file does not have a signature, but error is ignored in WinPE.");
              }
              else
              {
                v58 = "Catalog file is invalid, but error is ignored in WinPE.";
                if ( LastError != -2146885629 )
                  v58 = "Catalog signer is untrusted, but error is ignored in WinPE.";
                DevRtlWriteTextLog(v15, 32, 1, v58);
              }
            }
            else
            {
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package does not contain a catalog file, but error is ignored in WinPE.");
            }
            goto LABEL_238;
          }
          if ( !v10 || !v27 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package does not contain a catalog file. No error message will be displayed as client is running in"
              " non-interactive mode.");
            goto LABEL_137;
          }
          if ( LastError != -2146762496 )
          {
            if ( LastError == -2146885629 )
            {
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Catalog file is invalid. No error message will be displayed as client is running in non-interactive mode.");
            }
            else
            {
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Catalog signer is untrusted. No error message will be displayed as client is running in non-interactive mode.");
              LastError = -2146762487;
            }
            goto LABEL_47;
          }
          v41 = "Catalog file does not have a signature. No error message will be displayed as client is running in non-i"
                "nteractive mode.";
LABEL_140:
          v42 = 1;
          goto LABEL_112;
        }
      }
      v31 = v71;
      v67 = 0;
      v56 = RequestClientSideUi(v71, v75, (_DWORD)v69, v10 != 0 ? (unsigned int)v73 : 0, 10, (__int64)&v67, v15);
      if ( v56 )
      {
        if ( v10 )
        {
          switch ( LastError )
          {
            case 0x800B0109:
              v57 = "Driver package catalog file certificate does not belong to Trusted Root Certificates, and failed to "
                    "inform user. Error = 0x%08X";
              goto LABEL_227;
            case 0x800B010D:
              v57 = "Driver package catalog file certificate does not belong to Trusted Test Root Certificates, and faile"
                    "d to inform user. Error = 0x%08X";
              goto LABEL_227;
            case 0x800B010A:
              v57 = "Driver package catalog file certificate does not chain to a root, and failed to inform user. Error = 0x%08X";
              goto LABEL_227;
            case 0x800B0100:
              v57 = "Driver package catalog does not contain a signature, and failed to inform user. Error = 0x%08X";
              goto LABEL_227;
          }
        }
        DevRtlWriteTextLog(
          v15,
          32,
          1,
          "Driver package does not contain a catalog file, and failed to inform user. Error = 0x%08X",
          v56);
      }
      else
      {
        if ( (unsigned int)(v67 - 1) <= 1 )
        {
          if ( v10 )
          {
            switch ( LastError )
            {
              case 0x800B0109:
                v48 = "Driver package catalog file certificate does not belong to Trusted Root Certificates, but user wan"
                      "ts to install anyway.";
                break;
              case 0x800B010D:
                v48 = "Driver package catalog file certificate does not belong to Trusted Test Root Certificates, but use"
                      "r wants to install anyway.";
                break;
              case 0x800B010A:
                v48 = "Driver package catalog file certificate does not chain to a root, but user wants to install anyway.";
                break;
              default:
                v48 = "Driver package does not contain a signature, but user wants to install anyway.";
                if ( LastError != -2146762496 )
                  v48 = "Driver package does not contain a valid catalog file, but user wants to install anyway.";
                break;
            }
          }
          else
          {
            v48 = "Driver package does not contain a catalog file, but user wants to install anyway.";
          }
          goto LABEL_127;
        }
        if ( !v67 )
        {
          if ( !v10 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package does not contain a catalog file, and user does not want to install driver package.");
            goto LABEL_137;
          }
          switch ( LastError )
          {
            case 0x800B0109:
              v41 = "Driver package catalog file certificate does not belong to Trusted Root Certificates, and user does "
                    "not want to install driver package.";
              break;
            case 0x800B010D:
              v41 = "Driver package catalog file certificate does not belong to Trusted Test Root Certificates, and user "
                    "does not want to install driver package.";
              break;
            case 0x800B010A:
              v41 = "Driver package catalog file certificate does not chain to a root, and user does not want to install driver package.";
              break;
            case 0x800B0100:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package catalog file does not contain a signature, and user does not want to install driver package.");
              goto LABEL_47;
            default:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package does not contain a valid catalog file, and user does not want to install driver package.");
              goto LABEL_137;
          }
LABEL_188:
          v42 = 1;
          goto LABEL_112;
        }
        if ( v10 )
        {
          switch ( LastError )
          {
            case 0x800B0109:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package catalog file certificate does not belong to Trusted Root Certificates, and failed to disp"
                "lay UI to inform user.");
              goto LABEL_230;
            case 0x800B010D:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package catalog file certificate does not belong to Trusted Test Root Certificates, and failed to"
                " display UI to inform user.");
              goto LABEL_230;
            case 0x800B010A:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package catalog file certificate does not chain to a root, and failed to display UI to inform user.");
              goto LABEL_230;
            case 0x800B0100:
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package does not contain a signature, and failed to display UI to inform user.");
              goto LABEL_230;
          }
          DevRtlWriteTextLog(
            v15,
            32,
            1,
            "Driver package does not contain a valid catalog file, and failed to display UI to inform user.");
        }
        else
        {
          DevRtlWriteTextLog(
            v15,
            32,
            1,
            "Driver package does not contain a catalog file, and failed to display UI to inform user.");
        }
      }
      LastError = -536870353;
      goto LABEL_230;
    }
  }
  if ( LastError + 536870335 <= 1 && v68 && v23 == 3 )
  {
    if ( LastError == -536870335 )
    {
      DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is not trusted by system, and Code Integrity is enforced.");
      LastError = -536870333;
      goto LABEL_47;
    }
    DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is unknown, and Code Integrity is enforced.");
    v31 = v71;
    goto LABEL_231;
  }
  if ( LastError - 1 <= 0xE000023F )
  {
    v32 = LastError == -536870333;
  }
  else
  {
    v32 = LastError == -536870333;
    if ( LastError < 0xE0000243 )
    {
      v33 = v73;
      if ( lpFileName )
      {
        v34 = pSetupGetFileTitle(v73);
        DevRtlWriteTextLog(v15, 32, 5, "Validating driver package files against catalog '%ws'.", v34);
        for ( i = lpFileName; *i; lpFileName = i )
        {
          if ( (unsigned int)pSetupFileExists(i) )
          {
            if ( !(unsigned int)SpSignIsFileHashInCatalog(lpFileName, v73, hCatalog) )
            {
              LastError = GetLastError();
              pSetupGetFileTitle(v73);
              v38 = pSetupGetFileTitle(lpFileName);
              LODWORD(v66) = LastError;
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Failed to verify file '%ws' against catalog '%ws'. Error = 0x%08X",
                v38,
                v39,
                v66);
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Catalog did not contain file hash. File is likely corrupt or a victim of tampering.");
              break;
            }
            v36 = pSetupGetFileTitle(lpFileName);
            DevRtlWriteTextLog(v15, 32, 6, "Verified file '%ws'.", v36);
          }
          v37 = -1;
          do
            ++v37;
          while ( lpFileName[v37] );
          i = &lpFileName[v37 + 1];
        }
      }
      if ( !LastError || LastError == -536870335 )
      {
        DevRtlWriteTextLog(v15, 32, 5, "Driver package is valid.");
        v31 = v71;
        LastError = 0;
LABEL_231:
        if ( LastError )
          goto LABEL_47;
        v44 = v69;
        goto LABEL_241;
      }
      if ( LastError == -536870334 )
      {
        if ( v26 )
        {
          v31 = v71;
          v67 = 0;
          v40 = RequestClientSideUi(v71, v75, (_DWORD)v69, (_DWORD)v73, 20, (__int64)&v67, v15);
          if ( !v40 )
          {
            if ( (unsigned int)(v67 - 1) > 1 )
            {
              if ( !v67 )
              {
                DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is unknown, and user does not trust signer.");
                LastError = -536870333;
                goto LABEL_47;
              }
              DevRtlWriteTextLog(
                v15,
                32,
                1,
                "Driver package signer is unknown, and failed to display UI to inform user.");
              goto LABEL_76;
            }
            DevRtlWriteTextLog(v15, 32, 2, "Driver package signer is unknown, but user trusts signer.");
            if ( v67 == 2 )
              SpSignInstallCatalogCertificate(v33, v15);
            goto LABEL_239;
          }
          v43 = "Driver package signer is unknown, and failed to inform user. Error = 0x%08X";
          goto LABEL_80;
        }
        if ( !v22 )
        {
          DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is unknown. Assuming untrusted signer.");
          goto LABEL_47;
        }
        DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is unknown, but error is ignored in WinPE.");
LABEL_238:
        v31 = v71;
LABEL_239:
        v44 = v69;
        goto LABEL_240;
      }
      v44 = v69;
      v45 = pSetupGetFileTitle(v69);
      LODWORD(v65) = LastError;
      DevRtlWriteTextLog(v15, 32, 1, "Driver package appears to be tampered. Filename = %ws, Error = 0x%08X", v45, v65);
      if ( v68 && v23 == 3 )
      {
        v46 = "Driver package appears to be tampered, and Code Integrity is enforced.";
LABEL_87:
        DevRtlWriteTextLog(v15, 32, 1, v46);
        goto LABEL_47;
      }
      if ( v26 )
      {
        v31 = v71;
        v67 = 0;
        v40 = RequestClientSideUi(v71, v75, (_DWORD)v69, (_DWORD)v73, 10, (__int64)&v67, v15);
        if ( v40 )
        {
          v43 = "Driver package appears to be tampered, and failed to inform user. Error = 0x%08X";
LABEL_80:
          dwEncodingType[0] = v40;
          DevRtlWriteTextLog(v15, 32, 1, v43, *(_QWORD *)dwEncodingType);
LABEL_76:
          v41 = "Assuming that user does not want to install driver package.";
          v42 = 2;
LABEL_112:
          v47 = v15;
          goto LABEL_109;
        }
        if ( (unsigned int)(v67 - 1) > 1 )
        {
          v42 = 1;
          v47 = v15;
          if ( v67 )
          {
            DevRtlWriteTextLog(
              v15,
              32,
              1,
              "Driver package appears to be tampered, and failed to display UI to inform user.");
            goto LABEL_76;
          }
LABEL_108:
          v41 = "Driver package appears to be tampered, and user does not want to install it.";
LABEL_109:
          DevRtlWriteTextLog(v47, 32, v42, v41);
          goto LABEL_47;
        }
        v48 = "Driver package appears to be tampered, but user wants to install it anyway.";
        goto LABEL_127;
      }
      v49 = v15;
      if ( v22 )
        goto LABEL_96;
LABEL_117:
      DevRtlWriteTextLog(v49, 32, 1, "Driver package appears to be tampered, and it will not be installed.");
      goto LABEL_47;
    }
  }
  if ( v32 || LastError == -2146762479 )
  {
    v55 = pSetupGetFileTitle(v73);
    LODWORD(v65) = LastError;
    DevRtlWriteTextLog(v15, 32, 1, "Driver package signer is not trusted. Catalog = %ws, Error = 0x%08X", v55, v65);
    goto LABEL_47;
  }
  if ( LastError != -536870325 )
  {
    v54 = pSetupGetFileTitle(v73);
    LODWORD(v65) = LastError;
    DevRtlWriteTextLog(
      v15,
      32,
      1,
      "An unexpected error occurred while validating driver package. Catalog = %ws, Error = 0x%08X",
      v54,
      v65);
    if ( v23 == 3 )
    {
      v46 = "Driver package is considered unsigned, and Code Integrity is enforced.";
      goto LABEL_87;
    }
    if ( !v26 )
    {
      if ( !v22 )
      {
        DevRtlWriteTextLog(v15, 32, 1, "Driver package is considered unsigned.");
        goto LABEL_47;
      }
      DevRtlWriteTextLog(v15, 32, 1, "Driver package is considered unsigned, but error is ignored in WinPE.");
      goto LABEL_238;
    }
    v31 = v71;
    v67 = 0;
    v52 = RequestClientSideUi(v71, v75, (_DWORD)v69, (_DWORD)v73, 10, (__int64)&v67, v15);
    if ( v52 )
    {
      v53 = "Driver package is considered unsigned, and failed to inform user. Error = 0x%08X";
      goto LABEL_115;
    }
    if ( (unsigned int)(v67 - 1) > 1 )
    {
      if ( !v67 )
      {
        DevRtlWriteTextLog(
          v15,
          32,
          1,
          "Driver package is considered unsigned, and user does not want to install driver package.");
        goto LABEL_47;
      }
      DevRtlWriteTextLog(v15, 32, 1, "Driver package is considered unsigned, and failed to display UI to inform user.");
      v41 = "Assuming that user does not want to install driver package.";
      goto LABEL_188;
    }
    v48 = "Driver package is considered unsigned, but user wants to install driver package anyway.";
LABEL_127:
    DevRtlWriteTextLog(v15, 32, 2, v48);
    LastError = 0;
    goto LABEL_231;
  }
  v44 = v69;
  v50 = pSetupGetFileTitle(v69);
  LODWORD(v65) = v51;
  DevRtlWriteTextLog(
    v15,
    32,
    1,
    "Driver package INF file hash is not present in catalog file. Filename = %ws, Error = 0x%08X",
    v50,
    v65);
  if ( v23 == 3 )
  {
    v46 = "Driver package appears to be tampered, and Code Integrity is enforced.";
    goto LABEL_87;
  }
  if ( v26 )
  {
    v31 = v71;
    v67 = 0;
    v52 = RequestClientSideUi(v71, v75, (_DWORD)v69, (_DWORD)v73, 10, (__int64)&v67, v15);
    if ( !v52 )
    {
      if ( (unsigned int)(v67 - 1) <= 1 )
      {
        DevRtlWriteTextLog(v15, 32, 2, "Driver package appears to be tampered, but user wants to install it anyway.");
        goto LABEL_240;
      }
      v42 = 1;
      v47 = v15;
      if ( !v67 )
        goto LABEL_108;
      DevRtlWriteTextLog(v15, 32, 1, "Driver package appears to be tampered, and failed to display UI to inform user.");
LABEL_111:
      v41 = "Assuming that user does not want to install driver package.";
      v42 = 2;
      goto LABEL_112;
    }
    v53 = "Driver package appears to be tampered, and failed to inform user. Error = 0x%08X";
LABEL_115:
    dwEncodingTypea[0] = v52;
    DevRtlWriteTextLog(v15, 32, 1, v53, *(_QWORD *)dwEncodingTypea);
    goto LABEL_111;
  }
  v49 = v15;
  if ( !v22 )
    goto LABEL_117;
LABEL_96:
  DevRtlWriteTextLog(v49, 32, 1, "Driver package appears to be tampered, but error is ignored in WinPE.");
  v31 = v71;
LABEL_240:
  LastError = 0;
LABEL_241:
  inited = SdbInitDatabaseEx(2147745792LL, v30, 34404);
  v60 = inited;
  if ( inited )
  {
    v61 = pSpSignAreDriversInDirBlocked(v44, v31, inited);
    SdbReleaseDatabase(v60);
    if ( v61 == 1275 )
    {
      DevRtlWriteTextLog(v15, 32, 1, "Driver package contains a blocked driver file. Error = 0x%08X", 1275);
      LastError = 1275;
    }
  }
LABEL_47:
  if ( hCatalog != (HANDLE)-1LL )
    CryptCATClose(hCatalog);
  if ( v76 )
    SpSignFlushWVTCache();
  return LastError;
}

```

## disassembly

```asm
0x140014e08  push    rbp
0x140014e0a  push    rbx
0x140014e0b  push    rsi
0x140014e0c  push    rdi
0x140014e0d  push    r12
0x140014e0f  push    r13
0x140014e11  push    r14
0x140014e13  push    r15
0x140014e15  lea     rbp, [rsp-5F8h]
0x140014e1d  sub     rsp, 6F8h
0x140014e24  mov     rax, cs:__security_cookie
0x140014e2b  xor     rax, rsp
0x140014e2e  mov     [rbp+630h+var_50], rax
0x140014e35  mov     rax, [rbp+630h+arg_20]
0x140014e3c  xor     ebx, ebx
0x140014e3e  mov     r15, [rbp+630h+arg_40]
0x140014e45  mov     r14, r8
0x140014e48  mov     r12, [rbp+630h+arg_48]
0x140014e4f  movzx   r13d, dx
0x140014e53  mov     [rsp+730h+var_6D8], rax
0x140014e58  mov     edi, ebx
0x140014e5a  mov     rax, [rbp+630h+arg_28]
0x140014e61  mov     [rsp+730h+var_6C8], r8
0x140014e66  mov     r8d, 620h; Size
0x140014e6c  mov     word ptr [rsp+730h+var_6EC], dx
0x140014e71  xor     edx, edx; Val
0x140014e73  mov     [rsp+730h+var_6E8], rcx
0x140014e78  lea     rcx, [rbp+630h+var_670]; void *
0x140014e7c  mov     [rsp+730h+var_6B8], rax
0x140014e81  mov     [rsp+730h+lpFileName], r9
0x140014e86  mov     [rsp+730h+var_6E0], ebx
0x140014e8a  mov     [rbp+630h+var_6B0], ebx
0x140014e8d  mov     [rsp+730h+var_6F0], ebx
0x140014e91  call    memset_0
0x140014e96  mov     [rbp+630h+hCatalog], 0FFFFFFFFFFFFFFFFh
0x140014e9e  call    cs:__imp_DevRtlGetThreadLogToken
0x140014ea4  mov     [r15], bx
0x140014ea8  mov     rsi, rax
0x140014eab  mov     dword ptr [r12], 80000000h
0x140014eb3  test    r14, r14
0x140014eb6  jz      loc_140015095
0x140014ebc  mov     rcx, r14; lpFileName
0x140014ebf  call    pSetupFileExists
0x140014ec4  mov     ebx, eax
0x140014ec6  test    eax, eax
0x140014ec8  jz      loc_140015095
0x140014ece  mov     rcx, r14; pvObject
0x140014ed1  call    SpSignIsCatalogFileValid
0x140014ed6  mov     [rsp+730h+var_6E0], eax
0x140014eda  mov     r13d, eax
0x140014edd  test    eax, eax
0x140014edf  jnz     short loc_140014F2F
0x140014ee1  call    cs:__imp_GetLastError
0x140014ee7  mov     rcx, r14
0x140014eea  mov     edi, eax
0x140014eec  call    pSetupGetFileTitle
0x140014ef1  lea     edx, [r13+20h]
0x140014ef5  mov     dword ptr [rsp+730h+var_708], edi
0x140014ef9  mov     rcx, rsi
0x140014efc  mov     qword ptr [rsp+730h+dwEncodingType], rax
0x140014f01  lea     r9, aDriverPackageC_20; "Driver package catalog file is invalid."...
0x140014f08  lea     r8d, [r13+2]
0x140014f0c  call    cs:__imp_DevRtlWriteTextLog
0x140014f12  lea     r9, aAssumingThatDr; "Assuming that driver package is not sig"...
0x140014f19  mov     rcx, rsi
0x140014f1c  lea     edx, [r13+20h]
0x140014f20  lea     r8d, [r13+2]
0x140014f24  call    cs:__imp_DevRtlWriteTextLog
0x140014f2a  jmp     loc_14001508F
0x140014f2f  mov     edx, 20h ; ' '
0x140014f34  mov     [rsp+730h+var_6E0], r13d
0x140014f39  lea     r9, aDriverPackageC_18; "Driver package catalog is valid."
0x140014f40  mov     rcx, rsi
0x140014f43  lea     r8d, [rdx-1Ch]
0x140014f47  call    cs:__imp_DevRtlWriteTextLog
0x140014f4d  xor     r9d, r9d; dwPublicVersion
0x140014f50  mov     [rsp+730h+dwEncodingType], edi; dwEncodingType
0x140014f54  xor     r8d, r8d; hProv
0x140014f57  xor     edx, edx; fdwOpenFlags
0x140014f59  mov     rcx, r14; pwszFileName
0x140014f5c  call    cs:__imp_CryptCATOpen
0x140014f62  mov     [rbp+630h+hCatalog], rax
0x140014f66  mov     rdi, rax
0x140014f69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014f6d  jnz     short loc_140014F90
0x140014f6f  call    cs:__imp_GetLastError
0x140014f75  lea     r9, aUnableToPreOpe; "Unable to pre-open handle to catalog fi"...
0x140014f7c  mov     rcx, rsi
0x140014f7f  lea     edx, [rdi+21h]
0x140014f82  mov     [rsp+730h+dwEncodingType], eax
0x140014f86  lea     r8d, [rdi+3]
0x140014f8a  call    cs:__imp_DevRtlWriteTextLog
0x140014f90  mov     rdx, r14
0x140014f93  mov     r8, rdi
0x140014f96  mov     r14, [rsp+730h+var_6E8]
0x140014f9b  mov     rcx, r14
0x140014f9e  call    SpSignIsFileHashInCatalog
0x140014fa3  xor     edi, edi
0x140014fa5  test    eax, eax
0x140014fa7  jz      loc_140015082
0x140014fad  movzx   r13d, word ptr [rsp+730h+var_6EC]
0x140014fb3  lea     rcx, [rbp+630h+var_66C]; void *
0x140014fb7  xor     edx, edx; Val
0x140014fb9  mov     [rbp+630h+var_688], r13w
0x140014fbe  mov     r8d, 61Ch; Size
0x140014fc4  mov     [rbp+630h+var_690], rdi
0x140014fc8  mov     [rbp+630h+var_686], rdi
0x140014fcc  mov     [rbp+630h+var_67E], di
0x140014fd0  mov     [rbp+630h+var_698], 1Ch
0x140014fd7  mov     [rbp+630h+var_694], 2
0x140014fde  call    memset_0
0x140014fe3  lea     r8, [rbp+630h+var_670]
0x140014fe7  mov     [rbp+630h+var_670], 620h
0x140014fee  lea     rdx, [rbp+630h+var_698]
0x140014ff2  mov     rcx, r14; unsigned __int16 *
0x140014ff5  call    VerifyInfFile
0x140014ffa  xor     r14d, r14d
0x140014ffd  test    eax, eax
0x140014fff  jnz     short loc_140015017
0x140015001  call    cs:__imp_GetLastError
0x140015007  mov     edi, eax
0x140015009  test    eax, eax
0x14001500b  jz      short loc_140015017
0x14001500d  add     eax, 1FFFFDBFh
0x140015012  cmp     eax, 1
0x140015015  ja      short loc_140015079
0x140015017  lea     r8, [rbp+630h+var_464]; unsigned __int16 *
0x14001501e  mov     edx, 104h; unsigned __int64
0x140015023  mov     rcx, r15; unsigned __int16 *
0x140015026  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001502b  test    eax, eax
0x14001502d  jns     short loc_140015033
0x14001502f  mov     [r15], r14w
0x140015033  mov     eax, [rbp+630h+var_54]
0x140015039  cmp     eax, 0FF000000h
0x14001503e  jz      short loc_140015044
0x140015040  mov     [r12], eax
0x140015044  mov     dword ptr [rsp+730h+var_700], eax
0x140015048  lea     r9, aDriverPackageI_4; "Driver package is digitally signed by '"...
0x14001504f  mov     edx, 20h ; ' '
0x140015054  lea     rax, [rbp+630h+var_25C]
0x14001505b  mov     [rsp+730h+var_708], rax
0x140015060  mov     rcx, rsi
0x140015063  lea     rax, [rbp+630h+var_464]
0x14001506a  mov     qword ptr [rsp+730h+dwEncodingType], rax
0x14001506f  lea     r8d, [rdx-1Bh]
0x140015073  call    cs:__imp_DevRtlWriteTextLog
0x140015079  mov     [rbp+630h+var_6B0], 1
0x140015080  jmp     short loc_140015095
0x140015082  call    cs:__imp_GetLastError
0x140015088  mov     edi, eax
0x14001508a  mov     [rsp+730h+var_6E0], r13d
0x14001508f  movzx   r13d, word ptr [rsp+730h+var_6EC]
0x140015095  xor     r12d, r12d
0x140015098  lea     rdx, [rsp+730h+SystemInformation]; SystemInformation
0x14001509d  mov     [rsp+730h+SystemInformation], r12
0x1400150a2  xor     r9d, r9d; ReturnLength
0x1400150a5  lea     r8d, [r12+8]; SystemInformationLength
0x1400150aa  lea     ecx, [r12+67h]; SystemInformationClass
0x1400150af  mov     dword ptr [rsp+730h+SystemInformation], r8d
0x1400150b4  call    cs:__imp_NtQuerySystemInformation
0x1400150ba  test    eax, eax
0x1400150bc  jns     short loc_1400150C3
0x1400150be  mov     r14d, r12d
0x1400150c1  jmp     short loc_1400150E4
0x1400150c3  mov     eax, dword ptr [rsp+730h+SystemInformation+4]
0x1400150c7  test    al, 1
0x1400150c9  jnz     short loc_1400150D3
0x1400150cb  mov     r14d, 1
0x1400150d1  jmp     short loc_1400150E4
0x1400150d3  not     al
0x1400150d5  movzx   r14d, al
0x1400150d9  and     r14d, 2
0x1400150dd  or      r14d, 4
0x1400150e1  shr     r14d, 1
0x1400150e4  mov     edx, 20h ; ' '
0x1400150e9  mov     eax, r14d
0x1400150ec  lea     rcx, pSpSignCodeIntegrityStateNames
0x1400150f3  lea     r9, aCodeIntegrityS; "Code Integrity State: %ws"
0x1400150fa  mov     rax, [rcx+rax*8]
0x1400150fe  lea     r8d, [rdx-1Ah]
0x140015102  mov     rcx, rsi
0x140015105  mov     qword ptr [rsp+730h+dwEncodingType], rax
0x14001510a  call    cs:__imp_DevRtlWriteTextLog
0x140015110  movzx   ecx, r13w
0x140015114  test    ecx, ecx
0x140015116  jz      short loc_140015131
0x140015118  sub     ecx, 5
0x14001511b  jz      short loc_140015127
0x14001511d  sub     ecx, 1
0x140015120  jz      short loc_140015131
0x140015122  cmp     ecx, 3
0x140015125  jz      short loc_140015131
0x140015127  mov     [rsp+730h+var_6EC], 1
0x14001512f  jmp     short loc_140015149
0x140015131  mov     rcx, [rsp+730h+var_6E8]
0x140015136  mov     [rsp+730h+var_6EC], r12d
0x14001513b  call    IsExtensionDriverPackage
0x140015140  mov     dword ptr [rsp+730h+SystemInformation], r12d
0x140015145  test    eax, eax
0x140015147  jz      short loc_140015151
0x140015149  mov     dword ptr [rsp+730h+SystemInformation], 1
0x140015151  lea     eax, [rdi+7FF4FEF7h]
0x140015157  test    eax, 0FFFFFFFAh
0x14001515c  jnz     short loc_14001516C
0x14001515e  mov     r15d, 1
0x140015164  cmp     edi, 800B010Eh
0x14001516a  jnz     short loc_14001516F
0x14001516c  mov     r15d, r12d
0x14001516f  lea     rax, [rbp+630h+phkResult]
0x140015173  mov     [rbp+630h+phkResult], r12
0x140015177  mov     r9d, 20019h; samDesired
0x14001517d  mov     qword ptr [rsp+730h+dwEncodingType], rax; phkResult
0x140015182  xor     r8d, r8d; ulOptions
0x140015185  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x14001518c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015193  call    cs:__imp_RegOpenKeyExW
0x140015199  xor     r8d, r8d
0x14001519c  test    eax, eax
0x14001519e  jnz     loc_14001528D
0x1400151a4  mov     rcx, [rbp+630h+phkResult]; hKey
0x1400151a8  lea     r12d, [r8+1]
0x1400151ac  call    cs:__imp_RegCloseKey
0x1400151b2  xor     r8d, r8d
0x1400151b5  mov     r13d, r8d
0x1400151b8  mov     edx, 1
0x1400151bd  mov     eax, [rsp+730h+var_6E0]
0x1400151c1  mov     r9d, 80092003h
0x1400151c7  test    ebx, ebx
0x1400151c9  jz      loc_140015918
0x1400151cf  test    eax, eax
0x1400151d1  jz      loc_140015918
0x1400151d7  cmp     edi, r9d
0x1400151da  jz      loc_140015918
0x1400151e0  lea     eax, [rdi+7FF4FF00h]
0x1400151e6  cmp     eax, 0Dh
0x1400151e9  ja      short loc_1400151F9
0x1400151eb  mov     ecx, 2601h
0x1400151f0  bt      ecx, eax
0x1400151f3  jb      loc_140015914
0x1400151f9  lea     eax, [rdi+1FFFFDBFh]
0x1400151ff  mov     r15d, 1
0x140015205  cmp     eax, r15d
0x140015208  ja      loc_1400152C1
0x14001520e  cmp     [rsp+730h+var_6EC], r8d
0x140015213  jz      loc_1400152C1
0x140015219  cmp     r14d, 3
0x14001521d  jnz     loc_1400152C1
0x140015223  lea     edx, [r15+1Fh]
0x140015227  mov     r8d, r15d
0x14001522a  mov     rcx, rsi
0x14001522d  cmp     edi, 0E0000241h
0x140015233  jnz     short loc_1400152A7
0x140015235  lea     r9, aDriverPackageS_6; "Driver package signer is not trusted by"...
0x14001523c  call    cs:__imp_DevRtlWriteTextLog
0x140015242  mov     edi, 0E0000243h
0x140015247  xor     r14d, r14d
0x14001524a  mov     rax, [rbp+630h+hCatalog]
0x14001524e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015252  jz      short loc_14001525D
0x140015254  mov     rcx, rax; hCatalog
0x140015257  call    cs:__imp_CryptCATClose
0x14001525d  cmp     [rbp+630h+var_6B0], r14d
0x140015261  jz      short loc_140015268
0x140015263  call    SpSignFlushWVTCache
0x140015268  mov     eax, edi
0x14001526a  mov     rcx, [rbp+630h+var_50]
0x140015271  xor     rcx, rsp; StackCookie
0x140015274  call    __security_check_cookie
0x140015279  add     rsp, 6F8h
0x140015280  pop     r15
0x140015282  pop     r14
0x140015284  pop     r13
0x140015286  pop     r12
0x140015288  pop     rdi
0x140015289  pop     rsi
0x14001528a  pop     rbx
0x14001528b  pop     rbp
0x14001528c  retn
0x14001528d  cmp     [rbp+630h+arg_30], r8d
0x140015294  jnz     loc_1400151B5
0x14001529a  mov     edx, 1
0x14001529f  mov     r13d, edx
0x1400152a2  jmp     loc_1400151BD
0x1400152a7  lea     r9, aDriverPackageS_5; "Driver package signer is unknown, and C"...
0x1400152ae  call    cs:__imp_DevRtlWriteTextLog
0x1400152b4  mov     r12, [rsp+730h+var_6D8]
0x1400152b9  xor     r14d, r14d
0x1400152bc  jmp     loc_140015DEB
0x1400152c1  lea     eax, [rdi-1]
0x1400152c4  mov     ebx, 0E0000243h
0x1400152c9  cmp     eax, 0E000023Fh
0x1400152ce  jbe     loc_140015664
0x1400152d4  cmp     edi, ebx
0x1400152d6  jnb     loc_140015666
0x1400152dc  mov     r15, [rsp+730h+var_6C8]
0x1400152e1  cmp     [rsp+730h+lpFileName], r8
0x1400152e6  jz      loc_1400153EF
0x1400152ec  mov     rcx, r15
0x1400152ef  call    pSetupGetFileTitle
  ... truncated ...
```

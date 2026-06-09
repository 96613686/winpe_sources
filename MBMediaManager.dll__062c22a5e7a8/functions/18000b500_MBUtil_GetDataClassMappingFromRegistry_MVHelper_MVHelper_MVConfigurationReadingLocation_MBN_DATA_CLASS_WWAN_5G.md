# MBUtil::_GetDataClassMappingFromRegistry(MVHelper &,MVHelper::_MVConfigurationReadingLocation,MBN_DATA_CLASS,_WWAN_5G_FREQUENCY_RANGE,ushort * *)

- ea: `0x18000b500`
- end: `0x18000bccf`
- name: `?_GetDataClassMappingFromRegistry@MBUtil@@CAJAEAVMVHelper@@W4_MVConfigurationReadingLocation@2@W4MBN_DATA_CLASS@@W4_WWAN_5G_FREQUENCY_RANGE@@PEAPEAG@Z`
- size: `1999`
- prototype: `__int64 __fastcall(MVHelper *, int, int, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18000e538`

## callees

- `0x18000ad20`
- `0x18000b500`
- `0x18000bde0`
- `0x180014490`
- `0x180025054`
- `0x18002cd20`
- `0x18002d934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bba5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bba5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc16`
- `MobileNetworking!GetPersistentRegPath` at `0x18000b9ee`
- `MobileNetworking!GetPersistentRegPath` at `0x18000b9ee`

## string_xrefs

- `0x18000b590`: `DataClassMappingTable`
- `0x18000b5bc`: `DataClassMappingTable`
- `0x18000b5e8`: `DataClassMappingTable`
- `0x18000b614`: `DataClassMappingTable`
- `0x18000b651`: `DataClassMappingTable`
- `0x18000b6d7`: `DataClassMappingTable`
- `0x18000b703`: `DataClassMappingTable`
- `0x18000b722`: `DataClassMappingTable`
- `0x18000b7da`: `DataClassMappingTable`
- `0x18000b806`: `DataClassMappingTable`
- `0x18000b832`: `DataClassMappingTable`
- `0x18000b85e`: `DataClassMappingTable`
- `0x18000b90d`: `DataClassMappingTable`
- `0x18000b939`: `DataClassMappingTable`
- `0x18000b965`: `DataClassMappingTable`
- `0x18000b99c`: `DataClassMappingTable`
- `0x18000bbee`: `DataClassMappingTable`
- `0x18000bc31`: `GetStringValue Succeeded. readLocation=%d, wszName=%ls, wstrValue=%ls`
- `0x18000b8af`: `MBUtil::_GetDataClassMappingFromRegistry`
- `0x18000b8d3`: `MBUtil::_GetDataClassMappingFromRegistry`
- `0x18000b8c7`: `Could not map data class. DataClass=%d, HRESULT=0x%x`
- `0x18000bc62`: `GetStringValue Error. wszName=%ls, dwReadingRule=%d, HRESULT=0x%x`
- `0x18000bbcc`: `Asking for per-ICCID value but ICCID is not ready yet.`
- `0x18000ba45`: `\IMSISpecific`
- `0x18000ba2b`: `\IMSISpecific\Default`
- `0x18000ba4e`: `Asking for per-IMSI value of IMSI is not ready yet.`
- `0x18000b8a3`: `Data class not recognised. DataClass=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall MBUtil::_GetDataClassMappingFromRegistry(
        MVHelper *a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v5; // rbx
  unsigned __int64 v9; // rdx
  SIZE_T v10; // rcx
  int StringValue; // ebx
  __int64 v12; // r9
  const WCHAR *v13; // rdx
  __int64 v14; // r9
  const WCHAR *v15; // rdx
  char i; // r14
  int v18; // edi
  int PersistentRegPath; // eax
  const wchar_t *v20; // rax
  HKEY v21; // r12
  DWORD LastError; // ebx
  LSTATUS v23; // eax
  LSTATUS v24; // eax
  unsigned __int64 v25; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 **v31; // [rsp+48h] [rbp-B8h]
  wchar_t Data[512]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[512]; // [rsp+450h] [rbp+350h] BYREF

  v5 = a5;
  v31 = a5;
  if ( a3 != 32 )
  {
    if ( a3 > 128 )
    {
      if ( a3 > 0x80000 )
      {
        switch ( a3 )
        {
          case 0x100000:
            StringValue = MVHelper::GetStringValue(a1, L"3XRTT", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x200000:
            StringValue = MVHelper::GetStringValue(a1, L"1XEVDO_REVB", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x400000:
            StringValue = MVHelper::GetStringValue(a1, L"UMB", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
        }
      }
      else
      {
        switch ( a3 )
        {
          case 0x80000:
            StringValue = MVHelper::GetStringValue(a1, L"1XEVDV", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x10000:
            StringValue = MVHelper::GetStringValue(a1, L"1XRTT", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x20000:
            StringValue = MVHelper::GetStringValue(a1, L"1XEVDO", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x40000:
            StringValue = MVHelper::GetStringValue(a1, L"1XEVDO_REVA", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
        }
      }
      goto LABEL_46;
    }
    if ( a3 != 128 )
    {
      if ( a3 <= 4 )
      {
        switch ( a3 )
        {
          case 4:
            StringValue = MVHelper::GetStringValue(a1, L"UMTS", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 0x80000000:
            StringValue = MVHelper::GetStringValue(a1, L"CUSTOM", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 1:
            StringValue = MVHelper::GetStringValue(a1, L"GPRS", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          case 2:
            StringValue = MVHelper::GetStringValue(a1, L"EDGE", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
        }
LABEL_46:
        MBSettingUXLogging::Warn(
          "MBUtil::_GetDataClassMappingFromRegistry",
          0x1EDu,
          "Data class not recognised. DataClass=%d",
          a3);
        StringValue = -2147467259;
        goto LABEL_47;
      }
      if ( a3 == 8 )
      {
        StringValue = MVHelper::GetStringValue(a1, L"HSDPA", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
        goto LABEL_87;
      }
      if ( a3 == 16 )
      {
        StringValue = MVHelper::GetStringValue(a1, L"HSUPA", a2, a4, L"DataClassMappingTable", (BYTE *)Data);
        goto LABEL_87;
      }
      if ( a3 != 64 )
        goto LABEL_46;
      v12 = (unsigned int)(a4 - 1);
      if ( (_DWORD)v12 )
      {
        v12 = (unsigned int)(v12 - 1);
        if ( (_DWORD)v12 )
        {
          if ( (_DWORD)v12 != 1 )
          {
LABEL_23:
            StringValue = MVHelper::GetStringValue(a1, L"5G_NSA", a2, v12, L"DataClassMappingTable", (BYTE *)Data);
            goto LABEL_87;
          }
          v13 = L"5G_NSA_FR1_FR2";
        }
        else
        {
          v13 = L"5G_NSA_FR2";
        }
      }
      else
      {
        v13 = L"5G_NSA_FR1";
      }
      if ( (int)MVHelper::GetStringValue(a1, v13, a2, v12, L"DataClassMappingTable", (BYTE *)Data) < 0 )
        goto LABEL_23;
LABEL_89:
      v25 = -1;
      do
        ++v25;
      while ( Data[v25] );
      return _AllocStringWorker<CTCoAllocPolicy>(v10, v9, Data, v25, (__int64)phkResult, v5);
    }
    v14 = (unsigned int)(a4 - 1);
    if ( (_DWORD)v14 )
    {
      v14 = (unsigned int)(v14 - 1);
      if ( (_DWORD)v14 )
      {
        if ( (_DWORD)v14 != 1 )
          goto LABEL_33;
        v15 = L"5G_SA_FR1_FR2";
      }
      else
      {
        v15 = L"5G_SA_FR2";
      }
    }
    else
    {
      v15 = L"5G_SA_FR1";
    }
    if ( (int)MVHelper::GetStringValue(a1, v15, a2, v14, L"DataClassMappingTable", (BYTE *)Data) >= 0 )
      goto LABEL_89;
LABEL_33:
    StringValue = MVHelper::GetStringValue(a1, L"5G_SA", a2, v14, L"DataClassMappingTable", (BYTE *)Data);
    goto LABEL_87;
  }
  StringValue = -2147023728;
  for ( i = 0; ; ++i )
  {
    v18 = a2 & (15 << (4 * i));
    if ( !v18 )
    {
      MBSettingUXLogging::Warn(
        "MVHelper::GetStringValue",
        0xB2u,
        "GetStringValue Error. wszName=%ls, dwReadingRule=%d, HRESULT=0x%x",
        L"LTE",
        a2,
        StringValue);
      goto LABEL_87;
    }
    cbData = 512;
    Type = 0;
    v29 = 512;
    hKey = 0;
    PersistentRegPath = GetPersistentRegPath(1, 0, &v29, Buffer);
    StringValue = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      StringValue = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( StringValue >= 0 )
      break;
LABEL_81:
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v18 != 4 )
  {
    if ( v18 == 1 )
    {
      v20 = L"\\DeviceSpecific";
LABEL_66:
      swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, v20);
      goto LABEL_69;
    }
    if ( v18 != 2 )
    {
      if ( v18 != 8 )
      {
        StringValue = -2147024809;
        goto LABEL_81;
      }
      v20 = L"\\IMSISpecific\\Default";
      goto LABEL_66;
    }
    if ( *((_WORD *)a1 + 22) )
    {
      swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\IMSISpecific", (char *)a1 + 44);
      goto LABEL_69;
    }
    MBSettingUXLogging::Warn(
      "MVHelper::GetRegKeyHandleAndName",
      0xDCu,
      "Asking for per-IMSI value of IMSI is not ready yet.");
LABEL_80:
    StringValue = -2147023728;
    goto LABEL_81;
  }
  if ( !*(_WORD *)a1 )
  {
    MBSettingUXLogging::Warn(
      "MVHelper::GetRegKeyHandleAndName",
      0xD1u,
      "Asking for per-ICCID value but ICCID is not ready yet.");
    goto LABEL_80;
  }
  swprintf_s(Buffer, 0x200u, L"%s%s\\%s", Buffer, L"\\ICCIDSpecific", a1);
LABEL_69:
  swprintf_s(Buffer, 0x200u, L"%s%s", Buffer, L"\\CellUX");
  swprintf_s(Buffer, 0x200u, L"%s\\%s", Buffer, L"DataClassMappingTable");
  v21 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v21);
    SetLastError(LastError);
  }
  hKey = 0;
  v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey);
  StringValue = v23;
  if ( v23 > 0 )
    StringValue = (unsigned __int16)v23 | 0x80070000;
  if ( StringValue < 0 )
    goto LABEL_81;
  v24 = RegQueryValueExW(hKey, L"LTE", 0, &Type, (LPBYTE)Data, &cbData);
  StringValue = v24;
  if ( v24 > 0 )
    StringValue = (unsigned __int16)v24 | 0x80070000;
  if ( StringValue < 0 )
    goto LABEL_81;
  if ( Type != 1 )
  {
    StringValue = -2147418113;
    goto LABEL_81;
  }
  if ( hKey )
    RegCloseKey(hKey);
  MBSettingUXLogging::Info(
    "MVHelper::GetStringValue",
    0xAEu,
    "GetStringValue Succeeded. readLocation=%d, wszName=%ls, wstrValue=%ls",
    v18,
    L"LTE",
    Data);
LABEL_87:
  if ( StringValue >= 0 )
  {
    v5 = v31;
    goto LABEL_89;
  }
LABEL_47:
  MBSettingUXLogging::Warn(
    "MBUtil::_GetDataClassMappingFromRegistry",
    0x1F8u,
    "Could not map data class. DataClass=%d, HRESULT=0x%x",
    a3,
    StringValue);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18000b500  push    rbp
0x18000b502  push    rbx
0x18000b503  push    rsi
0x18000b504  push    rdi
0x18000b505  push    r13
0x18000b507  push    r15
0x18000b509  lea     rbp, [rsp-768h]
0x18000b511  sub     rsp, 868h
0x18000b518  mov     rax, cs:__security_cookie
0x18000b51f  xor     rax, rsp
0x18000b522  mov     [rbp+790h+var_40], rax
0x18000b529  mov     rbx, [rbp+790h+arg_20]
0x18000b530  mov     r15d, r8d
0x18000b533  mov     [rsp+890h+var_848], rbx
0x18000b538  mov     esi, edx
0x18000b53a  mov     r13, rcx
0x18000b53d  cmp     r8d, 20h ; ' '
0x18000b541  jz      loc_18000B984
0x18000b547  cmp     r8d, 80h
0x18000b54e  jg      loc_18000B79B
0x18000b554  jz      loc_18000B722
0x18000b55a  cmp     r8d, 4
0x18000b55e  jg      loc_18000B633
0x18000b564  jz      loc_18000B607
0x18000b56a  cmp     r8d, 80000000h
0x18000b571  jz      short loc_18000B5DB
0x18000b573  cmp     r8d, 1
0x18000b577  jz      short loc_18000B5AF
0x18000b579  cmp     r8d, 2
0x18000b57d  jnz     loc_18000B8A0
0x18000b583  lea     rax, [rsp+890h+Data]
0x18000b588  mov     r8d, edx; unsigned int
0x18000b58b  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b590  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b597  lea     rdx, aEdge; "EDGE"
0x18000b59e  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b5a3  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b5a8  mov     ebx, eax
0x18000b5aa  jmp     loc_18000BC8E
0x18000b5af  lea     rax, [rsp+890h+Data]
0x18000b5b4  mov     r8d, esi; unsigned int
0x18000b5b7  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b5bc  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b5c3  lea     rdx, aGprs; "GPRS"
0x18000b5ca  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b5cf  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b5d4  mov     ebx, eax
0x18000b5d6  jmp     loc_18000BC8E
0x18000b5db  lea     rax, [rsp+890h+Data]
0x18000b5e0  mov     r8d, esi; unsigned int
0x18000b5e3  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b5e8  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b5ef  lea     rdx, aCustom; "CUSTOM"
0x18000b5f6  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b5fb  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b600  mov     ebx, eax
0x18000b602  jmp     loc_18000BC8E
0x18000b607  lea     rax, [rsp+890h+Data]
0x18000b60c  mov     r8d, esi; unsigned int
0x18000b60f  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b614  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b61b  lea     rdx, aUmts; "UMTS"
0x18000b622  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b627  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b62c  mov     ebx, eax
0x18000b62e  jmp     loc_18000BC8E
0x18000b633  cmp     r15d, 8
0x18000b637  jz      loc_18000B6F6
0x18000b63d  cmp     r15d, 10h
0x18000b641  jz      loc_18000B6CA
0x18000b647  cmp     r15d, 40h ; '@'
0x18000b64b  jnz     loc_18000B8A0
0x18000b651  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b658  sub     r9d, 1; unsigned int
0x18000b65c  jz      short loc_18000B67C
0x18000b65e  sub     r9d, 1
0x18000b662  jz      short loc_18000B673
0x18000b664  cmp     r9d, 1
0x18000b668  jnz     short loc_18000B6A2
0x18000b66a  lea     rdx, a5gNsaFr1Fr2; "5G_NSA_FR1_FR2"
0x18000b671  jmp     short loc_18000B683
0x18000b673  lea     rdx, a5gNsaFr2; "5G_NSA_FR2"
0x18000b67a  jmp     short loc_18000B683
0x18000b67c  lea     rdx, a5gNsaFr1; "5G_NSA_FR1"
0x18000b683  lea     rax, [rsp+890h+Data]
0x18000b688  mov     r8d, esi; unsigned int
0x18000b68b  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b690  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b695  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b69a  test    eax, eax
0x18000b69c  jns     loc_18000BC9B
0x18000b6a2  lea     rax, [rsp+890h+Data]
0x18000b6a7  mov     r8d, esi; unsigned int
0x18000b6aa  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b6af  lea     rdx, a5gNsa; "5G_NSA"
0x18000b6b6  mov     rcx, r13; this
0x18000b6b9  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b6be  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b6c3  mov     ebx, eax
0x18000b6c5  jmp     loc_18000BC8E
0x18000b6ca  lea     rax, [rsp+890h+Data]
0x18000b6cf  mov     r8d, esi; unsigned int
0x18000b6d2  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b6d7  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b6de  lea     rdx, aHsupa; "HSUPA"
0x18000b6e5  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b6ea  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b6ef  mov     ebx, eax
0x18000b6f1  jmp     loc_18000BC8E
0x18000b6f6  lea     rax, [rsp+890h+Data]
0x18000b6fb  mov     r8d, esi; unsigned int
0x18000b6fe  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b703  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b70a  lea     rdx, aHsdpa; "HSDPA"
0x18000b711  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b716  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b71b  mov     ebx, eax
0x18000b71d  jmp     loc_18000BC8E
0x18000b722  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b729  sub     r9d, 1; unsigned int
0x18000b72d  jz      short loc_18000B74D
0x18000b72f  sub     r9d, 1
0x18000b733  jz      short loc_18000B744
0x18000b735  cmp     r9d, 1
0x18000b739  jnz     short loc_18000B773
0x18000b73b  lea     rdx, a5gSaFr1Fr2; "5G_SA_FR1_FR2"
0x18000b742  jmp     short loc_18000B754
0x18000b744  lea     rdx, a5gSaFr2; "5G_SA_FR2"
0x18000b74b  jmp     short loc_18000B754
0x18000b74d  lea     rdx, a5gSaFr1; "5G_SA_FR1"
0x18000b754  lea     rax, [rsp+890h+Data]
0x18000b759  mov     r8d, esi; unsigned int
0x18000b75c  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b761  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b766  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b76b  test    eax, eax
0x18000b76d  jns     loc_18000BC9B
0x18000b773  lea     rax, [rsp+890h+Data]
0x18000b778  mov     r8d, esi; unsigned int
0x18000b77b  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b780  lea     rdx, a5gSa; "5G_SA"
0x18000b787  mov     rcx, r13; this
0x18000b78a  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b78f  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b794  mov     ebx, eax
0x18000b796  jmp     loc_18000BC8E
0x18000b79b  cmp     r15d, 80000h
0x18000b7a2  jg      loc_18000B87D
0x18000b7a8  jz      loc_18000B851
0x18000b7ae  cmp     r15d, 10000h
0x18000b7b5  jz      short loc_18000B825
0x18000b7b7  cmp     r15d, 20000h
0x18000b7be  jz      short loc_18000B7F9
0x18000b7c0  cmp     r15d, 40000h
0x18000b7c7  jnz     loc_18000B8A0
0x18000b7cd  lea     rax, [rsp+890h+Data]
0x18000b7d2  mov     r8d, esi; unsigned int
0x18000b7d5  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b7da  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b7e1  lea     rdx, a1xevdoReva; "1XEVDO_REVA"
0x18000b7e8  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b7ed  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b7f2  mov     ebx, eax
0x18000b7f4  jmp     loc_18000BC8E
0x18000b7f9  lea     rax, [rsp+890h+Data]
0x18000b7fe  mov     r8d, esi; unsigned int
0x18000b801  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b806  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b80d  lea     rdx, a1xevdo; "1XEVDO"
0x18000b814  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b819  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b81e  mov     ebx, eax
0x18000b820  jmp     loc_18000BC8E
0x18000b825  lea     rax, [rsp+890h+Data]
0x18000b82a  mov     r8d, esi; unsigned int
0x18000b82d  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b832  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b839  lea     rdx, a1xrtt; "1XRTT"
0x18000b840  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b845  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b84a  mov     ebx, eax
0x18000b84c  jmp     loc_18000BC8E
0x18000b851  lea     rax, [rsp+890h+Data]
0x18000b856  mov     r8d, esi; unsigned int
0x18000b859  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b85e  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b865  lea     rdx, a1xevdv; "1XEVDV"
0x18000b86c  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b871  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b876  mov     ebx, eax
0x18000b878  jmp     loc_18000BC8E
0x18000b87d  cmp     r15d, 100000h
0x18000b884  jz      loc_18000B958
0x18000b88a  cmp     r15d, 200000h
0x18000b891  jz      loc_18000B92C
0x18000b897  cmp     r15d, 400000h
0x18000b89e  jz      short loc_18000B900
0x18000b8a0  mov     r9d, r15d
0x18000b8a3  lea     r8, aDataClassNotRe; "Data class not recognised. DataClass=%d"
0x18000b8aa  mov     edx, 1EDh; unsigned int
0x18000b8af  lea     rcx, aMbutilGetdatac; "MBUtil::_GetDataClassMappingFromRegistr"...
0x18000b8b6  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18000b8bb  mov     ebx, 80004005h
0x18000b8c0  mov     r9d, r15d
0x18000b8c3  mov     dword ptr [rsp+890h+phkResult], ebx
0x18000b8c7  lea     r8, aCouldNotMapDat; "Could not map data class. DataClass=%d,"...
0x18000b8ce  mov     edx, 1F8h; unsigned int
0x18000b8d3  lea     rcx, aMbutilGetdatac; "MBUtil::_GetDataClassMappingFromRegistr"...
0x18000b8da  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18000b8df  mov     eax, ebx
0x18000b8e1  mov     rcx, [rbp+790h+var_40]
0x18000b8e8  xor     rcx, rsp; StackCookie
0x18000b8eb  call    __security_check_cookie
0x18000b8f0  add     rsp, 868h
0x18000b8f7  pop     r15
0x18000b8f9  pop     r13
0x18000b8fb  pop     rdi
0x18000b8fc  pop     rsi
0x18000b8fd  pop     rbx
0x18000b8fe  pop     rbp
0x18000b8ff  retn
0x18000b900  lea     rax, [rsp+890h+Data]
0x18000b905  mov     r8d, esi; unsigned int
0x18000b908  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b90d  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b914  lea     rdx, aUmb; "UMB"
0x18000b91b  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b920  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b925  mov     ebx, eax
0x18000b927  jmp     loc_18000BC8E
0x18000b92c  lea     rax, [rsp+890h+Data]
0x18000b931  mov     r8d, esi; unsigned int
0x18000b934  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b939  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b940  lea     rdx, a1xevdoRevb; "1XEVDO_REVB"
0x18000b947  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b94c  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b951  mov     ebx, eax
0x18000b953  jmp     loc_18000BC8E
0x18000b958  lea     rax, [rsp+890h+Data]
0x18000b95d  mov     r8d, esi; unsigned int
0x18000b960  mov     [rsp+890h+lpcbData], rax; unsigned __int16 *
0x18000b965  lea     rdi, aDataclassmappi; "DataClassMappingTable"
0x18000b96c  lea     rdx, a3xrtt; "3XRTT"
0x18000b973  mov     [rsp+890h+phkResult], rdi; unsigned __int16 *
0x18000b978  call    ?GetStringValue@MVHelper@@QEAAJQEBGKK0PEAG@Z; MVHelper::GetStringValue(ushort const * const,ulong,ulong,ushort const * const,ushort *)
0x18000b97d  mov     ebx, eax
0x18000b97f  jmp     loc_18000BC8E
0x18000b984  mov     [rsp+890h+arg_18], r12
0x18000b98c  mov     ebx, 80070490h
0x18000b991  mov     [rsp+890h+var_30], r14
0x18000b999  xor     r14d, r14d
0x18000b99c  lea     r12, aDataclassmappi; "DataClassMappingTable"
0x18000b9a3  lea     ecx, ds:0[r14*4]
0x18000b9ab  mov     edi, 0Fh
0x18000b9b0  shl     edi, cl
0x18000b9b2  and     edi, esi
0x18000b9b4  jz      loc_18000BC1E
0x18000b9ba  lea     r9, [rbp+790h+Buffer]
0x18000b9c1  mov     [rsp+890h+cbData], 200h
0x18000b9c9  lea     r8, [rsp+890h+var_854]
0x18000b9ce  mov     [rsp+890h+Type], 0
0x18000b9d6  xor     edx, edx
0x18000b9d8  mov     [rsp+890h+var_854], 200h
0x18000b9e0  mov     ecx, 1
0x18000b9e5  mov     [rsp+890h+hKey], 0
0x18000b9ee  call    cs:__imp_GetPersistentRegPath
0x18000b9f4  mov     ebx, eax
0x18000b9f6  test    eax, eax
0x18000b9f8  jle     short loc_18000BA03
0x18000b9fa  movzx   ebx, ax
0x18000b9fd  or      ebx, 80070000h
0x18000ba03  test    ebx, ebx
0x18000ba05  js      loc_18000BBE9
0x18000ba0b  cmp     edi, 4
0x18000ba0e  jz      short loc_18000BA8C
0x18000ba10  mov     ecx, edi
0x18000ba12  sub     ecx, 1
0x18000ba15  jz      short loc_18000BA5F
0x18000ba17  sub     ecx, 1
0x18000ba1a  jz      short loc_18000BA34
0x18000ba1c  cmp     ecx, 6
0x18000ba1f  jz      short loc_18000BA2B
0x18000ba21  mov     ebx, 80070057h
0x18000ba26  jmp     loc_18000BBE9
0x18000ba2b  lea     rax, aImsispecificDe; "\\IMSISpecific\\Default"
0x18000ba32  jmp     short loc_18000BA66
0x18000ba34  cmp     word ptr [r13+2Ch], 0
0x18000ba3a  lea     rax, [r13+2Ch]
0x18000ba3e  jz      short loc_18000BA4E
0x18000ba40  mov     [rsp+890h+lpcbData], rax
0x18000ba45  lea     rax, aImsispecific; "\\IMSISpecific"
0x18000ba4c  jmp     short loc_18000BAA4
0x18000ba4e  lea     r8, aAskingForPerIm; "Asking for per-IMSI value of IMSI is no"...
0x18000ba55  mov     edx, 0DCh
0x18000ba5a  jmp     loc_18000BBD8
0x18000ba5f  lea     rax, aDevicespecific; "\\DeviceSpecific"
0x18000ba66  lea     r9, [rbp+790h+Buffer]
0x18000ba6d  mov     [rsp+890h+phkResult], rax
0x18000ba72  lea     r8, aSS_0; "%s%s"
  ... truncated ...
```

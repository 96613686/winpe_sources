# CWmsWebService::s_ConfigureVirtualIpPerSessionSettings(void)

- ea: `0x1400529a8`
- end: `0x1400532a9`
- name: `?s_ConfigureVirtualIpPerSessionSettings@CWmsWebService@@CAJXZ`
- size: `2305`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004e580`

## callees

- `0x140052548`
- `0x1400529a8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005327e`
- `ADVAPI32!RegCloseKey` at `0x14005327e`
- `ADVAPI32!RegCreateKeyExW` at `0x140052a5d`
- `ADVAPI32!RegCreateKeyExW` at `0x140052a5d`
- `ADVAPI32!RegSetValueExW` at `0x140052efd`
- `ADVAPI32!RegSetValueExW` at `0x140052fd7`
- `ADVAPI32!RegSetValueExW` at `0x140053080`
- `ADVAPI32!RegSetValueExW` at `0x140052efd`
- `ADVAPI32!RegSetValueExW` at `0x140052fd7`
- `ADVAPI32!RegSetValueExW` at `0x140053080`
- `KERNEL32!IsDebuggerPresent` at `0x140052adb`
- `KERNEL32!IsDebuggerPresent` at `0x140052bc6`
- `KERNEL32!IsDebuggerPresent` at `0x140052c87`
- `KERNEL32!IsDebuggerPresent` at `0x140052d60`
- `KERNEL32!IsDebuggerPresent` at `0x140052df4`
- `KERNEL32!IsDebuggerPresent` at `0x140052f7e`
- `KERNEL32!IsDebuggerPresent` at `0x1400530f0`
- `KERNEL32!IsDebuggerPresent` at `0x14005316c`
- `KERNEL32!IsDebuggerPresent` at `0x1400531ff`
- `KERNEL32!IsDebuggerPresent` at `0x140052adb`
- `KERNEL32!IsDebuggerPresent` at `0x140052bc6`
- `KERNEL32!IsDebuggerPresent` at `0x140052c87`
- `KERNEL32!IsDebuggerPresent` at `0x140052d60`
- `KERNEL32!IsDebuggerPresent` at `0x140052df4`
- `KERNEL32!IsDebuggerPresent` at `0x140052f7e`
- `KERNEL32!IsDebuggerPresent` at `0x1400530f0`
- `KERNEL32!IsDebuggerPresent` at `0x14005316c`
- `KERNEL32!IsDebuggerPresent` at `0x1400531ff`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x140052b48`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x140052b48`
- `IPHLPAPI!GetIfEntry2` at `0x140052cf1`
- `IPHLPAPI!GetIfEntry2` at `0x140052cf1`

## string_xrefs

- `0x140052a8a`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140052b75`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140052c48`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140053254`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140052a78`: `RegCreateKeyEx g_kszTsVirtualIpRegKeyPath failed`
- `0x140052a91`: `CWmsWebService::s_ConfigureVirtualIpPerSessionSettings`
- `0x140052b7c`: `CWmsWebService::s_ConfigureVirtualIpPerSessionSettings`
- `0x140052c41`: `CWmsWebService::s_ConfigureVirtualIpPerSessionSettings`
- `0x14005324d`: `CWmsWebService::s_ConfigureVirtualIpPerSessionSettings`
- `0x140052ec8`: `CWmsWebService::s_ConfigureVirtualIpPerSessionSettings - found %sNIC MAC address %s\n`
- `0x140052f18`: `RegSetValueEx VirtualMode failed`
- `0x140052fee`: `RegSetValueEx AllowPerSessionInMultiNIC failed`
- `0x14005309d`: `RegSetValueEx AdapterAddress failed`

## pseudocode

```c
__int64 CWmsWebService::s_ConfigureVirtualIpPerSessionSettings(void)
{
  ULONG v0; // r12d
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // r15
  __int64 v4; // r9
  __int64 v5; // r8
  NTSTATUS UnicastIpAddressTable; // eax
  ULONG v7; // edx
  ULONG NumEntries; // ecx
  const unsigned __int16 *v9; // r9
  __int64 v10; // r13
  NTSTATUS IfEntry2; // eax
  unsigned int v12; // r13d
  ULONG PhysicalAddressLength; // eax
  unsigned int v14; // r15d
  const wchar_t *v15; // r9
  int v16; // eax
  const wchar_t *v17; // rdx
  LSTATUS v18; // eax
  const wchar_t *v19; // rax
  LSTATUS v20; // eax
  __int64 v21; // rcx
  BYTE *v22; // rax
  unsigned __int64 v23; // rax
  LSTATUS v24; // eax
  const unsigned __int16 *dwOptions; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *samDesireda; // [rsp+28h] [rbp-D8h]
  REGSAM samDesiredb[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *lpSecurityAttributesa; // [rsp+30h] [rbp-D0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesb; // [rsp+30h] [rbp-D0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributesc; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v39; // [rsp+70h] [rbp-90h] BYREF
  struct _MIB_IF_ROW2 Row; // [rsp+80h] [rbp-80h] BYREF
  BYTE v41[128]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v0 = 0;
  Table = 0;
  Row.InterfaceLuid.Value = 0;
  memset_0(&Row.InterfaceIndex, 0, 0x540u);
  memset_0(v41, 0, sizeof(v41));
  v39 = (unsigned __int16 *)v41;
  *(_DWORD *)Data = 0;
  v38 = 64;
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\TSAppSrv\\VirtualIP",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      1909,
      L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
      L"RegCreateKeyEx g_kszTsVirtualIpRegKeyPath failed");
    v3 = L"lr == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x775u,
      L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
      L"CBRLAEx",
      L"lr == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v4 = 1909;
LABEL_6:
      LODWORD(phkResult) = v2;
      lpSecurityAttributesa = v3;
      samDesired = L"CBRLAEx";
LABEL_7:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        v4,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        samDesired,
        lpSecurityAttributesa,
        phkResult);
      goto LABEL_78;
    }
    v5 = 1909;
    goto LABEL_9;
  }
  UnicastIpAddressTable = GetUnicastIpAddressTable(2u, &Table);
  v2 = UnicastIpAddressTable;
  if ( UnicastIpAddressTable )
  {
    if ( UnicastIpAddressTable > 0 )
      v2 = (unsigned __int16)UnicastIpAddressTable | 0x80070000;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      1913,
      L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
      L"GetUnicastIpAddressTable failed");
    v3 = L"dwRetVal == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x779u,
      L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
      L"CBRLAEx",
      L"dwRetVal == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v4 = 1913;
      goto LABEL_6;
    }
    v5 = 1913;
    goto LABEL_9;
  }
  v7 = 0;
  NumEntries = Table->NumEntries;
  if ( Table->NumEntries )
  {
    while ( 1 )
    {
      v9 = (const unsigned __int16 *)(10LL * v7);
      if ( *((_WORD *)&Table->Table[v7].InterfaceLuid.Info + 3) != 131
        && *((_WORD *)&Table->Table[v7].InterfaceLuid.Info + 3) != 24
        && Table->Table[v7].DadState == NldsPreferred )
      {
        NumEntries = v7;
        if ( Table->Table[v7].PrefixOrigin == IpPrefixOriginDhcp )
          break;
      }
      if ( ++v7 >= Table->NumEntries )
      {
        if ( NumEntries >= Table->NumEntries )
          goto LABEL_77;
        break;
      }
    }
    v10 = NumEntries;
    Row.InterfaceLuid.Value = Table->Table[NumEntries].InterfaceLuid.Value;
    if ( Row.InterfaceIndex )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x79Cu,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        v9,
        L"ifRow.InterfaceIndex == 0");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          1948,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          L"ASSERT",
          L"ifRow.InterfaceIndex == 0");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          1948,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          L"ASSERT",
          L"ifRow.InterfaceIndex == 0");
    }
    IfEntry2 = GetIfEntry2(&Row);
    v2 = IfEntry2;
    if ( IfEntry2 )
    {
      if ( IfEntry2 > 0 )
        v2 = (unsigned __int16)IfEntry2 | 0x80070000;
      v12 = 1951;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1951,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"GetIfEntry2 failed");
      v3 = L"dwRetVal == 0L";
LABEL_32:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        v12,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CBRLAEx",
        v3,
        v2);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = v2;
        v4 = v12;
        lpSecurityAttributesa = v3;
        samDesired = L"CBRLAEx";
        goto LABEL_7;
      }
      v5 = v12;
      goto LABEL_9;
    }
    PhysicalAddressLength = Row.PhysicalAddressLength;
    if ( !Row.PhysicalAddressLength )
    {
      v14 = 1953;
      v2 = -2147023728;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1953,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"Invalid MAC address");
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x7A1u,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CBRLAEx",
        L"ifRow.PhysicalAddressLength != 0",
        -2147023728);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = -2147023728;
        lpSecurityAttributesa = L"ifRow.PhysicalAddressLength != 0";
        samDesired = L"CBRLAEx";
LABEL_38:
        v4 = v14;
        goto LABEL_7;
      }
      LODWORD(lpSecurityAttributes) = -2147023728;
      samDesireda = L"ifRow.PhysicalAddressLength != 0";
      dwOptions = L"CBRLAEx";
LABEL_40:
      v5 = v14;
      goto LABEL_10;
    }
    do
    {
      v15 = &psz;
      if ( v0 != PhysicalAddressLength - 1 )
        v15 = L"-";
      LODWORD(lpSecurityAttributes) = Row.PhysicalAddress[v0];
      v16 = StringCchPrintfExW(v39, v38, &v39, &v38, 0, L"%.2hX%s", lpSecurityAttributes, v15);
      v2 = v16;
      if ( v16 < 0 )
      {
        v14 = 1958;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          0x7A6u,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          L"CHRA",
          L"hr",
          v16);
        if ( IsDebuggerPresent() )
        {
          LODWORD(phkResult) = v2;
          lpSecurityAttributesa = L"hr";
          samDesired = L"CHRA";
          goto LABEL_38;
        }
        LODWORD(lpSecurityAttributes) = v2;
        samDesireda = L"hr";
        dwOptions = L"CHRA";
        goto LABEL_40;
      }
      PhysicalAddressLength = Row.PhysicalAddressLength;
      ++v0;
    }
    while ( v0 < Row.PhysicalAddressLength );
    v17 = L"DHCP enabled ";
    if ( Table->Table[v10].PrefixOrigin != IpPrefixOriginDhcp )
      v17 = &psz;
    DEBUGMSG(L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings - found %sNIC MAC address %s\n", v17, v41);
    *(_DWORD *)Data = 0;
    v18 = RegSetValueExW(hKey, L"VirtualMode", 0, 4u, Data, 4u);
    v2 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v2 = (unsigned __int16)v18 | 0x80070000;
      v19 = L"RegSetValueEx VirtualMode failed";
      v12 = 1965;
LABEL_51:
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        v12,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        v19);
      v3 = L"lr == 0L";
      goto LABEL_32;
    }
    *(_DWORD *)Data = 1;
    v20 = RegSetValueExW(hKey, L"AllowPerSessionInMultiNIC", 0, 4u, Data, 4u);
    v2 = v20;
    if ( v20 )
    {
      if ( v20 > 0 )
        v2 = (unsigned __int16)v20 | 0x80070000;
      v19 = L"RegSetValueEx AllowPerSessionInMultiNIC failed";
      v12 = 1969;
      goto LABEL_51;
    }
    v21 = 64;
    v22 = v41;
    do
    {
      if ( !*(_WORD *)v22 )
        break;
      v22 += 2;
      --v21;
    }
    while ( v21 );
    v2 = v21 == 0 ? 0x80070057 : 0;
    if ( v21 )
    {
      v23 = ((2 * (64 - v21)) & -(__int64)(v21 != 0)) + 2;
      if ( v23 <= 0xFFFFFFFF )
      {
        v2 = 0;
        v24 = RegSetValueExW(hKey, L"AdapterAddress", 0, 1u, v41, v23);
        if ( !v24 )
          goto LABEL_78;
        if ( v24 > 0 )
          v2 = (unsigned __int16)v24 | 0x80070000;
        else
          v2 = v24;
        DEBUGMSGLEVEL(
          4u,
          L"%s(%d) - %s - Test failed:  %s\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          1978,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          L"RegSetValueEx AdapterAddress failed");
        v3 = L"lr == 0L";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          0x7BAu,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          L"CBRLAEx",
          L"lr == 0L",
          v2);
        if ( IsDebuggerPresent() )
        {
          v4 = 1978;
          goto LABEL_6;
        }
        v5 = 1978;
LABEL_9:
        LODWORD(lpSecurityAttributes) = v2;
        samDesireda = v3;
        dwOptions = L"CBRLAEx";
LABEL_10:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          v5,
          L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
          dwOptions,
          samDesireda,
          lpSecurityAttributes);
        goto LABEL_78;
      }
      v2 = -2147024362;
      samDesiredb[0] = -2147024362;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - ERROR 0x%08X: %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1975,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        *(_QWORD *)samDesiredb,
        L"failed to convert MAC address size to DWORD");
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x7B7u,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CHRLA",
        L"hr",
        -2147024362);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = -2147024362;
        v4 = 1975;
        lpSecurityAttributesa = L"hr";
        samDesired = L"CHRLA";
        goto LABEL_7;
      }
      LODWORD(lpSecurityAttributesb) = -2147024362;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1975,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CHRLA",
        L"hr",
        lpSecurityAttributesb);
    }
    else
    {
      samDesiredb[0] = -2147024809;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - ERROR 0x%08X: %s\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1972,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        *(_QWORD *)samDesiredb,
        L"failed to get length of MAC address");
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x7B4u,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CHRLA",
        L"hr",
        v2);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = v2;
        v4 = 1972;
        lpSecurityAttributesa = L"hr";
        samDesired = L"CHRLA";
        goto LABEL_7;
      }
      LODWORD(lpSecurityAttributesc) = v2;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1972,
        L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
        L"CHRLA",
        L"hr",
        lpSecurityAttributesc);
    }
  }
  else
  {
LABEL_77:
    v2 = -2147023728;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      1939,
      L"CWmsWebService::s_ConfigureVirtualIpPerSessionSettings",
      L"Could not find valid MAC address");
  }
LABEL_78:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1400529a8  push    rbp
0x1400529aa  push    rbx
0x1400529ab  push    rsi
0x1400529ac  push    rdi
0x1400529ad  push    r12
0x1400529af  push    r13
0x1400529b1  push    r14
0x1400529b3  push    r15
0x1400529b5  lea     rbp, [rsp-568h]
0x1400529bd  sub     rsp, 668h
0x1400529c4  mov     rax, cs:__security_cookie
0x1400529cb  xor     rax, rsp
0x1400529ce  mov     [rbp+5A0h+var_50], rax
0x1400529d5  xor     r12d, r12d
0x1400529d8  lea     rcx, [rbp+5A0h+Row.InterfaceIndex]; void *
0x1400529dc  xor     edx, edx; Val
0x1400529de  mov     [rsp+6A0h+Table], r12
0x1400529e3  mov     r8d, 540h; Size
0x1400529e9  mov     qword ptr [rbp+5A0h+Row.InterfaceLuid], r12
0x1400529ed  call    memset_0
0x1400529f2  xor     edx, edx; Val
0x1400529f4  lea     rcx, [rbp+5A0h+var_D0]; void *
0x1400529fb  mov     r8d, 80h; Size
0x140052a01  call    memset_0
0x140052a06  mov     [rsp+6A0h+lpdwDisposition], r12; lpdwDisposition
0x140052a0b  lea     rax, [rbp+5A0h+var_D0]
0x140052a12  mov     [rsp+6A0h+var_630], rax
0x140052a17  lea     r13d, [r12+2]
0x140052a1c  lea     rax, [rsp+6A0h+hKey]
0x140052a21  mov     dword ptr [rsp+6A0h+Data], r12d
0x140052a26  mov     [rsp+6A0h+phkResult], rax; phkResult
0x140052a2b  lea     r15d, [r12+40h]
0x140052a30  mov     [rsp+6A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140052a35  lea     rdx, ?g_kszTsVirtualIpRegKeyPath@@3QBGB; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x140052a3c  mov     [rsp+6A0h+samDesired], r13d; samDesired
0x140052a41  xor     r9d, r9d; lpClass
0x140052a44  xor     r8d, r8d; Reserved
0x140052a47  mov     [rsp+6A0h+dwOptions], r12d; dwOptions
0x140052a4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140052a53  mov     [rsp+6A0h+var_638], r15
0x140052a58  mov     [rsp+6A0h+hKey], r12
0x140052a5d  call    cs:__imp_RegCreateKeyExW
0x140052a63  mov     ebx, eax
0x140052a65  test    eax, eax
0x140052a67  jz      loc_140052B40
0x140052a6d  jle     short loc_140052A78
0x140052a6f  movzx   ebx, ax
0x140052a72  or      ebx, 80070000h
0x140052a78  lea     rax, aRegcreatekeyex; "RegCreateKeyEx g_kszTsVirtualIpRegKeyPa"...
0x140052a7f  mov     r9d, 775h
0x140052a85  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052a8a  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140052a91  lea     rsi, aCwmswebservice_44; "CWmsWebService::s_ConfigureVirtualIpPer"...
0x140052a98  mov     r8, rdi
0x140052a9b  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140052aa2  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052aa7  mov     ecx, 4; unsigned __int8
0x140052aac  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052ab1  lea     r14, aCbrlaex; "CBRLAEx"
0x140052ab8  mov     [rsp+6A0h+samDesired], ebx; int
0x140052abc  lea     r15, aLr0l; "lr == 0L"
0x140052ac3  mov     r9, r14; unsigned __int16 *
0x140052ac6  mov     r8, rsi; unsigned __int16 *
0x140052ac9  mov     qword ptr [rsp+6A0h+dwOptions], r15; unsigned __int16 *
0x140052ace  mov     edx, 775h; unsigned int
0x140052ad3  mov     rcx, rdi; unsigned __int16 *
0x140052ad6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140052adb  call    cs:__imp_IsDebuggerPresent
0x140052ae1  test    eax, eax
0x140052ae3  jz      short loc_140052B15
0x140052ae5  mov     r9d, 775h
0x140052aeb  mov     dword ptr [rsp+6A0h+phkResult], ebx
0x140052aef  mov     [rsp+6A0h+lpSecurityAttributes], r15
0x140052af4  mov     qword ptr [rsp+6A0h+samDesired], r14
0x140052af9  mov     ecx, r13d; unsigned __int8
0x140052afc  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140052b03  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052b08  mov     r8, rdi
0x140052b0b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052b10  jmp     loc_140053274
0x140052b15  mov     r8d, 775h
0x140052b1b  mov     dword ptr [rsp+6A0h+lpSecurityAttributes], ebx
0x140052b1f  mov     qword ptr [rsp+6A0h+samDesired], r15
0x140052b24  mov     qword ptr [rsp+6A0h+dwOptions], r14
0x140052b29  mov     r9, rsi
0x140052b2c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140052b33  mov     rdx, rdi
0x140052b36  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140052b3b  jmp     loc_140053274
0x140052b40  mov     ecx, r13d; Family
0x140052b43  lea     rdx, [rsp+6A0h+Table]; Table
0x140052b48  call    cs:__imp_GetUnicastIpAddressTable
0x140052b4e  mov     ebx, eax
0x140052b50  test    eax, eax
0x140052b52  jz      loc_140052BE6
0x140052b58  jle     short loc_140052B63
0x140052b5a  movzx   ebx, ax
0x140052b5d  or      ebx, 80070000h
0x140052b63  lea     rax, aGetunicastipad; "GetUnicastIpAddressTable failed"
0x140052b6a  mov     r9d, 779h
0x140052b70  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052b75  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140052b7c  lea     rsi, aCwmswebservice_44; "CWmsWebService::s_ConfigureVirtualIpPer"...
0x140052b83  mov     r8, rdi
0x140052b86  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140052b8d  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052b92  mov     ecx, 4; unsigned __int8
0x140052b97  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052b9c  lea     r14, aCbrlaex; "CBRLAEx"
0x140052ba3  mov     [rsp+6A0h+samDesired], ebx; int
0x140052ba7  lea     r15, aDwretval0l; "dwRetVal == 0L"
0x140052bae  mov     r9, r14; unsigned __int16 *
0x140052bb1  mov     r8, rsi; unsigned __int16 *
0x140052bb4  mov     qword ptr [rsp+6A0h+dwOptions], r15; unsigned __int16 *
0x140052bb9  mov     edx, 779h; unsigned int
0x140052bbe  mov     rcx, rdi; unsigned __int16 *
0x140052bc1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140052bc6  call    cs:__imp_IsDebuggerPresent
0x140052bcc  test    eax, eax
0x140052bce  jz      short loc_140052BDB
0x140052bd0  mov     r9d, 779h
0x140052bd6  jmp     loc_140052AEB
0x140052bdb  mov     r8d, 779h
0x140052be1  jmp     loc_140052B1B
0x140052be6  mov     r8, [rsp+6A0h+Table]
0x140052beb  mov     edx, r12d
0x140052bee  mov     r14d, 4
0x140052bf4  mov     ecx, [r8]
0x140052bf7  test    ecx, ecx
0x140052bf9  jz      loc_14005323B
0x140052bff  mov     eax, edx
0x140052c01  lea     r9, [rax+rax*4]
0x140052c05  mov     eax, 83h
0x140052c0a  add     r9, r9; unsigned __int16 *
0x140052c0d  cmp     [r8+r9*8+2Eh], ax
0x140052c13  jz      short loc_140052C2F
0x140052c15  cmp     word ptr [r8+r9*8+2Eh], 18h
0x140052c1c  jz      short loc_140052C2F
0x140052c1e  cmp     [r8+r9*8+48h], r14d
0x140052c23  jnz     short loc_140052C2F
0x140052c25  cmp     dword ptr [r8+r9*8+34h], 3
0x140052c2b  mov     ecx, edx
0x140052c2d  jz      short loc_140052C3F
0x140052c2f  inc     edx
0x140052c31  cmp     edx, [r8]
0x140052c34  jb      short loc_140052BFF
0x140052c36  cmp     ecx, [r8]
0x140052c39  jnb     loc_14005323B
0x140052c3f  mov     eax, ecx
0x140052c41  lea     rsi, aCwmswebservice_44; "CWmsWebService::s_ConfigureVirtualIpPer"...
0x140052c48  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140052c4f  lea     r13, [rax+rax*4]
0x140052c53  add     r13, r13
0x140052c56  mov     rax, [r8+r13*8+28h]
0x140052c5b  mov     qword ptr [rbp+5A0h+Row.InterfaceLuid], rax
0x140052c5f  cmp     [rbp+5A0h+Row.InterfaceIndex], r12d
0x140052c63  jz      loc_140052CED
0x140052c69  lea     rax, aIfrowInterface; "ifRow.InterfaceIndex == 0"
0x140052c70  mov     ebx, 79Ch
0x140052c75  mov     edx, ebx; unsigned int
0x140052c77  mov     qword ptr [rsp+6A0h+dwOptions], rax; unsigned __int16 *
0x140052c7c  mov     r8, rsi; unsigned __int16 *
0x140052c7f  mov     rcx, rdi; unsigned __int16 *
0x140052c82  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140052c87  call    cs:__imp_IsDebuggerPresent
0x140052c8d  test    eax, eax
0x140052c8f  lea     rax, aIfrowInterface; "ifRow.InterfaceIndex == 0"
0x140052c96  jz      short loc_140052CC7
0x140052c98  mov     [rsp+6A0h+lpSecurityAttributes], rax
0x140052c9d  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140052ca4  lea     rax, aAssert; "ASSERT"
0x140052cab  mov     r9d, ebx
0x140052cae  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052cb3  mov     r8, rdi
0x140052cb6  mov     ecx, 2; unsigned __int8
0x140052cbb  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052cc0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052cc5  jmp     short loc_140052CED
0x140052cc7  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052ccc  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140052cd3  lea     rax, aAssert; "ASSERT"
0x140052cda  mov     r9, rsi
0x140052cdd  mov     r8d, ebx
0x140052ce0  mov     qword ptr [rsp+6A0h+dwOptions], rax
0x140052ce5  mov     rdx, rdi
0x140052ce8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140052ced  lea     rcx, [rbp+5A0h+Row]; Row
0x140052cf1  call    cs:__imp_GetIfEntry2
0x140052cf7  mov     ebx, eax
0x140052cf9  test    eax, eax
0x140052cfb  jz      loc_140052D8D
0x140052d01  jle     short loc_140052D0C
0x140052d03  movzx   ebx, ax
0x140052d06  or      ebx, 80070000h
0x140052d0c  lea     rax, aGetifentry2Fai; "GetIfEntry2 failed"
0x140052d13  mov     r13d, 79Fh
0x140052d19  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052d1e  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140052d25  mov     r9d, r13d
0x140052d28  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052d2d  mov     r8, rdi
0x140052d30  mov     ecx, r14d; unsigned __int8
0x140052d33  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052d38  lea     r15, aDwretval0l; "dwRetVal == 0L"
0x140052d3f  lea     r14, aCbrlaex; "CBRLAEx"
0x140052d46  mov     [rsp+6A0h+samDesired], ebx; int
0x140052d4a  mov     r9, r14; unsigned __int16 *
0x140052d4d  mov     qword ptr [rsp+6A0h+dwOptions], r15; unsigned __int16 *
0x140052d52  mov     r8, rsi; unsigned __int16 *
0x140052d55  mov     edx, r13d; unsigned int
0x140052d58  mov     rcx, rdi; unsigned __int16 *
0x140052d5b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140052d60  call    cs:__imp_IsDebuggerPresent
0x140052d66  test    eax, eax
0x140052d68  jz      short loc_140052D85
0x140052d6a  mov     dword ptr [rsp+6A0h+phkResult], ebx
0x140052d6e  mov     r9d, r13d
0x140052d71  mov     [rsp+6A0h+lpSecurityAttributes], r15
0x140052d76  mov     qword ptr [rsp+6A0h+samDesired], r14
0x140052d7b  mov     ecx, 2
0x140052d80  jmp     loc_140052AFC
0x140052d85  mov     r8d, r13d
0x140052d88  jmp     loc_140052B1B
0x140052d8d  mov     eax, [rbp+5A0h+Row.PhysicalAddressLength]
0x140052d93  test    eax, eax
0x140052d95  jnz     loc_140052E2A
0x140052d9b  lea     rax, aInvalidMacAddr; "Invalid MAC address"
0x140052da2  mov     r15d, 7A1h
0x140052da8  mov     qword ptr [rsp+6A0h+samDesired], rax
0x140052dad  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140052db4  mov     r9d, r15d
0x140052db7  mov     qword ptr [rsp+6A0h+dwOptions], rsi
0x140052dbc  mov     r8, rdi
0x140052dbf  mov     ecx, r14d; unsigned __int8
0x140052dc2  mov     ebx, 80070490h
0x140052dc7  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140052dcc  lea     r14, aCbrlaex; "CBRLAEx"
0x140052dd3  mov     [rsp+6A0h+samDesired], ebx; int
0x140052dd7  lea     r13, aIfrowPhysicala; "ifRow.PhysicalAddressLength != 0"
0x140052dde  mov     r9, r14; unsigned __int16 *
0x140052de1  mov     r8, rsi; unsigned __int16 *
0x140052de4  mov     qword ptr [rsp+6A0h+dwOptions], r13; unsigned __int16 *
0x140052de9  mov     edx, r15d; unsigned int
0x140052dec  mov     rcx, rdi; unsigned __int16 *
0x140052def  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140052df4  call    cs:__imp_IsDebuggerPresent
0x140052dfa  test    eax, eax
0x140052dfc  jz      short loc_140052E14
0x140052dfe  mov     dword ptr [rsp+6A0h+phkResult], ebx
0x140052e02  mov     [rsp+6A0h+lpSecurityAttributes], r13
0x140052e07  mov     qword ptr [rsp+6A0h+samDesired], r14
0x140052e0c  mov     r9d, r15d
0x140052e0f  jmp     loc_140052D7B
0x140052e14  mov     dword ptr [rsp+6A0h+lpSecurityAttributes], ebx
0x140052e18  mov     qword ptr [rsp+6A0h+samDesired], r13
0x140052e1d  mov     qword ptr [rsp+6A0h+dwOptions], r14
0x140052e22  mov     r8d, r15d
0x140052e25  jmp     loc_140052B29
0x140052e2a  lea     rcx, psz
0x140052e31  test    eax, eax
0x140052e33  jz      short loc_140052EAB
0x140052e35  dec     eax
0x140052e37  lea     rdx, asc_1400D42A4; "-"
0x140052e3e  cmp     r12d, eax
0x140052e41  mov     r9, rcx
0x140052e44  mov     rcx, [rsp+6A0h+var_630]; unsigned __int16 *
0x140052e49  cmovnz  r9, rdx
0x140052e4d  mov     eax, r12d
0x140052e50  mov     rdx, [rsp+6A0h+var_638]; unsigned __int64
0x140052e55  mov     [rsp+6A0h+phkResult], r9
0x140052e5a  lea     r9, [rsp+6A0h+var_638]; unsigned __int64 *
0x140052e5f  movzx   r8d, [rbp+rax+5A0h+Row.PhysicalAddress]
0x140052e68  lea     rax, a2hxS; "%.2hX%s"
0x140052e6f  mov     dword ptr [rsp+6A0h+lpSecurityAttributes], r8d
0x140052e74  lea     r8, [rsp+6A0h+var_630]; unsigned __int16 **
0x140052e79  mov     qword ptr [rsp+6A0h+samDesired], rax; unsigned __int16 *
0x140052e7e  mov     qword ptr [rsp+6A0h+dwOptions], 0; unsigned int
0x140052e87  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x140052e8c  mov     ebx, eax
0x140052e8e  test    eax, eax
0x140052e90  js      loc_140052F50
0x140052e96  mov     eax, [rbp+5A0h+Row.PhysicalAddressLength]
0x140052e9c  lea     rcx, psz
0x140052ea3  inc     r12d
0x140052ea6  cmp     r12d, eax
0x140052ea9  jb      short loc_140052E35
0x140052eab  mov     rax, [rsp+6A0h+Table]
0x140052eb0  lea     rdx, aDhcpEnabled; "DHCP enabled "
0x140052eb7  lea     r8, [rbp+5A0h+var_D0]
0x140052ebe  cmp     dword ptr [rax+r13*8+34h], 3
0x140052ec4  cmovnz  rdx, rcx
0x140052ec8  lea     rcx, aCwmswebservice_116; "CWmsWebService::s_ConfigureVirtualIpPer"...
0x140052ecf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140052ed4  mov     rcx, [rsp+6A0h+hKey]; hKey
0x140052ed9  lea     rax, [rsp+6A0h+Data]
0x140052ede  xor     r12d, r12d
0x140052ee1  mov     [rsp+6A0h+samDesired], r14d; cbData
0x140052ee6  mov     r9d, r14d; dwType
0x140052ee9  mov     qword ptr [rsp+6A0h+dwOptions], rax; lpData
0x140052eee  xor     r8d, r8d; Reserved
  ... truncated ...
```

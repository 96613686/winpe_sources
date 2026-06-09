# CFaxConfiguration::Load(void)

- ea: `0x140050adc`
- end: `0x1400510a9`
- name: `?Load@CFaxConfiguration@@QEAAKXZ`
- size: `1485`
- prototype: `__int64 __fastcall(CFaxConfiguration *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140047c20`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140050adc`
- `0x140065dbc`
- `0x140066868`
- `0x14006f808`
- `0x140070684`
- `0x1400708c4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140051089`
- `ADVAPI32!RegCloseKey` at `0x140051089`
- `KERNEL32!GetLastError` at `0x140050b59`
- `KERNEL32!GetLastError` at `0x140050d90`
- `KERNEL32!GetLastError` at `0x140050f08`
- `KERNEL32!GetLastError` at `0x140050f71`
- `KERNEL32!GetLastError` at `0x140050b59`
- `KERNEL32!GetLastError` at `0x140050d90`
- `KERNEL32!GetLastError` at `0x140050f08`
- `KERNEL32!GetLastError` at `0x140050f71`
- `KERNEL32!lstrcmpW` at `0x140050d48`
- `KERNEL32!lstrcmpW` at `0x140050d48`

## string_xrefs

- `0x140050c01`: `UseDeviceTsid`
- `0x140050ed5`: `AutoCreateAccountOnConnect`
- `0x140050f15`: `AutoCreateAccountOnConnect`
- `0x140050f46`: `IncomingFaxesArePublic`
- `0x140050f7e`: `IncomingFaxesArePublic`
- `0x140051041`: `QueueDirectory`

## pseudocode

```c
__int64 __fastcall CFaxConfiguration::Load(CFaxConfiguration *this)
{
  CFaxConfiguration *v1; // rbx
  HKEY v2; // rax
  HKEY v3; // rdi
  DWORD LastError; // eax
  unsigned int v5; // r14d
  unsigned __int16 **v6; // rsi
  int RegistryDwordDefault; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const WCHAR *RegistryStringValue; // rax
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r14
  DWORD v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ecx
  void *v26; // rcx
  int v27; // eax
  char v28; // al
  char v29; // al
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  bool v34; // zf
  int v35; // eax
  DWORD cbData; // [rsp+20h] [rbp-10h]
  DWORD cbDataa; // [rsp+20h] [rbp-10h]
  CFaxConfiguration *Data; // [rsp+60h] [rbp+30h] BYREF

  Data = this;
  v1 = g_pFaxConfig;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
  }
  v2 = (HKEY)OpenRegistryKey(-2147483646, *((_QWORD *)v1 + 15), 0, 131097);
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, LastError);
    }
    v6 = (unsigned __int16 **)((char *)v1 + 48);
    goto LABEL_23;
  }
  LODWORD(Data) = 0;
  RegistryDwordDefault = GetRegistryDwordDefault(v2, L"QueueState", (BYTE *)&Data);
  *((_DWORD *)v1 + 2) = RegistryDwordDefault != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v8 = GetRegistryDwordDefault(v3, L"Retries", (BYTE *)&Data);
  *((_DWORD *)v1 + 3) = v8 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v9 = GetRegistryDwordDefault(v3, L"Retry Delay", (BYTE *)&Data);
  *((_DWORD *)v1 + 4) = v9 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v10 = GetRegistryDwordDefault(v3, L"UseDeviceTsid", (BYTE *)&Data);
  *((_DWORD *)v1 + 5) = v10 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v11 = GetRegistryDwordDefault(v3, L"Branding", (BYTE *)&Data);
  *((_DWORD *)v1 + 6) = v11 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v12 = GetRegistryDwordDefault(v3, L"AllowPersonalCoverPages", (BYTE *)&Data);
  *((_DWORD *)v1 + 7) = v12 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v13 = GetRegistryDwordDefault(v3, L"QueueAgeLimit", (BYTE *)&Data);
  *((_DWORD *)v1 + 10) = v13 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v14 = GetRegistryDwordDefault(v3, L"StartCheapTime", (BYTE *)&Data);
  *((_DWORD *)v1 + 8) = v14 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v15 = GetRegistryDwordDefault(v3, L"StopCheapTime", (BYTE *)&Data);
  *((_DWORD *)v1 + 9) = v15 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v16 = GetRegistryDwordDefault(v3, L"UseArchive", (BYTE *)&Data);
  *((_DWORD *)v1 + 11) = v16 != 0 ? (unsigned int)Data : 0;
  RegistryStringValue = GetRegistryStringValue(v3, 1u, L"ArchiveFolder", L"\\\\\\", cbData);
  v6 = (unsigned __int16 **)((char *)v1 + 48);
  *((_QWORD *)v1 + 6) = RegistryStringValue;
  if ( *((_DWORD *)v1 + 11) && (!RegistryStringValue || !lstrcmpW(L"\\\\\\", RegistryStringValue)) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_31;
    }
    v19 = 12;
    goto LABEL_30;
  }
  v20 = ExpandEnvironmentString(*v6);
  if ( !v20 )
  {
    v21 = GetLastError();
    v5 = v21;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, v21);
    }
LABEL_23:
    if ( !v5 )
      goto LABEL_33;
    goto LABEL_32;
  }
  pMemFree(*v6);
  *v6 = (unsigned __int16 *)v20;
  LODWORD(Data) = 0;
  v22 = GetRegistryDwordDefault(v3, L"SizeQuotaWarn", (BYTE *)&Data);
  *((_DWORD *)v1 + 16) = v22 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v23 = GetRegistryDwordDefault(v3, L"HighWatermark", (BYTE *)&Data);
  *((_DWORD *)v1 + 17) = v23 != 0 ? (unsigned int)Data : 0;
  LODWORD(Data) = 0;
  v24 = GetRegistryDwordDefault(v3, L"LowWatermark", (BYTE *)&Data);
  v25 = v24 != 0 ? (unsigned int)Data : 0;
  *((_DWORD *)v1 + 18) = v25;
  if ( *((_DWORD *)v1 + 17) >= v25 )
  {
    LODWORD(Data) = 0;
    v5 = 0;
    v27 = GetRegistryDwordDefault(v3, L"ArchiveAgeLimit", (BYTE *)&Data);
    *((_DWORD *)v1 + 19) = v27 != 0 ? (unsigned int)Data : 0;
    if ( !(unsigned int)GetRegistryDwordDefault(v3, L"AutoCreateAccountOnConnect", (BYTE *)v1 + 80) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v28 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids,
          (unsigned int)L"AutoCreateAccountOnConnect",
          v28);
      }
      *((_DWORD *)v1 + 20) = 1;
    }
    if ( !(unsigned int)GetRegistryDwordDefault(v3, L"IncomingFaxesArePublic", (BYTE *)v1 + 84) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v29 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids,
          (unsigned int)L"IncomingFaxesArePublic",
          v29);
      }
      *((_DWORD *)v1 + 21) = 1;
    }
    LODWORD(Data) = 0;
    v30 = GetRegistryDwordDefault(v3, L"RecipientsLimit", (BYTE *)&Data);
    *((_DWORD *)v1 + 22) = v30 != 0 ? (unsigned int)Data : 0;
    LODWORD(Data) = 0;
    v31 = GetRegistryDwordDefault(v3, L"NextJobNumber", (BYTE *)&Data);
    *((_DWORD *)v1 + 27) = v31 != 0 ? (unsigned int)Data : 0;
    LODWORD(Data) = 0;
    v32 = GetRegistryDwordDefault(v3, L"LastUniqueLineId", (BYTE *)&Data);
    *((_DWORD *)v1 + 28) = v32 != 0 ? (unsigned int)Data : 0;
    LODWORD(Data) = 0;
    v33 = -(int)GetRegistryDwordDefault(v3, L"MaxLineCloseTime", (BYTE *)&Data);
    v34 = (v33 != 0 ? (unsigned int)Data : 0) == 0;
    *((_DWORD *)v1 + 29) = v33 != 0 ? (unsigned int)Data : 0;
    if ( v34 )
      *((_DWORD *)v1 + 29) = 300;
    *((_QWORD *)v1 + 12) = GetRegistryStringValue(v3, 1u, L"QueueDirectory", 0, cbDataa);
    LODWORD(Data) = 0;
    v35 = GetRegistryDwordDefault(v3, L"AllowRemote", (BYTE *)&Data);
    *((_DWORD *)v1 + 32) = 1;
    *((_DWORD *)v1 + 26) = v35 != 0 ? (unsigned int)Data : 0;
    goto LABEL_50;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = 14;
LABEL_30:
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
  }
LABEL_31:
  v5 = 13;
LABEL_32:
  pMemFree(*v6);
  v26 = (void *)*((_QWORD *)v1 + 12);
  *v6 = 0;
  pMemFree(v26);
  *((_QWORD *)v1 + 12) = 0;
LABEL_33:
  if ( v3 )
LABEL_50:
    RegCloseKey(v3);
  return v5;
}

```

## disassembly

```asm
0x140050adc  mov     [rsp-28h+arg_8], rbx
0x140050ae1  mov     [rsp-28h+arg_10], rsi
0x140050ae6  mov     [rsp-28h+Data], rcx
0x140050aeb  push    rbp
0x140050aec  push    rdi
0x140050aed  push    r13
0x140050aef  push    r14
0x140050af1  push    r15
0x140050af3  mov     rbp, rsp
0x140050af6  sub     rsp, 30h
0x140050afa  mov     rbx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140050b01  mov     rcx, cs:WPP_GLOBAL_Control
0x140050b08  lea     r13, WPP_GLOBAL_Control
0x140050b0f  cmp     rcx, r13
0x140050b12  jz      short loc_140050B35
0x140050b14  test    byte ptr [rcx+1Ch], 4
0x140050b18  jz      short loc_140050B35
0x140050b1a  cmp     byte ptr [rcx+19h], 5
0x140050b1e  jb      short loc_140050B35
0x140050b20  mov     rcx, [rcx+10h]
0x140050b24  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140050b2b  mov     edx, 0Ah
0x140050b30  call    WPP_SF_
0x140050b35  mov     rdx, [rbx+78h]
0x140050b39  mov     r9d, 20019h
0x140050b3f  xor     r8d, r8d
0x140050b42  mov     rcx, 0FFFFFFFF80000002h
0x140050b49  call    OpenRegistryKey
0x140050b4e  xor     r15d, r15d
0x140050b51  mov     rdi, rax
0x140050b54  test    rax, rax
0x140050b57  jnz     short loc_140050B99
0x140050b59  call    cs:__imp_GetLastError
0x140050b5f  mov     r14d, eax
0x140050b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140050b69  cmp     rcx, r13
0x140050b6c  jz      short loc_140050B90
0x140050b6e  test    byte ptr [rcx+1Ch], 4
0x140050b72  jz      short loc_140050B90
0x140050b74  cmp     byte ptr [rcx+19h], 2
0x140050b78  jb      short loc_140050B90
0x140050b7a  mov     rcx, [rcx+10h]
0x140050b7e  lea     edx, [rdi+0Bh]
0x140050b81  mov     r9d, eax
0x140050b84  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140050b8b  call    WPP_SF_d
0x140050b90  lea     rsi, [rbx+30h]
0x140050b94  jmp     loc_140050DC9
0x140050b99  xor     r9d, r9d
0x140050b9c  mov     dword ptr [rbp+Data], r15d
0x140050ba0  lea     r8, [rbp+Data]; lpData
0x140050ba4  mov     rcx, rdi; hKey
0x140050ba7  lea     rdx, aQueuestate; "QueueState"
0x140050bae  call    GetRegistryDwordDefault
0x140050bb3  neg     eax
0x140050bb5  lea     r8, [rbp+Data]; lpData
0x140050bb9  lea     rdx, aRetries; "Retries"
0x140050bc0  sbb     ecx, ecx
0x140050bc2  xor     r9d, r9d
0x140050bc5  and     ecx, dword ptr [rbp+Data]
0x140050bc8  mov     [rbx+8], ecx
0x140050bcb  mov     rcx, rdi; hKey
0x140050bce  mov     dword ptr [rbp+Data], r15d
0x140050bd2  call    GetRegistryDwordDefault
0x140050bd7  neg     eax
0x140050bd9  lea     r8, [rbp+Data]; lpData
0x140050bdd  lea     rdx, aRetryDelay; "Retry Delay"
0x140050be4  sbb     ecx, ecx
0x140050be6  xor     r9d, r9d
0x140050be9  and     ecx, dword ptr [rbp+Data]
0x140050bec  mov     [rbx+0Ch], ecx
0x140050bef  mov     rcx, rdi; hKey
0x140050bf2  mov     dword ptr [rbp+Data], r15d
0x140050bf6  call    GetRegistryDwordDefault
0x140050bfb  neg     eax
0x140050bfd  lea     r8, [rbp+Data]; lpData
0x140050c01  lea     rdx, aUsedevicetsid; "UseDeviceTsid"
0x140050c08  sbb     ecx, ecx
0x140050c0a  xor     r9d, r9d
0x140050c0d  and     ecx, dword ptr [rbp+Data]
0x140050c10  mov     [rbx+10h], ecx
0x140050c13  mov     rcx, rdi; hKey
0x140050c16  mov     dword ptr [rbp+Data], r15d
0x140050c1a  call    GetRegistryDwordDefault
0x140050c1f  neg     eax
0x140050c21  lea     r8, [rbp+Data]; lpData
0x140050c25  lea     rdx, aBranding; "Branding"
0x140050c2c  sbb     ecx, ecx
0x140050c2e  xor     r9d, r9d
0x140050c31  and     ecx, dword ptr [rbp+Data]
0x140050c34  mov     [rbx+14h], ecx
0x140050c37  mov     rcx, rdi; hKey
0x140050c3a  mov     dword ptr [rbp+Data], r15d
0x140050c3e  call    GetRegistryDwordDefault
0x140050c43  neg     eax
0x140050c45  lea     r8, [rbp+Data]; lpData
0x140050c49  lea     rdx, aAllowpersonalc; "AllowPersonalCoverPages"
0x140050c50  sbb     ecx, ecx
0x140050c52  xor     r9d, r9d
0x140050c55  and     ecx, dword ptr [rbp+Data]
0x140050c58  mov     [rbx+18h], ecx
0x140050c5b  mov     rcx, rdi; hKey
0x140050c5e  mov     dword ptr [rbp+Data], r15d
0x140050c62  call    GetRegistryDwordDefault
0x140050c67  neg     eax
0x140050c69  lea     r8, [rbp+Data]; lpData
0x140050c6d  lea     rdx, aQueueagelimit; "QueueAgeLimit"
0x140050c74  sbb     ecx, ecx
0x140050c76  xor     r9d, r9d
0x140050c79  and     ecx, dword ptr [rbp+Data]
0x140050c7c  mov     [rbx+1Ch], ecx
0x140050c7f  mov     rcx, rdi; hKey
0x140050c82  mov     dword ptr [rbp+Data], r15d
0x140050c86  call    GetRegistryDwordDefault
0x140050c8b  neg     eax
0x140050c8d  lea     r8, [rbp+Data]; lpData
0x140050c91  lea     rdx, aStartcheaptime; "StartCheapTime"
0x140050c98  sbb     ecx, ecx
0x140050c9a  xor     r9d, r9d
0x140050c9d  and     ecx, dword ptr [rbp+Data]
0x140050ca0  mov     [rbx+28h], ecx
0x140050ca3  mov     rcx, rdi; hKey
0x140050ca6  mov     dword ptr [rbp+Data], r15d
0x140050caa  call    GetRegistryDwordDefault
0x140050caf  neg     eax
0x140050cb1  sbb     ecx, ecx
0x140050cb3  and     ecx, dword ptr [rbp+Data]
0x140050cb6  mov     [rbx+20h], cx
0x140050cba  shr     ecx, 10h
0x140050cbd  mov     [rbx+22h], cx
0x140050cc1  lea     r8, [rbp+Data]; lpData
0x140050cc5  mov     rcx, rdi; hKey
0x140050cc8  mov     dword ptr [rbp+Data], r15d
0x140050ccc  xor     r9d, r9d
0x140050ccf  lea     rdx, aStopcheaptime; "StopCheapTime"
0x140050cd6  call    GetRegistryDwordDefault
0x140050cdb  neg     eax
0x140050cdd  lea     r8, [rbp+Data]; lpData
0x140050ce1  lea     rdx, aUsearchive; "UseArchive"
0x140050ce8  sbb     ecx, ecx
0x140050cea  xor     r9d, r9d
0x140050ced  and     ecx, dword ptr [rbp+Data]
0x140050cf0  mov     [rbx+24h], cx
0x140050cf4  shr     ecx, 10h
0x140050cf7  mov     [rbx+26h], cx
0x140050cfb  mov     rcx, rdi; hKey
0x140050cfe  mov     dword ptr [rbp+Data], r15d
0x140050d02  call    GetRegistryDwordDefault
0x140050d07  neg     eax
0x140050d09  lea     r9, asc_14008E5E8; "\\\\\\"
0x140050d10  lea     r8, aArchivefolder; "ArchiveFolder"
0x140050d17  mov     edx, 1; dwType
0x140050d1c  sbb     ecx, ecx
0x140050d1e  and     ecx, dword ptr [rbp+Data]
0x140050d21  mov     [rbx+2Ch], ecx
0x140050d24  mov     rcx, rdi; hKey
0x140050d27  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x140050d2c  lea     rsi, [rbx+30h]
0x140050d30  mov     [rsi], rax
0x140050d33  cmp     [rbx+2Ch], r15d
0x140050d37  jz      short loc_140050D80
0x140050d39  test    rax, rax
0x140050d3c  jz      short loc_140050D52
0x140050d3e  mov     rdx, rax; lpString2
0x140050d41  lea     rcx, asc_14008E5E8; "\\\\\\"
0x140050d48  call    cs:__imp_lstrcmpW
0x140050d4e  test    eax, eax
0x140050d50  jnz     short loc_140050D80
0x140050d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140050d59  cmp     rcx, r13
0x140050d5c  jz      loc_140050E80
0x140050d62  test    byte ptr [rcx+1Ch], 4
0x140050d66  jz      loc_140050E80
0x140050d6c  cmp     byte ptr [rcx+19h], 2
0x140050d70  jb      loc_140050E80
0x140050d76  mov     edx, 0Ch
0x140050d7b  jmp     loc_140050E70
0x140050d80  mov     rcx, [rsi]; unsigned __int16 *
0x140050d83  call    ExpandEnvironmentString
0x140050d88  mov     r14, rax
0x140050d8b  test    rax, rax
0x140050d8e  jnz     short loc_140050DD7
0x140050d90  call    cs:__imp_GetLastError
0x140050d96  mov     r14d, eax
0x140050d99  mov     rcx, cs:WPP_GLOBAL_Control
0x140050da0  cmp     rcx, r13
0x140050da3  jz      short loc_140050DC9
0x140050da5  test    byte ptr [rcx+1Ch], 4
0x140050da9  jz      short loc_140050DC9
0x140050dab  cmp     byte ptr [rcx+19h], 2
0x140050daf  jb      short loc_140050DC9
0x140050db1  mov     rcx, [rcx+10h]
0x140050db5  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140050dbc  mov     edx, 0Dh
0x140050dc1  mov     r9d, eax
0x140050dc4  call    WPP_SF_d
0x140050dc9  test    r14d, r14d
0x140050dcc  jz      loc_140050E9E
0x140050dd2  jmp     loc_140050E86
0x140050dd7  mov     rcx, [rsi]; lpMem
0x140050dda  call    pMemFree
0x140050ddf  xor     r9d, r9d
0x140050de2  mov     [rsi], r14
0x140050de5  lea     r8, [rbp+Data]; lpData
0x140050de9  mov     dword ptr [rbp+Data], r15d
0x140050ded  lea     rdx, aSizequotawarn; "SizeQuotaWarn"
0x140050df4  mov     rcx, rdi; hKey
0x140050df7  call    GetRegistryDwordDefault
0x140050dfc  neg     eax
0x140050dfe  lea     r8, [rbp+Data]; lpData
0x140050e02  lea     rdx, aHighwatermark; "HighWatermark"
0x140050e09  sbb     ecx, ecx
0x140050e0b  xor     r9d, r9d
0x140050e0e  and     ecx, dword ptr [rbp+Data]
0x140050e11  mov     [rbx+40h], ecx
0x140050e14  mov     rcx, rdi; hKey
0x140050e17  mov     dword ptr [rbp+Data], r15d
0x140050e1b  call    GetRegistryDwordDefault
0x140050e20  neg     eax
0x140050e22  lea     r8, [rbp+Data]; lpData
0x140050e26  lea     rdx, aLowwatermark; "LowWatermark"
0x140050e2d  sbb     ecx, ecx
0x140050e2f  xor     r9d, r9d
0x140050e32  and     ecx, dword ptr [rbp+Data]
0x140050e35  mov     [rbx+44h], ecx
0x140050e38  mov     rcx, rdi; hKey
0x140050e3b  mov     dword ptr [rbp+Data], r15d
0x140050e3f  call    GetRegistryDwordDefault
0x140050e44  neg     eax
0x140050e46  sbb     ecx, ecx
0x140050e48  and     ecx, dword ptr [rbp+Data]
0x140050e4b  mov     [rbx+48h], ecx
0x140050e4e  cmp     [rbx+44h], ecx
0x140050e51  jnb     short loc_140050EAC
0x140050e53  mov     rcx, cs:WPP_GLOBAL_Control
0x140050e5a  cmp     rcx, r13
0x140050e5d  jz      short loc_140050E80
0x140050e5f  test    byte ptr [rcx+1Ch], 4
0x140050e63  jz      short loc_140050E80
0x140050e65  cmp     byte ptr [rcx+19h], 2
0x140050e69  jb      short loc_140050E80
0x140050e6b  mov     edx, 0Eh
0x140050e70  mov     rcx, [rcx+10h]
0x140050e74  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140050e7b  call    WPP_SF_
0x140050e80  mov     r14d, 0Dh
0x140050e86  mov     rcx, [rsi]; lpMem
0x140050e89  call    pMemFree
0x140050e8e  mov     rcx, [rbx+60h]; lpMem
0x140050e92  mov     [rsi], r15
0x140050e95  call    pMemFree
0x140050e9a  mov     [rbx+60h], r15
0x140050e9e  test    rdi, rdi
0x140050ea1  jz      loc_14005108F
0x140050ea7  jmp     loc_140051086
0x140050eac  xor     r9d, r9d
0x140050eaf  mov     dword ptr [rbp+Data], r15d
0x140050eb3  lea     r8, [rbp+Data]; lpData
0x140050eb7  mov     rcx, rdi; hKey
0x140050eba  lea     rdx, aArchiveagelimi; "ArchiveAgeLimit"
0x140050ec1  mov     r14d, r15d
0x140050ec4  call    GetRegistryDwordDefault
0x140050ec9  neg     eax
0x140050ecb  lea     r8, [rbx+50h]; lpData
0x140050ecf  mov     r9d, 1
0x140050ed5  lea     rdx, aAutocreateacco; "AutoCreateAccountOnConnect"
0x140050edc  sbb     ecx, ecx
0x140050ede  and     ecx, dword ptr [rbp+Data]
0x140050ee1  mov     [rbx+4Ch], ecx
0x140050ee4  mov     rcx, rdi; hKey
0x140050ee7  call    GetRegistryDwordDefault
0x140050eec  test    eax, eax
0x140050eee  jnz     short loc_140050F3C
0x140050ef0  mov     rax, cs:WPP_GLOBAL_Control
0x140050ef7  cmp     rax, r13
0x140050efa  jz      short loc_140050F35
0x140050efc  test    byte ptr [rax+1Ch], 4
0x140050f00  jz      short loc_140050F35
0x140050f02  cmp     byte ptr [rax+19h], 3
0x140050f06  jb      short loc_140050F35
0x140050f08  call    cs:__imp_GetLastError
0x140050f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140050f15  lea     r9, aAutocreateacco; "AutoCreateAccountOnConnect"
0x140050f1c  mov     edx, 0Fh
0x140050f21  mov     [rsp+30h+cbData], eax
0x140050f25  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140050f2c  mov     rcx, [rcx+10h]
0x140050f30  call    WPP_SF_Sd
0x140050f35  mov     dword ptr [rbx+50h], 1
0x140050f3c  mov     r9d, 1
0x140050f42  lea     r8, [rbx+54h]; lpData
0x140050f46  lea     rdx, aIncomingfaxesa; "IncomingFaxesArePublic"
0x140050f4d  mov     rcx, rdi; hKey
0x140050f50  call    GetRegistryDwordDefault
0x140050f55  test    eax, eax
0x140050f57  jnz     short loc_140050FA5
0x140050f59  mov     rax, cs:WPP_GLOBAL_Control
0x140050f60  cmp     rax, r13
0x140050f63  jz      short loc_140050F9E
0x140050f65  test    byte ptr [rax+1Ch], 4
  ... truncated ...
```

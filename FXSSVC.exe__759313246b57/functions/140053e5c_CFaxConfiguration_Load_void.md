# CFaxConfiguration::Load(void)

- ea: `0x140053e5c`
- end: `0x14005444e`
- name: `?Load@CFaxConfiguration@@QEAAKXZ`
- size: `1522`
- prototype: `unsigned int __fastcall(CFaxConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004a944`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140053e5c`
- `0x14006998c`
- `0x14006a574`
- `0x140073d5c`
- `0x140074cb4`
- `0x140074f18`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140054427`
- `ADVAPI32!RegCloseKey` at `0x140054427`
- `KERNEL32!GetLastError` at `0x140053ed9`
- `KERNEL32!GetLastError` at `0x14005411c`
- `KERNEL32!GetLastError` at `0x14005429a`
- `KERNEL32!GetLastError` at `0x140054309`
- `KERNEL32!GetLastError` at `0x140053ed9`
- `KERNEL32!GetLastError` at `0x14005411c`
- `KERNEL32!GetLastError` at `0x14005429a`
- `KERNEL32!GetLastError` at `0x140054309`
- `KERNEL32!lstrcmpW` at `0x1400540ce`
- `KERNEL32!lstrcmpW` at `0x1400540ce`

## string_xrefs

- `0x140053f87`: `UseDeviceTsid`
- `0x140054267`: `AutoCreateAccountOnConnect`
- `0x1400542ad`: `AutoCreateAccountOnConnect`
- `0x1400542de`: `IncomingFaxesArePublic`
- `0x14005431c`: `IncomingFaxesArePublic`
- `0x1400543df`: `QueueDirectory`

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
  BYTE *RegistryStringValue; // rax
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
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, *((const WCHAR **)v1 + 15), 0, 0x20019u);
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
  if ( *((_DWORD *)v1 + 11) && (!RegistryStringValue || !lstrcmpW(L"\\\\\\", (LPCWSTR)RegistryStringValue)) )
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
0x140053e5c  mov     [rsp-28h+arg_8], rbx
0x140053e61  mov     [rsp-28h+arg_10], rsi
0x140053e66  mov     [rsp-28h+Data], rcx
0x140053e6b  push    rbp
0x140053e6c  push    rdi
0x140053e6d  push    r13
0x140053e6f  push    r14
0x140053e71  push    r15
0x140053e73  mov     rbp, rsp
0x140053e76  sub     rsp, 30h
0x140053e7a  mov     rbx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140053e81  mov     rcx, cs:WPP_GLOBAL_Control
0x140053e88  lea     r13, WPP_GLOBAL_Control
0x140053e8f  cmp     rcx, r13
0x140053e92  jz      short loc_140053EB5
0x140053e94  test    byte ptr [rcx+1Ch], 4
0x140053e98  jz      short loc_140053EB5
0x140053e9a  cmp     byte ptr [rcx+19h], 5
0x140053e9e  jb      short loc_140053EB5
0x140053ea0  mov     rcx, [rcx+10h]
0x140053ea4  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140053eab  mov     edx, 0Ah
0x140053eb0  call    WPP_SF_
0x140053eb5  mov     rdx, [rbx+78h]
0x140053eb9  mov     r9d, 20019h
0x140053ebf  xor     r8d, r8d
0x140053ec2  mov     rcx, 0FFFFFFFF80000002h
0x140053ec9  call    OpenRegistryKey
0x140053ece  xor     r15d, r15d
0x140053ed1  mov     rdi, rax
0x140053ed4  test    rax, rax
0x140053ed7  jnz     short loc_140053F1F
0x140053ed9  call    cs:__imp_GetLastError
0x140053ee0  nop     dword ptr [rax+rax+00h]
0x140053ee5  mov     r14d, eax
0x140053ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140053eef  cmp     rcx, r13
0x140053ef2  jz      short loc_140053F16
0x140053ef4  test    byte ptr [rcx+1Ch], 4
0x140053ef8  jz      short loc_140053F16
0x140053efa  cmp     byte ptr [rcx+19h], 2
0x140053efe  jb      short loc_140053F16
0x140053f00  mov     rcx, [rcx+10h]
0x140053f04  lea     edx, [rdi+0Bh]
0x140053f07  mov     r9d, eax
0x140053f0a  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140053f11  call    WPP_SF_d
0x140053f16  lea     rsi, [rbx+30h]
0x140053f1a  jmp     loc_14005415B
0x140053f1f  xor     r9d, r9d
0x140053f22  mov     dword ptr [rbp+Data], r15d
0x140053f26  lea     r8, [rbp+Data]; lpData
0x140053f2a  mov     rcx, rdi; hKey
0x140053f2d  lea     rdx, aQueuestate; "QueueState"
0x140053f34  call    GetRegistryDwordDefault
0x140053f39  neg     eax
0x140053f3b  lea     r8, [rbp+Data]; lpData
0x140053f3f  lea     rdx, aRetries; "Retries"
0x140053f46  sbb     ecx, ecx
0x140053f48  xor     r9d, r9d
0x140053f4b  and     ecx, dword ptr [rbp+Data]
0x140053f4e  mov     [rbx+8], ecx
0x140053f51  mov     rcx, rdi; hKey
0x140053f54  mov     dword ptr [rbp+Data], r15d
0x140053f58  call    GetRegistryDwordDefault
0x140053f5d  neg     eax
0x140053f5f  lea     r8, [rbp+Data]; lpData
0x140053f63  lea     rdx, aRetryDelay; "Retry Delay"
0x140053f6a  sbb     ecx, ecx
0x140053f6c  xor     r9d, r9d
0x140053f6f  and     ecx, dword ptr [rbp+Data]
0x140053f72  mov     [rbx+0Ch], ecx
0x140053f75  mov     rcx, rdi; hKey
0x140053f78  mov     dword ptr [rbp+Data], r15d
0x140053f7c  call    GetRegistryDwordDefault
0x140053f81  neg     eax
0x140053f83  lea     r8, [rbp+Data]; lpData
0x140053f87  lea     rdx, aUsedevicetsid; "UseDeviceTsid"
0x140053f8e  sbb     ecx, ecx
0x140053f90  xor     r9d, r9d
0x140053f93  and     ecx, dword ptr [rbp+Data]
0x140053f96  mov     [rbx+10h], ecx
0x140053f99  mov     rcx, rdi; hKey
0x140053f9c  mov     dword ptr [rbp+Data], r15d
0x140053fa0  call    GetRegistryDwordDefault
0x140053fa5  neg     eax
0x140053fa7  lea     r8, [rbp+Data]; lpData
0x140053fab  lea     rdx, aBranding; "Branding"
0x140053fb2  sbb     ecx, ecx
0x140053fb4  xor     r9d, r9d
0x140053fb7  and     ecx, dword ptr [rbp+Data]
0x140053fba  mov     [rbx+14h], ecx
0x140053fbd  mov     rcx, rdi; hKey
0x140053fc0  mov     dword ptr [rbp+Data], r15d
0x140053fc4  call    GetRegistryDwordDefault
0x140053fc9  neg     eax
0x140053fcb  lea     r8, [rbp+Data]; lpData
0x140053fcf  lea     rdx, aAllowpersonalc; "AllowPersonalCoverPages"
0x140053fd6  sbb     ecx, ecx
0x140053fd8  xor     r9d, r9d
0x140053fdb  and     ecx, dword ptr [rbp+Data]
0x140053fde  mov     [rbx+18h], ecx
0x140053fe1  mov     rcx, rdi; hKey
0x140053fe4  mov     dword ptr [rbp+Data], r15d
0x140053fe8  call    GetRegistryDwordDefault
0x140053fed  neg     eax
0x140053fef  lea     r8, [rbp+Data]; lpData
0x140053ff3  lea     rdx, aQueueagelimit; "QueueAgeLimit"
0x140053ffa  sbb     ecx, ecx
0x140053ffc  xor     r9d, r9d
0x140053fff  and     ecx, dword ptr [rbp+Data]
0x140054002  mov     [rbx+1Ch], ecx
0x140054005  mov     rcx, rdi; hKey
0x140054008  mov     dword ptr [rbp+Data], r15d
0x14005400c  call    GetRegistryDwordDefault
0x140054011  neg     eax
0x140054013  lea     r8, [rbp+Data]; lpData
0x140054017  lea     rdx, aStartcheaptime; "StartCheapTime"
0x14005401e  sbb     ecx, ecx
0x140054020  xor     r9d, r9d
0x140054023  and     ecx, dword ptr [rbp+Data]
0x140054026  mov     [rbx+28h], ecx
0x140054029  mov     rcx, rdi; hKey
0x14005402c  mov     dword ptr [rbp+Data], r15d
0x140054030  call    GetRegistryDwordDefault
0x140054035  neg     eax
0x140054037  sbb     ecx, ecx
0x140054039  and     ecx, dword ptr [rbp+Data]
0x14005403c  mov     [rbx+20h], cx
0x140054040  shr     ecx, 10h
0x140054043  mov     [rbx+22h], cx
0x140054047  lea     r8, [rbp+Data]; lpData
0x14005404b  mov     rcx, rdi; hKey
0x14005404e  mov     dword ptr [rbp+Data], r15d
0x140054052  xor     r9d, r9d
0x140054055  lea     rdx, aStopcheaptime; "StopCheapTime"
0x14005405c  call    GetRegistryDwordDefault
0x140054061  neg     eax
0x140054063  lea     r8, [rbp+Data]; lpData
0x140054067  lea     rdx, aUsearchive; "UseArchive"
0x14005406e  sbb     ecx, ecx
0x140054070  xor     r9d, r9d
0x140054073  and     ecx, dword ptr [rbp+Data]
0x140054076  mov     [rbx+24h], cx
0x14005407a  shr     ecx, 10h
0x14005407d  mov     [rbx+26h], cx
0x140054081  mov     rcx, rdi; hKey
0x140054084  mov     dword ptr [rbp+Data], r15d
0x140054088  call    GetRegistryDwordDefault
0x14005408d  neg     eax
0x14005408f  lea     r9, asc_1400945F8; "\\\\\\"
0x140054096  lea     r8, aArchivefolder; "ArchiveFolder"
0x14005409d  mov     edx, 1; dwType
0x1400540a2  sbb     ecx, ecx
0x1400540a4  and     ecx, dword ptr [rbp+Data]
0x1400540a7  mov     [rbx+2Ch], ecx
0x1400540aa  mov     rcx, rdi; hKey
0x1400540ad  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1400540b2  lea     rsi, [rbx+30h]
0x1400540b6  mov     [rsi], rax
0x1400540b9  cmp     [rbx+2Ch], r15d
0x1400540bd  jz      short loc_14005410C
0x1400540bf  test    rax, rax
0x1400540c2  jz      short loc_1400540DE
0x1400540c4  mov     rdx, rax; lpString2
0x1400540c7  lea     rcx, asc_1400945F8; "\\\\\\"
0x1400540ce  call    cs:__imp_lstrcmpW
0x1400540d5  nop     dword ptr [rax+rax+00h]
0x1400540da  test    eax, eax
0x1400540dc  jnz     short loc_14005410C
0x1400540de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400540e5  cmp     rcx, r13
0x1400540e8  jz      loc_140054212
0x1400540ee  test    byte ptr [rcx+1Ch], 4
0x1400540f2  jz      loc_140054212
0x1400540f8  cmp     byte ptr [rcx+19h], 2
0x1400540fc  jb      loc_140054212
0x140054102  mov     edx, 0Ch
0x140054107  jmp     loc_140054202
0x14005410c  mov     rcx, [rsi]; unsigned __int16 *
0x14005410f  call    ExpandEnvironmentString
0x140054114  mov     r14, rax
0x140054117  test    rax, rax
0x14005411a  jnz     short loc_140054169
0x14005411c  call    cs:__imp_GetLastError
0x140054123  nop     dword ptr [rax+rax+00h]
0x140054128  mov     r14d, eax
0x14005412b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054132  cmp     rcx, r13
0x140054135  jz      short loc_14005415B
0x140054137  test    byte ptr [rcx+1Ch], 4
0x14005413b  jz      short loc_14005415B
0x14005413d  cmp     byte ptr [rcx+19h], 2
0x140054141  jb      short loc_14005415B
0x140054143  mov     rcx, [rcx+10h]
0x140054147  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x14005414e  mov     edx, 0Dh
0x140054153  mov     r9d, eax
0x140054156  call    WPP_SF_d
0x14005415b  test    r14d, r14d
0x14005415e  jz      loc_140054230
0x140054164  jmp     loc_140054218
0x140054169  mov     rcx, [rsi]; lpMem
0x14005416c  call    pMemFree
0x140054171  xor     r9d, r9d
0x140054174  mov     [rsi], r14
0x140054177  lea     r8, [rbp+Data]; lpData
0x14005417b  mov     dword ptr [rbp+Data], r15d
0x14005417f  lea     rdx, aSizequotawarn; "SizeQuotaWarn"
0x140054186  mov     rcx, rdi; hKey
0x140054189  call    GetRegistryDwordDefault
0x14005418e  neg     eax
0x140054190  lea     r8, [rbp+Data]; lpData
0x140054194  lea     rdx, aHighwatermark; "HighWatermark"
0x14005419b  sbb     ecx, ecx
0x14005419d  xor     r9d, r9d
0x1400541a0  and     ecx, dword ptr [rbp+Data]
0x1400541a3  mov     [rbx+40h], ecx
0x1400541a6  mov     rcx, rdi; hKey
0x1400541a9  mov     dword ptr [rbp+Data], r15d
0x1400541ad  call    GetRegistryDwordDefault
0x1400541b2  neg     eax
0x1400541b4  lea     r8, [rbp+Data]; lpData
0x1400541b8  lea     rdx, aLowwatermark; "LowWatermark"
0x1400541bf  sbb     ecx, ecx
0x1400541c1  xor     r9d, r9d
0x1400541c4  and     ecx, dword ptr [rbp+Data]
0x1400541c7  mov     [rbx+44h], ecx
0x1400541ca  mov     rcx, rdi; hKey
0x1400541cd  mov     dword ptr [rbp+Data], r15d
0x1400541d1  call    GetRegistryDwordDefault
0x1400541d6  neg     eax
0x1400541d8  sbb     ecx, ecx
0x1400541da  and     ecx, dword ptr [rbp+Data]
0x1400541dd  mov     [rbx+48h], ecx
0x1400541e0  cmp     [rbx+44h], ecx
0x1400541e3  jnb     short loc_14005423E
0x1400541e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400541ec  cmp     rcx, r13
0x1400541ef  jz      short loc_140054212
0x1400541f1  test    byte ptr [rcx+1Ch], 4
0x1400541f5  jz      short loc_140054212
0x1400541f7  cmp     byte ptr [rcx+19h], 2
0x1400541fb  jb      short loc_140054212
0x1400541fd  mov     edx, 0Eh
0x140054202  mov     rcx, [rcx+10h]
0x140054206  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x14005420d  call    WPP_SF_
0x140054212  mov     r14d, 0Dh
0x140054218  mov     rcx, [rsi]; lpMem
0x14005421b  call    pMemFree
0x140054220  mov     rcx, [rbx+60h]; lpMem
0x140054224  mov     [rsi], r15
0x140054227  call    pMemFree
0x14005422c  mov     [rbx+60h], r15
0x140054230  test    rdi, rdi
0x140054233  jz      loc_140054433
0x140054239  jmp     loc_140054424
0x14005423e  xor     r9d, r9d
0x140054241  mov     dword ptr [rbp+Data], r15d
0x140054245  lea     r8, [rbp+Data]; lpData
0x140054249  mov     rcx, rdi; hKey
0x14005424c  lea     rdx, aArchiveagelimi; "ArchiveAgeLimit"
0x140054253  mov     r14d, r15d
0x140054256  call    GetRegistryDwordDefault
0x14005425b  neg     eax
0x14005425d  lea     r8, [rbx+50h]; lpData
0x140054261  mov     r9d, 1
0x140054267  lea     rdx, aAutocreateacco; "AutoCreateAccountOnConnect"
0x14005426e  sbb     ecx, ecx
0x140054270  and     ecx, dword ptr [rbp+Data]
0x140054273  mov     [rbx+4Ch], ecx
0x140054276  mov     rcx, rdi; hKey
0x140054279  call    GetRegistryDwordDefault
0x14005427e  test    eax, eax
0x140054280  jnz     short loc_1400542D4
0x140054282  mov     rax, cs:WPP_GLOBAL_Control
0x140054289  cmp     rax, r13
0x14005428c  jz      short loc_1400542CD
0x14005428e  test    byte ptr [rax+1Ch], 4
0x140054292  jz      short loc_1400542CD
0x140054294  cmp     byte ptr [rax+19h], 3
0x140054298  jb      short loc_1400542CD
0x14005429a  call    cs:__imp_GetLastError
0x1400542a1  nop     dword ptr [rax+rax+00h]
0x1400542a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400542ad  lea     r9, aAutocreateacco; "AutoCreateAccountOnConnect"
0x1400542b4  mov     edx, 0Fh
0x1400542b9  mov     [rsp+30h+cbData], eax
0x1400542bd  lea     r8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x1400542c4  mov     rcx, [rcx+10h]
0x1400542c8  call    WPP_SF_Sd
0x1400542cd  mov     dword ptr [rbx+50h], 1
0x1400542d4  mov     r9d, 1
0x1400542da  lea     r8, [rbx+54h]; lpData
0x1400542de  lea     rdx, aIncomingfaxesa; "IncomingFaxesArePublic"
0x1400542e5  mov     rcx, rdi; hKey
0x1400542e8  call    GetRegistryDwordDefault
0x1400542ed  test    eax, eax
0x1400542ef  jnz     short loc_140054343
  ... truncated ...
```

# CMsiSecureRepairManager::NeedsSecureRepair(ushort const *,eSecRepairModeEnum &)

- ea: `0x18020ab20`
- end: `0x18020b093`
- name: `?NeedsSecureRepair@CMsiSecureRepairManager@@SA_NPEBGAEAW4eSecRepairModeEnum@@@Z`
- size: `1395`
- prototype: `bool __fastcall(const unsigned __int16 *, enum eSecRepairModeEnum *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030568`
- `0x1801770f0`

## callees

- `0x1800012d8`
- `0x1800013a8`
- `0x180019bb4`
- `0x180025a18`
- `0x18004295c`
- `0x18020aa9c`
- `0x18020ab20`
- `0x18020bc4c`
- `0x18020bc88`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18020abb8`
- `ADVAPI32!RegQueryValueExW` at `0x18020ac23`
- `ADVAPI32!RegQueryValueExW` at `0x18020aca5`
- `ADVAPI32!RegQueryValueExW` at `0x18020ad60`
- `ADVAPI32!RegQueryValueExW` at `0x18020af87`
- `ADVAPI32!RegQueryValueExW` at `0x18020abb8`
- `ADVAPI32!RegQueryValueExW` at `0x18020ac23`
- `ADVAPI32!RegQueryValueExW` at `0x18020aca5`
- `ADVAPI32!RegQueryValueExW` at `0x18020ad60`
- `ADVAPI32!RegQueryValueExW` at `0x18020af87`
- `ADVAPI32!RegCloseKey` at `0x18020b03f`
- `ADVAPI32!RegCloseKey` at `0x18020b052`
- `ADVAPI32!RegCloseKey` at `0x18020b03f`
- `ADVAPI32!RegCloseKey` at `0x18020b052`

## string_xrefs

- `0x18020ab6b`: `SOFTWARE\Policies\Microsoft\Windows\Installer`
- `0x18020ab9c`: `SecureRepairPolicy`
- `0x18020ac41`: `SECREPAIR:  Block Behaviour for repair using AllowList registry is set`
- `0x18020ace1`: `SECREPAIR:  Block Behaviour for repair using old AllowList registry is set`
- `0x18020ad98`: `SECREPAIR:  Block Behaviour for repair using old AllowList registry is set`
- `0x18020ae5c`: `SECREPAIR: product found in AllowList registry: %s`
- `0x18020ae2c`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairAllowList`
- `0x18020af2a`: `SECREPAIR: product found in old registry: %s`
- `0x18020affe`: `SECREPAIR: product found in old registry: %s`
- `0x18020aeb0`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairWhiteList`
- `0x18020af40`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairWhiteList`

## pseudocode

```c
char __fastcall CMsiSecureRepairManager::NeedsSecureRepair(const unsigned __int16 *a1, enum eSecRepairModeEnum *a2)
{
  unsigned int v3; // r8d
  char v4; // bl
  char v5; // r14
  bool v6; // si
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // r8d
  const WCHAR *v10; // rax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // r9
  const WCHAR *v13; // rax
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  __int64 v19; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  HKEY v21; // [rsp+70h] [rbp-10h] BYREF
  int Data; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+48h] BYREF

  cbData = 4;
  hKey = 0;
  v21 = 0;
  Data = 0;
  MsiString::MsiString((MsiString *)&v19, a1);
  v4 = 1;
  if ( MsiRegOpen64bitKey(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer", v3, 0x20019u, &hKey) )
    goto LABEL_63;
  v5 = 0;
  v6 = 0;
  if ( !RegQueryValueExW(hKey, L"SecureRepairPolicy", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    if ( !Data )
    {
      *(_DWORD *)a2 = 1;
      goto LABEL_60;
    }
    if ( Data == 1 )
    {
      v5 = 1;
      goto LABEL_60;
    }
    if ( Data != 2 )
    {
      *(_DWORD *)a2 = 0;
      goto LABEL_60;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl'::`2'::impl) )
    {
      if ( !RegQueryValueExW(hKey, L"BlockBehaviourWithAllowList", 0, 0, (LPBYTE)&Data, &cbData) && !Data )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR:  Block Behaviour for repair using AllowList registry is set",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        *(_DWORD *)a2 = 1;
      }
      if ( *(_DWORD *)a2 != 1
        && !RegQueryValueExW(hKey, L"BlockBehaviourWithWhiteList", 0, 0, (LPBYTE)&Data, &cbData)
        && !Data )
      {
        *(_DWORD *)a2 = 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"SECREPAIR:  Block Behaviour for repair using old AllowList registry is set",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          if ( !byte_18030A5B9 )
          {
            if ( (unsigned int)dword_1803058D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803058D0) )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v7,
                byte_1802F40B3);
LABEL_32:
            byte_18030A5B9 = 1;
          }
        }
      }
    }
    else if ( !RegQueryValueExW(hKey, L"BlockBehaviourWithWhiteList", 0, 0, (LPBYTE)&Data, &cbData) && !Data )
    {
      *(_DWORD *)a2 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR:  Block Behaviour for repair using old AllowList registry is set",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( !byte_18030A5B9 )
        {
          if ( (unsigned int)dword_1803058D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803058D0) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v8,
              qword_1802F4080);
          goto LABEL_32;
        }
      }
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl'::`2'::impl) )
    {
      if ( !MsiRegOpen64bitKey(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairWhiteList",
              v9,
              0x20019u,
              &v21) )
      {
        v15 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
        if ( !RegQueryValueExW(v21, v15, 0, 0, 0, 0) )
        {
          v6 = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
          {
            if ( !byte_18030A5B8 )
            {
              if ( (unsigned int)dword_1803058D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803058D0) )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v16,
                  byte_1802F4055);
              if ( g_dmDiagnosticMode )
              {
                v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
                DebugString(
                  9,
                  0,
                  0,
                  L"SECREPAIR: product found in old registry: %s",
                  v17,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              }
              byte_18030A5B8 = 1;
            }
          }
        }
        RegCloseKey(v21);
      }
      goto LABEL_60;
    }
    v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
    v6 = IsProductInSecureRepairList(L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairAllowList", v10);
    if ( v6 )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_60;
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v12 = L"SECREPAIR: product found in AllowList registry: %s";
    }
    else
    {
      v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v6 = IsProductInSecureRepairList(L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairWhiteList", v13);
      if ( !v6 )
        goto LABEL_60;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl)
        && !byte_18030A5B8 )
      {
        if ( (unsigned int)dword_1803058D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803058D0) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v14,
            word_1802F402A);
        byte_18030A5B8 = 1;
      }
      if ( !g_dmDiagnosticMode )
        goto LABEL_60;
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v12 = L"SECREPAIR: product found in old registry: %s";
    }
    DebugString(9, 0, 0, v12, v11, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
LABEL_60:
  RegCloseKey(hKey);
  if ( v6 || v5 )
    v4 = 0;
LABEL_63:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return v4;
}

```

## disassembly

```asm
0x18020ab20  mov     [rsp-28h+arg_0], rbx
0x18020ab25  mov     [rsp-28h+arg_8], rsi
0x18020ab2a  push    rbp
0x18020ab2b  push    rdi
0x18020ab2c  push    r12
0x18020ab2e  push    r14
0x18020ab30  push    r15
0x18020ab32  mov     rbp, rsp
0x18020ab35  sub     rsp, 80h
0x18020ab3c  xor     r15d, r15d
0x18020ab3f  mov     [rbp+cbData], 4
0x18020ab46  mov     rdi, rdx
0x18020ab49  mov     [rbp+hKey], r15
0x18020ab4d  mov     rdx, rcx; unsigned __int16 *
0x18020ab50  mov     [rbp+var_10], r15
0x18020ab54  lea     rcx, [rbp+var_20]; this
0x18020ab58  mov     [rbp+Data], r15d
0x18020ab5c  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18020ab61  lea     rax, [rbp+hKey]
0x18020ab65  mov     r9d, 20019h; unsigned int
0x18020ab6b  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18020ab72  mov     [rsp+80h+lpData], rax; HKEY *
0x18020ab77  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18020ab7e  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18020ab83  lea     ebx, [r15+1]
0x18020ab87  test    eax, eax
0x18020ab89  jnz     loc_18020B065
0x18020ab8f  mov     rcx, [rbp+hKey]; hKey
0x18020ab93  lea     rax, [rbp+cbData]
0x18020ab97  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18020ab9c  lea     rdx, aSecurerepairpo; "SecureRepairPolicy"
0x18020aba3  lea     rax, [rbp+Data]
0x18020aba7  xor     r9d, r9d; lpType
0x18020abaa  xor     r8d, r8d; lpReserved
0x18020abad  mov     [rsp+80h+lpData], rax; lpData
0x18020abb2  mov     r14b, r15b
0x18020abb5  mov     sil, r15b
0x18020abb8  call    cs:__imp_RegQueryValueExW
0x18020abbe  test    eax, eax
0x18020abc0  jnz     loc_18020B04E
0x18020abc6  mov     eax, [rbp+Data]
0x18020abc9  test    eax, eax
0x18020abcb  jz      loc_18020B04C
0x18020abd1  sub     eax, ebx
0x18020abd3  jz      loc_18020B047
0x18020abd9  sub     eax, ebx
0x18020abdb  jz      short loc_18020ABE5
0x18020abdd  mov     [rdi], r15d
0x18020abe0  jmp     loc_18020B04E
0x18020abe5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl(void)'::`2'::impl
0x18020abec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(void)
0x18020abf1  mov     rcx, [rbp+hKey]; hKey
0x18020abf5  lea     r12, aNull; "(NULL)"
0x18020abfc  xor     r9d, r9d; lpType
0x18020abff  xor     r8d, r8d; lpReserved
0x18020ac02  test    al, al
0x18020ac04  lea     rax, [rbp+cbData]
0x18020ac08  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18020ac0d  lea     rax, [rbp+Data]
0x18020ac11  mov     [rsp+80h+lpData], rax; lpData
0x18020ac16  jz      loc_18020AD59
0x18020ac1c  lea     rdx, aBlockbehaviour; "BlockBehaviourWithAllowList"
0x18020ac23  call    cs:__imp_RegQueryValueExW
0x18020ac29  test    eax, eax
0x18020ac2b  jnz     short loc_18020AC7A
0x18020ac2d  cmp     [rbp+Data], r15d
0x18020ac31  jnz     short loc_18020AC7A
0x18020ac33  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020ac3a  jz      short loc_18020AC78
0x18020ac3c  mov     [rsp+80h+var_28], r15; void *
0x18020ac41  lea     r9, aSecrepairBlock; "SECREPAIR:  Block Behaviour for repair "...
0x18020ac48  mov     [rsp+80h+var_30], r15d; unsigned int
0x18020ac4d  lea     ecx, [rax+9]; int
0x18020ac50  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18020ac55  xor     edx, edx; unsigned __int16
0x18020ac57  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18020ac5c  xor     r8d, r8d; int
0x18020ac5f  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18020ac64  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18020ac69  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18020ac6e  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x18020ac73  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18020ac78  mov     [rdi], ebx
0x18020ac7a  cmp     [rdi], ebx
0x18020ac7c  jz      loc_18020AE05
0x18020ac82  mov     rcx, [rbp+hKey]; hKey
0x18020ac86  lea     rax, [rbp+cbData]
0x18020ac8a  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18020ac8f  lea     rdx, aBlockbehaviour_0; "BlockBehaviourWithWhiteList"
0x18020ac96  lea     rax, [rbp+Data]
0x18020ac9a  xor     r9d, r9d; lpType
0x18020ac9d  xor     r8d, r8d; lpReserved
0x18020aca0  mov     [rsp+80h+lpData], rax; lpData
0x18020aca5  call    cs:__imp_RegQueryValueExW
0x18020acab  test    eax, eax
0x18020acad  jnz     loc_18020AE05
0x18020acb3  cmp     [rbp+Data], r15d
0x18020acb7  jnz     loc_18020AE05
0x18020acbd  mov     [rdi], ebx
0x18020acbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x18020acc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x18020accb  test    al, al
0x18020accd  jz      loc_18020AE05
0x18020acd3  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020acda  jz      short loc_18020AD18
0x18020acdc  mov     [rsp+80h+var_28], r15; void *
0x18020ace1  lea     r9, aSecrepairBlock_0; "SECREPAIR:  Block Behaviour for repair "...
0x18020ace8  mov     [rsp+80h+var_30], r15d; unsigned int
0x18020aced  xor     edx, edx; unsigned __int16
0x18020acef  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18020acf4  xor     r8d, r8d; int
0x18020acf7  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18020acfc  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18020ad01  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18020ad06  lea     ecx, [rdx+9]; int
0x18020ad09  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18020ad0e  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x18020ad13  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18020ad18  cmp     cs:byte_18030A5B9, r15b
0x18020ad1f  jnz     loc_18020AE05
0x18020ad25  mov     eax, cs:dword_1803058D0
0x18020ad2b  cmp     eax, 4
0x18020ad2e  jbe     loc_18020ADFF
0x18020ad34  lea     rcx, dword_1803058D0
0x18020ad3b  call    _tlgKeywordOn
0x18020ad40  test    al, al
0x18020ad42  jz      loc_18020ADFF
0x18020ad48  lea     rdx, byte_1802F40B3
0x18020ad4f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18020ad54  jmp     loc_18020ADFF
0x18020ad59  lea     rdx, aBlockbehaviour_0; "BlockBehaviourWithWhiteList"
0x18020ad60  call    cs:__imp_RegQueryValueExW
0x18020ad66  test    eax, eax
0x18020ad68  jnz     loc_18020AE05
0x18020ad6e  cmp     [rbp+Data], r15d
0x18020ad72  jnz     loc_18020AE05
0x18020ad78  mov     [rdi], ebx
0x18020ad7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x18020ad81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x18020ad86  test    al, al
0x18020ad88  jz      short loc_18020AE05
0x18020ad8a  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020ad91  jz      short loc_18020ADCF
0x18020ad93  mov     [rsp+80h+var_28], r15; void *
0x18020ad98  lea     r9, aSecrepairBlock_0; "SECREPAIR:  Block Behaviour for repair "...
0x18020ad9f  mov     [rsp+80h+var_30], r15d; unsigned int
0x18020ada4  xor     edx, edx; unsigned __int16
0x18020ada6  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18020adab  xor     r8d, r8d; int
0x18020adae  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18020adb3  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18020adb8  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18020adbd  lea     ecx, [rdx+9]; int
0x18020adc0  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18020adc5  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x18020adca  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18020adcf  cmp     cs:byte_18030A5B9, r15b
0x18020add6  jnz     short loc_18020AE05
0x18020add8  mov     eax, cs:dword_1803058D0
0x18020adde  cmp     eax, 4
0x18020ade1  jbe     short loc_18020ADFF
0x18020ade3  lea     rcx, dword_1803058D0
0x18020adea  call    _tlgKeywordOn
0x18020adef  test    al, al
0x18020adf1  jz      short loc_18020ADFF
0x18020adf3  lea     rdx, qword_1802F4080
0x18020adfa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18020adff  mov     cs:byte_18030A5B9, bl
0x18020ae05  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl(void)'::`2'::impl
0x18020ae0c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(void)
0x18020ae11  test    al, al
0x18020ae13  jz      loc_18020AF36
0x18020ae19  mov     rcx, [rbp+var_20]
0x18020ae1d  mov     rax, [rcx]
0x18020ae20  mov     rax, [rax+50h]
0x18020ae24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020ae29  mov     rdx, rax; lpValueName
0x18020ae2c  lea     rcx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18020ae33  call    ?IsProductInSecureRepairList@@YA_NPEBG0@Z; IsProductInSecureRepairList(ushort const *,ushort const *)
0x18020ae38  mov     sil, al
0x18020ae3b  test    al, al
0x18020ae3d  jz      short loc_18020AE9D
0x18020ae3f  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020ae46  jz      loc_18020B04E
0x18020ae4c  mov     rcx, [rbp+var_20]
0x18020ae50  mov     rdx, [rcx]
0x18020ae53  mov     rax, [rdx+50h]
0x18020ae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020ae5c  lea     r9, aSecrepairProdu; "SECREPAIR: product found in AllowList r"...
0x18020ae63  mov     [rsp+80h+var_28], r15; void *
0x18020ae68  xor     edx, edx; unsigned __int16
0x18020ae6a  mov     [rsp+80h+var_30], r15d; unsigned int
0x18020ae6f  xor     r8d, r8d; int
0x18020ae72  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18020ae77  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18020ae7c  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18020ae81  lea     ecx, [rdx+9]; int
0x18020ae84  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18020ae89  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18020ae8e  mov     [rsp+80h+lpData], rax; unsigned __int16 *
0x18020ae93  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18020ae98  jmp     loc_18020B04E
0x18020ae9d  mov     rcx, [rbp+var_20]
0x18020aea1  mov     rax, [rcx]
0x18020aea4  mov     rax, [rax+50h]
0x18020aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020aead  mov     rdx, rax; lpValueName
0x18020aeb0  lea     rcx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18020aeb7  call    ?IsProductInSecureRepairList@@YA_NPEBG0@Z; IsProductInSecureRepairList(ushort const *,ushort const *)
0x18020aebc  mov     sil, al
0x18020aebf  test    al, al
0x18020aec1  jz      loc_18020B04E
0x18020aec7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x18020aece  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x18020aed3  test    al, al
0x18020aed5  jz      short loc_18020AF0D
0x18020aed7  cmp     cs:byte_18030A5B8, r15b
0x18020aede  jnz     short loc_18020AF0D
0x18020aee0  mov     eax, cs:dword_1803058D0
0x18020aee6  cmp     eax, 4
0x18020aee9  jbe     short loc_18020AF07
0x18020aeeb  lea     rcx, dword_1803058D0
0x18020aef2  call    _tlgKeywordOn
0x18020aef7  test    al, al
0x18020aef9  jz      short loc_18020AF07
0x18020aefb  lea     rdx, word_1802F402A
0x18020af02  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18020af07  mov     cs:byte_18030A5B8, bl
0x18020af0d  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020af14  jz      loc_18020B04E
0x18020af1a  mov     rcx, [rbp+var_20]
0x18020af1e  mov     rax, [rcx]
0x18020af21  mov     rax, [rax+50h]
0x18020af25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020af2a  lea     r9, aSecrepairProdu_0; "SECREPAIR: product found in old registr"...
0x18020af31  jmp     loc_18020AE63
0x18020af36  lea     rax, [rbp+var_10]
0x18020af3a  mov     r9d, 20019h; unsigned int
0x18020af40  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18020af47  mov     [rsp+80h+lpData], rax; HKEY *
0x18020af4c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18020af53  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18020af58  test    eax, eax
0x18020af5a  jnz     loc_18020B04E
0x18020af60  mov     rcx, [rbp+var_20]
0x18020af64  mov     rax, [rcx]
0x18020af67  mov     rax, [rax+50h]
0x18020af6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020af70  mov     rcx, [rbp+var_10]; hKey
0x18020af74  xor     r9d, r9d; lpType
0x18020af77  xor     r8d, r8d; lpReserved
0x18020af7a  mov     [rsp+80h+lpcbData], r15; lpcbData
0x18020af7f  mov     rdx, rax; lpValueName
0x18020af82  mov     [rsp+80h+lpData], r15; lpData
0x18020af87  call    cs:__imp_RegQueryValueExW
0x18020af8d  test    eax, eax
0x18020af8f  jnz     loc_18020B03B
0x18020af95  mov     sil, bl
0x18020af98  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x18020af9f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x18020afa4  test    al, al
0x18020afa6  jz      loc_18020B03B
0x18020afac  cmp     cs:byte_18030A5B8, r15b
0x18020afb3  jnz     loc_18020B03B
0x18020afb9  mov     eax, cs:dword_1803058D0
0x18020afbf  cmp     eax, 4
0x18020afc2  jbe     short loc_18020AFE0
0x18020afc4  lea     rcx, dword_1803058D0
0x18020afcb  call    _tlgKeywordOn
0x18020afd0  test    al, al
0x18020afd2  jz      short loc_18020AFE0
0x18020afd4  lea     rdx, byte_1802F4055
0x18020afdb  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18020afe0  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18020afe7  jz      short loc_18020B035
0x18020afe9  mov     rcx, [rbp+var_20]
0x18020afed  mov     rax, [rcx]
0x18020aff0  mov     rax, [rax+50h]
0x18020aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020aff9  mov     [rsp+80h+var_28], r15; void *
0x18020affe  lea     r9, aSecrepairProdu_0; "SECREPAIR: product found in old registr"...
0x18020b005  mov     [rsp+80h+var_30], r15d; unsigned int
0x18020b00a  xor     edx, edx; unsigned __int16
0x18020b00c  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18020b011  xor     r8d, r8d; int
0x18020b014  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18020b019  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18020b01e  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18020b023  lea     ecx, [rdx+9]; int
0x18020b026  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18020b02b  mov     [rsp+80h+lpData], rax; unsigned __int16 *
0x18020b030  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18020b035  mov     cs:byte_18030A5B8, bl
0x18020b03b  mov     rcx, [rbp+var_10]; hKey
0x18020b03f  call    cs:__imp_RegCloseKey
0x18020b045  jmp     short loc_18020B04E
0x18020b047  mov     r14b, bl
0x18020b04a  jmp     short loc_18020B04E
0x18020b04c  mov     [rdi], ebx
0x18020b04e  mov     rcx, [rbp+hKey]; hKey
  ... truncated ...
```

# UpdateAutoTriggerRegKeysEx

- ea: `0x180030340`
- end: `0x1800314e0`
- name: `UpdateAutoTriggerRegKeysEx`
- size: `4512`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18000e650`
- `0x18001248c`
- `0x180017548`
- `0x180019ba4`
- `0x180030340`
- `0x1800322b8`
- `0x1800324b0`
- `0x180032d90`
- `0x180045e34`
- `0x18005c710`
- `0x180066068`
- `0x18007f9ec`
- `0x1800dc318`
- `0x1800e7260`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800304b0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800304b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003119a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003119a`
- `RPCRT4!RpcImpersonateClient` at `0x180031101`
- `RPCRT4!RpcImpersonateClient` at `0x180031101`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031190`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031190`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800305e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030667`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800305e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030af9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030c72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003129f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003130c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030af9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030c72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030f00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003129f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003130c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030842`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030892`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800308e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003093f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030df4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030842`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030892`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800308e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003093f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030df4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003050a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003050a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003063d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800310a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003063d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800310a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030f70`

## string_xrefs

- `0x1800304ca`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800304ba`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800304c1`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800304d1`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800308db`: `UserSID`
- `0x18003090f`: `UserSID`
- `0x18003128c`: `UserSID`
- `0x18003083b`: `AutoTriggerProfilePhonebookPath`
- `0x180030868`: `AutoTriggerProfilePhonebookPath`
- `0x180030e59`: `AutoTriggerProfilePhonebookPath`
- `0x180030eb2`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall UpdateAutoTriggerRegKeysEx(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rdi
  int v5; // esi
  BYTE *v6; // rdx
  int v7; // r14d
  int v8; // r13d
  BYTE *v9; // r12
  int v10; // r15d
  struct _LIST_ENTRY **v11; // r8
  const char *v12; // rcx
  const char *v13; // r11
  const char *v14; // r10
  const char *v15; // r9
  char IsStateSeparationEnabled; // al
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r9
  unsigned int UserSid; // ebx
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  int v25; // edi
  unsigned int v26; // eax
  LSTATUS v27; // eax
  struct _LIST_ENTRY *v28; // rcx
  __int64 v29; // rdx
  unsigned int active; // eax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  struct _LIST_ENTRY *v35; // rcx
  unsigned int v36; // eax
  LSTATUS v37; // eax
  BYTE *v38; // r14
  unsigned int v39; // eax
  LSTATUS v40; // eax
  __int64 v41; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  LSTATUS v43; // eax
  __int64 v44; // rdi
  __int64 v45; // rax
  DWORD LastError; // eax
  struct _LIST_ENTRY *v47; // rcx
  int v48; // edx
  const WCHAR *v49; // r9
  __int64 v50; // rax
  LSTATUS v51; // eax
  __int64 result; // rax
  int v53; // r13d
  BYTE *v54; // r15
  __int64 v55; // rax
  struct _LIST_ENTRY *v56; // rcx
  struct _LIST_ENTRY *v57; // rcx
  const char *v58; // r9
  const BYTE *v59; // rcx
  LSTATUS v60; // eax
  const char *v61; // rdi
  const char *v62; // r9
  unsigned int v63; // eax
  struct _LIST_ENTRY *v64; // rcx
  struct _LIST_ENTRY *v65; // rcx
  int dwOptions; // [rsp+20h] [rbp-99h]
  int samDesired; // [rsp+28h] [rbp-91h]
  DWORD cbData; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  DWORD Type; // [rsp+70h] [rbp-49h] BYREF
  BYTE *v71; // [rsp+78h] [rbp-41h]
  int v72; // [rsp+80h] [rbp-39h]
  BYTE *lpData; // [rsp+88h] [rbp-31h] BYREF
  int v74; // [rsp+90h] [rbp-29h]
  HLOCAL hMem; // [rsp+98h] [rbp-21h]
  BYTE Data[8]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int *v77; // [rsp+A8h] [rbp-11h]
  BYTE v78[16]; // [rsp+B0h] [rbp-9h] BYREF

  v77 = (unsigned int *)a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1372, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD *)(a3 + 1580);
  v6 = (BYTE *)(a3 + 4);
  v7 = *(_DWORD *)(a3 + 1056);
  v8 = *(_DWORD *)(a3 + 1060);
  v9 = (BYTE *)(a3 + 518);
  v10 = *(_DWORD *)(a3 + 1584);
  *(_OWORD *)v78 = *(_OWORD *)(a3 + 1040);
  v71 = (BYTE *)(a3 + 4);
  hMem = (HLOCAL)(a3 + 1064);
  v74 = 0;
  v72 = v5;
  lpData = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  *(_DWORD *)Data = 1;
  v11 = &WPP_GLOBAL_Control;
  v12 = L"<NULL>";
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 5u )
  {
    v13 = L"<NULL>";
    v14 = L"<NULL>";
    v15 = L"<NULL>";
    if ( a3 != -1064 )
      v13 = (const char *)(a3 + 1064);
    if ( a3 != -4 )
      v14 = (const char *)(a3 + 4);
    if ( a3 != -518 )
      LODWORD(v15) = a3 + 518;
    LOBYTE(v11) = v5 != 0;
    LOBYTE(v6) = v10 != 0;
    WPP_SF_SSS_guid_cccc(
      v4[1].Flink,
      (_DWORD)v6,
      (_DWORD)v11,
      (_DWORD)v15,
      (__int64)v14,
      (__int64)v13,
      (__int64)v78,
      v7 != 0,
      v8 != 0,
      v10 != 0,
      v5 != 0);
    v6 = v71;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a3 == -518 || !v6 )
  {
    UserSid = 87;
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v4[1].Blink) & 0x2000) == 0
      || BYTE1(v4[1].Blink) < 2u )
    {
      goto LABEL_194;
    }
    Flink = v4[1].Flink;
    v41 = 1374;
    goto LABEL_170;
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v12);
  if ( v5 )
  {
    v17 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    v18 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  }
  else
  {
    v18 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
    v17 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  }
  if ( !IsStateSeparationEnabled )
    v18 = v17;
  v19 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0, 0, 0x20007u, 0, &hKey, 0);
  UserSid = v19;
  if ( v19 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v23 = 1375;
LABEL_27:
      WPP_SF_d(v22[1].Flink, v23, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v19);
      goto LABEL_194;
    }
    goto LABEL_194;
  }
  if ( !v5 || (v19 = ProfileSatisifesLockDownPolicy(v71, v9), (UserSid = v19) == 0) )
  {
    v24 = v72;
    v25 = 0;
    if ( v72 )
    {
      v26 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, 0, &cbData);
      if ( v26 || Type != 7 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
        {
LABEL_59:
          if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v28[1].Blink) & 0x2000) != 0
            && BYTE1(v28[1].Blink) >= 5u )
          {
            LOBYTE(samDesired) = v25;
            LOBYTE(dwOptions) = v10 != 0;
            LOBYTE(v20) = v7 != 0;
            WPP_SF_ccc(v28[1].Flink, 1381, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v20, dwOptions, samDesired);
            v28 = WPP_GLOBAL_Control;
          }
LABEL_63:
          if ( v7 )
          {
            if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v28[1].Blink) & 0x2000) != 0
              && BYTE1(v28[1].Blink) >= 5u )
            {
              WPP_SF_(v28[1].Flink, 1382, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
            }
            active = VpnProfileActiveSet(0, 0, 0, v24);
            if ( active
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1383, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, active);
            }
            v31 = RegDeleteValueW(hKey, L"AutoTriggerProfilePhonebookPath");
            if ( v31
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1384,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned int)L"AutoTriggerProfilePhonebookPath",
                v31);
            }
            v32 = RegDeleteValueW(hKey, L"AutoTriggerProfileEntryName");
            if ( v32
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1385,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned int)L"AutoTriggerProfileEntryName",
                v32);
            }
            v33 = RegDeleteValueW(hKey, L"UserSID");
            if ( v33
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1386,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned int)L"UserSID",
                v33);
            }
            v34 = RegDeleteValueW(hKey, L"AutoTriggerProfileGUID");
            UserSid = v34;
            if ( v34 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1387,
                  (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                  (unsigned int)L"AutoTriggerProfileGUID",
                  v34);
                v35 = WPP_GLOBAL_Control;
              }
              UserSid = 0;
            }
            else
            {
              v35 = WPP_GLOBAL_Control;
            }
            if ( !v72 || !v10 )
              goto LABEL_118;
            if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v35[1].Blink) & 0x2000) != 0
              && BYTE1(v35[1].Blink) >= 4u )
            {
              WPP_SF_(v35[1].Flink, 1388, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              v35 = WPP_GLOBAL_Control;
            }
            if ( v25 )
              goto LABEL_118;
            v36 = AddWStringToWMultiStringStart(&lpData, &cbData, v71);
            UserSid = 0;
            if ( v36 )
            {
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_118;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1391, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v36);
            }
            else
            {
              v37 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
              UserSid = v37;
              if ( v37 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control[1].Flink,
                    1389,
                    (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                    (unsigned int)L"AutoTriggerDisabledProfilesList",
                    v37);
                  v35 = WPP_GLOBAL_Control;
                }
                UserSid = 0;
                goto LABEL_118;
              }
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u )
              {
LABEL_118:
                if ( v8 )
                {
                  UserSid = RegSetValueExW(hKey, L"AutoTriggeringDisabled", 0, 4u, Data, 4u);
                  if ( UserSid )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
                    {
                      WPP_SF_S(
                        WPP_GLOBAL_Control[1].Flink,
                        1392,
                        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                        L"AutoTriggeringDisabled");
                      v35 = WPP_GLOBAL_Control;
                    }
                    UserSid = 0;
                  }
                  else
                  {
                    v35 = WPP_GLOBAL_Control;
                  }
                }
                if ( v35 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v35[1].Blink) & 0x2000) != 0
                  && BYTE1(v35[1].Blink) >= 4u )
                {
                  WPP_SF_(v35[1].Flink, 1393, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
                }
                goto LABEL_192;
              }
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1390, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
            }
            v35 = WPP_GLOBAL_Control;
            goto LABEL_118;
          }
          if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v28[1].Blink) & 0x2000) != 0
            && BYTE1(v28[1].Blink) >= 5u )
          {
            WPP_SF_(v28[1].Flink, 1394, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v10 && v24 )
          {
            if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(v28[1].Blink) & 0x2000) != 0 && BYTE1(v28[1].Blink) >= 5u )
              {
                WPP_SF_(v28[1].Flink, 1395, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
                v28 = WPP_GLOBAL_Control;
              }
              if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v28[1].Blink) & 0x2000) != 0
                && BYTE1(v28[1].Blink) >= 4u )
              {
                WPP_SF_(v28[1].Flink, 1396, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              }
            }
            v38 = v71;
            if ( v25 )
            {
              v39 = DeleteWStringFromWMultiString(&lpData, &cbData, v71);
              if ( v39 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1399, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v39);
                }
              }
              else
              {
                v40 = RegSetValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, 7u, lpData, cbData);
                if ( v40 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_Sd(
                      WPP_GLOBAL_Control[1].Flink,
                      1397,
                      (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                      (unsigned int)L"AutoTriggerDisabledProfilesList",
                      v40);
                  }
                }
                else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                       && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                       && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1398, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
                }
              }
            }
          }
          else
          {
            if ( v25 && v24 )
            {
              if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v28[1].Blink) & 0x2000) != 0
                && BYTE1(v28[1].Blink) >= 5u )
              {
                WPP_SF_(v28[1].Flink, 1400, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
                v28 = WPP_GLOBAL_Control;
              }
              UserSid = 1206;
              if ( v28 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(v28[1].Blink) & 0x2000) == 0
                || BYTE1(v28[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v41 = 1401;
              goto LABEL_169;
            }
            v38 = v71;
          }
          v43 = RegDeleteValueW(hKey, L"AutoTriggeringDisabled");
          if ( v43
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control[1].Flink,
              1402,
              (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
              (unsigned int)L"AutoTriggeringDisabled",
              v43);
          }
          v44 = -1;
          v45 = -1;
          do
            ++v45;
          while ( *(_WORD *)&v9[2 * v45] );
          LastError = RegSetValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, 1u, v9, 2 * v45 + 2);
          UserSid = LastError;
          if ( LastError )
          {
            v47 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v48 = 1403;
              v49 = L"AutoTriggerProfilePhonebookPath";
LABEL_184:
              WPP_SF_Sd(
                v47[1].Flink,
                v48,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (_DWORD)v49,
                LastError);
            }
LABEL_192:
            if ( lpData )
              LocalFree(lpData);
            goto LABEL_194;
          }
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)&v38[2 * v50] );
          v51 = RegSetValueExW(hKey, L"AutoTriggerProfileEntryName", 0, 1u, v38, 2 * v50 + 2);
          UserSid = v51;
          if ( v51 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control[1].Flink,
                1404,
                (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned int)L"AutoTriggerProfileEntryName",
                v51);
            }
            goto LABEL_192;
          }
          v53 = v72;
          v54 = (BYTE *)hMem;
          if ( !v72 )
          {
            v59 = (const BYTE *)L"S-1-5-80-4176366874-305252471-2256717057-2714189771-3552532790";
            do
LABEL_256:
              ++v44;
            while ( *(_WORD *)&v54[2 * v44] );
            UserSid = RegSetValueExW(hKey, L"UserSID", 0, 1u, v59, 2 * v44 + 2);
            if ( UserSid )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1414,
                  (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                  (unsigned int)L"AutoTriggerProfileEntryName",
                  UserSid);
              }
              goto LABEL_192;
            }
            v60 = RegSetValueExW(hKey, L"AutoTriggerProfileGUID", 0, 3u, v78, 0x10u);
            UserSid = v60;
            if ( v60 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  1415,
                  (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                  (unsigned int)L"AutoTriggerProfileGUID",
                  v60);
              }
              goto LABEL_192;
            }
            v61 = L"<NULL>";
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              v62 = L"<NULL>";
              if ( v54 )
                v62 = (const char *)v54;
              WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 1416, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v62);
            }
            v63 = VpnProfileActiveSet(v9, v71, v54, v53);
            UserSid = v63;
            if ( v63 )
            {
              v64 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                goto LABEL_192;
              if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
LABEL_279:
                if ( v64 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v64[1].Blink) & 0x2000) != 0
                  && BYTE1(v64[1].Blink) >= 5u )
                {
                  v65 = v64[1].Flink;
                  if ( v54 )
                    v61 = (const char *)v54;
                  WPP_SF_S(v65, 1418, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v61);
                }
                goto LABEL_192;
              }
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1417, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v63);
            }
            v64 = WPP_GLOBAL_Control;
            goto LABEL_279;
          }
          if ( hMem )
          {
            v55 = -1;
            do
              ++v55;
            while ( *((_WORD *)hMem + v55) );
            if ( v55 )
            {
LABEL_254:
              v59 = v54;
              goto LABEL_256;
            }
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1405, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          if ( (unsigned int)IsPublicPhonebook(v9) )
          {
            v56 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1406, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
              v56 = WPP_GLOBAL_Control;
            }
            v54 = (BYTE *)L"S-1-1-0";
            hMem = (HLOCAL)L"S-1-1-0";
            goto LABEL_248;
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1407, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          hMem = LocalAlloc(0x40u, 0x1388u);
          v54 = (BYTE *)hMem;
          v74 = 1;
          if ( hMem )
          {
            LastError = RpcImpersonateClient(g_hRpcHandle);
            UserSid = LastError;
            if ( LastError )
            {
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v48 = 1409;
            }
            else
            {
              UserSid = GetUserSid(v54);
              if ( UserSid
                && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1410, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
              }
              if ( RevertToSelf() )
              {
                if ( !UserSid )
                {
                  v56 = WPP_GLOBAL_Control;
LABEL_248:
                  if ( v56 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v56[1].Blink) & 0x2000) != 0
                    && BYTE1(v56[1].Blink) >= 5u )
                  {
                    v57 = v56[1].Flink;
                    v58 = L"<NULL>";
                    if ( v54 )
                      v58 = (const char *)v54;
                    WPP_SF_S(v57, 1413, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v58);
                  }
                  goto LABEL_254;
                }
                v28 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                {
                  goto LABEL_192;
                }
                v41 = 1412;
                goto LABEL_169;
              }
              LastError = GetLastError();
              UserSid = LastError;
              if ( !LastError )
                goto LABEL_192;
              v47 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              {
                goto LABEL_192;
              }
              v48 = 1411;
            }
            LODWORD(v49) = (_DWORD)v9;
            goto LABEL_184;
          }
          UserSid = 8;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_192;
          }
          v41 = 1408;
LABEL_169:
          Flink = v28[1].Flink;
LABEL_170:
          WPP_SF_d(Flink, v41, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
          goto LABEL_192;
        }
        v29 = 1380;
        goto LABEL_57;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1377, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      }
      lpData = (BYTE *)LocalAlloc(0x40u, cbData);
      v27 = RegQueryValueExW(hKey, L"AutoTriggerDisabledProfilesList", 0, &Type, lpData, &cbData);
      if ( v27 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_59;
        WPP_SF_Sd(
          WPP_GLOBAL_Control[1].Flink,
          1379,
          (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
          (unsigned int)L"AutoTriggerDisabledProfilesList",
          v27);
        goto LABEL_58;
      }
      if ( Type == 7 )
      {
        v26 = WideMultiStringListLookUp(lpData, cbData, v71);
        if ( !v26 )
        {
          v25 = 1;
          goto LABEL_58;
        }
        v25 = 0;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_63;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_59;
        v29 = 1378;
LABEL_57:
        WPP_SF_d(v28[1].Flink, v29, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v26);
      }
    }
LABEL_58:
    v28 = WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v23 = 1376;
    goto LABEL_27;
  }
LABEL_194:
  if ( hMem && v74 )
    LocalFree(hMem);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  *v77 = UserSid;
  if ( (Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_featureState & 0x10) != 0 )
    result = Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_featureState & 1;
  else
    result = Feature_VPN_BugFixes_25C_Disable_AutoConnectProfile_During_Disconnect__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
    result = SendAutoConnectModifiedNotification();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1419, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, UserSid);
  }
  return result;
}

```

## disassembly

```asm
0x180030340  push    rbp
0x180030342  push    rbx
0x180030343  push    rsi
0x180030344  push    rdi
0x180030345  push    r12
0x180030347  push    r13
0x180030349  push    r14
0x18003034b  push    r15
0x18003034d  lea     rbp, [rsp-1Fh]
0x180030352  sub     rsp, 0D8h
0x180030359  mov     rax, cs:__security_cookie
0x180030360  xor     rax, rsp
0x180030363  mov     [rbp+57h+var_50], rax
0x180030367  mov     rbx, r8
0x18003036a  mov     [rbp+57h+var_68], rbx
0x18003036e  mov     rdi, cs:WPP_GLOBAL_Control
0x180030375  lea     rax, WPP_GLOBAL_Control
0x18003037c  cmp     rdi, rax
0x18003037f  jz      short loc_1800303AC
0x180030381  test    dword ptr [rdi+1Ch], 2000h
0x180030388  jz      short loc_1800303AC
0x18003038a  cmp     byte ptr [rdi+19h], 6
0x18003038e  jb      short loc_1800303AC
0x180030390  mov     rcx, [rdi+10h]
0x180030394  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18003039b  mov     edx, 55Ch
0x1800303a0  call    WPP_SF_
0x1800303a5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800303ac  movups  xmm0, xmmword ptr [rbx+410h]
0x1800303b3  mov     esi, [rbx+62Ch]
0x1800303b9  lea     rdx, [rbx+4]
0x1800303bd  mov     r14d, [rbx+420h]
0x1800303c4  lea     rax, [rbx+428h]
0x1800303cb  mov     r13d, [rbx+424h]
0x1800303d2  lea     r12, [rbx+206h]
0x1800303d9  mov     r15d, [rbx+630h]
0x1800303e0  xor     ebx, ebx
0x1800303e2  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800303e7  mov     [rbp+57h+var_98], rdx
0x1800303eb  mov     [rbp+57h+hMem], rax
0x1800303ef  mov     [rbp+57h+var_80], 0
0x1800303f6  mov     [rbp+57h+var_90], esi
0x1800303f9  mov     [rbp+57h+lpData], rbx
0x1800303fd  mov     [rbp+57h+cbData], ebx
0x180030400  mov     [rbp+57h+Type], ebx
0x180030403  mov     [rbp+57h+hKey], rbx
0x180030407  mov     dword ptr [rbp+57h+Data], 1
0x18003040e  lea     r8, WPP_GLOBAL_Control
0x180030415  lea     rcx, aNull_5; "<NULL>"
0x18003041c  cmp     rdi, r8
0x18003041f  jz      short loc_18003049E
0x180030421  test    dword ptr [rdi+1Ch], 2000h
0x180030428  jz      short loc_18003049E
0x18003042a  cmp     byte ptr [rdi+19h], 5
0x18003042e  jb      short loc_18003049E
0x180030430  test    rax, rax
0x180030433  mov     r11, rcx
0x180030436  mov     r10, rcx
0x180030439  mov     r9, rcx
0x18003043c  cmovnz  r11, rax
0x180030440  test    rdx, rdx
0x180030443  cmovnz  r10, rdx
0x180030447  test    r12, r12
0x18003044a  cmovnz  r9, r12
0x18003044e  test    esi, esi
0x180030450  setnz   r8b
0x180030454  test    r15d, r15d
0x180030457  mov     [rsp+110h+var_C0], r8b
0x18003045c  setnz   dl
0x18003045f  test    r13d, r13d
0x180030462  mov     [rsp+110h+var_C8], dl
0x180030466  setnz   cl
0x180030469  test    r14d, r14d
0x18003046c  mov     byte ptr [rsp+110h+lpdwDisposition], cl
0x180030470  mov     rcx, [rdi+10h]
0x180030474  setnz   al
0x180030477  mov     byte ptr [rsp+110h+phkResult], al
0x18003047b  lea     rax, [rbp+57h+var_60]
0x18003047f  mov     [rsp+110h+lpSecurityAttributes], rax
0x180030484  mov     qword ptr [rsp+110h+samDesired], r11
0x180030489  mov     qword ptr [rsp+110h+dwOptions], r10
0x18003048e  call    WPP_SF_SSS_guid_cccc
0x180030493  mov     rdx, [rbp+57h+var_98]
0x180030497  mov     rdi, cs:WPP_GLOBAL_Control
0x18003049e  test    r12, r12
0x1800304a1  jz      loc_180031442
0x1800304a7  test    rdx, rdx
0x1800304aa  jz      loc_180031442
0x1800304b0  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800304b6  test    esi, esi
0x1800304b8  jz      short loc_1800304CA
0x1800304ba  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800304c1  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800304c8  jmp     short loc_1800304D8
0x1800304ca  lea     rdx, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800304d1  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800304d8  mov     [rsp+110h+lpdwDisposition], rbx; lpdwDisposition
0x1800304dd  test    al, al
0x1800304df  lea     rax, [rbp+57h+hKey]
0x1800304e3  mov     [rsp+110h+phkResult], rax; phkResult
0x1800304e8  cmovz   rdx, rcx; lpSubKey
0x1800304ec  mov     [rsp+110h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800304f1  xor     r9d, r9d; lpClass
0x1800304f4  mov     [rsp+110h+samDesired], 20007h; samDesired
0x1800304fc  xor     r8d, r8d; Reserved
0x1800304ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030506  mov     [rsp+110h+dwOptions], ebx; dwOptions
0x18003050a  call    cs:__imp_RegCreateKeyExW
0x180030510  xor     ecx, ecx
0x180030512  mov     ebx, eax
0x180030514  test    eax, eax
0x180030516  jz      short loc_180030566
0x180030518  mov     rcx, cs:WPP_GLOBAL_Control
0x18003051f  lea     r14, WPP_GLOBAL_Control
0x180030526  cmp     rcx, r14
0x180030529  jz      loc_180030F60
0x18003052f  test    dword ptr [rcx+1Ch], 2000h
0x180030536  jz      loc_180030F60
0x18003053c  mov     sil, 2
0x18003053f  cmp     [rcx+19h], sil
0x180030543  jb      loc_180030F60
0x180030549  mov     edx, 55Fh
0x18003054e  mov     rcx, [rcx+10h]
0x180030552  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180030559  mov     r9d, eax
0x18003055c  call    WPP_SF_d
0x180030561  jmp     loc_180030F60
0x180030566  test    esi, esi
0x180030568  jz      short loc_1800305B6
0x18003056a  mov     rcx, [rbp+57h+var_98]
0x18003056e  mov     rdx, r12
0x180030571  call    ProfileSatisifesLockDownPolicy
0x180030576  xor     ecx, ecx
0x180030578  mov     ebx, eax
0x18003057a  test    eax, eax
0x18003057c  jz      short loc_1800305B6
0x18003057e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030585  lea     r14, WPP_GLOBAL_Control
0x18003058c  cmp     rcx, r14
0x18003058f  jz      loc_180030F60
0x180030595  test    dword ptr [rcx+1Ch], 2000h
0x18003059c  jz      loc_180030F60
0x1800305a2  mov     sil, 2
0x1800305a5  cmp     [rcx+19h], sil
0x1800305a9  jb      loc_180030F60
0x1800305af  mov     edx, 560h
0x1800305b4  jmp     short loc_18003054E
0x1800305b6  mov     ebx, [rbp+57h+var_90]
0x1800305b9  mov     edi, ecx
0x1800305bb  mov     sil, 2
0x1800305be  test    ebx, ebx
0x1800305c0  jz      loc_180030750
0x1800305c6  lea     rax, [rbp+57h+cbData]
0x1800305ca  xor     r8d, r8d; lpReserved
0x1800305cd  mov     qword ptr [rsp+110h+samDesired], rax; lpcbData
0x1800305d2  lea     r9, [rbp+57h+Type]; lpType
0x1800305d6  mov     qword ptr [rsp+110h+dwOptions], rcx; lpData
0x1800305db  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x1800305e2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800305e6  call    cs:__imp_RegQueryValueExW
0x1800305ec  test    eax, eax
0x1800305ee  jnz     loc_180030716
0x1800305f4  cmp     [rbp+57h+Type], 7
0x1800305f8  jnz     loc_180030716
0x1800305fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180030605  lea     rax, WPP_GLOBAL_Control
0x18003060c  cmp     rcx, rax
0x18003060f  jz      short loc_180030635
0x180030611  test    dword ptr [rcx+1Ch], 2000h
0x180030618  jz      short loc_180030635
0x18003061a  cmp     byte ptr [rcx+19h], 4
0x18003061e  jb      short loc_180030635
0x180030620  mov     rcx, [rcx+10h]
0x180030624  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18003062b  mov     edx, 561h
0x180030630  call    WPP_SF_
0x180030635  mov     edx, [rbp+57h+cbData]; uBytes
0x180030638  mov     ecx, 40h ; '@'; uFlags
0x18003063d  call    cs:__imp_LocalAlloc
0x180030643  lea     rcx, [rbp+57h+cbData]
0x180030647  xor     r8d, r8d; lpReserved
0x18003064a  lea     r9, [rbp+57h+Type]; lpType
0x18003064e  mov     [rbp+57h+lpData], rax
0x180030652  mov     qword ptr [rsp+110h+samDesired], rcx; lpcbData
0x180030657  lea     rdx, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x18003065e  mov     rcx, [rbp+57h+hKey]; hKey
0x180030662  mov     qword ptr [rsp+110h+dwOptions], rax; lpData
0x180030667  call    cs:__imp_RegQueryValueExW
0x18003066d  test    eax, eax
0x18003066f  jnz     short loc_1800306CE
0x180030671  cmp     [rbp+57h+Type], 7
0x180030675  jnz     loc_180030750
0x18003067b  mov     r8, [rbp+57h+var_98]
0x18003067f  mov     edx, [rbp+57h+cbData]
0x180030682  mov     rcx, [rbp+57h+lpData]
0x180030686  call    WideMultiStringListLookUp
0x18003068b  test    eax, eax
0x18003068d  jnz     short loc_180030697
0x18003068f  lea     edi, [rax+1]
0x180030692  jmp     loc_180030750
0x180030697  xor     edi, edi
0x180030699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306a0  lea     r8, WPP_GLOBAL_Control
0x1800306a7  cmp     rcx, r8
0x1800306aa  jz      loc_1800307A4
0x1800306b0  test    dword ptr [rcx+1Ch], 2000h
0x1800306b7  jz      loc_180030757
0x1800306bd  cmp     [rcx+19h], sil
0x1800306c1  jb      loc_180030757
0x1800306c7  mov     edx, 562h
0x1800306cc  jmp     short loc_18003073D
0x1800306ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306d5  lea     r8, WPP_GLOBAL_Control
0x1800306dc  cmp     rcx, r8
0x1800306df  jz      loc_1800307A4
0x1800306e5  test    dword ptr [rcx+1Ch], 2000h
0x1800306ec  jz      short loc_180030757
0x1800306ee  cmp     [rcx+19h], sil
0x1800306f2  jb      short loc_180030757
0x1800306f4  mov     rcx, [rcx+10h]
0x1800306f8  lea     r9, aAutotriggerdis; "AutoTriggerDisabledProfilesList"
0x1800306ff  mov     edx, 563h
0x180030704  mov     [rsp+110h+dwOptions], eax
0x180030708  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18003070f  call    WPP_SF_Sd
0x180030714  jmp     short loc_180030750
0x180030716  mov     rcx, cs:WPP_GLOBAL_Control
0x18003071d  lea     rdx, WPP_GLOBAL_Control
0x180030724  cmp     rcx, rdx
0x180030727  jz      short loc_1800307A4
0x180030729  test    dword ptr [rcx+1Ch], 2000h
0x180030730  jz      short loc_180030757
0x180030732  cmp     byte ptr [rcx+19h], 4
0x180030736  jb      short loc_180030757
0x180030738  mov     edx, 564h
0x18003073d  mov     rcx, [rcx+10h]
0x180030741  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180030748  mov     r9d, eax
0x18003074b  call    WPP_SF_d
0x180030750  mov     rcx, cs:WPP_GLOBAL_Control
0x180030757  lea     rax, WPP_GLOBAL_Control
0x18003075e  cmp     rcx, rax
0x180030761  jz      short loc_1800307A4
0x180030763  test    dword ptr [rcx+1Ch], 2000h
0x18003076a  jz      short loc_1800307A4
0x18003076c  cmp     byte ptr [rcx+19h], 5
0x180030770  jb      short loc_1800307A4
0x180030772  mov     rcx, [rcx+10h]
0x180030776  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18003077d  test    r15d, r15d
0x180030780  mov     byte ptr [rsp+110h+samDesired], dil
0x180030785  mov     edx, 565h
0x18003078a  setnz   al
0x18003078d  test    r14d, r14d
0x180030790  mov     byte ptr [rsp+110h+dwOptions], al
0x180030794  setnz   r9b
0x180030798  call    WPP_SF_ccc
0x18003079d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307a4  test    r14d, r14d
0x1800307a7  jz      loc_180030B89
0x1800307ad  lea     rax, WPP_GLOBAL_Control
0x1800307b4  mov     r12d, 2000h
0x1800307ba  cmp     rcx, rax
0x1800307bd  jz      short loc_1800307E0
0x1800307bf  test    [rcx+1Ch], r12d
0x1800307c3  jz      short loc_1800307E0
0x1800307c5  cmp     byte ptr [rcx+19h], 5
0x1800307c9  jb      short loc_1800307E0
0x1800307cb  mov     rcx, [rcx+10h]
0x1800307cf  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800307d6  mov     edx, 566h
0x1800307db  call    WPP_SF_
0x1800307e0  mov     r9d, r14d
0x1800307e3  mov     [rsp+110h+dwOptions], ebx; int
0x1800307e7  xor     r8d, r8d; void *
0x1800307ea  xor     edx, edx; void *
0x1800307ec  xor     ecx, ecx; Src
0x1800307ee  call    VpnProfileActiveSet
0x1800307f3  test    eax, eax
0x1800307f5  jz      short loc_180030830
0x1800307f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307fe  lea     r14, WPP_GLOBAL_Control
0x180030805  cmp     rcx, r14
0x180030808  jz      short loc_180030837
0x18003080a  test    [rcx+1Ch], r12d
0x18003080e  jz      short loc_180030837
0x180030810  cmp     [rcx+19h], sil
0x180030814  jb      short loc_180030837
0x180030816  mov     rcx, [rcx+10h]
0x18003081a  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180030821  mov     edx, 567h
0x180030826  mov     r9d, eax
0x180030829  call    WPP_SF_d
0x18003082e  jmp     short loc_180030837
0x180030830  lea     r14, WPP_GLOBAL_Control
0x180030837  mov     rcx, [rbp+57h+hKey]; hKey
0x18003083b  lea     rdx, aAutotriggerpro_2; "AutoTriggerProfilePhonebookPath"
0x180030842  call    cs:__imp_RegDeleteValueW
0x180030848  test    eax, eax
0x18003084a  jz      short loc_180030884
  ... truncated ...
```

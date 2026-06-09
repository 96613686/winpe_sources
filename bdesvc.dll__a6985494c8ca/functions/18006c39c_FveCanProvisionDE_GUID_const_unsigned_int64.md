# FveCanProvisionDE(_GUID const *,unsigned __int64 *)

- ea: `0x18006c39c`
- end: `0x18006cd79`
- name: `?FveCanProvisionDE@@YAHPEBU_GUID@@PEA_K@Z`
- size: `2525`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800053a0`
- `0x18001e900`
- `0x180047e6c`

## callees

- `0x180001fe8`
- `0x1800032d0`
- `0x180003438`
- `0x180009f30`
- `0x180009f60`
- `0x18001c6c8`
- `0x1800239e0`
- `0x180025ed4`
- `0x18002f28c`
- `0x18006c39c`
- `0x18006d0c8`
- `0x18006d730`
- `0x18006e0f8`
- `0x18006fa60`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006c412`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006c412`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006cd4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006cd4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006c492`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006c511`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006c492`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006c511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c52a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006c716`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006c716`

## string_xrefs

- `0x18006c3dd`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall FveCanProvisionDE(struct _GUID *a1, unsigned __int64 *a2)
{
  bool v2; // r13
  unsigned int v3; // esi
  bool v4; // r14
  bool v5; // r12
  HMODULE Library; // rax
  HMODULE v7; // r15
  signed int LastError; // eax
  unsigned int v9; // ebx
  FARPROC ProcAddress; // r12
  signed int v11; // eax
  int (*v12)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *); // r13
  signed int v13; // eax
  int v14; // eax
  int v15; // r14d
  unsigned __int64 v16; // rax
  int v17; // eax
  int v18; // r14d
  unsigned __int64 v19; // rax
  LSTATUS ValueW; // eax
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // r14d
  int ShouldDeferForMdmPolicySync; // eax
  unsigned __int64 v25; // r8
  int IsAutoPilotScenario; // eax
  bool v27; // r9
  bool v28; // cl
  unsigned __int64 v29; // r8
  PVOID *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  bool v38; // [rsp+90h] [rbp-49h] BYREF
  bool v39; // [rsp+91h] [rbp-48h] BYREF
  bool v40; // [rsp+92h] [rbp-47h] BYREF
  bool v41; // [rsp+93h] [rbp-46h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v43[4]; // [rsp+A0h] [rbp-39h] BYREF
  DWORD pcbData; // [rsp+A4h] [rbp-35h] BYREF
  int pvData; // [rsp+A8h] [rbp-31h] BYREF
  int v46; // [rsp+ACh] [rbp-2Dh] BYREF
  int v47; // [rsp+B0h] [rbp-29h] BYREF
  int v48; // [rsp+B4h] [rbp-25h] BYREF
  int v49; // [rsp+B8h] [rbp-21h] BYREF
  HMODULE v50; // [rsp+C0h] [rbp-19h] BYREF
  int v51; // [rsp+C8h] [rbp-11h] BYREF
  int v52; // [rsp+CCh] [rbp-Dh] BYREF
  unsigned int v53; // [rsp+D0h] [rbp-9h] BYREF
  PSRWLOCK v54[11]; // [rsp+D8h] [rbp-1h] BYREF
  GUID *rguid; // [rsp+140h] [rbp+67h] BYREF
  unsigned __int64 *v56; // [rsp+148h] [rbp+6Fh] BYREF
  bool v57; // [rsp+150h] [rbp+77h] BYREF
  bool v58; // [rsp+158h] [rbp+7Fh] BYREF

  v56 = a2;
  rguid = a1;
  pcbData = 4;
  v2 = 1;
  v52 = 0;
  v38 = 0;
  LOBYTE(v56) = 0;
  v57 = 0;
  v3 = 0;
  v41 = 0;
  v4 = 0;
  v40 = 0;
  v5 = 0;
  v58 = 1;
  pvData = 0;
  v47 = 0;
  v46 = 0;
  v51 = 0;
  v48 = 0;
  v49 = 0;
  v42 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v50 = Library;
  v7 = Library;
  if ( !Library )
  {
    v42 |= 1u;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
    goto LABEL_101;
  }
  ProcAddress = GetProcAddress(Library, "NtQueryWnfStateData");
  if ( !ProcAddress )
  {
    v42 |= 2u;
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v5 = 0;
    }
    else
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
      v5 = 0;
    }
    goto LABEL_101;
  }
  v12 = (int (*)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *))GetProcAddress(
                                                                                                   v7,
                                                                                                   "NtQueryLicenseValue");
  if ( v12 )
  {
    pvData = 0;
    pcbData = 4;
    v9 = 0;
    v14 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
            &WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED,
            0,
            0,
            &v52,
            &pvData,
            &pcbData);
    v15 = v14;
    if ( v14 >= 0 )
    {
      if ( pcbData > 4 )
      {
        v16 = v42 | 0x10;
      }
      else
      {
        v38 = pvData == 1;
        v16 = v42 | (32 * ((pvData != 1) + 1LL));
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)v14);
      v16 = v42 | 8;
      v47 = v15;
    }
    v42 = v16;
    pvData = 0;
    pcbData = 4;
    v17 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
            &WNF_SHEL_OOBE_USER_LOGON_COMPLETE,
            0,
            0,
            &v52,
            &pvData,
            &pcbData);
    v18 = v17;
    if ( v17 >= 0 )
    {
      if ( pcbData > 4 )
      {
        v19 = v42 | 0x100;
      }
      else
      {
        LOBYTE(v56) = pvData == 1;
        v19 = v42 | (((pvData != 1) + 1LL) << 9);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)v17);
      v19 = v42 | 0x80;
      v46 = v18;
    }
    v42 = v19;
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
               L"SetupDisplayedEula",
               0x20000010u,
               0,
               &pvData,
               &pcbData);
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW > 0 )
        v9 = (unsigned __int16)ValueW | 0x80070000;
      else
        v9 = ValueW;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
      v21 = v42 | 0x800;
    }
    else
    {
      v21 = v42;
    }
    if ( pcbData > 4 )
    {
      v4 = 0;
      v42 = v21 | 0x1000;
    }
    else
    {
      v4 = pvData == 1;
      v39 = pvData == 1;
      v42 = v21 | (((pvData != 1) + 1LL) << 13);
      if ( pvData == 1 )
      {
        pvData = 0;
        pcbData = 4;
        v22 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, DWORD *))ProcAddress)(
                &WNF_DEP_OOBE_COMPLETE,
                0,
                0,
                &v52,
                &pvData,
                &pcbData);
        v23 = v22;
        if ( v22 >= 0 )
        {
          v4 = v39;
          if ( pcbData > 4 )
          {
            v42 |= 0x10000u;
          }
          else
          {
            v57 = pvData == 1;
            v42 |= ((unsigned __int64)(pvData != 1) << 17) + 0x20000;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              42,
              &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
              (unsigned int)v22);
          v42 |= 0x8000u;
          v51 = v23;
          v4 = v39;
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
    {
      ShouldDeferForMdmPolicySync = FveShouldDeferForMdmPolicySync(
                                      (int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *))ProcAddress,
                                      v12,
                                      &v58,
                                      &v42);
      v49 = ShouldDeferForMdmPolicySync;
      if ( ShouldDeferForMdmPolicySync >= 0 )
      {
        v2 = v58;
        v5 = (char)v56;
        v25 = ((-(__int64)v58 & 0xFFFFFFFFFFF00000uLL) + 0x200000) | v42;
        if ( (_BYTE)v56 || !v58 )
          v3 = 1;
        goto LABEL_71;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          (unsigned int)ShouldDeferForMdmPolicySync);
      v5 = (char)v56;
      v25 = v42 | 0x80000;
LABEL_70:
      v2 = v58;
LABEL_71:
      v27 = v38;
      v28 = v57;
      goto LABEL_72;
    }
    IsAutoPilotScenario = FveIsAutoPilotScenario(
                            (int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *))ProcAddress,
                            (__int64 (__fastcall *)(struct _UNICODE_STRING *, int *, int *, __int64, int *))v12,
                            &v41,
                            &v40,
                            &v42);
    v48 = IsAutoPilotScenario;
    if ( IsAutoPilotScenario == -2147024875 )
    {
      v25 = v42 | 0x400000;
      v42 |= 0x400000u;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
    }
    else if ( IsAutoPilotScenario >= 0 )
    {
      if ( !IsAutoPilotScenario )
      {
        v5 = (char)v56;
        v25 = ((-(__int64)v41 & 0xFFFFFFFFFF000000uLL) + 0x2000000) | v42;
        if ( !v41 )
        {
          v27 = v38;
          v28 = v57;
          if ( v38 || (_BYTE)v56 || v57 )
            v3 = 1;
          v2 = v58;
LABEL_72:
          v29 = (((v3 ^ 1LL) << 26) + 0x4000000) | v25;
          v42 = v29;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_llll(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v29, v27, v4, v5, v28);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
          {
            v30 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v2);
LABEL_96:
                v30 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_97;
              }
              goto LABEL_97;
            }
          }
          else
          {
            v30 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_DD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  48,
                  &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
                  v41,
                  v40);
                goto LABEL_96;
              }
LABEL_97:
              if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
                WPP_SF_d(v30[2], 49, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v3);
            }
          }
          v7 = v50;
          goto LABEL_101;
        }
        if ( v40 || (_BYTE)v56 )
          v3 = 1;
        goto LABEL_70;
      }
    }
    else
    {
      v25 = v42 | 0x800000;
      v42 |= 0x800000u;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)IsAutoPilotScenario);
    }
    v25 = v42;
LABEL_69:
    v5 = (char)v56;
    LOBYTE(v3) = (_BYTE)v56 != 0;
    goto LABEL_70;
  }
  v42 |= 4u;
  v13 = GetLastError();
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v2 = v58;
    v5 = 0;
  }
  else
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v9);
    v2 = v58;
    v5 = 0;
  }
LABEL_101:
  if ( rguid )
    FveRecordDeCheck(rguid, v42, v3);
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v54,
    &g_hBitLockerDelayProvider,
    &g_bitLockerDelayProviderInitLock,
    &g_bitLockerDelayProviderRefCount);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotBitlockerOobeDeferral>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_18009A4D8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A4D8, 0x400000000000LL) )
    {
      LOBYTE(v56) = v40;
      v58 = v41;
      v53 = v9;
      LOBYTE(rguid) = v2;
      LODWORD(v50) = v3;
      v39 = v5;
      v43[0] = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        (int)byte_18008E6A3,
        v32,
        v33,
        (__int64)&v38,
        (__int64)v43,
        (__int64)&v39,
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&v56,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&rguid,
        (__int64)&v49,
        (__int64)&v53);
    }
  }
  else if ( (unsigned int)dword_18009A4D8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A4D8, 0x400000000000LL) )
  {
    v49 = v51;
    LOBYTE(rguid) = v40;
    LOBYTE(v56) = v41;
    v39 = v38;
    LODWORD(v50) = v9;
    v53 = v3;
    v58 = v5;
    v43[0] = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v34,
      (int)byte_18008E4D3,
      v35,
      v36,
      (__int64)&v39,
      (__int64)v43,
      (__int64)&v58,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&rguid,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v49,
      (__int64)&v53,
      (__int64)&v50);
  }
  if ( v7 )
    FreeLibrary(v7);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v54);
  return v3;
}

```

## disassembly

```asm
0x18006c39c  mov     [rsp-8+arg_8], rdx
0x18006c3a1  mov     [rsp-8+rguid], rcx
0x18006c3a6  push    rbp
0x18006c3a7  push    rbx
0x18006c3a8  push    rsi
0x18006c3a9  push    rdi
0x18006c3aa  push    r12
0x18006c3ac  push    r13
0x18006c3ae  push    r14
0x18006c3b0  push    r15
0x18006c3b2  lea     rbp, [rsp-1Fh]
0x18006c3b7  sub     rsp, 0F8h
0x18006c3be  xor     edi, edi
0x18006c3c0  mov     [rbp+57h+var_8C], 4
0x18006c3c7  mov     r13b, 1
0x18006c3ca  mov     [rbp+57h+var_64], edi
0x18006c3cd  xor     edx, edx; hFile
0x18006c3cf  mov     [rbp+57h+var_A0], dil
0x18006c3d3  mov     r8d, 800h; dwFlags
0x18006c3d9  mov     byte ptr [rbp+57h+arg_8], dil
0x18006c3dd  lea     rcx, ModuleName; "ntdll.dll"
0x18006c3e4  mov     [rbp+57h+arg_10], dil
0x18006c3e8  mov     esi, edi
0x18006c3ea  mov     [rbp+57h+var_9D], dil
0x18006c3ee  mov     r14b, dil
0x18006c3f1  mov     [rbp+57h+var_9E], dil
0x18006c3f5  mov     r12b, dil
0x18006c3f8  mov     [rbp+57h+arg_18], r13b
0x18006c3fc  mov     [rbp+57h+var_88], edi
0x18006c3ff  mov     [rbp+57h+var_80], edi
0x18006c402  mov     [rbp+57h+var_84], edi
0x18006c405  mov     [rbp+57h+var_68], edi
0x18006c408  mov     [rbp+57h+var_7C], edi
0x18006c40b  mov     [rbp+57h+var_78], edi
0x18006c40e  mov     [rbp+57h+var_98], rdi
0x18006c412  call    cs:__imp_LoadLibraryExW
0x18006c419  nop     dword ptr [rax+rax+00h]
0x18006c41e  mov     [rbp+57h+var_70], rax
0x18006c422  mov     r15, rax
0x18006c425  test    rax, rax
0x18006c428  jnz     short loc_18006C488
0x18006c42a  or      [rbp+57h+var_98], 1
0x18006c42f  call    cs:__imp_GetLastError
0x18006c436  nop     dword ptr [rax+rax+00h]
0x18006c43b  mov     ebx, eax
0x18006c43d  test    eax, eax
0x18006c43f  jle     short loc_18006C44A
0x18006c441  movzx   ebx, ax
0x18006c444  or      ebx, 80070000h
0x18006c44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c451  lea     rdi, WPP_GLOBAL_Control
0x18006c458  cmp     rcx, rdi
0x18006c45b  jz      loc_18006CB00
0x18006c461  test    byte ptr [rcx+1Ch], 2
0x18006c465  jz      loc_18006CB00
0x18006c46b  mov     rcx, [rcx+10h]
0x18006c46f  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006c476  mov     edx, 24h ; '$'
0x18006c47b  mov     r9d, ebx
0x18006c47e  call    WPP_SF_d
0x18006c483  jmp     loc_18006CB00
0x18006c488  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18006c48f  mov     rcx, r15; hModule
0x18006c492  call    cs:__imp_GetProcAddress
0x18006c499  nop     dword ptr [rax+rax+00h]
0x18006c49e  mov     r12, rax
0x18006c4a1  test    rax, rax
0x18006c4a4  jnz     short loc_18006C507
0x18006c4a6  or      [rbp+57h+var_98], 2
0x18006c4ab  call    cs:__imp_GetLastError
0x18006c4b2  nop     dword ptr [rax+rax+00h]
0x18006c4b7  mov     ebx, eax
0x18006c4b9  test    eax, eax
0x18006c4bb  jle     short loc_18006C4C6
0x18006c4bd  movzx   ebx, ax
0x18006c4c0  or      ebx, 80070000h
0x18006c4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4cd  lea     rdi, WPP_GLOBAL_Control
0x18006c4d4  cmp     rcx, rdi
0x18006c4d7  jz      loc_18006CC60
0x18006c4dd  test    byte ptr [rcx+1Ch], 2
0x18006c4e1  jz      loc_18006CC60
0x18006c4e7  mov     rcx, [rcx+10h]
0x18006c4eb  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006c4f2  mov     edx, 25h ; '%'
0x18006c4f7  mov     r9d, ebx
0x18006c4fa  call    WPP_SF_d
0x18006c4ff  mov     r12b, sil
0x18006c502  jmp     loc_18006CB00
0x18006c507  lea     rdx, aNtquerylicense; "NtQueryLicenseValue"
0x18006c50e  mov     rcx, r15; hModule
0x18006c511  call    cs:__imp_GetProcAddress
0x18006c518  nop     dword ptr [rax+rax+00h]
0x18006c51d  mov     r13, rax
0x18006c520  test    rax, rax
0x18006c523  jnz     short loc_18006C58A
0x18006c525  or      [rbp+57h+var_98], 4
0x18006c52a  call    cs:__imp_GetLastError
0x18006c531  nop     dword ptr [rax+rax+00h]
0x18006c536  mov     ebx, eax
0x18006c538  test    eax, eax
0x18006c53a  jle     short loc_18006C545
0x18006c53c  movzx   ebx, ax
0x18006c53f  or      ebx, 80070000h
0x18006c545  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c54c  lea     rdi, WPP_GLOBAL_Control
0x18006c553  cmp     rcx, rdi
0x18006c556  jz      loc_18006CC54
0x18006c55c  test    byte ptr [rcx+1Ch], 2
0x18006c560  jz      loc_18006CC54
0x18006c566  mov     rcx, [rcx+10h]
0x18006c56a  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006c571  mov     edx, 26h ; '&'
0x18006c576  mov     r9d, ebx
0x18006c579  call    WPP_SF_d
0x18006c57e  mov     r13b, [rbp+57h+arg_18]
0x18006c582  mov     r12b, sil
0x18006c585  jmp     loc_18006CB00
0x18006c58a  lea     rax, [rbp+57h+var_8C]
0x18006c58e  mov     [rbp+57h+var_88], edi
0x18006c591  mov     [rsp+130h+pvData], rax
0x18006c596  lea     r9, [rbp+57h+var_64]
0x18006c59a  lea     rax, [rbp+57h+var_88]
0x18006c59e  mov     [rbp+57h+var_8C], 4
0x18006c5a5  mov     [rsp+130h+pdwType], rax
0x18006c5aa  lea     rcx, WNF_OLIC_OS_LICENSE_TERMS_ACCEPTED
0x18006c5b1  mov     rax, r12
0x18006c5b4  xor     r8d, r8d
0x18006c5b7  xor     edx, edx
0x18006c5b9  mov     ebx, edi
0x18006c5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5c0  lea     rdi, WPP_GLOBAL_Control
0x18006c5c7  mov     r14d, eax
0x18006c5ca  lea     r15, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006c5d1  test    eax, eax
0x18006c5d3  jns     short loc_18006C609
0x18006c5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5dc  cmp     rcx, rdi
0x18006c5df  jz      short loc_18006C5FB
0x18006c5e1  test    byte ptr [rcx+1Ch], 2
0x18006c5e5  jz      short loc_18006C5FB
0x18006c5e7  mov     rcx, [rcx+10h]
0x18006c5eb  mov     edx, 27h ; '''
0x18006c5f0  mov     r9d, eax
0x18006c5f3  mov     r8, r15
0x18006c5f6  call    WPP_SF_d
0x18006c5fb  mov     rax, [rbp+57h+var_98]
0x18006c5ff  or      rax, 8
0x18006c603  mov     [rbp+57h+var_80], r14d
0x18006c607  jmp     short loc_18006C635
0x18006c609  cmp     [rbp+57h+var_8C], 4
0x18006c60d  ja      short loc_18006C62D
0x18006c60f  cmp     [rbp+57h+var_88], 1
0x18006c613  setz    al
0x18006c616  mov     [rbp+57h+var_A0], al
0x18006c619  movzx   eax, al
0x18006c61c  xor     rax, 1
0x18006c620  inc     rax
0x18006c623  shl     rax, 5
0x18006c627  or      rax, [rbp+57h+var_98]
0x18006c62b  jmp     short loc_18006C635
0x18006c62d  mov     rax, [rbp+57h+var_98]
0x18006c631  or      rax, 10h
0x18006c635  mov     [rbp+57h+var_98], rax
0x18006c639  lea     r9, [rbp+57h+var_64]
0x18006c63d  lea     rax, [rbp+57h+var_8C]
0x18006c641  mov     [rbp+57h+var_88], ebx
0x18006c644  mov     [rsp+130h+pvData], rax
0x18006c649  lea     rcx, WNF_SHEL_OOBE_USER_LOGON_COMPLETE
0x18006c650  lea     rax, [rbp+57h+var_88]
0x18006c654  mov     [rbp+57h+var_8C], 4
0x18006c65b  mov     [rsp+130h+pdwType], rax
0x18006c660  xor     r8d, r8d
0x18006c663  mov     rax, r12
0x18006c666  xor     edx, edx
0x18006c668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c66d  mov     r14d, eax
0x18006c670  test    eax, eax
0x18006c672  jns     short loc_18006C6A9
0x18006c674  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c67b  cmp     rcx, rdi
0x18006c67e  jz      short loc_18006C69A
0x18006c680  test    byte ptr [rcx+1Ch], 2
0x18006c684  jz      short loc_18006C69A
0x18006c686  mov     rcx, [rcx+10h]
0x18006c68a  mov     edx, 28h ; '('
0x18006c68f  mov     r9d, eax
0x18006c692  mov     r8, r15
0x18006c695  call    WPP_SF_d
0x18006c69a  mov     rax, [rbp+57h+var_98]
0x18006c69e  bts     rax, 7
0x18006c6a3  mov     [rbp+57h+var_84], r14d
0x18006c6a7  jmp     short loc_18006C6D6
0x18006c6a9  cmp     [rbp+57h+var_8C], 4
0x18006c6ad  ja      short loc_18006C6CD
0x18006c6af  cmp     [rbp+57h+var_88], 1
0x18006c6b3  setz    al
0x18006c6b6  mov     byte ptr [rbp+57h+arg_8], al
0x18006c6b9  movzx   eax, al
0x18006c6bc  xor     rax, 1
0x18006c6c0  inc     rax
0x18006c6c3  shl     rax, 9
0x18006c6c7  or      rax, [rbp+57h+var_98]
0x18006c6cb  jmp     short loc_18006C6D6
0x18006c6cd  mov     rax, [rbp+57h+var_98]
0x18006c6d1  bts     rax, 8
0x18006c6d6  mov     [rbp+57h+var_98], rax
0x18006c6da  lea     r8, aSetupdisplayed; "SetupDisplayedEula"
0x18006c6e1  lea     rax, [rbp+57h+var_8C]
0x18006c6e5  mov     [rbp+57h+var_88], ebx
0x18006c6e8  mov     [rsp+130h+pcbData], rax; pcbData
0x18006c6ed  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006c6f4  lea     rax, [rbp+57h+var_88]
0x18006c6f8  mov     [rbp+57h+var_8C], 4
0x18006c6ff  mov     [rsp+130h+pvData], rax; pvData
0x18006c704  mov     r9d, 20000010h; dwFlags
0x18006c70a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18006c711  mov     [rsp+130h+pdwType], rbx; pdwType
0x18006c716  call    cs:__imp_RegGetValueW
0x18006c71d  nop     dword ptr [rax+rax+00h]
0x18006c722  test    eax, 0FFFFFFFDh
0x18006c727  jz      short loc_18006C76B
0x18006c729  test    eax, eax
0x18006c72b  jg      short loc_18006C731
0x18006c72d  mov     ebx, eax
0x18006c72f  jmp     short loc_18006C73A
0x18006c731  movzx   ebx, ax
0x18006c734  or      ebx, 80070000h
0x18006c73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c741  cmp     rcx, rdi
0x18006c744  jz      short loc_18006C760
0x18006c746  test    byte ptr [rcx+1Ch], 2
0x18006c74a  jz      short loc_18006C760
0x18006c74c  mov     rcx, [rcx+10h]
0x18006c750  mov     edx, 29h ; ')'
0x18006c755  mov     r9d, ebx
0x18006c758  mov     r8, r15
0x18006c75b  call    WPP_SF_d
0x18006c760  mov     rcx, [rbp+57h+var_98]
0x18006c764  bts     rcx, 0Bh
0x18006c769  jmp     short loc_18006C76F
0x18006c76b  mov     rcx, [rbp+57h+var_98]
0x18006c76f  cmp     [rbp+57h+var_8C], 4
0x18006c773  ja      loc_18006C848
0x18006c779  cmp     [rbp+57h+var_88], 1
0x18006c77d  setz    r14b
0x18006c781  movzx   eax, r14b
0x18006c785  xor     rax, 1
0x18006c789  mov     [rbp+57h+var_9F], r14b
0x18006c78d  inc     rax
0x18006c790  shl     rax, 0Dh
0x18006c794  or      rax, rcx
0x18006c797  mov     [rbp+57h+var_98], rax
0x18006c79b  test    r14b, r14b
0x18006c79e  jz      loc_18006C854
0x18006c7a4  lea     rax, [rbp+57h+var_8C]
0x18006c7a8  mov     [rbp+57h+var_88], esi
0x18006c7ab  mov     [rsp+130h+pvData], rax
0x18006c7b0  lea     r9, [rbp+57h+var_64]
0x18006c7b4  lea     rax, [rbp+57h+var_88]
0x18006c7b8  mov     [rbp+57h+var_8C], 4
0x18006c7bf  mov     [rsp+130h+pdwType], rax
0x18006c7c4  lea     rcx, WNF_DEP_OOBE_COMPLETE
0x18006c7cb  mov     rax, r12
0x18006c7ce  xor     r8d, r8d
0x18006c7d1  xor     edx, edx
0x18006c7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7d8  mov     r14d, eax
0x18006c7db  test    eax, eax
0x18006c7dd  jns     short loc_18006C815
0x18006c7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7e6  cmp     rcx, rdi
0x18006c7e9  jz      short loc_18006C805
0x18006c7eb  test    byte ptr [rcx+1Ch], 2
0x18006c7ef  jz      short loc_18006C805
0x18006c7f1  mov     rcx, [rcx+10h]
0x18006c7f5  mov     edx, 2Ah ; '*'
0x18006c7fa  mov     r9d, eax
0x18006c7fd  mov     r8, r15
0x18006c800  call    WPP_SF_d
0x18006c805  bts     [rbp+57h+var_98], 0Fh
0x18006c80b  mov     [rbp+57h+var_68], r14d
0x18006c80f  mov     r14b, [rbp+57h+var_9F]
0x18006c813  jmp     short loc_18006C854
0x18006c815  cmp     [rbp+57h+var_8C], 4
0x18006c819  mov     r14b, [rbp+57h+var_9F]
0x18006c81d  ja      short loc_18006C840
0x18006c81f  cmp     [rbp+57h+var_88], 1
0x18006c823  setz    al
0x18006c826  mov     [rbp+57h+arg_10], al
0x18006c829  movzx   eax, al
0x18006c82c  xor     rax, 1
0x18006c830  shl     rax, 11h
0x18006c834  add     rax, 20000h
0x18006c83a  or      [rbp+57h+var_98], rax
0x18006c83e  jmp     short loc_18006C854
0x18006c840  bts     [rbp+57h+var_98], 10h
0x18006c846  jmp     short loc_18006C854
0x18006c848  bts     rcx, 0Ch
0x18006c84d  mov     r14b, sil
  ... truncated ...
```

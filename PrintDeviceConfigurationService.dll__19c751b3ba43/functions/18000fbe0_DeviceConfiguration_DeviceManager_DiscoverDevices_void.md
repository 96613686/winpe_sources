# DeviceConfiguration::DeviceManager::_DiscoverDevices(void)

- ea: `0x18000fbe0`
- end: `0x180010b09`
- name: `?_DiscoverDevices@DeviceManager@DeviceConfiguration@@AEAA?AV?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@XZ`
- size: `3881`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ed18`

## callees

- `0x1800020c0`
- `0x1800033f0`
- `0x180003458`
- `0x180003609`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000af54`
- `0x18000b838`
- `0x18000e294`
- `0x18000e5ac`
- `0x18000e628`
- `0x18000eb80`
- `0x18000f6c4`
- `0x18000f9b4`
- `0x18000fbe0`
- `0x180010c38`
- `0x180011174`
- `0x1800115a0`
- `0x180011610`
- `0x1800146ec`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18000fce6`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18000fce6`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x1800105ea`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x1800105ea`

## string_xrefs

- `0x180010331`: `_PopulateInfoFromDeviceRegistry for device %ws failed with hr: 0x%x`
- `0x18000fd12`: `DeviceConfiguration::DeviceManager::_DiscoverDevices`
- `0x180010286`: `DeviceConfiguration::DeviceManager::_DiscoverDevices`
- `0x1800105d1`: `DeviceConfiguration::DeviceManager::_DiscoverDevices`
- `0x180010391`: `Device %ws does not have CONFIGFLAG_NEEDS_CLASS_CONFIG set. Skipping device...`
- `0x1800103bb`: `Device %ws is already in the process of being installed. Skipping device...`
- `0x1800103dd`: `Adding device %ws with device type %ws to the list of devices to be configured`

## pseudocode

```c
_QWORD *__fastcall DeviceConfiguration::DeviceManager::_DiscoverDevices(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // rbx
  int Objects; // eax
  __int64 v6; // r8
  unsigned int v7; // r15d
  unsigned int v8; // r13d
  __int64 v9; // rdx
  __m128i si128; // xmm7
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  GUID v14; // xmm6
  unsigned int DeviceTypeForPort; // r12d
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r10
  __int64 v22; // r11
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rax
  __int128 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  bool v29; // zf
  __int64 v30; // rax
  __int64 v31; // rbx
  int v32; // eax
  __int64 v33; // rcx
  __int128 *v34; // r8
  int v35; // edi
  unsigned __int16 *v36; // rdx
  __int128 *v37; // r8
  int v38; // ebx
  __int64 v39; // rax
  __int128 *v40; // r8
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // r9
  unsigned __int16 *v44; // rdx
  __int128 *v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r9
  const wchar_t *v49; // r8
  __int16 v51; // [rsp+78h] [rbp-90h]
  unsigned int v52; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v53; // [rsp+80h] [rbp-88h]
  unsigned int v54; // [rsp+84h] [rbp-84h]
  int v55; // [rsp+88h] [rbp-80h]
  int v56; // [rsp+8Ch] [rbp-7Ch]
  int v57; // [rsp+90h] [rbp-78h]
  __int64 v58; // [rsp+98h] [rbp-70h] BYREF
  int v59; // [rsp+A0h] [rbp-68h]
  unsigned int v60; // [rsp+A4h] [rbp-64h]
  GUID Buf2; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-50h] BYREF
  std::_Ref_count_base *v63; // [rsp+C0h] [rbp-48h]
  _QWORD *v64; // [rsp+C8h] [rbp-40h]
  _QWORD *v65; // [rsp+D0h] [rbp-38h]
  __int64 *v66; // [rsp+D8h] [rbp-30h]
  unsigned int *v67; // [rsp+E0h] [rbp-28h]
  char v68; // [rsp+E8h] [rbp-20h]
  __int128 v69; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v70; // [rsp+100h] [rbp-8h]
  unsigned __int64 v71; // [rsp+108h] [rbp+0h]
  __int128 v72; // [rsp+110h] [rbp+8h] BYREF
  __int64 v73; // [rsp+120h] [rbp+18h]
  __int64 v74; // [rsp+128h] [rbp+20h]
  __int128 v75; // [rsp+130h] [rbp+28h] BYREF
  __int64 v76; // [rsp+140h] [rbp+38h]
  __int64 v77; // [rsp+148h] [rbp+40h]
  _BYTE v78[32]; // [rsp+150h] [rbp+48h] BYREF
  _OWORD v79[2]; // [rsp+170h] [rbp+68h] BYREF
  _OWORD v80[2]; // [rsp+190h] [rbp+88h] BYREF
  _OWORD v81[2]; // [rsp+1B0h] [rbp+A8h] BYREF
  _OWORD v82[2]; // [rsp+1D0h] [rbp+C8h] BYREF

  v3 = a2;
  v64 = a2;
  v65 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v59 = 1;
  v52 = 0;
  v58 = 0;
  v66 = &v58;
  v67 = &v52;
  v68 = 1;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180024B88 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180024B88);
    if ( dword_180024B88 == -1 )
    {
      *(DEVPROPKEY *)byte_180024840 = DEVPKEY_Device_InstanceId;
      dword_180024854 = 0;
      qword_180024858 = 0;
      *(DEVPROPKEY *)byte_180024860 = DEVPKEY_Device_ConfigFlags;
      dword_180024874 = 0;
      qword_180024878 = 0;
      *(DEVPROPKEY *)byte_180024880 = DEVPKEY_Device_ClassGuid;
      dword_180024894 = 0;
      qword_180024898 = 0;
      *(DEVPROPKEY *)byte_1800248A0 = DEVPKEY_Device_ContainerId;
      dword_1800248B4 = 0;
      qword_1800248B8 = 0;
      xmmword_1800248C0 = xmmword_18001CB78;
      dword_1800248D0 = 5;
      dword_1800248D4 = 0;
      qword_1800248D8 = 0;
      xmmword_1800248E0 = xmmword_18001CB60;
      dword_1800248F0 = 2;
      dword_1800248F4 = 0;
      qword_1800248F8 = 0;
      xmmword_180024900 = xmmword_18001CB48;
      dword_180024910 = 4;
      dword_180024914 = 0;
      qword_180024918 = 0;
      xmmword_180024920 = xmmword_18001CB30;
      dword_180024930 = 3;
      dword_180024934 = 0;
      qword_180024938 = 0;
      xmmword_180024940 = xmmword_18001CB18;
      dword_180024950 = 6;
      dword_180024954 = 0;
      qword_180024958 = 0;
      xmmword_180024960 = xmmword_18001CB00;
      dword_180024970 = 7;
      dword_180024974 = 0;
      qword_180024978 = 0;
      xmmword_180024980 = xmmword_18001CAE8;
      dword_180024990 = 3;
      dword_180024994 = 0;
      qword_180024998 = 0;
      xmmword_1800249A0 = xmmword_18001CAD0;
      dword_1800249B0 = 4;
      dword_1800249B4 = 0;
      qword_1800249B8 = 0;
      xmmword_1800249C0 = xmmword_18001CAB8;
      dword_1800249D0 = 8;
      dword_1800249D4 = 0;
      qword_1800249D8 = 0;
      xmmword_1800249E0 = DEVPKEY_PSA_Aumid;
      dword_1800249F0 = 1;
      dword_1800249F4 = 0;
      qword_1800249F8 = 0;
      Init_thread_footer(&dword_180024B88);
    }
  }
  if ( dword_180024B8C > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180024B8C);
    if ( dword_180024B8C == -1 )
    {
      *(DEVPROPKEY *)byte_1800246A0 = DEVPKEY_Device_InstanceId;
      dword_1800246B4 = 0;
      qword_1800246B8 = 0;
      *(DEVPROPKEY *)byte_1800246C0 = DEVPKEY_Device_ConfigFlags;
      dword_1800246D4 = 0;
      qword_1800246D8 = 0;
      *(DEVPROPKEY *)byte_1800246E0 = DEVPKEY_Device_ClassGuid;
      dword_1800246F4 = 0;
      qword_1800246F8 = 0;
      *(DEVPROPKEY *)byte_180024700 = DEVPKEY_Device_ContainerId;
      dword_180024714 = 0;
      qword_180024718 = 0;
      xmmword_180024720 = xmmword_18001CB78;
      dword_180024730 = 5;
      dword_180024734 = 0;
      qword_180024738 = 0;
      xmmword_180024740 = xmmword_18001CB60;
      dword_180024750 = 2;
      dword_180024754 = 0;
      qword_180024758 = 0;
      xmmword_180024760 = xmmword_18001CB48;
      dword_180024770 = 4;
      dword_180024774 = 0;
      qword_180024778 = 0;
      xmmword_180024780 = xmmword_18001CB30;
      dword_180024790 = 3;
      dword_180024794 = 0;
      qword_180024798 = 0;
      xmmword_1800247A0 = xmmword_18001CB18;
      dword_1800247B0 = 6;
      dword_1800247B4 = 0;
      qword_1800247B8 = 0;
      xmmword_1800247C0 = xmmword_18001CB00;
      dword_1800247D0 = 7;
      dword_1800247D4 = 0;
      qword_1800247D8 = 0;
      xmmword_1800247E0 = xmmword_18001CAE8;
      dword_1800247F0 = 3;
      dword_1800247F4 = 0;
      qword_1800247F8 = 0;
      xmmword_180024800 = xmmword_18001CAD0;
      dword_180024810 = 4;
      dword_180024814 = 0;
      qword_180024818 = 0;
      xmmword_180024820 = xmmword_18001CAB8;
      dword_180024830 = 8;
      dword_180024834 = 0;
      qword_180024838 = 0;
      Init_thread_footer(&dword_180024B8C);
    }
  }
  if ( dword_180024B90 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180024B90);
    if ( dword_180024B90 == -1 )
    {
      *(DEVPROPKEY *)byte_1800241C8 = DEVPKEY_Device_ClassGuid;
      dword_1800241DC = 0;
      qword_1800241E0 = 0;
      dword_1800241E8 = 13;
      dword_1800241EC = 16;
      qword_1800241F0 = (__int64)&GUID_DEVCLASS_PRINTER;
      Init_thread_footer(&dword_180024B90);
    }
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
    a2,
    a3);
  Objects = DevGetObjects(3, 0, 14, byte_180024840, 1, &qword_1800241C0, &v52, &v58);
  v7 = Objects;
  v53 = Objects;
  if ( Objects < 0 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "DeviceConfiguration::DeviceManager::_DiscoverDevices",
      L"DevGetObjects failed with hr: 0x%x",
      (unsigned int)Objects);
  }
  else
  {
    v8 = 0;
    v57 = 0;
    if ( v52 )
    {
      v9 = 7;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v11 = 32LL * v8;
        v60 = *(_DWORD *)(v11 + v58 + 16);
        v12 = v60;
        v13 = *(_QWORD *)(v11 + v58 + 24);
        v14 = GUID_NULL;
        Buf2 = GUID_NULL;
        v69 = 0;
        v70 = 0;
        v71 = 7;
        LOWORD(v69) = 0;
        v75 = 0;
        v76 = 0;
        v77 = 7;
        LOWORD(v75) = 0;
        v72 = 0;
        v73 = 0;
        v74 = 7;
        LOWORD(v72) = 0;
        v55 = 0;
        DeviceTypeForPort = 0;
        v82[0] = 0;
        v82[1] = si128;
        LOWORD(v82[0]) = 0;
        v81[0] = 0;
        v81[1] = si128;
        LOWORD(v81[0]) = 0;
        v80[0] = 0;
        v80[1] = si128;
        LOWORD(v80[0]) = 0;
        v79[0] = 0;
        v79[1] = si128;
        LOWORD(v79[0]) = 0;
        v51 = 0;
        v56 = 0;
        LOBYTE(v6) = 3;
        LOBYTE(v9) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
          v9,
          v6);
        v54 = 0;
        if ( v12 )
        {
          v17 = 0;
          *(_QWORD *)&Buf2.Data1 = 0;
          v16 = *(_QWORD *)DEVPKEY_Device_InstanceId.fmtid.Data4;
          v18 = *(_QWORD *)&DEVPKEY_Device_InstanceId.fmtid.Data1;
          v19 = *(_QWORD *)DEVPKEY_Device_ConfigFlags.fmtid.Data4;
          v20 = *(_QWORD *)&DEVPKEY_Device_ConfigFlags.fmtid.Data1;
          v21 = *(_QWORD *)DEVPKEY_Device_ContainerId.fmtid.Data4;
          v22 = *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1;
          while ( 1 )
          {
            v23 = 6 * v17;
            v24 = *(_DWORD *)(v13 + 48 * v17 + 16);
            if ( v24 == 256 )
              break;
            switch ( v24 )
            {
              case 2:
                if ( v22 != *(_QWORD *)(v13 + 8 * v23)
                  || v21 != *(_QWORD *)(v13 + 8 * v23 + 8)
                  || *(_DWORD *)(v13 + 8 * v23 + 20)
                  || *(_DWORD *)(v13 + 8 * v23 + 32) != 13 )
                {
                  if ( *(_QWORD *)(v13 + 8 * v23) != 0x485FE5F6F01FAC5DLL
                    || *(_QWORD *)(v13 + 8 * v23 + 8) != 0x8C9925644427C6A8uLL
                    || *(_DWORD *)(v13 + 8 * v23 + 20)
                    || *(_DWORD *)(v13 + 8 * v23 + 32) != 18 )
                  {
                    break;
                  }
                  v27 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                  std::wstring::operator=(&v75, v27);
                  std::wstring::_Tidy_deallocate(v78);
                  std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                  DeviceTypeForPort = DeviceConfiguration::DeviceManager::_GetDeviceTypeForPort(v28, v78);
                  goto LABEL_84;
                }
                v14 = *(GUID *)*(_QWORD *)(v13 + 8 * v23 + 40);
                break;
              case 12:
                if ( v20 == *(_QWORD *)(v13 + 8 * v23)
                  && v19 == *(_QWORD *)(v13 + 8 * v23 + 8)
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 7 )
                {
                  v55 = **(_DWORD **)(v13 + 8 * v23 + 40);
                }
                break;
              case 5:
                if ( *(_QWORD *)(v13 + 8 * v23) != 0x485FE5F6F01FAC5DLL
                  || *(_QWORD *)(v13 + 8 * v23 + 8) != 0x8C9925644427C6A8uLL
                  || *(_DWORD *)(v13 + 8 * v23 + 20)
                  || *(_DWORD *)(v13 + 8 * v23 + 32) != 18 )
                {
                  break;
                }
                v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                v26 = &v72;
                goto LABEL_83;
              case 4:
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x485FE5F6F01FAC5DLL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x8C9925644427C6A8uLL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 18 )
                {
                  v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                  v26 = v82;
                  goto LABEL_83;
                }
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x4B37CD8CA00742A1LL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x7A7687557570AB95LL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20) )
                {
                  v29 = *(_DWORD *)(v13 + 8 * v23 + 32) == 17;
                  goto LABEL_48;
                }
                break;
              case 3:
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x485FE5F6F01FAC5DLL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x8C9925644427C6A8uLL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 18 )
                {
                  v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                  v26 = v81;
                  goto LABEL_83;
                }
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x4B37CD8CA00742A1LL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x7A7687557570AB95LL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20) )
                {
                  v29 = *(_DWORD *)(v13 + 8 * v23 + 32) == 7;
LABEL_48:
                  if ( v29 )
                    LOBYTE(v51) = 1;
                }
                break;
              case 6:
                if ( *(_QWORD *)(v13 + 8 * v23) != 0x4B37CD8CA00742A1LL
                  || *(_QWORD *)(v13 + 8 * v23 + 8) != 0x7A7687557570AB95LL
                  || *(_DWORD *)(v13 + 8 * v23 + 20)
                  || *(_DWORD *)(v13 + 8 * v23 + 32) != 18 )
                {
                  break;
                }
                v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                v26 = v80;
                goto LABEL_83;
              case 7:
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x4B37CD8CA00742A1LL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x7A7687557570AB95LL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 7 )
                {
                  v56 = **(_DWORD **)(v13 + 8 * v23 + 40);
                }
                break;
              case 8:
                if ( *(_QWORD *)(v13 + 8 * v23) == 0x4B37CD8CA00742A1LL
                  && *(_QWORD *)(v13 + 8 * v23 + 8) == 0x7A7687557570AB95LL
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 17 )
                {
                  HIBYTE(v51) = **(_BYTE **)(v13 + 8 * v23 + 40) == 0xFF;
                }
                break;
              default:
                if ( v24 == 1
                  && DEVPKEY_PSA_Aumid == *(_OWORD *)(v13 + 8 * v23)
                  && !*(_DWORD *)(v13 + 8 * v23 + 20)
                  && *(_DWORD *)(v13 + 8 * v23 + 32) == 18 )
                {
                  v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
                  v26 = v79;
                  goto LABEL_83;
                }
                break;
            }
LABEL_85:
            ++v54;
            v17 = ++*(_QWORD *)&Buf2.Data1;
            if ( v54 >= v60 )
            {
              Buf2 = v14;
              v3 = v64;
              v7 = v53;
              v8 = v57;
              goto LABEL_87;
            }
          }
          if ( v18 != *(_QWORD *)(v13 + 8 * v23)
            || v16 != *(_QWORD *)(v13 + 8 * v23 + 8)
            || *(_DWORD *)(v13 + 8 * v23 + 20)
            || *(_DWORD *)(v13 + 8 * v23 + 32) != 18 )
          {
            goto LABEL_85;
          }
          v25 = std::wstring::wstring(v78, *(_QWORD *)(v13 + 8 * v23 + 40));
          v26 = &v69;
LABEL_83:
          std::wstring::operator=(v26, v25);
LABEL_84:
          std::wstring::_Tidy_deallocate(v78);
          v16 = *(_QWORD *)DEVPKEY_Device_InstanceId.fmtid.Data4;
          v18 = *(_QWORD *)&DEVPKEY_Device_InstanceId.fmtid.Data1;
          v19 = *(_QWORD *)DEVPKEY_Device_ConfigFlags.fmtid.Data4;
          v20 = *(_QWORD *)&DEVPKEY_Device_ConfigFlags.fmtid.Data1;
          v21 = *(_QWORD *)DEVPKEY_Device_ContainerId.fmtid.Data4;
          v22 = *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1;
          goto LABEL_85;
        }
LABEL_87:
        if ( v73 && std::wstring::find(&v72, L"\\\\CSR|") != -1 )
        {
          DeviceTypeForPort = 1;
          v30 = std::wstring::wstring(v78, L"IPP Printer Connection");
          std::wstring::operator=(&v75, v30);
          std::wstring::_Tidy_deallocate(v78);
        }
        v31 = v70;
        if ( !v70 )
          goto LABEL_125;
        if ( !v73 || !v76 )
        {
          v32 = DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry(v16, &v69, &v72, &v75);
          v7 = v32;
          v53 = v32;
          if ( v32 < 0 )
          {
            v34 = &v69;
            if ( v71 > 7 )
              v34 = (__int128 *)v69;
            DeviceConfigurationTelemetry::WriteDbgTraceError(
              "DeviceConfiguration::DeviceManager::_DiscoverDevices",
              L"_PopulateInfoFromDeviceRegistry for device %ws failed with hr: 0x%x",
              v34,
              (unsigned int)v32);
          }
          else
          {
            DeviceTypeForPort = DeviceConfiguration::DeviceManager::_GetDeviceTypeForPort(v33, &v75);
          }
          v31 = v70;
        }
        if ( !v31 || !DeviceTypeForPort || !v73 || !v76 || !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        {
LABEL_125:
          v46 = DeviceConfiguration::StringifyDeviceType(DeviceTypeForPort);
          if ( v31 )
          {
            v49 = (const wchar_t *)&v69;
            if ( v71 > 7 )
              v49 = (const wchar_t *)v69;
          }
          else
          {
            v49 = L"Missing Device Id";
          }
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::DeviceManager::_DiscoverDevices",
            L"Invalid device! Device details: -Device Id: %ws -Device type %ws -PrinterName: %ws -PortName: %ws",
            v49,
            v46,
            v47,
            v48);
          goto LABEL_130;
        }
        v35 = v55;
        if ( (v55 & 0x80000) != 0 )
        {
          v38 = v56;
          if ( v56 != 1 )
          {
            v39 = DeviceConfiguration::StringifyDeviceType(DeviceTypeForPort);
            v40 = &v69;
            if ( v71 > 7 )
              v40 = (__int128 *)v69;
            DeviceConfigurationTelemetry::WriteDbgTraceInfo(
              "DeviceConfiguration::DeviceManager::_DiscoverDevices",
              L"Adding device %ws with device type %ws to the list of devices to be configured",
              v40,
              v39);
            std::make_shared<DeviceConfiguration::Device,>(&v62);
            if ( v62 )
            {
              Buf2 = v14;
              v41 = DeviceConfiguration::Device::Initalize(
                      v62,
                      (unsigned int)&v69,
                      (unsigned int)&v72,
                      (unsigned int)&v75,
                      (__int64)v82,
                      (__int64)v81,
                      (__int64)v80,
                      (__int64)v79,
                      (__int64)&Buf2,
                      v51,
                      SHIBYTE(v51),
                      DeviceTypeForPort,
                      v38,
                      v35);
              v7 = v41;
              v53 = v41;
              if ( v41 >= 0 )
              {
                v42 = v3[1];
                if ( v42 == v3[2] )
                {
                  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Emplace_reallocate<std::shared_ptr<DeviceConfiguration::Device> const &>(
                    v3,
                    v3[1],
                    &v62);
                }
                else
                {
                  std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
                    v42,
                    &v62);
                  v3[1] += 16LL;
                }
LABEL_123:
                if ( v63 )
                  std::_Ref_count_base::_Decref(v63);
                goto LABEL_130;
              }
              v43 = (unsigned int)v41;
              v44 = L"Initializing device %ws failed with hr: 0x%x";
            }
            else
            {
              v43 = v7;
              v44 = L"Creating a device object for %ws failed with hr: 0x%x";
            }
            v45 = &v69;
            if ( v71 > 7 )
              v45 = (__int128 *)v69;
            DeviceConfigurationTelemetry::WriteDbgTraceError(
              "DeviceConfiguration::DeviceManager::_DiscoverDevices",
              v44,
              v45,
              v43);
            goto LABEL_123;
          }
          v36 = L"Device %ws is already in the process of being installed. Skipping device...";
        }
        else
        {
          v36 = L"Device %ws does not have CONFIGFLAG_NEEDS_CLASS_CONFIG set. Skipping device...";
        }
        v37 = &v69;
        if ( v71 > 7 )
          v37 = (__int128 *)v69;
        DeviceConfigurationTelemetry::WriteDbgTraceInfo(
          "DeviceConfiguration::DeviceManager::_DiscoverDevices",
          v36,
          v37);
LABEL_130:
        std::wstring::_Tidy_deallocate(v79);
        std::wstring::_Tidy_deallocate(v80);
        std::wstring::_Tidy_deallocate(v81);
        std::wstring::_Tidy_deallocate(v82);
        std::wstring::_Tidy_deallocate(&v72);
        std::wstring::_Tidy_deallocate(&v75);
        std::wstring::_Tidy_deallocate(&v69);
        v57 = ++v8;
        v9 = 7;
      }
      while ( v8 < v52 );
    }
  }
  if ( v58 )
    DevFreeObjects();
  return v3;
}

```

## disassembly

```asm
0x18000fbe0  mov     rax, rsp
0x18000fbe3  push    rbp
0x18000fbe4  push    rbx
0x18000fbe5  push    rsi
0x18000fbe6  push    rdi
0x18000fbe7  push    r12
0x18000fbe9  push    r13
0x18000fbeb  push    r14
0x18000fbed  push    r15
0x18000fbef  lea     rbp, [rax-158h]
0x18000fbf6  sub     rsp, 218h
0x18000fbfd  movaps  xmmword ptr [rax-58h], xmm6
0x18000fc01  movaps  xmmword ptr [rax-68h], xmm7
0x18000fc05  mov     rax, cs:__security_cookie
0x18000fc0c  xor     rax, rsp
0x18000fc0f  mov     [rbp+150h+var_68], rax
0x18000fc16  mov     rsi, rdx
0x18000fc19  mov     [rbp+150h+var_190], rdx
0x18000fc1d  mov     [rbp+150h+var_188], rdx
0x18000fc21  xor     edi, edi
0x18000fc23  mov     [rbp+150h+var_1B8], edi
0x18000fc26  mov     [rdx], rdi
0x18000fc29  mov     [rdx+8], rdi
0x18000fc2d  mov     [rdx+10h], rdi
0x18000fc31  mov     [rbp+150h+var_1B8], 1
0x18000fc38  mov     [rsp+250h+var_1DC], edi
0x18000fc3c  mov     [rbp+150h+var_1C0], rdi
0x18000fc40  lea     rax, [rbp+150h+var_1C0]
0x18000fc44  mov     [rbp+150h+var_180], rax
0x18000fc48  lea     rax, [rsp+250h+var_1DC]
0x18000fc4d  mov     [rbp+150h+var_178], rax
0x18000fc51  mov     [rbp+150h+var_170], 1
0x18000fc55  mov     ecx, cs:_tls_index
0x18000fc5b  mov     rax, gs:58h
0x18000fc64  mov     r14d, 4
0x18000fc6a  mov     rbx, [rax+rcx*8]
0x18000fc6e  mov     eax, [rbx+r14]
0x18000fc72  cmp     cs:dword_180024B88, eax
0x18000fc78  jg      loc_180010697
0x18000fc7e  mov     eax, [rbx+r14]
0x18000fc82  cmp     cs:dword_180024B8C, eax
0x18000fc88  jg      loc_1800108E3
0x18000fc8e  mov     eax, [rbx+r14]
0x18000fc92  cmp     cs:dword_180024B90, eax
0x18000fc98  jg      loc_180010624
0x18000fc9e  mov     r8b, 3
0x18000fca1  mov     dl, 1
0x18000fca3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x18000fcaa  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000fcaf  lea     rax, [rbp+150h+var_1C0]
0x18000fcb3  mov     [rsp+250h+var_218], rax
0x18000fcb8  lea     rax, [rsp+250h+var_1DC]
0x18000fcbd  mov     [rsp+250h+var_220], rax
0x18000fcc2  lea     rax, qword_1800241C0
0x18000fcc9  mov     [rsp+250h+var_228], rax
0x18000fcce  mov     dword ptr [rsp+250h+var_230], 1
0x18000fcd6  lea     r9, byte_180024840
0x18000fcdd  xor     edx, edx
0x18000fcdf  lea     ecx, [rdx+3]
0x18000fce2  lea     r8d, [rdx+0Eh]
0x18000fce6  call    cs:__imp_DevGetObjects
0x18000fcec  mov     r15d, eax
0x18000fcef  mov     [rsp+250h+var_1D8], eax
0x18000fcf3  test    eax, eax
0x18000fcf5  js      loc_1800105C7
0x18000fcfb  mov     r13d, edi
0x18000fcfe  mov     [rbp+150h+var_1C8], edi
0x18000fd01  mov     ecx, [rsp+250h+var_1DC]
0x18000fd05  test    ecx, ecx
0x18000fd07  jz      loc_1800105E1
0x18000fd0d  mov     edx, 7
0x18000fd12  lea     r14, aDeviceconfigur_20; "DeviceConfiguration::DeviceManager::_Di"...
0x18000fd19  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18000fd21  mov     ecx, r13d
0x18000fd24  shl     rcx, 5
0x18000fd28  mov     rax, [rbp+150h+var_1C0]
0x18000fd2c  mov     ebx, [rcx+rax+10h]
0x18000fd30  mov     [rbp+150h+var_1B4], ebx
0x18000fd33  mov     rdi, [rcx+rax+18h]
0x18000fd38  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18000fd3f  movaps  [rbp+150h+Buf2], xmm6
0x18000fd43  xorps   xmm0, xmm0
0x18000fd46  movups  [rbp+150h+var_168], xmm0
0x18000fd4a  xor     ecx, ecx
0x18000fd4c  mov     [rbp+150h+var_158], rcx
0x18000fd50  mov     [rbp+150h+var_150], rdx
0x18000fd54  mov     word ptr [rbp+150h+var_168], cx
0x18000fd58  movups  [rbp+150h+var_128], xmm0
0x18000fd5c  mov     [rbp+150h+var_118], rcx
0x18000fd60  mov     [rbp+150h+var_110], rdx
0x18000fd64  mov     word ptr [rbp+150h+var_128], cx
0x18000fd68  movups  [rbp+150h+var_148], xmm0
0x18000fd6c  mov     [rbp+150h+var_138], rcx
0x18000fd70  mov     [rbp+150h+var_130], rdx
0x18000fd74  mov     word ptr [rbp+150h+var_148], cx
0x18000fd78  mov     [rbp+150h+var_1D0], ecx
0x18000fd7b  mov     r12d, ecx
0x18000fd7e  movups  [rbp+150h+var_88], xmm0
0x18000fd85  movdqu  [rbp+150h+var_78], xmm7
0x18000fd8d  mov     word ptr [rbp+150h+var_88], cx
0x18000fd94  movups  [rbp+150h+var_A8], xmm0
0x18000fd9b  movdqu  [rbp+150h+var_98], xmm7
0x18000fda3  mov     word ptr [rbp+150h+var_A8], cx
0x18000fdaa  movups  [rbp+150h+var_C8], xmm0
0x18000fdb1  movdqu  [rbp+150h+var_B8], xmm7
0x18000fdb9  mov     word ptr [rbp+150h+var_C8], cx
0x18000fdc0  movups  [rbp+150h+var_E8], xmm0
0x18000fdc4  movdqu  [rbp+150h+var_D8], xmm7
0x18000fdc9  mov     word ptr [rbp+150h+var_E8], cx
0x18000fdcd  mov     byte ptr [rsp+250h+var_1E0], cl
0x18000fdd1  mov     byte ptr [rsp+250h+var_1E0+1], cl
0x18000fdd5  mov     [rbp+150h+var_1CC], ecx
0x18000fdd8  mov     r8b, 3
0x18000fddb  mov     dl, 1
0x18000fddd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x18000fde4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000fde9  mov     [rsp+250h+var_1D4], 0
0x18000fdf1  test    ebx, ebx
0x18000fdf3  jz      loc_180010296
0x18000fdf9  xor     eax, eax
0x18000fdfb  mov     qword ptr [rbp+150h+Buf2], rax
0x18000fdff  mov     rcx, qword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data4
0x18000fe06  mov     rdx, qword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18000fe0d  mov     r8, qword ptr cs:DEVPKEY_Device_ConfigFlags.fmtid.Data4
0x18000fe14  mov     r9, qword ptr cs:DEVPKEY_Device_ConfigFlags.fmtid.Data1
0x18000fe1b  mov     r10, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data4
0x18000fe22  mov     r11, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000fe29  mov     r13, qword ptr cs:xmmword_18001CB78+8
0x18000fe30  mov     rsi, qword ptr cs:xmmword_18001CB78
0x18000fe37  mov     r14, qword ptr cs:xmmword_18001CB60+8
0x18000fe3e  mov     r15, qword ptr cs:xmmword_18001CB60
0x18000fe45  lea     rbx, [rax+rax*2]
0x18000fe49  add     rbx, rbx
0x18000fe4c  mov     eax, [rdi+rbx*8+10h]
0x18000fe50  cmp     eax, 100h
0x18000fe55  jnz     short loc_18000FE99
0x18000fe57  cmp     rdx, [rdi+rbx*8]
0x18000fe5b  jnz     loc_180010260
0x18000fe61  cmp     rcx, [rdi+rbx*8+8]
0x18000fe66  jnz     loc_180010260
0x18000fe6c  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000fe71  jnz     loc_180010260
0x18000fe77  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x18000fe7c  jnz     loc_180010260
0x18000fe82  mov     rdx, [rdi+rbx*8+28h]
0x18000fe87  lea     rcx, [rbp+150h+var_108]
0x18000fe8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000fe90  lea     rcx, [rbp+150h+var_168]
0x18000fe94  jmp     loc_180010209
0x18000fe99  cmp     eax, 2
0x18000fe9c  jnz     loc_18000FF37
0x18000fea2  cmp     r11, [rdi+rbx*8]
0x18000fea6  jnz     short loc_18000FECA
0x18000fea8  cmp     r10, [rdi+rbx*8+8]
0x18000fead  jnz     short loc_18000FECA
0x18000feaf  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000feb4  jnz     short loc_18000FECA
0x18000feb6  cmp     dword ptr [rdi+rbx*8+20h], 0Dh
0x18000febb  jnz     short loc_18000FECA
0x18000febd  mov     rax, [rdi+rbx*8+28h]
0x18000fec2  movups  xmm6, xmmword ptr [rax]
0x18000fec5  jmp     loc_180010260
0x18000feca  cmp     r15, [rdi+rbx*8]
0x18000fece  jnz     loc_180010260
0x18000fed4  cmp     r14, [rdi+rbx*8+8]
0x18000fed9  jnz     loc_180010260
0x18000fedf  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000fee4  jnz     loc_180010260
0x18000feea  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x18000feef  jnz     loc_180010260
0x18000fef5  mov     rdx, [rdi+rbx*8+28h]
0x18000fefa  lea     rcx, [rbp+150h+var_108]
0x18000fefe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ff03  mov     rdx, rax
0x18000ff06  lea     rcx, [rbp+150h+var_128]
0x18000ff0a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ff0f  lea     rcx, [rbp+150h+var_108]
0x18000ff13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ff18  mov     rdx, [rdi+rbx*8+28h]
0x18000ff1d  lea     rcx, [rbp+150h+var_108]
0x18000ff21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ff26  lea     rdx, [rbp+150h+var_108]
0x18000ff2a  call    ?_GetDeviceTypeForPort@DeviceManager@DeviceConfiguration@@AEAA?AW4DeviceType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeviceConfiguration::DeviceManager::_GetDeviceTypeForPort(std::wstring const &)
0x18000ff2f  mov     r12d, eax
0x18000ff32  jmp     loc_180010211
0x18000ff37  cmp     eax, 0Ch
0x18000ff3a  jnz     short loc_18000FF76
0x18000ff3c  cmp     r9, [rdi+rbx*8]
0x18000ff40  jnz     loc_180010260
0x18000ff46  cmp     r8, [rdi+rbx*8+8]
0x18000ff4b  jnz     loc_180010260
0x18000ff51  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000ff56  jnz     loc_180010260
0x18000ff5c  cmp     dword ptr [rdi+rbx*8+20h], 7
0x18000ff61  jnz     loc_180010260
0x18000ff67  mov     rax, [rdi+rbx*8+28h]
0x18000ff6c  mov     eax, [rax]
0x18000ff6e  mov     [rbp+150h+var_1D0], eax
0x18000ff71  jmp     loc_180010260
0x18000ff76  cmp     eax, 5
0x18000ff79  jnz     short loc_18000FFBD
0x18000ff7b  cmp     rsi, [rdi+rbx*8]
0x18000ff7f  jnz     loc_180010260
0x18000ff85  cmp     r13, [rdi+rbx*8+8]
0x18000ff8a  jnz     loc_180010260
0x18000ff90  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000ff95  jnz     loc_180010260
0x18000ff9b  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x18000ffa0  jnz     loc_180010260
0x18000ffa6  mov     rdx, [rdi+rbx*8+28h]
0x18000ffab  lea     rcx, [rbp+150h+var_108]
0x18000ffaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ffb4  lea     rcx, [rbp+150h+var_148]
0x18000ffb8  jmp     loc_180010209
0x18000ffbd  cmp     eax, 4
0x18000ffc0  jnz     loc_18001004C
0x18000ffc6  mov     rax, qword ptr cs:xmmword_18001CB48
0x18000ffcd  cmp     rax, [rdi+rbx*8]
0x18000ffd1  jnz     short loc_180010009
0x18000ffd3  mov     rax, qword ptr cs:xmmword_18001CB48+8
0x18000ffda  cmp     rax, [rdi+rbx*8+8]
0x18000ffdf  jnz     short loc_180010009
0x18000ffe1  cmp     dword ptr [rdi+rbx*8+14h], 0
0x18000ffe6  jnz     short loc_180010009
0x18000ffe8  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x18000ffed  jnz     short loc_180010009
0x18000ffef  mov     rdx, [rdi+rbx*8+28h]
0x18000fff4  lea     rcx, [rbp+150h+var_108]
0x18000fff8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000fffd  lea     rcx, [rbp+150h+var_88]
0x180010004  jmp     loc_180010209
0x180010009  mov     rax, qword ptr cs:xmmword_18001CAD0
0x180010010  cmp     rax, [rdi+rbx*8]
0x180010014  jnz     loc_180010260
0x18001001a  mov     rax, qword ptr cs:xmmword_18001CAD0+8
0x180010021  cmp     rax, [rdi+rbx*8+8]
0x180010026  jnz     loc_180010260
0x18001002c  cmp     dword ptr [rdi+rbx*8+14h], 0
0x180010031  jnz     loc_180010260
0x180010037  cmp     dword ptr [rdi+rbx*8+20h], 11h
0x18001003c  jnz     loc_180010260
0x180010042  mov     byte ptr [rsp+250h+var_1E0], 1
0x180010047  jmp     loc_180010260
0x18001004c  cmp     eax, 3
0x18001004f  jnz     short loc_1800100CC
0x180010051  mov     rax, qword ptr cs:xmmword_18001CB30
0x180010058  cmp     rax, [rdi+rbx*8]
0x18001005c  jnz     short loc_180010094
0x18001005e  mov     rax, qword ptr cs:xmmword_18001CB30+8
0x180010065  cmp     rax, [rdi+rbx*8+8]
0x18001006a  jnz     short loc_180010094
0x18001006c  cmp     dword ptr [rdi+rbx*8+14h], 0
0x180010071  jnz     short loc_180010094
0x180010073  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x180010078  jnz     short loc_180010094
0x18001007a  mov     rdx, [rdi+rbx*8+28h]
0x18001007f  lea     rcx, [rbp+150h+var_108]
0x180010083  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010088  lea     rcx, [rbp+150h+var_A8]
0x18001008f  jmp     loc_180010209
0x180010094  mov     rax, qword ptr cs:xmmword_18001CAE8
0x18001009b  cmp     rax, [rdi+rbx*8]
0x18001009f  jnz     loc_180010260
0x1800100a5  mov     rax, qword ptr cs:xmmword_18001CAE8+8
0x1800100ac  cmp     rax, [rdi+rbx*8+8]
0x1800100b1  jnz     loc_180010260
0x1800100b7  cmp     dword ptr [rdi+rbx*8+14h], 0
0x1800100bc  jnz     loc_180010260
0x1800100c2  cmp     dword ptr [rdi+rbx*8+20h], 7
0x1800100c7  jmp     loc_18001003C
0x1800100cc  cmp     eax, 6
0x1800100cf  jnz     short loc_180010124
0x1800100d1  mov     rax, qword ptr cs:xmmword_18001CB18
0x1800100d8  cmp     rax, [rdi+rbx*8]
0x1800100dc  jnz     loc_180010260
0x1800100e2  mov     rax, qword ptr cs:xmmword_18001CB18+8
0x1800100e9  cmp     rax, [rdi+rbx*8+8]
0x1800100ee  jnz     loc_180010260
0x1800100f4  cmp     dword ptr [rdi+rbx*8+14h], 0
0x1800100f9  jnz     loc_180010260
0x1800100ff  cmp     dword ptr [rdi+rbx*8+20h], 12h
0x180010104  jnz     loc_180010260
0x18001010a  mov     rdx, [rdi+rbx*8+28h]
0x18001010f  lea     rcx, [rbp+150h+var_108]
0x180010113  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010118  lea     rcx, [rbp+150h+var_C8]
0x18001011f  jmp     loc_180010209
0x180010124  cmp     eax, 7
0x180010127  jnz     short loc_180010171
0x180010129  mov     rax, qword ptr cs:xmmword_18001CB00
0x180010130  cmp     rax, [rdi+rbx*8]
0x180010134  jnz     loc_180010260
0x18001013a  mov     rax, qword ptr cs:xmmword_18001CB00+8
0x180010141  cmp     rax, [rdi+rbx*8+8]
0x180010146  jnz     loc_180010260
0x18001014c  cmp     dword ptr [rdi+rbx*8+14h], 0
0x180010151  jnz     loc_180010260
0x180010157  cmp     dword ptr [rdi+rbx*8+20h], 7
0x18001015c  jnz     loc_180010260
0x180010162  mov     rax, [rdi+rbx*8+28h]
  ... truncated ...
```

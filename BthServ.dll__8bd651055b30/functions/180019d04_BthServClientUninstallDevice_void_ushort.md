# BthServClientUninstallDevice(void *,ushort *)

- ea: `0x180019d04`
- end: `0x18001aa4a`
- name: `?BthServClientUninstallDevice@@YAJPEAXPEAG@Z`
- size: `3398`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180012c70`
- `0x180025bd0`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800110fc`
- `0x180011194`
- `0x1800114c8`
- `0x180012e00`
- `0x180016664`
- `0x180019d04`
- `0x18001aa50`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019f74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019f74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a6fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a75a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a99a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a99a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a367`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a474`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a578`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a367`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a474`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a578`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a947`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a95f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a974`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a947`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a95f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a974`
- `OLEAUT32!__imp_VariantInit` at `0x18001a22f`
- `OLEAUT32!__imp_VariantInit` at `0x18001a245`
- `OLEAUT32!__imp_VariantInit` at `0x18001a25b`
- `OLEAUT32!__imp_VariantInit` at `0x18001a26f`
- `OLEAUT32!__imp_VariantInit` at `0x18001a22f`
- `OLEAUT32!__imp_VariantInit` at `0x18001a245`
- `OLEAUT32!__imp_VariantInit` at `0x18001a25b`
- `OLEAUT32!__imp_VariantInit` at `0x18001a26f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2d8`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2e3`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2ee`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2f9`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2d8`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2e3`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2ee`
- `OLEAUT32!__imp_VariantClear` at `0x18001a2f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a135`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a135`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001a0a8`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001a0a8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a003`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a003`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a985`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a985`

## string_xrefs

- `0x180019ee9`: `Global\BTH_UNINSTALL_DEVICE_%s`
- `0x18001a46d`: `Microsoft\Windows\Bluetooth\UninstallDeviceTask`
- `0x18001a629`: `Microsoft\Windows\Bluetooth\UninstallDeviceTask`

## pseudocode

```c
__int64 __fastcall BthServClientUninstallDevice(void *a1, unsigned __int16 *a2)
{
  HANDLE EventW; // r12
  OLECHAR *v4; // r14
  OLECHAR *v5; // r13
  OLECHAR *v6; // r15
  int v7; // edx
  int v8; // r8d
  char v9; // di
  _BYTE *v10; // r10
  __int64 v11; // rcx
  unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  OLECHAR *v14; // rax
  unsigned __int16 v15; // r9
  OLECHAR *v16; // rcx
  int v17; // ebx
  _UNKNOWN **v18; // r8
  signed int LastError; // eax
  int v20; // esi
  bool v21; // dl
  __int64 (__fastcall *v22)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v23; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v25; // xmm8
  IRecordInfo *v26; // xmm9_8
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  char v29; // si
  BSTR v30; // rax
  BSTR v31; // rax
  BSTR v32; // rax
  char v33; // dl
  DWORD v34; // eax
  bool v35; // r14
  int v36; // r8d
  int v37; // edx
  __int128 *dwAuthnLevel; // [rsp+28h] [rbp-E0h]
  int dwImpLevel; // [rsp+30h] [rbp-D8h]
  int pAuthList; // [rsp+38h] [rbp-D0h]
  int dwCapabilities; // [rsp+40h] [rbp-C8h]
  int v43; // [rsp+68h] [rbp-A0h]
  LPVOID ppv; // [rsp+70h] [rbp-98h] BYREF
  __int64 v45; // [rsp+78h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-88h] BYREF
  __int64 v47; // [rsp+88h] [rbp-80h] BYREF
  IRecordInfo *v48; // [rsp+90h] [rbp-78h]
  OLECHAR *v49; // [rsp+98h] [rbp-70h]
  VARIANTARG v50; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v51; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v52; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v53; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v55; // [rsp+128h] [rbp+20h]
  __int128 v56; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v57; // [rsp+158h] [rbp+50h]
  __int128 v58; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v59; // [rsp+178h] [rbp+70h]
  __int128 v60; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v61; // [rsp+198h] [rbp+90h]
  OLECHAR psz[64]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR Name[264]; // [rsp+228h] [rbp+120h] BYREF

  v43 = 0;
  EventW = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v48 = 0;
  v55 = 0;
  ppv = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  memset_0(psz, 0, 0x7Cu);
  v9 = 1;
  v10 = WPP_GLOBAL_Control;
  LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      10,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = 2147483646;
  v12 = a2;
  v13 = 62;
  v14 = psz;
  do
  {
    if ( !v11 )
      break;
    v15 = *v12;
    if ( !*v12 )
      break;
    ++v12;
    *v14++ = v15;
    --v11;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  if ( !v13 )
  {
    v17 = -2147024809;
    LOBYTE(v13) = v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 3u;
    v18 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_159;
    WPP_RECORDER_AND_TRACE_SF_sS(*((_QWORD *)v10 + 2), v13, (_BYTE)v18, *((_QWORD *)v10 + 5));
    goto LABEL_22;
  }
  memset_0(Name, 0, 0x208u);
  if ( (int)StringCbPrintfW(Name, 0x208u, L"Global\\BTH_UNINSTALL_DEVICE_%s", psz) < 0 )
  {
    v17 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v13) = 0;
    }
    v18 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_159;
    WPP_RECORDER_AND_TRACE_SF_sdS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      pAuthList,
      dwCapabilities);
    goto LABEL_22;
  }
  EventW = CreateEventW(0, 1, 0, Name);
  if ( !EventW )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v13) = 0;
    }
    v18 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_159;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      13,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    goto LABEL_22;
  }
  v17 = CoInitializeEx(0, 0);
  if ( v17 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v13) = 0;
    }
    v18 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_159;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      14,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    goto LABEL_22;
  }
  v20 = 1;
  v43 = 1;
  v17 = CoInitializeSecurity(0, -1, 0, 0, 6u, 3u, 0, 0, 0);
  if ( v17 == -2147417831 )
  {
    v21 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  else if ( v17 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    LOBYTE(v13) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    v18 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_159;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      16,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    goto LABEL_22;
  }
  v17 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v17 >= 0 )
  {
    v22 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
    VariantInit(&pvarg);
    v23 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v53);
    v25 = *(_OWORD *)&v53.vt;
    v26 = v53.pRecInfo;
    VariantInit(&v52);
    v27 = *(_OWORD *)&v52.vt;
    v28 = v52.pRecInfo;
    VariantInit(&v51);
    v56 = v23;
    v57 = pRecInfo;
    v58 = v25;
    v59 = v26;
    v60 = v27;
    v61 = v28;
    v50 = v51;
    dwAuthnLevel = &v56;
    v17 = v22(ppv, &v50, &v60, &v58);
    VariantClear(&v51);
    VariantClear(&v52);
    VariantClear(&v53);
    VariantClear(&pvarg);
    v29 = 0;
    if ( v17 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (_DWORD)v18,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (unsigned int)&v56,
        dwImpLevel,
        18,
        (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
      goto LABEL_22;
    }
    v30 = SysAllocString(L"\\");
    v5 = v30;
    if ( !v30 )
    {
      v17 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
      goto LABEL_83;
    }
    v17 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v30, &v45);
    if ( v17 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (_DWORD)v18,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (unsigned int)&v56,
          dwImpLevel,
          20,
          (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      v45 = 0;
      goto LABEL_159;
    }
    v31 = SysAllocString(L"Microsoft\\Windows\\Bluetooth\\UninstallDeviceTask");
    v4 = v31;
    v49 = v31;
    if ( !v31 )
    {
      v17 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
      goto LABEL_83;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v45 + 104LL))(v45, v31, &v46);
    if ( v17 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (_DWORD)v18,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (unsigned int)&v56,
          dwImpLevel,
          22,
          (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      v46 = 0;
      goto LABEL_159;
    }
    v32 = SysAllocString(psz);
    v6 = v32;
    if ( !v32 )
    {
      v17 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
LABEL_83:
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v10 + 2), v13, (_BYTE)v18, *((_QWORD *)v10 + 5));
LABEL_22:
      v10 = WPP_GLOBAL_Control;
LABEL_159:
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID, __int64, _UNKNOWN **))(*(_QWORD *)ppv + 16LL))(ppv, v13, v18);
        v10 = WPP_GLOBAL_Control;
      }
      v20 = v43;
      goto LABEL_162;
    }
    LOWORD(v55) = 8;
    *((_QWORD *)&v55 + 1) = v32;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v33 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      v33 = 0;
    if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v33,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    *(_OWORD *)&v50.vt = v55;
    v50.pRecInfo = v48;
    v17 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v46 + 96LL))(v46, &v50, &v47);
    if ( v17 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (_DWORD)v18,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (unsigned int)&v56,
          dwImpLevel,
          25,
          (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      v47 = 0;
      goto LABEL_159;
    }
    v34 = WaitForSingleObject(EventW, 0x3A98u);
    if ( v34 )
    {
      if ( v34 != 258 )
      {
        if ( v34 == -1 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            v29 = 1;
          v35 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            GetLastError();
            LOBYTE(v36) = v35;
            LOBYTE(v37) = v29;
            WPP_RECORDER_AND_TRACE_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v37,
              v36,
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              (unsigned int)&v56,
              dwImpLevel,
              28,
              (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
            v10 = WPP_GLOBAL_Control;
          }
          v4 = v49;
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v13) = 1, v10[25] < 4u) )
          LOBYTE(v13) = 0;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_158;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)v10 + 2),
          v13,
          (_DWORD)v18,
          *((_QWORD *)v10 + 5),
          (_DWORD)dwAuthnLevel,
          dwImpLevel,
          29,
          (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
LABEL_157:
        v10 = WPP_GLOBAL_Control;
LABEL_158:
        v17 = 0;
        goto LABEL_159;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_158;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v13) = 0;
      }
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v13 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_158;
    }
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v10 + 2), v13, (_BYTE)v18, *((_QWORD *)v10 + 5));
    goto LABEL_157;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
  {
    LOBYTE(v13) = 0;
  }
  LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      17,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  ppv = 0;
LABEL_162:
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64, __int64, _UNKNOWN **))(*(_QWORD *)v45 + 16LL))(v45, v13, v18);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64, __int64, _UNKNOWN **))(*(_QWORD *)v46 + 16LL))(v46, v13, v18);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64, __int64, _UNKNOWN **))(*(_QWORD *)v47 + 16LL))(v47, v13, v18);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    SysFreeString(v6);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    SysFreeString(v5);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    CoUninitialize();
    v10 = WPP_GLOBAL_Control;
  }
  if ( EventW )
  {
    CloseHandle(EventW);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 4u )
    v9 = 0;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = v9;
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v10 + 2),
      v13,
      (_DWORD)v18,
      *((_QWORD *)v10 + 5),
      (_DWORD)dwAuthnLevel,
      dwImpLevel,
      30,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180019d04  mov     rax, rsp
0x180019d07  mov     [rax+18h], rbx
0x180019d0b  push    rbp
0x180019d0c  push    rsi
0x180019d0d  push    rdi
0x180019d0e  push    r12
0x180019d10  push    r13
0x180019d12  push    r14
0x180019d14  push    r15
0x180019d16  lea     rbp, [rax-3D8h]
0x180019d1d  sub     rsp, 4A0h
0x180019d24  movaps  xmmword ptr [rax-48h], xmm6
0x180019d28  movaps  xmmword ptr [rax-58h], xmm7
0x180019d2c  movaps  xmmword ptr [rax-68h], xmm8
0x180019d31  movaps  xmmword ptr [rax-78h], xmm9
0x180019d36  movaps  xmmword ptr [rax-88h], xmm10
0x180019d3e  movaps  xmmword ptr [rax-98h], xmm11
0x180019d46  mov     rax, cs:__security_cookie
0x180019d4d  xor     rax, rsp
0x180019d50  mov     [rbp+3D0h+var_A0], rax
0x180019d57  mov     rsi, rdx
0x180019d5a  mov     rbx, rcx
0x180019d5d  xor     eax, eax
0x180019d5f  mov     dword ptr [rsp+4D0h+var_470], eax
0x180019d63  mov     r12d, eax
0x180019d66  mov     r14d, eax
0x180019d69  mov     r13d, eax
0x180019d6c  mov     r15d, eax
0x180019d6f  xorps   xmm0, xmm0
0x180019d72  xor     ecx, ecx
0x180019d74  mov     [rbp+3D0h+var_448], rcx
0x180019d78  movups  [rbp+3D0h+var_3B0], xmm0
0x180019d7c  mov     [rsp+4D0h+ppv], rax
0x180019d81  mov     [rsp+4D0h+var_460], rax
0x180019d86  mov     [rsp+4D0h+var_458], rax
0x180019d8b  mov     [rbp+3D0h+var_450], rax
0x180019d8f  xor     edx, edx; Val
0x180019d91  lea     r8d, [rax+7Ch]; Size
0x180019d95  lea     rcx, [rbp+3D0h+psz]; void *
0x180019d9c  call    memset_0
0x180019da1  lea     r11, WPP_GLOBAL_Control
0x180019da8  lea     edi, [r15+1]
0x180019dac  mov     r10, cs:WPP_GLOBAL_Control
0x180019db3  cmp     r10, r11
0x180019db6  jz      short loc_180019DC4
0x180019db8  cmp     byte ptr [r10+19h], 4
0x180019dbd  jb      short loc_180019DC4
0x180019dbf  mov     dl, dil
0x180019dc2  jmp     short loc_180019DC8
0x180019dc4  xor     eax, eax
0x180019dc6  mov     dl, al
0x180019dc8  lea     rcx, WPP_RECORDER_INITIALIZED
0x180019dcf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180019dd6  setnz   r8b
0x180019dda  lea     rcx, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x180019de1  test    dl, dl
0x180019de3  jnz     short loc_180019DEA
0x180019de5  test    r8b, r8b
0x180019de8  jz      short loc_180019E1B
0x180019dea  mov     [rsp+4D0h+var_480], rsi
0x180019def  mov     [rsp+4D0h+var_488], rbx
0x180019df4  mov     qword ptr [rsp+4D0h+dwCapabilities], rcx
0x180019df9  mov     word ptr [rsp+4D0h+pAuthList], 0Ah
0x180019e00  mov     r9, [r10+28h]
0x180019e04  mov     rcx, [r10+10h]
0x180019e08  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x180019e0d  mov     r10, cs:WPP_GLOBAL_Control
0x180019e14  lea     r11, WPP_GLOBAL_Control
0x180019e1b  mov     ecx, 7FFFFFFEh
0x180019e20  mov     r8, rsi
0x180019e23  mov     edx, 3Eh ; '>'
0x180019e28  lea     rax, [rbp+3D0h+psz]
0x180019e2f  xor     ebx, ebx
0x180019e31  test    rcx, rcx
0x180019e34  jz      short loc_180019E54
0x180019e36  movzx   r9d, word ptr [r8]
0x180019e3a  test    r9w, r9w
0x180019e3e  jz      short loc_180019E54
0x180019e40  add     r8, 2
0x180019e44  mov     [rax], r9w
0x180019e48  add     rax, 2
0x180019e4c  sub     rcx, rdi
0x180019e4f  sub     rdx, rdi
0x180019e52  jnz     short loc_180019E31
0x180019e54  lea     rcx, [rax-2]
0x180019e58  test    rdx, rdx
0x180019e5b  cmovnz  rcx, rax
0x180019e5f  mov     [rcx], bx
0x180019e62  jnz     short loc_180019ECC
0x180019e64  mov     ebx, 80070057h
0x180019e69  cmp     r10, r11
0x180019e6c  jz      short loc_180019E7A
0x180019e6e  cmp     byte ptr [r10+19h], 3
0x180019e73  jb      short loc_180019E7A
0x180019e75  mov     dl, dil
0x180019e78  jmp     short loc_180019E7C
0x180019e7a  xor     dl, dl
0x180019e7c  lea     r8, WPP_RECORDER_INITIALIZED
0x180019e83  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180019e8a  setnz   r8b
0x180019e8e  test    dl, dl
0x180019e90  jnz     short loc_180019E9B
0x180019e92  test    r8b, r8b
0x180019e95  jz      loc_18001A8C8
0x180019e9b  mov     [rsp+4D0h+var_488], rsi
0x180019ea0  lea     rcx, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x180019ea7  mov     qword ptr [rsp+4D0h+dwCapabilities], rcx
0x180019eac  mov     word ptr [rsp+4D0h+pAuthList], 0Bh
0x180019eb3  mov     r9, [r10+28h]
0x180019eb7  mov     rcx, [r10+10h]
0x180019ebb  call    WPP_RECORDER_AND_TRACE_SF_sS
0x180019ec0  mov     r10, cs:WPP_GLOBAL_Control
0x180019ec7  jmp     loc_18001A8C8
0x180019ecc  mov     ebx, 208h
0x180019ed1  mov     r8d, ebx; Size
0x180019ed4  xor     edx, edx; Val
0x180019ed6  lea     rcx, [rbp+3D0h+Name]; void *
0x180019edd  call    memset_0
0x180019ee2  lea     r9, [rbp+3D0h+psz]
0x180019ee9  lea     r8, aGlobalBthUnins; "Global\\BTH_UNINSTALL_DEVICE_%s"
0x180019ef0  mov     edx, ebx; unsigned __int64
0x180019ef2  lea     rcx, [rbp+3D0h+Name]; unsigned __int16 *
0x180019ef9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019efe  xor     esi, esi
0x180019f00  test    eax, eax
0x180019f02  jns     short loc_180019F66
0x180019f04  mov     ebx, 80070057h
0x180019f09  mov     r10, cs:WPP_GLOBAL_Control
0x180019f10  lea     rax, WPP_GLOBAL_Control
0x180019f17  cmp     r10, rax
0x180019f1a  jz      short loc_180019F26
0x180019f1c  cmp     byte ptr [r10+19h], 3
0x180019f21  mov     dl, dil
0x180019f24  jnb     short loc_180019F29
0x180019f26  mov     dl, sil
0x180019f29  lea     r8, WPP_RECORDER_INITIALIZED
0x180019f30  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180019f37  setnz   r8b
0x180019f3b  test    dl, dl
0x180019f3d  jnz     short loc_180019F48
0x180019f3f  test    r8b, r8b
0x180019f42  jz      loc_18001A8C8
0x180019f48  lea     rax, [rbp+3D0h+psz]
0x180019f4f  mov     [rsp+4D0h+var_480], rax
0x180019f54  mov     r9, [r10+28h]
0x180019f58  mov     rcx, [r10+10h]
0x180019f5c  call    WPP_RECORDER_AND_TRACE_SF_sdS
0x180019f61  jmp     loc_180019EC0
0x180019f66  lea     r9, [rbp+3D0h+Name]; lpName
0x180019f6d  xor     r8d, r8d; bInitialState
0x180019f70  mov     edx, edi; bManualReset
0x180019f72  xor     ecx, ecx; lpEventAttributes
0x180019f74  call    cs:__imp_CreateEventW
0x180019f7a  mov     r12, rax
0x180019f7d  test    rax, rax
0x180019f80  jnz     short loc_180019FFF
0x180019f82  call    cs:__imp_GetLastError
0x180019f88  mov     ebx, eax
0x180019f8a  test    eax, eax
0x180019f8c  jle     short loc_180019F97
0x180019f8e  movzx   ebx, ax
0x180019f91  or      ebx, 80070000h
0x180019f97  mov     r10, cs:WPP_GLOBAL_Control
0x180019f9e  lea     rax, WPP_GLOBAL_Control
0x180019fa5  cmp     r10, rax
0x180019fa8  jz      short loc_180019FB4
0x180019faa  cmp     byte ptr [r10+19h], 3
0x180019faf  mov     dl, dil
0x180019fb2  jnb     short loc_180019FB7
0x180019fb4  mov     dl, sil
0x180019fb7  lea     r8, WPP_RECORDER_INITIALIZED
0x180019fbe  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x180019fc5  setnz   r8b
0x180019fc9  test    dl, dl
0x180019fcb  jnz     short loc_180019FD6
0x180019fcd  test    r8b, r8b
0x180019fd0  jz      loc_18001A8C8
0x180019fd6  mov     dword ptr [rsp+4D0h+var_488], ebx
0x180019fda  lea     rcx, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x180019fe1  mov     qword ptr [rsp+4D0h+dwCapabilities], rcx
0x180019fe6  mov     word ptr [rsp+4D0h+pAuthList], 0Dh
0x180019fed  mov     r9, [r10+28h]
0x180019ff1  mov     rcx, [r10+10h]
0x180019ff5  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180019ffa  jmp     loc_180019EC0
0x180019fff  xor     edx, edx; dwCoInit
0x18001a001  xor     ecx, ecx; pvReserved
0x18001a003  call    cs:__imp_CoInitializeEx
0x18001a009  mov     ebx, eax
0x18001a00b  test    eax, eax
0x18001a00d  jns     short loc_18001A077
0x18001a00f  mov     r10, cs:WPP_GLOBAL_Control
0x18001a016  lea     rax, WPP_GLOBAL_Control
0x18001a01d  cmp     r10, rax
0x18001a020  jz      short loc_18001A02C
0x18001a022  cmp     byte ptr [r10+19h], 3
0x18001a027  mov     dl, dil
0x18001a02a  jnb     short loc_18001A02F
0x18001a02c  mov     dl, sil
0x18001a02f  lea     r8, WPP_RECORDER_INITIALIZED
0x18001a036  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001a03d  setnz   r8b
0x18001a041  test    dl, dl
0x18001a043  jnz     short loc_18001A04E
0x18001a045  test    r8b, r8b
0x18001a048  jz      loc_18001A8C8
0x18001a04e  mov     dword ptr [rsp+4D0h+var_488], ebx
0x18001a052  lea     rcx, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001a059  mov     qword ptr [rsp+4D0h+dwCapabilities], rcx
0x18001a05e  mov     word ptr [rsp+4D0h+pAuthList], 0Eh
0x18001a065  mov     r9, [r10+28h]
0x18001a069  mov     rcx, [r10+10h]
0x18001a06d  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001a072  jmp     loc_180019EC0
0x18001a077  mov     esi, edi
0x18001a079  mov     dword ptr [rsp+4D0h+var_470], edi
0x18001a07d  xor     eax, eax
0x18001a07f  mov     [rsp+4D0h+pReserved3], rax; pReserved3
0x18001a084  mov     [rsp+4D0h+dwCapabilities], eax; dwCapabilities
0x18001a088  mov     [rsp+4D0h+pAuthList], rax; pAuthList
0x18001a08d  mov     [rsp+4D0h+dwImpLevel], 3; dwImpLevel
0x18001a095  mov     dword ptr [rsp+4D0h+dwAuthnLevel], 6; dwAuthnLevel
0x18001a09d  xor     r9d, r9d; pReserved1
0x18001a0a0  xor     r8d, r8d; asAuthSvc
0x18001a0a3  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001a0a6  xor     ecx, ecx; pSecDesc
0x18001a0a8  call    cs:__imp_CoInitializeSecurity
0x18001a0ae  mov     ebx, eax
0x18001a0b0  cmp     eax, 80010119h
0x18001a0b5  jnz     loc_18001A1B8
0x18001a0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0c2  lea     rax, WPP_GLOBAL_Control
0x18001a0c9  cmp     rcx, rax
0x18001a0cc  jz      short loc_18001A0D9
0x18001a0ce  cmp     byte ptr [rcx+19h], 3
0x18001a0d2  jb      short loc_18001A0D9
0x18001a0d4  mov     dl, dil
0x18001a0d7  jmp     short loc_18001A0DD
0x18001a0d9  xor     eax, eax
0x18001a0db  mov     dl, al
0x18001a0dd  lea     r8, WPP_RECORDER_INITIALIZED
0x18001a0e4  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001a0eb  setnz   r8b
0x18001a0ef  test    dl, dl
0x18001a0f1  jnz     short loc_18001A0F8
0x18001a0f3  test    r8b, r8b
0x18001a0f6  jz      short loc_18001A118
0x18001a0f8  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001a0ff  mov     qword ptr [rsp+4D0h+dwCapabilities], r9
0x18001a104  mov     word ptr [rsp+4D0h+pAuthList], 0Fh
0x18001a10b  mov     r9, [rcx+28h]
0x18001a10f  mov     rcx, [rcx+10h]
0x18001a113  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001a118  lea     rax, [rsp+4D0h+ppv]
0x18001a11d  mov     [rsp+4D0h+dwAuthnLevel], rax; ppv
0x18001a122  lea     r9, IID_ITaskService; riid
0x18001a129  mov     r8d, edi; dwClsContext
0x18001a12c  xor     edx, edx; pUnkOuter
0x18001a12e  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001a135  call    cs:__imp_CoCreateInstance
0x18001a13b  mov     ebx, eax
0x18001a13d  xor     ecx, ecx
0x18001a13f  test    eax, eax
0x18001a141  jns     loc_18001A21F
0x18001a147  mov     r10, cs:WPP_GLOBAL_Control
0x18001a14e  lea     rax, WPP_GLOBAL_Control
0x18001a155  cmp     r10, rax
0x18001a158  jz      short loc_18001A164
0x18001a15a  cmp     byte ptr [r10+19h], 3
0x18001a15f  mov     dl, dil
0x18001a162  jnb     short loc_18001A166
0x18001a164  mov     dl, cl
0x18001a166  lea     rax, WPP_RECORDER_INITIALIZED
0x18001a16d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001a174  setnz   r8b
0x18001a178  test    dl, dl
0x18001a17a  jnz     short loc_18001A181
0x18001a17c  test    r8b, r8b
0x18001a17f  jz      short loc_18001A1AE
0x18001a181  mov     dword ptr [rsp+4D0h+var_488], ebx
0x18001a185  lea     rcx, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001a18c  mov     qword ptr [rsp+4D0h+dwCapabilities], rcx
0x18001a191  mov     word ptr [rsp+4D0h+pAuthList], 11h
0x18001a198  mov     r9, [r10+28h]
0x18001a19c  mov     rcx, [r10+10h]
0x18001a1a0  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001a1a5  mov     r10, cs:WPP_GLOBAL_Control
0x18001a1ac  xor     ecx, ecx
0x18001a1ae  mov     [rsp+4D0h+ppv], rcx
0x18001a1b3  jmp     loc_18001A8E9
0x18001a1b8  test    ebx, ebx
0x18001a1ba  jns     loc_18001A118
0x18001a1c0  mov     r10, cs:WPP_GLOBAL_Control
0x18001a1c7  lea     rax, WPP_GLOBAL_Control
0x18001a1ce  cmp     r10, rax
0x18001a1d1  jz      short loc_18001A1DF
0x18001a1d3  cmp     byte ptr [r10+19h], 3
0x18001a1d8  jb      short loc_18001A1DF
0x18001a1da  mov     dl, dil
0x18001a1dd  jmp     short loc_18001A1E4
  ... truncated ...
```

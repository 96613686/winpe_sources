# DPGetPropForUpdate(ulong,IUpdateDeploymentDataProvider *,IUpdateDeploymentCallerIdentity *,CDeployUpdate *)

- ea: `0x180023fdc`
- end: `0x180024c97`
- name: `?DPGetPropForUpdate@@YAJKPEAUIUpdateDeploymentDataProvider@@PEAUIUpdateDeploymentCallerIdentity@@PEAVCDeployUpdate@@@Z`
- size: `3259`
- prototype: `int(unsigned int, struct IUpdateDeploymentDataProvider *, struct IUpdateDeploymentCallerIdentity *, struct CDeployUpdate *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180031f20`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x1800087d0`
- `0x180008b30`
- `0x18000c640`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180011bf0`
- `0x180015d24`
- `0x1800217c8`
- `0x180022790`
- `0x180022860`
- `0x1800228f4`
- `0x180022b24`
- `0x180023cb0`
- `0x180023fdc`
- `0x1800255c0`
- `0x180025714`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`
- `0x180068f20`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248c3`
- `RPCRT4!UuidFromStringW` at `0x1800240d5`
- `RPCRT4!UuidFromStringW` at `0x1800240d5`
- `RPCRT4!UuidToStringW` at `0x1800243c4`
- `RPCRT4!UuidToStringW` at `0x180024575`
- `RPCRT4!UuidToStringW` at `0x1800247c6`
- `RPCRT4!UuidToStringW` at `0x1800243c4`
- `RPCRT4!UuidToStringW` at `0x180024575`
- `RPCRT4!UuidToStringW` at `0x1800247c6`

## string_xrefs

- `0x180024697`: `UpdateClassification`
- `0x180024a92`: `UpdateClassification`
- `0x18002446b`: `Failed to get localized metadata for installed categories`
- `0x1800241d9`: `failed to get installed categories`
- `0x18002492d`: `update %ws is missing localized properties`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DPGetPropForUpdate(
        unsigned int a1,
        struct IUpdateDeploymentDataProvider *a2,
        struct IUpdateDeploymentCallerIdentity *a3,
        struct CDeployUpdate *a4)
{
  __int64 v8; // rdx
  signed int v9; // ebx
  int v10; // r12d
  unsigned int v11; // r14d
  RPC_STATUS v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(struct IUpdateDeploymentCallerIdentity *, void **); // rbx
  int v15; // eax
  int v16; // ebx
  unsigned int v17; // ecx
  int v18; // eax
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  int v22; // eax
  char *v23; // rsi
  void **v24; // r14
  _WORD *v25; // rcx
  unsigned int v26; // r15d
  int v27; // eax
  unsigned int v28; // ebx
  int ProductCategoryIdRecursive; // eax
  UUID *p_Uuid; // rcx
  RPC_WSTR v31; // rcx
  int v32; // eax
  RPC_STATUS v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rbx
  __int64 v36; // r14
  void *v37; // rcx
  __int64 v38; // r14
  void *v39; // rcx
  __int64 v40; // r14
  void *v41; // rcx
  __int64 v42; // r14
  void *v43; // rcx
  int v44; // eax
  int v45; // ecx
  unsigned int v46; // r12d
  unsigned int v47; // r14d
  unsigned int v48; // r15d
  __int64 v49; // r9
  int v50; // edx
  char *v51; // rbx
  __int64 v52; // rax
  void *v53; // rax
  __int64 v54; // rdx
  unsigned int v55; // ebx
  unsigned int v56; // r15d
  __int64 v57; // r9
  int v58; // edx
  char *v59; // r14
  __int64 v60; // rax
  const struct std::nothrow_t *v61; // rdx
  wchar_t *v63; // [rsp+20h] [rbp-E0h]
  wchar_t *v64; // [rsp+20h] [rbp-E0h]
  bool v65; // [rsp+70h] [rbp-90h] BYREF
  bool v66[3]; // [rsp+71h] [rbp-8Fh] BYREF
  int v67; // [rsp+74h] [rbp-8Ch]
  unsigned int v68; // [rsp+78h] [rbp-88h]
  _BYTE *v69; // [rsp+80h] [rbp-80h]
  char v70; // [rsp+88h] [rbp-78h]
  _QWORD v71[5]; // [rsp+90h] [rbp-70h] BYREF
  char v72; // [rsp+B8h] [rbp-48h]
  _BYTE v73[112]; // [rsp+C0h] [rbp-40h] BYREF
  int v74; // [rsp+130h] [rbp+30h] BYREF
  RPC_WSTR StringUuid; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v76; // [rsp+140h] [rbp+40h] BYREF
  void *v77; // [rsp+148h] [rbp+48h] BYREF
  void *v78; // [rsp+150h] [rbp+50h] BYREF
  void *lpMem; // [rsp+158h] [rbp+58h] BYREF
  void *v80; // [rsp+160h] [rbp+60h] BYREF
  RPC_WSTR v81; // [rsp+168h] [rbp+68h] BYREF
  __int128 Buf1; // [rsp+170h] [rbp+70h] BYREF
  struct _GUID v83; // [rsp+180h] [rbp+80h] BYREF
  __int128 v84; // [rsp+190h] [rbp+90h] BYREF
  UUID Uuid; // [rsp+1A0h] [rbp+A0h] BYREF
  int v86; // [rsp+1B0h] [rbp+B0h]
  _BYTE v87[656]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v68 = a1;
  if ( !a2 )
  {
    v8 = 1185;
LABEL_3:
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
      (const char *)0x80004003LL,
      (int)v63);
    return (unsigned int)v9;
  }
  if ( !a3 )
  {
    v8 = 1186;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 1187;
    goto LABEL_3;
  }
  v10 = 0;
  v67 = 0;
  v76 = 0;
  v77 = 0;
  v80 = 0;
  v78 = 0;
  v11 = 3456;
  lpMem = 0;
  v74 = 1;
  Uuid = 0;
  v86 = 0;
  v71[0] = &v77;
  v71[1] = &v74;
  v71[2] = &v76;
  v71[3] = &v80;
  v71[4] = &v78;
  v72 = 1;
  CDeployUpdate::CleanupProps(a4);
  v12 = UuidFromStringW(*((RPC_WSTR *)a4 + 2), &Uuid);
  v9 = v12;
  if ( v12 >= 1 )
    v9 = (unsigned __int16)v12 | 0x80010000;
  if ( v9 < 0 )
  {
    v13 = 1225;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
      (const char *)(unsigned int)v9,
      (int)v63);
    goto LABEL_169;
  }
  v86 = *((_DWORD *)a4 + 6);
  v9 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v78);
  if ( v9 < 0 )
  {
    v13 = 1228;
    goto LABEL_66;
  }
  v14 = *(__int64 (__fastcall **)(struct IUpdateDeploymentCallerIdentity *, void **))(*(_QWORD *)a3 + 128LL);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  v9 = v14(a3, &lpMem);
  if ( v9 < 0 )
  {
    v13 = 1229;
    goto LABEL_66;
  }
  LODWORD(v63) = 0;
  v15 = (*(__int64 (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD))(*(_QWORD *)a2 + 24LL))(
          a2,
          7,
          a1);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v17 = *((_DWORD *)v78 + 2);
    v76 = v17;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4DA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
      (const char *)(unsigned int)v15,
      0);
    LODWORD(v64) = v16;
    WUTrace(0, 0, 0x1000000, 5, v64, L"failed to get installed categories");
    v17 = v76;
  }
  if ( v17 )
    v11 = 3458;
  v9 = WuSmartPtr::XPtrBaseWithArrayAllocation<tagDeployableUpdateData,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDeployableUpdateData>>::ReleaseAndAllocArray(
         &v77,
         v17 + v74);
  if ( v9 < 0 )
  {
    v13 = 1257;
    goto LABEL_66;
  }
  switch ( *((_DWORD *)a4 + 14) )
  {
    case 1:
      v18 = 1;
      break;
    case 2:
      v18 = 2;
      break;
    case 4:
      v18 = 4;
      break;
    case 8:
      v18 = 8;
      break;
    default:
      v18 = 0;
      break;
  }
  LODWORD(v63) = v18;
  v9 = (*(__int64 (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
         a2,
         2,
         a1,
         v11);
  if ( v9 < 0 )
  {
    v13 = 1271;
    goto LABEL_66;
  }
  v9 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v80);
  if ( v9 < 0 )
  {
    v13 = 1273;
    goto LABEL_66;
  }
  switch ( *((_DWORD *)a4 + 14) )
  {
    case 1:
      v19 = 1;
      break;
    case 2:
      v19 = 2;
      break;
    case 4:
      v19 = 4;
      break;
    case 8:
      v19 = 8;
      break;
    default:
      v19 = 0;
      break;
  }
  LODWORD(v63) = v19;
  v9 = (*(__int64 (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD))(*(_QWORD *)a2 + 24LL))(
         a2,
         3,
         a1);
  if ( v9 < 0 )
  {
    v13 = 1287;
    goto LABEL_66;
  }
  v20 = 0;
  if ( !v76 )
    goto LABEL_61;
  while ( 1 )
  {
    StringUuid = 0;
    v21 = UuidToStringW((const UUID *)(*((_QWORD *)v78 + 2) + 16LL * v20), &StringUuid);
    if ( v21 >= 1 )
      v21 = (unsigned __int16)v21 | 0x80010000;
    if ( v21 < 0 )
      goto LABEL_55;
    LODWORD(v63) = 0;
    v22 = (*(__int64 (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD, __int64))(*(_QWORD *)a2 + 24LL))(
            a2,
            2,
            a1,
            1412);
    if ( v22 < 0 )
      break;
    v67 = ++v10;
LABEL_55:
    if ( StringUuid )
      XPtrRpcStringFree(StringUuid);
    if ( ++v20 >= v76 )
      goto LABEL_61;
  }
  LODWORD(v63) = v22;
  WUTrace(0, 0, 0x1000000, 5, v63, L"Failed to get localized metadata for installed categories");
  v67 = 0;
  if ( StringUuid )
    XPtrRpcStringFree(StringUuid);
LABEL_61:
  Buf1 = 0;
  v84 = 0;
  v83 = 0;
  v23 = (char *)v77;
  v24 = (void **)((char *)a4 + 568);
  if ( !*((_QWORD *)a4 + 71) )
  {
    v25 = (_WORD *)*((_QWORD *)v77 + 45);
    if ( v25 )
    {
      if ( *v25 )
      {
        v9 = DuplicateString<wchar_t *,wchar_t *>(v25, (char *)a4 + 568);
        if ( v9 < 0 )
        {
          v13 = 1352;
          goto LABEL_66;
        }
      }
    }
  }
  if ( !*v24 || !*(_WORD *)*v24 )
  {
    v26 = 0;
    if ( *((_DWORD *)v23 + 126) )
    {
      while ( 1 )
      {
        memset(v87, 0, 0x288u);
        v65 = 0;
        StringUuid = 0;
        v69 = v87;
        v70 = 1;
        v27 = UuidToStringW((const UUID *)(*((_QWORD *)v23 + 64) + 24LL * v26), &StringUuid);
        if ( v27 >= 1 )
          v27 = (unsigned __int16)v27 | 0x80010000;
        if ( v27 < 0 )
          break;
        LODWORD(v63) = 0;
        v28 = v68;
        if ( (*(int (__fastcall **)(struct IUpdateDeploymentDataProvider *, __int64, _QWORD, __int64))(*(_QWORD *)a2 + 24LL))(
               a2,
               2,
               v68,
               3590) < 0 )
          break;
        if ( (int)DPIsAppCategoryId((const struct tagDSUpdateMetadata *)&v87[8], &v65) >= 0 && v65 )
        {
          Buf1 = *(_OWORD *)(*((_QWORD *)v23 + 64) + 24LL * v26);
          v70 = 0;
          DPFreeDeployableUpdateData(v87);
        }
        else
        {
          ProductCategoryIdRecursive = FindProductCategoryIdRecursive(
                                         (const struct tagDSUpdateMetadata *)(v23 + 8),
                                         a2,
                                         v28,
                                         *((const wchar_t **)a4 + 6),
                                         *((const wchar_t **)a4 + 8),
                                         &v83);
          v9 = ProductCategoryIdRecursive;
          if ( ProductCategoryIdRecursive < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x578,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
              (const char *)(unsigned int)ProductCategoryIdRecursive,
              (int)v63);
            DPFreeDeployableUpdateData(v87);
            v31 = StringUuid;
            goto LABEL_89;
          }
          if ( DPIsGivenCategoryType((const struct tagDSUpdateMetadata *)&v87[8], L"UpdateClassification", &v65) < 0
            || !v65 )
          {
            break;
          }
          v84 = *(_OWORD *)(*((_QWORD *)v23 + 64) + 24LL * v26);
          v70 = 0;
          DPFreeDeployableUpdateData(v87);
        }
LABEL_83:
        if ( StringUuid )
          XPtrRpcStringFree(StringUuid);
        if ( ++v26 >= *((_DWORD *)v23 + 126) )
          goto LABEL_86;
      }
      v70 = 0;
      DPFreeDeployableUpdateData(v87);
      goto LABEL_83;
    }
LABEL_86:
    if ( !memcmp(&Buf1, &GUID_NULL, 0x10u) )
    {
      if ( !memcmp(&v83, &GUID_NULL, 0x10u) )
      {
        v32 = memcmp(&v84, &GUID_NULL, 0x10u);
        p_Uuid = (UUID *)&v84;
        if ( !v32 )
          p_Uuid = &Uuid;
      }
      else
      {
        p_Uuid = &v83;
      }
    }
    else
    {
      p_Uuid = (UUID *)&Buf1;
    }
    v81 = 0;
    v33 = UuidToStringW(p_Uuid, &v81);
    v9 = v33;
    if ( v33 >= 1 )
      v9 = (unsigned __int16)v33 | 0x80010000;
    if ( v9 < 0 )
    {
      v34 = 1430;
LABEL_103:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
        (const char *)(unsigned int)v9,
        (int)v63);
      v31 = v81;
LABEL_89:
      if ( v31 )
        XPtrRpcStringFree(v31);
      goto LABEL_169;
    }
    if ( *v24 )
    {
      SusFree(*v24);
      *v24 = 0;
    }
    v9 = DuplicateString<wchar_t *,wchar_t *>(v81, (char *)a4 + 568);
    if ( v9 < 0 )
    {
      v34 = 1431;
      goto LABEL_103;
    }
    if ( v81 )
      XPtrRpcStringFree(v81);
  }
  v35 = *((_QWORD *)v23 + 56);
  if ( v35 )
  {
    v36 = *(_QWORD *)(v35 + 8);
    v37 = (void *)*((_QWORD *)a4 + 55);
    if ( v37 )
      CoTaskMemFree(v37);
    *((_QWORD *)a4 + 55) = v36;
    *(_QWORD *)(v35 + 8) = 0;
    v38 = *(_QWORD *)(v35 + 16);
    v39 = (void *)*((_QWORD *)a4 + 56);
    if ( v39 )
      CoTaskMemFree(v39);
    *((_QWORD *)a4 + 56) = v38;
    *(_QWORD *)(v35 + 16) = 0;
    v40 = *(_QWORD *)(v35 + 32);
    v41 = (void *)*((_QWORD *)a4 + 57);
    if ( v41 )
      CoTaskMemFree(v41);
    *((_QWORD *)a4 + 57) = v40;
    *(_QWORD *)(v35 + 32) = 0;
    v42 = *(_QWORD *)(v35 + 40);
    v43 = (void *)*((_QWORD *)a4 + 58);
    if ( v43 )
      CoTaskMemFree(v43);
    *((_QWORD *)a4 + 58) = v42;
    *(_QWORD *)(v35 + 40) = 0;
    *((_DWORD *)a4 + 118) = *(_DWORD *)(v35 + 88);
    *(_DWORD *)(v35 + 88) = 0;
    *((_QWORD *)a4 + 60) = *(_QWORD *)(v35 + 96);
    *(_QWORD *)(v35 + 96) = 0;
    v44 = *(_DWORD *)(v35 + 72);
    if ( v44 && *(_QWORD *)(v35 + 80) )
    {
      *((_DWORD *)a4 + 131) = v44;
      *(_DWORD *)(v35 + 72) = 0;
      *((_QWORD *)a4 + 66) = *(_QWORD *)(v35 + 80);
      *(_QWORD *)(v35 + 80) = 0;
    }
  }
  else
  {
    Trace::UpdateIdToString::UpdateIdToString(
      (Trace::UpdateIdToString *)v73,
      (struct CDeployUpdate *)((char *)a4 + 200));
    WUTrace(0, 0, 0x1000000, 5, 0, L"update %ws is missing localized properties");
  }
  if ( !*((_QWORD *)a4 + 58) )
  {
    *((_QWORD *)a4 + 58) = *((_QWORD *)v23 + 28);
    *((_QWORD *)v23 + 28) = 0;
  }
  if ( !*((_QWORD *)a4 + 66) )
  {
    *((_DWORD *)a4 + 131) = *((_DWORD *)v23 + 58);
    *((_DWORD *)v23 + 58) = 0;
    *((_QWORD *)a4 + 66) = *((_QWORD *)v23 + 30);
    *((_QWORD *)v23 + 30) = 0;
  }
  *((_DWORD *)a4 + 38) = *((_DWORD *)v23 + 11);
  *((_DWORD *)a4 + 122) = *((_DWORD *)v23 + 51);
  *((_DWORD *)a4 + 134) = *((_DWORD *)v23 + 48);
  if ( !v80 )
    goto LABEL_134;
  v45 = *((_DWORD *)v23 + 48);
  if ( *((_DWORD *)v80 + 10) )
    goto LABEL_133;
  if ( (*((_DWORD *)v23 + 22) != 4 || (v45 & 0x18) != 0) && (v45 & 4) == 0 )
  {
    if ( *((_DWORD *)v23 + 22) != 4 || (v45 & 8) == 0 && (v45 & 0x10) == 0 )
    {
      *((_DWORD *)a4 + 130) = 2;
      goto LABEL_134;
    }
LABEL_133:
    *((_DWORD *)a4 + 130) = 1;
    goto LABEL_134;
  }
  *((_DWORD *)a4 + 130) = 3;
LABEL_134:
  v46 = v67;
  if ( !v67 )
    goto LABEL_168;
  v47 = 0;
  v48 = 0;
  if ( !*((_DWORD *)v23 + 126) )
    goto LABEL_168;
  do
  {
    v49 = *((_QWORD *)v23 + 64);
    if ( *(_DWORD *)(v49 + 24LL * v48 + 20) )
    {
      v50 = 0;
      v65 = 0;
      v66[0] = 0;
      while ( 1 )
      {
        v51 = (char *)v77 + 648 * (unsigned int)(v50 + v74);
        if ( *(_QWORD *)(v49 + 24LL * v48) == *(_QWORD *)(v51 + 12)
          && *(_QWORD *)(v49 + 24LL * v48 + 8) == *(_QWORD *)(v51 + 20) )
        {
          break;
        }
        if ( ++v50 >= v46 )
          goto LABEL_150;
      }
      if ( DPIsGivenCategoryType((const struct tagDSUpdateMetadata *)(v51 + 8), L"UpdateClassification", &v65) >= 0
        && v65 )
      {
        *(_OWORD *)((char *)a4 + 504) = *(_OWORD *)(v51 + 12);
      }
      else if ( (int)DPIsProductHierarchyCategory((const struct tagDSUpdateMetadata *)(v51 + 8), v66) >= 0 && v66[0] )
      {
        v52 = *((_QWORD *)v51 + 56);
        if ( v52 )
        {
          if ( *(_QWORD *)(v52 + 8) )
            ++v47;
        }
      }
    }
LABEL_150:
    ++v48;
  }
  while ( v48 < *((_DWORD *)v23 + 126) );
  if ( !v47 )
  {
LABEL_168:
    v9 = 0;
    goto LABEL_169;
  }
  v53 = SafeSusAllocArray(v47, 8u);
  *((_QWORD *)a4 + 62) = v53;
  if ( !v53 )
  {
    v54 = 1573;
    goto LABEL_179;
  }
  *((_DWORD *)a4 + 123) = v47;
  v55 = 0;
  v56 = 0;
  while ( 1 )
  {
    v57 = *((_QWORD *)v23 + 64);
    if ( !*(_DWORD *)(v57 + 24LL * v56 + 20) )
      goto LABEL_167;
    v58 = 0;
    v66[0] = 0;
    while ( 1 )
    {
      v59 = (char *)v77 + 648 * (unsigned int)(v58 + v74);
      if ( *(_QWORD *)(v57 + 24LL * v56) == *(_QWORD *)(v59 + 12)
        && *(_QWORD *)(v57 + 24LL * v56 + 8) == *(_QWORD *)(v59 + 20) )
      {
        break;
      }
      if ( ++v58 >= v46 )
        goto LABEL_167;
    }
    v60 = *((_QWORD *)v59 + 56);
    if ( !v60
      || !*(_QWORD *)(v60 + 8)
      || (int)DPIsProductHierarchyCategory((const struct tagDSUpdateMetadata *)(v59 + 8), v66) < 0
      || !v66[0] )
    {
      goto LABEL_167;
    }
    *(_QWORD *)(*((_QWORD *)a4 + 62) + 8LL * v55) = SusStrDup(*(const wchar_t **)(*((_QWORD *)v59 + 56) + 8LL));
    if ( !*(_QWORD *)(*((_QWORD *)a4 + 62) + 8LL * v55) )
      break;
    ++v55;
LABEL_167:
    ++v56;
    if ( v55 >= *((_DWORD *)a4 + 123) )
      goto LABEL_168;
  }
  *((_DWORD *)a4 + 123) = v55;
  v54 = 1603;
LABEL_179:
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v54,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPUpdateHelper.cpp",
    (const char *)0x8007000ELL,
    (int)v63);
LABEL_169:
  wil::details::lambda_call__lambda_47c7d2d5e38e54ab6a844b957ab533dd___::_lambda_call__lambda_47c7d2d5e38e54ab6a844b957ab533dd___(v71);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v78 )
  {
    operator delete(v78, (const struct std::nothrow_t *)0x288);
    v78 = 0;
  }
  if ( v80 )
  {
    operator delete(v80, (const struct std::nothrow_t *)0x288);
    v80 = 0;
  }
  if ( v77 )
    operator delete(v77, v61);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180023fdc  push    rbp
0x180023fde  push    rbx
0x180023fdf  push    rsi
0x180023fe0  push    rdi
0x180023fe1  push    r12
0x180023fe3  push    r13
0x180023fe5  push    r14
0x180023fe7  push    r15
0x180023fe9  lea     rbp, [rsp-368h]
0x180023ff1  sub     rsp, 468h
0x180023ff8  mov     rax, cs:__security_cookie
0x180023fff  xor     rax, rsp
0x180024002  mov     [rbp+3A0h+var_50], rax
0x180024009  mov     rdi, r9
0x18002400c  mov     rsi, r8
0x18002400f  mov     r13, rdx
0x180024012  mov     r15d, ecx
0x180024015  mov     [rsp+4A0h+var_428], ecx
0x180024019  xor     eax, eax
0x18002401b  test    rdx, rdx
0x18002401e  jnz     short loc_180024045
0x180024020  mov     edx, 4A1h; void *
0x180024025  mov     ebx, 80004003h
0x18002402a  mov     rcx, [rbp+3A8h]; this
0x180024031  mov     r9d, ebx; char *
0x180024034  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18002403b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024040  jmp     loc_180024C46
0x180024045  test    rsi, rsi
0x180024048  jnz     short loc_180024051
0x18002404a  mov     edx, 4A2h
0x18002404f  jmp     short loc_180024025
0x180024051  test    rdi, rdi
0x180024054  jnz     short loc_18002405D
0x180024056  mov     edx, 4A3h
0x18002405b  jmp     short loc_180024025
0x18002405d  mov     r12d, eax
0x180024060  mov     [rsp+4A0h+var_42C], eax
0x180024064  mov     [rbp+3A0h+var_360], eax
0x180024067  mov     [rbp+3A0h+var_358], rax
0x18002406b  mov     [rbp+3A0h+var_340], rax
0x18002406f  mov     [rbp+3A0h+var_350], rax
0x180024073  mov     r14d, 0D80h
0x180024079  mov     [rbp+3A0h+lpMem], rax
0x18002407d  mov     [rbp+3A0h+var_370], 1
0x180024084  xorps   xmm0, xmm0
0x180024087  xor     eax, eax
0x180024089  movups  xmmword ptr [rbp+3A0h+Uuid.Data1], xmm0
0x180024090  mov     [rbp+3A0h+var_2F0], eax
0x180024096  lea     rax, [rbp+3A0h+var_358]
0x18002409a  mov     [rbp+3A0h+var_410], rax
0x18002409e  lea     rax, [rbp+3A0h+var_370]
0x1800240a2  mov     [rbp+3A0h+var_408], rax
0x1800240a6  lea     rax, [rbp+3A0h+var_360]
0x1800240aa  mov     [rbp+3A0h+var_400], rax
0x1800240ae  lea     rax, [rbp+3A0h+var_340]
0x1800240b2  mov     [rbp+3A0h+var_3F8], rax
0x1800240b6  lea     rax, [rbp+3A0h+var_350]
0x1800240ba  mov     [rbp+3A0h+var_3F0], rax
0x1800240be  mov     [rbp+3A0h+var_3E8], 1
0x1800240c2  mov     rcx, rdi; this
0x1800240c5  call    ?CleanupProps@CDeployUpdate@@QEAAXXZ; CDeployUpdate::CleanupProps(void)
0x1800240ca  lea     rdx, [rbp+3A0h+Uuid]; Uuid
0x1800240d1  mov     rcx, [rdi+10h]; StringUuid
0x1800240d5  call    cs:__imp_UuidFromStringW
0x1800240db  mov     ebx, eax
0x1800240dd  cmp     eax, 1
0x1800240e0  jl      short loc_1800240EB
0x1800240e2  movzx   ebx, ax
0x1800240e5  or      ebx, 80010000h
0x1800240eb  test    ebx, ebx
0x1800240ed  jns     short loc_1800240F9
0x1800240ef  mov     edx, 4C9h
0x1800240f4  jmp     loc_1800244EE
0x1800240f9  mov     eax, [rdi+18h]
0x1800240fc  mov     [rbp+3A0h+var_2F0], eax
0x180024102  lea     rcx, [rbp+3A0h+var_350]
0x180024106  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x18002410b  mov     ebx, eax
0x18002410d  test    eax, eax
0x18002410f  jns     short loc_18002411B
0x180024111  mov     edx, 4CCh
0x180024116  jmp     loc_1800244EE
0x18002411b  mov     rax, [rsi]
0x18002411e  mov     rbx, [rax+80h]
0x180024125  mov     rcx, [rbp+3A0h+lpMem]; lpMem
0x180024129  test    rcx, rcx
0x18002412c  jz      short loc_180024139
0x18002412e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180024133  xor     ecx, ecx
0x180024135  mov     [rbp+3A0h+lpMem], rcx
0x180024139  lea     rdx, [rbp+3A0h+lpMem]
0x18002413d  mov     rcx, rsi
0x180024140  mov     rax, rbx
0x180024143  call    _guard_dispatch_icall
0x180024148  mov     ebx, eax
0x18002414a  xor     esi, esi
0x18002414c  test    eax, eax
0x18002414e  jns     short loc_18002415A
0x180024150  mov     edx, 4CDh
0x180024155  jmp     loc_1800244EE
0x18002415a  mov     rcx, [rbp+3A0h+var_350]
0x18002415e  mov     rdx, [rbp+3A0h+lpMem]
0x180024162  mov     rax, [r13+0]
0x180024166  mov     [rsp+4A0h+var_440], esi
0x18002416a  mov     [rsp+4A0h+var_448], rcx
0x18002416f  mov     [rsp+4A0h+var_450], rdx
0x180024174  mov     [rsp+4A0h+var_458], rsi
0x180024179  mov     rcx, [rdi+40h]
0x18002417d  mov     [rsp+4A0h+var_460], rcx
0x180024182  mov     [rsp+4A0h+var_468], esi
0x180024186  lea     rcx, OutputString
0x18002418d  mov     [rsp+4A0h+var_470], rcx
0x180024192  mov     rcx, [rdi+30h]
0x180024196  mov     [rsp+4A0h+var_478], rcx
0x18002419b  mov     dword ptr [rsp+4A0h+var_480], esi; int
0x18002419f  mov     r9d, 3
0x1800241a5  mov     r8d, r15d
0x1800241a8  lea     edx, [r9+4]
0x1800241ac  mov     rcx, r13
0x1800241af  mov     rax, [rax+18h]
0x1800241b3  call    _guard_dispatch_icall
0x1800241b8  mov     ebx, eax
0x1800241ba  mov     rcx, [rbp+3A8h]; this
0x1800241c1  test    eax, eax
0x1800241c3  jns     short loc_180024201
0x1800241c5  mov     r9d, eax; char *
0x1800241c8  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x1800241cf  mov     edx, 4DAh; void *
0x1800241d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800241d9  lea     rax, aFailedToGetIns; "failed to get installed categories"
0x1800241e0  mov     [rsp+4A0h+var_478], rax
0x1800241e5  mov     dword ptr [rsp+4A0h+var_480], ebx
0x1800241e9  xor     edx, edx
0x1800241eb  xor     ecx, ecx
0x1800241ed  lea     r9d, [rdx+5]
0x1800241f1  mov     r8d, 1000000h
0x1800241f7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800241fc  mov     ecx, [rbp+3A0h+var_360]
0x1800241ff  jmp     short loc_18002420B
0x180024201  mov     rax, [rbp+3A0h+var_350]
0x180024205  mov     ecx, [rax+8]
0x180024208  mov     [rbp+3A0h+var_360], ecx
0x18002420b  mov     eax, 0D82h
0x180024210  test    ecx, ecx
0x180024212  cmovnz  r14d, eax
0x180024216  mov     edx, [rbp+3A0h+var_370]
0x180024219  add     edx, ecx
0x18002421b  lea     rcx, [rbp+3A0h+var_358]
0x18002421f  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@UtagDeployableUpdateData@@U?$STArrayZeroAllocPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<tagDeployableUpdateData,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDeployableUpdateData>>::ReleaseAndAllocArray(unsigned __int64)
0x180024224  mov     ebx, eax
0x180024226  test    eax, eax
0x180024228  jns     short loc_180024234
0x18002422a  mov     edx, 4E9h
0x18002422f  jmp     loc_1800244EE
0x180024234  mov     rax, [r13+0]
0x180024238  mov     rsi, [rax+18h]
0x18002423c  mov     rdx, [rbp+3A0h+var_358]
0x180024240  mov     r8, [rdi+48h]
0x180024244  mov     r9, [rdi+40h]
0x180024248  mov     r10d, [rdi+18h]
0x18002424c  mov     r11, [rdi+10h]
0x180024250  mov     rbx, [rdi+30h]
0x180024254  mov     ecx, [rdi+38h]
0x180024257  sub     ecx, 1
0x18002425a  jz      short loc_180024286
0x18002425c  sub     ecx, 1
0x18002425f  jz      short loc_18002427F
0x180024261  sub     ecx, 2
0x180024264  jz      short loc_180024278
0x180024266  cmp     ecx, 4
0x180024269  jz      short loc_180024271
0x18002426b  xor     ecx, ecx
0x18002426d  mov     eax, ecx
0x18002426f  jmp     short loc_18002428D
0x180024271  mov     eax, 8
0x180024276  jmp     short loc_18002428B
0x180024278  mov     eax, 4
0x18002427d  jmp     short loc_18002428B
0x18002427f  mov     eax, 2
0x180024284  jmp     short loc_18002428B
0x180024286  mov     eax, 1
0x18002428b  xor     ecx, ecx
0x18002428d  mov     [rsp+4A0h+var_440], ecx
0x180024291  mov     [rsp+4A0h+var_448], rdx
0x180024296  mov     [rsp+4A0h+var_450], rcx
0x18002429b  mov     [rsp+4A0h+var_458], r8
0x1800242a0  mov     [rsp+4A0h+var_460], r9
0x1800242a5  mov     [rsp+4A0h+var_468], r10d
0x1800242aa  mov     [rsp+4A0h+var_470], r11
0x1800242af  mov     [rsp+4A0h+var_478], rbx
0x1800242b4  mov     dword ptr [rsp+4A0h+var_480], eax
0x1800242b8  mov     r9d, r14d
0x1800242bb  mov     r8d, r15d
0x1800242be  mov     edx, 2
0x1800242c3  mov     rcx, r13
0x1800242c6  mov     rax, rsi
0x1800242c9  call    _guard_dispatch_icall
0x1800242ce  mov     ebx, eax
0x1800242d0  xor     r14d, r14d
0x1800242d3  test    eax, eax
0x1800242d5  jns     short loc_1800242E1
0x1800242d7  mov     edx, 4F7h
0x1800242dc  jmp     loc_1800244EE
0x1800242e1  lea     rcx, [rbp+3A0h+var_340]
0x1800242e5  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x1800242ea  mov     ebx, eax
0x1800242ec  test    eax, eax
0x1800242ee  jns     short loc_1800242FA
0x1800242f0  mov     edx, 4F9h
0x1800242f5  jmp     loc_1800244EE
0x1800242fa  mov     rax, [r13+0]
0x1800242fe  mov     rsi, [rax+18h]
0x180024302  mov     rdx, [rbp+3A0h+var_340]
0x180024306  mov     r8, [rdi+48h]
0x18002430a  mov     r9, [rdi+40h]
0x18002430e  mov     r10d, [rdi+18h]
0x180024312  mov     r11, [rdi+10h]
0x180024316  mov     rbx, [rdi+30h]
0x18002431a  mov     ecx, [rdi+38h]
0x18002431d  sub     ecx, 1
0x180024320  jz      short loc_18002434B
0x180024322  sub     ecx, 1
0x180024325  jz      short loc_180024344
0x180024327  sub     ecx, 2
0x18002432a  jz      short loc_18002433D
0x18002432c  cmp     ecx, 4
0x18002432f  jz      short loc_180024336
0x180024331  mov     eax, r14d
0x180024334  jmp     short loc_180024350
0x180024336  mov     eax, 8
0x18002433b  jmp     short loc_180024350
0x18002433d  mov     eax, 4
0x180024342  jmp     short loc_180024350
0x180024344  mov     eax, 2
0x180024349  jmp     short loc_180024350
0x18002434b  mov     eax, 1
0x180024350  mov     [rsp+4A0h+var_440], r14d
0x180024355  mov     [rsp+4A0h+var_448], rdx
0x18002435a  mov     [rsp+4A0h+var_450], r14
0x18002435f  mov     [rsp+4A0h+var_458], r8
0x180024364  mov     [rsp+4A0h+var_460], r9
0x180024369  mov     [rsp+4A0h+var_468], r10d
0x18002436e  mov     [rsp+4A0h+var_470], r11
0x180024373  mov     [rsp+4A0h+var_478], rbx
0x180024378  mov     dword ptr [rsp+4A0h+var_480], eax
0x18002437c  xor     r9d, r9d
0x18002437f  mov     r8d, r15d
0x180024382  lea     edx, [r9+3]
0x180024386  mov     rcx, r13
0x180024389  mov     rax, rsi
0x18002438c  call    _guard_dispatch_icall
0x180024391  mov     ebx, eax
0x180024393  test    eax, eax
0x180024395  jns     short loc_1800243A1
0x180024397  mov     edx, 507h
0x18002439c  jmp     loc_1800244EE
0x1800243a1  xor     ebx, ebx
0x1800243a3  cmp     [rbp+3A0h+var_360], ebx
0x1800243a6  jbe     loc_1800244A2
0x1800243ac  mov     [rbp+3A0h+StringUuid], r14
0x1800243b0  mov     esi, ebx
0x1800243b2  mov     ecx, ebx
0x1800243b4  shl     rcx, 4
0x1800243b8  mov     rax, [rbp+3A0h+var_350]
0x1800243bc  add     rcx, [rax+10h]; Uuid
0x1800243c0  lea     rdx, [rbp+3A0h+StringUuid]; StringUuid
0x1800243c4  call    cs:__imp_UuidToStringW
0x1800243ca  cmp     eax, 1
0x1800243cd  jl      short loc_1800243D7
0x1800243cf  movzx   eax, ax
0x1800243d2  or      eax, 80010000h
0x1800243d7  test    eax, eax
0x1800243d9  js      short loc_18002444E
0x1800243db  mov     rdx, [rbp+3A0h+StringUuid]
0x1800243df  mov     eax, [rbp+3A0h+var_370]
0x1800243e2  add     rax, rsi
0x1800243e5  imul    rcx, rax, 288h
0x1800243ec  add     rcx, [rbp+3A0h+var_358]
0x1800243f0  mov     rax, [r13+0]
0x1800243f4  mov     [rsp+4A0h+var_440], 1
0x1800243fc  mov     [rsp+4A0h+var_448], rcx
0x180024401  mov     [rsp+4A0h+var_450], r14
0x180024406  mov     [rsp+4A0h+var_458], r14
0x18002440b  mov     [rsp+4A0h+var_460], r14
0x180024410  mov     [rsp+4A0h+var_468], r14d
0x180024415  mov     [rsp+4A0h+var_470], rdx
0x18002441a  mov     rcx, [rdi+30h]
0x18002441e  mov     [rsp+4A0h+var_478], rcx
0x180024423  mov     dword ptr [rsp+4A0h+var_480], r14d
0x180024428  mov     r9d, 584h
0x18002442e  mov     r8d, r15d
0x180024431  mov     edx, 2
0x180024436  mov     rcx, r13
0x180024439  mov     rax, [rax+18h]
0x18002443d  call    _guard_dispatch_icall
0x180024442  test    eax, eax
0x180024444  js      short loc_18002446B
0x180024446  inc     r12d
0x180024449  mov     [rsp+4A0h+var_42C], r12d
  ... truncated ...
```

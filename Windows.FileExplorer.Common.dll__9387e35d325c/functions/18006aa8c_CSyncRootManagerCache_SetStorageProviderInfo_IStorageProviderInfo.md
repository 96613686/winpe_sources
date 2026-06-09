# CSyncRootManagerCache::SetStorageProviderInfo(IStorageProviderInfo *)

- ea: `0x18006aa8c`
- end: `0x18006b62e`
- name: `?SetStorageProviderInfo@CSyncRootManagerCache@@QEAAJPEAUIStorageProviderInfo@@@Z`
- size: `2978`
- prototype: `__int64 __fastcall(CSyncRootManagerCache *__hidden this, struct IStorageProviderInfo *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006aa50`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x180007c58`
- `0x180009374`
- `0x18000a838`
- `0x18000b9b0`
- `0x180016dac`
- `0x18001be38`
- `0x18001d320`
- `0x180021cdc`
- `0x180022608`
- `0x180028358`
- `0x180037780`
- `0x180037ca0`
- `0x180038708`
- `0x180043c98`
- `0x1800669f4`
- `0x180069ec4`
- `0x18006aa8c`
- `0x18006c318`
- `0x180089010`

## import_xrefs

- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18006b586`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18006b586`

## string_xrefs

- `0x18006aafe`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006ab5b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006abbe`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006ac19`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006adf8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006ae63`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006af19`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006af80`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006afe4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006b048`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006b0bc`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006b30c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18006b51e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CSyncRootManagerCache::SetStorageProviderInfo(
        struct _RTL_SRWLOCK *this,
        struct IStorageProviderInfo *a2)
{
  char *v4; // r15
  __int64 (__fastcall *v5)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct IStorageProviderInfo *, unsigned __int16 **); // rbx
  int v9; // eax
  __int64 (__fastcall *v10)(struct IStorageProviderInfo *, __int64 *); // rbx
  int v11; // eax
  __int64 (__fastcall *v12)(struct IStorageProviderInfo *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(struct IStorageProviderInfo *, __int64 *); // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(struct IStorageProviderInfo *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, __int64 *); // rbx
  int v30; // eax
  __int64 (__fastcall *v31)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdx
  int v34; // r14d
  bool IsSameIdentifier; // r12
  CStorageProviderRootsCache *v36; // rcx
  __int64 (__fastcall *v37)(struct IStorageProviderInfo *, struct _RTL_SRWLOCK *); // rdi
  int v38; // eax
  CStorageProviderRootsCache *v39; // rax
  CStorageProviderRootsCache *v40; // rbx
  CStorageProviderRootsCache *v41; // r15
  __int64 v42; // rax
  CStorageProviderRootsCache **v43; // rdx
  __int64 (__fastcall *v44)(struct IStorageProviderInfo *, struct _RTL_SRWLOCK *); // rdi
  int v45; // eax
  char *Ptr; // rdx
  int v48; // [rsp+20h] [rbp-100h]
  int v49; // [rsp+20h] [rbp-100h]
  int v50; // [rsp+20h] [rbp-100h]
  __int64 v51; // [rsp+A0h] [rbp-80h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-78h] BYREF
  unsigned __int16 *v53; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-68h]
  __int64 v55; // [rsp+C0h] [rbp-60h]
  __int64 v56; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-50h]
  __int64 v58; // [rsp+D8h] [rbp-48h]
  __int64 v59; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v60; // [rsp+E8h] [rbp-38h]
  __int64 v61; // [rsp+F0h] [rbp-30h]
  __int64 v62; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v63; // [rsp+100h] [rbp-20h] BYREF
  __int64 v64; // [rsp+108h] [rbp-18h]
  __int64 v65; // [rsp+110h] [rbp-10h]
  __int64 v66; // [rsp+118h] [rbp-8h] BYREF
  __int64 v67; // [rsp+120h] [rbp+0h]
  __int64 v68; // [rsp+128h] [rbp+8h]
  unsigned int v69; // [rsp+130h] [rbp+10h] BYREF
  unsigned int v70; // [rsp+134h] [rbp+14h]
  __int64 v71; // [rsp+138h] [rbp+18h] BYREF
  __int64 v72; // [rsp+140h] [rbp+20h]
  __int64 v73; // [rsp+148h] [rbp+28h]
  __int64 v74; // [rsp+150h] [rbp+30h] BYREF
  __int64 v75; // [rsp+158h] [rbp+38h]
  __int64 v76; // [rsp+160h] [rbp+40h]
  __int64 v77; // [rsp+168h] [rbp+48h] BYREF
  __int64 v78; // [rsp+170h] [rbp+50h]
  __int64 v79; // [rsp+178h] [rbp+58h]
  __int64 v80[2]; // [rsp+180h] [rbp+60h] BYREF
  __int64 v81[2]; // [rsp+190h] [rbp+70h] BYREF
  __int64 v82[2]; // [rsp+1A0h] [rbp+80h] BYREF
  __int64 v83[2]; // [rsp+1B0h] [rbp+90h] BYREF
  __int64 v84[2]; // [rsp+1C0h] [rbp+A0h] BYREF
  __int64 v85[2]; // [rsp+1D0h] [rbp+B0h] BYREF
  __int64 v86[2]; // [rsp+1E0h] [rbp+C0h] BYREF
  __int64 v87[2]; // [rsp+1F0h] [rbp+D0h] BYREF
  __int64 v88[2]; // [rsp+200h] [rbp+E0h] BYREF
  __int64 v89[2]; // [rsp+210h] [rbp+F0h] BYREF
  _BYTE v90[48]; // [rsp+220h] [rbp+100h] BYREF
  GUID v91; // [rsp+250h] [rbp+130h] BYREF
  GUID v92; // [rsp+260h] [rbp+140h] BYREF
  GUID v93; // [rsp+270h] [rbp+150h] BYREF
  GUID v94; // [rsp+280h] [rbp+160h] BYREF
  GUID v95; // [rsp+290h] [rbp+170h] BYREF
  GUID v96; // [rsp+2A0h] [rbp+180h] BYREF
  GUID v97; // [rsp+2B0h] [rbp+190h] BYREF
  GUID v98; // [rsp+2C0h] [rbp+1A0h] BYREF
  GUID v99; // [rsp+2D0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+208h]

  v4 = 0;
  v52 = 0;
  v5 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
  v6 = v5(a2, &GUID_eee5c764_3857_4a91_a463_63a237cbe602, &v52);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103A,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v6,
      v48);
    goto LABEL_85;
  }
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v8 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, unsigned __int16 **))(*(_QWORD *)a2 + 24LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
  v54 = -1;
  v55 = -1;
  v9 = v8(a2, &v53);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103D,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v9,
      v48);
LABEL_5:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
    goto LABEL_85;
  }
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v10 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64 *))(*(_QWORD *)a2 + 64LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
  v57 = -1;
  v58 = -1;
  v11 = v10(a2, &v56);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1040,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v11,
      v48);
LABEL_8:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
    goto LABEL_5;
  }
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v12 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64 *))(*(_QWORD *)a2 + 88LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v59);
  v60 = -1;
  v61 = -1;
  v13 = v12(a2, &v59);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4163;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v13,
      v48);
LABEL_12:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v59);
    goto LABEL_8;
  }
  v92 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 24LL))(v52, &v92);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4166;
    goto LABEL_11;
  }
  v93 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 32LL))(v52, &v93);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4169;
    goto LABEL_11;
  }
  v94 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 64LL))(v52, &v94);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4172;
    goto LABEL_11;
  }
  v95 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 40LL))(v52, &v95);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4175;
    goto LABEL_11;
  }
  v98 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 72LL))(v52, &v98);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4178;
    goto LABEL_11;
  }
  v96 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 48LL))(v52, &v96);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4181;
    goto LABEL_11;
  }
  v97 = GUID_NULL;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v52 + 56LL))(v52, &v97);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 4184;
    goto LABEL_11;
  }
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v15 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64 *))(*(_QWORD *)a2 + 200LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v63);
  v64 = -1;
  v65 = -1;
  v16 = v15(a2, &v63);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105B,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v16,
      v48);
LABEL_29:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v63);
    goto LABEL_12;
  }
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v17 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64 *))(*(_QWORD *)a2 + 216LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v66);
  v67 = -1;
  v68 = -1;
  v18 = v17(a2, &v66);
  v7 = v18;
  if ( v18 < 0 )
  {
    v19 = 4190;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v18,
      v48);
LABEL_33:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v66);
    goto LABEL_29;
  }
  v69 = 0;
  v18 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, unsigned int *))(*(_QWORD *)a2 + 168LL))(a2, &v69);
  v7 = v18;
  if ( v18 < 0 )
  {
    v19 = 4193;
    goto LABEL_32;
  }
  v70 = v69;
  v91 = GUID_NULL;
  v18 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, GUID *))(*(_QWORD *)a2 + 296LL))(a2, &v91);
  v7 = v18;
  if ( v18 < 0 )
  {
    v19 = 4197;
    goto LABEL_32;
  }
  v51 = 0;
  v20 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v51);
  v21 = v20(a2, &GUID_4905f136_1f36_4b43_bbcb_fb93964639cd, &v51);
  v7 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1068,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v21,
      v48);
LABEL_40:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v51);
    goto LABEL_33;
  }
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v22 = v51;
  v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 24LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v71);
  v72 = -1;
  v73 = -1;
  v24 = v23(v22, &v71);
  v7 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106B,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v24,
      v48);
LABEL_43:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v71);
    goto LABEL_40;
  }
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v25 = v51;
  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 40LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
  v75 = -1;
  v76 = -1;
  v27 = v26(v25, &v74);
  v7 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106E,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v27,
      v48);
LABEL_46:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
    goto LABEL_43;
  }
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v28 = v51;
  v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 56LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
  v78 = -1;
  v79 = -1;
  v30 = v29(v28, &v77);
  v7 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1071,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v30,
      v48);
LABEL_49:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
    goto LABEL_46;
  }
  v99 = GUID_NULL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
  {
    v62 = 0;
    v31 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v62);
    v32 = v31(a2, &GUID_3dc30cfe_901e_46f2_9e6a_f65b8ce86363, &v62);
    v7 = v32;
    if ( v32 < 0 )
    {
      v33 = 4215;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v32,
        v48);
      Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v62);
      goto LABEL_49;
    }
    v32 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v62 + 32LL))(v62, &v99);
    v7 = v32;
    if ( v32 < 0 )
    {
      v33 = 4216;
      goto LABEL_53;
    }
    Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v62);
  }
  LockCacheAndFreeStale::LockCacheAndFreeStale((LockCacheAndFreeStale *)v90, this + 3);
  v34 = CSyncRootManagerCache::_EnsureCachedValues(this, v90, 0xFFFFFFFFLL);
  if ( v34 < 0 )
    goto LABEL_84;
  IsSameIdentifier = 0;
  while ( !IsSameIdentifier )
  {
    if ( v4 >= this[5].Ptr )
      goto LABEL_68;
    IsSameIdentifier = CStorageProviderRootsCache::IsSameIdentifier(
                         *((CStorageProviderRootsCache **)this[4].Ptr + (_QWORD)v4),
                         v53);
    if ( !IsSameIdentifier )
      goto LABEL_67;
    v36 = (CStorageProviderRootsCache *)*((_QWORD *)this[4].Ptr + (_QWORD)v4);
    *(_OWORD *)v80 = 0;
    *(GUID *)v82 = v91;
    *(GUID *)v83 = v99;
    *(GUID *)v84 = v98;
    *(GUID *)v85 = v97;
    *(GUID *)v86 = v96;
    *(GUID *)v87 = v95;
    *(GUID *)v88 = v94;
    *(GUID *)v89 = v93;
    *(GUID *)v81 = v92;
    v34 = CStorageProviderRootsCache::SetStorageProviderInfo(
            v36,
            (HKEY *)&v53,
            &v56,
            &v59,
            &v63,
            &v66,
            &v71,
            (const WCHAR **)&v74,
            (const WCHAR **)&v77,
            (struct _GUID *)v81,
            (struct _GUID *)v89,
            (struct _GUID *)v88,
            (struct _GUID *)v87,
            (struct _GUID *)v86,
            (struct _GUID *)v85,
            (__int64)v84,
            (__int64)v83,
            v70,
            (__int64)v82,
            (__int64)v80);
    if ( v34 < 0 )
      goto LABEL_67;
    if ( *(_DWORD *)(*((_QWORD *)this[4].Ptr + (_QWORD)v4) + 656LL) != 1 )
      goto LABEL_66;
    v37 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, struct _RTL_SRWLOCK *))(*(_QWORD *)a2 + 24LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &this[12],
      0);
    v38 = v37(a2, this + 12);
    if ( v38 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x109E,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v38,
        v49);
LABEL_66:
      ++v4;
    }
    else
    {
LABEL_67:
      ++v4;
      if ( v34 < 0 )
      {
LABEL_68:
        if ( v34 < 0 )
          goto LABEL_84;
        if ( !IsSameIdentifier )
        {
          v39 = (CStorageProviderRootsCache *)operator new(0x2A8u, (const struct std::nothrow_t *)&std::nothrow);
          v40 = v39;
          v80[0] = (__int64)v39;
          if ( !v39
            || (memset_0(v39, 0, 0x2A8u), (v41 = CStorageProviderRootsCache::CStorageProviderRootsCache(v40)) == 0) )
          {
            v34 = -2147024882;
            goto LABEL_84;
          }
          v42 = std::shared_ptr<WamAccountsCache>::shared_ptr<WamAccountsCache>(v81, &this[10]);
          *(GUID *)v89 = v91;
          *(GUID *)v88 = v99;
          *(GUID *)v87 = v98;
          *(GUID *)v86 = v97;
          *(GUID *)v85 = v96;
          *(GUID *)v84 = v95;
          *(GUID *)v83 = v94;
          *(GUID *)v82 = v93;
          *(GUID *)v80 = v92;
          v34 = CStorageProviderRootsCache::SetStorageProviderInfo(
                  v41,
                  (HKEY *)&v53,
                  &v56,
                  &v59,
                  &v63,
                  &v66,
                  &v71,
                  (const WCHAR **)&v74,
                  (const WCHAR **)&v77,
                  (struct _GUID *)v80,
                  (struct _GUID *)v82,
                  (struct _GUID *)v83,
                  (struct _GUID *)v84,
                  (struct _GUID *)v85,
                  (struct _GUID *)v86,
                  (__int64)v87,
                  (__int64)v88,
                  v70,
                  (__int64)v89,
                  v42);
          if ( v34 < 0 )
            goto LABEL_81;
          if ( *((_DWORD *)v41 + 164) == 1 )
          {
            v44 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, struct _RTL_SRWLOCK *))(*(_QWORD *)a2 + 24LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &this[12],
              0);
            v45 = v44(a2, this + 12);
            if ( v45 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x10C3,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)v45,
                v50);
          }
          v34 = 0;
          Ptr = (char *)this[5].Ptr;
          if ( Ptr != this[7].Ptr
            || (v34 = CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_EnsureCapacity(
                        &this[4],
                        Ptr + 1),
                v34 >= 0) )
          {
            v43 = (CStorageProviderRootsCache **)((char *)this[4].Ptr + 8 * (__int64)this[5].Ptr++);
            if ( v43 )
              *v43 = v41;
          }
          if ( v34 < 0 )
          {
LABEL_81:
            CStorageProviderRootsCache::`scalar deleting destructor'(v41, (unsigned int)v43);
            goto LABEL_84;
          }
        }
        break;
      }
    }
  }
  LODWORD(this[2].Ptr) = SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER);
LABEL_84:
  LockCacheAndFreeStale::~LockCacheAndFreeStale((LockCacheAndFreeStale *)v90);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v74);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v71);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v51);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v66);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v63);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v59);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v56);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
  v7 = v34;
LABEL_85:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
  return v7;
}

```

## disassembly

```asm
0x18006aa8c  mov     [rsp-8+arg_10], rbx
0x18006aa91  push    rbp
0x18006aa92  push    rsi
0x18006aa93  push    rdi
0x18006aa94  push    r12
0x18006aa96  push    r13
0x18006aa98  push    r14
0x18006aa9a  push    r15
0x18006aa9c  lea     rbp, [rsp-1D0h]
0x18006aaa4  sub     rsp, 2F0h
0x18006aaab  mov     rax, cs:__security_cookie
0x18006aab2  xor     rax, rsp
0x18006aab5  mov     [rbp+200h+var_40], rax
0x18006aabc  mov     rsi, rdx
0x18006aabf  mov     r13, rcx
0x18006aac2  xor     r15d, r15d
0x18006aac5  mov     [rbp+200h+var_278], r15
0x18006aac9  mov     rax, [rdx]
0x18006aacc  mov     rbx, [rax]
0x18006aacf  lea     rcx, [rbp+200h+var_278]
0x18006aad3  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006aad8  lea     r8, [rbp+200h+var_278]
0x18006aadc  lea     rdx, _GUID_eee5c764_3857_4a91_a463_63a237cbe602
0x18006aae3  mov     rcx, rsi
0x18006aae6  mov     rax, rbx
0x18006aae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaee  mov     ebx, eax
0x18006aaf0  test    eax, eax
0x18006aaf2  jns     short loc_18006AB14
0x18006aaf4  mov     rcx, [rbp+208h]; this
0x18006aafb  mov     r9d, eax; char *
0x18006aafe  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006ab05  mov     edx, 103Ah; void *
0x18006ab0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ab0f  jmp     loc_18006B5F9
0x18006ab14  mov     [rbp+200h+var_270], r15
0x18006ab18  mov     [rbp+200h+var_268], r15
0x18006ab1c  mov     [rbp+200h+var_260], r15
0x18006ab20  mov     rax, [rsi]
0x18006ab23  mov     rbx, [rax+18h]
0x18006ab27  lea     rcx, [rbp+200h+var_270]
0x18006ab2b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ab30  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006ab34  mov     [rbp+200h+var_268], r14
0x18006ab38  mov     [rbp+200h+var_260], r14
0x18006ab3c  lea     rdx, [rbp+200h+var_270]
0x18006ab40  mov     rcx, rsi
0x18006ab43  mov     rax, rbx
0x18006ab46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab4b  mov     ebx, eax
0x18006ab4d  test    eax, eax
0x18006ab4f  jns     short loc_18006AB7B
0x18006ab51  mov     rcx, [rbp+208h]; this
0x18006ab58  mov     r9d, eax; char *
0x18006ab5b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006ab62  mov     edx, 103Dh; void *
0x18006ab67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ab6c  nop
0x18006ab6d  lea     rcx, [rbp+200h+var_270]
0x18006ab71  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ab76  jmp     loc_18006B5F9
0x18006ab7b  mov     [rbp+200h+var_258], r15
0x18006ab7f  mov     [rbp+200h+var_250], r15
0x18006ab83  mov     [rbp+200h+var_248], r15
0x18006ab87  mov     rax, [rsi]
0x18006ab8a  mov     rbx, [rax+40h]
0x18006ab8e  lea     rcx, [rbp+200h+var_258]
0x18006ab92  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ab97  mov     [rbp+200h+var_250], r14
0x18006ab9b  mov     [rbp+200h+var_248], r14
0x18006ab9f  lea     rdx, [rbp+200h+var_258]
0x18006aba3  mov     rcx, rsi
0x18006aba6  mov     rax, rbx
0x18006aba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abae  mov     ebx, eax
0x18006abb0  test    eax, eax
0x18006abb2  jns     short loc_18006ABDB
0x18006abb4  mov     rcx, [rbp+208h]; this
0x18006abbb  mov     r9d, eax; char *
0x18006abbe  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006abc5  mov     edx, 1040h; void *
0x18006abca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006abcf  nop
0x18006abd0  lea     rcx, [rbp+200h+var_258]
0x18006abd4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006abd9  jmp     short loc_18006AB6D
0x18006abdb  mov     [rbp+200h+var_240], r15
0x18006abdf  mov     [rbp+200h+var_238], r15
0x18006abe3  mov     [rbp+200h+var_230], r15
0x18006abe7  mov     rax, [rsi]
0x18006abea  mov     rbx, [rax+58h]
0x18006abee  lea     rcx, [rbp+200h+var_240]
0x18006abf2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006abf7  mov     [rbp+200h+var_238], r14
0x18006abfb  mov     [rbp+200h+var_230], r14
0x18006abff  lea     rdx, [rbp+200h+var_240]
0x18006ac03  mov     rcx, rsi
0x18006ac06  mov     rax, rbx
0x18006ac09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac0e  mov     ebx, eax
0x18006ac10  test    eax, eax
0x18006ac12  jns     short loc_18006AC3B
0x18006ac14  mov     edx, 1043h; void *
0x18006ac19  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006ac20  mov     r9d, eax; char *
0x18006ac23  mov     rcx, [rbp+208h]; this
0x18006ac2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac2f  nop
0x18006ac30  lea     rcx, [rbp+200h+var_240]
0x18006ac34  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ac39  jmp     short loc_18006ABD0
0x18006ac3b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ac42  movdqu  [rbp+200h+var_C0], xmm0
0x18006ac4a  mov     rcx, [rbp+200h+var_278]
0x18006ac4e  mov     rax, [rcx]
0x18006ac51  lea     rdx, [rbp+200h+var_C0]
0x18006ac58  mov     rax, [rax+18h]
0x18006ac5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac61  mov     ebx, eax
0x18006ac63  test    eax, eax
0x18006ac65  jns     short loc_18006AC6E
0x18006ac67  mov     edx, 1046h
0x18006ac6c  jmp     short loc_18006AC19
0x18006ac6e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ac75  movdqu  [rbp+200h+var_B0], xmm0
0x18006ac7d  mov     rcx, [rbp+200h+var_278]
0x18006ac81  mov     rax, [rcx]
0x18006ac84  lea     rdx, [rbp+200h+var_B0]
0x18006ac8b  mov     rax, [rax+20h]
0x18006ac8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac94  mov     ebx, eax
0x18006ac96  test    eax, eax
0x18006ac98  jns     short loc_18006ACA4
0x18006ac9a  mov     edx, 1049h
0x18006ac9f  jmp     loc_18006AC19
0x18006aca4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006acab  movdqu  [rbp+200h+var_A0], xmm0
0x18006acb3  mov     rcx, [rbp+200h+var_278]
0x18006acb7  mov     rax, [rcx]
0x18006acba  lea     rdx, [rbp+200h+var_A0]
0x18006acc1  mov     rax, [rax+40h]
0x18006acc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acca  mov     ebx, eax
0x18006accc  test    eax, eax
0x18006acce  jns     short loc_18006ACDA
0x18006acd0  mov     edx, 104Ch
0x18006acd5  jmp     loc_18006AC19
0x18006acda  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ace1  movdqu  [rbp+200h+var_90], xmm0
0x18006ace9  mov     rcx, [rbp+200h+var_278]
0x18006aced  mov     rax, [rcx]
0x18006acf0  lea     rdx, [rbp+200h+var_90]
0x18006acf7  mov     rax, [rax+28h]
0x18006acfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad00  mov     ebx, eax
0x18006ad02  test    eax, eax
0x18006ad04  jns     short loc_18006AD10
0x18006ad06  mov     edx, 104Fh
0x18006ad0b  jmp     loc_18006AC19
0x18006ad10  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ad17  movdqu  [rbp+200h+var_60], xmm0
0x18006ad1f  mov     rcx, [rbp+200h+var_278]
0x18006ad23  mov     rax, [rcx]
0x18006ad26  lea     rdx, [rbp+200h+var_60]
0x18006ad2d  mov     rax, [rax+48h]
0x18006ad31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad36  mov     ebx, eax
0x18006ad38  test    eax, eax
0x18006ad3a  jns     short loc_18006AD46
0x18006ad3c  mov     edx, 1052h
0x18006ad41  jmp     loc_18006AC19
0x18006ad46  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ad4d  movdqu  [rbp+200h+var_80], xmm0
0x18006ad55  mov     rcx, [rbp+200h+var_278]
0x18006ad59  mov     rax, [rcx]
0x18006ad5c  lea     rdx, [rbp+200h+var_80]
0x18006ad63  mov     rax, [rax+30h]
0x18006ad67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad6c  mov     ebx, eax
0x18006ad6e  test    eax, eax
0x18006ad70  jns     short loc_18006AD7C
0x18006ad72  mov     edx, 1055h
0x18006ad77  jmp     loc_18006AC19
0x18006ad7c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ad83  movdqu  [rbp+200h+var_70], xmm0
0x18006ad8b  mov     rcx, [rbp+200h+var_278]
0x18006ad8f  mov     rax, [rcx]
0x18006ad92  lea     rdx, [rbp+200h+var_70]
0x18006ad99  mov     rax, [rax+38h]
0x18006ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ada2  mov     ebx, eax
0x18006ada4  test    eax, eax
0x18006ada6  jns     short loc_18006ADB2
0x18006ada8  mov     edx, 1058h
0x18006adad  jmp     loc_18006AC19
0x18006adb2  mov     [rbp+200h+var_220], r15
0x18006adb6  mov     [rbp+200h+var_218], r15
0x18006adba  mov     [rbp+200h+var_210], r15
0x18006adbe  mov     rax, [rsi]
0x18006adc1  mov     rbx, [rax+0C8h]
0x18006adc8  lea     rcx, [rbp+200h+var_220]
0x18006adcc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006add1  mov     [rbp+200h+var_218], r14
0x18006add5  mov     [rbp+200h+var_210], r14
0x18006add9  lea     rdx, [rbp+200h+var_220]
0x18006addd  mov     rcx, rsi
0x18006ade0  mov     rax, rbx
0x18006ade3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ade8  mov     ebx, eax
0x18006adea  test    eax, eax
0x18006adec  jns     short loc_18006AE18
0x18006adee  mov     rcx, [rbp+208h]; this
0x18006adf5  mov     r9d, eax; char *
0x18006adf8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006adff  mov     edx, 105Bh; void *
0x18006ae04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ae09  nop
0x18006ae0a  lea     rcx, [rbp+200h+var_220]
0x18006ae0e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ae13  jmp     loc_18006AC30
0x18006ae18  mov     [rbp+200h+var_208], r15
0x18006ae1c  mov     [rbp+200h+var_200], r15
0x18006ae20  mov     [rbp+200h+var_1F8], r15
0x18006ae24  mov     rax, [rsi]
0x18006ae27  mov     rbx, [rax+0D8h]
0x18006ae2e  lea     rcx, [rbp+200h+var_208]
0x18006ae32  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ae37  mov     [rbp+200h+var_200], r14
0x18006ae3b  mov     [rbp+200h+var_1F8], r14
0x18006ae3f  lea     rdx, [rbp+200h+var_208]
0x18006ae43  mov     rcx, rsi
0x18006ae46  mov     rax, rbx
0x18006ae49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae4e  mov     ebx, eax
0x18006ae50  test    eax, eax
0x18006ae52  jns     short loc_18006AE7B
0x18006ae54  mov     edx, 105Eh; void *
0x18006ae59  mov     rcx, [rbp+208h]; this
0x18006ae60  mov     r9d, eax; char *
0x18006ae63  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006ae6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ae6f  nop
0x18006ae70  lea     rcx, [rbp+200h+var_208]
0x18006ae74  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006ae79  jmp     short loc_18006AE0A
0x18006ae7b  mov     [rbp+200h+var_1F0], r15d
0x18006ae7f  mov     rax, [rsi]
0x18006ae82  lea     rdx, [rbp+200h+var_1F0]
0x18006ae86  mov     rcx, rsi
0x18006ae89  mov     rax, [rax+0A8h]
0x18006ae90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae95  mov     ebx, eax
0x18006ae97  test    eax, eax
0x18006ae99  jns     short loc_18006AEA2
0x18006ae9b  mov     edx, 1061h
0x18006aea0  jmp     short loc_18006AE59
0x18006aea2  mov     eax, [rbp+200h+var_1F0]
0x18006aea5  mov     [rbp+200h+var_1EC], eax
0x18006aea8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006aeaf  movdqu  [rbp+200h+var_D0], xmm0
0x18006aeb7  mov     rax, [rsi]
0x18006aeba  lea     rdx, [rbp+200h+var_D0]
0x18006aec1  mov     rcx, rsi
0x18006aec4  mov     rax, [rax+128h]
0x18006aecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aed0  mov     ebx, eax
0x18006aed2  test    eax, eax
0x18006aed4  jns     short loc_18006AEE0
0x18006aed6  mov     edx, 1065h
0x18006aedb  jmp     loc_18006AE59
0x18006aee0  mov     [rbp+200h+var_280], r15
0x18006aee4  mov     rax, [rsi]
0x18006aee7  mov     rbx, [rax]
0x18006aeea  lea     rcx, [rbp+200h+var_280]
0x18006aeee  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006aef3  lea     r8, [rbp+200h+var_280]
0x18006aef7  lea     rdx, _GUID_4905f136_1f36_4b43_bbcb_fb93964639cd
0x18006aefe  mov     rcx, rsi
0x18006af01  mov     rax, rbx
0x18006af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af09  mov     ebx, eax
0x18006af0b  test    eax, eax
0x18006af0d  jns     short loc_18006AF39
0x18006af0f  mov     rcx, [rbp+208h]; this
0x18006af16  mov     r9d, eax; char *
0x18006af19  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006af20  mov     edx, 1068h; void *
0x18006af25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006af2a  nop
0x18006af2b  lea     rcx, [rbp+200h+var_280]
0x18006af2f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006af34  jmp     loc_18006AE70
0x18006af39  mov     [rbp+200h+var_1E8], r15
0x18006af3d  mov     [rbp+200h+var_1E0], r15
0x18006af41  mov     [rbp+200h+var_1D8], r15
0x18006af45  mov     rdi, [rbp+200h+var_280]
0x18006af49  mov     rax, [rdi]
0x18006af4c  mov     rbx, [rax+18h]
0x18006af50  lea     rcx, [rbp+200h+var_1E8]
0x18006af54  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```

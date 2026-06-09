# CStorageProviderRootsCache::GetStorageProviderInfo(IStorageProviderInfo * *)

- ea: `0x18000964c`
- end: `0x180009f63`
- name: `?GetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJPEAPEAUIStorageProviderInfo@@@Z`
- size: `2327`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, struct IStorageProviderInfo **)`
- caller_count: `9`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800083f0`
- `0x180008a40`
- `0x18000a130`
- `0x180012554`
- `0x18001267c`
- `0x1800641e4`
- `0x180065888`
- `0x1800659d8`
- `0x18006b8ac`

## callees

- `0x180004a54`
- `0x18000776c`
- `0x1800077c8`
- `0x18000964c`
- `0x180012f60`
- `0x180013940`
- `0x18001c09c`
- `0x18001c864`
- `0x18001c8c8`
- `0x1800280d4`
- `0x1800669f4`
- `0x18006c318`
- `0x180089010`

## string_xrefs

- `0x1800096b1`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009703`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009753`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18000985d`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009a1b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009a99`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009b2b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009bb9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009c44`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009cdf`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009da9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009e0b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180009eb6`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CStorageProviderRootsCache::GetStorageProviderInfo(
        CStorageProviderRootsCache *this,
        struct IStorageProviderInfo **a2)
{
  const struct _GUID *v4; // rcx
  int Instance; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  struct IStorageProviderInfo *v9; // rcx
  int v10; // eax
  struct IStorageProviderInfo *v11; // rcx
  int v12; // eax
  struct IStorageProviderInfo *v13; // rcx
  struct IStorageProviderInfo *v14; // rdi
  __int64 (__fastcall *v15)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  struct IStorageProviderInfo *v18; // rdi
  __int64 (__fastcall *v19)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  struct IStorageProviderInfo *v22; // rdi
  __int64 (__fastcall *v23)(struct IStorageProviderInfo *, GUID *, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  struct IStorageProviderInfo *v26; // rbx
  __int64 (__fastcall *v27)(struct IStorageProviderInfo *, GUID *, __int64 *); // rdi
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  struct IStorageProviderInfo *v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rdx
  struct IStorageProviderInfo *v41; // rcx
  struct IStorageProviderInfo *v42; // rbx
  __int64 (__fastcall *v43)(struct IStorageProviderInfo *, GUID *, __int64 *); // rdi
  int v44; // eax
  __int64 v45; // rdx
  __int64 v47; // [rsp+20h] [rbp-30h] BYREF
  __int64 v48; // [rsp+28h] [rbp-28h] BYREF
  __int64 v49; // [rsp+30h] [rbp-20h] BYREF
  __int64 v50; // [rsp+38h] [rbp-18h] BYREF
  __int64 v51; // [rsp+40h] [rbp-10h] BYREF
  __int64 v52; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct IStorageProviderInfo *v54; // [rsp+88h] [rbp+38h] BYREF
  __int64 v55; // [rsp+90h] [rbp+40h] BYREF
  __int64 v56; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  v54 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v54);
  Instance = CStorageProviderInfo_CreateInstance(v4, (void **)&v54);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2908;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)Instance,
      v47);
LABEL_115:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v54);
    return v6;
  }
  v8 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 32LL))(v54, *(_QWORD *)this);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5D,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v8,
      v47);
    v9 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v6;
  }
  v10 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 72LL))(
          v54,
          *((_QWORD *)this + 3));
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5E,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v10,
      v47);
    v11 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v6;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 96LL))(
               v54,
               *((_QWORD *)this + 6));
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2911;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64, _QWORD))(*(_QWORD *)v54 + 176LL))(
               v54,
               4095,
               *((unsigned int *)this + 136));
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2912;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 104LL))(
               v54,
               (char *)this + 336);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2913;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 120LL))(
               v54,
               (char *)this + 352);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2914;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 136LL))(
               v54,
               (char *)this + 368);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2915;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 152LL))(
               v54,
               (char *)this + 384);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2916;
    goto LABEL_13;
  }
  v12 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 232LL))(
          v54,
          (char *)this + 400);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB65,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v12,
      v47);
    v13 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v6;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 208LL))(
               v54,
               *((_QWORD *)this + 9));
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2918;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 224LL))(
               v54,
               *((_QWORD *)this + 12));
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2919;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, _QWORD))(*(_QWORD *)v54 + 280LL))(
               v54,
               *((_QWORD *)this + 15));
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2920;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 304LL))(
               v54,
               (char *)this + 432);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2921;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 264LL))(
               v54,
               (char *)this + 416);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2922;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 344LL))(
               v54,
               (char *)this + 448);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2923;
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, char *))(*(_QWORD *)v54 + 368LL))(
               v54,
               (char *)this + 480);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2924;
    goto LABEL_13;
  }
  Instance = CStorageProviderRootsCache::SetIconOverlayHandlerClsidArrayHelper(this, v54);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2925;
    goto LABEL_13;
  }
  Instance = CStorageProviderRootsCache::SetContextMenuVerbsHelper(this, v54);
  v6 = Instance;
  if ( Instance < 0 )
  {
    v7 = 2926;
    goto LABEL_13;
  }
  v55 = 0;
  v14 = v54;
  v15 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v54;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
  v16 = v15(v14, &GUID_884abcd3_5446_45ff_9226_e95d8e2a7006, &v55);
  v6 = v16;
  if ( v16 < 0 )
  {
    v17 = 2929;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v16,
      v47);
LABEL_49:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
    goto LABEL_115;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 24LL))(v55, (char *)this + 496);
  v6 = v16;
  if ( v16 < 0 )
  {
    v17 = 2930;
    goto LABEL_48;
  }
  v56 = 0;
  v18 = v54;
  v19 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v54;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
  v20 = v19(v18, &GUID_04a48a40_5a26_4801_8086_617eb0d17d00, &v56);
  v6 = v20;
  if ( v20 < 0 )
  {
    v21 = 2933;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v20,
      v47);
LABEL_55:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
    goto LABEL_49;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v56 + 24LL))(v56, (char *)this + 464);
  v6 = v20;
  if ( v20 < 0 )
  {
    v21 = 2934;
    goto LABEL_54;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl) )
  {
    v51 = 0;
    v22 = v54;
    v23 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v54;
    Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v51);
    v24 = v23(v22, &GUID_bd80594c_4683_48bf_8701_79127c1462e7, &v51);
    v6 = v24;
    if ( v24 < 0 )
    {
      v25 = 2939;
LABEL_61:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v24,
        v47);
      Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v51);
      goto LABEL_55;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v51 + 24LL))(v51, (char *)this + 512);
    v6 = v24;
    if ( v24 < 0 )
    {
      v25 = 2940;
      goto LABEL_61;
    }
    Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v51);
  }
  v47 = 0;
  v26 = v54;
  v27 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v54;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v47);
  v28 = v27(v26, &GUID_cf745728_cbbe_415e_b530_066b3ed219b6, &v47);
  v6 = v28;
  if ( v28 < 0 )
  {
    v29 = 2944;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v28,
      v47);
LABEL_68:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v47);
    goto LABEL_55;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 24LL))(v47, *((_QWORD *)this + 18));
  v6 = v28;
  if ( v28 < 0 )
  {
    v29 = 2945;
    goto LABEL_67;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 40LL))(v47, *((_QWORD *)this + 21));
  v6 = v28;
  if ( v28 < 0 )
  {
    v29 = 2946;
    goto LABEL_67;
  }
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 56LL))(v47, *((_QWORD *)this + 24));
  v6 = v30;
  if ( v30 >= 0 )
  {
    v48 = 0;
    v35 = Microsoft::WRL::ComPtr<IStorageProviderInfo>::As<IStorageProviderIdentityInfo>(&v54, &v48);
    v6 = v35;
    if ( v35 < 0 )
    {
      v36 = 2950;
LABEL_85:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v35,
        v47);
LABEL_86:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
      goto LABEL_68;
    }
    v35 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 32LL))(v48, *((_QWORD *)this + 27));
    v6 = v35;
    if ( v35 < 0 )
    {
      v36 = 2951;
      goto LABEL_85;
    }
    v35 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 48LL))(v48, *((_QWORD *)this + 30));
    v6 = v35;
    if ( v35 < 0 )
    {
      v36 = 2952;
      goto LABEL_85;
    }
    v35 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 64LL))(v48, *((_QWORD *)this + 33));
    v6 = v35;
    if ( v35 < 0 )
    {
      v36 = 2953;
      goto LABEL_85;
    }
    (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v48 + 80LL))(v48, *((_DWORD *)this + 164) == 1);
    v49 = 0;
    v37 = Microsoft::WRL::ComPtr<IStorageProviderInfo>::As<IStorageProviderIdentityInfo2>(&v54, &v49);
    v6 = v37;
    if ( v37 < 0 )
    {
      v38 = 2957;
LABEL_95:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v37,
        v47);
LABEL_96:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
      goto LABEL_86;
    }
    v37 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 32LL))(v49, *((_QWORD *)this + 36));
    v6 = v37;
    if ( v37 < 0 )
    {
      v38 = 2958;
      goto LABEL_95;
    }
    v50 = 0;
    v39 = Microsoft::WRL::ComPtr<IStorageProviderInfo>::As<IStorageProviderIdentityInfo3>(&v54, &v50);
    v6 = v39;
    if ( v39 < 0 )
    {
      v40 = 2961;
LABEL_101:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v39,
        v47);
LABEL_102:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v50);
      goto LABEL_96;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 32LL))(v50, *((_QWORD *)this + 39));
    v6 = v39;
    if ( v39 < 0 )
    {
      v40 = 2962;
      goto LABEL_101;
    }
    v41 = v54;
    if ( v54 )
    {
      (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v54 + 8LL))(v54);
      v41 = v54;
    }
    *a2 = v41;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
    {
      v52 = 0;
      v42 = v54;
      v43 = **(__int64 (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v54;
      Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v52);
      v44 = v43(v42, &GUID_3dc30cfe_901e_46f2_9e6a_f65b8ce86363, &v52);
      v6 = v44;
      if ( v44 < 0 )
      {
        v45 = 2968;
LABEL_110:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v45,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)v44,
          v47);
        Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v52);
        goto LABEL_102;
      }
      v44 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v52 + 24LL))(v52, (char *)this + 528);
      v6 = v44;
      if ( v44 < 0 )
      {
        v45 = 2969;
        goto LABEL_110;
      }
      Microsoft::WRL::ComPtr<IStorageProviderShareLinkSourceInfo>::InternalRelease(&v52);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
    v6 = 0;
    goto LABEL_115;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB83,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v30,
    v47);
  v31 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(struct IStorageProviderInfo *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return v6;
}

```

## disassembly

```asm
0x18000964c  mov     [rsp-28h+arg_0], rbx
0x180009651  push    rbp
0x180009652  push    rsi
0x180009653  push    rdi
0x180009654  push    r14
0x180009656  push    r15
0x180009658  mov     rbp, rsp
0x18000965b  sub     rsp, 50h
0x18000965f  mov     r14, rdx
0x180009662  mov     rsi, rcx
0x180009665  xor     r15d, r15d
0x180009668  mov     [rdx], r15
0x18000966b  mov     [rbp+arg_8], r15
0x18000966f  lea     rcx, [rbp+arg_8]
0x180009673  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009678  lea     rdx, [rbp+arg_8]; void **
0x18000967c  call    ?CStorageProviderInfo_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CStorageProviderInfo_CreateInstance(_GUID const &,void * *)
0x180009681  mov     ebx, eax
0x180009683  test    eax, eax
0x180009685  jns     short loc_180009691
0x180009687  mov     edx, 0B5Ch
0x18000968c  jmp     loc_180009753
0x180009691  mov     rcx, [rbp+arg_8]
0x180009695  mov     rax, [rcx]
0x180009698  mov     rdx, [rsi]
0x18000969b  mov     rax, [rax+20h]
0x18000969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a4  mov     ebx, eax
0x1800096a6  test    eax, eax
0x1800096a8  jns     short loc_1800096E2
0x1800096aa  mov     rcx, [rbp+28h]; this
0x1800096ae  mov     r9d, eax; char *
0x1800096b1  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800096b8  mov     edx, 0B5Dh; void *
0x1800096bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096c2  nop
0x1800096c3  mov     rcx, [rbp+arg_8]
0x1800096c7  test    rcx, rcx
0x1800096ca  jz      short loc_1800096DD
0x1800096cc  mov     [rbp+arg_8], r15
0x1800096d0  mov     rax, [rcx]
0x1800096d3  mov     rax, [rax+10h]
0x1800096d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096dc  nop
0x1800096dd  jmp     loc_180009F4D
0x1800096e2  mov     rcx, [rbp+arg_8]
0x1800096e6  mov     rax, [rcx]
0x1800096e9  mov     rdx, [rsi+18h]
0x1800096ed  mov     rax, [rax+48h]
0x1800096f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f6  mov     ebx, eax
0x1800096f8  test    eax, eax
0x1800096fa  jns     short loc_180009734
0x1800096fc  mov     rcx, [rbp+28h]; this
0x180009700  mov     r9d, eax; char *
0x180009703  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000970a  mov     edx, 0B5Eh; void *
0x18000970f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009714  nop
0x180009715  mov     rcx, [rbp+arg_8]
0x180009719  test    rcx, rcx
0x18000971c  jz      short loc_18000972F
0x18000971e  mov     [rbp+arg_8], r15
0x180009722  mov     rax, [rcx]
0x180009725  mov     rax, [rax+10h]
0x180009729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000972e  nop
0x18000972f  jmp     loc_180009F4D
0x180009734  mov     rcx, [rbp+arg_8]
0x180009738  mov     rax, [rcx]
0x18000973b  mov     rdx, [rsi+30h]
0x18000973f  mov     rax, [rax+60h]
0x180009743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009748  mov     ebx, eax
0x18000974a  test    eax, eax
0x18000974c  jns     short loc_18000976B
0x18000974e  mov     edx, 0B5Fh; void *
0x180009753  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000975a  mov     r9d, eax; char *
0x18000975d  mov     rcx, [rbp+28h]; this
0x180009761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009766  jmp     loc_180009F44
0x18000976b  mov     rcx, [rbp+arg_8]
0x18000976f  mov     rax, [rcx]
0x180009772  mov     r8d, [rsi+220h]
0x180009779  mov     edx, 0FFFh
0x18000977e  mov     rax, [rax+0B0h]
0x180009785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978a  mov     ebx, eax
0x18000978c  test    eax, eax
0x18000978e  jns     short loc_180009797
0x180009790  mov     edx, 0B60h
0x180009795  jmp     short loc_180009753
0x180009797  mov     rcx, [rbp+arg_8]
0x18000979b  mov     rax, [rcx]
0x18000979e  lea     rdx, [rsi+150h]
0x1800097a5  mov     rax, [rax+68h]
0x1800097a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ae  mov     ebx, eax
0x1800097b0  test    eax, eax
0x1800097b2  jns     short loc_1800097BB
0x1800097b4  mov     edx, 0B61h
0x1800097b9  jmp     short loc_180009753
0x1800097bb  mov     rcx, [rbp+arg_8]
0x1800097bf  mov     rax, [rcx]
0x1800097c2  lea     rdx, [rsi+160h]
0x1800097c9  mov     rax, [rax+78h]
0x1800097cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097d2  mov     ebx, eax
0x1800097d4  test    eax, eax
0x1800097d6  jns     short loc_1800097E2
0x1800097d8  mov     edx, 0B62h
0x1800097dd  jmp     loc_180009753
0x1800097e2  mov     rcx, [rbp+arg_8]
0x1800097e6  mov     rax, [rcx]
0x1800097e9  lea     rdx, [rsi+170h]
0x1800097f0  mov     rax, [rax+88h]
0x1800097f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fc  mov     ebx, eax
0x1800097fe  test    eax, eax
0x180009800  jns     short loc_18000980C
0x180009802  mov     edx, 0B63h
0x180009807  jmp     loc_180009753
0x18000980c  mov     rcx, [rbp+arg_8]
0x180009810  mov     rax, [rcx]
0x180009813  lea     rdx, [rsi+180h]
0x18000981a  mov     rax, [rax+98h]
0x180009821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009826  mov     ebx, eax
0x180009828  test    eax, eax
0x18000982a  jns     short loc_180009836
0x18000982c  mov     edx, 0B64h
0x180009831  jmp     loc_180009753
0x180009836  mov     rcx, [rbp+arg_8]
0x18000983a  mov     rax, [rcx]
0x18000983d  lea     rdx, [rsi+190h]
0x180009844  mov     rax, [rax+0E8h]
0x18000984b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009850  mov     ebx, eax
0x180009852  test    eax, eax
0x180009854  jns     short loc_18000988E
0x180009856  mov     rcx, [rbp+28h]; this
0x18000985a  mov     r9d, eax; char *
0x18000985d  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180009864  mov     edx, 0B65h; void *
0x180009869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000986e  nop
0x18000986f  mov     rcx, [rbp+arg_8]
0x180009873  test    rcx, rcx
0x180009876  jz      short loc_180009889
0x180009878  mov     [rbp+arg_8], r15
0x18000987c  mov     rax, [rcx]
0x18000987f  mov     rax, [rax+10h]
0x180009883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009888  nop
0x180009889  jmp     loc_180009F4D
0x18000988e  mov     rcx, [rbp+arg_8]
0x180009892  mov     rax, [rcx]
0x180009895  mov     rdx, [rsi+48h]
0x180009899  mov     rax, [rax+0D0h]
0x1800098a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a5  mov     ebx, eax
0x1800098a7  test    eax, eax
0x1800098a9  jns     short loc_1800098B5
0x1800098ab  mov     edx, 0B66h
0x1800098b0  jmp     loc_180009753
0x1800098b5  mov     rcx, [rbp+arg_8]
0x1800098b9  mov     rax, [rcx]
0x1800098bc  mov     rdx, [rsi+60h]
0x1800098c0  mov     rax, [rax+0E0h]
0x1800098c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cc  mov     ebx, eax
0x1800098ce  test    eax, eax
0x1800098d0  jns     short loc_1800098DC
0x1800098d2  mov     edx, 0B67h
0x1800098d7  jmp     loc_180009753
0x1800098dc  mov     rcx, [rbp+arg_8]
0x1800098e0  mov     rax, [rcx]
0x1800098e3  mov     rdx, [rsi+78h]
0x1800098e7  mov     rax, [rax+118h]
0x1800098ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f3  mov     ebx, eax
0x1800098f5  test    eax, eax
0x1800098f7  jns     short loc_180009903
0x1800098f9  mov     edx, 0B68h
0x1800098fe  jmp     loc_180009753
0x180009903  mov     rcx, [rbp+arg_8]
0x180009907  mov     rax, [rcx]
0x18000990a  lea     rdx, [rsi+1B0h]
0x180009911  mov     rax, [rax+130h]
0x180009918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991d  mov     ebx, eax
0x18000991f  test    eax, eax
0x180009921  jns     short loc_18000992D
0x180009923  mov     edx, 0B69h
0x180009928  jmp     loc_180009753
0x18000992d  mov     rcx, [rbp+arg_8]
0x180009931  mov     rax, [rcx]
0x180009934  lea     rdx, [rsi+1A0h]
0x18000993b  mov     rax, [rax+108h]
0x180009942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009947  mov     ebx, eax
0x180009949  test    eax, eax
0x18000994b  jns     short loc_180009957
0x18000994d  mov     edx, 0B6Ah
0x180009952  jmp     loc_180009753
0x180009957  mov     rcx, [rbp+arg_8]
0x18000995b  mov     rax, [rcx]
0x18000995e  lea     rdx, [rsi+1C0h]
0x180009965  mov     rax, [rax+158h]
0x18000996c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009971  mov     ebx, eax
0x180009973  test    eax, eax
0x180009975  jns     short loc_180009981
0x180009977  mov     edx, 0B6Bh
0x18000997c  jmp     loc_180009753
0x180009981  mov     rcx, [rbp+arg_8]
0x180009985  mov     rax, [rcx]
0x180009988  lea     rdx, [rsi+1E0h]
0x18000998f  mov     rax, [rax+170h]
0x180009996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999b  mov     ebx, eax
0x18000999d  test    eax, eax
0x18000999f  jns     short loc_1800099AB
0x1800099a1  mov     edx, 0B6Ch
0x1800099a6  jmp     loc_180009753
0x1800099ab  mov     rdx, [rbp+arg_8]; struct IStorageProviderInfo *
0x1800099af  mov     rcx, rsi; this
0x1800099b2  call    ?SetIconOverlayHandlerClsidArrayHelper@CStorageProviderRootsCache@@AEAAJPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::SetIconOverlayHandlerClsidArrayHelper(IStorageProviderInfo *)
0x1800099b7  mov     ebx, eax
0x1800099b9  test    eax, eax
0x1800099bb  jns     short loc_1800099C7
0x1800099bd  mov     edx, 0B6Dh
0x1800099c2  jmp     loc_180009753
0x1800099c7  mov     rdx, [rbp+arg_8]; struct IStorageProviderInfo *
0x1800099cb  mov     rcx, rsi; this
0x1800099ce  call    ?SetContextMenuVerbsHelper@CStorageProviderRootsCache@@AEAAJPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::SetContextMenuVerbsHelper(IStorageProviderInfo *)
0x1800099d3  mov     ebx, eax
0x1800099d5  test    eax, eax
0x1800099d7  jns     short loc_1800099E3
0x1800099d9  mov     edx, 0B6Eh
0x1800099de  jmp     loc_180009753
0x1800099e3  mov     [rbp+arg_10], r15
0x1800099e7  mov     rdi, [rbp+arg_8]
0x1800099eb  mov     rax, [rdi]
0x1800099ee  mov     rbx, [rax]
0x1800099f1  lea     rcx, [rbp+arg_10]
0x1800099f5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800099fa  lea     r8, [rbp+arg_10]
0x1800099fe  lea     rdx, _GUID_884abcd3_5446_45ff_9226_e95d8e2a7006
0x180009a05  mov     rcx, rdi
0x180009a08  mov     rax, rbx
0x180009a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a10  mov     ebx, eax
0x180009a12  test    eax, eax
0x180009a14  jns     short loc_180009A3D
0x180009a16  mov     edx, 0B71h; void *
0x180009a1b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180009a22  mov     r9d, eax; char *
0x180009a25  mov     rcx, [rbp+28h]; this
0x180009a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a2e  nop
0x180009a2f  lea     rcx, [rbp+arg_10]
0x180009a33  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009a38  jmp     loc_180009F44
0x180009a3d  mov     rcx, [rbp+arg_10]
0x180009a41  mov     rax, [rcx]
0x180009a44  lea     rdx, [rsi+1F0h]
0x180009a4b  mov     rax, [rax+18h]
0x180009a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a54  mov     ebx, eax
0x180009a56  test    eax, eax
0x180009a58  jns     short loc_180009A61
0x180009a5a  mov     edx, 0B72h
0x180009a5f  jmp     short loc_180009A1B
0x180009a61  mov     [rbp+arg_18], r15
0x180009a65  mov     rdi, [rbp+arg_8]
0x180009a69  mov     rax, [rdi]
0x180009a6c  mov     rbx, [rax]
0x180009a6f  lea     rcx, [rbp+arg_18]
0x180009a73  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009a78  lea     r8, [rbp+arg_18]
0x180009a7c  lea     rdx, _GUID_04a48a40_5a26_4801_8086_617eb0d17d00
0x180009a83  mov     rcx, rdi
0x180009a86  mov     rax, rbx
0x180009a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8e  mov     ebx, eax
0x180009a90  test    eax, eax
0x180009a92  jns     short loc_180009ABB
0x180009a94  mov     edx, 0B75h; void *
0x180009a99  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180009aa0  mov     r9d, eax; char *
0x180009aa3  mov     rcx, [rbp+28h]; this
0x180009aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009aac  nop
0x180009aad  lea     rcx, [rbp+arg_18]
0x180009ab1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180009ab6  jmp     loc_180009A2F
0x180009abb  mov     rcx, [rbp+arg_18]
0x180009abf  mov     rax, [rcx]
  ... truncated ...
```

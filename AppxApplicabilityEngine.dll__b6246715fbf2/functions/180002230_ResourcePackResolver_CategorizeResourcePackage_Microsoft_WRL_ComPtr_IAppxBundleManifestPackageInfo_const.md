# ResourcePackResolver::CategorizeResourcePackage(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &)

- ea: `0x180002230`
- end: `0x180002aed`
- name: `?CategorizeResourcePackage@ResourcePackResolver@@IEAAXAEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z`
- size: `2237`
- prototype: `void __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001fd0`

## callees

- `0x180001250`
- `0x180001714`
- `0x180002230`
- `0x180002af4`
- `0x180003d44`
- `0x180008f50`
- `0x18000d6f4`
- `0x18000d770`
- `0x18000db80`
- `0x18000e250`
- `0x180016888`
- `0x180016908`
- `0x180016bb0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027df`

## pseudocode

```c
void __fastcall ResourcePackResolver::CategorizeResourcePackage(_QWORD *a1, _QWORD *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int v7; // edx
  int v8; // ecx
  int v9; // ebx
  int v10; // edx
  int v11; // ecx
  int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 **); // rbx
  int v15; // edx
  int v16; // ecx
  int v17; // ebx
  int v18; // edx
  int v19; // ecx
  int v20; // ebx
  int v21; // edx
  int v22; // ecx
  int v23; // ebx
  int v24; // edx
  int v25; // ecx
  int v26; // ebx
  __int64 v27; // rax
  int v28; // edx
  int v29; // ecx
  int v30; // ebx
  LPVOID v31; // rbx
  int v32; // edx
  int v33; // ecx
  int v34; // ebx
  int v35; // eax
  int v36; // edx
  int v37; // ecx
  int v38; // ebx
  int v39; // edx
  int v40; // ecx
  int v41; // ebx
  __int64 *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rdi
  __int64 v46; // rdi
  __int64 v47; // rbx
  __int64 *v48; // r14
  unsigned int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // rbx
  __int64 v52; // rax
  int v53; // r8d
  __int64 v54; // r9
  __int64 *v55; // rdx
  __int64 v56; // rbx
  __int64 v57; // rdi
  __int64 v58; // rax
  int v59; // edx
  int v60; // ecx
  int v61; // ebx
  unsigned int v62; // r10d
  __int64 v63; // rax
  int v64; // [rsp+20h] [rbp-99h]
  __int64 *v65; // [rsp+30h] [rbp-89h] BYREF
  int v66; // [rsp+38h] [rbp-81h] BYREF
  __int64 v67; // [rsp+40h] [rbp-79h] BYREF
  int v68; // [rsp+48h] [rbp-71h] BYREF
  __int64 v69; // [rsp+50h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-61h] BYREF
  LPVOID v71; // [rsp+60h] [rbp-59h] BYREF
  __int64 v72; // [rsp+68h] [rbp-51h]
  int v73; // [rsp+70h] [rbp-49h] BYREF
  __int64 v74; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v75[8]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v76[8]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v77; // [rsp+90h] [rbp-29h]
  char v78; // [rsp+98h] [rbp-21h] BYREF
  char v79; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v80[8]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v81[16]; // [rsp+B0h] [rbp-9h] BYREF
  _BYTE v82[16]; // [rsp+C0h] [rbp+7h] BYREF
  _BYTE v83[64]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v85; // [rsp+128h] [rbp+6Fh] BYREF
  int v86; // [rsp+130h] [rbp+77h] BYREF
  LPVOID v87; // [rsp+138h] [rbp+7Fh] BYREF

  v77 = -2;
  v69 = 0;
  v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(
         *a2,
         &GUID_44c2acbc_b2cf_4ccb_bbdb_9c6da8c3bc9e,
         &v69);
  if ( v6 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
    McTemplateU0zqd_EventWriteTransfer(
      v5,
      v4,
      (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
      98,
      94);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
      (const char *)(unsigned int)v6,
      v64);
  v68 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 32LL))(v69, &v68);
  if ( v9 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
    McTemplateU0zqd_EventWriteTransfer(
      v8,
      v7,
      (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
      101,
      94);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
      (const char *)(unsigned int)v9,
      v64);
  if ( v68 )
  {
    std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
      a1 + 13,
      v75,
      a2);
  }
  else
  {
    v85 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 40LL))(v69, &v85);
    if ( v12 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v11,
        v10,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        109,
        94);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v12,
        v64);
    if ( a1[45] != a1[46] )
    {
      v65 = 0;
      v13 = *a2;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)*a2 + 32LL);
      Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(&v65);
      v17 = v14(v13, &v65);
      if ( v17 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v16,
          v15,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          115,
          94);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v17,
          v64);
      v87 = 0;
      v58 = *v65;
      v87 = 0;
      v61 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v58 + 56))(v65, &v87);
      if ( v61 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v60,
          v59,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          118,
          94);
      if ( v61 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v61,
          v64);
      v56 = a1[45];
      v57 = a1[46];
      while ( v56 != v57 )
      {
        if ( !(unsigned int)std::wstring::compare(v56, v87) )
          std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
            a1 + 17,
            v75,
            a2);
        v56 += 40;
      }
      if ( v87 )
        CoTaskMemFree(v87);
      Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(&v65);
    }
    v67 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 64LL))(*a2, &v67);
    if ( v20 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v19,
        v18,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        131,
        94);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v20,
        v64);
    v86 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 32LL))(v67, &v86);
    if ( v23 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
      McTemplateU0zqd_EventWriteTransfer(
        v22,
        v21,
        (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        134,
        94);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)v23,
        v64);
    if ( !v86 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)0x8000FFFFLL,
        v64);
    do
    {
      v65 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v67 + 24LL))(v67, &v65);
      if ( v26 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v25,
          v24,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          141,
          94);
      if ( v26 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v26,
          v64);
      pv = 0;
      v27 = *v65;
      pv = 0;
      v30 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v27 + 24))(v65, &pv);
      if ( v30 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v29,
          v28,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          144,
          94);
      if ( v30 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x90,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v30,
          v64);
      v31 = pv;
      if ( pv )
      {
        v45 = *a2;
        if ( *a2 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v45 + 8LL))(*a2);
        v71 = v31;
        v72 = v45;
        v46 = std::_Tree_val<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<unsigned short *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
                a1 + 1,
                &v71);
        v47 = a1[2];
        v48 = *(__int64 **)(v47 + 8);
        if ( *((_BYTE *)v48 + 73) )
        {
          LOBYTE(v49) = 1;
        }
        else
        {
          do
          {
            LODWORD(v47) = (_DWORD)v48;
            v49 = (unsigned int)std::wstring::compare(v46 + 24, v48 + 3) >> 31;
            if ( (_BYTE)v49 )
              v48 = (__int64 *)*v48;
            else
              v48 = (__int64 *)v48[2];
          }
          while ( !*((_BYTE *)v48 + 73) );
        }
        std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(
          (_DWORD)a1 + 8,
          (unsigned int)&v78,
          (unsigned __int8)v49,
          v47,
          v46);
        v50 = v72;
        if ( v72 )
        {
          v72 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        if ( v85 )
          std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
            a1 + 21,
            v81,
            a2);
      }
      LODWORD(v87) = 0;
      v34 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v65 + 32))(v65, &v87);
      if ( v34 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v33,
          v32,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          156,
          94);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v34,
          v64);
      v35 = (int)v87;
      if ( (_DWORD)v87 )
      {
        v51 = *a2;
        if ( *a2 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v51 + 8LL))(*a2);
          v35 = (int)v87;
        }
        v73 = v35;
        v74 = v51;
        v52 = std::_Tree_val<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
                a1 + 5,
                &v73);
        v54 = a1[6];
        v55 = *(__int64 **)(v54 + 8);
        if ( *((_BYTE *)v55 + 41) )
        {
          LOBYTE(v53) = 1;
        }
        else
        {
          v62 = *(_DWORD *)(v52 + 24);
          do
          {
            LODWORD(v54) = (_DWORD)v55;
            LOBYTE(v53) = v62 < *((_DWORD *)v55 + 6);
            if ( v62 >= *((_DWORD *)v55 + 6) )
              v55 = (__int64 *)v55[2];
            else
              v55 = (__int64 *)*v55;
          }
          while ( !*((_BYTE *)v55 + 41) );
        }
        std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(
          (_DWORD)a1 + 40,
          (unsigned int)&v79,
          v53,
          v54,
          v52);
        Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(&v74);
        if ( v85 )
          std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
            a1 + 25,
            v82,
            a2);
      }
      v66 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v65 + 40))(v65, &v66);
      if ( v38 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v37,
          v36,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          168,
          94);
      if ( v38 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v38,
          v64);
      if ( v66 )
      {
        v63 = std::make_pair<enum DX_FEATURE_LEVEL &,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
                v75,
                &v66,
                a2);
        std::multimap<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::insert<std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
          a1 + 9,
          v80,
          v63);
        Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v76);
        if ( v85 )
          std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
            a1 + 29,
            v83,
            a2);
      }
      v41 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 40LL))(v67, &v86);
      if ( v41 == -2147023266 && (Microsoft_Windows_ApplicabilityEngineEnableBits & 2) != 0 )
        McTemplateU0zqd_EventWriteTransfer(
          v40,
          v39,
          (unsigned int)L"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          179,
          94);
      if ( v41 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
          (const char *)(unsigned int)v41,
          v64);
      if ( pv )
        CoTaskMemFree(pv);
      v42 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      }
    }
    while ( v86 );
    v43 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  v44 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
}

```

## disassembly

```asm
0x180002230  push    rbp
0x180002232  push    rsi
0x180002233  push    rdi
0x180002234  push    r12
0x180002236  push    r13
0x180002238  push    r14
0x18000223a  push    r15
0x18000223c  lea     rbp, [rsp-27h]
0x180002241  sub     rsp, 0E0h
0x180002248  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x180002250  mov     [rsp+110h+arg_0], rbx
0x180002258  mov     r12, rdx
0x18000225b  mov     r13, rcx
0x18000225e  xor     esi, esi
0x180002260  mov     [rbp+57h+var_C0], rsi
0x180002264  mov     rcx, [rdx]
0x180002267  mov     rax, [rcx]
0x18000226a  lea     r8, [rbp+57h+var_C0]
0x18000226e  lea     rdx, _GUID_44c2acbc_b2cf_4ccb_bbdb_9c6da8c3bc9e
0x180002275  mov     rax, [rax]
0x180002278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227d  mov     ebx, eax
0x18000227f  cmp     eax, 8007065Eh
0x180002284  jz      loc_1800027FF
0x18000228a  mov     rcx, [rbp+5Fh]; this
0x18000228e  test    ebx, ebx
0x180002290  js      loc_18000274A
0x180002296  mov     [rbp+57h+var_C8], esi
0x180002299  mov     rcx, [rbp+57h+var_C0]
0x18000229d  mov     rax, [rcx]
0x1800022a0  lea     rdx, [rbp+57h+var_C8]
0x1800022a4  mov     rax, [rax+20h]
0x1800022a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ad  mov     ebx, eax
0x1800022af  cmp     eax, 8007065Eh
0x1800022b4  jz      loc_18000282B
0x1800022ba  mov     rcx, [rbp+5Fh]; this
0x1800022be  test    ebx, ebx
0x1800022c0  js      loc_18000275F
0x1800022c6  cmp     [rbp+57h+var_C8], 0
0x1800022ca  jnz     loc_1800026CC
0x1800022d0  mov     [rbp+57h+arg_8], esi
0x1800022d3  mov     rcx, [rbp+57h+var_C0]
0x1800022d7  mov     rax, [rcx]
0x1800022da  lea     rdx, [rbp+57h+arg_8]
0x1800022de  mov     rax, [rax+28h]
0x1800022e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e7  mov     ebx, eax
0x1800022e9  cmp     eax, 8007065Eh
0x1800022ee  jz      loc_180002857
0x1800022f4  mov     rcx, [rbp+5Fh]; this
0x1800022f8  test    ebx, ebx
0x1800022fa  js      loc_180002774
0x180002300  mov     rax, [r13+170h]
0x180002307  cmp     [r13+168h], rax
0x18000230e  jz      short loc_18000238D
0x180002310  mov     [rsp+110h+var_E0], rsi
0x180002315  mov     rdi, [r12]
0x180002319  mov     rax, [rdi]
0x18000231c  mov     rbx, [rax+20h]
0x180002320  lea     rcx, [rsp+110h+var_E0]
0x180002325  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x18000232a  lea     rdx, [rsp+110h+var_E0]
0x18000232f  mov     rcx, rdi
0x180002332  mov     rax, rbx
0x180002335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233a  mov     ebx, eax
0x18000233c  cmp     eax, 8007065Eh
0x180002341  jnz     short loc_180002362
0x180002343  test    cs:Microsoft_Windows_ApplicabilityEngineEnableBits, 2
0x18000234a  jz      short loc_180002362
0x18000234c  mov     [rsp+110h+var_F0], eax; int
0x180002350  mov     r9d, 73h ; 's'
0x180002356  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000235d  call    McTemplateU0zqd_EventWriteTransfer
0x180002362  mov     rcx, [rbp+5Fh]; this
0x180002366  test    ebx, ebx
0x180002368  jns     loc_180002883
0x18000236e  mov     r9d, ebx; char *
0x180002371  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180002378  mov     edx, 73h ; 's'; void *
0x18000237d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180002383  lea     rcx, [rsp+110h+var_E0]
0x180002388  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x18000238d  mov     [rbp+57h+var_D0], rsi
0x180002391  mov     rcx, [r12]
0x180002395  mov     rax, [rcx]
0x180002398  lea     rdx, [rbp+57h+var_D0]
0x18000239c  mov     rax, [rax+40h]
0x1800023a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a5  mov     ebx, eax
0x1800023a7  cmp     eax, 8007065Eh
0x1800023ac  jz      loc_180002901
0x1800023b2  mov     rcx, [rbp+5Fh]; this
0x1800023b6  test    ebx, ebx
0x1800023b8  js      loc_180002789
0x1800023be  mov     [rbp+57h+arg_10], esi
0x1800023c1  mov     rcx, [rbp+57h+var_D0]
0x1800023c5  mov     rax, [rcx]
0x1800023c8  lea     rdx, [rbp+57h+arg_10]
0x1800023cc  mov     rax, [rax+20h]
0x1800023d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d5  mov     ebx, eax
0x1800023d7  cmp     eax, 8007065Eh
0x1800023dc  jz      loc_18000292D
0x1800023e2  mov     rcx, [rbp+5Fh]; this
0x1800023e6  test    ebx, ebx
0x1800023e8  js      loc_18000279E
0x1800023ee  mov     edx, [rbp+57h+arg_10]
0x1800023f1  test    edx, edx
0x1800023f3  setnz   al
0x1800023f6  mov     rcx, [rbp+5Fh]; this
0x1800023fa  test    al, al
0x1800023fc  jz      loc_180002959
0x180002402  test    edx, edx
0x180002404  jz      loc_18000255D
0x18000240a  mov     [rsp+110h+var_E0], rsi
0x18000240f  mov     rcx, [rbp+57h+var_D0]
0x180002413  mov     rax, [rcx]
0x180002416  lea     rdx, [rsp+110h+var_E0]
0x18000241b  mov     rax, [rax+18h]
0x18000241f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002424  mov     ebx, eax
0x180002426  cmp     eax, 8007065Eh
0x18000242b  jz      loc_180002971
0x180002431  mov     rcx, [rbp+5Fh]; this
0x180002435  test    ebx, ebx
0x180002437  js      loc_180002735
0x18000243d  mov     [rbp+57h+pv], rsi
0x180002441  mov     rcx, [rsp+110h+var_E0]
0x180002446  mov     rax, [rcx]
0x180002449  mov     [rbp+57h+pv], rsi
0x18000244d  lea     rdx, [rbp+57h+pv]
0x180002451  mov     rax, [rax+18h]
0x180002455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245a  mov     ebx, eax
0x18000245c  cmp     eax, 8007065Eh
0x180002461  jz      loc_18000299D
0x180002467  mov     rcx, [rbp+5Fh]; this
0x18000246b  test    ebx, ebx
0x18000246d  js      loc_180002720
0x180002473  mov     rbx, [rbp+57h+pv]
0x180002477  test    rbx, rbx
0x18000247a  jnz     loc_1800025AC
0x180002480  mov     dword ptr [rbp+57h+arg_18], esi
0x180002483  mov     rcx, [rsp+110h+var_E0]
0x180002488  mov     rax, [rcx]
0x18000248b  lea     rdx, [rbp+57h+arg_18]
0x18000248f  mov     rax, [rax+20h]
0x180002493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002498  mov     ebx, eax
0x18000249a  cmp     eax, 8007065Eh
0x18000249f  jz      loc_1800029F5
0x1800024a5  mov     rcx, [rbp+5Fh]; this
0x1800024a9  test    ebx, ebx
0x1800024ab  js      loc_18000270B
0x1800024b1  mov     eax, dword ptr [rbp+57h+arg_18]
0x1800024b4  test    eax, eax
0x1800024b6  jnz     loc_18000264A
0x1800024bc  mov     [rsp+110h+var_D8], esi
0x1800024c0  mov     rcx, [rsp+110h+var_E0]
0x1800024c5  mov     rax, [rcx]
0x1800024c8  lea     rdx, [rsp+110h+var_D8]
0x1800024cd  mov     rax, [rax+28h]
0x1800024d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d6  mov     ebx, eax
0x1800024d8  cmp     eax, 8007065Eh
0x1800024dd  jz      loc_180002A46
0x1800024e3  mov     rcx, [rbp+5Fh]; this
0x1800024e7  test    ebx, ebx
0x1800024e9  js      loc_1800026F6
0x1800024ef  cmp     [rsp+110h+var_D8], 0
0x1800024f4  jnz     loc_180002A72
0x1800024fa  mov     rcx, [rbp+57h+var_D0]
0x1800024fe  mov     rax, [rcx]
0x180002501  lea     rdx, [rbp+57h+arg_10]
0x180002505  mov     rax, [rax+28h]
0x180002509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000250e  mov     ebx, eax
0x180002510  cmp     eax, 8007065Eh
0x180002515  jz      loc_180002AC0
0x18000251b  mov     rcx, [rbp+5Fh]; this
0x18000251f  test    ebx, ebx
0x180002521  js      loc_1800026E1
0x180002527  mov     rcx, [rbp+57h+pv]; pv
0x18000252b  test    rcx, rcx
0x18000252e  jz      short loc_180002537
0x180002530  call    cs:__imp_CoTaskMemFree
0x180002536  nop
0x180002537  mov     rcx, [rsp+110h+var_E0]
0x18000253c  test    rcx, rcx
0x18000253f  jz      short loc_180002553
0x180002541  mov     [rsp+110h+var_E0], rsi
0x180002546  mov     rax, [rcx]
0x180002549  mov     rax, [rax+10h]
0x18000254d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002552  nop
0x180002553  cmp     [rbp+57h+arg_10], 0
0x180002557  jnz     loc_18000240A
0x18000255d  mov     rcx, [rbp+57h+var_D0]
0x180002561  test    rcx, rcx
0x180002564  jz      short loc_180002577
0x180002566  mov     [rbp+57h+var_D0], rsi
0x18000256a  mov     rax, [rcx]
0x18000256d  mov     rax, [rax+10h]
0x180002571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002576  nop
0x180002577  mov     rcx, [rbp+57h+var_C0]
0x18000257b  test    rcx, rcx
0x18000257e  jz      short loc_180002591
0x180002580  mov     [rbp+57h+var_C0], rsi
0x180002584  mov     rax, [rcx]
0x180002587  mov     rax, [rax+10h]
0x18000258b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002590  nop
0x180002591  mov     rbx, [rsp+110h+arg_0]
0x180002599  add     rsp, 0E0h
0x1800025a0  pop     r15
0x1800025a2  pop     r14
0x1800025a4  pop     r13
0x1800025a6  pop     r12
0x1800025a8  pop     rdi
0x1800025a9  pop     rsi
0x1800025aa  pop     rbp
0x1800025ab  retn
0x1800025ac  mov     rdi, [r12]
0x1800025b0  test    rdi, rdi
0x1800025b3  jz      short loc_1800025C5
0x1800025b5  mov     rax, [rdi]
0x1800025b8  mov     rcx, rdi
0x1800025bb  mov     rax, [rax+8]
0x1800025bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c4  nop
0x1800025c5  mov     [rbp+57h+var_B0], rbx
0x1800025c9  mov     [rbp+57h+var_A8], rdi
0x1800025cd  lea     rdx, [rbp+57h+var_B0]
0x1800025d1  lea     rcx, [r13+8]
0x1800025d5  call    ??$_Buynode@U?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@1@$$QEAU?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z; std::_Tree_val<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)
0x1800025da  mov     rdi, rax
0x1800025dd  mov     rbx, [r13+10h]
0x1800025e1  mov     r14, [rbx+8]
0x1800025e5  cmp     byte ptr [r14+49h], 0
0x1800025ea  jz      loc_1800029C9
0x1800025f0  mov     al, 1
0x1800025f2  mov     qword ptr [rsp+110h+var_F0], rdi
0x1800025f7  mov     r9, rbx
0x1800025fa  movzx   r8d, al
0x1800025fe  lea     rdx, [rbp+57h+var_78]
0x180002602  lea     rcx, [r13+8]
0x180002606  call    ?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@1@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *,std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x18000260b  nop
0x18000260c  mov     rcx, [rbp+57h+var_A8]
0x180002610  xor     esi, esi
0x180002612  test    rcx, rcx
0x180002615  jz      short loc_180002628
0x180002617  mov     [rbp+57h+var_A8], rsi
0x18000261b  mov     rax, [rcx]
0x18000261e  mov     rax, [rax+10h]
0x180002622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002627  nop
0x180002628  cmp     [rbp+57h+arg_8], 0
0x18000262c  jz      loc_180002480
0x180002632  lea     rcx, [r13+0A8h]
0x180002639  mov     r8, r12
0x18000263c  lea     rdx, [rbp+57h+var_60]
0x180002640  call    ?insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@std@@_N@2@AEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@_N@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &,bool)
0x180002645  jmp     loc_180002480
0x18000264a  mov     rbx, [r12]
0x18000264e  test    rbx, rbx
0x180002651  jz      short loc_180002665
0x180002653  mov     rax, [rbx]
0x180002656  mov     rcx, rbx
0x180002659  mov     rax, [rax+8]
0x18000265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002662  mov     eax, dword ptr [rbp+57h+arg_18]
0x180002665  mov     [rbp+57h+var_A0], eax
0x180002668  mov     [rbp+57h+var_98], rbx
0x18000266c  lea     rdx, [rbp+57h+var_A0]
0x180002670  lea     rcx, [r13+28h]
0x180002674  call    ??$_Buynode@U?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@1@$$QEAU?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z; std::_Tree_val<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Buynode<std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)
0x180002679  mov     r9, [r13+30h]
0x18000267d  mov     rdx, [r9+8]
0x180002681  cmp     byte ptr [rdx+29h], 0
0x180002685  jz      loc_180002A21
0x18000268b  mov     r8b, 1
0x18000268e  mov     qword ptr [rsp+110h+var_F0], rax
0x180002693  lea     rdx, [rbp+57h+var_70]
0x180002697  lea     rcx, [r13+28h]
0x18000269b  call    ?_Insert@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@1@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x1800026a0  nop
0x1800026a1  lea     rcx, [rbp+57h+var_98]
0x1800026a5  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x1800026aa  cmp     [rbp+57h+arg_8], 0
0x1800026ae  jz      loc_1800024BC
0x1800026b4  lea     rcx, [r13+0C8h]
0x1800026bb  mov     r8, r12
0x1800026be  lea     rdx, [rbp+57h+var_50]
0x1800026c2  call    ?insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@std@@_N@2@AEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@_N@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &,bool)
0x1800026c7  jmp     loc_1800024BC
0x1800026cc  lea     rcx, [r13+68h]
  ... truncated ...
```

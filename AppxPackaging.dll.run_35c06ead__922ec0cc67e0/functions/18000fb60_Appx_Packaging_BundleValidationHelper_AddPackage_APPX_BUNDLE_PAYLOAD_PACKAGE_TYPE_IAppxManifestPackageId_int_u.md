# Appx::Packaging::BundleValidationHelper::AddPackage(APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE,IAppxManifestPackageId *,int,ushort const *)

- ea: `0x18000fb60`
- end: `0x18001044d`
- name: `?AddPackage@BundleValidationHelper@Packaging@Appx@@QEAAJW4APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE@@PEAUIAppxManifestPackageId@@HPEBG@Z`
- size: `2285`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleValidationHelper *__hidden this, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE, struct IAppxManifestPackageId *, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d010`
- `0x180075c34`
- `0x1800f3498`
- `0x1800f3a7c`

## callees

- `0x180005db0`
- `0x180005eb8`
- `0x18000f3b0`
- `0x18000fb60`
- `0x180011710`
- `0x1800133fc`
- `0x18004d518`
- `0x18004fc4c`
- `0x180071f50`
- `0x180096a00`
- `0x180096b04`
- `0x1800992c4`
- `0x1800992d0`
- `0x1800c9aac`
- `0x1800cb3f8`
- `0x180106010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000fd6e`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000fd6e`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000fd9f`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000fec6`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000fd9f`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000fec6`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000fe59`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000fe8a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000fe59`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000fe8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001034a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010409`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fdfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001034a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010409`

## string_xrefs

- `0x1800102c3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180010434`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleValidationHelper::AddPackage(
        Appx::Packaging::BundleValidationHelper *this,
        enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE a2,
        struct IAppxManifestPackageId *a3,
        int a4,
        const unsigned __int16 *a5)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 *v9; // rax
  __int64 *v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rsi
  int v14; // r14d
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rax
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  ULONG v23; // eax
  void *v24; // rbx
  int v25; // ecx
  struct IAppxManifestPackageIdVtbl *lpVtbl; // rax
  int v27; // eax
  unsigned int v28; // edx
  Appx::Packaging::PackageNameInfo *v29; // rcx
  __int64 v30; // rcx
  int v31; // esi
  __int64 v32; // rbx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  int v35; // ecx
  struct _RTL_AVL_TABLE *v36; // rbx
  _QWORD *v37; // rax
  int v38; // ebx
  __int64 v39; // rdx
  unsigned int v40; // edx
  Appx::Packaging::PackageNameInfo *v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  unsigned int v44; // edx
  __int64 v45; // rcx
  unsigned int v46; // edx
  __int64 v47; // rcx
  int v48; // ecx
  __int64 v49; // rcx
  int v50; // eax
  __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rdx
  unsigned int v54; // edx
  const unsigned __int16 **v55; // rsi
  __int64 v56; // rdx
  unsigned int v57; // edx
  unsigned int v58; // edx
  int v59; // [rsp+28h] [rbp-31h]
  int v60; // [rsp+28h] [rbp-31h]
  int v61; // [rsp+28h] [rbp-31h]
  __int64 v62; // [rsp+38h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-19h] BYREF
  Appx::Packaging::PackageNameInfo *v64; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v65; // [rsp+50h] [rbp-9h]
  __int128 Buffer; // [rsp+58h] [rbp-1h] BYREF
  int v67; // [rsp+68h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+57h]
  unsigned int NewElement; // [rsp+B8h] [rbp+5Fh] BYREF
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE v70; // [rsp+C0h] [rbp+67h]
  int v71; // [rsp+D0h] [rbp+77h]

  v71 = a4;
  v70 = a2;
  if ( *((_DWORD *)this + 62) >= 0x2710u )
  {
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0q_EventWriteTransfer(this, &EVENT_BUNDLE_VALIDATION_TOO_MANY_PACKAGES, 2147483659LL);
    AppxPackagingLog(&EVENT_BUNDLE_VALIDATION_TOO_MANY_PACKAGES, 0xB00000B3, -2147483637);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
      (const char *)0x8000000BLL,
      v59);
    return 2147483659LL;
  }
  v62 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
  v7 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
         a3,
         &GUID_2256999d_d617_42f1_880e_0ba4542319d5,
         &v62);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
      (const char *)(unsigned int)v7,
      v59);
    v51 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    return v8;
  }
  v9 = (__int64 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
      (const char *)0x8007000ELL,
      v59);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    return 2147942414LL;
  }
  v9[2] = 0;
  v64 = (Appx::Packaging::PackageNameInfo *)v9;
  *(_OWORD *)v9 = 0;
  v9[3] = 0;
  v65 = v9 + 3;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 72LL))(v62);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
      (const char *)(unsigned int)v11,
      v59);
    Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v54);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    return v12;
  }
  v13 = a5;
  v14 = -2147024809;
  if ( !a5 )
  {
    Common::StringBuffer::Clear((Common::StringBuffer *)v10);
    goto LABEL_11;
  }
  v15 = 1073741822;
  v16 = a5;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v17 = -2147024809;
  if ( !v15 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      v59);
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
      (const char *)v17,
      v59);
    Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v46);
    v47 = v62;
    if ( v62 )
    {
      v62 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      return v17;
    }
    return v17;
  }
  v17 = Common::StringBuffer::SetValue((Common::StringBuffer *)v10, a5, 1073741822 - (int)v15);
  if ( (v17 & 0x80000000) != 0 )
    goto LABEL_58;
LABEL_11:
  if ( !*(_QWORD *)this )
    goto LABEL_26;
  v67 = 0;
  Buffer = 0;
  if ( v13 )
  {
    v18 = 1073741822;
    v19 = v13;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( !v18 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        v59);
      goto LABEL_18;
    }
    v14 = Common::StringBuffer::SetValue((Common::StringBuffer *)&Buffer, v13, 1073741822 - (int)v18);
    if ( v14 < 0 )
    {
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
        (const char *)(unsigned int)v14,
        v59);
      if ( *((_QWORD *)&Buffer + 1) )
        operator delete(*((void **)&Buffer + 1), v20);
      Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v20);
      v21 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      return (unsigned int)v14;
    }
    if ( (_DWORD)Buffer )
    {
      v23 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)this);
      v24 = (void *)*((_QWORD *)&Buffer + 1);
      *(_QWORD *)&Buffer = *((_QWORD *)&Buffer + 1);
      LOBYTE(NewElement) = 0;
      *((_QWORD *)&Buffer + 1) = v23 + 1;
      if ( !RtlInsertElementGenericTableAvl(*(PRTL_AVL_TABLE *)this, &Buffer, 0x10u, (PBOOLEAN)&NewElement)
        || !(_BYTE)NewElement )
      {
        v55 = (const unsigned __int16 **)v65;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dzz_EventWriteTransfer(
            v25,
            (unsigned int)&EVENT_BUNDLE_VALIDATION_DUPLICATE_FILENAME,
            -2146958844,
            v10[1],
            *v65);
        AppxPackagingLog(
          &EVENT_BUNDLE_VALIDATION_DUPLICATE_FILENAME,
          0xB0000188,
          -2146958844,
          (const unsigned __int16 *)v10[1],
          *v55);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
          (const char *)0x80080204LL,
          v60);
        if ( v24 )
          operator delete(v24, v53);
        goto LABEL_78;
      }
LABEL_26:
      lpVtbl = a3->lpVtbl;
      pv = 0;
      v27 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, LPVOID *))lpVtbl->GetPackageFullName)(a3, &pv);
      v17 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
          (const char *)(unsigned int)v27,
          v59);
        CoTaskMemFree(pv);
        v29 = (Appx::Packaging::PackageNameInfo *)v10;
        goto LABEL_28;
      }
      v31 = v71;
      v32 = 8;
      Buffer = (unsigned __int64)pv;
      v33 = 128;
      if ( !v71 )
      {
        v32 = 128;
        v33 = 8;
      }
      v34 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + v33), &Buffer);
      if ( v34 && v34[1] )
      {
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dzz_EventWriteTransfer(
            v35,
            (unsigned int)&EVENT_BUNDLE_VALIDATION_DUPLICATE_PACKAGE_FULL_NAME,
            -2146958844,
            v10[1],
            v10[3]);
        AppxPackagingLog(
          &EVENT_BUNDLE_VALIDATION_DUPLICATE_PACKAGE_FULL_NAME,
          0xB00001AE,
          -2146958844,
          (const unsigned __int16 *)v10[1],
          (const unsigned __int16 *)v10[3]);
        v56 = 82;
      }
      else
      {
        v36 = (struct _RTL_AVL_TABLE *)((char *)this + v32);
        Buffer = (unsigned __int64)pv;
        v37 = RtlLookupElementGenericTableAvl(v36, &Buffer);
        if ( !v37 || !v37[1] )
        {
          *(_QWORD *)&Buffer = pv;
          *((_QWORD *)&Buffer + 1) = pv;
          LOBYTE(NewElement) = 0;
          if ( !RtlInsertElementGenericTableAvl(v36, &Buffer, 0x10u, (PBOOLEAN)&NewElement) )
          {
            v38 = -2147024882;
LABEL_40:
            v39 = 86;
LABEL_41:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v39,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
              (const char *)(unsigned int)v38,
              v59);
            CoTaskMemFree(pv);
            v41 = (Appx::Packaging::PackageNameInfo *)v10;
LABEL_42:
            Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(v41, v40);
LABEL_43:
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
            return (unsigned int)v38;
          }
          if ( !(_BYTE)NewElement )
          {
            v38 = -2147024198;
            goto LABEL_40;
          }
          pv = 0;
        }
        if ( v70 )
        {
          if ( v70 != APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE_RESOURCE )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x78,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
              (const char *)0x80080200LL,
              v59);
            CoTaskMemFree(pv);
            Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v58);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
            return 2148008448LL;
          }
          v42 = 256;
          if ( !v31 )
            v42 = 584;
          v43 = Appx::Packaging::BundleValidationPackageSet::ValidateResourcePackage((char *)this + v42, v62, &v64);
          v38 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x73,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
              (const char *)(unsigned int)v43,
              v59);
            CoTaskMemFree(pv);
            v41 = v64;
            if ( !v64 )
              goto LABEL_43;
            goto LABEL_42;
          }
          goto LABEL_51;
        }
        NewElement = 0;
        v38 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v62 + 88LL))(v62, &NewElement);
        if ( v38 < 0 )
        {
          v39 = 93;
          goto LABEL_41;
        }
        if ( NewElement != 0xFFFF )
        {
          v49 = 256;
          if ( !v31 )
            v49 = 584;
          v50 = Appx::Packaging::BundleValidationPackageSet::ValidateApplicationPackage(
                  (char *)this + v49,
                  NewElement,
                  &v64);
          v17 = v50;
          if ( v50 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
              (const char *)(unsigned int)v50,
              v59);
            CoTaskMemFree(pv);
            v29 = v64;
            if ( !v64 )
            {
LABEL_29:
              v30 = v62;
              if ( v62 )
              {
                v62 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
              return v17;
            }
LABEL_28:
            Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(v29, v28);
            goto LABEL_29;
          }
LABEL_51:
          ++*((_DWORD *)this + 62);
          if ( v31 )
            *((_BYTE *)this + 252) = 1;
          CoTaskMemFree(pv);
          if ( v64 )
            Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(v64, v44);
          v45 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          }
          return 0;
        }
        if ( *((_BYTE *)this + 253) )
        {
          CoTaskMemFree(pv);
          Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v57);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
          return 0;
        }
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dzz_EventWriteTransfer(
            v48,
            (unsigned int)&EVENT_BUNDLE_VALIDATION_UNKNOWN_ARCHITECTURE,
            -2146958844,
            v10[1],
            v10[3]);
        AppxPackagingLog(
          &EVENT_BUNDLE_VALIDATION_UNKNOWN_ARCHITECTURE,
          0xB00000EB,
          -2146958844,
          (const unsigned __int16 *)v10[1],
          (const unsigned __int16 *)v10[3]);
        v56 = 107;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v56,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
        (const char *)0x80080204LL,
        v61);
      CoTaskMemFree(pv);
LABEL_78:
      Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v53);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      return 2148008452LL;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationhelper.cpp",
    (const char *)0x8007007BLL,
    v59);
  if ( *((_QWORD *)&Buffer + 1) )
    operator delete(*((void **)&Buffer + 1), v52);
  Appx::Packaging::PackageNameInfo::`scalar deleting destructor'((Appx::Packaging::PackageNameInfo *)v10, v52);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
  return 2147942523LL;
}

```

## disassembly

```asm
0x18000fb60  mov     rax, rsp
0x18000fb63  mov     [rax+20h], r9d
0x18000fb67  mov     [rax+10h], edx
0x18000fb6a  push    rbp
0x18000fb6b  push    r12
0x18000fb6d  push    r13
0x18000fb6f  lea     rbp, [rax-57h]
0x18000fb73  sub     rsp, 90h
0x18000fb7a  cmp     dword ptr [rcx+0F8h], 2710h
0x18000fb84  mov     r13, r8
0x18000fb87  mov     r12, rcx
0x18000fb8a  jnb     loc_180010204
0x18000fb90  mov     [rax+18h], rbx
0x18000fb94  lea     rcx, [rbp+4Fh+var_70]
0x18000fb98  mov     [rax-20h], rsi
0x18000fb9c  xor     esi, esi
0x18000fb9e  mov     [rbp+4Fh+var_70], rsi
0x18000fba2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000fba7  mov     rax, [r13+0]
0x18000fbab  lea     r8, [rbp+4Fh+var_70]
0x18000fbaf  lea     rdx, _GUID_2256999d_d617_42f1_880e_0ba4542319d5
0x18000fbb6  mov     rcx, r13
0x18000fbb9  mov     rax, [rax]
0x18000fbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc1  mov     ebx, eax
0x18000fbc3  test    eax, eax
0x18000fbc5  js      loc_1800100DB
0x18000fbcb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fbd2  mov     [rsp+0A0h+var_20], rdi
0x18000fbda  mov     ecx, 20h ; ' '; unsigned __int64
0x18000fbdf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fbe4  mov     rdi, rax
0x18000fbe7  test    rax, rax
0x18000fbea  jz      loc_18000FFFC
0x18000fbf0  mov     [rax+10h], rsi
0x18000fbf4  lea     rdx, [rax+18h]
0x18000fbf8  mov     [rbp+4Fh+var_60], rax
0x18000fbfc  xorps   xmm0, xmm0
0x18000fbff  movups  xmmword ptr [rax], xmm0
0x18000fc02  mov     [rax+18h], rsi
0x18000fc06  mov     rcx, [rbp+4Fh+var_70]
0x18000fc0a  mov     [rbp+4Fh+var_58], rdx
0x18000fc0e  mov     rax, [rcx]
0x18000fc11  mov     rax, [rax+48h]
0x18000fc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc1a  mov     ebx, eax
0x18000fc1c  test    eax, eax
0x18000fc1e  js      loc_18001025B
0x18000fc24  mov     rsi, [rbp+4Fh+arg_20]
0x18000fc28  mov     [rsp+0A0h+var_28], r14
0x18000fc2d  mov     r14d, 80070057h
0x18000fc33  mov     [rsp+0A0h+var_30], r15
0x18000fc38  mov     r15d, 3FFFFFFEh
0x18000fc3e  test    rsi, rsi
0x18000fc41  jz      loc_180010113
0x18000fc47  mov     ecx, r15d
0x18000fc4a  mov     rax, rsi
0x18000fc4d  nop     dword ptr [rax]
0x18000fc50  cmp     word ptr [rax], 0
0x18000fc54  jz      short loc_18000FC60
0x18000fc56  add     rax, 2
0x18000fc5a  sub     rcx, 1
0x18000fc5e  jnz     short loc_18000FC50
0x18000fc60  xor     eax, eax
0x18000fc62  mov     ebx, r14d
0x18000fc65  test    rcx, rcx
0x18000fc68  cmovnz  ebx, eax
0x18000fc6b  jz      loc_180010430
0x18000fc71  mov     r8d, r15d
0x18000fc74  mov     rdx, rsi; Src
0x18000fc77  sub     r8d, ecx; unsigned int
0x18000fc7a  mov     rcx, rdi; this
0x18000fc7d  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18000fc82  mov     ebx, eax
0x18000fc84  test    eax, eax
0x18000fc86  js      loc_18000FFB4
0x18000fc8c  cmp     qword ptr [r12], 0
0x18000fc91  jz      loc_18000FDBE
0x18000fc97  xor     ebx, ebx
0x18000fc99  xorps   xmm0, xmm0
0x18000fc9c  mov     [rbp+4Fh+var_40], ebx
0x18000fc9f  movups  [rbp+4Fh+Buffer], xmm0
0x18000fca3  test    rsi, rsi
0x18000fca6  jz      loc_180010120
0x18000fcac  mov     rcx, r15
0x18000fcaf  mov     rax, rsi
0x18000fcb2  cmp     [rax], bx
0x18000fcb5  jz      short loc_18000FCC1
0x18000fcb7  add     rax, 2
0x18000fcbb  sub     rcx, 1
0x18000fcbf  jnz     short loc_18000FCB2
0x18000fcc1  test    rcx, rcx
0x18000fcc4  cmovnz  r14d, ebx
0x18000fcc8  jz      loc_1800102BF
0x18000fcce  sub     r15d, ecx
0x18000fcd1  mov     rdx, rsi; Src
0x18000fcd4  mov     r8d, r15d; unsigned int
0x18000fcd7  lea     rcx, [rbp+4Fh+Buffer]; this
0x18000fcdb  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18000fce0  mov     r14d, eax
0x18000fce3  test    eax, eax
0x18000fce5  jns     short loc_18000FD61
0x18000fce7  mov     rcx, [rbp+57h]; this
0x18000fceb  lea     r8, aOnecorePrintsc_109; "onecore\\printscan\\appxpackaging\\lib"...
0x18000fcf2  mov     r9d, r14d; char *
0x18000fcf5  mov     edx, 3Ch ; '<'; void *
0x18000fcfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcff  mov     rcx, qword ptr [rbp+4Fh+Buffer+8]; void *
0x18000fd03  test    rcx, rcx
0x18000fd06  jz      short loc_18000FD0D
0x18000fd08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fd0d  mov     rcx, rdi; this
0x18000fd10  call    ??_GPackageNameInfo@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(uint)
0x18000fd15  mov     rcx, [rbp+4Fh+var_70]
0x18000fd19  test    rcx, rcx
0x18000fd1c  jz      short loc_18000FD2E
0x18000fd1e  mov     [rbp+4Fh+var_70], rbx
0x18000fd22  mov     rdx, [rcx]
0x18000fd25  mov     rax, [rdx+10h]
0x18000fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd2e  mov     eax, r14d
0x18000fd31  mov     r14, [rsp+0A0h+var_28]
0x18000fd36  mov     r15, [rsp+0A0h+var_30]
0x18000fd3b  mov     rdi, [rsp+0A0h+var_20]
0x18000fd43  mov     rbx, [rsp+0A0h+arg_10]
0x18000fd4b  mov     rsi, [rsp+88h]
0x18000fd53  add     rsp, 90h
0x18000fd5a  pop     r13
0x18000fd5c  pop     r12
0x18000fd5e  pop     rbp
0x18000fd5f  retn
0x18000fd61  cmp     dword ptr [rbp+4Fh+Buffer], ebx
0x18000fd64  jbe     loc_180010120
0x18000fd6a  mov     rcx, [r12]; Table
0x18000fd6e  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18000fd75  nop     dword ptr [rax+rax+00h]
0x18000fd7a  mov     rbx, qword ptr [rbp+4Fh+Buffer+8]
0x18000fd7e  lea     r9, [rbp+4Fh+NewElement]; NewElement
0x18000fd82  mov     r8d, 10h; BufferSize
0x18000fd88  mov     qword ptr [rbp+4Fh+Buffer], rbx
0x18000fd8c  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18000fd90  mov     byte ptr [rbp+4Fh+NewElement], 0
0x18000fd94  lea     ecx, [rax+1]
0x18000fd97  mov     qword ptr [rbp+4Fh+Buffer+8], rcx
0x18000fd9b  mov     rcx, [r12]; Table
0x18000fd9f  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18000fda6  nop     dword ptr [rax+rax+00h]
0x18000fdab  test    rax, rax
0x18000fdae  jz      loc_18001028B
0x18000fdb4  cmp     byte ptr [rbp+4Fh+NewElement], 0
0x18000fdb8  jz      loc_18001028B
0x18000fdbe  mov     rax, [r13+0]
0x18000fdc2  lea     rdx, [rbp+4Fh+pv]
0x18000fdc6  xor     r14d, r14d
0x18000fdc9  mov     rcx, r13
0x18000fdcc  mov     [rbp+4Fh+pv], r14
0x18000fdd0  mov     rax, [rax+48h]
0x18000fdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd9  mov     ebx, eax
0x18000fddb  test    eax, eax
0x18000fddd  jns     short loc_18000FE2F
0x18000fddf  mov     rcx, [rbp+57h]; this
0x18000fde3  lea     r8, aOnecorePrintsc_109; "onecore\\printscan\\appxpackaging\\lib"...
0x18000fdea  mov     r9d, eax; char *
0x18000fded  mov     edx, 4Bh ; 'K'; void *
0x18000fdf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fdf7  mov     rcx, [rbp+4Fh+pv]; pv
0x18000fdfb  call    cs:__imp_CoTaskMemFree
0x18000fe02  nop     dword ptr [rax+rax+00h]
0x18000fe07  mov     rcx, rdi; this
0x18000fe0a  call    ??_GPackageNameInfo@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(uint)
0x18000fe0f  mov     rcx, [rbp+4Fh+var_70]
0x18000fe13  test    rcx, rcx
0x18000fe16  jz      short loc_18000FE28
0x18000fe18  mov     [rbp+4Fh+var_70], r14
0x18000fe1c  mov     rax, [rcx]
0x18000fe1f  mov     rax, [rax+10h]
0x18000fe23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe28  mov     eax, ebx
0x18000fe2a  jmp     loc_18000FD31
0x18000fe2f  mov     rax, [rbp+4Fh+pv]
0x18000fe33  mov     edx, 8
0x18000fe38  mov     esi, [rbp+4Fh+arg_18]
0x18000fe3b  mov     ebx, edx
0x18000fe3d  test    esi, esi
0x18000fe3f  mov     qword ptr [rbp+4Fh+Buffer], rax
0x18000fe43  mov     ecx, 80h
0x18000fe48  mov     qword ptr [rbp+4Fh+Buffer+8], r14
0x18000fe4c  cmovz   ebx, ecx
0x18000fe4f  cmovz   ecx, edx
0x18000fe52  add     rcx, r12; Table
0x18000fe55  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18000fe59  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000fe60  nop     dword ptr [rax+rax+00h]
0x18000fe65  test    rax, rax
0x18000fe68  jz      short loc_18000FE74
0x18000fe6a  cmp     [rax+8], r14
0x18000fe6e  jnz     loc_1800102DC
0x18000fe74  mov     rax, [rbp+4Fh+pv]
0x18000fe78  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18000fe7c  add     rbx, r12
0x18000fe7f  mov     qword ptr [rbp+4Fh+Buffer], rax
0x18000fe83  mov     rcx, rbx; Table
0x18000fe86  mov     qword ptr [rbp+4Fh+Buffer+8], r14
0x18000fe8a  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000fe91  nop     dword ptr [rax+rax+00h]
0x18000fe96  test    rax, rax
0x18000fe99  jz      short loc_18000FEA5
0x18000fe9b  cmp     [rax+8], r14
0x18000fe9f  jnz     loc_18000FF2A
0x18000fea5  mov     rax, [rbp+4Fh+pv]
0x18000fea9  lea     r9, [rbp+4Fh+NewElement]; NewElement
0x18000fead  mov     r8d, 10h; BufferSize
0x18000feb3  mov     qword ptr [rbp+4Fh+Buffer], rax
0x18000feb7  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18000febb  mov     qword ptr [rbp+4Fh+Buffer+8], rax
0x18000febf  mov     rcx, rbx; Table
0x18000fec2  mov     byte ptr [rbp+4Fh+NewElement], r14b
0x18000fec6  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18000fecd  nop     dword ptr [rax+rax+00h]
0x18000fed2  test    rax, rax
0x18000fed5  jnz     short loc_18000FF1C
0x18000fed7  mov     ebx, 8007000Eh
0x18000fedc  mov     edx, 56h ; 'V'; void *
0x18000fee1  mov     rcx, [rbp+57h]; this
0x18000fee5  lea     r8, aOnecorePrintsc_109; "onecore\\printscan\\appxpackaging\\lib"...
0x18000feec  mov     r9d, ebx; char *
0x18000feef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fef4  mov     rcx, [rbp+4Fh+pv]; pv
0x18000fef8  call    cs:__imp_CoTaskMemFree
0x18000feff  nop     dword ptr [rax+rax+00h]
0x18000ff04  mov     rcx, rdi; this
0x18000ff07  call    ??_GPackageNameInfo@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(uint)
0x18000ff0c  lea     rcx, [rbp+4Fh+var_70]
0x18000ff10  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000ff15  mov     eax, ebx
0x18000ff17  jmp     loc_18000FD31
0x18000ff1c  cmp     byte ptr [rbp+4Fh+NewElement], r14b
0x18000ff20  jz      loc_180010037
0x18000ff26  mov     [rbp+4Fh+pv], r14
0x18000ff2a  mov     eax, [rbp+4Fh+arg_8]
0x18000ff2d  test    eax, eax
0x18000ff2f  jz      loc_180010041
0x18000ff35  cmp     eax, 1
0x18000ff38  jnz     loc_1800103EA
0x18000ff3e  mov     rdx, [rbp+4Fh+var_70]
0x18000ff42  lea     r8, [rbp+4Fh+var_60]
0x18000ff46  mov     eax, 248h
0x18000ff4b  test    esi, esi
0x18000ff4d  mov     ecx, 100h
0x18000ff52  cmovz   ecx, eax
0x18000ff55  add     rcx, r12
0x18000ff58  call    ?ValidateResourcePackage@BundleValidationPackageSet@Packaging@Appx@@QEAAJPEAUIAppxManifestPackageId2@@AEAV?$AutoPtr@UPackageNameInfo@Packaging@Appx@@$1??$AutoPtrDeallocate@UPackageNameInfo@Packaging@Appx@@@Common@@YAXPEAU123@@Z@Common@@@Z; Appx::Packaging::BundleValidationPackageSet::ValidateResourcePackage(IAppxManifestPackageId2 *,Common::AutoPtr<Appx::Packaging::PackageNameInfo,&Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(Appx::Packaging::PackageNameInfo *)> &)
0x18000ff5d  mov     ebx, eax
0x18000ff5f  test    eax, eax
0x18000ff61  js      loc_1800101CA
0x18000ff67  inc     dword ptr [r12+0F8h]
0x18000ff6f  test    esi, esi
0x18000ff71  jnz     loc_180010029
0x18000ff77  mov     rcx, [rbp+4Fh+pv]; pv
0x18000ff7b  call    cs:__imp_CoTaskMemFree
0x18000ff82  nop     dword ptr [rax+rax+00h]
0x18000ff87  mov     rcx, [rbp+4Fh+var_60]; this
0x18000ff8b  test    rcx, rcx
0x18000ff8e  jnz     loc_1800100D1
0x18000ff94  mov     rcx, [rbp+4Fh+var_70]
0x18000ff98  test    rcx, rcx
0x18000ff9b  jz      short loc_18000FFAD
0x18000ff9d  mov     [rbp+4Fh+var_70], r14
0x18000ffa1  mov     rax, [rcx]
0x18000ffa4  mov     rax, [rax+10h]
0x18000ffa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffad  xor     eax, eax
0x18000ffaf  jmp     loc_18000FD31
0x18000ffb4  mov     rcx, [rbp+57h]; this
0x18000ffb8  lea     r8, aOnecorePrintsc_109; "onecore\\printscan\\appxpackaging\\lib"...
0x18000ffbf  mov     r9d, ebx; char *
0x18000ffc2  mov     edx, 37h ; '7'; void *
0x18000ffc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffcc  mov     rcx, rdi; this
0x18000ffcf  call    ??_GPackageNameInfo@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::PackageNameInfo::`scalar deleting destructor'(uint)
0x18000ffd4  mov     rcx, [rbp+4Fh+var_70]
0x18000ffd8  test    rcx, rcx
0x18000ffdb  jz      loc_18000FE28
0x18000ffe1  mov     [rbp+4Fh+var_70], 0
0x18000ffe9  mov     rdx, [rcx]
0x18000ffec  mov     rax, [rdx+10h]
0x18000fff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff5  mov     eax, ebx
0x18000fff7  jmp     loc_18000FD31
0x18000fffc  mov     rcx, [rbp+57h]; this
0x180010000  lea     r8, aOnecorePrintsc_109; "onecore\\printscan\\appxpackaging\\lib"...
0x180010007  mov     ebx, 8007000Eh
0x18001000c  mov     edx, 35h ; '5'; void *
0x180010011  mov     r9d, ebx; char *
0x180010014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010019  lea     rcx, [rbp+4Fh+var_70]
0x18001001d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180010022  mov     eax, ebx
0x180010024  jmp     loc_18000FD3B
  ... truncated ...
```

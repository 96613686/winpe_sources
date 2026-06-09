# Appx::Packaging::BundleValidationPackageSet::ValidateTargetDeviceFamiliesFromManifestPackageId(IAppxManifestPackageId *,IAppxManifestTargetDeviceFamiliesEnumerator *,ushort const *)

- ea: `0x18000b454`
- end: `0x18000b99e`
- name: `?ValidateTargetDeviceFamiliesFromManifestPackageId@BundleValidationPackageSet@Packaging@Appx@@QEAAJPEAUIAppxManifestPackageId@@PEAUIAppxManifestTargetDeviceFamiliesEnumerator@@PEBG@Z`
- size: `1354`
- prototype: `int(Appx::Packaging::BundleValidationPackageSet *__hidden this, struct IAppxManifestPackageId *, struct IAppxManifestTargetDeviceFamiliesEnumerator *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d010`
- `0x18004b9e0`
- `0x1800f3a7c`

## callees

- `0x1800059f0`
- `0x180005eb8`
- `0x18000b454`
- `0x1800133fc`
- `0x180019950`
- `0x18004fde8`
- `0x1800538c8`
- `0x180096048`
- `0x1800992d0`
- `0x1800e8b50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b58a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b67b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b91d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b67b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b91d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b961`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleValidationPackageSet::ValidateTargetDeviceFamiliesFromManifestPackageId(
        Appx::Packaging::BundleValidationPackageSet *this,
        struct IAppxManifestPackageId *a2,
        struct IAppxManifestTargetDeviceFamiliesEnumerator *a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  int v9; // eax
  struct IAppxManifestTargetDeviceFamiliesEnumeratorVtbl *lpVtbl; // rax
  struct IAppxManifestTargetDeviceFamiliesEnumeratorVtbl *v11; // rax
  HRESULT (__stdcall *GetCurrent)(IAppxManifestTargetDeviceFamiliesEnumerator *, IAppxManifestTargetDeviceFamily **); // rbx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void (*v22)(void); // rax
  char *v23; // rax
  const unsigned __int16 **v24; // rbx
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 *v29; // r14
  int v30; // edi
  __int64 v31; // rdx
  unsigned int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // edx
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  __int64 *v39; // rdi
  __int64 *v40; // rsi
  unsigned int v41; // edx
  __int64 v42; // r9
  __int64 v43; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-58h]
  int bIgnoreCasea; // [rsp+20h] [rbp-58h]
  int v46; // [rsp+40h] [rbp-38h] BYREF
  __int64 v47; // [rsp+48h] [rbp-30h] BYREF
  __int64 v48; // [rsp+50h] [rbp-28h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int64 v50[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  int v52; // [rsp+C8h] [rbp+50h] BYREF

  v48 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
  v8 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_2256999d_d617_42f1_880e_0ba4542319d5,
         &v48);
  if ( v8 < 0 )
  {
    v28 = 146;
    goto LABEL_38;
  }
  v52 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 88LL))(v48, &v52);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCase);
    goto LABEL_61;
  }
  if ( v52 == 11 )
    ++*((_DWORD *)this + 80);
  lpVtbl = a3->lpVtbl;
  v46 = 0;
  v8 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamiliesEnumerator *, int *))lpVtbl->GetHasCurrent)(
         a3,
         &v46);
  if ( v8 < 0 )
  {
    v28 = 156;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    goto LABEL_28;
  }
  while ( 1 )
  {
    if ( !v46 )
    {
      v17 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      return 0;
    }
    v11 = a3->lpVtbl;
    v47 = 0;
    GetCurrent = v11->GetCurrent;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
    v13 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamiliesEnumerator *, __int64 *))GetCurrent)(
            a3,
            &v47);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      goto LABEL_60;
    }
    lpString1 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v47 + 24LL))(v47, &lpString1);
    if ( v8 < 0 )
    {
      v19 = 162;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
      CoTaskMemFree((LPVOID)lpString1);
      v20 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
LABEL_28:
      v21 = v48;
      if ( v48 )
      {
        v48 = 0;
        v22 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
LABEL_30:
        v22();
      }
      return (unsigned int)v8;
    }
    if ( !lpString1 )
    {
      v8 = -2147024882;
      v43 = 163;
      v42 = 2147942414LL;
      goto LABEL_58;
    }
    if ( !*((_BYTE *)this + 324) )
    {
      v14 = -1;
      do
        ++v14;
      while ( lpString1[v14] );
      if ( (unsigned int)v14 >= 8 && CompareStringOrdinal(lpString1, 8, L"Windows.", 8, 1) == 2 )
      {
        v50[0] = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v47 + 32LL))(v47, v50);
        if ( v8 >= 0 )
        {
          if ( v50[0] <= 0xA000045630000LL )
            *((_BYTE *)this + 324) = 1;
          goto LABEL_15;
        }
        v19 = 171;
        goto LABEL_26;
      }
    }
LABEL_15:
    if ( v52 != 11 )
      goto LABEL_16;
    v23 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v24 = (const unsigned __int16 **)v23;
    if ( !v23 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
      Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(0, v25);
      CoTaskMemFree((LPVOID)lpString1);
      v26 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v48;
      if ( v48 )
      {
        v48 = 0;
        v22 = *(void (**)(void))(*(_QWORD *)v27 + 16LL);
        goto LABEL_30;
      }
      return (unsigned int)v8;
    }
    *((_QWORD *)v23 + 2) = 0;
    v29 = (__int64 *)(v23 + 24);
    *(_OWORD *)v23 = 0;
    *((_QWORD *)v23 + 3) = 0;
    v30 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, char *))a2->lpVtbl->GetPackageFullName)(
            a2,
            v23 + 24);
    if ( v30 < 0 )
    {
      v31 = 182;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCase);
      Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>((Appx::Packaging::PackageNameInfo *)v24, v32);
      CoTaskMemFree((LPVOID)lpString1);
      v33 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v34 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      return (unsigned int)v30;
    }
    v30 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v24, a4);
    if ( v30 < 0 )
    {
      v31 = 183;
      goto LABEL_44;
    }
    if ( (int)Common::GenericMap<unsigned short *,unsigned short *>::Insert((char *)this + 200, lpString1, v24) < 0 )
      break;
    lpString1 = 0;
    Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(0, v35);
LABEL_16:
    v15 = ((__int64 (__fastcall *)(struct IAppxManifestTargetDeviceFamiliesEnumerator *, int *))a3->lpVtbl->MoveNext)(
            a3,
            &v46);
    v8 = v15;
    if ( v15 < 0 )
    {
      v42 = (unsigned int)v15;
      v43 = 198;
LABEL_58:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v43,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)v42,
        bIgnoreCase);
      CoTaskMemFree((LPVOID)lpString1);
LABEL_60:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
      goto LABEL_61;
    }
    CoTaskMemFree((LPVOID)lpString1);
    v16 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  v36 = Common::GenericMap<unsigned short const *,IAppxFile *>::Find((char *)this + 200, lpString1);
  v39 = (__int64 *)(v36 + 24);
  v40 = (__int64 *)(v36 + 8);
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
    McTemplateU0dzzzz_EventWriteTransfer(
      v37,
      (unsigned int)&EVENT_BUNDLE_VALIDATION_DUPLICATE_TARGET_DEVICE_FAMILY,
      v38,
      (unsigned int)v24[1],
      *v29,
      *v40,
      *v39);
  AppxPackagingLog(
    &EVENT_BUNDLE_VALIDATION_DUPLICATE_TARGET_DEVICE_FAMILY,
    0xB0000104,
    v38,
    v24[1],
    (const unsigned __int16 *)*v29,
    (const unsigned __int16 *)*v40,
    (const unsigned __int16 *)*v39);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
    (const char *)0x80080204LL,
    bIgnoreCasea);
  Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>((Appx::Packaging::PackageNameInfo *)v24, v41);
  CoTaskMemFree((LPVOID)lpString1);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
  v8 = -2146958844;
LABEL_61:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b454  push    rbp
0x18000b456  push    rbx
0x18000b457  push    rsi
0x18000b458  push    rdi
0x18000b459  push    r12
0x18000b45b  push    r13
0x18000b45d  push    r14
0x18000b45f  push    r15
0x18000b461  mov     rbp, rsp
0x18000b464  sub     rsp, 78h
0x18000b468  mov     rsi, rcx
0x18000b46b  xor     edi, edi
0x18000b46d  lea     rcx, [rbp+var_28]
0x18000b471  mov     [rbp+var_28], rdi
0x18000b475  mov     r13, r9
0x18000b478  mov     r15, r8
0x18000b47b  mov     r12, rdx
0x18000b47e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000b483  mov     rax, [r12]
0x18000b487  lea     r8, [rbp+var_28]
0x18000b48b  lea     rdx, _GUID_2256999d_d617_42f1_880e_0ba4542319d5
0x18000b492  mov     rcx, r12
0x18000b495  mov     rax, [rax]
0x18000b498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49d  mov     ebx, eax
0x18000b49f  test    eax, eax
0x18000b4a1  js      loc_18000B767
0x18000b4a7  mov     rcx, [rbp+var_28]
0x18000b4ab  lea     rdx, [rbp+arg_8]
0x18000b4af  mov     [rbp+arg_8], edi
0x18000b4b2  mov     rax, [rcx]
0x18000b4b5  mov     rax, [rax+58h]
0x18000b4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4be  mov     ebx, eax
0x18000b4c0  test    eax, eax
0x18000b4c2  js      loc_18000B82E
0x18000b4c8  cmp     [rbp+arg_8], 0Bh
0x18000b4cc  jz      loc_18000B84B
0x18000b4d2  mov     rax, [r15]
0x18000b4d5  lea     rdx, [rbp+var_38]
0x18000b4d9  mov     rcx, r15
0x18000b4dc  mov     [rbp+var_38], edi
0x18000b4df  mov     rax, [rax+20h]
0x18000b4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e8  mov     ebx, eax
0x18000b4ea  test    eax, eax
0x18000b4ec  js      loc_18000B740
0x18000b4f2  cmp     [rbp+var_38], edi
0x18000b4f5  jz      loc_18000B632
0x18000b4fb  mov     rax, [r15]
0x18000b4fe  lea     rcx, [rbp+var_30]
0x18000b502  mov     [rbp+var_30], rdi
0x18000b506  mov     rbx, [rax+18h]
0x18000b50a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000b50f  lea     rdx, [rbp+var_30]
0x18000b513  mov     rcx, r15
0x18000b516  mov     rax, rbx
0x18000b519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51e  mov     ebx, eax
0x18000b520  test    eax, eax
0x18000b522  js      loc_18000B96F
0x18000b528  mov     rcx, [rbp+var_30]
0x18000b52c  lea     rdx, [rbp+lpString1]
0x18000b530  mov     [rbp+lpString1], rdi
0x18000b534  mov     rax, [rcx]
0x18000b537  mov     rax, [rax+18h]
0x18000b53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b540  mov     ebx, eax
0x18000b542  test    eax, eax
0x18000b544  js      loc_18000B75D
0x18000b54a  mov     rcx, [rbp+lpString1]; lpString1
0x18000b54e  test    rcx, rcx
0x18000b551  jz      loc_18000B940
0x18000b557  cmp     [rsi+144h], dil
0x18000b55e  jnz     short loc_18000B59B
0x18000b560  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b564  inc     rax
0x18000b567  cmp     [rcx+rax*2], di
0x18000b56b  jnz     short loc_18000B564
0x18000b56d  cmp     eax, 8
0x18000b570  jb      short loc_18000B59B
0x18000b572  mov     r9d, 8; cchCount2
0x18000b578  mov     [rsp+78h+bIgnoreCase], 1; int
0x18000b580  mov     edx, r9d; cchCount1
0x18000b583  lea     r8, ?Win10DeviceFamilyNameStartsWith@Manifest@Packaging@Appx@@3QBGB; "Windows."
0x18000b58a  call    cs:__imp_CompareStringOrdinal
0x18000b591  nop     dword ptr [rax+rax+00h]
0x18000b596  cmp     eax, 2
0x18000b599  jz      short loc_18000B5F4
0x18000b59b  cmp     [rbp+arg_8], 0Bh
0x18000b59f  jz      loc_18000B6BD
0x18000b5a5  mov     rax, [r15]
0x18000b5a8  lea     rdx, [rbp+var_38]
0x18000b5ac  mov     rcx, r15
0x18000b5af  mov     rax, [rax+28h]
0x18000b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b8  mov     ebx, eax
0x18000b5ba  test    eax, eax
0x18000b5bc  js      loc_18000B936
0x18000b5c2  mov     rcx, [rbp+lpString1]; pv
0x18000b5c6  call    cs:__imp_CoTaskMemFree
0x18000b5cd  nop     dword ptr [rax+rax+00h]
0x18000b5d2  mov     rcx, [rbp+var_30]
0x18000b5d6  test    rcx, rcx
0x18000b5d9  jz      loc_18000B4F2
0x18000b5df  mov     [rbp+var_30], rdi
0x18000b5e3  mov     rax, [rcx]
0x18000b5e6  mov     rax, [rax+10h]
0x18000b5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ef  jmp     loc_18000B4F2
0x18000b5f4  mov     rcx, [rbp+var_30]
0x18000b5f8  lea     rdx, [rbp+var_18]
0x18000b5fc  mov     [rbp+var_18], rdi
0x18000b600  mov     rax, [rcx]
0x18000b603  mov     rax, [rax+20h]
0x18000b607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60c  mov     ebx, eax
0x18000b60e  test    eax, eax
0x18000b610  js      short loc_18000B65F
0x18000b612  mov     rax, 0A000045630000h
0x18000b61c  cmp     [rbp+var_18], rax
0x18000b620  ja      loc_18000B59B
0x18000b626  mov     byte ptr [rsi+144h], 1
0x18000b62d  jmp     loc_18000B59B
0x18000b632  mov     rcx, [rbp+var_28]
0x18000b636  test    rcx, rcx
0x18000b639  jz      short loc_18000B64B
0x18000b63b  mov     [rbp+var_28], rdi
0x18000b63f  mov     rax, [rcx]
0x18000b642  mov     rax, [rax+10h]
0x18000b646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64b  xor     eax, eax
0x18000b64d  add     rsp, 78h
0x18000b651  pop     r15
0x18000b653  pop     r14
0x18000b655  pop     r13
0x18000b657  pop     r12
0x18000b659  pop     rdi
0x18000b65a  pop     rsi
0x18000b65b  pop     rbx
0x18000b65c  pop     rbp
0x18000b65d  retn
0x18000b65f  mov     edx, 0ABh; void *
0x18000b664  mov     rcx, [rbp+40h]; this
0x18000b668  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x18000b66f  mov     r9d, ebx; char *
0x18000b672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b677  mov     rcx, [rbp+lpString1]; pv
0x18000b67b  call    cs:__imp_CoTaskMemFree
0x18000b682  nop     dword ptr [rax+rax+00h]
0x18000b687  mov     rcx, [rbp+var_30]
0x18000b68b  test    rcx, rcx
0x18000b68e  jz      short loc_18000B6A0
0x18000b690  mov     [rbp+var_30], rdi
0x18000b694  mov     rax, [rcx]
0x18000b697  mov     rax, [rax+10h]
0x18000b69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a0  mov     rcx, [rbp+var_28]
0x18000b6a4  test    rcx, rcx
0x18000b6a7  jz      short loc_18000B6B9
0x18000b6a9  mov     [rbp+var_28], rdi
0x18000b6ad  mov     rax, [rcx]
0x18000b6b0  mov     rax, [rax+10h]
0x18000b6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b9  mov     eax, ebx
0x18000b6bb  jmp     short loc_18000B64D
0x18000b6bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b6c4  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b6c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b6ce  mov     rbx, rax
0x18000b6d1  test    rax, rax
0x18000b6d4  jnz     loc_18000B76E
0x18000b6da  mov     rcx, [rbp+40h]; this
0x18000b6de  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x18000b6e5  mov     ebx, 8007000Eh
0x18000b6ea  mov     edx, 0B5h; void *
0x18000b6ef  mov     r9d, ebx; char *
0x18000b6f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6f7  xor     ecx, ecx
0x18000b6f9  call    ??$AutoPtrDeallocate@UPackageNameInfo@Packaging@Appx@@@Common@@YAXPEAUPackageNameInfo@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(Appx::Packaging::PackageNameInfo *)
0x18000b6fe  mov     rcx, [rbp+lpString1]; pv
0x18000b702  call    cs:__imp_CoTaskMemFree
0x18000b709  nop     dword ptr [rax+rax+00h]
0x18000b70e  mov     rcx, [rbp+var_30]
0x18000b712  test    rcx, rcx
0x18000b715  jz      short loc_18000B727
0x18000b717  mov     [rbp+var_30], rdi
0x18000b71b  mov     rax, [rcx]
0x18000b71e  mov     rax, [rax+10h]
0x18000b722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b727  mov     rcx, [rbp+var_28]
0x18000b72b  test    rcx, rcx
0x18000b72e  jz      short loc_18000B6B9
0x18000b730  mov     [rbp+var_28], rdi
0x18000b734  mov     rdx, [rcx]
0x18000b737  mov     rax, [rdx+10h]
0x18000b73b  jmp     loc_18000B6B4
0x18000b740  mov     edx, 9Ch; void *
0x18000b745  mov     rcx, [rbp+40h]; this
0x18000b749  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x18000b750  mov     r9d, ebx; char *
0x18000b753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b758  jmp     loc_18000B6A0
0x18000b75d  mov     edx, 0A2h
0x18000b762  jmp     loc_18000B664
0x18000b767  mov     edx, 92h
0x18000b76c  jmp     short loc_18000B745
0x18000b76e  mov     qword ptr [rax+10h], 0
0x18000b776  lea     r14, [rax+18h]
0x18000b77a  xorps   xmm0, xmm0
0x18000b77d  mov     rdx, r14
0x18000b780  movups  xmmword ptr [rax], xmm0
0x18000b783  mov     [rax+18h], rdi
0x18000b787  mov     rcx, [r12]
0x18000b78b  mov     rax, [rcx+48h]
0x18000b78f  mov     rcx, r12
0x18000b792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b797  mov     edi, eax
0x18000b799  test    eax, eax
0x18000b79b  js      loc_18000B827
0x18000b7a1  mov     rdx, r13; unsigned __int16 *
0x18000b7a4  mov     rcx, rbx; this
0x18000b7a7  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18000b7ac  mov     edi, eax
0x18000b7ae  test    eax, eax
0x18000b7b0  jns     loc_18000B856
0x18000b7b6  mov     edx, 0B7h; void *
0x18000b7bb  mov     rcx, [rbp+40h]; this
0x18000b7bf  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x18000b7c6  mov     r9d, edi; char *
0x18000b7c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7ce  mov     rcx, rbx
0x18000b7d1  call    ??$AutoPtrDeallocate@UPackageNameInfo@Packaging@Appx@@@Common@@YAXPEAUPackageNameInfo@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(Appx::Packaging::PackageNameInfo *)
0x18000b7d6  mov     rcx, [rbp+lpString1]; pv
0x18000b7da  call    cs:__imp_CoTaskMemFree
0x18000b7e1  nop     dword ptr [rax+rax+00h]
0x18000b7e6  mov     rcx, [rbp+var_30]
0x18000b7ea  test    rcx, rcx
0x18000b7ed  jz      short loc_18000B803
0x18000b7ef  mov     [rbp+var_30], 0
0x18000b7f7  mov     rax, [rcx]
0x18000b7fa  mov     rax, [rax+10h]
0x18000b7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b803  mov     rcx, [rbp+var_28]
0x18000b807  test    rcx, rcx
0x18000b80a  jz      short loc_18000B820
0x18000b80c  mov     [rbp+var_28], 0
0x18000b814  mov     rax, [rcx]
0x18000b817  mov     rax, [rax+10h]
0x18000b81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b820  mov     eax, edi
0x18000b822  jmp     loc_18000B64D
0x18000b827  mov     edx, 0B6h
0x18000b82c  jmp     short loc_18000B7BB
0x18000b82e  mov     rcx, [rbp+40h]; this
0x18000b832  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x18000b839  mov     r9d, eax; char *
0x18000b83c  mov     edx, 94h; void *
0x18000b841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b846  jmp     loc_18000B990
0x18000b84b  inc     dword ptr [rsi+140h]
0x18000b851  jmp     loc_18000B4D2
0x18000b856  mov     rdx, [rbp+lpString1]
0x18000b85a  lea     rdi, [rsi+0C8h]
0x18000b861  mov     rcx, rdi
0x18000b864  mov     r8, rbx
0x18000b867  call    ?Insert@?$GenericMap@PEAGPEAG@Common@@QEAAJPEAG0@Z; Common::GenericMap<ushort *,ushort *>::Insert(ushort *,ushort *)
0x18000b86c  test    eax, eax
0x18000b86e  js      short loc_18000B882
0x18000b870  xor     edi, edi
0x18000b872  xor     ecx, ecx
0x18000b874  mov     [rbp+lpString1], rdi
0x18000b878  call    ??$AutoPtrDeallocate@UPackageNameInfo@Packaging@Appx@@@Common@@YAXPEAUPackageNameInfo@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::PackageNameInfo>(Appx::Packaging::PackageNameInfo *)
0x18000b87d  jmp     loc_18000B5A5
0x18000b882  mov     rdx, [rbp+lpString1]
0x18000b886  mov     rcx, rdi
0x18000b889  call    ?Find@?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAAPEAUIAppxFile@@PEBG@Z; Common::GenericMap<ushort const *,IAppxFile *>::Find(ushort const *)
0x18000b88e  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x18000b895  lea     rdi, [rax+18h]
0x18000b899  lea     rsi, [rax+8]
0x18000b89d  jz      short loc_18000B8C7
0x18000b89f  mov     rax, [rdi]
0x18000b8a2  lea     rdx, EVENT_BUNDLE_VALIDATION_DUPLICATE_TARGET_DEVICE_FAMILY
0x18000b8a9  mov     r9, [rbx+8]
0x18000b8ad  mov     [rsp+78h+var_48], rax
0x18000b8b2  mov     rax, [rsi]
0x18000b8b5  mov     [rsp+78h+var_50], rax
0x18000b8ba  mov     rax, [r14]
0x18000b8bd  mov     qword ptr [rsp+78h+bIgnoreCase], rax
0x18000b8c2  call    McTemplateU0dzzzz_EventWriteTransfer
0x18000b8c7  mov     rax, [rdi]
0x18000b8ca  lea     rcx, EVENT_BUNDLE_VALIDATION_DUPLICATE_TARGET_DEVICE_FAMILY; struct _EVENT_DESCRIPTOR *
0x18000b8d1  mov     r9, [rbx+8]; unsigned __int16 *
0x18000b8d5  mov     edx, 0B0000104h; unsigned int
0x18000b8da  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x18000b8df  mov     rax, [rsi]
0x18000b8e2  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18000b8e7  mov     rax, [r14]
0x18000b8ea  mov     qword ptr [rsp+78h+bIgnoreCase], rax; int
0x18000b8ef  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJPEBG111@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,ushort const *,ushort const *,ushort const *,ushort const *)
  ... truncated ...
```

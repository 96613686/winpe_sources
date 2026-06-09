# GetFolderType

- ea: `0x1802a5b00`
- end: `0x1802a61e5`
- name: `GetFolderType`
- size: `1765`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802a5a40`

## callees

- `0x18000d6cc`
- `0x180018f50`
- `0x180045460`
- `0x180048fb0`
- `0x18005bf00`
- `0x18012cfc0`
- `0x18012fa50`
- `0x18015c600`
- `0x180173780`
- `0x1801ca260`
- `0x180211200`
- `0x180216c20`
- `0x180290f70`
- `0x1802a5b00`
- `0x1802ad7d4`
- `0x1802c3af8`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x18050dde0`
- `0x180628884`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802a5e61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802a5e61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802a5dcc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1802a5dcc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802a6038`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802a6038`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802a60f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1802a60f6`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802a5cc7`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802a5efa`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802a5cc7`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x1802a5efa`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5bee`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5d1a`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5fda`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5bee`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5d1a`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802a5fda`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c27`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c39`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c5f`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c27`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c39`
- `PROPSYS!PSPropertyBag_Delete` at `0x1802a5c5f`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802a5c6c`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802a6144`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802a5c6c`
- `PROPSYS!PSPropertyBag_WriteGUID` at `0x1802a6144`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a5d4d`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1802a5d4d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1802a5b74`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHGetViewStatePropertyBag` at `0x1802a5b74`

## pseudocode

```c
GUID *__fastcall GetFolderType(GUID *a1, IUnknown *a2, unsigned __int16 *a3, const ITEMIDLIST *a4)
{
  const unsigned __int16 *v8; // rdx
  GUID v9; // xmm6
  __int64 v10; // rdx
  unsigned __int64 v11; // xmm0_8
  unsigned __int64 v12; // rax
  int DriveNumberW; // eax
  CMountPoint *v14; // rbx
  int v15; // ebx
  int v16; // eax
  struct IShellItem2 *v17; // rdi
  HRESULT (__stdcall *GetPropertyStoreForKeys)(IShellItem2 *, const PROPERTYKEY *, UINT, GETPROPERTYSTOREFLAGS, const IID *const, void **); // rbx
  __int64 v19; // rdi
  bool v20; // r14
  int (__fastcall *v21)(__int64, GUID *, GUID *); // rbx
  GUID v22; // xmm0
  struct IShellItem2 *ppv; // [rsp+38h] [rbp-D0h] BYREF
  IPropertyBag *propBag; // [rsp+40h] [rbp-C8h] BYREF
  PROPVARIANT pvar[3]; // [rsp+48h] [rbp-C0h] BYREF
  GUID Buf1_8; // [rsp+68h] [rbp-A0h] BYREF
  GUID value_8; // [rsp+78h] [rbp-90h] BYREF
  GUID v29; // [rsp+88h] [rbp-80h] BYREF
  WCHAR pszStr2[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR String2[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  *a1 = FOLDERTYPEID_Invalid;
  propBag = 0;
  SHGetViewStatePropertyBag(a4, L"Shell", 5u, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&propBag);
  if ( !propBag )
    goto LABEL_10;
  Buf1_8 = FOLDERTYPEID_Invalid;
  if ( Windows::Internal::PerFolderRoots::IsUnderPerFolderRoot((Windows::Internal::PerFolderRoots *)a3, v8) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)pvar, a3);
    ppv = (struct IShellItem2 *)pvar;
    winrt::impl::call_factory<winrt::Windows::Internal::Storage::PerFolderRootManager,winrt::Windows::Internal::Storage::IPerFolderRootManagerStatics,_lambda_e1fe1346832bb179b80bcbcd404a46b3_>(
      &v29,
      &ppv);
    Buf1_8 = v29;
  }
  value_8 = 0;
  v9 = FOLDERTYPEID_Invalid;
  if ( PSPropertyBag_ReadGUID(propBag, L"PerFolderRootDerivedFolderType", &value_8) < 0 )
    value_8 = FOLDERTYPEID_Invalid;
  if ( memcmp_0(&Buf1_8, &value_8, 0x10u) )
  {
    PSPropertyBag_Delete(propBag, L"SniffedFolderType");
    PSPropertyBag_Delete(propBag, L"FolderType");
    if ( !memcmp_0(&FOLDERTYPEID_Invalid, &Buf1_8, 0x10u) )
    {
      PSPropertyBag_Delete(propBag, L"PerFolderRootDerivedFolderType");
    }
    else
    {
      PSPropertyBag_WriteGUID(propBag, L"PerFolderRootDerivedFolderType", &Buf1_8);
      *a1 = Buf1_8;
    }
LABEL_10:
    v9 = FOLDERTYPEID_Invalid;
  }
  v10 = *(_QWORD *)&v9.Data1;
  v11 = _mm_srli_si128((__m128i)v9, 8).m128i_u64[0];
  v12 = v11;
  if ( *(_QWORD *)&v9.Data1 == *(_QWORD *)&a1->Data1 )
  {
    if ( v11 == *(_QWORD *)a1->Data4 && propBag )
    {
      pszStr2[0] = 0;
      PSPropertyBag_ReadStr(propBag, L"FolderType", pszStr2, 260);
      if ( pszStr2[0] )
        SHGetFolderTypeFromCanonicalName(pszStr2);
      v9 = FOLDERTYPEID_Invalid;
      v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
      v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
    }
    if ( v10 == *(_QWORD *)&a1->Data1 )
    {
      if ( v12 == *(_QWORD *)a1->Data4 && propBag )
      {
        Buf1_8 = v9;
        if ( PSPropertyBag_ReadGUID(propBag, L"PerFolderRootDerivedFolderType", &Buf1_8) >= 0 )
          *a1 = Buf1_8;
        v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
        v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
      }
      if ( v10 == *(_QWORD *)&a1->Data1 )
      {
        if ( v12 == *(_QWORD *)a1->Data4 )
        {
          if ( PathIsNetworkPathW(a3) )
          {
            ppv = 0;
            if ( SHCreateItemFromIDList(a4, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)&ppv) >= 0 )
            {
              if ( !(unsigned int)CachedIsOfflineAvailable(ppv, propBag) )
                *a1 = FOLDERTYPEID_Generic;
              ((void (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl->Release)(ppv);
            }
          }
          v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
          v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
        }
        if ( v10 == *(_QWORD *)&a1->Data1 )
        {
          if ( v12 == *(_QWORD *)a1->Data4 )
          {
            ppv = 0;
            DriveNumberW = PathGetDriveNumberW(a3);
            if ( (int)CMountPoint::GetMountPoint(DriveNumberW, (struct CMountPoint **)&ppv) >= 0 )
            {
              v14 = (CMountPoint *)ppv;
              if ( ((unsigned int (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl[2].GetFileTime)(ppv)
                || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v14 + 368LL))(v14)
                || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v14 + 392LL))(v14) )
              {
                *a1 = FOLDERTYPEID_Generic;
              }
              CMountPoint::Release(v14);
            }
            v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
            v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
          }
          if ( v10 == *(_QWORD *)&a1->Data1 )
          {
            if ( v12 == *(_QWORD *)a1->Data4 )
            {
              ppv = 0;
              if ( !PathIsRootW(a3) && (int)GetCachedIniForFolder(a2, a4, a3, (void **)&ppv) >= 0 )
              {
                if ( (unsigned int)GetFolderString(
                                     (_DWORD)ppv,
                                     (unsigned int)L"ViewState",
                                     (unsigned int)L"FolderType",
                                     (unsigned int)pszStr2,
                                     260) )
                  SHGetFolderTypeFromCanonicalName(pszStr2);
                ((void (__fastcall *)(struct IShellItem2 *))ppv->lpVtbl->Release)(ppv);
              }
              v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
              v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
            }
            if ( v10 == *(_QWORD *)&a1->Data1 && v12 == *(_QWORD *)a1->Data4 && propBag )
            {
              pszStr2[0] = 0;
              PSPropertyBag_ReadStr(propBag, L"SniffedFolderType", pszStr2, 260);
              if ( pszStr2[0] )
                SHGetFolderTypeFromCanonicalName(pszStr2);
              v10 = *(_QWORD *)&FOLDERTYPEID_Invalid.Data1;
              v12 = *(_QWORD *)FOLDERTYPEID_Invalid.Data4;
            }
          }
        }
      }
    }
  }
  if ( v10 == *(_QWORD *)&a1->Data1 && v12 == *(_QWORD *)a1->Data4 )
  {
    v15 = 0;
    while ( 1 )
    {
      if ( (int)SHGetFolderPathEx((unsigned int)off_180801660[3 * v15], 0x4000, 0, (unsigned int)String2, 260) >= 0 )
      {
        v16 = PathComparePaths(String2, a3);
        v10 = (4 * (~LOBYTE(off_180801660[3 * v15 + 2]) & 2)) | 2u;
        if ( ((unsigned int)v10 & v16) != 0 )
          break;
      }
      if ( (unsigned int)++v15 >= 9 )
        goto LABEL_62;
    }
    *a1 = *off_180801660[3 * v15 + 1];
  }
LABEL_62:
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::GetImpl'::`2'::impl,
    v10);
  if ( propBag )
  {
    Buf1_8 = FOLDERTYPEID_Invalid;
    if ( PSPropertyBag_ReadGUID(propBag, L"KnownFolderDerivedFolderType", &Buf1_8) >= 0 )
      *a1 = Buf1_8;
    if ( !memcmp_0(&FOLDERTYPEID_Invalid, &Buf1_8, 0x10u) )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( CoCreateInstance(
             &CLSID_KnownFolderManager,
             0,
             1u,
             &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
             (LPVOID *)&ppv) >= 0 )
      {
        v17 = ppv;
        *(_QWORD *)&v29.Data1 = 0;
        GetPropertyStoreForKeys = ppv->lpVtbl->GetPropertyStoreForKeys;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        if ( ((int (__fastcall *)(struct IShellItem2 *, unsigned __int16 *, __int64, GUID *))GetPropertyStoreForKeys)(
               v17,
               a3,
               1,
               &v29) >= 0 )
        {
          v19 = *(_QWORD *)&v29.Data1;
          *(_QWORD *)&value_8.Data1 = 0;
          v20 = 0;
          v21 = ***(int (__fastcall ****)(__int64, GUID *, GUID *))&v29.Data1;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&value_8);
          if ( v21(v19, &GUID_0e207e42_dc38_440d_9b00_2e8cf0e23c8d, &value_8) >= 0 )
          {
            LOWORD(pvar[0]) = 0;
            if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, PROPVARIANT *))(**(_QWORD **)&value_8.Data1 + 24LL))(
                   *(_QWORD *)&value_8.Data1,
                   L"SniffPolicy",
                   pvar) >= 0 )
              v20 = wcscmp_0((const wchar_t *)pvar[1], L"override") == 0;
            PropVariantClear(pvar);
          }
          if ( (*(_QWORD *)&a1->Data1 == *(_QWORD *)&FOLDERTYPEID_Invalid.Data1
             && *(_QWORD *)a1->Data4 == *(_QWORD *)FOLDERTYPEID_Invalid.Data4
             || v20)
            && (*(int (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v29.Data1 + 72LL))(*(_QWORD *)&v29.Data1, &Buf1_8) >= 0 )
          {
            PSPropertyBag_WriteGUID(propBag, L"KnownFolderDerivedFolderType", &Buf1_8);
            *a1 = Buf1_8;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&value_8);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  SafeRelease<IFilterCreationCallback>(&propBag);
  if ( *(_QWORD *)&FOLDERTYPEID_Invalid.Data1 == *(_QWORD *)&a1->Data1
    && *(_QWORD *)FOLDERTYPEID_Invalid.Data4 == *(_QWORD *)a1->Data4 )
  {
    if ( (unsigned int)ShouldUseStorageProviderViews(a3) )
      v22 = FOLDERTYPEID_StorageProviderGeneric;
    else
      v22 = FOLDERTYPEID_Generic;
    *a1 = v22;
  }
  return a1;
}

```

## disassembly

```asm
0x1802a5b00  mov     rax, rsp
0x1802a5b03  mov     [rax+8], rbx
0x1802a5b07  push    rbp
0x1802a5b08  push    rsi
0x1802a5b09  push    rdi
0x1802a5b0a  push    r12
0x1802a5b0c  push    r13
0x1802a5b0e  push    r14
0x1802a5b10  push    r15
0x1802a5b12  lea     rbp, [rax-408h]
0x1802a5b19  sub     rsp, 4D0h
0x1802a5b20  movaps  xmmword ptr [rax-48h], xmm6
0x1802a5b24  mov     rax, cs:__security_cookie
0x1802a5b2b  xor     rax, rsp
0x1802a5b2e  mov     [rbp+400h+var_50], rax
0x1802a5b35  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5b3c  mov     rdi, r9
0x1802a5b3f  lea     rax, [rsp+500h+propBag]
0x1802a5b44  xor     r12d, r12d
0x1802a5b47  mov     [rsp+500h+ppv], rax; ppv
0x1802a5b4c  movdqu  xmmword ptr [rcx], xmm0
0x1802a5b50  mov     r15, r8
0x1802a5b53  mov     [rsp+500h+propBag], r12
0x1802a5b58  mov     r14, rdx
0x1802a5b5b  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1802a5b62  mov     rsi, rcx
0x1802a5b65  lea     r8d, [r12+5]; dwFlags
0x1802a5b6a  mov     rcx, rdi; pidl
0x1802a5b6d  lea     rdx, pszBagName; "Shell"
0x1802a5b74  call    cs:__imp_SHGetViewStatePropertyBag
0x1802a5b7a  lea     rbx, aPerfolderrootd; "PerFolderRootDerivedFolderType"
0x1802a5b81  lea     r13d, [r12+10h]
0x1802a5b86  cmp     [rsp+500h+propBag], r12
0x1802a5b8b  jz      loc_1802A5C7B
0x1802a5b91  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5b98  mov     rcx, r15; this
0x1802a5b9b  movdqu  [rsp+500h+Buf1+8], xmm0
0x1802a5ba1  call    ?IsUnderPerFolderRoot@PerFolderRoots@Internal@Windows@@YA_NPEBG@Z; Windows::Internal::PerFolderRoots::IsUnderPerFolderRoot(ushort const *)
0x1802a5ba6  test    al, al
0x1802a5ba8  jz      short loc_1802A5BD9
0x1802a5baa  mov     rdx, r15; unsigned __int16 *
0x1802a5bad  lea     rcx, [rsp+500h+pvar]; this
0x1802a5bb2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1802a5bb7  lea     rax, [rsp+500h+pvar]
0x1802a5bbc  lea     rdx, [rsp+500h+var_4D0]
0x1802a5bc1  mov     [rsp+500h+var_4D0], rax
0x1802a5bc6  lea     rcx, [rbp+400h+var_480]
0x1802a5bca  call    ??$call_factory@UPerFolderRootManager@Storage@Internal@Windows@winrt@@UIPerFolderRootManagerStatics@2345@V_lambda_e1fe1346832bb179b80bcbcd404a46b3_@@@impl@winrt@@YA?A_P$$QEAV_lambda_e1fe1346832bb179b80bcbcd404a46b3_@@@Z
0x1802a5bcf  movaps  xmm0, [rbp+400h+var_480]
0x1802a5bd3  movdqa  [rsp+500h+Buf1+8], xmm0
0x1802a5bd9  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5bde  lea     r8, [rsp+500h+value+8]; value
0x1802a5be3  xorps   xmm0, xmm0
0x1802a5be6  mov     rdx, rbx; propName
0x1802a5be9  movups  xmmword ptr [rsp+500h+value+8], xmm0
0x1802a5bee  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802a5bf4  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5bfb  test    eax, eax
0x1802a5bfd  jns     short loc_1802A5C05
0x1802a5bff  movdqu  xmmword ptr [rsp+500h+value+8], xmm6
0x1802a5c05  mov     r8, r13; Size
0x1802a5c08  lea     rdx, [rsp+500h+value+8]; Buf2
0x1802a5c0d  lea     rcx, [rsp+500h+Buf1+8]; Buf1
0x1802a5c12  call    memcmp_0
0x1802a5c17  test    eax, eax
0x1802a5c19  jz      short loc_1802A5C82
0x1802a5c1b  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5c20  lea     rdx, aSniffedfoldert; "SniffedFolderType"
0x1802a5c27  call    cs:__imp_PSPropertyBag_Delete
0x1802a5c2d  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5c32  lea     rdx, aFoldertype; "FolderType"
0x1802a5c39  call    cs:__imp_PSPropertyBag_Delete
0x1802a5c3f  mov     r8, r13; Size
0x1802a5c42  lea     rdx, [rsp+500h+Buf1+8]; Buf2
0x1802a5c47  lea     rcx, FOLDERTYPEID_Invalid; Buf1
0x1802a5c4e  call    memcmp_0
0x1802a5c53  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5c58  mov     rdx, rbx; propName
0x1802a5c5b  test    eax, eax
0x1802a5c5d  jnz     short loc_1802A5C67
0x1802a5c5f  call    cs:__imp_PSPropertyBag_Delete
0x1802a5c65  jmp     short loc_1802A5C7B
0x1802a5c67  lea     r8, [rsp+500h+Buf1+8]; value
0x1802a5c6c  call    cs:__imp_PSPropertyBag_WriteGUID
0x1802a5c72  movaps  xmm0, [rsp+500h+Buf1+8]
0x1802a5c77  movdqu  xmmword ptr [rsi], xmm0
0x1802a5c7b  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5c82  movdqa  xmm0, xmm6
0x1802a5c86  movq    rdx, xmm6
0x1802a5c8b  mov     r13d, 104h
0x1802a5c91  psrldq  xmm0, 8
0x1802a5c96  movq    rax, xmm0
0x1802a5c9b  cmp     rdx, [rsi]
0x1802a5c9e  jnz     loc_1802A5F21
0x1802a5ca4  cmp     rax, [rsi+8]
0x1802a5ca8  jnz     short loc_1802A5CF3
0x1802a5caa  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5caf  test    rcx, rcx
0x1802a5cb2  jz      short loc_1802A5CF3
0x1802a5cb4  mov     r9d, r13d; characterCount
0x1802a5cb7  mov     [rbp+400h+pszStr2], r12w
0x1802a5cbc  lea     r8, [rbp+400h+pszStr2]; value
0x1802a5cc0  lea     rdx, aFoldertype; "FolderType"
0x1802a5cc7  call    cs:__imp_PSPropertyBag_ReadStr
0x1802a5ccd  cmp     [rbp+400h+pszStr2], r12w
0x1802a5cd2  jz      short loc_1802A5CE0
0x1802a5cd4  mov     rdx, rsi
0x1802a5cd7  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802a5cdb  call    SHGetFolderTypeFromCanonicalName
0x1802a5ce0  movups  xmm6, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5ce7  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5cee  movq    rdx, xmm6
0x1802a5cf3  cmp     rdx, [rsi]
0x1802a5cf6  jnz     loc_1802A5F21
0x1802a5cfc  cmp     rax, [rsi+8]
0x1802a5d00  jnz     short loc_1802A5D3B
0x1802a5d02  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5d07  test    rcx, rcx
0x1802a5d0a  jz      short loc_1802A5D3B
0x1802a5d0c  lea     r8, [rsp+500h+Buf1+8]; value
0x1802a5d11  mov     rdx, rbx; propName
0x1802a5d14  movdqu  [rsp+500h+Buf1+8], xmm6
0x1802a5d1a  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802a5d20  test    eax, eax
0x1802a5d22  js      short loc_1802A5D2D
0x1802a5d24  movups  xmm0, [rsp+500h+Buf1+8]
0x1802a5d29  movdqu  xmmword ptr [rsi], xmm0
0x1802a5d2d  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5d34  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5d3b  cmp     rdx, [rsi]
0x1802a5d3e  jnz     loc_1802A5F21
0x1802a5d44  cmp     rax, [rsi+8]
0x1802a5d48  jnz     short loc_1802A5DB1
0x1802a5d4a  mov     rcx, r15; pszPath
0x1802a5d4d  call    cs:__imp_PathIsNetworkPathW
0x1802a5d53  test    eax, eax
0x1802a5d55  jz      short loc_1802A5DA3
0x1802a5d57  lea     r8, [rsp+500h+var_4D0]; ppv
0x1802a5d5c  mov     [rsp+500h+var_4D0], r12
0x1802a5d61  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1802a5d68  mov     rcx, rdi; pidl
0x1802a5d6b  call    SHCreateItemFromIDList
0x1802a5d70  test    eax, eax
0x1802a5d72  js      short loc_1802A5DA3
0x1802a5d74  mov     rdx, [rsp+500h+propBag]; struct IPropertyBag *
0x1802a5d79  mov     rcx, [rsp+500h+var_4D0]; struct IShellItem2 *
0x1802a5d7e  call    ?CachedIsOfflineAvailable@@YAHPEAUIShellItem2@@PEAUIPropertyBag@@@Z; CachedIsOfflineAvailable(IShellItem2 *,IPropertyBag *)
0x1802a5d83  test    eax, eax
0x1802a5d85  jnz     short loc_1802A5D92
0x1802a5d87  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x1802a5d8e  movdqu  xmmword ptr [rsi], xmm0
0x1802a5d92  mov     rcx, [rsp+500h+var_4D0]
0x1802a5d97  mov     rax, [rcx]
0x1802a5d9a  mov     rax, [rax+10h]
0x1802a5d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a5da3  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5daa  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5db1  cmp     rdx, [rsi]
0x1802a5db4  jnz     loc_1802A5F21
0x1802a5dba  cmp     rax, [rsi+8]
0x1802a5dbe  jnz     loc_1802A5E4A
0x1802a5dc4  mov     rcx, r15; pszPath
0x1802a5dc7  mov     [rsp+500h+var_4D0], r12
0x1802a5dcc  call    cs:__imp_PathGetDriveNumberW
0x1802a5dd2  mov     ecx, eax; int
0x1802a5dd4  lea     rdx, [rsp+500h+var_4D0]; struct CMountPoint **
0x1802a5dd9  call    ?GetMountPoint@CMountPoint@@SAJHPEAPEAV1@@Z; CMountPoint::GetMountPoint(int,CMountPoint * *)
0x1802a5dde  test    eax, eax
0x1802a5de0  js      short loc_1802A5E3C
0x1802a5de2  mov     rbx, [rsp+500h+var_4D0]
0x1802a5de7  mov     rcx, rbx
0x1802a5dea  mov     rax, [rbx]
0x1802a5ded  mov     rax, [rax+1C8h]
0x1802a5df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a5df9  test    eax, eax
0x1802a5dfb  jnz     short loc_1802A5E29
0x1802a5dfd  mov     rax, [rbx]
0x1802a5e00  mov     rcx, rbx
0x1802a5e03  mov     rax, [rax+170h]
0x1802a5e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a5e0f  test    eax, eax
0x1802a5e11  jnz     short loc_1802A5E29
0x1802a5e13  mov     rax, [rbx]
0x1802a5e16  mov     rcx, rbx
0x1802a5e19  mov     rax, [rax+188h]
0x1802a5e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a5e25  test    eax, eax
0x1802a5e27  jz      short loc_1802A5E34
0x1802a5e29  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Generic.Data1
0x1802a5e30  movdqu  xmmword ptr [rsi], xmm0
0x1802a5e34  mov     rcx, rbx; this
0x1802a5e37  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1802a5e3c  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5e43  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5e4a  cmp     rdx, [rsi]
0x1802a5e4d  jnz     loc_1802A5F21
0x1802a5e53  cmp     rax, [rsi+8]
0x1802a5e57  jnz     short loc_1802A5ED2
0x1802a5e59  mov     rcx, r15; pszPath
0x1802a5e5c  mov     [rsp+500h+var_4D0], r12
0x1802a5e61  call    cs:__imp_PathIsRootW
0x1802a5e67  test    eax, eax
0x1802a5e69  jnz     short loc_1802A5EC4
0x1802a5e6b  lea     r9, [rsp+500h+var_4D0]; ppv
0x1802a5e70  mov     r8, r15; pszName
0x1802a5e73  mov     rdx, rdi; pidl
0x1802a5e76  mov     rcx, r14; punk
0x1802a5e79  call    GetCachedIniForFolder
0x1802a5e7e  test    eax, eax
0x1802a5e80  js      short loc_1802A5EC4
0x1802a5e82  mov     rcx, [rsp+500h+var_4D0]
0x1802a5e87  lea     r9, [rbp+400h+pszStr2]
0x1802a5e8b  lea     r8, aFoldertype; "FolderType"
0x1802a5e92  mov     dword ptr [rsp+500h+ppv], r13d
0x1802a5e97  lea     rdx, aViewstate; "ViewState"
0x1802a5e9e  call    GetFolderString
0x1802a5ea3  test    eax, eax
0x1802a5ea5  jz      short loc_1802A5EB3
0x1802a5ea7  mov     rdx, rsi
0x1802a5eaa  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802a5eae  call    SHGetFolderTypeFromCanonicalName
0x1802a5eb3  mov     rcx, [rsp+500h+var_4D0]
0x1802a5eb8  mov     rax, [rcx]
0x1802a5ebb  mov     rax, [rax+10h]
0x1802a5ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a5ec4  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5ecb  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5ed2  cmp     rdx, [rsi]
0x1802a5ed5  jnz     short loc_1802A5F21
0x1802a5ed7  cmp     rax, [rsi+8]
0x1802a5edb  jnz     short loc_1802A5F21
0x1802a5edd  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5ee2  test    rcx, rcx
0x1802a5ee5  jz      short loc_1802A5F21
0x1802a5ee7  mov     r9d, r13d; characterCount
0x1802a5eea  mov     [rbp+400h+pszStr2], r12w
0x1802a5eef  lea     r8, [rbp+400h+pszStr2]; value
0x1802a5ef3  lea     rdx, aSniffedfoldert; "SniffedFolderType"
0x1802a5efa  call    cs:__imp_PSPropertyBag_ReadStr
0x1802a5f00  cmp     [rbp+400h+pszStr2], r12w
0x1802a5f05  jz      short loc_1802A5F13
0x1802a5f07  mov     rdx, rsi
0x1802a5f0a  lea     rcx, [rbp+400h+pszStr2]; pszStr2
0x1802a5f0e  call    SHGetFolderTypeFromCanonicalName
0x1802a5f13  mov     rdx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5f1a  mov     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x1802a5f21  mov     r14d, 1
0x1802a5f27  cmp     rdx, [rsi]
0x1802a5f2a  jnz     short loc_1802A5FA4
0x1802a5f2c  cmp     rax, [rsi+8]
0x1802a5f30  jnz     short loc_1802A5FA4
0x1802a5f32  mov     ebx, r12d
0x1802a5f35  lea     r13, off_180801660
0x1802a5f3c  movsxd  rax, ebx
0x1802a5f3f  lea     r9, [rbp+400h+String2]
0x1802a5f46  xor     r8d, r8d
0x1802a5f49  mov     dword ptr [rsp+500h+ppv], 104h
0x1802a5f51  mov     edx, 4000h
0x1802a5f56  lea     rdi, [rax+rax*2]
0x1802a5f5a  mov     rcx, [r13+rdi*8+0]
0x1802a5f5f  call    SHGetFolderPathEx
0x1802a5f64  test    eax, eax
0x1802a5f66  js      short loc_1802A5F8E
0x1802a5f68  mov     rdx, r15; lpString1
0x1802a5f6b  lea     rcx, [rbp+400h+String2]; lpString2
0x1802a5f72  call    PathComparePaths
0x1802a5f77  mov     cl, [r13+rdi*8+10h]
0x1802a5f7c  not     cl
0x1802a5f7e  movzx   edx, cl
0x1802a5f81  and     edx, 2
0x1802a5f84  shl     edx, 2
0x1802a5f87  or      edx, 2
0x1802a5f8a  test    eax, edx
0x1802a5f8c  jnz     short loc_1802A5F98
0x1802a5f8e  add     ebx, r14d
0x1802a5f91  cmp     ebx, 9
0x1802a5f94  jb      short loc_1802A5F3C
0x1802a5f96  jmp     short loc_1802A5FA4
0x1802a5f98  mov     rax, [r13+rdi*8+8]
0x1802a5f9d  movups  xmm0, xmmword ptr [rax]
0x1802a5fa0  movdqu  xmmword ptr [rsi], xmm0
0x1802a5fa4  mov     dl, r14b
0x1802a5fa7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting> `wil::Feature<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::GetImpl(void)'::`2'::impl
0x1802a5fae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDownloadsSorting@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDownloadsSorting>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1802a5fb3  mov     rcx, [rsp+500h+propBag]; propBag
0x1802a5fb8  test    rcx, rcx
0x1802a5fbb  jz      loc_1802A6170
0x1802a5fc1  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Invalid.Data1
0x1802a5fc8  lea     r8, [rsp+500h+Buf1+8]; value
0x1802a5fcd  lea     rdx, aKnownfolderder; "KnownFolderDerivedFolderType"
0x1802a5fd4  movdqu  [rsp+500h+Buf1+8], xmm0
0x1802a5fda  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802a5fe0  test    eax, eax
0x1802a5fe2  js      short loc_1802A5FED
0x1802a5fe4  movups  xmm0, [rsp+500h+Buf1+8]
0x1802a5fe9  movdqu  xmmword ptr [rsi], xmm0
0x1802a5fed  mov     r8d, 10h; Size
0x1802a5ff3  lea     rdx, [rsp+500h+Buf1+8]; Buf2
0x1802a5ff8  lea     rcx, FOLDERTYPEID_Invalid; Buf1
0x1802a5fff  call    memcmp_0
  ... truncated ...
```

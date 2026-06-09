# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(ushort const *,MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x1800441c8`
- end: `0x180044926`
- name: `?CreateFromPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGW4APPX_PACKAGE_TARGET_TYPE@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(const WCHAR *, int, __int64, MsixPackage::Provisioning::Library::MsixPackageAdapter **)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18004dae8`
- `0x18004ddb4`

## callees

- `0x18001bf0c`
- `0x18003167c`
- `0x1800329f4`
- `0x180039e9c`
- `0x18003b0b0`
- `0x180040a48`
- `0x1800441c8`
- `0x18004b70c`
- `0x18004f76c`
- `0x180053324`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18004481a`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004481a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004429e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800442b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800442b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800442a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044324`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800443bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004444b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800445ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004463e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800447e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800448d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800448ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800442a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044324`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800443bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004444b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800445ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004463e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800447e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800448d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800448ed`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800442c9`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800442c9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180044361`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180044361`

## string_xrefs

- `0x18004437f`: `Failed to open '%ws'.`
- `0x1800444db`: `Failed to create appx bundle factory.`
- `0x180044254`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800442f1`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004438e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004441a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800444ea`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044582`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800445fb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800447af`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800448a5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044245`: `Failed to create package adapter.`
- `0x1800445ec`: `Failed to create payload adapter for package reader.`
- `0x180044573`: `Failed to create appx bundle reader.`
- `0x18004440b`: `Failed to create appx factory.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(
        const WCHAR *a1,
        int a2,
        __int64 a3,
        MsixPackage::Provisioning::Library::MsixPackageAdapter **a4)
{
  int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  HRESULT v9; // ebx
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v10; // rbx
  IStream **v11; // r12
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  HRESULT v14; // edi
  char *v15; // rsi
  __int64 v16; // rcx
  int v17; // edi
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, IStream *, char *); // rsi
  struct IAppxPackageReader **v20; // r15
  _QWORD *v21; // rcx
  _QWORD *v22; // rdx
  char *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // esi
  __int64 v27; // r8
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, IStream *, char *); // r13
  _QWORD *v30; // rcx
  int v31; // edi
  struct IAppxPackageReader *v32; // r8
  int v33; // edi
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v34; // rcx
  char *v35; // rsi
  __int64 v36; // rdi
  struct IAppxPackageReader *v37; // rcx
  struct IAppxPackageReader *v38; // rdi
  __int64 v39; // rcx
  char *v40; // rdi
  __int64 v41; // rcx
  int v42; // esi
  unsigned __int64 v43; // rdi
  unsigned __int64 v44; // r8
  int v45; // eax
  int IsNotAnOptionalPackage; // edi
  char *v47; // [rsp+28h] [rbp-100h]
  HLOCAL hMem; // [rsp+30h] [rbp-F8h] BYREF
  int v49; // [rsp+38h] [rbp-F0h]
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v50; // [rsp+40h] [rbp-E8h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v51; // [rsp+48h] [rbp-E0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+50h] [rbp-D8h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter **v53; // [rsp+58h] [rbp-D0h]
  _QWORD v54[3]; // [rsp+60h] [rbp-C8h] BYREF
  __int16 v55; // [rsp+78h] [rbp-B0h]
  __int64 v56; // [rsp+88h] [rbp-A0h]
  __int64 v57; // [rsp+90h] [rbp-98h]
  __int16 v58; // [rsp+98h] [rbp-90h]
  __int64 v59; // [rsp+A8h] [rbp-80h]
  __int64 v60; // [rsp+B0h] [rbp-78h]
  __int64 v61; // [rsp+B8h] [rbp-70h]
  __int128 v62; // [rsp+C0h] [rbp-68h]
  __int64 v63; // [rsp+D0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v53 = a4;
  v49 = a2;
  if ( !a1 || !a3 || !a4 )
    return 2147500035LL;
  try
  {
    *a4 = 0;
    hMem = 0;
    v51 = 0;
    v6 = MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(
           a3,
           &v51);
    if ( v6 >= 0 )
    {
      hMem = 0;
      v9 = PathAllocCanonicalize(a1, 1u, (PWSTR *)&hMem);
      if ( v9 >= 0 )
      {
        v10 = v51;
        v11 = (IStream **)((char *)v51 + 224);
        v12 = *((_QWORD *)v51 + 28);
        *((_QWORD *)v51 + 28) = 0;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v14 = SHCreateStreamOnFileW((LPCWSTR)hMem, 0, v11);
        if ( v14 >= 0 )
        {
          v15 = (char *)v10 + 232;
          v16 = *((_QWORD *)v10 + 29);
          *((_QWORD *)v10 + 29) = 0;
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v17 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(
                  (MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216),
                  v13,
                  (struct _GUID *)((char *)v10 + 232));
          if ( v17 >= 0 )
          {
            v18 = *(_QWORD *)v15;
            v19 = *(int (__fastcall **)(__int64, IStream *, char *))(**(_QWORD **)v15 + 32LL);
            v20 = (struct IAppxPackageReader **)((char *)v10 + 240);
            v21 = (_QWORD *)*((_QWORD *)v10 + 30);
            *((_QWORD *)v10 + 30) = 0;
            if ( v21 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
            if ( v19(v18, *v11, (char *)v10 + 240) < 0 )
            {
              v23 = (char *)v10 + 248;
              v24 = *((_QWORD *)v10 + 31);
              *((_QWORD *)v10 + 31) = 0;
              if ( v24 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              v26 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(
                      (MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216),
                      v22,
                      (struct _GUID *)((char *)v10 + 248));
              if ( v26 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x608,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v26,
                  (int)"Failed to create appx bundle factory.",
                  v47);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v26;
              }
              v28 = *(_QWORD *)v23;
              v29 = *(__int64 (__fastcall **)(__int64, IStream *, char *))(**(_QWORD **)v23 + 32LL);
              v30 = (_QWORD *)*((_QWORD *)v10 + 32);
              *((_QWORD *)v10 + 32) = 0;
              if ( v30 )
                (*(void (__fastcall **)(_QWORD *, __int64, __int64, _QWORD))(*v30 + 16LL))(v30, v25, v27, *v30);
              v31 = v29(v28, *v11, (char *)v10 + 256);
              if ( v31 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x60E,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v31,
                  (int)"Failed to create appx bundle reader.",
                  v47);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v31;
              }
            }
            v32 = *v20;
            if ( *v20 )
            {
              v50 = 0;
              v33 = MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)a3,
                      0,
                      v32,
                      &v50);
              if ( v33 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x61B,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v33,
                  (int)"Failed to create payload adapter for package reader.",
                  v47);
                if ( v50 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v33;
              }
              v34 = v50;
              v35 = (char *)v50 + 56;
              if ( *((_QWORD *)v50 + 10) >= 8u )
                v35 = *(char **)v35;
              v36 = *((_QWORD *)v10 + 26);
              *((_QWORD *)v10 + 26) = v50;
              if ( v34 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v34 + 8LL))(v34);
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              v37 = (struct IAppxPackageReader *)*((_QWORD *)v50 + 17);
              v38 = *v20;
              *v20 = v37;
              if ( v37 )
                ((void (__fastcall *)(struct IAppxPackageReader *))v37->lpVtbl->AddRef)(v37);
              if ( v38 )
                ((void (__fastcall *)(struct IAppxPackageReader *))v38->lpVtbl->Release)(v38);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
            }
            else
            {
              v39 = *((_QWORD *)v10 + 32);
              v54[0] = a3;
              v54[1] = 0;
              v54[2] = hMem;
              v57 = 7;
              v56 = 0;
              v55 = 0;
              v60 = 7;
              v59 = 0;
              v58 = 0;
              v61 = v39;
              if ( v39 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
              v62 = 0;
              v63 = 0;
              v40 = (char *)v10 + 216;
              v41 = *((_QWORD *)v10 + 27);
              *((_QWORD *)v10 + 27) = 0;
              if ( v41 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              v42 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(
                      (struct MsixPackage::Provisioning::Library::PackageSource *)v54,
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)a3,
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **)v10 + 27);
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x62A,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v42,
                  (int)"Failed to initialize package adapter.",
                  v47);
                MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v54);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v42;
              }
              v35 = *(char **)(*(_QWORD *)v40 + 64LL);
              *((_DWORD *)v10 + 68) = *(unsigned __int8 *)(*(_QWORD *)v40 + 72LL);
              MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v54);
            }
            pperrinfo = 0;
            GetErrorInfo(0, &pperrinfo);
            v43 = -1;
            if ( *(_WORD *)v35 )
            {
              v44 = -1;
              do
                ++v44;
              while ( *(_WORD *)&v35[2 * v44] );
            }
            else
            {
              v44 = 0;
            }
            std::wstring::assign((_QWORD *)v10 + 6, v35, v44);
            if ( *(_WORD *)hMem )
            {
              do
                ++v43;
              while ( *((_WORD *)hMem + v43) );
            }
            else
            {
              v43 = 0;
            }
            std::wstring::assign((_QWORD *)v10 + 10, (char *)hMem, v43);
            *((_DWORD *)v10 + 8) = 1;
            v45 = v49;
            *((_DWORD *)v10 + 9) = v49;
            if ( v45
              || (IsNotAnOptionalPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::ValidateMainPackageIsNotAnOptionalPackage(v10),
                  IsNotAnOptionalPackage >= 0) )
            {
              *v53 = v10;
              if ( hMem )
                LocalFree(hMem);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x644,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                (const char *)(unsigned int)IsNotAnOptionalPackage,
                (int)"Failed to validate main package parameter is not an optional package.",
                v47);
              (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
              if ( hMem )
                LocalFree(hMem);
              return (unsigned int)IsNotAnOptionalPackage;
            }
          }
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5FE,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v17,
            (int)"Failed to create appx factory.",
            v47);
          if ( v10 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( hMem )
            LocalFree(hMem);
          result = (unsigned int)v17;
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5FA,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v14,
            (int)"Failed to open '%ws'.",
            (const char *)hMem);
          if ( v10 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( hMem )
            LocalFree(hMem);
          result = (unsigned int)v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5F2,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v9,
          (int)"Failed to canonicalize '%ws'.",
          (const char *)a1);
        if ( v51 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v51 + 16LL))(v51);
        if ( hMem )
          LocalFree(hMem);
        result = (unsigned int)v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5EB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v6,
        (int)"Failed to create package adapter.",
        v47);
      if ( v51 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v51 + 16LL))(v51);
      result = (unsigned int)v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x64B,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800441c8  push    rbx
0x1800441ca  push    rsi
0x1800441cb  push    rdi
0x1800441cc  push    r12
0x1800441ce  push    r13
0x1800441d0  push    r14
0x1800441d2  push    r15
0x1800441d4  sub     rsp, 0F0h
0x1800441db  mov     rax, cs:__security_cookie
0x1800441e2  xor     rax, rsp
0x1800441e5  mov     [rsp+128h+var_48], rax
0x1800441ed  mov     rax, r9
0x1800441f0  mov     [rsp+128h+var_D0], rax
0x1800441f5  mov     r14, r8
0x1800441f8  mov     [rsp+128h+var_F0], edx
0x1800441fc  mov     rdi, rcx
0x1800441ff  xor     r15d, r15d
0x180044202  test    rcx, rcx
0x180044205  jz      loc_1800448F7
0x18004420b  test    r8, r8
0x18004420e  jz      loc_1800448F7
0x180044214  test    rax, rax
0x180044217  jz      loc_1800448F7
0x18004421d  mov     [r9], r15
0x180044220  mov     [rsp+128h+hMem], r15
0x180044225  mov     [rsp+128h+var_E0], r15
0x18004422a  lea     rdx, [rsp+128h+var_E0]
0x18004422f  mov     rcx, r8
0x180044232  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180044237  mov     ebx, eax
0x180044239  test    eax, eax
0x18004423b  jns     short loc_180044294
0x18004423d  mov     rcx, [rsp+128h]; this
0x180044245  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x18004424c  mov     qword ptr [rsp+128h+var_108], rax; int
0x180044251  mov     r9d, ebx; char *
0x180044254  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004425b  mov     edx, 5EBh; void *
0x180044260  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044265  nop
0x180044266  mov     rcx, [rsp+128h+var_E0]
0x18004426b  test    rcx, rcx
0x18004426e  jz      short loc_18004427D
0x180044270  mov     rax, [rcx]
0x180044273  mov     rax, [rax+10h]
0x180044277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004427c  nop
0x18004427d  mov     rcx, [rsp+128h+hMem]; hMem
0x180044282  test    rcx, rcx
0x180044285  jz      short loc_18004428D
0x180044287  call    cs:__imp_LocalFree
0x18004428d  mov     eax, ebx
0x18004428f  jmp     loc_180044902
0x180044294  mov     rsi, [rsp+128h+hMem]
0x180044299  test    rsi, rsi
0x18004429c  jz      short loc_1800442B7
0x18004429e  call    cs:__imp_GetLastError
0x1800442a4  mov     ebx, eax
0x1800442a6  mov     rcx, rsi; hMem
0x1800442a9  call    cs:__imp_LocalFree
0x1800442af  mov     ecx, ebx; dwErrCode
0x1800442b1  call    cs:__imp_SetLastError
0x1800442b7  mov     [rsp+128h+hMem], r15
0x1800442bc  lea     r8, [rsp+128h+hMem]; ppszPathOut
0x1800442c1  mov     edx, 1; dwFlags
0x1800442c6  mov     rcx, rdi; pszPathIn
0x1800442c9  call    cs:__imp_PathAllocCanonicalize
0x1800442cf  mov     ebx, eax
0x1800442d1  test    eax, eax
0x1800442d3  jns     short loc_180044331
0x1800442d5  mov     rcx, [rsp+128h]; this
0x1800442dd  mov     [rsp+128h+var_100], rdi; char *
0x1800442e2  lea     rax, aFailedToCanoni; "Failed to canonicalize '%ws'."
0x1800442e9  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800442ee  mov     r9d, ebx; char *
0x1800442f1  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800442f8  mov     edx, 5F2h; void *
0x1800442fd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044302  nop
0x180044303  mov     rcx, [rsp+128h+var_E0]
0x180044308  test    rcx, rcx
0x18004430b  jz      short loc_18004431A
0x18004430d  mov     rax, [rcx]
0x180044310  mov     rax, [rax+10h]
0x180044314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044319  nop
0x18004431a  mov     rcx, [rsp+128h+hMem]; hMem
0x18004431f  test    rcx, rcx
0x180044322  jz      short loc_18004432A
0x180044324  call    cs:__imp_LocalFree
0x18004432a  mov     eax, ebx
0x18004432c  jmp     loc_180044902
0x180044331  mov     rbx, [rsp+128h+var_E0]
0x180044336  lea     r12, [rbx+0E0h]
0x18004433d  mov     rcx, [r12]
0x180044341  mov     [r12], r15
0x180044345  test    rcx, rcx
0x180044348  jz      short loc_180044357
0x18004434a  mov     rax, [rcx]
0x18004434d  mov     rax, [rax+10h]
0x180044351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044356  nop
0x180044357  mov     r8, r12; ppstm
0x18004435a  xor     edx, edx; grfMode
0x18004435c  mov     rcx, [rsp+128h+hMem]; pszFile
0x180044361  call    cs:__imp_SHCreateStreamOnFileW
0x180044367  mov     edi, eax
0x180044369  test    eax, eax
0x18004436b  jns     short loc_1800443CC
0x18004436d  mov     rcx, [rsp+128h]; this
0x180044375  mov     rdx, [rsp+128h+hMem]
0x18004437a  mov     [rsp+128h+var_100], rdx; char *
0x18004437f  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180044386  mov     qword ptr [rsp+128h+var_108], rax; int
0x18004438b  mov     r9d, edi; char *
0x18004438e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044395  mov     edx, 5FAh; void *
0x18004439a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004439f  nop
0x1800443a0  test    rbx, rbx
0x1800443a3  jz      short loc_1800443B5
0x1800443a5  mov     rax, [rbx]
0x1800443a8  mov     rcx, rbx
0x1800443ab  mov     rax, [rax+10h]
0x1800443af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443b4  nop
0x1800443b5  mov     rcx, [rsp+128h+hMem]; hMem
0x1800443ba  test    rcx, rcx
0x1800443bd  jz      short loc_1800443C5
0x1800443bf  call    cs:__imp_LocalFree
0x1800443c5  mov     eax, edi
0x1800443c7  jmp     loc_180044902
0x1800443cc  lea     r13, [r14+0D8h]
0x1800443d3  lea     rsi, [rbx+0E8h]
0x1800443da  mov     rcx, [rsi]
0x1800443dd  mov     [rsi], r15
0x1800443e0  test    rcx, rcx
0x1800443e3  jz      short loc_1800443F2
0x1800443e5  mov     rax, [rcx]
0x1800443e8  mov     rax, [rax+10h]
0x1800443ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443f1  nop
0x1800443f2  mov     r8, rsi
0x1800443f5  mov     rcx, r13; this
0x1800443f8  call    ??$CreateFactory@UIAppxFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(_GUID const &,IAppxFactory * *)
0x1800443fd  mov     edi, eax
0x1800443ff  test    eax, eax
0x180044401  jns     short loc_180044458
0x180044403  mov     rcx, [rsp+128h]; this
0x18004440b  lea     rax, aFailedToCreate_28; "Failed to create appx factory."
0x180044412  mov     qword ptr [rsp+128h+var_108], rax; int
0x180044417  mov     r9d, edi; char *
0x18004441a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044421  mov     edx, 5FEh; void *
0x180044426  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004442b  nop
0x18004442c  test    rbx, rbx
0x18004442f  jz      short loc_180044441
0x180044431  mov     rax, [rbx]
0x180044434  mov     rcx, rbx
0x180044437  mov     rax, [rax+10h]
0x18004443b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044440  nop
0x180044441  mov     rcx, [rsp+128h+hMem]; hMem
0x180044446  test    rcx, rcx
0x180044449  jz      short loc_180044451
0x18004444b  call    cs:__imp_LocalFree
0x180044451  mov     eax, edi
0x180044453  jmp     loc_180044902
0x180044458  mov     rdi, [rsi]
0x18004445b  mov     rax, [rdi]
0x18004445e  mov     rsi, [rax+20h]
0x180044462  lea     r15, [rbx+0F0h]
0x180044469  mov     rcx, [r15]
0x18004446c  mov     qword ptr [r15], 0
0x180044473  test    rcx, rcx
0x180044476  jz      short loc_180044485
0x180044478  mov     rdx, [rcx]
0x18004447b  mov     rax, [rdx+10h]
0x18004447f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044484  nop
0x180044485  mov     r8, r15
0x180044488  mov     rdx, [r12]
0x18004448c  mov     rcx, rdi
0x18004448f  mov     rax, rsi
0x180044492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044497  test    eax, eax
0x180044499  jns     loc_1800445BB
0x18004449f  lea     rdi, [rbx+0F8h]
0x1800444a6  mov     rcx, [rdi]
0x1800444a9  mov     qword ptr [rdi], 0
0x1800444b0  test    rcx, rcx
0x1800444b3  jz      short loc_1800444C2
0x1800444b5  mov     rax, [rcx]
0x1800444b8  mov     rax, [rax+10h]
0x1800444bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444c1  nop
0x1800444c2  mov     r8, rdi
0x1800444c5  mov     rcx, r13
0x1800444c8  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x1800444cd  mov     esi, eax
0x1800444cf  test    eax, eax
0x1800444d1  jns     short loc_180044523
0x1800444d3  mov     rcx, [rsp+128h]; this
0x1800444db  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x1800444e2  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800444e7  mov     r9d, esi; char *
0x1800444ea  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800444f1  mov     edx, 608h; void *
0x1800444f6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800444fb  nop
0x1800444fc  mov     rax, [rbx]
0x1800444ff  mov     rcx, rbx
0x180044502  mov     rax, [rax+10h]
0x180044506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004450b  nop
0x18004450c  mov     rcx, [rsp+128h+hMem]; hMem
0x180044511  test    rcx, rcx
0x180044514  jz      short loc_18004451C
0x180044516  call    cs:__imp_LocalFree
0x18004451c  mov     eax, esi
0x18004451e  jmp     loc_180044902
0x180044523  mov     rsi, [rdi]
0x180044526  mov     rax, [rsi]
0x180044529  mov     r13, [rax+20h]
0x18004452d  lea     rdi, [rbx+100h]
0x180044534  mov     rcx, [rdi]
0x180044537  mov     qword ptr [rdi], 0
0x18004453e  test    rcx, rcx
0x180044541  jz      short loc_180044550
0x180044543  mov     r9, [rcx]
0x180044546  mov     rax, [r9+10h]
0x18004454a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004454f  nop
0x180044550  mov     r8, rdi
0x180044553  mov     rdx, [r12]
0x180044557  mov     rcx, rsi
0x18004455a  mov     rax, r13
0x18004455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044562  mov     edi, eax
0x180044564  xor     r12d, r12d
0x180044567  test    eax, eax
0x180044569  jns     short loc_1800445BE
0x18004456b  mov     rcx, [rsp+128h]; this
0x180044573  lea     rax, aFailedToCreate_27; "Failed to create appx bundle reader."
0x18004457a  mov     qword ptr [rsp+128h+var_108], rax; int
0x18004457f  mov     r9d, edi; char *
0x180044582  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044589  mov     edx, 60Eh; void *
0x18004458e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044593  nop
0x180044594  mov     rax, [rbx]
0x180044597  mov     rcx, rbx
0x18004459a  mov     rax, [rax+10h]
0x18004459e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445a3  nop
0x1800445a4  mov     rcx, [rsp+128h+hMem]; hMem
0x1800445a9  test    rcx, rcx
0x1800445ac  jz      short loc_1800445B4
0x1800445ae  call    cs:__imp_LocalFree
0x1800445b4  mov     eax, edi
0x1800445b6  jmp     loc_180044902
0x1800445bb  xor     r12d, r12d
0x1800445be  mov     r8, [r15]; struct IAppxPackageReader *
0x1800445c1  test    r8, r8
0x1800445c4  jz      loc_1800446E6
0x1800445ca  mov     [rsp+128h+var_E8], r12
0x1800445cf  lea     r9, [rsp+128h+var_E8]; struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **
0x1800445d4  xor     edx, edx; int
0x1800445d6  mov     rcx, r14; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x1800445d9  call    ?CreateForPackageReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@HPEAUIAppxPackageReader@@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,IAppxPackageReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x1800445de  mov     edi, eax
0x1800445e0  test    eax, eax
0x1800445e2  jns     short loc_18004464B
0x1800445e4  mov     rcx, [rsp+128h]; this
0x1800445ec  lea     rax, aFailedToCreate_20; "Failed to create payload adapter for pa"...
0x1800445f3  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800445f8  mov     r9d, edi; char *
0x1800445fb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044602  mov     edx, 61Bh; void *
0x180044607  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004460c  nop
0x18004460d  mov     rcx, [rsp+128h+var_E8]
0x180044612  test    rcx, rcx
0x180044615  jz      short loc_180044624
0x180044617  mov     rax, [rcx]
0x18004461a  mov     rax, [rax+10h]
0x18004461e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044623  nop
0x180044624  mov     rax, [rbx]
0x180044627  mov     rcx, rbx
0x18004462a  mov     rax, [rax+10h]
0x18004462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044633  nop
0x180044634  mov     rcx, [rsp+128h+hMem]; hMem
0x180044639  test    rcx, rcx
0x18004463c  jz      short loc_180044644
0x18004463e  call    cs:__imp_LocalFree
0x180044644  mov     eax, edi
0x180044646  jmp     loc_180044902
  ... truncated ...
```

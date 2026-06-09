# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(ushort const *,MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x18004804c`
- end: `0x18004880a`
- name: `?CreateFromPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGW4APPX_PACKAGE_TARGET_TYPE@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z`
- size: `1982`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180051db0`
- `0x18005207c`

## callees

- `0x18001d160`
- `0x1800344e4`
- `0x180035998`
- `0x18003d4ec`
- `0x18003e780`
- `0x180044670`
- `0x18004804c`
- `0x18004f924`
- `0x180053b30`
- `0x180057830`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800486ec`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800486ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048128`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048147`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004810b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800481c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004826d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800482ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800483d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004846e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048504`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800486b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004810b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800481c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004826d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800482ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800483d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004846e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048504`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800486b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800487cb`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180048165`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180048165`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180048209`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180048209`

## string_xrefs

- `0x18004822d`: `Failed to open '%ws'.`
- `0x180048395`: `Failed to create appx bundle factory.`
- `0x1800480d8`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048193`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004823c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800482ce`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800483a4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048442`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800484c1`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004867b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004877d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800480c9`: `Failed to create package adapter.`
- `0x180048433`: `Failed to create appx bundle reader.`
- `0x1800482bf`: `Failed to create appx factory.`
- `0x1800484b2`: `Failed to create payload adapter for package reader.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
  HRESULT v13; // edi
  char *v14; // rsi
  __int64 v15; // rcx
  int v16; // edi
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, IStream *, char *); // rsi
  struct IAppxPackageReader **v19; // r15
  _QWORD *v20; // rcx
  char *v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // r8
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, IStream *, char *); // r13
  _QWORD *v28; // rcx
  int v29; // edi
  struct IAppxPackageReader *v30; // r8
  int v31; // edi
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v32; // rcx
  _QWORD *v33; // rsi
  __int64 v34; // rdi
  struct IAppxPackageReader *v35; // rcx
  struct IAppxPackageReader *v36; // rdi
  __int64 v37; // rcx
  char *v38; // rdi
  __int64 v39; // rcx
  int v40; // esi
  __int64 v41; // rdi
  __int64 v42; // r8
  int v43; // eax
  int IsNotAnOptionalPackage; // edi
  char *v45; // [rsp+28h] [rbp-100h]
  HLOCAL hMem; // [rsp+30h] [rbp-F8h] BYREF
  int v47; // [rsp+38h] [rbp-F0h]
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v48; // [rsp+40h] [rbp-E8h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v49; // [rsp+48h] [rbp-E0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+50h] [rbp-D8h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter **v51; // [rsp+58h] [rbp-D0h]
  _QWORD v52[3]; // [rsp+60h] [rbp-C8h] BYREF
  __int16 v53; // [rsp+78h] [rbp-B0h]
  __int64 v54; // [rsp+88h] [rbp-A0h]
  __int64 v55; // [rsp+90h] [rbp-98h]
  __int16 v56; // [rsp+98h] [rbp-90h]
  __int64 v57; // [rsp+A8h] [rbp-80h]
  __int64 v58; // [rsp+B0h] [rbp-78h]
  __int64 v59; // [rsp+B8h] [rbp-70h]
  __int128 v60; // [rsp+C0h] [rbp-68h]
  __int64 v61; // [rsp+D0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v51 = a4;
  v47 = a2;
  if ( !a1 || !a3 || !a4 )
    return 2147500035LL;
  try
  {
    *a4 = 0;
    hMem = 0;
    v49 = 0;
    v6 = MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(
           a3,
           &v49);
    if ( v6 >= 0 )
    {
      hMem = 0;
      v9 = PathAllocCanonicalize(a1, 1u, (PWSTR *)&hMem);
      if ( v9 >= 0 )
      {
        v10 = v49;
        v11 = (IStream **)((char *)v49 + 224);
        v12 = *((_QWORD *)v49 + 28);
        *((_QWORD *)v49 + 28) = 0;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v13 = SHCreateStreamOnFileW((LPCWSTR)hMem, 0, v11);
        if ( v13 >= 0 )
        {
          v14 = (char *)v10 + 232;
          v15 = *((_QWORD *)v10 + 29);
          *((_QWORD *)v10 + 29) = 0;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v16 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>((MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216));
          if ( v16 >= 0 )
          {
            v17 = *(_QWORD *)v14;
            v18 = *(int (__fastcall **)(__int64, IStream *, char *))(**(_QWORD **)v14 + 32LL);
            v19 = (struct IAppxPackageReader **)((char *)v10 + 240);
            v20 = (_QWORD *)*((_QWORD *)v10 + 30);
            *((_QWORD *)v10 + 30) = 0;
            if ( v20 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v20 + 16LL))(v20, *v20);
            if ( v18(v17, *v11, (char *)v10 + 240) < 0 )
            {
              v21 = (char *)v10 + 248;
              v22 = *((_QWORD *)v10 + 31);
              *((_QWORD *)v10 + 31) = 0;
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              v24 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>((MsixPackage::Provisioning::Library::MsixAppxPackaging *)(a3 + 216));
              if ( v24 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x608,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v24,
                  (int)"Failed to create appx bundle factory.",
                  v45);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v24;
              }
              v26 = *(_QWORD *)v21;
              v27 = *(__int64 (__fastcall **)(__int64, IStream *, char *))(**(_QWORD **)v21 + 32LL);
              v28 = (_QWORD *)*((_QWORD *)v10 + 32);
              *((_QWORD *)v10 + 32) = 0;
              if ( v28 )
                (*(void (__fastcall **)(_QWORD *, __int64, __int64, _QWORD))(*v28 + 16LL))(v28, v23, v25, *v28);
              v29 = v27(v26, *v11, (char *)v10 + 256);
              if ( v29 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x60E,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v29,
                  (int)"Failed to create appx bundle reader.",
                  v45);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v29;
              }
            }
            v30 = *v19;
            if ( *v19 )
            {
              v48 = 0;
              v31 = MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)a3,
                      0,
                      v30,
                      &v48);
              if ( v31 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x61B,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v31,
                  (int)"Failed to create payload adapter for package reader.",
                  v45);
                if ( v48 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v48 + 16LL))(v48);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v31;
              }
              v32 = v48;
              v33 = (_QWORD *)((char *)v48 + 56);
              if ( *((_QWORD *)v48 + 10) >= 8u )
                v33 = (_QWORD *)*v33;
              v34 = *((_QWORD *)v10 + 26);
              *((_QWORD *)v10 + 26) = v48;
              if ( v32 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v32 + 8LL))(v32);
              if ( v34 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              v35 = (struct IAppxPackageReader *)*((_QWORD *)v48 + 17);
              v36 = *v19;
              *v19 = v35;
              if ( v35 )
                ((void (__fastcall *)(struct IAppxPackageReader *))v35->lpVtbl->AddRef)(v35);
              if ( v36 )
                ((void (__fastcall *)(struct IAppxPackageReader *))v36->lpVtbl->Release)(v36);
              if ( v48 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v48 + 16LL))(v48);
            }
            else
            {
              v37 = *((_QWORD *)v10 + 32);
              v52[0] = a3;
              v52[1] = 0;
              v52[2] = hMem;
              v55 = 7;
              v54 = 0;
              v53 = 0;
              v58 = 7;
              v57 = 0;
              v56 = 0;
              v59 = v37;
              if ( v37 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
              v60 = 0;
              v61 = 0;
              v38 = (char *)v10 + 216;
              v39 = *((_QWORD *)v10 + 27);
              *((_QWORD *)v10 + 27) = 0;
              if ( v39 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
              v40 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(
                      (struct MsixPackage::Provisioning::Library::PackageSource *)v52,
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)a3,
                      (struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **)v10 + 27);
              if ( v40 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x62A,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v40,
                  (int)"Failed to initialize package adapter.",
                  v45);
                MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v52);
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
                if ( hMem )
                  LocalFree(hMem);
                return (unsigned int)v40;
              }
              v33 = *(_QWORD **)(*(_QWORD *)v38 + 64LL);
              *((_DWORD *)v10 + 68) = *(unsigned __int8 *)(*(_QWORD *)v38 + 72LL);
              MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v52);
            }
            pperrinfo = 0;
            GetErrorInfo(0, &pperrinfo);
            v41 = -1;
            if ( *(_WORD *)v33 )
            {
              v42 = -1;
              do
                ++v42;
              while ( *((_WORD *)v33 + v42) );
            }
            std::wstring::assign((char *)v10 + 48, v33);
            if ( *(_WORD *)hMem )
            {
              do
                ++v41;
              while ( *((_WORD *)hMem + v41) );
            }
            std::wstring::assign((char *)v10 + 80, hMem);
            *((_DWORD *)v10 + 8) = 1;
            v43 = v47;
            *((_DWORD *)v10 + 9) = v47;
            if ( v43
              || (IsNotAnOptionalPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::ValidateMainPackageIsNotAnOptionalPackage(v10),
                  IsNotAnOptionalPackage >= 0) )
            {
              *v51 = v10;
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
                v45);
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
            (const char *)(unsigned int)v16,
            (int)"Failed to create appx factory.",
            v45);
          if ( v10 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( hMem )
            LocalFree(hMem);
          result = (unsigned int)v16;
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5FA,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v13,
            (int)"Failed to open '%ws'.",
            (const char *)hMem);
          if ( v10 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( hMem )
            LocalFree(hMem);
          result = (unsigned int)v13;
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
        if ( v49 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v49 + 16LL))(v49);
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
        v45);
      if ( v49 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v49 + 16LL))(v49);
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
0x18004804c  push    rbx
0x18004804e  push    rsi
0x18004804f  push    rdi
0x180048050  push    r12
0x180048052  push    r13
0x180048054  push    r14
0x180048056  push    r15
0x180048058  sub     rsp, 0F0h
0x18004805f  mov     rax, cs:__security_cookie
0x180048066  xor     rax, rsp
0x180048069  mov     [rsp+128h+var_48], rax
0x180048071  mov     rax, r9
0x180048074  mov     [rsp+128h+var_D0], rax
0x180048079  mov     r14, r8
0x18004807c  mov     [rsp+128h+var_F0], edx
0x180048080  mov     rdi, rcx
0x180048083  xor     r15d, r15d
0x180048086  test    rcx, rcx
0x180048089  jz      loc_1800487DB
0x18004808f  test    r8, r8
0x180048092  jz      loc_1800487DB
0x180048098  test    rax, rax
0x18004809b  jz      loc_1800487DB
0x1800480a1  mov     [r9], r15
0x1800480a4  mov     [rsp+128h+hMem], r15
0x1800480a9  mov     [rsp+128h+var_E0], r15
0x1800480ae  lea     rdx, [rsp+128h+var_E0]
0x1800480b3  mov     rcx, r8
0x1800480b6  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x1800480bb  mov     ebx, eax
0x1800480bd  test    eax, eax
0x1800480bf  jns     short loc_18004811E
0x1800480c1  mov     rcx, [rsp+128h]; this
0x1800480c9  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x1800480d0  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800480d5  mov     r9d, ebx; char *
0x1800480d8  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800480df  mov     edx, 5EBh; void *
0x1800480e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800480e9  nop
0x1800480ea  mov     rcx, [rsp+128h+var_E0]
0x1800480ef  test    rcx, rcx
0x1800480f2  jz      short loc_180048101
0x1800480f4  mov     rax, [rcx]
0x1800480f7  mov     rax, [rax+10h]
0x1800480fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048100  nop
0x180048101  mov     rcx, [rsp+128h+hMem]; hMem
0x180048106  test    rcx, rcx
0x180048109  jz      short loc_180048117
0x18004810b  call    cs:__imp_LocalFree
0x180048112  nop     dword ptr [rax+rax+00h]
0x180048117  mov     eax, ebx
0x180048119  jmp     loc_1800487E6
0x18004811e  mov     rsi, [rsp+128h+hMem]
0x180048123  test    rsi, rsi
0x180048126  jz      short loc_180048153
0x180048128  call    cs:__imp_GetLastError
0x18004812f  nop     dword ptr [rax+rax+00h]
0x180048134  mov     ebx, eax
0x180048136  mov     rcx, rsi; hMem
0x180048139  call    cs:__imp_LocalFree
0x180048140  nop     dword ptr [rax+rax+00h]
0x180048145  mov     ecx, ebx; dwErrCode
0x180048147  call    cs:__imp_SetLastError
0x18004814e  nop     dword ptr [rax+rax+00h]
0x180048153  mov     [rsp+128h+hMem], r15
0x180048158  lea     r8, [rsp+128h+hMem]; ppszPathOut
0x18004815d  mov     edx, 1; dwFlags
0x180048162  mov     rcx, rdi; pszPathIn
0x180048165  call    cs:__imp_PathAllocCanonicalize
0x18004816c  nop     dword ptr [rax+rax+00h]
0x180048171  mov     ebx, eax
0x180048173  test    eax, eax
0x180048175  jns     short loc_1800481D9
0x180048177  mov     rcx, [rsp+128h]; this
0x18004817f  mov     [rsp+128h+var_100], rdi; char *
0x180048184  lea     rax, aFailedToCanoni; "Failed to canonicalize '%ws'."
0x18004818b  mov     qword ptr [rsp+128h+var_108], rax; int
0x180048190  mov     r9d, ebx; char *
0x180048193  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004819a  mov     edx, 5F2h; void *
0x18004819f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800481a4  nop
0x1800481a5  mov     rcx, [rsp+128h+var_E0]
0x1800481aa  test    rcx, rcx
0x1800481ad  jz      short loc_1800481BC
0x1800481af  mov     rax, [rcx]
0x1800481b2  mov     rax, [rax+10h]
0x1800481b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481bb  nop
0x1800481bc  mov     rcx, [rsp+128h+hMem]; hMem
0x1800481c1  test    rcx, rcx
0x1800481c4  jz      short loc_1800481D2
0x1800481c6  call    cs:__imp_LocalFree
0x1800481cd  nop     dword ptr [rax+rax+00h]
0x1800481d2  mov     eax, ebx
0x1800481d4  jmp     loc_1800487E6
0x1800481d9  mov     rbx, [rsp+128h+var_E0]
0x1800481de  lea     r12, [rbx+0E0h]
0x1800481e5  mov     rcx, [r12]
0x1800481e9  mov     [r12], r15
0x1800481ed  test    rcx, rcx
0x1800481f0  jz      short loc_1800481FF
0x1800481f2  mov     rax, [rcx]
0x1800481f5  mov     rax, [rax+10h]
0x1800481f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481fe  nop
0x1800481ff  mov     r8, r12; ppstm
0x180048202  xor     edx, edx; grfMode
0x180048204  mov     rcx, [rsp+128h+hMem]; pszFile
0x180048209  call    cs:__imp_SHCreateStreamOnFileW
0x180048210  nop     dword ptr [rax+rax+00h]
0x180048215  mov     edi, eax
0x180048217  test    eax, eax
0x180048219  jns     short loc_180048280
0x18004821b  mov     rcx, [rsp+128h]; this
0x180048223  mov     rdx, [rsp+128h+hMem]
0x180048228  mov     [rsp+128h+var_100], rdx; char *
0x18004822d  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180048234  mov     qword ptr [rsp+128h+var_108], rax; int
0x180048239  mov     r9d, edi; char *
0x18004823c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048243  mov     edx, 5FAh; void *
0x180048248  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004824d  nop
0x18004824e  test    rbx, rbx
0x180048251  jz      short loc_180048263
0x180048253  mov     rax, [rbx]
0x180048256  mov     rcx, rbx
0x180048259  mov     rax, [rax+10h]
0x18004825d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048262  nop
0x180048263  mov     rcx, [rsp+128h+hMem]; hMem
0x180048268  test    rcx, rcx
0x18004826b  jz      short loc_180048279
0x18004826d  call    cs:__imp_LocalFree
0x180048274  nop     dword ptr [rax+rax+00h]
0x180048279  mov     eax, edi
0x18004827b  jmp     loc_1800487E6
0x180048280  lea     r13, [r14+0D8h]
0x180048287  lea     rsi, [rbx+0E8h]
0x18004828e  mov     rcx, [rsi]
0x180048291  mov     [rsi], r15
0x180048294  test    rcx, rcx
0x180048297  jz      short loc_1800482A6
0x180048299  mov     rax, [rcx]
0x18004829c  mov     rax, [rax+10h]
0x1800482a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482a5  nop
0x1800482a6  mov     r8, rsi
0x1800482a9  mov     rcx, r13; this
0x1800482ac  call    ??$CreateFactory@UIAppxFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(_GUID const &,IAppxFactory * *)
0x1800482b1  mov     edi, eax
0x1800482b3  test    eax, eax
0x1800482b5  jns     short loc_180048312
0x1800482b7  mov     rcx, [rsp+128h]; this
0x1800482bf  lea     rax, aFailedToCreate_28; "Failed to create appx factory."
0x1800482c6  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800482cb  mov     r9d, edi; char *
0x1800482ce  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800482d5  mov     edx, 5FEh; void *
0x1800482da  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800482df  nop
0x1800482e0  test    rbx, rbx
0x1800482e3  jz      short loc_1800482F5
0x1800482e5  mov     rax, [rbx]
0x1800482e8  mov     rcx, rbx
0x1800482eb  mov     rax, [rax+10h]
0x1800482ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f4  nop
0x1800482f5  mov     rcx, [rsp+128h+hMem]; hMem
0x1800482fa  test    rcx, rcx
0x1800482fd  jz      short loc_18004830B
0x1800482ff  call    cs:__imp_LocalFree
0x180048306  nop     dword ptr [rax+rax+00h]
0x18004830b  mov     eax, edi
0x18004830d  jmp     loc_1800487E6
0x180048312  mov     rdi, [rsi]
0x180048315  mov     rax, [rdi]
0x180048318  mov     rsi, [rax+20h]
0x18004831c  lea     r15, [rbx+0F0h]
0x180048323  mov     rcx, [r15]
0x180048326  mov     qword ptr [r15], 0
0x18004832d  test    rcx, rcx
0x180048330  jz      short loc_18004833F
0x180048332  mov     rdx, [rcx]
0x180048335  mov     rax, [rdx+10h]
0x180048339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004833e  nop
0x18004833f  mov     r8, r15
0x180048342  mov     rdx, [r12]
0x180048346  mov     rcx, rdi
0x180048349  mov     rax, rsi
0x18004834c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048351  test    eax, eax
0x180048353  jns     loc_180048481
0x180048359  lea     rdi, [rbx+0F8h]
0x180048360  mov     rcx, [rdi]
0x180048363  mov     qword ptr [rdi], 0
0x18004836a  test    rcx, rcx
0x18004836d  jz      short loc_18004837C
0x18004836f  mov     rax, [rcx]
0x180048372  mov     rax, [rax+10h]
0x180048376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004837b  nop
0x18004837c  mov     r8, rdi
0x18004837f  mov     rcx, r13
0x180048382  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x180048387  mov     esi, eax
0x180048389  test    eax, eax
0x18004838b  jns     short loc_1800483E3
0x18004838d  mov     rcx, [rsp+128h]; this
0x180048395  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x18004839c  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800483a1  mov     r9d, esi; char *
0x1800483a4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800483ab  mov     edx, 608h; void *
0x1800483b0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800483b5  nop
0x1800483b6  mov     rax, [rbx]
0x1800483b9  mov     rcx, rbx
0x1800483bc  mov     rax, [rax+10h]
0x1800483c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483c5  nop
0x1800483c6  mov     rcx, [rsp+128h+hMem]; hMem
0x1800483cb  test    rcx, rcx
0x1800483ce  jz      short loc_1800483DC
0x1800483d0  call    cs:__imp_LocalFree
0x1800483d7  nop     dword ptr [rax+rax+00h]
0x1800483dc  mov     eax, esi
0x1800483de  jmp     loc_1800487E6
0x1800483e3  mov     rsi, [rdi]
0x1800483e6  mov     rax, [rsi]
0x1800483e9  mov     r13, [rax+20h]
0x1800483ed  lea     rdi, [rbx+100h]
0x1800483f4  mov     rcx, [rdi]
0x1800483f7  mov     qword ptr [rdi], 0
0x1800483fe  test    rcx, rcx
0x180048401  jz      short loc_180048410
0x180048403  mov     r9, [rcx]
0x180048406  mov     rax, [r9+10h]
0x18004840a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004840f  nop
0x180048410  mov     r8, rdi
0x180048413  mov     rdx, [r12]
0x180048417  mov     rcx, rsi
0x18004841a  mov     rax, r13
0x18004841d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048422  mov     edi, eax
0x180048424  xor     r12d, r12d
0x180048427  test    eax, eax
0x180048429  jns     short loc_180048484
0x18004842b  mov     rcx, [rsp+128h]; this
0x180048433  lea     rax, aFailedToCreate_27; "Failed to create appx bundle reader."
0x18004843a  mov     qword ptr [rsp+128h+var_108], rax; int
0x18004843f  mov     r9d, edi; char *
0x180048442  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048449  mov     edx, 60Eh; void *
0x18004844e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048453  nop
0x180048454  mov     rax, [rbx]
0x180048457  mov     rcx, rbx
0x18004845a  mov     rax, [rax+10h]
0x18004845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048463  nop
0x180048464  mov     rcx, [rsp+128h+hMem]; hMem
0x180048469  test    rcx, rcx
0x18004846c  jz      short loc_18004847A
0x18004846e  call    cs:__imp_LocalFree
0x180048475  nop     dword ptr [rax+rax+00h]
0x18004847a  mov     eax, edi
0x18004847c  jmp     loc_1800487E6
0x180048481  xor     r12d, r12d
0x180048484  mov     r8, [r15]; struct IAppxPackageReader *
0x180048487  test    r8, r8
0x18004848a  jz      loc_1800485B2
0x180048490  mov     [rsp+128h+var_E8], r12
0x180048495  lea     r9, [rsp+128h+var_E8]; struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **
0x18004849a  xor     edx, edx; int
0x18004849c  mov     rcx, r14; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18004849f  call    ?CreateForPackageReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@HPEAUIAppxPackageReader@@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,IAppxPackageReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x1800484a4  mov     edi, eax
0x1800484a6  test    eax, eax
0x1800484a8  jns     short loc_180048517
0x1800484aa  mov     rcx, [rsp+128h]; this
0x1800484b2  lea     rax, aFailedToCreate_20; "Failed to create payload adapter for pa"...
0x1800484b9  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800484be  mov     r9d, edi; char *
0x1800484c1  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800484c8  mov     edx, 61Bh; void *
0x1800484cd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800484d2  nop
0x1800484d3  mov     rcx, [rsp+128h+var_E8]
0x1800484d8  test    rcx, rcx
0x1800484db  jz      short loc_1800484EA
0x1800484dd  mov     rax, [rcx]
0x1800484e0  mov     rax, [rax+10h]
0x1800484e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484e9  nop
  ... truncated ...
```

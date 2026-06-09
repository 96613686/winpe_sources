# Appx::Packaging::Consumption::AppxPackageReader::ParseBlockMapAndSignature(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,Appx::Packaging::Consumption::SignatureValidationInfo *,ushort * *,APPX_SIGNATURE_ORIGIN_INTERNAL *,uchar * *,ulong *)

- ea: `0x1800c8800`
- end: `0x1800c8ef0`
- name: `?ParseBlockMapAndSignature@AppxPackageReader@Consumption@Packaging@Appx@@AEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEAUSignatureValidationInfo@234@PEAPEAGPEAW4APPX_SIGNATURE_ORIGIN_INTERNAL@@PEAPEAEPEAK@Z`
- size: `1776`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800459f0`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180024608`
- `0x180025a0c`
- `0x180046da4`
- `0x1800511e8`
- `0x1800593d8`
- `0x18005ccf0`
- `0x180071f50`
- `0x180096a00`
- `0x1800992c4`
- `0x1800c6720`
- `0x1800c8800`
- `0x1800c9850`
- `0x1800c9980`
- `0x1800c99f8`
- `0x1800c9aac`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_CreateTempFileStreamOnByteSender` at `0x1800c8984`
- `OpcServices!__imp_CreateTempFileStreamOnByteSender` at `0x1800c8984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8a64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8a64`

## string_xrefs

- `0x1800c887d`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c88ce`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c899d`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8ac2`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8ba0`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8be6`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8c88`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8cc8`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8d22`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8da2`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8e06`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c8e57`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800c885e`: `AppxBlockMap.xml`
- `0x1800c8935`: `SBOM.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::Consumption::AppxPackageReader::ParseBlockMapAndSignature(
        __int64 a1,
        struct _RTL_AVL_TABLE *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned __int16 **a5,
        _QWORD *a6,
        _DWORD *a7)
{
  unsigned __int16 **v11; // r15
  __int64 v12; // rbx
  __int64 *v13; // rdi
  int v14; // eax
  int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, struct IStream **); // rbx
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  const unsigned __int16 *v20; // rdx
  int FileInfo; // eax
  struct IOpcPartUriVtbl *lpVtbl; // rbx
  int TempFileStreamOnByteSender; // eax
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 *v27; // r15
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rbx
  enum APPX_SIGNATURE_ORIGIN_INTERNAL *v31; // r14
  int v32; // eax
  __int64 v33; // rcx
  void *v34; // rbx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, Appx::Packaging **); // rbx
  int v37; // eax
  unsigned __int8 **v38; // r9
  unsigned __int64 v39; // rdx
  int SignatureBufferFromStream; // eax
  unsigned __int64 v41; // rdx
  __int64 v42; // r14
  __int64 (__fastcall *v43)(__int64, __int64 *); // rdi
  int v44; // eax
  int v45; // edi
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  int v48; // eax
  unsigned __int64 v49; // rdx
  LPVOID *p_pv; // rcx
  __int64 v51; // r14
  __int64 (__fastcall *v52)(__int64, LPVOID *); // rdi
  int v53; // eax
  unsigned __int64 v54; // rdx
  int v55; // eax
  unsigned __int64 v56; // rdx
  int SubjectNameAndOriginFromSignature; // eax
  unsigned __int64 v58; // rdx
  char IsEnabled; // al
  unsigned __int64 v60; // rdx
  __int64 v61; // rcx
  void *v62; // rax
  int v64; // [rsp+20h] [rbp-50h]
  int v65; // [rsp+20h] [rbp-50h]
  enum APPX_SIGNATURE_ORIGIN_INTERNAL *v66; // [rsp+20h] [rbp-50h]
  int v67; // [rsp+20h] [rbp-50h]
  Appx::Packaging *v68; // [rsp+40h] [rbp-30h] BYREF
  __int64 v69; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-20h] BYREF
  struct IOpcPartUri v71[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  Appx::Packaging *v73; // [rsp+B0h] [rbp+40h] BYREF
  struct IStream *v74; // [rsp+C8h] [rbp+58h] BYREF

  v71[1].lpVtbl = (struct IOpcPartUriVtbl *)-2LL;
  *(_QWORD *)a4 = 0;
  v11 = a5;
  *(_DWORD *)a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v12 = *(_QWORD *)(a1 + 32);
  v13 = (__int64 *)(a1 + 80);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 80);
  v64 = (int)v13;
  v14 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
          v12,
          a2,
          L"AppxBlockMap.xml",
          0);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v74 = 0;
    v16 = *v13;
    v17 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v16 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    v15 = v17(v16, &v74);
    v18 = retaddr;
    if ( v15 < 0 )
    {
      v19 = 473;
LABEL_5:
      wil::details::in1diag3::_Log_Hr(
        v18,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)(unsigned int)v15,
        v64);
LABEL_68:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
      return (unsigned int)v15;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 48);
    v15 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(
            v74,
            v20,
            (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)(a1 + 48));
    v18 = retaddr;
    if ( v15 < 0 )
    {
      v19 = 476;
      goto LABEL_5;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl'::`2'::impl) )
    {
      v71[0].lpVtbl = 0;
      FileInfo = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(
                   *(_QWORD *)(a1 + 32),
                   a2,
                   L"SBOM.json",
                   0,
                   1u,
                   v71);
      if ( FileInfo >= 0 && FileInfo != 1 )
      {
        lpVtbl = v71[0].lpVtbl;
        if ( v71[0].lpVtbl )
        {
          v71[0].lpVtbl = 0;
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v71);
          TempFileStreamOnByteSender = CreateTempFileStreamOnByteSender(
                                         **(_QWORD **)(a1 + 32),
                                         lpVtbl->HasProperty,
                                         v71);
          v15 = TempFileStreamOnByteSender;
          if ( TempFileStreamOnByteSender < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1F3,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
              (const char *)(unsigned int)TempFileStreamOnByteSender,
              v65);
LABEL_17:
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v71);
            goto LABEL_68;
          }
          pv = 0;
          if ( (int)Appx::Packaging::Sbom::ExtractAuthorFromSbomStream((__int64 *)v71[0].lpVtbl, (WCHAR **)&pv) >= 0
            && pv )
          {
            *(_QWORD *)a4 = pv;
            *(_DWORD *)v11 = 5;
            a5 = 0;
            v24 = *(_QWORD *)(a1 + 32);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a5);
            Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
              v24,
              a2,
              L"AppxSignature.p7x",
              0);
            v25 = *(_QWORD *)(a1 + 32);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 96);
            Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
              v25,
              a2,
              L"AppxMetadata\\CodeIntegrity.cat",
              0);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a5);
            CoTaskMemFree(0);
            v15 = 0;
            goto LABEL_17;
          }
          CoTaskMemFree(pv);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v71);
        }
      }
    }
    v26 = *(_QWORD *)(a1 + 32);
    v27 = (__int64 *)(a1 + 96);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 96);
    LODWORD(v66) = a1 + 96;
    v15 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
            v26,
            a2,
            L"AppxMetadata\\CodeIntegrity.cat",
            0);
    if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2146958845 )
    {
      v28 = (unsigned int)v15;
      v29 = 550;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)v28,
        (int)v66);
      goto LABEL_68;
    }
    v30 = *(_QWORD *)(a1 + 32);
    v31 = (enum APPX_SIGNATURE_ORIGIN_INTERNAL *)(a1 + 88);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v31);
    v66 = v31;
    v32 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
            v30,
            a2,
            L"AppxSignature.p7x",
            0);
    v15 = v32;
    if ( v32 < 0 )
    {
      if ( v32 != -2146958845 )
      {
        v28 = (unsigned int)v32;
        v29 = 564;
        goto LABEL_22;
      }
      if ( a3 && !*(_BYTE *)(a3 + 18) )
      {
        v15 = -2146762496;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v33, &EVENT_PACKAGE_UNSIGNED, 2148204800LL);
        AppxPackagingLog(&EVENT_PACKAGE_UNSIGNED, 0xB000009C, -2146762496);
        goto LABEL_68;
      }
    }
    LODWORD(v73) = 0;
    v34 = 0;
    pv = 0;
    v35 = *(_QWORD *)v31;
    if ( *(_QWORD *)v31 )
    {
      v68 = 0;
      v36 = *(__int64 (__fastcall **)(__int64, Appx::Packaging **))(*(_QWORD *)v35 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      v37 = v36(v35, &v68);
      v15 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v37,
          (int)v31);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
        operator delete(0, v39);
        goto LABEL_68;
      }
      SignatureBufferFromStream = Appx::Packaging::GetSignatureBufferFromStream(
                                    v68,
                                    (struct IStream *)&v73,
                                    (unsigned int *)&pv,
                                    v38);
      v15 = SignatureBufferFromStream;
      if ( SignatureBufferFromStream < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x247,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)SignatureBufferFromStream,
          (int)v31);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
        operator delete(pv, v41);
        goto LABEL_68;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      v34 = pv;
    }
    else if ( *v27 )
    {
      v15 = -2146958845;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)0x80080203LL,
        (int)v31);
      operator delete(0, v47);
      goto LABEL_68;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl'::`2'::impl) )
    {
      if ( !a3 || !*(_QWORD *)v31 && *(_BYTE *)(a3 + 18) )
        goto LABEL_59;
      v69 = 0;
      v42 = *v27;
      if ( *v27 )
      {
        v43 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 56LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
        v44 = v43(v42, &v69);
        v45 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
            (const char *)(unsigned int)v44,
            (int)v66);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
          operator delete(v34, v46);
LABEL_44:
          v15 = v45;
          goto LABEL_68;
        }
      }
      LOBYTE(v66) = *(_BYTE *)(a3 + 16);
      v48 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, _QWORD, void *))a3)(
              *(_QWORD *)(a3 + 8),
              v74,
              (unsigned int)v73,
              v34);
      v45 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v48,
          (int)v66);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
        operator delete(v34, v49);
        goto LABEL_44;
      }
      p_pv = (LPVOID *)&v69;
    }
    else
    {
      if ( !a3 || *(_BYTE *)(a3 + 18) )
        goto LABEL_59;
      pv = 0;
      v51 = *v27;
      if ( *v27 )
      {
        v52 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v51 + 56LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
        v53 = v52(v51, &pv);
        v45 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x273,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
            (const char *)(unsigned int)v53,
            (int)v66);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
          operator delete(v34, v54);
          goto LABEL_44;
        }
      }
      LOBYTE(v66) = *(_BYTE *)(a3 + 16);
      v55 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, _QWORD, void *))a3)(
              *(_QWORD *)(a3 + 8),
              v74,
              (unsigned int)v73,
              v34);
      v45 = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x27D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v55,
          (int)v66);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
        operator delete(v34, v56);
        goto LABEL_44;
      }
      p_pv = &pv;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(p_pv);
LABEL_59:
    SubjectNameAndOriginFromSignature = Appx::Packaging::GetSubjectNameAndOriginFromSignature(
                                          (Appx::Packaging *)(unsigned int)v73,
                                          (unsigned int)v34,
                                          a4,
                                          a5,
                                          v66);
    v45 = SubjectNameAndOriginFromSignature;
    if ( SubjectNameAndOriginFromSignature >= 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59382817>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59382817>::GetImpl'::`2'::impl);
      v61 = (unsigned int)v73;
      if ( IsEnabled )
      {
        *a7 = (_DWORD)v73;
        v62 = v34;
        v34 = 0;
        v60 = (unsigned __int64)a6;
        *a6 = v62;
      }
      if ( (_DWORD)v61 && a3 && (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v61, EVENT_SIGNATURE_VALIDATION_PASSED, *(_QWORD *)a4);
      operator delete(v34, v60);
      v15 = 0;
      goto LABEL_68;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)SubjectNameAndOriginFromSignature,
      v67);
    operator delete(v34, v58);
    goto LABEL_44;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1D5,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
    (const char *)(unsigned int)v14,
    (int)v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800c8800  mov     rax, rsp
0x1800c8803  push    rbp
0x1800c8804  push    rsi
0x1800c8805  push    rdi
0x1800c8806  push    r12
0x1800c8808  push    r13
0x1800c880a  push    r14
0x1800c880c  push    r15
0x1800c880e  mov     rbp, rsp
0x1800c8811  sub     rsp, 70h
0x1800c8815  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800c881d  mov     [rax+10h], rbx
0x1800c8821  mov     r13, r9
0x1800c8824  mov     rsi, r8
0x1800c8827  mov     r12, rdx
0x1800c882a  mov     r14, rcx
0x1800c882d  xor     ecx, ecx
0x1800c882f  mov     [r9], rcx
0x1800c8832  mov     r15, [rbp+arg_20]
0x1800c8836  mov     [r15], ecx
0x1800c8839  mov     rax, [rbp+arg_28]
0x1800c883d  mov     [rax], rcx
0x1800c8840  mov     rax, [rbp+arg_30]
0x1800c8844  mov     [rax], ecx
0x1800c8846  mov     rbx, [r14+20h]
0x1800c884a  lea     rdi, [r14+50h]
0x1800c884e  mov     rcx, rdi
0x1800c8851  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8856  mov     [rsp+70h+var_50], rdi; int
0x1800c885b  xor     r9d, r9d
0x1800c885e  lea     r8, ?FileName@BlockMap@Packaging@Appx@@3QBGB; "AppxBlockMap.xml"
0x1800c8865  mov     rdx, r12
0x1800c8868  mov     rcx, rbx
0x1800c886b  call    ?ExtractFootprintFileAndRemoveFromMap@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAVAppxBlockMapReader@BlockMap@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader *,IAppxFile * *)
0x1800c8870  mov     ebx, eax
0x1800c8872  mov     rcx, [rbp+38h]; this
0x1800c8876  test    eax, eax
0x1800c8878  jns     short loc_1800C8893
0x1800c887a  mov     r9d, eax; char *
0x1800c887d  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c8884  mov     edx, 1D5h; void *
0x1800c8889  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c888e  jmp     loc_1800C8ED5
0x1800c8893  mov     [rbp+arg_18], 0
0x1800c889b  mov     rdi, [rdi]
0x1800c889e  mov     rax, [rdi]
0x1800c88a1  mov     rbx, [rax+38h]
0x1800c88a5  lea     rcx, [rbp+arg_18]
0x1800c88a9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c88ae  lea     rdx, [rbp+arg_18]
0x1800c88b2  mov     rcx, rdi
0x1800c88b5  mov     rax, rbx
0x1800c88b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c88bd  mov     ebx, eax
0x1800c88bf  mov     rcx, [rbp+38h]; this
0x1800c88c3  xor     edi, edi
0x1800c88c5  test    eax, eax
0x1800c88c7  jns     short loc_1800C88E2
0x1800c88c9  mov     edx, 1D9h; void *
0x1800c88ce  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c88d5  mov     r9d, ebx; char *
0x1800c88d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c88dd  jmp     loc_1800C8ECC
0x1800c88e2  lea     rcx, [r14+30h]
0x1800c88e6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c88eb  lea     r8, [r14+30h]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x1800c88ef  mov     rcx, [rbp+arg_18]; struct IStream *
0x1800c88f3  call    ?Create@AppxBlockMapReader@BlockMap@Packaging@Appx@@SAJPEAUIStream@@PEBGPEAPEAV1234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::Create(IStream *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x1800c88f8  mov     ebx, eax
0x1800c88fa  mov     rcx, [rbp+38h]
0x1800c88fe  test    eax, eax
0x1800c8900  jns     short loc_1800C8909
0x1800c8902  mov     edx, 1DCh
0x1800c8907  jmp     short loc_1800C88CE
0x1800c8909  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB> `wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl(void)'::`2'::impl
0x1800c8910  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(void)
0x1800c8915  test    al, al
0x1800c8917  jz      loc_1800C8A79
0x1800c891d  mov     [rbp+var_18], rdi
0x1800c8921  lea     rax, [rbp+var_18]
0x1800c8925  mov     [rsp+70h+var_48], rax
0x1800c892a  mov     dword ptr [rsp+70h+var_50], 1; int
0x1800c8932  xor     r9d, r9d
0x1800c8935  lea     r8, aSbomJson; "SBOM.json"
0x1800c893c  mov     rdx, r12
0x1800c893f  mov     rcx, [r14+20h]
0x1800c8943  call    ?ExtractFileInfo@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBG_NJPEAPEAUAppxFileInfo@234@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,bool,long,Appx::Packaging::Consumption::AppxFileInfo * *)
0x1800c8948  bt      eax, 1Fh
0x1800c894c  jb      loc_1800C8A79
0x1800c8952  cmp     eax, 1
0x1800c8955  jz      loc_1800C8A79
0x1800c895b  mov     rbx, [rbp+var_18]
0x1800c895f  test    rbx, rbx
0x1800c8962  jz      loc_1800C8A79
0x1800c8968  mov     [rbp+var_18], rdi
0x1800c896c  lea     rcx, [rbp+var_18]
0x1800c8970  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8975  mov     rcx, [r14+20h]
0x1800c8979  lea     r8, [rbp+var_18]
0x1800c897d  mov     rdx, [rbx+30h]
0x1800c8981  mov     rcx, [rcx]
0x1800c8984  call    cs:__imp_CreateTempFileStreamOnByteSender
0x1800c898b  nop     dword ptr [rax+rax+00h]
0x1800c8990  mov     ebx, eax
0x1800c8992  mov     rcx, [rbp+38h]; this
0x1800c8996  test    eax, eax
0x1800c8998  jns     short loc_1800C89B3
0x1800c899a  mov     r9d, eax; char *
0x1800c899d  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c89a4  mov     edx, 1F3h; void *
0x1800c89a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c89ae  jmp     loc_1800C8A56
0x1800c89b3  mov     [rbp+pv], rdi
0x1800c89b7  lea     rdx, [rbp+pv]
0x1800c89bb  mov     rcx, [rbp+var_18]
0x1800c89bf  call    Appx__Packaging__Sbom__ExtractAuthorFromSbomStream
0x1800c89c4  mov     rcx, [rbp+pv]; pv
0x1800c89c8  test    eax, eax
0x1800c89ca  js      loc_1800C8A64
0x1800c89d0  test    rcx, rcx
0x1800c89d3  jz      loc_1800C8A64
0x1800c89d9  mov     [r13+0], rcx
0x1800c89dd  mov     dword ptr [r15], 5
0x1800c89e4  mov     [rbp+arg_20], rdi
0x1800c89e8  mov     rbx, [r14+20h]
0x1800c89ec  lea     rcx, [rbp+arg_20]
0x1800c89f0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c89f5  lea     rax, [rbp+arg_20]
0x1800c89f9  mov     [rsp+70h+var_50], rax
0x1800c89fe  xor     r9d, r9d
0x1800c8a01  lea     r8, ?FileName@Signature@Packaging@Appx@@3QBGB; "AppxSignature.p7x"
0x1800c8a08  mov     rdx, r12
0x1800c8a0b  mov     rcx, rbx
0x1800c8a0e  call    ?ExtractFootprintFileAndRemoveFromMap@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAVAppxBlockMapReader@BlockMap@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader *,IAppxFile * *)
0x1800c8a13  mov     rdi, [r14+20h]
0x1800c8a17  lea     rbx, [r14+60h]
0x1800c8a1b  mov     rcx, rbx
0x1800c8a1e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8a23  mov     [rsp+70h+var_50], rbx
0x1800c8a28  xor     r9d, r9d
0x1800c8a2b  lea     r8, ?FileName@CodeIntegrity@Packaging@Appx@@3QBGB; "AppxMetadata\\CodeIntegrity.cat"
0x1800c8a32  mov     rdx, r12
0x1800c8a35  mov     rcx, rdi
0x1800c8a38  call    ?ExtractFootprintFileAndRemoveFromMap@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAVAppxBlockMapReader@BlockMap@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader *,IAppxFile * *)
0x1800c8a3d  lea     rcx, [rbp+arg_20]
0x1800c8a41  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8a46  xor     ecx, ecx; pv
0x1800c8a48  call    cs:__imp_CoTaskMemFree
0x1800c8a4f  nop     dword ptr [rax+rax+00h]
0x1800c8a54  xor     ebx, ebx
0x1800c8a56  lea     rcx, [rbp+var_18]
0x1800c8a5a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8a5f  jmp     loc_1800C8ECC
0x1800c8a64  call    cs:__imp_CoTaskMemFree
0x1800c8a6b  nop     dword ptr [rax+rax+00h]
0x1800c8a70  lea     rcx, [rbp+var_18]
0x1800c8a74  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8a79  mov     rbx, [r14+20h]
0x1800c8a7d  lea     r15, [r14+60h]
0x1800c8a81  mov     rcx, r15
0x1800c8a84  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8a89  mov     [rsp+70h+var_50], r15; int
0x1800c8a8e  xor     r9d, r9d
0x1800c8a91  lea     r8, ?FileName@CodeIntegrity@Packaging@Appx@@3QBGB; "AppxMetadata\\CodeIntegrity.cat"
0x1800c8a98  mov     rdx, r12
0x1800c8a9b  mov     rcx, rbx
0x1800c8a9e  call    ?ExtractFootprintFileAndRemoveFromMap@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAVAppxBlockMapReader@BlockMap@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader *,IAppxFile * *)
0x1800c8aa3  mov     ebx, eax
0x1800c8aa5  mov     eax, 80000000h
0x1800c8aaa  lea     ecx, [rbx+rax]
0x1800c8aad  mov     edi, 80080203h
0x1800c8ab2  test    eax, ecx
0x1800c8ab4  jnz     short loc_1800C8AD7
0x1800c8ab6  cmp     ebx, edi
0x1800c8ab8  jz      short loc_1800C8AD7
0x1800c8aba  mov     r9d, ebx; char *
0x1800c8abd  mov     edx, 226h; void *
0x1800c8ac2  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c8ac9  mov     rcx, [rbp+38h]; this
0x1800c8acd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8ad2  jmp     loc_1800C8ECC
0x1800c8ad7  mov     rbx, [r14+20h]
0x1800c8adb  add     r14, 58h ; 'X'
0x1800c8adf  mov     rcx, r14
0x1800c8ae2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8ae7  mov     [rsp+70h+var_50], r14; int
0x1800c8aec  xor     r9d, r9d
0x1800c8aef  lea     r8, ?FileName@Signature@Packaging@Appx@@3QBGB; "AppxSignature.p7x"
0x1800c8af6  mov     rdx, r12
0x1800c8af9  mov     rcx, rbx
0x1800c8afc  call    ?ExtractFootprintFileAndRemoveFromMap@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAVAppxBlockMapReader@BlockMap@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader *,IAppxFile * *)
0x1800c8b01  mov     ebx, eax
0x1800c8b03  xor     r12d, r12d
0x1800c8b06  test    eax, eax
0x1800c8b08  jns     short loc_1800C8B59
0x1800c8b0a  cmp     eax, edi
0x1800c8b0c  jz      short loc_1800C8B18
0x1800c8b0e  mov     r9d, eax
0x1800c8b11  mov     edx, 234h
0x1800c8b16  jmp     short loc_1800C8AC2
0x1800c8b18  test    rsi, rsi
0x1800c8b1b  jz      short loc_1800C8B59
0x1800c8b1d  cmp     [rsi+12h], r12b
0x1800c8b21  jnz     short loc_1800C8B59
0x1800c8b23  mov     ebx, 800B0100h
0x1800c8b28  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x1800c8b2f  jz      short loc_1800C8B40
0x1800c8b31  mov     r8d, ebx
0x1800c8b34  lea     rdx, EVENT_PACKAGE_UNSIGNED
0x1800c8b3b  call    McTemplateU0q_EventWriteTransfer
0x1800c8b40  mov     r8d, ebx; int
0x1800c8b43  mov     edx, 0B000009Ch; unsigned int
0x1800c8b48  lea     rcx, EVENT_PACKAGE_UNSIGNED; struct _EVENT_DESCRIPTOR *
0x1800c8b4f  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJ@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long)
0x1800c8b54  jmp     loc_1800C8ECC
0x1800c8b59  mov     dword ptr [rbp+arg_0], r12d
0x1800c8b5d  mov     rbx, r12
0x1800c8b60  mov     [rbp+pv], rbx
0x1800c8b64  mov     rdi, [r14]
0x1800c8b67  test    rdi, rdi
0x1800c8b6a  jz      loc_1800C8CB3
0x1800c8b70  mov     [rbp+var_30], r12
0x1800c8b74  mov     rax, [rdi]
0x1800c8b77  mov     rbx, [rax+38h]
0x1800c8b7b  lea     rcx, [rbp+var_30]
0x1800c8b7f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8b84  lea     rdx, [rbp+var_30]
0x1800c8b88  mov     rcx, rdi
0x1800c8b8b  mov     rax, rbx
0x1800c8b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8b93  mov     ebx, eax
0x1800c8b95  mov     rcx, [rbp+38h]; this
0x1800c8b99  test    eax, eax
0x1800c8b9b  jns     short loc_1800C8BC8
0x1800c8b9d  mov     r9d, eax; char *
0x1800c8ba0  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c8ba7  mov     edx, 246h; void *
0x1800c8bac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c8bb1  lea     rcx, [rbp+var_30]
0x1800c8bb5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8bba  nop
0x1800c8bbb  xor     ecx, ecx; void *
0x1800c8bbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c8bc2  nop
0x1800c8bc3  jmp     loc_1800C8ECC
0x1800c8bc8  lea     r8, [rbp+pv]; unsigned int *
0x1800c8bcc  lea     rdx, [rbp+arg_0]; struct IStream *
0x1800c8bd0  mov     rcx, [rbp+var_30]; this
0x1800c8bd4  call    ?GetSignatureBufferFromStream@Packaging@Appx@@YAJPEAUIStream@@PEAKPEAPEAE@Z; Appx::Packaging::GetSignatureBufferFromStream(IStream *,ulong *,uchar * *)
0x1800c8bd9  mov     ebx, eax
0x1800c8bdb  mov     rcx, [rbp+38h]; this
0x1800c8bdf  test    eax, eax
0x1800c8be1  jns     short loc_1800C8C10
0x1800c8be3  mov     r9d, eax; char *
0x1800c8be6  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c8bed  mov     edx, 247h; void *
0x1800c8bf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c8bf7  lea     rcx, [rbp+var_30]
0x1800c8bfb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8c00  nop
0x1800c8c01  mov     rcx, [rbp+pv]; void *
0x1800c8c05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c8c0a  nop
0x1800c8c0b  jmp     loc_1800C8ECC
0x1800c8c10  lea     rcx, [rbp+var_30]
0x1800c8c14  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8c19  mov     rbx, [rbp+pv]
0x1800c8c1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass> `wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl(void)'::`2'::impl
0x1800c8c24  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SignatureValidationBypass@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(void)
0x1800c8c29  test    al, al
0x1800c8c2b  jz      loc_1800C8D54
0x1800c8c31  test    rsi, rsi
0x1800c8c34  jz      loc_1800C8E38
0x1800c8c3a  cmp     [r14], r12
0x1800c8c3d  jnz     short loc_1800C8C49
0x1800c8c3f  cmp     [rsi+12h], r12b
0x1800c8c43  jnz     loc_1800C8E38
0x1800c8c49  mov     rax, r12
0x1800c8c4c  mov     [rbp+var_28], rax
0x1800c8c50  mov     r14, [r15]
0x1800c8c53  test    r14, r14
0x1800c8c56  jz      loc_1800C8CEB
0x1800c8c5c  mov     rax, [r14]
0x1800c8c5f  mov     rdi, [rax+38h]
0x1800c8c63  lea     rcx, [rbp+var_28]
0x1800c8c67  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c8c6c  lea     rdx, [rbp+var_28]
0x1800c8c70  mov     rcx, r14
0x1800c8c73  mov     rax, rdi
0x1800c8c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8c7b  mov     edi, eax
0x1800c8c7d  mov     rcx, [rbp+38h]; this
0x1800c8c81  test    eax, eax
0x1800c8c83  jns     short loc_1800C8CE7
0x1800c8c85  mov     r9d, eax; char *
0x1800c8c88  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800c8c8f  mov     edx, 25Bh; void *
0x1800c8c94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c8c99  lea     rcx, [rbp+var_28]
0x1800c8c9d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
  ... truncated ...
```

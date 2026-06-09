# Appx::Packaging::Consumption::AppxPackageReader::ParseBlockMapAndSignature(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,Appx::Packaging::Consumption::SignatureValidationInfo *,ushort * *,APPX_SIGNATURE_ORIGIN_INTERNAL *,uchar * *,ulong *)

- ea: `0x1800c8800`
- end: `0x1800c8ef0`
- name: `?ParseBlockMapAndSignature@AppxPackageReader@Consumption@Packaging@Appx@@AEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEAUSignatureValidationInfo@234@PEAPEAGPEAW4APPX_SIGNATURE_ORIGIN_INTERNAL@@PEAPEAEPEAK@Z`
- size: `1776`
- prototype: ``
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
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned __int16 **a5,
        _QWORD *a6,
        _DWORD *a7)
{
  __int64 v11; // rbx
  __int64 *v12; // rdi
  int v13; // eax
  int v14; // ebx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, struct IStream **); // rbx
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rbx
  __int64 *v21; // r15
  unsigned __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rbx
  enum APPX_SIGNATURE_ORIGIN_INTERNAL *v25; // r14
  int v26; // eax
  __int64 v27; // rcx
  void *v28; // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, Appx::Packaging **); // rbx
  int v31; // eax
  unsigned __int8 **v32; // r9
  unsigned __int64 v33; // rdx
  int SignatureBufferFromStream; // eax
  unsigned __int64 v35; // rdx
  __int64 v36; // r14
  __int64 (__fastcall *v37)(__int64, __int64 *); // rdi
  int v38; // eax
  int v39; // edi
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  int v42; // eax
  unsigned __int64 v43; // rdx
  LPVOID *v44; // rcx
  __int64 v45; // r14
  __int64 (__fastcall *v46)(__int64, LPVOID *); // rdi
  int v47; // eax
  unsigned __int64 v48; // rdx
  int v49; // eax
  unsigned __int64 v50; // rdx
  int SubjectNameAndOriginFromSignature; // eax
  unsigned __int64 v52; // rdx
  char IsEnabled; // al
  unsigned __int64 v54; // rdx
  __int64 v55; // rcx
  void *v56; // rax
  int v58; // [rsp+20h] [rbp-50h]
  enum APPX_SIGNATURE_ORIGIN_INTERNAL *v59; // [rsp+20h] [rbp-50h]
  int v60; // [rsp+20h] [rbp-50h]
  Appx::Packaging *v61; // [rsp+40h] [rbp-30h] BYREF
  __int64 v62; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  Appx::Packaging *v65; // [rsp+B0h] [rbp+40h] BYREF
  struct IStream *v66; // [rsp+C8h] [rbp+58h] BYREF

  pv[2] = (LPVOID)-2LL;
  *(_QWORD *)a4 = 0;
  *(_DWORD *)a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v11 = *(_QWORD *)(a1 + 32);
  v12 = (__int64 *)(a1 + 80);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 80);
  v58 = (int)v12;
  v13 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
          v11,
          a2,
          L"AppxBlockMap.xml",
          0);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v66 = 0;
    v15 = *v12;
    v16 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v15 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
    v14 = v16(v15, &v66);
    v17 = retaddr;
    if ( v14 < 0 )
    {
      v18 = 473;
LABEL_5:
      wil::details::in1diag3::_Log_Hr(
        v17,
        (void *)v18,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)(unsigned int)v14,
        v58);
LABEL_59:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      return (unsigned int)v14;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 48);
    v14 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(
            v66,
            v19,
            (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)(a1 + 48));
    v17 = retaddr;
    if ( v14 < 0 )
    {
      v18 = 476;
      goto LABEL_5;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl'::`2'::impl) )
    {
      pv[1] = 0;
      Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(*(_QWORD *)(a1 + 32), a2, L"SBOM.json", 0);
    }
    v20 = *(_QWORD *)(a1 + 32);
    v21 = (__int64 *)(a1 + 96);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 96);
    LODWORD(v59) = a1 + 96;
    v14 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
            v20,
            a2,
            L"AppxMetadata\\CodeIntegrity.cat",
            0);
    if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2146958845 )
    {
      v22 = (unsigned int)v14;
      v23 = 550;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)v22,
        (int)v59);
      goto LABEL_59;
    }
    v24 = *(_QWORD *)(a1 + 32);
    v25 = (enum APPX_SIGNATURE_ORIGIN_INTERNAL *)(a1 + 88);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v25);
    v59 = v25;
    v26 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFootprintFileAndRemoveFromMap(
            v24,
            a2,
            L"AppxSignature.p7x",
            0);
    v14 = v26;
    if ( v26 < 0 )
    {
      if ( v26 != -2146958845 )
      {
        v22 = (unsigned int)v26;
        v23 = 564;
        goto LABEL_13;
      }
      if ( a3 && !*(_BYTE *)(a3 + 18) )
      {
        v14 = -2146762496;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v27, &EVENT_PACKAGE_UNSIGNED, 2148204800LL);
        AppxPackagingLog(&EVENT_PACKAGE_UNSIGNED, 0xB000009C, -2146762496);
        goto LABEL_59;
      }
    }
    LODWORD(v65) = 0;
    v28 = 0;
    pv[0] = 0;
    v29 = *(_QWORD *)v25;
    if ( *(_QWORD *)v25 )
    {
      v61 = 0;
      v30 = *(__int64 (__fastcall **)(__int64, Appx::Packaging **))(*(_QWORD *)v29 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
      v31 = v30(v29, &v61);
      v14 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v31,
          (int)v25);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
        operator delete(0, v33);
        goto LABEL_59;
      }
      SignatureBufferFromStream = Appx::Packaging::GetSignatureBufferFromStream(
                                    v61,
                                    (struct IStream *)&v65,
                                    (unsigned int *)pv,
                                    v32);
      v14 = SignatureBufferFromStream;
      if ( SignatureBufferFromStream < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x247,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)SignatureBufferFromStream,
          (int)v25);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
        operator delete(pv[0], v35);
        goto LABEL_59;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
      v28 = pv[0];
    }
    else if ( *v21 )
    {
      v14 = -2146958845;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
        (const char *)0x80080203LL,
        (int)v25);
      operator delete(0, v41);
      goto LABEL_59;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignatureValidationBypass>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SignatureValidationBypass>::GetImpl'::`2'::impl) )
    {
      if ( !a3 || !*(_QWORD *)v25 && *(_BYTE *)(a3 + 18) )
        goto LABEL_50;
      v62 = 0;
      v36 = *v21;
      if ( *v21 )
      {
        v37 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 56LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
        v38 = v37(v36, &v62);
        v39 = v38;
        if ( v38 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
            (const char *)(unsigned int)v38,
            (int)v59);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
          operator delete(v28, v40);
LABEL_35:
          v14 = v39;
          goto LABEL_59;
        }
      }
      LOBYTE(v59) = *(_BYTE *)(a3 + 16);
      v42 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, _QWORD, void *))a3)(
              *(_QWORD *)(a3 + 8),
              v66,
              (unsigned int)v65,
              v28);
      v39 = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v42,
          (int)v59);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
        operator delete(v28, v43);
        goto LABEL_35;
      }
      v44 = (LPVOID *)&v62;
    }
    else
    {
      if ( !a3 || *(_BYTE *)(a3 + 18) )
        goto LABEL_50;
      pv[0] = 0;
      v45 = *v21;
      if ( *v21 )
      {
        v46 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v45 + 56LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(pv);
        v47 = v46(v45, pv);
        v39 = v47;
        if ( v47 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x273,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
            (const char *)(unsigned int)v47,
            (int)v59);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(pv);
          operator delete(v28, v48);
          goto LABEL_35;
        }
      }
      LOBYTE(v59) = *(_BYTE *)(a3 + 16);
      v49 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, _QWORD, void *))a3)(
              *(_QWORD *)(a3 + 8),
              v66,
              (unsigned int)v65,
              v28);
      v39 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x27D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v49,
          (int)v59);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(pv);
        operator delete(v28, v50);
        goto LABEL_35;
      }
      v44 = pv;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v44);
LABEL_50:
    SubjectNameAndOriginFromSignature = Appx::Packaging::GetSubjectNameAndOriginFromSignature(
                                          (Appx::Packaging *)(unsigned int)v65,
                                          (unsigned int)v28,
                                          a4,
                                          a5,
                                          v59);
    v39 = SubjectNameAndOriginFromSignature;
    if ( SubjectNameAndOriginFromSignature >= 0 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59382817>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59382817>::GetImpl'::`2'::impl);
      v55 = (unsigned int)v65;
      if ( IsEnabled )
      {
        *a7 = (_DWORD)v65;
        v56 = v28;
        v28 = 0;
        v54 = (unsigned __int64)a6;
        *a6 = v56;
      }
      if ( (_DWORD)v55 && a3 && (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v55, EVENT_SIGNATURE_VALIDATION_PASSED, *(_QWORD *)a4);
      operator delete(v28, v54);
      v14 = 0;
      goto LABEL_59;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)SubjectNameAndOriginFromSignature,
      v60);
    operator delete(v28, v52);
    goto LABEL_35;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1D5,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
    (const char *)(unsigned int)v13,
    (int)v12);
  return (unsigned int)v14;
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

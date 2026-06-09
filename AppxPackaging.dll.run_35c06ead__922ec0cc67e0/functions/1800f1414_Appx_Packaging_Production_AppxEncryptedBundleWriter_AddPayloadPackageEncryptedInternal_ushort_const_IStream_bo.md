# Appx::Packaging::Production::AppxEncryptedBundleWriter::AddPayloadPackageEncryptedInternal(ushort const *,IStream *,bool)

- ea: `0x1800f1414`
- end: `0x1800f1a83`
- name: `?AddPayloadPackageEncryptedInternal@AppxEncryptedBundleWriter@Production@Packaging@Appx@@AEAAJPEBGPEAUIStream@@_N@Z`
- size: `1647`
- prototype: `int(Appx::Packaging::Production::AppxEncryptedBundleWriter *__hidden this, const unsigned __int16 *, struct IStream *, bool)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f1310`

## callees

- `0x180005eb8`
- `0x180011510`
- `0x1800133fc`
- `0x180022b50`
- `0x1800292d0`
- `0x180046f00`
- `0x180050ae8`
- `0x18005fc20`
- `0x180070110`
- `0x1800759b0`
- `0x180076b84`
- `0x180080c10`
- `0x18008378c`
- `0x180087554`
- `0x180088768`
- `0x1800f1414`
- `0x1800f3a7c`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f17f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f17f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1803`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f1577`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f15c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f1577`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f15c6`

## string_xrefs

- `0x1800f1470`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f14c9`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f151e`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f1564`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f1635`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f16f6`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f1741`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f17ae`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f18f1`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`
- `0x1800f1a27`: `onecore\printscan\appxpackaging\production\src\appxencryptedbundlewriter.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::AppxEncryptedBundleWriter::AddPayloadPackageEncryptedInternal(
        Appx::Packaging::Production::AppxEncryptedBundleWriter *this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        unsigned __int8 a4)
{
  int v7; // eax
  int v8; // ebx
  struct IAppxPackageReader *v9; // rdi
  HRESULT (__stdcall *GetBlockMap)(IAppxPackageReader *, IAppxBlockMapReader **); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  int ValidatedPackageData; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  Appx::Packaging::Production::BundleManifestWriterHelper *v21; // rbx
  char v22; // r13
  unsigned __int64 *v23; // r8
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  UINT32 v28; // r8d
  APPX_KEY_INFO *v29; // r9
  Appx::Packaging **v30; // r14
  __int64 v31; // rdx
  __int64 v32; // rax
  UINT32 v33; // ecx
  __int64 v34; // rcx
  struct IStream *v35; // rdx
  int StreamCurrentPosition; // eax
  __int64 v37; // rdx
  struct Appx::Packaging::AppxEncryptedPackageEditor *v38; // r15
  int v39; // edi
  unsigned __int64 *v40; // r8
  Appx::Packaging *v41; // rcx
  __int64 v42; // r8
  unsigned __int64 v43; // rbx
  __int64 v44; // rdx
  int v46; // [rsp+20h] [rbp-99h]
  const char *v47; // [rsp+20h] [rbp-99h]
  int v48; // [rsp+20h] [rbp-99h]
  struct IAppxManifestPackageId *v49; // [rsp+50h] [rbp-69h] BYREF
  struct IAppxManifestTargetDeviceFamiliesEnumerator *v50; // [rsp+58h] [rbp-61h] BYREF
  struct IAppxManifestQualifiedResourcesEnumerator *v51; // [rsp+60h] [rbp-59h] BYREF
  struct Appx::Packaging::AppxEncryptedPackageEditor *v52; // [rsp+68h] [rbp-51h] BYREF
  __int64 v53; // [rsp+70h] [rbp-49h] BYREF
  __int64 v54; // [rsp+78h] [rbp-41h] BYREF
  struct IAppxManifestPackageId *v55; // [rsp+80h] [rbp-39h] BYREF
  LPVOID v56; // [rsp+88h] [rbp-31h] BYREF
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE v57; // [rsp+90h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-21h] BYREF
  struct IAppxPackageReader *v59; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int64 v60; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-9h] BYREF
  APPX_KEY_INFO v62; // [rsp+B8h] [rbp-1h] BYREF
  APPX_ENCRYPTED_EXEMPTIONS v63; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  LPVOID pv; // [rsp+120h] [rbp+67h] BYREF
  unsigned __int8 v66; // [rsp+138h] [rbp+7Fh]

  v66 = a4;
  v59 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
  v7 = Appx::Packaging::Consumption::AppxPackageReader::Create(a3, **((_QWORD **)this + 15) == 0, 0, &v59);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !*((_QWORD *)this + 8) )
    {
      v54 = 0;
      v9 = v59;
      GetBlockMap = v59->lpVtbl->GetBlockMap;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
      v8 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetBlockMap)(v9, &v54);
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v8,
          v46);
LABEL_6:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
        goto LABEL_58;
      }
      v11 = v54;
      v53 = 0;
      v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 40LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
      v13 = v12(v11, &v53);
      v8 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v13,
          v46);
LABEL_9:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
        goto LABEL_6;
      }
      bstrString = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v53 + 56LL))(v53, &bstrString);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 162;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v14,
          v46);
        SysFreeString(bstrString);
        goto LABEL_9;
      }
      v14 = Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeBlockMapWriter(
              *((Appx::Packaging::Production::EncryptedPackageWriterHelper **)this + 14),
              bstrString);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = 163;
        goto LABEL_12;
      }
      Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=((char *)this + 64, &v53);
      v16 = *((_QWORD *)this + 15) + 944LL;
      *((_QWORD *)this + 11) = *((_QWORD *)this + 8);
      Microsoft::WRL::ComPtr<IUri>::operator=(v16);
      SysFreeString(bstrString);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
    }
    v57 = APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE_APPLICATION;
    v17 = -1;
    v49 = 0;
    v51 = 0;
    v50 = 0;
    LOBYTE(pv) = 0;
    do
      ++v17;
    while ( a2[v17] );
    ValidatedPackageData = Appx::Packaging::FileNameHelper::ValidateFileNameAgainstReservedFolder(
                             a2,
                             v17,
                             L"appxmetadata\\stub",
                             0x11u,
                             (bool *)&pv);
    v8 = ValidatedPackageData;
    if ( ValidatedPackageData < 0 )
    {
      v19 = 181;
LABEL_20:
      v20 = (unsigned int)ValidatedPackageData;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
        (const char *)v20,
        (int)v47);
LABEL_22:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      goto LABEL_58;
    }
    v21 = (Appx::Packaging::Production::BundleManifestWriterHelper *)*((_QWORD *)this + 15);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    v22 = (char)pv;
    ValidatedPackageData = Appx::Packaging::Production::BundleManifestWriterHelper::GetValidatedPackageData(
                             v21,
                             a2,
                             v59,
                             (bool)pv,
                             &v57,
                             &v49,
                             &v51,
                             &v50);
    v8 = ValidatedPackageData;
    if ( ValidatedPackageData < 0 )
    {
      v19 = 184;
      goto LABEL_20;
    }
    if ( !*((_BYTE *)this + 33) )
    {
      pv = 0;
      v24 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, LPVOID *))v49->lpVtbl->GetName)(v49, &pv);
      v8 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v24,
          (int)v47);
LABEL_28:
        CoTaskMemFree(pv);
        goto LABEL_22;
      }
      v56 = 0;
      v25 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, LPVOID *))v49->lpVtbl->GetPublisher)(v49, &v56);
      v8 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v25,
          (int)v47);
LABEL_31:
        CoTaskMemFree(v56);
        goto LABEL_28;
      }
      v55 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
      v47 = L"~";
      v26 = Appx::Packaging::Manifest::BundlePayloadPackageId::Create(pv, v56, 0, 11);
      v8 = v26;
      if ( v26 < 0 )
      {
        v27 = 200;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
          (const char *)(unsigned int)v26,
          (int)L"~");
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
        goto LABEL_31;
      }
      v26 = Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeVersionNeutralPackageFullName(
              *((Appx::Packaging::Production::EncryptedPackageWriterHelper **)this + 14),
              v55);
      v8 = v26;
      if ( v26 < 0 )
      {
        v27 = 203;
        goto LABEL_34;
      }
      *((_BYTE *)this + 33) = 1;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
      CoTaskMemFree(v56);
      CoTaskMemFree(pv);
    }
    v60 = 0;
    ValidatedPackageData = Appx::Packaging::GetStreamCurrentPosition(
                             *((Appx::Packaging **)this + 13),
                             (struct IStream *)&v60,
                             v23);
    v8 = ValidatedPackageData;
    if ( ValidatedPackageData < 0 )
    {
      v19 = 209;
      goto LABEL_20;
    }
    v28 = *((_DWORD *)this + 9);
    v29 = 0;
    v30 = (Appx::Packaging **)((char *)this + 104);
    memset(&v62, 0, sizeof(v62));
    if ( v28 )
    {
      v31 = *((_QWORD *)this + 14);
      v32 = *(_QWORD *)(v31 + 48);
      if ( !*(_QWORD *)(v32 + 112) || (v62.keyId = **(BYTE ***)(v32 + 96)) == 0 )
      {
        v8 = -2146958848;
        v19 = 221;
        v20 = 2148008448LL;
        goto LABEL_21;
      }
      v29 = &v62;
      v30 = (Appx::Packaging **)((char *)this + 104);
      v33 = *(unsigned __int8 *)(*(_QWORD *)(v31 + 48) + 128LL);
      v62.key = (BYTE *)*((_QWORD *)this + 5);
      v62.keyIdLength = v33;
      v62.keyLength = v28;
    }
    v34 = *((_QWORD *)this + 20);
    v35 = (struct IStream *)*((_QWORD *)this + 13);
    v63.count = *(_DWORD *)v34;
    *(&v63.count + 1) = 0;
    v63.plainTextFiles = *(LPCWSTR **)(v34 + 8);
    v52 = 0;
    StreamCurrentPosition = Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage(
                              a3,
                              v35,
                              (const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *)((char *)this + 72),
                              v29,
                              &v63,
                              0,
                              0,
                              &v52);
    v8 = StreamCurrentPosition;
    if ( StreamCurrentPosition < 0 )
    {
      v37 = 245;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
        (const char *)(unsigned int)StreamCurrentPosition,
        v48);
      Common::AutoPtrDeallocate<Appx::Packaging::AppxEncryptedPackageEditor>(v52);
      goto LABEL_22;
    }
    v38 = v52;
    v39 = Common::Array<Appx::Packaging::AppxEncryptedPackageEditor,Common::ContainerOperations<Appx::Packaging::AppxEncryptedPackageEditor,Appx::Packaging::AppxEncryptedPackageEditor>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::AppxEncryptedPackageEditor>,Common::ArrayOperations<Appx::Packaging::AppxEncryptedPackageEditor,Common::NoKey>>::EnsureCapacity(
            (char *)this + 128,
            *((_QWORD *)this + 18) + 1LL);
    if ( v39 < 0 )
    {
      v44 = 247;
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)this + 16) + 8LL * (*((_QWORD *)this + 18))++) = v38;
      v41 = *v30;
      v52 = 0;
      v61 = 0;
      StreamCurrentPosition = Appx::Packaging::GetStreamCurrentPosition(v41, (struct IStream *)&v61, v40);
      v8 = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v37 = 252;
        goto LABEL_46;
      }
      v43 = v61 - v60;
      v39 = Appx::Packaging::Production::EncryptedPackageWriterHelper::AddFileFooter(
              *((_QWORD *)this + 14),
              a2,
              v42,
              v61 - v60);
      if ( v39 >= 0 )
      {
        StreamCurrentPosition = Appx::Packaging::Production::BundleManifestWriterHelper::AddValidatedPackageData(
                                  *((Appx::Packaging::Production::BundleManifestWriterHelper **)this + 15),
                                  a2,
                                  v60,
                                  v43,
                                  v57,
                                  v49,
                                  v66,
                                  v51,
                                  v50,
                                  v22);
        v8 = StreamCurrentPosition;
        if ( StreamCurrentPosition >= 0 )
        {
          Common::AutoPtrDeallocate<Appx::Packaging::AppxEncryptedPackageEditor>(v52);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
          v8 = 0;
          goto LABEL_58;
        }
        v37 = 270;
        goto LABEL_46;
      }
      v44 = 257;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
      (const char *)(unsigned int)v39,
      v48);
    Common::AutoPtrDeallocate<Appx::Packaging::AppxEncryptedPackageEditor>(v52);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    v8 = v39;
    goto LABEL_58;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x96,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedbundlewriter.cpp",
    (const char *)(unsigned int)v7,
    v46);
LABEL_58:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800f1414  mov     [rsp-8+arg_8], rbx
0x1800f1419  mov     [rsp-8+arg_18], r9b
0x1800f141e  push    rbp
0x1800f141f  push    rsi
0x1800f1420  push    rdi
0x1800f1421  push    r12
0x1800f1423  push    r13
0x1800f1425  push    r14
0x1800f1427  push    r15
0x1800f1429  lea     rbp, [rsp-27h]
0x1800f142e  sub     rsp, 0E0h
0x1800f1435  mov     rsi, rcx
0x1800f1438  xor     edi, edi
0x1800f143a  lea     rcx, [rbp+57h+var_70]
0x1800f143e  mov     [rbp+57h+var_70], rdi
0x1800f1442  mov     r15, r8
0x1800f1445  mov     r12, rdx
0x1800f1448  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f144d  mov     rax, [rsi+78h]
0x1800f1451  lea     r9, [rbp+57h+var_70]; struct IAppxPackageReader **
0x1800f1455  mov     rcx, r15; struct IStream *
0x1800f1458  cmp     [rax], rdi
0x1800f145b  setz    dl; bool
0x1800f145e  xor     r8d, r8d; unsigned __int16 *
0x1800f1461  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,IAppxPackageReader * *)
0x1800f1466  mov     ebx, eax
0x1800f1468  test    eax, eax
0x1800f146a  jns     short loc_1800F1489
0x1800f146c  mov     rcx, [rbp+5Fh]; this
0x1800f1470  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1477  mov     r9d, eax; char *
0x1800f147a  mov     edx, 96h; void *
0x1800f147f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1484  jmp     loc_1800F1A5C
0x1800f1489  lea     r14, [rsi+40h]
0x1800f148d  cmp     [r14], rdi
0x1800f1490  jnz     loc_1800F15E4
0x1800f1496  mov     [rbp+57h+var_98], rdi
0x1800f149a  lea     rcx, [rbp+57h+var_98]
0x1800f149e  mov     rdi, [rbp+57h+var_70]
0x1800f14a2  mov     rax, [rdi]
0x1800f14a5  mov     rbx, [rax+18h]
0x1800f14a9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f14ae  lea     rdx, [rbp+57h+var_98]
0x1800f14b2  mov     rcx, rdi
0x1800f14b5  mov     rax, rbx
0x1800f14b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f14bd  mov     ebx, eax
0x1800f14bf  xor     eax, eax
0x1800f14c1  test    ebx, ebx
0x1800f14c3  jns     short loc_1800F14EB
0x1800f14c5  mov     rcx, [rbp+5Fh]; this
0x1800f14c9  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f14d0  mov     r9d, ebx; char *
0x1800f14d3  mov     edx, 9Ch; void *
0x1800f14d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f14dd  lea     rcx, [rbp+57h+var_98]
0x1800f14e1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f14e6  jmp     loc_1800F1A5C
0x1800f14eb  mov     rdi, [rbp+57h+var_98]
0x1800f14ef  lea     rcx, [rbp+57h+var_A0]
0x1800f14f3  mov     [rbp+57h+var_A0], rax
0x1800f14f7  mov     rax, [rdi]
0x1800f14fa  mov     rbx, [rax+28h]
0x1800f14fe  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f1503  lea     rdx, [rbp+57h+var_A0]
0x1800f1507  mov     rcx, rdi
0x1800f150a  mov     rax, rbx
0x1800f150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1512  xor     edi, edi
0x1800f1514  mov     ebx, eax
0x1800f1516  test    eax, eax
0x1800f1518  jns     short loc_1800F153D
0x1800f151a  mov     rcx, [rbp+5Fh]; this
0x1800f151e  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1525  mov     r9d, eax; char *
0x1800f1528  mov     edx, 9Fh; void *
0x1800f152d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1532  lea     rcx, [rbp+57h+var_A0]
0x1800f1536  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f153b  jmp     short loc_1800F14DD
0x1800f153d  mov     rcx, [rbp+57h+var_A0]
0x1800f1541  lea     rdx, [rbp+57h+bstrString]
0x1800f1545  mov     [rbp+57h+bstrString], rdi
0x1800f1549  mov     rax, [rcx]
0x1800f154c  mov     rax, [rax+38h]
0x1800f1550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1555  mov     ebx, eax
0x1800f1557  test    eax, eax
0x1800f1559  jns     short loc_1800F1585
0x1800f155b  mov     edx, 0A2h; void *
0x1800f1560  mov     rcx, [rbp+5Fh]; this
0x1800f1564  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f156b  mov     r9d, eax; char *
0x1800f156e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1573  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f1577  call    cs:__imp_SysFreeString
0x1800f157e  nop     dword ptr [rax+rax+00h]
0x1800f1583  jmp     short loc_1800F1532
0x1800f1585  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800f1589  mov     rcx, [rsi+70h]; this
0x1800f158d  call    ?InitializeBlockMapWriter@EncryptedPackageWriterHelper@Production@Packaging@Appx@@QEAAJPEBG@Z; Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeBlockMapWriter(ushort const *)
0x1800f1592  mov     ebx, eax
0x1800f1594  test    eax, eax
0x1800f1596  jns     short loc_1800F159F
0x1800f1598  mov     edx, 0A3h
0x1800f159d  jmp     short loc_1800F1560
0x1800f159f  lea     rdx, [rbp+57h+var_A0]
0x1800f15a3  mov     rcx, r14
0x1800f15a6  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800f15ab  mov     rcx, [rsi+78h]
0x1800f15af  mov     rdx, [r14]
0x1800f15b2  add     rcx, 3B0h
0x1800f15b9  mov     [rsi+58h], rdx
0x1800f15bd  call    ??4?$ComPtr@UIUri@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUri@@@Z; Microsoft::WRL::ComPtr<IUri>::operator=(IUri *)
0x1800f15c2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f15c6  call    cs:__imp_SysFreeString
0x1800f15cd  nop     dword ptr [rax+rax+00h]
0x1800f15d2  lea     rcx, [rbp+57h+var_A0]
0x1800f15d6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f15db  lea     rcx, [rbp+57h+var_98]
0x1800f15df  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f15e4  mov     [rbp+57h+var_80], edi
0x1800f15e7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f15eb  mov     [rbp+57h+var_C0], rdi
0x1800f15ef  mov     [rbp+57h+var_B0], rdi
0x1800f15f3  mov     [rbp+57h+var_B8], rdi
0x1800f15f7  mov     byte ptr [rbp+57h+pv], dil
0x1800f15fb  inc     rdx; unsigned __int64
0x1800f15fe  cmp     [r12+rdx*2], di
0x1800f1603  jnz     short loc_1800F15FB
0x1800f1605  lea     rax, [rbp+57h+pv]
0x1800f1609  mov     r9d, 11h; unsigned int
0x1800f160f  lea     r8, aAppxmetadataSt_1; "appxmetadata\\stub"
0x1800f1616  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800f161b  mov     rcx, r12; Src
0x1800f161e  call    ?ValidateFileNameAgainstReservedFolder@FileNameHelper@Packaging@Appx@@SAJPEBG_K0IPEA_N@Z; Appx::Packaging::FileNameHelper::ValidateFileNameAgainstReservedFolder(ushort const *,unsigned __int64,ushort const *,uint,bool *)
0x1800f1623  mov     ebx, eax
0x1800f1625  test    eax, eax
0x1800f1627  jns     short loc_1800F1661
0x1800f1629  mov     edx, 0B5h; void *
0x1800f162e  mov     r9d, eax; char *
0x1800f1631  mov     rcx, [rbp+5Fh]; this
0x1800f1635  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f163c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1641  lea     rcx, [rbp+57h+var_B8]
0x1800f1645  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f164a  lea     rcx, [rbp+57h+var_B0]
0x1800f164e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f1653  lea     rcx, [rbp+57h+var_C0]
0x1800f1657  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f165c  jmp     loc_1800F1A5C
0x1800f1661  mov     rbx, [rsi+78h]
0x1800f1665  lea     rcx, [rbp+57h+var_B8]
0x1800f1669  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f166e  lea     rcx, [rbp+57h+var_B0]
0x1800f1672  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f1677  lea     rcx, [rbp+57h+var_C0]
0x1800f167b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f1680  mov     r13b, byte ptr [rbp+57h+pv]
0x1800f1684  lea     rax, [rbp+57h+var_B8]
0x1800f1688  mov     r8, [rbp+57h+var_70]; struct IAppxPackageReader *
0x1800f168c  mov     r9b, r13b; bool
0x1800f168f  mov     [rsp+110h+var_D8], rax; struct IAppxManifestTargetDeviceFamiliesEnumerator **
0x1800f1694  mov     rdx, r12; unsigned __int16 *
0x1800f1697  lea     rax, [rbp+57h+var_B0]
0x1800f169b  mov     rcx, rbx; this
0x1800f169e  mov     [rsp+110h+var_E0], rax; struct IAppxManifestQualifiedResourcesEnumerator **
0x1800f16a3  lea     rax, [rbp+57h+var_C0]
0x1800f16a7  mov     [rsp+110h+var_E8], rax; struct IAppxManifestPackageId **
0x1800f16ac  lea     rax, [rbp+57h+var_80]
0x1800f16b0  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800f16b5  call    ?GetValidatedPackageData@BundleManifestWriterHelper@Production@Packaging@Appx@@QEAAJPEBGPEAUIAppxPackageReader@@_NPEAW4APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE@@PEAPEAUIAppxManifestPackageId@@PEAPEAUIAppxManifestQualifiedResourcesEnumerator@@PEAPEAUIAppxManifestTargetDeviceFamiliesEnumerator@@@Z; Appx::Packaging::Production::BundleManifestWriterHelper::GetValidatedPackageData(ushort const *,IAppxPackageReader *,bool,APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *,IAppxManifestPackageId * *,IAppxManifestQualifiedResourcesEnumerator * *,IAppxManifestTargetDeviceFamiliesEnumerator * *)
0x1800f16ba  mov     ebx, eax
0x1800f16bc  test    eax, eax
0x1800f16be  jns     short loc_1800F16CA
0x1800f16c0  mov     edx, 0B8h
0x1800f16c5  jmp     loc_1800F162E
0x1800f16ca  cmp     [rsi+21h], dil
0x1800f16ce  jnz     loc_1800F180F
0x1800f16d4  mov     rcx, [rbp+57h+var_C0]
0x1800f16d8  lea     rdx, [rbp+57h+pv]
0x1800f16dc  mov     [rbp+57h+pv], rdi
0x1800f16e0  mov     rax, [rcx]
0x1800f16e3  mov     rax, [rax+18h]
0x1800f16e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f16ec  mov     ebx, eax
0x1800f16ee  test    eax, eax
0x1800f16f0  jns     short loc_1800F171F
0x1800f16f2  mov     rcx, [rbp+5Fh]; this
0x1800f16f6  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f16fd  mov     r9d, eax; char *
0x1800f1700  mov     edx, 0BEh; void *
0x1800f1705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f170a  mov     rcx, [rbp+57h+pv]; pv
0x1800f170e  call    cs:__imp_CoTaskMemFree
0x1800f1715  nop     dword ptr [rax+rax+00h]
0x1800f171a  jmp     loc_1800F1641
0x1800f171f  mov     rcx, [rbp+57h+var_C0]
0x1800f1723  lea     rdx, [rbp+57h+var_88]
0x1800f1727  mov     [rbp+57h+var_88], rdi
0x1800f172b  mov     rax, [rcx]
0x1800f172e  mov     rax, [rax+28h]
0x1800f1732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1737  mov     ebx, eax
0x1800f1739  test    eax, eax
0x1800f173b  jns     short loc_1800F1767
0x1800f173d  mov     rcx, [rbp+5Fh]; this
0x1800f1741  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f1748  mov     r9d, eax; char *
0x1800f174b  mov     edx, 0C0h; void *
0x1800f1750  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1755  mov     rcx, [rbp+57h+var_88]; pv
0x1800f1759  call    cs:__imp_CoTaskMemFree
0x1800f1760  nop     dword ptr [rax+rax+00h]
0x1800f1765  jmp     short loc_1800F170A
0x1800f1767  lea     rcx, [rbp+57h+var_90]
0x1800f176b  mov     [rbp+57h+var_90], rdi
0x1800f176f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f1774  mov     rdx, [rbp+57h+var_88]
0x1800f1778  lea     rax, [rbp+57h+var_90]
0x1800f177c  mov     rcx, [rbp+57h+pv]
0x1800f1780  mov     r9d, 0Bh
0x1800f1786  mov     [rsp+110h+var_E8], rax
0x1800f178b  xor     r8d, r8d
0x1800f178e  lea     rax, ?BundleResourceIdValue@BundleManifest@Packaging@Appx@@3QBGB; "~"
0x1800f1795  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800f179a  call    ?Create@BundlePayloadPackageId@Manifest@Packaging@Appx@@SAJPEBG0_KUAppxPackageArchitecture@Types@234@0PEAPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Manifest::BundlePayloadPackageId::Create(ushort const *,ushort const *,unsigned __int64,Appx::Packaging::Manifest::Types::AppxPackageArchitecture,ushort const *,IAppxManifestPackageId * *)
0x1800f179f  mov     ebx, eax
0x1800f17a1  test    eax, eax
0x1800f17a3  jns     short loc_1800F17C8
0x1800f17a5  mov     edx, 0C8h; void *
0x1800f17aa  mov     rcx, [rbp+5Fh]; this
0x1800f17ae  lea     r8, aOnecorePrintsc_128; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f17b5  mov     r9d, eax; char *
0x1800f17b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f17bd  lea     rcx, [rbp+57h+var_90]
0x1800f17c1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f17c6  jmp     short loc_1800F1755
0x1800f17c8  mov     rdx, [rbp+57h+var_90]; struct IAppxManifestPackageId *
0x1800f17cc  mov     rcx, [rsi+70h]; this
0x1800f17d0  call    ?InitializeVersionNeutralPackageFullName@EncryptedPackageWriterHelper@Production@Packaging@Appx@@QEAAJPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Production::EncryptedPackageWriterHelper::InitializeVersionNeutralPackageFullName(IAppxManifestPackageId *)
0x1800f17d5  mov     ebx, eax
0x1800f17d7  test    eax, eax
0x1800f17d9  jns     short loc_1800F17E2
0x1800f17db  mov     edx, 0CBh
0x1800f17e0  jmp     short loc_1800F17AA
0x1800f17e2  lea     rcx, [rbp+57h+var_90]
0x1800f17e6  mov     byte ptr [rsi+21h], 1
0x1800f17ea  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f17ef  mov     rcx, [rbp+57h+var_88]; pv
0x1800f17f3  call    cs:__imp_CoTaskMemFree
0x1800f17fa  nop     dword ptr [rax+rax+00h]
0x1800f17ff  mov     rcx, [rbp+57h+pv]; pv
0x1800f1803  call    cs:__imp_CoTaskMemFree
0x1800f180a  nop     dword ptr [rax+rax+00h]
0x1800f180f  mov     [rbp+57h+var_68], rdi
0x1800f1813  lea     rdx, [rbp+57h+var_68]; struct IStream *
0x1800f1817  lea     rdi, [rsi+68h]
0x1800f181b  mov     rcx, [rdi]; this
0x1800f181e  call    ?GetStreamCurrentPosition@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamCurrentPosition(IStream *,unsigned __int64 *)
0x1800f1823  xor     r10d, r10d
0x1800f1826  mov     ebx, eax
0x1800f1828  test    eax, eax
0x1800f182a  jns     short loc_1800F1836
0x1800f182c  mov     edx, 0D1h
0x1800f1831  jmp     loc_1800F162E
0x1800f1836  mov     r8d, [rsi+24h]
0x1800f183a  xor     eax, eax
0x1800f183c  mov     [rbp+57h+var_58.keyId], rax
0x1800f1840  xorps   xmm0, xmm0
0x1800f1843  mov     r9, r10
0x1800f1846  mov     r14, rdi
0x1800f1849  movups  xmmword ptr [rbp+57h+var_58.keyLength], xmm0
0x1800f184d  test    r8d, r8d
0x1800f1850  jz      short loc_1800F189A
0x1800f1852  mov     rdx, [rsi+70h]
0x1800f1856  mov     rax, [rdx+30h]
0x1800f185a  cmp     [rax+70h], r10
0x1800f185e  jbe     loc_1800F190E
0x1800f1864  mov     rax, [rax+60h]
0x1800f1868  mov     rcx, [rax]
0x1800f186b  mov     [rbp+57h+var_58.keyId], rcx
0x1800f186f  test    rcx, rcx
0x1800f1872  jz      loc_1800F190E
0x1800f1878  mov     rax, [rdx+30h]
0x1800f187c  lea     r9, [rbp+57h+var_58]; struct APPX_KEY_INFO *
0x1800f1880  lea     r14, [rsi+68h]
0x1800f1884  movzx   ecx, byte ptr [rax+80h]
0x1800f188b  mov     rax, [rsi+28h]
0x1800f188f  mov     [rbp+57h+var_58.key], rax
0x1800f1893  mov     [rbp+57h+var_58.keyIdLength], ecx
0x1800f1896  mov     [rbp+57h+var_58.keyLength], r8d
0x1800f189a  mov     rcx, [rsi+0A0h]
0x1800f18a1  lea     r8, [rsi+48h]; struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *
0x1800f18a5  mov     rdx, [rdi]; struct IStream *
0x1800f18a8  mov     eax, [rcx]
0x1800f18aa  mov     [rbp+57h+var_40.count], eax
0x1800f18ad  xor     eax, eax
0x1800f18af  mov     dword ptr [rbp+57h+var_40+4], eax
  ... truncated ...
```

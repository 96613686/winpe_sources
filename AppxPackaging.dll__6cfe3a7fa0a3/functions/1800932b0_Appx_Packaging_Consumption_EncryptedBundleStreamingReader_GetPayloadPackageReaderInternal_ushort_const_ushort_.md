# Appx::Packaging::Consumption::EncryptedBundleStreamingReader::GetPayloadPackageReaderInternal(ushort const *,ushort const *,IAppxPackageStreamingReader * *)

- ea: `0x1800932b0`
- end: `0x1800937d4`
- name: `?GetPayloadPackageReaderInternal@EncryptedBundleStreamingReader@Consumption@Packaging@Appx@@AEAAJPEBG0PEAPEAUIAppxPackageStreamingReader@@@Z`
- size: `1316`
- prototype: `__int64 __fastcall(Appx::Packaging::Consumption::EncryptedBundleStreamingReader *this, const unsigned __int16 *, unsigned __int16 *, struct IAppxPackageStreamingReader **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d0160`
- `0x1800d0190`

## callees

- `0x180005eb8`
- `0x180005f60`
- `0x1800133fc`
- `0x180022c8c`
- `0x180023ae8`
- `0x1800433e0`
- `0x18005ed94`
- `0x18006c368`
- `0x180071f50`
- `0x1800932b0`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800cf090`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093454`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093454`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093513`

## string_xrefs

- `0x1800932f4`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18009336e`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x1800933e6`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18009343c`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18009348f`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x180093563`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x1800935cb`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x180093622`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x180093694`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18009370c`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::Consumption::EncryptedBundleStreamingReader::GetPayloadPackageReaderInternal(
        Appx::Packaging::Consumption::EncryptedBundleStreamingReader *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IAppxPackageStreamingReader **a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int BundlePayloadPackageInfo; // eax
  __int64 v11; // rdx
  struct IAppxBundleManifestPackageInfo *v12; // rdi
  HRESULT (__stdcall *GetPackageId)(IAppxBundleManifestPackageInfo *, IAppxManifestPackageId **); // rbx
  int v14; // eax
  int v15; // eax
  int ExternalPayloadUri; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  int UnknownStreamingReader2; // eax
  int BundlePayloadStreamingReader; // eax
  __int64 v22; // rdx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct IAppxStreamingDataSource **); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, struct IAppxStreamingDataSource **); // rbx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, Appx::Packaging **); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, Appx::Packaging **); // rdi
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, struct IAppxBundleManifestPackageInfo **); // rbx
  int v32; // eax
  __int64 v33; // rdx
  Appx::Packaging *v34; // rcx
  int v36; // [rsp+20h] [rbp-99h]
  struct IAppxBundleManifestPackageInfo *v37; // [rsp+20h] [rbp-99h]
  struct Appx::Packaging::ManifestComparisonHelper *v38; // [rsp+30h] [rbp-89h]
  struct IAppxStreamingDataSource *v39; // [rsp+40h] [rbp-79h] BYREF
  Appx::Packaging *v40; // [rsp+48h] [rbp-71h] BYREF
  int v41[2]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v42; // [rsp+58h] [rbp-61h] BYREF
  struct IAppxBundleManifestPackageInfo *v43; // [rsp+60h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-51h] BYREF
  __int64 v45; // [rsp+70h] [rbp-49h] BYREF
  struct IAppxBundleManifestPackageInfo *v46; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int16 *v47; // [rsp+80h] [rbp-39h] BYREF
  __int64 v48; // [rsp+88h] [rbp-31h] BYREF
  __int64 v49; // [rsp+90h] [rbp-29h] BYREF
  LPCWSTR pwzURI[2]; // [rsp+98h] [rbp-21h] BYREF
  int v51; // [rsp+A8h] [rbp-11h]
  __int128 v52; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( a3 )
  {
    if ( !a4 )
    {
      v8 = 240;
      goto LABEL_3;
    }
    v43 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
    BundlePayloadPackageInfo = Appx::Packaging::Consumption::StreamingReaderHelper::GetBundlePayloadPackageInfo(
                                 *((struct IAppxBundleManifestReader **)this + 4),
                                 a3,
                                 &v43);
    v9 = BundlePayloadPackageInfo;
    if ( BundlePayloadPackageInfo < 0 )
    {
      v11 = 243;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)BundlePayloadPackageInfo,
        v36);
LABEL_55:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
      return v9;
    }
    v49 = 0;
    v48 = 0;
    BundlePayloadPackageInfo = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, __int64 *))v43->lpVtbl->GetOffset)(
                                 v43,
                                 &v49);
    v9 = BundlePayloadPackageInfo;
    if ( BundlePayloadPackageInfo < 0 )
    {
      v11 = 247;
      goto LABEL_10;
    }
    BundlePayloadPackageInfo = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, __int64 *))v43->lpVtbl->GetSize)(
                                 v43,
                                 &v48);
    v9 = BundlePayloadPackageInfo;
    if ( BundlePayloadPackageInfo < 0 )
    {
      v11 = 248;
      goto LABEL_10;
    }
    v40 = 0;
    v39 = 0;
    if ( v49 )
    {
      v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IAppxStreamingDataSource **))*((_QWORD *)this + 36);
      v24 = **v23;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
      v25 = v24(v23, &GUID_3cc7f52c_5d10_4686_8944_713e716ea8da, &v39);
      v9 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)v25,
          v36);
        goto LABEL_17;
      }
    }
    else
    {
      v12 = v43;
      v42 = 0;
      GetPackageId = v43->lpVtbl->GetPackageId;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      v14 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, __int64 *))GetPackageId)(v12, &v42);
      v9 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)v14,
          v36);
LABEL_16:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
LABEL_17:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
        goto LABEL_55;
      }
      pv = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v42 + 72LL))(v42, &pv);
      v9 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)v15,
          v36);
LABEL_20:
        CoTaskMemFree(pv);
        goto LABEL_16;
      }
      v51 = 0;
      *(_OWORD *)pwzURI = 0;
      ExternalPayloadUri = Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(
                             a2,
                             a3,
                             (const unsigned __int16 *)pv,
                             (struct Common::StringBuffer *)pwzURI);
      v9 = ExternalPayloadUri;
      if ( ExternalPayloadUri < 0 )
      {
        v17 = 260;
        goto LABEL_23;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
      ExternalPayloadUri = Appx::Packaging::Consumption::AppxDataSourceFactory::CreateStreamingDataSource(
                             pwzURI[1],
                             &v39);
      v9 = ExternalPayloadUri;
      if ( ExternalPayloadUri < 0 )
      {
        v17 = 261;
        goto LABEL_23;
      }
      v52 = 0;
      ExternalPayloadUri = (*(__int64 (__fastcall **)(struct IAppxStreamingDataSource *, __int128 *))(*(_QWORD *)v39 + 24LL))(
                             v39,
                             &v52);
      v9 = ExternalPayloadUri;
      if ( ExternalPayloadUri < 0 )
      {
        v17 = 263;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)ExternalPayloadUri,
          v36);
        if ( pwzURI[1] )
          operator delete((void *)pwzURI[1], v18);
        goto LABEL_20;
      }
      v48 = v52;
      if ( pwzURI[1] )
        operator delete((void *)pwzURI[1], v19);
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
    }
    *(_QWORD *)v41 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v41);
    UnknownStreamingReader2 = Appx::Packaging::Consumption::BundlePackageStreamingReader::CreateUnknownStreamingReader2(
                                v39,
                                *((_DWORD *)this + 70),
                                *((_QWORD *)this + 39),
                                0,
                                (__int64)v41);
    if ( UnknownStreamingReader2 >= 0 )
    {
      v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, Appx::Packaging **))v41;
      v27 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, Appx::Packaging **))v41;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      BundlePayloadStreamingReader = v27(v26, &GUID_955b4a18_4722_4d2f_b244_ba9897c8b46c, &v40);
      v9 = BundlePayloadStreamingReader;
      if ( BundlePayloadStreamingReader < 0 )
      {
        v22 = 292;
        goto LABEL_35;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)UnknownStreamingReader2,
        (int)v37);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      v38 = (struct Appx::Packaging::ManifestComparisonHelper *)&v40;
      v37 = (struct IAppxBundleManifestPackageInfo *)*((_QWORD *)this + 37);
      BundlePayloadStreamingReader = Appx::Packaging::Consumption::AppxEncryptedPackageLoader::CreateBundlePayloadStreamingReader(
                                       *((unsigned int *)this + 70),
                                       v39,
                                       v49,
                                       v48);
      v9 = BundlePayloadStreamingReader;
      if ( BundlePayloadStreamingReader < 0 )
      {
        v22 = 288;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)BundlePayloadStreamingReader,
          (int)v37);
LABEL_36:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v41);
        goto LABEL_17;
      }
    }
    v45 = 0;
    v28 = Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>::As<IAppxBundleManifestPackageInfo4>(&v43, &v45);
    v9 = v28;
    if ( v28 >= 0 )
    {
      LODWORD(v47) = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v45 + 24LL))(v45, &v47);
      v9 = v28;
      if ( v28 >= 0 )
      {
        v30 = *((_QWORD *)this + 3);
        v46 = 0;
        v31 = *(__int64 (__fastcall **)(__int64, struct IAppxBundleManifestPackageInfo **))(*(_QWORD *)v30 + 40LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        v32 = v31(v30, &v46);
        v9 = v32;
        if ( v32 >= 0 )
        {
          v32 = Appx::Packaging::ValidateBundlePayloadPackage(
                  v40,
                  (struct IAppxPackageReader *)a3,
                  (const unsigned __int16 *)(unsigned int)v47,
                  (int)v43,
                  v46,
                  (struct IUri *)this + 8,
                  v38);
          v9 = v32;
          if ( v32 >= 0 )
          {
            v34 = v40;
            if ( v40 )
            {
              (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v40 + 8LL))(v40);
              v34 = v40;
            }
            *a4 = v34;
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v41);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
            v9 = 0;
            goto LABEL_55;
          }
          v33 = 301;
        }
        else
        {
          v33 = 300;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)v32,
          (int)v37);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        goto LABEL_44;
      }
      v29 = 298;
    }
    else
    {
      v29 = 296;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)v28,
      (int)v37);
LABEL_44:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    goto LABEL_36;
  }
  v8 = 239;
LABEL_3:
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
    (const char *)0x80004003LL,
    v36);
  return v9;
}

```

## disassembly

```asm
0x1800932b0  push    rbp
0x1800932b2  push    rbx
0x1800932b3  push    rsi
0x1800932b4  push    rdi
0x1800932b5  push    r12
0x1800932b7  push    r13
0x1800932b9  push    r14
0x1800932bb  push    r15
0x1800932bd  lea     rbp, [rsp-1Fh]
0x1800932c2  sub     rsp, 0D8h
0x1800932c9  mov     rax, cs:__security_cookie
0x1800932d0  xor     rax, rsp
0x1800932d3  mov     [rbp+57h+var_50], rax
0x1800932d7  xor     r13d, r13d
0x1800932da  mov     r15, r9
0x1800932dd  mov     r14, r8
0x1800932e0  mov     r12, rdx
0x1800932e3  mov     rsi, rcx
0x1800932e6  test    r8, r8
0x1800932e9  jnz     short loc_18009330D
0x1800932eb  mov     edx, 0EFh; void *
0x1800932f0  mov     rcx, [rbp+5Fh]; this
0x1800932f4  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x1800932fb  mov     ebx, 80004003h
0x180093300  mov     r9d, ebx; char *
0x180093303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093308  jmp     loc_1800937B1
0x18009330d  test    r15, r15
0x180093310  jnz     short loc_180093319
0x180093312  mov     edx, 0F0h
0x180093317  jmp     short loc_1800932F0
0x180093319  lea     rcx, [rbp+57h+var_B0]
0x18009331d  mov     [rbp+57h+var_B0], r13
0x180093321  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093326  mov     rcx, [rsi+20h]; struct IAppxBundleManifestReader *
0x18009332a  lea     r8, [rbp+57h+var_B0]; struct IAppxBundleManifestPackageInfo **
0x18009332e  mov     rdx, r14; unsigned __int16 *
0x180093331  call    ?GetBundlePayloadPackageInfo@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestReader@@PEBGPEAPEAUIAppxBundleManifestPackageInfo@@@Z; Appx::Packaging::Consumption::StreamingReaderHelper::GetBundlePayloadPackageInfo(IAppxBundleManifestReader *,ushort const *,IAppxBundleManifestPackageInfo * *)
0x180093336  mov     ebx, eax
0x180093338  test    eax, eax
0x18009333a  jns     short loc_180093343
0x18009333c  mov     edx, 0F3h
0x180093341  jmp     short loc_18009336A
0x180093343  mov     rcx, [rbp+57h+var_B0]
0x180093347  lea     rdx, [rbp+57h+var_80]
0x18009334b  mov     [rbp+57h+var_80], r13
0x18009334f  mov     [rbp+57h+var_88], r13
0x180093353  mov     rax, [rcx]
0x180093356  mov     rax, [rax+30h]
0x18009335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009335f  mov     ebx, eax
0x180093361  test    eax, eax
0x180093363  jns     short loc_180093382
0x180093365  mov     edx, 0F7h; void *
0x18009336a  mov     rcx, [rbp+5Fh]; this
0x18009336e  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x180093375  mov     r9d, eax; char *
0x180093378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009337d  jmp     loc_1800937A8
0x180093382  mov     rcx, [rbp+57h+var_B0]
0x180093386  lea     rdx, [rbp+57h+var_88]
0x18009338a  mov     rax, [rcx]
0x18009338d  mov     rax, [rax+38h]
0x180093391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093396  mov     ebx, eax
0x180093398  test    eax, eax
0x18009339a  jns     short loc_1800933A3
0x18009339c  mov     edx, 0F8h
0x1800933a1  jmp     short loc_18009336A
0x1800933a3  mov     [rbp+57h+var_C8], r13
0x1800933a7  mov     [rbp+57h+var_D0], r13
0x1800933ab  cmp     [rbp+57h+var_80], r13
0x1800933af  jnz     loc_1800935E8
0x1800933b5  mov     rdi, [rbp+57h+var_B0]
0x1800933b9  lea     rcx, [rbp+57h+var_B8]
0x1800933bd  mov     [rbp+57h+var_B8], r13
0x1800933c1  mov     rax, [rdi]
0x1800933c4  mov     rbx, [rax+20h]
0x1800933c8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800933cd  lea     rdx, [rbp+57h+var_B8]
0x1800933d1  mov     rcx, rdi
0x1800933d4  mov     rax, rbx
0x1800933d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800933dc  mov     ebx, eax
0x1800933de  test    eax, eax
0x1800933e0  jns     short loc_18009341A
0x1800933e2  mov     rcx, [rbp+5Fh]; this
0x1800933e6  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x1800933ed  mov     r9d, eax; char *
0x1800933f0  mov     edx, 0FFh; void *
0x1800933f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800933fa  lea     rcx, [rbp+57h+var_B8]
0x1800933fe  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093403  lea     rcx, [rbp+57h+var_D0]
0x180093407  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009340c  lea     rcx, [rbp+57h+var_C8]
0x180093410  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093415  jmp     loc_1800937A8
0x18009341a  mov     rcx, [rbp+57h+var_B8]
0x18009341e  lea     rdx, [rbp+57h+pv]
0x180093422  mov     [rbp+57h+pv], r13
0x180093426  mov     rax, [rcx]
0x180093429  mov     rax, [rax+48h]
0x18009342d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093432  mov     ebx, eax
0x180093434  test    eax, eax
0x180093436  jns     short loc_180093462
0x180093438  mov     rcx, [rbp+5Fh]; this
0x18009343c  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x180093443  mov     r9d, eax; char *
0x180093446  mov     edx, 101h; void *
0x18009344b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093450  mov     rcx, [rbp+57h+pv]; pv
0x180093454  call    cs:__imp_CoTaskMemFree
0x18009345b  nop     dword ptr [rax+rax+00h]
0x180093460  jmp     short loc_1800933FA
0x180093462  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x180093466  lea     r9, [rbp+57h+pwzURI]; struct Common::StringBuffer *
0x18009346a  xorps   xmm0, xmm0
0x18009346d  mov     [rbp+57h+var_68], r13d
0x180093471  mov     rdx, r14; unsigned __int16 *
0x180093474  mov     rcx, r12; unsigned __int16 *
0x180093477  movups  xmmword ptr [rbp+57h+pwzURI], xmm0
0x18009347b  call    ?GetExternalPayloadUri@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEBG00AEAVStringBuffer@Common@@@Z; Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(ushort const *,ushort const *,ushort const *,Common::StringBuffer &)
0x180093480  mov     ebx, eax
0x180093482  test    eax, eax
0x180093484  jns     short loc_1800934AE
0x180093486  mov     edx, 104h; void *
0x18009348b  mov     rcx, [rbp+5Fh]; this
0x18009348f  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x180093496  mov     r9d, eax; char *
0x180093499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009349e  mov     rcx, [rbp+57h+pwzURI+8]; void *
0x1800934a2  test    rcx, rcx
0x1800934a5  jz      short loc_180093450
0x1800934a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800934ac  jmp     short loc_180093450
0x1800934ae  lea     rcx, [rbp+57h+var_D0]
0x1800934b2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800934b7  mov     rcx, [rbp+57h+pwzURI+8]; pwzURI
0x1800934bb  lea     rdx, [rbp+57h+var_D0]; struct IAppxStreamingDataSource **
0x1800934bf  call    ?CreateStreamingDataSource@AppxDataSourceFactory@Consumption@Packaging@Appx@@SAJPEBGPEAPEAUIAppxStreamingDataSource@@@Z; Appx::Packaging::Consumption::AppxDataSourceFactory::CreateStreamingDataSource(ushort const *,IAppxStreamingDataSource * *)
0x1800934c4  mov     ebx, eax
0x1800934c6  test    eax, eax
0x1800934c8  jns     short loc_1800934D1
0x1800934ca  mov     edx, 105h
0x1800934cf  jmp     short loc_18009348B
0x1800934d1  mov     rcx, [rbp+57h+var_D0]
0x1800934d5  lea     rdx, [rbp+57h+var_60]
0x1800934d9  xorps   xmm0, xmm0
0x1800934dc  movups  [rbp+57h+var_60], xmm0
0x1800934e0  mov     rax, [rcx]
0x1800934e3  mov     rax, [rax+18h]
0x1800934e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934ec  mov     ebx, eax
0x1800934ee  test    eax, eax
0x1800934f0  jns     short loc_1800934F9
0x1800934f2  mov     edx, 107h
0x1800934f7  jmp     short loc_18009348B
0x1800934f9  mov     rcx, [rbp+57h+pwzURI+8]; void *
0x1800934fd  mov     rax, qword ptr [rbp+57h+var_60]
0x180093501  mov     [rbp+57h+var_88], rax
0x180093505  test    rcx, rcx
0x180093508  jz      short loc_18009350F
0x18009350a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009350f  mov     rcx, [rbp+57h+pv]; pv
0x180093513  call    cs:__imp_CoTaskMemFree
0x18009351a  nop     dword ptr [rax+rax+00h]
0x18009351f  lea     rcx, [rbp+57h+var_B8]
0x180093523  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093528  lea     rcx, [rbp+57h+var_C0]
0x18009352c  mov     qword ptr [rbp+57h+var_C0], r13
0x180093530  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093535  mov     r8, [rsi+138h]
0x18009353c  lea     rax, [rbp+57h+var_C0]
0x180093540  mov     edx, [rsi+118h]
0x180093546  xor     r9d, r9d
0x180093549  mov     rcx, [rbp+57h+var_D0]
0x18009354d  mov     [rsp+110h+var_F0], rax; int
0x180093552  call    ?CreateUnknownStreamingReader2@BundlePackageStreamingReader@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@W4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxFootprintFileDownloadProgressHandler@@PEBGPEAPEAUIUnknown@@@Z; Appx::Packaging::Consumption::BundlePackageStreamingReader::CreateUnknownStreamingReader2(IAppxStreamingDataSource *,APPX_PACKAGE_READER_OPTIONS,IAppxFootprintFileDownloadProgressHandler *,ushort const *,IUnknown * *)
0x180093557  test    eax, eax
0x180093559  jns     loc_18009363B
0x18009355f  mov     rcx, [rbp+5Fh]; this
0x180093563  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18009356a  mov     r9d, eax; char *
0x18009356d  mov     edx, 118h; void *
0x180093572  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093577  lea     rcx, [rbp+57h+var_C8]
0x18009357b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093580  mov     r9, [rbp+57h+var_88]
0x180093584  lea     rax, [rbp+57h+var_C8]
0x180093588  mov     r8, [rbp+57h+var_80]
0x18009358c  mov     rdx, [rbp+57h+var_D0]
0x180093590  mov     ecx, [rsi+118h]
0x180093596  mov     [rsp+110h+var_E0], rax; struct Appx::Packaging::ManifestComparisonHelper *
0x18009359b  mov     rax, [rsi+138h]
0x1800935a2  mov     [rsp+110h+var_E8], rax
0x1800935a7  mov     rax, [rsi+128h]
0x1800935ae  mov     [rsp+110h+var_F0], rax; int
0x1800935b3  call    ?CreateBundlePayloadStreamingReader@AppxEncryptedPackageLoader@Consumption@Packaging@Appx@@SAJW4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxStreamingDataSource@@_K2PEAVAppxEncryptionSettings@34@PEAUIAppxFootprintFileDownloadProgressHandler@@PEAPEAUIAppxPackageStreamingReader@@@Z; Appx::Packaging::Consumption::AppxEncryptedPackageLoader::CreateBundlePayloadStreamingReader(APPX_PACKAGE_READER_OPTIONS,IAppxStreamingDataSource *,unsigned __int64,unsigned __int64,Appx::Packaging::AppxEncryptionSettings *,IAppxFootprintFileDownloadProgressHandler *,IAppxPackageStreamingReader * *)
0x1800935b8  mov     ebx, eax
0x1800935ba  test    eax, eax
0x1800935bc  jns     loc_180093674
0x1800935c2  mov     edx, 120h; void *
0x1800935c7  mov     rcx, [rbp+5Fh]; this
0x1800935cb  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x1800935d2  mov     r9d, eax; char *
0x1800935d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800935da  lea     rcx, [rbp+57h+var_C0]
0x1800935de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800935e3  jmp     loc_180093403
0x1800935e8  mov     rdi, [rsi+120h]
0x1800935ef  lea     rcx, [rbp+57h+var_D0]
0x1800935f3  mov     rax, [rdi]
0x1800935f6  mov     rbx, [rax]
0x1800935f9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800935fe  lea     r8, [rbp+57h+var_D0]
0x180093602  mov     rcx, rdi
0x180093605  lea     rdx, _GUID_3cc7f52c_5d10_4686_8944_713e716ea8da
0x18009360c  mov     rax, rbx
0x18009360f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093614  mov     ebx, eax
0x180093616  test    eax, eax
0x180093618  jns     loc_180093528
0x18009361e  mov     rcx, [rbp+5Fh]; this
0x180093622  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x180093629  mov     r9d, eax; char *
0x18009362c  mov     edx, 10Ch; void *
0x180093631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093636  jmp     loc_180093403
0x18009363b  mov     rbx, qword ptr [rbp+57h+var_C0]
0x18009363f  lea     rcx, [rbp+57h+var_C8]
0x180093643  mov     rax, [rbx]
0x180093646  mov     rdi, [rax]
0x180093649  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009364e  lea     r8, [rbp+57h+var_C8]
0x180093652  mov     rcx, rbx
0x180093655  lea     rdx, _GUID_955b4a18_4722_4d2f_b244_ba9897c8b46c
0x18009365c  mov     rax, rdi
0x18009365f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093664  mov     ebx, eax
0x180093666  test    eax, eax
0x180093668  jns     short loc_180093674
0x18009366a  mov     edx, 124h
0x18009366f  jmp     loc_1800935C7
0x180093674  lea     rdx, [rbp+57h+var_A0]
0x180093678  mov     [rbp+57h+var_A0], r13
0x18009367c  lea     rcx, [rbp+57h+var_B0]
0x180093680  call    ??$As@UIAppxBundleManifestPackageInfo4@@@?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>::As<IAppxBundleManifestPackageInfo4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo4>>)
0x180093685  mov     ebx, eax
0x180093687  test    eax, eax
0x180093689  jns     short loc_1800936B1
0x18009368b  mov     edx, 128h; void *
0x180093690  mov     rcx, [rbp+5Fh]; this
0x180093694  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18009369b  mov     r9d, eax; char *
0x18009369e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800936a3  lea     rcx, [rbp+57h+var_A0]
0x1800936a7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800936ac  jmp     loc_1800935DA
0x1800936b1  mov     rcx, [rbp+57h+var_A0]
0x1800936b5  lea     rdx, [rbp+57h+var_90]
0x1800936b9  mov     dword ptr [rbp+57h+var_90], r13d
0x1800936bd  mov     rax, [rcx]
0x1800936c0  mov     rax, [rax+18h]
0x1800936c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936c9  mov     ebx, eax
0x1800936cb  test    eax, eax
0x1800936cd  jns     short loc_1800936D6
0x1800936cf  mov     edx, 12Ah
0x1800936d4  jmp     short loc_180093690
0x1800936d6  mov     rdi, [rsi+18h]
0x1800936da  lea     rcx, [rbp+57h+var_98]
0x1800936de  mov     [rbp+57h+var_98], r13
0x1800936e2  mov     rax, [rdi]
0x1800936e5  mov     rbx, [rax+28h]
0x1800936e9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800936ee  lea     rdx, [rbp+57h+var_98]
0x1800936f2  mov     rcx, rdi
0x1800936f5  mov     rax, rbx
0x1800936f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936fd  mov     ebx, eax
0x1800936ff  test    eax, eax
0x180093701  jns     short loc_180093729
0x180093703  mov     edx, 12Ch; void *
0x180093708  mov     rcx, [rbp+5Fh]; this
0x18009370c  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x180093713  mov     r9d, eax; char *
0x180093716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009371b  lea     rcx, [rbp+57h+var_98]
0x18009371f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180093724  jmp     loc_1800936A3
0x180093729  mov     r10, [rbp+57h+var_98]
0x18009372d  lea     rax, [rsi+40h]
0x180093731  mov     r9, [rbp+57h+var_B0]; int
0x180093735  mov     rdx, r14; struct IAppxPackageReader *
0x180093738  mov     r8d, dword ptr [rbp+57h+var_90]; unsigned __int16 *
0x18009373c  mov     rcx, [rbp+57h+var_C8]; this
0x180093740  mov     [rsp+110h+var_E8], rax; struct IUri *
0x180093745  mov     [rsp+110h+var_F0], r10; struct IAppxBundleManifestPackageInfo *
  ... truncated ...
```

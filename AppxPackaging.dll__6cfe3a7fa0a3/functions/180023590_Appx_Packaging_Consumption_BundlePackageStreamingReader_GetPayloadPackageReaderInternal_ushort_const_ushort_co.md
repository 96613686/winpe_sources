# Appx::Packaging::Consumption::BundlePackageStreamingReader::GetPayloadPackageReaderInternal(ushort const *,ushort const *,IAppxPackageStreamingReader * *)

- ea: `0x180023590`
- end: `0x180023adf`
- name: `?GetPayloadPackageReaderInternal@BundlePackageStreamingReader@Consumption@Packaging@Appx@@AEAAJPEBG0PEAPEAUIAppxPackageStreamingReader@@@Z`
- size: `1359`
- prototype: `__int64 __fastcall(Appx::Packaging::Consumption::BundlePackageStreamingReader *this, const unsigned __int16 *, unsigned __int16 *, struct IAppxPackageStreamingReader **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180060390`
- `0x1800cbbe0`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180022c8c`
- `0x180022cec`
- `0x180022d84`
- `0x180023590`
- `0x180023ae8`
- `0x1800433e0`
- `0x1800992c4`
- `0x1800cb53c`
- `0x1800cf090`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002391a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800238b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002391a`

## string_xrefs

- `0x1800237df`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x18002382c`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x18002384d`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800238e9`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023944`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023986`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800239c1`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023a3c`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023a62`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023a9f`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180023ab4`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::BundlePackageStreamingReader::GetPayloadPackageReaderInternal(
        Appx::Packaging::Consumption::BundlePackageStreamingReader *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IAppxPackageStreamingReader **a4)
{
  int BundlePayloadPackageInfo; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  LPVOID v12; // rbx
  __int64 v13; // r8
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, struct IAppxBundleManifestPackageInfo **); // rbx
  int v19; // eax
  int v20; // eax
  Appx::Packaging *v21; // rcx
  struct IAppxBundleManifestPackageInfo *v22; // rdx
  __int64 v23; // rdx
  struct IAppxBundleManifestPackageInfo *v24; // rcx
  struct IAppxBundleManifestPackageInfo *v26; // rcx
  __int64 v27; // rdx
  struct IAppxBundleManifestPackageInfo *v28; // rcx
  __int64 v29; // rcx
  Appx::Packaging *v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // rdx
  struct IAppxBundleManifestPackageInfo *v33; // rdi
  HRESULT (__stdcall *GetPackageId)(IAppxBundleManifestPackageInfo *, IAppxManifestPackageId **); // rbx
  int v35; // eax
  int v36; // eax
  int ExternalPayloadUri; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned __int64 v40; // rdx
  __int64 v41; // rdx
  int v42; // [rsp+20h] [rbp-59h]
  int v43; // [rsp+20h] [rbp-59h]
  Appx::Packaging *v44; // [rsp+30h] [rbp-49h] BYREF
  struct IAppxBundleManifestPackageInfo *v45; // [rsp+38h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-39h] BYREF
  __int64 v47; // [rsp+48h] [rbp-31h] BYREF
  __int64 v48; // [rsp+50h] [rbp-29h] BYREF
  struct IAppxBundleManifestPackageInfo *v49; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v50; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v51; // [rsp+68h] [rbp-11h] BYREF
  void *v52[2]; // [rsp+70h] [rbp-9h] BYREF
  int v53; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned __int16 *v55; // [rsp+F0h] [rbp+77h] BYREF

  if ( !a3 )
  {
    v27 = 175;
LABEL_31:
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)0x80004003LL,
      v42);
    return v9;
  }
  if ( !a4 )
  {
    v27 = 176;
    goto LABEL_31;
  }
  v45 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
  BundlePayloadPackageInfo = Appx::Packaging::Consumption::StreamingReaderHelper::GetBundlePayloadPackageInfo(
                               *((struct IAppxBundleManifestReader **)this + 8),
                               a3,
                               &v45);
  v9 = BundlePayloadPackageInfo;
  if ( BundlePayloadPackageInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)BundlePayloadPackageInfo,
      v42);
LABEL_27:
    v26 = v45;
    if ( v45 )
    {
      v45 = 0;
      ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v26->lpVtbl->Release)(v26);
    }
    return v9;
  }
  v50 = 0;
  v51 = 0;
  v10 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, unsigned __int64 *))v45->lpVtbl->GetOffset)(
          v45,
          &v50);
  v9 = v10;
  if ( v10 < 0 )
  {
    v32 = 186;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v10,
      v42);
    goto LABEL_42;
  }
  v10 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, unsigned __int64 *))v45->lpVtbl->GetSize)(
          v45,
          &v51);
  v9 = v10;
  if ( v10 < 0 )
  {
    v32 = 187;
    goto LABEL_50;
  }
  v44 = 0;
  if ( !v50 )
  {
    v33 = v45;
    v48 = 0;
    GetPackageId = v45->lpVtbl->GetPackageId;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
    v35 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, __int64 *))GetPackageId)(v33, &v48);
    v9 = v35;
    if ( v35 >= 0 )
    {
      pv = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v48 + 72LL))(v48, &pv);
      v9 = v36;
      if ( v36 >= 0 )
      {
        v53 = 0;
        *(_OWORD *)v52 = 0;
        ExternalPayloadUri = Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(
                               a2,
                               a3,
                               (const unsigned __int16 *)pv,
                               (struct Common::StringBuffer *)v52);
        v9 = ExternalPayloadUri;
        if ( ExternalPayloadUri >= 0 )
        {
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
          ExternalPayloadUri = Appx::Packaging::Consumption::AppxPackageStreamingReader::Create(
                                 v52[1],
                                 *((unsigned int *)this + 52),
                                 v39,
                                 &v44);
          v9 = ExternalPayloadUri;
          if ( ExternalPayloadUri >= 0 )
          {
            if ( v52[1] )
              operator delete(v52[1], v40);
            CoTaskMemFree(pv);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
            goto LABEL_11;
          }
          v38 = 200;
        }
        else
        {
          v38 = 199;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
          (const char *)(unsigned int)ExternalPayloadUri,
          v42);
        if ( v52[1] )
          operator delete(v52[1], v31);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
          (const char *)(unsigned int)v36,
          v42);
      }
      CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
        (const char *)(unsigned int)v35,
        v42);
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
LABEL_41:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
LABEL_42:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    return v9;
  }
  pv = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
  v11 = Appx::Packaging::Consumption::BundlePayloadStreamingDataSource::Create(
          *((struct IAppxStreamingDataSource **)this + 25),
          v50,
          v51,
          (struct IAppxStreamingDataSource **)&pv);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v11,
      v42);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
    goto LABEL_41;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
  v12 = pv;
  v14 = Appx::Packaging::Consumption::AppxPackageStreamingReader::Create(pv, *((unsigned int *)this + 52), v13, &v44);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v14,
      v42);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pv);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
    v9 = v15;
    goto LABEL_42;
  }
  if ( v12 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_11:
  v47 = 0;
  v16 = Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>::As<IAppxBundleManifestPackageInfo4>(&v45, &v47);
  v9 = v16;
  if ( v16 < 0 )
  {
    v41 = 214;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v16,
      v42);
LABEL_65:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
    goto LABEL_41;
  }
  LODWORD(v55) = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v47 + 24LL))(v47, &v55);
  v9 = v16;
  if ( v16 < 0 )
  {
    v41 = 216;
    goto LABEL_63;
  }
  v17 = *((_QWORD *)this + 7);
  v49 = 0;
  v18 = *(__int64 (__fastcall **)(__int64, struct IAppxBundleManifestPackageInfo **))(*(_QWORD *)v17 + 40LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
  v19 = v18(v17, &v49);
  v9 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v19,
      v42);
    v28 = v49;
    if ( v49 )
    {
      v49 = 0;
      ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v28->lpVtbl->Release)(v28);
    }
    v29 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_27;
  }
  v20 = Appx::Packaging::ValidateBundlePayloadPackage(
          v44,
          (struct IAppxPackageReader *)a3,
          (const unsigned __int16 *)(unsigned int)v55,
          (int)v45,
          v49,
          *((struct IUri **)this + 12),
          v44);
  v9 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v20,
      v43);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    goto LABEL_65;
  }
  v21 = v44;
  if ( v44 )
  {
    (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v44 + 8LL))(v44);
    v21 = v44;
  }
  v22 = v49;
  *a4 = v21;
  if ( v22 )
  {
    v49 = 0;
    ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v22->lpVtbl->Release)(v22);
    v21 = v44;
  }
  v23 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v21 = v44;
  }
  if ( v21 )
  {
    v44 = 0;
    (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v24 = v45;
  if ( v45 )
  {
    v45 = 0;
    ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v24->lpVtbl->Release)(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180023590  push    rbp
0x180023592  push    rbx
0x180023593  push    rsi
0x180023594  push    rdi
0x180023595  push    r12
0x180023597  push    r13
0x180023599  push    r14
0x18002359b  push    r15
0x18002359d  lea     rbp, [rsp-1Fh]
0x1800235a2  sub     rsp, 98h
0x1800235a9  xor     r13d, r13d
0x1800235ac  mov     r15, r9
0x1800235af  mov     r14, r8
0x1800235b2  mov     r12, rdx
0x1800235b5  mov     rsi, rcx
0x1800235b8  test    r8, r8
0x1800235bb  jz      loc_180023823
0x1800235c1  test    r9, r9
0x1800235c4  jz      loc_180023842
0x1800235ca  lea     rcx, [rbp+57h+var_98]
0x1800235ce  mov     [rbp+57h+var_98], r13
0x1800235d2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800235d7  mov     rcx, [rsi+40h]; struct IAppxBundleManifestReader *
0x1800235db  lea     r8, [rbp+57h+var_98]; struct IAppxBundleManifestPackageInfo **
0x1800235df  mov     rdx, r14; unsigned __int16 *
0x1800235e2  call    ?GetBundlePayloadPackageInfo@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestReader@@PEBGPEAPEAUIAppxBundleManifestPackageInfo@@@Z; Appx::Packaging::Consumption::StreamingReaderHelper::GetBundlePayloadPackageInfo(IAppxBundleManifestReader *,ushort const *,IAppxBundleManifestPackageInfo * *)
0x1800235e7  mov     ebx, eax
0x1800235e9  test    eax, eax
0x1800235eb  js      loc_1800237DB
0x1800235f1  mov     rcx, [rbp+57h+var_98]
0x1800235f5  lea     rdx, [rbp+57h+var_70]
0x1800235f9  mov     [rbp+57h+var_70], r13
0x1800235fd  mov     [rbp+57h+var_68], r13
0x180023601  mov     rax, [rcx]
0x180023604  mov     rax, [rax+30h]
0x180023608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002360d  mov     ebx, eax
0x18002360f  test    eax, eax
0x180023611  js      loc_180023934
0x180023617  mov     rcx, [rbp+57h+var_98]
0x18002361b  lea     rdx, [rbp+57h+var_68]
0x18002361f  mov     rax, [rcx]
0x180023622  mov     rax, [rax+38h]
0x180023626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002362b  mov     ebx, eax
0x18002362d  test    eax, eax
0x18002362f  js      loc_18002393B
0x180023635  mov     [rbp+57h+var_A0], r13
0x180023639  cmp     [rbp+57h+var_70], r13
0x18002363d  jz      loc_180023955
0x180023643  lea     rcx, [rbp+57h+pv]
0x180023647  mov     [rbp+57h+pv], r13
0x18002364b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180023650  mov     r8, [rbp+57h+var_68]; unsigned __int64
0x180023654  lea     r9, [rbp+57h+pv]; struct IAppxStreamingDataSource **
0x180023658  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x18002365c  mov     rcx, [rsi+0C8h]; struct IAppxStreamingDataSource *
0x180023663  call    ?Create@BundlePayloadStreamingDataSource@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@_K1PEAPEAU5@@Z; Appx::Packaging::Consumption::BundlePayloadStreamingDataSource::Create(IAppxStreamingDataSource *,unsigned __int64,unsigned __int64,IAppxStreamingDataSource * *)
0x180023668  mov     ebx, eax
0x18002366a  test    eax, eax
0x18002366c  js      loc_180023A38
0x180023672  lea     rcx, [rbp+57h+var_A0]
0x180023676  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18002367b  mov     rbx, [rbp+57h+pv]
0x18002367f  lea     r9, [rbp+57h+var_A0]
0x180023683  mov     edx, [rsi+0D0h]
0x180023689  mov     rcx, rbx
0x18002368c  call    ?Create@AppxPackageStreamingReader@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@W4APPX_PACKAGE_READER_OPTIONS@@PEBGPEAPEAUIAppxPackageStreamingReader@@@Z; Appx::Packaging::Consumption::AppxPackageStreamingReader::Create(IAppxStreamingDataSource *,APPX_PACKAGE_READER_OPTIONS,ushort const *,IAppxPackageStreamingReader * *)
0x180023691  mov     edi, eax
0x180023693  test    eax, eax
0x180023695  js      loc_180023A5E
0x18002369b  test    rbx, rbx
0x18002369e  jz      short loc_1800236AF
0x1800236a0  mov     rax, [rbx]
0x1800236a3  mov     rcx, rbx
0x1800236a6  mov     rax, [rax+10h]
0x1800236aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236af  lea     rdx, [rbp+57h+var_88]
0x1800236b3  mov     [rbp+57h+var_88], r13
0x1800236b7  lea     rcx, [rbp+57h+var_98]
0x1800236bb  call    ??$As@UIAppxBundleManifestPackageInfo4@@@?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>::As<IAppxBundleManifestPackageInfo4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo4>>)
0x1800236c0  mov     ebx, eax
0x1800236c2  test    eax, eax
0x1800236c4  js      loc_180023A8F
0x1800236ca  mov     rcx, [rbp+57h+var_88]
0x1800236ce  lea     rdx, [rbp+57h+arg_10]
0x1800236d2  mov     dword ptr [rbp+57h+arg_10], r13d
0x1800236d6  mov     rax, [rcx]
0x1800236d9  mov     rax, [rax+18h]
0x1800236dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236e2  mov     ebx, eax
0x1800236e4  test    eax, eax
0x1800236e6  js      loc_180023A96
0x1800236ec  mov     rdi, [rsi+38h]
0x1800236f0  lea     rcx, [rbp+57h+var_78]
0x1800236f4  mov     [rbp+57h+var_78], r13
0x1800236f8  mov     rax, [rdi]
0x1800236fb  mov     rbx, [rax+28h]
0x1800236ff  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180023704  lea     rdx, [rbp+57h+var_78]
0x180023708  mov     rcx, rdi
0x18002370b  mov     rax, rbx
0x18002370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023713  mov     ebx, eax
0x180023715  test    eax, eax
0x180023717  js      loc_180023849
0x18002371d  mov     rdx, [rbp+57h+var_78]
0x180023721  mov     rax, [rsi+60h]
0x180023725  mov     r9, [rbp+57h+var_98]; int
0x180023729  mov     r8d, dword ptr [rbp+57h+arg_10]; unsigned __int16 *
0x18002372d  mov     rcx, [rbp+57h+var_A0]; this
0x180023731  mov     [rsp+0D0h+var_A8], rax; struct IUri *
0x180023736  mov     [rsp+0D0h+var_B0], rdx; int
0x18002373b  mov     rdx, r14; struct IAppxPackageReader *
0x18002373e  call    ?ValidateBundlePayloadPackage@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEBGHPEAUIAppxBundleManifestPackageInfo@@PEAUIUri@@PEAVManifestComparisonHelper@12@@Z; Appx::Packaging::ValidateBundlePayloadPackage(IAppxPackageReader *,ushort const *,int,IAppxBundleManifestPackageInfo *,IUri *,Appx::Packaging::ManifestComparisonHelper *)
0x180023743  mov     ebx, eax
0x180023745  test    eax, eax
0x180023747  js      loc_180023AB0
0x18002374d  mov     rcx, [rbp+57h+var_A0]
0x180023751  test    rcx, rcx
0x180023754  jz      short loc_180023766
0x180023756  mov     rax, [rcx]
0x180023759  mov     rax, [rax+8]
0x18002375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023762  mov     rcx, [rbp+57h+var_A0]
0x180023766  mov     rdx, [rbp+57h+var_78]
0x18002376a  mov     [r15], rcx
0x18002376d  test    rdx, rdx
0x180023770  jz      short loc_180023789
0x180023772  mov     [rbp+57h+var_78], r13
0x180023776  mov     rcx, rdx
0x180023779  mov     rax, [rdx]
0x18002377c  mov     rax, [rax+10h]
0x180023780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023785  mov     rcx, [rbp+57h+var_A0]
0x180023789  mov     rdx, [rbp+57h+var_88]
0x18002378d  test    rdx, rdx
0x180023790  jz      short loc_1800237A9
0x180023792  mov     [rbp+57h+var_88], r13
0x180023796  mov     rcx, rdx
0x180023799  mov     rax, [rdx]
0x18002379c  mov     rax, [rax+10h]
0x1800237a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237a5  mov     rcx, [rbp+57h+var_A0]
0x1800237a9  test    rcx, rcx
0x1800237ac  jz      short loc_1800237BE
0x1800237ae  mov     [rbp+57h+var_A0], r13
0x1800237b2  mov     rax, [rcx]
0x1800237b5  mov     rax, [rax+10h]
0x1800237b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237be  mov     rcx, [rbp+57h+var_98]
0x1800237c2  test    rcx, rcx
0x1800237c5  jz      short loc_1800237D7
0x1800237c7  mov     [rbp+57h+var_98], r13
0x1800237cb  mov     rax, [rcx]
0x1800237ce  mov     rax, [rax+10h]
0x1800237d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237d7  xor     eax, eax
0x1800237d9  jmp     short loc_18002380E
0x1800237db  mov     rcx, [rbp+5Fh]; this
0x1800237df  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x1800237e6  mov     r9d, ebx; char *
0x1800237e9  mov     edx, 0B6h; void *
0x1800237ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800237f3  mov     rcx, [rbp+57h+var_98]
0x1800237f7  test    rcx, rcx
0x1800237fa  jz      short loc_18002380C
0x1800237fc  mov     [rbp+57h+var_98], r13
0x180023800  mov     rax, [rcx]
0x180023803  mov     rax, [rax+10h]
0x180023807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002380c  mov     eax, ebx
0x18002380e  add     rsp, 98h
0x180023815  pop     r15
0x180023817  pop     r14
0x180023819  pop     r13
0x18002381b  pop     r12
0x18002381d  pop     rdi
0x18002381e  pop     rsi
0x18002381f  pop     rbx
0x180023820  pop     rbp
0x180023821  retn
0x180023823  mov     edx, 0AFh; void *
0x180023828  mov     rcx, [rbp+5Fh]; this
0x18002382c  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x180023833  mov     ebx, 80004003h
0x180023838  mov     r9d, ebx; char *
0x18002383b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023840  jmp     short loc_18002380C
0x180023842  mov     edx, 0B0h
0x180023847  jmp     short loc_180023828
0x180023849  mov     rcx, [rbp+5Fh]; this
0x18002384d  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x180023854  mov     r9d, ebx; char *
0x180023857  mov     edx, 0DAh; void *
0x18002385c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023861  mov     rcx, [rbp+57h+var_78]
0x180023865  test    rcx, rcx
0x180023868  jz      short loc_18002387A
0x18002386a  mov     [rbp+57h+var_78], r13
0x18002386e  mov     rax, [rcx]
0x180023871  mov     rax, [rax+10h]
0x180023875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002387a  mov     rcx, [rbp+57h+var_88]
0x18002387e  test    rcx, rcx
0x180023881  jz      short loc_180023893
0x180023883  mov     [rbp+57h+var_88], r13
0x180023887  mov     rax, [rcx]
0x18002388a  mov     rax, [rax+10h]
0x18002388e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023893  mov     rcx, [rbp+57h+var_A0]
0x180023897  test    rcx, rcx
0x18002389a  jz      loc_1800237F3
0x1800238a0  mov     [rbp+57h+var_A0], r13
0x1800238a4  mov     rax, [rcx]
0x1800238a7  mov     rax, [rax+10h]
0x1800238ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238b0  jmp     loc_1800237F3
0x1800238b5  mov     rcx, [rbp+57h+pv]; pv
0x1800238b9  call    cs:__imp_CoTaskMemFree
0x1800238c0  nop     dword ptr [rax+rax+00h]
0x1800238c5  lea     rcx, [rbp+57h+var_80]
0x1800238c9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800238ce  lea     rcx, [rbp+57h+var_A0]
0x1800238d2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800238d7  lea     rcx, [rbp+57h+var_98]
0x1800238db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800238e0  jmp     loc_18002380C
0x1800238e5  mov     rcx, [rbp+5Fh]; this
0x1800238e9  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x1800238f0  mov     r9d, eax; char *
0x1800238f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238f8  mov     rcx, [rbp+57h+var_60+8]; void *
0x1800238fc  test    rcx, rcx
0x1800238ff  jz      short loc_1800238B5
0x180023901  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023906  jmp     short loc_1800238B5
0x180023908  mov     rcx, [rbp+57h+var_60+8]; void *
0x18002390c  test    rcx, rcx
0x18002390f  jz      short loc_180023916
0x180023911  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023916  mov     rcx, [rbp+57h+pv]; pv
0x18002391a  call    cs:__imp_CoTaskMemFree
0x180023921  nop     dword ptr [rax+rax+00h]
0x180023926  lea     rcx, [rbp+57h+var_80]
0x18002392a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18002392f  jmp     loc_1800236AF
0x180023934  mov     edx, 0BAh
0x180023939  jmp     short loc_180023940
0x18002393b  mov     edx, 0BBh; void *
0x180023940  mov     rcx, [rbp+5Fh]; this
0x180023944  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x18002394b  mov     r9d, eax; char *
0x18002394e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023953  jmp     short loc_1800238D7
0x180023955  mov     rdi, [rbp+57h+var_98]
0x180023959  lea     rcx, [rbp+57h+var_80]
0x18002395d  mov     [rbp+57h+var_80], r13
0x180023961  mov     rax, [rdi]
0x180023964  mov     rbx, [rax+20h]
0x180023968  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18002396d  lea     rdx, [rbp+57h+var_80]
0x180023971  mov     rcx, rdi
0x180023974  mov     rax, rbx
0x180023977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002397c  mov     ebx, eax
0x18002397e  test    eax, eax
0x180023980  jns     short loc_18002399F
0x180023982  mov     rcx, [rbp+5Fh]; this
0x180023986  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x18002398d  mov     r9d, eax; char *
0x180023990  mov     edx, 0C2h; void *
0x180023995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002399a  jmp     loc_1800238C5
0x18002399f  mov     rcx, [rbp+57h+var_80]
0x1800239a3  lea     rdx, [rbp+57h+pv]
0x1800239a7  mov     [rbp+57h+pv], r13
0x1800239ab  mov     rax, [rcx]
0x1800239ae  mov     rax, [rax+48h]
0x1800239b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239b7  mov     ebx, eax
0x1800239b9  test    eax, eax
0x1800239bb  jns     short loc_1800239DA
0x1800239bd  mov     rcx, [rbp+5Fh]; this
0x1800239c1  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x1800239c8  mov     r9d, eax; char *
0x1800239cb  mov     edx, 0C4h; void *
0x1800239d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239d5  jmp     loc_1800238B5
0x1800239da  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x1800239de  lea     r9, [rbp+57h+var_60]; struct Common::StringBuffer *
0x1800239e2  xorps   xmm0, xmm0
0x1800239e5  mov     [rbp+57h+var_50], r13d
0x1800239e9  mov     rdx, r14; unsigned __int16 *
0x1800239ec  mov     rcx, r12; unsigned __int16 *
0x1800239ef  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800239f3  call    ?GetExternalPayloadUri@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEBG00AEAVStringBuffer@Common@@@Z; Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(ushort const *,ushort const *,ushort const *,Common::StringBuffer &)
0x1800239f8  mov     ebx, eax
0x1800239fa  test    eax, eax
0x1800239fc  jns     short loc_180023A08
  ... truncated ...
```

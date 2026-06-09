# Appx::Packaging::Production::BundlePackageWriter::AddPayloadPackageInternal(ushort const *,IStream *,bool)

- ea: `0x180076584`
- end: `0x180076b7b`
- name: `?AddPayloadPackageInternal@BundlePackageWriter@Production@Packaging@Appx@@AEAAJPEBGPEAUIStream@@_N@Z`
- size: `1527`
- prototype: `int(Appx::Packaging::Production::BundlePackageWriter *__hidden this, const unsigned __int16 *, struct IStream *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f05b0`

## callees

- `0x180005eb8`
- `0x180008f4c`
- `0x1800133fc`
- `0x1800292d0`
- `0x1800455ec`
- `0x18004db04`
- `0x180050ae8`
- `0x180071f50`
- `0x180076584`
- `0x180076b84`
- `0x180076bd4`
- `0x18007f7cc`
- `0x1800f06c0`
- `0x1800f2fd0`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800766fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180076730`
- `OLEAUT32!__imp_SysFreeString` at `0x1800766fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180076730`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180076af7`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180076af7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180076b21`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180076b21`

## string_xrefs

- `0x1800765db`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x18007663a`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x18007668f`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800766ec`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180076791`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800768f2`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180076910`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180076933`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800769b1`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180076ab2`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180076b35`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::BundlePackageWriter::AddPayloadPackageInternal(
        Appx::Packaging::Production::BundlePackageWriter *this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        bool a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  struct IAppxPackageReader *v11; // rbx
  HRESULT (__stdcall *GetBlockMap)(IAppxPackageReader *, IAppxBlockMapReader **); // rdi
  int v13; // eax
  int v14; // edi
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rdi
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  OLECHAR *v22; // rcx
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64 *, __int64 *); // rdi
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, struct IStream **); // rdi
  int v31; // eax
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, struct IStream **); // rdi
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rdi
  int BlockReceiver; // eax
  unsigned __int64 *v38; // r8
  __int64 v39; // rdx
  Appx::Packaging *v40; // rcx
  unsigned __int64 *v41; // r8
  unsigned __int64 v42; // rdx
  int v43; // eax
  struct IBlockReceiver *v44; // rbx
  int v45; // eax
  int v46; // [rsp+20h] [rbp-79h]
  int v47; // [rsp+20h] [rbp-79h]
  int v48; // [rsp+20h] [rbp-79h]
  __int64 v49; // [rsp+40h] [rbp-59h] BYREF
  struct IBlockReceiver *v50; // [rsp+48h] [rbp-51h] BYREF
  struct IAppxPackageReader *v51; // [rsp+50h] [rbp-49h] BYREF
  __int64 v52; // [rsp+58h] [rbp-41h] BYREF
  __int64 v53; // [rsp+60h] [rbp-39h] BYREF
  __int64 v54; // [rsp+68h] [rbp-31h] BYREF
  __int64 v55; // [rsp+70h] [rbp-29h] BYREF
  struct IStream *v56; // [rsp+78h] [rbp-21h] BYREF
  int v57; // [rsp+80h] [rbp-19h] BYREF
  struct IStream *v58; // [rsp+88h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v60; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v61[10]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  IErrorInfo *pperrinfo; // [rsp+100h] [rbp+67h] BYREF

  v51 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
  v8 = Appx::Packaging::Consumption::AppxPackageReader::Create(
         (__int64)a3,
         **((_QWORD **)this + 7) == 0,
         0,
         (Appx::Packaging::Consumption::AppxPackageReader **)&v51);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
      (const char *)(unsigned int)v8,
      v46);
LABEL_3:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
    return v9;
  }
  v11 = v51;
  if ( !*((_BYTE *)this + 73) )
  {
    v55 = 0;
    GetBlockMap = v51->lpVtbl->GetBlockMap;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
    v13 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetBlockMap)(v11, &v55);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v13,
        v46);
LABEL_7:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
      goto LABEL_63;
    }
    v54 = 0;
    v15 = v55;
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
    v17 = v16(v15, &v54);
    v14 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v17,
        v46);
LABEL_10:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
      goto LABEL_7;
    }
    Microsoft::WRL::ComPtr<IUri>::operator=(*((_QWORD *)this + 7) + 944LL);
    bstrString = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v54 + 56LL))(v54, &bstrString);
    v14 = v18;
    if ( v18 < 0 )
    {
      v19 = (unsigned int)v18;
      v20 = 158;
LABEL_13:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)v19,
        v46);
      SysFreeString(bstrString);
      goto LABEL_10;
    }
    v21 = Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(
            *((Appx::Packaging::Production::PackageWriterHelper **)this + 6),
            bstrString);
    v14 = v21;
    if ( v21 < 0 )
    {
      v19 = (unsigned int)v21;
      v20 = 159;
      goto LABEL_13;
    }
    v22 = bstrString;
    *((_BYTE *)this + 73) = 1;
    SysFreeString(v22);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
  }
  if ( !*((_BYTE *)this + 74) )
  {
    v49 = 0;
    v57 = 0;
    GetFootprintFile = v11[1].lpVtbl->GetFootprintFile;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    v24 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetFootprintFile)(&v11[1], &v49);
    v14 = v24;
    if ( v24 < 0 )
    {
      v25 = 168;
      goto LABEL_20;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 32LL))(v49, &v57);
    v14 = v24;
    if ( v24 < 0 )
    {
      v25 = 169;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v24,
        v46);
LABEL_21:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      goto LABEL_63;
    }
    while ( v57 )
    {
      v53 = 0;
      v52 = 0;
      v26 = v49;
      v27 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v49 + 24LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
      v28 = v27(v26, &v53, &v52);
      v14 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAE,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)v28,
          v46);
        goto LABEL_38;
      }
      v29 = v53;
      v56 = 0;
      v30 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v53 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
      v31 = v30(v29, &v56);
      v14 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)v31,
          v46);
        goto LABEL_36;
      }
      v32 = v52;
      v58 = 0;
      v33 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v52 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
      v34 = v33(v32, &v58);
      v14 = v34;
      if ( v34 < 0 )
      {
        v35 = 180;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)v34,
          v46);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
LABEL_36:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
LABEL_38:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
        goto LABEL_21;
      }
      v34 = Appx::Packaging::Production::BundlePackageWriter::AddPublisherBridgingArtifact(this, v56, v58);
      v14 = v34;
      if ( v34 < 0 )
      {
        v35 = 182;
        goto LABEL_34;
      }
      v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 40LL))(v49, &v57);
      v14 = v34;
      if ( v34 < 0 )
      {
        v35 = 183;
        goto LABEL_34;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
    }
    *((_BYTE *)this + 74) = 1;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
  }
  v36 = *((_QWORD *)this + 6);
  v50 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  v47 = 0;
  BlockReceiver = Appx::Packaging::Production::PackageWriterHelper::CreateBlockReceiver(
                    v36,
                    a2,
                    2,
                    L"application/vnd.ms-appx");
  v14 = BlockReceiver;
  if ( BlockReceiver < 0 )
  {
    v39 = 195;
LABEL_42:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
      (const char *)(unsigned int)BlockReceiver,
      v47);
LABEL_62:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    goto LABEL_63;
  }
  v40 = (Appx::Packaging *)*((_QWORD *)this + 5);
  v61[0] = 0;
  BlockReceiver = Appx::Packaging::GetStreamCurrentPosition(v40, (struct IStream *)v61, v38);
  v14 = BlockReceiver;
  if ( BlockReceiver < 0 )
  {
    v39 = 201;
    goto LABEL_42;
  }
  v60 = 0;
  BlockReceiver = Appx::Packaging::GetStreamSize(a3, (struct IStream *)&v60, v41);
  v14 = BlockReceiver;
  if ( BlockReceiver < 0 )
  {
    v39 = 204;
    goto LABEL_42;
  }
  LOBYTE(pperrinfo) = 0;
  v42 = -1;
  do
    ++v42;
  while ( a2[v42] );
  BlockReceiver = Appx::Packaging::FileNameHelper::ValidateFileNameAgainstReservedFolder(
                    a2,
                    v42,
                    L"appxmetadata\\stub",
                    0x11u,
                    (bool *)&pperrinfo);
  v14 = BlockReceiver;
  if ( BlockReceiver < 0 )
  {
    v39 = 211;
    goto LABEL_42;
  }
  v43 = Appx::Packaging::Production::BundleManifestWriterHelper::AddPackage(
          *((Appx::Packaging::Production::BundleManifestWriterHelper **)this + 7),
          a2,
          v11,
          v61[0],
          v60,
          a4,
          (bool)pperrinfo);
  v44 = v50;
  v14 = v43;
  if ( v43 < 0
    || (v14 = Appx::Packaging::Production::PackageWriterHelper::AddPartBytes(
                *((Appx::Packaging::HashEngine ***)this + 6),
                a3,
                v50,
                0,
                0,
                0,
                0),
        v14 < 0) )
  {
    pperrinfo = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
    if ( GetErrorInfo(0, &pperrinfo) < 0 )
      goto LABEL_60;
    (*(void (__fastcall **)(struct IBlockReceiver *))(*(_QWORD *)v44 + 32LL))(v44);
    if ( pperrinfo )
      SetErrorInfo(0, pperrinfo);
    if ( v14 < 0 )
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v14,
        v48);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
    goto LABEL_62;
  }
  v45 = (*(__int64 (__fastcall **)(struct IBlockReceiver *))(*(_QWORD *)v44 + 32LL))(v44);
  v9 = v45;
  if ( v45 >= 0 )
  {
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    goto LABEL_3;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xF7,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
    (const char *)(unsigned int)v45,
    v48);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  v14 = v9;
LABEL_63:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180076584  push    rbp
0x180076586  push    rbx
0x180076587  push    rsi
0x180076588  push    rdi
0x180076589  push    r12
0x18007658b  push    r13
0x18007658d  push    r14
0x18007658f  push    r15
0x180076591  lea     rbp, [rsp-1Fh]
0x180076596  sub     rsp, 0B8h
0x18007659d  mov     r14, rcx
0x1800765a0  xor     esi, esi
0x1800765a2  lea     rcx, [rbp+57h+var_A0]
0x1800765a6  mov     [rbp+57h+var_A0], rsi
0x1800765aa  mov     r13b, r9b
0x1800765ad  mov     r12, r8
0x1800765b0  mov     r15, rdx
0x1800765b3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800765b8  mov     rax, [r14+38h]
0x1800765bc  lea     r9, [rbp+57h+var_A0]
0x1800765c0  mov     rcx, r12
0x1800765c3  cmp     [rax], rsi
0x1800765c6  setz    dl
0x1800765c9  xor     r8d, r8d
0x1800765cc  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader> * *)
0x1800765d1  mov     ebx, eax
0x1800765d3  test    eax, eax
0x1800765d5  jns     short loc_1800765FF
0x1800765d7  mov     rcx, [rbp+5Fh]; this
0x1800765db  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800765e2  mov     r9d, eax; char *
0x1800765e5  mov     edx, 92h; void *
0x1800765ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800765ef  lea     rcx, [rbp+57h+var_A0]
0x1800765f3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800765f8  mov     eax, ebx
0x1800765fa  jmp     loc_180076B66
0x1800765ff  mov     rbx, [rbp+57h+var_A0]
0x180076603  cmp     [r14+49h], sil
0x180076607  jnz     loc_18007674E
0x18007660d  mov     [rbp+57h+var_80], rsi
0x180076611  lea     rcx, [rbp+57h+var_80]
0x180076615  mov     rax, [rbx]
0x180076618  mov     rdi, [rax+18h]
0x18007661c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076621  lea     rdx, [rbp+57h+var_80]
0x180076625  mov     rcx, rbx
0x180076628  mov     rax, rdi
0x18007662b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076630  mov     edi, eax
0x180076632  test    eax, eax
0x180076634  jns     short loc_18007665C
0x180076636  mov     rcx, [rbp+5Fh]; this
0x18007663a  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180076641  mov     r9d, eax; char *
0x180076644  mov     edx, 97h; void *
0x180076649  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007664e  lea     rcx, [rbp+57h+var_80]
0x180076652  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076657  jmp     loc_180076B5B
0x18007665c  mov     [rbp+57h+var_88], rsi
0x180076660  lea     rcx, [rbp+57h+var_88]
0x180076664  mov     rsi, [rbp+57h+var_80]
0x180076668  mov     rax, [rsi]
0x18007666b  mov     rdi, [rax+28h]
0x18007666f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076674  lea     rdx, [rbp+57h+var_88]
0x180076678  mov     rcx, rsi
0x18007667b  mov     rax, rdi
0x18007667e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076683  xor     esi, esi
0x180076685  mov     edi, eax
0x180076687  test    eax, eax
0x180076689  jns     short loc_1800766AE
0x18007668b  mov     rcx, [rbp+5Fh]; this
0x18007668f  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180076696  mov     r9d, eax; char *
0x180076699  mov     edx, 9Ah; void *
0x18007669e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800766a3  lea     rcx, [rbp+57h+var_88]
0x1800766a7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800766ac  jmp     short loc_18007664E
0x1800766ae  mov     rcx, [r14+38h]
0x1800766b2  mov     rdx, [rbp+57h+var_88]
0x1800766b6  add     rcx, 3B0h
0x1800766bd  call    ??4?$ComPtr@UIUri@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUri@@@Z; Microsoft::WRL::ComPtr<IUri>::operator=(IUri *)
0x1800766c2  mov     rcx, [rbp+57h+var_88]
0x1800766c6  lea     rdx, [rbp+57h+bstrString]
0x1800766ca  mov     [rbp+57h+bstrString], rsi
0x1800766ce  mov     rax, [rcx]
0x1800766d1  mov     rax, [rax+38h]
0x1800766d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766da  mov     edi, eax
0x1800766dc  test    eax, eax
0x1800766de  jns     short loc_18007670A
0x1800766e0  mov     r9d, eax; char *
0x1800766e3  mov     edx, 9Eh; void *
0x1800766e8  mov     rcx, [rbp+5Fh]; this
0x1800766ec  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800766f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800766f8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800766fc  call    cs:__imp_SysFreeString
0x180076703  nop     dword ptr [rax+rax+00h]
0x180076708  jmp     short loc_1800766A3
0x18007670a  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x18007670e  mov     rcx, [r14+30h]; this
0x180076712  call    ?InitializeBlockMapWriter@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBG@Z; Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(ushort const * const)
0x180076717  mov     edi, eax
0x180076719  test    eax, eax
0x18007671b  jns     short loc_180076727
0x18007671d  mov     r9d, eax
0x180076720  mov     edx, 9Fh
0x180076725  jmp     short loc_1800766E8
0x180076727  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18007672b  mov     byte ptr [r14+49h], 1
0x180076730  call    cs:__imp_SysFreeString
0x180076737  nop     dword ptr [rax+rax+00h]
0x18007673c  lea     rcx, [rbp+57h+var_88]
0x180076740  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076745  lea     rcx, [rbp+57h+var_80]
0x180076749  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007674e  cmp     [r14+4Ah], sil
0x180076752  jnz     loc_18007696C
0x180076758  mov     [rbp+57h+var_B0], rsi
0x18007675c  lea     rcx, [rbp+57h+var_B0]
0x180076760  mov     [rbp+57h+var_70], esi
0x180076763  mov     rax, [rbx+8]
0x180076767  mov     rdi, [rax+20h]
0x18007676b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076770  lea     rdx, [rbp+57h+var_B0]
0x180076774  mov     rax, rdi
0x180076777  lea     rcx, [rbx+8]
0x18007677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076780  xor     esi, esi
0x180076782  mov     edi, eax
0x180076784  test    eax, eax
0x180076786  jns     short loc_1800767AE
0x180076788  mov     edx, 0A8h; void *
0x18007678d  mov     rcx, [rbp+5Fh]; this
0x180076791  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180076798  mov     r9d, eax; char *
0x18007679b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800767a0  lea     rcx, [rbp+57h+var_B0]
0x1800767a4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800767a9  jmp     loc_180076B5B
0x1800767ae  mov     rcx, [rbp+57h+var_B0]
0x1800767b2  lea     rdx, [rbp+57h+var_70]
0x1800767b6  mov     rax, [rcx]
0x1800767b9  mov     rax, [rax+20h]
0x1800767bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767c2  mov     edi, eax
0x1800767c4  test    eax, eax
0x1800767c6  jns     short loc_1800767CF
0x1800767c8  mov     edx, 0A9h
0x1800767cd  jmp     short loc_18007678D
0x1800767cf  cmp     [rbp+57h+var_70], esi
0x1800767d2  jz      loc_18007695E
0x1800767d8  mov     [rbp+57h+var_90], rsi
0x1800767dc  lea     rcx, [rbp+57h+var_98]
0x1800767e0  mov     [rbp+57h+var_98], rsi
0x1800767e4  mov     rsi, [rbp+57h+var_B0]
0x1800767e8  mov     rax, [rsi]
0x1800767eb  mov     rdi, [rax+18h]
0x1800767ef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800767f4  lea     rcx, [rbp+57h+var_90]
0x1800767f8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800767fd  lea     r8, [rbp+57h+var_98]
0x180076801  mov     rcx, rsi
0x180076804  lea     rdx, [rbp+57h+var_90]
0x180076808  mov     rax, rdi
0x18007680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076810  mov     edi, eax
0x180076812  test    eax, eax
0x180076814  js      loc_18007692F
0x18007681a  mov     rsi, [rbp+57h+var_90]
0x18007681e  lea     rcx, [rbp+57h+var_78]
0x180076822  mov     [rbp+57h+var_78], 0
0x18007682a  mov     rax, [rsi]
0x18007682d  mov     rdi, [rax+38h]
0x180076831  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076836  lea     rdx, [rbp+57h+var_78]
0x18007683a  mov     rcx, rsi
0x18007683d  mov     rax, rdi
0x180076840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076845  mov     edi, eax
0x180076847  test    eax, eax
0x180076849  js      loc_18007690C
0x18007684f  mov     rsi, [rbp+57h+var_98]
0x180076853  lea     rcx, [rbp+57h+var_68]
0x180076857  mov     [rbp+57h+var_68], 0
0x18007685f  mov     rax, [rsi]
0x180076862  mov     rdi, [rax+38h]
0x180076866  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007686b  lea     rdx, [rbp+57h+var_68]
0x18007686f  mov     rcx, rsi
0x180076872  mov     rax, rdi
0x180076875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007687a  xor     esi, esi
0x18007687c  mov     edi, eax
0x18007687e  test    eax, eax
0x180076880  js      short loc_1800768E9
0x180076882  mov     r8, [rbp+57h+var_68]; struct IStream *
0x180076886  mov     rcx, r14; this
0x180076889  mov     rdx, [rbp+57h+var_78]; struct IStream *
0x18007688d  call    ?AddPublisherBridgingArtifact@BundlePackageWriter@Production@Packaging@Appx@@AEAAJPEAUIStream@@0@Z; Appx::Packaging::Production::BundlePackageWriter::AddPublisherBridgingArtifact(IStream *,IStream *)
0x180076892  mov     edi, eax
0x180076894  test    eax, eax
0x180076896  js      short loc_1800768E2
0x180076898  mov     rcx, [rbp+57h+var_B0]
0x18007689c  lea     rdx, [rbp+57h+var_70]
0x1800768a0  mov     rax, [rcx]
0x1800768a3  mov     rax, [rax+28h]
0x1800768a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768ac  mov     edi, eax
0x1800768ae  test    eax, eax
0x1800768b0  js      short loc_1800768DB
0x1800768b2  lea     rcx, [rbp+57h+var_68]
0x1800768b6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800768bb  lea     rcx, [rbp+57h+var_78]
0x1800768bf  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800768c4  lea     rcx, [rbp+57h+var_98]
0x1800768c8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800768cd  lea     rcx, [rbp+57h+var_90]
0x1800768d1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800768d6  jmp     loc_1800767CF
0x1800768db  mov     edx, 0B7h
0x1800768e0  jmp     short loc_1800768EE
0x1800768e2  mov     edx, 0B6h
0x1800768e7  jmp     short loc_1800768EE
0x1800768e9  mov     edx, 0B4h; void *
0x1800768ee  mov     rcx, [rbp+5Fh]; this
0x1800768f2  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800768f9  mov     r9d, eax; char *
0x1800768fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076901  lea     rcx, [rbp+57h+var_68]
0x180076905  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007690a  jmp     short loc_180076924
0x18007690c  mov     rcx, [rbp+5Fh]; this
0x180076910  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180076917  mov     r9d, eax; char *
0x18007691a  mov     edx, 0B1h; void *
0x18007691f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076924  lea     rcx, [rbp+57h+var_78]
0x180076928  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007692d  jmp     short loc_180076947
0x18007692f  mov     rcx, [rbp+5Fh]; this
0x180076933  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x18007693a  mov     r9d, eax; char *
0x18007693d  mov     edx, 0AEh; void *
0x180076942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076947  lea     rcx, [rbp+57h+var_98]
0x18007694b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076950  lea     rcx, [rbp+57h+var_90]
0x180076954  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180076959  jmp     loc_1800767A0
0x18007695e  lea     rcx, [rbp+57h+var_B0]
0x180076962  mov     byte ptr [r14+4Ah], 1
0x180076967  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007696c  mov     rdi, [r14+30h]
0x180076970  lea     rcx, [rbp+57h+var_A8]
0x180076974  mov     [rbp+57h+var_A8], rsi
0x180076978  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007697d  lea     rax, [rbp+57h+var_A8]
0x180076981  mov     r8d, 2
0x180076987  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18007698c  lea     r9, ?PayloadPackageContentType@Bundle@Packaging@Appx@@3QBGB; "application/vnd.ms-appx"
0x180076993  mov     rdx, r15
0x180076996  mov     dword ptr [rsp+0F0h+var_D0], esi; int
0x18007699a  mov     rcx, rdi
0x18007699d  call    ?CreateBlockReceiver@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBGW4FileType@FileNameHelper@34@0W4APPX_COMPRESSION_OPTION@@PEAPEAUIBlockReceiver@@@Z; Appx::Packaging::Production::PackageWriterHelper::CreateBlockReceiver(ushort const * const,Appx::Packaging::FileNameHelper::FileType,ushort const * const,APPX_COMPRESSION_OPTION,IBlockReceiver * *)
0x1800769a2  mov     edi, eax
0x1800769a4  test    eax, eax
0x1800769a6  jns     short loc_1800769C5
0x1800769a8  mov     edx, 0C3h; void *
0x1800769ad  mov     rcx, [rbp+5Fh]; this
0x1800769b1  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800769b8  mov     r9d, eax; char *
0x1800769bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800769c0  jmp     loc_180076B52
0x1800769c5  mov     rcx, [r14+28h]; this
0x1800769c9  lea     rdx, [rbp+57h+var_50]; struct IStream *
0x1800769cd  mov     [rbp+57h+var_50], rsi
0x1800769d1  call    ?GetStreamCurrentPosition@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamCurrentPosition(IStream *,unsigned __int64 *)
0x1800769d6  mov     edi, eax
0x1800769d8  test    eax, eax
0x1800769da  jns     short loc_1800769E3
0x1800769dc  mov     edx, 0C9h
0x1800769e1  jmp     short loc_1800769AD
0x1800769e3  lea     rdx, [rbp+57h+var_58]; struct IStream *
0x1800769e7  mov     [rbp+57h+var_58], rsi
0x1800769eb  mov     rcx, r12; this
0x1800769ee  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x1800769f3  mov     edi, eax
0x1800769f5  test    eax, eax
0x1800769f7  jns     short loc_180076A00
0x1800769f9  mov     edx, 0CCh
0x1800769fe  jmp     short loc_1800769AD
0x180076a00  mov     byte ptr [rbp+57h+pperrinfo], sil
0x180076a04  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180076a08  inc     rdx; unsigned __int64
  ... truncated ...
```

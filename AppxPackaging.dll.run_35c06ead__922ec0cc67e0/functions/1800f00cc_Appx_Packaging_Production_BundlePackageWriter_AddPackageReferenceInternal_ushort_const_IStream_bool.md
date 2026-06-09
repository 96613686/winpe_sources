# Appx::Packaging::Production::BundlePackageWriter::AddPackageReferenceInternal(ushort const *,IStream *,bool)

- ea: `0x1800f00cc`
- end: `0x1800f056e`
- name: `?AddPackageReferenceInternal@BundlePackageWriter@Production@Packaging@Appx@@AEAAJPEBGPEAUIStream@@_N@Z`
- size: `1186`
- prototype: `int(Appx::Packaging::Production::BundlePackageWriter *__hidden this, const unsigned __int16 *, struct IStream *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800efff0`

## callees

- `0x180005eb8`
- `0x180008f4c`
- `0x1800133fc`
- `0x1800292d0`
- `0x1800455ec`
- `0x180076b84`
- `0x180076bd4`
- `0x1800f00cc`
- `0x1800f06c0`
- `0x1800f2fd0`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800f0228`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0259`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0228`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0259`

## string_xrefs

- `0x1800f0164`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f01bb`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f0215`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f02ba`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f041b`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f0439`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f045c`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f04b4`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x1800f053b`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::BundlePackageWriter::AddPackageReferenceInternal(
        Appx::Packaging::Production::BundlePackageWriter *this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        bool a4)
{
  int v8; // eax
  unsigned __int64 *v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rdx
  struct IAppxPackageReader *v12; // rbx
  HRESULT (__stdcall *GetBlockMap)(IAppxPackageReader *, IAppxBlockMapReader **); // rdi
  int v14; // eax
  int StreamSize; // edi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rdi
  int v18; // eax
  __int64 v19; // rdx
  OLECHAR *v20; // rcx
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  __int64 v22; // rdx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, __int64 *, __int64 *); // rdi
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, struct IStream **); // rdi
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, struct IStream **); // rdi
  __int64 v31; // rdx
  __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  int v35; // [rsp+20h] [rbp-69h]
  __int64 v36; // [rsp+40h] [rbp-49h] BYREF
  __int64 v37; // [rsp+48h] [rbp-41h] BYREF
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  __int64 v39; // [rsp+58h] [rbp-31h] BYREF
  __int64 v40; // [rsp+60h] [rbp-29h] BYREF
  struct IStream *v41; // [rsp+68h] [rbp-21h] BYREF
  int v42; // [rsp+70h] [rbp-19h] BYREF
  struct IStream *v43; // [rsp+78h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-9h] BYREF
  struct IAppxPackageReader *v45; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int64 v46[10]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  bool v48; // [rsp+F0h] [rbp+67h] BYREF

  v45 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
  v8 = Appx::Packaging::Consumption::AppxPackageReader::Create(
         (__int64)a3,
         **((_QWORD **)this + 7) == 0,
         0,
         (Appx::Packaging::Consumption::AppxPackageReader **)&v45);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 257;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
      (const char *)(unsigned int)v8,
      v35);
    goto LABEL_51;
  }
  v12 = v45;
  if ( !*((_BYTE *)this + 73) )
  {
    v40 = 0;
    GetBlockMap = v45->lpVtbl->GetBlockMap;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
    v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetBlockMap)(v12, &v40);
    StreamSize = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v14,
        v35);
LABEL_6:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      goto LABEL_7;
    }
    v39 = 0;
    v16 = v40;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    v18 = v17(v16, &v39);
    StreamSize = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v18,
        v35);
LABEL_10:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<IUri>::operator=(*((_QWORD *)this + 7) + 944LL);
    bstrString = 0;
    StreamSize = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 56LL))(v39, &bstrString);
    if ( StreamSize < 0 )
    {
      v19 = 269;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)StreamSize,
        v35);
      SysFreeString(bstrString);
      goto LABEL_10;
    }
    StreamSize = Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(
                   *((Appx::Packaging::Production::PackageWriterHelper **)this + 6),
                   bstrString);
    if ( StreamSize < 0 )
    {
      v19 = 270;
      goto LABEL_13;
    }
    v20 = bstrString;
    *((_BYTE *)this + 73) = 1;
    SysFreeString(v20);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
  }
  if ( !*((_BYTE *)this + 74) )
  {
    v36 = 0;
    v42 = 0;
    GetFootprintFile = v12[1].lpVtbl->GetFootprintFile;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
    StreamSize = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetFootprintFile)(&v12[1], &v36);
    if ( StreamSize < 0 )
    {
      v22 = 279;
      goto LABEL_20;
    }
    StreamSize = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 32LL))(v36, &v42);
    if ( StreamSize < 0 )
    {
      v22 = 280;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)StreamSize,
        v35);
LABEL_21:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
      goto LABEL_7;
    }
    while ( v42 )
    {
      v38 = 0;
      v37 = 0;
      v23 = v36;
      v24 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v36 + 24LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
      v25 = v24(v23, &v38, &v37);
      StreamSize = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)v25,
          v35);
        goto LABEL_38;
      }
      v26 = v38;
      v41 = 0;
      v27 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v38 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
      v28 = v27(v26, &v41);
      StreamSize = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)v28,
          v35);
        goto LABEL_36;
      }
      v29 = v37;
      v43 = 0;
      v30 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v37 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
      StreamSize = v30(v29, &v43);
      if ( StreamSize < 0 )
      {
        v31 = 291;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
          (const char *)(unsigned int)StreamSize,
          v35);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
LABEL_36:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
LABEL_38:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
        goto LABEL_21;
      }
      StreamSize = Appx::Packaging::Production::BundlePackageWriter::AddPublisherBridgingArtifact(this, v41, v43);
      if ( StreamSize < 0 )
      {
        v31 = 293;
        goto LABEL_34;
      }
      StreamSize = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 40LL))(v36, &v42);
      if ( StreamSize < 0 )
      {
        v31 = 294;
        goto LABEL_34;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
    }
    *((_BYTE *)this + 74) = 1;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v36);
  }
  v46[0] = 0;
  StreamSize = Appx::Packaging::GetStreamSize(a3, (struct IStream *)v46, v9);
  if ( StreamSize >= 0 )
  {
    v48 = 0;
    v33 = -1;
    do
      ++v33;
    while ( a2[v33] );
    StreamSize = Appx::Packaging::FileNameHelper::ValidateFileNameAgainstReservedFolder(
                   a2,
                   v33,
                   L"appxmetadata\\stub",
                   0x11u,
                   &v48);
    if ( StreamSize >= 0 )
    {
      v8 = Appx::Packaging::Production::BundleManifestWriterHelper::AddPackage(
             *((Appx::Packaging::Production::BundleManifestWriterHelper **)this + 7),
             a2,
             v12,
             0,
             v46[0],
             a4,
             v48);
      v10 = v8;
      if ( v8 >= 0 )
      {
        v10 = 0;
        goto LABEL_51;
      }
      v11 = 311;
      goto LABEL_49;
    }
    v32 = 308;
  }
  else
  {
    v32 = 301;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v32,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
    (const char *)(unsigned int)StreamSize,
    v35);
LABEL_7:
  v10 = StreamSize;
LABEL_51:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
  return v10;
}

```

## disassembly

```asm
0x1800f00cc  push    rbp
0x1800f00ce  push    rbx
0x1800f00cf  push    rsi
0x1800f00d0  push    rdi
0x1800f00d1  push    r12
0x1800f00d3  push    r13
0x1800f00d5  push    r14
0x1800f00d7  push    r15
0x1800f00d9  lea     rbp, [rsp-1Fh]
0x1800f00de  sub     rsp, 0A8h
0x1800f00e5  mov     r14, rcx
0x1800f00e8  xor     esi, esi
0x1800f00ea  lea     rcx, [rbp+57h+var_58]
0x1800f00ee  mov     [rbp+57h+var_58], rsi
0x1800f00f2  mov     r13b, r9b
0x1800f00f5  mov     r12, r8
0x1800f00f8  mov     r15, rdx
0x1800f00fb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0100  mov     rax, [r14+38h]
0x1800f0104  lea     r9, [rbp+57h+var_58]
0x1800f0108  mov     rcx, r12
0x1800f010b  cmp     [rax], rsi
0x1800f010e  setz    dl
0x1800f0111  xor     r8d, r8d
0x1800f0114  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader> * *)
0x1800f0119  mov     ebx, eax
0x1800f011b  test    eax, eax
0x1800f011d  jns     short loc_1800F0129
0x1800f011f  mov     edx, 101h
0x1800f0124  jmp     loc_1800F0537
0x1800f0129  mov     rbx, [rbp+57h+var_58]
0x1800f012d  cmp     [r14+49h], sil
0x1800f0131  jnz     loc_1800F0277
0x1800f0137  mov     [rbp+57h+var_80], rsi
0x1800f013b  lea     rcx, [rbp+57h+var_80]
0x1800f013f  mov     rax, [rbx]
0x1800f0142  mov     rdi, [rax+18h]
0x1800f0146  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f014b  lea     rdx, [rbp+57h+var_80]
0x1800f014f  mov     rcx, rbx
0x1800f0152  mov     rax, rdi
0x1800f0155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f015a  mov     edi, eax
0x1800f015c  test    eax, eax
0x1800f015e  jns     short loc_1800F0188
0x1800f0160  mov     rcx, [rbp+5Fh]; this
0x1800f0164  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f016b  mov     r9d, eax; char *
0x1800f016e  mov     edx, 106h; void *
0x1800f0173  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0178  lea     rcx, [rbp+57h+var_80]
0x1800f017c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0181  mov     ebx, edi
0x1800f0183  jmp     loc_1800F054E
0x1800f0188  mov     [rbp+57h+var_88], rsi
0x1800f018c  lea     rcx, [rbp+57h+var_88]
0x1800f0190  mov     rsi, [rbp+57h+var_80]
0x1800f0194  mov     rax, [rsi]
0x1800f0197  mov     rdi, [rax+28h]
0x1800f019b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f01a0  lea     rdx, [rbp+57h+var_88]
0x1800f01a4  mov     rcx, rsi
0x1800f01a7  mov     rax, rdi
0x1800f01aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f01af  xor     esi, esi
0x1800f01b1  mov     edi, eax
0x1800f01b3  test    eax, eax
0x1800f01b5  jns     short loc_1800F01DA
0x1800f01b7  mov     rcx, [rbp+5Fh]; this
0x1800f01bb  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f01c2  mov     r9d, eax; char *
0x1800f01c5  mov     edx, 109h; void *
0x1800f01ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f01cf  lea     rcx, [rbp+57h+var_88]
0x1800f01d3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f01d8  jmp     short loc_1800F0178
0x1800f01da  mov     rcx, [r14+38h]
0x1800f01de  mov     rdx, [rbp+57h+var_88]
0x1800f01e2  add     rcx, 3B0h
0x1800f01e9  call    ??4?$ComPtr@UIUri@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUri@@@Z; Microsoft::WRL::ComPtr<IUri>::operator=(IUri *)
0x1800f01ee  mov     rcx, [rbp+57h+var_88]
0x1800f01f2  lea     rdx, [rbp+57h+bstrString]
0x1800f01f6  mov     [rbp+57h+bstrString], rsi
0x1800f01fa  mov     rax, [rcx]
0x1800f01fd  mov     rax, [rax+38h]
0x1800f0201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0206  mov     edi, eax
0x1800f0208  test    eax, eax
0x1800f020a  jns     short loc_1800F0236
0x1800f020c  mov     edx, 10Dh; void *
0x1800f0211  mov     rcx, [rbp+5Fh]; this
0x1800f0215  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f021c  mov     r9d, edi; char *
0x1800f021f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0224  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f0228  call    cs:__imp_SysFreeString
0x1800f022f  nop     dword ptr [rax+rax+00h]
0x1800f0234  jmp     short loc_1800F01CF
0x1800f0236  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800f023a  mov     rcx, [r14+30h]; this
0x1800f023e  call    ?InitializeBlockMapWriter@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBG@Z; Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(ushort const * const)
0x1800f0243  mov     edi, eax
0x1800f0245  test    eax, eax
0x1800f0247  jns     short loc_1800F0250
0x1800f0249  mov     edx, 10Eh
0x1800f024e  jmp     short loc_1800F0211
0x1800f0250  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800f0254  mov     byte ptr [r14+49h], 1
0x1800f0259  call    cs:__imp_SysFreeString
0x1800f0260  nop     dword ptr [rax+rax+00h]
0x1800f0265  lea     rcx, [rbp+57h+var_88]
0x1800f0269  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f026e  lea     rcx, [rbp+57h+var_80]
0x1800f0272  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0277  cmp     [r14+4Ah], sil
0x1800f027b  jnz     loc_1800F0495
0x1800f0281  mov     [rbp+57h+var_A0], rsi
0x1800f0285  lea     rcx, [rbp+57h+var_A0]
0x1800f0289  mov     [rbp+57h+var_70], esi
0x1800f028c  mov     rax, [rbx+8]
0x1800f0290  mov     rdi, [rax+20h]
0x1800f0294  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0299  lea     rdx, [rbp+57h+var_A0]
0x1800f029d  mov     rax, rdi
0x1800f02a0  lea     rcx, [rbx+8]
0x1800f02a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f02a9  xor     esi, esi
0x1800f02ab  mov     edi, eax
0x1800f02ad  test    eax, eax
0x1800f02af  jns     short loc_1800F02D7
0x1800f02b1  mov     edx, 117h; void *
0x1800f02b6  mov     rcx, [rbp+5Fh]; this
0x1800f02ba  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f02c1  mov     r9d, edi; char *
0x1800f02c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f02c9  lea     rcx, [rbp+57h+var_A0]
0x1800f02cd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f02d2  jmp     loc_1800F0181
0x1800f02d7  mov     rcx, [rbp+57h+var_A0]
0x1800f02db  lea     rdx, [rbp+57h+var_70]
0x1800f02df  mov     rax, [rcx]
0x1800f02e2  mov     rax, [rax+20h]
0x1800f02e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f02eb  mov     edi, eax
0x1800f02ed  test    eax, eax
0x1800f02ef  jns     short loc_1800F02F8
0x1800f02f1  mov     edx, 118h
0x1800f02f6  jmp     short loc_1800F02B6
0x1800f02f8  cmp     [rbp+57h+var_70], esi
0x1800f02fb  jz      loc_1800F0487
0x1800f0301  mov     [rbp+57h+var_90], rsi
0x1800f0305  lea     rcx, [rbp+57h+var_98]
0x1800f0309  mov     [rbp+57h+var_98], rsi
0x1800f030d  mov     rsi, [rbp+57h+var_A0]
0x1800f0311  mov     rax, [rsi]
0x1800f0314  mov     rdi, [rax+18h]
0x1800f0318  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f031d  lea     rcx, [rbp+57h+var_90]
0x1800f0321  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0326  lea     r8, [rbp+57h+var_98]
0x1800f032a  mov     rcx, rsi
0x1800f032d  lea     rdx, [rbp+57h+var_90]
0x1800f0331  mov     rax, rdi
0x1800f0334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0339  mov     edi, eax
0x1800f033b  test    eax, eax
0x1800f033d  js      loc_1800F0458
0x1800f0343  mov     rsi, [rbp+57h+var_90]
0x1800f0347  lea     rcx, [rbp+57h+var_78]
0x1800f034b  mov     [rbp+57h+var_78], 0
0x1800f0353  mov     rax, [rsi]
0x1800f0356  mov     rdi, [rax+38h]
0x1800f035a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f035f  lea     rdx, [rbp+57h+var_78]
0x1800f0363  mov     rcx, rsi
0x1800f0366  mov     rax, rdi
0x1800f0369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f036e  mov     edi, eax
0x1800f0370  test    eax, eax
0x1800f0372  js      loc_1800F0435
0x1800f0378  mov     rsi, [rbp+57h+var_98]
0x1800f037c  lea     rcx, [rbp+57h+var_68]
0x1800f0380  mov     [rbp+57h+var_68], 0
0x1800f0388  mov     rax, [rsi]
0x1800f038b  mov     rdi, [rax+38h]
0x1800f038f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0394  lea     rdx, [rbp+57h+var_68]
0x1800f0398  mov     rcx, rsi
0x1800f039b  mov     rax, rdi
0x1800f039e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f03a3  xor     esi, esi
0x1800f03a5  mov     edi, eax
0x1800f03a7  test    eax, eax
0x1800f03a9  js      short loc_1800F0412
0x1800f03ab  mov     r8, [rbp+57h+var_68]; struct IStream *
0x1800f03af  mov     rcx, r14; this
0x1800f03b2  mov     rdx, [rbp+57h+var_78]; struct IStream *
0x1800f03b6  call    ?AddPublisherBridgingArtifact@BundlePackageWriter@Production@Packaging@Appx@@AEAAJPEAUIStream@@0@Z; Appx::Packaging::Production::BundlePackageWriter::AddPublisherBridgingArtifact(IStream *,IStream *)
0x1800f03bb  mov     edi, eax
0x1800f03bd  test    eax, eax
0x1800f03bf  js      short loc_1800F040B
0x1800f03c1  mov     rcx, [rbp+57h+var_A0]
0x1800f03c5  lea     rdx, [rbp+57h+var_70]
0x1800f03c9  mov     rax, [rcx]
0x1800f03cc  mov     rax, [rax+28h]
0x1800f03d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f03d5  mov     edi, eax
0x1800f03d7  test    eax, eax
0x1800f03d9  js      short loc_1800F0404
0x1800f03db  lea     rcx, [rbp+57h+var_68]
0x1800f03df  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f03e4  lea     rcx, [rbp+57h+var_78]
0x1800f03e8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f03ed  lea     rcx, [rbp+57h+var_98]
0x1800f03f1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f03f6  lea     rcx, [rbp+57h+var_90]
0x1800f03fa  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f03ff  jmp     loc_1800F02F8
0x1800f0404  mov     edx, 126h
0x1800f0409  jmp     short loc_1800F0417
0x1800f040b  mov     edx, 125h
0x1800f0410  jmp     short loc_1800F0417
0x1800f0412  mov     edx, 123h; void *
0x1800f0417  mov     rcx, [rbp+5Fh]; this
0x1800f041b  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f0422  mov     r9d, edi; char *
0x1800f0425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f042a  lea     rcx, [rbp+57h+var_68]
0x1800f042e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0433  jmp     short loc_1800F044D
0x1800f0435  mov     rcx, [rbp+5Fh]; this
0x1800f0439  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f0440  mov     r9d, edi; char *
0x1800f0443  mov     edx, 120h; void *
0x1800f0448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f044d  lea     rcx, [rbp+57h+var_78]
0x1800f0451  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0456  jmp     short loc_1800F0470
0x1800f0458  mov     rcx, [rbp+5Fh]; this
0x1800f045c  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f0463  mov     r9d, edi; char *
0x1800f0466  mov     edx, 11Dh; void *
0x1800f046b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0470  lea     rcx, [rbp+57h+var_98]
0x1800f0474  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0479  lea     rcx, [rbp+57h+var_90]
0x1800f047d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0482  jmp     loc_1800F02C9
0x1800f0487  lea     rcx, [rbp+57h+var_A0]
0x1800f048b  mov     byte ptr [r14+4Ah], 1
0x1800f0490  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800f0495  lea     rdx, [rbp+57h+var_50]; struct IStream *
0x1800f0499  mov     [rbp+57h+var_50], rsi
0x1800f049d  mov     rcx, r12; this
0x1800f04a0  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x1800f04a5  mov     edi, eax
0x1800f04a7  test    eax, eax
0x1800f04a9  jns     short loc_1800F04C8
0x1800f04ab  mov     edx, 12Dh; void *
0x1800f04b0  mov     rcx, [rbp+5Fh]; this
0x1800f04b4  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f04bb  mov     r9d, edi; char *
0x1800f04be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f04c3  jmp     loc_1800F0181
0x1800f04c8  mov     [rbp+57h+arg_0], sil
0x1800f04cc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f04d0  inc     rdx; unsigned __int64
0x1800f04d3  cmp     [r15+rdx*2], si
0x1800f04d8  jnz     short loc_1800F04D0
0x1800f04da  lea     rax, [rbp+57h+arg_0]
0x1800f04de  mov     r9d, 11h; unsigned int
0x1800f04e4  lea     r8, aAppxmetadataSt_0; "appxmetadata\\stub"
0x1800f04eb  mov     [rsp+0E0h+var_C0], rax; bool *
0x1800f04f0  mov     rcx, r15; Src
0x1800f04f3  call    ?ValidateFileNameAgainstReservedFolder@FileNameHelper@Packaging@Appx@@SAJPEBG_K0IPEA_N@Z; Appx::Packaging::FileNameHelper::ValidateFileNameAgainstReservedFolder(ushort const *,unsigned __int64,ushort const *,uint,bool *)
0x1800f04f8  mov     edi, eax
0x1800f04fa  test    eax, eax
0x1800f04fc  jns     short loc_1800F0505
0x1800f04fe  mov     edx, 134h
0x1800f0503  jmp     short loc_1800F04B0
0x1800f0505  mov     al, [rbp+57h+arg_0]
0x1800f0508  xor     r9d, r9d; unsigned __int64
0x1800f050b  mov     rcx, [r14+38h]; this
0x1800f050f  mov     r8, rbx; struct IAppxPackageReader *
0x1800f0512  mov     [rsp+0E0h+var_B0], al; bool
0x1800f0516  mov     rdx, r15; unsigned __int16 *
0x1800f0519  mov     rax, [rbp+57h+var_50]
0x1800f051d  mov     [rsp+0E0h+var_B8], r13b; bool
0x1800f0522  mov     [rsp+0E0h+var_C0], rax; int
0x1800f0527  call    ?AddPackage@BundleManifestWriterHelper@Production@Packaging@Appx@@QEAAJPEBGPEAUIAppxPackageReader@@_K2_N3@Z; Appx::Packaging::Production::BundleManifestWriterHelper::AddPackage(ushort const *,IAppxPackageReader *,unsigned __int64,unsigned __int64,bool,bool)
0x1800f052c  mov     ebx, eax
0x1800f052e  test    eax, eax
0x1800f0530  jns     short loc_1800F054C
0x1800f0532  mov     edx, 137h; void *
0x1800f0537  mov     rcx, [rbp+5Fh]; this
0x1800f053b  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f0542  mov     r9d, eax; char *
0x1800f0545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f054a  jmp     short loc_1800F054E
0x1800f054c  mov     ebx, esi
  ... truncated ...
```

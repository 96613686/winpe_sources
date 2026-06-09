# Appx::Packaging::AppxPackageEditorImpl::CreateDeltaPackageUsingBaselineBlockMap(IStream *,IStream *,ushort const *,IStream *)

- ea: `0x1800ba130`
- end: `0x1800ba855`
- name: `?CreateDeltaPackageUsingBaselineBlockMap@AppxPackageEditorImpl@Packaging@Appx@@UEAAJPEAUIStream@@0PEBG0@Z`
- size: `1829`
- prototype: `int(Appx::Packaging::AppxPackageEditorImpl *__hidden this, struct IStream *, struct IStream *, const unsigned __int16 *, struct IStream *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800027f4`
- `0x1800029e4`
- `0x180005830`
- `0x180005eb8`
- `0x1800133fc`
- `0x1800455ec`
- `0x18005ccf0`
- `0x18007a9a0`
- `0x18007fdf4`
- `0x1800992a0`
- `0x1800b6e9c`
- `0x1800b738c`
- `0x1800b7aa8`
- `0x1800b7b5c`
- `0x1800ba130`
- `0x1800bb090`
- `0x1800bb204`
- `0x1800bb3ec`
- `0x1800bc6a4`
- `0x180106010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba318`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba406`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba4ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba54b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba613`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba6c0`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba761`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba7d2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba318`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba406`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba4ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba54b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba613`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba6c0`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba761`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800ba7d2`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba2f9`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba3e3`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba488`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba52c`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba5f0`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba69d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba73e`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba7b3`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba2f9`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba3e3`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba488`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba52c`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba5f0`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba69d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba73e`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800ba7b3`

## string_xrefs

- `0x1800ba175`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba1e1`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba23c`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba28e`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba2d7`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba3ad`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba452`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba4f6`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba5ba`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba667`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800ba708`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxPackageEditorImpl::CreateDeltaPackageUsingBaselineBlockMap(
        Appx::Packaging::AppxPackageEditorImpl *this,
        struct IStream *a2,
        struct IStream *a3,
        Appx::Packaging *a4,
        struct IStream *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  Appx::Packaging *v11; // rdi
  __int64 v12; // rsi
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  int v15; // eax
  PVOID v16; // rbx
  int v17; // eax
  int v18; // r14d
  __int64 *v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rsi
  struct Appx::Packaging::Production::PackageWriterHelper *v22; // r8
  unsigned int v23; // edx
  Appx::Packaging::Production::PackageWriterHelper *v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rsi
  int v28; // eax
  struct Appx::Packaging::Production::PackageWriterHelper *v29; // r8
  unsigned int v30; // edx
  Appx::Packaging::Production::PackageWriterHelper *v31; // rcx
  __int64 *v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rsi
  int FootprintFilesAndAddToOpcPackage; // eax
  unsigned int v36; // edi
  unsigned int v37; // edx
  Appx::Packaging::Production::PackageWriterHelper *v38; // rcx
  __int64 *v39; // rax
  __int64 v40; // rsi
  __int64 v41; // r14
  int v42; // eax
  unsigned int v43; // edx
  Appx::Packaging::Production::PackageWriterHelper *v44; // rcx
  __int64 *v45; // rax
  __int64 v46; // rsi
  __int64 v47; // r14
  int v48; // eax
  unsigned int v49; // edx
  Appx::Packaging::Production::PackageWriterHelper *v50; // rcx
  __int64 *v51; // rax
  __int64 v52; // rsi
  __int64 v53; // r14
  int v54; // eax
  unsigned int v55; // edx
  unsigned int v56; // edx
  Appx::Packaging::Production::PackageWriterHelper *v57; // rcx
  __int64 *v58; // rax
  __int64 v59; // rsi
  __int64 v60; // r14
  Appx::Packaging::Production::PackageWriterHelper *v61; // rcx
  __int64 *v62; // rax
  __int64 v63; // rdi
  __int64 v64; // rsi
  Appx::Packaging::Production::PackageWriterHelper *v66; // [rsp+20h] [rbp-B1h] BYREF
  PVOID RestartKey; // [rsp+28h] [rbp-A9h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v68; // [rsp+30h] [rbp-A1h] BYREF
  __int64 v69; // [rsp+38h] [rbp-99h] BYREF
  Appx::Packaging *v70; // [rsp+40h] [rbp-91h] BYREF
  Appx::Packaging::Production::PackageWriterHelper **v71; // [rsp+48h] [rbp-89h] BYREF
  struct Appx::Packaging::Production::PackageWriterHelper *v72; // [rsp+50h] [rbp-81h] BYREF
  char v73; // [rsp+58h] [rbp-79h]
  struct _RTL_AVL_TABLE Table; // [rsp+60h] [rbp-71h] BYREF
  void (__fastcall *v75)(__int64); // [rsp+C8h] [rbp-9h]
  void (__fastcall *v76)(__int64); // [rsp+D0h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 693;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v8 = 694;
      goto LABEL_3;
    }
    if ( !a5 )
    {
      v8 = 695;
      goto LABEL_3;
    }
    v70 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
    v10 = Appx::Packaging::Consumption::AppxPackageReader::Create((__int64)a2, 1, 0, &v70);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BA,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v10,
        (int)v66);
      goto LABEL_82;
    }
    v11 = v70;
    v12 = *((_QWORD *)v70 + 6);
    v69 = v12;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v69);
    v68 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    v14 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(a3, v13, &v68);
    v9 = v14;
    if ( v14 >= 0 )
    {
      RestartKey = 0;
      v15 = Appx::Packaging::ZipEditor::Create(a2, 0, &RestartKey);
      v9 = v15;
      if ( v15 >= 0 )
      {
        Common::GenericMap<char const *,Appx::Packaging::ZipFileItem *>::GenericMap<char const *,Appx::Packaging::ZipFileItem *>(&Table);
        v16 = RestartKey;
        v17 = Appx::Packaging::PopulateZipFileMap(RestartKey, &Table);
        v18 = v17;
        if ( v17 >= 0 )
        {
          v66 = 0;
          v71 = &v66;
          v72 = 0;
          v73 = 1;
          v18 = Appx::Packaging::Production::PackageWriterHelper::Create(a5, 0, &v72);
          wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::Production::PackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::PackageWriterHelper>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::Production::PackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::PackageWriterHelper>>>(&v71);
          if ( v18 >= 0 )
          {
            v28 = Appx::Packaging::AddBaselinePackageVersionToOpcPackage(a4, (const unsigned __int16 *)v66, v22);
            v18 = v28;
            if ( v28 >= 0 )
            {
              FootprintFilesAndAddToOpcPackage = Appx::Packaging::ExtractFootprintFilesAndAddToOpcPackage(v11, v66, v29);
              v36 = FootprintFilesAndAddToOpcPackage;
              if ( FootprintFilesAndAddToOpcPackage >= 0 )
              {
                v42 = Appx::Packaging::ExtractContentTypesFileAndAddToOpcPackage(&Table, v66);
                v36 = v42;
                if ( v42 >= 0 )
                {
                  v48 = Appx::Packaging::ExtractPayloadFilesDeltaAndAddToOpcPackage(v12, &Table, v68, v66);
                  v36 = v48;
                  if ( v48 >= 0 )
                  {
                    v54 = Appx::Packaging::Production::PackageWriterHelper::Close(v66);
                    v36 = v54;
                    if ( v54 >= 0 )
                    {
                      v61 = v66;
                      v66 = 0;
                      if ( v61 )
                        Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v61, v55);
                      while ( 1 )
                      {
                        RestartKey = 0;
                        v62 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
                        if ( !v62 )
                          break;
                        v63 = *v62;
                        v64 = v62[1];
                        RtlDeleteElementGenericTableAvl(&Table, v62);
                        if ( v75 )
                          v75(v63);
                        if ( v76 )
                          v76(v64);
                      }
                      Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v16);
                      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
                      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
                      v9 = 0;
                      goto LABEL_82;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2D2,
                      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                      (const char *)(unsigned int)v54,
                      (int)v66);
                    v57 = v66;
                    v66 = 0;
                    if ( v57 )
                      Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v57, v56);
                    while ( 1 )
                    {
                      RestartKey = 0;
                      v58 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
                      if ( !v58 )
                        break;
                      v59 = *v58;
                      v60 = v58[1];
                      RtlDeleteElementGenericTableAvl(&Table, v58);
                      if ( v75 )
                        v75(v59);
                      if ( v76 )
                        v76(v60);
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2D0,
                      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                      (const char *)(unsigned int)v48,
                      (int)v66);
                    v50 = v66;
                    v66 = 0;
                    if ( v50 )
                      Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v50, v49);
                    while ( 1 )
                    {
                      RestartKey = 0;
                      v51 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
                      if ( !v51 )
                        break;
                      v52 = *v51;
                      v53 = v51[1];
                      RtlDeleteElementGenericTableAvl(&Table, v51);
                      if ( v75 )
                        v75(v52);
                      if ( v76 )
                        v76(v53);
                    }
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2CE,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                    (const char *)(unsigned int)v42,
                    (int)v66);
                  v44 = v66;
                  v66 = 0;
                  if ( v44 )
                    Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v44, v43);
                  while ( 1 )
                  {
                    RestartKey = 0;
                    v45 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
                    if ( !v45 )
                      break;
                    v46 = *v45;
                    v47 = v45[1];
                    RtlDeleteElementGenericTableAvl(&Table, v45);
                    if ( v75 )
                      v75(v46);
                    if ( v76 )
                      v76(v47);
                  }
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2CC,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                  (const char *)(unsigned int)FootprintFilesAndAddToOpcPackage,
                  (int)v66);
                v38 = v66;
                v66 = 0;
                if ( v38 )
                  Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v38, v37);
                while ( 1 )
                {
                  RestartKey = 0;
                  v39 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
                  if ( !v39 )
                    break;
                  v40 = *v39;
                  v41 = v39[1];
                  RtlDeleteElementGenericTableAvl(&Table, v39);
                  if ( v75 )
                    v75(v40);
                  if ( v76 )
                    v76(v41);
                }
              }
              Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v16);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
              v9 = v36;
LABEL_82:
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
              return v9;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CA,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
              (const char *)(unsigned int)v28,
              (int)v66);
            v31 = v66;
            v66 = 0;
            if ( v31 )
              Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v31, v30);
            while ( 1 )
            {
              RestartKey = 0;
              v32 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
              if ( !v32 )
                break;
              v33 = *v32;
              v34 = v32[1];
              RtlDeleteElementGenericTableAvl(&Table, v32);
              if ( v75 )
                v75(v33);
              if ( v76 )
                v76(v34);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2C7,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
              (const char *)(unsigned int)v18,
              (int)v66);
            v24 = v66;
            v66 = 0;
            if ( v24 )
              Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(v24, v23);
            while ( 1 )
            {
              RestartKey = 0;
              v25 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
              if ( !v25 )
                break;
              v26 = *v25;
              v27 = v25[1];
              RtlDeleteElementGenericTableAvl(&Table, v25);
              if ( v75 )
                v75(v26);
              if ( v76 )
                v76(v27);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C4,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)v17,
            (int)v66);
          while ( 1 )
          {
            RestartKey = 0;
            v19 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(&Table, &RestartKey);
            if ( !v19 )
              break;
            v20 = *v19;
            v21 = v19[1];
            RtlDeleteElementGenericTableAvl(&Table, v19);
            if ( v75 )
              v75(v20);
            if ( v76 )
              v76(v21);
          }
        }
        Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v16);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
        v9 = v18;
        goto LABEL_82;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v15,
        (int)v66);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(RestartKey);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v14,
        (int)v66);
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
    goto LABEL_82;
  }
  v8 = 692;
LABEL_3:
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
    (const char *)0x80070057LL,
    (int)v66);
  return v9;
}

```

## disassembly

```asm
0x1800ba130  mov     [rsp-8+arg_0], rbx
0x1800ba135  push    rbp
0x1800ba136  push    rsi
0x1800ba137  push    rdi
0x1800ba138  push    r12
0x1800ba13a  push    r13
0x1800ba13c  push    r14
0x1800ba13e  push    r15
0x1800ba140  lea     rbp, [rsp-1Fh]
0x1800ba145  sub     rsp, 0F0h
0x1800ba14c  mov     rax, cs:__security_cookie
0x1800ba153  xor     rax, rsp
0x1800ba156  mov     [rbp+4Fh+var_40], rax
0x1800ba15a  mov     r13, [rbp+4Fh+arg_20]
0x1800ba15e  mov     r12, r9
0x1800ba161  mov     r14, r8
0x1800ba164  mov     r15, rdx
0x1800ba167  test    rdx, rdx
0x1800ba16a  jnz     short loc_1800BA18E
0x1800ba16c  mov     edx, 2B4h; void *
0x1800ba171  mov     rcx, [rbp+57h]; this
0x1800ba175  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba17c  mov     ebx, 80070057h
0x1800ba181  mov     r9d, ebx; char *
0x1800ba184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba189  jmp     loc_1800BA82B
0x1800ba18e  test    r14, r14
0x1800ba191  jnz     short loc_1800BA19A
0x1800ba193  mov     edx, 2B5h
0x1800ba198  jmp     short loc_1800BA171
0x1800ba19a  test    r12, r12
0x1800ba19d  jnz     short loc_1800BA1A6
0x1800ba19f  mov     edx, 2B6h
0x1800ba1a4  jmp     short loc_1800BA171
0x1800ba1a6  test    r13, r13
0x1800ba1a9  jnz     short loc_1800BA1B2
0x1800ba1ab  mov     edx, 2B7h
0x1800ba1b0  jmp     short loc_1800BA171
0x1800ba1b2  lea     rcx, [rsp+120h+var_E0]
0x1800ba1b7  mov     [rsp+120h+var_E0], 0
0x1800ba1c0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba1c5  lea     r9, [rsp+120h+var_E0]
0x1800ba1ca  xor     r8d, r8d
0x1800ba1cd  mov     dl, 1
0x1800ba1cf  mov     rcx, r15
0x1800ba1d2  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader> * *)
0x1800ba1d7  mov     ebx, eax
0x1800ba1d9  test    eax, eax
0x1800ba1db  jns     short loc_1800BA1FA
0x1800ba1dd  mov     rcx, [rbp+57h]; this
0x1800ba1e1  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba1e8  mov     r9d, eax; char *
0x1800ba1eb  mov     edx, 2BAh; void *
0x1800ba1f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba1f5  jmp     loc_1800BA821
0x1800ba1fa  mov     rdi, [rsp+120h+var_E0]
0x1800ba1ff  lea     rcx, [rsp+120h+var_E8]
0x1800ba204  mov     rsi, [rdi+30h]
0x1800ba208  mov     [rsp+120h+var_E8], rsi
0x1800ba20d  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x1800ba212  lea     rcx, [rsp+120h+var_F0]
0x1800ba217  mov     [rsp+120h+var_F0], 0
0x1800ba220  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba225  lea     r8, [rsp+120h+var_F0]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x1800ba22a  mov     rcx, r14; struct IStream *
0x1800ba22d  call    ?Create@AppxBlockMapReader@BlockMap@Packaging@Appx@@SAJPEAUIStream@@PEBGPEAPEAV1234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::Create(IStream *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x1800ba232  mov     ebx, eax
0x1800ba234  test    eax, eax
0x1800ba236  jns     short loc_1800BA269
0x1800ba238  mov     rcx, [rbp+57h]; this
0x1800ba23c  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba243  mov     r9d, eax; char *
0x1800ba246  mov     edx, 2BEh; void *
0x1800ba24b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba250  lea     rcx, [rsp+120h+var_F0]
0x1800ba255  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba25a  lea     rcx, [rsp+120h+var_E8]
0x1800ba25f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba264  jmp     loc_1800BA821
0x1800ba269  lea     r8, [rsp+120h+RestartKey]
0x1800ba26e  mov     [rsp+120h+RestartKey], 0
0x1800ba277  xor     edx, edx
0x1800ba279  mov     rcx, r15
0x1800ba27c  call    ?Create@ZipEditor@Packaging@Appx@@SAJPEAUIStream@@PEBGAEAV?$AutoPtr@VZipEditor@Packaging@Appx@@$1??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@@Z; Appx::Packaging::ZipEditor::Create(IStream *,ushort const *,Common::AutoPtr<Appx::Packaging::ZipEditor,&Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)> &)
0x1800ba281  xor     r15d, r15d
0x1800ba284  mov     ebx, eax
0x1800ba286  test    eax, eax
0x1800ba288  jns     short loc_1800BA2AE
0x1800ba28a  mov     rcx, [rbp+57h]; this
0x1800ba28e  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba295  mov     r9d, eax; char *
0x1800ba298  mov     edx, 2C2h; void *
0x1800ba29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba2a2  mov     rcx, [rsp+120h+RestartKey]; void *
0x1800ba2a7  call    ??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAVZipEditor@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)
0x1800ba2ac  jmp     short loc_1800BA250
0x1800ba2ae  lea     rcx, [rbp+4Fh+Table]
0x1800ba2b2  call    ??0?$GenericMap@PEBDPEAVZipFileItem@Packaging@Appx@@@Common@@QEAA@P6A?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@ZP6AXPEBD@ZP6AXPEAVZipFileItem@Packaging@Appx@@@Z@Z; Common::GenericMap<char const *,Appx::Packaging::ZipFileItem *>::GenericMap<char const *,Appx::Packaging::ZipFileItem *>(_RTL_GENERIC_COMPARE_RESULTS (*)(_RTL_AVL_TABLE *,void *,void *),void (*)(char const *),void (*)(Appx::Packaging::ZipFileItem *))
0x1800ba2b7  mov     rbx, [rsp+120h+RestartKey]
0x1800ba2bc  lea     rdx, [rbp+4Fh+Table]
0x1800ba2c0  mov     rcx, rbx
0x1800ba2c3  call    ?PopulateZipFileMap@Packaging@Appx@@YAJAEAVZipEditor@12@AEAV?$GenericMap@PEBDPEAVZipFileItem@Packaging@Appx@@@Common@@@Z; Appx::Packaging::PopulateZipFileMap(Appx::Packaging::ZipEditor &,Common::GenericMap<char const *,Appx::Packaging::ZipFileItem *> &)
0x1800ba2c8  mov     r14d, eax
0x1800ba2cb  test    eax, eax
0x1800ba2cd  jns     loc_1800BA36C
0x1800ba2d3  mov     rcx, [rbp+57h]; this
0x1800ba2d7  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba2de  mov     r9d, eax; char *
0x1800ba2e1  mov     edx, 2C4h; void *
0x1800ba2e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba2eb  lea     rdx, [rsp+120h+RestartKey]; RestartKey
0x1800ba2f0  mov     [rsp+120h+RestartKey], r15
0x1800ba2f5  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba2f9  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800ba300  nop     dword ptr [rax+rax+00h]
0x1800ba305  test    rax, rax
0x1800ba308  jz      short loc_1800BA348
0x1800ba30a  mov     rdi, [rax]
0x1800ba30d  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba311  mov     rsi, [rax+8]
0x1800ba315  mov     rdx, rax; Buffer
0x1800ba318  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800ba31f  nop     dword ptr [rax+rax+00h]
0x1800ba324  mov     rax, [rbp+4Fh+var_58]
0x1800ba328  test    rax, rax
0x1800ba32b  jz      short loc_1800BA335
0x1800ba32d  mov     rcx, rdi
0x1800ba330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba335  mov     rax, [rbp+4Fh+var_50]
0x1800ba339  test    rax, rax
0x1800ba33c  jz      short loc_1800BA2EB
0x1800ba33e  mov     rcx, rsi
0x1800ba341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba346  jmp     short loc_1800BA2EB
0x1800ba348  mov     rcx, rbx; void *
0x1800ba34b  call    ??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAVZipEditor@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)
0x1800ba350  lea     rcx, [rsp+120h+var_F0]
0x1800ba355  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba35a  lea     rcx, [rsp+120h+var_E8]
0x1800ba35f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba364  mov     ebx, r14d
0x1800ba367  jmp     loc_1800BA821
0x1800ba36c  lea     rax, [rsp+120h+var_100]
0x1800ba371  mov     [rsp+120h+var_100], r15; int
0x1800ba376  lea     r8, [rsp+120h+var_D0]; struct Appx::Packaging::Production::PackageWriterHelper **
0x1800ba37b  mov     [rsp+120h+var_D8], rax
0x1800ba380  xor     edx, edx; int
0x1800ba382  mov     [rsp+120h+var_D0], r15
0x1800ba387  mov     rcx, r13; struct IStream *
0x1800ba38a  mov     [rbp+4Fh+var_C8], 1
0x1800ba38e  call    ?Create@PackageWriterHelper@Production@Packaging@Appx@@SAJPEAUIStream@@HPEAPEAV1234@@Z; Appx::Packaging::Production::PackageWriterHelper::Create(IStream *,int,Appx::Packaging::Production::PackageWriterHelper * *)
0x1800ba393  lea     rcx, [rsp+120h+var_D8]
0x1800ba398  mov     r14d, eax
0x1800ba39b  call    ??1?$out_param_t@V?$unique_ptr@VPackageWriterHelper@Production@Packaging@Appx@@U?$default_delete@VPackageWriterHelper@Production@Packaging@Appx@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::Production::PackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::PackageWriterHelper>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::Production::PackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::PackageWriterHelper>>>(void)
0x1800ba3a0  test    r14d, r14d
0x1800ba3a3  jns     loc_1800BA436
0x1800ba3a9  mov     rcx, [rbp+57h]; this
0x1800ba3ad  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba3b4  mov     r9d, r14d; char *
0x1800ba3b7  mov     edx, 2C7h; void *
0x1800ba3bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba3c1  mov     rcx, [rsp+120h+var_100]; this
0x1800ba3c6  mov     [rsp+120h+var_100], r15
0x1800ba3cb  test    rcx, rcx
0x1800ba3ce  jz      short loc_1800BA3D5
0x1800ba3d0  call    ??_GPackageWriterHelper@Production@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(uint)
0x1800ba3d5  lea     rdx, [rsp+120h+RestartKey]; RestartKey
0x1800ba3da  mov     [rsp+120h+RestartKey], r15
0x1800ba3df  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba3e3  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800ba3ea  nop     dword ptr [rax+rax+00h]
0x1800ba3ef  test    rax, rax
0x1800ba3f2  jz      loc_1800BA348
0x1800ba3f8  mov     rdi, [rax]
0x1800ba3fb  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba3ff  mov     rsi, [rax+8]
0x1800ba403  mov     rdx, rax; Buffer
0x1800ba406  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800ba40d  nop     dword ptr [rax+rax+00h]
0x1800ba412  mov     rax, [rbp+4Fh+var_58]
0x1800ba416  test    rax, rax
0x1800ba419  jz      short loc_1800BA423
0x1800ba41b  mov     rcx, rdi
0x1800ba41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba423  mov     rax, [rbp+4Fh+var_50]
0x1800ba427  test    rax, rax
0x1800ba42a  jz      short loc_1800BA3D5
0x1800ba42c  mov     rcx, rsi
0x1800ba42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba434  jmp     short loc_1800BA3D5
0x1800ba436  mov     rdx, [rsp+120h+var_100]; unsigned __int16 *
0x1800ba43b  mov     rcx, r12; this
0x1800ba43e  call    ?AddBaselinePackageVersionToOpcPackage@Packaging@Appx@@YAJPEBGPEAVPackageWriterHelper@Production@12@@Z; Appx::Packaging::AddBaselinePackageVersionToOpcPackage(ushort const *,Appx::Packaging::Production::PackageWriterHelper *)
0x1800ba443  mov     r14d, eax
0x1800ba446  test    eax, eax
0x1800ba448  jns     loc_1800BA4DB
0x1800ba44e  mov     rcx, [rbp+57h]; this
0x1800ba452  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba459  mov     r9d, eax; char *
0x1800ba45c  mov     edx, 2CAh; void *
0x1800ba461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba466  mov     rcx, [rsp+120h+var_100]; this
0x1800ba46b  mov     [rsp+120h+var_100], r15
0x1800ba470  test    rcx, rcx
0x1800ba473  jz      short loc_1800BA47A
0x1800ba475  call    ??_GPackageWriterHelper@Production@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(uint)
0x1800ba47a  lea     rdx, [rsp+120h+RestartKey]; RestartKey
0x1800ba47f  mov     [rsp+120h+RestartKey], r15
0x1800ba484  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba488  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800ba48f  nop     dword ptr [rax+rax+00h]
0x1800ba494  test    rax, rax
0x1800ba497  jz      loc_1800BA348
0x1800ba49d  mov     rdi, [rax]
0x1800ba4a0  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba4a4  mov     rsi, [rax+8]
0x1800ba4a8  mov     rdx, rax; Buffer
0x1800ba4ab  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800ba4b2  nop     dword ptr [rax+rax+00h]
0x1800ba4b7  mov     rax, [rbp+4Fh+var_58]
0x1800ba4bb  test    rax, rax
0x1800ba4be  jz      short loc_1800BA4C8
0x1800ba4c0  mov     rcx, rdi
0x1800ba4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba4c8  mov     rax, [rbp+4Fh+var_50]
0x1800ba4cc  test    rax, rax
0x1800ba4cf  jz      short loc_1800BA47A
0x1800ba4d1  mov     rcx, rsi
0x1800ba4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba4d9  jmp     short loc_1800BA47A
0x1800ba4db  mov     rdx, [rsp+120h+var_100]; struct Appx::Packaging::Consumption::AppxPackageReader *
0x1800ba4e0  mov     rcx, rdi; this
0x1800ba4e3  call    ?ExtractFootprintFilesAndAddToOpcPackage@Packaging@Appx@@YAJPEAVAppxPackageReader@Consumption@12@PEAVPackageWriterHelper@Production@12@@Z; Appx::Packaging::ExtractFootprintFilesAndAddToOpcPackage(Appx::Packaging::Consumption::AppxPackageReader *,Appx::Packaging::Production::PackageWriterHelper *)
0x1800ba4e8  mov     edi, eax
0x1800ba4ea  test    eax, eax
0x1800ba4ec  jns     loc_1800BA59E
0x1800ba4f2  mov     rcx, [rbp+57h]; this
0x1800ba4f6  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba4fd  mov     r9d, eax; char *
0x1800ba500  mov     edx, 2CCh; void *
0x1800ba505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba50a  mov     rcx, [rsp+120h+var_100]; this
0x1800ba50f  mov     [rsp+120h+var_100], r15
0x1800ba514  test    rcx, rcx
0x1800ba517  jz      short loc_1800BA51E
0x1800ba519  call    ??_GPackageWriterHelper@Production@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(uint)
0x1800ba51e  lea     rdx, [rsp+120h+RestartKey]; RestartKey
0x1800ba523  mov     [rsp+120h+RestartKey], r15
0x1800ba528  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba52c  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800ba533  nop     dword ptr [rax+rax+00h]
0x1800ba538  test    rax, rax
0x1800ba53b  jz      short loc_1800BA57B
0x1800ba53d  mov     rsi, [rax]
0x1800ba540  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba544  mov     r14, [rax+8]
0x1800ba548  mov     rdx, rax; Buffer
0x1800ba54b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800ba552  nop     dword ptr [rax+rax+00h]
0x1800ba557  mov     rax, [rbp+4Fh+var_58]
0x1800ba55b  test    rax, rax
0x1800ba55e  jz      short loc_1800BA568
0x1800ba560  mov     rcx, rsi
0x1800ba563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba568  mov     rax, [rbp+4Fh+var_50]
0x1800ba56c  test    rax, rax
0x1800ba56f  jz      short loc_1800BA51E
0x1800ba571  mov     rcx, r14
0x1800ba574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba579  jmp     short loc_1800BA51E
0x1800ba57b  mov     rcx, rbx; void *
0x1800ba57e  call    ??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAVZipEditor@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)
0x1800ba583  lea     rcx, [rsp+120h+var_F0]
0x1800ba588  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba58d  lea     rcx, [rsp+120h+var_E8]
0x1800ba592  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ba597  mov     ebx, edi
0x1800ba599  jmp     loc_1800BA821
0x1800ba59e  mov     rdx, [rsp+120h+var_100]
0x1800ba5a3  lea     rcx, [rbp+4Fh+Table]
0x1800ba5a7  call    ?ExtractContentTypesFileAndAddToOpcPackage@Packaging@Appx@@YAJAEAV?$GenericMap@PEBDPEAVZipFileItem@Packaging@Appx@@@Common@@PEAVPackageWriterHelper@Production@12@@Z; Appx::Packaging::ExtractContentTypesFileAndAddToOpcPackage(Common::GenericMap<char const *,Appx::Packaging::ZipFileItem *> &,Appx::Packaging::Production::PackageWriterHelper *)
0x1800ba5ac  mov     edi, eax
0x1800ba5ae  test    eax, eax
0x1800ba5b0  jns     loc_1800BA643
0x1800ba5b6  mov     rcx, [rbp+57h]; this
0x1800ba5ba  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800ba5c1  mov     r9d, eax; char *
0x1800ba5c4  mov     edx, 2CEh; void *
0x1800ba5c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba5ce  mov     rcx, [rsp+120h+var_100]; this
0x1800ba5d3  mov     [rsp+120h+var_100], r15
0x1800ba5d8  test    rcx, rcx
0x1800ba5db  jz      short loc_1800BA5E2
0x1800ba5dd  call    ??_GPackageWriterHelper@Production@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Production::PackageWriterHelper::`scalar deleting destructor'(uint)
0x1800ba5e2  lea     rdx, [rsp+120h+RestartKey]; RestartKey
0x1800ba5e7  mov     [rsp+120h+RestartKey], r15
0x1800ba5ec  lea     rcx, [rbp+4Fh+Table]; Table
0x1800ba5f0  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800ba5f7  nop     dword ptr [rax+rax+00h]
0x1800ba5fc  test    rax, rax
  ... truncated ...
```

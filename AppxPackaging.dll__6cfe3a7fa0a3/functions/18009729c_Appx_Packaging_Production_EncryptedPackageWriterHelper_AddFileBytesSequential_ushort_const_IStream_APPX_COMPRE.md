# Appx::Packaging::Production::EncryptedPackageWriterHelper::AddFileBytesSequential(ushort const *,IStream *,APPX_COMPRESSION_OPTION,Appx::Packaging::EncryptionEngine *,bool,bool,unsigned __int64 *)

- ea: `0x18009729c`
- end: `0x180097e3a`
- name: `?AddFileBytesSequential@EncryptedPackageWriterHelper@Production@Packaging@Appx@@AEAAJPEBGPEAUIStream@@W4APPX_COMPRESSION_OPTION@@PEAVEncryptionEngine@34@_N4PEA_K@Z`
- size: `2974`
- prototype: `__int64 __usercall@<rax>(struct Appx::Packaging::CatalogHelper **this@<rcx>, const unsigned __int16 *@<rdx>, struct IStream *@<r8>, enum APPX_COMPRESSION_OPTION@<r9d>, struct Appx::Packaging::EncryptionEngine *, bool, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ee018`

## callees

- `0x180005eb8`
- `0x180007234`
- `0x180008c40`
- `0x180008f4c`
- `0x180009eb8`
- `0x1800133fc`
- `0x18007cf20`
- `0x180081f90`
- `0x180084398`
- `0x180088490`
- `0x1800888b4`
- `0x180089630`
- `0x18008972c`
- `0x18008da78`
- `0x18009729c`
- `0x180097e40`
- `0x1800992c4`
- `0x1800992d0`
- `0x18009d3d0`
- `0x1800b65f4`
- `0x1800ea8d8`
- `0x1800ff100`
- `0x1801006dc`
- `0x180106010`

## string_xrefs

- `0x180097306`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097340`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097379`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800973fb`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x18009746a`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800974e0`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800975eb`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097645`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800976a9`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x1800976f8`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097748`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x18009781e`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097938`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097a3a`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097a7f`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097abe`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097afb`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097b33`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097b6b`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097bad`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097bef`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097c31`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097c73`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097cb5`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097cfd`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097d47`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097d8d`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`
- `0x180097dc5`: `onecore\printscan\appxpackaging\production\src\encryptedpackagewriterhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::Production::EncryptedPackageWriterHelper::AddFileBytesSequential(
        struct Appx::Packaging::CatalogHelper **this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        enum APPX_COMPRESSION_OPTION a4,
        struct Appx::Packaging::EncryptionEngine *a5,
        bool a6,
        bool a7,
        unsigned __int64 *a8)
{
  struct IStream *v9; // r13
  void *v11; // rbx
  unsigned __int64 *v12; // r8
  unsigned int v13; // edi
  unsigned __int64 v14; // rdx
  int StreamSize; // eax
  unsigned int v17; // esi
  unsigned __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  char *v22; // r15
  unsigned __int8 *v23; // rsi
  int v24; // edi
  int v25; // edi
  int v26; // edi
  unsigned __int64 v27; // rdx
  unsigned int v28; // edi
  int v29; // eax
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rdx
  struct Appx::Packaging::CatalogHelper *v32; // rdi
  unsigned __int64 v33; // rdx
  unsigned int v34; // r12d
  Appx::Packaging::PackageSignConfigInfo *v35; // rax
  bool v36; // dl
  struct Appx::Packaging::PackageSignConfigInfo *v37; // rax
  void (*v38)(const unsigned __int16 *); // rdx
  Appx::Packaging::PackageSignConfigInfo *v39; // rdi
  int v40; // eax
  unsigned int v41; // r15d
  int PE; // eax
  unsigned int v43; // r9d
  unsigned __int64 v44; // rdx
  int TempFolderPathCached; // eax
  unsigned __int64 v46; // rdx
  int v47; // eax
  unsigned __int64 v48; // rdx
  int v49; // eax
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  int v52; // eax
  int v53; // eax
  int v54; // eax
  unsigned __int64 v55; // rdx
  int v56; // eax
  unsigned int v57; // r15d
  unsigned int v58; // r13d
  unsigned __int8 *v59; // rax
  unsigned __int8 *v60; // rdi
  int v61; // eax
  unsigned __int8 *v62; // rax
  Appx::Packaging::HashEngine *v63; // rcx
  int v64; // eax
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // rdx
  int v67; // eax
  int HashValue; // eax
  int v69; // eax
  unsigned __int64 v70; // r8
  struct Appx::Packaging::CatalogHelper *v71; // rdx
  int v72; // eax
  struct IStream *v73; // r9
  int v74; // eax
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // rdx
  unsigned __int64 v77; // rdx
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rdx
  unsigned __int64 v80; // rdx
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rdx
  unsigned __int64 v83; // rdx
  unsigned __int64 v84; // rdx
  unsigned __int64 v85; // rdx
  unsigned __int64 v86; // rdx
  unsigned __int64 v87; // rdx
  unsigned __int64 v88; // rdx
  unsigned __int64 v89; // rdx
  unsigned __int64 v90; // rdx
  unsigned __int64 v91; // rdx
  unsigned __int64 v92; // rdx
  unsigned __int64 v93; // rdx
  unsigned __int64 v94; // rdx
  unsigned __int64 v95; // rdx
  unsigned __int64 v96; // rdx
  unsigned __int64 v97; // rdx
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rdx
  unsigned __int8 *v100; // [rsp+28h] [rbp-99h]
  int v101; // [rsp+28h] [rbp-99h]
  unsigned int v102; // [rsp+30h] [rbp-91h]
  unsigned __int8 *v103; // [rsp+40h] [rbp-81h]
  bool v104; // [rsp+58h] [rbp-69h] BYREF
  Appx::Packaging *v105; // [rsp+60h] [rbp-61h] BYREF
  bool v106; // [rsp+68h] [rbp-59h]
  bool v107; // [rsp+69h] [rbp-58h] BYREF
  unsigned __int8 *v108; // [rsp+70h] [rbp-51h] BYREF
  unsigned int v109; // [rsp+78h] [rbp-49h] BYREF
  unsigned __int16 *v110; // [rsp+80h] [rbp-41h] BYREF
  Appx::Packaging *v111; // [rsp+88h] [rbp-39h] BYREF
  unsigned int v112; // [rsp+90h] [rbp-31h] BYREF
  char *v113; // [rsp+98h] [rbp-29h]
  char *v114; // [rsp+A0h] [rbp-21h]
  unsigned int v115; // [rsp+A8h] [rbp-19h] BYREF
  unsigned __int8 *v116[9]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+3Fh]
  Appx::Packaging *v119; // [rsp+118h] [rbp+57h]

  v119 = a3;
  v116[1] = (unsigned __int8 *)-2LL;
  v9 = a3;
  v107 = 0;
  v115 = 0;
  v110 = 0;
  v11 = operator new[](0x10000u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v100);
    operator delete(0, v14);
    return v13;
  }
  StreamSize = Appx::Packaging::GetStreamSize(v9, (struct IStream *)&v110, v12);
  v17 = StreamSize;
  if ( StreamSize < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
      (const char *)(unsigned int)StreamSize,
      (int)v100);
    operator delete(v11, v18);
    return v17;
  }
  v19 = Appx::Packaging::SetStreamPosition(v9, 0);
  v17 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
      (const char *)(unsigned int)v19,
      (int)v100);
    operator delete(v11, v21);
    return v17;
  }
  v106 = 0;
  v22 = (char *)v110;
  v114 = (char *)v110;
  v113 = (char *)v110;
  v111 = (Appx::Packaging *)v110;
  v23 = 0;
  v108 = 0;
  v105 = 0;
  if ( a4 )
  {
    v24 = a4 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
          {
            v13 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30,
              (unsigned int)"onecore\\printscan\\AppxPackaging\\lib\\Zip\\src\\AppxZipUtil.hpp",
              (const char *)0x80070057LL,
              (int)v100);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x177,
              (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
              (const char *)0x80070057LL,
              v101);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
            Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(0);
            operator delete(v11, v27);
            return v13;
          }
          v28 = 4;
        }
        else
        {
          v28 = 3;
        }
      }
      else
      {
        v28 = 2;
      }
    }
    else
    {
      v28 = 1;
    }
    v106 = a6;
    if ( a6 )
    {
      LOBYTE(v20) = a6;
      v29 = Appx::Packaging::ZipDeflator::Create(v28, v20, &v108);
      v13 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v29,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v108);
        operator delete(v11, v30);
        return v13;
      }
      if ( !this[7] )
      {
        v32 = (struct Appx::Packaging::CatalogHelper *)operator new[](
                                                         0x18000u,
                                                         (const struct std::nothrow_t *)&std::nothrow);
        if ( this[7] == v32 )
        {
          v32 = this[7];
        }
        else
        {
          operator delete(this[7], v31);
          this[7] = v32;
        }
        if ( !v32 )
        {
          v13 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x181,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)0x8007000ELL,
            (int)v100);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v108);
          operator delete(v11, v33);
          return v13;
        }
      }
      v113 = 0;
      v23 = v108;
    }
    else
    {
      if ( a7 )
      {
        v13 = -2146958848;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)0x80080200LL,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(0);
        operator delete(v11, v51);
        return v13;
      }
      v110 = 0;
      TempFolderPathCached = Appx::Packaging::FileNameHelper::GetTempFolderPathCached(
                               this[1],
                               (const unsigned __int16 **)&v110);
      v41 = TempFolderPathCached;
      if ( TempFolderPathCached < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18F,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)TempFolderPathCached,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(0);
        operator delete(v11, v46);
        return v41;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      v100 = (unsigned __int8 *)&v105;
      v47 = Appx::Packaging::ZipDeflator::DeflateToTempFileStream(v28, v9, v110, &v111);
      v13 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v47,
          (int)&v105);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(0);
        operator delete(v11, v48);
        return v13;
      }
      v9 = v105;
      v119 = v105;
      v49 = Appx::Packaging::SetStreamPosition(v105, 0);
      v13 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x199,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v49,
          (int)&v105);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(0);
        operator delete(v11, v50);
        return v13;
      }
      v113 = (char *)v111;
      v22 = (char *)v111;
      v114 = (char *)v111;
    }
  }
  v110 = 0;
  while ( v22 )
  {
    v34 = (unsigned int)v22;
    if ( (unsigned __int64)v22 > 0x10000 )
      v34 = 0x10000;
    v112 = 0;
    if ( a7 )
    {
      if ( !*this )
      {
        v35 = (Appx::Packaging::PackageSignConfigInfo *)operator new(
                                                          0x40u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
        if ( !v35
          || (v37 = (struct Appx::Packaging::PackageSignConfigInfo *)Appx::Packaging::PackageSignConfigInfo::PackageSignConfigInfo(
                                                                       v35,
                                                                       v36),
              (v39 = v37) == 0) )
        {
          v13 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A9,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)0x8007000ELL,
            (int)v100);
          Common::AutoPtrDeallocate<Appx::Packaging::PackageSignConfigInfo>(0);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v77);
          return v13;
        }
        v40 = Appx::Packaging::CatalogHelper::Create(v37, v38, this);
        v41 = v40;
        if ( v40 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)(unsigned int)v40,
            (int)v100);
          Common::AutoPtrDeallocate<Appx::Packaging::PackageSignConfigInfo>(v39);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v76);
          return v41;
        }
        Common::AutoPtrDeallocate<Appx::Packaging::PackageSignConfigInfo>(v39);
        v22 = v114;
      }
      *((_BYTE *)*this + 200) = *((_BYTE *)this + 121);
      PE = Appx::Packaging::CatalogHelper::ReadBlockAndFindPE(
             *this,
             a2,
             v9,
             v34,
             (bool)v100,
             &v115,
             &v112,
             (unsigned __int8 *)v11,
             &v107);
      v13 = PE;
      if ( PE < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)PE,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v44);
        return v13;
      }
    }
    else
    {
      v52 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, unsigned int *))(*(_QWORD *)v9 + 24LL))(
              v9,
              v11,
              v34,
              &v112);
      v13 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v52,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v98);
        return v13;
      }
    }
    if ( v112 != v34 )
    {
      v13 = -2146958848;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)0x80080200LL,
        (int)v100);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
      operator delete(v11, v97);
      return v13;
    }
    if ( a6 )
    {
      v53 = Appx::Packaging::HashEngine::HashData(this[3], v34, (const unsigned __int8 *)v11);
      v13 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v53,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v78);
        return v13;
      }
    }
    v109 = 0;
    if ( v106 )
    {
      v104 = 0;
      v103 = (unsigned __int8 *)this[7];
      if ( (unsigned __int64)v22 <= v34 )
      {
        v56 = Appx::Packaging::ZipDeflator::Deflate(
                (Appx::Packaging::ZipDeflator *)v23,
                v34,
                (const unsigned __int8 *)v11,
                v43,
                4,
                &v104,
                &v109,
                v103);
        v13 = v56;
        if ( v56 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DC,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)(unsigned int)v56,
            (int)v100);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v80);
          return v13;
        }
      }
      else
      {
        v54 = Appx::Packaging::ZipDeflator::Deflate(
                (Appx::Packaging::ZipDeflator *)v23,
                v34,
                (const unsigned __int8 *)v11,
                v43,
                *(_DWORD *)v23,
                &v104,
                &v109,
                v103);
        v13 = v54;
        if ( v54 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D6,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)(unsigned int)v54,
            (int)v100);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v55);
          return v13;
        }
      }
      if ( v104 )
      {
        v13 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E0,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)0x8000FFFFLL,
          (int)v100);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v79);
        return v13;
      }
      v108 = (unsigned __int8 *)this[7];
      v57 = 98304;
      v58 = v109;
      v113 += v109;
    }
    else
    {
      v57 = 0x10000;
      v58 = v34;
      v108 = (unsigned __int8 *)v11;
    }
    v59 = (unsigned __int8 *)operator new[](0x10000u, (const struct std::nothrow_t *)&std::nothrow);
    v60 = v59;
    if ( !v59 )
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)0x8007000ELL,
        (int)v100);
      operator delete(0, v95);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
      operator delete(v11, v96);
      return v13;
    }
    if ( a5 )
    {
      LODWORD(v111) = 0;
      v61 = Appx::Packaging::EncryptionEngine::Encrypt(
              a5,
              (unsigned __int64)v110,
              v57,
              v58,
              v108,
              v102,
              (unsigned int *)&v111,
              v59);
      v41 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v61,
          (int)v100);
        operator delete(v60, v81);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v82);
        return v41;
      }
      v62 = v60;
      v108 = v60;
      v58 = (unsigned int)v111;
    }
    else
    {
      v62 = v108;
    }
    if ( a6 )
    {
      v116[0] = 0;
      LODWORD(v111) = 0;
      v63 = this[4];
      if ( a5 )
      {
        v64 = Appx::Packaging::HashEngine::HashData(v63, v58, v62);
        v41 = v64;
        if ( v64 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)(unsigned int)v64,
            (int)v100);
          operator delete(v60, v65);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v66);
          return v41;
        }
      }
      else
      {
        v67 = Appx::Packaging::HashEngine::HashData(v63, v34, (const unsigned __int8 *)v11);
        v41 = v67;
        if ( v67 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x210,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
            (const char *)(unsigned int)v67,
            (int)v100);
          operator delete(v60, v87);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
          Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
          operator delete(v11, v88);
          return v41;
        }
      }
      HashValue = Appx::Packaging::HashEngine::GetHashValue(
                    this[4],
                    (unsigned int *)&v111,
                    (const unsigned __int8 **)v116);
      v41 = HashValue;
      if ( HashValue < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x212,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)HashValue,
          (int)v100);
        operator delete(v60, v85);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v86);
        return v41;
      }
      v69 = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddBlock(this[11], v116[0], (unsigned int)v111, v109);
      v41 = v69;
      if ( v69 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x213,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
          (const char *)(unsigned int)v69,
          (int)v100);
        operator delete(v60, v83);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
        Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
        operator delete(v11, v84);
        return v41;
      }
    }
    v70 = (unsigned __int64)this[14];
    v71 = (struct Appx::Packaging::CatalogHelper *)(v58 + v70);
    this[14] = v71;
    if ( v70 > ~(unsigned __int64)v58 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x217,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)0x80070216LL,
        (int)v100);
      operator delete(v60, v93);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
      operator delete(v11, v94);
      return 2147942934LL;
    }
    v72 = Appx::Packaging::SetStreamSize(this[10], v71, v70);
    v41 = v72;
    if ( v72 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x218,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)(unsigned int)v72,
        (int)v100);
      operator delete(v60, v91);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
      operator delete(v11, v92);
      return v41;
    }
    v74 = Appx::Packaging::WriteExactNumberOfBytesToStream(
            (Appx::Packaging *)v58,
            (unsigned int)v108,
            (const unsigned __int8 *)this[10],
            v73);
    v41 = v74;
    if ( v74 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\encryptedpackagewriterhelper.cpp",
        (const char *)(unsigned int)v74,
        (int)v100);
      operator delete(v60, v89);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
      operator delete(v11, v90);
      return v41;
    }
    v110 = (unsigned __int16 *)((char *)v110 + v34);
    v22 = &v114[-v34];
    v114 = v22;
    operator delete(v60, v75);
    v9 = v119;
  }
  *a8 = (unsigned __int64)v113;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v105);
  Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>((char *)v23);
  operator delete(v11, v99);
  return 0;
}

```

## disassembly

```asm
0x18009729c  mov     rax, rsp
0x18009729f  mov     [rax+18h], r8
0x1800972a3  mov     [rax+10h], rdx
0x1800972a7  push    rbp
0x1800972a8  push    rsi
0x1800972a9  push    rdi
0x1800972aa  push    r12
0x1800972ac  push    r13
0x1800972ae  push    r14
0x1800972b0  push    r15
0x1800972b2  lea     rbp, [rax-3Fh]
0x1800972b6  sub     rsp, 0C0h
0x1800972bd  mov     [rbp+37h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800972c5  mov     [rax+8], rbx
0x1800972c9  mov     edi, r9d
0x1800972cc  mov     r13, r8
0x1800972cf  mov     r14, rcx
0x1800972d2  xor     r12d, r12d
0x1800972d5  mov     [rbp+37h+var_8F], r12b
0x1800972d9  mov     [rbp+37h+var_50], r12d
0x1800972dd  mov     [rbp+37h+var_78], r12
0x1800972e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800972e8  mov     ecx, 10000h; unsigned __int64
0x1800972ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800972f2  mov     rbx, rax
0x1800972f5  test    rax, rax
0x1800972f8  jnz     short loc_180097327
0x1800972fa  mov     rcx, [rbp+3Fh]; this
0x1800972fe  mov     edi, 8007000Eh
0x180097303  mov     r9d, edi; char *
0x180097306  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x18009730d  mov     edx, 167h; void *
0x180097312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097317  nop
0x180097318  xor     ecx, ecx; void *
0x18009731a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009731f  nop
0x180097320  mov     eax, edi
0x180097322  jmp     loc_180097E1E
0x180097327  lea     rdx, [rbp+37h+var_78]; struct IStream *
0x18009732b  mov     rcx, r13; this
0x18009732e  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x180097333  mov     esi, eax
0x180097335  test    eax, eax
0x180097337  jns     short loc_180097362
0x180097339  mov     rcx, [rbp+3Fh]; this
0x18009733d  mov     r9d, eax; char *
0x180097340  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180097347  mov     edx, 16Ch; void *
0x18009734c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097351  nop
0x180097352  mov     rcx, rbx; void *
0x180097355  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009735a  nop
0x18009735b  mov     eax, esi
0x18009735d  jmp     loc_180097E1E
0x180097362  xor     edx, edx; struct IStream *
0x180097364  mov     rcx, r13; this
0x180097367  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x18009736c  mov     esi, eax
0x18009736e  test    eax, eax
0x180097370  jns     short loc_180097396
0x180097372  mov     rcx, [rbp+3Fh]; this
0x180097376  mov     r9d, eax; char *
0x180097379  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180097380  mov     edx, 16Dh; void *
0x180097385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009738a  nop
0x18009738b  mov     rcx, rbx; void *
0x18009738e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097393  nop
0x180097394  jmp     short loc_18009735B
0x180097396  mov     [rbp+37h+var_90], r12b
0x18009739a  mov     r15, [rbp+37h+var_78]
0x18009739e  mov     [rbp+37h+var_58], r15
0x1800973a2  mov     rcx, r15
0x1800973a5  mov     [rbp+37h+var_60], rcx
0x1800973a9  mov     [rbp+37h+var_70], rcx
0x1800973ad  mov     rsi, r12
0x1800973b0  mov     [rbp+37h+var_88], r12
0x1800973b4  mov     [rbp+37h+var_98], r12
0x1800973b8  mov     cl, [rbp+37h+arg_28]
0x1800973bb  test    edi, edi
0x1800973bd  jz      loc_18009751A
0x1800973c3  sub     edi, 1
0x1800973c6  jz      short loc_180097440
0x1800973c8  sub     edi, 1
0x1800973cb  jz      short loc_180097439
0x1800973cd  sub     edi, 1
0x1800973d0  jz      short loc_180097432
0x1800973d2  cmp     edi, 1
0x1800973d5  jz      short loc_18009742B
0x1800973d7  mov     rcx, [rbp+3Fh]; this
0x1800973db  mov     edi, 80070057h
0x1800973e0  mov     r9d, edi; char *
0x1800973e3  lea     r8, aOnecorePrintsc_80; "onecore\\printscan\\AppxPackaging\\lib"...
0x1800973ea  mov     edx, 30h ; '0'; void *
0x1800973ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800973f4  mov     rcx, [rbp+3Fh]; this
0x1800973f8  mov     r9d, edi; char *
0x1800973fb  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180097402  mov     edx, 177h; void *
0x180097407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009740c  lea     rcx, [rbp+37h+var_98]
0x180097410  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097415  xor     ecx, ecx; void *
0x180097417  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x18009741c  nop
0x18009741d  mov     rcx, rbx; void *
0x180097420  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097425  nop
0x180097426  jmp     loc_180097320
0x18009742b  mov     edi, 4
0x180097430  jmp     short loc_180097445
0x180097432  mov     edi, 3
0x180097437  jmp     short loc_180097445
0x180097439  mov     edi, 2
0x18009743e  jmp     short loc_180097445
0x180097440  mov     edi, 1
0x180097445  mov     [rbp+37h+var_90], cl
0x180097448  test    cl, cl
0x18009744a  jz      loc_18009761C
0x180097450  lea     r8, [rbp+37h+var_88]
0x180097454  mov     dl, cl
0x180097456  mov     ecx, edi
0x180097458  call    ?Create@ZipDeflator@Packaging@Appx@@SAJW4ZipCompressionType@23@_NAEAV?$AutoPtr@VZipDeflator@Packaging@Appx@@$1??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@@Z; Appx::Packaging::ZipDeflator::Create(Appx::Packaging::ZipCompressionType,bool,Common::AutoPtr<Appx::Packaging::ZipDeflator,&Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)> &)
0x18009745d  mov     edi, eax
0x18009745f  test    eax, eax
0x180097461  jns     short loc_18009749C
0x180097463  mov     rcx, [rbp+3Fh]; this
0x180097467  mov     r9d, eax; char *
0x18009746a  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x180097471  mov     edx, 17Dh; void *
0x180097476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009747b  lea     rcx, [rbp+37h+var_98]
0x18009747f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097484  mov     rcx, [rbp+37h+var_88]; void *
0x180097488  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x18009748d  nop
0x18009748e  mov     rcx, rbx; void *
0x180097491  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097496  nop
0x180097497  jmp     loc_180097320
0x18009749c  cmp     [r14+38h], r12
0x1800974a0  jnz     short loc_180097512
0x1800974a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800974a9  mov     ecx, 18000h; unsigned __int64
0x1800974ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800974b3  mov     rdi, rax
0x1800974b6  cmp     [r14+38h], rax
0x1800974ba  jz      short loc_1800974CB
0x1800974bc  mov     rcx, [r14+38h]; void *
0x1800974c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800974c5  mov     [r14+38h], rdi
0x1800974c9  jmp     short loc_1800974CF
0x1800974cb  mov     rdi, [r14+38h]
0x1800974cf  test    rdi, rdi
0x1800974d2  jnz     short loc_180097512
0x1800974d4  mov     rcx, [rbp+3Fh]; this
0x1800974d8  mov     edi, 8007000Eh
0x1800974dd  mov     r9d, edi; char *
0x1800974e0  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x1800974e7  mov     edx, 181h; void *
0x1800974ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800974f1  lea     rcx, [rbp+37h+var_98]
0x1800974f5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800974fa  mov     rcx, [rbp+37h+var_88]; void *
0x1800974fe  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x180097503  nop
0x180097504  mov     rcx, rbx; void *
0x180097507  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009750c  nop
0x18009750d  jmp     loc_180097320
0x180097512  mov     [rbp+37h+var_60], r12
0x180097516  mov     rsi, [rbp+37h+var_88]
0x18009751a  mov     [rbp+37h+var_78], r12
0x18009751e  test    r15, r15
0x180097521  jz      loc_180097DF6
0x180097527  mov     r12d, r15d
0x18009752a  mov     eax, 10000h
0x18009752f  cmp     r15, rax
0x180097532  cmova   r12d, eax
0x180097536  xor     edi, edi
0x180097538  mov     [rbp+37h+var_68], edi
0x18009753b  cmp     [rbp+37h+arg_30], dil
0x18009753f  jz      loc_180097778
0x180097545  cmp     [r14], rdi
0x180097548  jnz     short loc_180097598
0x18009754a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180097551  lea     ecx, [rdi+40h]; unsigned __int64
0x180097554  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180097559  test    rax, rax
0x18009755c  jz      loc_180097A73
0x180097562  mov     rcx, rax; this
0x180097565  call    ??0PackageSignConfigInfo@Packaging@Appx@@QEAA@_N@Z; Appx::Packaging::PackageSignConfigInfo::PackageSignConfigInfo(bool)
0x18009756a  mov     rdi, rax
0x18009756d  test    rax, rax
0x180097570  jz      loc_180097A73
0x180097576  mov     r8, r14; struct Appx::Packaging::CatalogHelper **
0x180097579  mov     rcx, rax; struct Appx::Packaging::PackageSignConfigInfo *
0x18009757c  call    ?Create@CatalogHelper@Packaging@Appx@@SAJPEAVPackageSignConfigInfo@23@P6AXPEBG@ZPEAPEAV123@@Z; Appx::Packaging::CatalogHelper::Create(Appx::Packaging::PackageSignConfigInfo *,void (*)(ushort const *),Appx::Packaging::CatalogHelper * *)
0x180097581  mov     r15d, eax
0x180097584  test    eax, eax
0x180097586  js      loc_180097A33
0x18009758c  mov     rcx, rdi; void *
0x18009758f  call    ??$AutoPtrDeallocate@VPackageSignConfigInfo@Packaging@Appx@@@Common@@YAXPEAVPackageSignConfigInfo@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::PackageSignConfigInfo>(Appx::Packaging::PackageSignConfigInfo *)
0x180097594  mov     r15, [rbp+37h+var_58]
0x180097598  mov     rcx, [r14]
0x18009759b  mov     al, [r14+79h]
0x18009759f  mov     [rcx+0C8h], al
0x1800975a5  lea     rax, [rbp+37h+var_8F]
0x1800975a9  mov     [rsp+40h], rax; bool *
0x1800975ae  mov     [rsp+0F0h+var_B8], rbx; unsigned __int8 *
0x1800975b3  lea     rax, [rbp+37h+var_68]
0x1800975b7  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x1800975bc  lea     rax, [rbp+37h+var_50]
0x1800975c0  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x1800975c5  mov     r9d, r12d; unsigned int
0x1800975c8  mov     r8, r13; struct IStream *
0x1800975cb  mov     rdx, [rbp+37h+arg_8]; unsigned __int16 *
0x1800975cf  mov     rcx, [r14]; this
0x1800975d2  call    ?ReadBlockAndFindPE@CatalogHelper@Packaging@Appx@@QEAAJPEBGPEAUIStream@@I_NPEAI3PEAEPEA_N@Z; Appx::Packaging::CatalogHelper::ReadBlockAndFindPE(ushort const *,IStream *,uint,bool,uint *,uint *,uchar *,bool *)
0x1800975d7  mov     edi, eax
0x1800975d9  xor     r13d, r13d
0x1800975dc  test    eax, eax
0x1800975de  jns     loc_18009779F
0x1800975e4  mov     rcx, [rbp+3Fh]; this
0x1800975e8  mov     r9d, eax; char *
0x1800975eb  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x1800975f2  mov     edx, 1B7h; void *
0x1800975f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800975fc  lea     rcx, [rbp+37h+var_98]
0x180097600  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097605  mov     rcx, rsi; void *
0x180097608  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x18009760d  nop
0x18009760e  mov     rcx, rbx; void *
0x180097611  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097616  nop
0x180097617  jmp     loc_180097320
0x18009761c  cmp     [rbp+37h+arg_30], r12b
0x180097620  jnz     loc_18009773C
0x180097626  mov     [rbp+37h+var_78], r12
0x18009762a  lea     rdx, [rbp+37h+var_78]; unsigned __int16 **
0x18009762e  mov     rcx, [r14+8]; this
0x180097632  call    ?GetTempFolderPathCached@FileNameHelper@Packaging@Appx@@QEAAJPEAPEBG@Z; Appx::Packaging::FileNameHelper::GetTempFolderPathCached(ushort const * *)
0x180097637  mov     r15d, eax
0x18009763a  test    eax, eax
0x18009763c  jns     short loc_180097678
0x18009763e  mov     rcx, [rbp+3Fh]; this
0x180097642  mov     r9d, eax; char *
0x180097645  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x18009764c  mov     edx, 18Fh; void *
0x180097651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097656  lea     rcx, [rbp+37h+var_98]
0x18009765a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009765f  xor     ecx, ecx; void *
0x180097661  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x180097666  nop
0x180097667  mov     rcx, rbx; void *
0x18009766a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009766f  nop
0x180097670  mov     eax, r15d
0x180097673  jmp     loc_180097E1E
0x180097678  lea     rcx, [rbp+37h+var_98]
0x18009767c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097681  lea     rax, [rbp+37h+var_98]
0x180097685  mov     [rsp+0F0h+var_D0], rax; int
0x18009768a  lea     r9, [rbp+37h+var_70]
0x18009768e  mov     r8, [rbp+37h+var_78]
0x180097692  mov     rdx, r13
0x180097695  mov     ecx, edi
0x180097697  call    ?DeflateToTempFileStream@ZipDeflator@Packaging@Appx@@SAJW4ZipCompressionType@23@PEAUIStream@@PEBGPEA_KPEAPEAU5@@Z; Appx::Packaging::ZipDeflator::DeflateToTempFileStream(Appx::Packaging::ZipCompressionType,IStream *,ushort const *,unsigned __int64 *,IStream * *)
0x18009769c  mov     edi, eax
0x18009769e  test    eax, eax
0x1800976a0  jns     short loc_1800976D9
0x1800976a2  mov     rcx, [rbp+3Fh]; this
0x1800976a6  mov     r9d, eax; char *
0x1800976a9  lea     r8, aOnecorePrintsc_119; "onecore\\printscan\\appxpackaging\\prod"...
0x1800976b0  mov     edx, 195h; void *
0x1800976b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800976ba  lea     rcx, [rbp+37h+var_98]
0x1800976be  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800976c3  xor     ecx, ecx; void *
0x1800976c5  call    ??$AutoPtrDeallocate@VZipDeflator@Packaging@Appx@@@Common@@YAXPEAVZipDeflator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipDeflator>(Appx::Packaging::ZipDeflator *)
0x1800976ca  nop
0x1800976cb  mov     rcx, rbx; void *
0x1800976ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800976d3  nop
0x1800976d4  jmp     loc_180097320
0x1800976d9  mov     r13, [rbp+37h+var_98]
0x1800976dd  mov     [rbp+37h+arg_10], r13
0x1800976e1  xor     edx, edx; struct IStream *
0x1800976e3  mov     rcx, r13; this
0x1800976e6  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x1800976eb  mov     edi, eax
0x1800976ed  test    eax, eax
0x1800976ef  jns     short loc_180097728
0x1800976f1  mov     rcx, [rbp+3Fh]; this
0x1800976f5  mov     r9d, eax; char *
  ... truncated ...
```

# Appx::Packaging::BlockMap::AppxBlockMapReader::Create(IStream *,ushort const *,bool,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)

- ea: `0x18005cd3c`
- end: `0x18005dbd0`
- name: `?Create@AppxBlockMapReader@BlockMap@Packaging@Appx@@SAJPEAUIStream@@PEBG_N1PEAPEAV1234@@Z`
- size: `3732`
- prototype: `__int64 __usercall@<rax>(struct IStream *@<rcx>, const unsigned __int16 *@<rdx>, bool@<r8b>, const unsigned __int16 *@<r9>, struct Appx::Packaging::BlockMap::AppxBlockMapReader **)`
- caller_count: `7`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005cb00`
- `0x18005cbf0`
- `0x18005ccf0`
- `0x1800c56a0`
- `0x1800c5790`
- `0x1800c5bd0`
- `0x1800c5cc0`

## callees

- `0x180002294`
- `0x1800026c4`
- `0x1800059f0`
- `0x180005eb8`
- `0x1800087e0`
- `0x1800133fc`
- `0x180046e28`
- `0x1800511a4`
- `0x18005307c`
- `0x18005baa8`
- `0x18005bb18`
- `0x18005cd3c`
- `0x18005f450`
- `0x18005fe04`
- `0x180060f40`
- `0x1800617c8`
- `0x180061a04`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800e6888`
- `0x1800e6a60`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d4cd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cfa6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cfa6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18005d55a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18005d55a`

## string_xrefs

- `0x18005cdc7`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005ce07`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005ce4e`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005ce82`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005cf05`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005cfbf`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d151`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d221`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d2a3`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d313`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d39a`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d65f`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d6f3`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d790`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d82d`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d8c1`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d94c`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d9c9`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005da38`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005daa7`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005db0c`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005d515`: `AppxBlockMap.xml`
- `0x18005d073`: `packageStatics->GetByInstalledLocation`
- `0x18005d064`: `Failed when trying to find package by its installed location. Failure not caused by ERROR_NOT_FOUND or E_NOT_SET`
- `0x18005d089`: `AppxBlockMapReader.cpp`
- `0x18005d07e`: `AppxBlockMapReader::Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::BlockMap::AppxBlockMapReader::Create(
        struct IStream *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        struct Appx::Packaging::BlockMap::AppxBlockMapReader **a5)
{
  char v6; // si
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  Appx::Packaging::BlockMap::AppxBlockMapReader *v14; // r13
  int v15; // eax
  unsigned __int64 v16; // rdx
  int PackagePathFromSignatureFileFullPath; // eax
  unsigned __int64 v18; // rdx
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v19; // rbx
  unsigned __int16 *v20; // r15
  int v21; // eax
  int v22; // edi
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  __int64 v25; // rdi
  int ActivationFactory; // eax
  unsigned __int64 v27; // rdx
  __int64 v28; // r14
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, struct Windows::Internal::StateRepository::IPackage **); // rdi
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // r8
  int v34; // edi
  const struct _tlgProvider_t *v35; // rax
  int v36; // r9d
  unsigned __int64 v37; // rdx
  int IsPackageFolded; // eax
  __int64 v39; // rcx
  __int64 v40; // r8
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  int v43; // eax
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, _QWORD, __int64 *); // rdi
  int v46; // eax
  int v47; // eax
  int v48; // eax
  unsigned int v49; // r14d
  __int64 v50; // rsi
  __int64 (__fastcall *v51)(__int64, _QWORD, __int64 *); // rdi
  int v52; // eax
  __int64 v53; // rsi
  __int64 (__fastcall *v54)(__int64, __int64, __int64 *); // rdi
  int v55; // eax
  int v56; // eax
  const unsigned __int16 *StringRawBuffer; // rsi
  int FullFilePathFromPackageInstalledLocation; // eax
  HRESULT v59; // eax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  unsigned __int64 v63; // rdx
  unsigned __int64 v64; // rdx
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // rdx
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // rdx
  unsigned __int64 v70; // rdx
  IStream *pstmTemplate; // [rsp+28h] [rbp-E0h]
  bool v73[8]; // [rsp+58h] [rbp-B0h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v74; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+70h] [rbp-98h] BYREF
  __int64 v77; // [rsp+78h] [rbp-90h] BYREF
  __int64 v78; // [rsp+80h] [rbp-88h] BYREF
  __int64 v79; // [rsp+88h] [rbp-80h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v80; // [rsp+90h] [rbp-78h] BYREF
  IStream *ppstm; // [rsp+98h] [rbp-70h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v82; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v83; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v84[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v85; // [rsp+C0h] [rbp-48h]
  _QWORD v86[2]; // [rsp+C8h] [rbp-40h] BYREF
  HSTRING_HEADER pszFile; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v88; // [rsp+F0h] [rbp-18h]
  HSTRING string[2]; // [rsp+F8h] [rbp-10h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader **v90; // [rsp+108h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v86[1] = -2;
  v6 = a3;
  v90 = a5;
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
  {
    pstmTemplate = (IStream *)string;
    McGenEventWrite_EventWriteTransfer(a1, EVENT_BLOCKMAP_READER_CREATE_START, a3, 1);
  }
  if ( !a2 || (v9 = Appx::Packaging::BlockMap::AppxBlockMapReader::ValidateSignature(a1, a2), v10 = v9, v9 >= 0) )
  {
    v82 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
    v11 = Appx::Packaging::BlockMap::AppxBlockMapReader::CreateAppxBlockMapReaderFromStream(a1, &v82);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
        (const char *)(unsigned int)v11,
        (int)pstmTemplate);
LABEL_141:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
      return v10;
    }
    v14 = v82;
    if ( v6 )
    {
      v80 = 0;
      if ( a2 )
      {
        PackagePathFromSignatureFileFullPath = Appx::Packaging::BlockMap::AppxBlockMapReader::GetPackagePathFromSignatureFileFullPath(
                                                 a2,
                                                 &v80);
        v10 = PackagePathFromSignatureFileFullPath;
        if ( PackagePathFromSignatureFileFullPath < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x70,
            (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
            (const char *)(unsigned int)PackagePathFromSignatureFileFullPath,
            (int)pstmTemplate);
          operator delete(v80, v18);
          goto LABEL_141;
        }
      }
      else
      {
        v15 = Appx::Packaging::BlockMap::AppxBlockMapReader::SetInstalledLocationFromFolderPath(a4);
        v10 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
            (const char *)(unsigned int)v15,
            (int)pstmTemplate);
          operator delete(v80, v16);
          goto LABEL_141;
        }
      }
      memset(&pszFile, 0, 20);
      v19 = v80;
      Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&pszFile, (const unsigned __int16 *)v80);
      v20 = *(unsigned __int16 **)&pszFile.Reserved.Reserved2[8];
      if ( (unsigned int)Common::String::StartsWith(
                           *(const unsigned __int16 **)&pszFile.Reserved.Reserved2[8],
                           LODWORD(pszFile.Reserved.Reserved1),
                           L"\\\\?\\",
                           4u) )
      {
        *(_OWORD *)v84 = 0;
        v85 = 0;
        v21 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v84, v20 + 4);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
            (const char *)(unsigned int)v21,
            (int)pstmTemplate);
          if ( v84[1] )
            operator delete(v84[1], v23);
          if ( v20 )
            operator delete(v20, v23);
          operator delete(v19, v23);
          goto LABEL_21;
        }
        Common::StringBuffer::operator=(&pszFile, v84);
        if ( v84[1] )
          operator delete(v84[1], v24);
        v20 = *(unsigned __int16 **)&pszFile.Reserved.Reserved2[8];
      }
      v75 = 0;
      v74 = 0;
      v88 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pszFile,
        L"Windows.Internal.StateRepository.Package",
        0x29u,
        0x28u);
      v25 = v88;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
      ActivationFactory = RoGetActivationFactory(v25, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v75);
      v22 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)ActivationFactory,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v27);
        operator delete(v19, v27);
        goto LABEL_21;
      }
      string[0] = (HSTRING)v20;
      v28 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&pszFile, string) + 24);
      v88 = 0;
      v29 = v75;
      v30 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)v75 + 560LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
      v31 = v30(v29, v28, &v74);
      v34 = v31;
      if ( v31 < 0 )
      {
        if ( v31 != -2147023728 )
        {
          v35 = Appx::Packaging::AppxPackagingProvider::Provider();
          v32 = *(unsigned int *)v35;
          if ( (unsigned int)v32 > 5 )
          {
            string[0] = (HSTRING)L"Failed when trying to find package by its installed location. Failure not caused by ERR"
                                  "OR_NOT_FOUND or E_NOT_SET";
            LODWORD(v78) = v34;
            v80 = (struct Appx::Packaging::BlockMap::AppxBlockMapReader *)L"packageStatics->GetByInstalledLocation";
            v82 = (struct Appx::Packaging::BlockMap::AppxBlockMapReader *)L"AppxBlockMapReader::Create";
            ppstm = (IStream *)L"AppxBlockMapReader.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v35,
              (unsigned int)&byte_18015A63F,
              v33,
              v36,
              (__int64)&ppstm,
              (__int64)&v82,
              (__int64)&v80,
              (__int64)&v78,
              (__int64)string);
          }
        }
        v82 = 0;
        *v90 = v14;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v32, EVENT_BLOCKMAP_READER_CREATE_STOP, v33, 1);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v37);
        operator delete(v19, v37);
LABEL_140:
        v10 = 0;
        goto LABEL_141;
      }
      v73[0] = 0;
      IsPackageFolded = Appx::Packaging::BlockMap::AppxBlockMapReader::IsPackageFolded(v74, v73);
      v22 = IsPackageFolded;
      if ( IsPackageFolded < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)IsPackageFolded,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
LABEL_137:
        operator delete(v19, v41);
LABEL_21:
        v10 = v22;
        goto LABEL_141;
      }
      if ( !v73[0] )
      {
        v82 = 0;
        *v90 = v14;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v39, EVENT_BLOCKMAP_READER_CREATE_STOP, v40, 1);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v42);
        operator delete(v19, v42);
        goto LABEL_140;
      }
      v86[0] = 0;
      v43 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, _QWORD *))(*(_QWORD *)v74 + 1032LL))(
              v74,
              v86);
      v22 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v43,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
        goto LABEL_137;
      }
      v76 = 0;
      v44 = v75;
      v45 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v75 + 256LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
      v46 = v45(v44, v86[0], &v76);
      v22 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA7,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v46,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
        goto LABEL_137;
      }
      v83 = 0;
      v47 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v76 + 56LL))(v76, &v83);
      v22 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v47,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
        goto LABEL_137;
      }
      v79 = 0;
      v88 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &pszFile,
        L"Windows.Internal.StateRepository.PackageLocation",
        0x31u,
        0x30u);
      v48 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(
              v88,
              &v79);
      v22 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v48,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
        goto LABEL_137;
      }
      v77 = 0;
      v49 = 0;
      if ( v83 )
      {
        while ( 1 )
        {
          v50 = v76;
          v51 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v76 + 48LL);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
          v22 = v51(v50, v49, &v77);
          if ( v22 < 0 )
            break;
          v73[0] = 0;
          v52 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)v77 + 288LL))(v77, v73);
          v22 = v52;
          if ( v52 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB6,
              (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
              (const char *)(unsigned int)v52,
              (int)pstmTemplate);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
            if ( v20 )
              operator delete(v20, v41);
            goto LABEL_137;
          }
          if ( v73[0] )
          {
            v78 = 0;
            v53 = v79;
            v54 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v79 + 96LL);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
            v55 = v54(v53, v77, &v78);
            v22 = v55;
            if ( v55 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBB,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v55,
                (int)pstmTemplate);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            string[0] = 0;
            v56 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v78 + 88LL))(v78, string);
            v22 = v56;
            if ( v56 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBE,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v56,
                (int)pstmTemplate);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
            *(_OWORD *)v84 = 0;
            v85 = 0;
            FullFilePathFromPackageInstalledLocation = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFullFilePathFromPackageInstalledLocation(
                                                         StringRawBuffer,
                                                         L"AppxSignature.p7x",
                                                         (struct Common::StringBuffer *)v84);
            v22 = FullFilePathFromPackageInstalledLocation;
            if ( FullFilePathFromPackageInstalledLocation < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC2,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)FullFilePathFromPackageInstalledLocation,
                (int)pstmTemplate);
              if ( v84[1] )
                operator delete(v84[1], v70);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            memset(&pszFile, 0, 20);
            v22 = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFullFilePathFromPackageInstalledLocation(
                    StringRawBuffer,
                    L"AppxBlockMap.xml",
                    (struct Common::StringBuffer *)&pszFile);
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC5,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v22,
                (int)pstmTemplate);
              if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
                operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v69);
              if ( v84[1] )
                operator delete(v84[1], v69);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            ppstm = 0;
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
            v59 = SHCreateStreamOnFileEx(*(LPCWSTR *)&pszFile.Reserved.Reserved2[8], 0, 0x80u, 0, 0, &ppstm);
            v22 = v59;
            if ( v59 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCE,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v59,
                (int)pstmTemplate);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
              if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
                operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v68);
              if ( v84[1] )
                operator delete(v84[1], v68);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            if ( a2 )
            {
              v60 = Appx::Packaging::BlockMap::AppxBlockMapReader::ValidateSignature(ppstm, v84[1]);
              v22 = v60;
              if ( v60 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD2,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                  (const char *)(unsigned int)v60,
                  (int)pstmTemplate);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
                if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
                  operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v65);
                if ( v84[1] )
                  operator delete(v84[1], v65);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
                Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
                if ( v20 )
                  operator delete(v20, v41);
                goto LABEL_137;
              }
            }
            v80 = 0;
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v80);
            v61 = Appx::Packaging::BlockMap::AppxBlockMapReader::CreateAppxBlockMapReaderFromStream(ppstm, &v80);
            v22 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD6,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v61,
                (int)pstmTemplate);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v80);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
              if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
                operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v67);
              if ( v84[1] )
                operator delete(v84[1], v67);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            v62 = Appx::Packaging::BlockMap::AppxBlockMapReader::AddFilesToMap(v14, v80);
            v22 = v62;
            if ( v62 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD9,
                (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
                (const char *)(unsigned int)v62,
                (int)pstmTemplate);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v80);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
              if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
                operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v66);
              if ( v84[1] )
                operator delete(v84[1], v66);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
              if ( v20 )
                operator delete(v20, v41);
              goto LABEL_137;
            }
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v80);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
            if ( *(_QWORD *)&pszFile.Reserved.Reserved2[8] )
              operator delete(*(void **)&pszFile.Reserved.Reserved2[8], v63);
            if ( v84[1] )
              operator delete(v84[1], v63);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
          }
          if ( ++v49 >= v83 )
            goto LABEL_83;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v22,
          (int)pstmTemplate);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
        if ( v20 )
          operator delete(v20, v41);
        goto LABEL_137;
      }
LABEL_83:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v79);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
      if ( v20 )
        operator delete(v20, v64);
      operator delete(v19, v64);
    }
    v82 = 0;
    *v90 = v14;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(v12, EVENT_BLOCKMAP_READER_CREATE_STOP, v13, 1);
    goto LABEL_140;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x60,
    (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
    (const char *)(unsigned int)v9,
    (int)pstmTemplate);
  return v10;
}

```

## disassembly

```asm
0x18005cd3c  mov     rax, rsp
0x18005cd3f  push    rbp
0x18005cd40  push    rsi
0x18005cd41  push    rdi
0x18005cd42  push    r12
0x18005cd44  push    r13
0x18005cd46  push    r14
0x18005cd48  push    r15
0x18005cd4a  lea     rbp, [rax-58h]
0x18005cd4e  sub     rsp, 120h
0x18005cd55  mov     [rbp+50h+var_88], 0FFFFFFFFFFFFFFFEh
0x18005cd5d  mov     [rax+18h], rbx
0x18005cd61  mov     rax, cs:__security_cookie
0x18005cd68  xor     rax, rsp
0x18005cd6b  mov     [rbp+50h+var_40], rax
0x18005cd6f  mov     r14, r9
0x18005cd72  mov     sil, r8b
0x18005cd75  mov     r12, rdx
0x18005cd78  mov     rdi, rcx
0x18005cd7b  mov     rax, [rbp+50h+arg_20]
0x18005cd82  mov     [rbp+50h+var_50], rax
0x18005cd86  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18005cd8d  jz      short loc_18005CDAA
0x18005cd8f  lea     rax, [rbp+50h+string]
0x18005cd93  mov     [rsp+150h+pstmTemplate], rax; int
0x18005cd98  mov     r9d, 1
0x18005cd9e  lea     rdx, EVENT_BLOCKMAP_READER_CREATE_START
0x18005cda5  call    McGenEventWrite_EventWriteTransfer
0x18005cdaa  test    r12, r12
0x18005cdad  jz      short loc_18005CDDD
0x18005cdaf  mov     rdx, r12; unsigned __int16 *
0x18005cdb2  mov     rcx, rdi; struct IStream *
0x18005cdb5  call    ?ValidateSignature@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEAUIStream@@PEBG@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::ValidateSignature(IStream *,ushort const *)
0x18005cdba  mov     ebx, eax
0x18005cdbc  test    eax, eax
0x18005cdbe  jns     short loc_18005CDDD
0x18005cdc0  mov     rcx, [rbp+58h]; this
0x18005cdc4  mov     r9d, eax; char *
0x18005cdc7  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005cdce  mov     edx, 60h ; '`'; void *
0x18005cdd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cdd8  jmp     loc_18005DBA6
0x18005cddd  mov     [rbp+50h+var_B8], 0
0x18005cde5  lea     rcx, [rbp+50h+var_B8]
0x18005cde9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005cdee  lea     rdx, [rbp+50h+var_B8]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x18005cdf2  mov     rcx, rdi; struct IStream *
0x18005cdf5  call    ?CreateAppxBlockMapReaderFromStream@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEAUIStream@@PEAPEAV1234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::CreateAppxBlockMapReaderFromStream(IStream *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x18005cdfa  mov     ebx, eax
0x18005cdfc  test    eax, eax
0x18005cdfe  jns     short loc_18005CE1D
0x18005ce00  mov     rcx, [rbp+58h]; this
0x18005ce04  mov     r9d, eax; char *
0x18005ce07  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005ce0e  mov     edx, 64h ; 'd'; void *
0x18005ce13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce18  jmp     loc_18005DB9D
0x18005ce1d  mov     r13, [rbp+50h+var_B8]
0x18005ce21  test    sil, sil
0x18005ce24  jz      loc_18005DB6A
0x18005ce2a  xor     esi, esi
0x18005ce2c  mov     [rbp+50h+var_C8], rsi
0x18005ce30  lea     rdx, [rbp+50h+var_C8]
0x18005ce34  test    r12, r12
0x18005ce37  jnz     short loc_18005CE6D
0x18005ce39  mov     rcx, r14; unsigned __int16 *
0x18005ce3c  call    ?SetInstalledLocationFromFolderPath@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEBGAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::SetInstalledLocationFromFolderPath(ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x18005ce41  mov     ebx, eax
0x18005ce43  test    eax, eax
0x18005ce45  jns     short loc_18005CEA3
0x18005ce47  mov     rcx, [rbp+58h]; this
0x18005ce4b  mov     r9d, eax; char *
0x18005ce4e  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005ce55  lea     edx, [rsi+6Ch]; void *
0x18005ce58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce5d  nop
0x18005ce5e  mov     rcx, [rbp+50h+var_C8]; void *
0x18005ce62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ce67  nop
0x18005ce68  jmp     loc_18005DB9D
0x18005ce6d  mov     rcx, r12
0x18005ce70  call    ?GetPackagePathFromSignatureFileFullPath@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEBGAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::GetPackagePathFromSignatureFileFullPath(ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x18005ce75  mov     ebx, eax
0x18005ce77  test    eax, eax
0x18005ce79  jns     short loc_18005CEA3
0x18005ce7b  mov     rcx, [rbp+58h]; this
0x18005ce7f  mov     r9d, eax; char *
0x18005ce82  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005ce89  mov     edx, 70h ; 'p'; void *
0x18005ce8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce93  nop
0x18005ce94  mov     rcx, [rbp+50h+var_C8]; void *
0x18005ce98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ce9d  nop
0x18005ce9e  jmp     loc_18005DB9D
0x18005cea3  xorps   xmm0, xmm0
0x18005cea6  movups  xmmword ptr [rbp+50h+pszFile], xmm0
0x18005ceaa  mov     [rbp+50h+var_70], esi
0x18005cead  mov     rbx, [rbp+50h+var_C8]
0x18005ceb1  mov     rdx, rbx; unsigned __int16 *
0x18005ceb4  lea     rcx, [rbp+50h+pszFile]; this
0x18005ceb8  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18005cebd  mov     edx, dword ptr [rbp+50h+pszFile]; unsigned __int64
0x18005cec0  mov     r9d, 4; unsigned __int64
0x18005cec6  mov     r8, cs:off_180114578; unsigned __int16 *
0x18005cecd  mov     r15, [rbp+50h+pszFile+8]
0x18005ced1  mov     rcx, r15; Buf2
0x18005ced4  call    ?StartsWith@String@Common@@SAHPEBG_K01@Z; Common::String::StartsWith(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x18005ced9  test    eax, eax
0x18005cedb  jz      loc_18005CF61
0x18005cee1  xorps   xmm0, xmm0
0x18005cee4  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x18005cee8  mov     [rbp+50h+var_98], esi
0x18005ceeb  lea     rdx, [r15+8]; unsigned __int16 *
0x18005ceef  lea     rcx, [rbp+50h+var_A8]; this
0x18005cef3  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18005cef8  mov     edi, eax
0x18005cefa  test    eax, eax
0x18005cefc  jns     short loc_18005CF42
0x18005cefe  mov     rcx, [rbp+58h]; this
0x18005cf02  mov     r9d, eax; char *
0x18005cf05  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005cf0c  mov     edx, 7Ah ; 'z'; void *
0x18005cf11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf16  mov     rcx, [rbp+50h+var_A8+8]; void *
0x18005cf1a  test    rcx, rcx
0x18005cf1d  jz      short loc_18005CF24
0x18005cf1f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cf24  test    r15, r15
0x18005cf27  jz      short loc_18005CF32
0x18005cf29  mov     rcx, r15; void *
0x18005cf2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cf31  nop
0x18005cf32  mov     rcx, rbx; void *
0x18005cf35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cf3a  nop
0x18005cf3b  mov     ebx, edi
0x18005cf3d  jmp     loc_18005DB9D
0x18005cf42  lea     rdx, [rbp+50h+var_A8]
0x18005cf46  lea     rcx, [rbp+50h+pszFile]
0x18005cf4a  call    ??4StringBuffer@Common@@QEAAAEAV01@$$QEAV01@@Z; Common::StringBuffer::operator=(Common::StringBuffer &&)
0x18005cf4f  mov     rcx, [rbp+50h+var_A8+8]; void *
0x18005cf53  test    rcx, rcx
0x18005cf56  jz      short loc_18005CF5D
0x18005cf58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cf5d  mov     r15, [rbp+50h+pszFile+8]
0x18005cf61  mov     [rsp+150h+var_F0], rsi
0x18005cf66  mov     [rsp+150h+var_F8], rsi
0x18005cf6b  mov     [rbp+50h+var_68], rsi
0x18005cf6f  mov     r9d, 28h ; '('; unsigned int
0x18005cf75  lea     r8d, [r9+1]; unsigned int
0x18005cf79  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18005cf80  lea     rcx, [rbp+50h+pszFile]; hstringHeader
0x18005cf84  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005cf89  mov     rdi, [rbp+50h+var_68]
0x18005cf8d  lea     rcx, [rsp+150h+var_F0]
0x18005cf92  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005cf97  lea     r8, [rsp+150h+var_F0]
0x18005cf9c  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18005cfa3  mov     rcx, rdi
0x18005cfa6  call    cs:__imp_RoGetActivationFactory
0x18005cfad  nop     dword ptr [rax+rax+00h]
0x18005cfb2  mov     edi, eax
0x18005cfb4  test    eax, eax
0x18005cfb6  jns     short loc_18005D000
0x18005cfb8  mov     rcx, [rbp+58h]; this
0x18005cfbc  mov     r9d, eax; char *
0x18005cfbf  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005cfc6  mov     edx, 81h; void *
0x18005cfcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cfd0  lea     rcx, [rsp+150h+var_F8]
0x18005cfd5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005cfda  lea     rcx, [rsp+150h+var_F0]
0x18005cfdf  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005cfe4  test    r15, r15
0x18005cfe7  jz      short loc_18005CFF2
0x18005cfe9  mov     rcx, r15; void *
0x18005cfec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cff1  nop
0x18005cff2  mov     rcx, rbx; void *
0x18005cff5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cffa  nop
0x18005cffb  jmp     loc_18005CF3B
0x18005d000  mov     [rbp+50h+string], r15
0x18005d004  lea     rdx, [rbp+50h+string]
0x18005d008  lea     rcx, [rbp+50h+pszFile]
0x18005d00c  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18005d011  mov     r14, [rax+18h]
0x18005d015  mov     [rbp+50h+var_68], rsi
0x18005d019  mov     rsi, [rsp+150h+var_F0]
0x18005d01e  mov     rax, [rsi]
0x18005d021  mov     rdi, [rax+230h]
0x18005d028  lea     rcx, [rsp+150h+var_F8]
0x18005d02d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d032  lea     r8, [rsp+150h+var_F8]
0x18005d037  mov     rdx, r14
0x18005d03a  mov     rcx, rsi
0x18005d03d  mov     rax, rdi
0x18005d040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d045  mov     edi, eax
0x18005d047  xor     esi, esi
0x18005d049  test    eax, eax
0x18005d04b  jns     loc_18005D130
0x18005d051  cmp     eax, 80070490h
0x18005d056  jz      short loc_18005D0D1
0x18005d058  call    ?Provider@AppxPackagingProvider@Packaging@Appx@@SAPEBU_tlgProvider_t@@XZ; Appx::Packaging::AppxPackagingProvider::Provider(void)
0x18005d05d  mov     ecx, [rax]
0x18005d05f  cmp     ecx, 5
0x18005d062  jbe     short loc_18005D0D1
0x18005d064  lea     rcx, aFailedWhenTryi; "Failed when trying to find package by i"...
0x18005d06b  mov     [rbp+50h+string], rcx
0x18005d06f  mov     dword ptr [rsp+150h+var_D8], edi
0x18005d073  lea     rcx, aPackagestatics; "packageStatics->GetByInstalledLocation"
0x18005d07a  mov     [rbp+50h+var_C8], rcx
0x18005d07e  lea     rcx, aAppxblockmapre; "AppxBlockMapReader::Create"
0x18005d085  mov     [rbp+50h+var_B8], rcx
0x18005d089  lea     rcx, aAppxblockmapre_0; "AppxBlockMapReader.cpp"
0x18005d090  mov     [rbp+50h+var_C0], rcx
0x18005d094  lea     rcx, [rbp+50h+string]
0x18005d098  mov     [rsp+40h], rcx
0x18005d09d  lea     rcx, [rsp+150h+var_D8]
0x18005d0a2  mov     [rsp+150h+var_118], rcx
0x18005d0a7  lea     rcx, [rbp+50h+var_C8]
0x18005d0ab  mov     [rsp+150h+var_120], rcx
0x18005d0b0  lea     rcx, [rbp+50h+var_B8]
0x18005d0b4  mov     [rsp+150h+ppstm], rcx
0x18005d0b9  lea     rcx, [rbp+50h+var_C0]
0x18005d0bd  mov     [rsp+150h+pstmTemplate], rcx
0x18005d0c2  lea     rdx, byte_18015A63F
0x18005d0c9  mov     rcx, rax
0x18005d0cc  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18005d0d1  mov     [rbp+50h+var_B8], rsi
0x18005d0d5  mov     rax, [rbp+50h+var_50]
0x18005d0d9  mov     [rax], r13
0x18005d0dc  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18005d0e3  jz      short loc_18005D100
0x18005d0e5  lea     rax, [rbp+50h+string]
0x18005d0e9  mov     [rsp+150h+pstmTemplate], rax
0x18005d0ee  mov     r9d, 1
0x18005d0f4  lea     rdx, EVENT_BLOCKMAP_READER_CREATE_STOP
0x18005d0fb  call    McGenEventWrite_EventWriteTransfer
0x18005d100  lea     rcx, [rsp+150h+var_F8]
0x18005d105  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d10a  lea     rcx, [rsp+150h+var_F0]
0x18005d10f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d114  test    r15, r15
0x18005d117  jz      short loc_18005D122
0x18005d119  mov     rcx, r15; void *
0x18005d11c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d121  nop
0x18005d122  mov     rcx, rbx; void *
0x18005d125  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d12a  nop
0x18005d12b  jmp     loc_18005DB9B
0x18005d130  mov     [rsp+150h+var_100], sil
0x18005d135  lea     rdx, [rsp+150h+var_100]; bool *
0x18005d13a  mov     rcx, [rsp+150h+var_F8]; struct Windows::Internal::StateRepository::IPackage *
0x18005d13f  call    ?IsPackageFolded@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEAUIPackage@StateRepository@Internal@Windows@@PEA_N@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::IsPackageFolded(Windows::Internal::StateRepository::IPackage *,bool *)
0x18005d144  mov     edi, eax
0x18005d146  test    eax, eax
0x18005d148  jns     short loc_18005D192
0x18005d14a  mov     rcx, [rbp+58h]; this
0x18005d14e  mov     r9d, eax; char *
0x18005d151  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005d158  mov     edx, 9Bh; void *
0x18005d15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d162  lea     rcx, [rsp+150h+var_F8]
0x18005d167  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d16c  lea     rcx, [rsp+150h+var_F0]
0x18005d171  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d176  test    r15, r15
0x18005d179  jz      short loc_18005D184
0x18005d17b  mov     rcx, r15; void *
0x18005d17e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d183  nop
0x18005d184  mov     rcx, rbx; void *
0x18005d187  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d18c  nop
0x18005d18d  jmp     loc_18005CF3B
0x18005d192  cmp     [rsp+150h+var_100], sil
0x18005d197  jnz     short loc_18005D1F8
0x18005d199  mov     [rbp+50h+var_B8], rsi
0x18005d19d  mov     rax, [rbp+50h+var_50]
0x18005d1a1  mov     [rax], r13
0x18005d1a4  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18005d1ab  jz      short loc_18005D1C8
0x18005d1ad  lea     rax, [rbp+50h+string]
0x18005d1b1  mov     [rsp+150h+pstmTemplate], rax
0x18005d1b6  mov     r9d, 1
0x18005d1bc  lea     rdx, EVENT_BLOCKMAP_READER_CREATE_STOP
0x18005d1c3  call    McGenEventWrite_EventWriteTransfer
0x18005d1c8  lea     rcx, [rsp+150h+var_F8]
0x18005d1cd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d1d2  lea     rcx, [rsp+150h+var_F0]
0x18005d1d7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005d1dc  test    r15, r15
0x18005d1df  jz      short loc_18005D1EA
0x18005d1e1  mov     rcx, r15; void *
0x18005d1e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005d1e9  nop
  ... truncated ...
```

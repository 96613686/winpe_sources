# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageHandler::DownloadImageAssetsForModernApplication(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PipelineApplicationData *)

- ea: `0x18019ce00`
- end: `0x18019d46e`
- name: `?DownloadImageAssetsForModernApplication@PlaceholderImageHandler@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAXPEAUPipelineApplicationData@2345@@Z`
- size: `1646`
- prototype: `void __fastcall(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageHandler *__hidden this, struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PipelineApplicationData *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019cb98`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18007ae80`
- `0x180087bd8`
- `0x18015cfa4`
- `0x180161204`
- `0x18017d9d0`
- `0x180199f64`
- `0x18019ce00`
- `0x18019d54c`
- `0x18019d714`
- `0x18019d77c`
- `0x1801f89a4`
- `0x180201e50`
- `0x18020c3ea`
- `0x18023ed84`
- `0x18023f0b0`
- `0x18023f240`
- `0x18023fcc0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019cf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019cffb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019cf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019cffb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019d3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019cfc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019cfc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d2ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019d332`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18019d1e9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18019d1fe`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18019d1e9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x18019d1fe`

## string_xrefs

- `0x18019ce69`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholderimagehandler.cpp`
- `0x18019cea3`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholderimagehandler.cpp`
- `0x18019cec3`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitializationbackgroundtask\lib\placeholderimagehandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageHandler::DownloadImageAssetsForModernApplication(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageHandler *this,
        struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PipelineApplicationData *a2)
{
  int v4; // eax
  int v5; // eax
  unsigned int v6; // r14d
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rdi
  __int64 (__fastcall *v13)(__int64 *, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  __int64 *v17; // rdi
  __int64 (__fastcall *v18)(__int64 *, HSTRING *); // rbx
  int v19; // eax
  PCWSTR v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rbx
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, HSTRING, _QWORD, HSTRING *); // rdi
  _QWORD *v41; // rax
  __int64 v42; // rax
  int v43; // eax
  int v44; // ebx
  PCWSTR v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // r8
  PCWSTR v48; // rax
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v51; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v52; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v54; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v55; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD Buf1[2]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v58; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v63; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v64[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v65[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v66[240]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v67[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v68; // [rsp+1C8h] [rbp+C8h]
  _BYTE v69[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v61 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)a2 + 17) + 136LL))(*((_QWORD *)a2 + 17), &v61);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\plac"
                    "eholderimagehandler.cpp",
      (const char *)(unsigned int)v4,
      v49);
  v54 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v61 + 56))(v61, &v54);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\plac"
                    "eholderimagehandler.cpp",
      (const char *)(unsigned int)v5,
      v49);
  v6 = 0;
  if ( v54 )
  {
    while ( 1 )
    {
      v51 = 0;
      v7 = *v61;
      v51 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v7 + 48))(v61, v6, &v51);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDD,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v8,
          v49);
      v59 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v51 + 48))(v51, &v59);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v9,
          v49);
      if ( v59 )
        goto LABEL_48;
      v52 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v51 + 56))(v51, &v52);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v10,
          v49);
      v53 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v51 + 64))(v51, &v53);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v11,
          v49);
      string = 0;
      v12 = v51;
      v13 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v51 + 72);
      WindowsDeleteString(0);
      string = 0;
      v14 = v13(v12, &string);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v14,
          v49);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v16 = -1;
      do
        ++v16;
      while ( StringRawBuffer[v16] );
      std::wstring::_Assign<unsigned short>((char *)a2 + 32, StringRawBuffer);
      v55 = 0;
      v17 = v51;
      v18 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v51 + 80);
      WindowsDeleteString(0);
      v55 = 0;
      v19 = v18(v17, &v55);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEF,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v19,
          v49);
      v20 = WindowsGetStringRawBuffer(v55, 0);
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      std::wstring::_Assign<unsigned short>((char *)a2 + 64, v20);
      Buf1[0] = v52;
      Buf1[1] = v53;
      if ( !memcmp_0(Buf1, &qword_1804284D0, 8u) )
        break;
      if ( !memcmp_0(Buf1, &qword_1804284C8, 8u) )
      {
        v50 = 1;
        goto LABEL_27;
      }
      if ( !memcmp_0(Buf1, &qword_1804284C0, 8u) )
      {
        v50 = 2;
        goto LABEL_27;
      }
      if ( !memcmp_0(Buf1, qword_1804284E0, 8u) )
      {
        v50 = 3;
        goto LABEL_27;
      }
      if ( !memcmp_0(Buf1, &qword_1804284D8, 8u) )
      {
        v50 = 4;
        goto LABEL_27;
      }
      v50 = 5;
LABEL_47:
      WindowsDeleteString(v55);
      v55 = 0;
      WindowsDeleteString(string);
      string = 0;
LABEL_48:
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v51);
      if ( ++v6 >= v54 )
        goto LABEL_49;
    }
    v50 = 0;
LABEL_27:
    v62 = 0;
    v22 = *v51;
    v62 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v22 + 96))(v51, &v62);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\pl"
                      "aceholderimagehandler.cpp",
        (const char *)(unsigned int)v23,
        v49);
    v60 = 0;
    WindowsDeleteString(0);
    v60 = 0;
    v24 = v62;
    v25 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v62);
    if ( v25 >= 0 )
      v25 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 64LL))(v24, &v60);
    if ( v25 >= 0 )
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
      if ( v50 == 5 )
      {
        v26 = std::operator<<<unsigned short>(v66, a2);
        v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, L"_");
        v29 = (_QWORD *)std::unordered_map<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes,unsigned short const *>::at(
                          v28,
                          &v50);
        v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, *v29);
        v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, L"_");
        v32 = std::basic_ostream<unsigned short>::operator<<(v31, v52);
        v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32);
        v34 = std::basic_ostream<unsigned short>::operator<<(v33, v53);
      }
      else
      {
        v35 = std::operator<<<unsigned short>(v66, a2);
        v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, L"_");
        v38 = (_QWORD *)std::unordered_map<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes,unsigned short const *>::at(
                          v37,
                          &v50);
        v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, *v38);
      }
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L".jpg");
      v58 = 0;
      v39 = *((_QWORD *)this + 4);
      v40 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, HSTRING *))(*(_QWORD *)v39 + 152LL);
      WindowsDeleteString(0);
      v58 = 0;
      v41 = (_QWORD *)std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                        v65,
                        v69);
      if ( v41[3] > 7u )
        v41 = (_QWORD *)*v41;
      v63 = v41;
      v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v67, &v63);
      v43 = v40(v39, v60, *(_QWORD *)(v42 + 24), &v58);
      v44 = v43;
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x112,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\"
                        "placeholderimagehandler.cpp",
          (const char *)(unsigned int)v43,
          v49);
      v68 = 0;
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v69);
      if ( v44 >= 0 )
      {
        v45 = WindowsGetStringRawBuffer(v58, 0);
        v46 = *(_QWORD *)std::map<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes,std::wstring>::_Try_emplace<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes const &,>(
                           (char *)a2 + 120,
                           v64,
                           &v50)
            + 40LL;
        v47 = -1;
        do
          ++v47;
        while ( v45[v47] );
        std::wstring::_Assign<unsigned short>(v46, v45);
        if ( (Microsoft_Windows_ShellCommon_StartLayoutPopulationEnableBits & 1) != 0 )
        {
          v48 = WindowsGetStringRawBuffer(v58, 0);
          McTemplateU0z_EventWriteTransfer(
            &Microsoft_Windows_StartLayoutPopulation_Provider_Context,
            StartLayoutBackgroundTask_AssetDownloaded,
            v48);
        }
      }
      WindowsDeleteString(v58);
      v58 = 0;
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v65);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitializationbackgroundtask\\lib\\pl"
                      "aceholderimagehandler.cpp",
        (const char *)(unsigned int)v25,
        v49);
    }
    WindowsDeleteString(v60);
    v60 = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v62);
    goto LABEL_47;
  }
LABEL_49:
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v61);
}

```

## disassembly

```asm
0x18019ce00  mov     [rsp-8+arg_10], rbx
0x18019ce05  push    rbp
0x18019ce06  push    rsi
0x18019ce07  push    rdi
0x18019ce08  push    r12
0x18019ce0a  push    r13
0x18019ce0c  push    r14
0x18019ce0e  push    r15
0x18019ce10  lea     rbp, [rsp-100h]
0x18019ce18  sub     rsp, 200h
0x18019ce1f  mov     rax, cs:__security_cookie
0x18019ce26  xor     rax, rsp
0x18019ce29  mov     [rbp+130h+var_40], rax
0x18019ce30  mov     r15, rdx
0x18019ce33  mov     r13, rcx
0x18019ce36  xor     r12d, r12d
0x18019ce39  mov     [rbp+130h+var_1B0], r12
0x18019ce3d  mov     rcx, [rdx+88h]
0x18019ce44  mov     rax, [rcx]
0x18019ce47  mov     [rbp+130h+var_1B0], r12
0x18019ce4b  lea     rdx, [rbp+130h+var_1B0]
0x18019ce4f  mov     rax, [rax+88h]
0x18019ce56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ce5b  mov     rcx, [rbp+138h]; this
0x18019ce62  test    eax, eax
0x18019ce64  jns     short loc_18019CE7B
0x18019ce66  mov     r9d, eax; char *
0x18019ce69  lea     r8, aShellcommonShe_208; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18019ce70  mov     edx, 0D5h; void *
0x18019ce75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019ce7b  mov     [rsp+230h+var_1E8], r12d
0x18019ce80  mov     rcx, [rbp+130h+var_1B0]
0x18019ce84  mov     rax, [rcx]
0x18019ce87  lea     rdx, [rsp+230h+var_1E8]
0x18019ce8c  mov     rax, [rax+38h]
0x18019ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ce95  mov     rcx, [rbp+138h]; this
0x18019ce9c  test    eax, eax
0x18019ce9e  jns     short loc_18019CEB5
0x18019cea0  mov     r9d, eax; char *
0x18019cea3  lea     r8, aShellcommonShe_208; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18019ceaa  mov     edx, 0D8h; void *
0x18019ceaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019ceb5  mov     r14d, r12d
0x18019ceb8  cmp     [rsp+230h+var_1E8], r12d
0x18019cebd  jbe     loc_18019D3C4
0x18019cec3  lea     rsi, aShellcommonShe_208; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18019ceca  mov     [rsp+230h+var_1F8], r12
0x18019cecf  mov     rcx, [rbp+130h+var_1B0]
0x18019ced3  mov     rax, [rcx]
0x18019ced6  mov     [rsp+230h+var_1F8], r12
0x18019cedb  lea     r8, [rsp+230h+var_1F8]
0x18019cee0  mov     edx, r14d
0x18019cee3  mov     rax, [rax+30h]
0x18019cee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ceec  mov     rcx, [rbp+138h]; this
0x18019cef3  test    eax, eax
0x18019cef5  js      loc_18019D45D
0x18019cefb  mov     [rsp+230h+var_1C0], r12d
0x18019cf00  mov     rcx, [rsp+230h+var_1F8]
0x18019cf05  mov     rax, [rcx]
0x18019cf08  lea     rdx, [rsp+230h+var_1C0]
0x18019cf0d  mov     rax, [rax+30h]
0x18019cf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf16  mov     rcx, [rbp+138h]; this
0x18019cf1d  test    eax, eax
0x18019cf1f  js      loc_18019D44C
0x18019cf25  cmp     [rsp+230h+var_1C0], r12d
0x18019cf2a  jnz     loc_18019D3AC
0x18019cf30  mov     [rsp+230h+var_1F0], r12d
0x18019cf35  mov     rcx, [rsp+230h+var_1F8]
0x18019cf3a  mov     rax, [rcx]
0x18019cf3d  lea     rdx, [rsp+230h+var_1F0]
0x18019cf42  mov     rax, [rax+38h]
0x18019cf46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf4b  mov     rcx, [rbp+138h]; this
0x18019cf52  test    eax, eax
0x18019cf54  js      loc_18019D43B
0x18019cf5a  mov     [rsp+230h+var_1EC], r12d
0x18019cf5f  mov     rcx, [rsp+230h+var_1F8]
0x18019cf64  mov     rax, [rcx]
0x18019cf67  lea     rdx, [rsp+230h+var_1EC]
0x18019cf6c  mov     rax, [rax+40h]
0x18019cf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cf75  mov     rcx, [rbp+138h]; this
0x18019cf7c  test    eax, eax
0x18019cf7e  js      loc_18019D42A
0x18019cf84  mov     [rsp+230h+string], r12
0x18019cf89  mov     rdi, [rsp+230h+var_1F8]
0x18019cf8e  mov     rax, [rdi]
0x18019cf91  mov     rbx, [rax+48h]
0x18019cf95  xor     ecx, ecx; string
0x18019cf97  call    cs:__imp_WindowsDeleteString
0x18019cf9d  mov     [rsp+230h+string], r12
0x18019cfa2  lea     rdx, [rsp+230h+string]
0x18019cfa7  mov     rcx, rdi
0x18019cfaa  mov     rax, rbx
0x18019cfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cfb2  mov     rcx, [rbp+138h]; this
0x18019cfb9  test    eax, eax
0x18019cfbb  js      loc_18019D419
0x18019cfc1  xor     edx, edx; length
0x18019cfc3  mov     rcx, [rsp+230h+string]; string
0x18019cfc8  call    cs:__imp_WindowsGetStringRawBuffer
0x18019cfce  or      r8, 0FFFFFFFFFFFFFFFFh
0x18019cfd2  inc     r8
0x18019cfd5  cmp     [rax+r8*2], r12w
0x18019cfda  jnz     short loc_18019CFD2
0x18019cfdc  lea     rcx, [r15+20h]
0x18019cfe0  mov     rdx, rax
0x18019cfe3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18019cfe8  mov     [rsp+230h+var_1E0], r12
0x18019cfed  mov     rdi, [rsp+230h+var_1F8]
0x18019cff2  mov     rax, [rdi]
0x18019cff5  mov     rbx, [rax+50h]
0x18019cff9  xor     ecx, ecx; string
0x18019cffb  call    cs:__imp_WindowsDeleteString
0x18019d001  mov     [rsp+230h+var_1E0], r12
0x18019d006  lea     rdx, [rsp+230h+var_1E0]
0x18019d00b  mov     rcx, rdi
0x18019d00e  mov     rax, rbx
0x18019d011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d016  mov     rcx, [rbp+138h]; this
0x18019d01d  test    eax, eax
0x18019d01f  js      loc_18019D408
0x18019d025  xor     edx, edx; length
0x18019d027  mov     rcx, [rsp+230h+var_1E0]; string
0x18019d02c  call    cs:__imp_WindowsGetStringRawBuffer
0x18019d032  or      r8, 0FFFFFFFFFFFFFFFFh
0x18019d036  inc     r8
0x18019d039  cmp     [rax+r8*2], r12w
0x18019d03e  jnz     short loc_18019D036
0x18019d040  lea     rcx, [r15+40h]
0x18019d044  mov     rdx, rax
0x18019d047  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18019d04c  mov     eax, [rsp+230h+var_1F0]
0x18019d050  mov     [rsp+230h+Buf1], eax
0x18019d054  mov     eax, [rsp+230h+var_1EC]
0x18019d058  mov     [rsp+230h+var_1CC], eax
0x18019d05c  mov     ebx, 8
0x18019d061  mov     r8d, ebx; Size
0x18019d064  lea     rdx, qword_1804284D0; Buf2
0x18019d06b  lea     rcx, [rsp+230h+Buf1]; Buf1
0x18019d070  call    memcmp_0
0x18019d075  test    eax, eax
0x18019d077  jnz     short loc_18019D083
0x18019d079  mov     [rsp+230h+var_200], r12d
0x18019d07e  jmp     loc_18019D10D
0x18019d083  mov     r8, rbx; Size
0x18019d086  lea     rdx, qword_1804284C8; Buf2
0x18019d08d  lea     rcx, [rsp+230h+Buf1]; Buf1
0x18019d092  call    memcmp_0
0x18019d097  test    eax, eax
0x18019d099  jnz     short loc_18019D0A5
0x18019d09b  mov     [rsp+230h+var_200], 1
0x18019d0a3  jmp     short loc_18019D10D
0x18019d0a5  mov     r8, rbx; Size
0x18019d0a8  lea     rdx, qword_1804284C0; Buf2
0x18019d0af  lea     rcx, [rsp+230h+Buf1]; Buf1
0x18019d0b4  call    memcmp_0
0x18019d0b9  test    eax, eax
0x18019d0bb  jnz     short loc_18019D0C7
0x18019d0bd  mov     [rsp+230h+var_200], 2
0x18019d0c5  jmp     short loc_18019D10D
0x18019d0c7  mov     r8, rbx; Size
0x18019d0ca  lea     rdx, qword_1804284E0; Buf2
0x18019d0d1  lea     rcx, [rsp+230h+Buf1]; Buf1
0x18019d0d6  call    memcmp_0
0x18019d0db  test    eax, eax
0x18019d0dd  jnz     short loc_18019D0E9
0x18019d0df  mov     [rsp+230h+var_200], 3
0x18019d0e7  jmp     short loc_18019D10D
0x18019d0e9  mov     r8, rbx; Size
0x18019d0ec  lea     rdx, qword_1804284D8; Buf2
0x18019d0f3  lea     rcx, [rsp+230h+Buf1]; Buf1
0x18019d0f8  call    memcmp_0
0x18019d0fd  test    eax, eax
0x18019d0ff  jnz     loc_18019D384
0x18019d105  mov     [rsp+230h+var_200], 4
0x18019d10d  mov     [rbp+130h+var_1A8], r12
0x18019d111  mov     rcx, [rsp+230h+var_1F8]
0x18019d116  mov     rax, [rcx]
0x18019d119  mov     [rbp+130h+var_1A8], r12
0x18019d11d  lea     rdx, [rbp+130h+var_1A8]
0x18019d121  mov     rax, [rax+60h]
0x18019d125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d12a  mov     rcx, [rbp+138h]; this
0x18019d131  test    eax, eax
0x18019d133  js      loc_18019D3F7
0x18019d139  mov     [rsp+230h+var_1B8], r12
0x18019d13e  xor     ecx, ecx; string
0x18019d140  call    cs:__imp_WindowsDeleteString
0x18019d146  mov     [rsp+230h+var_1B8], r12
0x18019d14b  mov     rbx, [rbp+130h+var_1A8]
0x18019d14f  mov     rcx, rbx
0x18019d152  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x18019d157  test    eax, eax
0x18019d159  js      short loc_18019D16F
0x18019d15b  mov     rax, [rbx]
0x18019d15e  lea     rdx, [rsp+230h+var_1B8]
0x18019d163  mov     rcx, rbx
0x18019d166  mov     rax, [rax+40h]
0x18019d16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d16f  mov     rcx, [rbp+138h]; this
0x18019d176  test    eax, eax
0x18019d178  jns     short loc_18019D18F
0x18019d17a  mov     r9d, eax; char *
0x18019d17d  mov     r8, rsi; unsigned int
0x18019d180  mov     edx, 100h; void *
0x18019d185  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18019d18a  jmp     loc_18019D369
0x18019d18f  lea     rcx, [rbp+130h+var_180]
0x18019d193  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18019d198  nop
0x18019d199  mov     rdx, r15
0x18019d19c  lea     rcx, [rbp+130h+var_170]
0x18019d1a0  cmp     [rsp+230h+var_200], 5
0x18019d1a5  jnz     short loc_18019D206
0x18019d1a7  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18019d1ac  mov     rcx, rax
0x18019d1af  lea     rdx, asc_1804284B8; "_"
0x18019d1b6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d1bb  mov     rbx, rax
0x18019d1be  lea     rdx, [rsp+230h+var_200]
0x18019d1c3  call    ?at@?$unordered_map@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEBGU?$hash@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@U?$equal_to@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@7@V?$allocator@U?$pair@$$CBW4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEBG@std@@@7@@std@@QEBAAEBQEBGAEBW4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Z; std::unordered_map<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes,ushort const *>::at(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes const &)
0x18019d1c8  mov     rdx, [rax]
0x18019d1cb  mov     rcx, rbx
0x18019d1ce  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d1d3  mov     rcx, rax
0x18019d1d6  lea     rdx, asc_1804284B8; "_"
0x18019d1dd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d1e2  mov     edx, [rsp+230h+var_1F0]
0x18019d1e6  mov     rcx, rax
0x18019d1e9  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x18019d1ef  mov     rcx, rax
0x18019d1f2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18019d1f7  mov     edx, [rsp+230h+var_1EC]
0x18019d1fb  mov     rcx, rax
0x18019d1fe  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x18019d204  jmp     short loc_18019D232
0x18019d206  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18019d20b  mov     rcx, rax
0x18019d20e  lea     rdx, asc_1804284B8; "_"
0x18019d215  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d21a  mov     rbx, rax
0x18019d21d  lea     rdx, [rsp+230h+var_200]
0x18019d222  call    ?at@?$unordered_map@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEBGU?$hash@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@U?$equal_to@W4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@7@V?$allocator@U?$pair@$$CBW4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@PEBG@std@@@7@@std@@QEBAAEBQEBGAEBW4PlaceholderImageSizes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@Z; std::unordered_map<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes,ushort const *>::at(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::PlaceholderImageSizes const &)
0x18019d227  mov     rdx, [rax]
0x18019d22a  mov     rcx, rbx
0x18019d22d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d232  lea     rdx, aJpg; ".jpg"
0x18019d239  mov     rcx, rax
0x18019d23c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18019d241  mov     [rsp+230h+var_1C8], r12
0x18019d246  mov     rbx, [r13+20h]
0x18019d24a  mov     rax, [rbx]
0x18019d24d  mov     rdi, [rax+98h]
0x18019d254  xor     ecx, ecx; string
0x18019d256  call    cs:__imp_WindowsDeleteString
0x18019d25c  mov     [rsp+230h+var_1C8], r12
0x18019d261  lea     rdx, [rbp+130h+var_60]
0x18019d268  lea     rcx, [rbp+130h+var_180]
0x18019d26c  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18019d271  nop
0x18019d272  cmp     qword ptr [rax+18h], 7
0x18019d277  jbe     short loc_18019D27C
0x18019d279  mov     rax, [rax]
0x18019d27c  mov     [rbp+130h+var_1A0], rax
0x18019d280  lea     rdx, [rbp+130h+var_1A0]
0x18019d284  lea     rcx, [rbp+130h+var_80]
0x18019d28b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18019d290  nop
0x18019d291  lea     r9, [rsp+230h+var_1C8]
0x18019d296  mov     r8, [rax+18h]
0x18019d29a  mov     rdx, [rsp+230h+var_1B8]
0x18019d29f  mov     rcx, rbx
0x18019d2a2  mov     rax, rdi
0x18019d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d2aa  mov     ebx, eax
0x18019d2ac  mov     rcx, [rbp+138h]; this
0x18019d2b3  test    eax, eax
0x18019d2b5  jns     short loc_18019D2C8
0x18019d2b7  mov     r9d, eax; char *
0x18019d2ba  mov     r8, rsi; unsigned int
0x18019d2bd  mov     edx, 112h; void *
0x18019d2c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18019d2c7  nop
0x18019d2c8  shr     ebx, 1Fh
0x18019d2cb  mov     [rbp+130h+var_68], r12
0x18019d2d2  lea     rcx, [rbp+130h+var_60]; void *
0x18019d2d9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18019d2de  xor     bl, 1
0x18019d2e1  jz      short loc_18019D34F
0x18019d2e3  xor     edx, edx; length
0x18019d2e5  mov     rcx, [rsp+230h+var_1C8]; string
0x18019d2ea  call    cs:__imp_WindowsGetStringRawBuffer
0x18019d2f0  mov     rbx, rax
0x18019d2f3  lea     rcx, [r15+78h]
0x18019d2f7  lea     r8, [rsp+230h+var_200]
0x18019d2fc  lea     rdx, [rbp+130h+var_198]
  ... truncated ...
```

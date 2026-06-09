# StartLayoutCmdlet::AppendTileAsset(Windows::Foundation::IUriRuntimeClass *,IXmlWriter *)

- ea: `0x180259340`
- end: `0x180259941`
- name: `?AppendTileAsset@StartLayoutCmdlet@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAUIXmlWriter@@@Z`
- size: `1537`
- prototype: `__int64 __fastcall(StartLayoutCmdlet *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, struct IXmlWriter *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1802590b8`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18003153c`
- `0x18004ffc0`
- `0x1800756e4`
- `0x18007ae80`
- `0x1800e5fe8`
- `0x1801087f4`
- `0x18018e5b0`
- `0x18019a0e8`
- `0x1801ecc24`
- `0x180201e50`
- `0x18021aa5c`
- `0x180259340`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1802593f6`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1802593f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025968e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802596b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025986d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025989e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802598c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802598ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025968e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802596b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259838`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025986d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025989e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802598c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802598ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802593ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025940f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802597c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802593ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025940f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802597c5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18025959e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18025959e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802594cf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802594cf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180259486`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180259486`

## string_xrefs

- `0x1802593b1`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259497`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x1802594e5`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x1802595b4`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259656`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x18025981f`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x1802598d7`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259571`: `Windows.Storage.PathIO`
- `0x180259713`: `RelativeFilePath`
- `0x180259628`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StartLayoutCmdlet::AppendTileAsset(
        StartLayoutCmdlet *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        struct IXmlWriter *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v6; // eax
  int LastError; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v9; // rbx
  PCWSTR v10; // rax
  PCWSTR *v11; // rax
  PCWSTR *v12; // rcx
  const char *v13; // r9
  const WCHAR *v14; // r9
  HRESULT v15; // eax
  HRESULT v16; // edi
  __int64 v17; // rbx
  int ActivationFactory; // eax
  __int64 v19; // r8
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, HSTRING *); // rdi
  int v24; // eax
  __int64 v25; // rdx
  PCWSTR *v26; // rdx
  HRESULT (__stdcall *WriteString)(IXmlWriter *, LPCWSTR); // rbx
  PCWSTR v28; // rax
  int cchValue; // [rsp+20h] [rbp-E0h]
  int cchValuea; // [rsp+20h] [rbp-E0h]
  HSTRING v32; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v33; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR pszMore[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v41; // [rsp+88h] [rbp-78h]
  _BYTE v42[32]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-38h]
  WCHAR pszPathOut[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPathIn[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 128LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  LastError = v6;
  if ( v6 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = -1;
    if ( FindStringOrdinal(0x400000u, StringRawBuffer, -1, L"ms-appdata:///local/", -1, 1) )
    {
      LastError = 0;
      goto LABEL_53;
    }
    v10 = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v42, v10);
    std::wstring::substr(v42, pszMore, 20, -1);
    v11 = *(PCWSTR **)std::wstring::end(pszMore, &v38);
    v12 = pszMore;
    if ( v41 > 7 )
      v12 = (PCWSTR *)pszMore[0];
    while ( v12 != v11 )
    {
      if ( *(_WORD *)v12 == 47 )
        *(_WORD *)v12 = 92;
      v12 = (PCWSTR *)((char *)v12 + 2);
    }
    if ( !(unsigned int)SHExpandEnvironmentStringsW(
                          L"%USERPROFILE%\\AppData\\Local\\Packages\\Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe\\LocalState\\",
                          pszPathIn,
                          260) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xEB,
                    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet"
                                  "\\startlayoutcmdletimpl.cpp",
                    v13);
LABEL_52:
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(pszMore);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v42);
      goto LABEL_53;
    }
    v14 = (const WCHAR *)pszMore;
    if ( v41 > 7 )
      v14 = pszMore[0];
    v15 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, v14);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
        (const char *)(unsigned int)v15,
        cchValuea);
LABEL_18:
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(pszMore);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v42);
      LastError = v16;
      goto LABEL_53;
    }
    v32 = 0;
    v34[0] = 0;
    do
      ++v9;
    while ( pszPathOut[v9] );
    LastError = ULongLongToUInt(v9, v34);
    if ( LastError < 0
      || (LastError = Microsoft::WRL::Wrappers::HString::Set(
                        (Microsoft::WRL::Wrappers::HString *)&v32,
                        pszPathOut,
                        v34[0]),
          LastError < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
        (const char *)(unsigned int)LastError,
        cchValuea);
    }
    else
    {
      v35 = 0;
      v44 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Storage.PathIO",
        0x17u,
        0x16u);
      v17 = v44;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      ActivationFactory = RoGetActivationFactory(v17, &GUID_0f2f3758_8ec7_4381_922b_8f6c07d288f3, &v35);
      LastError = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        *(_QWORD *)v34 = 0;
        v38 = v32;
        ___call_and_wait_for_completion_UIPathIOStatics_Storage_Windows__PEAUHSTRING____PEAPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_3___ZPEAU4__wil__YA_A_PPEAUIPathIOStatics_Storage_Windows__P8123_EAAJPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_3__Z__QEAPEAU4__Z(
          &v39,
          v35,
          v19,
          &v38);
        v20 = v39;
        v39 = 0;
        v38 = 0;
        *(_QWORD *)v34 = v20;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        v36 = 0;
        v44 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.Cryptography.CryptographicBuffer",
          0x32u,
          0x31u);
        v21 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::ICryptographicBufferStatics>>(
                v44,
                &v36);
        v16 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startl"
                          "ayoutcmdletimpl.cpp",
            (const char *)(unsigned int)v21,
            cchValuea);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          WindowsDeleteString(v32);
          v32 = 0;
          goto LABEL_18;
        }
        v33 = 0;
        v22 = v36;
        v23 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v36 + 112LL);
        WindowsDeleteString(0);
        v33 = 0;
        v24 = v23(v22, v20, &v33);
        LastError = v24;
        if ( v24 >= 0 )
        {
          v24 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a3->lpVtbl->WriteStartElement)(
                  a3,
                  0,
                  L"SecondaryTileAsset",
                  0);
          LastError = v24;
          if ( v24 >= 0 )
          {
            v24 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a3->lpVtbl->WriteStartElement)(
                    a3,
                    0,
                    L"RelativeFilePath",
                    0);
            LastError = v24;
            if ( v24 >= 0 )
            {
              v26 = pszMore;
              if ( v41 > 7 )
                v26 = (PCWSTR *)pszMore[0];
              v24 = ((__int64 (__fastcall *)(struct IXmlWriter *, PCWSTR *))a3->lpVtbl->WriteCData)(a3, v26);
              LastError = v24;
              if ( v24 >= 0 )
              {
                v24 = ((__int64 (__fastcall *)(struct IXmlWriter *))a3->lpVtbl->WriteEndElement)(a3);
                LastError = v24;
                if ( v24 >= 0 )
                {
                  v24 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a3->lpVtbl->WriteStartElement)(
                          a3,
                          0,
                          L"Base64EncodedImage",
                          0);
                  LastError = v24;
                  if ( v24 >= 0 )
                  {
                    WriteString = a3->lpVtbl->WriteString;
                    v28 = WindowsGetStringRawBuffer(v33, 0);
                    v24 = ((__int64 (__fastcall *)(struct IXmlWriter *, PCWSTR))WriteString)(a3, v28);
                    LastError = v24;
                    if ( v24 >= 0 )
                    {
                      v24 = ((__int64 (__fastcall *)(struct IXmlWriter *))a3->lpVtbl->WriteEndElement)(a3);
                      LastError = v24;
                      if ( v24 >= 0 )
                      {
                        v24 = ((__int64 (__fastcall *)(struct IXmlWriter *))a3->lpVtbl->WriteEndElement)(a3);
                        LastError = v24;
                        if ( v24 >= 0 )
                        {
                          WindowsDeleteString(v33);
                          v33 = 0;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                          WindowsDeleteString(v32);
                          v32 = 0;
                          std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(pszMore);
                          std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v42);
                          WindowsDeleteString(string);
                          return 0;
                        }
                        v25 = 268;
                      }
                      else
                      {
                        v25 = 266;
                      }
                    }
                    else
                    {
                      v25 = 265;
                    }
                  }
                  else
                  {
                    v25 = 264;
                  }
                }
                else
                {
                  v25 = 262;
                }
              }
              else
              {
                v25 = 261;
              }
            }
            else
            {
              v25 = 260;
            }
          }
          else
          {
            v25 = 258;
          }
        }
        else
        {
          v25 = 254;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlay"
                        "outcmdletimpl.cpp",
          (const char *)(unsigned int)v24,
          cchValuea);
        WindowsDeleteString(v33);
        v33 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlay"
                        "outcmdletimpl.cpp",
          (const char *)(unsigned int)ActivationFactory,
          cchValuea);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    }
    WindowsDeleteString(v32);
    v32 = 0;
    goto LABEL_52;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD7,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
    (const char *)(unsigned int)v6,
    cchValue);
LABEL_53:
  WindowsDeleteString(string);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180259340  mov     [rsp-8+arg_0], rbx
0x180259345  push    rbp
0x180259346  push    rsi
0x180259347  push    rdi
0x180259348  push    r14
0x18025934a  push    r15
0x18025934c  lea     rbp, [rsp-400h]
0x180259354  sub     rsp, 500h
0x18025935b  mov     rax, cs:__security_cookie
0x180259362  xor     rax, rsp
0x180259365  mov     [rbp+420h+var_30], rax
0x18025936c  mov     r14, r8
0x18025936f  mov     rdi, rdx
0x180259372  xor     r15d, r15d
0x180259375  mov     [rsp+520h+string], r15
0x18025937a  mov     rax, [rdx]
0x18025937d  mov     rbx, [rax+80h]
0x180259384  xor     ecx, ecx; string
0x180259386  call    cs:__imp_WindowsDeleteString
0x18025938c  mov     [rsp+520h+string], r15
0x180259391  lea     rdx, [rsp+520h+string]
0x180259396  mov     rcx, rdi
0x180259399  mov     rax, rbx
0x18025939c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802593a1  mov     ebx, eax
0x1802593a3  test    eax, eax
0x1802593a5  jns     short loc_1802593C7
0x1802593a7  mov     rcx, [rbp+428h]; this
0x1802593ae  mov     r9d, eax; char *
0x1802593b1  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802593b8  mov     edx, 0D7h; void *
0x1802593bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802593c2  jmp     loc_18025990E
0x1802593c7  xor     edx, edx; length
0x1802593c9  mov     rcx, [rsp+520h+string]; string
0x1802593ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1802593d4  mov     [rsp+520h+bIgnoreCase], 1; bIgnoreCase
0x1802593dc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802593e0  mov     [rsp+520h+cchValue], ebx; cchValue
0x1802593e4  lea     r9, StringValue; "ms-appdata:///local/"
0x1802593eb  mov     r8d, ebx; cchSource
0x1802593ee  mov     rdx, rax; lpStringSource
0x1802593f1  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x1802593f6  call    cs:__imp_FindStringOrdinal
0x1802593fc  test    eax, eax
0x1802593fe  jz      short loc_180259408
0x180259400  mov     ebx, r15d
0x180259403  jmp     loc_18025990E
0x180259408  xor     edx, edx; length
0x18025940a  mov     rcx, [rsp+520h+string]; string
0x18025940f  call    cs:__imp_WindowsGetStringRawBuffer
0x180259415  mov     rdx, rax
0x180259418  lea     rcx, [rbp+420h+var_490]
0x18025941c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180259421  nop
0x180259422  mov     r9, rbx
0x180259425  mov     r8d, 14h
0x18025942b  lea     rdx, [rsp+520h+pszMore]
0x180259430  lea     rcx, [rbp+420h+var_490]
0x180259434  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180259439  nop
0x18025943a  lea     rdx, [rsp+520h+var_4C0]
0x18025943f  lea     rcx, [rsp+520h+pszMore]
0x180259444  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180259449  mov     rax, [rax]
0x18025944c  lea     rcx, [rsp+520h+pszMore]
0x180259451  cmp     [rbp+420h+var_498], 7
0x180259456  cmova   rcx, [rsp+520h+pszMore]
0x18025945c  jmp     short loc_18025946D
0x18025945e  cmp     word ptr [rcx], 2Fh ; '/'
0x180259462  jnz     short loc_180259469
0x180259464  mov     word ptr [rcx], 5Ch ; '\'
0x180259469  add     rcx, 2
0x18025946d  cmp     rcx, rax
0x180259470  jnz     short loc_18025945E
0x180259472  mov     r8d, 104h
0x180259478  lea     rdx, [rbp+420h+pszPathIn]
0x18025947f  lea     rcx, aUserprofileApp_1; "%USERPROFILE%\\AppData\\Local\\Packages"...
0x180259486  call    cs:__imp_SHExpandEnvironmentStringsW
0x18025948c  test    eax, eax
0x18025948e  jnz     short loc_1802594AF
0x180259490  mov     rcx, [rbp+428h]; this
0x180259497  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025949e  mov     edx, 0EBh; void *
0x1802594a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802594a8  mov     ebx, eax
0x1802594aa  jmp     loc_1802598F9
0x1802594af  lea     r9, [rsp+520h+pszMore]
0x1802594b4  cmp     [rbp+420h+var_498], 7
0x1802594b9  cmova   r9, [rsp+520h+pszMore]; pszMore
0x1802594bf  lea     r8, [rbp+420h+pszPathIn]; pszPathIn
0x1802594c6  mov     edx, 104h; cchPathOut
0x1802594cb  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1802594cf  call    cs:__imp_PathCchCombine
0x1802594d5  mov     edi, eax
0x1802594d7  test    eax, eax
0x1802594d9  jns     short loc_180259512
0x1802594db  mov     rcx, [rbp+428h]; this
0x1802594e2  mov     r9d, eax; char *
0x1802594e5  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802594ec  mov     edx, 0EEh; void *
0x1802594f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802594f6  nop
0x1802594f7  lea     rcx, [rsp+520h+pszMore]; void *
0x1802594fc  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180259501  nop
0x180259502  lea     rcx, [rbp+420h+var_490]; void *
0x180259506  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18025950b  mov     ebx, edi
0x18025950d  jmp     loc_18025990E
0x180259512  mov     [rsp+520h+var_4F0], r15
0x180259517  mov     [rsp+520h+var_4E0], r15d
0x18025951c  lea     rax, [rbp+420h+pszPathOut]
0x180259520  inc     rbx
0x180259523  cmp     [rax+rbx*2], r15w
0x180259528  jnz     short loc_180259520
0x18025952a  lea     rdx, [rsp+520h+var_4E0]; unsigned int *
0x18025952f  mov     rcx, rbx; unsigned __int64
0x180259532  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180259537  mov     ebx, eax
0x180259539  test    eax, eax
0x18025953b  js      loc_1802598CD
0x180259541  mov     r8d, [rsp+520h+var_4E0]; unsigned int
0x180259546  lea     rdx, [rbp+420h+pszPathOut]; unsigned __int16 *
0x18025954a  lea     rcx, [rsp+520h+var_4F0]; this
0x18025954f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180259554  mov     ebx, eax
0x180259556  test    eax, eax
0x180259558  js      loc_1802598CD
0x18025955e  mov     [rsp+520h+var_4D8], r15
0x180259563  mov     [rbp+420h+var_458], r15
0x180259567  mov     r9d, 16h; unsigned int
0x18025956d  lea     r8d, [r9+1]; unsigned int
0x180259571  lea     rdx, ?RuntimeClass_Windows_Storage_PathIO@@3QBGB; "Windows.Storage.PathIO"
0x180259578  lea     rcx, [rbp+420h+hstringHeader]; hstringHeader
0x18025957c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180259581  mov     rbx, [rbp+420h+var_458]
0x180259585  lea     rcx, [rsp+520h+var_4D8]
0x18025958a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025958f  lea     r8, [rsp+520h+var_4D8]
0x180259594  lea     rdx, _GUID_0f2f3758_8ec7_4381_922b_8f6c07d288f3
0x18025959b  mov     rcx, rbx
0x18025959e  call    cs:__imp_RoGetActivationFactory
0x1802595a4  mov     ebx, eax
0x1802595a6  test    eax, eax
0x1802595a8  jns     short loc_1802595CA
0x1802595aa  mov     rcx, [rbp+428h]; this
0x1802595b1  mov     r9d, eax; char *
0x1802595b4  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802595bb  mov     edx, 0F5h; void *
0x1802595c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802595c5  jmp     loc_180259859
0x1802595ca  mov     qword ptr [rsp+520h+var_4E0], r15
0x1802595cf  mov     rax, [rsp+520h+var_4F0]
0x1802595d4  mov     [rsp+520h+var_4C0], rax
0x1802595d9  lea     r9, [rsp+520h+var_4C0]
0x1802595de  mov     rdx, [rsp+520h+var_4D8]
0x1802595e3  lea     rcx, [rsp+520h+var_4B8]
0x1802595e8  call    ??$call_and_wait_for_completion@UIPathIOStatics@Storage@Windows@@PEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@3@$$ZPEAU4@@wil@@YA?A_PPEAUIPathIOStatics@Storage@Windows@@P8123@EAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@3@@Z$$QEAPEAU4@@Z
0x1802595ed  mov     rbx, [rsp+520h+var_4B8]
0x1802595f2  mov     [rsp+520h+var_4B8], r15
0x1802595f7  mov     [rsp+520h+var_4C0], r15
0x1802595fc  mov     qword ptr [rsp+520h+var_4E0], rbx
0x180259601  lea     rcx, [rsp+520h+var_4C0]
0x180259606  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025960b  lea     rcx, [rsp+520h+var_4B8]
0x180259610  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259615  mov     [rsp+520h+var_4D0], r15
0x18025961a  mov     [rbp+420h+var_458], r15
0x18025961e  mov     r9d, 31h ; '1'; unsigned int
0x180259624  lea     r8d, [r9+1]; unsigned int
0x180259628  lea     rdx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x18025962f  lea     rcx, [rbp+420h+hstringHeader]; hstringHeader
0x180259633  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180259638  lea     rdx, [rsp+520h+var_4D0]
0x18025963d  mov     rcx, [rbp+420h+var_458]
0x180259641  call    ??$GetActivationFactory@V?$ComPtr@UICryptographicBufferStatics@Cryptography@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICryptographicBufferStatics@Cryptography@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::ICryptographicBufferStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::ICryptographicBufferStatics>>)
0x180259646  mov     edi, eax
0x180259648  test    eax, eax
0x18025964a  jns     short loc_18025969E
0x18025964c  mov     rcx, [rbp+428h]; this
0x180259653  mov     r9d, eax; char *
0x180259656  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025965d  mov     edx, 0FBh; void *
0x180259662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259667  nop
0x180259668  lea     rcx, [rsp+520h+var_4D0]
0x18025966d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259672  nop
0x180259673  lea     rcx, [rsp+520h+var_4E0]
0x180259678  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025967d  nop
0x18025967e  lea     rcx, [rsp+520h+var_4D8]
0x180259683  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259688  nop
0x180259689  mov     rcx, [rsp+520h+var_4F0]; string
0x18025968e  call    cs:__imp_WindowsDeleteString
0x180259694  mov     [rsp+520h+var_4F0], r15
0x180259699  jmp     loc_1802594F7
0x18025969e  mov     [rsp+520h+var_4E8], r15
0x1802596a3  mov     rsi, [rsp+520h+var_4D0]
0x1802596a8  mov     rax, [rsi]
0x1802596ab  mov     rdi, [rax+70h]
0x1802596af  xor     ecx, ecx; string
0x1802596b1  call    cs:__imp_WindowsDeleteString
0x1802596b7  mov     [rsp+520h+var_4E8], r15
0x1802596bc  lea     r8, [rsp+520h+var_4E8]
0x1802596c1  mov     rdx, rbx
0x1802596c4  mov     rcx, rsi
0x1802596c7  mov     rax, rdi
0x1802596ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802596cf  mov     ebx, eax
0x1802596d1  test    eax, eax
0x1802596d3  jns     short loc_1802596DF
0x1802596d5  mov     edx, 0FEh
0x1802596da  jmp     loc_18025981C
0x1802596df  mov     rax, [r14]
0x1802596e2  xor     r9d, r9d
0x1802596e5  lea     r8, aSecondarytilea_0; "SecondaryTileAsset"
0x1802596ec  xor     edx, edx
0x1802596ee  mov     rcx, r14
0x1802596f1  mov     rax, [rax+0D8h]
0x1802596f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802596fd  mov     ebx, eax
0x1802596ff  test    eax, eax
0x180259701  jns     short loc_18025970D
0x180259703  mov     edx, 102h
0x180259708  jmp     loc_18025981C
0x18025970d  mov     rax, [r14]
0x180259710  xor     r9d, r9d
0x180259713  lea     r8, aRelativefilepa; "RelativeFilePath"
0x18025971a  xor     edx, edx
0x18025971c  mov     rcx, r14
0x18025971f  mov     rax, [rax+0D8h]
0x180259726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025972b  mov     ebx, eax
0x18025972d  test    eax, eax
0x18025972f  jns     short loc_18025973B
0x180259731  mov     edx, 104h
0x180259736  jmp     loc_18025981C
0x18025973b  mov     rax, [r14]
0x18025973e  lea     rdx, [rsp+520h+pszMore]
0x180259743  cmp     [rbp+420h+var_498], 7
0x180259748  cmova   rdx, [rsp+520h+pszMore]
0x18025974e  mov     rcx, r14
0x180259751  mov     rax, [rax+40h]
0x180259755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025975a  mov     ebx, eax
0x18025975c  test    eax, eax
0x18025975e  jns     short loc_18025976A
0x180259760  mov     edx, 105h
0x180259765  jmp     loc_18025981C
0x18025976a  mov     rax, [r14]
0x18025976d  mov     rcx, r14
0x180259770  mov     rax, [rax+78h]
0x180259774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259779  mov     ebx, eax
0x18025977b  test    eax, eax
0x18025977d  jns     short loc_180259789
0x18025977f  mov     edx, 106h
0x180259784  jmp     loc_18025981C
0x180259789  mov     rax, [r14]
0x18025978c  xor     r9d, r9d
0x18025978f  lea     r8, aBase64encodedi; "Base64EncodedImage"
0x180259796  xor     edx, edx
0x180259798  mov     rcx, r14
0x18025979b  mov     rax, [rax+0D8h]
0x1802597a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802597a7  mov     ebx, eax
0x1802597a9  test    eax, eax
0x1802597ab  jns     short loc_1802597B4
0x1802597ad  mov     edx, 108h
0x1802597b2  jmp     short loc_18025981C
0x1802597b4  mov     rax, [r14]
0x1802597b7  mov     rbx, [rax+0E0h]
0x1802597be  xor     edx, edx; length
0x1802597c0  mov     rcx, [rsp+520h+var_4E8]; string
0x1802597c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1802597cb  mov     rdx, rax
0x1802597ce  mov     rcx, r14
0x1802597d1  mov     rax, rbx
0x1802597d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802597d9  mov     ebx, eax
0x1802597db  test    eax, eax
0x1802597dd  jns     short loc_1802597E6
0x1802597df  mov     edx, 109h
0x1802597e4  jmp     short loc_18025981C
0x1802597e6  mov     rax, [r14]
0x1802597e9  mov     rcx, r14
0x1802597ec  mov     rax, [rax+78h]
0x1802597f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802597f5  mov     ebx, eax
0x1802597f7  test    eax, eax
0x1802597f9  jns     short loc_180259802
0x1802597fb  mov     edx, 10Ah
0x180259800  jmp     short loc_18025981C
0x180259802  mov     rax, [r14]
0x180259805  mov     rcx, r14
0x180259808  mov     rax, [rax+78h]
0x18025980c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

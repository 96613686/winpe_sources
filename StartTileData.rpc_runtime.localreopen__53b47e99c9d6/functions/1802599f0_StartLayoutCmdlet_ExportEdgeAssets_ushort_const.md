# StartLayoutCmdlet::ExportEdgeAssets(ushort const *)

- ea: `0x1802599f0`
- end: `0x18025a242`
- name: `?ExportEdgeAssets@StartLayoutCmdlet@@UEAAJPEBG@Z`
- size: `2130`
- prototype: `__int64 __fastcall(StartLayoutCmdlet *__hidden this, LPCWSTR pszFile)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18002dde0`
- `0x180073930`
- `0x18017ea00`
- `0x180180858`
- `0x180181710`
- `0x180239ed8`
- `0x1802590b8`
- `0x1802599f0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259c57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a0ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259c57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180259f71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a0ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025a1e7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180259a37`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180259a37`
- `XmlLite!CreateXmlWriter` at `0x180259a98`
- `XmlLite!CreateXmlWriter` at `0x180259a98`

## string_xrefs

- `0x180259a4e`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259aaf`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259b0a`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259b68`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259bcd`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259c40`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259ce8`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259dad`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259e54`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259f1d`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x180259fdb`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x18025a0bb`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`
- `0x18025a156`: `shellcommon\shell\tiles\curatedtilecollections\powershellmodule\startlayoutcmdlet\startlayoutcmdletimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall StartLayoutCmdlet::ExportEdgeAssets(StartLayoutCmdlet *this, LPCWSTR pszFile)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  unsigned int i; // esi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  HSTRING v29; // rdi
  __int64 (__fastcall *v30)(HSTRING, struct Windows::UI::StartScreen::ISecondaryTileVisualElements **); // rbx
  int v31; // eax
  __int64 v32; // rcx
  int appended; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rcx
  int pstmTemplate; // [rsp+20h] [rbp-68h]
  HSTRING string; // [rsp+30h] [rbp-58h] BYREF
  __int64 v42; // [rsp+38h] [rbp-50h] BYREF
  IStream *ppstm; // [rsp+40h] [rbp-48h] BYREF
  __int64 v44; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v45[8]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v46; // [rsp+58h] [rbp-30h] BYREF
  struct Windows::UI::StartScreen::ISecondaryTileVisualElements *v47; // [rsp+60h] [rbp-28h] BYREF
  HSTRING v48; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v50; // [rsp+A0h] [rbp+18h] BYREF
  void *ppvObject; // [rsp+A8h] [rbp+20h] BYREF

  ppstm = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  v4 = SHCreateStreamOnFileEx(pszFile, 0x1001u, 0, 0, 0, &ppstm);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
      (const char *)(unsigned int)v4,
      pstmTemplate);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
    return v5;
  }
  ppvObject = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
  v7 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
      (const char *)(unsigned int)v7,
      pstmTemplate);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
    return v8;
  }
  try
  {
    v9 = (*(__int64 (**)(void))(*(_QWORD *)ppvObject + 24LL))();
    v10 = v9;
    if ( v9 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                ppvObject,
                0,
                L"SecondaryTileAssets",
                0);
        v15 = v14;
        if ( v14 >= 0 )
        {
          wil::GetActivationFactory<Windows::UI::StartScreen::ISecondaryTileStatics>(v45);
          wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(
            v45,
            &v44);
          string = 0;
          v16 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
          v18 = v16;
          if ( v16 >= 0 )
          {
            v48 = string;
            ___CallAndWaitForCompletion_UISecondaryTileStaticsPrivate_StartScreen_UI_Internal_Windows__PEAUHSTRING____PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVSecondaryTile_StartScreen_UI_Windows___Collections_Foundation_Windows___Foundation_5___ZPEAU6__wil__YA_A_PPEAUISecondaryTileStaticsPrivate_StartScreen_UI_Internal_Windows__P812345_EAAJPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAU__IVectorView_PEAVSecondaryTile_StartScreen_UI_Windows___Collections_Foundation_Windows___Foundation_5__Z__QEAPEAU6__Z(
              &v42,
              v44,
              v17,
              &v48);
            v50 = 0;
            v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 56LL))(v42, &v50);
            v20 = v19;
            if ( v19 >= 0 )
            {
              for ( i = 0; i < v50; ++i )
              {
                v46 = 0;
                v23 = v42;
                v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 48LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                v25 = v24(v23, i, &v46);
                v20 = v25;
                if ( v25 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA6,
                    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet"
                                  "\\startlayoutcmdletimpl.cpp",
                    (const char *)(unsigned int)v25,
                    pstmTemplate);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                  v26 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                  }
                  goto LABEL_43;
                }
                v48 = 0;
                v27 = Microsoft::WRL::ComPtr<Windows::UI::StartScreen::ISecondaryTile>::As<Windows::UI::StartScreen::ISecondaryTile2>(
                        &v46,
                        &v48);
                v20 = v27;
                if ( v27 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA9,
                    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet"
                                  "\\startlayoutcmdletimpl.cpp",
                    (const char *)(unsigned int)v27,
                    pstmTemplate);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                  v28 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                  }
                  goto LABEL_43;
                }
                v47 = 0;
                v29 = v48;
                v30 = *(__int64 (__fastcall **)(HSTRING, struct Windows::UI::StartScreen::ISecondaryTileVisualElements **))(*(_QWORD *)v48 + 64LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                v31 = v30(v29, &v47);
                v20 = v31;
                if ( v31 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xAC,
                    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet"
                                  "\\startlayoutcmdletimpl.cpp",
                    (const char *)(unsigned int)v31,
                    pstmTemplate);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                  v32 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  }
                  goto LABEL_43;
                }
                appended = StartLayoutCmdlet::AppendAllAssetsForTile(this, v47, (struct IXmlWriter *)ppvObject);
                v20 = appended;
                if ( appended < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xAF,
                    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet"
                                  "\\startlayoutcmdletimpl.cpp",
                    (const char *)(unsigned int)appended,
                    pstmTemplate);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                  v34 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                  }
                  goto LABEL_43;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              }
              v35 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
              v20 = v35;
              if ( v35 >= 0 )
              {
                v37 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                v20 = v37;
                if ( v37 >= 0 )
                {
                  v39 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                  WindowsDeleteString(string);
                  string = 0;
                  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
                  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v45);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB5,
                  (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\"
                                "startlayoutcmdletimpl.cpp",
                  (const char *)(unsigned int)v37,
                  pstmTemplate);
                v38 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB3,
                  (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\"
                                "startlayoutcmdletimpl.cpp",
                  (const char *)(unsigned int)v35,
                  pstmTemplate);
                v36 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA1,
                (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\st"
                              "artlayoutcmdletimpl.cpp",
                (const char *)(unsigned int)v19,
                pstmTemplate);
              v21 = v42;
              if ( v42 )
              {
                v42 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
            }
LABEL_43:
            WindowsDeleteString(string);
            string = 0;
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
            result = v20;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9D,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\star"
                            "tlayoutcmdletimpl.cpp",
              (const char *)(unsigned int)v16,
              pstmTemplate);
            WindowsDeleteString(string);
            string = 0;
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v44);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
            result = v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x96,
            (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startl"
                          "ayoutcmdletimpl.cpp",
            (const char *)(unsigned int)v14,
            pstmTemplate);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
          result = v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x93,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlay"
                        "outcmdletimpl.cpp",
          (const char *)(unsigned int)v12,
          pstmTemplate);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayoutcmdlet\\startlayoutcmdletimpl.cpp",
        (const char *)(unsigned int)v9,
        pstmTemplate);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
      result = v10;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB8,
                           (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\powershellmodule\\startlayou"
                                         "tcmdlet\\startlayoutcmdletimpl.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1802599f0  mov     rax, rsp
0x1802599f3  mov     [rax+8], rbx
0x1802599f7  mov     [rax+10h], rsi
0x1802599fb  push    rdi
0x1802599fc  push    r14
0x1802599fe  push    r15
0x180259a00  sub     rsp, 70h
0x180259a04  mov     rbx, rdx
0x180259a07  mov     r14, rcx
0x180259a0a  xor     r15d, r15d
0x180259a0d  mov     [rax-48h], r15
0x180259a11  lea     rcx, [rax-48h]
0x180259a15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259a1a  lea     rax, [rsp+88h+var_48]
0x180259a1f  mov     [rsp+88h+ppstm], rax; ppstm
0x180259a24  mov     [rsp+88h+pstmTemplate], r15; int
0x180259a29  xor     r9d, r9d; fCreate
0x180259a2c  xor     r8d, r8d; dwAttributes
0x180259a2f  mov     edx, 1001h; grfMode
0x180259a34  mov     rcx, rbx; pszFile
0x180259a37  call    cs:__imp_SHCreateStreamOnFileEx
0x180259a3d  mov     ebx, eax
0x180259a3f  test    eax, eax
0x180259a41  jns     short loc_180259A71
0x180259a43  mov     rcx, [rsp+88h]; this
0x180259a4b  mov     r9d, eax; char *
0x180259a4e  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259a55  mov     edx, 8Eh; void *
0x180259a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259a5f  nop
0x180259a60  lea     rcx, [rsp+88h+var_48]
0x180259a65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259a6a  mov     eax, ebx
0x180259a6c  jmp     loc_18025A22B
0x180259a71  mov     [rsp+88h+ppvObject], r15
0x180259a79  lea     rcx, [rsp+88h+ppvObject]
0x180259a81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259a86  xor     r8d, r8d; pMalloc
0x180259a89  lea     rdx, [rsp+88h+ppvObject]; ppvObject
0x180259a91  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180259a98  call    cs:__imp_CreateXmlWriter
0x180259a9e  mov     ebx, eax
0x180259aa0  test    eax, eax
0x180259aa2  jns     short loc_180259AE0
0x180259aa4  mov     rcx, [rsp+88h]; this
0x180259aac  mov     r9d, eax; char *
0x180259aaf  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259ab6  mov     edx, 91h; void *
0x180259abb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259ac0  nop
0x180259ac1  lea     rcx, [rsp+88h+ppvObject]
0x180259ac9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259ace  nop
0x180259acf  lea     rcx, [rsp+88h+var_48]
0x180259ad4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259ad9  mov     eax, ebx
0x180259adb  jmp     loc_18025A22B
0x180259ae0  mov     rcx, [rsp+88h+ppvObject]
0x180259ae8  mov     rax, [rcx]
0x180259aeb  mov     rdx, [rsp+88h+var_48]
0x180259af0  mov     rax, [rax+18h]
0x180259af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259af9  mov     ebx, eax
0x180259afb  test    eax, eax
0x180259afd  jns     short loc_180259B3B
0x180259aff  mov     rcx, [rsp+88h]; this
0x180259b07  mov     r9d, eax; char *
0x180259b0a  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259b11  mov     edx, 92h; void *
0x180259b16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259b1b  nop
0x180259b1c  lea     rcx, [rsp+88h+ppvObject]
0x180259b24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259b29  nop
0x180259b2a  lea     rcx, [rsp+88h+var_48]
0x180259b2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259b34  mov     eax, ebx
0x180259b36  jmp     loc_18025A22B
0x180259b3b  mov     rcx, [rsp+88h+ppvObject]
0x180259b43  mov     rax, [rcx]
0x180259b46  mov     edx, 1
0x180259b4b  mov     r8d, edx
0x180259b4e  mov     rax, [rax+28h]
0x180259b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259b57  mov     ebx, eax
0x180259b59  test    eax, eax
0x180259b5b  jns     short loc_180259B99
0x180259b5d  mov     rcx, [rsp+88h]; this
0x180259b65  mov     r9d, eax; char *
0x180259b68  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259b6f  mov     edx, 93h; void *
0x180259b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259b79  nop
0x180259b7a  lea     rcx, [rsp+88h+ppvObject]
0x180259b82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259b87  nop
0x180259b88  lea     rcx, [rsp+88h+var_48]
0x180259b8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259b92  mov     eax, ebx
0x180259b94  jmp     loc_18025A22B
0x180259b99  mov     rcx, [rsp+88h+ppvObject]
0x180259ba1  mov     rax, [rcx]
0x180259ba4  xor     r9d, r9d
0x180259ba7  lea     r8, aSecondarytilea; "SecondaryTileAssets"
0x180259bae  xor     edx, edx
0x180259bb0  mov     rax, [rax+0D8h]
0x180259bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259bbc  mov     ebx, eax
0x180259bbe  test    eax, eax
0x180259bc0  jns     short loc_180259BFE
0x180259bc2  mov     rcx, [rsp+88h]; this
0x180259bca  mov     r9d, eax; char *
0x180259bcd  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259bd4  mov     edx, 96h; void *
0x180259bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259bde  nop
0x180259bdf  lea     rcx, [rsp+88h+ppvObject]
0x180259be7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259bec  nop
0x180259bed  lea     rcx, [rsp+88h+var_48]
0x180259bf2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259bf7  mov     eax, ebx
0x180259bf9  jmp     loc_18025A22B
0x180259bfe  lea     rcx, [rsp+88h+var_38]
0x180259c03  call    ??$GetActivationFactory@UISecondaryTileStatics@StartScreen@UI@Windows@@@wil@@YA?AV?$com_ptr_t@UISecondaryTileStatics@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::UI::StartScreen::ISecondaryTileStatics>(ushort const *)
0x180259c08  nop
0x180259c09  lea     rdx, [rsp+88h+var_40]
0x180259c0e  lea     rcx, [rsp+88h+var_38]
0x180259c13  call    ??$query@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@@?$com_ptr_t@UISecondaryTileStatics@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(void)
0x180259c18  nop
0x180259c19  mov     [rsp+88h+string], r15
0x180259c1e  lea     rdx, off_1803F4E58; "Microsoft.MicrosoftEdge.Stable_8wekyb3d"...
0x180259c25  lea     rcx, [rsp+88h+string]; string
0x180259c2a  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180259c2f  mov     ebx, eax
0x180259c31  test    eax, eax
0x180259c33  jns     short loc_180259C97
0x180259c35  mov     rcx, [rsp+88h]; this
0x180259c3d  mov     r9d, eax; char *
0x180259c40  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259c47  mov     edx, 9Dh; void *
0x180259c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259c51  nop
0x180259c52  mov     rcx, [rsp+88h+string]; string
0x180259c57  call    cs:__imp_WindowsDeleteString
0x180259c5d  mov     [rsp+88h+string], r15
0x180259c62  lea     rcx, [rsp+88h+var_40]; void *
0x180259c67  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259c6c  nop
0x180259c6d  lea     rcx, [rsp+88h+var_38]; void *
0x180259c72  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259c77  nop
0x180259c78  lea     rcx, [rsp+88h+ppvObject]
0x180259c80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259c85  nop
0x180259c86  lea     rcx, [rsp+88h+var_48]
0x180259c8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259c90  mov     eax, ebx
0x180259c92  jmp     loc_18025A22B
0x180259c97  mov     rax, [rsp+88h+string]
0x180259c9c  mov     [rsp+88h+var_20], rax
0x180259ca1  lea     r9, [rsp+88h+var_20]
0x180259ca6  mov     rdx, [rsp+88h+var_40]
0x180259cab  lea     rcx, [rsp+88h+var_50]
0x180259cb0  call    ??$CallAndWaitForCompletion@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@PEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@5@$$ZPEAU6@@wil@@YA?A_PPEAUISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@P812345@EAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@5@@Z$$QEAPEAU6@@Z
0x180259cb5  nop
0x180259cb6  mov     [rsp+88h+arg_10], r15d
0x180259cbe  mov     rcx, [rsp+88h+var_50]
0x180259cc3  mov     rax, [rcx]
0x180259cc6  lea     rdx, [rsp+88h+arg_10]
0x180259cce  mov     rax, [rax+38h]
0x180259cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259cd7  mov     ebx, eax
0x180259cd9  test    eax, eax
0x180259cdb  jns     short loc_180259D5B
0x180259cdd  mov     rcx, [rsp+88h]; this
0x180259ce5  mov     r9d, eax; char *
0x180259ce8  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259cef  mov     edx, 0A1h; void *
0x180259cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259cf9  nop
0x180259cfa  mov     rcx, [rsp+88h+var_50]
0x180259cff  test    rcx, rcx
0x180259d02  jz      short loc_180259D16
0x180259d04  mov     [rsp+88h+var_50], r15
0x180259d09  mov     rax, [rcx]
0x180259d0c  mov     rax, [rax+10h]
0x180259d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259d15  nop
0x180259d16  mov     rcx, [rsp+88h+string]; string
0x180259d1b  call    cs:__imp_WindowsDeleteString
0x180259d21  mov     [rsp+88h+string], r15
0x180259d26  lea     rcx, [rsp+88h+var_40]; void *
0x180259d2b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259d30  nop
0x180259d31  lea     rcx, [rsp+88h+var_38]; void *
0x180259d36  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259d3b  nop
0x180259d3c  lea     rcx, [rsp+88h+ppvObject]
0x180259d44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259d49  nop
0x180259d4a  lea     rcx, [rsp+88h+var_48]
0x180259d4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259d54  mov     eax, ebx
0x180259d56  jmp     loc_18025A22B
0x180259d5b  mov     esi, r15d
0x180259d5e  cmp     esi, [rsp+88h+arg_10]
0x180259d65  jnb     loc_18025A096
0x180259d6b  mov     [rsp+88h+var_30], r15
0x180259d70  mov     rdi, [rsp+88h+var_50]
0x180259d75  mov     rax, [rdi]
0x180259d78  mov     rbx, [rax+30h]
0x180259d7c  lea     rcx, [rsp+88h+var_30]
0x180259d81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259d86  lea     r8, [rsp+88h+var_30]
0x180259d8b  mov     edx, esi
0x180259d8d  mov     rcx, rdi
0x180259d90  mov     rax, rbx
0x180259d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259d98  mov     ebx, eax
0x180259d9a  test    eax, eax
0x180259d9c  jns     loc_180259E2B
0x180259da2  mov     rcx, [rsp+88h]; this
0x180259daa  mov     r9d, eax; char *
0x180259dad  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259db4  mov     edx, 0A6h; void *
0x180259db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259dbe  nop
0x180259dbf  lea     rcx, [rsp+88h+var_30]
0x180259dc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259dc9  nop
0x180259dca  mov     rcx, [rsp+88h+var_50]
0x180259dcf  test    rcx, rcx
0x180259dd2  jz      short loc_180259DE6
0x180259dd4  mov     [rsp+88h+var_50], r15
0x180259dd9  mov     rax, [rcx]
0x180259ddc  mov     rax, [rax+10h]
0x180259de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259de5  nop
0x180259de6  mov     rcx, [rsp+88h+string]; string
0x180259deb  call    cs:__imp_WindowsDeleteString
0x180259df1  mov     [rsp+88h+string], r15
0x180259df6  lea     rcx, [rsp+88h+var_40]; void *
0x180259dfb  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259e00  nop
0x180259e01  lea     rcx, [rsp+88h+var_38]; void *
0x180259e06  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259e0b  nop
0x180259e0c  lea     rcx, [rsp+88h+ppvObject]
0x180259e14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259e19  nop
0x180259e1a  lea     rcx, [rsp+88h+var_48]
0x180259e1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259e24  mov     eax, ebx
0x180259e26  jmp     loc_18025A22B
0x180259e2b  mov     [rsp+88h+var_20], r15
0x180259e30  lea     rdx, [rsp+88h+var_20]
0x180259e35  lea     rcx, [rsp+88h+var_30]
0x180259e3a  call    ??$As@UISecondaryTile2@StartScreen@UI@Windows@@@?$ComPtr@UISecondaryTile@StartScreen@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISecondaryTile2@StartScreen@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::StartScreen::ISecondaryTile>::As<Windows::UI::StartScreen::ISecondaryTile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::ISecondaryTile2>>)
0x180259e3f  mov     ebx, eax
0x180259e41  test    eax, eax
0x180259e43  jns     loc_180259EDD
0x180259e49  mov     rcx, [rsp+88h]; this
0x180259e51  mov     r9d, eax; char *
0x180259e54  lea     r8, aShellcommonShe_80; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180259e5b  mov     edx, 0A9h; void *
0x180259e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180259e65  nop
0x180259e66  lea     rcx, [rsp+88h+var_20]
0x180259e6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259e70  nop
0x180259e71  lea     rcx, [rsp+88h+var_30]
0x180259e76  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259e7b  nop
0x180259e7c  mov     rcx, [rsp+88h+var_50]
0x180259e81  test    rcx, rcx
0x180259e84  jz      short loc_180259E98
0x180259e86  mov     [rsp+88h+var_50], r15
0x180259e8b  mov     rax, [rcx]
0x180259e8e  mov     rax, [rax+10h]
0x180259e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180259e97  nop
0x180259e98  mov     rcx, [rsp+88h+string]; string
0x180259e9d  call    cs:__imp_WindowsDeleteString
0x180259ea3  mov     [rsp+88h+string], r15
0x180259ea8  lea     rcx, [rsp+88h+var_40]; void *
0x180259ead  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259eb2  nop
0x180259eb3  lea     rcx, [rsp+88h+var_38]; void *
0x180259eb8  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180259ebd  nop
0x180259ebe  lea     rcx, [rsp+88h+ppvObject]
0x180259ec6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259ecb  nop
0x180259ecc  lea     rcx, [rsp+88h+var_48]
0x180259ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180259ed6  mov     eax, ebx
0x180259ed8  jmp     loc_18025A22B
0x180259edd  mov     [rsp+88h+var_28], r15
0x180259ee2  mov     rdi, [rsp+88h+var_20]
  ... truncated ...
```

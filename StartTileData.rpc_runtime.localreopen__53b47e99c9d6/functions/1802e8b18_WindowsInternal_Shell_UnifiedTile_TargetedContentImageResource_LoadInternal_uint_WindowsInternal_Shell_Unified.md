# WindowsInternal::Shell::UnifiedTile::TargetedContentImageResource::LoadInternal(uint,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast *,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme *,HSTRING__ * *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x1802e8b18`
- end: `0x1802e8f4d`
- name: `?LoadInternal@TargetedContentImageResource@UnifiedTile@Shell@WindowsInternal@@AEBAJIW4TileImageResourceContrast@234@W4TileImageResourceTheme@234@PEAW45234@PEAW46234@PEAPEAUHSTRING__@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `1077`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1802e6e5c`
- `0x1802e7914`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180035518`
- `0x18003640c`
- `0x1800421ac`
- `0x180073930`
- `0x1802e8b18`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8cd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8cd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8cfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802e8f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802e8d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802e8d0d`

## string_xrefs

- `0x1802e8ba7`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x1802e8d3f`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x1802e8e05`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::TargetedContentImageResource::LoadInternal(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        HSTRING string,
        __int64 a6,
        HSTRING *a7,
        __int64 a8)
{
  HSTRING *v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rcx
  const char *v12; // r9
  HSTRING *v13; // rcx
  __int64 result; // rax
  __int64 v15; // rdi
  unsigned __int8 (__fastcall *v16)(__int64, const struct _GUID *, GUID *, __int64 *); // rbx
  unsigned int v17; // edx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *, _QWORD, _QWORD); // rbx
  HSTRING *v20; // rbx
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rcx
  HSTRING *v24; // rcx
  int StreamFromFile; // eax
  unsigned int v26; // ebx
  __int64 v27; // rcx
  HSTRING *v28; // rcx
  HSTRING v29; // rax
  HSTRING v30; // rcx
  __int64 v31; // rcx
  HSTRING *v32; // rcx
  enum DEVICE_SCALE_FACTOR v33; // [rsp+20h] [rbp-88h]
  __int64 v34; // [rsp+60h] [rbp-48h] BYREF
  HSTRING v35[8]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  HSTRING v37; // [rsp+B0h] [rbp+8h] BYREF
  ShellMRTHelper::Common *v38; // [rsp+B8h] [rbp+10h]
  int v39; // [rsp+C0h] [rbp+18h]

  v39 = a3;
  LODWORD(v38) = a2;
  if ( string )
    *(_DWORD *)string = 2;
  v9 = a7;
  if ( a7 )
    *a7 = 0;
  v10 = a8;
  if ( a8 )
    *(_QWORD *)a8 = 0;
  v11 = *(_QWORD *)(a1 + 96);
  try
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
    if ( !a7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)0x8000FFFFLL,
        v33);
      v13 = a7;
      if ( a7 )
      {
        a7 = 0;
        (*((void (__fastcall **)(HSTRING *, HSTRING))*v13 + 2))(v13, *v13);
      }
      return 2147549183LL;
    }
    DataStoreCache::DataItemIdentifier::DataItemIdentifier(
      (DataStoreCache::DataItemIdentifier *)&v37,
      *(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **)(a1 + 88));
    (*((void (__fastcall **)(HSTRING *, __int64 *, HSTRING))*a7 + 5))(a7, &a8, v37);
    v34 = 0;
    string = 0;
    v15 = a8;
    v16 = *(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64 *))(*(_QWORD *)a8 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    if ( v16(v15, &c_MRTTransformerId, &GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a, &v34) )
    {
      v18 = v34;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *, _QWORD, _QWORD))(*(_QWORD *)v34 + 72LL);
      v33 = ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent((ShellMRTHelper::Common *)(unsigned int)v38, v17);
      v20 = (HSTRING *)v19(v18, v35, *(_QWORD *)(a1 + 80), *(unsigned int *)(a1 + 72));
      WindowsDeleteString(string);
      string = 0;
      string = *v20;
      *v20 = 0;
      WindowsDeleteString(v35[0]);
LABEL_20:
      if ( v10
        && (StreamFromFile = anonymous_namespace_::LoadStreamFromFile(*(_QWORD *)(a1 + 104), string, v10),
            v26 = StreamFromFile,
            StreamFromFile < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x391,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
          (const char *)(unsigned int)StreamFromFile,
          v33);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v27 = a8;
        if ( a8 )
        {
          a8 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        WindowsDeleteString(v37);
        v37 = 0;
        v28 = a7;
        if ( a7 )
        {
          a7 = 0;
          (*((void (__fastcall **)(HSTRING *))*v28 + 2))(v28);
        }
        return v26;
      }
      else
      {
        if ( v9 )
        {
          v29 = string;
          v30 = 0;
          string = 0;
          *v9 = v29;
        }
        else
        {
          v30 = string;
        }
        WindowsDeleteString(v30);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v31 = a8;
        if ( a8 )
        {
          a8 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        WindowsDeleteString(v37);
        v37 = 0;
        v32 = a7;
        if ( a7 )
        {
          a7 = 0;
          (*((void (__fastcall **)(HSTRING *))*v32 + 2))(v32);
        }
        return 0;
      }
    }
    v35[0] = (HSTRING)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 80), 0);
    v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
    v22 = v21;
    if ( v21 >= 0 )
      goto LABEL_20;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
      (const char *)(unsigned int)v21,
      v33);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v23 = a8;
    if ( a8 )
    {
      a8 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    WindowsDeleteString(v37);
    v37 = 0;
    v24 = a7;
    if ( a7 )
    {
      a7 = 0;
      (*((void (__fastcall **)(HSTRING *))*v24 + 2))(v24);
    }
    result = v22;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x399,
                           (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1802e8b18  mov     [rsp+arg_10], r8d
0x1802e8b1d  mov     dword ptr [rsp+arg_8], edx
0x1802e8b21  push    rbx
0x1802e8b22  push    rsi
0x1802e8b23  push    rdi
0x1802e8b24  push    r12
0x1802e8b26  push    r13
0x1802e8b28  push    r14
0x1802e8b2a  push    r15
0x1802e8b2c  sub     rsp, 70h
0x1802e8b30  mov     r13d, r9d
0x1802e8b33  mov     r15, rcx
0x1802e8b36  mov     r12, [rsp+0A8h+string]
0x1802e8b3e  xor     ebx, ebx
0x1802e8b40  test    r12, r12
0x1802e8b43  jz      short loc_1802E8B4D
0x1802e8b45  mov     dword ptr [r12], 2
0x1802e8b4d  mov     rsi, [rsp+0A8h+arg_30]
0x1802e8b55  test    rsi, rsi
0x1802e8b58  jz      short loc_1802E8B5D
0x1802e8b5a  mov     [rsi], rbx
0x1802e8b5d  mov     r14, [rsp+0A8h+arg_38]
0x1802e8b65  test    r14, r14
0x1802e8b68  jz      short loc_1802E8B6D
0x1802e8b6a  mov     [r14], rbx
0x1802e8b6d  mov     rcx, [rcx+60h]
0x1802e8b71  mov     rax, [rcx]
0x1802e8b74  lea     r8, TileData
0x1802e8b7b  lea     rdx, [rsp+0A8h+arg_30]
0x1802e8b83  mov     rax, [rax+18h]
0x1802e8b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8b8c  nop
0x1802e8b8d  cmp     [rsp+0A8h+arg_30], rbx
0x1802e8b95  jnz     short loc_1802E8BE2
0x1802e8b97  mov     rcx, [rsp+0A8h]; this
0x1802e8b9f  mov     edi, 8000FFFFh
0x1802e8ba4  mov     r9d, edi; char *
0x1802e8ba7  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802e8bae  mov     edx, 375h; void *
0x1802e8bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802e8bb8  nop
0x1802e8bb9  mov     rcx, [rsp+0A8h+arg_30]
0x1802e8bc1  test    rcx, rcx
0x1802e8bc4  jz      short loc_1802E8BDB
0x1802e8bc6  mov     [rsp+0A8h+arg_30], rbx
0x1802e8bce  mov     rdx, [rcx]
0x1802e8bd1  mov     rax, [rdx+10h]
0x1802e8bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8bda  nop
0x1802e8bdb  mov     eax, edi
0x1802e8bdd  jmp     loc_1802E8F3C
0x1802e8be2  mov     rdx, [r15+58h]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *
0x1802e8be6  lea     rcx, [rsp+0A8h+arg_0]; this
0x1802e8bee  call    ??0DataItemIdentifier@DataStoreCache@@QEAA@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::DataItemIdentifier::DataItemIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x1802e8bf3  nop
0x1802e8bf4  mov     rcx, [rsp+0A8h+arg_30]
0x1802e8bfc  mov     rax, [rcx]
0x1802e8bff  mov     r8, [rsp+0A8h+arg_0]
0x1802e8c07  lea     rdx, [rsp+0A8h+arg_38]
0x1802e8c0f  mov     rax, [rax+28h]
0x1802e8c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8c18  nop
0x1802e8c19  mov     [rsp+0A8h+var_48], rbx
0x1802e8c1e  mov     [rsp+0A8h+string], rbx
0x1802e8c26  mov     rdi, [rsp+0A8h+arg_38]
0x1802e8c2e  mov     rax, [rdi]
0x1802e8c31  mov     rbx, [rax+30h]
0x1802e8c35  lea     rcx, [rsp+0A8h+var_48]
0x1802e8c3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e8c3f  lea     r9, [rsp+0A8h+var_48]
0x1802e8c44  lea     r8, _GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a
0x1802e8c4b  lea     rdx, c_MRTTransformerId
0x1802e8c52  mov     rcx, rdi
0x1802e8c55  mov     rax, rbx
0x1802e8c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8c5d  xor     edi, edi
0x1802e8c5f  test    al, al
0x1802e8c61  jz      loc_1802E8D07
0x1802e8c67  mov     rdi, [rsp+0A8h+var_48]
0x1802e8c6c  mov     rax, [rdi]
0x1802e8c6f  mov     rbx, [rax+48h]
0x1802e8c73  mov     ecx, dword ptr [rsp+0A8h+arg_8]; this
0x1802e8c7a  call    ?DeviceScaleFactorFromScalePercent@Common@ShellMRTHelper@@YA?AW4DEVICE_SCALE_FACTOR@@I@Z; ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent(uint)
0x1802e8c7f  mov     [rsp+0A8h+var_58], 0
0x1802e8c88  mov     rdx, [rsp+0A8h+arg_28]
0x1802e8c90  mov     [rsp+0A8h+var_60], rdx
0x1802e8c95  mov     [rsp+0A8h+var_68], r12
0x1802e8c9a  mov     [rsp+0A8h+var_70], 0
0x1802e8ca2  mov     [rsp+0A8h+var_78], r13d
0x1802e8ca7  mov     ecx, [rsp+0A8h+arg_10]
0x1802e8cae  mov     [rsp+0A8h+var_80], ecx
0x1802e8cb2  mov     [rsp+0A8h+var_88], eax; int
0x1802e8cb6  mov     r9d, [r15+48h]
0x1802e8cba  mov     r8, [r15+50h]
0x1802e8cbe  lea     rdx, [rsp+0A8h+var_40]
0x1802e8cc3  mov     rcx, rdi
0x1802e8cc6  mov     rax, rbx
0x1802e8cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8cce  mov     rbx, rax
0x1802e8cd1  mov     rcx, [rsp+0A8h+string]; string
0x1802e8cd9  call    cs:__imp_WindowsDeleteString
0x1802e8cdf  xor     edi, edi
0x1802e8ce1  mov     [rsp+0A8h+string], rdi
0x1802e8ce9  mov     rcx, [rbx]
0x1802e8cec  mov     [rsp+0A8h+string], rcx
0x1802e8cf4  mov     [rbx], rdi
0x1802e8cf7  mov     rcx, [rsp+0A8h+var_40]; string
0x1802e8cfc  call    cs:__imp_WindowsDeleteString
0x1802e8d02  jmp     loc_1802E8DD3
0x1802e8d07  xor     edx, edx; length
0x1802e8d09  mov     rcx, [r15+50h]; string
0x1802e8d0d  call    cs:__imp_WindowsGetStringRawBuffer
0x1802e8d13  mov     [rsp+0A8h+var_40], rax
0x1802e8d18  lea     rdx, [rsp+0A8h+var_40]
0x1802e8d1d  lea     rcx, [rsp+0A8h+string]; string
0x1802e8d25  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802e8d2a  mov     ebx, eax
0x1802e8d2c  test    eax, eax
0x1802e8d2e  jns     loc_1802E8DD3
0x1802e8d34  mov     rcx, [rsp+0A8h]; this
0x1802e8d3c  mov     r9d, eax; char *
0x1802e8d3f  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802e8d46  mov     edx, 38Ch; void *
0x1802e8d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802e8d50  nop
0x1802e8d51  mov     rcx, [rsp+0A8h+string]; string
0x1802e8d59  call    cs:__imp_WindowsDeleteString
0x1802e8d5f  mov     [rsp+0A8h+string], rdi
0x1802e8d67  lea     rcx, [rsp+0A8h+var_48]
0x1802e8d6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e8d71  nop
0x1802e8d72  mov     rcx, [rsp+0A8h+arg_38]
0x1802e8d7a  test    rcx, rcx
0x1802e8d7d  jz      short loc_1802E8D94
0x1802e8d7f  mov     [rsp+0A8h+arg_38], rdi
0x1802e8d87  mov     rax, [rcx]
0x1802e8d8a  mov     rax, [rax+10h]
0x1802e8d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8d93  nop
0x1802e8d94  mov     rcx, [rsp+0A8h+arg_0]; string
0x1802e8d9c  call    cs:__imp_WindowsDeleteString
0x1802e8da2  mov     [rsp+0A8h+arg_0], rdi
0x1802e8daa  mov     rcx, [rsp+0A8h+arg_30]
0x1802e8db2  test    rcx, rcx
0x1802e8db5  jz      short loc_1802E8DCC
0x1802e8db7  mov     [rsp+0A8h+arg_30], rdi
0x1802e8dbf  mov     rax, [rcx]
0x1802e8dc2  mov     rax, [rax+10h]
0x1802e8dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8dcb  nop
0x1802e8dcc  mov     eax, ebx
0x1802e8dce  jmp     loc_1802E8F3C
0x1802e8dd3  test    r14, r14
0x1802e8dd6  jz      loc_1802E8E99
0x1802e8ddc  mov     r8, r14
0x1802e8ddf  mov     rdx, [rsp+0A8h+string]
0x1802e8de7  mov     rcx, [r15+68h]
0x1802e8deb  call    _anonymous_namespace___LoadStreamFromFile
0x1802e8df0  mov     ebx, eax
0x1802e8df2  test    eax, eax
0x1802e8df4  jns     loc_1802E8E99
0x1802e8dfa  mov     rcx, [rsp+0A8h]; this
0x1802e8e02  mov     r9d, eax; char *
0x1802e8e05  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1802e8e0c  mov     edx, 391h; void *
0x1802e8e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802e8e16  nop
0x1802e8e17  mov     rcx, [rsp+0A8h+string]; string
0x1802e8e1f  call    cs:__imp_WindowsDeleteString
0x1802e8e25  mov     [rsp+0A8h+string], rdi
0x1802e8e2d  lea     rcx, [rsp+0A8h+var_48]
0x1802e8e32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e8e37  nop
0x1802e8e38  mov     rcx, [rsp+0A8h+arg_38]
0x1802e8e40  test    rcx, rcx
0x1802e8e43  jz      short loc_1802E8E5A
0x1802e8e45  mov     [rsp+0A8h+arg_38], rdi
0x1802e8e4d  mov     rax, [rcx]
0x1802e8e50  mov     rax, [rax+10h]
0x1802e8e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8e59  nop
0x1802e8e5a  mov     rcx, [rsp+0A8h+arg_0]; string
0x1802e8e62  call    cs:__imp_WindowsDeleteString
0x1802e8e68  mov     [rsp+0A8h+arg_0], rdi
0x1802e8e70  mov     rcx, [rsp+0A8h+arg_30]
0x1802e8e78  test    rcx, rcx
0x1802e8e7b  jz      short loc_1802E8E92
0x1802e8e7d  mov     [rsp+0A8h+arg_30], rdi
0x1802e8e85  mov     rax, [rcx]
0x1802e8e88  mov     rax, [rax+10h]
0x1802e8e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8e91  nop
0x1802e8e92  mov     eax, ebx
0x1802e8e94  jmp     loc_1802E8F3C
0x1802e8e99  test    rsi, rsi
0x1802e8e9c  jz      short loc_1802E8EB6
0x1802e8e9e  mov     rax, [rsp+0A8h+string]
0x1802e8ea6  mov     rcx, rdi
0x1802e8ea9  mov     [rsp+0A8h+string], rcx
0x1802e8eb1  mov     [rsi], rax
0x1802e8eb4  jmp     short loc_1802E8EBE
0x1802e8eb6  mov     rcx, [rsp+0A8h+string]; string
0x1802e8ebe  call    cs:__imp_WindowsDeleteString
0x1802e8ec4  mov     [rsp+0A8h+string], rdi
0x1802e8ecc  lea     rcx, [rsp+0A8h+var_48]
0x1802e8ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802e8ed6  nop
0x1802e8ed7  mov     rcx, [rsp+0A8h+arg_38]
0x1802e8edf  test    rcx, rcx
0x1802e8ee2  jz      short loc_1802E8EF9
0x1802e8ee4  mov     [rsp+0A8h+arg_38], rdi
0x1802e8eec  mov     rax, [rcx]
0x1802e8eef  mov     rax, [rax+10h]
0x1802e8ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8ef8  nop
0x1802e8ef9  mov     rcx, [rsp+0A8h+arg_0]; string
0x1802e8f01  call    cs:__imp_WindowsDeleteString
0x1802e8f07  mov     [rsp+0A8h+arg_0], rdi
0x1802e8f0f  mov     rcx, [rsp+0A8h+arg_30]
0x1802e8f17  test    rcx, rcx
0x1802e8f1a  jz      short loc_1802E8F31
0x1802e8f1c  mov     [rsp+0A8h+arg_30], rdi
0x1802e8f24  mov     rax, [rcx]
0x1802e8f27  mov     rax, [rax+10h]
0x1802e8f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e8f30  nop
0x1802e8f31  xor     eax, eax
0x1802e8f33  jmp     short loc_1802E8F3C
0x1802e8f35  mov     eax, dword ptr [rsp+0A8h+string]
0x1802e8f3c  add     rsp, 70h
0x1802e8f40  pop     r15
0x1802e8f42  pop     r14
0x1802e8f44  pop     r13
0x1802e8f46  pop     r12
0x1802e8f48  pop     rdi
0x1802e8f49  pop     rsi
0x1802e8f4a  pop     rbx
0x1802e8f4b  retn
```

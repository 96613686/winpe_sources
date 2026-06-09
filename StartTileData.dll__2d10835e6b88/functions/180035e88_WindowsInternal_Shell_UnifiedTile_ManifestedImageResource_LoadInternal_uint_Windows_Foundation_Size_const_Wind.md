# WindowsInternal::Shell::UnifiedTile::ManifestedImageResource::LoadInternal(uint,Windows::Foundation::Size const &,Windows::Foundation::Size const &,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme,WindowsInternal::Shell::UnifiedTile::TileImageResourceAlternateForm,WindowsInternal::Shell::UnifiedTile::TileImageResourceContrast *,WindowsInternal::Shell::UnifiedTile::TileImageResourceTheme *,WindowsInternal::Shell::UnifiedTile::TileImageResourceAlternateForm *,HSTRING__ * *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180035e88`
- end: `0x180036406`
- name: `?LoadInternal@ManifestedImageResource@UnifiedTile@Shell@WindowsInternal@@AEBAJIAEBUSize@Foundation@Windows@@0W4TileImageResourceContrast@234@W4TileImageResourceTheme@234@W4TileImageResourceAlternateForm@234@PEAW48234@PEAW49234@PEAW4TileImageResourceAlternateForm@234@PEAPEAUHSTRING__@@PEAPEAUIRandomAccessStream@Streams@Storage@7@@Z`
- size: `1406`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802e7564`
- `0x1802e7824`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180035518`
- `0x180035e88`
- `0x18003640c`
- `0x1800421ac`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003617d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003617d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800360a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800361b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003620c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800362bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800363a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800360a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800361b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003620c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800362bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800363a2`

## string_xrefs

- `0x180036198`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x180036310`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x1800363bf`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 WindowsInternal::Shell::UnifiedTile::ManifestedImageResource::LoadInternal(
        __int64 a1,
        int a2,
        float *a3,
        float *a4,
        int a5,
        int a6,
        int a7,
        ...)
{
  HSTRING v8; // r12
  __int64 v9; // r13
  HSTRING *v10; // r14
  __int64 v11; // r15
  __int64 v12; // rdi
  unsigned __int8 (__fastcall *v13)(__int64, const struct _GUID *, GUID *, __int64 *); // rbx
  unsigned int v14; // edx
  HSTRING *v15; // rbx
  int StreamFromFile; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // r9
  HSTRING *v20; // rcx
  __int64 result; // rax
  HSTRING v22; // rbx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rcx
  HSTRING *v27; // rcx
  HSTRING v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  HSTRING *v31; // rcx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *, _QWORD, _QWORD, enum DEVICE_SCALE_FACTOR, int, int, int, HSTRING, __int64, __int64); // rbx
  enum DEVICE_SCALE_FACTOR v34; // eax
  HSTRING *v35; // rcx
  int v36; // [rsp+20h] [rbp-98h]
  HSTRING v37[9]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  HSTRING v39; // [rsp+C0h] [rbp+8h] BYREF
  ShellMRTHelper::Common *v40; // [rsp+C8h] [rbp+10h]
  float *v41; // [rsp+D0h] [rbp+18h]
  float *v42; // [rsp+D8h] [rbp+20h]
  HSTRING string; // [rsp+F8h] [rbp+40h] BYREF
  va_list stringa; // [rsp+F8h] [rbp+40h]
  __int64 v45; // [rsp+100h] [rbp+48h]
  __int64 v46; // [rsp+108h] [rbp+50h] BYREF
  va_list va1; // [rsp+108h] [rbp+50h]
  HSTRING *v48; // [rsp+110h] [rbp+58h] BYREF
  va_list va2; // [rsp+110h] [rbp+58h]
  __int64 v50; // [rsp+118h] [rbp+60h] BYREF
  va_list va3; // [rsp+118h] [rbp+60h]
  va_list va4; // [rsp+120h] [rbp+68h] BYREF

  va_start(va4, a7);
  va_start(va3, a7);
  va_start(va2, a7);
  va_start(va1, a7);
  va_start(stringa, a7);
  string = va_arg(va1, HSTRING);
  v45 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v46 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v48 = va_arg(va3, HSTRING *);
  va_copy(va4, va3);
  v50 = va_arg(va4, _QWORD);
  v42 = a4;
  v41 = a3;
  LODWORD(v40) = a2;
  v8 = string;
  if ( string )
    *(_DWORD *)string = 2;
  v9 = v46;
  if ( v46 )
    *(_DWORD *)v46 = 0;
  v10 = v48;
  if ( v48 )
    *v48 = 0;
  v11 = v50;
  if ( v50 )
    *(_QWORD *)v50 = 0;
  try
  {
    if ( *(_DWORD *)(a1 + 72) != 5 && *(_BYTE *)(a1 + 128) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)0x80070057LL,
        v36);
      return 2147942487LL;
    }
    (*(void (__fastcall **)(_QWORD, HSTRING **, __int128 *))(**(_QWORD **)(a1 + 96) + 24LL))(
      *(_QWORD *)(a1 + 96),
      (HSTRING **)va2,
      &TileData);
    if ( v48 )
    {
      DataStoreCache::DataItemIdentifier::DataItemIdentifier(
        (DataStoreCache::DataItemIdentifier *)&v39,
        *(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **)(a1 + 80));
      (*((void (__fastcall **)(HSTRING *, __int64 *, HSTRING))*v48 + 5))(v48, (__int64 *)va3, v39);
      v46 = 0;
      string = 0;
      v12 = v50;
      v13 = *(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64 *))(*(_QWORD *)v50 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)va1);
      if ( v13(v12, &c_MRTTransformerId, &GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a, (__int64 *)va1) )
      {
        if ( *(_BYTE *)(a1 + 128) )
        {
          v15 = (HSTRING *)(*(__int64 (__fastcall **)(__int64, HSTRING *, _QWORD, _QWORD, _WORD, _WORD, int, int, int, HSTRING, __int64, __int64))(*(_QWORD *)v46 + 64LL))(
                             v46,
                             v37,
                             *(_QWORD *)(a1 + 88),
                             *(unsigned int *)(a1 + 72),
                             (int)*v41,
                             (int)*v42,
                             a5,
                             a6,
                             a7,
                             v8,
                             v45,
                             v9);
        }
        else
        {
          v32 = v46;
          v33 = *(__int64 (__fastcall **)(__int64, HSTRING *, _QWORD, _QWORD, enum DEVICE_SCALE_FACTOR, int, int, int, HSTRING, __int64, __int64))(*(_QWORD *)v46 + 72LL);
          v34 = ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent(
                  (ShellMRTHelper::Common *)(unsigned int)v40,
                  v14);
          v15 = (HSTRING *)v33(v32, v37, *(_QWORD *)(a1 + 88), *(unsigned int *)(a1 + 72), v34, a5, a6, a7, v8, v45, v9);
        }
        WindowsDeleteString(string);
        string = 0;
        string = *v15;
        *v15 = 0;
        WindowsDeleteString(v37[0]);
        goto LABEL_15;
      }
      v22 = *(HSTRING *)(a1 + 88);
      if ( v22 && v22 == string
        || (WindowsDeleteString(string),
            string = 0,
            v23 = WindowsDuplicateString(v22, (HSTRING *)stringa),
            v24 = v23,
            v23 >= 0) )
      {
LABEL_15:
        if ( v11
          && (StreamFromFile = anonymous_namespace_::LoadStreamFromFile(*(_QWORD *)(a1 + 112), string, v11),
              StreamFromFile < 0) )
        {
          WindowsDeleteString(string);
          string = 0;
          v17 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          v18 = v50;
          if ( v50 )
          {
            v50 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          WindowsDeleteString(v39);
          v39 = 0;
          v20 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*((void (__fastcall **)(HSTRING *))*v20 + 2))(v20);
          }
          return (unsigned int)StreamFromFile;
        }
        else
        {
          if ( v10 )
          {
            v28 = string;
            string = 0;
            *v10 = v28;
          }
          WindowsDeleteString(string);
          string = 0;
          v29 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v50;
          if ( v50 )
          {
            v50 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          WindowsDeleteString(v39);
          v39 = 0;
          v31 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*((void (__fastcall **)(HSTRING *))*v31 + 2))(v31);
          }
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)(unsigned int)v23,
        v36);
      WindowsDeleteString(string);
      string = 0;
      v25 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      WindowsDeleteString(v39);
      v39 = 0;
      v27 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*((void (__fastcall **)(HSTRING *))*v27 + 2))(v27);
      }
      result = v24;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
        (const char *)0x8000FFFFLL,
        v36);
      v35 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*((void (__fastcall **)(HSTRING *, HSTRING))*v35 + 2))(v35, *v35);
      }
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1EF,
                           (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x180035e88  mov     [rsp+arg_18], r9
0x180035e8d  mov     [rsp+arg_10], r8
0x180035e92  mov     dword ptr [rsp+arg_8], edx
0x180035e96  push    rbx
0x180035e97  push    rsi
0x180035e98  push    rdi
0x180035e99  push    r12
0x180035e9b  push    r13
0x180035e9d  push    r14
0x180035e9f  push    r15
0x180035ea1  sub     rsp, 80h
0x180035ea8  mov     rsi, rcx
0x180035eab  mov     r12, [rsp+0B8h+string]
0x180035eb3  xor     ebx, ebx
0x180035eb5  test    r12, r12
0x180035eb8  jz      short loc_180035EC2
0x180035eba  mov     dword ptr [r12], 2
0x180035ec2  mov     r13, [rsp+0B8h+arg_48]
0x180035eca  test    r13, r13
0x180035ecd  jz      short loc_180035ED3
0x180035ecf  mov     [r13+0], ebx
0x180035ed3  mov     r14, [rsp+0B8h+arg_50]
0x180035edb  test    r14, r14
0x180035ede  jz      short loc_180035EE3
0x180035ee0  mov     [r14], rbx
0x180035ee3  mov     r15, [rsp+0B8h+arg_58]
0x180035eeb  test    r15, r15
0x180035eee  jz      short loc_180035EF3
0x180035ef0  mov     [r15], rbx
0x180035ef3  cmp     dword ptr [rcx+48h], 5
0x180035ef7  jnz     loc_1800362F4
0x180035efd  mov     rcx, [rcx+60h]
0x180035f01  mov     rax, [rcx]
0x180035f04  lea     r8, TileData
0x180035f0b  lea     rdx, [rsp+0B8h+arg_50]
0x180035f13  mov     rax, [rax+18h]
0x180035f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f1c  nop
0x180035f1d  cmp     [rsp+0B8h+arg_50], rbx
0x180035f25  jz      loc_1800363AF
0x180035f2b  mov     rdx, [rsi+50h]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *
0x180035f2f  lea     rcx, [rsp+0B8h+arg_0]; this
0x180035f37  call    ??0DataItemIdentifier@DataStoreCache@@QEAA@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; DataStoreCache::DataItemIdentifier::DataItemIdentifier(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x180035f3c  nop
0x180035f3d  mov     rcx, [rsp+0B8h+arg_50]
0x180035f45  mov     rax, [rcx]
0x180035f48  mov     r8, [rsp+0B8h+arg_0]
0x180035f50  lea     rdx, [rsp+0B8h+arg_58]
0x180035f58  mov     rax, [rax+28h]
0x180035f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f61  nop
0x180035f62  mov     [rsp+0B8h+arg_48], rbx
0x180035f6a  mov     [rsp+0B8h+string], rbx
0x180035f72  mov     rdi, [rsp+0B8h+arg_58]
0x180035f7a  mov     rax, [rdi]
0x180035f7d  mov     rbx, [rax+30h]
0x180035f81  lea     rcx, [rsp+0B8h+arg_48]
0x180035f89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035f8e  lea     r9, [rsp+0B8h+arg_48]
0x180035f96  lea     r8, _GUID_461218a4_e7b8_4c32_bdb8_7421111d6c4a
0x180035f9d  lea     rdx, c_MRTTransformerId
0x180035fa4  mov     rcx, rdi
0x180035fa7  mov     rax, rbx
0x180035faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035faf  xor     edi, edi
0x180035fb1  test    al, al
0x180035fb3  jz      loc_180036145
0x180035fb9  cmp     [rsi+80h], dil
0x180035fc0  jz      loc_180036328
0x180035fc6  mov     rcx, [rsp+0B8h+arg_48]
0x180035fce  mov     rax, [rcx]
0x180035fd1  mov     rdx, [rsp+0B8h+arg_18]
0x180035fd9  cvttss2si r8d, dword ptr [rdx]
0x180035fde  mov     rdx, [rsp+0B8h+arg_10]
0x180035fe6  cvttss2si r9d, dword ptr [rdx]
0x180035feb  mov     [rsp+0B8h+var_60], r13
0x180035ff0  mov     rdx, [rsp+0B8h+arg_40]
0x180035ff8  mov     [rsp+0B8h+var_68], rdx
0x180035ffd  mov     [rsp+0B8h+var_70], r12
0x180036002  mov     edx, [rsp+0B8h+arg_30]
0x180036009  mov     dword ptr [rsp+0B8h+var_78], edx
0x18003600d  mov     edx, [rsp+0B8h+arg_28]
0x180036014  mov     [rsp+0B8h+var_80], edx
0x180036018  mov     edx, [rsp+0B8h+arg_20]
0x18003601f  mov     [rsp+0B8h+var_88], edx
0x180036023  mov     word ptr [rsp+0B8h+var_90], r8w
0x180036029  mov     word ptr [rsp+0B8h+var_98], r9w
0x18003602f  mov     r9d, [rsi+48h]
0x180036033  mov     r8, [rsi+58h]
0x180036037  lea     rdx, [rsp+0B8h+var_48]
0x18003603c  mov     rax, [rax+40h]
0x180036040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036045  mov     rbx, rax
0x180036048  mov     rcx, [rsp+0B8h+string]; string
0x180036050  call    cs:__imp_WindowsDeleteString
0x180036056  mov     [rsp+0B8h+string], rdi
0x18003605e  mov     rcx, [rbx]
0x180036061  mov     [rsp+0B8h+string], rcx
0x180036069  mov     [rbx], rdi
0x18003606c  mov     rcx, [rsp+0B8h+var_48]; string
0x180036071  call    cs:__imp_WindowsDeleteString
0x180036077  test    r15, r15
0x18003607a  jz      loc_180036243
0x180036080  mov     r8, r15
0x180036083  mov     rdx, [rsp+0B8h+string]
0x18003608b  mov     rcx, [rsi+70h]
0x18003608f  call    _anonymous_namespace___LoadStreamFromFile
0x180036094  mov     ebx, eax
0x180036096  test    eax, eax
0x180036098  jns     loc_180036243
0x18003609e  mov     rcx, [rsp+0B8h+string]; string
0x1800360a6  call    cs:__imp_WindowsDeleteString
0x1800360ac  mov     [rsp+0B8h+string], rdi
0x1800360b4  mov     rcx, [rsp+0B8h+arg_48]
0x1800360bc  test    rcx, rcx
0x1800360bf  jz      short loc_1800360D6
0x1800360c1  mov     [rsp+0B8h+arg_48], rdi
0x1800360c9  mov     rax, [rcx]
0x1800360cc  mov     rax, [rax+10h]
0x1800360d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360d5  nop
0x1800360d6  mov     rcx, [rsp+0B8h+arg_58]
0x1800360de  test    rcx, rcx
0x1800360e1  jz      short loc_1800360F8
0x1800360e3  mov     [rsp+0B8h+arg_58], rdi
0x1800360eb  mov     rax, [rcx]
0x1800360ee  mov     rax, [rax+10h]
0x1800360f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360f7  nop
0x1800360f8  mov     rcx, [rsp+0B8h+arg_0]; string
0x180036100  call    cs:__imp_WindowsDeleteString
0x180036106  mov     [rsp+0B8h+arg_0], rdi
0x18003610e  mov     rcx, [rsp+0B8h+arg_50]
0x180036116  test    rcx, rcx
0x180036119  jz      short loc_180036130
0x18003611b  mov     [rsp+0B8h+arg_50], rdi
0x180036123  mov     rax, [rcx]
0x180036126  mov     rax, [rax+10h]
0x18003612a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003612f  nop
0x180036130  mov     eax, ebx
0x180036132  add     rsp, 80h
0x180036139  pop     r15
0x18003613b  pop     r14
0x18003613d  pop     r13
0x18003613f  pop     r12
0x180036141  pop     rdi
0x180036142  pop     rsi
0x180036143  pop     rbx
0x180036144  retn
0x180036145  mov     rbx, [rsi+58h]
0x180036149  test    rbx, rbx
0x18003614c  jz      short loc_18003615C
0x18003614e  cmp     rbx, [rsp+0B8h+string]
0x180036156  jz      loc_180036077
0x18003615c  mov     rcx, [rsp+0B8h+string]; string
0x180036164  call    cs:__imp_WindowsDeleteString
0x18003616a  mov     [rsp+0B8h+string], rdi
0x180036172  lea     rdx, [rsp+0B8h+string]; newString
0x18003617a  mov     rcx, rbx; string
0x18003617d  call    cs:__imp_WindowsDuplicateString
0x180036183  mov     ebx, eax
0x180036185  test    eax, eax
0x180036187  jns     loc_180036077
0x18003618d  mov     rcx, [rsp+0B8h]; this
0x180036195  mov     r9d, eax; char *
0x180036198  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18003619f  mov     edx, 1E2h; void *
0x1800361a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800361a9  nop
0x1800361aa  mov     rcx, [rsp+0B8h+string]; string
0x1800361b2  call    cs:__imp_WindowsDeleteString
0x1800361b8  mov     [rsp+0B8h+string], rdi
0x1800361c0  mov     rcx, [rsp+0B8h+arg_48]
0x1800361c8  test    rcx, rcx
0x1800361cb  jz      short loc_1800361E2
0x1800361cd  mov     [rsp+0B8h+arg_48], rdi
0x1800361d5  mov     rax, [rcx]
0x1800361d8  mov     rax, [rax+10h]
0x1800361dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361e1  nop
0x1800361e2  mov     rcx, [rsp+0B8h+arg_58]
0x1800361ea  test    rcx, rcx
0x1800361ed  jz      short loc_180036204
0x1800361ef  mov     [rsp+0B8h+arg_58], rdi
0x1800361f7  mov     rax, [rcx]
0x1800361fa  mov     rax, [rax+10h]
0x1800361fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036203  nop
0x180036204  mov     rcx, [rsp+0B8h+arg_0]; string
0x18003620c  call    cs:__imp_WindowsDeleteString
0x180036212  mov     [rsp+0B8h+arg_0], rdi
0x18003621a  mov     rcx, [rsp+0B8h+arg_50]
0x180036222  test    rcx, rcx
0x180036225  jz      short loc_18003623C
0x180036227  mov     [rsp+0B8h+arg_50], rdi
0x18003622f  mov     rax, [rcx]
0x180036232  mov     rax, [rax+10h]
0x180036236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003623b  nop
0x18003623c  mov     eax, ebx
0x18003623e  jmp     loc_180036132
0x180036243  test    r14, r14
0x180036246  jz      short loc_18003625B
0x180036248  mov     rax, [rsp+0B8h+string]
0x180036250  mov     [rsp+0B8h+string], rdi
0x180036258  mov     [r14], rax
0x18003625b  mov     rcx, [rsp+0B8h+string]; string
0x180036263  call    cs:__imp_WindowsDeleteString
0x180036269  mov     [rsp+0B8h+string], rdi
0x180036271  mov     rcx, [rsp+0B8h+arg_48]
0x180036279  test    rcx, rcx
0x18003627c  jz      short loc_180036293
0x18003627e  mov     [rsp+0B8h+arg_48], rdi
0x180036286  mov     rax, [rcx]
0x180036289  mov     rax, [rax+10h]
0x18003628d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036292  nop
0x180036293  mov     rcx, [rsp+0B8h+arg_58]
0x18003629b  test    rcx, rcx
0x18003629e  jz      short loc_1800362B5
0x1800362a0  mov     [rsp+0B8h+arg_58], rdi
0x1800362a8  mov     rax, [rcx]
0x1800362ab  mov     rax, [rax+10h]
0x1800362af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362b4  nop
0x1800362b5  mov     rcx, [rsp+0B8h+arg_0]; string
0x1800362bd  call    cs:__imp_WindowsDeleteString
0x1800362c3  mov     [rsp+0B8h+arg_0], rdi
0x1800362cb  mov     rcx, [rsp+0B8h+arg_50]
0x1800362d3  test    rcx, rcx
0x1800362d6  jz      short loc_1800362ED
0x1800362d8  mov     [rsp+0B8h+arg_50], rdi
0x1800362e0  mov     rax, [rcx]
0x1800362e3  mov     rax, [rax+10h]
0x1800362e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362ec  nop
0x1800362ed  xor     eax, eax
0x1800362ef  jmp     loc_180036132
0x1800362f4  cmp     [rcx+80h], bl
0x1800362fa  jz      loc_180035EFD
0x180036300  mov     rcx, [rsp+0B8h]; this
0x180036308  mov     ebx, 80070057h
0x18003630d  mov     r9d, ebx; char *
0x180036310  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180036317  mov     edx, 1AFh; void *
0x18003631c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036321  mov     eax, ebx
0x180036323  jmp     loc_180036132
0x180036328  mov     rdi, [rsp+0B8h+arg_48]
0x180036330  mov     rax, [rdi]
0x180036333  mov     rbx, [rax+48h]
0x180036337  mov     ecx, dword ptr [rsp+0B8h+arg_8]; this
0x18003633e  call    ?DeviceScaleFactorFromScalePercent@Common@ShellMRTHelper@@YA?AW4DEVICE_SCALE_FACTOR@@I@Z; ShellMRTHelper::Common::DeviceScaleFactorFromScalePercent(uint)
0x180036343  mov     [rsp+0B8h+var_68], r13
0x180036348  mov     rdx, [rsp+0B8h+arg_40]
0x180036350  mov     [rsp+0B8h+var_70], rdx
0x180036355  mov     [rsp+0B8h+var_78], r12
0x18003635a  mov     edx, [rsp+0B8h+arg_30]
0x180036361  mov     [rsp+0B8h+var_80], edx
0x180036365  mov     edx, [rsp+0B8h+arg_28]
0x18003636c  mov     [rsp+0B8h+var_88], edx
0x180036370  mov     edx, [rsp+0B8h+arg_20]
0x180036377  mov     [rsp+0B8h+var_90], edx
0x18003637b  mov     [rsp+0B8h+var_98], eax
0x18003637f  mov     r9d, [rsi+48h]
0x180036383  mov     r8, [rsi+58h]
0x180036387  lea     rdx, [rsp+0B8h+var_48]
0x18003638c  mov     rcx, rdi
0x18003638f  mov     rax, rbx
0x180036392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036397  mov     rbx, rax
0x18003639a  mov     rcx, [rsp+0B8h+string]; string
0x1800363a2  call    cs:__imp_WindowsDeleteString
0x1800363a8  xor     edi, edi
0x1800363aa  jmp     loc_180036056
0x1800363af  mov     rcx, [rsp+0B8h]; this
0x1800363b7  mov     edi, 8000FFFFh
0x1800363bc  mov     r9d, edi; char *
0x1800363bf  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800363c6  mov     edx, 1BBh; void *
0x1800363cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363d0  nop
0x1800363d1  mov     rcx, [rsp+0B8h+arg_50]
0x1800363d9  test    rcx, rcx
0x1800363dc  jz      short loc_1800363F3
0x1800363de  mov     [rsp+0B8h+arg_50], rbx
0x1800363e6  mov     rdx, [rcx]
0x1800363e9  mov     rax, [rdx+10h]
0x1800363ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363f2  nop
0x1800363f3  mov     eax, edi
0x1800363f5  jmp     loc_180036132
0x1800363fa  mov     eax, dword ptr [rsp+0B8h+string]
0x180036401  jmp     loc_180036132
```

# winrt::WindowsInternal::Shell::JumpList::implementation::JumpListItemCustomVerb::JumpListItemCustomVerb(winrt::WindowsInternal::Shell::JumpList::implementation::JumpListItemCustomVerbKind,winrt::WindowsInternal::Shell::JumpList::JumpListItem const &,winrt::hstring const &,winrt::hstring const &,winrt::WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions)

- ea: `0x18002f668`
- end: `0x18002fc8b`
- name: `??0JumpListItemCustomVerb@implementation@JumpList@Shell@WindowsInternal@winrt@@QEAA@W4JumpListItemCustomVerbKind@12345@AEBUJumpListItem@2345@AEBUhstring@5@2W4VerbEnumerationOptions@UnifiedTile@345@@Z`
- size: `1571`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180128208`

## callees

- `0x18001dac0`
- `0x1800240ac`
- `0x180025868`
- `0x18002f668`
- `0x18003153c`
- `0x1800385d0`
- `0x1800488e8`
- `0x1800bdb2c`
- `0x180105530`
- `0x180159390`
- `0x1801a723c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fbfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fac3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fbfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002fc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc37`

## string_xrefs

- `0x18002f6f8`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f744`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f777`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f7af`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f80d`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f853`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f88b`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f8e9`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f92b`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f963`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f9c1`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fa03`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fa3b`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fad4`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fb16`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fb4e`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fbac`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fc0b`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002fc5b`: `shellcommon\shell\tiles\jumplist\lib\jumplistverbs.cpp`
- `0x18002f9e8`: `OpenFileLocation`
- `0x18002f75c`: `JumpListRemoveItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall winrt::WindowsInternal::Shell::JumpList::implementation::JumpListItemCustomVerb::JumpListItemCustomVerb(
        __int64 a1,
        int a2,
        _QWORD *a3,
        HSTRING *a4,
        HSTRING *a5,
        char a6)
{
  char v10; // bl
  int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  const WCHAR **v20; // rcx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  HSTRING *v31; // rbx
  __int64 v32; // rcx
  HSTRING v33; // rdi
  HRESULT v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  HSTRING *v39; // rbx
  HSTRING v40; // rdi
  HRESULT v41; // eax
  HSTRING *v42; // rbx
  HSTRING v43; // rdi
  HRESULT v44; // eax
  const WCHAR *v46; // [rsp+20h] [rbp-30h] BYREF
  __int64 v47; // [rsp+28h] [rbp-28h]
  _BYTE v48[8]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v49[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HSTRING v51; // [rsp+90h] [rbp+40h] BYREF

  WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>();
  *(_QWORD *)a1 = &winrt::WindowsInternal::Shell::JumpList::implementation::JumpListItemCustomVerb::`vftable';
  *(_QWORD *)(a1 + 8) = &WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,4,0,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *(_QWORD *)(a1 + 16) = &winrt::WindowsInternal::Shell::JumpList::implementation::JumpListTileCustomVerb::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 144) = *a3;
  Microsoft::WRL::ComPtr<CRefCountedObject<CItemLayoutChainDisplacement::ChainLink>>::InternalAddRef();
  *(_DWORD *)(a1 + 152) = a2;
  if ( (a6 & 2) != 0 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 1;
    v11 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)(a1 + 104),
            L"Segoe Fluent Icons",
            0x12u);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v11,
        (int)v46);
  }
  v12 = *(_DWORD *)(a1 + 152);
  if ( !v12 )
  {
    v35 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(a1 + 80), L"Open", 4u);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v35,
        (int)v46);
    if ( !v10 )
      goto LABEL_59;
    v36 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)(a1 + 96),
            &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::Open,
            1u);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v36,
        (int)v46);
    v37 = winrt::WindowsInternal::Shell::JumpList::from_string_abi(&v46, a1 + 80);
    winrt::hstring::operator std::basic_string_view<unsigned short>(v37, v49);
    v51 = *(HSTRING *)winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(
                        v48,
                        2100,
                        v49);
    v38 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 88), &v51);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v38,
        (int)v46);
    goto LABEL_57;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 != 1 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xD9,
            (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
            (const char *)0x8000FFFFLL,
            (int)v46);
        v16 = Microsoft::WRL::Wrappers::HString::Set(
                (Microsoft::WRL::Wrappers::HString *)(a1 + 80),
                L"JumpListRemoveItem",
                0x12u);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
            (const char *)(unsigned int)v16,
            (int)v46);
        if ( v10 )
        {
          v17 = Microsoft::WRL::Wrappers::HString::Set(
                  (Microsoft::WRL::Wrappers::HString *)(a1 + 96),
                  &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::Uninstall,
                  1u);
          if ( v17 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD0,
              (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
              (const char *)(unsigned int)v17,
              (int)v46);
          v18 = winrt::WindowsInternal::Shell::JumpList::from_string_abi(v48, a1 + 80);
          winrt::hstring::operator std::basic_string_view<unsigned short>(v18, v49);
          v51 = *(HSTRING *)winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(
                              &v46,
                              2102,
                              v49);
          v19 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 88), &v51);
          if ( v19 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xD3,
              (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
              (const char *)(unsigned int)v19,
              (int)v46);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v46);
LABEL_19:
          v20 = (const WCHAR **)v48;
LABEL_58:
          winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
          goto LABEL_59;
        }
        goto LABEL_59;
      }
      v21 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)(a1 + 80),
              L"JumpListUnpinItem",
              0x11u);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v21,
          (int)v46);
      if ( !v10 )
        goto LABEL_59;
      v22 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)(a1 + 96),
              &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::Unpin,
              1u);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v22,
          (int)v46);
      v23 = winrt::WindowsInternal::Shell::JumpList::from_string_abi(&v46, a1 + 80);
      winrt::hstring::operator std::basic_string_view<unsigned short>(v23, v49);
      v51 = *(HSTRING *)winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(
                          v48,
                          2103,
                          v49);
      v24 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 88), &v51);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v24,
          (int)v46);
    }
    else
    {
      v25 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)(a1 + 80),
              L"JumpListPinItem",
              0xFu);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v25,
          (int)v46);
      if ( !v10 )
        goto LABEL_59;
      v26 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)(a1 + 96),
              &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::Pin,
              1u);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v26,
          (int)v46);
      v27 = winrt::WindowsInternal::Shell::JumpList::from_string_abi(&v46, a1 + 80);
      winrt::hstring::operator std::basic_string_view<unsigned short>(v27, v49);
      v51 = *(HSTRING *)winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(
                          v48,
                          2101,
                          v49);
      v28 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 88), &v51);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
          (const char *)(unsigned int)v28,
          (int)v46);
    }
LABEL_57:
    winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
    v20 = &v46;
    goto LABEL_58;
  }
  v29 = Microsoft::WRL::Wrappers::HString::Set(
          (Microsoft::WRL::Wrappers::HString *)(a1 + 80),
          L"OpenFileLocation",
          0x10u);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
  if ( v10 )
  {
    v30 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)(a1 + 96),
            &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::OpenFileLocation,
            1u);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v30,
        (int)v46);
    v31 = (HSTRING *)(a1 + 88);
    v32 = *(_QWORD *)winrt::WindowsInternal::Shell::JumpList::from_string_abi(v48, a1 + 80);
    if ( v32 )
    {
      v46 = *(const WCHAR **)(v32 + 16);
      v47 = *(unsigned int *)(v32 + 4);
    }
    else
    {
      v46 = &String1;
      v47 = 0;
    }
    v33 = *(HSTRING *)winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(
                        &v51,
                        2104,
                        &v46);
    if ( !v33 || (v34 = 0, v33 != *v31) )
    {
      WindowsDeleteString(*v31);
      *v31 = 0;
      v34 = WindowsDuplicateString(v33, (HSTRING *)(a1 + 88));
    }
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
        (const char *)(unsigned int)v34,
        (int)v46);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
    goto LABEL_19;
  }
LABEL_59:
  v39 = (HSTRING *)(a1 + 64);
  v40 = *a4;
  if ( !*a4 || (v41 = 0, v40 != *v39) )
  {
    WindowsDeleteString(*v39);
    *v39 = 0;
    v41 = WindowsDuplicateString(v40, (HSTRING *)(a1 + 64));
  }
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
      (const char *)(unsigned int)v41,
      (int)v46);
  v42 = (HSTRING *)(a1 + 72);
  v43 = *a5;
  if ( !*a5 || (v44 = 0, v43 != *v42) )
  {
    WindowsDeleteString(*v42);
    *v42 = 0;
    v44 = WindowsDuplicateString(v43, (HSTRING *)(a1 + 72));
  }
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\lib\\jumplistverbs.cpp",
      (const char *)(unsigned int)v44,
      (int)v46);
  *(_DWORD *)(a1 + 136) |= 1u;
  return a1;
}

```

## disassembly

```asm
0x18002f668  mov     [rsp-28h+arg_8], rbx
0x18002f66d  mov     [rsp-28h+arg_0], rcx
0x18002f672  push    rbp
0x18002f673  push    rsi
0x18002f674  push    rdi
0x18002f675  push    r14
0x18002f677  push    r15
0x18002f679  mov     rbp, rsp
0x18002f67c  sub     rsp, 50h
0x18002f680  mov     r14, r9
0x18002f683  mov     rbx, r8
0x18002f686  mov     edi, edx
0x18002f688  mov     rsi, rcx
0x18002f68b  call    ??0?$TileVerbBase@$0A@$0A@$0IA@VFtmBase@WRL@Microsoft@@@Private@UnifiedTile@Shell@WindowsInternal@@QEAA@XZ; WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>(void)
0x18002f690  nop
0x18002f691  lea     rax, ??_7JumpListItemCustomVerb@implementation@JumpList@Shell@WindowsInternal@winrt@@6B@; const winrt::WindowsInternal::Shell::JumpList::implementation::JumpListItemCustomVerb::`vftable'
0x18002f698  mov     [rsi], rax
0x18002f69b  lea     rax, ??_7?$TileVerbBase@$0A@$03$0A@VFtmBase@WRL@Microsoft@@@Private@UnifiedTile@Shell@WindowsInternal@@6BIWeakReferenceSource@@@; const WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,4,0,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18002f6a2  mov     [rsi+8], rax
0x18002f6a6  lea     rax, ??_7JumpListTileCustomVerb@implementation@JumpList@Shell@WindowsInternal@winrt@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const winrt::WindowsInternal::Shell::JumpList::implementation::JumpListTileCustomVerb::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002f6ad  mov     [rsi+10h], rax
0x18002f6b1  lea     rcx, [rsi+90h]
0x18002f6b8  mov     rax, [rbx]
0x18002f6bb  mov     [rcx], rax
0x18002f6be  call    ?InternalAddRef@?$ComPtr@V?$CRefCountedObject@UChainLink@CItemLayoutChainDisplacement@@@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CRefCountedObject<CItemLayoutChainDisplacement::ChainLink>>::InternalAddRef(void)
0x18002f6c3  nop
0x18002f6c4  mov     [rsi+98h], edi
0x18002f6ca  mov     r15d, 1
0x18002f6d0  test    [rbp+arg_28], 2
0x18002f6d4  jnz     short loc_18002F70A
0x18002f6d6  mov     bl, r15b
0x18002f6d9  lea     rcx, [rsi+68h]; this
0x18002f6dd  lea     r8d, [r15+11h]; unsigned int
0x18002f6e1  lea     rdx, ?FontFamily@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Segoe Fluent Icons"
0x18002f6e8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f6ed  mov     rcx, [rbp+28h]; this
0x18002f6f1  test    eax, eax
0x18002f6f3  jns     short loc_18002F70C
0x18002f6f5  mov     r9d, eax; char *
0x18002f6f8  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f6ff  mov     edx, 8Ah; void *
0x18002f704  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f70a  xor     bl, bl
0x18002f70c  mov     ecx, [rsi+98h]
0x18002f712  test    ecx, ecx
0x18002f714  jz      loc_18002FAF5
0x18002f71a  sub     ecx, r15d
0x18002f71d  jz      loc_18002F9E2
0x18002f723  sub     ecx, r15d
0x18002f726  jz      loc_18002F90A
0x18002f72c  sub     ecx, r15d
0x18002f72f  jz      loc_18002F832
0x18002f735  cmp     ecx, r15d
0x18002f738  jz      short loc_18002F756
0x18002f73a  mov     rcx, [rbp+28h]; this
0x18002f73e  mov     r9d, 8000FFFFh; char *
0x18002f744  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f74b  mov     edx, 0D9h; void *
0x18002f750  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002f756  mov     r8d, 12h; unsigned int
0x18002f75c  lea     rdx, ?JumpListRemoveItem@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "JumpListRemoveItem"
0x18002f763  lea     rcx, [rsi+50h]; this
0x18002f767  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f76c  mov     rcx, [rbp+28h]; this
0x18002f770  test    eax, eax
0x18002f772  jns     short loc_18002F789
0x18002f774  mov     r9d, eax; char *
0x18002f777  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f77e  mov     edx, 0CCh; void *
0x18002f783  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f789  test    bl, bl
0x18002f78b  jz      loc_18002FBD1
0x18002f791  lea     rcx, [rsi+60h]; this
0x18002f795  mov     r8d, r15d; unsigned int
0x18002f798  lea     rdx, ?Uninstall@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; unsigned __int16 *
0x18002f79f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f7a4  mov     rcx, [rbp+28h]; this
0x18002f7a8  test    eax, eax
0x18002f7aa  jns     short loc_18002F7C1
0x18002f7ac  mov     r9d, eax; char *
0x18002f7af  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f7b6  mov     edx, 0D0h; void *
0x18002f7bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f7c1  lea     rdx, [rsi+50h]
0x18002f7c5  lea     rcx, [rbp+var_20]
0x18002f7c9  call    ?from_string_abi@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@4@AEBVHString@Wrappers@WRL@Microsoft@@@Z; winrt::WindowsInternal::Shell::JumpList::from_string_abi(Microsoft::WRL::Wrappers::HString const &)
0x18002f7ce  nop
0x18002f7cf  lea     rdx, [rbp+var_18]
0x18002f7d3  mov     rcx, rax
0x18002f7d6  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002f7db  lea     r8, [rbp+var_18]
0x18002f7df  mov     edx, 836h
0x18002f7e4  lea     rcx, [rbp+var_30]
0x18002f7e8  call    ?LoadStringResourceWithFallback@StringHelpers@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@5@IAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(uint,std::basic_string_view<ushort> const &)
0x18002f7ed  nop
0x18002f7ee  mov     rax, [rax]
0x18002f7f1  mov     [rbp+arg_10], rax
0x18002f7f5  lea     rcx, [rsi+58h]; newString
0x18002f7f9  lea     rdx, [rbp+arg_10]; HSTRING *
0x18002f7fd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002f802  mov     rcx, [rbp+28h]; this
0x18002f806  test    eax, eax
0x18002f808  jns     short loc_18002F81F
0x18002f80a  mov     r9d, eax; char *
0x18002f80d  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f814  mov     edx, 0D3h; void *
0x18002f819  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f81f  lea     rcx, [rbp+var_30]
0x18002f823  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002f828  nop
0x18002f829  lea     rcx, [rbp+var_20]
0x18002f82d  jmp     loc_18002FBCC
0x18002f832  mov     r8d, 11h; unsigned int
0x18002f838  lea     rdx, ?JumpListUnpinItem@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "JumpListUnpinItem"
0x18002f83f  lea     rcx, [rsi+50h]; this
0x18002f843  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f848  mov     rcx, [rbp+28h]; this
0x18002f84c  test    eax, eax
0x18002f84e  jns     short loc_18002F865
0x18002f850  mov     r9d, eax; char *
0x18002f853  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f85a  mov     edx, 0BEh; void *
0x18002f85f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f865  test    bl, bl
0x18002f867  jz      loc_18002FBD1
0x18002f86d  lea     rcx, [rsi+60h]; this
0x18002f871  mov     r8d, r15d; unsigned int
0x18002f874  lea     rdx, ?Unpin@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; unsigned __int16 *
0x18002f87b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f880  mov     rcx, [rbp+28h]; this
0x18002f884  test    eax, eax
0x18002f886  jns     short loc_18002F89D
0x18002f888  mov     r9d, eax; char *
0x18002f88b  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f892  mov     edx, 0C2h; void *
0x18002f897  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f89d  lea     rdx, [rsi+50h]
0x18002f8a1  lea     rcx, [rbp+var_30]
0x18002f8a5  call    ?from_string_abi@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@4@AEBVHString@Wrappers@WRL@Microsoft@@@Z; winrt::WindowsInternal::Shell::JumpList::from_string_abi(Microsoft::WRL::Wrappers::HString const &)
0x18002f8aa  nop
0x18002f8ab  lea     rdx, [rbp+var_18]
0x18002f8af  mov     rcx, rax
0x18002f8b2  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002f8b7  lea     r8, [rbp+var_18]
0x18002f8bb  mov     edx, 837h
0x18002f8c0  lea     rcx, [rbp+var_20]
0x18002f8c4  call    ?LoadStringResourceWithFallback@StringHelpers@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@5@IAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(uint,std::basic_string_view<ushort> const &)
0x18002f8c9  nop
0x18002f8ca  mov     rax, [rax]
0x18002f8cd  mov     [rbp+arg_10], rax
0x18002f8d1  lea     rcx, [rsi+58h]; newString
0x18002f8d5  lea     rdx, [rbp+arg_10]; HSTRING *
0x18002f8d9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002f8de  mov     rcx, [rbp+28h]; this
0x18002f8e2  test    eax, eax
0x18002f8e4  jns     short loc_18002F8FB
0x18002f8e6  mov     r9d, eax; char *
0x18002f8e9  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f8f0  mov     edx, 0C5h; void *
0x18002f8f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f8fb  lea     rcx, [rbp+var_20]
0x18002f8ff  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002f904  nop
0x18002f905  jmp     loc_18002FBC8
0x18002f90a  mov     r8d, 0Fh; unsigned int
0x18002f910  lea     rdx, ?JumpListPinItem@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "JumpListPinItem"
0x18002f917  lea     rcx, [rsi+50h]; this
0x18002f91b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f920  mov     rcx, [rbp+28h]; this
0x18002f924  test    eax, eax
0x18002f926  jns     short loc_18002F93D
0x18002f928  mov     r9d, eax; char *
0x18002f92b  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f932  mov     edx, 0AFh; void *
0x18002f937  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f93d  test    bl, bl
0x18002f93f  jz      loc_18002FBD1
0x18002f945  lea     rcx, [rsi+60h]; this
0x18002f949  mov     r8d, r15d; unsigned int
0x18002f94c  lea     rdx, ?Pin@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; unsigned __int16 *
0x18002f953  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f958  mov     rcx, [rbp+28h]; this
0x18002f95c  test    eax, eax
0x18002f95e  jns     short loc_18002F975
0x18002f960  mov     r9d, eax; char *
0x18002f963  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f96a  mov     edx, 0B3h; void *
0x18002f96f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f975  lea     rdx, [rsi+50h]
0x18002f979  lea     rcx, [rbp+var_30]
0x18002f97d  call    ?from_string_abi@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@4@AEBVHString@Wrappers@WRL@Microsoft@@@Z; winrt::WindowsInternal::Shell::JumpList::from_string_abi(Microsoft::WRL::Wrappers::HString const &)
0x18002f982  nop
0x18002f983  lea     rdx, [rbp+var_18]
0x18002f987  mov     rcx, rax
0x18002f98a  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002f98f  lea     r8, [rbp+var_18]
0x18002f993  mov     edx, 835h
0x18002f998  lea     rcx, [rbp+var_20]
0x18002f99c  call    ?LoadStringResourceWithFallback@StringHelpers@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@5@IAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(uint,std::basic_string_view<ushort> const &)
0x18002f9a1  nop
0x18002f9a2  mov     rax, [rax]
0x18002f9a5  mov     [rbp+arg_10], rax
0x18002f9a9  lea     rcx, [rsi+58h]; newString
0x18002f9ad  lea     rdx, [rbp+arg_10]; HSTRING *
0x18002f9b1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002f9b6  mov     rcx, [rbp+28h]; this
0x18002f9ba  test    eax, eax
0x18002f9bc  jns     short loc_18002F9D3
0x18002f9be  mov     r9d, eax; char *
0x18002f9c1  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002f9c8  mov     edx, 0B6h; void *
0x18002f9cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f9d3  lea     rcx, [rbp+var_20]
0x18002f9d7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002f9dc  nop
0x18002f9dd  jmp     loc_18002FBC8
0x18002f9e2  mov     r8d, 10h; unsigned int
0x18002f9e8  lea     rdx, ?OpenFileLocation@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "OpenFileLocation"
0x18002f9ef  lea     rcx, [rsi+50h]; this
0x18002f9f3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002f9f8  mov     rcx, [rbp+28h]; this
0x18002f9fc  test    eax, eax
0x18002f9fe  jns     short loc_18002FA15
0x18002fa00  mov     r9d, eax; char *
0x18002fa03  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002fa0a  mov     edx, 0A0h; void *
0x18002fa0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fa15  test    bl, bl
0x18002fa17  jz      loc_18002FBD1
0x18002fa1d  lea     rcx, [rsi+60h]; this
0x18002fa21  mov     r8d, r15d; unsigned int
0x18002fa24  lea     rdx, ?OpenFileLocation@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; unsigned __int16 *
0x18002fa2b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002fa30  mov     rcx, [rbp+28h]; this
0x18002fa34  test    eax, eax
0x18002fa36  jns     short loc_18002FA4D
0x18002fa38  mov     r9d, eax; char *
0x18002fa3b  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002fa42  mov     edx, 0A4h; void *
0x18002fa47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fa4d  lea     rbx, [rsi+58h]
0x18002fa51  lea     rdx, [rsi+50h]
0x18002fa55  lea     rcx, [rbp+var_20]
0x18002fa59  call    ?from_string_abi@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@4@AEBVHString@Wrappers@WRL@Microsoft@@@Z; winrt::WindowsInternal::Shell::JumpList::from_string_abi(Microsoft::WRL::Wrappers::HString const &)
0x18002fa5e  nop
0x18002fa5f  mov     rcx, [rax]
0x18002fa62  test    rcx, rcx
0x18002fa65  jz      short loc_18002FA78
0x18002fa67  mov     rax, [rcx+10h]
0x18002fa6b  mov     [rbp+var_30], rax
0x18002fa6f  mov     eax, [rcx+4]
0x18002fa72  mov     [rbp+var_28], rax
0x18002fa76  jmp     short loc_18002FA8B
0x18002fa78  lea     rax, String1
0x18002fa7f  mov     [rbp+var_30], rax
0x18002fa83  mov     [rbp+var_28], 0
0x18002fa8b  lea     r8, [rbp+var_30]
0x18002fa8f  mov     edx, 838h
0x18002fa94  lea     rcx, [rbp+arg_10]
0x18002fa98  call    ?LoadStringResourceWithFallback@StringHelpers@JumpList@Shell@WindowsInternal@winrt@@YA?AUhstring@5@IAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::WindowsInternal::Shell::JumpList::StringHelpers::LoadStringResourceWithFallback(uint,std::basic_string_view<ushort> const &)
0x18002fa9d  nop
0x18002fa9e  mov     rdi, [rax]
0x18002faa1  test    rdi, rdi
0x18002faa4  jz      short loc_18002FAAD
0x18002faa6  xor     eax, eax
0x18002faa8  cmp     rdi, [rbx]
0x18002faab  jz      short loc_18002FAC9
0x18002faad  mov     rcx, [rbx]; string
0x18002fab0  call    cs:__imp_WindowsDeleteString
0x18002fab6  mov     qword ptr [rbx], 0
0x18002fabd  mov     rdx, rbx; newString
0x18002fac0  mov     rcx, rdi; string
0x18002fac3  call    cs:__imp_WindowsDuplicateString
0x18002fac9  mov     rcx, [rbp+28h]; this
0x18002facd  test    eax, eax
0x18002facf  jns     short loc_18002FAE6
0x18002fad1  mov     r9d, eax; char *
0x18002fad4  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002fadb  mov     edx, 0A7h; void *
0x18002fae0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fae6  lea     rcx, [rbp+arg_10]
0x18002faea  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002faef  nop
0x18002faf0  jmp     loc_18002F829
0x18002faf5  mov     r8d, 4; unsigned int
0x18002fafb  lea     rdx, ?Open@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Open"
0x18002fb02  lea     rcx, [rsi+50h]; this
0x18002fb06  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002fb0b  mov     rcx, [rbp+28h]; this
0x18002fb0f  test    eax, eax
0x18002fb11  jns     short loc_18002FB28
0x18002fb13  mov     r9d, eax; char *
0x18002fb16  lea     r8, aShellcommonShe_27; "shellcommon\\shell\\tiles\\jumplist\\li"...
0x18002fb1d  mov     edx, 91h; void *
0x18002fb22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fb28  test    bl, bl
0x18002fb2a  jz      loc_18002FBD1
0x18002fb30  lea     rcx, [rsi+60h]; this
0x18002fb34  mov     r8d, r15d; unsigned int
0x18002fb37  lea     rdx, ?Open@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; unsigned __int16 *
  ... truncated ...
```

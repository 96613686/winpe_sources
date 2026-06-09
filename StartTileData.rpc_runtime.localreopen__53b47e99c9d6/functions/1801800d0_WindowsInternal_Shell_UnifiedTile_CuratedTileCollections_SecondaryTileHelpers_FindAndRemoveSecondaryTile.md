# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileHelpers::FindAndRemoveSecondaryTile

- ea: `0x1801800d0`
- end: `0x1801804b5`
- name: `WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileHelpers::FindAndRemoveSecondaryTile`
- size: `997`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180181360`
- `0x1801cf2f0`
- `0x18024e1dc`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x18010aa74`
- `0x180161204`
- `0x18017ea00`
- `0x1801800d0`
- `0x1801804bc`
- `0x180201e50`
- `0x180232d58`
- `0x180232ee8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180180316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180180316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018010e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801802e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801803fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018043e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018044c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018010e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801802e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180180332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801803fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018043e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018044c`

## string_xrefs

- `0x180180132`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x180180174`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x1801801c4`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x18018020f`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x180180253`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x180180288`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x1801803e3`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x180180479`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x18018048e`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`
- `0x1801804a3`: `shellcommon\shell\tiles\inc\SecondaryTileHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
HRESULT __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SecondaryTileHelpers::FindAndRemoveSecondaryTile(
        __int64 a1,
        __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  int v13; // eax
  unsigned int i; // esi
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rbx
  int v28; // eax
  int v30; // [rsp+20h] [rbp-49h]
  _BYTE v31[8]; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string2; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v33; // [rsp+40h] [rbp-29h] BYREF
  INT32 result; // [rsp+44h] [rbp-25h] BYREF
  __int64 v35; // [rsp+48h] [rbp-21h] BYREF
  HSTRING string1; // [rsp+50h] [rbp-19h] BYREF
  HSTRING string; // [rsp+58h] [rbp-11h] BYREF
  __int64 v38; // [rsp+60h] [rbp-9h] BYREF
  __int64 *v39; // [rsp+68h] [rbp-1h] BYREF
  __int64 v40; // [rsp+70h] [rbp+7h] BYREF
  __int64 *v41; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+80h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v44; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v5,
      v30);
  string1 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 56LL);
  WindowsDeleteString(0);
  string1 = 0;
  v7 = v6(a1, &string1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v7,
      v30);
  v42 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.StartScreen.SecondaryTile",
    0x25u,
    0x24u);
  v8 = Windows::Foundation::GetActivationFactoryAsUser<Windows::UI::StartScreen::ISecondaryTileStatics>(v44, a2, &v42);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v8,
      v30);
  wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(
    &v42,
    &v41);
  v40 = 0;
  v9 = *v41;
  v40 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v9 + 48))(v41, string, &v40);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v10,
      v30);
  v39 = 0;
  v11 = v40;
  v12 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *>>(v40);
  if ( v12 >= 0 )
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v11 + 64LL))(v11, &v39);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v12,
      v30);
  v33 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v39 + 56))(v39, &v33);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
      (const char *)(unsigned int)v13,
      v30);
  for ( i = 0; i < v33; ++i )
  {
    v35 = 0;
    v15 = *v39;
    v35 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 48))(v39, i, &v35);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
        (const char *)(unsigned int)v16,
        v30);
    string2 = 0;
    v17 = v35;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 56LL);
    WindowsDeleteString(0);
    string2 = 0;
    v19 = v18(v17, &string2);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
        (const char *)(unsigned int)v19,
        v30);
    result = 0;
    v20 = WindowsCompareStringOrdinal(string1, string2, &result);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
        (const char *)(unsigned int)v20,
        v30);
    if ( !result )
    {
      LOBYTE(v21) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::GetImpl'::`2'::impl,
        v21);
      v38 = 0;
      v22 = *v41;
      v38 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, __int64 *))(v22 + 80))(v41, string, string2, &v38);
      v24 = retaddr;
      if ( v23 < 0 )
      {
        v25 = (unsigned int)v23;
        v26 = 48;
        goto LABEL_30;
      }
      v31[0] = 0;
      v27 = v38;
      v28 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v38);
      if ( v28 >= 0 )
        v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 64LL))(v27, v31);
      v24 = retaddr;
      if ( v28 < 0 )
      {
        v25 = (unsigned int)v28;
        v26 = 51;
        goto LABEL_30;
      }
      v24 = retaddr;
      if ( !v31[0] )
      {
        v25 = 2147500037LL;
        v26 = 53;
LABEL_30:
        wil::details::in1diag3::_Log_Hr(
          v24,
          (void *)v26,
          (unsigned int)"shellcommon\\shell\\tiles\\inc\\SecondaryTileHelpers.h",
          (const char *)v25,
          v30);
      }
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v38);
      WindowsDeleteString(string2);
      string2 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
      break;
    }
    WindowsDeleteString(string2);
    string2 = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v39);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v40);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v41);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v42);
  WindowsDeleteString(string1);
  string1 = 0;
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x1801800d0  mov     [rsp-8+arg_10], rbx
0x1801800d5  mov     [rsp-8+arg_18], rsi
0x1801800da  push    rbp
0x1801800db  push    rdi
0x1801800dc  push    r14
0x1801800de  lea     rbp, [rsp-47h]
0x1801800e3  sub     rsp, 0B0h
0x1801800ea  mov     rax, cs:__security_cookie
0x1801800f1  xor     rax, rsp
0x1801800f4  mov     [rbp+57h+var_18], rax
0x1801800f8  mov     rsi, rdx
0x1801800fb  mov     rdi, rcx
0x1801800fe  xor     r14d, r14d
0x180180101  mov     [rbp+57h+string], r14
0x180180105  mov     rax, [rcx]
0x180180108  mov     rbx, [rax+30h]
0x18018010c  xor     ecx, ecx; string
0x18018010e  call    cs:__imp_WindowsDeleteString
0x180180114  mov     [rbp+57h+string], r14
0x180180118  lea     rdx, [rbp+57h+string]
0x18018011c  mov     rcx, rdi
0x18018011f  mov     rax, rbx
0x180180122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180127  mov     rcx, [rbp+5Fh]; this
0x18018012b  test    eax, eax
0x18018012d  jns     short loc_180180143
0x18018012f  mov     r9d, eax; char *
0x180180132  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x180180139  lea     edx, [r14+12h]; void *
0x18018013d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180143  mov     [rbp+57h+string1], r14
0x180180147  mov     rax, [rdi]
0x18018014a  mov     rbx, [rax+38h]
0x18018014e  xor     ecx, ecx; string
0x180180150  call    cs:__imp_WindowsDeleteString
0x180180156  mov     [rbp+57h+string1], r14
0x18018015a  lea     rdx, [rbp+57h+string1]
0x18018015e  mov     rcx, rdi
0x180180161  mov     rax, rbx
0x180180164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180169  mov     rcx, [rbp+5Fh]; this
0x18018016d  test    eax, eax
0x18018016f  jns     short loc_180180186
0x180180171  mov     r9d, eax; char *
0x180180174  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x18018017b  mov     edx, 14h; void *
0x180180180  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180186  mov     [rbp+57h+var_40], r14
0x18018018a  mov     [rbp+57h+var_20], r14
0x18018018e  mov     r9d, 24h ; '$'; unsigned int
0x180180194  lea     r8d, [r9+1]; unsigned int
0x180180198  lea     rdx, ?RuntimeClass_Windows_UI_StartScreen_SecondaryTile@@3QBGB; "Windows.UI.StartScreen.SecondaryTile"
0x18018019f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801801a3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801801a8  nop
0x1801801a9  lea     r8, [rbp+57h+var_40]
0x1801801ad  mov     rdx, rsi
0x1801801b0  mov     rcx, [rbp+57h+var_20]
0x1801801b4  call    ??$GetActivationFactoryAsUser@UISecondaryTileStatics@StartScreen@UI@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUISecondaryTileStatics@StartScreen@UI@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::UI::StartScreen::ISecondaryTileStatics>(HSTRING__ *,Windows::System::IUser *,Windows::UI::StartScreen::ISecondaryTileStatics * *)
0x1801801b9  mov     rcx, [rbp+5Fh]; this
0x1801801bd  test    eax, eax
0x1801801bf  jns     short loc_1801801D6
0x1801801c1  mov     r9d, eax; char *
0x1801801c4  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x1801801cb  mov     edx, 17h; void *
0x1801801d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801801d6  lea     rdx, [rbp+57h+var_48]
0x1801801da  lea     rcx, [rbp+57h+var_40]
0x1801801de  call    ??$query@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@@?$com_ptr_t@UISecondaryTileStatics@StartScreen@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UISecondaryTileStaticsPrivate@StartScreen@UI@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::StartScreen::ISecondaryTileStatics,wil::err_exception_policy>::query<Windows::Internal::UI::StartScreen::ISecondaryTileStaticsPrivate>(void)
0x1801801e3  nop
0x1801801e4  mov     [rbp+57h+var_50], r14
0x1801801e8  mov     rcx, [rbp+57h+var_48]
0x1801801ec  mov     rax, [rcx]
0x1801801ef  mov     [rbp+57h+var_50], r14
0x1801801f3  lea     r8, [rbp+57h+var_50]
0x1801801f7  mov     rdx, [rbp+57h+string]
0x1801801fb  mov     rax, [rax+30h]
0x1801801ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180204  mov     rcx, [rbp+5Fh]; this
0x180180208  test    eax, eax
0x18018020a  jns     short loc_180180221
0x18018020c  mov     r9d, eax; char *
0x18018020f  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x180180216  mov     edx, 1Bh; void *
0x18018021b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180221  mov     [rbp+57h+var_58], r14
0x180180225  mov     rbx, [rbp+57h+var_50]
0x180180229  mov     rcx, rbx
0x18018022c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVSecondaryTile@StartScreen@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::UI::StartScreen::SecondaryTile *> *> *,tagCOWAIT_FLAGS,void *)
0x180180231  test    eax, eax
0x180180233  js      short loc_180180248
0x180180235  mov     rax, [rbx]
0x180180238  lea     rdx, [rbp+57h+var_58]
0x18018023c  mov     rcx, rbx
0x18018023f  mov     rax, [rax+40h]
0x180180243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180248  mov     rcx, [rbp+5Fh]; this
0x18018024c  test    eax, eax
0x18018024e  jns     short loc_180180265
0x180180250  mov     r9d, eax; char *
0x180180253  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x18018025a  mov     edx, 1Dh; void *
0x18018025f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180265  mov     [rbp+57h+var_80], r14d
0x180180269  mov     rcx, [rbp+57h+var_58]
0x18018026d  mov     rax, [rcx]
0x180180270  lea     rdx, [rbp+57h+var_80]
0x180180274  mov     rax, [rax+38h]
0x180180278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018027d  mov     rcx, [rbp+5Fh]; this
0x180180281  test    eax, eax
0x180180283  jns     short loc_18018029A
0x180180285  mov     r9d, eax; char *
0x180180288  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x18018028f  mov     edx, 20h ; ' '; void *
0x180180294  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018029a  mov     esi, r14d
0x18018029d  cmp     esi, [rbp+57h+var_80]
0x1801802a0  jnb     loc_180180412
0x1801802a6  mov     [rbp+57h+var_78], r14
0x1801802aa  mov     rcx, [rbp+57h+var_58]
0x1801802ae  mov     rax, [rcx]
0x1801802b1  mov     [rbp+57h+var_78], r14
0x1801802b5  lea     r8, [rbp+57h+var_78]
0x1801802b9  mov     edx, esi
0x1801802bb  mov     rax, [rax+30h]
0x1801802bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801802c4  mov     rcx, [rbp+5Fh]; this
0x1801802c8  test    eax, eax
0x1801802ca  js      loc_1801804A0
0x1801802d0  mov     [rbp+57h+string2], r14
0x1801802d4  mov     rdi, [rbp+57h+var_78]
0x1801802d8  mov     rax, [rdi]
0x1801802db  mov     rbx, [rax+38h]
0x1801802df  xor     ecx, ecx; string
0x1801802e1  call    cs:__imp_WindowsDeleteString
0x1801802e7  mov     [rbp+57h+string2], r14
0x1801802eb  lea     rdx, [rbp+57h+string2]
0x1801802ef  mov     rcx, rdi
0x1801802f2  mov     rax, rbx
0x1801802f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801802fa  mov     rcx, [rbp+5Fh]; this
0x1801802fe  test    eax, eax
0x180180300  js      loc_18018048B
0x180180306  mov     [rbp+57h+result], r14d
0x18018030a  lea     r8, [rbp+57h+result]; result
0x18018030e  mov     rdx, [rbp+57h+string2]; string2
0x180180312  mov     rcx, [rbp+57h+string1]; string1
0x180180316  call    cs:__imp_WindowsCompareStringOrdinal
0x18018031c  mov     rcx, [rbp+5Fh]; this
0x180180320  test    eax, eax
0x180180322  js      loc_180180476
0x180180328  cmp     [rbp+57h+result], r14d
0x18018032c  jz      short loc_18018034C
0x18018032e  mov     rcx, [rbp+57h+string2]; string
0x180180332  call    cs:__imp_WindowsDeleteString
0x180180338  mov     [rbp+57h+string2], r14
0x18018033c  lea     rcx, [rbp+57h+var_78]; void *
0x180180340  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180180345  inc     esi
0x180180347  jmp     loc_18018029D
0x18018034c  mov     dl, 1
0x18018034e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles> `wil::Feature<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::GetImpl(void)'::`2'::impl
0x180180355  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EdgePinnedSecondaryTiles>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18018035a  mov     [rbp+57h+var_60], r14
0x18018035e  mov     rcx, [rbp+57h+var_48]
0x180180362  mov     rax, [rcx]
0x180180365  mov     [rbp+57h+var_60], r14
0x180180369  lea     r9, [rbp+57h+var_60]
0x18018036d  mov     r8, [rbp+57h+string2]
0x180180371  mov     rdx, [rbp+57h+string]
0x180180375  mov     rax, [rax+50h]
0x180180379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018037e  mov     rcx, [rbp+5Fh]
0x180180382  test    eax, eax
0x180180384  jns     short loc_180180390
0x180180386  mov     r9d, eax
0x180180389  mov     edx, 30h ; '0'
0x18018038e  jmp     short loc_1801803E3
0x180180390  mov     [rbp+57h+var_90], r14b
0x180180394  mov     rbx, [rbp+57h+var_60]
0x180180398  mov     rcx, rbx
0x18018039b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)
0x1801803a0  test    eax, eax
0x1801803a2  js      short loc_1801803B7
0x1801803a4  mov     rax, [rbx]
0x1801803a7  lea     rdx, [rbp+57h+var_90]
0x1801803ab  mov     rcx, rbx
0x1801803ae  mov     rax, [rax+40h]
0x1801803b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801803b7  mov     rcx, [rbp+5Fh]
0x1801803bb  test    eax, eax
0x1801803bd  jns     short loc_1801803C9
0x1801803bf  mov     r9d, eax
0x1801803c2  mov     edx, 33h ; '3'
0x1801803c7  jmp     short loc_1801803E3
0x1801803c9  cmp     [rbp+57h+var_90], r14b
0x1801803cd  setnz   al
0x1801803d0  mov     rcx, [rbp+5Fh]; this
0x1801803d4  test    al, al
0x1801803d6  jnz     short loc_1801803F0
0x1801803d8  mov     r9d, 80004005h; char *
0x1801803de  mov     edx, 35h ; '5'; void *
0x1801803e3  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x1801803ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801803ef  nop
0x1801803f0  lea     rcx, [rbp+57h+var_60]; void *
0x1801803f4  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801803f9  nop
0x1801803fa  mov     rcx, [rbp+57h+string2]; string
0x1801803fe  call    cs:__imp_WindowsDeleteString
0x180180404  mov     [rbp+57h+string2], r14
0x180180408  lea     rcx, [rbp+57h+var_78]; void *
0x18018040c  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180180411  nop
0x180180412  lea     rcx, [rbp+57h+var_58]; void *
0x180180416  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18018041b  nop
0x18018041c  lea     rcx, [rbp+57h+var_50]; void *
0x180180420  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180180425  nop
0x180180426  lea     rcx, [rbp+57h+var_48]; void *
0x18018042a  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18018042f  nop
0x180180430  lea     rcx, [rbp+57h+var_40]; void *
0x180180434  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180180439  nop
0x18018043a  mov     rcx, [rbp+57h+string1]; string
0x18018043e  call    cs:__imp_WindowsDeleteString
0x180180444  mov     [rbp+57h+string1], r14
0x180180448  mov     rcx, [rbp+57h+string]; string
0x18018044c  call    cs:__imp_WindowsDeleteString
0x180180452  mov     rcx, [rbp+57h+var_18]
0x180180456  xor     rcx, rsp; StackCookie
0x180180459  call    __security_check_cookie
0x18018045e  lea     r11, [rsp+0C0h+var_10]
0x180180466  mov     rbx, [r11+30h]
0x18018046a  mov     rsi, [r11+38h]
0x18018046e  mov     rsp, r11
0x180180471  pop     r14
0x180180473  pop     rdi
0x180180474  pop     rbp
0x180180475  retn
0x180180476  mov     r9d, eax; char *
0x180180479  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x180180480  mov     edx, 2Ah ; '*'; void *
0x180180485  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018048b  mov     r9d, eax; char *
0x18018048e  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x180180495  mov     edx, 27h ; '''; void *
0x18018049a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801804a0  mov     r9d, eax; char *
0x1801804a3  lea     r8, aShellcommonShe_212; "shellcommon\\shell\\tiles\\inc\\Seconda"...
0x1801804aa  mov     edx, 24h ; '$'; void *
0x1801804af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# WindowsInternal::Shell::UnifiedTile::DesktopIconImageResource::LoadInternal(Windows::Foundation::Size const &,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x1800823f8`
- end: `0x180082725`
- name: `?LoadInternal@DesktopIconImageResource@UnifiedTile@Shell@WindowsInternal@@AEBAJAEBUSize@Foundation@Windows@@PEAPEAUIRandomAccessStream@Streams@Storage@7@@Z`
- size: `813`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::DesktopIconImageResource *__hidden this, const struct Windows::Foundation::Size *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1802e7008`
- `0x1802e98d0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800823f8`
- `0x18008272c`
- `0x18008277c`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082615`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800824ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800825a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800824ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800825a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082704`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008246f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008246f`

## string_xrefs

- `0x180082623`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x18008269d`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x1800826d5`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`
- `0x1800826ef`: `shellcommon\shell\tiles\unifiedtilemodel\lib\tileimageresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::DesktopIconImageResource::LoadInternal(
        WindowsInternal::Shell::UnifiedTile::DesktopIconImageResource *this,
        const struct Windows::Foundation::Size *a2,
        struct Windows::Storage::Streams::IRandomAccessStream **a3)
{
  HRESULT v6; // eax
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, unsigned __int64, HSTRING, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-60h]
  __int64 v29; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v30; // [rsp+38h] [rbp-48h] BYREF
  __int64 v31; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  v29 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.Shell.StartUI.TileImageHelpers", 0x2Fu, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_fafd0ef2_a207_43c0_8134_23e35b2b9099, &v29);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    v27 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return v9;
  }
  v32 = 0;
  v10 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
          (char *)this + 72,
          &v32);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
      (const char *)(unsigned int)v10,
      v28);
LABEL_34:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    return v9;
  }
  v30 = 0;
  v11 = v32;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
  WindowsDeleteString(0);
  v30 = 0;
  v13 = v12(v11, &v30);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
      (const char *)(unsigned int)v13,
      v28);
    WindowsDeleteString(v30);
    v30 = 0;
    goto LABEL_34;
  }
  v31 = 0;
  v14 = v29;
  v15 = *(__int64 (__fastcall **)(__int64, unsigned __int64, HSTRING, __int64 *))(*(_QWORD *)v29 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v16 = v15(v14, _mm_unpacklo_ps((__m128)*(unsigned int *)a2, (__m128)*((unsigned int *)a2 + 1)).m128_u64[0], v30, &v31);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\tileimageresource.cpp",
      (const char *)(unsigned int)v16,
      v28);
    v24 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    WindowsDeleteString(v30);
    v30 = 0;
    v25 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return v9;
  }
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Storage::Streams::IRandomAccessStream * *>(
         v31,
         a3);
  if ( (v9 & 0x80000000) != 0 )
  {
    v21 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    WindowsDeleteString(v30);
    v30 = 0;
    v22 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v9;
  }
  v17 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  WindowsDeleteString(v30);
  v30 = 0;
  v18 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1800823f8  mov     [rsp-28h+arg_18], rbx
0x1800823fd  push    rbp
0x1800823fe  push    rsi
0x1800823ff  push    rdi
0x180082400  push    r14
0x180082402  push    r15
0x180082404  mov     rbp, rsp
0x180082407  sub     rsp, 80h
0x18008240e  mov     rax, cs:__security_cookie
0x180082415  xor     rax, rsp
0x180082418  mov     [rbp+var_10], rax
0x18008241c  mov     rsi, r8
0x18008241f  mov     r14, rdx
0x180082422  mov     rdi, rcx
0x180082425  xor     r15d, r15d
0x180082428  mov     [r8], r15
0x18008242b  mov     [rbp+var_50], r15
0x18008242f  mov     [rbp+string], r15
0x180082433  lea     r9, [rbp+string]; string
0x180082437  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18008243b  lea     edx, [r15+2Fh]; length
0x18008243f  lea     rcx, ?RuntimeClass_Windows_Internal_Shell_StartUI_TileImageHelpers@@3QBGB; "Windows.Internal.Shell.StartUI.TileImag"...
0x180082446  call    cs:__imp_WindowsCreateStringReference
0x18008244c  test    eax, eax
0x18008244e  js      loc_180082609
0x180082454  mov     rbx, [rbp+string]
0x180082458  lea     rcx, [rbp+var_50]
0x18008245c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082461  lea     r8, [rbp+var_50]
0x180082465  lea     rdx, _GUID_fafd0ef2_a207_43c0_8134_23e35b2b9099
0x18008246c  mov     rcx, rbx
0x18008246f  call    cs:__imp_RoGetActivationFactory
0x180082475  mov     ebx, eax
0x180082477  test    eax, eax
0x180082479  js      loc_180082696
0x18008247f  mov     [rbp+var_38], r15
0x180082483  lea     rcx, [rdi+48h]
0x180082487  lea     rdx, [rbp+var_38]
0x18008248b  call    ??$As@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>>)
0x180082490  mov     ebx, eax
0x180082492  test    eax, eax
0x180082494  js      loc_1800826CE
0x18008249a  mov     [rbp+var_48], r15
0x18008249e  mov     rdi, [rbp+var_38]
0x1800824a2  mov     rax, [rdi]
0x1800824a5  mov     rbx, [rax+30h]
0x1800824a9  xor     ecx, ecx; string
0x1800824ab  call    cs:__imp_WindowsDeleteString
0x1800824b1  mov     [rbp+var_48], r15
0x1800824b5  lea     rdx, [rbp+var_48]
0x1800824b9  mov     rcx, rdi
0x1800824bc  mov     rax, rbx
0x1800824bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800824c4  mov     ebx, eax
0x1800824c6  test    eax, eax
0x1800824c8  js      loc_1800826E8
0x1800824ce  mov     [rbp+var_40], r15
0x1800824d2  mov     rdi, [rbp+var_50]
0x1800824d6  mov     rax, [rdi]
0x1800824d9  mov     rbx, [rax+38h]
0x1800824dd  lea     rcx, [rbp+var_40]
0x1800824e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800824e6  movss   xmm1, dword ptr [r14]
0x1800824eb  movss   xmm0, dword ptr [r14+4]
0x1800824f1  lea     r9, [rbp+var_40]
0x1800824f5  mov     r8, [rbp+var_48]
0x1800824f9  unpcklps xmm1, xmm0
0x1800824fc  movq    rdx, xmm1
0x180082501  mov     rcx, rdi
0x180082504  mov     rax, rbx
0x180082507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008250c  mov     ebx, eax
0x18008250e  test    eax, eax
0x180082510  js      loc_18008261C
0x180082516  mov     rdx, rsi
0x180082519  mov     rcx, [rbp+var_40]
0x18008251d  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@PEAPEAUIRandomAccessStream@Streams@Storage@3@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@PEAPEAUIRandomAccessStream@Streams@Storage@4@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Storage::Streams::IRandomAccessStream * *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Storage::Streams::IRandomAccessStream * *,tagCOWAIT_FLAGS,ulong,bool *)
0x180082522  mov     ebx, eax
0x180082524  test    eax, eax
0x180082526  js      short loc_180082588
0x180082528  mov     rcx, [rbp+var_40]
0x18008252c  test    rcx, rcx
0x18008252f  jz      short loc_180082542
0x180082531  mov     [rbp+var_40], r15
0x180082535  mov     rax, [rcx]
0x180082538  mov     rax, [rax+10h]
0x18008253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082541  nop
0x180082542  mov     rcx, [rbp+var_48]; string
0x180082546  call    cs:__imp_WindowsDeleteString
0x18008254c  mov     [rbp+var_48], r15
0x180082550  mov     rcx, [rbp+var_38]
0x180082554  test    rcx, rcx
0x180082557  jz      short loc_18008256A
0x180082559  mov     [rbp+var_38], r15
0x18008255d  mov     rax, [rcx]
0x180082560  mov     rax, [rax+10h]
0x180082564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082569  nop
0x18008256a  mov     rcx, [rbp+var_50]
0x18008256e  test    rcx, rcx
0x180082571  jz      short loc_180082584
0x180082573  mov     [rbp+var_50], r15
0x180082577  mov     rax, [rcx]
0x18008257a  mov     rax, [rax+10h]
0x18008257e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082583  nop
0x180082584  xor     eax, eax
0x180082586  jmp     short loc_1800825E6
0x180082588  mov     rcx, [rbp+var_40]
0x18008258c  test    rcx, rcx
0x18008258f  jz      short loc_1800825A2
0x180082591  mov     [rbp+var_40], r15
0x180082595  mov     rdx, [rcx]
0x180082598  mov     rax, [rdx+10h]
0x18008259c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800825a1  nop
0x1800825a2  mov     rcx, [rbp+var_48]; string
0x1800825a6  call    cs:__imp_WindowsDeleteString
0x1800825ac  mov     [rbp+var_48], r15
0x1800825b0  mov     rcx, [rbp+var_38]
0x1800825b4  test    rcx, rcx
0x1800825b7  jz      short loc_1800825CA
0x1800825b9  mov     [rbp+var_38], r15
0x1800825bd  mov     rax, [rcx]
0x1800825c0  mov     rax, [rax+10h]
0x1800825c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800825c9  nop
0x1800825ca  mov     rcx, [rbp+var_50]
0x1800825ce  test    rcx, rcx
0x1800825d1  jz      short loc_1800825E4
0x1800825d3  mov     [rbp+var_50], r15
0x1800825d7  mov     rax, [rcx]
0x1800825da  mov     rax, [rax+10h]
0x1800825de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800825e3  nop
0x1800825e4  mov     eax, ebx
0x1800825e6  mov     rcx, [rbp+var_10]
0x1800825ea  xor     rcx, rsp; StackCookie
0x1800825ed  call    __security_check_cookie
0x1800825f2  mov     rbx, [rsp+80h+arg_18]
0x1800825fa  add     rsp, 80h
0x180082601  pop     r15
0x180082603  pop     r14
0x180082605  pop     rdi
0x180082606  pop     rsi
0x180082607  pop     rbp
0x180082608  retn
0x180082609  xor     r9d, r9d; lpArguments
0x18008260c  xor     r8d, r8d; nNumberOfArguments
0x18008260f  lea     edx, [r9+1]; dwExceptionFlags
0x180082613  mov     ecx, eax; dwExceptionCode
0x180082615  call    cs:__imp_RaiseException
0x18008261b  int     3; Trap to Debugger
0x18008261c  mov     rcx, [rbp+28h]; this
0x180082620  mov     r9d, ebx; char *
0x180082623  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18008262a  mov     edx, 0DEh; void *
0x18008262f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082634  nop
0x180082635  mov     rcx, [rbp+var_40]
0x180082639  test    rcx, rcx
0x18008263c  jz      short loc_18008264F
0x18008263e  mov     [rbp+var_40], r15
0x180082642  mov     rax, [rcx]
0x180082645  mov     rax, [rax+10h]
0x180082649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008264e  nop
0x18008264f  mov     rcx, [rbp+var_48]; string
0x180082653  call    cs:__imp_WindowsDeleteString
0x180082659  mov     [rbp+var_48], r15
0x18008265d  mov     rcx, [rbp+var_38]
0x180082661  test    rcx, rcx
0x180082664  jz      short loc_180082677
0x180082666  mov     [rbp+var_38], r15
0x18008266a  mov     rax, [rcx]
0x18008266d  mov     rax, [rax+10h]
0x180082671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082676  nop
0x180082677  mov     rcx, [rbp+var_50]
0x18008267b  test    rcx, rcx
0x18008267e  jz      short loc_180082691
0x180082680  mov     [rbp+var_50], r15
0x180082684  mov     rax, [rcx]
0x180082687  mov     rax, [rax+10h]
0x18008268b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082690  nop
0x180082691  jmp     loc_1800825E4
0x180082696  mov     rcx, [rbp+28h]; this
0x18008269a  mov     r9d, ebx; char *
0x18008269d  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800826a4  mov     edx, 0D5h; void *
0x1800826a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800826ae  nop
0x1800826af  mov     rcx, [rbp+var_50]
0x1800826b3  test    rcx, rcx
0x1800826b6  jz      short loc_1800826C9
0x1800826b8  mov     [rbp+var_50], r15
0x1800826bc  mov     rax, [rcx]
0x1800826bf  mov     rax, [rax+10h]
0x1800826c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826c8  nop
0x1800826c9  jmp     loc_1800825E4
0x1800826ce  mov     rcx, [rbp+28h]; this
0x1800826d2  mov     r9d, eax; char *
0x1800826d5  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800826dc  mov     edx, 0D8h; void *
0x1800826e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800826e6  jmp     short loc_18008270E
0x1800826e8  mov     rcx, [rbp+28h]; this
0x1800826ec  mov     r9d, eax; char *
0x1800826ef  lea     r8, aShellcommonShe_233; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800826f6  mov     edx, 0DBh; void *
0x1800826fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082700  mov     rcx, [rbp+var_48]; string
0x180082704  call    cs:__imp_WindowsDeleteString
0x18008270a  mov     [rbp+var_48], r15
0x18008270e  lea     rcx, [rbp+var_38]
0x180082712  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082717  lea     rcx, [rbp+var_50]
0x18008271b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082720  jmp     loc_1800825E4
```

# WindowsInternal::Shell::UnifiedTile::Private::CopyVerbEnumerationArgs(WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs * *)

- ea: `0x180123b1c`
- end: `0x180123f40`
- name: `?CopyVerbEnumerationArgs@Private@UnifiedTile@Shell@WindowsInternal@@YAJPEAUIVerbEnumerationArgs@234@PEAPEAU5234@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::Private *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1802db560`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180123b1c`
- `0x18012be74`
- `0x1801a7468`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180123b7c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180123b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180123b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180123b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123f07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123ec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123f07`

## string_xrefs

- `0x180123bc1`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123c10`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123c5b`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123cb9`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123d02`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123df3`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123e27`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`
- `0x180123e90`: `ShellCommon\internal\Shell\inc\Private\TileVerbProviderUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::CopyVerbEnumerationArgs(
        WindowsInternal::Shell::UnifiedTile::Private *this,
        struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *a2,
        struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs **a3)
{
  HRESULT v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *); // rbx
  __int64 (__fastcall *v20)(WindowsInternal::Shell::UnifiedTile::Private *, GUID *, __int64 *); // rbx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v28; // rax
  HSTRING v29; // [rsp+20h] [rbp-60h] BYREF
  __int64 v30; // [rsp+28h] [rbp-58h] BYREF
  __int64 v31; // [rsp+30h] [rbp-50h] BYREF
  __int64 v32; // [rsp+38h] [rbp-48h] BYREF
  __int64 v33; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v30 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"WindowsInternal.Shell.UnifiedTile.VerbEnumerationArgs",
         0x35u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>>(
         string,
         &v30);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 16;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v6,
      (int)v29);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    return v7;
  }
  v34 = 0;
  v9 = (*(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private *, unsigned int *))(*(_QWORD *)this + 48LL))(
         this,
         &v34);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v9,
      (int)v29);
    v10 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v7;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 56LL))(v30, v34);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 21;
    goto LABEL_11;
  }
  v29 = 0;
  v11 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *))(*(_QWORD *)this + 64LL);
  WindowsDeleteString(0);
  v29 = 0;
  v12 = v11(this, &v29);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v12,
      (int)v29);
    WindowsDeleteString(v29);
    v29 = 0;
    v13 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v7;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 72LL))(v30, v29);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 25;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v14,
      (int)v29);
LABEL_40:
    WindowsDeleteString(v29);
    v29 = 0;
    goto LABEL_41;
  }
  v16 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(v29);
  v29 = 0;
  v17 = v16(this, &v29);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v17,
      (int)v29);
    WindowsDeleteString(v29);
    v29 = 0;
    v18 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v7;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 88LL))(v30, v29);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 28;
    goto LABEL_18;
  }
  v19 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private *, HSTRING *))(*(_QWORD *)this + 96LL);
  WindowsDeleteString(v29);
  v29 = 0;
  v14 = v19(this, &v29);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 30;
    goto LABEL_18;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 104LL))(v30, v29);
  v7 = v14;
  if ( v14 < 0 )
  {
    v15 = 31;
    goto LABEL_18;
  }
  v31 = 0;
  v20 = **(__int64 (__fastcall ***)(WindowsInternal::Shell::UnifiedTile::Private *, GUID *, __int64 *))this;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v21 = v20(this, &GUID_3b8c9be7_fc8c_42e2_a6b5_7005aa719c35, &v31);
  v7 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v21,
      (int)v29);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    goto LABEL_40;
  }
  v33 = 0;
  v22 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>::As<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>(
          &v30,
          &v33);
  v7 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v22,
      (int)v29);
LABEL_38:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    goto LABEL_39;
  }
  v32 = 0;
  v23 = v31;
  v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v25 = v24(v23, &v32);
  v7 = v25;
  if ( v25 < 0 )
  {
    v26 = 40;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileVerbProviderUtils.h",
      (const char *)(unsigned int)v25,
      (int)v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    goto LABEL_38;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 80LL))(v33, v32);
  v7 = v25;
  if ( v25 < 0 )
  {
    v26 = 41;
    goto LABEL_37;
  }
  v28 = v30;
  v30 = 0;
  *(_QWORD *)a2 = v28;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  WindowsDeleteString(v29);
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return 0;
}

```

## disassembly

```asm
0x180123b1c  mov     [rsp-18h+arg_10], rbx
0x180123b21  mov     [rsp-18h+arg_18], rsi
0x180123b26  push    rbp
0x180123b27  push    rdi
0x180123b28  push    r14
0x180123b2a  mov     rbp, rsp
0x180123b2d  sub     rsp, 80h
0x180123b34  mov     rax, cs:__security_cookie
0x180123b3b  xor     rax, rsp
0x180123b3e  mov     [rbp+var_10], rax
0x180123b42  mov     rsi, rdx
0x180123b45  mov     rdi, rcx
0x180123b48  xor     r14d, r14d
0x180123b4b  mov     [rbp+var_58], r14
0x180123b4f  mov     [rbp+string], r14
0x180123b53  lea     r9, [rbp+string]; string
0x180123b57  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180123b5b  lea     edx, [r14+35h]; length
0x180123b5f  lea     rcx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_VerbEnumerationArgs@@3QBGB; "WindowsInternal.Shell.UnifiedTile.VerbE"...
0x180123b66  call    cs:__imp_WindowsCreateStringReference
0x180123b6c  test    eax, eax
0x180123b6e  jns     short loc_180123B83
0x180123b70  xor     r9d, r9d; lpArguments
0x180123b73  xor     r8d, r8d; nNumberOfArguments
0x180123b76  lea     edx, [r14+1]; dwExceptionFlags
0x180123b7a  mov     ecx, eax; dwExceptionCode
0x180123b7c  call    cs:__imp_RaiseException
0x180123b82  int     3; Trap to Debugger
0x180123b83  lea     rdx, [rbp+var_58]
0x180123b87  mov     rcx, [rbp+string]
0x180123b8b  call    ??$ActivateInstance@V?$ComPtr@UIVerbEnumerationArgs@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIVerbEnumerationArgs@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>>)
0x180123b90  mov     ebx, eax
0x180123b92  test    eax, eax
0x180123b94  jns     short loc_180123B9D
0x180123b96  mov     edx, 10h
0x180123b9b  jmp     short loc_180123C10
0x180123b9d  mov     [rbp+var_38], r14d
0x180123ba1  mov     rax, [rdi]
0x180123ba4  lea     rdx, [rbp+var_38]
0x180123ba8  mov     rcx, rdi
0x180123bab  mov     rax, [rax+30h]
0x180123baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123bb4  mov     ebx, eax
0x180123bb6  test    eax, eax
0x180123bb8  jns     short loc_180123BF2
0x180123bba  mov     rcx, [rbp+18h]; this
0x180123bbe  mov     r9d, eax; char *
0x180123bc1  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123bc8  mov     edx, 14h; void *
0x180123bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123bd2  nop
0x180123bd3  mov     rcx, [rbp+var_58]
0x180123bd7  test    rcx, rcx
0x180123bda  jz      short loc_180123BED
0x180123bdc  mov     [rbp+var_58], r14
0x180123be0  mov     rax, [rcx]
0x180123be3  mov     rax, [rax+10h]
0x180123be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123bec  nop
0x180123bed  jmp     loc_180123ED6
0x180123bf2  mov     rcx, [rbp+var_58]
0x180123bf6  mov     rax, [rcx]
0x180123bf9  mov     edx, [rbp+var_38]
0x180123bfc  mov     rax, [rax+38h]
0x180123c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123c05  mov     ebx, eax
0x180123c07  test    eax, eax
0x180123c09  jns     short loc_180123C28
0x180123c0b  mov     edx, 15h; void *
0x180123c10  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123c17  mov     r9d, eax; char *
0x180123c1a  mov     rcx, [rbp+18h]; this
0x180123c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123c23  jmp     loc_180123ECD
0x180123c28  mov     [rbp+var_60], r14
0x180123c2c  mov     rax, [rdi]
0x180123c2f  mov     rbx, [rax+40h]
0x180123c33  xor     ecx, ecx; string
0x180123c35  call    cs:__imp_WindowsDeleteString
0x180123c3b  mov     [rbp+var_60], r14
0x180123c3f  lea     rdx, [rbp+var_60]
0x180123c43  mov     rcx, rdi
0x180123c46  mov     rax, rbx
0x180123c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123c4e  mov     ebx, eax
0x180123c50  test    eax, eax
0x180123c52  jns     short loc_180123C9A
0x180123c54  mov     rcx, [rbp+18h]; this
0x180123c58  mov     r9d, eax; char *
0x180123c5b  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123c62  mov     edx, 18h; void *
0x180123c67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123c6c  nop
0x180123c6d  mov     rcx, [rbp+var_60]; string
0x180123c71  call    cs:__imp_WindowsDeleteString
0x180123c77  mov     [rbp+var_60], r14
0x180123c7b  mov     rcx, [rbp+var_58]
0x180123c7f  test    rcx, rcx
0x180123c82  jz      short loc_180123C95
0x180123c84  mov     [rbp+var_58], r14
0x180123c88  mov     rax, [rcx]
0x180123c8b  mov     rax, [rax+10h]
0x180123c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123c94  nop
0x180123c95  jmp     loc_180123ED6
0x180123c9a  mov     rcx, [rbp+var_58]
0x180123c9e  mov     rax, [rcx]
0x180123ca1  mov     rdx, [rbp+var_60]
0x180123ca5  mov     rax, [rax+48h]
0x180123ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123cae  mov     ebx, eax
0x180123cb0  test    eax, eax
0x180123cb2  jns     short loc_180123CD1
0x180123cb4  mov     edx, 19h; void *
0x180123cb9  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123cc0  mov     r9d, eax; char *
0x180123cc3  mov     rcx, [rbp+18h]; this
0x180123cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123ccc  jmp     loc_180123EBF
0x180123cd1  mov     rax, [rdi]
0x180123cd4  mov     rbx, [rax+50h]
0x180123cd8  mov     rcx, [rbp+var_60]; string
0x180123cdc  call    cs:__imp_WindowsDeleteString
0x180123ce2  mov     [rbp+var_60], r14
0x180123ce6  lea     rdx, [rbp+var_60]
0x180123cea  mov     rcx, rdi
0x180123ced  mov     rax, rbx
0x180123cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123cf5  mov     ebx, eax
0x180123cf7  test    eax, eax
0x180123cf9  jns     short loc_180123D41
0x180123cfb  mov     rcx, [rbp+18h]; this
0x180123cff  mov     r9d, eax; char *
0x180123d02  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123d09  mov     edx, 1Bh; void *
0x180123d0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123d13  nop
0x180123d14  mov     rcx, [rbp+var_60]; string
0x180123d18  call    cs:__imp_WindowsDeleteString
0x180123d1e  mov     [rbp+var_60], r14
0x180123d22  mov     rcx, [rbp+var_58]
0x180123d26  test    rcx, rcx
0x180123d29  jz      short loc_180123D3C
0x180123d2b  mov     [rbp+var_58], r14
0x180123d2f  mov     rax, [rcx]
0x180123d32  mov     rax, [rax+10h]
0x180123d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123d3b  nop
0x180123d3c  jmp     loc_180123ED6
0x180123d41  mov     rcx, [rbp+var_58]
0x180123d45  mov     rax, [rcx]
0x180123d48  mov     rdx, [rbp+var_60]
0x180123d4c  mov     rax, [rax+58h]
0x180123d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123d55  mov     ebx, eax
0x180123d57  test    eax, eax
0x180123d59  jns     short loc_180123D65
0x180123d5b  mov     edx, 1Ch
0x180123d60  jmp     loc_180123CB9
0x180123d65  mov     rax, [rdi]
0x180123d68  mov     rbx, [rax+60h]
0x180123d6c  mov     rcx, [rbp+var_60]; string
0x180123d70  call    cs:__imp_WindowsDeleteString
0x180123d76  mov     [rbp+var_60], r14
0x180123d7a  lea     rdx, [rbp+var_60]
0x180123d7e  mov     rcx, rdi
0x180123d81  mov     rax, rbx
0x180123d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123d89  mov     ebx, eax
0x180123d8b  test    eax, eax
0x180123d8d  jns     short loc_180123D99
0x180123d8f  mov     edx, 1Eh
0x180123d94  jmp     loc_180123CB9
0x180123d99  mov     rcx, [rbp+var_58]
0x180123d9d  mov     rax, [rcx]
0x180123da0  mov     rdx, [rbp+var_60]
0x180123da4  mov     rax, [rax+68h]
0x180123da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123dad  mov     ebx, eax
0x180123daf  test    eax, eax
0x180123db1  jns     short loc_180123DBD
0x180123db3  mov     edx, 1Fh
0x180123db8  jmp     loc_180123CB9
0x180123dbd  mov     [rbp+var_50], r14
0x180123dc1  mov     rax, [rdi]
0x180123dc4  mov     rbx, [rax]
0x180123dc7  lea     rcx, [rbp+var_50]
0x180123dcb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123dd0  lea     r8, [rbp+var_50]
0x180123dd4  lea     rdx, _GUID_3b8c9be7_fc8c_42e2_a6b5_7005aa719c35
0x180123ddb  mov     rcx, rdi
0x180123dde  mov     rax, rbx
0x180123de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123de6  mov     ebx, eax
0x180123de8  test    eax, eax
0x180123dea  jns     short loc_180123E09
0x180123dec  mov     rcx, [rbp+18h]; this
0x180123df0  mov     r9d, eax; char *
0x180123df3  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123dfa  mov     edx, 22h ; '"'; void *
0x180123dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123e04  jmp     loc_180123EB5
0x180123e09  mov     [rbp+var_40], r14
0x180123e0d  lea     rdx, [rbp+var_40]
0x180123e11  lea     rcx, [rbp+var_58]
0x180123e15  call    ??$As@UIVerbEnumerationArgsPrivate@Private@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIVerbEnumerationArgs@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVerbEnumerationArgsPrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>::As<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>>)
0x180123e1a  mov     ebx, eax
0x180123e1c  test    eax, eax
0x180123e1e  jns     short loc_180123E3A
0x180123e20  mov     rcx, [rbp+18h]; this
0x180123e24  mov     r9d, eax; char *
0x180123e27  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123e2e  mov     edx, 25h ; '%'; void *
0x180123e33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123e38  jmp     short loc_180123EAB
0x180123e3a  mov     [rbp+var_48], r14
0x180123e3e  mov     rdi, [rbp+var_50]
0x180123e42  mov     rax, [rdi]
0x180123e45  mov     rbx, [rax+48h]
0x180123e49  lea     rcx, [rbp+var_48]
0x180123e4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123e52  lea     rdx, [rbp+var_48]
0x180123e56  mov     rcx, rdi
0x180123e59  mov     rax, rbx
0x180123e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123e61  mov     ebx, eax
0x180123e63  test    eax, eax
0x180123e65  jns     short loc_180123E6E
0x180123e67  mov     edx, 28h ; '('
0x180123e6c  jmp     short loc_180123E8D
0x180123e6e  mov     rcx, [rbp+var_40]
0x180123e72  mov     rax, [rcx]
0x180123e75  mov     rdx, [rbp+var_48]
0x180123e79  mov     rax, [rax+50h]
0x180123e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123e82  mov     ebx, eax
0x180123e84  test    eax, eax
0x180123e86  jns     short loc_180123EDA
0x180123e88  mov     edx, 29h ; ')'; void *
0x180123e8d  mov     r9d, eax; char *
0x180123e90  lea     r8, aShellcommonInt_1; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x180123e97  mov     rcx, [rbp+18h]; this
0x180123e9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123ea0  nop
0x180123ea1  lea     rcx, [rbp+var_48]
0x180123ea5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123eaa  nop
0x180123eab  lea     rcx, [rbp+var_40]
0x180123eaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123eb4  nop
0x180123eb5  lea     rcx, [rbp+var_50]
0x180123eb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123ebe  nop
0x180123ebf  mov     rcx, [rbp+var_60]; string
0x180123ec3  call    cs:__imp_WindowsDeleteString
0x180123ec9  mov     [rbp+var_60], r14
0x180123ecd  lea     rcx, [rbp+var_58]
0x180123ed1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123ed6  mov     eax, ebx
0x180123ed8  jmp     short loc_180123F1C
0x180123eda  mov     rax, [rbp+var_58]
0x180123ede  mov     [rbp+var_58], r14
0x180123ee2  mov     [rsi], rax
0x180123ee5  lea     rcx, [rbp+var_48]
0x180123ee9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123eee  nop
0x180123eef  lea     rcx, [rbp+var_40]
0x180123ef3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123ef8  nop
0x180123ef9  lea     rcx, [rbp+var_50]
0x180123efd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123f02  nop
0x180123f03  mov     rcx, [rbp+var_60]; string
0x180123f07  call    cs:__imp_WindowsDeleteString
0x180123f0d  mov     [rbp+var_60], r14
0x180123f11  lea     rcx, [rbp+var_58]
0x180123f15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180123f1a  xor     eax, eax
0x180123f1c  mov     rcx, [rbp+var_10]
0x180123f20  xor     rcx, rsp; StackCookie
0x180123f23  call    __security_check_cookie
0x180123f28  lea     r11, [rsp+80h+var_s0]
0x180123f30  mov     rbx, [r11+30h]
0x180123f34  mov     rsi, [r11+38h]
0x180123f38  mov     rsp, r11
0x180123f3b  pop     r14
0x180123f3d  pop     rdi
0x180123f3e  pop     rbp
0x180123f3f  retn
```

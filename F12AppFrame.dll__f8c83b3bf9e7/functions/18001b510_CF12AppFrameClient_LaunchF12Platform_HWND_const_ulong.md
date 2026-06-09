# CF12AppFrameClient::LaunchF12Platform(HWND__ * const,ulong)

- ea: `0x18001b510`
- end: `0x18001ba3a`
- name: `?LaunchF12Platform@CF12AppFrameClient@@UEAAJQEAUHWND__@@K@Z`
- size: `1322`
- prototype: `__int64 __fastcall(CF12AppFrameClient *this, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001800`
- `0x180006e00`
- `0x18001a874`
- `0x18001b510`
- `0x18001c4c4`
- `0x18001d1bc`
- `0x18001ddd8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b672`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b780`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b672`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001b5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001b5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b5c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b5dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b96b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b5c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b5dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b96b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b746`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x18001b547`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x18001b547`

## string_xrefs

- `0x18001b631`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall CF12AppFrameClient::LaunchF12Platform(CF12AppFrameClient *this, HWND a2, unsigned int a3)
{
  unsigned int F12Chooser; // esi
  const wchar_t *v6; // rdi
  unsigned __int64 v7; // rbx
  UINT32 v8; // edx
  const WCHAR *v9; // rcx
  HRESULT v10; // ebx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int ActivationFactory; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  HSTRING v22; // rbx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // rcx
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-58h] BYREF
  __int64 v47; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v49; // [rsp+40h] [rbp-40h] BYREF
  int v50; // [rsp+48h] [rbp-38h] BYREF
  __int64 v51; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING v53; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v50 = 0;
  F12Chooser = IsDeveloperModeEnabled(&v50);
  if ( (F12Chooser & 0x80000000) != 0 )
    return F12Chooser;
  if ( !v50 )
    return F12Chooser;
  F12Chooser = TryLaunchStoreApp(a2, a3);
  if ( !F12Chooser )
    return F12Chooser;
  F12Chooser = TryLoadF12Chooser(a2, a3);
  if ( !F12Chooser )
    return F12Chooser;
  string = 0;
  v6 = L"https://go.microsoft.com/fwlink/?linkid=861967";
  if ( !(unsigned int)IsInternal() )
    v6 = L"https://go.microsoft.com/fwlink/?linkid=861968";
  if ( !v6 )
  {
    WindowsDeleteString(string);
    v8 = 0;
    v9 = &String;
    goto LABEL_14;
  }
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  if ( v7 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(string);
    v8 = v7;
    v9 = v6;
LABEL_14:
    string = 0;
    v10 = WindowsCreateString(v9, v8, &string);
    goto LABEL_15;
  }
  v10 = -2147024362;
LABEL_15:
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v10,
      v45);
LABEL_60:
    WindowsDeleteString(string);
    return (unsigned int)v10;
  }
  v45 = 0;
  v53 = 0;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &v53);
  if ( v11 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    JUMPOUT(0x18001BA39LL);
  }
  ActivationFactory = RoGetActivationFactory(v53, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v45);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v45);
    v15 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_60;
  }
  v47 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, string, &v47);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v16,
      v45);
    v17 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    goto LABEL_60;
  }
  v46 = 0;
  v53 = 0;
  v19 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &v53);
  if ( v19 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  v22 = v53;
  v23 = v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
  }
  v24 = RoGetActivationFactory(v22, &GUID_00000035_0000_0000_c000_000000000046, &v46);
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v24,
      v45);
    v25 = v46;
    if ( v46 )
    {
      v46 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v25)[2])(v25);
    }
    v26 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_60;
  }
  v49 = 0;
  v28 = (**v46)(v46, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v49);
  v10 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v28,
      v45);
    v29 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v46;
    if ( v46 )
    {
      v46 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v30)[2])(v30);
    }
    v31 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    goto LABEL_60;
  }
  v51 = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 64LL))(v49, v47, &v51);
  v10 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"inetcore\\devtoolbar\\v3\\f12app\\appframe\\f12appframeclient.cpp",
      (const char *)(unsigned int)v33,
      v45);
    v34 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v46;
    if ( v46 )
    {
      v46 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v36)[2])(v36);
    }
    v37 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    goto LABEL_60;
  }
  v40 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v46;
  if ( v46 )
  {
    v46 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v42)[2])(v42);
  }
  v43 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  WindowsDeleteString(string);
  return F12Chooser;
}

```

## disassembly

```asm
0x18001b510  mov     [rsp-18h+arg_0], rbx
0x18001b515  mov     [rsp-18h+arg_18], rsi
0x18001b51a  push    rbp
0x18001b51b  push    rdi
0x18001b51c  push    r14
0x18001b51e  mov     rbp, rsp
0x18001b521  sub     rsp, 80h
0x18001b528  mov     rax, cs:__security_cookie
0x18001b52f  xor     rax, rsp
0x18001b532  mov     [rbp+var_8], rax
0x18001b536  mov     edi, r8d
0x18001b539  mov     rbx, rdx
0x18001b53c  xor     r14d, r14d
0x18001b53f  mov     [rbp+var_38], r14d
0x18001b543  lea     rcx, [rbp+var_38]
0x18001b547  call    cs:__imp_IsDeveloperModeEnabled
0x18001b54d  mov     esi, eax
0x18001b54f  test    eax, eax
0x18001b551  js      loc_18001BA04
0x18001b557  cmp     [rbp+var_38], r14d
0x18001b55b  jz      loc_18001BA04
0x18001b561  mov     edx, edi; unsigned int
0x18001b563  mov     rcx, rbx; HWND
0x18001b566  call    ?TryLaunchStoreApp@@YAJQEAUHWND__@@K@Z; TryLaunchStoreApp(HWND__ * const,ulong)
0x18001b56b  mov     esi, eax
0x18001b56d  test    eax, eax
0x18001b56f  jz      loc_18001BA04
0x18001b575  mov     edx, edi; unsigned int
0x18001b577  mov     rcx, rbx; HWND
0x18001b57a  call    ?TryLoadF12Chooser@@YAJQEAUHWND__@@K@Z; TryLoadF12Chooser(HWND__ * const,ulong)
0x18001b57f  mov     esi, eax
0x18001b581  test    eax, eax
0x18001b583  jz      loc_18001BA04
0x18001b589  mov     [rbp+string], r14
0x18001b58d  call    ?IsInternal@@YAJXZ; IsInternal(void)
0x18001b592  mov     rdi, cs:off_180037DD8; "https://go.microsoft.com/fwlink/?linkid"...
0x18001b599  test    eax, eax
0x18001b59b  cmovz   rdi, cs:off_180037DD0; "https://go.microsoft.com/fwlink/?linkid"...
0x18001b5a3  test    rdi, rdi
0x18001b5a6  jz      short loc_18001B5D8
0x18001b5a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b5ac  inc     rbx
0x18001b5af  cmp     [rdi+rbx*2], r14w
0x18001b5b4  jnz     short loc_18001B5AC
0x18001b5b6  mov     eax, 0FFFFFFFFh
0x18001b5bb  cmp     rbx, rax
0x18001b5be  ja      short loc_18001B5D1
0x18001b5c0  mov     rcx, [rbp+string]; string
0x18001b5c4  call    cs:__imp_WindowsDeleteString
0x18001b5ca  mov     edx, ebx
0x18001b5cc  mov     rcx, rdi
0x18001b5cf  jmp     short loc_18001B5EB
0x18001b5d1  mov     ebx, 80070216h
0x18001b5d6  jmp     short loc_18001B5FB
0x18001b5d8  mov     rcx, [rbp+string]; string
0x18001b5dc  call    cs:__imp_WindowsDeleteString
0x18001b5e2  xor     edx, edx; length
0x18001b5e4  lea     rcx, String; sourceString
0x18001b5eb  mov     [rbp+string], r14
0x18001b5ef  lea     r8, [rbp+string]; string
0x18001b5f3  call    cs:__imp_WindowsCreateString
0x18001b5f9  mov     ebx, eax
0x18001b5fb  test    ebx, ebx
0x18001b5fd  jns     short loc_18001B61C
0x18001b5ff  mov     rcx, [rbp+18h]; this
0x18001b603  mov     r9d, ebx; char *
0x18001b606  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b60d  mov     edx, 0E0h; void *
0x18001b612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b617  jmp     loc_18001B967
0x18001b61c  mov     [rbp+var_60], r14
0x18001b620  mov     [rbp+var_10], r14
0x18001b624  lea     r9, [rbp+var_10]; string
0x18001b628  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001b62c  mov     edx, 16h; length
0x18001b631  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001b638  call    cs:__imp_WindowsCreateStringReference
0x18001b63e  test    eax, eax
0x18001b640  js      loc_18001BA32
0x18001b646  mov     rbx, [rbp+var_10]
0x18001b64a  mov     rcx, [rbp+var_60]
0x18001b64e  test    rcx, rcx
0x18001b651  jz      short loc_18001B664
0x18001b653  mov     [rbp+var_60], r14
0x18001b657  mov     rax, [rcx]
0x18001b65a  mov     rax, [rax+10h]
0x18001b65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b663  nop
0x18001b664  lea     r8, [rbp+var_60]
0x18001b668  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18001b66f  mov     rcx, rbx
0x18001b672  call    cs:__imp_RoGetActivationFactory
0x18001b678  mov     ebx, eax
0x18001b67a  test    eax, eax
0x18001b67c  jns     short loc_18001B6B6
0x18001b67e  mov     rcx, [rbp+18h]; this
0x18001b682  mov     r9d, eax; char *
0x18001b685  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b68c  mov     edx, 0E3h; void *
0x18001b691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b696  nop
0x18001b697  mov     rcx, [rbp+var_60]
0x18001b69b  test    rcx, rcx
0x18001b69e  jz      short loc_18001B6B1
0x18001b6a0  mov     [rbp+var_60], r14
0x18001b6a4  mov     rax, [rcx]
0x18001b6a7  mov     rax, [rax+10h]
0x18001b6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6b0  nop
0x18001b6b1  jmp     loc_18001B967
0x18001b6b6  mov     [rbp+var_50], r14
0x18001b6ba  mov     rcx, [rbp+var_60]
0x18001b6be  mov     rax, [rcx]
0x18001b6c1  lea     r8, [rbp+var_50]
0x18001b6c5  mov     rdx, [rbp+string]
0x18001b6c9  mov     rax, [rax+30h]
0x18001b6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6d2  mov     ebx, eax
0x18001b6d4  test    eax, eax
0x18001b6d6  jns     short loc_18001B72A
0x18001b6d8  mov     rcx, [rbp+18h]; this
0x18001b6dc  mov     r9d, eax; char *
0x18001b6df  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b6e6  mov     edx, 0E6h; void *
0x18001b6eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6f0  nop
0x18001b6f1  mov     rcx, [rbp+var_50]
0x18001b6f5  test    rcx, rcx
0x18001b6f8  jz      short loc_18001B70B
0x18001b6fa  mov     [rbp+var_50], r14
0x18001b6fe  mov     rax, [rcx]
0x18001b701  mov     rax, [rax+10h]
0x18001b705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b70a  nop
0x18001b70b  mov     rcx, [rbp+var_60]
0x18001b70f  test    rcx, rcx
0x18001b712  jz      short loc_18001B725
0x18001b714  mov     [rbp+var_60], r14
0x18001b718  mov     rax, [rcx]
0x18001b71b  mov     rax, [rax+10h]
0x18001b71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b724  nop
0x18001b725  jmp     loc_18001B967
0x18001b72a  mov     [rbp+var_58], r14
0x18001b72e  mov     [rbp+var_10], r14
0x18001b732  lea     r9, [rbp+var_10]; string
0x18001b736  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001b73a  mov     edx, 17h; length
0x18001b73f  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18001b746  call    cs:__imp_WindowsCreateStringReference
0x18001b74c  test    eax, eax
0x18001b74e  js      loc_18001BA2A
0x18001b754  mov     rbx, [rbp+var_10]
0x18001b758  mov     rcx, [rbp+var_58]
0x18001b75c  test    rcx, rcx
0x18001b75f  jz      short loc_18001B772
0x18001b761  mov     [rbp+var_58], r14
0x18001b765  mov     rax, [rcx]
0x18001b768  mov     rax, [rax+10h]
0x18001b76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b771  nop
0x18001b772  lea     r8, [rbp+var_58]
0x18001b776  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18001b77d  mov     rcx, rbx
0x18001b780  call    cs:__imp_RoGetActivationFactory
0x18001b786  mov     ebx, eax
0x18001b788  test    eax, eax
0x18001b78a  jns     short loc_18001B7F8
0x18001b78c  mov     rcx, [rbp+18h]; this
0x18001b790  mov     r9d, eax; char *
0x18001b793  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b79a  mov     edx, 0E9h; void *
0x18001b79f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b7a4  nop
0x18001b7a5  mov     rcx, [rbp+var_58]
0x18001b7a9  test    rcx, rcx
0x18001b7ac  jz      short loc_18001B7BF
0x18001b7ae  mov     [rbp+var_58], r14
0x18001b7b2  mov     rax, [rcx]
0x18001b7b5  mov     rax, [rax+10h]
0x18001b7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7be  nop
0x18001b7bf  mov     rcx, [rbp+var_50]
0x18001b7c3  test    rcx, rcx
0x18001b7c6  jz      short loc_18001B7D9
0x18001b7c8  mov     [rbp+var_50], r14
0x18001b7cc  mov     rax, [rcx]
0x18001b7cf  mov     rax, [rax+10h]
0x18001b7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d8  nop
0x18001b7d9  mov     rcx, [rbp+var_60]
0x18001b7dd  test    rcx, rcx
0x18001b7e0  jz      short loc_18001B7F3
0x18001b7e2  mov     [rbp+var_60], r14
0x18001b7e6  mov     rax, [rcx]
0x18001b7e9  mov     rax, [rax+10h]
0x18001b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7f2  nop
0x18001b7f3  jmp     loc_18001B967
0x18001b7f8  mov     [rbp+var_40], r14
0x18001b7fc  mov     rcx, [rbp+var_58]
0x18001b800  mov     rax, [rcx]
0x18001b803  lea     r8, [rbp+var_40]
0x18001b807  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x18001b80e  mov     rax, [rax]
0x18001b811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b816  mov     ebx, eax
0x18001b818  test    eax, eax
0x18001b81a  jns     loc_18001B8A6
0x18001b820  mov     rcx, [rbp+18h]; this
0x18001b824  mov     r9d, eax; char *
0x18001b827  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b82e  mov     edx, 0ECh; void *
0x18001b833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b838  nop
0x18001b839  mov     rcx, [rbp+var_40]
0x18001b83d  test    rcx, rcx
0x18001b840  jz      short loc_18001B853
0x18001b842  mov     [rbp+var_40], r14
0x18001b846  mov     rax, [rcx]
0x18001b849  mov     rax, [rax+10h]
0x18001b84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b852  nop
0x18001b853  mov     rcx, [rbp+var_58]
0x18001b857  test    rcx, rcx
0x18001b85a  jz      short loc_18001B86D
0x18001b85c  mov     [rbp+var_58], r14
0x18001b860  mov     rax, [rcx]
0x18001b863  mov     rax, [rax+10h]
0x18001b867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b86c  nop
0x18001b86d  mov     rcx, [rbp+var_50]
0x18001b871  test    rcx, rcx
0x18001b874  jz      short loc_18001B887
0x18001b876  mov     [rbp+var_50], r14
0x18001b87a  mov     rax, [rcx]
0x18001b87d  mov     rax, [rax+10h]
0x18001b881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b886  nop
0x18001b887  mov     rcx, [rbp+var_60]
0x18001b88b  test    rcx, rcx
0x18001b88e  jz      short loc_18001B8A1
0x18001b890  mov     [rbp+var_60], r14
0x18001b894  mov     rax, [rcx]
0x18001b897  mov     rax, [rax+10h]
0x18001b89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a0  nop
0x18001b8a1  jmp     loc_18001B967
0x18001b8a6  mov     [rbp+var_30], r14
0x18001b8aa  mov     rcx, [rbp+var_40]
0x18001b8ae  mov     rax, [rcx]
0x18001b8b1  lea     r8, [rbp+var_30]
0x18001b8b5  mov     rdx, [rbp+var_50]
0x18001b8b9  mov     rax, [rax+40h]
0x18001b8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c2  mov     ebx, eax
0x18001b8c4  test    eax, eax
0x18001b8c6  jns     loc_18001B978
0x18001b8cc  mov     rcx, [rbp+18h]; this
0x18001b8d0  mov     r9d, eax; char *
0x18001b8d3  lea     r8, aInetcoreDevtoo; "inetcore\\devtoolbar\\v3\\f12app\\appfr"...
0x18001b8da  mov     edx, 0EFh; void *
0x18001b8df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8e4  nop
0x18001b8e5  mov     rcx, [rbp+var_30]
0x18001b8e9  test    rcx, rcx
0x18001b8ec  jz      short loc_18001B8FF
0x18001b8ee  mov     [rbp+var_30], r14
0x18001b8f2  mov     rax, [rcx]
0x18001b8f5  mov     rax, [rax+10h]
0x18001b8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8fe  nop
0x18001b8ff  mov     rcx, [rbp+var_40]
0x18001b903  test    rcx, rcx
0x18001b906  jz      short loc_18001B919
0x18001b908  mov     [rbp+var_40], r14
0x18001b90c  mov     rax, [rcx]
0x18001b90f  mov     rax, [rax+10h]
0x18001b913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b918  nop
0x18001b919  mov     rcx, [rbp+var_58]
0x18001b91d  test    rcx, rcx
0x18001b920  jz      short loc_18001B933
0x18001b922  mov     [rbp+var_58], r14
0x18001b926  mov     rax, [rcx]
0x18001b929  mov     rax, [rax+10h]
0x18001b92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b932  nop
0x18001b933  mov     rcx, [rbp+var_50]
0x18001b937  test    rcx, rcx
0x18001b93a  jz      short loc_18001B94D
0x18001b93c  mov     [rbp+var_50], r14
0x18001b940  mov     rax, [rcx]
0x18001b943  mov     rax, [rax+10h]
0x18001b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b94c  nop
0x18001b94d  mov     rcx, [rbp+var_60]
0x18001b951  test    rcx, rcx
0x18001b954  jz      short loc_18001B967
0x18001b956  mov     [rbp+var_60], r14
  ... truncated ...
```

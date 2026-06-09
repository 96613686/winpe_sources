# OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration(Microsoft::WRL::ComPtr<OSIntegration::DEH::ActivatableClassRegistration>,Windows::Internal::String const &)

- ea: `0x180046a78`
- end: `0x180046d61`
- name: `?SubmitClassEntryPointRegistration@DownloadUploadClassHelper@Internal@DEH@OSIntegration@@CAJV?$ComPtr@UActivatableClassRegistration@DEH@OSIntegration@@@WRL@Microsoft@@AEBVString@2Windows@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046944`

## callees

- `0x18003a300`
- `0x180046a78`
- `0x18009aff4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046b3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046b3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180046bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046cf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046b56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046cf0`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration(
        _QWORD *a1,
        __int64 a2)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v5; // rdx
  HRESULT v6; // esi
  HRESULT v7; // edi
  __int64 v8; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char *v15; // [rsp+28h] [rbp-18h]
  HSTRING v16[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+78h] [rbp+38h]
  HSTRING string; // [rsp+90h] [rbp+50h] BYREF
  HSTRING v19; // [rsp+98h] [rbp+58h] BYREF

  string = 0;
  if ( !off_1802E0678 )
  {
    v7 = -2147467261;
LABEL_7:
    LODWORD(v15) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration",
      "entryPointAttribute.Initialize(DownloadUploadClassConstants::attributeEntryPoint)",
      v15,
      (int)v16[0]);
    if ( string )
      WindowsDeleteString(string);
    v8 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)v7;
  }
  v16[0] = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( off_1802E0678[v5] );
  v6 = -2147024362;
  if ( v5 <= 0xFFFFFFFF )
  {
    v7 = WindowsCreateString(off_1802E0678, v5, v16);
    if ( v7 >= 0 )
    {
      v10 = string;
      string = v16[0];
      WindowsDeleteString(v10);
    }
  }
  else
  {
    v7 = -2147024362;
  }
  if ( v7 < 0 )
    goto LABEL_7;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, __int64))(*(_QWORD *)*a1 + 112LL))(*a1, &string, a2) )
  {
    LODWORD(v15) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration",
      "!(wil::verify_bool(activatableClass->AddAttribute(entryPointAttribute, activatableClassEntryPoint)))",
      v15,
      (int)v16[0]);
    if ( string )
      WindowsDeleteString(string);
LABEL_41:
    v14 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return 2147942414LL;
  }
  v19 = 0;
  if ( off_1802E0680 )
  {
    v16[0] = 0;
    do
      ++v4;
    while ( off_1802E0680[v4] );
    if ( v4 <= 0xFFFFFFFF )
    {
      v6 = WindowsCreateString(off_1802E0680, v4, v16);
      if ( v6 >= 0 )
      {
        v11 = v19;
        v19 = v16[0];
        WindowsDeleteString(v11);
      }
    }
    if ( v6 >= 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, __int64))(*(_QWORD *)*a1 + 104LL))(*a1, &v19, 1) )
      {
        if ( v19 )
          WindowsDeleteString(v19);
        if ( string )
          WindowsDeleteString(string);
        v12 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        return 0;
      }
      LODWORD(v15) = -2147024882;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
        "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration",
        "!(wil::verify_bool(activatableClass->AddAttribute(aliasedAttribute, 1)))",
        v15,
        (int)v16[0]);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v19);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
      goto LABEL_41;
    }
  }
  else
  {
    v6 = -2147467261;
  }
  LODWORD(v15) = v6;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x1D7,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
    "OSIntegration::DEH::Internal::DownloadUploadClassHelper::SubmitClassEntryPointRegistration",
    "aliasedAttribute.Initialize(DownloadUploadClassConstants::attributeAliased)",
    v15,
    (int)v16[0]);
  if ( v19 )
    WindowsDeleteString(v19);
  if ( string )
    WindowsDeleteString(string);
  v13 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046a78  mov     [rsp-38h+arg_8], rbx
0x180046a7d  mov     [rsp-38h+arg_0], rcx
0x180046a82  push    rbp
0x180046a83  push    rsi
0x180046a84  push    rdi
0x180046a85  push    r12
0x180046a87  push    r13
0x180046a89  push    r14
0x180046a8b  push    r15
0x180046a8d  mov     rbp, rsp
0x180046a90  sub     rsp, 40h
0x180046a94  mov     r15, rdx
0x180046a97  mov     rbx, rcx
0x180046a9a  xor     r12d, r12d
0x180046a9d  mov     [rbp+string], r12
0x180046aa1  mov     rcx, cs:off_1802E0678; sourceString
0x180046aa8  test    rcx, rcx
0x180046aab  jz      short loc_180046AD9
0x180046aad  mov     [rbp+var_10], r12
0x180046ab1  or      r14, 0FFFFFFFFFFFFFFFFh
0x180046ab5  mov     rdx, r14
0x180046ab8  inc     rdx; length
0x180046abb  cmp     [rcx+rdx*2], r12w
0x180046ac0  jnz     short loc_180046AB8
0x180046ac2  mov     esi, 80070216h
0x180046ac7  mov     r13d, 0FFFFFFFFh
0x180046acd  cmp     rdx, r13
0x180046ad0  jbe     short loc_180046B3A
0x180046ad2  mov     edi, esi
0x180046ad4  jmp     loc_180046B5C
0x180046ad9  mov     edi, 80004003h
0x180046ade  mov     rcx, [rbp+38h]; this
0x180046ae2  mov     dword ptr [rsp+40h+var_18], edi; char *
0x180046ae6  lea     rax, aEntrypointattr; "entryPointAttribute.Initialize(Download"...
0x180046aed  mov     [rsp+40h+var_20], rax; char *
0x180046af2  lea     r9, aOsintegrationD_93; "OSIntegration::DEH::Internal::DownloadU"...
0x180046af9  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180046b00  mov     edx, 1D0h; void *
0x180046b05  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180046b0a  nop
0x180046b0b  mov     rcx, [rbp+string]; string
0x180046b0f  test    rcx, rcx
0x180046b12  jz      short loc_180046B1B
0x180046b14  call    cs:__imp_WindowsDeleteString
0x180046b1a  nop
0x180046b1b  mov     rcx, [rbx]
0x180046b1e  test    rcx, rcx
0x180046b21  jz      short loc_180046B33
0x180046b23  mov     [rbx], r12
0x180046b26  mov     rdx, [rcx]
0x180046b29  mov     rax, [rdx+10h]
0x180046b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b32  nop
0x180046b33  mov     eax, edi
0x180046b35  jmp     loc_180046C2D
0x180046b3a  lea     r8, [rbp+var_10]; string
0x180046b3e  call    cs:__imp_WindowsCreateString
0x180046b44  mov     edi, eax
0x180046b46  test    eax, eax
0x180046b48  js      short loc_180046B5C
0x180046b4a  mov     rcx, [rbp+string]; string
0x180046b4e  mov     rax, [rbp+var_10]
0x180046b52  mov     [rbp+string], rax
0x180046b56  call    cs:__imp_WindowsDeleteString
0x180046b5c  test    edi, edi
0x180046b5e  js      loc_180046ADE
0x180046b64  mov     rcx, [rbx]
0x180046b67  mov     rax, [rcx]
0x180046b6a  mov     r8, r15
0x180046b6d  lea     rdx, [rbp+string]
0x180046b71  mov     rax, [rax+70h]
0x180046b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b7a  test    al, al
0x180046b7c  jz      loc_180046CB6
0x180046b82  mov     [rbp+arg_18], r12
0x180046b86  mov     rcx, cs:off_1802E0680; sourceString
0x180046b8d  test    rcx, rcx
0x180046b90  jz      loc_180046C45
0x180046b96  mov     [rbp+var_10], r12
0x180046b9a  inc     r14
0x180046b9d  cmp     [rcx+r14*2], r12w
0x180046ba2  jnz     short loc_180046B9A
0x180046ba4  cmp     r14, r13
0x180046ba7  ja      short loc_180046BCE
0x180046ba9  mov     edx, r14d; length
0x180046bac  lea     r8, [rbp+var_10]; string
0x180046bb0  call    cs:__imp_WindowsCreateString
0x180046bb6  mov     esi, eax
0x180046bb8  test    eax, eax
0x180046bba  js      short loc_180046BCE
0x180046bbc  mov     rcx, [rbp+arg_18]; string
0x180046bc0  mov     rax, [rbp+var_10]
0x180046bc4  mov     [rbp+arg_18], rax
0x180046bc8  call    cs:__imp_WindowsDeleteString
0x180046bce  test    esi, esi
0x180046bd0  js      short loc_180046C4A
0x180046bd2  mov     rcx, [rbx]
0x180046bd5  mov     rax, [rcx]
0x180046bd8  mov     r8d, 1
0x180046bde  lea     rdx, [rbp+arg_18]
0x180046be2  mov     rax, [rax+68h]
0x180046be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046beb  test    al, al
0x180046bed  jz      loc_180046D19
0x180046bf3  mov     rcx, [rbp+arg_18]; string
0x180046bf7  test    rcx, rcx
0x180046bfa  jz      short loc_180046C03
0x180046bfc  call    cs:__imp_WindowsDeleteString
0x180046c02  nop
0x180046c03  mov     rcx, [rbp+string]; string
0x180046c07  test    rcx, rcx
0x180046c0a  jz      short loc_180046C13
0x180046c0c  call    cs:__imp_WindowsDeleteString
0x180046c12  nop
0x180046c13  mov     rcx, [rbx]
0x180046c16  test    rcx, rcx
0x180046c19  jz      short loc_180046C2B
0x180046c1b  mov     [rbx], r12
0x180046c1e  mov     rax, [rcx]
0x180046c21  mov     rax, [rax+10h]
0x180046c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c2a  nop
0x180046c2b  xor     eax, eax
0x180046c2d  mov     rbx, [rsp+40h+arg_8]
0x180046c35  add     rsp, 40h
0x180046c39  pop     r15
0x180046c3b  pop     r14
0x180046c3d  pop     r13
0x180046c3f  pop     r12
0x180046c41  pop     rdi
0x180046c42  pop     rsi
0x180046c43  pop     rbp
0x180046c44  retn
0x180046c45  mov     esi, 80004003h
0x180046c4a  mov     rcx, [rbp+38h]; this
0x180046c4e  mov     dword ptr [rsp+40h+var_18], esi; char *
0x180046c52  lea     rax, aAliasedattribu; "aliasedAttribute.Initialize(DownloadUpl"...
0x180046c59  mov     [rsp+40h+var_20], rax; char *
0x180046c5e  lea     r9, aOsintegrationD_93; "OSIntegration::DEH::Internal::DownloadU"...
0x180046c65  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180046c6c  mov     edx, 1D7h; void *
0x180046c71  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180046c76  nop
0x180046c77  mov     rcx, [rbp+arg_18]; string
0x180046c7b  test    rcx, rcx
0x180046c7e  jz      short loc_180046C87
0x180046c80  call    cs:__imp_WindowsDeleteString
0x180046c86  nop
0x180046c87  mov     rcx, [rbp+string]; string
0x180046c8b  test    rcx, rcx
0x180046c8e  jz      short loc_180046C97
0x180046c90  call    cs:__imp_WindowsDeleteString
0x180046c96  nop
0x180046c97  mov     rcx, [rbx]
0x180046c9a  test    rcx, rcx
0x180046c9d  jz      short loc_180046CAF
0x180046c9f  mov     [rbx], r12
0x180046ca2  mov     rax, [rcx]
0x180046ca5  mov     rax, [rax+10h]
0x180046ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cae  nop
0x180046caf  mov     eax, esi
0x180046cb1  jmp     loc_180046C2D
0x180046cb6  mov     rcx, [rbp+38h]; this
0x180046cba  mov     dword ptr [rsp+40h+var_18], 8007000Eh; char *
0x180046cc2  lea     rax, aWilVerifyBoolA_0; "!(wil::verify_bool(activatableClass->Ad"...
0x180046cc9  mov     [rsp+40h+var_20], rax; char *
0x180046cce  lea     r9, aOsintegrationD_93; "OSIntegration::DEH::Internal::DownloadU"...
0x180046cd5  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180046cdc  mov     edx, 1D3h; void *
0x180046ce1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180046ce6  nop
0x180046ce7  mov     rcx, [rbp+string]; string
0x180046ceb  test    rcx, rcx
0x180046cee  jz      short loc_180046CF7
0x180046cf0  call    cs:__imp_WindowsDeleteString
0x180046cf6  nop
0x180046cf7  mov     rcx, [rbx]
0x180046cfa  test    rcx, rcx
0x180046cfd  jz      short loc_180046D0F
0x180046cff  mov     [rbx], r12
0x180046d02  mov     rax, [rcx]
0x180046d05  mov     rax, [rax+10h]
0x180046d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d0e  nop
0x180046d0f  mov     eax, 8007000Eh
0x180046d14  jmp     loc_180046C2D
0x180046d19  mov     rcx, [rbp+38h]; this
0x180046d1d  mov     dword ptr [rsp+40h+var_18], 8007000Eh; char *
0x180046d25  lea     rax, aWilVerifyBoolA; "!(wil::verify_bool(activatableClass->Ad"...
0x180046d2c  mov     [rsp+40h+var_20], rax; char *
0x180046d31  lea     r9, aOsintegrationD_93; "OSIntegration::DEH::Internal::DownloadU"...
0x180046d38  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180046d3f  mov     edx, 1D9h; void *
0x180046d44  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180046d49  nop
0x180046d4a  lea     rcx, [rbp+arg_18]
0x180046d4e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180046d53  nop
0x180046d54  lea     rcx, [rbp+string]
0x180046d58  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180046d5d  nop
0x180046d5e  jmp     short loc_180046CF7
```

# OSIntegration::Tools::MoCOMHelper::WriteACIDCustomProperties(Microsoft::WRL::ComPtr<OSIntegration::DEH::OutOfProcessActivatableClassRegistration> &)

- ea: `0x1800393fc`
- end: `0x1800398ca`
- name: `?WriteACIDCustomProperties@MoCOMHelper@Tools@OSIntegration@@AEBAJAEAV?$ComPtr@UOutOfProcessActivatableClassRegistration@DEH@OSIntegration@@@WRL@Microsoft@@@Z`
- size: `1230`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ad8f4`

## callees

- `0x18000b3bc`
- `0x1800393fc`
- `0x1800398d0`
- `0x18003a300`
- `0x18003a320`
- `0x180098bf4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003953a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003978d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003953a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003978d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800396e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800396f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003976a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003977e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800397a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800395a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800396e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800396f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003976a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003977e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800397a5`

## string_xrefs

- `0x180039640`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003967e`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180039735`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180039844`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18003987c`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::WriteACIDCustomProperties(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 i; // rdi
  unsigned int *v5; // rsi
  HSTRING v6; // rcx
  int v7; // eax
  HRESULT v8; // ebx
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 j; // rsi
  __int64 v12; // rdi
  HSTRING v13; // rcx
  int v14; // eax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  HSTRING v17; // rcx
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // rdx
  HSTRING v20; // rcx
  char *v21; // rax
  HSTRING v22; // rdx
  HSTRING v23; // rcx
  __int64 v24; // rcx
  HSTRING v25; // rcx
  __int64 v26; // rdx
  unsigned __int64 v27; // r9
  HSTRING v29; // rcx
  HSTRING v30; // rcx
  HSTRING v31; // rcx
  char *v32; // rax
  HSTRING v33; // rdx
  HSTRING v34; // rcx
  __int64 v35; // rcx
  HSTRING v36; // rcx
  HSTRING v37; // rcx
  __int64 v38; // [rsp+20h] [rbp-20h] BYREF
  char v39; // [rsp+28h] [rbp-18h] BYREF
  char v40; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HSTRING v42; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v43; // [rsp+88h] [rbp+48h] BYREF
  HSTRING v44; // [rsp+90h] [rbp+50h] BYREF
  HSTRING string; // [rsp+98h] [rbp+58h] BYREF

  v43 = 0;
  v44 = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 96LL))(*a2, &v42);
  for ( i = 0; i < a1[55]; ++i )
  {
    v5 = *(unsigned int **)(a1[53] + 8 * i);
    v6 = v42;
    string = v42;
    if ( v42 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v42 + 8LL))(v42);
    v7 = OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
           v6,
           v5,
           &string);
    v8 = v7;
    if ( v7 == -2147023728 || v7 == -2147483637 )
    {
      v9 = (const WCHAR *)*((_QWORD *)v5 + 2);
      if ( !v9 )
      {
        v8 = -2147467261;
LABEL_61:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA55,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v8,
          v38);
        v30 = v42;
        if ( v42 )
        {
          v42 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v30 + 16LL))(v30);
        }
        goto LABEL_63;
      }
      string = 0;
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      if ( v10 <= 0xFFFFFFFF )
      {
        v8 = WindowsCreateString(v9, v10, &string);
        if ( v8 >= 0 )
        {
          v31 = v43;
          v43 = string;
          WindowsDeleteString(v31);
        }
      }
      else
      {
        v8 = -2147024362;
      }
      if ( v8 < 0 )
        goto LABEL_61;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, _QWORD))(*(_QWORD *)*a2 + 104LL))(*a2, &v43, *v5) )
      {
        v8 = -2147024882;
        v26 = 2646;
LABEL_45:
        v27 = (unsigned int)v8;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)v27,
          v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v44);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v43);
        return (unsigned int)v8;
      }
      v32 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 96LL))(*a2, &v38);
      v33 = 0;
      if ( &v39 != v32 )
      {
        v33 = *(HSTRING *)v32;
        *(_QWORD *)v32 = 0;
      }
      v34 = v42;
      v42 = v33;
      if ( v34 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v34 + 16LL))(v34);
      v35 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    else if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v7,
        v38);
      v37 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
      }
      goto LABEL_63;
    }
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= a1[67] )
    {
      v29 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v29 + 16LL))(v29);
      }
      if ( v44 )
        WindowsDeleteString(v44);
      if ( v43 )
        WindowsDeleteString(v43);
      return 0;
    }
    v12 = *(_QWORD *)(a1[65] + 8 * j);
    v13 = v42;
    string = v42;
    if ( v42 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v42 + 8LL))(v42);
    v14 = OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(
            v13,
            v12,
            &string);
    v8 = v14;
    if ( v14 != -2147023728 && v14 != -2147483637 )
    {
      if ( v14 < 0 )
      {
        v27 = (unsigned int)v14;
        v26 = 2678;
        goto LABEL_46;
      }
      continue;
    }
    v15 = *(const WCHAR **)(v12 + 32);
    if ( !v15 )
    {
      v8 = -2147467261;
LABEL_44:
      v26 = 2668;
      goto LABEL_45;
    }
    string = 0;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    if ( v16 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
    }
    else
    {
      v8 = WindowsCreateString(v15, v16, &string);
      if ( v8 >= 0 )
      {
        v17 = v43;
        v43 = string;
        WindowsDeleteString(v17);
      }
    }
    if ( v8 < 0 )
      goto LABEL_44;
    v18 = *(const WCHAR **)(v12 + 8);
    if ( !v18 )
      break;
    string = 0;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
    }
    else
    {
      v8 = WindowsCreateString(v18, v19, &string);
      if ( v8 >= 0 )
      {
        v20 = v44;
        v44 = string;
        WindowsDeleteString(v20);
      }
    }
    if ( v8 < 0 )
      goto LABEL_40;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, HSTRING *))(*(_QWORD *)*a2 + 112LL))(*a2, &v43, &v44) )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)0x8007000ELL,
        v38);
      v36 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
      }
      goto LABEL_63;
    }
    v21 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 96LL))(*a2, &v38);
    v22 = 0;
    if ( &v40 != v21 )
    {
      v22 = *(HSTRING *)v21;
      *(_QWORD *)v21 = 0;
    }
    v23 = v42;
    v42 = v22;
    if ( v23 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  v8 = -2147467261;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA6D,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v8,
    v38);
  v25 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_63:
  if ( v44 )
    WindowsDeleteString(v44);
  if ( v43 )
    WindowsDeleteString(v43);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800393fc  push    rbp
0x1800393fe  push    rbx
0x1800393ff  push    rsi
0x180039400  push    rdi
0x180039401  push    r12
0x180039403  push    r14
0x180039405  push    r15
0x180039407  mov     rbp, rsp
0x18003940a  sub     rsp, 40h
0x18003940e  mov     r15, rdx
0x180039411  mov     r14, rcx
0x180039414  xor     r12d, r12d
0x180039417  mov     [rbp+arg_8], r12
0x18003941b  mov     [rbp+arg_10], r12
0x18003941f  mov     rcx, [rdx]
0x180039422  mov     rax, [rcx]
0x180039425  lea     rdx, [rbp+arg_0]
0x180039429  mov     rax, [rax+60h]
0x18003942d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039432  nop
0x180039433  mov     edi, r12d
0x180039436  cmp     rdi, [r14+1B8h]
0x18003943d  jnb     short loc_1800394BB
0x18003943f  mov     rax, [r14+1A8h]
0x180039446  mov     rsi, [rax+rdi*8]
0x18003944a  mov     rcx, [rbp+arg_0]
0x18003944e  mov     [rbp+string], rcx
0x180039452  test    rcx, rcx
0x180039455  jz      short loc_180039464
0x180039457  mov     rax, [rcx]
0x18003945a  mov     rax, [rax+8]
0x18003945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039463  nop
0x180039464  lea     r8, [rbp+string]
0x180039468  mov     rdx, rsi
0x18003946b  call    ?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180039470  mov     ebx, eax
0x180039472  cmp     eax, 80070490h
0x180039477  jz      short loc_180039484
0x180039479  cmp     eax, 8000000Bh
0x18003947e  jnz     loc_18003982C
0x180039484  mov     rcx, [rsi+10h]; sourceString
0x180039488  test    rcx, rcx
0x18003948b  jz      loc_180039729
0x180039491  mov     [rbp+string], r12
0x180039495  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039499  inc     rdx; length
0x18003949c  cmp     [rcx+rdx*2], r12w
0x1800394a1  jnz     short loc_180039499
0x1800394a3  mov     eax, 0FFFFFFFFh
0x1800394a8  cmp     rdx, rax
0x1800394ab  jbe     loc_180039789
0x1800394b1  mov     ebx, 80070216h
0x1800394b6  jmp     loc_1800397AB
0x1800394bb  mov     rsi, r12
0x1800394be  cmp     rsi, [r14+218h]
0x1800394c5  jnb     loc_1800396BD
0x1800394cb  mov     rax, [r14+208h]
0x1800394d2  mov     rdi, [rax+rsi*8]
0x1800394d6  mov     rcx, [rbp+arg_0]
0x1800394da  mov     [rbp+string], rcx
0x1800394de  test    rcx, rcx
0x1800394e1  jz      short loc_1800394F0
0x1800394e3  mov     rax, [rcx]
0x1800394e6  mov     rax, [rax+8]
0x1800394ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394ef  nop
0x1800394f0  lea     r8, [rbp+string]
0x1800394f4  mov     rdx, rdi
0x1800394f7  call    ?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@VStringPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x1800394fc  mov     ebx, eax
0x1800394fe  cmp     eax, 80070490h
0x180039503  jnz     loc_1800396FA
0x180039509  mov     rcx, [rdi+20h]; sourceString
0x18003950d  test    rcx, rcx
0x180039510  jz      loc_180039671
0x180039516  mov     [rbp+string], r12
0x18003951a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003951e  inc     rdx; length
0x180039521  cmp     [rcx+rdx*2], r12w
0x180039526  jnz     short loc_18003951E
0x180039528  mov     eax, 0FFFFFFFFh
0x18003952d  cmp     rdx, rax
0x180039530  ja      loc_180039715
0x180039536  lea     r8, [rbp+string]; string
0x18003953a  call    cs:__imp_WindowsCreateString
0x180039540  mov     ebx, eax
0x180039542  test    eax, eax
0x180039544  js      short loc_180039558
0x180039546  mov     rcx, [rbp+arg_8]; string
0x18003954a  mov     rax, [rbp+string]
0x18003954e  mov     [rbp+arg_8], rax
0x180039552  call    cs:__imp_WindowsDeleteString
0x180039558  mov     eax, 0FFFFFFFFh
0x18003955d  test    ebx, ebx
0x18003955f  js      loc_180039676
0x180039565  mov     rcx, [rdi+8]; sourceString
0x180039569  test    rcx, rcx
0x18003956c  jz      loc_180039634
0x180039572  mov     [rbp+string], r12
0x180039576  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003957a  inc     rdx; length
0x18003957d  cmp     [rcx+rdx*2], r12w
0x180039582  jnz     short loc_18003957A
0x180039584  cmp     rdx, rax
0x180039587  ja      loc_18003971F
0x18003958d  lea     r8, [rbp+string]; string
0x180039591  call    cs:__imp_WindowsCreateString
0x180039597  mov     ebx, eax
0x180039599  test    eax, eax
0x18003959b  js      short loc_1800395AF
0x18003959d  mov     rcx, [rbp+arg_10]; string
0x1800395a1  mov     rax, [rbp+string]
0x1800395a5  mov     [rbp+arg_10], rax
0x1800395a9  call    cs:__imp_WindowsDeleteString
0x1800395af  test    ebx, ebx
0x1800395b1  js      loc_180039639
0x1800395b7  mov     rcx, [r15]
0x1800395ba  mov     rax, [rcx]
0x1800395bd  lea     r8, [rbp+arg_10]
0x1800395c1  lea     rdx, [rbp+arg_8]
0x1800395c5  mov     rax, [rax+70h]
0x1800395c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395ce  test    al, al
0x1800395d0  jz      loc_180039838
0x1800395d6  mov     rcx, [r15]
0x1800395d9  mov     rax, [rcx]
0x1800395dc  lea     rdx, [rbp+var_20]
0x1800395e0  mov     rax, [rax+60h]
0x1800395e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395e9  mov     rdx, r12
0x1800395ec  lea     rcx, [rbp+var_10]
0x1800395f0  cmp     rcx, rax
0x1800395f3  jz      short loc_1800395FB
0x1800395f5  mov     rdx, [rax]
0x1800395f8  mov     [rax], r12
0x1800395fb  mov     rcx, [rbp+arg_0]
0x1800395ff  mov     [rbp+arg_0], rdx
0x180039603  test    rcx, rcx
0x180039606  jz      short loc_180039615
0x180039608  mov     rax, [rcx]
0x18003960b  mov     rax, [rax+10h]
0x18003960f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039614  nop
0x180039615  mov     rcx, [rbp+var_20]
0x180039619  test    rcx, rcx
0x18003961c  jz      short loc_18003962F
0x18003961e  mov     [rbp+var_20], r12
0x180039622  mov     rax, [rcx]
0x180039625  mov     rax, [rax+10h]
0x180039629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003962e  nop
0x18003962f  jmp     loc_18003970D
0x180039634  mov     ebx, 80004003h
0x180039639  mov     rcx, [rbp+38h]; this
0x18003963d  mov     r9d, ebx; char *
0x180039640  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180039647  mov     edx, 0A6Dh; void *
0x18003964c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039651  nop
0x180039652  mov     rcx, [rbp+arg_0]
0x180039656  test    rcx, rcx
0x180039659  jz      short loc_18003966C
0x18003965b  mov     [rbp+arg_0], r12
0x18003965f  mov     rax, [rcx]
0x180039662  mov     rax, [rax+10h]
0x180039666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003966b  nop
0x18003966c  jmp     loc_180039761
0x180039671  mov     ebx, 80004003h
0x180039676  mov     edx, 0A6Ch; void *
0x18003967b  mov     r9d, ebx; char *
0x18003967e  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180039685  mov     rcx, [rbp+38h]; this
0x180039689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003968e  nop
0x18003968f  lea     rcx, [rbp+arg_0]
0x180039693  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039698  nop
0x180039699  lea     rcx, [rbp+arg_10]
0x18003969d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800396a2  nop
0x1800396a3  lea     rcx, [rbp+arg_8]
0x1800396a7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800396ac  mov     eax, ebx
0x1800396ae  add     rsp, 40h
0x1800396b2  pop     r15
0x1800396b4  pop     r14
0x1800396b6  pop     r12
0x1800396b8  pop     rdi
0x1800396b9  pop     rsi
0x1800396ba  pop     rbx
0x1800396bb  pop     rbp
0x1800396bc  retn
0x1800396bd  mov     rcx, [rbp+arg_0]
0x1800396c1  test    rcx, rcx
0x1800396c4  jz      short loc_1800396D7
0x1800396c6  mov     [rbp+arg_0], r12
0x1800396ca  mov     rax, [rcx]
0x1800396cd  mov     rax, [rax+10h]
0x1800396d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396d6  nop
0x1800396d7  mov     rcx, [rbp+arg_10]; string
0x1800396db  test    rcx, rcx
0x1800396de  jz      short loc_1800396E7
0x1800396e0  call    cs:__imp_WindowsDeleteString
0x1800396e6  nop
0x1800396e7  mov     rcx, [rbp+arg_8]; string
0x1800396eb  test    rcx, rcx
0x1800396ee  jz      short loc_1800396F6
0x1800396f0  call    cs:__imp_WindowsDeleteString
0x1800396f6  xor     eax, eax
0x1800396f8  jmp     short loc_1800396AE
0x1800396fa  cmp     eax, 8000000Bh
0x1800396ff  jz      loc_180039509
0x180039705  test    eax, eax
0x180039707  js      loc_1800398BC
0x18003970d  inc     rsi
0x180039710  jmp     loc_1800394BE
0x180039715  mov     ebx, 80070216h
0x18003971a  jmp     loc_18003955D
0x18003971f  mov     ebx, 80070216h
0x180039724  jmp     loc_1800395AF
0x180039729  mov     ebx, 80004003h
0x18003972e  mov     rcx, [rbp+38h]; this
0x180039732  mov     r9d, ebx; char *
0x180039735  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003973c  mov     edx, 0A55h; void *
0x180039741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039746  nop
0x180039747  mov     rcx, [rbp+arg_0]
0x18003974b  test    rcx, rcx
0x18003974e  jz      short loc_180039761
0x180039750  mov     [rbp+arg_0], r12
0x180039754  mov     rax, [rcx]
0x180039757  mov     rax, [rax+10h]
0x18003975b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039760  nop
0x180039761  mov     rcx, [rbp+arg_10]; string
0x180039765  test    rcx, rcx
0x180039768  jz      short loc_180039771
0x18003976a  call    cs:__imp_WindowsDeleteString
0x180039770  nop
0x180039771  mov     rcx, [rbp+arg_8]; string
0x180039775  test    rcx, rcx
0x180039778  jz      loc_1800396AC
0x18003977e  call    cs:__imp_WindowsDeleteString
0x180039784  jmp     loc_1800396AC
0x180039789  lea     r8, [rbp+string]; string
0x18003978d  call    cs:__imp_WindowsCreateString
0x180039793  mov     ebx, eax
0x180039795  test    eax, eax
0x180039797  js      short loc_1800397AB
0x180039799  mov     rcx, [rbp+arg_8]; string
0x18003979d  mov     rax, [rbp+string]
0x1800397a1  mov     [rbp+arg_8], rax
0x1800397a5  call    cs:__imp_WindowsDeleteString
0x1800397ab  test    ebx, ebx
0x1800397ad  js      loc_18003972E
0x1800397b3  mov     rcx, [r15]
0x1800397b6  mov     rax, [rcx]
0x1800397b9  mov     r8d, [rsi]
0x1800397bc  lea     rdx, [rbp+arg_8]
0x1800397c0  mov     rax, [rax+68h]
0x1800397c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397c9  test    al, al
0x1800397cb  jz      loc_1800398AD
0x1800397d1  mov     rcx, [r15]
0x1800397d4  mov     rax, [rcx]
0x1800397d7  lea     rdx, [rbp+var_20]
0x1800397db  mov     rax, [rax+60h]
0x1800397df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397e4  mov     rdx, r12
0x1800397e7  lea     rcx, [rbp+var_18]
0x1800397eb  cmp     rcx, rax
0x1800397ee  jz      short loc_1800397F6
0x1800397f0  mov     rdx, [rax]
0x1800397f3  mov     [rax], r12
0x1800397f6  mov     rcx, [rbp+arg_0]
0x1800397fa  mov     [rbp+arg_0], rdx
0x1800397fe  test    rcx, rcx
0x180039801  jz      short loc_180039810
0x180039803  mov     rax, [rcx]
0x180039806  mov     rax, [rax+10h]
0x18003980a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980f  nop
0x180039810  mov     rcx, [rbp+var_20]
0x180039814  test    rcx, rcx
0x180039817  jz      short loc_18003982A
0x180039819  mov     [rbp+var_20], r12
0x18003981d  mov     rax, [rcx]
0x180039820  mov     rax, [rax+10h]
0x180039824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039829  nop
0x18003982a  jmp     short loc_180039830
0x18003982c  test    ebx, ebx
0x18003982e  js      short loc_180039875
0x180039830  inc     rdi
0x180039833  jmp     loc_180039436
0x180039838  mov     rcx, [rbp+38h]; this
  ... truncated ...
```

# OSIntegration::Tools::MoCOMHelper::WriteContractCustomProperties(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionRegistration> &)

- ea: `0x1800367ac`
- end: `0x180036bea`
- name: `?WriteContractCustomProperties@MoCOMHelper@Tools@OSIntegration@@AEBAJAEAV?$ComPtr@UExtensionRegistration@DEH@OSIntegration@@@WRL@Microsoft@@@Z`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007d530`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x18003647c`
- `0x1800367ac`
- `0x180036bf0`
- `0x180036e58`
- `0x180036eb4`
- `0x18003dbd0`
- `0x18004d910`
- `0x180069eb4`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800368db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800368db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800368f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036ae3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800368f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036ae3`

## string_xrefs

- `0x1800369a5`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800369e3`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180036a23`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::WriteContractCustomProperties(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  unsigned __int64 i; // rdi
  unsigned __int64 v6; // rsi
  HSTRING v7; // rdx
  __int64 v8; // rdi
  int v9; // eax
  HRESULT v10; // ebx
  const WCHAR *v11; // rcx
  unsigned __int64 v12; // rdx
  HSTRING v13; // rcx
  const WCHAR *v14; // rcx
  unsigned __int64 v15; // rdx
  HSTRING v16; // rcx
  char *v17; // rax
  HSTRING v18; // rcx
  HSTRING v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  HSTRING v22; // rcx
  unsigned int *v24; // rsi
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // [rsp+20h] [rbp-10h] BYREF
  char v30; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  HSTRING v32; // [rsp+70h] [rbp+40h] BYREF
  HSTRING v33; // [rsp+78h] [rbp+48h] BYREF
  HSTRING v34; // [rsp+80h] [rbp+50h] BYREF
  HSTRING string; // [rsp+88h] [rbp+58h] BYREF

  v33 = 0;
  v34 = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 128LL))(*a2, &v32);
  for ( i = 0; i < a1[51]; ++i )
  {
    v24 = *(unsigned int **)(a1[49] + 8 * i);
    string = v32;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&string);
    v26 = OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
            v25,
            v24,
            &string);
    v10 = v26;
    if ( v26 == -2147023728 || v26 == -2147483637 )
    {
      string = (HSTRING)*((_QWORD *)v24 + 2);
      v27 = Windows::Internal::String::Initialize<unsigned short const *>(&v33, &string);
      v10 = v27;
      if ( v27 < 0 )
      {
        v21 = (unsigned int)v27;
        v20 = 2774;
        goto LABEL_37;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, _QWORD))(*(_QWORD *)*a2 + 136LL))(*a2, &v33, *v24) )
      {
        v10 = -2147024882;
        v20 = 2775;
LABEL_36:
        v21 = (unsigned int)v10;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)v21,
          v29);
LABEL_38:
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v32);
        Windows::Internal::String::~String((Windows::Internal::String *)&v34);
        Windows::Internal::String::~String((Windows::Internal::String *)&v33);
        return (unsigned int)v10;
      }
      v28 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 128LL))(*a2, &v29);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(&v32, v28);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v29);
    }
    else if ( v26 < 0 )
    {
      v21 = (unsigned int)v26;
      v20 = 2783;
      goto LABEL_37;
    }
  }
  v6 = 0;
  v7 = v32;
  while ( v6 < a1[63] )
  {
    v8 = *(_QWORD *)(a1[61] + 8 * v6);
    string = v7;
    if ( v7 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 8LL))(v7);
    v9 = OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::DefaultPropertyComparisonRule<Common::StringBuffer>>::Evaluate(
           v4,
           v8,
           &string);
    v10 = v9;
    if ( v9 != -2147023728 && v9 != -2147483637 )
    {
      if ( v9 >= 0 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xAF8,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
                (const char *)0xB7,
                v29);
        goto LABEL_38;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAFA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v9,
        v29);
      v22 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v22 + 16LL))(v22);
      }
      goto LABEL_43;
    }
    v11 = *(const WCHAR **)(v8 + 32);
    if ( !v11 )
    {
      v10 = -2147467261;
LABEL_35:
      v20 = 2795;
      goto LABEL_36;
    }
    string = 0;
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( v12 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
    }
    else
    {
      v10 = WindowsCreateString(v11, v12, &string);
      if ( v10 >= 0 )
      {
        v13 = v33;
        v33 = string;
        WindowsDeleteString(v13);
      }
    }
    if ( v10 < 0 )
      goto LABEL_35;
    v14 = *(const WCHAR **)(v8 + 8);
    if ( !v14 )
    {
      v10 = -2147467261;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAEC,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v10,
        v29);
      v19 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
      }
LABEL_43:
      if ( v34 )
        WindowsDeleteString(v34);
      if ( v33 )
        WindowsDeleteString(v33);
      return (unsigned int)v10;
    }
    string = 0;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
    }
    else
    {
      v10 = WindowsCreateString(v14, v15, &string);
      if ( v10 >= 0 )
      {
        v16 = v34;
        v34 = string;
        WindowsDeleteString(v16);
      }
    }
    if ( v10 < 0 )
      goto LABEL_31;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, HSTRING *))(*(_QWORD *)*a2 + 144LL))(*a2, &v33, &v34) )
    {
      v10 = -2147024882;
      v20 = 2799;
      goto LABEL_36;
    }
    v17 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 128LL))(*a2, &v29);
    v7 = 0;
    if ( &v30 != v17 )
    {
      v7 = *(HSTRING *)v17;
      *(_QWORD *)v17 = 0;
    }
    v18 = v32;
    v32 = v7;
    if ( v18 )
    {
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
      v7 = v32;
    }
    v4 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      v7 = v32;
    }
    ++v6;
  }
  if ( v7 )
  {
    v32 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( v34 )
    WindowsDeleteString(v34);
  if ( v33 )
    WindowsDeleteString(v33);
  return 0;
}

```

## disassembly

```asm
0x1800367ac  push    rbp
0x1800367ae  push    rbx
0x1800367af  push    rsi
0x1800367b0  push    rdi
0x1800367b1  push    r12
0x1800367b3  push    r14
0x1800367b5  push    r15
0x1800367b7  mov     rbp, rsp
0x1800367ba  sub     rsp, 30h
0x1800367be  mov     r15, rdx
0x1800367c1  mov     r14, rcx
0x1800367c4  xor     r12d, r12d
0x1800367c7  mov     [rbp+arg_8], r12
0x1800367cb  mov     [rbp+arg_10], r12
0x1800367cf  mov     rcx, [rdx]
0x1800367d2  mov     rax, [rcx]
0x1800367d5  lea     rdx, [rbp+arg_0]
0x1800367d9  mov     rax, [rax+80h]
0x1800367e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367e5  nop
0x1800367e6  mov     edi, r12d
0x1800367e9  cmp     rdi, [r14+198h]
0x1800367f0  jb      loc_180036AF3
0x1800367f6  mov     rsi, r12
0x1800367f9  mov     rdx, [rbp+arg_0]
0x1800367fd  cmp     rsi, [r14+1F8h]
0x180036804  jnb     loc_180036AAB
0x18003680a  mov     rax, [r14+1E8h]
0x180036811  mov     rdi, [rax+rsi*8]
0x180036815  mov     [rbp+string], rdx
0x180036819  test    rdx, rdx
0x18003681c  jz      short loc_18003682E
0x18003681e  mov     rax, [rdx]
0x180036821  mov     rcx, rdx
0x180036824  mov     rax, [rax+8]
0x180036828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003682d  nop
0x18003682e  lea     r8, [rbp+string]
0x180036832  mov     rdx, rdi
0x180036835  call    ?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@V?$DefaultPropertyComparisonRule@VStringBuffer@Common@@@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::DefaultPropertyComparisonRule<Common::StringBuffer>>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x18003683a  mov     ebx, eax
0x18003683c  cmp     eax, 80070490h
0x180036841  jnz     loc_180036A13
0x180036847  mov     rcx, [rdi+20h]; sourceString
0x18003684b  test    rcx, rcx
0x18003684e  jz      loc_1800369D6
0x180036854  mov     [rbp+string], r12
0x180036858  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003685c  inc     rdx; length
0x18003685f  cmp     [rcx+rdx*2], r12w
0x180036864  jnz     short loc_18003685C
0x180036866  mov     eax, 0FFFFFFFFh
0x18003686b  cmp     rdx, rax
0x18003686e  ja      loc_180036A97
0x180036874  lea     r8, [rbp+string]; string
0x180036878  call    cs:__imp_WindowsCreateString
0x18003687f  nop     dword ptr [rax+rax+00h]
0x180036884  mov     ebx, eax
0x180036886  test    eax, eax
0x180036888  js      short loc_1800368A2
0x18003688a  mov     rcx, [rbp+arg_8]; string
0x18003688e  mov     rax, [rbp+string]
0x180036892  mov     [rbp+arg_8], rax
0x180036896  call    cs:__imp_WindowsDeleteString
0x18003689d  nop     dword ptr [rax+rax+00h]
0x1800368a2  mov     eax, 0FFFFFFFFh
0x1800368a7  test    ebx, ebx
0x1800368a9  js      loc_1800369DB
0x1800368af  mov     rcx, [rdi+8]; sourceString
0x1800368b3  test    rcx, rcx
0x1800368b6  jz      loc_180036999
0x1800368bc  mov     [rbp+string], r12
0x1800368c0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800368c4  inc     rdx; length
0x1800368c7  cmp     [rcx+rdx*2], r12w
0x1800368cc  jnz     short loc_1800368C4
0x1800368ce  cmp     rdx, rax
0x1800368d1  ja      loc_180036AA1
0x1800368d7  lea     r8, [rbp+string]; string
0x1800368db  call    cs:__imp_WindowsCreateString
0x1800368e2  nop     dword ptr [rax+rax+00h]
0x1800368e7  mov     ebx, eax
0x1800368e9  test    eax, eax
0x1800368eb  js      short loc_180036905
0x1800368ed  mov     rcx, [rbp+arg_10]; string
0x1800368f1  mov     rax, [rbp+string]
0x1800368f5  mov     [rbp+arg_10], rax
0x1800368f9  call    cs:__imp_WindowsDeleteString
0x180036900  nop     dword ptr [rax+rax+00h]
0x180036905  test    ebx, ebx
0x180036907  js      loc_18003699E
0x18003690d  mov     rcx, [r15]
0x180036910  mov     rax, [rcx]
0x180036913  lea     r8, [rbp+arg_10]
0x180036917  lea     rdx, [rbp+arg_8]
0x18003691b  mov     rax, [rax+90h]
0x180036922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036927  test    al, al
0x180036929  jz      loc_180036BDA
0x18003692f  mov     rcx, [r15]
0x180036932  mov     rax, [rcx]
0x180036935  lea     rdx, [rbp+var_10]
0x180036939  mov     rax, [rax+80h]
0x180036940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036945  mov     rdx, r12
0x180036948  lea     rcx, [rbp+var_8]
0x18003694c  cmp     rcx, rax
0x18003694f  jz      short loc_180036957
0x180036951  mov     rdx, [rax]
0x180036954  mov     [rax], r12
0x180036957  mov     rcx, [rbp+arg_0]
0x18003695b  mov     [rbp+arg_0], rdx
0x18003695f  test    rcx, rcx
0x180036962  jz      short loc_180036974
0x180036964  mov     rax, [rcx]
0x180036967  mov     rax, [rax+10h]
0x18003696b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036970  mov     rdx, [rbp+arg_0]
0x180036974  mov     rcx, [rbp+var_10]
0x180036978  test    rcx, rcx
0x18003697b  jz      short loc_180036991
0x18003697d  mov     [rbp+var_10], r12
0x180036981  mov     rax, [rcx]
0x180036984  mov     rax, [rax+10h]
0x180036988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003698d  mov     rdx, [rbp+arg_0]
0x180036991  inc     rsi
0x180036994  jmp     loc_1800367FD
0x180036999  mov     ebx, 80004003h
0x18003699e  mov     rcx, [rbp+38h]; this
0x1800369a2  mov     r9d, ebx; char *
0x1800369a5  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800369ac  mov     edx, 0AECh; void *
0x1800369b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369b6  nop
0x1800369b7  mov     rcx, [rbp+arg_0]
0x1800369bb  test    rcx, rcx
0x1800369be  jz      short loc_1800369D1
0x1800369c0  mov     [rbp+arg_0], r12
0x1800369c4  mov     rax, [rcx]
0x1800369c7  mov     rax, [rax+10h]
0x1800369cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369d0  nop
0x1800369d1  jmp     loc_180036A5A
0x1800369d6  mov     ebx, 80004003h
0x1800369db  mov     edx, 0AEBh; void *
0x1800369e0  mov     r9d, ebx; char *
0x1800369e3  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800369ea  mov     rcx, [rbp+38h]; this
0x1800369ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369f3  nop
0x1800369f4  lea     rcx, [rbp+arg_0]
0x1800369f8  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800369fd  nop
0x1800369fe  lea     rcx, [rbp+arg_10]; this
0x180036a02  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180036a07  nop
0x180036a08  lea     rcx, [rbp+arg_8]; this
0x180036a0c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180036a11  jmp     short loc_180036A85
0x180036a13  cmp     ebx, 8000000Bh
0x180036a19  jz      loc_180036847
0x180036a1f  mov     rcx, [rbp+38h]; this
0x180036a23  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180036a2a  test    ebx, ebx
0x180036a2c  jns     loc_180036BC3
0x180036a32  mov     r9d, ebx; char *
0x180036a35  mov     edx, 0AFAh; void *
0x180036a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a3f  nop
0x180036a40  mov     rcx, [rbp+arg_0]
0x180036a44  test    rcx, rcx
0x180036a47  jz      short loc_180036A5A
0x180036a49  mov     [rbp+arg_0], r12
0x180036a4d  mov     rax, [rcx]
0x180036a50  mov     rax, [rax+10h]
0x180036a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a59  nop
0x180036a5a  mov     rcx, [rbp+arg_10]; string
0x180036a5e  test    rcx, rcx
0x180036a61  jz      short loc_180036A70
0x180036a63  call    cs:__imp_WindowsDeleteString
0x180036a6a  nop     dword ptr [rax+rax+00h]
0x180036a6f  nop
0x180036a70  mov     rcx, [rbp+arg_8]; string
0x180036a74  test    rcx, rcx
0x180036a77  jz      short loc_180036A85
0x180036a79  call    cs:__imp_WindowsDeleteString
0x180036a80  nop     dword ptr [rax+rax+00h]
0x180036a85  mov     eax, ebx
0x180036a87  add     rsp, 30h
0x180036a8b  pop     r15
0x180036a8d  pop     r14
0x180036a8f  pop     r12
0x180036a91  pop     rdi
0x180036a92  pop     rsi
0x180036a93  pop     rbx
0x180036a94  pop     rbp
0x180036a95  retn
0x180036a97  mov     ebx, 80070216h
0x180036a9c  jmp     loc_1800368A7
0x180036aa1  mov     ebx, 80070216h
0x180036aa6  jmp     loc_180036905
0x180036aab  test    rdx, rdx
0x180036aae  jz      short loc_180036AC4
0x180036ab0  mov     [rbp+arg_0], r12
0x180036ab4  mov     rax, [rdx]
0x180036ab7  mov     rcx, rdx
0x180036aba  mov     rax, [rax+10h]
0x180036abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac3  nop
0x180036ac4  mov     rcx, [rbp+arg_10]; string
0x180036ac8  test    rcx, rcx
0x180036acb  jz      short loc_180036ADA
0x180036acd  call    cs:__imp_WindowsDeleteString
0x180036ad4  nop     dword ptr [rax+rax+00h]
0x180036ad9  nop
0x180036ada  mov     rcx, [rbp+arg_8]; string
0x180036ade  test    rcx, rcx
0x180036ae1  jz      short loc_180036AEF
0x180036ae3  call    cs:__imp_WindowsDeleteString
0x180036aea  nop     dword ptr [rax+rax+00h]
0x180036aef  xor     eax, eax
0x180036af1  jmp     short loc_180036A87
0x180036af3  mov     rax, [r14+188h]
0x180036afa  mov     rsi, [rax+rdi*8]
0x180036afe  mov     rax, [rbp+arg_0]
0x180036b02  mov     [rbp+string], rax
0x180036b06  lea     rcx, [rbp+string]
0x180036b0a  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x180036b0f  lea     r8, [rbp+string]
0x180036b13  mov     rdx, rsi
0x180036b16  call    ?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180036b1b  mov     ebx, eax
0x180036b1d  cmp     eax, 80070490h
0x180036b22  jz      short loc_180036B3C
0x180036b24  cmp     eax, 8000000Bh
0x180036b29  jz      short loc_180036B3C
0x180036b2b  test    eax, eax
0x180036b2d  jns     short loc_180036B9F
0x180036b2f  mov     r9d, eax
0x180036b32  mov     edx, 0ADFh
0x180036b37  jmp     loc_1800369E3
0x180036b3c  mov     rax, [rsi+10h]
0x180036b40  mov     [rbp+string], rax
0x180036b44  lea     rdx, [rbp+string]
0x180036b48  lea     rcx, [rbp+arg_8]
0x180036b4c  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180036b51  mov     ebx, eax
0x180036b53  test    eax, eax
0x180036b55  js      short loc_180036BB6
0x180036b57  mov     rcx, [r15]
0x180036b5a  mov     rax, [rcx]
0x180036b5d  mov     r8d, [rsi]
0x180036b60  lea     rdx, [rbp+arg_8]
0x180036b64  mov     rax, [rax+88h]
0x180036b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b70  test    al, al
0x180036b72  jz      short loc_180036BA7
0x180036b74  mov     rcx, [r15]
0x180036b77  mov     rax, [rcx]
0x180036b7a  lea     rdx, [rbp+var_10]
0x180036b7e  mov     rax, [rax+80h]
0x180036b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b8a  mov     rdx, rax
0x180036b8d  lea     rcx, [rbp+arg_0]
0x180036b91  call    ??4?$ComPtr@UExeServerRegistration@DEH@OSIntegration@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration> &&)
0x180036b96  lea     rcx, [rbp+var_10]
0x180036b9a  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180036b9f  inc     rdi
0x180036ba2  jmp     loc_1800367E9
0x180036ba7  mov     ebx, 8007000Eh
0x180036bac  mov     edx, 0AD7h
0x180036bb1  jmp     loc_1800369E0
0x180036bb6  mov     r9d, eax
0x180036bb9  mov     edx, 0AD6h
0x180036bbe  jmp     loc_1800369E3
0x180036bc3  mov     r9d, 0B7h; char *
0x180036bc9  mov     edx, 0AF8h; void *
0x180036bce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036bd3  mov     ebx, eax
0x180036bd5  jmp     loc_1800369F4
0x180036bda  mov     ebx, 8007000Eh
0x180036bdf  mov     edx, 0AEFh
0x180036be4  jmp     loc_1800369E0
```

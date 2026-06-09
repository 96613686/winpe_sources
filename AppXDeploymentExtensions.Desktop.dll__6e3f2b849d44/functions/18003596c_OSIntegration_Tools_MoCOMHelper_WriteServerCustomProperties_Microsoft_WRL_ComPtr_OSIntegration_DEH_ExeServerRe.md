# OSIntegration::Tools::MoCOMHelper::WriteServerCustomProperties(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration> &)

- ea: `0x18003596c`
- end: `0x180035cc5`
- name: `?WriteServerCustomProperties@MoCOMHelper@Tools@OSIntegration@@AEBAJAEAV?$ComPtr@UExeServerRegistration@DEH@OSIntegration@@@WRL@Microsoft@@@Z`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a670`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x18003596c`
- `0x1800361a8`
- `0x18003647c`
- `0x180036e58`
- `0x180036eb4`
- `0x18003dbd0`
- `0x18004d910`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035aed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800359fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035aed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035b03`

## string_xrefs

- `0x180035ab8`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180035c92`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::WriteServerCustomProperties(_QWORD *a1, _QWORD *a2)
{
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rdi
  HSTRING v6; // rcx
  unsigned int *v8; // rsi
  __int64 v9; // rcx
  int v10; // eax
  HRESULT v11; // ebx
  const WCHAR *v12; // rcx
  unsigned __int64 v13; // rdx
  HSTRING v14; // rcx
  HSTRING v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  HSTRING v24; // [rsp+70h] [rbp+40h] BYREF
  HSTRING v25; // [rsp+78h] [rbp+48h] BYREF
  HSTRING string; // [rsp+80h] [rbp+50h] BYREF
  HSTRING v27; // [rsp+88h] [rbp+58h] BYREF

  v25 = 0;
  string = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a2 + 176LL))(*a2, &v24);
  for ( i = 0; i < a1[59]; ++i )
  {
    v8 = *(unsigned int **)(a1[57] + 8 * i);
    v27 = v24;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v27);
    v10 = OSIntegration::Tools::PropertyMatchingAlgorithm<unsigned long,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(
            v9,
            v8,
            &v27);
    v11 = v10;
    if ( v10 == -2147023728 || v10 == -2147483637 )
    {
      v12 = (const WCHAR *)*((_QWORD *)v8 + 2);
      if ( !v12 )
      {
        v11 = -2147467261;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA95,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v11,
          v22[0]);
        v15 = v24;
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        }
        if ( string )
          WindowsDeleteString(string);
        if ( v25 )
          WindowsDeleteString(v25);
        return (unsigned int)v11;
      }
      v27 = 0;
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 > 0xFFFFFFFF )
      {
        v11 = -2147024362;
      }
      else
      {
        v11 = WindowsCreateString(v12, v13, &v27);
        if ( v11 >= 0 )
        {
          v14 = v25;
          v25 = v27;
          WindowsDeleteString(v14);
        }
      }
      if ( v11 < 0 )
        goto LABEL_20;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, _QWORD))(*(_QWORD *)*a2 + 296LL))(*a2, &v25, *v8) )
      {
        v11 = -2147024882;
        v18 = 2147942414LL;
        v16 = 2710;
        goto LABEL_49;
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 176LL))(*a2, v22);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(&v24, v17);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v22);
    }
    else if ( v10 < 0 )
    {
      v16 = 2718;
LABEL_48:
      v18 = (unsigned int)v10;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)v18,
        v22[0]);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v24);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v25);
      return (unsigned int)v11;
    }
  }
  for ( j = 0; j < a1[71]; ++j )
  {
    v19 = *(_QWORD *)(a1[69] + 8 * j);
    v27 = v24;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v27);
    v10 = OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(
            v20,
            v19,
            &v27);
    v11 = v10;
    if ( v10 == -2147023728 || v10 == -2147483637 )
    {
      v27 = *(HSTRING *)(v19 + 32);
      v10 = Windows::Internal::String::Initialize<unsigned short const *>(&v25, &v27);
      v11 = v10;
      if ( v10 < 0 )
      {
        v16 = 2732;
        goto LABEL_48;
      }
      v27 = *(HSTRING *)(v19 + 8);
      v10 = Windows::Internal::String::Initialize<unsigned short const *>(&string, &v27);
      v11 = v10;
      if ( v10 < 0 )
      {
        v16 = 2733;
        goto LABEL_48;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, HSTRING *, HSTRING *))(*(_QWORD *)*a2 + 304LL))(
              *a2,
              &v25,
              &string) )
      {
        v11 = -2147024882;
        v18 = 2147942414LL;
        v16 = 2734;
        goto LABEL_49;
      }
      v21 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 176LL))(*a2, v22);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(&v24, v21);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v22);
    }
    else if ( v10 < 0 )
    {
      v16 = 2742;
      goto LABEL_48;
    }
  }
  v6 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v25 )
    WindowsDeleteString(v25);
  return 0;
}

```

## disassembly

```asm
0x18003596c  push    rbp
0x18003596e  push    rbx
0x18003596f  push    rsi
0x180035970  push    rdi
0x180035971  push    r12
0x180035973  push    r14
0x180035975  push    r15
0x180035977  mov     rbp, rsp
0x18003597a  sub     rsp, 30h
0x18003597e  mov     r15, rdx
0x180035981  mov     r14, rcx
0x180035984  xor     r12d, r12d
0x180035987  mov     [rbp+arg_8], r12
0x18003598b  mov     [rbp+string], r12
0x18003598f  mov     rcx, [rdx]
0x180035992  mov     rax, [rcx]
0x180035995  lea     rdx, [rbp+arg_0]
0x180035999  mov     rax, [rax+0B0h]
0x1800359a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359a5  nop
0x1800359a6  mov     edi, r12d
0x1800359a9  cmp     rdi, [r14+1D8h]
0x1800359b0  jb      short loc_180035A19
0x1800359b2  mov     rdi, r12
0x1800359b5  cmp     rdi, [r14+238h]
0x1800359bc  jb      loc_180035B9F
0x1800359c2  mov     rcx, [rbp+arg_0]
0x1800359c6  test    rcx, rcx
0x1800359c9  jz      short loc_1800359DC
0x1800359cb  mov     [rbp+arg_0], r12
0x1800359cf  mov     rax, [rcx]
0x1800359d2  mov     rax, [rax+10h]
0x1800359d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359db  nop
0x1800359dc  mov     rcx, [rbp+string]; string
0x1800359e0  test    rcx, rcx
0x1800359e3  jz      short loc_1800359F2
0x1800359e5  call    cs:__imp_WindowsDeleteString
0x1800359ec  nop     dword ptr [rax+rax+00h]
0x1800359f1  nop
0x1800359f2  mov     rcx, [rbp+arg_8]; string
0x1800359f6  test    rcx, rcx
0x1800359f9  jz      short loc_180035A07
0x1800359fb  call    cs:__imp_WindowsDeleteString
0x180035a02  nop     dword ptr [rax+rax+00h]
0x180035a07  xor     eax, eax
0x180035a09  add     rsp, 30h
0x180035a0d  pop     r15
0x180035a0f  pop     r14
0x180035a11  pop     r12
0x180035a13  pop     rdi
0x180035a14  pop     rsi
0x180035a15  pop     rbx
0x180035a16  pop     rbp
0x180035a17  retn
0x180035a19  mov     rax, [r14+1C8h]
0x180035a20  mov     rsi, [rax+rdi*8]
0x180035a24  mov     rax, [rbp+arg_0]
0x180035a28  mov     [rbp+arg_18], rax
0x180035a2c  lea     rcx, [rbp+arg_18]
0x180035a30  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x180035a35  lea     r8, [rbp+arg_18]
0x180035a39  mov     rdx, rsi
0x180035a3c  call    ?Evaluate@?$PropertyMatchingAlgorithm@KVDwordPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@K@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<ulong,OSIntegration::Tools::DwordPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<ulong> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180035a41  mov     ebx, eax
0x180035a43  cmp     eax, 80070490h
0x180035a48  jnz     loc_180035B24
0x180035a4e  mov     rcx, [rsi+10h]; sourceString
0x180035a52  test    rcx, rcx
0x180035a55  jz      loc_180035B16
0x180035a5b  mov     [rbp+arg_18], r12
0x180035a5f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035a63  inc     rdx; length
0x180035a66  cmp     [rcx+rdx*2], r12w
0x180035a6b  jnz     short loc_180035A63
0x180035a6d  mov     eax, 0FFFFFFFFh
0x180035a72  cmp     rdx, rax
0x180035a75  ja      loc_180035B1D
0x180035a7b  lea     r8, [rbp+arg_18]; string
0x180035a7f  call    cs:__imp_WindowsCreateString
0x180035a86  nop     dword ptr [rax+rax+00h]
0x180035a8b  mov     ebx, eax
0x180035a8d  test    eax, eax
0x180035a8f  js      short loc_180035AA9
0x180035a91  mov     rcx, [rbp+arg_8]; string
0x180035a95  mov     rax, [rbp+arg_18]
0x180035a99  mov     [rbp+arg_8], rax
0x180035a9d  call    cs:__imp_WindowsDeleteString
0x180035aa4  nop     dword ptr [rax+rax+00h]
0x180035aa9  test    ebx, ebx
0x180035aab  jns     loc_180035B3D
0x180035ab1  mov     rcx, [rbp+38h]; this
0x180035ab5  mov     r9d, ebx; char *
0x180035ab8  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180035abf  mov     edx, 0A95h; void *
0x180035ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ac9  nop
0x180035aca  mov     rcx, [rbp+arg_0]
0x180035ace  test    rcx, rcx
0x180035ad1  jz      short loc_180035AE4
0x180035ad3  mov     [rbp+arg_0], r12
0x180035ad7  mov     rax, [rcx]
0x180035ada  mov     rax, [rax+10h]
0x180035ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ae3  nop
0x180035ae4  mov     rcx, [rbp+string]; string
0x180035ae8  test    rcx, rcx
0x180035aeb  jz      short loc_180035AFA
0x180035aed  call    cs:__imp_WindowsDeleteString
0x180035af4  nop     dword ptr [rax+rax+00h]
0x180035af9  nop
0x180035afa  mov     rcx, [rbp+arg_8]; string
0x180035afe  test    rcx, rcx
0x180035b01  jz      short loc_180035B0F
0x180035b03  call    cs:__imp_WindowsDeleteString
0x180035b0a  nop     dword ptr [rax+rax+00h]
0x180035b0f  mov     eax, ebx
0x180035b11  jmp     loc_180035A09
0x180035b16  mov     ebx, 80004003h
0x180035b1b  jmp     short loc_180035AB1
0x180035b1d  mov     ebx, 80070216h
0x180035b22  jmp     short loc_180035AA9
0x180035b24  cmp     eax, 8000000Bh
0x180035b29  jz      loc_180035A4E
0x180035b2f  test    eax, eax
0x180035b31  jns     short loc_180035B85
0x180035b33  mov     edx, 0A9Eh
0x180035b38  jmp     loc_180035C8F
0x180035b3d  mov     rcx, [r15]
0x180035b40  mov     rax, [rcx]
0x180035b43  mov     r8d, [rsi]
0x180035b46  lea     rdx, [rbp+arg_8]
0x180035b4a  mov     rax, [rax+128h]
0x180035b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b56  test    al, al
0x180035b58  jz      short loc_180035B8D
0x180035b5a  mov     rcx, [r15]
0x180035b5d  mov     rax, [rcx]
0x180035b60  lea     rdx, [rbp+var_10]
0x180035b64  mov     rax, [rax+0B0h]
0x180035b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b70  mov     rdx, rax
0x180035b73  lea     rcx, [rbp+arg_0]
0x180035b77  call    ??4?$ComPtr@UExeServerRegistration@DEH@OSIntegration@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration> &&)
0x180035b7c  lea     rcx, [rbp+var_10]
0x180035b80  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180035b85  inc     rdi
0x180035b88  jmp     loc_1800359A9
0x180035b8d  mov     ebx, 8007000Eh
0x180035b92  mov     r9d, ebx
0x180035b95  mov     edx, 0A96h
0x180035b9a  jmp     loc_180035C92
0x180035b9f  mov     rax, [r14+228h]
0x180035ba6  mov     rsi, [rax+rdi*8]
0x180035baa  mov     rax, [rbp+arg_0]
0x180035bae  mov     [rbp+arg_18], rax
0x180035bb2  lea     rcx, [rbp+arg_18]
0x180035bb6  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x180035bbb  lea     r8, [rbp+arg_18]
0x180035bbf  mov     rdx, rsi
0x180035bc2  call    ?Evaluate@?$PropertyMatchingAlgorithm@VStringBuffer@Common@@VStringPropertyComparisonRule@Tools@OSIntegration@@@Tools@OSIntegration@@QEAAJPEBV?$Property@VStringBuffer@Common@@@Internal@23@V?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; OSIntegration::Tools::PropertyMatchingAlgorithm<Common::StringBuffer,OSIntegration::Tools::StringPropertyComparisonRule>::Evaluate(OSIntegration::Tools::Internal::Property<Common::StringBuffer> const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>)
0x180035bc7  mov     ebx, eax
0x180035bc9  cmp     eax, 80070490h
0x180035bce  jz      short loc_180035BE9
0x180035bd0  cmp     eax, 8000000Bh
0x180035bd5  jz      short loc_180035BE9
0x180035bd7  test    eax, eax
0x180035bd9  jns     loc_180035C6C
0x180035bdf  mov     edx, 0AB6h
0x180035be4  jmp     loc_180035C8F
0x180035be9  mov     rax, [rsi+20h]
0x180035bed  mov     [rbp+arg_18], rax
0x180035bf1  lea     rdx, [rbp+arg_18]
0x180035bf5  lea     rcx, [rbp+arg_8]
0x180035bf9  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180035bfe  mov     ebx, eax
0x180035c00  test    eax, eax
0x180035c02  js      loc_180035C8A
0x180035c08  mov     rax, [rsi+8]
0x180035c0c  mov     [rbp+arg_18], rax
0x180035c10  lea     rdx, [rbp+arg_18]
0x180035c14  lea     rcx, [rbp+string]
0x180035c18  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180035c1d  mov     ebx, eax
0x180035c1f  test    eax, eax
0x180035c21  js      short loc_180035C83
0x180035c23  mov     rcx, [r15]
0x180035c26  mov     rax, [rcx]
0x180035c29  lea     r8, [rbp+string]
0x180035c2d  lea     rdx, [rbp+arg_8]
0x180035c31  mov     rax, [rax+130h]
0x180035c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c3d  test    al, al
0x180035c3f  jz      short loc_180035C74
0x180035c41  mov     rcx, [r15]
0x180035c44  mov     rax, [rcx]
0x180035c47  lea     rdx, [rbp+var_10]
0x180035c4b  mov     rax, [rax+0B0h]
0x180035c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c57  mov     rdx, rax
0x180035c5a  lea     rcx, [rbp+arg_0]
0x180035c5e  call    ??4?$ComPtr@UExeServerRegistration@DEH@OSIntegration@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration>::operator=(Microsoft::WRL::ComPtr<OSIntegration::DEH::ExeServerRegistration> &&)
0x180035c63  lea     rcx, [rbp+var_10]
0x180035c67  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180035c6c  inc     rdi
0x180035c6f  jmp     loc_1800359B5
0x180035c74  mov     ebx, 8007000Eh
0x180035c79  mov     r9d, ebx
0x180035c7c  mov     edx, 0AAEh
0x180035c81  jmp     short loc_180035C92
0x180035c83  mov     edx, 0AADh
0x180035c88  jmp     short loc_180035C8F
0x180035c8a  mov     edx, 0AACh; void *
0x180035c8f  mov     r9d, eax; char *
0x180035c92  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180035c99  mov     rcx, [rbp+38h]; this
0x180035c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ca2  nop
0x180035ca3  lea     rcx, [rbp+arg_0]
0x180035ca7  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180035cac  nop
0x180035cad  lea     rcx, [rbp+string]; this
0x180035cb1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180035cb6  nop
0x180035cb7  lea     rcx, [rbp+arg_8]; this
0x180035cbb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180035cc0  jmp     loc_180035B0F
```

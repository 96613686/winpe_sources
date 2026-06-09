# Windows::Internal::UI::ApplicationSettings::WebAccountProviderData::CloneWebAccountProvider(Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x180039f34`
- end: `0x18003a17e`
- name: `?CloneWebAccountProvider@WebAccountProviderData@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccountProvider@Credentials@Security@5@PEAPEAU6785@@Z`
- size: `586`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::WebAccountProviderData *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bfbc`
- `0x18003c084`
- `0x18003c160`

## callees

- `0x180006eac`
- `0x180011f64`
- `0x180011ffc`
- `0x180038f9c`
- `0x180039f34`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a062`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a049`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a083`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a083`

## string_xrefs

- `0x18003a042`: `Windows.Internal.Security.Credentials.WebAccountProviderInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::WebAccountProviderData::CloneWebAccountProvider(
        Windows::Internal::UI::ApplicationSettings::WebAccountProviderData *this,
        void (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        struct Windows::Security::Credentials::IWebAccountProvider **a3)
{
  void (__fastcall *v5)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, void *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-49h]
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-29h] BYREF
  __int64 v20; // [rsp+48h] [rbp-21h] BYREF
  void *v21; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-11h] BYREF
  char v23; // [rsp+68h] [rbp-1h]
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a3 = 0;
  v20 = 0;
  string = (HSTRING)a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
  v5 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v5((struct Windows::Security::Credentials::IWebAccountProvider *)a2, &GUID_ad7b0e08_6151_4da3_b6ba_890936053b0e, &v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  v21 = 0;
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v20 + 32LL))(v20, &v21, &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = v20;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
    hstringHeader.Reserved.Reserved1 = v21;
    v22[0] = v8;
    string = 0;
    v22[1] = v21;
    v23 = 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    v17 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.Security.Credentials.WebAccountProviderInternal",
           0x40u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v9 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    ActivationFactory = RoGetActivationFactory(v9, &GUID_4f81bfe6_fdb4_4dc4_86b9_4af32d514b78, &v17);
    v7 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v18 = 0;
      v11 = v17;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, void *, __int64 *))(*(_QWORD *)v17 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      v13 = v12(v11, v19, v21, &v18);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v18 + 48LL))(
                v18,
                a3);
        v7 = v13;
        if ( v13 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          wil::details::ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___::_ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___(v22);
          v7 = 0;
          goto LABEL_16;
        }
        v14 = 155;
      }
      else
      {
        v14 = 154;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
        (const char *)(unsigned int)v13,
        v16);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v16);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    wil::details::ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___::_ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___(v22);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v6,
      v16);
  }
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return v7;
}

```

## disassembly

```asm
0x180039f34  push    rbp
0x180039f36  push    rbx
0x180039f37  push    rsi
0x180039f38  push    rdi
0x180039f39  lea     rbp, [rsp-3Fh]
0x180039f3e  sub     rsp, 0A8h
0x180039f45  mov     rax, cs:__security_cookie
0x180039f4c  xor     rax, rsp
0x180039f4f  mov     [rbp+57h+var_30], rax
0x180039f53  mov     rsi, r8
0x180039f56  mov     rdi, rdx
0x180039f59  mov     qword ptr [r8], 0
0x180039f60  mov     [rbp+57h+var_78], 0
0x180039f68  mov     [rbp+57h+string], rdx
0x180039f6c  lea     rcx, [rbp+57h+string]
0x180039f70  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180039f75  nop
0x180039f76  mov     rax, [rdi]
0x180039f79  mov     rbx, [rax]
0x180039f7c  lea     rcx, [rbp+57h+var_78]
0x180039f80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039f85  lea     r8, [rbp+57h+var_78]
0x180039f89  lea     rdx, _GUID_ad7b0e08_6151_4da3_b6ba_890936053b0e
0x180039f90  mov     rcx, rdi
0x180039f93  mov     rax, rbx
0x180039f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f9b  nop
0x180039f9c  lea     rcx, [rbp+57h+string]
0x180039fa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039fa5  mov     [rbp+57h+var_70], 0
0x180039fad  mov     [rbp+57h+var_80], 0
0x180039fb4  mov     rcx, [rbp+57h+var_78]
0x180039fb8  mov     rax, [rcx]
0x180039fbb  lea     r8, [rbp+57h+var_80]
0x180039fbf  lea     rdx, [rbp+57h+var_70]
0x180039fc3  mov     rax, [rax+20h]
0x180039fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fcc  mov     ebx, eax
0x180039fce  test    eax, eax
0x180039fd0  jns     short loc_180039FEF
0x180039fd2  mov     rcx, [rbp+5Fh]; this
0x180039fd6  mov     r9d, eax; char *
0x180039fd9  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039fe0  mov     edx, 87h; void *
0x180039fe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fea  jmp     loc_18003A15B
0x180039fef  mov     rbx, [rbp+57h+var_78]
0x180039ff3  test    rbx, rbx
0x180039ff6  jz      short loc_18003A008
0x180039ff8  mov     rax, [rbx]
0x180039ffb  mov     rcx, rbx
0x180039ffe  mov     rax, [rax+8]
0x18003a002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a007  nop
0x18003a008  mov     rax, [rbp+57h+var_70]
0x18003a00c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18003a010  mov     [rbp+57h+var_68], rbx
0x18003a014  mov     [rbp+57h+string], 0
0x18003a01c  mov     [rbp+57h+var_60], rax
0x18003a020  mov     [rbp+57h+var_58], 1
0x18003a024  lea     rcx, [rbp+57h+string]
0x18003a028  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a02d  mov     [rbp+57h+var_90], 0
0x18003a035  lea     r9, [rbp+57h+string]; string
0x18003a039  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003a03d  mov     edx, 40h ; '@'; length
0x18003a042  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Credentials_WebAccountProviderInternal@@3QBGB; "Windows.Internal.Security.Credentials.W"...
0x18003a049  call    cs:__imp_WindowsCreateStringReference
0x18003a04f  test    eax, eax
0x18003a051  jns     short loc_18003A068
0x18003a053  xor     r9d, r9d; lpArguments
0x18003a056  xor     r8d, r8d; nNumberOfArguments
0x18003a059  lea     edx, [r9+1]; dwExceptionFlags
0x18003a05d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003a062  call    cs:__imp_RaiseException
0x18003a068  mov     rbx, [rbp+57h+string]
0x18003a06c  lea     rcx, [rbp+57h+var_90]
0x18003a070  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a075  lea     r8, [rbp+57h+var_90]
0x18003a079  lea     rdx, _GUID_4f81bfe6_fdb4_4dc4_86b9_4af32d514b78
0x18003a080  mov     rcx, rbx
0x18003a083  call    cs:__imp_RoGetActivationFactory
0x18003a089  mov     ebx, eax
0x18003a08b  test    eax, eax
0x18003a08d  jns     short loc_18003A0C0
0x18003a08f  mov     rcx, [rbp+5Fh]; this
0x18003a093  mov     r9d, eax; char *
0x18003a096  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003a09d  mov     edx, 94h; void *
0x18003a0a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0a7  nop
0x18003a0a8  lea     rcx, [rbp+57h+var_90]
0x18003a0ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a0b1  nop
0x18003a0b2  lea     rcx, [rbp+57h+var_68]
0x18003a0b6  call    wil__details__ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff______ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___
0x18003a0bb  jmp     loc_18003A15B
0x18003a0c0  mov     [rbp+57h+var_88], 0
0x18003a0c8  mov     rdi, [rbp+57h+var_90]
0x18003a0cc  mov     rax, [rdi]
0x18003a0cf  mov     rbx, [rax+38h]
0x18003a0d3  lea     rcx, [rbp+57h+var_88]
0x18003a0d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a0dc  lea     r9, [rbp+57h+var_88]
0x18003a0e0  mov     r8, [rbp+57h+var_70]
0x18003a0e4  mov     edx, [rbp+57h+var_80]
0x18003a0e7  mov     rcx, rdi
0x18003a0ea  mov     rax, rbx
0x18003a0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0f2  mov     ebx, eax
0x18003a0f4  test    eax, eax
0x18003a0f6  jns     short loc_18003A11C
0x18003a0f8  mov     edx, 9Ah; void *
0x18003a0fd  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003a104  mov     r9d, eax; char *
0x18003a107  mov     rcx, [rbp+5Fh]; this
0x18003a10b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a110  nop
0x18003a111  lea     rcx, [rbp+57h+var_88]
0x18003a115  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a11a  jmp     short loc_18003A0A8
0x18003a11c  mov     rcx, [rbp+57h+var_88]
0x18003a120  mov     rax, [rcx]
0x18003a123  mov     rdx, rsi
0x18003a126  mov     rax, [rax+30h]
0x18003a12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a12f  mov     ebx, eax
0x18003a131  test    eax, eax
0x18003a133  jns     short loc_18003A13C
0x18003a135  mov     edx, 9Bh
0x18003a13a  jmp     short loc_18003A0FD
0x18003a13c  lea     rcx, [rbp+57h+var_88]
0x18003a140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a145  nop
0x18003a146  lea     rcx, [rbp+57h+var_90]
0x18003a14a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a14f  nop
0x18003a150  lea     rcx, [rbp+57h+var_68]
0x18003a154  call    wil__details__ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff______ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___
0x18003a159  xor     ebx, ebx
0x18003a15b  lea     rcx, [rbp+57h+var_78]
0x18003a15f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a164  mov     eax, ebx
0x18003a166  mov     rcx, [rbp+57h+var_30]
0x18003a16a  xor     rcx, rsp; StackCookie
0x18003a16d  call    __security_check_cookie
0x18003a172  add     rsp, 0A8h
0x18003a179  pop     rdi
0x18003a17a  pop     rsi
0x18003a17b  pop     rbx
0x18003a17c  pop     rbp
0x18003a17d  retn
```

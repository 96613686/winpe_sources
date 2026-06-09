# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18008e400`
- end: `0x18008e86c`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x18001e61c`
- `0x1800272d4`
- `0x18008d258`
- `0x18008e400`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e80a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e7fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e80a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e65b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e74c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e65b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008e74c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008e4dc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008e4dc`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v8)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HSTRING v14; // rbx
  __int64 (__fastcall *v15)(char *, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rax
  __int64 (__fastcall *v18)(char *, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // rax
  __int64 (__fastcall *v21)(char *, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdx
  _QWORD *v27; // rbx
  __int64 v28; // rsi
  __int64 v29; // rdi
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, HSTRING, __int64 *); // rbx
  int v35; // eax
  __int64 v36; // rdx
  _QWORD *v37; // rbx
  __int64 v38; // rsi
  __int64 v39; // rdi
  HRESULT v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  __int64 v43; // rbx
  _QWORD *v44; // rdi
  __int64 v45; // rsi
  HRESULT v46; // eax
  int v47; // edx
  unsigned int v48; // r8d
  int v49; // [rsp+20h] [rbp-39h]
  _BYTE v50[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v51; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v52; // [rsp+40h] [rbp-19h] BYREF
  __int64 v53; // [rsp+48h] [rbp-11h] BYREF
  __int64 v54; // [rsp+50h] [rbp-9h] BYREF
  __int64 v55; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v56; // [rsp+60h] [rbp+7h] BYREF
  __int64 v57; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  HSTRING string; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(
         (CLaunchActivatedEventArgs *)((char *)this - 256),
         a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v4,
      v49);
    return v5;
  }
  v7 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v56 = 0;
  v57 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v56);
  ActivationFactory = v8(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v56);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 105;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v49);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v56);
    return v5;
  }
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    __debugbreak();
  }
  v14 = string;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v57);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v57);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 106;
    goto LABEL_9;
  }
  v51 = 0;
  v15 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
  WindowsDeleteString(0);
  v51 = 0;
  v16 = v15((char *)this - 16, &v51);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v16,
      v49);
LABEL_35:
    WindowsDeleteString(v51);
    v51 = 0;
    goto LABEL_36;
  }
  v17 = *((_QWORD *)this - 2);
  v52 = 0;
  v18 = *(__int64 (__fastcall **)(char *, HSTRING *))(v17 + 56);
  WindowsDeleteString(0);
  v52 = 0;
  v19 = v18((char *)this - 16, &v52);
  v5 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v19,
      v49);
LABEL_34:
    WindowsDeleteString(v52);
    v52 = 0;
    goto LABEL_35;
  }
  v20 = *((_QWORD *)this - 1);
  v53 = 0;
  v21 = *(__int64 (__fastcall **)(char *, __int64 *))(v20 + 48);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v53);
  v22 = v21((char *)this - 8, &v53);
  v5 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v22,
      v49);
LABEL_33:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v53);
    goto LABEL_34;
  }
  v23 = v57;
  v54 = 0;
  v24 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v57 + 144LL);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v54);
  v25 = v24(v23, v51, &v54);
  v5 = v25;
  if ( v25 < 0 )
  {
    v26 = 120;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v25,
      v49);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v54);
    goto LABEL_33;
  }
  v27 = v56;
  v28 = v54;
  v50[0] = 0;
  v29 = *v56;
  string = 0;
  v30 = WindowsCreateStringReference(L"Arguments", 9u, &hstringHeader, &string);
  if ( v30 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
    __debugbreak();
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v29 + 80))(v27, string, v28, v50);
  v5 = v25;
  if ( v25 < 0 )
  {
    v26 = 122;
    goto LABEL_18;
  }
  v33 = v57;
  v55 = 0;
  v34 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v57 + 144LL);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v55);
  v35 = v34(v33, v52, &v55);
  v5 = v35;
  if ( v35 < 0 )
  {
    v36 = 125;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v35,
      v49);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v55);
    goto LABEL_32;
  }
  v37 = v56;
  v38 = v55;
  v39 = *v56;
  string = 0;
  v40 = WindowsCreateStringReference(L"TileId", 6u, &hstringHeader, &string);
  if ( v40 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
    JUMPOUT(0x18008E86BLL);
  }
  v35 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v39 + 80))(v37, string, v38, v50);
  v5 = v35;
  if ( v35 < 0 )
  {
    v36 = 126;
    goto LABEL_31;
  }
  v43 = v53;
  if ( v53 )
  {
    v44 = v56;
    v45 = *v56;
    string = 0;
    v46 = WindowsCreateStringReference(L"TileActivatedInfo", 0x11u, &hstringHeader, &string);
    if ( v46 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v46, v47, v48);
      __debugbreak();
    }
    v35 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v45 + 80))(v44, string, v43, v50);
    v5 = v35;
    if ( v35 < 0 )
    {
      v36 = 130;
      goto LABEL_31;
    }
  }
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v53);
  WindowsDeleteString(v52);
  v52 = 0;
  WindowsDeleteString(v51);
  v51 = 0;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v56);
  return 0;
}

```

## disassembly

```asm
0x18008e400  mov     [rsp-8+arg_10], rbx
0x18008e405  mov     [rsp-8+arg_18], rsi
0x18008e40a  push    rbp
0x18008e40b  push    rdi
0x18008e40c  push    r14
0x18008e40e  lea     rbp, [rsp-47h]
0x18008e413  sub     rsp, 0A0h
0x18008e41a  mov     rax, cs:__security_cookie
0x18008e421  xor     rax, rsp
0x18008e424  mov     [rbp+57h+var_20], rax
0x18008e428  mov     rsi, rcx
0x18008e42b  mov     rdi, rdx
0x18008e42e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x18008e435  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18008e43a  xor     r14d, r14d
0x18008e43d  mov     ebx, eax
0x18008e43f  test    eax, eax
0x18008e441  jns     short loc_18008E461
0x18008e443  mov     rcx, [rbp+5Fh]; this
0x18008e447  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e44e  mov     r9d, eax; char *
0x18008e451  lea     edx, [r14+64h]; void *
0x18008e455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e45a  mov     eax, ebx
0x18008e45c  jmp     loc_18008E828
0x18008e461  mov     rax, [rdi]
0x18008e464  lea     rcx, [rbp+57h+var_50]
0x18008e468  mov     [rbp+57h+var_50], r14
0x18008e46c  mov     [rbp+57h+var_48], r14
0x18008e470  mov     rbx, [rax]
0x18008e473  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e478  lea     r8, [rbp+57h+var_50]
0x18008e47c  mov     rcx, rdi
0x18008e47f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18008e486  mov     rax, rbx
0x18008e489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e48e  mov     ebx, eax
0x18008e490  test    eax, eax
0x18008e492  jns     short loc_18008E49B
0x18008e494  mov     edx, 69h ; 'i'
0x18008e499  jmp     short loc_18008E4ED
0x18008e49b  lea     r9, [rbp+57h+string]; string
0x18008e49f  mov     [rbp+57h+string], r14
0x18008e4a3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008e4a7  mov     edx, 20h ; ' '; length
0x18008e4ac  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18008e4b3  call    cs:__imp_WindowsCreateStringReference
0x18008e4b9  test    eax, eax
0x18008e4bb  js      loc_18008E854
0x18008e4c1  mov     rbx, [rbp+57h+string]
0x18008e4c5  lea     rcx, [rbp+57h+var_48]
0x18008e4c9  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e4ce  lea     r8, [rbp+57h+var_48]
0x18008e4d2  mov     rcx, rbx
0x18008e4d5  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18008e4dc  call    cs:__imp_RoGetActivationFactory
0x18008e4e2  mov     ebx, eax
0x18008e4e4  test    eax, eax
0x18008e4e6  jns     short loc_18008E505
0x18008e4e8  mov     edx, 6Ah ; 'j'; void *
0x18008e4ed  mov     rcx, [rbp+5Fh]; this
0x18008e4f1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e4f8  mov     r9d, eax; char *
0x18008e4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e500  jmp     loc_18008E7C6
0x18008e505  lea     rdi, [rsi-10h]
0x18008e509  mov     [rbp+57h+var_78], r14
0x18008e50d  mov     rax, [rdi]
0x18008e510  xor     ecx, ecx; string
0x18008e512  mov     rbx, [rax+30h]
0x18008e516  call    cs:__imp_WindowsDeleteString
0x18008e51c  lea     rdx, [rbp+57h+var_78]
0x18008e520  mov     [rbp+57h+var_78], r14
0x18008e524  mov     rcx, rdi
0x18008e527  mov     rax, rbx
0x18008e52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e52f  mov     ebx, eax
0x18008e531  test    eax, eax
0x18008e533  jns     short loc_18008E552
0x18008e535  mov     rcx, [rbp+5Fh]; this
0x18008e539  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e540  mov     r9d, eax; char *
0x18008e543  mov     edx, 6Eh ; 'n'; void *
0x18008e548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e54d  jmp     loc_18008E7B8
0x18008e552  mov     rax, [rdi]
0x18008e555  xor     ecx, ecx; string
0x18008e557  mov     [rbp+57h+var_70], r14
0x18008e55b  mov     rbx, [rax+38h]
0x18008e55f  call    cs:__imp_WindowsDeleteString
0x18008e565  lea     rdx, [rbp+57h+var_70]
0x18008e569  mov     [rbp+57h+var_70], r14
0x18008e56d  mov     rcx, rdi
0x18008e570  mov     rax, rbx
0x18008e573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e578  mov     ebx, eax
0x18008e57a  test    eax, eax
0x18008e57c  jns     short loc_18008E59B
0x18008e57e  mov     rcx, [rbp+5Fh]; this
0x18008e582  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e589  mov     r9d, eax; char *
0x18008e58c  mov     edx, 71h ; 'q'; void *
0x18008e591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e596  jmp     loc_18008E7AA
0x18008e59b  mov     rax, [rsi-8]
0x18008e59f  lea     rcx, [rbp+57h+var_68]
0x18008e5a3  mov     [rbp+57h+var_68], r14
0x18008e5a7  mov     rbx, [rax+30h]
0x18008e5ab  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e5b0  lea     rdx, [rbp+57h+var_68]
0x18008e5b4  mov     rax, rbx
0x18008e5b7  lea     rcx, [rsi-8]
0x18008e5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5c0  mov     ebx, eax
0x18008e5c2  test    eax, eax
0x18008e5c4  jns     short loc_18008E5E3
0x18008e5c6  mov     rcx, [rbp+5Fh]; this
0x18008e5ca  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e5d1  mov     r9d, eax; char *
0x18008e5d4  mov     edx, 74h ; 't'; void *
0x18008e5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e5de  jmp     loc_18008E7A1
0x18008e5e3  mov     rdi, [rbp+57h+var_48]
0x18008e5e7  lea     rcx, [rbp+57h+var_60]
0x18008e5eb  mov     [rbp+57h+var_60], r14
0x18008e5ef  mov     rax, [rdi]
0x18008e5f2  mov     rbx, [rax+90h]
0x18008e5f9  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e5fe  mov     rdx, [rbp+57h+var_78]
0x18008e602  lea     r8, [rbp+57h+var_60]
0x18008e606  mov     rcx, rdi
0x18008e609  mov     rax, rbx
0x18008e60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e611  mov     ebx, eax
0x18008e613  test    eax, eax
0x18008e615  jns     short loc_18008E634
0x18008e617  mov     edx, 78h ; 'x'; void *
0x18008e61c  mov     rcx, [rbp+5Fh]; this
0x18008e620  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e627  mov     r9d, eax; char *
0x18008e62a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e62f  jmp     loc_18008E798
0x18008e634  mov     rbx, [rbp+57h+var_50]
0x18008e638  lea     r9, [rbp+57h+string]; string
0x18008e63c  mov     rsi, [rbp+57h+var_60]
0x18008e640  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008e644  mov     [rbp+57h+var_80], r14b
0x18008e648  lea     rcx, aArguments; "Arguments"
0x18008e64f  mov     edx, 9; length
0x18008e654  mov     rdi, [rbx]
0x18008e657  mov     [rbp+57h+string], r14
0x18008e65b  call    cs:__imp_WindowsCreateStringReference
0x18008e661  test    eax, eax
0x18008e663  js      loc_18008E85C
0x18008e669  mov     rdx, [rbp+57h+string]
0x18008e66d  lea     r9, [rbp+57h+var_80]
0x18008e671  mov     rax, [rdi+50h]
0x18008e675  mov     r8, rsi
0x18008e678  mov     rcx, rbx
0x18008e67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e680  mov     ebx, eax
0x18008e682  test    eax, eax
0x18008e684  jns     short loc_18008E68D
0x18008e686  mov     edx, 7Ah ; 'z'
0x18008e68b  jmp     short loc_18008E61C
0x18008e68d  mov     rdi, [rbp+57h+var_48]
0x18008e691  lea     rcx, [rbp+57h+var_58]
0x18008e695  mov     [rbp+57h+var_58], r14
0x18008e699  mov     rax, [rdi]
0x18008e69c  mov     rbx, [rax+90h]
0x18008e6a3  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e6a8  mov     rdx, [rbp+57h+var_70]
0x18008e6ac  lea     r8, [rbp+57h+var_58]
0x18008e6b0  mov     rcx, rdi
0x18008e6b3  mov     rax, rbx
0x18008e6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6bb  mov     ebx, eax
0x18008e6bd  test    eax, eax
0x18008e6bf  jns     short loc_18008E6CB
0x18008e6c1  mov     edx, 7Dh ; '}'
0x18008e6c6  jmp     loc_18008E77C
0x18008e6cb  mov     rbx, [rbp+57h+var_50]
0x18008e6cf  lea     r9, [rbp+57h+string]; string
0x18008e6d3  mov     rsi, [rbp+57h+var_58]
0x18008e6d7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008e6db  mov     edx, 6; length
0x18008e6e0  lea     rcx, aTileid; "TileId"
0x18008e6e7  mov     rdi, [rbx]
0x18008e6ea  mov     [rbp+57h+string], r14
0x18008e6ee  call    cs:__imp_WindowsCreateStringReference
0x18008e6f4  test    eax, eax
0x18008e6f6  js      loc_18008E864
0x18008e6fc  mov     rdx, [rbp+57h+string]
0x18008e700  lea     r9, [rbp+57h+var_80]
0x18008e704  mov     rax, [rdi+50h]
0x18008e708  mov     r8, rsi
0x18008e70b  mov     rcx, rbx
0x18008e70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e713  mov     ebx, eax
0x18008e715  test    eax, eax
0x18008e717  jns     short loc_18008E720
0x18008e719  mov     edx, 7Eh ; '~'
0x18008e71e  jmp     short loc_18008E77C
0x18008e720  mov     rbx, [rbp+57h+var_68]
0x18008e724  test    rbx, rbx
0x18008e727  jz      loc_18008E7DD
0x18008e72d  mov     rdi, [rbp+57h+var_50]
0x18008e731  lea     r9, [rbp+57h+string]; string
0x18008e735  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008e739  mov     edx, 11h; length
0x18008e73e  lea     rcx, aTileactivatedi; "TileActivatedInfo"
0x18008e745  mov     rsi, [rdi]
0x18008e748  mov     [rbp+57h+string], r14
0x18008e74c  call    cs:__imp_WindowsCreateStringReference
0x18008e752  test    eax, eax
0x18008e754  js      loc_18008E84C
0x18008e75a  mov     rdx, [rbp+57h+string]
0x18008e75e  lea     r9, [rbp+57h+var_80]
0x18008e762  mov     rax, [rsi+50h]
0x18008e766  mov     r8, rbx
0x18008e769  mov     rcx, rdi
0x18008e76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e771  mov     ebx, eax
0x18008e773  test    eax, eax
0x18008e775  jns     short loc_18008E7DD
0x18008e777  mov     edx, 82h; void *
0x18008e77c  mov     rcx, [rbp+5Fh]; this
0x18008e780  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18008e787  mov     r9d, eax; char *
0x18008e78a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e78f  lea     rcx, [rbp+57h+var_58]
0x18008e793  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e798  lea     rcx, [rbp+57h+var_60]
0x18008e79c  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7a1  lea     rcx, [rbp+57h+var_68]
0x18008e7a5  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7aa  mov     rcx, [rbp+57h+var_70]; string
0x18008e7ae  call    cs:__imp_WindowsDeleteString
0x18008e7b4  mov     [rbp+57h+var_70], r14
0x18008e7b8  mov     rcx, [rbp+57h+var_78]; string
0x18008e7bc  call    cs:__imp_WindowsDeleteString
0x18008e7c2  mov     [rbp+57h+var_78], r14
0x18008e7c6  lea     rcx, [rbp+57h+var_48]
0x18008e7ca  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7cf  lea     rcx, [rbp+57h+var_50]
0x18008e7d3  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7d8  jmp     loc_18008E45A
0x18008e7dd  lea     rcx, [rbp+57h+var_58]
0x18008e7e1  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7e6  lea     rcx, [rbp+57h+var_60]
0x18008e7ea  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7ef  lea     rcx, [rbp+57h+var_68]
0x18008e7f3  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e7f8  mov     rcx, [rbp+57h+var_70]; string
0x18008e7fc  call    cs:__imp_WindowsDeleteString
0x18008e802  mov     rcx, [rbp+57h+var_78]; string
0x18008e806  mov     [rbp+57h+var_70], r14
0x18008e80a  call    cs:__imp_WindowsDeleteString
0x18008e810  lea     rcx, [rbp+57h+var_48]
0x18008e814  mov     [rbp+57h+var_78], r14
0x18008e818  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e81d  lea     rcx, [rbp+57h+var_50]
0x18008e821  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008e826  xor     eax, eax
0x18008e828  mov     rcx, [rbp+57h+var_20]
0x18008e82c  xor     rcx, rsp; StackCookie
0x18008e82f  call    __security_check_cookie
0x18008e834  lea     r11, [rsp+0B0h+var_10]
0x18008e83c  mov     rbx, [r11+30h]
0x18008e840  mov     rsi, [r11+38h]
0x18008e844  mov     rsp, r11
0x18008e847  pop     r14
0x18008e849  pop     rdi
0x18008e84a  pop     rbp
0x18008e84b  retn
0x18008e84c  mov     ecx, eax; this
0x18008e84e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008e853  int     3; Trap to Debugger
0x18008e854  mov     ecx, eax; this
0x18008e856  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008e85b  int     3; Trap to Debugger
0x18008e85c  mov     ecx, eax; this
0x18008e85e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008e863  int     3; Trap to Debugger
0x18008e864  mov     ecx, eax; this
0x18008e866  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

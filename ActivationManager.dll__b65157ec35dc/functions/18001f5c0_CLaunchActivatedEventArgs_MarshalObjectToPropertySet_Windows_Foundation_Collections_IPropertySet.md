# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18001f5c0`
- end: `0x18001fa0c`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001f5c0`
- `0x180022904`
- `0x180031540`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f689`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f72e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f96e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f72e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f96e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f9ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f673`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f673`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f6ab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f6ab`

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
  HSTRING v12; // rbx
  __int64 (__fastcall *v13)(char *, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(char *, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rax
  __int64 (__fastcall *v19)(char *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  _QWORD *v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 (__fastcall *v28)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  _QWORD *v33; // rsi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 (__fastcall *v36)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  __int64 v37; // rbx
  _QWORD *v38; // rsi
  __int64 v39; // rax
  __int64 (__fastcall *v40)(_QWORD *, HSTRING, __int64, _BYTE *); // rdi
  int v41; // [rsp+20h] [rbp-39h]
  _BYTE v42[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v43; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v44; // [rsp+40h] [rbp-19h] BYREF
  __int64 v45; // [rsp+48h] [rbp-11h] BYREF
  __int64 v46; // [rsp+50h] [rbp-9h] BYREF
  __int64 v47; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v48; // [rsp+60h] [rbp+7h] BYREF
  __int64 v49; // [rsp+68h] [rbp+Fh] BYREF
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
      v41);
    return v5;
  }
  v7 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v48 = 0;
  v49 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
  ActivationFactory = v8(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v48);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 105;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v41);
LABEL_34:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    return v5;
  }
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v12 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v49);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 106;
    goto LABEL_10;
  }
  v43 = 0;
  v13 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
  WindowsDeleteString(0);
  v43 = 0;
  v14 = v13((char *)this - 16, &v43);
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v14,
      v41);
LABEL_33:
    WindowsDeleteString(v43);
    v43 = 0;
    goto LABEL_34;
  }
  v15 = *((_QWORD *)this - 2);
  v44 = 0;
  v16 = *(__int64 (__fastcall **)(char *, HSTRING *))(v15 + 56);
  WindowsDeleteString(0);
  v44 = 0;
  v17 = v16((char *)this - 16, &v44);
  v5 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v17,
      v41);
LABEL_32:
    WindowsDeleteString(v44);
    v44 = 0;
    goto LABEL_33;
  }
  v18 = *((_QWORD *)this - 1);
  v45 = 0;
  v19 = *(__int64 (__fastcall **)(char *, __int64 *))(v18 + 48);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  v20 = v19((char *)this - 8, &v45);
  v5 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v20,
      v41);
LABEL_31:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    goto LABEL_32;
  }
  v21 = v49;
  v46 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v49 + 144LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  v23 = v22(v21, v43, &v46);
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = 120;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v23,
      v41);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    goto LABEL_31;
  }
  v25 = v48;
  v26 = v46;
  v42[0] = 0;
  v27 = *v48;
  string = 0;
  v28 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v27 + 80);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
  v23 = v28(v25, string, v26, v42);
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = 122;
    goto LABEL_19;
  }
  v29 = v49;
  v47 = 0;
  v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v49 + 144LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  v31 = v30(v29, v44, &v47);
  v5 = v31;
  if ( v31 < 0 )
  {
    v32 = 125;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v31,
      v41);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    goto LABEL_30;
  }
  v33 = v48;
  v34 = v47;
  v35 = *v48;
  string = 0;
  v36 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v35 + 80);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileId", 7u, 6u);
  v31 = v36(v33, string, v34, v42);
  v5 = v31;
  if ( v31 < 0 )
  {
    v32 = 126;
    goto LABEL_29;
  }
  v37 = v45;
  if ( v45 )
  {
    v38 = v48;
    v39 = *v48;
    string = 0;
    v40 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v39 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileActivatedInfo", 0x12u, 0x11u);
    v31 = v40(v38, string, v37, v42);
    v5 = v31;
    if ( v31 < 0 )
    {
      v32 = 130;
      goto LABEL_29;
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v43);
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
  return 0;
}

```

## disassembly

```asm
0x18001f5c0  mov     [rsp-8+arg_10], rbx
0x18001f5c5  mov     [rsp-8+arg_18], rsi
0x18001f5ca  push    rbp
0x18001f5cb  push    rdi
0x18001f5cc  push    r14
0x18001f5ce  lea     rbp, [rsp-47h]
0x18001f5d3  sub     rsp, 0A0h
0x18001f5da  mov     rax, cs:__security_cookie
0x18001f5e1  xor     rax, rsp
0x18001f5e4  mov     [rbp+57h+var_20], rax
0x18001f5e8  mov     rsi, rcx
0x18001f5eb  mov     rdi, rdx
0x18001f5ee  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x18001f5f5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18001f5fa  xor     r14d, r14d
0x18001f5fd  mov     ebx, eax
0x18001f5ff  test    eax, eax
0x18001f601  jns     short loc_18001F621
0x18001f603  mov     rcx, [rbp+5Fh]; this
0x18001f607  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f60e  mov     r9d, eax; char *
0x18001f611  lea     edx, [r14+64h]; void *
0x18001f615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f61a  mov     eax, ebx
0x18001f61c  jmp     loc_18001F9E8
0x18001f621  mov     rax, [rdi]
0x18001f624  lea     rcx, [rbp+57h+var_50]
0x18001f628  mov     [rbp+57h+var_50], r14
0x18001f62c  mov     [rbp+57h+var_48], r14
0x18001f630  mov     rbx, [rax]
0x18001f633  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f638  lea     r8, [rbp+57h+var_50]
0x18001f63c  mov     rcx, rdi
0x18001f63f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001f646  mov     rax, rbx
0x18001f649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f64e  mov     ebx, eax
0x18001f650  test    eax, eax
0x18001f652  jns     short loc_18001F65B
0x18001f654  mov     edx, 69h ; 'i'
0x18001f659  jmp     short loc_18001F6BC
0x18001f65b  lea     r9, [rbp+57h+string]; string
0x18001f65f  mov     [rbp+57h+string], r14
0x18001f663  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001f667  mov     edx, 20h ; ' '; length
0x18001f66c  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001f673  call    cs:__imp_WindowsCreateStringReference
0x18001f679  test    eax, eax
0x18001f67b  jns     short loc_18001F690
0x18001f67d  xor     r9d, r9d; lpArguments
0x18001f680  xor     r8d, r8d; nNumberOfArguments
0x18001f683  mov     ecx, eax; dwExceptionCode
0x18001f685  lea     edx, [r9+1]; dwExceptionFlags
0x18001f689  call    cs:__imp_RaiseException
0x18001f68f  int     3; Trap to Debugger
0x18001f690  mov     rbx, [rbp+57h+string]
0x18001f694  lea     rcx, [rbp+57h+var_48]
0x18001f698  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f69d  lea     r8, [rbp+57h+var_48]
0x18001f6a1  mov     rcx, rbx
0x18001f6a4  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18001f6ab  call    cs:__imp_RoGetActivationFactory
0x18001f6b1  mov     ebx, eax
0x18001f6b3  test    eax, eax
0x18001f6b5  jns     short loc_18001F6D4
0x18001f6b7  mov     edx, 6Ah ; 'j'; void *
0x18001f6bc  mov     rcx, [rbp+5Fh]; this
0x18001f6c0  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f6c7  mov     r9d, eax; char *
0x18001f6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6cf  jmp     loc_18001F986
0x18001f6d4  lea     rdi, [rsi-10h]
0x18001f6d8  mov     [rbp+57h+var_78], r14
0x18001f6dc  mov     rax, [rdi]
0x18001f6df  xor     ecx, ecx; string
0x18001f6e1  mov     rbx, [rax+30h]
0x18001f6e5  call    cs:__imp_WindowsDeleteString
0x18001f6eb  lea     rdx, [rbp+57h+var_78]
0x18001f6ef  mov     [rbp+57h+var_78], r14
0x18001f6f3  mov     rcx, rdi
0x18001f6f6  mov     rax, rbx
0x18001f6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6fe  mov     ebx, eax
0x18001f700  test    eax, eax
0x18001f702  jns     short loc_18001F721
0x18001f704  mov     rcx, [rbp+5Fh]; this
0x18001f708  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f70f  mov     r9d, eax; char *
0x18001f712  mov     edx, 6Eh ; 'n'; void *
0x18001f717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f71c  jmp     loc_18001F978
0x18001f721  mov     rax, [rdi]
0x18001f724  xor     ecx, ecx; string
0x18001f726  mov     [rbp+57h+var_70], r14
0x18001f72a  mov     rbx, [rax+38h]
0x18001f72e  call    cs:__imp_WindowsDeleteString
0x18001f734  lea     rdx, [rbp+57h+var_70]
0x18001f738  mov     [rbp+57h+var_70], r14
0x18001f73c  mov     rcx, rdi
0x18001f73f  mov     rax, rbx
0x18001f742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f747  mov     ebx, eax
0x18001f749  test    eax, eax
0x18001f74b  jns     short loc_18001F76A
0x18001f74d  mov     rcx, [rbp+5Fh]; this
0x18001f751  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f758  mov     r9d, eax; char *
0x18001f75b  mov     edx, 71h ; 'q'; void *
0x18001f760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f765  jmp     loc_18001F96A
0x18001f76a  mov     rax, [rsi-8]
0x18001f76e  lea     rcx, [rbp+57h+var_68]
0x18001f772  mov     [rbp+57h+var_68], r14
0x18001f776  mov     rbx, [rax+30h]
0x18001f77a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f77f  lea     rdx, [rbp+57h+var_68]
0x18001f783  mov     rax, rbx
0x18001f786  lea     rcx, [rsi-8]
0x18001f78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f78f  mov     ebx, eax
0x18001f791  test    eax, eax
0x18001f793  jns     short loc_18001F7B2
0x18001f795  mov     rcx, [rbp+5Fh]; this
0x18001f799  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f7a0  mov     r9d, eax; char *
0x18001f7a3  mov     edx, 74h ; 't'; void *
0x18001f7a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7ad  jmp     loc_18001F961
0x18001f7b2  mov     rdi, [rbp+57h+var_48]
0x18001f7b6  lea     rcx, [rbp+57h+var_60]
0x18001f7ba  mov     [rbp+57h+var_60], r14
0x18001f7be  mov     rax, [rdi]
0x18001f7c1  mov     rbx, [rax+90h]
0x18001f7c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f7cd  mov     rdx, [rbp+57h+var_78]
0x18001f7d1  lea     r8, [rbp+57h+var_60]
0x18001f7d5  mov     rcx, rdi
0x18001f7d8  mov     rax, rbx
0x18001f7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7e0  mov     ebx, eax
0x18001f7e2  test    eax, eax
0x18001f7e4  jns     short loc_18001F803
0x18001f7e6  mov     edx, 78h ; 'x'; void *
0x18001f7eb  mov     rcx, [rbp+5Fh]; this
0x18001f7ef  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f7f6  mov     r9d, eax; char *
0x18001f7f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7fe  jmp     loc_18001F958
0x18001f803  mov     rsi, [rbp+57h+var_50]
0x18001f807  lea     rdx, aArguments; "Arguments"
0x18001f80e  mov     rbx, [rbp+57h+var_60]
0x18001f812  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f816  mov     [rbp+57h+var_80], r14b
0x18001f81a  mov     r9d, 9; unsigned int
0x18001f820  mov     rax, [rsi]
0x18001f823  mov     [rbp+57h+string], r14
0x18001f827  lea     r8d, [r9+1]; unsigned int
0x18001f82b  mov     rdi, [rax+50h]
0x18001f82f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f834  mov     rdx, [rbp+57h+string]
0x18001f838  lea     r9, [rbp+57h+var_80]
0x18001f83c  mov     r8, rbx
0x18001f83f  mov     rcx, rsi
0x18001f842  mov     rax, rdi
0x18001f845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84a  mov     ebx, eax
0x18001f84c  test    eax, eax
0x18001f84e  jns     short loc_18001F857
0x18001f850  mov     edx, 7Ah ; 'z'
0x18001f855  jmp     short loc_18001F7EB
0x18001f857  mov     rdi, [rbp+57h+var_48]
0x18001f85b  lea     rcx, [rbp+57h+var_58]
0x18001f85f  mov     [rbp+57h+var_58], r14
0x18001f863  mov     rax, [rdi]
0x18001f866  mov     rbx, [rax+90h]
0x18001f86d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f872  mov     rdx, [rbp+57h+var_70]
0x18001f876  lea     r8, [rbp+57h+var_58]
0x18001f87a  mov     rcx, rdi
0x18001f87d  mov     rax, rbx
0x18001f880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f885  mov     ebx, eax
0x18001f887  test    eax, eax
0x18001f889  jns     short loc_18001F895
0x18001f88b  mov     edx, 7Dh ; '}'
0x18001f890  jmp     loc_18001F93C
0x18001f895  mov     rsi, [rbp+57h+var_50]
0x18001f899  lea     rdx, aTileid; "TileId"
0x18001f8a0  mov     rbx, [rbp+57h+var_58]
0x18001f8a4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f8a8  mov     r9d, 6; unsigned int
0x18001f8ae  mov     rax, [rsi]
0x18001f8b1  mov     [rbp+57h+string], r14
0x18001f8b5  lea     r8d, [r9+1]; unsigned int
0x18001f8b9  mov     rdi, [rax+50h]
0x18001f8bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f8c2  mov     rdx, [rbp+57h+string]
0x18001f8c6  lea     r9, [rbp+57h+var_80]
0x18001f8ca  mov     r8, rbx
0x18001f8cd  mov     rcx, rsi
0x18001f8d0  mov     rax, rdi
0x18001f8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8d8  mov     ebx, eax
0x18001f8da  test    eax, eax
0x18001f8dc  jns     short loc_18001F8E5
0x18001f8de  mov     edx, 7Eh ; '~'
0x18001f8e3  jmp     short loc_18001F93C
0x18001f8e5  mov     rbx, [rbp+57h+var_68]
0x18001f8e9  test    rbx, rbx
0x18001f8ec  jz      loc_18001F99D
0x18001f8f2  mov     rsi, [rbp+57h+var_50]
0x18001f8f6  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x18001f8fd  mov     r9d, 11h; unsigned int
0x18001f903  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f907  mov     rax, [rsi]
0x18001f90a  lea     r8d, [r9+1]; unsigned int
0x18001f90e  mov     [rbp+57h+string], r14
0x18001f912  mov     rdi, [rax+50h]
0x18001f916  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f91b  mov     rdx, [rbp+57h+string]
0x18001f91f  lea     r9, [rbp+57h+var_80]
0x18001f923  mov     r8, rbx
0x18001f926  mov     rcx, rsi
0x18001f929  mov     rax, rdi
0x18001f92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f931  mov     ebx, eax
0x18001f933  test    eax, eax
0x18001f935  jns     short loc_18001F99D
0x18001f937  mov     edx, 82h; void *
0x18001f93c  mov     rcx, [rbp+5Fh]; this
0x18001f940  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\lib\\activationevent"...
0x18001f947  mov     r9d, eax; char *
0x18001f94a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f94f  lea     rcx, [rbp+57h+var_58]
0x18001f953  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f958  lea     rcx, [rbp+57h+var_60]
0x18001f95c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f961  lea     rcx, [rbp+57h+var_68]
0x18001f965  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f96a  mov     rcx, [rbp+57h+var_70]; string
0x18001f96e  call    cs:__imp_WindowsDeleteString
0x18001f974  mov     [rbp+57h+var_70], r14
0x18001f978  mov     rcx, [rbp+57h+var_78]; string
0x18001f97c  call    cs:__imp_WindowsDeleteString
0x18001f982  mov     [rbp+57h+var_78], r14
0x18001f986  lea     rcx, [rbp+57h+var_48]
0x18001f98a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f98f  lea     rcx, [rbp+57h+var_50]
0x18001f993  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f998  jmp     loc_18001F61A
0x18001f99d  lea     rcx, [rbp+57h+var_58]
0x18001f9a1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9a6  lea     rcx, [rbp+57h+var_60]
0x18001f9aa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9af  lea     rcx, [rbp+57h+var_68]
0x18001f9b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9b8  mov     rcx, [rbp+57h+var_70]; string
0x18001f9bc  call    cs:__imp_WindowsDeleteString
0x18001f9c2  mov     rcx, [rbp+57h+var_78]; string
0x18001f9c6  mov     [rbp+57h+var_70], r14
0x18001f9ca  call    cs:__imp_WindowsDeleteString
0x18001f9d0  lea     rcx, [rbp+57h+var_48]
0x18001f9d4  mov     [rbp+57h+var_78], r14
0x18001f9d8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9dd  lea     rcx, [rbp+57h+var_50]
0x18001f9e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9e6  xor     eax, eax
0x18001f9e8  mov     rcx, [rbp+57h+var_20]
0x18001f9ec  xor     rcx, rsp; StackCookie
0x18001f9ef  call    __security_check_cookie
0x18001f9f4  lea     r11, [rsp+0B0h+var_10]
0x18001f9fc  mov     rbx, [r11+30h]
0x18001fa00  mov     rsi, [r11+38h]
0x18001fa04  mov     rsp, r11
0x18001fa07  pop     r14
0x18001fa09  pop     rdi
0x18001fa0a  pop     rbp
0x18001fa0b  retn
```

# CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800217f8`
- end: `0x180021cab`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CActivatedEventArgsWithViewIdBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022904`
- `0x180098130`
- `0x180098ee0`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x1800217f8`
- `0x180021cb4`
- `0x180031540`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800218bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021a30`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021b3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021bd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800218bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021a30`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021b3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800218a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021a1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021b24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800218a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021a1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021b24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021bc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800218dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800218dd`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **))
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rax
  __int64 (__fastcall *v8)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdx
  HRESULT v11; // eax
  HSTRING v12; // rbx
  __int64 (__fastcall *v13)(RTL_SRWLOCK *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, _OWORD *); // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  _QWORD *v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rdi
  HRESULT v24; // eax
  __int64 v25; // rbx
  _QWORD *v26; // rsi
  __int64 v27; // rax
  __int64 (__fastcall *v28)(_QWORD *, HSTRING, __int64, char *); // rdi
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  _QWORD *v33; // rbx
  __int64 v34; // rsi
  __int64 v35; // rdi
  HRESULT v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, __int64 *); // rbx
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // rdx
  _QWORD *v42; // rbx
  __int64 v43; // rsi
  __int64 v44; // rdi
  HRESULT v45; // eax
  int v46; // [rsp+20h] [rbp-49h]
  char v47[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v48; // [rsp+38h] [rbp-31h] BYREF
  __int64 v49; // [rsp+40h] [rbp-29h] BYREF
  __int64 v50; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v51; // [rsp+50h] [rbp-19h] BYREF
  __int64 v52; // [rsp+58h] [rbp-11h] BYREF
  __int64 v53; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v54; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v57; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = CActivatedEventArgsBase::MarshalObjectToPropertySet(this, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v4,
      v46);
    return v5;
  }
  v7 = *a2;
  v51 = 0;
  v52 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
  ActivationFactory = v8(
                        (struct Windows::Foundation::Collections::IPropertySet *)a2,
                        &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                        &v51);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 549;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v46);
LABEL_45:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
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
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  ActivationFactory = RoGetActivationFactory(v12, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v52);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 550;
    goto LABEL_10;
  }
  v54 = 0;
  ActivationFactory = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, unsigned int *))this[19].Ptr + 6))(this + 19, &v54);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 553;
    goto LABEL_10;
  }
  v48 = 0;
  v13 = (__int64 (__fastcall *)(RTL_SRWLOCK *, __int64 *))*((_QWORD *)this[20].Ptr + 6);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
  v14 = v13(this + 20, &v48);
  v5 = v14;
  if ( v14 < 0 )
  {
    v15 = 556;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v14,
      v46);
LABEL_44:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    goto LABEL_45;
  }
  Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, _OWORD *))this[21].Ptr;
  v57 = 0;
  v14 = Ptr[8](this + 21, &v57);
  v5 = v14;
  if ( v14 < 0 )
  {
    v15 = 559;
    goto LABEL_15;
  }
  v17 = v52;
  v49 = 0;
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 80LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  v19 = v18(v17, v54, &v49);
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 563;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v19,
      v46);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
    goto LABEL_44;
  }
  v21 = v51;
  v22 = v49;
  v47[0] = 0;
  v23 = *v51;
  string = 0;
  v24 = WindowsCreateStringReference(L"CurrentlyShownApplicationViewId", 0x1Fu, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    RaiseException(v24, 1u, 0, 0);
    __debugbreak();
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v23 + 80))(v21, string, v22, v47);
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 565;
    goto LABEL_20;
  }
  v25 = v48;
  if ( v48 )
  {
    v26 = v51;
    v27 = *v51;
    string = 0;
    v28 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v27 + 80);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ViewSwitcher", 0xDu, 0xCu);
    v19 = v28(v26, string, v25, v47);
    v5 = v19;
    if ( v19 < 0 )
    {
      v20 = 569;
      goto LABEL_20;
    }
  }
  v29 = v52;
  v50 = 0;
  v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 104LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
  v31 = v30(v29, v57, &v50);
  v5 = v31;
  if ( v31 < 0 )
  {
    v32 = 573;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v31,
      v46);
LABEL_42:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
    goto LABEL_43;
  }
  v33 = v51;
  v34 = v50;
  v35 = *v51;
  string = 0;
  v36 = WindowsCreateStringReference(L"MultiView:AamActivationId", 0x19u, &hstringHeader, &string);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
    __debugbreak();
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v35 + 80))(v33, string, v34, v47);
  v5 = v31;
  if ( v31 < 0 )
  {
    v32 = 574;
    goto LABEL_30;
  }
  v37 = v52;
  v53 = 0;
  v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
  LOBYTE(v39) = BYTE8(v57);
  v40 = v38(v37, v39, &v53);
  v5 = v40;
  if ( v40 < 0 )
  {
    v41 = 577;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v40,
      v46);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
    goto LABEL_42;
  }
  v42 = v51;
  v43 = v53;
  v44 = *v51;
  string = 0;
  v45 = WindowsCreateStringReference(L"IsApplicationMultiviewActivationPolicyEnabled", 0x2Du, &hstringHeader, &string);
  if ( v45 < 0 )
  {
    RaiseException(v45, 1u, 0, 0);
    __debugbreak();
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v44 + 80))(v42, string, v43, v47);
  v5 = v40;
  if ( v40 < 0 )
  {
    v41 = 578;
    goto LABEL_41;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
  return 0;
}

```

## disassembly

```asm
0x1800217f8  mov     [rsp-8+arg_10], rbx
0x1800217fd  mov     [rsp-8+arg_18], rsi
0x180021802  push    rbp
0x180021803  push    rdi
0x180021804  push    r14
0x180021806  lea     rbp, [rsp-47h]
0x18002180b  sub     rsp, 0B0h
0x180021812  mov     rax, cs:__security_cookie
0x180021819  xor     rax, rsp
0x18002181c  mov     [rbp+57h+var_20], rax
0x180021820  mov     rdi, rdx
0x180021823  mov     rsi, rcx
0x180021826  call    ?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18002182b  xor     r14d, r14d
0x18002182e  mov     ebx, eax
0x180021830  test    eax, eax
0x180021832  jns     short loc_180021853
0x180021834  mov     rcx, [rbp+5Fh]; this
0x180021838  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18002183f  mov     r9d, eax; char *
0x180021842  mov     edx, 220h; void *
0x180021847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002184c  mov     eax, ebx
0x18002184e  jmp     loc_180021C87
0x180021853  mov     rax, [rdi]
0x180021856  lea     rcx, [rbp+57h+var_70]
0x18002185a  mov     [rbp+57h+var_70], r14
0x18002185e  mov     [rbp+57h+var_68], r14
0x180021862  mov     rbx, [rax]
0x180021865  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002186a  lea     r8, [rbp+57h+var_70]
0x18002186e  mov     rcx, rdi
0x180021871  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180021878  mov     rax, rbx
0x18002187b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021880  mov     ebx, eax
0x180021882  test    eax, eax
0x180021884  jns     short loc_18002188D
0x180021886  mov     edx, 225h
0x18002188b  jmp     short loc_1800218EE
0x18002188d  lea     r9, [rbp+57h+string]; string
0x180021891  mov     [rbp+57h+string], r14
0x180021895  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021899  mov     edx, 20h ; ' '; length
0x18002189e  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800218a5  call    cs:__imp_WindowsCreateStringReference
0x1800218ab  test    eax, eax
0x1800218ad  jns     short loc_1800218C2
0x1800218af  xor     r9d, r9d; lpArguments
0x1800218b2  xor     r8d, r8d; nNumberOfArguments
0x1800218b5  mov     ecx, eax; dwExceptionCode
0x1800218b7  lea     edx, [r9+1]; dwExceptionFlags
0x1800218bb  call    cs:__imp_RaiseException
0x1800218c1  int     3; Trap to Debugger
0x1800218c2  mov     rbx, [rbp+57h+string]
0x1800218c6  lea     rcx, [rbp+57h+var_68]
0x1800218ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800218cf  lea     r8, [rbp+57h+var_68]
0x1800218d3  mov     rcx, rbx
0x1800218d6  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800218dd  call    cs:__imp_RoGetActivationFactory
0x1800218e3  mov     ebx, eax
0x1800218e5  test    eax, eax
0x1800218e7  jns     short loc_180021906
0x1800218e9  mov     edx, 226h; void *
0x1800218ee  mov     rcx, [rbp+5Fh]; this
0x1800218f2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800218f9  mov     r9d, eax; char *
0x1800218fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021901  jmp     loc_180021C38
0x180021906  lea     rcx, [rsi+98h]
0x18002190d  mov     [rbp+57h+var_58], r14d
0x180021911  mov     rax, [rcx]
0x180021914  lea     rdx, [rbp+57h+var_58]
0x180021918  mov     rax, [rax+30h]
0x18002191c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021921  mov     ebx, eax
0x180021923  test    eax, eax
0x180021925  jns     short loc_18002192E
0x180021927  mov     edx, 229h
0x18002192c  jmp     short loc_1800218EE
0x18002192e  lea     rdi, [rsi+0A0h]
0x180021935  mov     [rbp+57h+var_88], r14
0x180021939  mov     rax, [rdi]
0x18002193c  lea     rcx, [rbp+57h+var_88]
0x180021940  mov     rbx, [rax+30h]
0x180021944  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021949  lea     rdx, [rbp+57h+var_88]
0x18002194d  mov     rcx, rdi
0x180021950  mov     rax, rbx
0x180021953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021958  mov     ebx, eax
0x18002195a  test    eax, eax
0x18002195c  jns     short loc_18002197B
0x18002195e  mov     edx, 22Ch; void *
0x180021963  mov     rcx, [rbp+5Fh]; this
0x180021967  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18002196e  mov     r9d, eax; char *
0x180021971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021976  jmp     loc_180021C2F
0x18002197b  lea     rcx, [rsi+0A8h]
0x180021982  xorps   xmm0, xmm0
0x180021985  mov     rax, [rcx]
0x180021988  lea     rdx, [rbp+57h+var_30]
0x18002198c  movups  [rbp+57h+var_30], xmm0
0x180021990  mov     rax, [rax+40h]
0x180021994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021999  mov     ebx, eax
0x18002199b  test    eax, eax
0x18002199d  jns     short loc_1800219A6
0x18002199f  mov     edx, 22Fh
0x1800219a4  jmp     short loc_180021963
0x1800219a6  mov     rdi, [rbp+57h+var_68]
0x1800219aa  lea     rcx, [rbp+57h+var_80]
0x1800219ae  mov     [rbp+57h+var_80], r14
0x1800219b2  mov     rax, [rdi]
0x1800219b5  mov     rbx, [rax+50h]
0x1800219b9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800219be  mov     edx, [rbp+57h+var_58]
0x1800219c1  lea     r8, [rbp+57h+var_80]
0x1800219c5  mov     rcx, rdi
0x1800219c8  mov     rax, rbx
0x1800219cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d0  mov     ebx, eax
0x1800219d2  test    eax, eax
0x1800219d4  jns     short loc_1800219F3
0x1800219d6  mov     edx, 233h; void *
0x1800219db  mov     rcx, [rbp+5Fh]; this
0x1800219df  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800219e6  mov     r9d, eax; char *
0x1800219e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219ee  jmp     loc_180021C26
0x1800219f3  mov     rbx, [rbp+57h+var_70]
0x1800219f7  lea     r9, [rbp+57h+string]; string
0x1800219fb  mov     rsi, [rbp+57h+var_80]
0x1800219ff  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021a03  mov     [rbp+57h+var_90], r14b
0x180021a07  lea     rcx, aCurrentlyshown; "CurrentlyShownApplicationViewId"
0x180021a0e  mov     edx, 1Fh; length
0x180021a13  mov     rdi, [rbx]
0x180021a16  mov     [rbp+57h+string], r14
0x180021a1a  call    cs:__imp_WindowsCreateStringReference
0x180021a20  test    eax, eax
0x180021a22  jns     short loc_180021A37
0x180021a24  xor     r9d, r9d; lpArguments
0x180021a27  xor     r8d, r8d; nNumberOfArguments
0x180021a2a  mov     ecx, eax; dwExceptionCode
0x180021a2c  lea     edx, [r9+1]; dwExceptionFlags
0x180021a30  call    cs:__imp_RaiseException
0x180021a36  int     3; Trap to Debugger
0x180021a37  mov     rdx, [rbp+57h+string]
0x180021a3b  lea     r9, [rbp+57h+var_90]
0x180021a3f  mov     rax, [rdi+50h]
0x180021a43  mov     r8, rsi
0x180021a46  mov     rcx, rbx
0x180021a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a4e  mov     ebx, eax
0x180021a50  test    eax, eax
0x180021a52  jns     short loc_180021A5B
0x180021a54  mov     edx, 235h
0x180021a59  jmp     short loc_1800219DB
0x180021a5b  mov     rbx, [rbp+57h+var_88]
0x180021a5f  test    rbx, rbx
0x180021a62  jz      short loc_180021AB3
0x180021a64  mov     rsi, [rbp+57h+var_70]
0x180021a68  lea     rdx, aViewswitcher; "ViewSwitcher"
0x180021a6f  mov     r9d, 0Ch; unsigned int
0x180021a75  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180021a79  mov     rax, [rsi]
0x180021a7c  lea     r8d, [r9+1]; unsigned int
0x180021a80  mov     [rbp+57h+string], r14
0x180021a84  mov     rdi, [rax+50h]
0x180021a88  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180021a8d  mov     rdx, [rbp+57h+string]
0x180021a91  lea     r9, [rbp+57h+var_90]
0x180021a95  mov     r8, rbx
0x180021a98  mov     rcx, rsi
0x180021a9b  mov     rax, rdi
0x180021a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa3  mov     ebx, eax
0x180021aa5  test    eax, eax
0x180021aa7  jns     short loc_180021AB3
0x180021aa9  mov     edx, 239h
0x180021aae  jmp     loc_1800219DB
0x180021ab3  mov     rdi, [rbp+57h+var_68]
0x180021ab7  lea     rcx, [rbp+57h+var_78]
0x180021abb  mov     [rbp+57h+var_78], r14
0x180021abf  mov     rax, [rdi]
0x180021ac2  mov     rbx, [rax+68h]
0x180021ac6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021acb  mov     rdx, qword ptr [rbp+57h+var_30]
0x180021acf  lea     r8, [rbp+57h+var_78]
0x180021ad3  mov     rcx, rdi
0x180021ad6  mov     rax, rbx
0x180021ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ade  mov     ebx, eax
0x180021ae0  test    eax, eax
0x180021ae2  jns     short loc_180021B01
0x180021ae4  mov     edx, 23Dh; void *
0x180021ae9  mov     rcx, [rbp+5Fh]; this
0x180021aed  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021af4  mov     r9d, eax; char *
0x180021af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021afc  jmp     loc_180021C1D
0x180021b01  mov     rbx, [rbp+57h+var_70]
0x180021b05  lea     r9, [rbp+57h+string]; string
0x180021b09  mov     rsi, [rbp+57h+var_78]
0x180021b0d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021b11  mov     edx, 19h; length
0x180021b16  lea     rcx, aMultiviewAamac; "MultiView:AamActivationId"
0x180021b1d  mov     rdi, [rbx]
0x180021b20  mov     [rbp+57h+string], r14
0x180021b24  call    cs:__imp_WindowsCreateStringReference
0x180021b2a  test    eax, eax
0x180021b2c  jns     short loc_180021B41
0x180021b2e  xor     r9d, r9d; lpArguments
0x180021b31  xor     r8d, r8d; nNumberOfArguments
0x180021b34  mov     ecx, eax; dwExceptionCode
0x180021b36  lea     edx, [r9+1]; dwExceptionFlags
0x180021b3a  call    cs:__imp_RaiseException
0x180021b40  int     3; Trap to Debugger
0x180021b41  mov     rdx, [rbp+57h+string]
0x180021b45  lea     r9, [rbp+57h+var_90]
0x180021b49  mov     rax, [rdi+50h]
0x180021b4d  mov     r8, rsi
0x180021b50  mov     rcx, rbx
0x180021b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b58  mov     ebx, eax
0x180021b5a  test    eax, eax
0x180021b5c  jns     short loc_180021B65
0x180021b5e  mov     edx, 23Eh
0x180021b63  jmp     short loc_180021AE9
0x180021b65  mov     rdi, [rbp+57h+var_68]
0x180021b69  lea     rcx, [rbp+57h+var_60]
0x180021b6d  mov     [rbp+57h+var_60], r14
0x180021b71  mov     rax, [rdi]
0x180021b74  mov     rbx, [rax+88h]
0x180021b7b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021b80  mov     dl, byte ptr [rbp+57h+var_30+8]
0x180021b83  lea     r8, [rbp+57h+var_60]
0x180021b87  mov     rcx, rdi
0x180021b8a  mov     rax, rbx
0x180021b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b92  mov     ebx, eax
0x180021b94  test    eax, eax
0x180021b96  jns     short loc_180021B9F
0x180021b98  mov     edx, 241h
0x180021b9d  jmp     short loc_180021C01
0x180021b9f  mov     rbx, [rbp+57h+var_70]
0x180021ba3  lea     r9, [rbp+57h+string]; string
0x180021ba7  mov     rsi, [rbp+57h+var_60]
0x180021bab  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180021baf  mov     edx, 2Dh ; '-'; length
0x180021bb4  lea     rcx, aIsapplicationm; "IsApplicationMultiviewActivationPolicyE"...
0x180021bbb  mov     rdi, [rbx]
0x180021bbe  mov     [rbp+57h+string], r14
0x180021bc2  call    cs:__imp_WindowsCreateStringReference
0x180021bc8  test    eax, eax
0x180021bca  jns     short loc_180021BDF
0x180021bcc  xor     r9d, r9d; lpArguments
0x180021bcf  xor     r8d, r8d; nNumberOfArguments
0x180021bd2  mov     ecx, eax; dwExceptionCode
0x180021bd4  lea     edx, [r9+1]; dwExceptionFlags
0x180021bd8  call    cs:__imp_RaiseException
0x180021bde  int     3; Trap to Debugger
0x180021bdf  mov     rdx, [rbp+57h+string]
0x180021be3  lea     r9, [rbp+57h+var_90]
0x180021be7  mov     rax, [rdi+50h]
0x180021beb  mov     r8, rsi
0x180021bee  mov     rcx, rbx
0x180021bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bf6  mov     ebx, eax
0x180021bf8  test    eax, eax
0x180021bfa  jns     short loc_180021C4F
0x180021bfc  mov     edx, 242h; void *
0x180021c01  mov     rcx, [rbp+5Fh]; this
0x180021c05  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180021c0c  mov     r9d, eax; char *
0x180021c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021c14  lea     rcx, [rbp+57h+var_60]
0x180021c18  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c1d  lea     rcx, [rbp+57h+var_78]
0x180021c21  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c26  lea     rcx, [rbp+57h+var_80]
0x180021c2a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c2f  lea     rcx, [rbp+57h+var_88]
0x180021c33  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c38  lea     rcx, [rbp+57h+var_68]
0x180021c3c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c41  lea     rcx, [rbp+57h+var_70]
0x180021c45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c4a  jmp     loc_18002184C
0x180021c4f  lea     rcx, [rbp+57h+var_60]
0x180021c53  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c58  lea     rcx, [rbp+57h+var_78]
0x180021c5c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c61  lea     rcx, [rbp+57h+var_80]
0x180021c65  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180021c6a  lea     rcx, [rbp+57h+var_88]
0x180021c6e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
  ... truncated ...
```

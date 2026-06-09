# CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18008d4a0`
- end: `0x18008d944`
- name: `?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1188`
- prototype: `__int64 __fastcall(CActivatedEventArgsWithViewIdBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008d258`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x18001e61c`
- `0x1800272d4`
- `0x18008c5b8`
- `0x18008d4a0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d54d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d70d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d54d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d6b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d70d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008d842`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008d576`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008d576`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
        RTL_SRWLOCK *this,
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
  __int64 (__fastcall *v15)(RTL_SRWLOCK *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, _OWORD *); // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rdi
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // rbx
  _QWORD *v30; // rdi
  __int64 v31; // rsi
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64 *); // rbx
  int v37; // eax
  __int64 v38; // rdx
  _QWORD *v39; // rbx
  __int64 v40; // rsi
  __int64 v41; // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, __int64 *); // rbx
  __int64 v47; // rdx
  int v48; // eax
  __int64 v49; // rdx
  _QWORD *v50; // rbx
  __int64 v51; // rsi
  __int64 v52; // rdi
  HRESULT v53; // eax
  int v54; // edx
  unsigned int v55; // r8d
  int v56; // [rsp+20h] [rbp-49h]
  char v57[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v58; // [rsp+38h] [rbp-31h] BYREF
  __int64 v59; // [rsp+40h] [rbp-29h] BYREF
  __int64 v60; // [rsp+48h] [rbp-21h] BYREF
  _QWORD *v61; // [rsp+50h] [rbp-19h] BYREF
  __int64 v62; // [rsp+58h] [rbp-11h] BYREF
  __int64 v63; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v67; // [rsp+90h] [rbp+27h] BYREF
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
      v56);
    return v5;
  }
  v7 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v61 = 0;
  v62 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v61);
  ActivationFactory = v8(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v61);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 549;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v56);
LABEL_42:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v61);
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
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v62);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 550;
    goto LABEL_9;
  }
  v64 = 0;
  ActivationFactory = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, unsigned int *))this[19].Ptr + 6))(this + 19, &v64);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 553;
    goto LABEL_9;
  }
  v58 = 0;
  v15 = (__int64 (__fastcall *)(RTL_SRWLOCK *, __int64 *))*((_QWORD *)this[20].Ptr + 6);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v58);
  v16 = v15(this + 20, &v58);
  v5 = v16;
  if ( v16 < 0 )
  {
    v17 = 556;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v16,
      v56);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v58);
    goto LABEL_42;
  }
  Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, _OWORD *))this[21].Ptr;
  v67 = 0;
  v16 = Ptr[8](this + 21, &v67);
  v5 = v16;
  if ( v16 < 0 )
  {
    v17 = 559;
    goto LABEL_14;
  }
  v19 = v62;
  v59 = 0;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v62 + 80LL);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v59);
  v21 = v20(v19, v64, &v59);
  v5 = v21;
  if ( v21 < 0 )
  {
    v22 = 563;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v21,
      v56);
LABEL_40:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v59);
    goto LABEL_41;
  }
  v23 = v61;
  v24 = v59;
  v57[0] = 0;
  v25 = *v61;
  string = 0;
  v26 = WindowsCreateStringReference(L"CurrentlyShownApplicationViewId", 0x1Fu, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    __debugbreak();
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v25 + 80))(v23, string, v24, v57);
  v5 = v21;
  if ( v21 < 0 )
  {
    v22 = 565;
    goto LABEL_19;
  }
  v29 = v58;
  if ( v58 )
  {
    v30 = v61;
    v31 = *v61;
    string = 0;
    v32 = WindowsCreateStringReference(L"ViewSwitcher", 0xCu, &hstringHeader, &string);
    if ( v32 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
      __debugbreak();
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v31 + 80))(v30, string, v29, v57);
    v5 = v21;
    if ( v21 < 0 )
    {
      v22 = 569;
      goto LABEL_19;
    }
  }
  v35 = v62;
  v60 = 0;
  v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v62 + 104LL);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v60);
  v37 = v36(v35, v67, &v60);
  v5 = v37;
  if ( v37 < 0 )
  {
    v38 = 573;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v37,
      v56);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v60);
    goto LABEL_40;
  }
  v39 = v61;
  v40 = v60;
  v41 = *v61;
  string = 0;
  v42 = WindowsCreateStringReference(L"MultiView:AamActivationId", 0x19u, &hstringHeader, &string);
  if ( v42 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
    JUMPOUT(0x18008D943LL);
  }
  v37 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v41 + 80))(v39, string, v40, v57);
  v5 = v37;
  if ( v37 < 0 )
  {
    v38 = 574;
    goto LABEL_29;
  }
  v45 = v62;
  v63 = 0;
  v46 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v62 + 136LL);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v63);
  LOBYTE(v47) = BYTE8(v67);
  v48 = v46(v45, v47, &v63);
  v5 = v48;
  if ( v48 < 0 )
  {
    v49 = 577;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v49,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v48,
      v56);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v63);
    goto LABEL_39;
  }
  v50 = v61;
  v51 = v63;
  v52 = *v61;
  string = 0;
  v53 = WindowsCreateStringReference(L"IsApplicationMultiviewActivationPolicyEnabled", 0x2Du, &hstringHeader, &string);
  if ( v53 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v53, v54, v55);
    __debugbreak();
  }
  v48 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v52 + 80))(v50, string, v51, v57);
  v5 = v48;
  if ( v48 < 0 )
  {
    v49 = 578;
    goto LABEL_38;
  }
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v61);
  return 0;
}

```

## disassembly

```asm
0x18008d4a0  mov     [rsp-8+arg_10], rbx
0x18008d4a5  mov     [rsp-8+arg_18], rsi
0x18008d4aa  push    rbp
0x18008d4ab  push    rdi
0x18008d4ac  push    r14
0x18008d4ae  lea     rbp, [rsp-47h]
0x18008d4b3  sub     rsp, 0B0h
0x18008d4ba  mov     rax, cs:__security_cookie
0x18008d4c1  xor     rax, rsp
0x18008d4c4  mov     [rbp+57h+var_20], rax
0x18008d4c8  mov     rdi, rdx
0x18008d4cb  mov     rsi, rcx
0x18008d4ce  call    ?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18008d4d3  xor     r14d, r14d
0x18008d4d6  mov     ebx, eax
0x18008d4d8  test    eax, eax
0x18008d4da  jns     short loc_18008D4FB
0x18008d4dc  mov     rcx, [rbp+5Fh]; this
0x18008d4e0  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d4e7  mov     r9d, eax; char *
0x18008d4ea  mov     edx, 220h; void *
0x18008d4ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d4f4  mov     eax, ebx
0x18008d4f6  jmp     loc_18008D8F8
0x18008d4fb  mov     rax, [rdi]
0x18008d4fe  lea     rcx, [rbp+57h+var_70]
0x18008d502  mov     [rbp+57h+var_70], r14
0x18008d506  mov     [rbp+57h+var_68], r14
0x18008d50a  mov     rbx, [rax]
0x18008d50d  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d512  lea     r8, [rbp+57h+var_70]
0x18008d516  mov     rcx, rdi
0x18008d519  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18008d520  mov     rax, rbx
0x18008d523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d528  mov     ebx, eax
0x18008d52a  test    eax, eax
0x18008d52c  jns     short loc_18008D535
0x18008d52e  mov     edx, 225h
0x18008d533  jmp     short loc_18008D587
0x18008d535  lea     r9, [rbp+57h+string]; string
0x18008d539  mov     [rbp+57h+string], r14
0x18008d53d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008d541  mov     edx, 20h ; ' '; length
0x18008d546  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18008d54d  call    cs:__imp_WindowsCreateStringReference
0x18008d553  test    eax, eax
0x18008d555  js      loc_18008D924
0x18008d55b  mov     rbx, [rbp+57h+string]
0x18008d55f  lea     rcx, [rbp+57h+var_68]
0x18008d563  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d568  lea     r8, [rbp+57h+var_68]
0x18008d56c  mov     rcx, rbx
0x18008d56f  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18008d576  call    cs:__imp_RoGetActivationFactory
0x18008d57c  mov     ebx, eax
0x18008d57e  test    eax, eax
0x18008d580  jns     short loc_18008D59F
0x18008d582  mov     edx, 226h; void *
0x18008d587  mov     rcx, [rbp+5Fh]; this
0x18008d58b  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d592  mov     r9d, eax; char *
0x18008d595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d59a  jmp     loc_18008D8A9
0x18008d59f  lea     rcx, [rsi+98h]
0x18008d5a6  mov     [rbp+57h+var_58], r14d
0x18008d5aa  mov     rax, [rcx]
0x18008d5ad  lea     rdx, [rbp+57h+var_58]
0x18008d5b1  mov     rax, [rax+30h]
0x18008d5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d5ba  mov     ebx, eax
0x18008d5bc  test    eax, eax
0x18008d5be  jns     short loc_18008D5C7
0x18008d5c0  mov     edx, 229h
0x18008d5c5  jmp     short loc_18008D587
0x18008d5c7  lea     rdi, [rsi+0A0h]
0x18008d5ce  mov     [rbp+57h+var_88], r14
0x18008d5d2  mov     rax, [rdi]
0x18008d5d5  lea     rcx, [rbp+57h+var_88]
0x18008d5d9  mov     rbx, [rax+30h]
0x18008d5dd  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d5e2  lea     rdx, [rbp+57h+var_88]
0x18008d5e6  mov     rcx, rdi
0x18008d5e9  mov     rax, rbx
0x18008d5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d5f1  mov     ebx, eax
0x18008d5f3  test    eax, eax
0x18008d5f5  jns     short loc_18008D614
0x18008d5f7  mov     edx, 22Ch; void *
0x18008d5fc  mov     rcx, [rbp+5Fh]; this
0x18008d600  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d607  mov     r9d, eax; char *
0x18008d60a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d60f  jmp     loc_18008D8A0
0x18008d614  lea     rcx, [rsi+0A8h]
0x18008d61b  xorps   xmm0, xmm0
0x18008d61e  mov     rax, [rcx]
0x18008d621  lea     rdx, [rbp+57h+var_30]
0x18008d625  movups  [rbp+57h+var_30], xmm0
0x18008d629  mov     rax, [rax+40h]
0x18008d62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d632  mov     ebx, eax
0x18008d634  test    eax, eax
0x18008d636  jns     short loc_18008D63F
0x18008d638  mov     edx, 22Fh
0x18008d63d  jmp     short loc_18008D5FC
0x18008d63f  mov     rdi, [rbp+57h+var_68]
0x18008d643  lea     rcx, [rbp+57h+var_80]
0x18008d647  mov     [rbp+57h+var_80], r14
0x18008d64b  mov     rax, [rdi]
0x18008d64e  mov     rbx, [rax+50h]
0x18008d652  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d657  mov     edx, [rbp+57h+var_58]
0x18008d65a  lea     r8, [rbp+57h+var_80]
0x18008d65e  mov     rcx, rdi
0x18008d661  mov     rax, rbx
0x18008d664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d669  mov     ebx, eax
0x18008d66b  test    eax, eax
0x18008d66d  jns     short loc_18008D68C
0x18008d66f  mov     edx, 233h; void *
0x18008d674  mov     rcx, [rbp+5Fh]; this
0x18008d678  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d67f  mov     r9d, eax; char *
0x18008d682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d687  jmp     loc_18008D897
0x18008d68c  mov     rbx, [rbp+57h+var_70]
0x18008d690  lea     r9, [rbp+57h+string]; string
0x18008d694  mov     rsi, [rbp+57h+var_80]
0x18008d698  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008d69c  mov     [rbp+57h+var_90], r14b
0x18008d6a0  lea     rcx, aCurrentlyshown; "CurrentlyShownApplicationViewId"
0x18008d6a7  mov     edx, 1Fh; length
0x18008d6ac  mov     rdi, [rbx]
0x18008d6af  mov     [rbp+57h+string], r14
0x18008d6b3  call    cs:__imp_WindowsCreateStringReference
0x18008d6b9  test    eax, eax
0x18008d6bb  js      loc_18008D92C
0x18008d6c1  mov     rdx, [rbp+57h+string]
0x18008d6c5  lea     r9, [rbp+57h+var_90]
0x18008d6c9  mov     rax, [rdi+50h]
0x18008d6cd  mov     r8, rsi
0x18008d6d0  mov     rcx, rbx
0x18008d6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6d8  mov     ebx, eax
0x18008d6da  test    eax, eax
0x18008d6dc  jns     short loc_18008D6E5
0x18008d6de  mov     edx, 235h
0x18008d6e3  jmp     short loc_18008D674
0x18008d6e5  mov     rbx, [rbp+57h+var_88]
0x18008d6e9  test    rbx, rbx
0x18008d6ec  jz      short loc_18008D742
0x18008d6ee  mov     rdi, [rbp+57h+var_70]
0x18008d6f2  lea     r9, [rbp+57h+string]; string
0x18008d6f6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008d6fa  mov     edx, 0Ch; length
0x18008d6ff  lea     rcx, aViewswitcher; "ViewSwitcher"
0x18008d706  mov     rsi, [rdi]
0x18008d709  mov     [rbp+57h+string], r14
0x18008d70d  call    cs:__imp_WindowsCreateStringReference
0x18008d713  test    eax, eax
0x18008d715  js      loc_18008D934
0x18008d71b  mov     rdx, [rbp+57h+string]
0x18008d71f  lea     r9, [rbp+57h+var_90]
0x18008d723  mov     rax, [rsi+50h]
0x18008d727  mov     r8, rbx
0x18008d72a  mov     rcx, rdi
0x18008d72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d732  mov     ebx, eax
0x18008d734  test    eax, eax
0x18008d736  jns     short loc_18008D742
0x18008d738  mov     edx, 239h
0x18008d73d  jmp     loc_18008D674
0x18008d742  mov     rdi, [rbp+57h+var_68]
0x18008d746  lea     rcx, [rbp+57h+var_78]
0x18008d74a  mov     [rbp+57h+var_78], r14
0x18008d74e  mov     rax, [rdi]
0x18008d751  mov     rbx, [rax+68h]
0x18008d755  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d75a  mov     rdx, qword ptr [rbp+57h+var_30]
0x18008d75e  lea     r8, [rbp+57h+var_78]
0x18008d762  mov     rcx, rdi
0x18008d765  mov     rax, rbx
0x18008d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d76d  mov     ebx, eax
0x18008d76f  test    eax, eax
0x18008d771  jns     short loc_18008D790
0x18008d773  mov     edx, 23Dh; void *
0x18008d778  mov     rcx, [rbp+5Fh]; this
0x18008d77c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d783  mov     r9d, eax; char *
0x18008d786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d78b  jmp     loc_18008D88E
0x18008d790  mov     rbx, [rbp+57h+var_70]
0x18008d794  lea     r9, [rbp+57h+string]; string
0x18008d798  mov     rsi, [rbp+57h+var_78]
0x18008d79c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008d7a0  mov     edx, 19h; length
0x18008d7a5  lea     rcx, aMultiviewAamac; "MultiView:AamActivationId"
0x18008d7ac  mov     rdi, [rbx]
0x18008d7af  mov     [rbp+57h+string], r14
0x18008d7b3  call    cs:__imp_WindowsCreateStringReference
0x18008d7b9  test    eax, eax
0x18008d7bb  js      loc_18008D93C
0x18008d7c1  mov     rdx, [rbp+57h+string]
0x18008d7c5  lea     r9, [rbp+57h+var_90]
0x18008d7c9  mov     rax, [rdi+50h]
0x18008d7cd  mov     r8, rsi
0x18008d7d0  mov     rcx, rbx
0x18008d7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d7d8  mov     ebx, eax
0x18008d7da  test    eax, eax
0x18008d7dc  jns     short loc_18008D7E5
0x18008d7de  mov     edx, 23Eh
0x18008d7e3  jmp     short loc_18008D778
0x18008d7e5  mov     rdi, [rbp+57h+var_68]
0x18008d7e9  lea     rcx, [rbp+57h+var_60]
0x18008d7ed  mov     [rbp+57h+var_60], r14
0x18008d7f1  mov     rax, [rdi]
0x18008d7f4  mov     rbx, [rax+88h]
0x18008d7fb  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d800  mov     dl, byte ptr [rbp+57h+var_30+8]
0x18008d803  lea     r8, [rbp+57h+var_60]
0x18008d807  mov     rcx, rdi
0x18008d80a  mov     rax, rbx
0x18008d80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d812  mov     ebx, eax
0x18008d814  test    eax, eax
0x18008d816  jns     short loc_18008D81F
0x18008d818  mov     edx, 241h
0x18008d81d  jmp     short loc_18008D872
0x18008d81f  mov     rbx, [rbp+57h+var_70]
0x18008d823  lea     r9, [rbp+57h+string]; string
0x18008d827  mov     rsi, [rbp+57h+var_60]
0x18008d82b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18008d82f  mov     edx, 2Dh ; '-'; length
0x18008d834  lea     rcx, aIsapplicationm; "IsApplicationMultiviewActivationPolicyE"...
0x18008d83b  mov     rdi, [rbx]
0x18008d83e  mov     [rbp+57h+string], r14
0x18008d842  call    cs:__imp_WindowsCreateStringReference
0x18008d848  test    eax, eax
0x18008d84a  js      loc_18008D91C
0x18008d850  mov     rdx, [rbp+57h+string]
0x18008d854  lea     r9, [rbp+57h+var_90]
0x18008d858  mov     rax, [rdi+50h]
0x18008d85c  mov     r8, rsi
0x18008d85f  mov     rcx, rbx
0x18008d862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d867  mov     ebx, eax
0x18008d869  test    eax, eax
0x18008d86b  jns     short loc_18008D8C0
0x18008d86d  mov     edx, 242h; void *
0x18008d872  mov     rcx, [rbp+5Fh]; this
0x18008d876  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18008d87d  mov     r9d, eax; char *
0x18008d880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d885  lea     rcx, [rbp+57h+var_60]
0x18008d889  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d88e  lea     rcx, [rbp+57h+var_78]
0x18008d892  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d897  lea     rcx, [rbp+57h+var_80]
0x18008d89b  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8a0  lea     rcx, [rbp+57h+var_88]
0x18008d8a4  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8a9  lea     rcx, [rbp+57h+var_68]
0x18008d8ad  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8b2  lea     rcx, [rbp+57h+var_70]
0x18008d8b6  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8bb  jmp     loc_18008D4F4
0x18008d8c0  lea     rcx, [rbp+57h+var_60]
0x18008d8c4  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8c9  lea     rcx, [rbp+57h+var_78]
0x18008d8cd  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8d2  lea     rcx, [rbp+57h+var_80]
0x18008d8d6  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8db  lea     rcx, [rbp+57h+var_88]
0x18008d8df  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8e4  lea     rcx, [rbp+57h+var_68]
0x18008d8e8  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8ed  lea     rcx, [rbp+57h+var_70]
0x18008d8f1  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18008d8f6  xor     eax, eax
0x18008d8f8  mov     rcx, [rbp+57h+var_20]
0x18008d8fc  xor     rcx, rsp; StackCookie
0x18008d8ff  call    __security_check_cookie
0x18008d904  lea     r11, [rsp+0C0h+var_10]
0x18008d90c  mov     rbx, [r11+30h]
0x18008d910  mov     rsi, [r11+38h]
0x18008d914  mov     rsp, r11
0x18008d917  pop     r14
0x18008d919  pop     rdi
0x18008d91a  pop     rbp
0x18008d91b  retn
0x18008d91c  mov     ecx, eax; this
0x18008d91e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008d923  int     3; Trap to Debugger
0x18008d924  mov     ecx, eax; this
0x18008d926  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18008d92b  int     3; Trap to Debugger
0x18008d92c  mov     ecx, eax; this
  ... truncated ...
```

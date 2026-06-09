# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18004c8e0`
- end: `0x18004ccdf`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18001bf68`
- `0x18004a1c4`
- `0x18004a9c0`
- `0x18004b8f0`
- `0x18004c8e0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ca66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc9a`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 (__fastcall **v8)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v9)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 (__fastcall *v15)(char *, HSTRING *); // rbx
  int v16; // eax
  __int64 v17; // rax
  __int64 (__fastcall *v18)(char *, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // rax
  __int64 (__fastcall *v21)(char *, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  _QWORD *v31; // rsi
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 (__fastcall *v34)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, HSTRING, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r8
  _QWORD *v43; // rsi
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 (__fastcall *v46)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rbx
  _QWORD *v50; // rsi
  __int64 v51; // rax
  __int64 (__fastcall *v52)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  int v58; // [rsp+20h] [rbp-39h]
  _BYTE v59[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v61; // [rsp+40h] [rbp-19h] BYREF
  __int64 v62; // [rsp+48h] [rbp-11h] BYREF
  __int64 v63; // [rsp+50h] [rbp-9h] BYREF
  __int64 v64; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v65; // [rsp+60h] [rbp+7h] BYREF
  __int64 v66; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v68; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(
         (CLaunchActivatedEventArgs *)((char *)this - 256),
         a2);
  v7 = v4;
  if ( v4 >= 0 )
  {
    v8 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v65 = 0;
    v66 = 0;
    v9 = *v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v5, v6);
    v10 = v9(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v65);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = 105;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v10,
        v58);
LABEL_33:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v13, v14);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v55, v56);
      return v7;
    }
    v68 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
            v68,
            (__int64)&v66,
            v12);
    v7 = v10;
    if ( v10 < 0 )
    {
      v11 = 106;
      goto LABEL_7;
    }
    string = 0;
    v15 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = v15((char *)this - 16, &string);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v16,
        v58);
LABEL_10:
      WindowsDeleteString(string);
LABEL_32:
      string = 0;
      goto LABEL_33;
    }
    v17 = *((_QWORD *)this - 2);
    v61 = 0;
    v18 = *(__int64 (__fastcall **)(char *, HSTRING *))(v17 + 56);
    WindowsDeleteString(0);
    v61 = 0;
    v19 = v18((char *)this - 16, &v61);
    v7 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v19,
        v58);
LABEL_13:
      WindowsDeleteString(v61);
      v61 = 0;
      goto LABEL_10;
    }
    v20 = *((_QWORD *)this - 1);
    v62 = 0;
    v21 = *(__int64 (__fastcall **)(char *, __int64 *))(v20 + 48);
    Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
    v22 = v21((char *)this - 8, &v62);
    v7 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v22,
        v58);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
      goto LABEL_13;
    }
    v25 = v66;
    v63 = 0;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v66 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, v23, v24);
    v27 = v26(v25, string, &v63);
    v7 = v27;
    if ( v27 >= 0 )
    {
      v31 = v65;
      v32 = v63;
      v59[0] = 0;
      v33 = *v65;
      v68 = 0;
      v34 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v33 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
      v27 = v34(v31, v68, v32, v59);
      v7 = v27;
      if ( v27 >= 0 )
      {
        v37 = v66;
        v64 = 0;
        v38 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v66 + 144LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v35, v36);
        v39 = v38(v37, v61, &v64);
        v7 = v39;
        if ( v39 >= 0 )
        {
          v43 = v65;
          v44 = v64;
          v45 = *v65;
          v68 = 0;
          v46 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v45 + 80);
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileId", 7u, 6u);
          v39 = v46(v43, v68, v44, v59);
          v7 = v39;
          if ( v39 >= 0 )
          {
            v49 = v62;
            if ( !v62
              || (v50 = v65,
                  v51 = *v65,
                  v68 = 0,
                  v52 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v51 + 80),
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                    &hstringHeader,
                    L"TileActivatedInfo",
                    0x12u,
                    0x11u),
                  v39 = v52(v50, v68, v49, v59),
                  v7 = v39,
                  v39 >= 0) )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v47, v48);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, v53, v54);
              Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v62);
              WindowsDeleteString(v61);
              v61 = 0;
              WindowsDeleteString(string);
              v7 = 0;
              goto LABEL_32;
            }
            v40 = 130;
          }
          else
          {
            v40 = 126;
          }
        }
        else
        {
          v40 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
          (const char *)(unsigned int)v39,
          v58);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v41, v42);
        goto LABEL_20;
      }
      v28 = 122;
    }
    else
    {
      v28 = 120;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v27,
      v58);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, v29, v30);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
    (const char *)(unsigned int)v4,
    v58);
  return v7;
}

```

## disassembly

```asm
0x18004c8e0  mov     [rsp-8+arg_10], rbx
0x18004c8e5  mov     [rsp-8+arg_18], rsi
0x18004c8ea  push    rbp
0x18004c8eb  push    rdi
0x18004c8ec  push    r14
0x18004c8ee  lea     rbp, [rsp-47h]
0x18004c8f3  sub     rsp, 0A0h
0x18004c8fa  mov     rax, cs:__security_cookie
0x18004c901  xor     rax, rsp
0x18004c904  mov     [rbp+57h+var_20], rax
0x18004c908  mov     rsi, rcx
0x18004c90b  mov     rdi, rdx
0x18004c90e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x18004c915  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18004c91a  xor     r14d, r14d
0x18004c91d  mov     ebx, eax
0x18004c91f  test    eax, eax
0x18004c921  jns     short loc_18004C93F
0x18004c923  mov     rcx, [rbp+5Fh]; this
0x18004c927  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004c92e  mov     r9d, eax; char *
0x18004c931  lea     edx, [r14+64h]; void *
0x18004c935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c93a  jmp     loc_18004CCB9
0x18004c93f  mov     rax, [rdi]
0x18004c942  lea     rcx, [rbp+57h+var_50]
0x18004c946  mov     [rbp+57h+var_50], r14
0x18004c94a  mov     [rbp+57h+var_48], r14
0x18004c94e  mov     rbx, [rax]
0x18004c951  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c956  lea     r8, [rbp+57h+var_50]
0x18004c95a  mov     rcx, rdi
0x18004c95d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004c964  mov     rax, rbx
0x18004c967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c96c  mov     ebx, eax
0x18004c96e  test    eax, eax
0x18004c970  jns     short loc_18004C979
0x18004c972  mov     edx, 69h ; 'i'
0x18004c977  jmp     short loc_18004C9AF
0x18004c979  mov     r9d, 20h ; ' '; unsigned int
0x18004c97f  mov     [rbp+57h+var_28], r14
0x18004c983  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18004c98a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004c98e  lea     r8d, [r9+1]; unsigned int
0x18004c992  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004c997  mov     rcx, [rbp+57h+var_28]
0x18004c99b  lea     rdx, [rbp+57h+var_48]
0x18004c99f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18004c9a4  mov     ebx, eax
0x18004c9a6  test    eax, eax
0x18004c9a8  jns     short loc_18004C9C7
0x18004c9aa  mov     edx, 6Ah ; 'j'; void *
0x18004c9af  mov     rcx, [rbp+5Fh]; this
0x18004c9b3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004c9ba  mov     r9d, eax; char *
0x18004c9bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c9c2  jmp     loc_18004CCA7
0x18004c9c7  lea     rdi, [rsi-10h]
0x18004c9cb  mov     [rbp+57h+string], r14
0x18004c9cf  mov     rax, [rdi]
0x18004c9d2  xor     ecx, ecx; string
0x18004c9d4  mov     rbx, [rax+30h]
0x18004c9d8  call    cs:__imp_WindowsDeleteString
0x18004c9de  lea     rdx, [rbp+57h+string]
0x18004c9e2  mov     [rbp+57h+string], r14
0x18004c9e6  mov     rcx, rdi
0x18004c9e9  mov     rax, rbx
0x18004c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9f1  mov     ebx, eax
0x18004c9f3  test    eax, eax
0x18004c9f5  jns     short loc_18004CA1E
0x18004c9f7  mov     rcx, [rbp+5Fh]; this
0x18004c9fb  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004ca02  mov     r9d, eax; char *
0x18004ca05  mov     edx, 6Eh ; 'n'; void *
0x18004ca0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ca0f  mov     rcx, [rbp+57h+string]; string
0x18004ca13  call    cs:__imp_WindowsDeleteString
0x18004ca19  jmp     loc_18004CCA3
0x18004ca1e  mov     rax, [rdi]
0x18004ca21  xor     ecx, ecx; string
0x18004ca23  mov     [rbp+57h+var_70], r14
0x18004ca27  mov     rbx, [rax+38h]
0x18004ca2b  call    cs:__imp_WindowsDeleteString
0x18004ca31  lea     rdx, [rbp+57h+var_70]
0x18004ca35  mov     [rbp+57h+var_70], r14
0x18004ca39  mov     rcx, rdi
0x18004ca3c  mov     rax, rbx
0x18004ca3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca44  mov     ebx, eax
0x18004ca46  test    eax, eax
0x18004ca48  jns     short loc_18004CA72
0x18004ca4a  mov     rcx, [rbp+5Fh]; this
0x18004ca4e  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004ca55  mov     r9d, eax; char *
0x18004ca58  mov     edx, 71h ; 'q'; void *
0x18004ca5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ca62  mov     rcx, [rbp+57h+var_70]; string
0x18004ca66  call    cs:__imp_WindowsDeleteString
0x18004ca6c  mov     [rbp+57h+var_70], r14
0x18004ca70  jmp     short loc_18004CA0F
0x18004ca72  mov     rax, [rsi-8]
0x18004ca76  lea     rcx, [rbp+57h+var_68]
0x18004ca7a  mov     [rbp+57h+var_68], r14
0x18004ca7e  mov     rbx, [rax+30h]
0x18004ca82  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18004ca87  lea     rdx, [rbp+57h+var_68]
0x18004ca8b  mov     rax, rbx
0x18004ca8e  lea     rcx, [rsi-8]
0x18004ca92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca97  mov     ebx, eax
0x18004ca99  test    eax, eax
0x18004ca9b  jns     short loc_18004CAC0
0x18004ca9d  mov     rcx, [rbp+5Fh]; this
0x18004caa1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004caa8  mov     r9d, eax; char *
0x18004caab  mov     edx, 74h ; 't'; void *
0x18004cab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cab5  lea     rcx, [rbp+57h+var_68]
0x18004cab9  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18004cabe  jmp     short loc_18004CA62
0x18004cac0  mov     rdi, [rbp+57h+var_48]
0x18004cac4  lea     rcx, [rbp+57h+var_60]
0x18004cac8  mov     [rbp+57h+var_60], r14
0x18004cacc  mov     rax, [rdi]
0x18004cacf  mov     rbx, [rax+90h]
0x18004cad6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cadb  mov     rdx, [rbp+57h+string]
0x18004cadf  lea     r8, [rbp+57h+var_60]
0x18004cae3  mov     rcx, rdi
0x18004cae6  mov     rax, rbx
0x18004cae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caee  mov     ebx, eax
0x18004caf0  test    eax, eax
0x18004caf2  jns     short loc_18004CB17
0x18004caf4  mov     edx, 78h ; 'x'; void *
0x18004caf9  mov     rcx, [rbp+5Fh]; this
0x18004cafd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004cb04  mov     r9d, eax; char *
0x18004cb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cb0c  lea     rcx, [rbp+57h+var_60]
0x18004cb10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb15  jmp     short loc_18004CAB5
0x18004cb17  mov     rsi, [rbp+57h+var_50]
0x18004cb1b  lea     rdx, aArguments; "Arguments"
0x18004cb22  mov     rbx, [rbp+57h+var_60]
0x18004cb26  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004cb2a  mov     [rbp+57h+var_80], r14b
0x18004cb2e  mov     r9d, 9; unsigned int
0x18004cb34  mov     rax, [rsi]
0x18004cb37  mov     [rbp+57h+var_28], r14
0x18004cb3b  lea     r8d, [r9+1]; unsigned int
0x18004cb3f  mov     rdi, [rax+50h]
0x18004cb43  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004cb48  mov     rdx, [rbp+57h+var_28]
0x18004cb4c  lea     r9, [rbp+57h+var_80]
0x18004cb50  mov     r8, rbx
0x18004cb53  mov     rcx, rsi
0x18004cb56  mov     rax, rdi
0x18004cb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb5e  mov     ebx, eax
0x18004cb60  test    eax, eax
0x18004cb62  jns     short loc_18004CB6B
0x18004cb64  mov     edx, 7Ah ; 'z'
0x18004cb69  jmp     short loc_18004CAF9
0x18004cb6b  mov     rdi, [rbp+57h+var_48]
0x18004cb6f  lea     rcx, [rbp+57h+var_58]
0x18004cb73  mov     [rbp+57h+var_58], r14
0x18004cb77  mov     rax, [rdi]
0x18004cb7a  mov     rbx, [rax+90h]
0x18004cb81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cb86  mov     rdx, [rbp+57h+var_70]
0x18004cb8a  lea     r8, [rbp+57h+var_58]
0x18004cb8e  mov     rcx, rdi
0x18004cb91  mov     rax, rbx
0x18004cb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb99  mov     ebx, eax
0x18004cb9b  test    eax, eax
0x18004cb9d  jns     short loc_18004CBC5
0x18004cb9f  mov     edx, 7Dh ; '}'; void *
0x18004cba4  mov     rcx, [rbp+5Fh]; this
0x18004cba8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18004cbaf  mov     r9d, eax; char *
0x18004cbb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cbb7  lea     rcx, [rbp+57h+var_58]
0x18004cbbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cbc0  jmp     loc_18004CB0C
0x18004cbc5  mov     rsi, [rbp+57h+var_50]
0x18004cbc9  lea     rdx, aTileid; "TileId"
0x18004cbd0  mov     rbx, [rbp+57h+var_58]
0x18004cbd4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004cbd8  mov     r9d, 6; unsigned int
0x18004cbde  mov     rax, [rsi]
0x18004cbe1  mov     [rbp+57h+var_28], r14
0x18004cbe5  lea     r8d, [r9+1]; unsigned int
0x18004cbe9  mov     rdi, [rax+50h]
0x18004cbed  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004cbf2  mov     rdx, [rbp+57h+var_28]
0x18004cbf6  lea     r9, [rbp+57h+var_80]
0x18004cbfa  mov     r8, rbx
0x18004cbfd  mov     rcx, rsi
0x18004cc00  mov     rax, rdi
0x18004cc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc08  mov     ebx, eax
0x18004cc0a  test    eax, eax
0x18004cc0c  jns     short loc_18004CC15
0x18004cc0e  mov     edx, 7Eh ; '~'
0x18004cc13  jmp     short loc_18004CBA4
0x18004cc15  mov     rbx, [rbp+57h+var_68]
0x18004cc19  test    rbx, rbx
0x18004cc1c  jz      short loc_18004CC6D
0x18004cc1e  mov     rsi, [rbp+57h+var_50]
0x18004cc22  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x18004cc29  mov     r9d, 11h; unsigned int
0x18004cc2f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004cc33  mov     rax, [rsi]
0x18004cc36  lea     r8d, [r9+1]; unsigned int
0x18004cc3a  mov     [rbp+57h+var_28], r14
0x18004cc3e  mov     rdi, [rax+50h]
0x18004cc42  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004cc47  mov     rdx, [rbp+57h+var_28]
0x18004cc4b  lea     r9, [rbp+57h+var_80]
0x18004cc4f  mov     r8, rbx
0x18004cc52  mov     rcx, rsi
0x18004cc55  mov     rax, rdi
0x18004cc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc5d  mov     ebx, eax
0x18004cc5f  test    eax, eax
0x18004cc61  jns     short loc_18004CC6D
0x18004cc63  mov     edx, 82h
0x18004cc68  jmp     loc_18004CBA4
0x18004cc6d  lea     rcx, [rbp+57h+var_58]
0x18004cc71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cc76  lea     rcx, [rbp+57h+var_60]
0x18004cc7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cc7f  lea     rcx, [rbp+57h+var_68]
0x18004cc83  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18004cc88  mov     rcx, [rbp+57h+var_70]; string
0x18004cc8c  call    cs:__imp_WindowsDeleteString
0x18004cc92  mov     rcx, [rbp+57h+string]; string
0x18004cc96  mov     [rbp+57h+var_70], r14
0x18004cc9a  call    cs:__imp_WindowsDeleteString
0x18004cca0  mov     ebx, r14d
0x18004cca3  mov     [rbp+57h+string], r14
0x18004cca7  lea     rcx, [rbp+57h+var_48]
0x18004ccab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ccb0  lea     rcx, [rbp+57h+var_50]
0x18004ccb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ccb9  mov     eax, ebx
0x18004ccbb  mov     rcx, [rbp+57h+var_20]
0x18004ccbf  xor     rcx, rsp; StackCookie
0x18004ccc2  call    __security_check_cookie
0x18004ccc7  lea     r11, [rsp+0B0h+var_10]
0x18004cccf  mov     rbx, [r11+30h]
0x18004ccd3  mov     rsi, [r11+38h]
0x18004ccd7  mov     rsp, r11
0x18004ccda  pop     r14
0x18004ccdc  pop     rdi
0x18004ccdd  pop     rbp
0x18004ccde  retn
```

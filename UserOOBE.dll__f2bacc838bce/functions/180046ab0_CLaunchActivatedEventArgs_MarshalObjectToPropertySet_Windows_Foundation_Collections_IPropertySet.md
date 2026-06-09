# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180046ab0`
- end: `0x180046eaf`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800067b0`
- `0x180007134`
- `0x180012328`
- `0x180044bc8`
- `0x180045adc`
- `0x180046ab0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046be3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046ba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046be3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046e6a`

## pseudocode

```c
__int64 __fastcall CLaunchActivatedEventArgs::MarshalObjectToPropertySet(
        CLaunchActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(char *, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(char *, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(char *, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  _QWORD *v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 (__fastcall *v25)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  _QWORD *v30; // rsi
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 (__fastcall *v33)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v34; // rbx
  _QWORD *v35; // rsi
  __int64 v36; // rax
  __int64 (__fastcall *v37)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  int v39; // [rsp+20h] [rbp-39h]
  _BYTE v40[8]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v42; // [rsp+40h] [rbp-19h] BYREF
  __int64 v43; // [rsp+48h] [rbp-11h] BYREF
  __int64 v44; // [rsp+50h] [rbp-9h] BYREF
  __int64 v45; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp+7h] BYREF
  __int64 v47; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  __int64 v49; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(
         (CLaunchActivatedEventArgs *)((char *)this - 256),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v46 = 0;
    v47 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v46);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 105;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v8,
        v39);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      return v5;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v49,
           &v47);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 106;
      goto LABEL_7;
    }
    string = 0;
    v10 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 2) + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10((char *)this - 16, &string);
    v5 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v11,
        v39);
LABEL_10:
      WindowsDeleteString(string);
LABEL_32:
      string = 0;
      goto LABEL_33;
    }
    v12 = *((_QWORD *)this - 2);
    v42 = 0;
    v13 = *(__int64 (__fastcall **)(char *, HSTRING *))(v12 + 56);
    WindowsDeleteString(0);
    v42 = 0;
    v14 = v13((char *)this - 16, &v42);
    v5 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v14,
        v39);
LABEL_13:
      WindowsDeleteString(v42);
      v42 = 0;
      goto LABEL_10;
    }
    v15 = *((_QWORD *)this - 1);
    v43 = 0;
    v16 = *(__int64 (__fastcall **)(char *, __int64 *))(v15 + 48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v17 = v16((char *)this - 8, &v43);
    v5 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
        (const char *)(unsigned int)v17,
        v39);
LABEL_16:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      goto LABEL_13;
    }
    v18 = v47;
    v44 = 0;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v20 = v19(v18, string, &v44);
    v5 = v20;
    if ( v20 >= 0 )
    {
      v22 = v46;
      v23 = v44;
      v40[0] = 0;
      v24 = *v46;
      v49 = 0;
      v25 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v24 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
      v20 = v25(v22, v49, v23, v40);
      v5 = v20;
      if ( v20 >= 0 )
      {
        v26 = v47;
        v45 = 0;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 144LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v28 = v27(v26, v42, &v45);
        v5 = v28;
        if ( v28 >= 0 )
        {
          v30 = v46;
          v31 = v45;
          v32 = *v46;
          v49 = 0;
          v33 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v32 + 80);
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TileId", 7u, 6u);
          v28 = v33(v30, v49, v31, v40);
          v5 = v28;
          if ( v28 >= 0 )
          {
            v34 = v43;
            if ( !v43
              || (v35 = v46,
                  v36 = *v46,
                  v49 = 0,
                  v37 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v36 + 80),
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                    &hstringHeader,
                    L"TileActivatedInfo",
                    0x12u,
                    0x11u),
                  v28 = v37(v35, v49, v34, v40),
                  v5 = v28,
                  v28 >= 0) )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              WindowsDeleteString(v42);
              v42 = 0;
              WindowsDeleteString(string);
              v5 = 0;
              goto LABEL_32;
            }
            v29 = 130;
          }
          else
          {
            v29 = 126;
          }
        }
        else
        {
          v29 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
          (const char *)(unsigned int)v28,
          v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_20;
      }
      v21 = 122;
    }
    else
    {
      v21 = 120;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
      (const char *)(unsigned int)v20,
      v39);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\launchactivated.cpp",
    (const char *)(unsigned int)v4,
    v39);
  return v5;
}

```

## disassembly

```asm
0x180046ab0  mov     [rsp-8+arg_10], rbx
0x180046ab5  mov     [rsp-8+arg_18], rsi
0x180046aba  push    rbp
0x180046abb  push    rdi
0x180046abc  push    r14
0x180046abe  lea     rbp, [rsp-47h]
0x180046ac3  sub     rsp, 0A0h
0x180046aca  mov     rax, cs:__security_cookie
0x180046ad1  xor     rax, rsp
0x180046ad4  mov     [rbp+57h+var_20], rax
0x180046ad8  mov     rsi, rcx
0x180046adb  mov     rdi, rdx
0x180046ade  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x180046ae5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180046aea  xor     r14d, r14d
0x180046aed  mov     ebx, eax
0x180046aef  test    eax, eax
0x180046af1  jns     short loc_180046B0F
0x180046af3  mov     rcx, [rbp+5Fh]; this
0x180046af7  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046afe  mov     r9d, eax; char *
0x180046b01  lea     edx, [r14+64h]; void *
0x180046b05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046b0a  jmp     loc_180046E89
0x180046b0f  mov     rax, [rdi]
0x180046b12  lea     rcx, [rbp+57h+var_50]
0x180046b16  mov     [rbp+57h+var_50], r14
0x180046b1a  mov     [rbp+57h+var_48], r14
0x180046b1e  mov     rbx, [rax]
0x180046b21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046b26  lea     r8, [rbp+57h+var_50]
0x180046b2a  mov     rcx, rdi
0x180046b2d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180046b34  mov     rax, rbx
0x180046b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b3c  mov     ebx, eax
0x180046b3e  test    eax, eax
0x180046b40  jns     short loc_180046B49
0x180046b42  mov     edx, 69h ; 'i'
0x180046b47  jmp     short loc_180046B7F
0x180046b49  mov     r9d, 20h ; ' '; unsigned int
0x180046b4f  mov     [rbp+57h+var_28], r14
0x180046b53  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180046b5a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180046b5e  lea     r8d, [r9+1]; unsigned int
0x180046b62  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046b67  mov     rcx, [rbp+57h+var_28]
0x180046b6b  lea     rdx, [rbp+57h+var_48]
0x180046b6f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180046b74  mov     ebx, eax
0x180046b76  test    eax, eax
0x180046b78  jns     short loc_180046B97
0x180046b7a  mov     edx, 6Ah ; 'j'; void *
0x180046b7f  mov     rcx, [rbp+5Fh]; this
0x180046b83  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046b8a  mov     r9d, eax; char *
0x180046b8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046b92  jmp     loc_180046E77
0x180046b97  lea     rdi, [rsi-10h]
0x180046b9b  mov     [rbp+57h+string], r14
0x180046b9f  mov     rax, [rdi]
0x180046ba2  xor     ecx, ecx; string
0x180046ba4  mov     rbx, [rax+30h]
0x180046ba8  call    cs:__imp_WindowsDeleteString
0x180046bae  lea     rdx, [rbp+57h+string]
0x180046bb2  mov     [rbp+57h+string], r14
0x180046bb6  mov     rcx, rdi
0x180046bb9  mov     rax, rbx
0x180046bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bc1  mov     ebx, eax
0x180046bc3  test    eax, eax
0x180046bc5  jns     short loc_180046BEE
0x180046bc7  mov     rcx, [rbp+5Fh]; this
0x180046bcb  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046bd2  mov     r9d, eax; char *
0x180046bd5  mov     edx, 6Eh ; 'n'; void *
0x180046bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046bdf  mov     rcx, [rbp+57h+string]; string
0x180046be3  call    cs:__imp_WindowsDeleteString
0x180046be9  jmp     loc_180046E73
0x180046bee  mov     rax, [rdi]
0x180046bf1  xor     ecx, ecx; string
0x180046bf3  mov     [rbp+57h+var_70], r14
0x180046bf7  mov     rbx, [rax+38h]
0x180046bfb  call    cs:__imp_WindowsDeleteString
0x180046c01  lea     rdx, [rbp+57h+var_70]
0x180046c05  mov     [rbp+57h+var_70], r14
0x180046c09  mov     rcx, rdi
0x180046c0c  mov     rax, rbx
0x180046c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c14  mov     ebx, eax
0x180046c16  test    eax, eax
0x180046c18  jns     short loc_180046C42
0x180046c1a  mov     rcx, [rbp+5Fh]; this
0x180046c1e  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046c25  mov     r9d, eax; char *
0x180046c28  mov     edx, 71h ; 'q'; void *
0x180046c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046c32  mov     rcx, [rbp+57h+var_70]; string
0x180046c36  call    cs:__imp_WindowsDeleteString
0x180046c3c  mov     [rbp+57h+var_70], r14
0x180046c40  jmp     short loc_180046BDF
0x180046c42  mov     rax, [rsi-8]
0x180046c46  lea     rcx, [rbp+57h+var_68]
0x180046c4a  mov     [rbp+57h+var_68], r14
0x180046c4e  mov     rbx, [rax+30h]
0x180046c52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046c57  lea     rdx, [rbp+57h+var_68]
0x180046c5b  mov     rax, rbx
0x180046c5e  lea     rcx, [rsi-8]
0x180046c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c67  mov     ebx, eax
0x180046c69  test    eax, eax
0x180046c6b  jns     short loc_180046C90
0x180046c6d  mov     rcx, [rbp+5Fh]; this
0x180046c71  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046c78  mov     r9d, eax; char *
0x180046c7b  mov     edx, 74h ; 't'; void *
0x180046c80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046c85  lea     rcx, [rbp+57h+var_68]
0x180046c89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046c8e  jmp     short loc_180046C32
0x180046c90  mov     rdi, [rbp+57h+var_48]
0x180046c94  lea     rcx, [rbp+57h+var_60]
0x180046c98  mov     [rbp+57h+var_60], r14
0x180046c9c  mov     rax, [rdi]
0x180046c9f  mov     rbx, [rax+90h]
0x180046ca6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046cab  mov     rdx, [rbp+57h+string]
0x180046caf  lea     r8, [rbp+57h+var_60]
0x180046cb3  mov     rcx, rdi
0x180046cb6  mov     rax, rbx
0x180046cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cbe  mov     ebx, eax
0x180046cc0  test    eax, eax
0x180046cc2  jns     short loc_180046CE7
0x180046cc4  mov     edx, 78h ; 'x'; void *
0x180046cc9  mov     rcx, [rbp+5Fh]; this
0x180046ccd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046cd4  mov     r9d, eax; char *
0x180046cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046cdc  lea     rcx, [rbp+57h+var_60]
0x180046ce0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046ce5  jmp     short loc_180046C85
0x180046ce7  mov     rsi, [rbp+57h+var_50]
0x180046ceb  lea     rdx, aArguments; "Arguments"
0x180046cf2  mov     rbx, [rbp+57h+var_60]
0x180046cf6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180046cfa  mov     [rbp+57h+var_80], r14b
0x180046cfe  mov     r9d, 9; unsigned int
0x180046d04  mov     rax, [rsi]
0x180046d07  mov     [rbp+57h+var_28], r14
0x180046d0b  lea     r8d, [r9+1]; unsigned int
0x180046d0f  mov     rdi, [rax+50h]
0x180046d13  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046d18  mov     rdx, [rbp+57h+var_28]
0x180046d1c  lea     r9, [rbp+57h+var_80]
0x180046d20  mov     r8, rbx
0x180046d23  mov     rcx, rsi
0x180046d26  mov     rax, rdi
0x180046d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d2e  mov     ebx, eax
0x180046d30  test    eax, eax
0x180046d32  jns     short loc_180046D3B
0x180046d34  mov     edx, 7Ah ; 'z'
0x180046d39  jmp     short loc_180046CC9
0x180046d3b  mov     rdi, [rbp+57h+var_48]
0x180046d3f  lea     rcx, [rbp+57h+var_58]
0x180046d43  mov     [rbp+57h+var_58], r14
0x180046d47  mov     rax, [rdi]
0x180046d4a  mov     rbx, [rax+90h]
0x180046d51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046d56  mov     rdx, [rbp+57h+var_70]
0x180046d5a  lea     r8, [rbp+57h+var_58]
0x180046d5e  mov     rcx, rdi
0x180046d61  mov     rax, rbx
0x180046d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d69  mov     ebx, eax
0x180046d6b  test    eax, eax
0x180046d6d  jns     short loc_180046D95
0x180046d6f  mov     edx, 7Dh ; '}'; void *
0x180046d74  mov     rcx, [rbp+5Fh]; this
0x180046d78  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180046d7f  mov     r9d, eax; char *
0x180046d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046d87  lea     rcx, [rbp+57h+var_58]
0x180046d8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046d90  jmp     loc_180046CDC
0x180046d95  mov     rsi, [rbp+57h+var_50]
0x180046d99  lea     rdx, aTileid; "TileId"
0x180046da0  mov     rbx, [rbp+57h+var_58]
0x180046da4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180046da8  mov     r9d, 6; unsigned int
0x180046dae  mov     rax, [rsi]
0x180046db1  mov     [rbp+57h+var_28], r14
0x180046db5  lea     r8d, [r9+1]; unsigned int
0x180046db9  mov     rdi, [rax+50h]
0x180046dbd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046dc2  mov     rdx, [rbp+57h+var_28]
0x180046dc6  lea     r9, [rbp+57h+var_80]
0x180046dca  mov     r8, rbx
0x180046dcd  mov     rcx, rsi
0x180046dd0  mov     rax, rdi
0x180046dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dd8  mov     ebx, eax
0x180046dda  test    eax, eax
0x180046ddc  jns     short loc_180046DE5
0x180046dde  mov     edx, 7Eh ; '~'
0x180046de3  jmp     short loc_180046D74
0x180046de5  mov     rbx, [rbp+57h+var_68]
0x180046de9  test    rbx, rbx
0x180046dec  jz      short loc_180046E3D
0x180046dee  mov     rsi, [rbp+57h+var_50]
0x180046df2  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x180046df9  mov     r9d, 11h; unsigned int
0x180046dff  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180046e03  mov     rax, [rsi]
0x180046e06  lea     r8d, [r9+1]; unsigned int
0x180046e0a  mov     [rbp+57h+var_28], r14
0x180046e0e  mov     rdi, [rax+50h]
0x180046e12  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046e17  mov     rdx, [rbp+57h+var_28]
0x180046e1b  lea     r9, [rbp+57h+var_80]
0x180046e1f  mov     r8, rbx
0x180046e22  mov     rcx, rsi
0x180046e25  mov     rax, rdi
0x180046e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e2d  mov     ebx, eax
0x180046e2f  test    eax, eax
0x180046e31  jns     short loc_180046E3D
0x180046e33  mov     edx, 82h
0x180046e38  jmp     loc_180046D74
0x180046e3d  lea     rcx, [rbp+57h+var_58]
0x180046e41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e46  lea     rcx, [rbp+57h+var_60]
0x180046e4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e4f  lea     rcx, [rbp+57h+var_68]
0x180046e53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e58  mov     rcx, [rbp+57h+var_70]; string
0x180046e5c  call    cs:__imp_WindowsDeleteString
0x180046e62  mov     rcx, [rbp+57h+string]; string
0x180046e66  mov     [rbp+57h+var_70], r14
0x180046e6a  call    cs:__imp_WindowsDeleteString
0x180046e70  mov     ebx, r14d
0x180046e73  mov     [rbp+57h+string], r14
0x180046e77  lea     rcx, [rbp+57h+var_48]
0x180046e7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e80  lea     rcx, [rbp+57h+var_50]
0x180046e84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046e89  mov     eax, ebx
0x180046e8b  mov     rcx, [rbp+57h+var_20]
0x180046e8f  xor     rcx, rsp; StackCookie
0x180046e92  call    __security_check_cookie
0x180046e97  lea     r11, [rsp+0B0h+var_10]
0x180046e9f  mov     rbx, [r11+30h]
0x180046ea3  mov     rsi, [r11+38h]
0x180046ea7  mov     rsp, r11
0x180046eaa  pop     r14
0x180046eac  pop     rdi
0x180046ead  pop     rbp
0x180046eae  retn
```

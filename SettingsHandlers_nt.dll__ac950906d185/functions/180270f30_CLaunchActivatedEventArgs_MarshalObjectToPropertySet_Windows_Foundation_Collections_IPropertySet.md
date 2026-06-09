# CLaunchActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180270f30`
- end: `0x180271354`
- name: `?MarshalObjectToPropertySet@CLaunchActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CLaunchActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18002012c`
- `0x180221a84`
- `0x180224af4`
- `0x180225a2c`
- `0x180270f30`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802710c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802712f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802710c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802712f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180271308`

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
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v47);
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
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
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
      Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
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
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
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
0x180270f30  mov     [rsp-8+arg_10], rbx
0x180270f35  mov     [rsp-8+arg_18], rsi
0x180270f3a  push    rbp
0x180270f3b  push    rdi
0x180270f3c  push    r14
0x180270f3e  lea     rbp, [rsp-47h]
0x180270f43  sub     rsp, 0A0h
0x180270f4a  mov     rax, cs:__security_cookie
0x180270f51  xor     rax, rsp
0x180270f54  mov     [rbp+57h+var_20], rax
0x180270f58  mov     rsi, rcx
0x180270f5b  mov     rdi, rdx
0x180270f5e  add     rcx, 0FFFFFFFFFFFFFF00h; this
0x180270f65  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithPrelaunchAndViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithPrelaunchAndViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180270f6a  xor     r14d, r14d
0x180270f6d  mov     ebx, eax
0x180270f6f  test    eax, eax
0x180270f71  jns     short loc_180270F8F
0x180270f73  mov     rcx, [rbp+5Fh]; this
0x180270f77  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180270f7e  mov     r9d, eax; char *
0x180270f81  lea     edx, [r14+64h]; void *
0x180270f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270f8a  jmp     loc_18027132D
0x180270f8f  mov     rax, [rdi]
0x180270f92  lea     rcx, [rbp+57h+var_50]
0x180270f96  mov     [rbp+57h+var_50], r14
0x180270f9a  mov     [rbp+57h+var_48], r14
0x180270f9e  mov     rbx, [rax]
0x180270fa1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180270fa6  lea     r8, [rbp+57h+var_50]
0x180270faa  mov     rcx, rdi
0x180270fad  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180270fb4  mov     rax, rbx
0x180270fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270fbc  mov     ebx, eax
0x180270fbe  test    eax, eax
0x180270fc0  jns     short loc_180270FC9
0x180270fc2  mov     edx, 69h ; 'i'
0x180270fc7  jmp     short loc_180270FFF
0x180270fc9  mov     r9d, 20h ; ' '; unsigned int
0x180270fcf  mov     [rbp+57h+var_28], r14
0x180270fd3  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180270fda  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180270fde  lea     r8d, [r9+1]; unsigned int
0x180270fe2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180270fe7  mov     rcx, [rbp+57h+var_28]
0x180270feb  lea     rdx, [rbp+57h+var_48]
0x180270fef  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180270ff4  mov     ebx, eax
0x180270ff6  test    eax, eax
0x180270ff8  jns     short loc_180271017
0x180270ffa  mov     edx, 6Ah ; 'j'; void *
0x180270fff  mov     rcx, [rbp+5Fh]; this
0x180271003  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18027100a  mov     r9d, eax; char *
0x18027100d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271012  jmp     loc_18027131B
0x180271017  lea     rdi, [rsi-10h]
0x18027101b  mov     [rbp+57h+string], r14
0x18027101f  mov     rax, [rdi]
0x180271022  xor     ecx, ecx; string
0x180271024  mov     rbx, [rax+30h]
0x180271028  call    cs:__imp_WindowsDeleteString
0x18027102f  nop     dword ptr [rax+rax+00h]
0x180271034  lea     rdx, [rbp+57h+string]
0x180271038  mov     [rbp+57h+string], r14
0x18027103c  mov     rcx, rdi
0x18027103f  mov     rax, rbx
0x180271042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180271047  mov     ebx, eax
0x180271049  test    eax, eax
0x18027104b  jns     short loc_18027107A
0x18027104d  mov     rcx, [rbp+5Fh]; this
0x180271051  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180271058  mov     r9d, eax; char *
0x18027105b  mov     edx, 6Eh ; 'n'; void *
0x180271060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271065  mov     rcx, [rbp+57h+string]; string
0x180271069  call    cs:__imp_WindowsDeleteString
0x180271070  nop     dword ptr [rax+rax+00h]
0x180271075  jmp     loc_180271317
0x18027107a  mov     rax, [rdi]
0x18027107d  xor     ecx, ecx; string
0x18027107f  mov     [rbp+57h+var_70], r14
0x180271083  mov     rbx, [rax+38h]
0x180271087  call    cs:__imp_WindowsDeleteString
0x18027108e  nop     dword ptr [rax+rax+00h]
0x180271093  lea     rdx, [rbp+57h+var_70]
0x180271097  mov     [rbp+57h+var_70], r14
0x18027109b  mov     rcx, rdi
0x18027109e  mov     rax, rbx
0x1802710a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802710a6  mov     ebx, eax
0x1802710a8  test    eax, eax
0x1802710aa  jns     short loc_1802710DA
0x1802710ac  mov     rcx, [rbp+5Fh]; this
0x1802710b0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x1802710b7  mov     r9d, eax; char *
0x1802710ba  mov     edx, 71h ; 'q'; void *
0x1802710bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802710c4  mov     rcx, [rbp+57h+var_70]; string
0x1802710c8  call    cs:__imp_WindowsDeleteString
0x1802710cf  nop     dword ptr [rax+rax+00h]
0x1802710d4  mov     [rbp+57h+var_70], r14
0x1802710d8  jmp     short loc_180271065
0x1802710da  mov     rax, [rsi-8]
0x1802710de  lea     rcx, [rbp+57h+var_68]
0x1802710e2  mov     [rbp+57h+var_68], r14
0x1802710e6  mov     rbx, [rax+30h]
0x1802710ea  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1802710ef  lea     rdx, [rbp+57h+var_68]
0x1802710f3  mov     rax, rbx
0x1802710f6  lea     rcx, [rsi-8]
0x1802710fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802710ff  mov     ebx, eax
0x180271101  test    eax, eax
0x180271103  jns     short loc_180271128
0x180271105  mov     rcx, [rbp+5Fh]; this
0x180271109  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180271110  mov     r9d, eax; char *
0x180271113  mov     edx, 74h ; 't'; void *
0x180271118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027111d  lea     rcx, [rbp+57h+var_68]
0x180271121  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180271126  jmp     short loc_1802710C4
0x180271128  mov     rdi, [rbp+57h+var_48]
0x18027112c  lea     rcx, [rbp+57h+var_60]
0x180271130  mov     [rbp+57h+var_60], r14
0x180271134  mov     rax, [rdi]
0x180271137  mov     rbx, [rax+90h]
0x18027113e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180271143  mov     rdx, [rbp+57h+string]
0x180271147  lea     r8, [rbp+57h+var_60]
0x18027114b  mov     rcx, rdi
0x18027114e  mov     rax, rbx
0x180271151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180271156  mov     ebx, eax
0x180271158  test    eax, eax
0x18027115a  jns     short loc_18027117F
0x18027115c  mov     edx, 78h ; 'x'; void *
0x180271161  mov     rcx, [rbp+5Fh]; this
0x180271165  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x18027116c  mov     r9d, eax; char *
0x18027116f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271174  lea     rcx, [rbp+57h+var_60]
0x180271178  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18027117d  jmp     short loc_18027111D
0x18027117f  mov     rsi, [rbp+57h+var_50]
0x180271183  lea     rdx, aArguments; "Arguments"
0x18027118a  mov     rbx, [rbp+57h+var_60]
0x18027118e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180271192  mov     [rbp+57h+var_80], r14b
0x180271196  mov     r9d, 9; unsigned int
0x18027119c  mov     rax, [rsi]
0x18027119f  mov     [rbp+57h+var_28], r14
0x1802711a3  lea     r8d, [r9+1]; unsigned int
0x1802711a7  mov     rdi, [rax+50h]
0x1802711ab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802711b0  mov     rdx, [rbp+57h+var_28]
0x1802711b4  lea     r9, [rbp+57h+var_80]
0x1802711b8  mov     r8, rbx
0x1802711bb  mov     rcx, rsi
0x1802711be  mov     rax, rdi
0x1802711c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802711c6  mov     ebx, eax
0x1802711c8  test    eax, eax
0x1802711ca  jns     short loc_1802711D3
0x1802711cc  mov     edx, 7Ah ; 'z'
0x1802711d1  jmp     short loc_180271161
0x1802711d3  mov     rdi, [rbp+57h+var_48]
0x1802711d7  lea     rcx, [rbp+57h+var_58]
0x1802711db  mov     [rbp+57h+var_58], r14
0x1802711df  mov     rax, [rdi]
0x1802711e2  mov     rbx, [rax+90h]
0x1802711e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802711ee  mov     rdx, [rbp+57h+var_70]
0x1802711f2  lea     r8, [rbp+57h+var_58]
0x1802711f6  mov     rcx, rdi
0x1802711f9  mov     rax, rbx
0x1802711fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180271201  mov     ebx, eax
0x180271203  test    eax, eax
0x180271205  jns     short loc_18027122D
0x180271207  mov     edx, 7Dh ; '}'; void *
0x18027120c  mov     rcx, [rbp+5Fh]; this
0x180271210  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\lib\\activationevent"...
0x180271217  mov     r9d, eax; char *
0x18027121a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027121f  lea     rcx, [rbp+57h+var_58]
0x180271223  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180271228  jmp     loc_180271174
0x18027122d  mov     rsi, [rbp+57h+var_50]
0x180271231  lea     rdx, aTileid; "TileId"
0x180271238  mov     rbx, [rbp+57h+var_58]
0x18027123c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180271240  mov     r9d, 6; unsigned int
0x180271246  mov     rax, [rsi]
0x180271249  mov     [rbp+57h+var_28], r14
0x18027124d  lea     r8d, [r9+1]; unsigned int
0x180271251  mov     rdi, [rax+50h]
0x180271255  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18027125a  mov     rdx, [rbp+57h+var_28]
0x18027125e  lea     r9, [rbp+57h+var_80]
0x180271262  mov     r8, rbx
0x180271265  mov     rcx, rsi
0x180271268  mov     rax, rdi
0x18027126b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180271270  mov     ebx, eax
0x180271272  test    eax, eax
0x180271274  jns     short loc_18027127D
0x180271276  mov     edx, 7Eh ; '~'
0x18027127b  jmp     short loc_18027120C
0x18027127d  mov     rbx, [rbp+57h+var_68]
0x180271281  test    rbx, rbx
0x180271284  jz      short loc_1802712D5
0x180271286  mov     rsi, [rbp+57h+var_50]
0x18027128a  lea     rdx, aTileactivatedi; "TileActivatedInfo"
0x180271291  mov     r9d, 11h; unsigned int
0x180271297  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18027129b  mov     rax, [rsi]
0x18027129e  lea     r8d, [r9+1]; unsigned int
0x1802712a2  mov     [rbp+57h+var_28], r14
0x1802712a6  mov     rdi, [rax+50h]
0x1802712aa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802712af  mov     rdx, [rbp+57h+var_28]
0x1802712b3  lea     r9, [rbp+57h+var_80]
0x1802712b7  mov     r8, rbx
0x1802712ba  mov     rcx, rsi
0x1802712bd  mov     rax, rdi
0x1802712c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802712c5  mov     ebx, eax
0x1802712c7  test    eax, eax
0x1802712c9  jns     short loc_1802712D5
0x1802712cb  mov     edx, 82h
0x1802712d0  jmp     loc_18027120C
0x1802712d5  lea     rcx, [rbp+57h+var_58]
0x1802712d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802712de  lea     rcx, [rbp+57h+var_60]
0x1802712e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802712e7  lea     rcx, [rbp+57h+var_68]
0x1802712eb  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1802712f0  mov     rcx, [rbp+57h+var_70]; string
0x1802712f4  call    cs:__imp_WindowsDeleteString
0x1802712fb  nop     dword ptr [rax+rax+00h]
0x180271300  mov     rcx, [rbp+57h+string]; string
0x180271304  mov     [rbp+57h+var_70], r14
0x180271308  call    cs:__imp_WindowsDeleteString
0x18027130f  nop     dword ptr [rax+rax+00h]
0x180271314  mov     ebx, r14d
0x180271317  mov     [rbp+57h+string], r14
0x18027131b  lea     rcx, [rbp+57h+var_48]
0x18027131f  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x180271324  lea     rcx, [rbp+57h+var_50]
0x180271328  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18027132d  mov     eax, ebx
0x18027132f  mov     rcx, [rbp+57h+var_20]
0x180271333  xor     rcx, rsp; StackCookie
0x180271336  call    __security_check_cookie
0x18027133b  lea     r11, [rsp+0B0h+var_10]
0x180271343  mov     rbx, [r11+30h]
0x180271347  mov     rsi, [r11+38h]
0x18027134b  mov     rsp, r11
0x18027134e  pop     r14
0x180271350  pop     rdi
0x180271351  pop     rbp
0x180271352  retn
```

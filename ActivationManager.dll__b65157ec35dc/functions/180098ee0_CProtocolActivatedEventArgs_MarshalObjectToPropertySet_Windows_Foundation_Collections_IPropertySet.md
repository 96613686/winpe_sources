# CProtocolActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180098ee0`
- end: `0x180099237`
- name: `?MarshalObjectToPropertySet@CProtocolActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(CProtocolActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x1800217f8`
- `0x180031540`
- `0x18003eed0`
- `0x18003f158`
- `0x18005ae90`
- `0x180098ee0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800991e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800991e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180099040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180099040`

## string_xrefs

- `0x180098f24`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x180098fb0`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x180098ff2`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x180099055`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x180099166`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`

## pseudocode

```c
__int64 __fastcall CProtocolActivatedEventArgs::MarshalObjectToPropertySet(
        CProtocolActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  HSTRING v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdx
  _QWORD *v14; // rsi
  void *v15; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(_QWORD *, __int64, void *, _BYTE *); // rdi
  __int64 v18; // rbx
  _QWORD *v19; // rsi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  _QWORD *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  int v31; // [rsp+20h] [rbp-29h]
  _BYTE v32[8]; // [rsp+30h] [rbp-19h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-11h] BYREF
  void *v34; // [rsp+40h] [rbp-9h] BYREF
  __int64 v35; // [rsp+48h] [rbp-1h] BYREF
  __int64 v36; // [rsp+50h] [rbp+7h] BYREF
  _QWORD *v37; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v38; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v40; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
         (CProtocolActivatedEventArgs *)((char *)this + 48),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v37 = 0;
    v38 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v37);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 96;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
        (const char *)(unsigned int)v8,
        v31);
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      return v5;
    }
    v40 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v40,
           (__int64)&v38);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 97;
      goto LABEL_7;
    }
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    v10 = Microsoft::WRL::AgileRef::InternalResolve(
            (CProtocolActivatedEventArgs *)((char *)this + 296),
            &GUID_9e365e57_48b2_4160_956f_c7385120bbfc,
            &v34);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
        (const char *)(unsigned int)v10,
        v31);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
      goto LABEL_26;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    v35 = 0;
    newString = 0;
    WindowsDeleteString(0);
    v11 = (HSTRING)*((_QWORD *)this + 38);
    newString = 0;
    v12 = WindowsDuplicateString(v11, &newString);
    v5 = v12;
    if ( v12 >= 0 )
    {
      v14 = v37;
      v15 = v34;
      v32[0] = 0;
      v16 = *v37;
      v40 = 0;
      v17 = *(__int64 (__fastcall **)(_QWORD *, __int64, void *, _BYTE *))(v16 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Uri", 4u, 3u);
      v12 = v17(v14, v40, v15, v32);
      v5 = v12;
      if ( v12 >= 0 )
      {
        v18 = v35;
        if ( !v35
          || (v19 = v37,
              v20 = *v37,
              v40 = 0,
              v21 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v20 + 80),
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Data", 5u, 4u),
              v12 = v21(v19, v40, v18, v32),
              v5 = v12,
              v12 >= 0) )
        {
          v22 = v38;
          v36 = 0;
          v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v38 + 144LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
          v24 = v23(v22, newString, &v36);
          v5 = v24;
          if ( v24 >= 0 )
          {
            v26 = v37;
            v27 = v36;
            v28 = *v37;
            v40 = 0;
            v29 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v28 + 80);
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"CallerPackageFamilyName",
              0x18u,
              0x17u);
            v24 = v29(v26, v40, v27, v32);
            v5 = v24;
            if ( v24 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
              WindowsDeleteString(newString);
              newString = 0;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
              v5 = 0;
              goto LABEL_26;
            }
            v25 = 121;
          }
          else
          {
            v25 = 120;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
            (const char *)(unsigned int)v24,
            v31);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
          goto LABEL_14;
        }
        v13 = 116;
      }
      else
      {
        v13 = 112;
      }
    }
    else
    {
      v13 = 108;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
      (const char *)(unsigned int)v12,
      v31);
LABEL_14:
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
    (const char *)(unsigned int)v4,
    v31);
  return v5;
}

```

## disassembly

```asm
0x180098ee0  mov     [rsp-8+arg_10], rbx
0x180098ee5  mov     [rsp-8+arg_18], rsi
0x180098eea  push    rbp
0x180098eeb  push    rdi
0x180098eec  push    r14
0x180098eee  lea     rbp, [rsp-47h]
0x180098ef3  sub     rsp, 90h
0x180098efa  mov     rax, cs:__security_cookie
0x180098f01  xor     rax, rsp
0x180098f04  mov     [rbp+57h+var_18], rax
0x180098f08  mov     rdi, rcx
0x180098f0b  mov     rsi, rdx
0x180098f0e  add     rcx, 30h ; '0'; this
0x180098f12  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180098f17  xor     r14d, r14d
0x180098f1a  mov     ebx, eax
0x180098f1c  test    eax, eax
0x180098f1e  jns     short loc_180098F3C
0x180098f20  mov     rcx, [rbp+5Fh]; this
0x180098f24  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x180098f2b  mov     r9d, eax; char *
0x180098f2e  lea     edx, [r14+5Bh]; void *
0x180098f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098f37  jmp     loc_180099211
0x180098f3c  mov     rax, [rsi]
0x180098f3f  lea     rcx, [rbp+57h+var_48]
0x180098f43  mov     [rbp+57h+var_48], r14
0x180098f47  mov     [rbp+57h+var_40], r14
0x180098f4b  mov     rbx, [rax]
0x180098f4e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098f53  lea     r8, [rbp+57h+var_48]
0x180098f57  mov     rcx, rsi
0x180098f5a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180098f61  mov     rax, rbx
0x180098f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f69  mov     ebx, eax
0x180098f6b  test    eax, eax
0x180098f6d  jns     short loc_180098F76
0x180098f6f  mov     edx, 60h ; '`'
0x180098f74  jmp     short loc_180098FAC
0x180098f76  mov     r9d, 20h ; ' '; unsigned int
0x180098f7c  mov     [rbp+57h+var_20], r14
0x180098f80  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180098f87  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180098f8b  lea     r8d, [r9+1]; unsigned int
0x180098f8f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180098f94  mov     rcx, [rbp+57h+var_20]
0x180098f98  lea     rdx, [rbp+57h+var_40]
0x180098f9c  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x180098fa1  mov     ebx, eax
0x180098fa3  test    eax, eax
0x180098fa5  jns     short loc_180098FC4
0x180098fa7  mov     edx, 61h ; 'a'; void *
0x180098fac  mov     rcx, [rbp+5Fh]; this
0x180098fb0  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x180098fb7  mov     r9d, eax; char *
0x180098fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098fbf  jmp     loc_1800991FF
0x180098fc4  lea     rcx, [rbp+57h+var_60]
0x180098fc8  mov     [rbp+57h+var_60], r14
0x180098fcc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180098fd1  lea     rcx, [rdi+128h]; this
0x180098fd8  lea     r8, [rbp+57h+var_60]; void **
0x180098fdc  lea     rdx, _GUID_9e365e57_48b2_4160_956f_c7385120bbfc; struct _GUID *
0x180098fe3  call    ?InternalResolve@AgileRef@WRL@Microsoft@@IEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::AgileRef::InternalResolve(_GUID const &,void * *)
0x180098fe8  mov     ebx, eax
0x180098fea  test    eax, eax
0x180098fec  jns     short loc_180099014
0x180098fee  mov     rcx, [rbp+5Fh]; this
0x180098ff2  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x180098ff9  mov     r9d, eax; char *
0x180098ffc  mov     edx, 65h ; 'e'; void *
0x180099001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099006  lea     rcx, [rbp+57h+var_60]
0x18009900a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009900f  jmp     loc_1800991FF
0x180099014  lea     rcx, [rbp+57h+var_58]
0x180099018  mov     [rbp+57h+var_58], r14
0x18009901c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099021  xor     ecx, ecx; string
0x180099023  mov     [rbp+57h+var_58], r14
0x180099027  mov     [rbp+57h+newString], r14
0x18009902b  call    cs:__imp_WindowsDeleteString
0x180099031  mov     rcx, [rdi+130h]; string
0x180099038  lea     rdx, [rbp+57h+newString]; newString
0x18009903c  mov     [rbp+57h+newString], r14
0x180099040  call    cs:__imp_WindowsDuplicateString
0x180099046  mov     ebx, eax
0x180099048  test    eax, eax
0x18009904a  jns     short loc_18009907D
0x18009904c  mov     edx, 6Ch ; 'l'; void *
0x180099051  mov     rcx, [rbp+5Fh]; this
0x180099055  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x18009905c  mov     r9d, eax; char *
0x18009905f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099064  mov     rcx, [rbp+57h+newString]; string
0x180099068  call    cs:__imp_WindowsDeleteString
0x18009906e  lea     rcx, [rbp+57h+var_58]
0x180099072  mov     [rbp+57h+newString], r14
0x180099076  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009907b  jmp     short loc_180099006
0x18009907d  mov     rsi, [rbp+57h+var_48]
0x180099081  lea     rdx, aUri; "Uri"
0x180099088  mov     rbx, [rbp+57h+var_60]
0x18009908c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180099090  mov     [rbp+57h+var_70], r14b
0x180099094  mov     r9d, 3; unsigned int
0x18009909a  mov     rax, [rsi]
0x18009909d  mov     [rbp+57h+var_20], r14
0x1800990a1  lea     r8d, [r9+1]; unsigned int
0x1800990a5  mov     rdi, [rax+50h]
0x1800990a9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800990ae  mov     rdx, [rbp+57h+var_20]
0x1800990b2  lea     r9, [rbp+57h+var_70]
0x1800990b6  mov     r8, rbx
0x1800990b9  mov     rcx, rsi
0x1800990bc  mov     rax, rdi
0x1800990bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990c4  mov     ebx, eax
0x1800990c6  test    eax, eax
0x1800990c8  jns     short loc_1800990D1
0x1800990ca  mov     edx, 70h ; 'p'
0x1800990cf  jmp     short loc_180099051
0x1800990d1  mov     rbx, [rbp+57h+var_58]
0x1800990d5  test    rbx, rbx
0x1800990d8  jz      short loc_180099129
0x1800990da  mov     rsi, [rbp+57h+var_48]
0x1800990de  lea     rdx, aData; "Data"
0x1800990e5  mov     r9d, 4; unsigned int
0x1800990eb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800990ef  mov     rax, [rsi]
0x1800990f2  lea     r8d, [r9+1]; unsigned int
0x1800990f6  mov     [rbp+57h+var_20], r14
0x1800990fa  mov     rdi, [rax+50h]
0x1800990fe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099103  mov     rdx, [rbp+57h+var_20]
0x180099107  lea     r9, [rbp+57h+var_70]
0x18009910b  mov     r8, rbx
0x18009910e  mov     rcx, rsi
0x180099111  mov     rax, rdi
0x180099114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099119  mov     ebx, eax
0x18009911b  test    eax, eax
0x18009911d  jns     short loc_180099129
0x18009911f  mov     edx, 74h ; 't'
0x180099124  jmp     loc_180099051
0x180099129  mov     rdi, [rbp+57h+var_40]
0x18009912d  lea     rcx, [rbp+57h+var_50]
0x180099131  mov     [rbp+57h+var_50], r14
0x180099135  mov     rax, [rdi]
0x180099138  mov     rbx, [rax+90h]
0x18009913f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099144  mov     rdx, [rbp+57h+newString]
0x180099148  lea     r8, [rbp+57h+var_50]
0x18009914c  mov     rcx, rdi
0x18009914f  mov     rax, rbx
0x180099152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099157  mov     ebx, eax
0x180099159  test    eax, eax
0x18009915b  jns     short loc_180099183
0x18009915d  mov     edx, 78h ; 'x'; void *
0x180099162  mov     rcx, [rbp+5Fh]; this
0x180099166  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\lib\\activationevent"...
0x18009916d  mov     r9d, eax; char *
0x180099170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099175  lea     rcx, [rbp+57h+var_50]
0x180099179  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009917e  jmp     loc_180099064
0x180099183  mov     rsi, [rbp+57h+var_48]
0x180099187  lea     rdx, aCallerpackagef; "CallerPackageFamilyName"
0x18009918e  mov     rbx, [rbp+57h+var_50]
0x180099192  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180099196  mov     r9d, 17h; unsigned int
0x18009919c  mov     rax, [rsi]
0x18009919f  mov     [rbp+57h+var_20], r14
0x1800991a3  lea     r8d, [r9+1]; unsigned int
0x1800991a7  mov     rdi, [rax+50h]
0x1800991ab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800991b0  mov     rdx, [rbp+57h+var_20]
0x1800991b4  lea     r9, [rbp+57h+var_70]
0x1800991b8  mov     r8, rbx
0x1800991bb  mov     rcx, rsi
0x1800991be  mov     rax, rdi
0x1800991c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991c6  mov     ebx, eax
0x1800991c8  test    eax, eax
0x1800991ca  jns     short loc_1800991D3
0x1800991cc  mov     edx, 79h ; 'y'
0x1800991d1  jmp     short loc_180099162
0x1800991d3  lea     rcx, [rbp+57h+var_50]
0x1800991d7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800991dc  mov     rcx, [rbp+57h+newString]; string
0x1800991e0  call    cs:__imp_WindowsDeleteString
0x1800991e6  lea     rcx, [rbp+57h+var_58]
0x1800991ea  mov     [rbp+57h+newString], r14
0x1800991ee  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800991f3  lea     rcx, [rbp+57h+var_60]
0x1800991f7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800991fc  mov     ebx, r14d
0x1800991ff  lea     rcx, [rbp+57h+var_40]
0x180099203  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099208  lea     rcx, [rbp+57h+var_48]
0x18009920c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099211  mov     eax, ebx
0x180099213  mov     rcx, [rbp+57h+var_18]
0x180099217  xor     rcx, rsp; StackCookie
0x18009921a  call    __security_check_cookie
0x18009921f  lea     r11, [rsp+0A0h+var_10]
0x180099227  mov     rbx, [r11+30h]
0x18009922b  mov     rsi, [r11+38h]
0x18009922f  mov     rsp, r11
0x180099232  pop     r14
0x180099234  pop     rdi
0x180099235  pop     rbp
0x180099236  retn
```

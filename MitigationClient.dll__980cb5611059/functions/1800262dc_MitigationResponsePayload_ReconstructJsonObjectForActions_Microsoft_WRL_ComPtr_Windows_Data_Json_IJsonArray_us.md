# MitigationResponsePayload::ReconstructJsonObjectForActions(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,ushort * *)

- ea: `0x1800262dc`
- end: `0x180026669`
- name: `?ReconstructJsonObjectForActions@MitigationResponsePayload@@AEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAPEAG@Z`
- size: `909`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800254b0`

## callees

- `0x18000a6e0`
- `0x18001055c`
- `0x18001208c`
- `0x180024d34`
- `0x180024d80`
- `0x180024e70`
- `0x180025130`
- `0x1800253bc`
- `0x1800262dc`
- `0x1800266c8`
- `0x180026930`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026383`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002636a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002636a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026587`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800263a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800263a4`

## string_xrefs

- `0x180026363`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MitigationResponsePayload::ReconstructJsonObjectForActions(
        __int64 a1,
        const unsigned __int16 *a2,
        STRSAFE_LPWSTR *a3)
{
  __int64 *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64); // rdi
  __int64 v20; // rbx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64); // rdi
  __int64 v23; // rbx
  int v24; // eax
  int v25; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // rcx
  const unsigned __int16 *v28; // r12
  unsigned __int64 v29; // rbx
  int v30; // edi
  int v32; // [rsp+20h] [rbp-59h]
  unsigned __int64 *v33; // [rsp+28h] [rbp-51h]
  __int64 v34; // [rsp+40h] [rbp-39h] BYREF
  __int64 v35; // [rsp+48h] [rbp-31h] BYREF
  __int64 v36; // [rsp+50h] [rbp-29h] BYREF
  __int64 v37; // [rsp+58h] [rbp-21h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp-19h] BYREF
  HSTRING v39[2]; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v39[1] = (HSTRING)a2;
  v38 = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])a2);
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v6, &v38);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v34 = 0;
    if ( WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v9 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    ActivationFactory = RoGetActivationFactory(v9, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v34);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v32);
LABEL_7:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
      goto LABEL_30;
    }
    v35 = 0;
    v11 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a2;
    v12 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    v13 = v12(v11, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v35);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
        (const char *)(unsigned int)v13,
        v32);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
      goto LABEL_7;
    }
    v36 = 0;
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v34 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&string,
      *(const unsigned __int16 **)(a1 + 48));
    v16 = v15(v14, string, &v36);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 244;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
        (const char *)(unsigned int)v16,
        v32);
LABEL_14:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      goto LABEL_10;
    }
    v18 = v38;
    v19 = (*v38)[7];
    v20 = v36;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&string,
      MitigationResponsePayload::s_instanceId);
    v19(v18, (GUID *)string, v20);
    v21 = v38;
    v22 = (*v38)[7];
    v23 = v35;
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)&string,
      MitigationResponsePayload::s_serviceDrivenActions);
    v16 = v22(v21, (GUID *)string, v23);
    v8 = v16;
    if ( v16 < 0 )
    {
      v17 = 248;
      goto LABEL_13;
    }
    v37 = 0;
    v24 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
            &v38,
            (__int64)&v37);
    v8 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
        (const char *)(unsigned int)v24,
        v32);
LABEL_19:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      goto LABEL_14;
    }
    v39[0] = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 56LL))(v37, v39);
    v8 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
        (const char *)(unsigned int)v25,
        v32);
      Windows::Internal::String::~String((Windows::Internal::String *)v39);
      goto LABEL_19;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v39[0], 0);
    v28 = StringRawBuffer;
    v29 = -1;
    do
      ++v29;
    while ( StringRawBuffer[v29] );
    *a3 = 0;
    if ( v29 + 1 < v29 )
    {
      v30 = -2147024362;
    }
    else
    {
      v30 = _AllocArray<unsigned short,CTCoAllocPolicy>(v27, 0, v29 + 1, a3);
      if ( v30 >= 0 )
      {
        StringCchCopyNExW(*a3, v29 + 1, v28, v29, 0, v33, 0x300u);
LABEL_29:
        Windows::Internal::String::~String((Windows::Internal::String *)v39);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
        v8 = v30;
        goto LABEL_30;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
      (const char *)(unsigned int)v30,
      v32);
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEA,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\mitigationresponsepayload.cpp",
    (const char *)(unsigned int)v7,
    v32);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  return v8;
}

```

## disassembly

```asm
0x1800262dc  mov     [rsp-8+arg_18], rbx
0x1800262e1  push    rbp
0x1800262e2  push    rsi
0x1800262e3  push    rdi
0x1800262e4  push    r12
0x1800262e6  push    r13
0x1800262e8  push    r14
0x1800262ea  push    r15
0x1800262ec  lea     rbp, [rsp-27h]
0x1800262f1  sub     rsp, 0A0h
0x1800262f8  mov     rax, cs:__security_cookie
0x1800262ff  xor     rax, rsp
0x180026302  mov     [rbp+57h+var_38], rax
0x180026306  mov     r14, r8
0x180026309  mov     r15, rdx
0x18002630c  mov     rsi, rcx
0x18002630f  mov     [rbp+57h+var_60], rdx
0x180026313  xor     r13d, r13d
0x180026316  mov     [rbp+57h+var_70], r13
0x18002631a  lea     rcx, [rbp+57h+string]; string
0x18002631e  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180026323  lea     rdx, [rbp+57h+var_70]
0x180026327  mov     rcx, [rax]
0x18002632a  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18002632f  mov     ebx, eax
0x180026331  test    eax, eax
0x180026333  jns     short loc_180026352
0x180026335  mov     rcx, [rbp+5Fh]; this
0x180026339  mov     r9d, eax; char *
0x18002633c  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180026343  mov     edx, 0EAh; void *
0x180026348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002634d  jmp     loc_18002662E
0x180026352  mov     [rbp+57h+var_90], r13
0x180026356  lea     r9, [rbp+57h+string]; string
0x18002635a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002635e  mov     edx, 1Bh; length
0x180026363  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18002636a  call    cs:__imp_WindowsCreateStringReference
0x180026370  test    eax, eax
0x180026372  jns     short loc_180026389
0x180026374  xor     r9d, r9d; lpArguments
0x180026377  xor     r8d, r8d; nNumberOfArguments
0x18002637a  lea     edx, [r9+1]; dwExceptionFlags
0x18002637e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026383  call    cs:__imp_RaiseException
0x180026389  mov     rbx, [rbp+57h+string]
0x18002638d  lea     rcx, [rbp+57h+var_90]
0x180026391  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026396  lea     r8, [rbp+57h+var_90]
0x18002639a  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800263a1  mov     rcx, rbx
0x1800263a4  call    cs:__imp_RoGetActivationFactory
0x1800263aa  mov     ebx, eax
0x1800263ac  test    eax, eax
0x1800263ae  jns     short loc_1800263D7
0x1800263b0  mov     rcx, [rbp+5Fh]; this
0x1800263b4  mov     r9d, eax; char *
0x1800263b7  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800263be  mov     edx, 0EDh; void *
0x1800263c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263c8  nop
0x1800263c9  lea     rcx, [rbp+57h+var_90]
0x1800263cd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800263d2  jmp     loc_18002662E
0x1800263d7  mov     [rbp+57h+var_88], r13
0x1800263db  mov     rdi, [r15]
0x1800263de  mov     rax, [rdi]
0x1800263e1  mov     rbx, [rax]
0x1800263e4  lea     rcx, [rbp+57h+var_88]
0x1800263e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800263ed  lea     r8, [rbp+57h+var_88]
0x1800263f1  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800263f8  mov     rcx, rdi
0x1800263fb  mov     rax, rbx
0x1800263fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026403  mov     ebx, eax
0x180026405  test    eax, eax
0x180026407  jns     short loc_18002642D
0x180026409  mov     rcx, [rbp+5Fh]; this
0x18002640d  mov     r9d, eax; char *
0x180026410  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180026417  mov     edx, 0F0h; void *
0x18002641c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026421  nop
0x180026422  lea     rcx, [rbp+57h+var_88]
0x180026426  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002642b  jmp     short loc_1800263C9
0x18002642d  mov     [rbp+57h+var_80], r13
0x180026431  mov     rdi, [rbp+57h+var_90]
0x180026435  mov     rax, [rdi]
0x180026438  mov     rbx, [rax+50h]
0x18002643c  lea     rcx, [rbp+57h+var_80]
0x180026440  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026445  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180026449  lea     rcx, [rbp+57h+string]; this
0x18002644d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180026452  lea     r8, [rbp+57h+var_80]
0x180026456  mov     rdx, [rbp+57h+string]
0x18002645a  mov     rcx, rdi
0x18002645d  mov     rax, rbx
0x180026460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026465  mov     ebx, eax
0x180026467  test    eax, eax
0x180026469  jns     short loc_18002648F
0x18002646b  mov     edx, 0F4h; void *
0x180026470  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180026477  mov     r9d, eax; char *
0x18002647a  mov     rcx, [rbp+5Fh]; this
0x18002647e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026483  nop
0x180026484  lea     rcx, [rbp+57h+var_80]
0x180026488  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002648d  jmp     short loc_180026422
0x18002648f  mov     rsi, [rbp+57h+var_70]
0x180026493  mov     rax, [rsi]
0x180026496  mov     rdi, [rax+38h]
0x18002649a  mov     rbx, [rbp+57h+var_80]
0x18002649e  mov     rdx, cs:?s_instanceId@MitigationResponsePayload@@0QEBGEB; unsigned __int16 *
0x1800264a5  lea     rcx, [rbp+57h+string]; this
0x1800264a9  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800264ae  mov     r8, rbx
0x1800264b1  mov     rdx, [rbp+57h+string]
0x1800264b5  mov     rcx, rsi
0x1800264b8  mov     rax, rdi
0x1800264bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c0  mov     rsi, [rbp+57h+var_70]
0x1800264c4  mov     rax, [rsi]
0x1800264c7  mov     rdi, [rax+38h]
0x1800264cb  mov     rbx, [rbp+57h+var_88]
0x1800264cf  mov     rdx, cs:?s_serviceDrivenActions@MitigationResponsePayload@@0QEBGEB; unsigned __int16 *
0x1800264d6  lea     rcx, [rbp+57h+string]; this
0x1800264da  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800264df  mov     r8, rbx
0x1800264e2  mov     rdx, [rbp+57h+string]
0x1800264e6  mov     rcx, rsi
0x1800264e9  mov     rax, rdi
0x1800264ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264f1  mov     ebx, eax
0x1800264f3  test    eax, eax
0x1800264f5  jns     short loc_180026501
0x1800264f7  mov     edx, 0F8h
0x1800264fc  jmp     loc_180026470
0x180026501  mov     [rbp+57h+var_78], r13
0x180026505  lea     rdx, [rbp+57h+var_78]
0x180026509  lea     rcx, [rbp+57h+var_70]
0x18002650d  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180026512  mov     ebx, eax
0x180026514  test    eax, eax
0x180026516  jns     short loc_18002653F
0x180026518  mov     rcx, [rbp+5Fh]; this
0x18002651c  mov     r9d, eax; char *
0x18002651f  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180026526  mov     edx, 0FCh; void *
0x18002652b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026530  nop
0x180026531  lea     rcx, [rbp+57h+var_78]
0x180026535  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002653a  jmp     loc_180026484
0x18002653f  mov     [rbp+57h+var_68], r13
0x180026543  mov     rcx, [rbp+57h+var_78]
0x180026547  mov     rax, [rcx]
0x18002654a  lea     rdx, [rbp+57h+var_68]
0x18002654e  mov     rax, [rax+38h]
0x180026552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026557  mov     ebx, eax
0x180026559  test    eax, eax
0x18002655b  jns     short loc_180026581
0x18002655d  mov     rcx, [rbp+5Fh]; this
0x180026561  mov     r9d, eax; char *
0x180026564  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002656b  mov     edx, 0FFh; void *
0x180026570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026575  nop
0x180026576  lea     rcx, [rbp+57h+var_68]; this
0x18002657a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002657f  jmp     short loc_180026531
0x180026581  xor     edx, edx; length
0x180026583  mov     rcx, [rbp+57h+var_68]; string
0x180026587  call    cs:__imp_WindowsGetStringRawBuffer
0x18002658d  mov     r12, rax
0x180026590  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026594  inc     rbx
0x180026597  cmp     [rax+rbx*2], r13w
0x18002659c  jnz     short loc_180026594
0x18002659e  mov     [r14], r13
0x1800265a1  lea     rsi, [rbx+1]
0x1800265a5  cmp     rsi, rbx
0x1800265a8  jb      short loc_1800265DD
0x1800265aa  mov     r9, r14
0x1800265ad  mov     r8, rsi
0x1800265b0  xor     edx, edx
0x1800265b2  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800265b7  mov     edi, eax
0x1800265b9  test    eax, eax
0x1800265bb  js      short loc_1800265E2
0x1800265bd  mov     [rsp+0D0h+var_A0], 300h; unsigned int
0x1800265c5  mov     [rsp+0D0h+var_B0], r13; unsigned __int16 **
0x1800265ca  mov     r9, rbx; unsigned __int64
0x1800265cd  mov     r8, r12; unsigned __int16 *
0x1800265d0  mov     rdx, rsi; unsigned __int64
0x1800265d3  mov     rcx, [r14]; pszDest
0x1800265d6  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800265db  jmp     short loc_1800265FB
0x1800265dd  mov     edi, 80070216h
0x1800265e2  mov     rcx, [rbp+5Fh]; this
0x1800265e6  mov     r9d, edi; char *
0x1800265e9  lea     r8, aOnecoreBaseDia_27; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800265f0  mov     edx, 100h; void *
0x1800265f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265fa  nop
0x1800265fb  lea     rcx, [rbp+57h+var_68]; this
0x1800265ff  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180026604  nop
0x180026605  lea     rcx, [rbp+57h+var_78]
0x180026609  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002660e  nop
0x18002660f  lea     rcx, [rbp+57h+var_80]
0x180026613  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026618  nop
0x180026619  lea     rcx, [rbp+57h+var_88]
0x18002661d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026622  nop
0x180026623  lea     rcx, [rbp+57h+var_90]
0x180026627  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002662c  mov     ebx, edi
0x18002662e  lea     rcx, [rbp+57h+var_70]
0x180026632  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026637  nop
0x180026638  mov     rcx, r15
0x18002663b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026640  mov     eax, ebx
0x180026642  mov     rcx, [rbp+57h+var_38]
0x180026646  xor     rcx, rsp; StackCookie
0x180026649  call    __security_check_cookie
0x18002664e  mov     rbx, [rsp+0D0h+arg_18]
0x180026656  add     rsp, 0A0h
0x18002665d  pop     r15
0x18002665f  pop     r14
0x180026661  pop     r13
0x180026663  pop     r12
0x180026665  pop     rdi
0x180026666  pop     rsi
0x180026667  pop     rbp
0x180026668  retn
```

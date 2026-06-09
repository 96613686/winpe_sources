# FSServiceDrivenActionJsonDescriptor::InitializeFromString(ushort const *,Microsoft::WRL::ComPtr<FSActionContext>)

- ea: `0x1800a2180`
- end: `0x1800a2702`
- name: `?InitializeFromString@FSServiceDrivenActionJsonDescriptor@@AEAAJPEBGV?$ComPtr@VFSActionContext@@@WRL@Microsoft@@@Z`
- size: `1410`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a3618`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001a090`
- `0x18001c6f4`
- `0x18001ec78`
- `0x180032640`
- `0x1800328bc`
- `0x1800334b4`
- `0x18009f424`
- `0x1800a2180`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2243`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a22e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a23b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a24f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2243`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a22e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a23b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a24f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a2258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a22fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a23cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a250d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a2258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a22fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a23cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a250d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2542`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2542`

## string_xrefs

- `0x1800a21e0`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a227f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a231f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a23f3`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a242f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a260e`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a2634`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a2658`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a267c`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSServiceDrivenActionJsonDescriptor::InitializeFromString(
        __int64 a1,
        const unsigned __int16 *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING, __int64 *); // rsi
  unsigned __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, HSTRING *); // rsi
  unsigned __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64 *); // rsi
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  unsigned int i; // esi
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v31; // rcx
  int v32; // eax
  PCWSTR v33; // rax
  int v34; // eax
  __int64 (__fastcall *v35)(__int64, __int64 *, HSTRING *, __int64 *); // rbx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rdx
  UINT32 *v40; // [rsp+20h] [rbp-99h]
  UINT32 length[2]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v42; // [rsp+38h] [rbp-81h] BYREF
  __int64 v43; // [rsp+40h] [rbp-79h] BYREF
  HSTRING v44; // [rsp+48h] [rbp-71h] BYREF
  __int64 v45; // [rsp+50h] [rbp-69h] BYREF
  __int64 v46; // [rsp+58h] [rbp-61h] BYREF
  HSTRING v47; // [rsp+60h] [rbp-59h] BYREF
  __int64 v48; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v49; // [rsp+70h] [rbp-49h] BYREF
  __int64 v50; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v51[2]; // [rsp+80h] [rbp-39h] BYREF
  HSTRING string; // [rsp+90h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-21h] BYREF
  HSTRING v54; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING_HEADER v55; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v51[1] = a3;
  v51[0] = 0;
  v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v54, (const unsigned __int16 (*)[29])a2);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         *v6,
         v51);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v7,
      (int)v40);
    goto LABEL_55;
  }
  v42 = 0;
  v9 = v51[0];
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v51[0] + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  length[0] = 0;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( (int)ULongLongToUInt(v11, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length[0], &hstringHeader, &string);
  v12 = v10(v9, string, &v42);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v12,
      (int)v40);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    goto LABEL_55;
  }
  v44 = 0;
  v13 = v42;
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v42 + 80LL);
  length[0] = 0;
  v15 = -1;
  do
    ++v15;
  while ( FSServiceDrivenActionJsonDescriptor::s_instanceIdTag[v15] );
  if ( (int)ULongLongToUInt(v15, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(FSServiceDrivenActionJsonDescriptor::s_instanceIdTag, length[0], &hstringHeader, &string);
  v16 = v14(v13, string, &v44);
  v8 = v16;
  if ( v16 < 0 )
  {
    v17 = 149;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v16,
      (int)v40);
LABEL_17:
    Windows::Internal::String::~String((Windows::Internal::String *)&v44);
    goto LABEL_9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v44, 0);
  v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          a1 + 16,
          StringRawBuffer,
          -1);
  v8 = v16;
  if ( v16 < 0 )
  {
    v17 = 150;
    goto LABEL_16;
  }
  v43 = 0;
  v19 = v42;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v42 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  length[0] = 0;
  v21 = -1;
  do
    ++v21;
  while ( FSServiceDrivenActionJsonDescriptor::s_serviceDrivenActionsTag[v21] );
  if ( (int)ULongLongToUInt(v21, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(
    FSServiceDrivenActionJsonDescriptor::s_serviceDrivenActionsTag,
    length[0],
    &hstringHeader,
    &string);
  v22 = v20(v19, string, &v43);
  v8 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v22,
      (int)v40);
LABEL_26:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    goto LABEL_17;
  }
  v46 = 0;
  v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
          &v43,
          &v46);
  v8 = v23;
  if ( v23 < 0 )
  {
    v24 = 158;
    goto LABEL_29;
  }
  v49 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v49);
  v8 = v23;
  if ( v23 < 0 )
  {
    v24 = 161;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v23,
      (int)v40);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    goto LABEL_26;
  }
  for ( i = 0; i < v49; ++i )
  {
    v45 = 0;
    v26 = v43;
    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    v28 = v27(v26, i, &v45);
    v8 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v28,
        (int)v40);
      goto LABEL_53;
    }
    v47 = 0;
    v29 = v45;
    v30 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v45 + 80LL);
    length[0] = 0;
    v31 = -1;
    do
      ++v31;
    while ( FSServiceDrivenActionJsonDescriptor::s_actionTypeTag[v31] );
    if ( (int)ULongLongToUInt(v31, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSServiceDrivenActionJsonDescriptor::s_actionTypeTag, length[0], &v55, &v54);
    v32 = v30(v29, v54, &v47);
    v8 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v32,
        (int)v40);
LABEL_51:
      Windows::Internal::String::~String((Windows::Internal::String *)&v47);
LABEL_53:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
      goto LABEL_30;
    }
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    v33 = WindowsGetStringRawBuffer(v47, 0);
    v34 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &string,
            v33,
            -1);
    v8 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v34,
        (int)v40);
      goto LABEL_49;
    }
    v48 = 0;
    v35 = *(__int64 (__fastcall **)(__int64, __int64 *, HSTRING *, __int64 *))(*(_QWORD *)a1 + 48LL);
    *(_QWORD *)length = *a3;
    Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(length);
    v50 = v45;
    Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(&v50);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    v40 = length;
    v36 = v35(a1, &v48, &string, &v50);
    v8 = v36;
    if ( v36 < 0 )
    {
      v38 = 176;
      goto LABEL_47;
    }
    v36 = CTSimpleArray<Microsoft::WRL::ComPtr<IServiceDrivenAction>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>>::_AddSortedEx<FSCompareServiceDrivenActions,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &>(
            a1 + 40,
            v37,
            &v48);
    v8 = v36;
    if ( v36 < 0 )
    {
      v38 = 179;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v36,
        (int)length);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
LABEL_49:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
      goto LABEL_51;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
    Windows::Internal::String::~String((Windows::Internal::String *)&v47);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  Windows::Internal::String::~String((Windows::Internal::String *)&v44);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  v8 = 0;
LABEL_55:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v51);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a3);
  return v8;
}

```

## disassembly

```asm
0x1800a2180  mov     [rsp-8+arg_18], rbx
0x1800a2185  push    rbp
0x1800a2186  push    rsi
0x1800a2187  push    rdi
0x1800a2188  push    r12
0x1800a218a  push    r13
0x1800a218c  push    r14
0x1800a218e  push    r15
0x1800a2190  lea     rbp, [rsp-27h]
0x1800a2195  sub     rsp, 0E0h
0x1800a219c  mov     rax, cs:__security_cookie
0x1800a21a3  xor     rax, rsp
0x1800a21a6  mov     [rbp+57h+var_40], rax
0x1800a21aa  mov     r12, r8
0x1800a21ad  mov     rdi, rdx
0x1800a21b0  mov     r15, rcx
0x1800a21b3  mov     [rbp+57h+var_88], r8
0x1800a21b7  xor     r13d, r13d
0x1800a21ba  mov     [rbp+57h+var_90], r13
0x1800a21be  lea     rcx, [rbp+57h+var_60]; string
0x1800a21c2  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800a21c7  lea     rdx, [rbp+57h+var_90]
0x1800a21cb  mov     rcx, [rax]
0x1800a21ce  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x1800a21d3  mov     ebx, eax
0x1800a21d5  test    eax, eax
0x1800a21d7  jns     short loc_1800A21F6
0x1800a21d9  mov     rcx, [rbp+5Fh]; this
0x1800a21dd  mov     r9d, eax; char *
0x1800a21e0  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a21e7  mov     edx, 8Dh; void *
0x1800a21ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a21f1  jmp     loc_1800A26C7
0x1800a21f6  mov     [rsp+110h+var_D8], r13
0x1800a21fb  mov     rbx, [rbp+57h+var_90]
0x1800a21ff  mov     rax, [rbx]
0x1800a2202  mov     rsi, [rax+30h]
0x1800a2206  lea     rcx, [rsp+110h+var_D8]
0x1800a220b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a2210  mov     [rsp+110h+length], r13d
0x1800a2215  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a2219  mov     rcx, r14
0x1800a221c  inc     rcx; unsigned __int64
0x1800a221f  cmp     [rdi+rcx*2], r13w
0x1800a2224  jnz     short loc_1800A221C
0x1800a2226  lea     rdx, [rsp+110h+length]; unsigned int *
0x1800a222b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a2230  test    eax, eax
0x1800a2232  jns     short loc_1800A2249
0x1800a2234  xor     r9d, r9d; lpArguments
0x1800a2237  xor     r8d, r8d; nNumberOfArguments
0x1800a223a  lea     edx, [r9+1]; dwExceptionFlags
0x1800a223e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a2243  call    cs:__imp_RaiseException
0x1800a2249  lea     r9, [rbp+57h+string]; string
0x1800a224d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a2251  mov     edx, [rsp+110h+length]; length
0x1800a2255  mov     rcx, rdi; sourceString
0x1800a2258  call    cs:__imp_WindowsCreateStringReference
0x1800a225e  lea     r8, [rsp+110h+var_D8]
0x1800a2263  mov     rdx, [rbp+57h+string]
0x1800a2267  mov     rcx, rbx
0x1800a226a  mov     rax, rsi
0x1800a226d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2272  mov     ebx, eax
0x1800a2274  test    eax, eax
0x1800a2276  jns     short loc_1800A22A0
0x1800a2278  mov     rcx, [rbp+5Fh]; this
0x1800a227c  mov     r9d, eax; char *
0x1800a227f  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a2286  mov     edx, 91h; void *
0x1800a228b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2290  nop
0x1800a2291  lea     rcx, [rsp+110h+var_D8]
0x1800a2296  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a229b  jmp     loc_1800A26C7
0x1800a22a0  mov     [rbp+57h+var_C8], r13
0x1800a22a4  mov     rdi, [rsp+110h+var_D8]
0x1800a22a9  mov     rax, [rdi]
0x1800a22ac  mov     rsi, [rax+50h]
0x1800a22b0  mov     rbx, cs:?s_instanceIdTag@FSServiceDrivenActionJsonDescriptor@@0QEBGEB; ushort const * const FSServiceDrivenActionJsonDescriptor::s_instanceIdTag
0x1800a22b7  mov     [rsp+110h+length], r13d
0x1800a22bc  mov     rcx, r14
0x1800a22bf  inc     rcx; unsigned __int64
0x1800a22c2  cmp     [rbx+rcx*2], r13w
0x1800a22c7  jnz     short loc_1800A22BF
0x1800a22c9  lea     rdx, [rsp+110h+length]; unsigned int *
0x1800a22ce  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a22d3  test    eax, eax
0x1800a22d5  jns     short loc_1800A22EC
0x1800a22d7  xor     r9d, r9d; lpArguments
0x1800a22da  xor     r8d, r8d; nNumberOfArguments
0x1800a22dd  lea     edx, [r9+1]; dwExceptionFlags
0x1800a22e1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a22e6  call    cs:__imp_RaiseException
0x1800a22ec  lea     r9, [rbp+57h+string]; string
0x1800a22f0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a22f4  mov     edx, [rsp+110h+length]; length
0x1800a22f8  mov     rcx, rbx; sourceString
0x1800a22fb  call    cs:__imp_WindowsCreateStringReference
0x1800a2301  lea     r8, [rbp+57h+var_C8]
0x1800a2305  mov     rdx, [rbp+57h+string]
0x1800a2309  mov     rcx, rdi
0x1800a230c  mov     rax, rsi
0x1800a230f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2314  mov     ebx, eax
0x1800a2316  test    eax, eax
0x1800a2318  jns     short loc_1800A2341
0x1800a231a  mov     edx, 95h; void *
0x1800a231f  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a2326  mov     r9d, eax; char *
0x1800a2329  mov     rcx, [rbp+5Fh]; this
0x1800a232d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2332  nop
0x1800a2333  lea     rcx, [rbp+57h+var_C8]; this
0x1800a2337  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a233c  jmp     loc_1800A2291
0x1800a2341  xor     edx, edx; length
0x1800a2343  mov     rcx, [rbp+57h+var_C8]; string
0x1800a2347  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a234d  lea     rcx, [r15+10h]
0x1800a2351  mov     r8, r14
0x1800a2354  mov     rdx, rax
0x1800a2357  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a235c  mov     ebx, eax
0x1800a235e  test    eax, eax
0x1800a2360  jns     short loc_1800A2369
0x1800a2362  mov     edx, 96h
0x1800a2367  jmp     short loc_1800A231F
0x1800a2369  mov     [rbp+57h+var_D0], r13
0x1800a236d  mov     rdi, [rsp+110h+var_D8]
0x1800a2372  mov     rax, [rdi]
0x1800a2375  mov     rsi, [rax+48h]
0x1800a2379  lea     rcx, [rbp+57h+var_D0]
0x1800a237d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a2382  mov     rbx, cs:?s_serviceDrivenActionsTag@FSServiceDrivenActionJsonDescriptor@@0QEBGEB; ushort const * const FSServiceDrivenActionJsonDescriptor::s_serviceDrivenActionsTag
0x1800a2389  mov     [rsp+110h+length], r13d
0x1800a238e  mov     rcx, r14
0x1800a2391  inc     rcx; unsigned __int64
0x1800a2394  cmp     [rbx+rcx*2], r13w
0x1800a2399  jnz     short loc_1800A2391
0x1800a239b  lea     rdx, [rsp+110h+length]; unsigned int *
0x1800a23a0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a23a5  test    eax, eax
0x1800a23a7  jns     short loc_1800A23BE
0x1800a23a9  xor     r9d, r9d; lpArguments
0x1800a23ac  xor     r8d, r8d; nNumberOfArguments
0x1800a23af  lea     edx, [r9+1]; dwExceptionFlags
0x1800a23b3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a23b8  call    cs:__imp_RaiseException
0x1800a23be  lea     r9, [rbp+57h+string]; string
0x1800a23c2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a23c6  mov     edx, [rsp+110h+length]; length
0x1800a23ca  mov     rcx, rbx; sourceString
0x1800a23cd  call    cs:__imp_WindowsCreateStringReference
0x1800a23d3  lea     r8, [rbp+57h+var_D0]
0x1800a23d7  mov     rdx, [rbp+57h+string]
0x1800a23db  mov     rcx, rdi
0x1800a23de  mov     rax, rsi
0x1800a23e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23e6  mov     ebx, eax
0x1800a23e8  test    eax, eax
0x1800a23ea  jns     short loc_1800A2413
0x1800a23ec  mov     rcx, [rbp+5Fh]; this
0x1800a23f0  mov     r9d, eax; char *
0x1800a23f3  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a23fa  mov     edx, 9Ah; void *
0x1800a23ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2404  nop
0x1800a2405  lea     rcx, [rbp+57h+var_D0]
0x1800a2409  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a240e  jmp     loc_1800A2333
0x1800a2413  mov     [rbp+57h+var_B8], r13
0x1800a2417  lea     rdx, [rbp+57h+var_B8]
0x1800a241b  lea     rcx, [rbp+57h+var_D0]
0x1800a241f  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800a2424  mov     ebx, eax
0x1800a2426  test    eax, eax
0x1800a2428  jns     short loc_1800A244E
0x1800a242a  mov     edx, 9Eh; void *
0x1800a242f  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a2436  mov     r9d, eax; char *
0x1800a2439  mov     rcx, [rbp+5Fh]; this
0x1800a243d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2442  nop
0x1800a2443  lea     rcx, [rbp+57h+var_B8]
0x1800a2447  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a244c  jmp     short loc_1800A2405
0x1800a244e  mov     [rbp+57h+var_A0], r13d
0x1800a2452  mov     rcx, [rbp+57h+var_B8]
0x1800a2456  mov     rax, [rcx]
0x1800a2459  lea     rdx, [rbp+57h+var_A0]
0x1800a245d  mov     rax, [rax+38h]
0x1800a2461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2466  mov     ebx, eax
0x1800a2468  test    eax, eax
0x1800a246a  jns     short loc_1800A2473
0x1800a246c  mov     edx, 0A1h
0x1800a2471  jmp     short loc_1800A242F
0x1800a2473  mov     esi, r13d
0x1800a2476  cmp     esi, [rbp+57h+var_A0]
0x1800a2479  jnb     loc_1800A269C
0x1800a247f  mov     [rbp+57h+var_C0], r13
0x1800a2483  mov     rdi, [rbp+57h+var_D0]
0x1800a2487  mov     rax, [rdi]
0x1800a248a  mov     rbx, [rax+30h]
0x1800a248e  lea     rcx, [rbp+57h+var_C0]
0x1800a2492  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a2497  lea     r8, [rbp+57h+var_C0]
0x1800a249b  mov     edx, esi
0x1800a249d  mov     rcx, rdi
0x1800a24a0  mov     rax, rbx
0x1800a24a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24a8  mov     ebx, eax
0x1800a24aa  test    eax, eax
0x1800a24ac  js      loc_1800A2675
0x1800a24b2  mov     [rbp+57h+var_B0], r13
0x1800a24b6  mov     rdi, [rbp+57h+var_C0]
0x1800a24ba  mov     rax, [rdi]
0x1800a24bd  mov     r14, [rax+50h]
0x1800a24c1  mov     rbx, cs:?s_actionTypeTag@FSServiceDrivenActionJsonDescriptor@@0QEBGEB; ushort const * const FSServiceDrivenActionJsonDescriptor::s_actionTypeTag
0x1800a24c8  mov     [rsp+110h+length], r13d
0x1800a24cd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a24d1  inc     rcx; unsigned __int64
0x1800a24d4  cmp     [rbx+rcx*2], r13w
0x1800a24d9  jnz     short loc_1800A24D1
0x1800a24db  lea     rdx, [rsp+110h+length]; unsigned int *
0x1800a24e0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a24e5  test    eax, eax
0x1800a24e7  jns     short loc_1800A24FE
0x1800a24e9  xor     r9d, r9d; lpArguments
0x1800a24ec  xor     r8d, r8d; nNumberOfArguments
0x1800a24ef  lea     edx, [r9+1]; dwExceptionFlags
0x1800a24f3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a24f8  call    cs:__imp_RaiseException
0x1800a24fe  lea     r9, [rbp+57h+var_60]; string
0x1800a2502  lea     r8, [rbp+57h+var_58]; hstringHeader
0x1800a2506  mov     edx, [rsp+110h+length]; length
0x1800a250a  mov     rcx, rbx; sourceString
0x1800a250d  call    cs:__imp_WindowsCreateStringReference
0x1800a2513  lea     r8, [rbp+57h+var_B0]
0x1800a2517  mov     rdx, [rbp+57h+var_60]
0x1800a251b  mov     rcx, rdi
0x1800a251e  mov     rax, r14
0x1800a2521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2526  mov     ebx, eax
0x1800a2528  test    eax, eax
0x1800a252a  js      loc_1800A2651
0x1800a2530  mov     [rbp+57h+string], r13
0x1800a2534  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x1800a2538  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x1800a253c  xor     edx, edx; length
0x1800a253e  mov     rcx, [rbp+57h+var_B0]; string
0x1800a2542  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2548  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a254c  mov     rdx, rax
0x1800a254f  lea     rcx, [rbp+57h+string]
0x1800a2553  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a2558  mov     ebx, eax
0x1800a255a  test    eax, eax
0x1800a255c  js      loc_1800A262D
0x1800a2562  mov     [rbp+57h+var_A8], r13
0x1800a2566  mov     rax, [r15]
0x1800a2569  mov     rbx, [rax+30h]
0x1800a256d  mov     rax, [r12]
0x1800a2571  mov     qword ptr [rsp+110h+length], rax
0x1800a2576  lea     rcx, [rsp+110h+length]
0x1800a257b  call    ?InternalAddRef@?$ComPtr@VCFlightStore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(void)
0x1800a2580  mov     rcx, [rbp+57h+var_C0]
0x1800a2584  mov     [rbp+57h+var_98], rcx
0x1800a2588  lea     rcx, [rbp+57h+var_98]
0x1800a258c  call    ?InternalAddRef@?$ComPtr@VCFlightStore@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CFlightStore>::InternalAddRef(void)
0x1800a2591  lea     rcx, [rbp+57h+var_A8]
0x1800a2595  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a259a  lea     rax, [rsp+110h+length]
0x1800a259f  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800a25a4  lea     r9, [rbp+57h+var_98]
0x1800a25a8  lea     r8, [rbp+57h+string]
0x1800a25ac  lea     rdx, [rbp+57h+var_A8]
0x1800a25b0  mov     rcx, r15
0x1800a25b3  mov     rax, rbx
0x1800a25b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a25bb  mov     ebx, eax
0x1800a25bd  test    eax, eax
0x1800a25bf  js      short loc_1800A2609
0x1800a25c1  lea     rcx, [r15+28h]
0x1800a25c5  lea     r8, [rbp+57h+var_A8]
0x1800a25c9  call    ??$_AddSortedEx@VFSCompareServiceDrivenActions@@AEBV?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@@@QEAAJAEBVFSCompareServiceDrivenActions@@AEBV?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IServiceDrivenAction>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>>::_AddSortedEx<FSCompareServiceDrivenActions,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &>(FSCompareServiceDrivenActions const &,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &,unsigned __int64 *)
0x1800a25ce  mov     ebx, eax
0x1800a25d0  test    eax, eax
0x1800a25d2  js      short loc_1800A2602
0x1800a25d4  lea     rcx, [rbp+57h+var_A8]
0x1800a25d8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a25dd  nop
0x1800a25de  lea     rcx, [rbp+57h+string]
0x1800a25e2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a25e7  nop
0x1800a25e8  lea     rcx, [rbp+57h+var_B0]; this
0x1800a25ec  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800a25f1  nop
  ... truncated ...
```

# ServiceDrivenActionJsonDescriptor::InitializeFromString(ushort const *,Microsoft::WRL::ComPtr<ActionContext>)

- ea: `0x180039d10`
- end: `0x18003a188`
- name: `?InitializeFromString@ServiceDrivenActionJsonDescriptor@@AEAAJPEBGV?$ComPtr@VActionContext@@@WRL@Microsoft@@@Z`
- size: `1144`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b120`

## callees

- `0x18000a6e0`
- `0x18001055c`
- `0x18001208c`
- `0x18001e1b4`
- `0x18002407c`
- `0x1800240b8`
- `0x180024d34`
- `0x180024e20`
- `0x180024ec0`
- `0x1800253bc`
- `0x180026930`
- `0x1800374fc`
- `0x180039d10`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039fcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039fcb`

## string_xrefs

- `0x180039d6b`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x180039dc8`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x180039e27`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x180039ebb`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x180039ef9`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x18003a09c`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x18003a0c2`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x18003a0e6`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`
- `0x18003a10a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ServiceDrivenActionJsonDescriptor::InitializeFromString(
        _QWORD *a1,
        const unsigned __int16 *a2,
        _QWORD *a3)
{
  __int64 *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, _QWORD); // rbx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  unsigned int i; // esi
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, HSTRING *); // rbx
  int v28; // eax
  PCWSTR v29; // rax
  int v30; // eax
  __int64 (__fastcall *v31)(_QWORD *, __int64 *, HSTRING *, _QWORD *); // rbx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  int *v36; // [rsp+20h] [rbp-99h]
  __int64 v37; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  __int64 v40; // [rsp+48h] [rbp-71h] BYREF
  __int64 v41; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v42; // [rsp+58h] [rbp-61h] BYREF
  __int64 v43; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-51h] BYREF
  int v45[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v46; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v47[2]; // [rsp+80h] [rbp-39h] BYREF
  HSTRING v48[4]; // [rsp+90h] [rbp-29h] BYREF
  HSTRING v49[4]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v47[1] = a3;
  v46 = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(v49, (const unsigned __int16 (*)[29])a2);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         *v6,
         (__int64)&v46);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v7,
      (int)v36);
    goto LABEL_41;
  }
  v37 = 0;
  v9 = v46;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v46 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v48, a2);
  v11 = v10(v9, v48[0], &v37);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v11,
      (int)v36);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    goto LABEL_41;
  }
  string = 0;
  v12 = v37;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v37 + 80LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v48,
    ServiceDrivenActionJsonDescriptor::s_instanceIdTag);
  v14 = v13(v12, v48[0], &string);
  v8 = v14;
  if ( v14 < 0 )
  {
    v15 = 139;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v14,
      (int)v36);
LABEL_9:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    goto LABEL_5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          a1 + 2,
          StringRawBuffer,
          -1);
  v8 = v14;
  if ( v14 < 0 )
  {
    v15 = 140;
    goto LABEL_8;
  }
  v38 = 0;
  v17 = v37;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v37 + 72LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v48,
    ServiceDrivenActionJsonDescriptor::s_serviceDrivenActionsTag);
  v19 = v18(v17, v48[0], &v38);
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v19,
      (int)v36);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    goto LABEL_9;
  }
  v41 = 0;
  v20 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
          &v38,
          (__int64)&v41);
  v8 = v20;
  if ( v20 < 0 )
  {
    v21 = 148;
    goto LABEL_17;
  }
  v44 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v44);
  v8 = v20;
  if ( v20 < 0 )
  {
    v21 = 151;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v20,
      (int)v36);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    goto LABEL_14;
  }
  for ( i = 0; i < v44; ++i )
  {
    v40 = 0;
    v23 = v38;
    v24 = (*v38)[6];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v25 = v24(v23, (GUID *)i, (__int64)&v40);
    v8 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v25,
        (int)v36);
      goto LABEL_39;
    }
    v42 = 0;
    v26 = v40;
    v27 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v40 + 80LL);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v49,
      ServiceDrivenActionJsonDescriptor::s_actionTypeTag);
    v28 = v27(v26, v49[0], &v42);
    v8 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v28,
        (int)v36);
      goto LABEL_37;
    }
    memset(v48, 0, 24);
    v29 = WindowsGetStringRawBuffer(v42, 0);
    v30 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v48, v29, -1);
    v8 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v30,
        (int)v36);
      goto LABEL_35;
    }
    v43 = 0;
    v31 = *(__int64 (__fastcall **)(_QWORD *, __int64 *, HSTRING *, _QWORD *))(*a1 + 40LL);
    *(_QWORD *)v45 = *a3;
    Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(v45);
    v47[0] = v40;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    v36 = v45;
    v32 = v31(a1, &v43, v48, v47);
    v8 = v32;
    if ( v32 < 0 )
    {
      v34 = 166;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v32,
        (int)v45);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
LABEL_35:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v48);
LABEL_37:
      Windows::Internal::String::~String((Windows::Internal::String *)&v42);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      goto LABEL_18;
    }
    v32 = CTSimpleArray<Microsoft::WRL::ComPtr<IServiceDrivenAction>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>>::_AddSortedEx<CompareServiceDrivenActions,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &>(
            a1 + 5,
            v33,
            &v43);
    v8 = v32;
    if ( v32 < 0 )
    {
      v34 = 169;
      goto LABEL_33;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v48);
    Windows::Internal::String::~String((Windows::Internal::String *)&v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
  v8 = 0;
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a3);
  return v8;
}

```

## disassembly

```asm
0x180039d10  push    rbp
0x180039d12  push    rbx
0x180039d13  push    rsi
0x180039d14  push    rdi
0x180039d15  push    r12
0x180039d17  push    r14
0x180039d19  push    r15
0x180039d1b  lea     rbp, [rsp-27h]
0x180039d20  sub     rsp, 0E0h
0x180039d27  mov     rax, cs:__security_cookie
0x180039d2e  xor     rax, rsp
0x180039d31  mov     [rbp+57h+var_40], rax
0x180039d35  mov     r15, r8
0x180039d38  mov     rsi, rdx
0x180039d3b  mov     r14, rcx
0x180039d3e  mov     [rbp+57h+var_88], r8
0x180039d42  xor     r12d, r12d
0x180039d45  mov     [rbp+57h+var_98], r12
0x180039d49  lea     rcx, [rbp+57h+var_60]; string
0x180039d4d  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180039d52  lea     rdx, [rbp+57h+var_98]
0x180039d56  mov     rcx, [rax]
0x180039d59  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180039d5e  mov     ebx, eax
0x180039d60  test    eax, eax
0x180039d62  jns     short loc_180039D81
0x180039d64  mov     rcx, [rbp+5Fh]; this
0x180039d68  mov     r9d, eax; char *
0x180039d6b  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180039d72  mov     edx, 83h; void *
0x180039d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d7c  jmp     loc_18003A156
0x180039d81  mov     [rsp+110h+var_E0], r12
0x180039d86  mov     rdi, [rbp+57h+var_98]
0x180039d8a  mov     rax, [rdi]
0x180039d8d  mov     rbx, [rax+30h]
0x180039d91  lea     rcx, [rsp+110h+var_E0]
0x180039d96  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039d9b  mov     rdx, rsi; unsigned __int16 *
0x180039d9e  lea     rcx, [rbp+57h+var_80]; this
0x180039da2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180039da7  lea     r8, [rsp+110h+var_E0]
0x180039dac  mov     rdx, [rbp+57h+var_80]
0x180039db0  mov     rcx, rdi
0x180039db3  mov     rax, rbx
0x180039db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dbb  mov     ebx, eax
0x180039dbd  test    eax, eax
0x180039dbf  jns     short loc_180039DE9
0x180039dc1  mov     rcx, [rbp+5Fh]; this
0x180039dc5  mov     r9d, eax; char *
0x180039dc8  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180039dcf  mov     edx, 87h; void *
0x180039dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039dd9  nop
0x180039dda  lea     rcx, [rsp+110h+var_E0]
0x180039ddf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039de4  jmp     loc_18003A156
0x180039de9  mov     [rbp+57h+string], r12
0x180039ded  mov     rdi, [rsp+110h+var_E0]
0x180039df2  mov     rax, [rdi]
0x180039df5  mov     rbx, [rax+50h]
0x180039df9  mov     rdx, cs:?s_instanceIdTag@ServiceDrivenActionJsonDescriptor@@0QEBGEB; unsigned __int16 *
0x180039e00  lea     rcx, [rbp+57h+var_80]; this
0x180039e04  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180039e09  lea     r8, [rbp+57h+string]
0x180039e0d  mov     rdx, [rbp+57h+var_80]
0x180039e11  mov     rcx, rdi
0x180039e14  mov     rax, rbx
0x180039e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e1c  mov     ebx, eax
0x180039e1e  test    eax, eax
0x180039e20  jns     short loc_180039E46
0x180039e22  mov     edx, 8Bh; void *
0x180039e27  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180039e2e  mov     r9d, eax; char *
0x180039e31  mov     rcx, [rbp+5Fh]; this
0x180039e35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e3a  nop
0x180039e3b  lea     rcx, [rbp+57h+string]; this
0x180039e3f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180039e44  jmp     short loc_180039DDA
0x180039e46  xor     edx, edx; length
0x180039e48  mov     rcx, [rbp+57h+string]; string
0x180039e4c  call    cs:__imp_WindowsGetStringRawBuffer
0x180039e52  lea     rcx, [r14+10h]
0x180039e56  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039e5a  mov     rdx, rax
0x180039e5d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180039e62  mov     ebx, eax
0x180039e64  test    eax, eax
0x180039e66  jns     short loc_180039E6F
0x180039e68  mov     edx, 8Ch
0x180039e6d  jmp     short loc_180039E27
0x180039e6f  mov     [rsp+110h+var_D8], r12
0x180039e74  mov     rdi, [rsp+110h+var_E0]
0x180039e79  mov     rax, [rdi]
0x180039e7c  mov     rbx, [rax+48h]
0x180039e80  lea     rcx, [rsp+110h+var_D8]
0x180039e85  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039e8a  mov     rdx, cs:?s_serviceDrivenActionsTag@ServiceDrivenActionJsonDescriptor@@0QEBGEB; unsigned __int16 *
0x180039e91  lea     rcx, [rbp+57h+var_80]; this
0x180039e95  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180039e9a  lea     r8, [rsp+110h+var_D8]
0x180039e9f  mov     rdx, [rbp+57h+var_80]
0x180039ea3  mov     rcx, rdi
0x180039ea6  mov     rax, rbx
0x180039ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039eae  mov     ebx, eax
0x180039eb0  test    eax, eax
0x180039eb2  jns     short loc_180039EDC
0x180039eb4  mov     rcx, [rbp+5Fh]; this
0x180039eb8  mov     r9d, eax; char *
0x180039ebb  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180039ec2  mov     edx, 90h; void *
0x180039ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ecc  nop
0x180039ecd  lea     rcx, [rsp+110h+var_D8]
0x180039ed2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039ed7  jmp     loc_180039E3B
0x180039edc  mov     [rbp+57h+var_C0], r12
0x180039ee0  lea     rdx, [rbp+57h+var_C0]
0x180039ee4  lea     rcx, [rsp+110h+var_D8]
0x180039ee9  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180039eee  mov     ebx, eax
0x180039ef0  test    eax, eax
0x180039ef2  jns     short loc_180039F18
0x180039ef4  mov     edx, 94h; void *
0x180039ef9  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180039f00  mov     r9d, eax; char *
0x180039f03  mov     rcx, [rbp+5Fh]; this
0x180039f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f0c  nop
0x180039f0d  lea     rcx, [rbp+57h+var_C0]
0x180039f11  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039f16  jmp     short loc_180039ECD
0x180039f18  mov     [rbp+57h+var_A8], r12d
0x180039f1c  mov     rcx, [rbp+57h+var_C0]
0x180039f20  mov     rax, [rcx]
0x180039f23  lea     rdx, [rbp+57h+var_A8]
0x180039f27  mov     rax, [rax+38h]
0x180039f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f30  mov     ebx, eax
0x180039f32  test    eax, eax
0x180039f34  jns     short loc_180039F3D
0x180039f36  mov     edx, 97h
0x180039f3b  jmp     short loc_180039EF9
0x180039f3d  mov     esi, r12d
0x180039f40  cmp     esi, [rbp+57h+var_A8]
0x180039f43  jnb     loc_18003A12A
0x180039f49  mov     [rbp+57h+var_C8], r12
0x180039f4d  mov     rdi, [rsp+110h+var_D8]
0x180039f52  mov     rax, [rdi]
0x180039f55  mov     rbx, [rax+30h]
0x180039f59  lea     rcx, [rbp+57h+var_C8]
0x180039f5d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039f62  lea     r8, [rbp+57h+var_C8]
0x180039f66  mov     edx, esi
0x180039f68  mov     rcx, rdi
0x180039f6b  mov     rax, rbx
0x180039f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f73  mov     ebx, eax
0x180039f75  test    eax, eax
0x180039f77  js      loc_18003A103
0x180039f7d  mov     [rbp+57h+var_B8], r12
0x180039f81  mov     rdi, [rbp+57h+var_C8]
0x180039f85  mov     rax, [rdi]
0x180039f88  mov     rbx, [rax+50h]
0x180039f8c  mov     rdx, cs:?s_actionTypeTag@ServiceDrivenActionJsonDescriptor@@0QEBGEB; unsigned __int16 *
0x180039f93  lea     rcx, [rbp+57h+var_60]; this
0x180039f97  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180039f9c  lea     r8, [rbp+57h+var_B8]
0x180039fa0  mov     rdx, [rbp+57h+var_60]
0x180039fa4  mov     rcx, rdi
0x180039fa7  mov     rax, rbx
0x180039faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039faf  mov     ebx, eax
0x180039fb1  test    eax, eax
0x180039fb3  js      loc_18003A0DF
0x180039fb9  mov     [rbp+57h+var_80], r12
0x180039fbd  mov     [rbp+57h+var_78], r12
0x180039fc1  mov     [rbp+57h+var_70], r12
0x180039fc5  xor     edx, edx; length
0x180039fc7  mov     rcx, [rbp+57h+var_B8]; string
0x180039fcb  call    cs:__imp_WindowsGetStringRawBuffer
0x180039fd1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039fd5  mov     rdx, rax
0x180039fd8  lea     rcx, [rbp+57h+var_80]
0x180039fdc  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180039fe1  mov     ebx, eax
0x180039fe3  test    eax, eax
0x180039fe5  js      loc_18003A0BB
0x180039feb  mov     [rbp+57h+var_B0], r12
0x180039fef  mov     rax, [r14]
0x180039ff2  mov     rbx, [rax+28h]
0x180039ff6  mov     rax, [r15]
0x180039ff9  mov     qword ptr [rbp+57h+var_A0], rax
0x180039ffd  lea     rcx, [rbp+57h+var_A0]
0x18003a001  call    ?InternalAddRef@?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(void)
0x18003a006  mov     rcx, [rbp+57h+var_C8]
0x18003a00a  mov     [rbp+57h+var_90], rcx
0x18003a00e  test    rcx, rcx
0x18003a011  jz      short loc_18003A020
0x18003a013  mov     rax, [rcx]
0x18003a016  mov     rax, [rax+8]
0x18003a01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a01f  nop
0x18003a020  lea     rcx, [rbp+57h+var_B0]
0x18003a024  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a029  lea     rax, [rbp+57h+var_A0]
0x18003a02d  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18003a032  lea     r9, [rbp+57h+var_90]
0x18003a036  lea     r8, [rbp+57h+var_80]
0x18003a03a  lea     rdx, [rbp+57h+var_B0]
0x18003a03e  mov     rcx, r14
0x18003a041  mov     rax, rbx
0x18003a044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a049  mov     ebx, eax
0x18003a04b  test    eax, eax
0x18003a04d  js      short loc_18003A097
0x18003a04f  lea     rcx, [r14+28h]
0x18003a053  lea     r8, [rbp+57h+var_B0]
0x18003a057  call    ??$_AddSortedEx@VCompareServiceDrivenActions@@AEBV?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@@@@@QEAAJAEBVCompareServiceDrivenActions@@AEBV?$ComPtr@UIServiceDrivenAction@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IServiceDrivenAction>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IServiceDrivenAction>>>::_AddSortedEx<CompareServiceDrivenActions,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &>(CompareServiceDrivenActions const &,Microsoft::WRL::ComPtr<IServiceDrivenAction> const &,unsigned __int64 *)
0x18003a05c  mov     ebx, eax
0x18003a05e  test    eax, eax
0x18003a060  js      short loc_18003A090
0x18003a062  lea     rcx, [rbp+57h+var_B0]
0x18003a066  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a06b  nop
0x18003a06c  lea     rcx, [rbp+57h+var_80]
0x18003a070  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003a075  nop
0x18003a076  lea     rcx, [rbp+57h+var_B8]; this
0x18003a07a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a07f  nop
0x18003a080  lea     rcx, [rbp+57h+var_C8]
0x18003a084  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a089  inc     esi
0x18003a08b  jmp     loc_180039F40
0x18003a090  mov     edx, 0A9h
0x18003a095  jmp     short loc_18003A09C
0x18003a097  mov     edx, 0A6h; void *
0x18003a09c  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003a0a3  mov     r9d, eax; char *
0x18003a0a6  mov     rcx, [rbp+5Fh]; this
0x18003a0aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0af  nop
0x18003a0b0  lea     rcx, [rbp+57h+var_B0]
0x18003a0b4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a0b9  jmp     short loc_18003A0D4
0x18003a0bb  mov     rcx, [rbp+5Fh]; this
0x18003a0bf  mov     r9d, eax; char *
0x18003a0c2  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003a0c9  mov     edx, 0A2h; void *
0x18003a0ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0d3  nop
0x18003a0d4  lea     rcx, [rbp+57h+var_80]
0x18003a0d8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003a0dd  jmp     short loc_18003A0F8
0x18003a0df  mov     rcx, [rbp+5Fh]; this
0x18003a0e3  mov     r9d, eax; char *
0x18003a0e6  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003a0ed  mov     edx, 0A0h; void *
0x18003a0f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0f7  nop
0x18003a0f8  lea     rcx, [rbp+57h+var_B8]; this
0x18003a0fc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a101  jmp     short loc_18003A11C
0x18003a103  mov     rcx, [rbp+5Fh]; this
0x18003a107  mov     r9d, eax; char *
0x18003a10a  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003a111  mov     edx, 9Ch; void *
0x18003a116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a11b  nop
0x18003a11c  lea     rcx, [rbp+57h+var_C8]
0x18003a120  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a125  jmp     loc_180039F0D
0x18003a12a  lea     rcx, [rbp+57h+var_C0]
0x18003a12e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a133  nop
0x18003a134  lea     rcx, [rsp+110h+var_D8]
0x18003a139  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a13e  nop
0x18003a13f  lea     rcx, [rbp+57h+string]; this
0x18003a143  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a148  nop
0x18003a149  lea     rcx, [rsp+110h+var_E0]
0x18003a14e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a153  mov     ebx, r12d
0x18003a156  lea     rcx, [rbp+57h+var_98]
0x18003a15a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a15f  nop
0x18003a160  mov     rcx, r15
0x18003a163  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003a168  mov     eax, ebx
0x18003a16a  mov     rcx, [rbp+57h+var_40]
0x18003a16e  xor     rcx, rsp; StackCookie
0x18003a171  call    __security_check_cookie
0x18003a176  add     rsp, 0E0h
0x18003a17d  pop     r15
  ... truncated ...
```

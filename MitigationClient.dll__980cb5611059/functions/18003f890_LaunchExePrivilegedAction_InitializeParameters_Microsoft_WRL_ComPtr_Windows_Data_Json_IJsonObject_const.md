# LaunchExePrivilegedAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x18003f890`
- end: `0x18003fb19`
- name: `?InitializeParameters@LaunchExePrivilegedAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x18001e164`
- `0x18002407c`
- `0x1800240b8`
- `0x1800253bc`
- `0x180026930`
- `0x18002c090`
- `0x1800336cc`
- `0x18003f890`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f9cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fa94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f9cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fa94`

## string_xrefs

- `0x18003f935`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003f976`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003f9ed`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003fab9`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`

## pseudocode

```c
__int64 __fastcall LaunchExePrivilegedAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  int FileName; // eax
  int v11; // edi
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  PCWSTR v14; // rax
  int inited; // eax
  __int64 v16; // rdx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rbx
  PCWSTR v19; // rax
  int v20; // eax
  HSTRING v22; // [rsp+20h] [rbp-50h] BYREF
  int v23; // [rsp+28h] [rbp-48h] BYREF
  HSTRING v24; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v26,
    LaunchExePrivilegedAction::s_exeNameTag);
  v6 = v5(v4, v26[0], &string);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 86;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      (const char *)(unsigned int)v6,
      (int)v22);
    goto LABEL_19;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1 + 80);
  *(_QWORD *)(a1 + 88) = -1;
  *(_QWORD *)(a1 + 96) = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  FileName = FileUtils::GetFileName(StringRawBuffer, (unsigned __int16 **)(a1 + 80));
  v11 = FileName;
  if ( FileName >= 0 )
  {
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
           a1 + 56,
           L"%s\\%s",
           *(_QWORD *)(*(_QWORD *)(a1 + 160) + 88LL),
           *(_QWORD *)(a1 + 80));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 95;
      goto LABEL_7;
    }
    v22 = 0;
    v12 = *a2;
    v13 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v26,
      LaunchExePrivilegedAction::s_argumentTag);
    if ( v13(v12, v26[0], &v22) < 0
      || (v14 = WindowsGetStringRawBuffer(v22, 0),
          inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                     a1 + 104,
                     v14,
                     -1),
          v7 = inited,
          inited >= 0) )
    {
      v23 = 0;
      JsonUtils::InitDwordFromJson(a2, L"Options", &v23);
      *(_DWORD *)(a1 + 128) = v23;
      inited = JsonUtils::InitDwordFromJson(a2, L"Timeout", a1 + 132);
      v7 = inited;
      if ( inited >= 0 )
      {
        v24 = 0;
        v17 = *a2;
        v18 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
        Windows::Internal::StringReference::_ConstructorHelper(
          (Windows::Internal::StringReference *)v26,
          LaunchExePrivilegedAction::s_expiryTag);
        if ( v18(v17, v26[0], &v24) < 0
          || (v19 = WindowsGetStringRawBuffer(v24, 0),
              v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      a1 + 136,
                      v19,
                      -1),
              v7 = v20,
              v20 >= 0) )
        {
          Windows::Internal::String::~String((Windows::Internal::String *)&v24);
          Windows::Internal::String::~String((Windows::Internal::String *)&v22);
          v7 = 0;
          goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
          (const char *)(unsigned int)v20,
          (int)v22);
        Windows::Internal::String::~String((Windows::Internal::String *)&v24);
        goto LABEL_12;
      }
      v16 = 110;
    }
    else
    {
      v16 = 101;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      (const char *)(unsigned int)inited,
      (int)v22);
LABEL_12:
    Windows::Internal::String::~String((Windows::Internal::String *)&v22);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
    (const char *)(unsigned int)FileName,
    (int)v22);
  v7 = v11;
LABEL_19:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v7;
}

```

## disassembly

```asm
0x18003f890  mov     [rsp-28h+arg_10], rbx
0x18003f895  push    rbp
0x18003f896  push    rsi
0x18003f897  push    rdi
0x18003f898  push    r12
0x18003f89a  push    r14
0x18003f89c  mov     rbp, rsp
0x18003f89f  sub     rsp, 70h
0x18003f8a3  mov     rax, cs:__security_cookie
0x18003f8aa  xor     rax, rsp
0x18003f8ad  mov     [rbp+var_10], rax
0x18003f8b1  mov     r14, rdx
0x18003f8b4  mov     rsi, rcx
0x18003f8b7  mov     [rbp+string], 0
0x18003f8bf  mov     rdi, [rdx]
0x18003f8c2  mov     rax, [rdi]
0x18003f8c5  mov     rbx, [rax+50h]
0x18003f8c9  mov     rdx, cs:?s_exeNameTag@LaunchExePrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003f8d0  lea     rcx, [rbp+var_30]; this
0x18003f8d4  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003f8d9  lea     r8, [rbp+string]
0x18003f8dd  mov     rdx, [rbp+var_30]
0x18003f8e1  mov     rcx, rdi
0x18003f8e4  mov     rax, rbx
0x18003f8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8ec  mov     ebx, eax
0x18003f8ee  test    eax, eax
0x18003f8f0  jns     short loc_18003F8F9
0x18003f8f2  mov     edx, 56h ; 'V'
0x18003f8f7  jmp     short loc_18003F976
0x18003f8f9  lea     rbx, [rsi+50h]
0x18003f8fd  mov     rcx, rbx
0x18003f900  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f905  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003f909  mov     [rbx+8], r12
0x18003f90d  mov     [rbx+10h], r12
0x18003f911  xor     edx, edx; length
0x18003f913  mov     rcx, [rbp+string]; string
0x18003f917  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f91d  mov     rdx, rbx; unsigned __int16 **
0x18003f920  mov     rcx, rax; unsigned __int16 *
0x18003f923  call    ?GetFileName@FileUtils@@SAJPEBGPEAPEAG@Z; FileUtils::GetFileName(ushort const *,ushort * *)
0x18003f928  mov     edi, eax
0x18003f92a  test    eax, eax
0x18003f92c  jns     short loc_18003F94D
0x18003f92e  mov     rcx, [rbp+28h]; this
0x18003f932  mov     r9d, eax; char *
0x18003f935  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003f93c  lea     edx, [r12+5Ch]; void *
0x18003f941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f946  mov     ebx, edi
0x18003f948  jmp     loc_18003FAEE
0x18003f94d  mov     r8, [rsi+0A0h]
0x18003f954  lea     rcx, [rsi+38h]
0x18003f958  mov     r9, [rbx]
0x18003f95b  mov     r8, [r8+58h]
0x18003f95f  lea     rdx, aSS_0; "%s\\%s"
0x18003f966  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18003f96b  mov     ebx, eax
0x18003f96d  test    eax, eax
0x18003f96f  jns     short loc_18003F98E
0x18003f971  mov     edx, 5Fh ; '_'; void *
0x18003f976  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003f97d  mov     r9d, eax; char *
0x18003f980  mov     rcx, [rbp+28h]; this
0x18003f984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f989  jmp     loc_18003FAEE
0x18003f98e  mov     [rbp+var_50], 0
0x18003f996  mov     rdi, [r14]
0x18003f999  mov     rax, [rdi]
0x18003f99c  mov     rbx, [rax+50h]
0x18003f9a0  mov     rdx, cs:?s_argumentTag@LaunchExePrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003f9a7  lea     rcx, [rbp+var_30]; this
0x18003f9ab  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003f9b0  lea     r8, [rbp+var_50]
0x18003f9b4  mov     rdx, [rbp+var_30]
0x18003f9b8  mov     rcx, rdi
0x18003f9bb  mov     rax, rbx
0x18003f9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9c3  test    eax, eax
0x18003f9c5  js      short loc_18003FA0F
0x18003f9c7  xor     edx, edx; length
0x18003f9c9  mov     rcx, [rbp+var_50]; string
0x18003f9cd  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f9d3  lea     rcx, [rsi+68h]
0x18003f9d7  mov     r8, r12
0x18003f9da  mov     rdx, rax
0x18003f9dd  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003f9e2  mov     ebx, eax
0x18003f9e4  test    eax, eax
0x18003f9e6  jns     short loc_18003FA0F
0x18003f9e8  mov     edx, 65h ; 'e'; void *
0x18003f9ed  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003f9f4  mov     r9d, eax; char *
0x18003f9f7  mov     rcx, [rbp+28h]; this
0x18003f9fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa00  nop
0x18003fa01  lea     rcx, [rbp+var_50]; this
0x18003fa05  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003fa0a  jmp     loc_18003FAEE
0x18003fa0f  mov     [rbp+var_48], 0
0x18003fa16  lea     r8, [rbp+var_48]
0x18003fa1a  lea     rdx, aOptions; "Options"
0x18003fa21  mov     rcx, r14
0x18003fa24  call    ?InitDwordFromJson@JsonUtils@@SAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; JsonUtils::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x18003fa29  mov     eax, [rbp+var_48]
0x18003fa2c  mov     [rsi+80h], eax
0x18003fa32  lea     r8, [rsi+84h]
0x18003fa39  lea     rdx, aTimeout; "Timeout"
0x18003fa40  mov     rcx, r14
0x18003fa43  call    ?InitDwordFromJson@JsonUtils@@SAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAK@Z; JsonUtils::InitDwordFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,ulong &)
0x18003fa48  mov     ebx, eax
0x18003fa4a  test    eax, eax
0x18003fa4c  jns     short loc_18003FA55
0x18003fa4e  mov     edx, 6Eh ; 'n'
0x18003fa53  jmp     short loc_18003F9ED
0x18003fa55  mov     [rbp+var_40], 0
0x18003fa5d  mov     rdi, [r14]
0x18003fa60  mov     rax, [rdi]
0x18003fa63  mov     rbx, [rax+50h]
0x18003fa67  mov     rdx, cs:?s_expiryTag@LaunchExePrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003fa6e  lea     rcx, [rbp+var_30]; this
0x18003fa72  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003fa77  lea     r8, [rbp+var_40]
0x18003fa7b  mov     rdx, [rbp+var_30]
0x18003fa7f  mov     rcx, rdi
0x18003fa82  mov     rax, rbx
0x18003fa85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa8a  test    eax, eax
0x18003fa8c  js      short loc_18003FAD9
0x18003fa8e  xor     edx, edx; length
0x18003fa90  mov     rcx, [rbp+var_40]; string
0x18003fa94  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fa9a  lea     rcx, [rsi+88h]
0x18003faa1  mov     r8, r12
0x18003faa4  mov     rdx, rax
0x18003faa7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003faac  mov     ebx, eax
0x18003faae  test    eax, eax
0x18003fab0  jns     short loc_18003FAD9
0x18003fab2  mov     rcx, [rbp+28h]; this
0x18003fab6  mov     r9d, eax; char *
0x18003fab9  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fac0  mov     edx, 74h ; 't'; void *
0x18003fac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003faca  nop
0x18003facb  lea     rcx, [rbp+var_40]; this
0x18003facf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003fad4  jmp     loc_18003FA01
0x18003fad9  lea     rcx, [rbp+var_40]; this
0x18003fadd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003fae2  nop
0x18003fae3  lea     rcx, [rbp+var_50]; this
0x18003fae7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003faec  xor     ebx, ebx
0x18003faee  lea     rcx, [rbp+string]; this
0x18003faf2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003faf7  mov     eax, ebx
0x18003faf9  mov     rcx, [rbp+var_10]
0x18003fafd  xor     rcx, rsp; StackCookie
0x18003fb00  call    __security_check_cookie
0x18003fb05  mov     rbx, [rsp+70h+arg_10]
0x18003fb0d  add     rsp, 70h
0x18003fb11  pop     r14
0x18003fb13  pop     r12
0x18003fb15  pop     rdi
0x18003fb16  pop     rsi
0x18003fb17  pop     rbp
0x18003fb18  retn
```

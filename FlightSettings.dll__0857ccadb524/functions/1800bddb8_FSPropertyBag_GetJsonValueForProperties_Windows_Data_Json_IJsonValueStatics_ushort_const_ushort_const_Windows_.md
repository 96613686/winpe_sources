# FSPropertyBag::GetJsonValueForProperties(Windows::Data::Json::IJsonValueStatics *,ushort const *,ushort const *,Windows::Data::Json::IJsonValue * *)

- ea: `0x1800bddb8`
- end: `0x1800be03b`
- name: `?GetJsonValueForProperties@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEBG1PEAPEAUIJsonValue@345@@Z`
- size: `643`
- prototype: `int(FSPropertyBag *__hidden this, struct Windows::Data::Json::IJsonValueStatics *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800be878`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180032640`
- `0x1800327e4`
- `0x18003290c`
- `0x18009bc00`
- `0x1800bddb8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bde71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdeda`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdf36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bde71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdeda`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bdf36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bde85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bdec1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bdf4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bde85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bdec1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bdf4a`

## string_xrefs

- `0x1800bde16`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bdfb1`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FSPropertyBag::GetJsonValueForProperties(
        FSPropertyBag *this,
        struct Windows::Data::Json::IJsonValueStatics *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Data::Json::IJsonValue **a5)
{
  __int64 *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  void (__fastcall *v11)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // r12
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64); // r13
  __int64 v16; // r12
  void (__fastcall *v17)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // rsi
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64); // rdi
  __int64 v20; // rbx
  HSTRING *v21; // rax
  int v22; // eax
  struct Windows::Data::Json::IJsonValue *v23; // rax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v26; // [rsp+28h] [rbp-48h] BYREF
  __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *a5 = 0;
  v29 = 0;
  v8 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])a2);
  v9 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v8, &v29);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v28 = 0;
    v11 = *(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    length = 0;
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    if ( (int)ULongLongToUInt(v13, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a3, length, &hstringHeader, &string);
    v11(a2, string, &v28);
    v14 = v29;
    v15 = (*v29)[7];
    v16 = v28;
    if ( WindowsCreateStringReference(L"key", 3u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v15(v14, (GUID *)string, v16);
    v27 = 0;
    v17 = *(void (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    length = 0;
    do
      ++v12;
    while ( a4[v12] );
    if ( (int)ULongLongToUInt(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a4, length, &hstringHeader, &string);
    v17(a2, string, &v27);
    v18 = v29;
    v19 = (*v29)[7];
    v20 = v27;
    v21 = Windows::Internal::StringReference::StringReference(&string, L"value");
    v19(v18, (GUID *)*v21, v20);
    v26 = 0;
    v22 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v29,
            (__int64)&v26);
    v10 = v22;
    if ( v22 >= 0 )
    {
      v23 = v26;
      v26 = 0;
      *a5 = v23;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A0,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v22,
        length);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x593,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v9,
      length);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  return v10;
}

```

## disassembly

```asm
0x1800bddb8  mov     [rsp-38h+arg_0], rbx
0x1800bddbd  push    rbp
0x1800bddbe  push    rsi
0x1800bddbf  push    rdi
0x1800bddc0  push    r12
0x1800bddc2  push    r13
0x1800bddc4  push    r14
0x1800bddc6  push    r15
0x1800bddc8  mov     rbp, rsp
0x1800bddcb  sub     rsp, 70h
0x1800bddcf  mov     rax, cs:__security_cookie
0x1800bddd6  xor     rax, rsp
0x1800bddd9  mov     [rbp+var_8], rax
0x1800bdddd  mov     r15, r9
0x1800bdde0  mov     rsi, r8
0x1800bdde3  mov     rdi, rdx
0x1800bdde6  mov     r14, [rbp+arg_20]
0x1800bddea  xor     r13d, r13d
0x1800bdded  mov     [r14], r13
0x1800bddf0  mov     [rbp+var_30], r13
0x1800bddf4  lea     rcx, [rbp+string]; string
0x1800bddf8  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800bddfd  lea     rdx, [rbp+var_30]
0x1800bde01  mov     rcx, [rax]
0x1800bde04  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800bde09  mov     ebx, eax
0x1800bde0b  test    eax, eax
0x1800bde0d  jns     short loc_1800BDE2C
0x1800bde0f  mov     rcx, [rbp+38h]; this
0x1800bde13  mov     r9d, eax; char *
0x1800bde16  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bde1d  mov     edx, 593h; void *
0x1800bde22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bde27  jmp     loc_1800BE00C
0x1800bde2c  mov     [rbp+var_38], r13
0x1800bde30  mov     rax, [rdi]
0x1800bde33  mov     r12, [rax+50h]
0x1800bde37  lea     rcx, [rbp+var_38]
0x1800bde3b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bde40  mov     [rbp+length], r13d
0x1800bde44  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bde48  mov     rcx, rbx
0x1800bde4b  inc     rcx; unsigned __int64
0x1800bde4e  cmp     [rsi+rcx*2], r13w
0x1800bde53  jnz     short loc_1800BDE4B
0x1800bde55  lea     rdx, [rbp+length]; unsigned int *
0x1800bde59  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bde5e  test    eax, eax
0x1800bde60  jns     short loc_1800BDE77
0x1800bde62  xor     r9d, r9d; lpArguments
0x1800bde65  xor     r8d, r8d; nNumberOfArguments
0x1800bde68  lea     edx, [r9+1]; dwExceptionFlags
0x1800bde6c  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bde71  call    cs:__imp_RaiseException
0x1800bde77  lea     r9, [rbp+string]; string
0x1800bde7b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bde7f  mov     edx, [rbp+length]; length
0x1800bde82  mov     rcx, rsi; sourceString
0x1800bde85  call    cs:__imp_WindowsCreateStringReference
0x1800bde8b  lea     r8, [rbp+var_38]
0x1800bde8f  mov     rdx, [rbp+string]
0x1800bde93  mov     rcx, rdi
0x1800bde96  mov     rax, r12
0x1800bde99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde9e  mov     rsi, [rbp+var_30]
0x1800bdea2  mov     rax, [rsi]
0x1800bdea5  mov     r13, [rax+38h]
0x1800bdea9  mov     r12, [rbp+var_38]
0x1800bdead  lea     r9, [rbp+string]; string
0x1800bdeb1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bdeb5  mov     edx, 3; length
0x1800bdeba  lea     rcx, aKey; "key"
0x1800bdec1  call    cs:__imp_WindowsCreateStringReference
0x1800bdec7  test    eax, eax
0x1800bdec9  jns     short loc_1800BDEE0
0x1800bdecb  xor     r9d, r9d; lpArguments
0x1800bdece  xor     r8d, r8d; nNumberOfArguments
0x1800bded1  lea     edx, [r9+1]; dwExceptionFlags
0x1800bded5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bdeda  call    cs:__imp_RaiseException
0x1800bdee0  mov     r8, r12
0x1800bdee3  mov     rdx, [rbp+string]
0x1800bdee7  mov     rcx, rsi
0x1800bdeea  mov     rax, r13
0x1800bdeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdef2  xor     r12d, r12d
0x1800bdef5  mov     [rbp+var_40], r12
0x1800bdef9  mov     rax, [rdi]
0x1800bdefc  mov     rsi, [rax+50h]
0x1800bdf00  lea     rcx, [rbp+var_40]
0x1800bdf04  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdf09  mov     [rbp+length], r12d
0x1800bdf0d  inc     rbx
0x1800bdf10  cmp     [r15+rbx*2], r12w
0x1800bdf15  jnz     short loc_1800BDF0D
0x1800bdf17  lea     rdx, [rbp+length]; unsigned int *
0x1800bdf1b  mov     rcx, rbx; unsigned __int64
0x1800bdf1e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bdf23  test    eax, eax
0x1800bdf25  jns     short loc_1800BDF3C
0x1800bdf27  xor     r9d, r9d; lpArguments
0x1800bdf2a  xor     r8d, r8d; nNumberOfArguments
0x1800bdf2d  lea     edx, [r9+1]; dwExceptionFlags
0x1800bdf31  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bdf36  call    cs:__imp_RaiseException
0x1800bdf3c  lea     r9, [rbp+string]; string
0x1800bdf40  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800bdf44  mov     edx, [rbp+length]; length
0x1800bdf47  mov     rcx, r15; sourceString
0x1800bdf4a  call    cs:__imp_WindowsCreateStringReference
0x1800bdf50  lea     r8, [rbp+var_40]
0x1800bdf54  mov     rdx, [rbp+string]
0x1800bdf58  mov     rcx, rdi
0x1800bdf5b  mov     rax, rsi
0x1800bdf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdf63  mov     rsi, [rbp+var_30]
0x1800bdf67  mov     rax, [rsi]
0x1800bdf6a  mov     rdi, [rax+38h]
0x1800bdf6e  mov     rbx, [rbp+var_40]
0x1800bdf72  lea     rdx, aValue_0; "value"
0x1800bdf79  lea     rcx, [rbp+string]; string
0x1800bdf7d  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x1800bdf82  mov     r8, rbx
0x1800bdf85  mov     rdx, [rax]
0x1800bdf88  mov     rcx, rsi
0x1800bdf8b  mov     rax, rdi
0x1800bdf8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdf93  mov     [rbp+var_48], r12
0x1800bdf97  lea     rdx, [rbp+var_48]
0x1800bdf9b  lea     rcx, [rbp+var_30]
0x1800bdf9f  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800bdfa4  mov     ebx, eax
0x1800bdfa6  test    eax, eax
0x1800bdfa8  jns     short loc_1800BDFE1
0x1800bdfaa  mov     rcx, [rbp+38h]; this
0x1800bdfae  mov     r9d, eax; char *
0x1800bdfb1  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bdfb8  mov     edx, 5A0h; void *
0x1800bdfbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdfc2  lea     rcx, [rbp+var_48]
0x1800bdfc6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdfcb  nop
0x1800bdfcc  lea     rcx, [rbp+var_40]
0x1800bdfd0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdfd5  nop
0x1800bdfd6  lea     rcx, [rbp+var_38]
0x1800bdfda  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdfdf  jmp     short loc_1800BE00C
0x1800bdfe1  mov     rax, [rbp+var_48]
0x1800bdfe5  mov     [rbp+var_48], r12
0x1800bdfe9  mov     [r14], rax
0x1800bdfec  lea     rcx, [rbp+var_48]
0x1800bdff0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdff5  nop
0x1800bdff6  lea     rcx, [rbp+var_40]
0x1800bdffa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bdfff  nop
0x1800be000  lea     rcx, [rbp+var_38]
0x1800be004  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be009  mov     ebx, r12d
0x1800be00c  lea     rcx, [rbp+var_30]
0x1800be010  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be015  mov     eax, ebx
0x1800be017  mov     rcx, [rbp+var_8]
0x1800be01b  xor     rcx, rsp; StackCookie
0x1800be01e  call    __security_check_cookie
0x1800be023  mov     rbx, [rsp+70h+arg_0]
0x1800be02b  add     rsp, 70h
0x1800be02f  pop     r15
0x1800be031  pop     r14
0x1800be033  pop     r13
0x1800be035  pop     r12
0x1800be037  pop     rdi
0x1800be038  pop     rsi
0x1800be039  pop     rbp
0x1800be03a  retn
```

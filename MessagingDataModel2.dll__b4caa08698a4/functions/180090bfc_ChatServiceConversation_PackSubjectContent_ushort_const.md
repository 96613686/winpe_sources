# ChatServiceConversation::_PackSubjectContent(ushort const *)

- ea: `0x180090bfc`
- end: `0x180090ebc`
- name: `?_PackSubjectContent@ChatServiceConversation@@AEAAJPEBG@Z`
- size: `704`
- prototype: `__int64 __fastcall(ChatServiceConversation *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008fd90`

## callees

- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x18008f830`
- `0x180090bfc`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090cde`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090cde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090e5d`

## string_xrefs

- `0x180090cbf`: `Windows.Data.Json.JsonValue`
- `0x180090c30`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceConversation::_PackSubjectContent(
        ChatServiceConversation *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int ActivationFactory; // eax
  char v7; // r8
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  char v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  int v21; // ecx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h]
  const WCHAR *v26; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v27[8]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+68h] [rbp-1h] BYREF
  __int64 v30; // [rsp+70h] [rbp+7h] BYREF
  __int64 v31; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+80h] [rbp+17h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp+1Fh] BYREF

  v26 = a2;
  v33 = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v25, &v33);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v28 = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
           &v33,
           (__int64)&v28);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v30 = 0;
      v25 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v25, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v30);
      v4 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v8 = v30;
        v31 = 0;
        v9 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v30 + 80LL);
        v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26, v7);
        v11 = v9(v8, v10[1].Reserved.Reserved1, &v31);
        v4 = v11;
        if ( v11 < 0
          || (v13 = v28,
              v14 = v31,
              v27[0] = 0,
              v15 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v28 + 80LL),
              v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_1800FD680,
                      v12),
              v11 = v15(v13, v16[1].Reserved.Reserved1, v14, v27),
              v4 = v11,
              v11 < 0) )
        {
          Log_HREvent_67(v11);
        }
        else
        {
          v32 = 0;
          v17 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v33,
                  (__int64)&v32);
          v4 = v17;
          if ( v17 >= 0 )
          {
            v18 = v32;
            string = 0;
            v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 56LL);
            WindowsDeleteString(0);
            string = 0;
            v20 = v19(v18, &string);
            v4 = v20;
            if ( v20 >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                      (char *)this + 312,
                                      StringRawBuffer) )
              {
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                v4 = 0;
                goto LABEL_22;
              }
              v4 = -2147024882;
              v21 = -2147024882;
            }
            else
            {
              v21 = v20;
            }
            Log_HREvent_67(v21);
            WindowsDeleteString(string);
            string = 0;
          }
          else
          {
            Log_HREvent_67(v17);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      }
      else
      {
        Log_HREvent_67(ActivationFactory);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    }
    else
    {
      Log_HREvent_67(v5);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  }
  else
  {
    Log_HREvent_67(v3);
  }
LABEL_22:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  return v4;
}

```

## disassembly

```asm
0x180090bfc  mov     [rsp-8+arg_10], rbx
0x180090c01  push    rbp
0x180090c02  push    rsi
0x180090c03  push    rdi
0x180090c04  push    r14
0x180090c06  push    r15
0x180090c08  lea     rbp, [rsp-37h]
0x180090c0d  sub     rsp, 0A0h
0x180090c14  mov     rax, cs:__security_cookie
0x180090c1b  xor     rax, rsp
0x180090c1e  mov     [rbp+57h+var_30], rax
0x180090c22  xor     r15d, r15d
0x180090c25  mov     [rbp+57h+var_70], rdx
0x180090c29  mov     r14, rcx
0x180090c2c  mov     [rbp+57h+var_38], r15
0x180090c30  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180090c37  mov     [rbp+57h+var_78], r15
0x180090c3b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180090c3f  lea     edi, [r15+1Ch]
0x180090c43  mov     r9d, edi; unsigned int
0x180090c46  lea     r8d, [r15+1Dh]; unsigned int
0x180090c4a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090c4f  mov     rcx, [rbp+57h+var_78]
0x180090c53  lea     rdx, [rbp+57h+var_38]
0x180090c57  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180090c5c  mov     ebx, eax
0x180090c5e  test    eax, eax
0x180090c60  jns     short loc_180090C77
0x180090c62  lea     edx, [rdi-1Bh]
0x180090c65  mov     r9d, 18Ah
0x180090c6b  mov     ecx, eax; int
0x180090c6d  call    Log_HREvent_67
0x180090c72  jmp     loc_180090E8E
0x180090c77  lea     rdx, [rbp+57h+var_60]
0x180090c7b  mov     [rbp+57h+var_60], r15
0x180090c7f  lea     rcx, [rbp+57h+var_38]
0x180090c83  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180090c88  mov     ebx, eax
0x180090c8a  test    eax, eax
0x180090c8c  jns     short loc_180090CAE
0x180090c8e  mov     edx, 1
0x180090c93  mov     r9d, 18Dh
0x180090c99  mov     ecx, eax; int
0x180090c9b  call    Log_HREvent_67
0x180090ca0  lea     rcx, [rbp+57h+var_60]
0x180090ca4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090ca9  jmp     loc_180090E8E
0x180090cae  mov     r9d, 1Bh; unsigned int
0x180090cb4  mov     [rbp+57h+var_50], r15
0x180090cb8  mov     r8d, edi; unsigned int
0x180090cbb  mov     [rbp+57h+var_78], r15
0x180090cbf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180090cc6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180090cca  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090ccf  mov     rcx, [rbp+57h+var_78]
0x180090cd3  lea     r8, [rbp+57h+var_50]
0x180090cd7  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180090cde  call    cs:__imp_RoGetActivationFactory
0x180090ce4  mov     ebx, eax
0x180090ce6  test    eax, eax
0x180090ce8  jns     short loc_180090D07
0x180090cea  mov     edx, 1
0x180090cef  mov     r9d, 191h
0x180090cf5  mov     ecx, eax; int
0x180090cf7  call    Log_HREvent_67
0x180090cfc  lea     rcx, [rbp+57h+var_50]
0x180090d00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090d05  jmp     short loc_180090CA0
0x180090d07  mov     rdi, [rbp+57h+var_50]
0x180090d0b  lea     rdx, [rbp+57h+var_70]
0x180090d0f  mov     [rbp+57h+var_48], r15
0x180090d13  lea     rcx, [rbp+57h+hstringHeader]
0x180090d17  mov     rax, [rdi]
0x180090d1a  mov     rbx, [rax+50h]
0x180090d1e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090d23  lea     r8, [rbp+57h+var_48]
0x180090d27  mov     rcx, rdi
0x180090d2a  mov     rdx, [rax+18h]
0x180090d2e  mov     rax, rbx
0x180090d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d36  mov     ebx, eax
0x180090d38  test    eax, eax
0x180090d3a  jns     short loc_180090D59
0x180090d3c  mov     r9d, 194h
0x180090d42  mov     edx, 1
0x180090d47  mov     ecx, eax; int
0x180090d49  call    Log_HREvent_67
0x180090d4e  lea     rcx, [rbp+57h+var_48]
0x180090d52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090d57  jmp     short loc_180090CFC
0x180090d59  mov     rsi, [rbp+57h+var_60]
0x180090d5d  lea     rdx, off_1800FD680; "subject"
0x180090d64  mov     rbx, [rbp+57h+var_48]
0x180090d68  lea     rcx, [rbp+57h+hstringHeader]
0x180090d6c  mov     [rbp+57h+var_68], r15b
0x180090d70  mov     rax, [rsi]
0x180090d73  mov     rdi, [rax+50h]
0x180090d77  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090d7c  lea     r9, [rbp+57h+var_68]
0x180090d80  mov     r8, rbx
0x180090d83  mov     rcx, rsi
0x180090d86  mov     rdx, [rax+18h]
0x180090d8a  mov     rax, rdi
0x180090d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d92  mov     ebx, eax
0x180090d94  test    eax, eax
0x180090d96  jns     short loc_180090DA0
0x180090d98  mov     r9d, 197h
0x180090d9e  jmp     short loc_180090D42
0x180090da0  lea     rdx, [rbp+57h+var_40]
0x180090da4  mov     [rbp+57h+var_40], r15
0x180090da8  lea     rcx, [rbp+57h+var_38]
0x180090dac  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180090db1  mov     ebx, eax
0x180090db3  test    eax, eax
0x180090db5  jns     short loc_180090DD7
0x180090db7  mov     edx, 1
0x180090dbc  mov     r9d, 19Ah
0x180090dc2  mov     ecx, eax; int
0x180090dc4  call    Log_HREvent_67
0x180090dc9  lea     rcx, [rbp+57h+var_40]
0x180090dcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090dd2  jmp     loc_180090D4E
0x180090dd7  mov     rdi, [rbp+57h+var_40]
0x180090ddb  xor     ecx, ecx; string
0x180090ddd  mov     [rbp+57h+string], r15
0x180090de1  mov     rax, [rdi]
0x180090de4  mov     rbx, [rax+38h]
0x180090de8  call    cs:__imp_WindowsDeleteString
0x180090dee  lea     rdx, [rbp+57h+string]
0x180090df2  mov     [rbp+57h+string], r15
0x180090df6  mov     rcx, rdi
0x180090df9  mov     rax, rbx
0x180090dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090e01  mov     ebx, eax
0x180090e03  test    eax, eax
0x180090e05  jns     short loc_180090E29
0x180090e07  mov     edx, 1
0x180090e0c  mov     r9d, 19Dh
0x180090e12  mov     ecx, eax; int
0x180090e14  call    Log_HREvent_67
0x180090e19  mov     rcx, [rbp+57h+string]; string
0x180090e1d  call    cs:__imp_WindowsDeleteString
0x180090e23  mov     [rbp+57h+string], r15
0x180090e27  jmp     short loc_180090DC9
0x180090e29  mov     rcx, [rbp+57h+string]; string
0x180090e2d  xor     edx, edx; length
0x180090e2f  call    cs:__imp_WindowsGetStringRawBuffer
0x180090e35  mov     rdx, rax
0x180090e38  lea     rcx, [r14+138h]
0x180090e3f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180090e44  test    al, al
0x180090e46  jnz     short loc_180090E59
0x180090e48  mov     ebx, 8007000Eh
0x180090e4d  xor     edx, edx
0x180090e4f  mov     ecx, ebx
0x180090e51  mov     r9d, 19Fh
0x180090e57  jmp     short loc_180090E14
0x180090e59  mov     rcx, [rbp+57h+string]; string
0x180090e5d  call    cs:__imp_WindowsDeleteString
0x180090e63  lea     rcx, [rbp+57h+var_40]
0x180090e67  mov     [rbp+57h+string], r15
0x180090e6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090e70  lea     rcx, [rbp+57h+var_48]
0x180090e74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090e79  lea     rcx, [rbp+57h+var_50]
0x180090e7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090e82  lea     rcx, [rbp+57h+var_60]
0x180090e86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090e8b  mov     ebx, r15d
0x180090e8e  lea     rcx, [rbp+57h+var_38]
0x180090e92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090e97  mov     eax, ebx
0x180090e99  mov     rcx, [rbp+57h+var_30]
0x180090e9d  xor     rcx, rsp; StackCookie
0x180090ea0  call    __security_check_cookie
0x180090ea5  mov     rbx, [rsp+0C0h+arg_10]
0x180090ead  add     rsp, 0A0h
0x180090eb4  pop     r15
0x180090eb6  pop     r14
0x180090eb8  pop     rdi
0x180090eb9  pop     rsi
0x180090eba  pop     rbp
0x180090ebb  retn
```

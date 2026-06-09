# ChatServiceConversation::_PackParticipantsContent(ushort const *)

- ea: `0x180090934`
- end: `0x180090bf4`
- name: `?_PackParticipantsContent@ChatServiceConversation@@AEAAJPEBG@Z`
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
- `0x180090934`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090a16`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090b95`

## string_xrefs

- `0x1800909f7`: `Windows.Data.Json.JsonValue`
- `0x180090968`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceConversation::_PackParticipantsContent(
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
                      (const WCHAR **)off_1800FD6A0,
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
                                      (char *)this + 192,
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
0x180090934  mov     [rsp-8+arg_10], rbx
0x180090939  push    rbp
0x18009093a  push    rsi
0x18009093b  push    rdi
0x18009093c  push    r14
0x18009093e  push    r15
0x180090940  lea     rbp, [rsp-37h]
0x180090945  sub     rsp, 0A0h
0x18009094c  mov     rax, cs:__security_cookie
0x180090953  xor     rax, rsp
0x180090956  mov     [rbp+57h+var_30], rax
0x18009095a  xor     r15d, r15d
0x18009095d  mov     [rbp+57h+var_70], rdx
0x180090961  mov     r14, rcx
0x180090964  mov     [rbp+57h+var_38], r15
0x180090968  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18009096f  mov     [rbp+57h+var_78], r15
0x180090973  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180090977  lea     edi, [r15+1Ch]
0x18009097b  mov     r9d, edi; unsigned int
0x18009097e  lea     r8d, [r15+1Dh]; unsigned int
0x180090982  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090987  mov     rcx, [rbp+57h+var_78]
0x18009098b  lea     rdx, [rbp+57h+var_38]
0x18009098f  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180090994  mov     ebx, eax
0x180090996  test    eax, eax
0x180090998  jns     short loc_1800909AF
0x18009099a  lea     edx, [rdi-1Bh]
0x18009099d  mov     r9d, 141h
0x1800909a3  mov     ecx, eax; int
0x1800909a5  call    Log_HREvent_67
0x1800909aa  jmp     loc_180090BC6
0x1800909af  lea     rdx, [rbp+57h+var_60]
0x1800909b3  mov     [rbp+57h+var_60], r15
0x1800909b7  lea     rcx, [rbp+57h+var_38]
0x1800909bb  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800909c0  mov     ebx, eax
0x1800909c2  test    eax, eax
0x1800909c4  jns     short loc_1800909E6
0x1800909c6  mov     edx, 1
0x1800909cb  mov     r9d, 144h
0x1800909d1  mov     ecx, eax; int
0x1800909d3  call    Log_HREvent_67
0x1800909d8  lea     rcx, [rbp+57h+var_60]
0x1800909dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800909e1  jmp     loc_180090BC6
0x1800909e6  mov     r9d, 1Bh; unsigned int
0x1800909ec  mov     [rbp+57h+var_50], r15
0x1800909f0  mov     r8d, edi; unsigned int
0x1800909f3  mov     [rbp+57h+var_78], r15
0x1800909f7  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800909fe  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180090a02  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090a07  mov     rcx, [rbp+57h+var_78]
0x180090a0b  lea     r8, [rbp+57h+var_50]
0x180090a0f  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180090a16  call    cs:__imp_RoGetActivationFactory
0x180090a1c  mov     ebx, eax
0x180090a1e  test    eax, eax
0x180090a20  jns     short loc_180090A3F
0x180090a22  mov     edx, 1
0x180090a27  mov     r9d, 148h
0x180090a2d  mov     ecx, eax; int
0x180090a2f  call    Log_HREvent_67
0x180090a34  lea     rcx, [rbp+57h+var_50]
0x180090a38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090a3d  jmp     short loc_1800909D8
0x180090a3f  mov     rdi, [rbp+57h+var_50]
0x180090a43  lea     rdx, [rbp+57h+var_70]
0x180090a47  mov     [rbp+57h+var_48], r15
0x180090a4b  lea     rcx, [rbp+57h+hstringHeader]
0x180090a4f  mov     rax, [rdi]
0x180090a52  mov     rbx, [rax+50h]
0x180090a56  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090a5b  lea     r8, [rbp+57h+var_48]
0x180090a5f  mov     rcx, rdi
0x180090a62  mov     rdx, [rax+18h]
0x180090a66  mov     rax, rbx
0x180090a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090a6e  mov     ebx, eax
0x180090a70  test    eax, eax
0x180090a72  jns     short loc_180090A91
0x180090a74  mov     r9d, 14Ch
0x180090a7a  mov     edx, 1
0x180090a7f  mov     ecx, eax; int
0x180090a81  call    Log_HREvent_67
0x180090a86  lea     rcx, [rbp+57h+var_48]
0x180090a8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090a8f  jmp     short loc_180090A34
0x180090a91  mov     rsi, [rbp+57h+var_60]
0x180090a95  lea     rdx, off_1800FD6A0; "participants"
0x180090a9c  mov     rbx, [rbp+57h+var_48]
0x180090aa0  lea     rcx, [rbp+57h+hstringHeader]
0x180090aa4  mov     [rbp+57h+var_68], r15b
0x180090aa8  mov     rax, [rsi]
0x180090aab  mov     rdi, [rax+50h]
0x180090aaf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090ab4  lea     r9, [rbp+57h+var_68]
0x180090ab8  mov     r8, rbx
0x180090abb  mov     rcx, rsi
0x180090abe  mov     rdx, [rax+18h]
0x180090ac2  mov     rax, rdi
0x180090ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090aca  mov     ebx, eax
0x180090acc  test    eax, eax
0x180090ace  jns     short loc_180090AD8
0x180090ad0  mov     r9d, 14Fh
0x180090ad6  jmp     short loc_180090A7A
0x180090ad8  lea     rdx, [rbp+57h+var_40]
0x180090adc  mov     [rbp+57h+var_40], r15
0x180090ae0  lea     rcx, [rbp+57h+var_38]
0x180090ae4  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180090ae9  mov     ebx, eax
0x180090aeb  test    eax, eax
0x180090aed  jns     short loc_180090B0F
0x180090aef  mov     edx, 1
0x180090af4  mov     r9d, 152h
0x180090afa  mov     ecx, eax; int
0x180090afc  call    Log_HREvent_67
0x180090b01  lea     rcx, [rbp+57h+var_40]
0x180090b05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090b0a  jmp     loc_180090A86
0x180090b0f  mov     rdi, [rbp+57h+var_40]
0x180090b13  xor     ecx, ecx; string
0x180090b15  mov     [rbp+57h+string], r15
0x180090b19  mov     rax, [rdi]
0x180090b1c  mov     rbx, [rax+38h]
0x180090b20  call    cs:__imp_WindowsDeleteString
0x180090b26  lea     rdx, [rbp+57h+string]
0x180090b2a  mov     [rbp+57h+string], r15
0x180090b2e  mov     rcx, rdi
0x180090b31  mov     rax, rbx
0x180090b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090b39  mov     ebx, eax
0x180090b3b  test    eax, eax
0x180090b3d  jns     short loc_180090B61
0x180090b3f  mov     edx, 1
0x180090b44  mov     r9d, 155h
0x180090b4a  mov     ecx, eax; int
0x180090b4c  call    Log_HREvent_67
0x180090b51  mov     rcx, [rbp+57h+string]; string
0x180090b55  call    cs:__imp_WindowsDeleteString
0x180090b5b  mov     [rbp+57h+string], r15
0x180090b5f  jmp     short loc_180090B01
0x180090b61  mov     rcx, [rbp+57h+string]; string
0x180090b65  xor     edx, edx; length
0x180090b67  call    cs:__imp_WindowsGetStringRawBuffer
0x180090b6d  mov     rdx, rax
0x180090b70  lea     rcx, [r14+0C0h]
0x180090b77  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180090b7c  test    al, al
0x180090b7e  jnz     short loc_180090B91
0x180090b80  mov     ebx, 8007000Eh
0x180090b85  xor     edx, edx
0x180090b87  mov     ecx, ebx
0x180090b89  mov     r9d, 157h
0x180090b8f  jmp     short loc_180090B4C
0x180090b91  mov     rcx, [rbp+57h+string]; string
0x180090b95  call    cs:__imp_WindowsDeleteString
0x180090b9b  lea     rcx, [rbp+57h+var_40]
0x180090b9f  mov     [rbp+57h+string], r15
0x180090ba3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090ba8  lea     rcx, [rbp+57h+var_48]
0x180090bac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090bb1  lea     rcx, [rbp+57h+var_50]
0x180090bb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090bba  lea     rcx, [rbp+57h+var_60]
0x180090bbe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090bc3  mov     ebx, r15d
0x180090bc6  lea     rcx, [rbp+57h+var_38]
0x180090bca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090bcf  mov     eax, ebx
0x180090bd1  mov     rcx, [rbp+57h+var_30]
0x180090bd5  xor     rcx, rsp; StackCookie
0x180090bd8  call    __security_check_cookie
0x180090bdd  mov     rbx, [rsp+0C0h+arg_10]
0x180090be5  add     rsp, 0A0h
0x180090bec  pop     r15
0x180090bee  pop     r14
0x180090bf0  pop     rdi
0x180090bf1  pop     rsi
0x180090bf2  pop     rbp
0x180090bf3  retn
```

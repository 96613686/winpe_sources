# AsyncMediaServiceDocument::_GenerateCreationContent(void)

- ea: `0x1800972d0`
- end: `0x180097582`
- name: `?_GenerateCreationContent@AsyncMediaServiceDocument@@AEAAJXZ`
- size: `690`
- prototype: `__int64 __fastcall(AsyncMediaServiceDocument *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800976e0`

## callees

- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x180096cac`
- `0x1800972d0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800973ab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800973ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800974ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800974ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800974b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800974ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009752a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800974b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800974ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009752a`

## string_xrefs

- `0x18009738c`: `Windows.Data.Json.JsonValue`
- `0x1800972f6`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceDocument::_GenerateCreationContent(AsyncMediaServiceDocument *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int ActivationFactory; // eax
  char v6; // r8
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  char v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  int v20; // ecx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-39h] BYREF
  __int64 v24; // [rsp+48h] [rbp-21h]
  _BYTE v25[8]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v26; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  __int64 v28; // [rsp+68h] [rbp-1h] BYREF
  __int64 v29; // [rsp+70h] [rbp+7h] BYREF
  __int64 v30; // [rsp+78h] [rbp+Fh] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp+17h] BYREF

  v31 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v2 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v24, &v31);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v26 = 0;
    v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
           &v31,
           (__int64)&v26);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v28 = 0;
      v24 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v24, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v28);
      v3 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v7 = v28;
        v29 = 0;
        v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v28 + 80LL);
        v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
               &hstringHeader,
               (const WCHAR **)off_1800FD780,
               v6);
        v10 = v8(v7, v9[1].Reserved.Reserved1, &v29);
        v3 = v10;
        if ( v10 < 0
          || (v12 = v26,
              v13 = v29,
              v25[0] = 0,
              v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v26 + 80LL),
              v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_1800FD790,
                      v11),
              v10 = v14(v12, v15[1].Reserved.Reserved1, v13, v25),
              v3 = v10,
              v10 < 0) )
        {
          Log_HREvent_69(v10);
        }
        else
        {
          v30 = 0;
          v16 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v31,
                  (__int64)&v30);
          v3 = v16;
          if ( v16 >= 0 )
          {
            v17 = v30;
            string = 0;
            v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 56LL);
            WindowsDeleteString(0);
            string = 0;
            v19 = v18(v17, &string);
            v3 = v19;
            if ( v19 >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                      (char *)this + 96,
                                      StringRawBuffer) )
              {
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
                v3 = 0;
                goto LABEL_22;
              }
              v3 = -2147024882;
              v20 = -2147024882;
            }
            else
            {
              v20 = v19;
            }
            Log_HREvent_69(v20);
            WindowsDeleteString(string);
            string = 0;
          }
          else
          {
            Log_HREvent_69(v16);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      }
      else
      {
        Log_HREvent_69(ActivationFactory);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    }
    else
    {
      Log_HREvent_69(v4);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  }
  else
  {
    Log_HREvent_69(v2);
  }
LABEL_22:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return v3;
}

```

## disassembly

```asm
0x1800972d0  push    rbp
0x1800972d2  push    rbx
0x1800972d3  push    rsi
0x1800972d4  push    rdi
0x1800972d5  push    r14
0x1800972d7  push    r15
0x1800972d9  lea     rbp, [rsp-2Fh]
0x1800972de  sub     rsp, 98h
0x1800972e5  mov     rax, cs:__security_cookie
0x1800972ec  xor     rax, rsp
0x1800972ef  mov     [rbp+57h+var_38], rax
0x1800972f3  xor     r15d, r15d
0x1800972f6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800972fd  mov     r14, rcx
0x180097300  mov     [rbp+57h+var_40], r15
0x180097304  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180097308  mov     [rbp+57h+var_78], r15
0x18009730c  lea     edi, [r15+1Ch]
0x180097310  mov     r9d, edi; unsigned int
0x180097313  lea     r8d, [r15+1Dh]; unsigned int
0x180097317  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009731c  mov     rcx, [rbp+57h+var_78]
0x180097320  lea     rdx, [rbp+57h+var_40]
0x180097324  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180097329  mov     ebx, eax
0x18009732b  test    eax, eax
0x18009732d  jns     short loc_180097344
0x18009732f  lea     edx, [rdi-1Bh]
0x180097332  mov     r9d, 146h
0x180097338  mov     ecx, eax; int
0x18009733a  call    Log_HREvent_69
0x18009733f  jmp     loc_18009755B
0x180097344  lea     rdx, [rbp+57h+var_68]
0x180097348  mov     [rbp+57h+var_68], r15
0x18009734c  lea     rcx, [rbp+57h+var_40]
0x180097350  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180097355  mov     ebx, eax
0x180097357  test    eax, eax
0x180097359  jns     short loc_18009737B
0x18009735b  mov     edx, 1
0x180097360  mov     r9d, 149h
0x180097366  mov     ecx, eax; int
0x180097368  call    Log_HREvent_69
0x18009736d  lea     rcx, [rbp+57h+var_68]
0x180097371  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097376  jmp     loc_18009755B
0x18009737b  mov     r9d, 1Bh; unsigned int
0x180097381  mov     [rbp+57h+var_58], r15
0x180097385  mov     r8d, edi; unsigned int
0x180097388  mov     [rbp+57h+var_78], r15
0x18009738c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180097393  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180097397  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009739c  mov     rcx, [rbp+57h+var_78]
0x1800973a0  lea     r8, [rbp+57h+var_58]
0x1800973a4  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800973ab  call    cs:__imp_RoGetActivationFactory
0x1800973b1  mov     ebx, eax
0x1800973b3  test    eax, eax
0x1800973b5  jns     short loc_1800973D4
0x1800973b7  mov     edx, 1
0x1800973bc  mov     r9d, 14Dh
0x1800973c2  mov     ecx, eax; int
0x1800973c4  call    Log_HREvent_69
0x1800973c9  lea     rcx, [rbp+57h+var_58]
0x1800973cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800973d2  jmp     short loc_18009736D
0x1800973d4  mov     rdi, [rbp+57h+var_58]
0x1800973d8  lea     rdx, off_1800FD780; "win_msg/media"
0x1800973df  mov     [rbp+57h+var_50], r15
0x1800973e3  lea     rcx, [rbp+57h+hstringHeader]
0x1800973e7  mov     rax, [rdi]
0x1800973ea  mov     rbx, [rax+50h]
0x1800973ee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800973f3  lea     r8, [rbp+57h+var_50]
0x1800973f7  mov     rcx, rdi
0x1800973fa  mov     rdx, [rax+18h]
0x1800973fe  mov     rax, rbx
0x180097401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097406  mov     ebx, eax
0x180097408  test    eax, eax
0x18009740a  jns     short loc_180097429
0x18009740c  mov     r9d, 151h
0x180097412  mov     edx, 1
0x180097417  mov     ecx, eax; int
0x180097419  call    Log_HREvent_69
0x18009741e  lea     rcx, [rbp+57h+var_50]
0x180097422  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097427  jmp     short loc_1800973C9
0x180097429  mov     rsi, [rbp+57h+var_68]
0x18009742d  lea     rdx, off_1800FD790; "type"
0x180097434  mov     rbx, [rbp+57h+var_50]
0x180097438  lea     rcx, [rbp+57h+hstringHeader]
0x18009743c  mov     [rbp+57h+var_70], r15b
0x180097440  mov     rax, [rsi]
0x180097443  mov     rdi, [rax+50h]
0x180097447  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009744c  lea     r9, [rbp+57h+var_70]
0x180097450  mov     r8, rbx
0x180097453  mov     rcx, rsi
0x180097456  mov     rdx, [rax+18h]
0x18009745a  mov     rax, rdi
0x18009745d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097462  mov     ebx, eax
0x180097464  test    eax, eax
0x180097466  jns     short loc_180097470
0x180097468  mov     r9d, 154h
0x18009746e  jmp     short loc_180097412
0x180097470  lea     rdx, [rbp+57h+var_48]
0x180097474  mov     [rbp+57h+var_48], r15
0x180097478  lea     rcx, [rbp+57h+var_40]
0x18009747c  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180097481  mov     ebx, eax
0x180097483  test    eax, eax
0x180097485  jns     short loc_1800974A7
0x180097487  mov     edx, 1
0x18009748c  mov     r9d, 157h
0x180097492  mov     ecx, eax; int
0x180097494  call    Log_HREvent_69
0x180097499  lea     rcx, [rbp+57h+var_48]
0x18009749d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800974a2  jmp     loc_18009741E
0x1800974a7  mov     rdi, [rbp+57h+var_48]
0x1800974ab  xor     ecx, ecx; string
0x1800974ad  mov     [rbp+57h+string], r15
0x1800974b1  mov     rax, [rdi]
0x1800974b4  mov     rbx, [rax+38h]
0x1800974b8  call    cs:__imp_WindowsDeleteString
0x1800974be  lea     rdx, [rbp+57h+string]
0x1800974c2  mov     [rbp+57h+string], r15
0x1800974c6  mov     rcx, rdi
0x1800974c9  mov     rax, rbx
0x1800974cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800974d1  mov     ebx, eax
0x1800974d3  test    eax, eax
0x1800974d5  jns     short loc_1800974F9
0x1800974d7  mov     edx, 1
0x1800974dc  mov     r9d, 15Ah
0x1800974e2  mov     ecx, eax; int
0x1800974e4  call    Log_HREvent_69
0x1800974e9  mov     rcx, [rbp+57h+string]; string
0x1800974ed  call    cs:__imp_WindowsDeleteString
0x1800974f3  mov     [rbp+57h+string], r15
0x1800974f7  jmp     short loc_180097499
0x1800974f9  mov     rcx, [rbp+57h+string]; string
0x1800974fd  xor     edx, edx; length
0x1800974ff  call    cs:__imp_WindowsGetStringRawBuffer
0x180097505  mov     rdx, rax
0x180097508  lea     rcx, [r14+60h]
0x18009750c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180097511  test    al, al
0x180097513  jnz     short loc_180097526
0x180097515  mov     ebx, 8007000Eh
0x18009751a  xor     edx, edx
0x18009751c  mov     ecx, ebx
0x18009751e  mov     r9d, 15Ch
0x180097524  jmp     short loc_1800974E4
0x180097526  mov     rcx, [rbp+57h+string]; string
0x18009752a  call    cs:__imp_WindowsDeleteString
0x180097530  lea     rcx, [rbp+57h+var_48]
0x180097534  mov     [rbp+57h+string], r15
0x180097538  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009753d  lea     rcx, [rbp+57h+var_50]
0x180097541  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097546  lea     rcx, [rbp+57h+var_58]
0x18009754a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009754f  lea     rcx, [rbp+57h+var_68]
0x180097553  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097558  mov     ebx, r15d
0x18009755b  lea     rcx, [rbp+57h+var_40]
0x18009755f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097564  mov     eax, ebx
0x180097566  mov     rcx, [rbp+57h+var_38]
0x18009756a  xor     rcx, rsp; StackCookie
0x18009756d  call    __security_check_cookie
0x180097572  add     rsp, 98h
0x180097579  pop     r15
0x18009757b  pop     r14
0x18009757d  pop     rdi
0x18009757e  pop     rsi
0x18009757f  pop     rbx
0x180097580  pop     rbp
0x180097581  retn
```

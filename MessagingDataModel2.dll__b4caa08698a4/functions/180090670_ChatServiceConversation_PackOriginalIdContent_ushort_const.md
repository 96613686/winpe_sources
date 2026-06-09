# ChatServiceConversation::_PackOriginalIdContent(ushort const *)

- ea: `0x180090670`
- end: `0x18009092d`
- name: `?_PackOriginalIdContent@ChatServiceConversation@@AEAAJPEBG@Z`
- size: `701`
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
- `0x180090670`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090752`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180090752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800908a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800908a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009085c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800908ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009085c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800908ce`

## string_xrefs

- `0x180090733`: `Windows.Data.Json.JsonValue`
- `0x1800906a4`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceConversation::_PackOriginalIdContent(
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
                      (const WCHAR **)off_1800FD688,
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
                                      (char *)this + 120,
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
0x180090670  mov     [rsp-8+arg_10], rbx
0x180090675  push    rbp
0x180090676  push    rsi
0x180090677  push    rdi
0x180090678  push    r14
0x18009067a  push    r15
0x18009067c  lea     rbp, [rsp-37h]
0x180090681  sub     rsp, 0A0h
0x180090688  mov     rax, cs:__security_cookie
0x18009068f  xor     rax, rsp
0x180090692  mov     [rbp+57h+var_30], rax
0x180090696  xor     r15d, r15d
0x180090699  mov     [rbp+57h+var_70], rdx
0x18009069d  mov     r14, rcx
0x1800906a0  mov     [rbp+57h+var_38], r15
0x1800906a4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800906ab  mov     [rbp+57h+var_78], r15
0x1800906af  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800906b3  lea     edi, [r15+1Ch]
0x1800906b7  mov     r9d, edi; unsigned int
0x1800906ba  lea     r8d, [r15+1Dh]; unsigned int
0x1800906be  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800906c3  mov     rcx, [rbp+57h+var_78]
0x1800906c7  lea     rdx, [rbp+57h+var_38]
0x1800906cb  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800906d0  mov     ebx, eax
0x1800906d2  test    eax, eax
0x1800906d4  jns     short loc_1800906EB
0x1800906d6  lea     edx, [rdi-1Bh]
0x1800906d9  mov     r9d, 1A7h
0x1800906df  mov     ecx, eax; int
0x1800906e1  call    Log_HREvent_67
0x1800906e6  jmp     loc_1800908FF
0x1800906eb  lea     rdx, [rbp+57h+var_60]
0x1800906ef  mov     [rbp+57h+var_60], r15
0x1800906f3  lea     rcx, [rbp+57h+var_38]
0x1800906f7  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800906fc  mov     ebx, eax
0x1800906fe  test    eax, eax
0x180090700  jns     short loc_180090722
0x180090702  mov     edx, 1
0x180090707  mov     r9d, 1AAh
0x18009070d  mov     ecx, eax; int
0x18009070f  call    Log_HREvent_67
0x180090714  lea     rcx, [rbp+57h+var_60]
0x180090718  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009071d  jmp     loc_1800908FF
0x180090722  mov     r9d, 1Bh; unsigned int
0x180090728  mov     [rbp+57h+var_50], r15
0x18009072c  mov     r8d, edi; unsigned int
0x18009072f  mov     [rbp+57h+var_78], r15
0x180090733  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18009073a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18009073e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090743  mov     rcx, [rbp+57h+var_78]
0x180090747  lea     r8, [rbp+57h+var_50]
0x18009074b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180090752  call    cs:__imp_RoGetActivationFactory
0x180090758  mov     ebx, eax
0x18009075a  test    eax, eax
0x18009075c  jns     short loc_18009077B
0x18009075e  mov     edx, 1
0x180090763  mov     r9d, 1AEh
0x180090769  mov     ecx, eax; int
0x18009076b  call    Log_HREvent_67
0x180090770  lea     rcx, [rbp+57h+var_50]
0x180090774  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090779  jmp     short loc_180090714
0x18009077b  mov     rdi, [rbp+57h+var_50]
0x18009077f  lea     rdx, [rbp+57h+var_70]
0x180090783  mov     [rbp+57h+var_48], r15
0x180090787  lea     rcx, [rbp+57h+hstringHeader]
0x18009078b  mov     rax, [rdi]
0x18009078e  mov     rbx, [rax+50h]
0x180090792  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180090797  lea     r8, [rbp+57h+var_48]
0x18009079b  mov     rcx, rdi
0x18009079e  mov     rdx, [rax+18h]
0x1800907a2  mov     rax, rbx
0x1800907a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800907aa  mov     ebx, eax
0x1800907ac  test    eax, eax
0x1800907ae  jns     short loc_1800907CD
0x1800907b0  mov     r9d, 1B1h
0x1800907b6  mov     edx, 1
0x1800907bb  mov     ecx, eax; int
0x1800907bd  call    Log_HREvent_67
0x1800907c2  lea     rcx, [rbp+57h+var_48]
0x1800907c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800907cb  jmp     short loc_180090770
0x1800907cd  mov     rsi, [rbp+57h+var_60]
0x1800907d1  lea     rdx, off_1800FD688; "originalId"
0x1800907d8  mov     rbx, [rbp+57h+var_48]
0x1800907dc  lea     rcx, [rbp+57h+hstringHeader]
0x1800907e0  mov     [rbp+57h+var_68], r15b
0x1800907e4  mov     rax, [rsi]
0x1800907e7  mov     rdi, [rax+50h]
0x1800907eb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800907f0  lea     r9, [rbp+57h+var_68]
0x1800907f4  mov     r8, rbx
0x1800907f7  mov     rcx, rsi
0x1800907fa  mov     rdx, [rax+18h]
0x1800907fe  mov     rax, rdi
0x180090801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090806  mov     ebx, eax
0x180090808  test    eax, eax
0x18009080a  jns     short loc_180090814
0x18009080c  mov     r9d, 1B4h
0x180090812  jmp     short loc_1800907B6
0x180090814  lea     rdx, [rbp+57h+var_40]
0x180090818  mov     [rbp+57h+var_40], r15
0x18009081c  lea     rcx, [rbp+57h+var_38]
0x180090820  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180090825  mov     ebx, eax
0x180090827  test    eax, eax
0x180090829  jns     short loc_18009084B
0x18009082b  mov     edx, 1
0x180090830  mov     r9d, 1B7h
0x180090836  mov     ecx, eax; int
0x180090838  call    Log_HREvent_67
0x18009083d  lea     rcx, [rbp+57h+var_40]
0x180090841  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090846  jmp     loc_1800907C2
0x18009084b  mov     rdi, [rbp+57h+var_40]
0x18009084f  xor     ecx, ecx; string
0x180090851  mov     [rbp+57h+string], r15
0x180090855  mov     rax, [rdi]
0x180090858  mov     rbx, [rax+38h]
0x18009085c  call    cs:__imp_WindowsDeleteString
0x180090862  lea     rdx, [rbp+57h+string]
0x180090866  mov     [rbp+57h+string], r15
0x18009086a  mov     rcx, rdi
0x18009086d  mov     rax, rbx
0x180090870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090875  mov     ebx, eax
0x180090877  test    eax, eax
0x180090879  jns     short loc_18009089D
0x18009087b  mov     edx, 1
0x180090880  mov     r9d, 1BAh
0x180090886  mov     ecx, eax; int
0x180090888  call    Log_HREvent_67
0x18009088d  mov     rcx, [rbp+57h+string]; string
0x180090891  call    cs:__imp_WindowsDeleteString
0x180090897  mov     [rbp+57h+string], r15
0x18009089b  jmp     short loc_18009083D
0x18009089d  mov     rcx, [rbp+57h+string]; string
0x1800908a1  xor     edx, edx; length
0x1800908a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800908a9  mov     rdx, rax
0x1800908ac  lea     rcx, [r14+78h]
0x1800908b0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800908b5  test    al, al
0x1800908b7  jnz     short loc_1800908CA
0x1800908b9  mov     ebx, 8007000Eh
0x1800908be  xor     edx, edx
0x1800908c0  mov     ecx, ebx
0x1800908c2  mov     r9d, 1BCh
0x1800908c8  jmp     short loc_180090888
0x1800908ca  mov     rcx, [rbp+57h+string]; string
0x1800908ce  call    cs:__imp_WindowsDeleteString
0x1800908d4  lea     rcx, [rbp+57h+var_40]
0x1800908d8  mov     [rbp+57h+string], r15
0x1800908dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800908e1  lea     rcx, [rbp+57h+var_48]
0x1800908e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800908ea  lea     rcx, [rbp+57h+var_50]
0x1800908ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800908f3  lea     rcx, [rbp+57h+var_60]
0x1800908f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800908fc  mov     ebx, r15d
0x1800908ff  lea     rcx, [rbp+57h+var_38]
0x180090903  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180090908  mov     eax, ebx
0x18009090a  mov     rcx, [rbp+57h+var_30]
0x18009090e  xor     rcx, rsp; StackCookie
0x180090911  call    __security_check_cookie
0x180090916  mov     rbx, [rsp+0C0h+arg_10]
0x18009091e  add     rsp, 0A0h
0x180090925  pop     r15
0x180090927  pop     r14
0x180090929  pop     rdi
0x18009092a  pop     rsi
0x18009092b  pop     rbp
0x18009092c  retn
```

# AsyncMediaServiceRevokeDocumentTransaction::_GenerateRevokeContent(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800aea08`
- end: `0x1800aecef`
- name: `?_GenerateRevokeContent@AsyncMediaServiceRevokeDocumentTransaction@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800aed50`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x1800242c4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x1800ae87c`
- `0x1800aea08`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aeae1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aeae1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aec49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aec49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aebee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aebee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec97`

## string_xrefs

- `0x1800aeac2`: `Windows.Data.Json.JsonValue`
- `0x1800aea39`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceRevokeDocumentTransaction::_GenerateRevokeContent(__int64 a1, __int64 a2)
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
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h]
  _BYTE v25[8]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  __int64 v28; // [rsp+68h] [rbp-21h] BYREF
  __int64 v29; // [rsp+70h] [rbp-19h] BYREF
  __int64 v30; // [rsp+78h] [rbp-11h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp-9h] BYREF
  _OWORD v32[2]; // [rsp+88h] [rbp-1h] BYREF

  v31 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v24, &v31);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v26 = 0;
    v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
           &v31,
           (__int64)&v26);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v28 = 0;
      v24 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v24, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v28);
      v4 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v8 = v28;
        v29 = 0;
        v9 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v28 + 80LL);
        v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_1800FD848,
                v7);
        v11 = v9(v8, v10[1].Reserved.Reserved1, &v29);
        v4 = v11;
        if ( v11 < 0
          || (v13 = v26,
              v14 = v29,
              v25[0] = 0,
              v15 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v26 + 80LL),
              v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_1800FD840,
                      v12),
              v11 = v15(v13, v16[1].Reserved.Reserved1, v14, v25),
              v4 = v11,
              v11 < 0) )
        {
          Log_HREvent_90(v11);
        }
        else
        {
          v30 = 0;
          v17 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                  &v31,
                  (__int64)&v30);
          v4 = v17;
          if ( v17 >= 0 )
          {
            v18 = v30;
            string = 0;
            v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 56LL);
            WindowsDeleteString(0);
            string = 0;
            v20 = v19(v18, &string);
            v4 = v20;
            if ( v20 >= 0 )
            {
              memset(v32, 0, sizeof(v32));
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v32);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                      v32,
                                      StringRawBuffer) )
              {
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
                  a2,
                  v32);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
                v4 = 0;
                goto LABEL_22;
              }
              v4 = -2147024882;
              Log_HREvent_90(-2147024882);
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v32);
            }
            else
            {
              Log_HREvent_90(v20);
            }
            WindowsDeleteString(string);
            string = 0;
          }
          else
          {
            Log_HREvent_90(v17);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      }
      else
      {
        Log_HREvent_90(ActivationFactory);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    }
    else
    {
      Log_HREvent_90(v5);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  }
  else
  {
    Log_HREvent_90(v3);
  }
LABEL_22:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return v4;
}

```

## disassembly

```asm
0x1800aea08  push    rbp
0x1800aea0a  push    rbx
0x1800aea0b  push    rsi
0x1800aea0c  push    rdi
0x1800aea0d  push    r14
0x1800aea0f  push    r15
0x1800aea11  lea     rbp, [rsp-2Fh]
0x1800aea16  sub     rsp, 0B8h
0x1800aea1d  mov     rax, cs:__security_cookie
0x1800aea24  xor     rax, rsp
0x1800aea27  mov     [rbp+57h+var_38], rax
0x1800aea2b  xor     r15d, r15d
0x1800aea2e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800aea32  mov     r14, rdx
0x1800aea35  mov     [rbp+57h+var_60], r15
0x1800aea39  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800aea40  mov     [rbp+57h+var_98], r15
0x1800aea44  lea     edi, [r15+1Ch]
0x1800aea48  mov     r9d, edi; unsigned int
0x1800aea4b  lea     r8d, [r15+1Dh]; unsigned int
0x1800aea4f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aea54  mov     rcx, [rbp+57h+var_98]
0x1800aea58  lea     rdx, [rbp+57h+var_60]
0x1800aea5c  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800aea61  mov     ebx, eax
0x1800aea63  test    eax, eax
0x1800aea65  jns     short loc_1800AEA7A
0x1800aea67  lea     edx, [rdi-1Bh]
0x1800aea6a  mov     ecx, eax; int
0x1800aea6c  lea     r9d, [rdi+6Bh]
0x1800aea70  call    Log_HREvent_90
0x1800aea75  jmp     loc_1800AECC8
0x1800aea7a  lea     rdx, [rbp+57h+var_88]
0x1800aea7e  mov     [rbp+57h+var_88], r15
0x1800aea82  lea     rcx, [rbp+57h+var_60]
0x1800aea86  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x1800aea8b  mov     ebx, eax
0x1800aea8d  test    eax, eax
0x1800aea8f  jns     short loc_1800AEAB1
0x1800aea91  mov     edx, 1
0x1800aea96  mov     r9d, 8Ah
0x1800aea9c  mov     ecx, eax; int
0x1800aea9e  call    Log_HREvent_90
0x1800aeaa3  lea     rcx, [rbp+57h+var_88]
0x1800aeaa7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aeaac  jmp     loc_1800AECC8
0x1800aeab1  mov     r9d, 1Bh; unsigned int
0x1800aeab7  mov     [rbp+57h+var_78], r15
0x1800aeabb  mov     r8d, edi; unsigned int
0x1800aeabe  mov     [rbp+57h+var_98], r15
0x1800aeac2  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800aeac9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800aeacd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aead2  mov     rcx, [rbp+57h+var_98]
0x1800aead6  lea     r8, [rbp+57h+var_78]
0x1800aeada  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800aeae1  call    cs:__imp_RoGetActivationFactory
0x1800aeae7  mov     ebx, eax
0x1800aeae9  test    eax, eax
0x1800aeaeb  jns     short loc_1800AEB0A
0x1800aeaed  mov     edx, 1
0x1800aeaf2  mov     r9d, 8Eh
0x1800aeaf8  mov     ecx, eax; int
0x1800aeafa  call    Log_HREvent_90
0x1800aeaff  lea     rcx, [rbp+57h+var_78]
0x1800aeb03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aeb08  jmp     short loc_1800AEAA3
0x1800aeb0a  mov     rdi, [rbp+57h+var_78]
0x1800aeb0e  lea     rdx, off_1800FD848; "P1D"
0x1800aeb15  mov     [rbp+57h+var_70], r15
0x1800aeb19  lea     rcx, [rbp+57h+hstringHeader]
0x1800aeb1d  mov     rax, [rdi]
0x1800aeb20  mov     rbx, [rax+50h]
0x1800aeb24  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aeb29  lea     r8, [rbp+57h+var_70]
0x1800aeb2d  mov     rcx, rdi
0x1800aeb30  mov     rdx, [rax+18h]
0x1800aeb34  mov     rax, rbx
0x1800aeb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb3c  mov     ebx, eax
0x1800aeb3e  test    eax, eax
0x1800aeb40  jns     short loc_1800AEB5F
0x1800aeb42  mov     r9d, 94h
0x1800aeb48  mov     edx, 1
0x1800aeb4d  mov     ecx, eax; int
0x1800aeb4f  call    Log_HREvent_90
0x1800aeb54  lea     rcx, [rbp+57h+var_70]
0x1800aeb58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aeb5d  jmp     short loc_1800AEAFF
0x1800aeb5f  mov     rsi, [rbp+57h+var_88]
0x1800aeb63  lea     rdx, off_1800FD840; "date"
0x1800aeb6a  mov     rbx, [rbp+57h+var_70]
0x1800aeb6e  lea     rcx, [rbp+57h+hstringHeader]
0x1800aeb72  mov     [rbp+57h+var_90], r15b
0x1800aeb76  mov     rax, [rsi]
0x1800aeb79  mov     rdi, [rax+50h]
0x1800aeb7d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800aeb82  lea     r9, [rbp+57h+var_90]
0x1800aeb86  mov     r8, rbx
0x1800aeb89  mov     rcx, rsi
0x1800aeb8c  mov     rdx, [rax+18h]
0x1800aeb90  mov     rax, rdi
0x1800aeb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb98  mov     ebx, eax
0x1800aeb9a  test    eax, eax
0x1800aeb9c  jns     short loc_1800AEBA6
0x1800aeb9e  mov     r9d, 97h
0x1800aeba4  jmp     short loc_1800AEB48
0x1800aeba6  lea     rdx, [rbp+57h+var_68]
0x1800aebaa  mov     [rbp+57h+var_68], r15
0x1800aebae  lea     rcx, [rbp+57h+var_60]
0x1800aebb2  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800aebb7  mov     ebx, eax
0x1800aebb9  test    eax, eax
0x1800aebbb  jns     short loc_1800AEBDD
0x1800aebbd  mov     edx, 1
0x1800aebc2  mov     r9d, 9Ah
0x1800aebc8  mov     ecx, eax; int
0x1800aebca  call    Log_HREvent_90
0x1800aebcf  lea     rcx, [rbp+57h+var_68]
0x1800aebd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aebd8  jmp     loc_1800AEB54
0x1800aebdd  mov     rdi, [rbp+57h+var_68]
0x1800aebe1  xor     ecx, ecx; string
0x1800aebe3  mov     [rbp+57h+string], r15
0x1800aebe7  mov     rax, [rdi]
0x1800aebea  mov     rbx, [rax+38h]
0x1800aebee  call    cs:__imp_WindowsDeleteString
0x1800aebf4  lea     rdx, [rbp+57h+string]
0x1800aebf8  mov     [rbp+57h+string], r15
0x1800aebfc  mov     rcx, rdi
0x1800aebff  mov     rax, rbx
0x1800aec02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec07  mov     ebx, eax
0x1800aec09  test    eax, eax
0x1800aec0b  jns     short loc_1800AEC2F
0x1800aec0d  mov     edx, 1
0x1800aec12  mov     r9d, 9Dh
0x1800aec18  mov     ecx, eax; int
0x1800aec1a  call    Log_HREvent_90
0x1800aec1f  mov     rcx, [rbp+57h+string]; string
0x1800aec23  call    cs:__imp_WindowsDeleteString
0x1800aec29  mov     [rbp+57h+string], r15
0x1800aec2d  jmp     short loc_1800AEBCF
0x1800aec2f  xorps   xmm0, xmm0
0x1800aec32  lea     rcx, [rbp+57h+var_58]
0x1800aec36  movups  [rbp+57h+var_58], xmm0
0x1800aec3a  movups  [rbp+57h+var_48], xmm0
0x1800aec3e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800aec43  mov     rcx, [rbp+57h+string]; string
0x1800aec47  xor     edx, edx; length
0x1800aec49  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aec4f  mov     rdx, rax
0x1800aec52  lea     rcx, [rbp+57h+var_58]
0x1800aec56  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800aec5b  test    al, al
0x1800aec5d  jnz     short loc_1800AEC7E
0x1800aec5f  mov     ebx, 8007000Eh
0x1800aec64  xor     edx, edx
0x1800aec66  mov     ecx, ebx; int
0x1800aec68  mov     r9d, 0A0h
0x1800aec6e  call    Log_HREvent_90
0x1800aec73  lea     rcx, [rbp+57h+var_58]
0x1800aec77  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800aec7c  jmp     short loc_1800AEC1F
0x1800aec7e  lea     rdx, [rbp+57h+var_58]
0x1800aec82  mov     rcx, r14
0x1800aec85  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800aec8a  lea     rcx, [rbp+57h+var_58]
0x1800aec8e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800aec93  mov     rcx, [rbp+57h+string]; string
0x1800aec97  call    cs:__imp_WindowsDeleteString
0x1800aec9d  lea     rcx, [rbp+57h+var_68]
0x1800aeca1  mov     [rbp+57h+string], r15
0x1800aeca5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aecaa  lea     rcx, [rbp+57h+var_70]
0x1800aecae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aecb3  lea     rcx, [rbp+57h+var_78]
0x1800aecb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aecbc  lea     rcx, [rbp+57h+var_88]
0x1800aecc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aecc5  mov     ebx, r15d
0x1800aecc8  lea     rcx, [rbp+57h+var_60]
0x1800aeccc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800aecd1  mov     eax, ebx
0x1800aecd3  mov     rcx, [rbp+57h+var_38]
0x1800aecd7  xor     rcx, rsp; StackCookie
0x1800aecda  call    __security_check_cookie
0x1800aecdf  add     rsp, 0B8h
0x1800aece6  pop     r15
0x1800aece8  pop     r14
0x1800aecea  pop     rdi
0x1800aeceb  pop     rsi
0x1800aecec  pop     rbx
0x1800aeced  pop     rbp
0x1800aecee  retn
```

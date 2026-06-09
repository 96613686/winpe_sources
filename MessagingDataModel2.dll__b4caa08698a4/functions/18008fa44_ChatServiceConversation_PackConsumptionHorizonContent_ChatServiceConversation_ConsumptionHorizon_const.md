# ChatServiceConversation::_PackConsumptionHorizonContent(ChatServiceConversation::ConsumptionHorizon const *)

- ea: `0x18008fa44`
- end: `0x18008fd7b`
- name: `?_PackConsumptionHorizonContent@ChatServiceConversation@@AEAAJPEBUConsumptionHorizon@1@@Z`
- size: `823`
- prototype: `__int64 __fastcall(ChatServiceConversation *__hidden this, const struct ChatServiceConversation::ConsumptionHorizon *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008fd90`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18003214c`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x18008f830`
- `0x18008fa44`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008fb25`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008fb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fc9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fcd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fd13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fc9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fcd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008fd13`

## string_xrefs

- `0x18008fb06`: `Windows.Data.Json.JsonValue`
- `0x18008fa77`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceConversation::_PackConsumptionHorizonContent(
        ChatServiceConversation *this,
        const struct ChatServiceConversation::ConsumptionHorizon *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int ActivationFactory; // eax
  int v8; // eax
  char v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v12; // rax
  int v13; // eax
  char v14; // r8
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  int v23; // ecx
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v26; // [rsp+40h] [rbp-59h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-51h] BYREF
  __int64 v28; // [rsp+60h] [rbp-39h]
  _BYTE v29[8]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h] BYREF
  __int64 v31; // [rsp+78h] [rbp-21h] BYREF
  HSTRING string; // [rsp+80h] [rbp-19h] BYREF
  __int64 v33; // [rsp+88h] [rbp-11h] BYREF
  __int64 v34; // [rsp+90h] [rbp-9h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+98h] [rbp-1h] BYREF
  _OWORD v36[2]; // [rsp+A0h] [rbp+7h] BYREF

  v35 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v28, &v35);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v30 = 0;
    v6 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
           &v35,
           (__int64)&v30);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v31 = 0;
      v28 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v28, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v31);
      v5 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        memset(v36, 0, sizeof(v36));
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v36);
        v8 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
               v36,
               L"%I64u%c%I64u%c%I64u",
               *(_QWORD *)a2);
        v5 = v8;
        if ( v8 >= 0 )
        {
          v10 = v31;
          v33 = 0;
          v26 = *(const WCHAR **)&v36[0];
          v11 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v31 + 80LL);
          v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26, v9);
          v13 = v11(v10, v12[1].Reserved.Reserved1, &v33);
          v5 = v13;
          if ( v13 < 0
            || (v15 = v30,
                v16 = v33,
                v29[0] = 0,
                v17 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v30 + 80LL),
                v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_1800FD690,
                        v14),
                v13 = v17(v15, v18[1].Reserved.Reserved1, v16, v29),
                v5 = v13,
                v13 < 0) )
          {
            Log_HREvent_67(v13);
          }
          else
          {
            v34 = 0;
            v19 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                    &v35,
                    (__int64)&v34);
            v5 = v19;
            if ( v19 >= 0 )
            {
              v20 = v34;
              string = 0;
              v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 56LL);
              WindowsDeleteString(0);
              string = 0;
              v22 = v21(v20, &string);
              v5 = v22;
              if ( v22 >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                        (char *)this + 248,
                                        StringRawBuffer) )
                {
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
                  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v36);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                  v5 = 0;
                  goto LABEL_25;
                }
                v5 = -2147024882;
                v23 = -2147024882;
              }
              else
              {
                v23 = v22;
              }
              Log_HREvent_67(v23);
              WindowsDeleteString(string);
              string = 0;
            }
            else
            {
              Log_HREvent_67(v19);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        }
        else
        {
          Log_HREvent_67(v8);
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v36);
      }
      else
      {
        Log_HREvent_67(ActivationFactory);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    }
    else
    {
      Log_HREvent_67(v6);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  }
  else
  {
    Log_HREvent_67(v4);
  }
LABEL_25:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  return v5;
}

```

## disassembly

```asm
0x18008fa44  mov     [rsp-8+arg_10], rbx
0x18008fa49  push    rbp
0x18008fa4a  push    rsi
0x18008fa4b  push    rdi
0x18008fa4c  push    r14
0x18008fa4e  push    r15
0x18008fa50  lea     rbp, [rsp-37h]
0x18008fa55  sub     rsp, 0D0h
0x18008fa5c  mov     rax, cs:__security_cookie
0x18008fa63  xor     rax, rsp
0x18008fa66  mov     [rbp+57h+var_30], rax
0x18008fa6a  xor     r15d, r15d
0x18008fa6d  mov     rdi, rdx
0x18008fa70  mov     r14, rcx
0x18008fa73  mov     [rbp+57h+var_58], r15
0x18008fa77  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18008fa7e  mov     [rbp+57h+var_90], r15
0x18008fa82  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18008fa86  lea     esi, [r15+1Ch]
0x18008fa8a  mov     r9d, esi; unsigned int
0x18008fa8d  lea     r8d, [r15+1Dh]; unsigned int
0x18008fa91  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008fa96  mov     rcx, [rbp+57h+var_90]
0x18008fa9a  lea     rdx, [rbp+57h+var_58]
0x18008fa9e  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18008faa3  mov     ebx, eax
0x18008faa5  test    eax, eax
0x18008faa7  jns     short loc_18008FABE
0x18008faa9  lea     edx, [rsi-1Bh]
0x18008faac  mov     r9d, 15Fh
0x18008fab2  mov     ecx, eax; int
0x18008fab4  call    Log_HREvent_67
0x18008fab9  jmp     loc_18008FD4D
0x18008fabe  lea     rdx, [rbp+57h+var_80]
0x18008fac2  mov     [rbp+57h+var_80], r15
0x18008fac6  lea     rcx, [rbp+57h+var_58]
0x18008faca  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x18008facf  mov     ebx, eax
0x18008fad1  test    eax, eax
0x18008fad3  jns     short loc_18008FAF5
0x18008fad5  mov     edx, 1
0x18008fada  mov     r9d, 162h
0x18008fae0  mov     ecx, eax; int
0x18008fae2  call    Log_HREvent_67
0x18008fae7  lea     rcx, [rbp+57h+var_80]
0x18008faeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008faf0  jmp     loc_18008FD4D
0x18008faf5  mov     r9d, 1Bh; unsigned int
0x18008fafb  mov     [rbp+57h+var_78], r15
0x18008faff  mov     r8d, esi; unsigned int
0x18008fb02  mov     [rbp+57h+var_90], r15
0x18008fb06  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18008fb0d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18008fb11  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008fb16  mov     rcx, [rbp+57h+var_90]
0x18008fb1a  lea     r8, [rbp+57h+var_78]
0x18008fb1e  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18008fb25  call    cs:__imp_RoGetActivationFactory
0x18008fb2b  mov     ebx, eax
0x18008fb2d  test    eax, eax
0x18008fb2f  jns     short loc_18008FB4E
0x18008fb31  mov     edx, 1
0x18008fb36  mov     r9d, 166h
0x18008fb3c  mov     ecx, eax; int
0x18008fb3e  call    Log_HREvent_67
0x18008fb43  lea     rcx, [rbp+57h+var_78]
0x18008fb47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fb4c  jmp     short loc_18008FAE7
0x18008fb4e  xorps   xmm0, xmm0
0x18008fb51  lea     rcx, [rbp+57h+var_50]
0x18008fb55  movups  [rbp+57h+var_50], xmm0
0x18008fb59  movups  [rbp+57h+var_40], xmm0
0x18008fb5d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18008fb62  mov     rcx, [rdi+10h]
0x18008fb66  lea     rdx, aI64uCI64uCI64u; "%I64u%c%I64u%c%I64u"
0x18008fb6d  mov     rax, [rdi+8]
0x18008fb71  mov     r9d, 3Bh ; ';'
0x18008fb77  mov     r8, [rdi]
0x18008fb7a  mov     [rsp+0F0h+var_C0], rcx
0x18008fb7f  lea     rcx, [rbp+57h+var_50]
0x18008fb83  mov     [rsp+0F0h+var_C8], r9d
0x18008fb88  mov     [rsp+0F0h+var_D0], rax
0x18008fb8d  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18008fb92  mov     ebx, eax
0x18008fb94  test    eax, eax
0x18008fb96  jns     short loc_18008FBB5
0x18008fb98  mov     edx, 1
0x18008fb9d  mov     r9d, 172h
0x18008fba3  mov     ecx, eax; int
0x18008fba5  call    Log_HREvent_67
0x18008fbaa  lea     rcx, [rbp+57h+var_50]
0x18008fbae  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008fbb3  jmp     short loc_18008FB43
0x18008fbb5  mov     rdx, qword ptr [rbp+57h+var_50]
0x18008fbb9  lea     rcx, [rbp+57h+hstringHeader]
0x18008fbbd  mov     rdi, [rbp+57h+var_78]
0x18008fbc1  mov     [rbp+57h+var_68], r15
0x18008fbc5  mov     [rbp+57h+var_B0], rdx
0x18008fbc9  lea     rdx, [rbp+57h+var_B0]
0x18008fbcd  mov     rax, [rdi]
0x18008fbd0  mov     rbx, [rax+50h]
0x18008fbd4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008fbd9  lea     r8, [rbp+57h+var_68]
0x18008fbdd  mov     rcx, rdi
0x18008fbe0  mov     rdx, [rax+18h]
0x18008fbe4  mov     rax, rbx
0x18008fbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbec  mov     ebx, eax
0x18008fbee  test    eax, eax
0x18008fbf0  jns     short loc_18008FC0F
0x18008fbf2  mov     r9d, 176h
0x18008fbf8  mov     edx, 1
0x18008fbfd  mov     ecx, eax; int
0x18008fbff  call    Log_HREvent_67
0x18008fc04  lea     rcx, [rbp+57h+var_68]
0x18008fc08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fc0d  jmp     short loc_18008FBAA
0x18008fc0f  mov     rsi, [rbp+57h+var_80]
0x18008fc13  lea     rdx, off_1800FD690; "consumptionHorizon"
0x18008fc1a  mov     rbx, [rbp+57h+var_68]
0x18008fc1e  lea     rcx, [rbp+57h+hstringHeader]
0x18008fc22  mov     [rbp+57h+var_88], r15b
0x18008fc26  mov     rax, [rsi]
0x18008fc29  mov     rdi, [rax+50h]
0x18008fc2d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008fc32  lea     r9, [rbp+57h+var_88]
0x18008fc36  mov     r8, rbx
0x18008fc39  mov     rcx, rsi
0x18008fc3c  mov     rdx, [rax+18h]
0x18008fc40  mov     rax, rdi
0x18008fc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fc48  mov     ebx, eax
0x18008fc4a  test    eax, eax
0x18008fc4c  jns     short loc_18008FC56
0x18008fc4e  mov     r9d, 17Ah
0x18008fc54  jmp     short loc_18008FBF8
0x18008fc56  lea     rdx, [rbp+57h+var_60]
0x18008fc5a  mov     [rbp+57h+var_60], r15
0x18008fc5e  lea     rcx, [rbp+57h+var_58]
0x18008fc62  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18008fc67  mov     ebx, eax
0x18008fc69  test    eax, eax
0x18008fc6b  jns     short loc_18008FC8D
0x18008fc6d  mov     edx, 1
0x18008fc72  mov     r9d, 17Dh
0x18008fc78  mov     ecx, eax; int
0x18008fc7a  call    Log_HREvent_67
0x18008fc7f  lea     rcx, [rbp+57h+var_60]
0x18008fc83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fc88  jmp     loc_18008FC04
0x18008fc8d  mov     rdi, [rbp+57h+var_60]
0x18008fc91  xor     ecx, ecx; string
0x18008fc93  mov     [rbp+57h+string], r15
0x18008fc97  mov     rax, [rdi]
0x18008fc9a  mov     rbx, [rax+38h]
0x18008fc9e  call    cs:__imp_WindowsDeleteString
0x18008fca4  lea     rdx, [rbp+57h+string]
0x18008fca8  mov     [rbp+57h+string], r15
0x18008fcac  mov     rcx, rdi
0x18008fcaf  mov     rax, rbx
0x18008fcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fcb7  mov     ebx, eax
0x18008fcb9  test    eax, eax
0x18008fcbb  jns     short loc_18008FCDF
0x18008fcbd  mov     edx, 1
0x18008fcc2  mov     r9d, 180h
0x18008fcc8  mov     ecx, eax; int
0x18008fcca  call    Log_HREvent_67
0x18008fccf  mov     rcx, [rbp+57h+string]; string
0x18008fcd3  call    cs:__imp_WindowsDeleteString
0x18008fcd9  mov     [rbp+57h+string], r15
0x18008fcdd  jmp     short loc_18008FC7F
0x18008fcdf  mov     rcx, [rbp+57h+string]; string
0x18008fce3  xor     edx, edx; length
0x18008fce5  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fceb  mov     rdx, rax
0x18008fcee  lea     rcx, [r14+0F8h]
0x18008fcf5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18008fcfa  test    al, al
0x18008fcfc  jnz     short loc_18008FD0F
0x18008fcfe  mov     ebx, 8007000Eh
0x18008fd03  xor     edx, edx
0x18008fd05  mov     ecx, ebx
0x18008fd07  mov     r9d, 182h
0x18008fd0d  jmp     short loc_18008FCCA
0x18008fd0f  mov     rcx, [rbp+57h+string]; string
0x18008fd13  call    cs:__imp_WindowsDeleteString
0x18008fd19  lea     rcx, [rbp+57h+var_60]
0x18008fd1d  mov     [rbp+57h+string], r15
0x18008fd21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fd26  lea     rcx, [rbp+57h+var_68]
0x18008fd2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fd2f  lea     rcx, [rbp+57h+var_50]
0x18008fd33  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008fd38  lea     rcx, [rbp+57h+var_78]
0x18008fd3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fd41  lea     rcx, [rbp+57h+var_80]
0x18008fd45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fd4a  mov     ebx, r15d
0x18008fd4d  lea     rcx, [rbp+57h+var_58]
0x18008fd51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008fd56  mov     eax, ebx
0x18008fd58  mov     rcx, [rbp+57h+var_30]
0x18008fd5c  xor     rcx, rsp; StackCookie
0x18008fd5f  call    __security_check_cookie
0x18008fd64  mov     rbx, [rsp+0F0h+arg_10]
0x18008fd6c  add     rsp, 0D0h
0x18008fd73  pop     r15
0x18008fd75  pop     r14
0x18008fd77  pop     rdi
0x18008fd78  pop     rsi
0x18008fd79  pop     rbp
0x18008fd7a  retn
```

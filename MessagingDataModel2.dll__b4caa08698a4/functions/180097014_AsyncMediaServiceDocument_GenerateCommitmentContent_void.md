# AsyncMediaServiceDocument::_GenerateCommitmentContent(void)

- ea: `0x180097014`
- end: `0x1800972c9`
- name: `?_GenerateCommitmentContent@AsyncMediaServiceDocument@@AEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(AsyncMediaServiceDocument *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800976e0`
- `0x180097d60`

## callees

- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x180096cac`
- `0x180097014`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800970ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800970ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800971fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800971fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097271`

## string_xrefs

- `0x1800970d0`: `Windows.Data.Json.JsonValue`
- `0x18009703a`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceDocument::_GenerateCommitmentContent(AsyncMediaServiceDocument *this)
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
               (const WCHAR **)off_1800FD770,
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
                      (const WCHAR **)off_1800FD788,
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
                                      (char *)this + 128,
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
0x180097014  push    rbp
0x180097016  push    rbx
0x180097017  push    rsi
0x180097018  push    rdi
0x180097019  push    r14
0x18009701b  push    r15
0x18009701d  lea     rbp, [rsp-2Fh]
0x180097022  sub     rsp, 98h
0x180097029  mov     rax, cs:__security_cookie
0x180097030  xor     rax, rsp
0x180097033  mov     [rbp+57h+var_38], rax
0x180097037  xor     r15d, r15d
0x18009703a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180097041  mov     r14, rcx
0x180097044  mov     [rbp+57h+var_40], r15
0x180097048  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18009704c  mov     [rbp+57h+var_78], r15
0x180097050  lea     edi, [r15+1Ch]
0x180097054  mov     r9d, edi; unsigned int
0x180097057  lea     r8d, [r15+1Dh]; unsigned int
0x18009705b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180097060  mov     rcx, [rbp+57h+var_78]
0x180097064  lea     rdx, [rbp+57h+var_40]
0x180097068  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18009706d  mov     ebx, eax
0x18009706f  test    eax, eax
0x180097071  jns     short loc_180097088
0x180097073  lea     edx, [rdi-1Bh]
0x180097076  mov     r9d, 164h
0x18009707c  mov     ecx, eax; int
0x18009707e  call    Log_HREvent_69
0x180097083  jmp     loc_1800972A2
0x180097088  lea     rdx, [rbp+57h+var_68]
0x18009708c  mov     [rbp+57h+var_68], r15
0x180097090  lea     rcx, [rbp+57h+var_40]
0x180097094  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180097099  mov     ebx, eax
0x18009709b  test    eax, eax
0x18009709d  jns     short loc_1800970BF
0x18009709f  mov     edx, 1
0x1800970a4  mov     r9d, 167h
0x1800970aa  mov     ecx, eax; int
0x1800970ac  call    Log_HREvent_69
0x1800970b1  lea     rcx, [rbp+57h+var_68]
0x1800970b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800970ba  jmp     loc_1800972A2
0x1800970bf  mov     r9d, 1Bh; unsigned int
0x1800970c5  mov     [rbp+57h+var_58], r15
0x1800970c9  mov     r8d, edi; unsigned int
0x1800970cc  mov     [rbp+57h+var_78], r15
0x1800970d0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800970d7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800970db  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800970e0  mov     rcx, [rbp+57h+var_78]
0x1800970e4  lea     r8, [rbp+57h+var_58]
0x1800970e8  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800970ef  call    cs:__imp_RoGetActivationFactory
0x1800970f5  mov     ebx, eax
0x1800970f7  test    eax, eax
0x1800970f9  jns     short loc_180097118
0x1800970fb  mov     edx, 1
0x180097100  mov     r9d, 16Bh
0x180097106  mov     ecx, eax; int
0x180097108  call    Log_HREvent_69
0x18009710d  lea     rcx, [rbp+57h+var_58]
0x180097111  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097116  jmp     short loc_1800970B1
0x180097118  mov     rdi, [rbp+57h+var_58]
0x18009711c  lea     rdx, off_1800FD770; "P100Y"
0x180097123  mov     [rbp+57h+var_50], r15
0x180097127  lea     rcx, [rbp+57h+hstringHeader]
0x18009712b  mov     rax, [rdi]
0x18009712e  mov     rbx, [rax+50h]
0x180097132  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180097137  lea     r8, [rbp+57h+var_50]
0x18009713b  mov     rcx, rdi
0x18009713e  mov     rdx, [rax+18h]
0x180097142  mov     rax, rbx
0x180097145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009714a  mov     ebx, eax
0x18009714c  test    eax, eax
0x18009714e  jns     short loc_18009716D
0x180097150  mov     r9d, 171h
0x180097156  mov     edx, 1
0x18009715b  mov     ecx, eax; int
0x18009715d  call    Log_HREvent_69
0x180097162  lea     rcx, [rbp+57h+var_50]
0x180097166  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009716b  jmp     short loc_18009710D
0x18009716d  mov     rsi, [rbp+57h+var_68]
0x180097171  lea     rdx, off_1800FD788; "date"
0x180097178  mov     rbx, [rbp+57h+var_50]
0x18009717c  lea     rcx, [rbp+57h+hstringHeader]
0x180097180  mov     [rbp+57h+var_70], r15b
0x180097184  mov     rax, [rsi]
0x180097187  mov     rdi, [rax+50h]
0x18009718b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180097190  lea     r9, [rbp+57h+var_70]
0x180097194  mov     r8, rbx
0x180097197  mov     rcx, rsi
0x18009719a  mov     rdx, [rax+18h]
0x18009719e  mov     rax, rdi
0x1800971a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800971a6  mov     ebx, eax
0x1800971a8  test    eax, eax
0x1800971aa  jns     short loc_1800971B4
0x1800971ac  mov     r9d, 174h
0x1800971b2  jmp     short loc_180097156
0x1800971b4  lea     rdx, [rbp+57h+var_48]
0x1800971b8  mov     [rbp+57h+var_48], r15
0x1800971bc  lea     rcx, [rbp+57h+var_40]
0x1800971c0  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800971c5  mov     ebx, eax
0x1800971c7  test    eax, eax
0x1800971c9  jns     short loc_1800971EB
0x1800971cb  mov     edx, 1
0x1800971d0  mov     r9d, 177h
0x1800971d6  mov     ecx, eax; int
0x1800971d8  call    Log_HREvent_69
0x1800971dd  lea     rcx, [rbp+57h+var_48]
0x1800971e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800971e6  jmp     loc_180097162
0x1800971eb  mov     rdi, [rbp+57h+var_48]
0x1800971ef  xor     ecx, ecx; string
0x1800971f1  mov     [rbp+57h+string], r15
0x1800971f5  mov     rax, [rdi]
0x1800971f8  mov     rbx, [rax+38h]
0x1800971fc  call    cs:__imp_WindowsDeleteString
0x180097202  lea     rdx, [rbp+57h+string]
0x180097206  mov     [rbp+57h+string], r15
0x18009720a  mov     rcx, rdi
0x18009720d  mov     rax, rbx
0x180097210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097215  mov     ebx, eax
0x180097217  test    eax, eax
0x180097219  jns     short loc_18009723D
0x18009721b  mov     edx, 1
0x180097220  mov     r9d, 17Ah
0x180097226  mov     ecx, eax; int
0x180097228  call    Log_HREvent_69
0x18009722d  mov     rcx, [rbp+57h+string]; string
0x180097231  call    cs:__imp_WindowsDeleteString
0x180097237  mov     [rbp+57h+string], r15
0x18009723b  jmp     short loc_1800971DD
0x18009723d  mov     rcx, [rbp+57h+string]; string
0x180097241  xor     edx, edx; length
0x180097243  call    cs:__imp_WindowsGetStringRawBuffer
0x180097249  mov     rdx, rax
0x18009724c  lea     rcx, [r14+80h]
0x180097253  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180097258  test    al, al
0x18009725a  jnz     short loc_18009726D
0x18009725c  mov     ebx, 8007000Eh
0x180097261  xor     edx, edx
0x180097263  mov     ecx, ebx
0x180097265  mov     r9d, 17Ch
0x18009726b  jmp     short loc_180097228
0x18009726d  mov     rcx, [rbp+57h+string]; string
0x180097271  call    cs:__imp_WindowsDeleteString
0x180097277  lea     rcx, [rbp+57h+var_48]
0x18009727b  mov     [rbp+57h+string], r15
0x18009727f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097284  lea     rcx, [rbp+57h+var_50]
0x180097288  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009728d  lea     rcx, [rbp+57h+var_58]
0x180097291  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097296  lea     rcx, [rbp+57h+var_68]
0x18009729a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009729f  mov     ebx, r15d
0x1800972a2  lea     rcx, [rbp+57h+var_40]
0x1800972a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800972ab  mov     eax, ebx
0x1800972ad  mov     rcx, [rbp+57h+var_38]
0x1800972b1  xor     rcx, rsp; StackCookie
0x1800972b4  call    __security_check_cookie
0x1800972b9  add     rsp, 98h
0x1800972c0  pop     r15
0x1800972c2  pop     r14
0x1800972c4  pop     rdi
0x1800972c5  pop     rsi
0x1800972c6  pop     rbx
0x1800972c7  pop     rbp
0x1800972c8  retn
```

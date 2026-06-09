# CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180020e9c`
- end: `0x18002129c`
- name: `?ParseMpsMsGraphServicesResponseForDiscoveryEndpoint@MpsParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800157bc`

## callees

- `0x180003a60`
- `0x1800067a4`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e5e8`
- `0x18000f7a4`
- `0x180012700`
- `0x1800133a0`
- `0x18001aab4`
- `0x18001bfe4`
- `0x18001c298`
- `0x18001df80`
- `0x18001ea14`
- `0x18001ea64`
- `0x180020e9c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002122d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002122d`

## string_xrefs

- `0x180020f0c`: `Windows.Data.Json.JsonObject`
- `0x180020ec8`: `ParseMpsMsGraphServicesResponseForDiscoveryEndpoint`
- `0x180021038`: `Number of discovery service endpoints returned (%u) is not 1`
- `0x18002103f`: `CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint`
- `0x18002121b`: `CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, HSTRING *); // rbx
  int v17; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  HSTRING string; // [rsp+20h] [rbp-89h] BYREF
  __int64 v24; // [rsp+28h] [rbp-81h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-79h] BYREF
  __int64 v26; // [rsp+38h] [rbp-71h] BYREF
  int v27; // [rsp+40h] [rbp-69h] BYREF
  __int64 v28; // [rsp+48h] [rbp-61h] BYREF
  __int64 v29; // [rsp+50h] [rbp-59h] BYREF
  __int64 v30; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v31[80]; // [rsp+60h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v33; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  CloudPrintHelperTelemetry::WatchCurrentThread(v31, "ParseMpsMsGraphServicesResponseForDiscoveryEndpoint");
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  v27 = 0;
  v29 = 0;
  v26 = 0;
  v25 = 0;
  v28 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v33,
         (__int64)&v29);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 592;
LABEL_5:
    v9 = (unsigned int)v3;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)v9,
      (int)string);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
    return v4;
  }
  v6 = v29;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v30);
  v3 = v7(v6, *(_QWORD *)(v8 + 24), &v26);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 595;
    goto LABEL_5;
  }
  v10 = v26;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v26 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"endpoints", 0xAu, 9u);
  v3 = v11(v10, v33, &v25);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 598;
    goto LABEL_5;
  }
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         &v25,
         (__int64)&v28);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 599;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 56LL))(v28, &v27);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 600;
    goto LABEL_5;
  }
  if ( v27 != 1 )
  {
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint",
      L"Number of discovery service endpoints returned (%u) is not 1");
    v4 = -2147483637;
    v9 = 2147483659LL;
    v5 = 606;
    goto LABEL_6;
  }
  v24 = 0;
  v12 = v25;
  v13 = (*v25)[6];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v14 = v13(v12, 0, (__int64)&v24);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v14,
      (int)string);
LABEL_19:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    goto LABEL_20;
  }
  string = 0;
  v15 = v24;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v24 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"uri", 4u, 3u);
  v17 = v16(v15, v33, &string);
  v4 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_19;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v20 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
  std::wstring::_Assign<unsigned short>(a2, v21, v20);
  if ( !*(_QWORD *)(a2 + 16) || std::wstring::find(a2, L"https://", 0) == -1 )
  {
    v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint",
      L"Empty string or Insecure endpoint returned from MS Graph. DiscoveryEndpoint=%s",
      v22);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
    return 2147942413LL;
  }
  else
  {
    CloudPrint::CloudPrintHelper::RemoveTrailingForwardSlash(a2);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
    return 0;
  }
}

```

## disassembly

```asm
0x180020e9c  mov     [rsp-8+arg_10], rbx
0x180020ea1  push    rbp
0x180020ea2  push    rsi
0x180020ea3  push    rdi
0x180020ea4  push    r14
0x180020ea6  push    r15
0x180020ea8  lea     rbp, [rsp-37h]
0x180020ead  sub     rsp, 0E0h
0x180020eb4  mov     rax, cs:__security_cookie
0x180020ebb  xor     rax, rsp
0x180020ebe  mov     [rbp+57h+var_30], rax
0x180020ec2  mov     rsi, rdx
0x180020ec5  mov     r14, rcx
0x180020ec8  lea     rdx, aParsempsmsgrap; "ParseMpsMsGraphServicesResponseForDisco"...
0x180020ecf  lea     rcx, [rbp+57h+var_A0]
0x180020ed3  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x180020ed8  nop
0x180020ed9  xor     r15d, r15d
0x180020edc  mov     [rsi+10h], r15
0x180020ee0  mov     rcx, rsi
0x180020ee3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020ee8  mov     [rax], r15w
0x180020eec  mov     [rbp+57h+var_C0], r15d
0x180020ef0  mov     [rbp+57h+var_B0], r15
0x180020ef4  mov     [rbp+57h+var_C8], r15
0x180020ef8  mov     [rbp+57h+var_D0], r15
0x180020efc  mov     [rbp+57h+var_B8], r15
0x180020f00  mov     [rbp+57h+var_38], r15
0x180020f04  lea     r9d, [r15+1Ch]; unsigned int
0x180020f08  lea     r8d, [r15+1Dh]; unsigned int
0x180020f0c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180020f13  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020f17  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020f1c  lea     rdx, [rbp+57h+var_B0]
0x180020f20  mov     rcx, [rbp+57h+var_38]
0x180020f24  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180020f29  mov     ebx, eax
0x180020f2b  test    eax, eax
0x180020f2d  jns     short loc_180020F36
0x180020f2f  mov     edx, 250h
0x180020f34  jmp     short loc_180020F82
0x180020f36  mov     rdi, [rbp+57h+var_B0]
0x180020f3a  mov     rax, [rdi]
0x180020f3d  mov     rbx, [rax+30h]
0x180020f41  lea     rcx, [rbp+57h+var_C8]
0x180020f45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020f4a  mov     rcx, r14
0x180020f4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020f52  mov     [rbp+57h+var_A8], rax
0x180020f56  lea     rdx, [rbp+57h+var_A8]
0x180020f5a  lea     rcx, [rbp+57h+hstringHeader]
0x180020f5e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020f63  nop
0x180020f64  lea     r8, [rbp+57h+var_C8]
0x180020f68  mov     rdx, [rax+18h]
0x180020f6c  mov     rcx, rdi
0x180020f6f  mov     rax, rbx
0x180020f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f77  mov     ebx, eax
0x180020f79  test    eax, eax
0x180020f7b  jns     short loc_180020F9A
0x180020f7d  mov     edx, 253h; void *
0x180020f82  mov     r9d, eax; char *
0x180020f85  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x180020f8c  mov     rcx, [rbp+5Fh]; this
0x180020f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f95  jmp     loc_180021137
0x180020f9a  mov     rdi, [rbp+57h+var_C8]
0x180020f9e  mov     rax, [rdi]
0x180020fa1  mov     rbx, [rax+48h]
0x180020fa5  lea     rcx, [rbp+57h+var_D0]
0x180020fa9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fae  mov     [rbp+57h+var_38], r15
0x180020fb2  mov     r9d, 9; unsigned int
0x180020fb8  lea     r8d, [r9+1]; unsigned int
0x180020fbc  lea     rdx, aEndpoints; "endpoints"
0x180020fc3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020fc7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020fcc  nop
0x180020fcd  lea     r8, [rbp+57h+var_D0]
0x180020fd1  mov     rdx, [rbp+57h+var_38]
0x180020fd5  mov     rcx, rdi
0x180020fd8  mov     rax, rbx
0x180020fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fe0  mov     ebx, eax
0x180020fe2  test    eax, eax
0x180020fe4  jns     short loc_180020FED
0x180020fe6  mov     edx, 256h
0x180020feb  jmp     short loc_180020F82
0x180020fed  lea     rdx, [rbp+57h+var_B8]
0x180020ff1  lea     rcx, [rbp+57h+var_D0]
0x180020ff5  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180020ffa  mov     ebx, eax
0x180020ffc  test    eax, eax
0x180020ffe  jns     short loc_18002100A
0x180021000  mov     edx, 257h
0x180021005  jmp     loc_180020F82
0x18002100a  mov     rcx, [rbp+57h+var_B8]
0x18002100e  mov     rax, [rcx]
0x180021011  lea     rdx, [rbp+57h+var_C0]
0x180021015  mov     rax, [rax+38h]
0x180021019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002101e  mov     ebx, eax
0x180021020  test    eax, eax
0x180021022  jns     short loc_18002102E
0x180021024  mov     edx, 258h
0x180021029  jmp     loc_180020F82
0x18002102e  mov     r8d, [rbp+57h+var_C0]
0x180021032  cmp     r8d, 1
0x180021036  jz      short loc_18002105D
0x180021038  lea     rdx, aNumberOfDiscov; "Number of discovery service endpoints r"...
0x18002103f  lea     rcx, aCloudprintMpsp; "CloudPrint::MpsParser::ParseMpsMsGraphS"...
0x180021046  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002104b  mov     ebx, 8000000Bh
0x180021050  mov     r9d, ebx
0x180021053  mov     edx, 25Eh
0x180021058  jmp     loc_180020F85
0x18002105d  mov     [rsp+100h+var_D8], r15
0x180021062  mov     rdi, [rbp+57h+var_D0]
0x180021066  mov     rax, [rdi]
0x180021069  mov     rbx, [rax+30h]
0x18002106d  lea     rcx, [rsp+100h+var_D8]
0x180021072  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021077  lea     r8, [rsp+100h+var_D8]
0x18002107c  xor     edx, edx
0x18002107e  mov     rcx, rdi
0x180021081  mov     rax, rbx
0x180021084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021089  mov     ebx, eax
0x18002108b  test    eax, eax
0x18002108d  jns     short loc_1800210AC
0x18002108f  mov     rcx, [rbp+5Fh]; this
0x180021093  mov     r9d, eax; char *
0x180021096  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18002109d  mov     edx, 262h; void *
0x1800210a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800210a7  jmp     loc_18002112C
0x1800210ac  mov     [rsp+100h+string], r15
0x1800210b1  mov     rdi, [rsp+100h+var_D8]
0x1800210b6  mov     rax, [rdi]
0x1800210b9  mov     rbx, [rax+50h]
0x1800210bd  xor     ecx, ecx; string
0x1800210bf  call    cs:__imp_WindowsDeleteString
0x1800210c5  mov     [rsp+100h+string], r15; int
0x1800210ca  mov     [rbp+57h+var_38], r15
0x1800210ce  mov     r9d, 3; unsigned int
0x1800210d4  lea     r8d, [r9+1]; unsigned int
0x1800210d8  lea     rdx, aUri; "uri"
0x1800210df  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800210e3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800210e8  nop
0x1800210e9  lea     r8, [rsp+100h+string]
0x1800210ee  mov     rdx, [rbp+57h+var_38]
0x1800210f2  mov     rcx, rdi
0x1800210f5  mov     rax, rbx
0x1800210f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210fd  mov     ebx, eax
0x1800210ff  test    eax, eax
0x180021101  jns     short loc_18002116F
0x180021103  mov     rcx, [rbp+5Fh]; this
0x180021107  mov     r9d, eax; char *
0x18002110a  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x180021111  mov     edx, 265h; void *
0x180021116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002111b  nop
0x18002111c  mov     rcx, [rsp+100h+string]; string
0x180021121  call    cs:__imp_WindowsDeleteString
0x180021127  mov     [rsp+100h+string], r15
0x18002112c  lea     rcx, [rsp+100h+var_D8]
0x180021131  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021136  nop
0x180021137  lea     rcx, [rbp+57h+var_B8]
0x18002113b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021140  nop
0x180021141  lea     rcx, [rbp+57h+var_D0]
0x180021145  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002114a  nop
0x18002114b  lea     rcx, [rbp+57h+var_C8]
0x18002114f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021154  nop
0x180021155  lea     rcx, [rbp+57h+var_B0]
0x180021159  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002115e  nop
0x18002115f  lea     rcx, [rbp+57h+var_A0]; this
0x180021163  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180021168  mov     eax, ebx
0x18002116a  jmp     loc_180021279
0x18002116f  xor     edx, edx; length
0x180021171  mov     rcx, [rsp+100h+string]; string
0x180021176  call    cs:__imp_WindowsGetStringRawBuffer
0x18002117c  mov     rcx, rax
0x18002117f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180021184  mov     r8, rax
0x180021187  mov     rdx, rcx
0x18002118a  mov     rcx, rsi
0x18002118d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180021192  cmp     [rsi+10h], r15
0x180021196  jz      short loc_180021209
0x180021198  xor     r8d, r8d
0x18002119b  lea     rdx, aHttps; "https://"
0x1800211a2  mov     rcx, rsi
0x1800211a5  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800211aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800211ae  jz      short loc_180021209
0x1800211b0  mov     rcx, rsi
0x1800211b3  call    ?RemoveTrailingForwardSlash@CloudPrintHelper@CloudPrint@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::RemoveTrailingForwardSlash(std::wstring &)
0x1800211b8  nop
0x1800211b9  mov     rcx, [rsp+100h+string]; string
0x1800211be  call    cs:__imp_WindowsDeleteString
0x1800211c4  mov     [rsp+100h+string], r15
0x1800211c9  lea     rcx, [rsp+100h+var_D8]
0x1800211ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211d3  nop
0x1800211d4  lea     rcx, [rbp+57h+var_B8]
0x1800211d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211dd  nop
0x1800211de  lea     rcx, [rbp+57h+var_D0]
0x1800211e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211e7  nop
0x1800211e8  lea     rcx, [rbp+57h+var_C8]
0x1800211ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211f1  nop
0x1800211f2  lea     rcx, [rbp+57h+var_B0]
0x1800211f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211fb  nop
0x1800211fc  lea     rcx, [rbp+57h+var_A0]; this
0x180021200  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180021205  xor     eax, eax
0x180021207  jmp     short loc_180021279
0x180021209  mov     rcx, rsi
0x18002120c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180021211  mov     r8, rax
0x180021214  lea     rdx, aEmptyStringOrI; "Empty string or Insecure endpoint retur"...
0x18002121b  lea     rcx, aCloudprintMpsp; "CloudPrint::MpsParser::ParseMpsMsGraphS"...
0x180021222  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180021227  nop
0x180021228  mov     rcx, [rsp+100h+string]; string
0x18002122d  call    cs:__imp_WindowsDeleteString
0x180021233  mov     [rsp+100h+string], r15
0x180021238  lea     rcx, [rsp+100h+var_D8]
0x18002123d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021242  nop
0x180021243  lea     rcx, [rbp+57h+var_B8]
0x180021247  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002124c  nop
0x18002124d  lea     rcx, [rbp+57h+var_D0]
0x180021251  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021256  nop
0x180021257  lea     rcx, [rbp+57h+var_C8]
0x18002125b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021260  nop
0x180021261  lea     rcx, [rbp+57h+var_B0]
0x180021265  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002126a  nop
0x18002126b  lea     rcx, [rbp+57h+var_A0]; this
0x18002126f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180021274  mov     eax, 8007000Dh
0x180021279  mov     rcx, [rbp+57h+var_30]
0x18002127d  xor     rcx, rsp; StackCookie
0x180021280  call    __security_check_cookie
0x180021285  mov     rbx, [rsp+100h+arg_10]
0x18002128d  add     rsp, 0E0h
0x180021294  pop     r15
0x180021296  pop     r14
0x180021298  pop     rdi
0x180021299  pop     rsi
0x18002129a  pop     rbp
0x18002129b  retn
```

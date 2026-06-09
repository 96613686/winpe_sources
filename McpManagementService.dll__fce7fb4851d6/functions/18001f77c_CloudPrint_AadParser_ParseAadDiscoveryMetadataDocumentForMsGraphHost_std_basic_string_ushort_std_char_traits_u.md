# CloudPrint::AadParser::ParseAadDiscoveryMetadataDocumentForMsGraphHost(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001f77c`
- end: `0x18001f99b`
- name: `?ParseAadDiscoveryMetadataDocumentForMsGraphHost@AadParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

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
- `0x18001bfe4`
- `0x18001c298`
- `0x18001ea64`
- `0x18001f77c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f8fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f8fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f948`

## string_xrefs

- `0x18001f7e4`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudPrint::AadParser::ParseAadDiscoveryMetadataDocumentForMsGraphHost(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v17; // [rsp+28h] [rbp-51h] BYREF
  __int64 v18; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v20[80]; // [rsp+40h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+17h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  CloudPrintHelperTelemetry::WatchCurrentThread(v20, "ParseAadDiscoveryMetadataDocumentForMsGraphHost");
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  v18 = 0;
  v17 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v22,
         (__int64)&v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 662;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
    goto LABEL_12;
  }
  v6 = v18;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v19);
  v3 = v7(v6, *(_QWORD *)(v8 + 24), &v17);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 665;
    goto LABEL_5;
  }
  string = 0;
  v9 = v17;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v17 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"msgraph_host", 0xDu, 0xCu);
  v11 = v10(v9, v22, &string);
  v4 = v11;
  if ( v11 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Assign<unsigned short>(a2, v14, v13);
    if ( *(_QWORD *)(a2 + 16) )
    {
      WindowsDeleteString(string);
      v4 = 0;
    }
    else
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::AadParser::ParseAadDiscoveryMetadataDocumentForMsGraphHost",
        L"Empty \"msgraph_host\" string from AAD");
      WindowsDeleteString(string);
      v4 = -2147024883;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
    WindowsDeleteString(string);
  }
  string = 0;
LABEL_12:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v20);
  return v4;
}

```

## disassembly

```asm
0x18001f77c  mov     [rsp-8+arg_10], rbx
0x18001f781  mov     [rsp-8+arg_18], rsi
0x18001f786  push    rbp
0x18001f787  push    rdi
0x18001f788  push    r14
0x18001f78a  lea     rbp, [rsp-47h]
0x18001f78f  sub     rsp, 0C0h
0x18001f796  mov     rax, cs:__security_cookie
0x18001f79d  xor     rax, rsp
0x18001f7a0  mov     [rbp+57h+var_20], rax
0x18001f7a4  mov     rsi, rdx
0x18001f7a7  mov     r14, rcx
0x18001f7aa  lea     rdx, aParseaaddiscov; "ParseAadDiscoveryMetadataDocumentForMsG"...
0x18001f7b1  lea     rcx, [rbp+57h+var_90]
0x18001f7b5  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001f7ba  nop
0x18001f7bb  mov     qword ptr [rsi+10h], 0
0x18001f7c3  mov     rcx, rsi
0x18001f7c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f7cb  xor     ecx, ecx
0x18001f7cd  mov     [rax], cx
0x18001f7d0  mov     [rbp+57h+var_A0], rcx
0x18001f7d4  mov     [rbp+57h+var_A8], rcx
0x18001f7d8  mov     [rbp+57h+var_28], rcx
0x18001f7dc  lea     r9d, [rcx+1Ch]; unsigned int
0x18001f7e0  lea     r8d, [rcx+1Dh]; unsigned int
0x18001f7e4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001f7eb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f7ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f7f4  lea     rdx, [rbp+57h+var_A0]
0x18001f7f8  mov     rcx, [rbp+57h+var_28]
0x18001f7fc  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x18001f801  mov     ebx, eax
0x18001f803  test    eax, eax
0x18001f805  jns     short loc_18001F80E
0x18001f807  mov     edx, 296h
0x18001f80c  jmp     short loc_18001F85A
0x18001f80e  mov     rdi, [rbp+57h+var_A0]
0x18001f812  mov     rax, [rdi]
0x18001f815  mov     rbx, [rax+30h]
0x18001f819  lea     rcx, [rbp+57h+var_A8]
0x18001f81d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f822  mov     rcx, r14
0x18001f825  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f82a  mov     [rbp+57h+var_98], rax
0x18001f82e  lea     rdx, [rbp+57h+var_98]
0x18001f832  lea     rcx, [rbp+57h+hstringHeader]
0x18001f836  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f83b  nop
0x18001f83c  lea     r8, [rbp+57h+var_A8]
0x18001f840  mov     rdx, [rax+18h]
0x18001f844  mov     rcx, rdi
0x18001f847  mov     rax, rbx
0x18001f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84f  mov     ebx, eax
0x18001f851  test    eax, eax
0x18001f853  jns     short loc_18001F872
0x18001f855  mov     edx, 299h; void *
0x18001f85a  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f861  mov     r9d, eax; char *
0x18001f864  mov     rcx, [rbp+5Fh]; this
0x18001f868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f86d  jmp     loc_18001F958
0x18001f872  mov     [rbp+57h+string], 0
0x18001f87a  mov     rdi, [rbp+57h+var_A8]
0x18001f87e  mov     rax, [rdi]
0x18001f881  mov     rbx, [rax+50h]
0x18001f885  xor     ecx, ecx; string
0x18001f887  call    cs:__imp_WindowsDeleteString
0x18001f88d  mov     [rbp+57h+string], 0
0x18001f895  mov     [rbp+57h+var_28], 0
0x18001f89d  mov     r9d, 0Ch; unsigned int
0x18001f8a3  lea     r8d, [r9+1]; unsigned int
0x18001f8a7  lea     rdx, aMsgraphHost; "msgraph_host"
0x18001f8ae  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f8b2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f8b7  nop
0x18001f8b8  lea     r8, [rbp+57h+string]
0x18001f8bc  mov     rdx, [rbp+57h+var_28]
0x18001f8c0  mov     rcx, rdi
0x18001f8c3  mov     rax, rbx
0x18001f8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8cb  mov     ebx, eax
0x18001f8cd  test    eax, eax
0x18001f8cf  jns     short loc_18001F8F6
0x18001f8d1  mov     rcx, [rbp+5Fh]; this
0x18001f8d5  mov     r9d, eax; char *
0x18001f8d8  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f8df  mov     edx, 29Dh; void *
0x18001f8e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f8e9  nop
0x18001f8ea  mov     rcx, [rbp+57h+string]; string
0x18001f8ee  call    cs:__imp_WindowsDeleteString
0x18001f8f4  jmp     short loc_18001F950
0x18001f8f6  xor     edx, edx; length
0x18001f8f8  mov     rcx, [rbp+57h+string]; string
0x18001f8fc  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f902  mov     rcx, rax
0x18001f905  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001f90a  mov     r8, rax
0x18001f90d  mov     rdx, rcx
0x18001f910  mov     rcx, rsi
0x18001f913  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001f918  cmp     qword ptr [rsi+10h], 0
0x18001f91d  jnz     short loc_18001F944
0x18001f91f  lea     rdx, aEmptyMsgraphHo; "Empty \"msgraph_host\" string from AAD"
0x18001f926  lea     rcx, aCloudprintAadp; "CloudPrint::AadParser::ParseAadDiscover"...
0x18001f92d  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001f932  nop
0x18001f933  mov     rcx, [rbp+57h+string]; string
0x18001f937  call    cs:__imp_WindowsDeleteString
0x18001f93d  mov     ebx, 8007000Dh
0x18001f942  jmp     short loc_18001F950
0x18001f944  mov     rcx, [rbp+57h+string]; string
0x18001f948  call    cs:__imp_WindowsDeleteString
0x18001f94e  xor     ebx, ebx
0x18001f950  mov     [rbp+57h+string], 0
0x18001f958  lea     rcx, [rbp+57h+var_A8]
0x18001f95c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f961  nop
0x18001f962  lea     rcx, [rbp+57h+var_A0]
0x18001f966  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f96b  nop
0x18001f96c  lea     rcx, [rbp+57h+var_90]; this
0x18001f970  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001f975  mov     eax, ebx
0x18001f977  mov     rcx, [rbp+57h+var_20]
0x18001f97b  xor     rcx, rsp; StackCookie
0x18001f97e  call    __security_check_cookie
0x18001f983  lea     r11, [rsp+0D0h+var_10]
0x18001f98b  mov     rbx, [r11+30h]
0x18001f98f  mov     rsi, [r11+38h]
0x18001f993  mov     rsp, r11
0x18001f996  pop     r14
0x18001f998  pop     rdi
0x18001f999  pop     rbp
0x18001f99a  retn
```

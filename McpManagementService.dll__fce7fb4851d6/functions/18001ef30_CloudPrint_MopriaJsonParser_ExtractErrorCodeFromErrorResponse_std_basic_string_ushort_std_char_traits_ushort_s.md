# CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001ef30`
- end: `0x18001f112`
- name: `?ExtractErrorCodeFromErrorResponse@MopriaJsonParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z`
- size: `482`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016184`
- `0x18001b128`

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
- `0x18001ea64`
- `0x18001ef30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f09e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f09e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f0bf`

## string_xrefs

- `0x18001ef98`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v11; // rax
  int v12; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  __int64 v18; // [rsp+28h] [rbp-51h] BYREF
  __int64 v19; // [rsp+30h] [rbp-49h] BYREF
  __int64 v20; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v21[80]; // [rsp+40h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+17h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  CloudPrintHelperTelemetry::WatchCurrentThread(v21, "ExtractErrorCodeFromErrorResponse");
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  v19 = 0;
  v18 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v23,
         (__int64)&v19);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 548;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
    goto LABEL_10;
  }
  v6 = v19;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v20);
  v3 = v7(v6, *(_QWORD *)(v8 + 24), &v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 551;
    goto LABEL_5;
  }
  string = 0;
  v9 = v18;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v18 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18003F0F8);
  v12 = v10(v9, *(_QWORD *)(v11 + 24), &string);
  v4 = v12;
  if ( v12 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Assign<unsigned short>(a2, v15, v14);
    WindowsDeleteString(string);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
    WindowsDeleteString(string);
  }
  string = 0;
LABEL_10:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v21);
  return v4;
}

```

## disassembly

```asm
0x18001ef30  mov     [rsp-8+arg_10], rbx
0x18001ef35  mov     [rsp-8+arg_18], rsi
0x18001ef3a  push    rbp
0x18001ef3b  push    rdi
0x18001ef3c  push    r14
0x18001ef3e  lea     rbp, [rsp-47h]
0x18001ef43  sub     rsp, 0C0h
0x18001ef4a  mov     rax, cs:__security_cookie
0x18001ef51  xor     rax, rsp
0x18001ef54  mov     [rbp+57h+var_20], rax
0x18001ef58  mov     rsi, rdx
0x18001ef5b  mov     r14, rcx
0x18001ef5e  lea     rdx, aExtracterrorco; "ExtractErrorCodeFromErrorResponse"
0x18001ef65  lea     rcx, [rbp+57h+var_90]
0x18001ef69  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001ef6e  nop
0x18001ef6f  mov     qword ptr [rsi+10h], 0
0x18001ef77  mov     rcx, rsi
0x18001ef7a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001ef7f  xor     ecx, ecx
0x18001ef81  mov     [rax], cx
0x18001ef84  mov     [rbp+57h+var_A0], rcx
0x18001ef88  mov     [rbp+57h+var_A8], rcx
0x18001ef8c  mov     [rbp+57h+var_28], rcx
0x18001ef90  lea     r9d, [rcx+1Ch]; unsigned int
0x18001ef94  lea     r8d, [rcx+1Dh]; unsigned int
0x18001ef98  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001ef9f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001efa3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001efa8  lea     rdx, [rbp+57h+var_A0]
0x18001efac  mov     rcx, [rbp+57h+var_28]
0x18001efb0  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x18001efb5  mov     ebx, eax
0x18001efb7  test    eax, eax
0x18001efb9  jns     short loc_18001EFC2
0x18001efbb  mov     edx, 224h
0x18001efc0  jmp     short loc_18001F00E
0x18001efc2  mov     rdi, [rbp+57h+var_A0]
0x18001efc6  mov     rax, [rdi]
0x18001efc9  mov     rbx, [rax+30h]
0x18001efcd  lea     rcx, [rbp+57h+var_A8]
0x18001efd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001efd6  mov     rcx, r14
0x18001efd9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001efde  mov     [rbp+57h+var_98], rax
0x18001efe2  lea     rdx, [rbp+57h+var_98]
0x18001efe6  lea     rcx, [rbp+57h+hstringHeader]
0x18001efea  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001efef  nop
0x18001eff0  lea     r8, [rbp+57h+var_A8]
0x18001eff4  mov     rdx, [rax+18h]
0x18001eff8  mov     rcx, rdi
0x18001effb  mov     rax, rbx
0x18001effe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f003  mov     ebx, eax
0x18001f005  test    eax, eax
0x18001f007  jns     short loc_18001F026
0x18001f009  mov     edx, 227h; void *
0x18001f00e  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f015  mov     r9d, eax; char *
0x18001f018  mov     rcx, [rbp+5Fh]; this
0x18001f01c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f021  jmp     loc_18001F0CF
0x18001f026  mov     [rbp+57h+string], 0
0x18001f02e  mov     rdi, [rbp+57h+var_A8]
0x18001f032  mov     rax, [rdi]
0x18001f035  mov     rbx, [rax+50h]
0x18001f039  xor     ecx, ecx; string
0x18001f03b  call    cs:__imp_WindowsDeleteString
0x18001f041  mov     [rbp+57h+string], 0
0x18001f049  lea     rdx, off_18003F0F8; "code"
0x18001f050  lea     rcx, [rbp+57h+hstringHeader]
0x18001f054  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f059  nop
0x18001f05a  lea     r8, [rbp+57h+string]
0x18001f05e  mov     rdx, [rax+18h]
0x18001f062  mov     rcx, rdi
0x18001f065  mov     rax, rbx
0x18001f068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f06d  mov     ebx, eax
0x18001f06f  test    eax, eax
0x18001f071  jns     short loc_18001F098
0x18001f073  mov     rcx, [rbp+5Fh]; this
0x18001f077  mov     r9d, eax; char *
0x18001f07a  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f081  mov     edx, 22Bh; void *
0x18001f086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f08b  nop
0x18001f08c  mov     rcx, [rbp+57h+string]; string
0x18001f090  call    cs:__imp_WindowsDeleteString
0x18001f096  jmp     short loc_18001F0C7
0x18001f098  xor     edx, edx; length
0x18001f09a  mov     rcx, [rbp+57h+string]; string
0x18001f09e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f0a4  mov     rcx, rax
0x18001f0a7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001f0ac  mov     r8, rax
0x18001f0af  mov     rdx, rcx
0x18001f0b2  mov     rcx, rsi
0x18001f0b5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001f0ba  nop
0x18001f0bb  mov     rcx, [rbp+57h+string]; string
0x18001f0bf  call    cs:__imp_WindowsDeleteString
0x18001f0c5  xor     ebx, ebx
0x18001f0c7  mov     [rbp+57h+string], 0
0x18001f0cf  lea     rcx, [rbp+57h+var_A8]
0x18001f0d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f0d8  nop
0x18001f0d9  lea     rcx, [rbp+57h+var_A0]
0x18001f0dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f0e2  nop
0x18001f0e3  lea     rcx, [rbp+57h+var_90]; this
0x18001f0e7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001f0ec  mov     eax, ebx
0x18001f0ee  mov     rcx, [rbp+57h+var_20]
0x18001f0f2  xor     rcx, rsp; StackCookie
0x18001f0f5  call    __security_check_cookie
0x18001f0fa  lea     r11, [rsp+0D0h+var_10]
0x18001f102  mov     rbx, [r11+30h]
0x18001f106  mov     rsi, [r11+38h]
0x18001f10a  mov     rsp, r11
0x18001f10d  pop     r14
0x18001f10f  pop     rdi
0x18001f110  pop     rbp
0x18001f111  retn
```

# AppServiceResourceHandler::GetResourceValFromResponseValueSet(Windows::Foundation::Collections::IPropertySet *,std::shared_ptr<CDPAppSvcApplication> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180040854`
- end: `0x180040954`
- name: `?GetResourceValFromResponseValueSet@AppServiceResourceHandler@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@AEBV?$shared_ptr@UCDPAppSvcApplication@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@7@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180028a64`
- `0x180028eb4`

## callees

- `0x180002a4c`
- `0x180004a58`
- `0x18000ecb8`
- `0x180027e64`
- `0x180028854`
- `0x180029304`
- `0x18002c570`
- `0x18003fe90`
- `0x18003ff10`
- `0x180040854`
- `0x18005c0fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004091b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004091b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AppServiceResourceHandler::GetResourceValFromResponseValueSet(
        __int64 a1,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  HSTRING v10; // rax
  int v11; // [rsp+30h] [rbp-98h] BYREF
  HSTRING v12; // [rsp+38h] [rbp-90h] BYREF
  HSTRING string; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v16[32]; // [rsp+80h] [rbp-48h] BYREF

  v11 = 0;
  if ( a2 )
  {
    try
    {
      PropertySetHelper::PropertySetHelper((PropertySetHelper *)v14, a2);
      v6 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a3 + 224LL);
      std::string::string((__int64)v15, v6);
      v7 = *(_QWORD *)cdp::UTF8toHSTRING(&string, v15);
      PropertySetHelper::GetString(v14, &v12, v7);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v15);
      v8 = cdp::HSTRINGtoUTF8(v16, v12);
      std::string::operator=(a4, v8);
      std::string::_Tidy_deallocate(v16);
      WindowsDeleteString(v12);
      v12 = 0;
      PropertySetHelper::~PropertySetHelper((PropertySetHelper *)v14);
    }
    catch ( ... )
    {
      LODWORD(v10) = GetCurrentThreadId();
      string = v10;
      LODWORD(v12) = 309;
      cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
        (__int64)&v11,
        (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                 "Failed to get the resource value from the response valueset.\"}",
        (__int64)"..\\appsvcresourcehandler.cpp",
        (__int64)&v12,
        (__int64)&string);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180040854  push    rbx
0x180040856  push    rsi
0x180040857  push    rdi
0x180040858  sub     rsp, 0B0h
0x18004085f  mov     rax, cs:__security_cookie
0x180040866  xor     rax, rsp
0x180040869  mov     [rsp+0C8h+var_28], rax
0x180040871  mov     rsi, r9
0x180040874  mov     rdi, r8
0x180040877  xor     ebx, ebx
0x180040879  mov     [rsp+0C8h+var_98], ebx
0x18004087d  test    rdx, rdx
0x180040880  jz      loc_180040937
0x180040886  lea     rcx, [rsp+0C8h+var_80]; this
0x18004088b  call    ??0PropertySetHelper@@QEAA@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180040890  nop
0x180040891  mov     rcx, [rdi]
0x180040894  add     rcx, 0E0h
0x18004089b  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800408a0  mov     rdx, rax
0x1800408a3  lea     rcx, [rsp+0C8h+var_68]
0x1800408a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800408ad  nop
0x1800408ae  lea     rdx, [rsp+0C8h+var_68]
0x1800408b3  lea     rcx, [rsp+0C8h+string]
0x1800408b8  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x1800408bd  nop
0x1800408be  mov     r8, [rax]
0x1800408c1  lea     rdx, [rsp+0C8h+var_90]
0x1800408c6  lea     rcx, [rsp+0C8h+var_80]
0x1800408cb  call    ?GetString@PropertySetHelper@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; PropertySetHelper::GetString(HSTRING__ *)
0x1800408d0  nop
0x1800408d1  mov     rcx, [rsp+0C8h+string]; string
0x1800408d6  call    cs:__imp_WindowsDeleteString
0x1800408dc  mov     [rsp+0C8h+string], rbx
0x1800408e1  lea     rcx, [rsp+0C8h+var_68]
0x1800408e6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800408eb  mov     rdx, [rsp+0C8h+var_90]
0x1800408f0  lea     rcx, [rsp+0C8h+var_48]
0x1800408f8  call    ?HSTRINGtoUTF8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAUHSTRING__@@@Z; cdp::HSTRINGtoUTF8(HSTRING__ * const)
0x1800408fd  mov     rdx, rax
0x180040900  mov     rcx, rsi
0x180040903  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180040908  lea     rcx, [rsp+0C8h+var_48]
0x180040910  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180040915  nop
0x180040916  mov     rcx, [rsp+0C8h+var_90]; string
0x18004091b  call    cs:__imp_WindowsDeleteString
0x180040921  mov     [rsp+0C8h+var_90], rbx
0x180040926  lea     rcx, [rsp+0C8h+var_80]; this
0x18004092b  call    ??1PropertySetHelper@@QEAA@XZ; PropertySetHelper::~PropertySetHelper(void)
0x180040930  nop
0x180040931  jmp     short loc_180040937
0x180040933  mov     ebx, [rsp+0C8h+var_98]
0x180040937  mov     eax, ebx
0x180040939  mov     rcx, [rsp+0C8h+var_28]
0x180040941  xor     rcx, rsp; StackCookie
0x180040944  call    __security_check_cookie
0x180040949  add     rsp, 0B0h
0x180040950  pop     rdi
0x180040951  pop     rsi
0x180040952  pop     rbx
0x180040953  retn
```

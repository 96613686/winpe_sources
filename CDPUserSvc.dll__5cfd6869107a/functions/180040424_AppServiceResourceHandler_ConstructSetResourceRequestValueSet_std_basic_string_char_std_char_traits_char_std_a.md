# AppServiceResourceHandler::ConstructSetResourceRequestValueSet(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::shared_ptr<CDPAppSvcApplication> const &,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180040424`
- end: `0x180040727`
- name: `?ConstructSetResourceRequestValueSet@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBV?$shared_ptr@UCDPAppSvcApplication@@@3@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028eb4`

## callees

- `0x180002a4c`
- `0x180003678`
- `0x180004a58`
- `0x18000ecb8`
- `0x180020cc4`
- `0x180021398`
- `0x180028854`
- `0x180029304`
- `0x18002c570`
- `0x18003fe90`
- `0x18003fec0`
- `0x180040424`
- `0x1800409b4`
- `0x180040c80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800405cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800405e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004068e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800405cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800405e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004068e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AppServiceResourceHandler::ConstructSetResourceRequestValueSet(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        HSTRING *a5)
{
  __int64 v9; // rdx
  HSTRING v10; // rsi
  __int64 v11; // rdx
  HSTRING *v12; // rax
  __int64 v13; // rdx
  HSTRING v14; // rsi
  __int64 v15; // rdx
  HSTRING *v16; // rax
  __int64 v17; // rdx
  HSTRING v18; // rsi
  __int64 v19; // rdx
  HSTRING *v20; // rax
  _QWORD *UnderlyingProperties; // rax
  HSTRING v22; // rax
  HSTRING string; // [rsp+30h] [rbp-A8h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-A0h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v26[24]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-58h] BYREF

  *a5 = 0;
  if ( *a4 )
  {
    try
    {
      v25 = 0;
      PropertySetHelper::PropertySetHelper((PropertySetHelper *)v26, 0);
      v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a4 + 160LL);
      std::string::string((__int64)v28, v9);
      v10 = *(HSTRING *)cdp::UTF8toHSTRING(&v24, v28);
      v11 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a4 + 96LL);
      std::string::string((__int64)v27, v11);
      v12 = (HSTRING *)cdp::UTF8toHSTRING(&string, v27);
      PropertySetHelper::SetString((PropertySetHelper *)v26, *v12, v10);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v27);
      WindowsDeleteString(v24);
      v24 = 0;
      std::string::_Tidy_deallocate(v28);
      v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
      std::string::string((__int64)v27, v13);
      v14 = *(HSTRING *)cdp::UTF8toHSTRING(&string, v27);
      v15 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a4 + 192LL);
      std::string::string((__int64)v28, v15);
      v16 = (HSTRING *)cdp::UTF8toHSTRING(&v24, v28);
      PropertySetHelper::SetString((PropertySetHelper *)v26, *v16, v14);
      WindowsDeleteString(v24);
      v24 = 0;
      std::string::_Tidy_deallocate(v28);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v27);
      v17 = std::_String_val<std::_Simple_types<char>>::_Myptr(a3);
      std::string::string((__int64)v27, v17);
      v18 = *(HSTRING *)cdp::UTF8toHSTRING(&string, v27);
      v19 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a4 + 224LL);
      std::string::string((__int64)v28, v19);
      v20 = (HSTRING *)cdp::UTF8toHSTRING(&v24, v28);
      PropertySetHelper::SetString((PropertySetHelper *)v26, *v20, v18);
      WindowsDeleteString(v24);
      v24 = 0;
      std::string::_Tidy_deallocate(v28);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v27);
      string = 0;
      UnderlyingProperties = (_QWORD *)PropertySetHelper::GetUnderlyingProperties(v26, &v24);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(&string, *UnderlyingProperties);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(&string);
      *a5 = string;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      PropertySetHelper::~PropertySetHelper((PropertySetHelper *)v26);
    }
    catch ( ... )
    {
      LODWORD(v22) = GetCurrentThreadId();
      v24 = v22;
      LODWORD(string) = 293;
      cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
        (__int64)&v25,
        (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                 "Failed to construct valueset for set-resource request or storing it in the out param.\"}",
        (__int64)"..\\appsvcresourcehandler.cpp",
        (__int64)&string,
        (__int64)&v24);
    }
    return 0;
  }
  else
  {
    v25 = -2147418113;
    LODWORD(string) = 277;
    Log<long &,char const (&)[40],int>(a1, a2, &v25, "..\\appsvcresourcehandler.cpp", &string);
    return v25;
  }
}

```

## disassembly

```asm
0x180040424  mov     [rsp+arg_0], rbx
0x180040429  push    rsi
0x18004042a  push    rdi
0x18004042b  push    r12
0x18004042d  push    r14
0x18004042f  push    r15
0x180040431  sub     rsp, 0B0h
0x180040438  mov     rax, cs:__security_cookie
0x18004043f  xor     rax, rsp
0x180040442  mov     [rsp+0D8h+var_38], rax
0x18004044a  mov     rdi, r9
0x18004044d  mov     r15, r8
0x180040450  mov     r14, rdx
0x180040453  mov     r12, [rsp+0D8h+arg_20]
0x18004045b  mov     qword ptr [r12], 0
0x180040463  cmp     qword ptr [r9], 0
0x180040467  jnz     short loc_18004049D
0x180040469  mov     [rsp+0D8h+var_98], 8000FFFFh
0x180040471  mov     dword ptr [rsp+0D8h+string], 115h
0x180040479  lea     rax, [rsp+0D8h+string]
0x18004047e  mov     [rsp+0D8h+var_B8], rax
0x180040483  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x18004048a  lea     r8, [rsp+0D8h+var_98]
0x18004048f  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180040494  mov     eax, [rsp+0D8h+var_98]
0x180040498  jmp     loc_1800406FF
0x18004049d  xor     ebx, ebx
0x18004049f  mov     [rsp+0D8h+var_98], ebx
0x1800404a3  xor     edx, edx; struct Windows::Foundation::Collections::IPropertySet *
0x1800404a5  lea     rcx, [rsp+0D8h+var_90]; this
0x1800404aa  call    ??0PropertySetHelper@@QEAA@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x1800404af  nop
0x1800404b0  mov     rcx, [rdi]
0x1800404b3  add     rcx, 0A0h
0x1800404ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800404bf  mov     rdx, rax
0x1800404c2  lea     rcx, [rsp+0D8h+var_58]
0x1800404ca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800404cf  nop
0x1800404d0  lea     rdx, [rsp+0D8h+var_58]
0x1800404d8  lea     rcx, [rsp+0D8h+var_A0]
0x1800404dd  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x1800404e2  nop
0x1800404e3  mov     rsi, [rax]
0x1800404e6  mov     rcx, [rdi]
0x1800404e9  add     rcx, 60h ; '`'
0x1800404ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800404f2  mov     rdx, rax
0x1800404f5  lea     rcx, [rsp+0D8h+var_78]
0x1800404fa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800404ff  nop
0x180040500  lea     rdx, [rsp+0D8h+var_78]
0x180040505  lea     rcx, [rsp+0D8h+string]
0x18004050a  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004050f  nop
0x180040510  mov     r8, rsi; HSTRING
0x180040513  mov     rdx, [rax]; HSTRING
0x180040516  lea     rcx, [rsp+0D8h+var_90]; this
0x18004051b  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x180040520  nop
0x180040521  mov     rcx, [rsp+0D8h+string]; string
0x180040526  call    cs:__imp_WindowsDeleteString
0x18004052c  mov     [rsp+0D8h+string], rbx
0x180040531  lea     rcx, [rsp+0D8h+var_78]
0x180040536  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004053b  nop
0x18004053c  mov     rcx, [rsp+0D8h+var_A0]; string
0x180040541  call    cs:__imp_WindowsDeleteString
0x180040547  mov     [rsp+0D8h+var_A0], rbx
0x18004054c  lea     rcx, [rsp+0D8h+var_58]
0x180040554  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180040559  mov     rcx, r14
0x18004055c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040561  mov     rdx, rax
0x180040564  lea     rcx, [rsp+0D8h+var_78]
0x180040569  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004056e  nop
0x18004056f  lea     rdx, [rsp+0D8h+var_78]
0x180040574  lea     rcx, [rsp+0D8h+string]
0x180040579  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x18004057e  nop
0x18004057f  mov     rsi, [rax]
0x180040582  mov     rcx, [rdi]
0x180040585  add     rcx, 0C0h
0x18004058c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040591  mov     rdx, rax
0x180040594  lea     rcx, [rsp+0D8h+var_58]
0x18004059c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800405a1  nop
0x1800405a2  lea     rdx, [rsp+0D8h+var_58]
0x1800405aa  lea     rcx, [rsp+0D8h+var_A0]
0x1800405af  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x1800405b4  nop
0x1800405b5  mov     r8, rsi; HSTRING
0x1800405b8  mov     rdx, [rax]; HSTRING
0x1800405bb  lea     rcx, [rsp+0D8h+var_90]; this
0x1800405c0  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x1800405c5  nop
0x1800405c6  mov     rcx, [rsp+0D8h+var_A0]; string
0x1800405cb  call    cs:__imp_WindowsDeleteString
0x1800405d1  mov     [rsp+0D8h+var_A0], rbx
0x1800405d6  lea     rcx, [rsp+0D8h+var_58]
0x1800405de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800405e3  nop
0x1800405e4  mov     rcx, [rsp+0D8h+string]; string
0x1800405e9  call    cs:__imp_WindowsDeleteString
0x1800405ef  mov     [rsp+0D8h+string], rbx
0x1800405f4  lea     rcx, [rsp+0D8h+var_78]
0x1800405f9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800405fe  mov     rcx, r15
0x180040601  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040606  mov     rdx, rax
0x180040609  lea     rcx, [rsp+0D8h+var_78]
0x18004060e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180040613  nop
0x180040614  lea     rdx, [rsp+0D8h+var_78]
0x180040619  lea     rcx, [rsp+0D8h+string]
0x18004061e  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180040623  nop
0x180040624  mov     rsi, [rax]
0x180040627  mov     rcx, [rdi]
0x18004062a  add     rcx, 0E0h
0x180040631  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040636  mov     rdx, rax
0x180040639  lea     rcx, [rsp+0D8h+var_58]
0x180040641  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180040646  nop
0x180040647  lea     rdx, [rsp+0D8h+var_58]
0x18004064f  lea     rcx, [rsp+0D8h+var_A0]
0x180040654  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180040659  nop
0x18004065a  mov     r8, rsi; HSTRING
0x18004065d  mov     rdx, [rax]; HSTRING
0x180040660  lea     rcx, [rsp+0D8h+var_90]; this
0x180040665  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x18004066a  nop
0x18004066b  mov     rcx, [rsp+0D8h+var_A0]; string
0x180040670  call    cs:__imp_WindowsDeleteString
0x180040676  mov     [rsp+0D8h+var_A0], rbx
0x18004067b  lea     rcx, [rsp+0D8h+var_58]
0x180040683  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180040688  nop
0x180040689  mov     rcx, [rsp+0D8h+string]; string
0x18004068e  call    cs:__imp_WindowsDeleteString
0x180040694  mov     [rsp+0D8h+string], rbx
0x180040699  lea     rcx, [rsp+0D8h+var_78]
0x18004069e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800406a3  mov     [rsp+0D8h+string], rbx
0x1800406a8  lea     rdx, [rsp+0D8h+var_A0]
0x1800406ad  lea     rcx, [rsp+0D8h+var_90]
0x1800406b2  call    ?GetUnderlyingProperties@PropertySetHelper@@QEBA?AV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; PropertySetHelper::GetUnderlyingProperties(void)
0x1800406b7  mov     rdx, [rax]
0x1800406ba  lea     rcx, [rsp+0D8h+string]
0x1800406bf  call    ??4?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(Windows::Foundation::Collections::IPropertySet *)
0x1800406c4  lea     rcx, [rsp+0D8h+var_A0]
0x1800406c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800406ce  lea     rcx, [rsp+0D8h+string]
0x1800406d3  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x1800406d8  mov     rax, [rsp+0D8h+string]
0x1800406dd  mov     [r12], rax
0x1800406e1  lea     rcx, [rsp+0D8h+string]
0x1800406e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800406eb  nop
0x1800406ec  lea     rcx, [rsp+0D8h+var_90]; this
0x1800406f1  call    ??1PropertySetHelper@@QEAA@XZ; PropertySetHelper::~PropertySetHelper(void)
0x1800406f6  nop
0x1800406f7  jmp     short loc_1800406FD
0x1800406f9  mov     ebx, [rsp+0D8h+var_98]
0x1800406fd  mov     eax, ebx
0x1800406ff  mov     rcx, [rsp+0D8h+var_38]
0x180040707  xor     rcx, rsp; StackCookie
0x18004070a  call    __security_check_cookie
0x18004070f  mov     rbx, [rsp+0D8h+arg_0]
0x180040717  add     rsp, 0B0h
0x18004071e  pop     r15
0x180040720  pop     r14
0x180040722  pop     r12
0x180040724  pop     rdi
0x180040725  pop     rsi
0x180040726  retn
```

# AppServiceResourceHandler::ConstructGetResourceRequestValueSet(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::shared_ptr<CDPAppSvcApplication> const &,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x1800401d8`
- end: `0x18004041b`
- name: `?ConstructGetResourceRequestValueSet@AppServiceResourceHandler@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$shared_ptr@UCDPAppSvcApplication@@@3@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028a64`

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
- `0x1800401d8`
- `0x1800409b4`
- `0x180040c80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800402c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800402e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004036e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004038c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800402c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800402e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004036e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004038c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AppServiceResourceHandler::ConstructGetResourceRequestValueSet(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        HSTRING *a4)
{
  __int64 v8; // rdx
  HSTRING v9; // rsi
  __int64 v10; // rdx
  HSTRING *v11; // rax
  __int64 v12; // rdx
  HSTRING v13; // rsi
  __int64 v14; // rdx
  HSTRING *v15; // rax
  _QWORD *UnderlyingProperties; // rax
  HSTRING v17; // rax
  HSTRING string; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-A0h] BYREF
  HSTRING v20; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+80h] [rbp-58h] BYREF

  *a4 = 0;
  if ( *a3 )
  {
    try
    {
      v19 = 0;
      PropertySetHelper::PropertySetHelper((PropertySetHelper *)v21, 0);
      v8 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a3 + 128LL);
      std::string::string((__int64)v23, v8);
      v9 = *(HSTRING *)cdp::UTF8toHSTRING(&v20, v23);
      v10 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a3 + 96LL);
      std::string::string((__int64)v22, v10);
      v11 = (HSTRING *)cdp::UTF8toHSTRING(&string, v22);
      PropertySetHelper::SetString((PropertySetHelper *)v21, *v11, v9);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v22);
      WindowsDeleteString(v20);
      v20 = 0;
      std::string::_Tidy_deallocate(v23);
      v12 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
      std::string::string((__int64)v22, v12);
      v13 = *(HSTRING *)cdp::UTF8toHSTRING(&string, v22);
      v14 = std::_String_val<std::_Simple_types<char>>::_Myptr(*a3 + 192LL);
      std::string::string((__int64)v23, v14);
      v15 = (HSTRING *)cdp::UTF8toHSTRING(&v20, v23);
      PropertySetHelper::SetString((PropertySetHelper *)v21, *v15, v13);
      WindowsDeleteString(v20);
      v20 = 0;
      std::string::_Tidy_deallocate(v23);
      WindowsDeleteString(string);
      string = 0;
      std::string::_Tidy_deallocate(v22);
      string = 0;
      UnderlyingProperties = (_QWORD *)PropertySetHelper::GetUnderlyingProperties(v21, &v20);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(&string, *UnderlyingProperties);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(&string);
      *a4 = string;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      PropertySetHelper::~PropertySetHelper((PropertySetHelper *)v21);
    }
    catch ( ... )
    {
      LODWORD(v17) = GetCurrentThreadId();
      v20 = v17;
      LODWORD(string) = 269;
      cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
        (__int64)&v19,
        (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                 "Failed to construct valueset for get-resource request or storing it in the out param.\"}",
        (__int64)"..\\appsvcresourcehandler.cpp",
        (__int64)&string,
        (__int64)&v20);
    }
    return 0;
  }
  else
  {
    v19 = -2147418113;
    LODWORD(string) = 255;
    Log<long &,char const (&)[40],int>(a1, a2, &v19, "..\\appsvcresourcehandler.cpp", &string);
    return v19;
  }
}

```

## disassembly

```asm
0x1800401d8  push    rbx
0x1800401da  push    rsi
0x1800401db  push    rdi
0x1800401dc  push    r14
0x1800401de  push    r15
0x1800401e0  sub     rsp, 0B0h
0x1800401e7  mov     rax, cs:__security_cookie
0x1800401ee  xor     rax, rsp
0x1800401f1  mov     [rsp+0D8h+var_38], rax
0x1800401f9  mov     r14, r9
0x1800401fc  mov     rdi, r8
0x1800401ff  mov     r15, rdx
0x180040202  mov     qword ptr [r9], 0
0x180040209  cmp     qword ptr [r8], 0
0x18004020d  jnz     short loc_180040243
0x18004020f  mov     [rsp+0D8h+var_A0], 8000FFFFh
0x180040217  mov     dword ptr [rsp+0D8h+string], 0FFh
0x18004021f  lea     rax, [rsp+0D8h+string]
0x180040224  mov     [rsp+0D8h+var_B8], rax
0x180040229  lea     r9, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180040230  lea     r8, [rsp+0D8h+var_A0]
0x180040235  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18004023a  mov     eax, [rsp+0D8h+var_A0]
0x18004023e  jmp     loc_1800403FC
0x180040243  xor     ebx, ebx
0x180040245  mov     [rsp+0D8h+var_A0], ebx
0x180040249  xor     edx, edx; struct Windows::Foundation::Collections::IPropertySet *
0x18004024b  lea     rcx, [rsp+0D8h+var_90]; this
0x180040250  call    ??0PropertySetHelper@@QEAA@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180040255  nop
0x180040256  mov     rcx, [rdi]
0x180040259  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18004025d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040262  mov     rdx, rax
0x180040265  lea     rcx, [rsp+0D8h+var_58]
0x18004026d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180040272  nop
0x180040273  lea     rdx, [rsp+0D8h+var_58]
0x18004027b  lea     rcx, [rsp+0D8h+var_98]
0x180040280  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180040285  nop
0x180040286  mov     rsi, [rax]
0x180040289  mov     rcx, [rdi]
0x18004028c  add     rcx, 60h ; '`'
0x180040290  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040295  mov     rdx, rax
0x180040298  lea     rcx, [rsp+0D8h+var_78]
0x18004029d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800402a2  nop
0x1800402a3  lea     rdx, [rsp+0D8h+var_78]
0x1800402a8  lea     rcx, [rsp+0D8h+string]
0x1800402ad  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x1800402b2  nop
0x1800402b3  mov     r8, rsi; HSTRING
0x1800402b6  mov     rdx, [rax]; HSTRING
0x1800402b9  lea     rcx, [rsp+0D8h+var_90]; this
0x1800402be  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x1800402c3  nop
0x1800402c4  mov     rcx, [rsp+0D8h+string]; string
0x1800402c9  call    cs:__imp_WindowsDeleteString
0x1800402cf  mov     [rsp+0D8h+string], rbx
0x1800402d4  lea     rcx, [rsp+0D8h+var_78]
0x1800402d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800402de  nop
0x1800402df  mov     rcx, [rsp+0D8h+var_98]; string
0x1800402e4  call    cs:__imp_WindowsDeleteString
0x1800402ea  mov     [rsp+0D8h+var_98], rbx
0x1800402ef  lea     rcx, [rsp+0D8h+var_58]
0x1800402f7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800402fc  mov     rcx, r15
0x1800402ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040304  mov     rdx, rax
0x180040307  lea     rcx, [rsp+0D8h+var_78]
0x18004030c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180040311  nop
0x180040312  lea     rdx, [rsp+0D8h+var_78]
0x180040317  lea     rcx, [rsp+0D8h+string]
0x18004031c  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180040321  nop
0x180040322  mov     rsi, [rax]
0x180040325  mov     rcx, [rdi]
0x180040328  add     rcx, 0C0h
0x18004032f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180040334  mov     rdx, rax
0x180040337  lea     rcx, [rsp+0D8h+var_58]
0x18004033f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180040344  nop
0x180040345  lea     rdx, [rsp+0D8h+var_58]
0x18004034d  lea     rcx, [rsp+0D8h+var_98]
0x180040352  call    ?UTF8toHSTRING@cdp@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UTF8toHSTRING(std::string const &)
0x180040357  nop
0x180040358  mov     r8, rsi; HSTRING
0x18004035b  mov     rdx, [rax]; HSTRING
0x18004035e  lea     rcx, [rsp+0D8h+var_90]; this
0x180040363  call    ?SetString@PropertySetHelper@@QEAAXPEAUHSTRING__@@0@Z; PropertySetHelper::SetString(HSTRING__ *,HSTRING__ *)
0x180040368  nop
0x180040369  mov     rcx, [rsp+0D8h+var_98]; string
0x18004036e  call    cs:__imp_WindowsDeleteString
0x180040374  mov     [rsp+0D8h+var_98], rbx
0x180040379  lea     rcx, [rsp+0D8h+var_58]
0x180040381  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180040386  nop
0x180040387  mov     rcx, [rsp+0D8h+string]; string
0x18004038c  call    cs:__imp_WindowsDeleteString
0x180040392  mov     [rsp+0D8h+string], rbx
0x180040397  lea     rcx, [rsp+0D8h+var_78]
0x18004039c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800403a1  mov     [rsp+0D8h+string], rbx
0x1800403a6  lea     rdx, [rsp+0D8h+var_98]
0x1800403ab  lea     rcx, [rsp+0D8h+var_90]
0x1800403b0  call    ?GetUnderlyingProperties@PropertySetHelper@@QEBA?AV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; PropertySetHelper::GetUnderlyingProperties(void)
0x1800403b5  mov     rdx, [rax]
0x1800403b8  lea     rcx, [rsp+0D8h+string]
0x1800403bd  call    ??4?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(Windows::Foundation::Collections::IPropertySet *)
0x1800403c2  lea     rcx, [rsp+0D8h+var_98]
0x1800403c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800403cc  lea     rcx, [rsp+0D8h+string]
0x1800403d1  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x1800403d6  mov     rax, [rsp+0D8h+string]
0x1800403db  mov     [r14], rax
0x1800403de  lea     rcx, [rsp+0D8h+string]
0x1800403e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800403e8  nop
0x1800403e9  lea     rcx, [rsp+0D8h+var_90]; this
0x1800403ee  call    ??1PropertySetHelper@@QEAA@XZ; PropertySetHelper::~PropertySetHelper(void)
0x1800403f3  nop
0x1800403f4  jmp     short loc_1800403FA
0x1800403f6  mov     ebx, [rsp+0D8h+var_A0]
0x1800403fa  mov     eax, ebx
0x1800403fc  mov     rcx, [rsp+0D8h+var_38]
0x180040404  xor     rcx, rsp; StackCookie
0x180040407  call    __security_check_cookie
0x18004040c  add     rsp, 0B0h
0x180040413  pop     r15
0x180040415  pop     r14
0x180040417  pop     rdi
0x180040418  pop     rsi
0x180040419  pop     rbx
0x18004041a  retn
```

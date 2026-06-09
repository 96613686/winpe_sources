# Windows::Service::Task::Protect(void)

- ea: `0x1402512d4`
- end: `0x14025149d`
- name: `?Protect@Task@Service@Windows@@AEAAXXZ`
- size: `457`
- prototype: `void __fastcall(Windows::Service::Task *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140250cfc`

## callees

- `0x1400413a8`
- `0x1402512d4`
- `0x140254d48`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140251323`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140251323`
- `OLEAUT32!__imp_SysFreeString` at `0x14025142c`
- `OLEAUT32!__imp_SysFreeString` at `0x14025142c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1402513f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14025140a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14025141b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1402513f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14025140a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14025141b`

## string_xrefs

- `0x140251460`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140251475`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x14025148a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402513b0`: `Microsoft\Windows\UpdateOrchestrator`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Service::Task::Protect(__int64 **this)
{
  HRESULT v2; // eax
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  const WCHAR *v6; // rdx
  int v7; // eax
  const char *v8; // r9
  int ppv; // [rsp+20h] [rbp-58h]
  BSTR bstrString; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v12; // [rsp+48h] [rbp-30h] BYREF
  HSTRING v13; // [rsp+50h] [rbp-28h] BYREF
  LPVOID v14; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v14 = 0;
  v2 = CoCreateInstance(
         &GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df,
         0,
         4u,
         &GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5,
         &v14);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v2,
        ppv);
    bstrString = 0;
    v3 = *this;
    v4 = **this;
    bstrString = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v4 + 152))(v3, &bstrString);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v13 = 0;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v13,
      bstrString);
    v12 = 0;
    v6 = (const WCHAR *)(this + 1);
    if ( (unsigned __int64)this[4] > 7 )
      v6 = *(const WCHAR **)v6;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v12,
      v6);
    string = 0;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &string,
      L"Microsoft\\Windows\\UpdateOrchestrator");
    v7 = (*(__int64 (__fastcall **)(LPVOID, HSTRING, HSTRING, HSTRING))(*(_QWORD *)v14 + 24LL))(v14, v12, string, v13);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v7,
        ppv);
    if ( string )
      WindowsDeleteString(string);
    if ( v12 )
      WindowsDeleteString(v12);
    if ( v13 )
      WindowsDeleteString(v13);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v14 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x11A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x1402512d4  push    rbx
0x1402512d6  sub     rsp, 70h
0x1402512da  mov     rax, cs:__security_cookie
0x1402512e1  xor     rax, rsp
0x1402512e4  mov     [rsp+78h+var_18], rax
0x1402512e9  mov     rbx, rcx
0x1402512ec  mov     [rsp+78h+var_48], 0
0x1402512f4  mov     [rsp+78h+var_48], 2
0x1402512fc  mov     [rsp+78h+var_20], 0
0x140251305  lea     rax, [rsp+78h+var_20]
0x14025130a  mov     qword ptr [rsp+78h+ppv], rax; int
0x14025130f  lea     r9, _GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5; riid
0x140251316  xor     edx, edx; pUnkOuter
0x140251318  lea     r8d, [rdx+4]; dwClsContext
0x14025131c  lea     rcx, _GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df; rclsid
0x140251323  call    cs:__imp_CoCreateInstance
0x140251329  mov     rcx, [rsp+78h]; this
0x14025132e  test    eax, eax
0x140251330  js      loc_14025145D
0x140251336  mov     [rsp+78h+bstrString], 0
0x14025133f  mov     rcx, [rbx]
0x140251342  mov     rax, [rcx]
0x140251345  mov     [rsp+78h+bstrString], 0
0x14025134e  lea     rdx, [rsp+78h+bstrString]
0x140251353  mov     rax, [rax+98h]
0x14025135a  call    _guard_dispatch_icall
0x14025135f  mov     rcx, [rsp+78h]; this
0x140251364  test    eax, eax
0x140251366  js      loc_140251472
0x14025136c  mov     [rsp+78h+var_28], 0
0x140251375  mov     rdx, [rsp+78h+bstrString]; sourceString
0x14025137a  lea     rcx, [rsp+78h+var_28]; string
0x14025137f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x140251384  nop
0x140251385  mov     [rsp+78h+var_30], 0
0x14025138e  lea     rdx, [rbx+8]
0x140251392  cmp     qword ptr [rdx+18h], 7
0x140251397  jbe     short loc_14025139C
0x140251399  mov     rdx, [rdx]; sourceString
0x14025139c  lea     rcx, [rsp+78h+var_30]; string
0x1402513a1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1402513a6  nop
0x1402513a7  mov     [rsp+78h+string], 0
0x1402513b0  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x1402513b7  lea     rcx, [rsp+78h+string]; string
0x1402513bc  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1402513c1  nop
0x1402513c2  mov     rcx, [rsp+78h+var_20]
0x1402513c7  mov     rax, [rcx]
0x1402513ca  mov     r9, [rsp+78h+var_28]
0x1402513cf  mov     r8, [rsp+78h+string]
0x1402513d4  mov     rdx, [rsp+78h+var_30]
0x1402513d9  mov     rax, [rax+18h]
0x1402513dd  call    _guard_dispatch_icall
0x1402513e2  mov     rcx, [rsp+78h]; this
0x1402513e7  test    eax, eax
0x1402513e9  js      loc_140251487
0x1402513ef  mov     rcx, [rsp+78h+string]; string
0x1402513f4  test    rcx, rcx
0x1402513f7  jz      short loc_140251400
0x1402513f9  call    cs:__imp_WindowsDeleteString
0x1402513ff  nop
0x140251400  mov     rcx, [rsp+78h+var_30]; string
0x140251405  test    rcx, rcx
0x140251408  jz      short loc_140251411
0x14025140a  call    cs:__imp_WindowsDeleteString
0x140251410  nop
0x140251411  mov     rcx, [rsp+78h+var_28]; string
0x140251416  test    rcx, rcx
0x140251419  jz      short loc_140251422
0x14025141b  call    cs:__imp_WindowsDeleteString
0x140251421  nop
0x140251422  mov     rcx, [rsp+78h+bstrString]; bstrString
0x140251427  test    rcx, rcx
0x14025142a  jz      short loc_140251433
0x14025142c  call    cs:__imp_SysFreeString
0x140251432  nop
0x140251433  mov     rcx, [rsp+78h+var_20]
0x140251438  test    rcx, rcx
0x14025143b  jz      short loc_14025144A
0x14025143d  mov     rax, [rcx]
0x140251440  mov     rax, [rax+10h]
0x140251444  call    _guard_dispatch_icall
0x140251449  nop
0x14025144a  mov     rcx, [rsp+78h+var_18]
0x14025144f  xor     rcx, rsp; StackCookie
0x140251452  call    __security_check_cookie
0x140251457  add     rsp, 70h
0x14025145b  pop     rbx
0x14025145c  retn
0x14025145d  mov     r9d, eax; char *
0x140251460  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140251467  mov     edx, 1C96h; void *
0x14025146c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251472  mov     r9d, eax; char *
0x140251475  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14025147c  mov     edx, 10Dh; void *
0x140251481  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251487  mov     r9d, eax; char *
0x14025148a  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251491  mov     edx, 118h; void *
0x140251496  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

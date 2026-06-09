# Details::GetLaunchUri(ushort const *,CloudExperienceHostAPI::Redirection::IRedirectionManager *)

- ea: `0x18002581c`
- end: `0x1800259a0`
- name: `?GetLaunchUri@Details@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEBGPEAUIRedirectionManager@Redirection@CloudExperienceHostAPI@@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180027080`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x18001197c`
- `0x180017a84`
- `0x180017c58`
- `0x1800211a0`
- `0x18002581c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025974`

## string_xrefs

- `0x1800258bd`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Details::GetLaunchUri(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD *); // rsi
  HSTRING v10; // rdx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-50h]
  int v14; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v17[1] = a1;
  v17[0] = a2;
  v13 = 0;
  string = 0;
  if ( a3 )
  {
    v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v5(a3, &string);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v6,
        0);
  }
  v16 = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         v19,
         &v16);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v7,
      v13);
  *a1 = 0;
  v14 = 1;
  v8 = v16;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v16 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  v10 = string;
  if ( !string )
  {
    v14 = 3;
    v10 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v17) + 24);
  }
  v11 = v9(v8, v10, a1);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v11,
      v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x18002581c  mov     [rsp-18h+arg_18], rbx
0x180025821  push    rbp
0x180025822  push    rsi
0x180025823  push    rdi
0x180025824  mov     rbp, rsp
0x180025827  sub     rsp, 70h
0x18002582b  mov     rax, cs:__security_cookie
0x180025832  xor     rax, rsp
0x180025835  mov     [rbp+var_8], rax
0x180025839  mov     rsi, r8
0x18002583c  mov     rdi, rcx
0x18002583f  mov     [rbp+var_30], rcx
0x180025843  mov     [rbp+var_38], rdx
0x180025847  mov     [rbp+var_50], 0
0x18002584e  mov     [rbp+string], 0
0x180025856  test    r8, r8
0x180025859  jz      short loc_1800258A3
0x18002585b  mov     rax, [r8]
0x18002585e  mov     rbx, [rax+40h]
0x180025862  xor     ecx, ecx; string
0x180025864  call    cs:__imp_WindowsDeleteString
0x18002586b  nop     dword ptr [rax+rax+00h]
0x180025870  mov     [rbp+string], 0
0x180025878  lea     rdx, [rbp+string]
0x18002587c  mov     rcx, rsi
0x18002587f  mov     rax, rbx
0x180025882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025887  mov     rcx, [rbp+18h]; this
0x18002588b  test    eax, eax
0x18002588d  jns     short loc_1800258A3
0x18002588f  mov     r9d, eax; char *
0x180025892  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025899  mov     edx, 24h ; '$'; void *
0x18002589e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800258a3  mov     [rbp+var_40], 0
0x1800258ab  mov     [rbp+var_10], 0
0x1800258b3  mov     r9d, 16h; unsigned int
0x1800258b9  lea     r8d, [r9+1]; unsigned int
0x1800258bd  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800258c4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800258c8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800258cd  nop
0x1800258ce  lea     rdx, [rbp+var_40]
0x1800258d2  mov     rcx, [rbp+var_10]
0x1800258d6  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800258db  mov     rcx, [rbp+18h]; this
0x1800258df  test    eax, eax
0x1800258e1  jns     short loc_1800258F8
0x1800258e3  mov     r9d, eax; char *
0x1800258e6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800258ed  mov     edx, 29h ; ')'; void *
0x1800258f2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800258f8  mov     qword ptr [rdi], 0
0x1800258ff  mov     [rbp+var_50], 1
0x180025906  mov     rbx, [rbp+var_40]
0x18002590a  mov     rax, [rbx]
0x18002590d  mov     rsi, [rax+30h]
0x180025911  mov     rcx, rdi
0x180025914  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025919  mov     rdx, [rbp+string]
0x18002591d  test    rdx, rdx
0x180025920  jnz     short loc_18002593B
0x180025922  lea     rdx, [rbp+var_38]
0x180025926  lea     rcx, [rbp+hstringHeader]
0x18002592a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002592f  nop
0x180025930  mov     [rbp+var_50], 3
0x180025937  mov     rdx, [rax+18h]
0x18002593b  mov     r8, rdi
0x18002593e  mov     rcx, rbx
0x180025941  mov     rax, rsi
0x180025944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025949  mov     rcx, [rbp+18h]; this
0x18002594d  test    eax, eax
0x18002594f  jns     short loc_180025966
0x180025951  mov     r9d, eax; char *
0x180025954  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002595b  mov     edx, 2Bh ; '+'; void *
0x180025960  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025966  lea     rcx, [rbp+var_40]
0x18002596a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002596f  nop
0x180025970  mov     rcx, [rbp+string]; string
0x180025974  call    cs:__imp_WindowsDeleteString
0x18002597b  nop     dword ptr [rax+rax+00h]
0x180025980  mov     rax, rdi
0x180025983  mov     rcx, [rbp+var_8]
0x180025987  xor     rcx, rsp; StackCookie
0x18002598a  call    __security_check_cookie
0x18002598f  mov     rbx, [rsp+70h+arg_18]
0x180025997  add     rsp, 70h
0x18002599b  pop     rdi
0x18002599c  pop     rsi
0x18002599d  pop     rbp
0x18002599e  retn
```

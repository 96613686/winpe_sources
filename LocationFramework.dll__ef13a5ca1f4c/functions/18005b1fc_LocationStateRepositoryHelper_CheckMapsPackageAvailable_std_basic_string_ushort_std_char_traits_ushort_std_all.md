# LocationStateRepositoryHelper::CheckMapsPackageAvailable(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005b1fc`
- end: `0x18005b488`
- name: `?CheckMapsPackageAvailable@LocationStateRepositoryHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006a280`

## callees

- `0x180012310`
- `0x1800142c4`
- `0x180014340`
- `0x180020c64`
- `0x18005b1fc`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b258`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005b258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005b242`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b27a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b31d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b27a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b31d`

## string_xrefs

- `0x18005b2a1`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LocationStateRepositoryHelper::CheckMapsPackageAvailable(__int64 a1)
{
  HRESULT v2; // eax
  HSTRING v3; // rbx
  int ActivationFactory; // eax
  int v5; // ebx
  __int64 v6; // rcx
  HSTRING v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, HSTRING, __int64 *); // rbx
  wil::details *v15; // [rsp+28h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  __int64 v18; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h] BYREF
  __int64 v20; // [rsp+60h] [rbp+7h] BYREF
  __int64 v21; // [rsp+68h] [rbp+Fh] BYREF
  int v22; // [rsp+70h] [rbp+17h] BYREF
  __int64 v23; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v21 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  v3 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v21);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v15) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
      "LocationStateRepositoryHelper::CheckMapsPackageAvailable",
      "GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_StateRepository_Application).Get(), &applicationStatics)",
      v15,
      (int)hstringHeader.Reserved.Reserved1);
    v6 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return (unsigned int)v5;
  }
  v23 = 0;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  v8 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v5 = RoGetActivationFactory(v8, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v23);
  if ( v5 < 0 )
  {
LABEL_15:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    return (unsigned int)v5;
  }
  v19 = 0;
  v9 = v23;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v11);
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18);
  v5 = v10(v9, *(_QWORD *)(v12 + 24), &v19);
  if ( v5 < 0 )
  {
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    goto LABEL_15;
  }
  v20 = 0;
  v13 = v21;
  v14 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 288LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Microsoft.WindowsMaps_8wekyb3d8bbwe",
    0x24u,
    0x23u);
  v5 = v14(v13, v19, string, &v20);
  if ( v5 < 0 || (v22 = 0, v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 56LL))(v20, &v22), v5 < 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    goto LABEL_9;
  }
  if ( !v22 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v5 = -2147418113;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  return 0;
}

```

## disassembly

```asm
0x18005b1fc  push    rbp
0x18005b1fe  push    rbx
0x18005b1ff  push    rsi
0x18005b200  push    rdi
0x18005b201  lea     rbp, [rsp-3Fh]
0x18005b206  sub     rsp, 98h
0x18005b20d  mov     rax, cs:__security_cookie
0x18005b214  xor     rax, rsp
0x18005b217  mov     [rbp+57h+var_30], rax
0x18005b21b  mov     rsi, rcx
0x18005b21e  mov     [rbp+57h+var_48], 0
0x18005b226  mov     [rbp+57h+string], 0
0x18005b22e  lea     r9, [rbp+57h+string]; string
0x18005b232  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005b236  mov     edx, 2Ch ; ','; length
0x18005b23b  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18005b242  call    cs:__imp_WindowsCreateStringReference
0x18005b248  test    eax, eax
0x18005b24a  jns     short loc_18005B25F
0x18005b24c  xor     r9d, r9d; lpArguments
0x18005b24f  xor     r8d, r8d; nNumberOfArguments
0x18005b252  lea     edx, [r9+1]; dwExceptionFlags
0x18005b256  mov     ecx, eax; dwExceptionCode
0x18005b258  call    cs:__imp_RaiseException
0x18005b25e  int     3; Trap to Debugger
0x18005b25f  mov     rbx, [rbp+57h+string]
0x18005b263  lea     rcx, [rbp+57h+var_48]
0x18005b267  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b26c  lea     r8, [rbp+57h+var_48]
0x18005b270  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18005b277  mov     rcx, rbx
0x18005b27a  call    cs:__imp_RoGetActivationFactory
0x18005b280  mov     ebx, eax
0x18005b282  test    eax, eax
0x18005b284  jns     short loc_18005B2D8
0x18005b286  mov     rcx, [rbp+5Fh]; this
0x18005b28a  mov     dword ptr [rsp+0B0h+var_88], eax; wil::details *
0x18005b28e  lea     rax, aGetactivationf_1; "GetActivationFactory( HStringReference("...
0x18005b295  mov     [rsp+0B0h+var_90], rax; char *
0x18005b29a  lea     r9, aLocationstater; "LocationStateRepositoryHelper::CheckMap"...
0x18005b2a1  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18005b2a8  mov     edx, 1Ch; void *
0x18005b2ad  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18005b2b2  nop
0x18005b2b3  mov     rcx, [rbp+57h+var_48]
0x18005b2b7  test    rcx, rcx
0x18005b2ba  jz      short loc_18005B2D1
0x18005b2bc  mov     [rbp+57h+var_48], 0
0x18005b2c4  mov     rax, [rcx]
0x18005b2c7  mov     rax, [rax+10h]
0x18005b2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2d0  nop
0x18005b2d1  mov     eax, ebx
0x18005b2d3  jmp     loc_18005B470
0x18005b2d8  mov     [rbp+57h+var_38], 0
0x18005b2e0  mov     [rbp+57h+string], 0
0x18005b2e8  mov     r9d, 25h ; '%'; unsigned int
0x18005b2ee  lea     r8d, [r9+1]; unsigned int
0x18005b2f2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18005b2f9  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005b2fd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005b302  mov     rbx, [rbp+57h+string]
0x18005b306  lea     rcx, [rbp+57h+var_38]
0x18005b30a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b30f  lea     r8, [rbp+57h+var_38]
0x18005b313  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18005b31a  mov     rcx, rbx
0x18005b31d  call    cs:__imp_RoGetActivationFactory
0x18005b323  mov     ebx, eax
0x18005b325  test    eax, eax
0x18005b327  js      loc_18005B433
0x18005b32d  mov     [rbp+57h+var_58], 0
0x18005b335  mov     rdi, [rbp+57h+var_38]
0x18005b339  mov     rax, [rdi]
0x18005b33c  mov     rbx, [rax+50h]
0x18005b340  lea     rcx, [rbp+57h+var_58]
0x18005b344  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b349  mov     rcx, rsi
0x18005b34c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b351  mov     [rbp+57h+var_60], rax
0x18005b355  lea     rdx, [rbp+57h+var_60]
0x18005b359  lea     rcx, [rbp+57h+hstringHeader]
0x18005b35d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005b362  nop
0x18005b363  lea     r8, [rbp+57h+var_58]
0x18005b367  mov     rdx, [rax+18h]
0x18005b36b  mov     rcx, rdi
0x18005b36e  mov     rax, rbx
0x18005b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b376  mov     ebx, eax
0x18005b378  test    eax, eax
0x18005b37a  jns     short loc_18005B38A
0x18005b37c  lea     rcx, [rbp+57h+var_58]
0x18005b380  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b385  jmp     loc_18005B433
0x18005b38a  mov     [rbp+57h+var_50], 0
0x18005b392  mov     rdi, [rbp+57h+var_48]
0x18005b396  mov     rax, [rdi]
0x18005b399  mov     rbx, [rax+120h]
0x18005b3a0  lea     rcx, [rbp+57h+var_50]
0x18005b3a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b3a9  mov     [rbp+57h+string], 0
0x18005b3b1  mov     r9d, 23h ; '#'; unsigned int
0x18005b3b7  lea     r8d, [r9+1]; unsigned int
0x18005b3bb  lea     rdx, aMicrosoftWindo_0; "Microsoft.WindowsMaps_8wekyb3d8bbwe"
0x18005b3c2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005b3c6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005b3cb  nop
0x18005b3cc  lea     r9, [rbp+57h+var_50]
0x18005b3d0  mov     r8, [rbp+57h+string]
0x18005b3d4  mov     rdx, [rbp+57h+var_58]
0x18005b3d8  mov     rcx, rdi
0x18005b3db  mov     rax, rbx
0x18005b3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3e3  mov     ebx, eax
0x18005b3e5  test    eax, eax
0x18005b3e7  jns     short loc_18005B3F4
0x18005b3e9  lea     rcx, [rbp+57h+var_50]
0x18005b3ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b3f2  jmp     short loc_18005B37C
0x18005b3f4  mov     [rbp+57h+var_40], 0
0x18005b3fb  mov     rcx, [rbp+57h+var_50]
0x18005b3ff  mov     rax, [rcx]
0x18005b402  lea     rdx, [rbp+57h+var_40]
0x18005b406  mov     rax, [rax+38h]
0x18005b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b40f  mov     ebx, eax
0x18005b411  test    eax, eax
0x18005b413  js      short loc_18005B3E9
0x18005b415  lea     rcx, [rbp+57h+var_50]
0x18005b419  cmp     [rbp+57h+var_40], 0
0x18005b41d  ja      short loc_18005B44B
0x18005b41f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b424  nop
0x18005b425  lea     rcx, [rbp+57h+var_58]
0x18005b429  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b42e  mov     ebx, 8000FFFFh
0x18005b433  lea     rcx, [rbp+57h+var_38]
0x18005b437  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b43c  nop
0x18005b43d  lea     rcx, [rbp+57h+var_48]
0x18005b441  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b446  jmp     loc_18005B2D1
0x18005b44b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b450  nop
0x18005b451  lea     rcx, [rbp+57h+var_58]
0x18005b455  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b45a  nop
0x18005b45b  lea     rcx, [rbp+57h+var_38]
0x18005b45f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b464  nop
0x18005b465  lea     rcx, [rbp+57h+var_48]
0x18005b469  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005b46e  xor     eax, eax
0x18005b470  mov     rcx, [rbp+57h+var_30]
0x18005b474  xor     rcx, rsp; StackCookie
0x18005b477  call    __security_check_cookie
0x18005b47c  add     rsp, 98h
0x18005b483  pop     rdi
0x18005b484  pop     rsi
0x18005b485  pop     rbx
0x18005b486  pop     rbp
0x18005b487  retn
```

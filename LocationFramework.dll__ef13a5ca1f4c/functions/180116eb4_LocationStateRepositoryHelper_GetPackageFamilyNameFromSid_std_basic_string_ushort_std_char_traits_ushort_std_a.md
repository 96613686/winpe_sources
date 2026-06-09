# LocationStateRepositoryHelper::GetPackageFamilyNameFromSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180116eb4`
- end: `0x1801171b8`
- name: `?GetPackageFamilyNameFromSid@LocationStateRepositoryHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018f40`

## callees

- `0x180012310`
- `0x1800142c4`
- `0x180014340`
- `0x18001be08`
- `0x180020880`
- `0x180020c64`
- `0x180022da4`
- `0x18009c310`
- `0x1800a98c0`
- `0x180116eb4`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180117136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180117136`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801170d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011714c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801170d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180117123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011714c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116f2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116f2f`

## string_xrefs

- `0x180116f56`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`
- `0x180116fd9`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`
- `0x18011703d`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`
- `0x1801170a9`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`
- `0x18011710d`: `onecoreuap\drivers\MobilePC\Location\Product\Common\inc\LocationStateRepositoryHelper.h`
- `0x180116f4f`: `LocationStateRepositoryHelper::GetPackageFamilyNameFromSid`
- `0x180116fd2`: `LocationStateRepositoryHelper::GetPackageFamilyNameFromSid`
- `0x180117036`: `LocationStateRepositoryHelper::GetPackageFamilyNameFromSid`
- `0x1801170a2`: `LocationStateRepositoryHelper::GetPackageFamilyNameFromSid`
- `0x180117106`: `LocationStateRepositoryHelper::GetPackageFamilyNameFromSid`
- `0x180116fc6`: `packageFamilyStatics->FindByPackageSID(HStringReference(PackageSid.c_str()).Get(), &packageFamilies)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LocationStateRepositoryHelper::GetPackageFamilyNameFromSid(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  PCWSTR StringRawBuffer; // rax
  wil::details *v22; // [rsp+28h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+48h] [rbp-38h]
  __int64 v25; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  __int64 v27; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v28; // [rsp+68h] [rbp-18h] BYREF
  __int64 v29; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+18h]

  std::wstring::_Eos(a2, 0);
  v29 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageFamily",
    0x2Fu,
    0x2Eu);
  v4 = v24;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v29);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v22) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
      "LocationStateRepositoryHelper::GetPackageFamilyNameFromSid",
      "GetActivationFactory( HStringReference(RuntimeClass_Windows_Internal_StateRepository_PackageFamily).Get(), &packageFamilyStatics)",
      v22,
      (int)hstringHeader.Reserved.Reserved1);
    goto LABEL_17;
  }
  v25 = 0;
  v7 = v29;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 160LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  string = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v9);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
  v11 = v8(v7, *(_QWORD *)(v10 + 24), &v25);
  v6 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v22) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
      "LocationStateRepositoryHelper::GetPackageFamilyNameFromSid",
      "packageFamilyStatics->FindByPackageSID(HStringReference(PackageSid.c_str()).Get(), &packageFamilies)",
      v22,
      (int)hstringHeader.Reserved.Reserved1);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    goto LABEL_17;
  }
  v28 = 0;
  v27 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v28);
  v6 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v22) = v12;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
      "LocationStateRepositoryHelper::GetPackageFamilyNameFromSid",
      "packageFamilies->get_Size(&familyCount)",
      v22,
      (int)hstringHeader.Reserved.Reserved1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_5;
  }
  for ( i = 0; i < v28; ++i )
  {
    v14 = v25;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v16 = v15(v14, i, &v27);
    if ( v16 >= 0 )
    {
      string = 0;
      v17 = v27;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 88LL);
      WindowsDeleteString(0);
      string = 0;
      v19 = v18(v17, &string);
      if ( v19 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        std::wstring::assign(a2, StringRawBuffer);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
        v6 = 0;
        goto LABEL_17;
      }
      LODWORD(v22) = v19;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
        "LocationStateRepositoryHelper::GetPackageFamilyNameFromSid",
        "packageFamily->get_PackageFamilyName(result.GetAddressOf())",
        (const char *)v22,
        (int)hstringHeader.Reserved.Reserved1);
      WindowsDeleteString(string);
    }
    else
    {
      LODWORD(v22) = v16;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Common\\inc\\LocationStateRepositoryHelper.h",
        "LocationStateRepositoryHelper::GetPackageFamilyNameFromSid",
        "packageFamilies->GetAt(i, &packageFamily)",
        (const char *)v22,
        (int)hstringHeader.Reserved.Reserved1);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v6 = -2147023728;
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  return v6;
}

```

## disassembly

```asm
0x180116eb4  mov     [rsp-18h+arg_10], rbx
0x180116eb9  mov     [rsp-18h+arg_18], rsi
0x180116ebe  push    rbp
0x180116ebf  push    rdi
0x180116ec0  push    r14
0x180116ec2  mov     rbp, rsp
0x180116ec5  sub     rsp, 80h
0x180116ecc  mov     rax, cs:__security_cookie
0x180116ed3  xor     rax, rsp
0x180116ed6  mov     [rbp+var_8], rax
0x180116eda  mov     r14, rdx
0x180116edd  mov     rsi, rcx
0x180116ee0  xor     edx, edx
0x180116ee2  mov     rcx, r14
0x180116ee5  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180116eea  mov     [rbp+var_10], 0
0x180116ef2  mov     [rbp+var_38], 0
0x180116efa  mov     r9d, 2Eh ; '.'; unsigned int
0x180116f00  lea     r8d, [r9+1]; unsigned int
0x180116f04  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180116f0b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180116f0f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180116f14  mov     rbx, [rbp+var_38]
0x180116f18  lea     rcx, [rbp+var_10]
0x180116f1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180116f21  lea     r8, [rbp+var_10]
0x180116f25  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x180116f2c  mov     rcx, rbx
0x180116f2f  call    cs:__imp_RoGetActivationFactory
0x180116f35  mov     ebx, eax
0x180116f37  test    eax, eax
0x180116f39  jns     short loc_180116F6C
0x180116f3b  mov     rcx, [rbp+18h]; this
0x180116f3f  mov     dword ptr [rsp+80h+var_58], eax; wil::details *
0x180116f43  lea     rax, aGetactivationf_0; "GetActivationFactory( HStringReference("...
0x180116f4a  mov     [rsp+80h+var_60], rax; char *
0x180116f4f  lea     r9, aLocationstater_0; "LocationStateRepositoryHelper::GetPacka"...
0x180116f56  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180116f5d  mov     edx, 35h ; '5'; void *
0x180116f62  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180116f67  jmp     loc_180117189
0x180116f6c  mov     [rbp+var_30], 0
0x180116f74  mov     rdi, [rbp+var_10]
0x180116f78  mov     rax, [rdi]
0x180116f7b  mov     rbx, [rax+0A0h]
0x180116f82  lea     rcx, [rbp+var_30]
0x180116f86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180116f8b  mov     rcx, rsi
0x180116f8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180116f93  mov     [rbp+string], rax
0x180116f97  lea     rdx, [rbp+string]
0x180116f9b  lea     rcx, [rbp+hstringHeader]
0x180116f9f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180116fa4  nop
0x180116fa5  lea     r8, [rbp+var_30]
0x180116fa9  mov     rdx, [rax+18h]
0x180116fad  mov     rcx, rdi
0x180116fb0  mov     rax, rbx
0x180116fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116fb8  mov     ebx, eax
0x180116fba  test    eax, eax
0x180116fbc  jns     short loc_180116FF9
0x180116fbe  mov     rcx, [rbp+18h]; this
0x180116fc2  mov     dword ptr [rsp+80h+var_58], eax; wil::details *
0x180116fc6  lea     rax, aPackagefamilys; "packageFamilyStatics->FindByPackageSID("...
0x180116fcd  mov     [rsp+80h+var_60], rax; char *
0x180116fd2  lea     r9, aLocationstater_0; "LocationStateRepositoryHelper::GetPacka"...
0x180116fd9  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180116fe0  mov     edx, 38h ; '8'; void *
0x180116fe5  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180116fea  nop
0x180116feb  lea     rcx, [rbp+var_30]
0x180116fef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180116ff4  jmp     loc_180117189
0x180116ff9  mov     [rbp+var_18], 0
0x180117000  mov     [rbp+var_20], 0
0x180117008  mov     rcx, [rbp+var_30]
0x18011700c  mov     rax, [rcx]
0x18011700f  lea     rdx, [rbp+var_18]
0x180117013  mov     rax, [rax+38h]
0x180117017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011701c  mov     ebx, eax
0x18011701e  test    eax, eax
0x180117020  jns     short loc_18011705A
0x180117022  mov     rcx, [rbp+18h]; this
0x180117026  mov     dword ptr [rsp+80h+var_58], eax; wil::details *
0x18011702a  lea     rax, aPackagefamilie; "packageFamilies->get_Size(&familyCount)"
0x180117031  mov     [rsp+80h+var_60], rax; char *
0x180117036  lea     r9, aLocationstater_0; "LocationStateRepositoryHelper::GetPacka"...
0x18011703d  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180117044  mov     edx, 3Ch ; '<'; void *
0x180117049  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011704e  nop
0x18011704f  lea     rcx, [rbp+var_20]
0x180117053  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117058  jmp     short loc_180116FEB
0x18011705a  xor     esi, esi
0x18011705c  cmp     esi, [rbp+var_18]
0x18011705f  jnb     loc_180117171
0x180117065  mov     rdi, [rbp+var_30]
0x180117069  mov     rax, [rdi]
0x18011706c  mov     rbx, [rax+30h]
0x180117070  lea     rcx, [rbp+var_20]
0x180117074  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117079  lea     r8, [rbp+var_20]
0x18011707d  mov     edx, esi
0x18011707f  mov     rcx, rdi
0x180117082  mov     rax, rbx
0x180117085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011708a  mov     rcx, [rbp+18h]; this
0x18011708e  test    eax, eax
0x180117090  jns     short loc_1801170BC
0x180117092  mov     dword ptr [rsp+80h+var_58], eax; char *
0x180117096  lea     rax, aPackagefamilie_0; "packageFamilies->GetAt(i, &packageFamil"...
0x18011709d  mov     [rsp+80h+var_60], rax; char *
0x1801170a2  lea     r9, aLocationstater_0; "LocationStateRepositoryHelper::GetPacka"...
0x1801170a9  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1801170b0  mov     edx, 3Fh ; '?'; void *
0x1801170b5  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801170ba  jmp     short loc_180117129
0x1801170bc  mov     [rbp+string], 0
0x1801170c4  mov     rdi, [rbp+var_20]
0x1801170c8  mov     rax, [rdi]
0x1801170cb  mov     rbx, [rax+58h]
0x1801170cf  xor     ecx, ecx; string
0x1801170d1  call    cs:__imp_WindowsDeleteString
0x1801170d7  mov     [rbp+string], 0
0x1801170df  lea     rdx, [rbp+string]
0x1801170e3  mov     rcx, rdi
0x1801170e6  mov     rax, rbx
0x1801170e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801170ee  mov     rcx, [rbp+18h]; this
0x1801170f2  test    eax, eax
0x1801170f4  jns     short loc_180117130
0x1801170f6  mov     dword ptr [rsp+80h+var_58], eax; char *
0x1801170fa  lea     rax, aPackagefamilyG; "packageFamily->get_PackageFamilyName(re"...
0x180117101  mov     [rsp+80h+var_60], rax; char *
0x180117106  lea     r9, aLocationstater_0; "LocationStateRepositoryHelper::GetPacka"...
0x18011710d  lea     r8, aOnecoreuapDriv_62; "onecoreuap\\drivers\\MobilePC\\Location"...
0x180117114  mov     edx, 42h ; 'B'; void *
0x180117119  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011711e  nop
0x18011711f  mov     rcx, [rbp+string]; string
0x180117123  call    cs:__imp_WindowsDeleteString
0x180117129  inc     esi
0x18011712b  jmp     loc_18011705C
0x180117130  xor     edx, edx; length
0x180117132  mov     rcx, [rbp+string]; string
0x180117136  call    cs:__imp_WindowsGetStringRawBuffer
0x18011713c  mov     rdx, rax
0x18011713f  mov     rcx, r14
0x180117142  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180117147  nop
0x180117148  mov     rcx, [rbp+string]; string
0x18011714c  call    cs:__imp_WindowsDeleteString
0x180117152  mov     [rbp+string], 0
0x18011715a  lea     rcx, [rbp+var_20]
0x18011715e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117163  nop
0x180117164  lea     rcx, [rbp+var_30]
0x180117168  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18011716d  xor     ebx, ebx
0x18011716f  jmp     short loc_180117189
0x180117171  lea     rcx, [rbp+var_20]
0x180117175  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18011717a  nop
0x18011717b  lea     rcx, [rbp+var_30]
0x18011717f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117184  mov     ebx, 80070490h
0x180117189  lea     rcx, [rbp+var_10]
0x18011718d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117192  mov     eax, ebx
0x180117194  mov     rcx, [rbp+var_8]
0x180117198  xor     rcx, rsp; StackCookie
0x18011719b  call    __security_check_cookie
0x1801171a0  lea     r11, [rsp+80h+var_s0]
0x1801171a8  mov     rbx, [r11+30h]
0x1801171ac  mov     rsi, [r11+38h]
0x1801171b0  mov     rsp, r11
0x1801171b3  pop     r14
0x1801171b5  pop     rdi
0x1801171b6  pop     rbp
0x1801171b7  retn
```

# StoreApplication::GetStoreAppInstallLocationFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800dac8c`
- end: `0x1800dae39`
- name: `?GetStoreAppInstallLocationFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `429`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d8280`
- `0x1800da410`
- `0x1800db734`
- `0x1800dc88c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001082c`
- `0x18001c5f0`
- `0x1800295dc`
- `0x1800c97f0`
- `0x1800d8684`
- `0x1800dac8c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dadaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dadaf`

## string_xrefs

- `0x1800dad4d`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dad97`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dacde`: `IPackage::get_InstalledLocation() failed`
- `0x1800daceb`: `StoreApplication::GetStoreAppInstallLocationFromPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StoreApplication::GetStoreAppInstallLocationFromPackage(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rdi
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v14 = a1;
  v13 = 0;
  v3 = *a2;
  v4 = *(int (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)*a2 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( v4(v3, &v13) >= 0 )
  {
    v14 = 0;
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
    v6 = **v13;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v7 = v6(v5, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v14);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x308,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v7,
        (int)v13);
    string[0] = 0;
    v8 = v14;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 96LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      string,
      0);
    v10 = v9(v8, string);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v10,
        (int)v13);
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    std::wstring::wstring(&v16, StringRawBuffer);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = v16;
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v16) = 0;
    std::wstring::_Tidy_deallocate(&v16);
    Windows::Internal::String::~String(string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "StoreApplication::GetStoreAppInstallLocationFromPackage",
      771,
      "IPackage::get_InstalledLocation() failed");
    std::wstring::wstring(a1, &pszFormat);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return a1;
}

```

## disassembly

```asm
0x1800dac8c  mov     [rsp-18h+arg_10], rbx
0x1800dac91  push    rbp
0x1800dac92  push    rsi
0x1800dac93  push    rdi
0x1800dac94  mov     rbp, rsp
0x1800dac97  sub     rsp, 70h
0x1800dac9b  mov     rax, cs:__security_cookie
0x1800daca2  xor     rax, rsp
0x1800daca5  mov     [rbp+var_10], rax
0x1800daca9  mov     rsi, rcx
0x1800dacac  mov     [rbp+var_48], rcx
0x1800dacb0  mov     [rbp+var_50], 0
0x1800dacb8  mov     rdi, [rdx]
0x1800dacbb  mov     rax, [rdi]
0x1800dacbe  mov     rbx, [rax+38h]
0x1800dacc2  lea     rcx, [rbp+var_50]
0x1800dacc6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daccb  lea     rdx, [rbp+var_50]
0x1800daccf  mov     rcx, rdi
0x1800dacd2  mov     rax, rbx
0x1800dacd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dacda  test    eax, eax
0x1800dacdc  jns     short loc_1800DAD10
0x1800dacde  lea     r9, aIpackageGetIns; "IPackage::get_InstalledLocation() faile"...
0x1800dace5  mov     r8d, 303h
0x1800daceb  lea     rdx, aStoreapplicati_5; "StoreApplication::GetStoreAppInstallLoc"...
0x1800dacf2  mov     ecx, 3
0x1800dacf7  call    AslLogCallPrintf
0x1800dacfc  lea     rdx, pszFormat
0x1800dad03  mov     rcx, rsi
0x1800dad06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dad0b  jmp     loc_1800DAE11
0x1800dad10  mov     [rbp+var_48], 0
0x1800dad18  mov     rbx, [rbp+var_50]
0x1800dad1c  mov     rax, [rbx]
0x1800dad1f  mov     rdi, [rax]
0x1800dad22  lea     rcx, [rbp+var_48]
0x1800dad26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dad2b  lea     r8, [rbp+var_48]
0x1800dad2f  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800dad36  mov     rcx, rbx
0x1800dad39  mov     rax, rdi
0x1800dad3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dad41  nop
0x1800dad42  mov     rcx, [rbp+18h]; this
0x1800dad46  test    eax, eax
0x1800dad48  jns     short loc_1800DAD5F
0x1800dad4a  mov     r9d, eax; char *
0x1800dad4d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dad54  mov     edx, 308h; void *
0x1800dad59  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dad5f  mov     [rbp+string], 0
0x1800dad67  mov     rdi, [rbp+var_48]
0x1800dad6b  mov     rax, [rdi]
0x1800dad6e  mov     rbx, [rax+60h]
0x1800dad72  xor     edx, edx
0x1800dad74  lea     rcx, [rbp+string]
0x1800dad78  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dad7d  lea     rdx, [rbp+string]
0x1800dad81  mov     rcx, rdi
0x1800dad84  mov     rax, rbx
0x1800dad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dad8c  mov     rcx, [rbp+18h]; this
0x1800dad90  test    eax, eax
0x1800dad92  jns     short loc_1800DADA9
0x1800dad94  mov     r9d, eax; char *
0x1800dad97  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dad9e  mov     edx, 30Bh; void *
0x1800dada3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dada9  xor     edx, edx; length
0x1800dadab  mov     rcx, [rbp+string]; string
0x1800dadaf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dadb5  mov     rdx, rax
0x1800dadb8  lea     rcx, [rbp+var_30]
0x1800dadbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dadc1  mov     qword ptr [rsi+10h], 0
0x1800dadc9  mov     qword ptr [rsi+18h], 0
0x1800dadd1  movups  xmm0, [rbp+var_30]
0x1800dadd5  movups  xmmword ptr [rsi], xmm0
0x1800dadd8  movups  xmm1, [rbp+var_20]
0x1800daddc  movups  xmmword ptr [rsi+10h], xmm1
0x1800dade0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800dade8  movdqu  [rbp+var_20], xmm0
0x1800daded  xor     eax, eax
0x1800dadef  mov     word ptr [rbp+var_30], ax
0x1800dadf3  lea     rcx, [rbp+var_30]
0x1800dadf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dadfc  nop
0x1800dadfd  lea     rcx, [rbp+string]; this
0x1800dae01  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800dae06  nop
0x1800dae07  lea     rcx, [rbp+var_48]
0x1800dae0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dae10  nop
0x1800dae11  lea     rcx, [rbp+var_50]
0x1800dae15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dae1a  mov     rax, rsi
0x1800dae1d  mov     rcx, [rbp+var_10]
0x1800dae21  xor     rcx, rsp; StackCookie
0x1800dae24  call    __security_check_cookie
0x1800dae29  mov     rbx, [rsp+70h+arg_10]
0x1800dae31  add     rsp, 70h
0x1800dae35  pop     rdi
0x1800dae36  pop     rsi
0x1800dae37  pop     rbp
0x1800dae38  retn
```

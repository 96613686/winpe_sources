# Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800430e8`
- end: `0x18004321b`
- name: `?GetSrUserFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180042514`
- `0x180042720`
- `0x180044f4c`

## callees

- `0x1800094c0`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x180039e9c`
- `0x18003e4f0`
- `0x18003e6d8`
- `0x1800430e8`
- `0x180045f78`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800431f0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800431f0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180043125`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180043125`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(_QWORD *a1, __int64 a2)
{
  const unsigned __int16 *v4; // rdx
  const char *v5; // r9
  __int64 *v6; // rax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD *); // rbx
  const unsigned __int16 *v10; // rax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-40h]
  _QWORD v14[2]; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string[4]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v14[1] = a1;
  if ( !ImpersonateSelf(SecurityImpersonation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  BYTE1(v13) = 1;
  v14[0] = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[38])v4);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
         *v6,
         (__int64)v14);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v7,
      v13);
  *a1 = 0;
  v8 = v14[0];
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v14[0] + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v10);
  v11 = v9(v8, string[0], a1);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v11,
      v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v14);
  RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x1800430e8  mov     [rsp-18h+arg_10], rbx
0x1800430ed  mov     [rsp-18h+arg_18], rsi
0x1800430f2  push    rbp
0x1800430f3  push    rdi
0x1800430f4  push    r14
0x1800430f6  mov     rbp, rsp
0x1800430f9  sub     rsp, 60h
0x1800430fd  mov     rax, cs:__security_cookie
0x180043104  xor     rax, rsp
0x180043107  mov     [rbp+var_8], rax
0x18004310b  mov     r14, rdx
0x18004310e  mov     rsi, rcx
0x180043111  mov     [rbp+var_30], rcx
0x180043115  mov     [rbp+var_3C], 0
0x18004311c  mov     rbx, [rbp+18h]
0x180043120  mov     ecx, 2; ImpersonationLevel
0x180043125  call    cs:__imp_ImpersonateSelf
0x18004312b  test    eax, eax
0x18004312d  jnz     short loc_180043144
0x18004312f  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180043136  mov     edx, 2E5h; void *
0x18004313b  mov     rcx, rbx; this
0x18004313e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180043144  mov     [rbp+var_3F], 1
0x180043148  mov     [rbp+var_38], 0
0x180043150  lea     rcx, [rbp+string]; string
0x180043154  call    ??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[38])
0x180043159  lea     rdx, [rbp+var_38]
0x18004315d  mov     rcx, [rax]
0x180043160  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x180043165  mov     rcx, [rbp+18h]; this
0x180043169  test    eax, eax
0x18004316b  jns     short loc_180043182
0x18004316d  mov     r9d, eax; char *
0x180043170  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180043177  mov     edx, 2EEh; void *
0x18004317c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043182  mov     qword ptr [rsi], 0
0x180043189  mov     [rbp+var_3C], 1
0x180043190  mov     rdi, [rbp+var_38]
0x180043194  mov     rax, [rdi]
0x180043197  mov     rbx, [rax+50h]
0x18004319b  mov     rcx, rsi
0x18004319e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800431a3  mov     rcx, r14
0x1800431a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800431ab  mov     rdx, rax; unsigned __int16 *
0x1800431ae  lea     rcx, [rbp+string]; this
0x1800431b2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800431b7  mov     r8, rsi
0x1800431ba  mov     rdx, [rbp+string]
0x1800431be  mov     rcx, rdi
0x1800431c1  mov     rax, rbx
0x1800431c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431c9  mov     rcx, [rbp+18h]; this
0x1800431cd  test    eax, eax
0x1800431cf  jns     short loc_1800431E6
0x1800431d1  mov     r9d, eax; char *
0x1800431d4  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800431db  mov     edx, 2F3h; void *
0x1800431e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800431e6  lea     rcx, [rbp+var_38]
0x1800431ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800431ef  nop
0x1800431f0  call    cs:__imp_RevertToSelf
0x1800431f6  mov     rax, rsi
0x1800431f9  mov     rcx, [rbp+var_8]
0x1800431fd  xor     rcx, rsp; StackCookie
0x180043200  call    __security_check_cookie
0x180043205  lea     r11, [rsp+60h+var_s0]
0x18004320a  mov     rbx, [r11+30h]
0x18004320e  mov     rsi, [r11+38h]
0x180043212  mov     rsp, r11
0x180043215  pop     r14
0x180043217  pop     rdi
0x180043218  pop     rbp
0x180043219  retn
```

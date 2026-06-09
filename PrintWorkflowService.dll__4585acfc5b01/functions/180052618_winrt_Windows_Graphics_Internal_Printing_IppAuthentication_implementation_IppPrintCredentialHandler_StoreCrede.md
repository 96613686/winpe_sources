# winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::StoreCredentials(winrt::hstring const &,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials const &)

- ea: `0x180052618`
- end: `0x1800527d4`
- name: `?StoreCredentials@IppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEBUhstring@8@AEBUIppPrinterCredentials@345678@@Z`
- size: `444`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *this, const struct winrt::hstring *, const struct winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800523f4`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x180008698`
- `0x180012784`
- `0x180012820`
- `0x1800129dc`
- `0x1800129f8`
- `0x180012b10`
- `0x18002d8f0`
- `0x180036688`
- `0x180052618`
- `0x18005e010`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180052771`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180052771`

## string_xrefs

- `0x18005278a`: `onecoreuap\printscan\print\workflow\broker\ipp_auth_lib\ippprintcredentialhandler.cpp`
- `0x18005277b`: `CredWrite failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::StoreCredentials(
        winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *this,
        const struct winrt::hstring *a2,
        const struct winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrinterCredentials *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // r14
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // eax
  const char *v15; // [rsp+28h] [rbp-91h]
  __int64 v16; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-79h] BYREF
  _CREDENTIALW Credential; // [rsp+50h] [rbp-69h] BYREF
  int v20; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-11h]
  _BYTE v22[32]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v16 = 0;
  v6 = *(_QWORD *)a3;
  v20 = 0;
  v21 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 48LL))(v6, &v16);
  winrt::check_hresult(v17, v7, &v20);
  v18[0] = v16;
  v16 = 0;
  v8 = *(_QWORD *)a3;
  v20 = 0;
  v21 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, &v16);
  winrt::check_hresult(v17, v9, &v20);
  v10 = v16;
  v11 = winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *)((char *)this + 24));
  v12 = std::wstring::wstring(&v20, L"Storing IPP authentication credential for printer:");
  std::operator+<unsigned short>(v22, v12, v11);
  std::wstring::_Tidy_deallocate(&v20);
  memset_0(&Credential, 0, sizeof(Credential));
  Credential.TargetName = (LPWSTR)winrt::hstring::c_str(a2);
  Credential.UserName = (LPWSTR)winrt::hstring::c_str((winrt::hstring *)v18);
  Credential.CredentialBlob = (LPBYTE)winrt::hstring::c_str((winrt::hstring *)&v16);
  if ( v10 )
    v13 = *(_DWORD *)(v10 + 4);
  else
    v13 = 0;
  Credential.CredentialBlobSize = 2 * v13 + 2;
  Credential.Comment = (LPWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  Credential.Persist = 2;
  Credential.Type = 1;
  v14 = CredWriteW(&Credential, 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0xE6,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\ipp_auth_lib\\ippprintcredentialhandler.cpp",
    (const char *)v14,
    (__int64)"CredWrite failed!",
    v15);
  std::wstring::_Tidy_deallocate(v22);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v16);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v18);
}

```

## disassembly

```asm
0x180052618  push    rbp
0x18005261a  push    rbx
0x18005261b  push    rsi
0x18005261c  push    rdi
0x18005261d  push    r14
0x18005261f  lea     rbp, [rsp-37h]
0x180052624  sub     rsp, 0F0h
0x18005262b  mov     rax, cs:__security_cookie
0x180052632  xor     rax, rsp
0x180052635  mov     [rbp+57h+var_30], rax
0x180052639  mov     rbx, r8
0x18005263c  mov     rsi, rdx
0x18005263f  mov     rdi, rcx
0x180052642  mov     [rsp+110h+var_E0], 0
0x18005264b  mov     rcx, [r8]
0x18005264e  mov     [rbp+57h+var_70], 0
0x180052655  xorps   xmm0, xmm0
0x180052658  movdqu  [rbp+57h+var_68], xmm0
0x18005265d  mov     rax, [rcx]
0x180052660  lea     rdx, [rsp+110h+var_E0]
0x180052665  mov     rax, [rax+30h]
0x180052669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005266e  lea     r8, [rbp+57h+var_70]
0x180052672  mov     edx, eax
0x180052674  lea     rcx, [rsp+110h+var_D8]
0x180052679  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005267e  mov     rax, [rsp+110h+var_E0]
0x180052683  mov     [rbp+57h+var_D0], rax
0x180052687  mov     [rsp+110h+var_E0], 0
0x180052690  mov     rcx, [rbx]
0x180052693  mov     [rbp+57h+var_70], 0
0x18005269a  xorps   xmm0, xmm0
0x18005269d  movdqu  [rbp+57h+var_68], xmm0
0x1800526a2  mov     rax, [rcx]
0x1800526a5  lea     rdx, [rsp+110h+var_E0]
0x1800526aa  mov     rax, [rax+38h]
0x1800526ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526b3  lea     r8, [rbp+57h+var_70]
0x1800526b7  mov     edx, eax
0x1800526b9  lea     rcx, [rsp+110h+var_D8]
0x1800526be  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800526c3  mov     r14, [rsp+110h+var_E0]
0x1800526c8  mov     [rsp+110h+var_E0], r14
0x1800526cd  lea     rcx, [rdi+18h]; this
0x1800526d1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800526d6  mov     rbx, rax
0x1800526d9  lea     rdx, aStoringIppAuth; "Storing IPP authentication credential f"...
0x1800526e0  lea     rcx, [rbp+57h+var_70]
0x1800526e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800526e9  nop
0x1800526ea  mov     r8, rbx
0x1800526ed  mov     rdx, rax
0x1800526f0  lea     rcx, [rbp+57h+var_50]
0x1800526f4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800526f9  nop
0x1800526fa  lea     rcx, [rbp+57h+var_70]
0x1800526fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052703  xor     edx, edx; Val
0x180052705  lea     r8d, [rdx+50h]; Size
0x180052709  lea     rcx, [rbp+57h+Credential]; void *
0x18005270d  call    memset_0
0x180052712  mov     rcx, rsi; this
0x180052715  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18005271a  mov     [rbp+57h+Credential.TargetName], rax
0x18005271e  lea     rcx, [rbp+57h+var_D0]; this
0x180052722  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180052727  mov     [rbp+57h+Credential.UserName], rax
0x18005272b  lea     rcx, [rsp+110h+var_E0]; this
0x180052730  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180052735  mov     [rbp+57h+Credential.CredentialBlob], rax
0x180052739  test    r14, r14
0x18005273c  jz      short loc_180052744
0x18005273e  mov     eax, [r14+4]
0x180052742  jmp     short loc_180052746
0x180052744  xor     eax, eax
0x180052746  lea     eax, ds:2[rax*2]
0x18005274d  mov     [rbp+57h+Credential.CredentialBlobSize], eax
0x180052750  lea     rcx, [rbp+57h+var_50]
0x180052754  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052759  mov     [rbp+57h+Credential.Comment], rax
0x18005275d  mov     [rbp+57h+Credential.Persist], 2
0x180052764  mov     [rbp+57h+Credential.Type], 1
0x18005276b  xor     edx, edx; Flags
0x18005276d  lea     rcx, [rbp+57h+Credential]; Credential
0x180052771  call    cs:__imp_CredWriteW
0x180052777  mov     rcx, [rbp+5Fh]; this
0x18005277b  lea     rdx, aCredwriteFaile; "CredWrite failed!"
0x180052782  mov     [rsp+110h+var_F0], rdx; __int64
0x180052787  mov     r9d, eax; char *
0x18005278a  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\workflow"...
0x180052791  mov     edx, 0E6h; void *
0x180052796  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18005279b  nop
0x18005279c  lea     rcx, [rbp+57h+var_50]
0x1800527a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800527a5  nop
0x1800527a6  lea     rcx, [rsp+110h+var_E0]
0x1800527ab  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800527b0  nop
0x1800527b1  lea     rcx, [rbp+57h+var_D0]
0x1800527b5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800527ba  mov     rcx, [rbp+57h+var_30]
0x1800527be  xor     rcx, rsp; StackCookie
0x1800527c1  call    __security_check_cookie
0x1800527c6  add     rsp, 0F0h
0x1800527cd  pop     r14
0x1800527cf  pop     rdi
0x1800527d0  pop     rsi
0x1800527d1  pop     rbx
0x1800527d2  pop     rbp
0x1800527d3  retn
```

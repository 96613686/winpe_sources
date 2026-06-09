# winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::TryGetStoredCredentials(winrt::hstring const &)

- ea: `0x18005281c`
- end: `0x1800528e9`
- name: `?TryGetStoredCredentials@IppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUIppPrinterCredentials@345678@AEBUhstring@8@@Z`
- size: `205`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, winrt::hstring *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051560`

## callees

- `0x180009718`
- `0x1800129dc`
- `0x180012b10`
- `0x180050584`
- `0x180050c6c`
- `0x1800527dc`
- `0x18005281c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052853`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x180052849`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x180052849`

## string_xrefs

- `0x180052876`: `onecoreuap\printscan\print\workflow\broker\ipp_auth_lib\ippprintcredentialhandler.cpp`
- `0x180052866`: `CredRead failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::TryGetStoredCredentials(
        __int64 a1,
        _QWORD *a2,
        winrt::hstring *a3)
{
  const WCHAR *v4; // rax
  DWORD LastError; // eax
  __int64 v6; // rax
  const char *v8; // [rsp+28h] [rbp-30h]
  LPBYTE CredentialBlob; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v10[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  PCREDENTIALW Credential; // [rsp+78h] [rbp+20h] BYREF

  v12 = a1;
  Credential = 0;
  v4 = winrt::hstring::c_str(a3);
  if ( CredReadW(v4, 1u, 0, &Credential) )
  {
    LODWORD(v12) = 0;
    CredentialBlob = Credential->CredentialBlob;
    v6 = winrt::hstring::hstring((winrt::hstring *)v10, Credential->UserName);
    winrt::make<winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrinterCredentials,winrt::hstring,unsigned short *,long>(
      a2,
      v6,
      &CredentialBlob,
      &v12);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
  }
  else
  {
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\ipp_auth_lib\\ippprintcredentialhandler.cpp",
      (const char *)(LastError != 1168),
      "CredRead failed!",
      v8);
    *a2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_CREDENTIALW *,void (*)(void *),&void CredFree(void *),wistd::integral_constant<unsigned __int64,0>,_CREDENTIALW *,_CREDENTIALW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CREDENTIALW *,void (*)(void *),&void CredFree(void *),wistd::integral_constant<unsigned __int64,0>,_CREDENTIALW *,_CREDENTIALW *,0,std::nullptr_t>>(&Credential);
  return a2;
}

```

## disassembly

```asm
0x18005281c  mov     [rsp+arg_0], rcx
0x180052821  push    rbx
0x180052822  sub     rsp, 50h
0x180052826  mov     rbx, rdx
0x180052829  mov     [rsp+58h+Credential], 0
0x180052832  mov     rcx, r8; this
0x180052835  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18005283a  lea     r9, [rsp+58h+Credential]; Credential
0x18005283f  xor     r8d, r8d; Flags
0x180052842  lea     edx, [r8+1]; Type
0x180052846  mov     rcx, rax; TargetName
0x180052849  call    cs:__imp_CredReadW
0x18005284f  test    eax, eax
0x180052851  jnz     short loc_180052890
0x180052853  call    cs:__imp_GetLastError
0x180052859  cmp     eax, 490h
0x18005285e  setnz   al
0x180052861  mov     rcx, [rsp+58h]; this
0x180052866  lea     rdx, aCredreadFailed; "CredRead failed!"
0x18005286d  mov     [rsp+58h+var_38], rdx; void *
0x180052872  movzx   r9d, al; char *
0x180052876  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\workflow"...
0x18005287d  mov     edx, 8Fh; void *
0x180052882  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180052887  mov     qword ptr [rbx], 0
0x18005288e  jmp     short loc_1800528D6
0x180052890  mov     dword ptr [rsp+58h+arg_0], 0
0x180052898  mov     rdx, [rsp+58h+Credential]
0x18005289d  mov     rax, [rdx+28h]
0x1800528a1  mov     [rsp+58h+var_20], rax
0x1800528a6  mov     rdx, [rdx+48h]; unsigned __int16 *
0x1800528aa  lea     rcx, [rsp+58h+var_18]; this
0x1800528af  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800528b4  nop
0x1800528b5  lea     r9, [rsp+58h+arg_0]
0x1800528ba  lea     r8, [rsp+58h+var_20]
0x1800528bf  mov     rdx, rax
0x1800528c2  mov     rcx, rbx
0x1800528c5  call    ??$make@UIppPrinterCredentials@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@Uhstring@8@PEAGJ@winrt@@YA?A_P$$QEAUhstring@0@$$QEAPEAG$$QEAJ@Z
0x1800528ca  nop
0x1800528cb  lea     rcx, [rsp+58h+var_18]
0x1800528d0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800528d5  nop
0x1800528d6  lea     rcx, [rsp+58h+Credential]
0x1800528db  call    ??1?$unique_storage@U?$resource_policy@PEAU_CREDENTIALW@@P6AXPEAX@Z$1?CredFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CREDENTIALW *,void (*)(void *),&CredFree(void *),wistd::integral_constant<unsigned __int64,0>,_CREDENTIALW *,_CREDENTIALW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CREDENTIALW *,void (*)(void *),&CredFree(void *),wistd::integral_constant<unsigned __int64,0>,_CREDENTIALW *,_CREDENTIALW *,0,std::nullptr_t>>(void)
0x1800528e0  mov     rax, rbx
0x1800528e3  add     rsp, 50h
0x1800528e7  pop     rbx
0x1800528e8  retn
```

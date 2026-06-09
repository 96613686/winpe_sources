# winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::RemovePrinterCredentials(winrt::hstring const &)

- ea: `0x18005225c`
- end: `0x1800522c0`
- name: `?RemovePrinterCredentials@IppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@QEAAXAEBUhstring@8@@Z`
- size: `100`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *this, const struct winrt::hstring *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180051560`
- `0x180052230`

## callees

- `0x1800129dc`
- `0x18005225c`
- `0x1800527dc`
- `0x1800529b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052286`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005227c`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005227c`

## string_xrefs

- `0x1800522a2`: `onecoreuap\printscan\print\workflow\broker\ipp_auth_lib\ippprintcredentialhandler.cpp`
- `0x180052291`: `CredDelete failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::RemovePrinterCredentials(
        winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *this,
        const struct winrt::hstring *a2)
{
  const WCHAR *v3; // rax
  DWORD LastError; // eax
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::ValidateCredStoreId(
    this,
    a2);
  v3 = winrt::hstring::c_str(a2);
  if ( !CredDeleteW(v3, 1u, 0) )
  {
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\ipp_auth_lib\\ippprintcredentialhandler.cpp",
      (const char *)(LastError != 1168),
      "CredDelete failed!",
      v5);
  }
}

```

## disassembly

```asm
0x18005225c  push    rbx
0x18005225e  sub     rsp, 30h
0x180052262  mov     rbx, rdx
0x180052265  call    ?ValidateCredStoreId@IppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEBUhstring@8@@Z; winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::ValidateCredStoreId(winrt::hstring const &)
0x18005226a  mov     rcx, rbx; this
0x18005226d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180052272  xor     r8d, r8d; Flags
0x180052275  mov     rcx, rax; TargetName
0x180052278  lea     edx, [r8+1]; Type
0x18005227c  call    cs:__imp_CredDeleteW
0x180052282  test    eax, eax
0x180052284  jnz     short loc_1800522BA
0x180052286  call    cs:__imp_GetLastError
0x18005228c  mov     rcx, [rsp+38h]; this
0x180052291  lea     rdx, aCreddeleteFail; "CredDelete failed!"
0x180052298  cmp     eax, 490h
0x18005229d  mov     [rsp+38h+var_18], rdx; void *
0x1800522a2  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\workflow"...
0x1800522a9  mov     edx, 86h; void *
0x1800522ae  setnz   al
0x1800522b1  movzx   r9d, al; char *
0x1800522b5  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800522ba  add     rsp, 30h
0x1800522be  pop     rbx
0x1800522bf  retn
```

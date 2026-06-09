# Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::OnShow(bool *,Windows::Foundation::Size *,HSTRING__ * *)

- ea: `0x180049c10`
- end: `0x180049d77`
- name: `?OnShow@ImportAccountsOperation@Sync@ApplicationModel@Internal@Windows@@UEAAJPEA_NPEAUSize@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `359`
- prototype: `int(Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation *__hidden this, bool *, struct Windows::Foundation::Size *, HSTRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006eac`
- `0x180008d78`
- `0x18000e87c`
- `0x180011ffc`
- `0x180049c10`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180049d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180049d21`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation::OnShow(
        Windows::Internal::ApplicationModel::Sync::ImportAccountsOperation *this,
        bool *a2,
        struct Windows::Foundation::Size *a3,
        HSTRING *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, HSTRING *); // rbx
  HRESULT v10; // eax
  __int64 v11; // rdx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  *a4 = 0;
  *a2 = 1;
  v14 = 0;
  v16 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.ApplicationModel.Sync.AccountsResourceHelper",
    0x3Eu,
    0x3Du);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(
         v16,
         &v14);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = v14;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ImportAccountsWindowTitle",
      0x1Au,
      0x19u);
    v10 = v9(v8, v16, &string);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v10 = WindowsDuplicateString(string, a4);
      v7 = v10;
      if ( v10 >= 0 )
      {
        *(_DWORD *)a3 = 1139015680;
        *((_DWORD *)a3 + 1) = 1142292480;
        WindowsDeleteString(string);
        v7 = 0;
        goto LABEL_9;
      }
      v11 = 109;
    }
    else
    {
      v11 = 107;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
    WindowsDeleteString(string);
LABEL_9:
    string = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\importaccountsoperation.cpp",
    (const char *)(unsigned int)v6,
    (int)string);
LABEL_10:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return v7;
}

```

## disassembly

```asm
0x180049c10  push    rbp
0x180049c12  push    rbx
0x180049c13  push    rsi
0x180049c14  push    rdi
0x180049c15  push    r14
0x180049c17  mov     rbp, rsp
0x180049c1a  sub     rsp, 60h
0x180049c1e  mov     rax, cs:__security_cookie
0x180049c25  xor     rax, rsp
0x180049c28  mov     [rbp+var_10], rax
0x180049c2c  mov     r14, r9
0x180049c2f  mov     rsi, r8
0x180049c32  mov     qword ptr [r9], 0
0x180049c39  mov     byte ptr [rdx], 1
0x180049c3c  mov     [rbp+var_38], 0
0x180049c44  mov     [rbp+var_18], 0
0x180049c4c  mov     r9d, 3Dh ; '='; unsigned int
0x180049c52  lea     r8d, [r9+1]; unsigned int
0x180049c56  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_Sync_AccountsResourceHelper@@3QBGB; "Windows.Internal.ApplicationModel.Sync."...
0x180049c5d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180049c61  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049c66  lea     rdx, [rbp+var_38]
0x180049c6a  mov     rcx, [rbp+var_18]
0x180049c6e  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>)
0x180049c73  mov     ebx, eax
0x180049c75  test    eax, eax
0x180049c77  jns     short loc_180049C96
0x180049c79  mov     rcx, [rbp+28h]; this
0x180049c7d  mov     r9d, eax; char *
0x180049c80  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x180049c87  mov     edx, 69h ; 'i'; void *
0x180049c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c91  jmp     loc_180049D55
0x180049c96  mov     [rbp+string], 0
0x180049c9e  mov     rdi, [rbp+var_38]
0x180049ca2  mov     rax, [rdi]
0x180049ca5  mov     rbx, [rax+50h]
0x180049ca9  xor     ecx, ecx; string
0x180049cab  call    cs:__imp_WindowsDeleteString
0x180049cb1  mov     [rbp+string], 0
0x180049cb9  mov     [rbp+var_18], 0
0x180049cc1  mov     r9d, 19h; unsigned int
0x180049cc7  lea     r8d, [r9+1]; unsigned int
0x180049ccb  lea     rdx, aImportaccounts; "ImportAccountsWindowTitle"
0x180049cd2  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180049cd6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049cdb  nop
0x180049cdc  lea     r8, [rbp+string]
0x180049ce0  mov     rdx, [rbp+var_18]
0x180049ce4  mov     rcx, rdi
0x180049ce7  mov     rax, rbx
0x180049cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cef  mov     ebx, eax
0x180049cf1  test    eax, eax
0x180049cf3  jns     short loc_180049D1A
0x180049cf5  mov     edx, 6Bh ; 'k'; void *
0x180049cfa  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\accountscontrol\\api"...
0x180049d01  mov     r9d, eax; char *
0x180049d04  mov     rcx, [rbp+28h]; this
0x180049d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d0d  nop
0x180049d0e  mov     rcx, [rbp+string]; string
0x180049d12  call    cs:__imp_WindowsDeleteString
0x180049d18  jmp     short loc_180049D4D
0x180049d1a  mov     rdx, r14; newString
0x180049d1d  mov     rcx, [rbp+string]; string
0x180049d21  call    cs:__imp_WindowsDuplicateString
0x180049d27  mov     ebx, eax
0x180049d29  test    eax, eax
0x180049d2b  jns     short loc_180049D34
0x180049d2d  mov     edx, 6Dh ; 'm'
0x180049d32  jmp     short loc_180049CFA
0x180049d34  mov     dword ptr [rsi], 43E40000h
0x180049d3a  mov     dword ptr [rsi+4], 44160000h
0x180049d41  mov     rcx, [rbp+string]; string
0x180049d45  call    cs:__imp_WindowsDeleteString
0x180049d4b  xor     ebx, ebx
0x180049d4d  mov     [rbp+string], 0
0x180049d55  lea     rcx, [rbp+var_38]
0x180049d59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049d5e  mov     eax, ebx
0x180049d60  mov     rcx, [rbp+var_10]
0x180049d64  xor     rcx, rsp; StackCookie
0x180049d67  call    __security_check_cookie
0x180049d6c  add     rsp, 60h
0x180049d70  pop     r14
0x180049d72  pop     rdi
0x180049d73  pop     rsi
0x180049d74  pop     rbx
0x180049d75  pop     rbp
0x180049d76  retn
```

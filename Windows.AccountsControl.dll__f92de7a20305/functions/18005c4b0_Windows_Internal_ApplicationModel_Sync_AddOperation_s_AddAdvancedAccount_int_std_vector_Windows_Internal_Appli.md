# Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddAdvancedAccount(int,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData,std::allocator<Windows::Internal::ApplicationModel::Sync::ProviderData>> *)

- ea: `0x18005c4b0`
- end: `0x18005c5f2`
- name: `?s_AddAdvancedAccount@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJHPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005aca0`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x18005c4b0`
- `0x18005cc0c`
- `0x18005d3c4`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c4e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c4e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c5c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddAdvancedAccount(int a1, char a2)
{
  int AccountString; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HSTRING v7; // rdi
  int v9; // [rsp+20h] [rbp-29h]
  HSTRING string; // [rsp+40h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-1h] BYREF
  HSTRING v12; // [rsp+60h] [rbp+17h]
  HSTRING_HEADER v13; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING v14; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  WindowsDeleteString(0);
  string = 0;
  v12 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AdvancedAddAccountName", 0x17u, 0x16u);
  AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v12, &string);
  v5 = AccountString;
  if ( AccountString >= 0 )
  {
    v12 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Microsoft,Advanced", 0x13u, 0x12u);
    v7 = string;
    v14 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v13,
      L"Windows.Internal.ApplicationModel.Sync.Provider.AdvancedAddAccount",
      0x43u,
      0x42u);
    AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddProviderToPriorityList(
                      v14,
                      v7,
                      a1,
                      1000,
                      a2);
    v5 = AccountString;
    if ( AccountString >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 746;
  }
  else
  {
    v6 = 737;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)AccountString,
    v9);
LABEL_7:
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18005c4b0  mov     [rsp-8+arg_10], rbx
0x18005c4b5  mov     [rsp-8+arg_18], rsi
0x18005c4ba  push    rbp
0x18005c4bb  push    rdi
0x18005c4bc  push    r14
0x18005c4be  lea     rbp, [rsp-47h]
0x18005c4c3  sub     rsp, 90h
0x18005c4ca  mov     rax, cs:__security_cookie
0x18005c4d1  xor     rax, rsp
0x18005c4d4  mov     [rbp+57h+var_18], rax
0x18005c4d8  mov     r14, rdx
0x18005c4db  mov     esi, ecx
0x18005c4dd  mov     [rbp+57h+string], 0
0x18005c4e5  xor     ecx, ecx; string
0x18005c4e7  call    cs:__imp_WindowsDeleteString
0x18005c4ed  mov     [rbp+57h+string], 0
0x18005c4f5  mov     [rbp+57h+var_40], 0
0x18005c4fd  mov     r9d, 16h; unsigned int
0x18005c503  lea     r8d, [r9+1]; unsigned int
0x18005c507  lea     rdx, aAdvancedaddacc; "AdvancedAddAccountName"
0x18005c50e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c512  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c517  nop
0x18005c518  lea     rdx, [rbp+57h+string]; HSTRING *
0x18005c51c  mov     rcx, [rbp+57h+var_40]; HSTRING
0x18005c520  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005c525  mov     ebx, eax
0x18005c527  test    eax, eax
0x18005c529  jns     short loc_18005C532
0x18005c52b  mov     edx, 2E1h
0x18005c530  jmp     short loc_18005C5AB
0x18005c532  mov     [rbp+57h+var_40], 0
0x18005c53a  mov     r9d, 12h; unsigned int
0x18005c540  lea     r8d, [r9+1]; unsigned int
0x18005c544  lea     rdx, aMicrosoftAdvan; "Microsoft,Advanced"
0x18005c54b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005c54f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c554  nop
0x18005c555  mov     rbx, [rbp+57h+var_40]
0x18005c559  mov     rdi, [rbp+57h+string]
0x18005c55d  mov     [rbp+57h+var_20], 0
0x18005c565  mov     r9d, 42h ; 'B'; unsigned int
0x18005c56b  lea     r8d, [r9+1]; unsigned int
0x18005c56f  lea     rdx, aWindowsInterna_9; "Windows.Internal.ApplicationModel.Sync."...
0x18005c576  lea     rcx, [rbp+57h+var_38]; hstringHeader
0x18005c57a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005c57f  nop
0x18005c580  mov     qword ptr [rsp+0A0h+var_70], r14; char
0x18005c585  mov     [rsp+0A0h+var_78], 3E8h; int
0x18005c58d  mov     [rsp+0A0h+var_80], esi; int
0x18005c591  mov     r9, rbx
0x18005c594  mov     rdx, rdi; HSTRING
0x18005c597  mov     rcx, [rbp+57h+var_20]; HSTRING
0x18005c59b  call    ?s_AddProviderToPriorityList@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@000HIPEAV?$vector@UProviderData@Sync@ApplicationModel@Internal@Windows@@V?$allocator@UProviderData@Sync@ApplicationModel@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_AddProviderToPriorityList(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,int,uint,std::vector<Windows::Internal::ApplicationModel::Sync::ProviderData> *)
0x18005c5a0  mov     ebx, eax
0x18005c5a2  test    eax, eax
0x18005c5a4  jns     short loc_18005C5C0
0x18005c5a6  mov     edx, 2EAh; void *
0x18005c5ab  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005c5b2  mov     r9d, eax; char *
0x18005c5b5  mov     rcx, [rbp+5Fh]; this
0x18005c5b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5be  jmp     short loc_18005C5C2
0x18005c5c0  xor     ebx, ebx
0x18005c5c2  mov     rcx, [rbp+57h+string]; string
0x18005c5c6  call    cs:__imp_WindowsDeleteString
0x18005c5cc  mov     eax, ebx
0x18005c5ce  mov     rcx, [rbp+57h+var_18]
0x18005c5d2  xor     rcx, rsp; StackCookie
0x18005c5d5  call    __security_check_cookie
0x18005c5da  lea     r11, [rsp+0A0h+var_10]
0x18005c5e2  mov     rbx, [r11+30h]
0x18005c5e6  mov     rsi, [r11+38h]
0x18005c5ea  mov     rsp, r11
0x18005c5ed  pop     r14
0x18005c5ef  pop     rdi
0x18005c5f0  pop     rbp
0x18005c5f1  retn
```

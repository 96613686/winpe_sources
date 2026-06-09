# Windows::Internal::ApplicationModel::Sync::AddOperation::OnAddDisallowedShow(bool *,Windows::Foundation::Size *,HSTRING__ * *)

- ea: `0x18005a48c`
- end: `0x18005a56e`
- name: `?OnAddDisallowedShow@AddOperation@Sync@ApplicationModel@Internal@Windows@@AEAAJPEA_NPEAUSize@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `226`
- prototype: `int(Windows::Internal::ApplicationModel::Sync::AddOperation *__hidden this, bool *, struct Windows::Foundation::Size *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005ac40`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x18005a48c`
- `0x18005d3c4`
- `0x180069730`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a4be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a4be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005a516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005a516`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::OnAddDisallowedShow(
        Windows::Internal::ApplicationModel::Sync::AddOperation *this,
        bool *a2,
        struct Windows::Foundation::Size *a3,
        HSTRING *a4)
{
  HRESULT AccountString; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-40h] BYREF
  HSTRING v12; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a4 = 0;
  *a2 = 1;
  WindowsDeleteString(0);
  string = 0;
  v12 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AddAccountWindowTitle", 0x16u, 0x15u);
  AccountString = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(v12, &string);
  v7 = AccountString;
  if ( AccountString >= 0 )
  {
    AccountString = WindowsDuplicateString(string, a4);
    v7 = AccountString;
    if ( AccountString >= 0 )
    {
      *(_DWORD *)a3 = 1139015680;
      *((_DWORD *)a3 + 1) = 1142292480;
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 231;
  }
  else
  {
    v8 = 230;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)AccountString,
    (int)string);
LABEL_7:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18005a48c  push    rbx
0x18005a48e  push    rsi
0x18005a48f  push    rdi
0x18005a490  sub     rsp, 50h
0x18005a494  mov     rax, cs:__security_cookie
0x18005a49b  xor     rax, rsp
0x18005a49e  mov     [rsp+68h+var_20], rax
0x18005a4a3  mov     rsi, r9
0x18005a4a6  mov     rdi, r8
0x18005a4a9  mov     qword ptr [r9], 0
0x18005a4b0  mov     byte ptr [rdx], 1
0x18005a4b3  mov     [rsp+68h+string], 0
0x18005a4bc  xor     ecx, ecx; string
0x18005a4be  call    cs:__imp_WindowsDeleteString
0x18005a4c4  mov     [rsp+68h+string], 0; int
0x18005a4cd  mov     [rsp+68h+var_28], 0
0x18005a4d6  mov     r9d, 15h; unsigned int
0x18005a4dc  lea     r8d, [r9+1]; unsigned int
0x18005a4e0  lea     rdx, aAddaccountwind; "AddAccountWindowTitle"
0x18005a4e7  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x18005a4ec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005a4f1  nop
0x18005a4f2  lea     rdx, [rsp+68h+string]; HSTRING *
0x18005a4f7  mov     rcx, [rsp+68h+var_28]; HSTRING
0x18005a4fc  call    ?s_GetAccountString@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAccountString(HSTRING__ *,HSTRING__ * *)
0x18005a501  mov     ebx, eax
0x18005a503  test    eax, eax
0x18005a505  jns     short loc_18005A50E
0x18005a507  mov     edx, 0E6h
0x18005a50c  jmp     short loc_18005A527
0x18005a50e  mov     rdx, rsi; newString
0x18005a511  mov     rcx, [rsp+68h+string]; string
0x18005a516  call    cs:__imp_WindowsDuplicateString
0x18005a51c  mov     ebx, eax
0x18005a51e  test    eax, eax
0x18005a520  jns     short loc_18005A53D
0x18005a522  mov     edx, 0E7h; void *
0x18005a527  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005a52e  mov     r9d, eax; char *
0x18005a531  mov     rcx, [rsp+68h]; this
0x18005a536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a53b  jmp     short loc_18005A54C
0x18005a53d  mov     dword ptr [rdi], 43E40000h
0x18005a543  mov     dword ptr [rdi+4], 44160000h
0x18005a54a  xor     ebx, ebx
0x18005a54c  mov     rcx, [rsp+68h+string]; string
0x18005a551  call    cs:__imp_WindowsDeleteString
0x18005a557  mov     eax, ebx
0x18005a559  mov     rcx, [rsp+68h+var_20]
0x18005a55e  xor     rcx, rsp; StackCookie
0x18005a561  call    __security_check_cookie
0x18005a566  add     rsp, 50h
0x18005a56a  pop     rdi
0x18005a56b  pop     rsi
0x18005a56c  pop     rbx
0x18005a56d  retn
```

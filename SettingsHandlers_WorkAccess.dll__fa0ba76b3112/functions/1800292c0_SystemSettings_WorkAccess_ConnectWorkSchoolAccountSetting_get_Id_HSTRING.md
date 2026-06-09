# SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::get_Id(HSTRING__ * *)

- ea: `0x1800292c0`
- end: `0x180029350`
- name: `?get_Id@ConnectWorkSchoolAccountSetting@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `144`
- prototype: `int(SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x1800292c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002930b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002930b`

## string_xrefs

- `0x1800292ee`: `SystemSettings_WorkAccess_AddWorkOrSchoolAccount`
- `0x180029322`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::get_Id(
        SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *this,
        HSTRING *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a2 = 0;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"SystemSettings_WorkAccess_AddWorkOrSchoolAccount",
    0x31u,
    0x30u);
  v3 = WindowsDuplicateString(string, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC9,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
    (const char *)(unsigned int)v3,
    (int)hstringHeader.Reserved.Reserved1);
  return v4;
}

```

## disassembly

```asm
0x1800292c0  push    rbx
0x1800292c2  sub     rsp, 50h
0x1800292c6  mov     rax, cs:__security_cookie
0x1800292cd  xor     rax, rsp
0x1800292d0  mov     [rsp+58h+var_18], rax
0x1800292d5  mov     r9d, 30h ; '0'; unsigned int
0x1800292db  mov     qword ptr [rdx], 0
0x1800292e2  mov     rbx, rdx
0x1800292e5  mov     [rsp+58h+string], 0
0x1800292ee  lea     rdx, aSystemsettings_33; "SystemSettings_WorkAccess_AddWorkOrScho"...
0x1800292f5  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x1800292fa  lea     r8d, [r9+1]; unsigned int
0x1800292fe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029303  mov     rcx, [rsp+58h+string]; string
0x180029308  mov     rdx, rbx; newString
0x18002930b  call    cs:__imp_WindowsDuplicateString
0x180029312  nop     dword ptr [rax+rax+00h]
0x180029317  mov     ebx, eax
0x180029319  test    eax, eax
0x18002931b  jns     short loc_18002933A
0x18002931d  mov     rcx, [rsp+58h]; this
0x180029322  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180029329  mov     r9d, eax; char *
0x18002932c  mov     edx, 0C9h; void *
0x180029331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029336  mov     eax, ebx
0x180029338  jmp     short loc_18002933C
0x18002933a  xor     eax, eax
0x18002933c  mov     rcx, [rsp+58h+var_18]
0x180029341  xor     rcx, rsp; StackCookie
0x180029344  call    __security_check_cookie
0x180029349  add     rsp, 50h
0x18002934d  pop     rbx
0x18002934e  retn
```

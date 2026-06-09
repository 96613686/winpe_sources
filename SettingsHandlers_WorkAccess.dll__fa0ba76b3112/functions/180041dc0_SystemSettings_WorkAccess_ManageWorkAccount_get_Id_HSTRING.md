# SystemSettings::WorkAccess::ManageWorkAccount::get_Id(HSTRING__ * *)

- ea: `0x180041dc0`
- end: `0x180041e50`
- name: `?get_Id@ManageWorkAccount@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `144`
- prototype: `int(SystemSettings::WorkAccess::ManageWorkAccount *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x180041dc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180041e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180041e0b`

## string_xrefs

- `0x180041e22`: `shellcommon\shell\settingshandlers\workaccess\lib\manageworkaccount.cpp`
- `0x180041dee`: `SystemSettings_WorkAccess_ManageWorkAccount`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::ManageWorkAccount::get_Id(
        SystemSettings::WorkAccess::ManageWorkAccount *this,
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
    L"SystemSettings_WorkAccess_ManageWorkAccount",
    0x2Cu,
    0x2Bu);
  v3 = WindowsDuplicateString(string, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\manageworkaccount.cpp",
    (const char *)(unsigned int)v3,
    (int)hstringHeader.Reserved.Reserved1);
  return v4;
}

```

## disassembly

```asm
0x180041dc0  push    rbx
0x180041dc2  sub     rsp, 50h
0x180041dc6  mov     rax, cs:__security_cookie
0x180041dcd  xor     rax, rsp
0x180041dd0  mov     [rsp+58h+var_18], rax
0x180041dd5  mov     r9d, 2Bh ; '+'; unsigned int
0x180041ddb  mov     qword ptr [rdx], 0
0x180041de2  mov     rbx, rdx
0x180041de5  mov     [rsp+58h+string], 0
0x180041dee  lea     rdx, aSystemsettings_25; "SystemSettings_WorkAccess_ManageWorkAcc"...
0x180041df5  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x180041dfa  lea     r8d, [r9+1]; unsigned int
0x180041dfe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041e03  mov     rcx, [rsp+58h+string]; string
0x180041e08  mov     rdx, rbx; newString
0x180041e0b  call    cs:__imp_WindowsDuplicateString
0x180041e12  nop     dword ptr [rax+rax+00h]
0x180041e17  mov     ebx, eax
0x180041e19  test    eax, eax
0x180041e1b  jns     short loc_180041E3A
0x180041e1d  mov     rcx, [rsp+58h]; this
0x180041e22  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\settingshandlers\\w"...
0x180041e29  mov     r9d, eax; char *
0x180041e2c  mov     edx, 31h ; '1'; void *
0x180041e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041e36  mov     eax, ebx
0x180041e38  jmp     short loc_180041E3C
0x180041e3a  xor     eax, eax
0x180041e3c  mov     rcx, [rsp+58h+var_18]
0x180041e41  xor     rcx, rsp; StackCookie
0x180041e44  call    __security_check_cookie
0x180041e49  add     rsp, 50h
0x180041e4d  pop     rbx
0x180041e4e  retn
```

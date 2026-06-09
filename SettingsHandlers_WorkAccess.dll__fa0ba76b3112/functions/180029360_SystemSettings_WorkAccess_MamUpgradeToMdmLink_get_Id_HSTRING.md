# SystemSettings::WorkAccess::MamUpgradeToMdmLink::get_Id(HSTRING__ * *)

- ea: `0x180029360`
- end: `0x1800293f0`
- name: `?get_Id@MamUpgradeToMdmLink@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `144`
- prototype: `int(SystemSettings::WorkAccess::MamUpgradeToMdmLink *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x180029360`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800293ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800293ab`

## string_xrefs

- `0x18002938e`: `SystemSettings_WorkAccess_MamUpgradeToMdmLink`
- `0x1800293c2`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::MamUpgradeToMdmLink::get_Id(
        SystemSettings::WorkAccess::MamUpgradeToMdmLink *this,
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
    L"SystemSettings_WorkAccess_MamUpgradeToMdmLink",
    0x2Eu,
    0x2Du);
  v3 = WindowsDuplicateString(string, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x275,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
    (const char *)(unsigned int)v3,
    (int)hstringHeader.Reserved.Reserved1);
  return v4;
}

```

## disassembly

```asm
0x180029360  push    rbx
0x180029362  sub     rsp, 50h
0x180029366  mov     rax, cs:__security_cookie
0x18002936d  xor     rax, rsp
0x180029370  mov     [rsp+58h+var_18], rax
0x180029375  mov     r9d, 2Dh ; '-'; unsigned int
0x18002937b  mov     qword ptr [rdx], 0
0x180029382  mov     rbx, rdx
0x180029385  mov     [rsp+58h+string], 0
0x18002938e  lea     rdx, aSystemsettings_20; "SystemSettings_WorkAccess_MamUpgradeToM"...
0x180029395  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x18002939a  lea     r8d, [r9+1]; unsigned int
0x18002939e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800293a3  mov     rcx, [rsp+58h+string]; string
0x1800293a8  mov     rdx, rbx; newString
0x1800293ab  call    cs:__imp_WindowsDuplicateString
0x1800293b2  nop     dword ptr [rax+rax+00h]
0x1800293b7  mov     ebx, eax
0x1800293b9  test    eax, eax
0x1800293bb  jns     short loc_1800293DA
0x1800293bd  mov     rcx, [rsp+58h]; this
0x1800293c2  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x1800293c9  mov     r9d, eax; char *
0x1800293cc  mov     edx, 275h; void *
0x1800293d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293d6  mov     eax, ebx
0x1800293d8  jmp     short loc_1800293DC
0x1800293da  xor     eax, eax
0x1800293dc  mov     rcx, [rsp+58h+var_18]
0x1800293e1  xor     rcx, rsp; StackCookie
0x1800293e4  call    __security_check_cookie
0x1800293e9  add     rsp, 50h
0x1800293ed  pop     rbx
0x1800293ee  retn
```

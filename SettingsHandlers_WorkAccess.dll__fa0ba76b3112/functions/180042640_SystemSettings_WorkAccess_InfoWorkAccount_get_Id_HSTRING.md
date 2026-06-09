# SystemSettings::WorkAccess::InfoWorkAccount::get_Id(HSTRING__ * *)

- ea: `0x180042640`
- end: `0x1800426d0`
- name: `?get_Id@InfoWorkAccount@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `144`
- prototype: `int(SystemSettings::WorkAccess::InfoWorkAccount *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x180042640`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004268b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004268b`

## string_xrefs

- `0x1800426a2`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`
- `0x18004266e`: `SystemSettings_WorkAccess_InfoWorkAccount`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::InfoWorkAccount::get_Id(
        SystemSettings::WorkAccess::InfoWorkAccount *this,
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
    L"SystemSettings_WorkAccess_InfoWorkAccount",
    0x2Au,
    0x29u);
  v3 = WindowsDuplicateString(string, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8A,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
    (const char *)(unsigned int)v3,
    (int)hstringHeader.Reserved.Reserved1);
  return v4;
}

```

## disassembly

```asm
0x180042640  push    rbx
0x180042642  sub     rsp, 50h
0x180042646  mov     rax, cs:__security_cookie
0x18004264d  xor     rax, rsp
0x180042650  mov     [rsp+58h+var_18], rax
0x180042655  mov     r9d, 29h ; ')'; unsigned int
0x18004265b  mov     qword ptr [rdx], 0
0x180042662  mov     rbx, rdx
0x180042665  mov     [rsp+58h+string], 0
0x18004266e  lea     rdx, aSystemsettings_46; "SystemSettings_WorkAccess_InfoWorkAccou"...
0x180042675  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x18004267a  lea     r8d, [r9+1]; unsigned int
0x18004267e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042683  mov     rcx, [rsp+58h+string]; string
0x180042688  mov     rdx, rbx; newString
0x18004268b  call    cs:__imp_WindowsDuplicateString
0x180042692  nop     dword ptr [rax+rax+00h]
0x180042697  mov     ebx, eax
0x180042699  test    eax, eax
0x18004269b  jns     short loc_1800426BA
0x18004269d  mov     rcx, [rsp+58h]; this
0x1800426a2  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x1800426a9  mov     r9d, eax; char *
0x1800426ac  mov     edx, 8Ah; void *
0x1800426b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800426b6  mov     eax, ebx
0x1800426b8  jmp     short loc_1800426BC
0x1800426ba  xor     eax, eax
0x1800426bc  mov     rcx, [rsp+58h+var_18]
0x1800426c1  xor     rcx, rsp; StackCookie
0x1800426c4  call    __security_check_cookie
0x1800426c9  add     rsp, 50h
0x1800426cd  pop     rbx
0x1800426ce  retn
```

# SystemSettings::WorkAccess::DisconnectWorkAccount::get_Id(HSTRING__ * *)

- ea: `0x180041620`
- end: `0x1800416b0`
- name: `?get_Id@DisconnectWorkAccount@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `144`
- prototype: `int(SystemSettings::WorkAccess::DisconnectWorkAccount *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004166b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004166b`

## string_xrefs

- `0x180041682`: `shellcommon\shell\settingshandlers\workaccess\lib\disconnectworkaccount.cpp`
- `0x18004164e`: `SystemSettings_WorkAccess_DisconnectWorkAccount`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::DisconnectWorkAccount::get_Id(
        SystemSettings::WorkAccess::DisconnectWorkAccount *this,
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
    L"SystemSettings_WorkAccess_DisconnectWorkAccount",
    0x30u,
    0x2Fu);
  v3 = WindowsDuplicateString(string, a2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x57,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\disconnectworkaccount.cpp",
    (const char *)(unsigned int)v3,
    (int)hstringHeader.Reserved.Reserved1);
  return v4;
}

```

## disassembly

```asm
0x180041620  push    rbx
0x180041622  sub     rsp, 50h
0x180041626  mov     rax, cs:__security_cookie
0x18004162d  xor     rax, rsp
0x180041630  mov     [rsp+58h+var_18], rax
0x180041635  mov     r9d, 2Fh ; '/'; unsigned int
0x18004163b  mov     qword ptr [rdx], 0
0x180041642  mov     rbx, rdx
0x180041645  mov     [rsp+58h+string], 0
0x18004164e  lea     rdx, aSystemsettings_8; "SystemSettings_WorkAccess_DisconnectWor"...
0x180041655  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x18004165a  lea     r8d, [r9+1]; unsigned int
0x18004165e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041663  mov     rcx, [rsp+58h+string]; string
0x180041668  mov     rdx, rbx; newString
0x18004166b  call    cs:__imp_WindowsDuplicateString
0x180041672  nop     dword ptr [rax+rax+00h]
0x180041677  mov     ebx, eax
0x180041679  test    eax, eax
0x18004167b  jns     short loc_18004169A
0x18004167d  mov     rcx, [rsp+58h]; this
0x180041682  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\w"...
0x180041689  mov     r9d, eax; char *
0x18004168c  mov     edx, 57h ; 'W'; void *
0x180041691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041696  mov     eax, ebx
0x180041698  jmp     short loc_18004169C
0x18004169a  xor     eax, eax
0x18004169c  mov     rcx, [rsp+58h+var_18]
0x1800416a1  xor     rcx, rsp; StackCookie
0x1800416a4  call    __security_check_cookie
0x1800416a9  add     rsp, 50h
0x1800416ad  pop     rbx
0x1800416ae  retn
```

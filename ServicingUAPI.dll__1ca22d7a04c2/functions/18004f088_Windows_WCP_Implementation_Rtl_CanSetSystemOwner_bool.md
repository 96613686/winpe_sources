# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x18004f088`
- end: `0x18004f30a`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `642`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002c298`
- `0x180042178`
- `0x1800432e0`
- `0x180043c70`
- `0x180124100`
- `0x18012fa2c`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x18004f088`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18004f22f`
- `ntdll!NtPrivilegeCheck` at `0x18004f22f`
- `ntdll!NtOpenThreadToken` at `0x18004f0d2`
- `ntdll!NtOpenThreadToken` at `0x18004f0d2`
- `ntdll!NtClose` at `0x18004f13f`
- `ntdll!NtClose` at `0x18004f1e3`
- `ntdll!NtClose` at `0x18004f28c`
- `ntdll!NtClose` at `0x18004f2c7`
- `ntdll!NtClose` at `0x18004f13f`
- `ntdll!NtClose` at `0x18004f1e3`
- `ntdll!NtClose` at `0x18004f28c`
- `ntdll!NtClose` at `0x18004f2c7`
- `ntdll!NtOpenProcessToken` at `0x18004f186`
- `ntdll!NtOpenProcessToken` at `0x18004f186`

## string_xrefs

- `0x18004f0f4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f198`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f241`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f25f`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`
- `0x18004f112`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x18004f1b6`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
        Windows::WCP::Implementation::Rtl *this,
        bool *a2)
{
  unsigned int v3; // ebx
  void *v5; // rcx
  _QWORD v6[4]; // [rsp+28h] [rbp-49h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v8[5]; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int8 Result[8]; // [rsp+90h] [rbp+1Fh] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+27h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+A0h] [rbp+2Fh] BYREF

  v8[4] = -2;
  *(_BYTE *)this = 0;
  TokenHandle = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741700 )
  {
    v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v6[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v6[2] = 570;
    v6[3] = "NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())";
    RtlReportErrorOrigination(v6, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return v3;
  }
  v5 = TokenHandle;
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( (v3 & 0x80000000) != 0 )
    {
      v7[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v7[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
      v7[2] = 578;
      v7[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())";
      RtlReportErrorOrigination(v7, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(TokenHandle) < 0 )
          __fastfail(7u);
        TokenHandle = 0;
      }
      return v3;
    }
    v5 = TokenHandle;
  }
  Result[0] = 0;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  v3 = NtPrivilegeCheck(v5, &RequiredPrivileges, Result);
  if ( (v3 & 0x80000000) != 0 )
  {
    v8[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v8[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v8[2] = 586;
    v8[3] = "NtPrivilegeCheck(Token, &PrivilegeSet, &Result)";
    RtlReportErrorOrigination(v8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return v3;
  }
  *(_BYTE *)this = Result[0] != 0;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(TokenHandle) < 0 )
      __fastfail(7u);
    TokenHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18004f088  mov     rax, rsp
0x18004f08b  push    rbp
0x18004f08c  lea     rbp, [rax-5Fh]
0x18004f090  sub     rsp, 0C0h
0x18004f097  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18004f09f  mov     [rax+10h], rbx
0x18004f0a3  mov     [rax+18h], rdi
0x18004f0a7  mov     rax, cs:__security_cookie
0x18004f0ae  xor     rax, rsp
0x18004f0b1  mov     [rbp+57h+var_10], rax
0x18004f0b5  mov     rdi, rcx
0x18004f0b8  mov     byte ptr [rcx], 0
0x18004f0bb  mov     [rbp+57h+TokenHandle], 0
0x18004f0c3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004f0c7  xor     r8d, r8d; OpenAsSelf
0x18004f0ca  lea     edx, [r8+8]; DesiredAccess
0x18004f0ce  lea     rcx, [r8-2]; ThreadHandle
0x18004f0d2  call    cs:__imp_NtOpenThreadToken
0x18004f0d9  nop     dword ptr [rax+rax+00h]
0x18004f0de  mov     ebx, eax
0x18004f0e0  mov     eax, 80000000h
0x18004f0e5  lea     ecx, [rbx+rax]
0x18004f0e8  test    eax, ecx
0x18004f0ea  jnz     short loc_18004F165
0x18004f0ec  cmp     ebx, 0C000007Ch
0x18004f0f2  jz      short loc_18004F165
0x18004f0f4  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f0fb  mov     [rbp+57h+var_A0], rax
0x18004f0ff  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x18004f106  mov     [rbp+57h+var_98], rax
0x18004f10a  mov     [rbp+57h+var_90], 23Ah
0x18004f112  lea     rax, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18004f119  mov     [rbp+57h+var_88], rax
0x18004f11d  mov     r8d, ebx
0x18004f120  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f127  lea     rcx, [rbp+57h+var_A0]
0x18004f12b  call    RtlReportErrorOrigination
0x18004f130  nop
0x18004f131  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18004f135  lea     rax, [rcx-1]
0x18004f139  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004f13d  ja      short loc_18004F15E
0x18004f13f  call    cs:__imp_NtClose
0x18004f146  nop     dword ptr [rax+rax+00h]
0x18004f14b  test    eax, eax
0x18004f14d  jns     short loc_18004F156
0x18004f14f  mov     ecx, 7
0x18004f154  int     29h; Win8: RtlFailFast(ecx)
0x18004f156  mov     [rbp+57h+TokenHandle], 0
0x18004f15e  mov     eax, ebx
0x18004f160  jmp     loc_18004F2E8
0x18004f165  mov     rcx, [rbp+57h+TokenHandle]
0x18004f169  lea     rax, [rcx+1]
0x18004f16d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004f173  jnz     loc_18004F20B
0x18004f179  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18004f17d  mov     edx, 8; DesiredAccess
0x18004f182  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004f186  call    cs:__imp_NtOpenProcessToken
0x18004f18d  nop     dword ptr [rax+rax+00h]
0x18004f192  mov     ebx, eax
0x18004f194  test    eax, eax
0x18004f196  jns     short loc_18004F207
0x18004f198  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f19f  mov     [rbp+57h+var_80], rax
0x18004f1a3  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x18004f1aa  mov     [rbp+57h+var_78], rax
0x18004f1ae  mov     [rbp+57h+var_70], 242h
0x18004f1b6  lea     rax, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18004f1bd  mov     [rbp+57h+var_68], rax
0x18004f1c1  mov     r8d, ebx
0x18004f1c4  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f1cb  lea     rcx, [rbp+57h+var_80]
0x18004f1cf  call    RtlReportErrorOrigination
0x18004f1d4  nop
0x18004f1d5  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18004f1d9  lea     rax, [rcx-1]
0x18004f1dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004f1e1  ja      short loc_18004F202
0x18004f1e3  call    cs:__imp_NtClose
0x18004f1ea  nop     dword ptr [rax+rax+00h]
0x18004f1ef  test    eax, eax
0x18004f1f1  jns     short loc_18004F1FA
0x18004f1f3  mov     ecx, 7
0x18004f1f8  int     29h; Win8: RtlFailFast(ecx)
0x18004f1fa  mov     [rbp+57h+TokenHandle], 0
0x18004f202  jmp     loc_18004F15E
0x18004f207  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x18004f20b  mov     [rbp+57h+Result], 0
0x18004f20f  mov     eax, 1
0x18004f214  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x18004f217  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x18004f21a  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x18004f222  xor     eax, eax
0x18004f224  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18004f227  lea     r8, [rbp+57h+Result]; Result
0x18004f22b  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18004f22f  call    cs:__imp_NtPrivilegeCheck
0x18004f236  nop     dword ptr [rax+rax+00h]
0x18004f23b  mov     ebx, eax
0x18004f23d  test    eax, eax
0x18004f23f  jns     short loc_18004F2B0
0x18004f241  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f248  mov     [rbp+57h+var_60], rax
0x18004f24c  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x18004f253  mov     [rbp+57h+var_58], rax
0x18004f257  mov     [rbp+57h+var_50], 24Ah
0x18004f25f  lea     rax, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x18004f266  mov     [rbp+57h+var_48], rax
0x18004f26a  mov     r8d, ebx
0x18004f26d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f274  lea     rcx, [rbp+57h+var_60]
0x18004f278  call    RtlReportErrorOrigination
0x18004f27d  nop
0x18004f27e  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18004f282  lea     rax, [rcx-1]
0x18004f286  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004f28a  ja      short loc_18004F2AB
0x18004f28c  call    cs:__imp_NtClose
0x18004f293  nop     dword ptr [rax+rax+00h]
0x18004f298  test    eax, eax
0x18004f29a  jns     short loc_18004F2A3
0x18004f29c  mov     ecx, 7
0x18004f2a1  int     29h; Win8: RtlFailFast(ecx)
0x18004f2a3  mov     [rbp+57h+TokenHandle], 0
0x18004f2ab  jmp     loc_18004F15E
0x18004f2b0  cmp     [rbp+57h+Result], 0
0x18004f2b4  setnz   al
0x18004f2b7  mov     [rdi], al
0x18004f2b9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18004f2bd  lea     rax, [rcx-1]
0x18004f2c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004f2c5  ja      short loc_18004F2E6
0x18004f2c7  call    cs:__imp_NtClose
0x18004f2ce  nop     dword ptr [rax+rax+00h]
0x18004f2d3  test    eax, eax
0x18004f2d5  jns     short loc_18004F2DE
0x18004f2d7  mov     ecx, 7
0x18004f2dc  int     29h; Win8: RtlFailFast(ecx)
0x18004f2de  mov     [rbp+57h+TokenHandle], 0
0x18004f2e6  xor     eax, eax
0x18004f2e8  mov     rcx, [rbp+57h+var_10]
0x18004f2ec  xor     rcx, rsp; StackCookie
0x18004f2ef  call    __security_check_cookie
0x18004f2f4  lea     r11, [rsp+0C0h+var_s0]
0x18004f2fc  mov     rbx, [r11+18h]
0x18004f300  mov     rdi, [r11+20h]
0x18004f304  mov     rsp, r11
0x18004f307  pop     rbp
0x18004f308  retn
```

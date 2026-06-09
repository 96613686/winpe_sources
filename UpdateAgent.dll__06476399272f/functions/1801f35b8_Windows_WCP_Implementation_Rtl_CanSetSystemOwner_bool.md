# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x1801f35b8`
- end: `0x1801f383a`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `642`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180149300`
- `0x18014ced0`
- `0x1801873f0`
- `0x180192cec`
- `0x1801df218`
- `0x1801df624`

## callees

- `0x1800059d0`
- `0x1801efdc0`
- `0x1801f35b8`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x1801f36b6`
- `ntdll!NtOpenProcessToken` at `0x1801f36b6`
- `ntdll!NtOpenThreadToken` at `0x1801f3602`
- `ntdll!NtOpenThreadToken` at `0x1801f3602`
- `ntdll!NtClose` at `0x1801f366f`
- `ntdll!NtClose` at `0x1801f3713`
- `ntdll!NtClose` at `0x1801f37bc`
- `ntdll!NtClose` at `0x1801f37f7`
- `ntdll!NtClose` at `0x1801f366f`
- `ntdll!NtClose` at `0x1801f3713`
- `ntdll!NtClose` at `0x1801f37bc`
- `ntdll!NtClose` at `0x1801f37f7`
- `ntdll!NtPrivilegeCheck` at `0x1801f375f`
- `ntdll!NtPrivilegeCheck` at `0x1801f375f`

## string_xrefs

- `0x1801f3624`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f36c8`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f3771`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f36e6`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x1801f3642`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x1801f378f`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

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
0x1801f35b8  mov     rax, rsp
0x1801f35bb  push    rbp
0x1801f35bc  lea     rbp, [rax-5Fh]
0x1801f35c0  sub     rsp, 0C0h
0x1801f35c7  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x1801f35cf  mov     [rax+10h], rbx
0x1801f35d3  mov     [rax+18h], rdi
0x1801f35d7  mov     rax, cs:__security_cookie
0x1801f35de  xor     rax, rsp
0x1801f35e1  mov     [rbp+57h+var_10], rax
0x1801f35e5  mov     rdi, rcx
0x1801f35e8  mov     byte ptr [rcx], 0
0x1801f35eb  mov     [rbp+57h+TokenHandle], 0
0x1801f35f3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801f35f7  xor     r8d, r8d; OpenAsSelf
0x1801f35fa  lea     edx, [r8+8]; DesiredAccess
0x1801f35fe  lea     rcx, [r8-2]; ThreadHandle
0x1801f3602  call    cs:__imp_NtOpenThreadToken
0x1801f3609  nop     dword ptr [rax+rax+00h]
0x1801f360e  mov     ebx, eax
0x1801f3610  mov     eax, 80000000h
0x1801f3615  lea     ecx, [rbx+rax]
0x1801f3618  test    eax, ecx
0x1801f361a  jnz     short loc_1801F3695
0x1801f361c  cmp     ebx, 0C000007Ch
0x1801f3622  jz      short loc_1801F3695
0x1801f3624  lea     rax, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f362b  mov     [rbp+57h+var_A0], rax
0x1801f362f  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x1801f3636  mov     [rbp+57h+var_98], rax
0x1801f363a  mov     [rbp+57h+var_90], 23Ah
0x1801f3642  lea     rax, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x1801f3649  mov     [rbp+57h+var_88], rax
0x1801f364d  mov     r8d, ebx
0x1801f3650  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f3657  lea     rcx, [rbp+57h+var_A0]
0x1801f365b  call    RtlReportErrorOrigination
0x1801f3660  nop
0x1801f3661  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1801f3665  lea     rax, [rcx-1]
0x1801f3669  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f366d  ja      short loc_1801F368E
0x1801f366f  call    cs:__imp_NtClose
0x1801f3676  nop     dword ptr [rax+rax+00h]
0x1801f367b  test    eax, eax
0x1801f367d  jns     short loc_1801F3686
0x1801f367f  mov     ecx, 7
0x1801f3684  int     29h; Win8: RtlFailFast(ecx)
0x1801f3686  mov     [rbp+57h+TokenHandle], 0
0x1801f368e  mov     eax, ebx
0x1801f3690  jmp     loc_1801F3818
0x1801f3695  mov     rcx, [rbp+57h+TokenHandle]
0x1801f3699  lea     rax, [rcx+1]
0x1801f369d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801f36a3  jnz     loc_1801F373B
0x1801f36a9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1801f36ad  mov     edx, 8; DesiredAccess
0x1801f36b2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1801f36b6  call    cs:__imp_NtOpenProcessToken
0x1801f36bd  nop     dword ptr [rax+rax+00h]
0x1801f36c2  mov     ebx, eax
0x1801f36c4  test    eax, eax
0x1801f36c6  jns     short loc_1801F3737
0x1801f36c8  lea     rax, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f36cf  mov     [rbp+57h+var_80], rax
0x1801f36d3  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x1801f36da  mov     [rbp+57h+var_78], rax
0x1801f36de  mov     [rbp+57h+var_70], 242h
0x1801f36e6  lea     rax, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1801f36ed  mov     [rbp+57h+var_68], rax
0x1801f36f1  mov     r8d, ebx
0x1801f36f4  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f36fb  lea     rcx, [rbp+57h+var_80]
0x1801f36ff  call    RtlReportErrorOrigination
0x1801f3704  nop
0x1801f3705  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1801f3709  lea     rax, [rcx-1]
0x1801f370d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f3711  ja      short loc_1801F3732
0x1801f3713  call    cs:__imp_NtClose
0x1801f371a  nop     dword ptr [rax+rax+00h]
0x1801f371f  test    eax, eax
0x1801f3721  jns     short loc_1801F372A
0x1801f3723  mov     ecx, 7
0x1801f3728  int     29h; Win8: RtlFailFast(ecx)
0x1801f372a  mov     [rbp+57h+TokenHandle], 0
0x1801f3732  jmp     loc_1801F368E
0x1801f3737  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x1801f373b  mov     [rbp+57h+Result], 0
0x1801f373f  mov     eax, 1
0x1801f3744  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x1801f3747  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x1801f374a  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1801f3752  xor     eax, eax
0x1801f3754  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1801f3757  lea     r8, [rbp+57h+Result]; Result
0x1801f375b  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1801f375f  call    cs:__imp_NtPrivilegeCheck
0x1801f3766  nop     dword ptr [rax+rax+00h]
0x1801f376b  mov     ebx, eax
0x1801f376d  test    eax, eax
0x1801f376f  jns     short loc_1801F37E0
0x1801f3771  lea     rax, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f3778  mov     [rbp+57h+var_60], rax
0x1801f377c  lea     rax, aWindowsWcpImpl_8; "Windows::WCP::Implementation::Rtl::CanS"...
0x1801f3783  mov     [rbp+57h+var_58], rax
0x1801f3787  mov     [rbp+57h+var_50], 24Ah
0x1801f378f  lea     rax, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x1801f3796  mov     [rbp+57h+var_48], rax
0x1801f379a  mov     r8d, ebx
0x1801f379d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f37a4  lea     rcx, [rbp+57h+var_60]
0x1801f37a8  call    RtlReportErrorOrigination
0x1801f37ad  nop
0x1801f37ae  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1801f37b2  lea     rax, [rcx-1]
0x1801f37b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f37ba  ja      short loc_1801F37DB
0x1801f37bc  call    cs:__imp_NtClose
0x1801f37c3  nop     dword ptr [rax+rax+00h]
0x1801f37c8  test    eax, eax
0x1801f37ca  jns     short loc_1801F37D3
0x1801f37cc  mov     ecx, 7
0x1801f37d1  int     29h; Win8: RtlFailFast(ecx)
0x1801f37d3  mov     [rbp+57h+TokenHandle], 0
0x1801f37db  jmp     loc_1801F368E
0x1801f37e0  cmp     [rbp+57h+Result], 0
0x1801f37e4  setnz   al
0x1801f37e7  mov     [rdi], al
0x1801f37e9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1801f37ed  lea     rax, [rcx-1]
0x1801f37f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f37f5  ja      short loc_1801F3816
0x1801f37f7  call    cs:__imp_NtClose
0x1801f37fe  nop     dword ptr [rax+rax+00h]
0x1801f3803  test    eax, eax
0x1801f3805  jns     short loc_1801F380E
0x1801f3807  mov     ecx, 7
0x1801f380c  int     29h; Win8: RtlFailFast(ecx)
0x1801f380e  mov     [rbp+57h+TokenHandle], 0
0x1801f3816  xor     eax, eax
0x1801f3818  mov     rcx, [rbp+57h+var_10]
0x1801f381c  xor     rcx, rsp; StackCookie
0x1801f381f  call    __security_check_cookie
0x1801f3824  lea     r11, [rsp+0C0h+var_s0]
0x1801f382c  mov     rbx, [r11+18h]
0x1801f3830  mov     rdi, [r11+20h]
0x1801f3834  mov     rsp, r11
0x1801f3837  pop     rbp
0x1801f3838  retn
```

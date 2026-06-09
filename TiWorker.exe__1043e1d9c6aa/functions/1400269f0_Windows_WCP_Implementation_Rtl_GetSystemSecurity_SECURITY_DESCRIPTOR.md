# Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)

- ea: `0x1400269f0`
- end: `0x140026acc`
- name: `?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010e7c`
- `0x1400146f4`
- `0x140015228`

## callees

- `0x140002310`
- `0x140002584`
- `0x140003150`
- `0x1400031b8`
- `0x140006b54`
- `0x140025f24`
- `0x1400269f0`

## string_xrefs

- `0x140026a42`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026a5c`: `Windows::WCP::Implementation::Rtl::GetSystemSecurity`
- `0x140026a6d`: `g_SystemSecurityStatus`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity(
        Windows::WCP::Implementation::Rtl *this,
        struct _SECURITY_DESCRIPTOR **a2)
{
  PVOID ThreadLocalStoragePointer; // rax
  __int64 v4; // r8
  _QWORD v6[4]; // [rsp+20h] [rbp-38h] BYREF
  int v7; // [rsp+40h] [rbp-18h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v7 = 0;
  if ( dword_1400538E0 > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_1400538E0);
    if ( dword_1400538E0 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__);
      Init_thread_footer(&dword_1400538E0);
    }
  }
  v4 = (unsigned int)dword_140053790;
  *(_QWORD *)this = P;
  if ( (int)v4 >= 0 )
    return 0;
  v6[2] = 194;
  v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v6[1] = "Windows::WCP::Implementation::Rtl::GetSystemSecurity";
  v6[3] = "g_SystemSecurityStatus";
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           &v7,
           v6,
           v4);
}

```

## disassembly

```asm
0x1400269f0  push    rbx
0x1400269f2  sub     rsp, 50h
0x1400269f6  mov     rax, cs:__security_cookie
0x1400269fd  xor     rax, rsp
0x140026a00  mov     [rsp+58h+var_10], rax
0x140026a05  mov     rax, gs:58h
0x140026a0e  mov     rbx, rcx
0x140026a11  mov     ecx, 130h
0x140026a16  mov     [rsp+58h+var_18], 0
0x140026a1e  mov     rdx, [rax]
0x140026a21  mov     eax, [rcx+rdx]
0x140026a24  cmp     cs:dword_1400538E0, eax
0x140026a2a  jg      short loc_140026A95
0x140026a2c  mov     rax, qword ptr cs:P
0x140026a33  mov     r8d, cs:dword_140053790
0x140026a3a  mov     [rbx], rax
0x140026a3d  test    r8d, r8d
0x140026a40  jns     short loc_140026A80
0x140026a42  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026a49  mov     [rsp+58h+var_28], 0C2h
0x140026a52  mov     [rsp+58h+var_38], rax
0x140026a57  lea     rdx, [rsp+58h+var_38]
0x140026a5c  lea     rax, aWindowsWcpImpl_0; "Windows::WCP::Implementation::Rtl::GetS"...
0x140026a63  mov     [rsp+58h+var_30], rax
0x140026a68  lea     rcx, [rsp+58h+var_18]
0x140026a6d  lea     rax, aGSystemsecurit; "g_SystemSecurityStatus"
0x140026a74  mov     [rsp+58h+var_20], rax
0x140026a79  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026a7e  jmp     short loc_140026A82
0x140026a80  xor     eax, eax
0x140026a82  mov     rcx, [rsp+58h+var_10]
0x140026a87  xor     rcx, rsp; StackCookie
0x140026a8a  call    __security_check_cookie
0x140026a8f  add     rsp, 50h
0x140026a93  pop     rbx
0x140026a94  retn
0x140026a95  lea     rcx, dword_1400538E0
0x140026a9c  call    _Init_thread_header
0x140026aa1  cmp     cs:dword_1400538E0, 0FFFFFFFFh
0x140026aa8  jnz     short loc_140026A2C
0x140026aaa  call    _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____lambda_1___operator__
0x140026aaf  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____dynamic_atexit_destructor_for__g_SystemSecurity__; void (__cdecl *)()
0x140026ab6  call    atexit
0x140026abb  lea     rcx, dword_1400538E0
0x140026ac2  call    _Init_thread_footer
0x140026ac7  jmp     loc_140026A2C
```

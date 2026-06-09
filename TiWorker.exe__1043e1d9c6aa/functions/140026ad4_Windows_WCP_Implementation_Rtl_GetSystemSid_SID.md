# Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)

- ea: `0x140026ad4`
- end: `0x140026bb0`
- name: `?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SID **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025f24`

## callees

- `0x140002310`
- `0x140002584`
- `0x140003150`
- `0x1400031b8`
- `0x140006b54`
- `0x140025f7c`
- `0x140026ad4`

## string_xrefs

- `0x140026b26`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026b40`: `Windows::WCP::Implementation::Rtl::GetSystemSid`
- `0x140026b51`: `g_SystemSidStatus`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetSystemSid(
        Windows::WCP::Implementation::Rtl *this,
        struct _SID **a2)
{
  PVOID ThreadLocalStoragePointer; // rax
  __int64 v4; // r8
  _QWORD v6[4]; // [rsp+20h] [rbp-38h] BYREF
  int v7; // [rsp+40h] [rbp-18h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v7 = 0;
  if ( dword_1400538E4 > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_1400538E4);
    if ( dword_1400538E4 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__);
      Init_thread_footer(&dword_1400538E4);
    }
  }
  v4 = (unsigned int)dword_14005378C;
  *(_QWORD *)this = qword_1400538D8;
  if ( (int)v4 >= 0 )
    return 0;
  v6[2] = 119;
  v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v6[1] = "Windows::WCP::Implementation::Rtl::GetSystemSid";
  v6[3] = "g_SystemSidStatus";
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           &v7,
           v6,
           v4);
}

```

## disassembly

```asm
0x140026ad4  push    rbx
0x140026ad6  sub     rsp, 50h
0x140026ada  mov     rax, cs:__security_cookie
0x140026ae1  xor     rax, rsp
0x140026ae4  mov     [rsp+58h+var_10], rax
0x140026ae9  mov     rax, gs:58h
0x140026af2  mov     rbx, rcx
0x140026af5  mov     ecx, 130h
0x140026afa  mov     [rsp+58h+var_18], 0
0x140026b02  mov     rdx, [rax]
0x140026b05  mov     eax, [rcx+rdx]
0x140026b08  cmp     cs:dword_1400538E4, eax
0x140026b0e  jg      short loc_140026B79
0x140026b10  mov     rax, cs:qword_1400538D8
0x140026b17  mov     r8d, cs:dword_14005378C
0x140026b1e  mov     [rbx], rax
0x140026b21  test    r8d, r8d
0x140026b24  jns     short loc_140026B64
0x140026b26  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026b2d  mov     [rsp+58h+var_28], 77h ; 'w'
0x140026b36  mov     [rsp+58h+var_38], rax
0x140026b3b  lea     rdx, [rsp+58h+var_38]
0x140026b40  lea     rax, aWindowsWcpImpl_2; "Windows::WCP::Implementation::Rtl::GetS"...
0x140026b47  mov     [rsp+58h+var_30], rax
0x140026b4c  lea     rcx, [rsp+58h+var_18]
0x140026b51  lea     rax, aGSystemsidstat; "g_SystemSidStatus"
0x140026b58  mov     [rsp+58h+var_20], rax
0x140026b5d  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026b62  jmp     short loc_140026B66
0x140026b64  xor     eax, eax
0x140026b66  mov     rcx, [rsp+58h+var_10]
0x140026b6b  xor     rcx, rsp; StackCookie
0x140026b6e  call    __security_check_cookie
0x140026b73  add     rsp, 50h
0x140026b77  pop     rbx
0x140026b78  retn
0x140026b79  lea     rcx, dword_1400538E4
0x140026b80  call    _Init_thread_header
0x140026b85  cmp     cs:dword_1400538E4, 0FFFFFFFFh
0x140026b8c  jnz     short loc_140026B10
0x140026b8e  call    _Windows__WCP__Implementation__Rtl__GetSystemSid____5____lambda_1___operator__
0x140026b93  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSid____5____dynamic_atexit_destructor_for__g_SystemSid__; void (__cdecl *)()
0x140026b9a  call    atexit
0x140026b9f  lea     rcx, dword_1400538E4
0x140026ba6  call    _Init_thread_footer
0x140026bab  jmp     loc_140026B10
```

# Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)

- ea: `0x1400267e4`
- end: `0x1400268c0`
- name: `?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140019c2c`
- `0x14001eb74`
- `0x14001fc6c`

## callees

- `0x1400023e0`
- `0x140002654`
- `0x140003220`
- `0x140003288`
- `0x140008138`
- `0x1400261c8`
- `0x1400267e4`

## string_xrefs

- `0x140026836`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026861`: `g_SystemSecurityStatus`
- `0x140026850`: `Windows::WCP::Implementation::Rtl::GetSystemSecurity`

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
  if ( dword_140040A38 > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_140040A38);
    if ( dword_140040A38 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__);
      Init_thread_footer(&dword_140040A38);
    }
  }
  v4 = (unsigned int)dword_1400408E0;
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
0x1400267e4  push    rbx
0x1400267e6  sub     rsp, 50h
0x1400267ea  mov     rax, cs:__security_cookie
0x1400267f1  xor     rax, rsp
0x1400267f4  mov     [rsp+58h+var_10], rax
0x1400267f9  mov     rax, gs:58h
0x140026802  mov     rbx, rcx
0x140026805  mov     ecx, 130h
0x14002680a  mov     [rsp+58h+var_18], 0
0x140026812  mov     rdx, [rax]
0x140026815  mov     eax, [rcx+rdx]
0x140026818  cmp     cs:dword_140040A38, eax
0x14002681e  jg      short loc_140026889
0x140026820  mov     rax, qword ptr cs:P
0x140026827  mov     r8d, cs:dword_1400408E0
0x14002682e  mov     [rbx], rax
0x140026831  test    r8d, r8d
0x140026834  jns     short loc_140026874
0x140026836  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002683d  mov     [rsp+58h+var_28], 0C2h
0x140026846  mov     [rsp+58h+var_38], rax
0x14002684b  lea     rdx, [rsp+58h+var_38]
0x140026850  lea     rax, aWindowsWcpImpl_0; "Windows::WCP::Implementation::Rtl::GetS"...
0x140026857  mov     [rsp+58h+var_30], rax
0x14002685c  lea     rcx, [rsp+58h+var_18]
0x140026861  lea     rax, aGSystemsecurit; "g_SystemSecurityStatus"
0x140026868  mov     [rsp+58h+var_20], rax
0x14002686d  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026872  jmp     short loc_140026876
0x140026874  xor     eax, eax
0x140026876  mov     rcx, [rsp+58h+var_10]
0x14002687b  xor     rcx, rsp; StackCookie
0x14002687e  call    __security_check_cookie
0x140026883  add     rsp, 50h
0x140026887  pop     rbx
0x140026888  retn
0x140026889  lea     rcx, dword_140040A38
0x140026890  call    _Init_thread_header
0x140026895  cmp     cs:dword_140040A38, 0FFFFFFFFh
0x14002689c  jnz     short loc_140026820
0x14002689e  call    _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____lambda_1___operator__
0x1400268a3  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____dynamic_atexit_destructor_for__g_SystemSecurity__; void (__cdecl *)()
0x1400268aa  call    atexit
0x1400268af  lea     rcx, dword_140040A38
0x1400268b6  call    _Init_thread_footer
0x1400268bb  jmp     loc_140026820
```

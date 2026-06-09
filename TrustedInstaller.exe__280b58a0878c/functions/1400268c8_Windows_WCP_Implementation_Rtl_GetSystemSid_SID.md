# Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)

- ea: `0x1400268c8`
- end: `0x1400269a4`
- name: `?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SID **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400261c8`

## callees

- `0x1400023e0`
- `0x140002654`
- `0x140003220`
- `0x140003288`
- `0x140008138`
- `0x140026220`
- `0x1400268c8`

## string_xrefs

- `0x14002691a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026945`: `g_SystemSidStatus`
- `0x140026934`: `Windows::WCP::Implementation::Rtl::GetSystemSid`

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
  if ( dword_140040A3C > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_140040A3C);
    if ( dword_140040A3C == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__);
      Init_thread_footer(&dword_140040A3C);
    }
  }
  v4 = (unsigned int)dword_1400408DC;
  *(_QWORD *)this = qword_140040A30;
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
0x1400268c8  push    rbx
0x1400268ca  sub     rsp, 50h
0x1400268ce  mov     rax, cs:__security_cookie
0x1400268d5  xor     rax, rsp
0x1400268d8  mov     [rsp+58h+var_10], rax
0x1400268dd  mov     rax, gs:58h
0x1400268e6  mov     rbx, rcx
0x1400268e9  mov     ecx, 130h
0x1400268ee  mov     [rsp+58h+var_18], 0
0x1400268f6  mov     rdx, [rax]
0x1400268f9  mov     eax, [rcx+rdx]
0x1400268fc  cmp     cs:dword_140040A3C, eax
0x140026902  jg      short loc_14002696D
0x140026904  mov     rax, cs:qword_140040A30
0x14002690b  mov     r8d, cs:dword_1400408DC
0x140026912  mov     [rbx], rax
0x140026915  test    r8d, r8d
0x140026918  jns     short loc_140026958
0x14002691a  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026921  mov     [rsp+58h+var_28], 77h ; 'w'
0x14002692a  mov     [rsp+58h+var_38], rax
0x14002692f  lea     rdx, [rsp+58h+var_38]
0x140026934  lea     rax, aWindowsWcpImpl_2; "Windows::WCP::Implementation::Rtl::GetS"...
0x14002693b  mov     [rsp+58h+var_30], rax
0x140026940  lea     rcx, [rsp+58h+var_18]
0x140026945  lea     rax, aGSystemsidstat; "g_SystemSidStatus"
0x14002694c  mov     [rsp+58h+var_20], rax
0x140026951  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026956  jmp     short loc_14002695A
0x140026958  xor     eax, eax
0x14002695a  mov     rcx, [rsp+58h+var_10]
0x14002695f  xor     rcx, rsp; StackCookie
0x140026962  call    __security_check_cookie
0x140026967  add     rsp, 50h
0x14002696b  pop     rbx
0x14002696c  retn
0x14002696d  lea     rcx, dword_140040A3C
0x140026974  call    _Init_thread_header
0x140026979  cmp     cs:dword_140040A3C, 0FFFFFFFFh
0x140026980  jnz     short loc_140026904
0x140026982  call    _Windows__WCP__Implementation__Rtl__GetSystemSid____5____lambda_1___operator__
0x140026987  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSid____5____dynamic_atexit_destructor_for__g_SystemSid__; void (__cdecl *)()
0x14002698e  call    atexit
0x140026993  lea     rcx, dword_140040A3C
0x14002699a  call    _Init_thread_footer
0x14002699f  jmp     loc_140026904
```

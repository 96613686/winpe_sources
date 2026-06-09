# Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)

- ea: `0x14002793c`
- end: `0x140027a18`
- name: `?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SID **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140027248`

## callees

- `0x140002360`
- `0x1400025d4`
- `0x140003150`
- `0x1400031b8`
- `0x140026548`
- `0x1400272a0`
- `0x14002793c`

## string_xrefs

- `0x14002798e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400279a8`: `Windows::WCP::Implementation::Rtl::GetSystemSid`
- `0x1400279b9`: `g_SystemSidStatus`

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
  if ( dword_14005078C > *(_DWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) )
  {
    Init_thread_header(&dword_14005078C);
    if ( dword_14005078C == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__);
      Init_thread_footer(&dword_14005078C);
    }
  }
  v4 = (unsigned int)dword_14005063C;
  *(_QWORD *)this = qword_140050780;
  if ( (int)v4 >= 0 )
    return 0;
  v6[2] = 119;
  v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v6[1] = "Windows::WCP::Implementation::Rtl::GetSystemSid";
  v6[3] = "g_SystemSidStatus";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v7,
           v6,
           v4);
}

```

## disassembly

```asm
0x14002793c  push    rbx
0x14002793e  sub     rsp, 50h
0x140027942  mov     rax, cs:__security_cookie
0x140027949  xor     rax, rsp
0x14002794c  mov     [rsp+58h+var_10], rax
0x140027951  mov     rax, gs:58h
0x14002795a  mov     rbx, rcx
0x14002795d  mov     ecx, 130h
0x140027962  mov     [rsp+58h+var_18], 0
0x14002796a  mov     rdx, [rax]
0x14002796d  mov     eax, [rcx+rdx]
0x140027970  cmp     cs:dword_14005078C, eax
0x140027976  jg      short loc_1400279E1
0x140027978  mov     rax, cs:qword_140050780
0x14002797f  mov     r8d, cs:dword_14005063C
0x140027986  mov     [rbx], rax
0x140027989  test    r8d, r8d
0x14002798c  jns     short loc_1400279CC
0x14002798e  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027995  mov     [rsp+58h+var_28], 77h ; 'w'
0x14002799e  mov     [rsp+58h+var_38], rax
0x1400279a3  lea     rdx, [rsp+58h+var_38]
0x1400279a8  lea     rax, aWindowsWcpImpl_2; "Windows::WCP::Implementation::Rtl::GetS"...
0x1400279af  mov     [rsp+58h+var_30], rax
0x1400279b4  lea     rcx, [rsp+58h+var_18]
0x1400279b9  lea     rax, aGSystemsidstat; "g_SystemSidStatus"
0x1400279c0  mov     [rsp+58h+var_20], rax
0x1400279c5  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1400279ca  jmp     short loc_1400279CE
0x1400279cc  xor     eax, eax
0x1400279ce  mov     rcx, [rsp+58h+var_10]
0x1400279d3  xor     rcx, rsp; StackCookie
0x1400279d6  call    __security_check_cookie
0x1400279db  add     rsp, 50h
0x1400279df  pop     rbx
0x1400279e0  retn
0x1400279e1  lea     rcx, dword_14005078C
0x1400279e8  call    _Init_thread_header
0x1400279ed  cmp     cs:dword_14005078C, 0FFFFFFFFh
0x1400279f4  jnz     short loc_140027978
0x1400279f6  call    _Windows__WCP__Implementation__Rtl__GetSystemSid____5____lambda_1___operator__
0x1400279fb  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSid____5____dynamic_atexit_destructor_for__g_SystemSid__; void (__cdecl *)()
0x140027a02  call    atexit
0x140027a07  lea     rcx, dword_14005078C
0x140027a0e  call    _Init_thread_footer
0x140027a13  jmp     loc_140027978
```

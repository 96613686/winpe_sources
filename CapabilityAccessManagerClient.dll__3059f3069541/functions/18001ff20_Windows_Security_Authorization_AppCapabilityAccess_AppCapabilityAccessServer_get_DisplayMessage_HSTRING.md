# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::get_DisplayMessage(HSTRING__ * *)

- ea: `0x18001ff20`
- end: `0x180020068`
- name: `?get_DisplayMessage@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `328`
- prototype: `int(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003c80`
- `0x18000aa04`
- `0x18001b5ac`
- `0x18001e4a0`
- `0x18001ff20`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ff59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ff59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ffdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ffdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001ffea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001ffea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ffc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ffc3`

## string_xrefs

- `0x18002002e`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x180020041`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x180020055`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::get_DisplayMessage(
        RTL_SRWLOCK *this,
        HSTRING *a2)
{
  PVOID Ptr; // rcx
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  HRESULT v8; // eax
  int v9[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)0x80004003LL,
        v9[0]);
    AcquireSRWLockExclusive(this + 15);
    *(_QWORD *)v9 = this + 15;
    if ( !LOBYTE(this[27].Ptr) )
      Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(this - 2);
    if ( this[12].Ptr && (Ptr = this[13].Ptr) != 0 )
    {
      v5 = (*(__int64 (__fastcall **)(PVOID, HSTRING *))(*(_QWORD *)Ptr + 64LL))(Ptr, a2);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
          (const char *)(unsigned int)v5,
          v9[0]);
    }
    else
    {
      if ( WindowsCreateStringReference(&sourceString, 0, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v8 = WindowsDuplicateString(string, a2);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
          (const char *)(unsigned int)v8,
          v9[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3F,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001ff20  mov     [rsp+arg_10], rbx
0x18001ff25  mov     [rsp+arg_18], rsi
0x18001ff2a  push    rdi
0x18001ff2b  sub     rsp, 50h
0x18001ff2f  mov     rax, cs:__security_cookie
0x18001ff36  xor     rax, rsp
0x18001ff39  mov     [rsp+58h+var_10], rax
0x18001ff3e  mov     rsi, rdx
0x18001ff41  mov     rdi, rcx
0x18001ff44  mov     rcx, [rsp+58h]; this
0x18001ff49  test    rdx, rdx
0x18001ff4c  jz      loc_180020028
0x18001ff52  lea     rbx, [rdi+78h]
0x18001ff56  mov     rcx, rbx; SRWLock
0x18001ff59  call    cs:__imp_AcquireSRWLockExclusive
0x18001ff5f  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18001ff64  lea     rcx, [rdi-10h]; this
0x18001ff68  cmp     byte ptr [rcx+0E8h], 0
0x18001ff6f  jnz     short loc_18001FF76
0x18001ff71  call    ?InitializeUsage@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(void)
0x18001ff76  cmp     qword ptr [rdi+60h], 0
0x18001ff7b  jz      short loc_18001FFB0
0x18001ff7d  mov     rcx, [rdi+68h]
0x18001ff81  test    rcx, rcx
0x18001ff84  jz      short loc_18001FFB0
0x18001ff86  mov     rax, [rcx]
0x18001ff89  mov     rdx, rsi
0x18001ff8c  mov     rax, [rax+40h]
0x18001ff90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff95  mov     rcx, [rsp+58h]; this
0x18001ff9a  test    eax, eax
0x18001ff9c  js      loc_18002003E
0x18001ffa2  lea     rcx, [rsp+58h+var_38]
0x18001ffa7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ffac  xor     eax, eax
0x18001ffae  jmp     short loc_18002000B
0x18001ffb0  lea     r9, [rsp+58h+string]; string
0x18001ffb5  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18001ffba  xor     edx, edx; length
0x18001ffbc  lea     rcx, sourceString; sourceString
0x18001ffc3  call    cs:__imp_WindowsCreateStringReference
0x18001ffc9  test    eax, eax
0x18001ffcb  jns     short loc_18001FFE2
0x18001ffcd  xor     r9d, r9d; lpArguments
0x18001ffd0  xor     r8d, r8d; nNumberOfArguments
0x18001ffd3  lea     edx, [r9+1]; dwExceptionFlags
0x18001ffd7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001ffdc  call    cs:__imp_RaiseException
0x18001ffe2  mov     rdx, rsi; newString
0x18001ffe5  mov     rcx, [rsp+58h+string]; string
0x18001ffea  call    cs:__imp_WindowsDuplicateString
0x18001fff0  mov     rcx, [rsp+58h]; this
0x18001fff5  test    eax, eax
0x18001fff7  js      short loc_180020052
0x18001fff9  lea     rcx, [rsp+58h+var_38]
0x18001fffe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020003  xor     eax, eax
0x180020005  jmp     short loc_18002000B
0x180020007  mov     eax, [rsp+58h+var_38]
0x18002000b  mov     rcx, [rsp+58h+var_10]
0x180020010  xor     rcx, rsp; StackCookie
0x180020013  call    __security_check_cookie
0x180020018  mov     rbx, [rsp+58h+arg_10]
0x18002001d  mov     rsi, [rsp+58h+arg_18]
0x180020022  add     rsp, 50h
0x180020026  pop     rdi
0x180020027  retn
0x180020028  mov     r9d, 80004003h; char *
0x18002002e  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180020035  lea     edx, [rsi+2Ch]; void *
0x180020038  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002003e  mov     r9d, eax; char *
0x180020041  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180020048  mov     edx, 3Bh ; ';'; void *
0x18002004d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020052  mov     r9d, eax; char *
0x180020055  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18002005c  mov     edx, 37h ; '7'; void *
0x180020061  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

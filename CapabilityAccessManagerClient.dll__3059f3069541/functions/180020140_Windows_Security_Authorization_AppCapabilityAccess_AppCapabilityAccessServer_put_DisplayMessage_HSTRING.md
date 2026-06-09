# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::put_DisplayMessage(HSTRING__ *)

- ea: `0x180020140`
- end: `0x180020205`
- name: `?put_DisplayMessage@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `197`
- prototype: `int(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000aa04`
- `0x18001b5ac`
- `0x18001e4a0`
- `0x180020140`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002015c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002015c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800201a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800201a9`

## string_xrefs

- `0x1800201f2`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::put_DisplayMessage(
        RTL_SRWLOCK *this,
        HSTRING a2)
{
  RTL_SRWLOCK *v4; // rbx
  PVOID Ptr; // rcx
  int v6; // eax
  bool v7; // al
  const char *v8; // r9
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp+8h] BYREF

  v4 = this + 15;
  AcquireSRWLockExclusive(this + 15);
  try
  {
    v12 = v4;
    if ( !LOBYTE(this[27].Ptr) )
      Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(this - 2);
    if ( this[12].Ptr && (Ptr = this[13].Ptr) != 0 )
    {
      v6 = (*(__int64 (__fastcall **)(PVOID, HSTRING))(*(_QWORD *)Ptr + 72LL))(Ptr, a2);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
          (const char *)(unsigned int)v6,
          v10);
      v7 = a2 && WindowsGetStringLen(a2);
      BYTE1(this[27].Ptr) = v7;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
      result = 0;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x60,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180020140  mov     [rsp+arg_8], rbx
0x180020145  mov     [rsp+arg_10], rsi
0x18002014a  push    rdi; int
0x18002014b  sub     rsp, 20h
0x18002014f  mov     rsi, rdx
0x180020152  mov     rdi, rcx
0x180020155  lea     rbx, [rcx+78h]
0x180020159  mov     rcx, rbx; SRWLock
0x18002015c  call    cs:__imp_AcquireSRWLockExclusive
0x180020162  mov     [rsp+28h+arg_0], rbx
0x180020167  lea     rcx, [rdi-10h]; this
0x18002016b  cmp     byte ptr [rcx+0E8h], 0
0x180020172  jnz     short loc_180020179
0x180020174  call    ?InitializeUsage@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::InitializeUsage(void)
0x180020179  cmp     qword ptr [rdi+60h], 0
0x18002017e  jz      short loc_1800201CD
0x180020180  mov     rcx, [rdi+68h]
0x180020184  test    rcx, rcx
0x180020187  jz      short loc_1800201CD
0x180020189  mov     rax, [rcx]
0x18002018c  mov     rdx, rsi
0x18002018f  mov     rax, [rax+48h]
0x180020193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020198  mov     rcx, [rsp+28h]; this
0x18002019d  test    eax, eax
0x18002019f  js      short loc_1800201EF
0x1800201a1  test    rsi, rsi
0x1800201a4  jz      short loc_1800201B7
0x1800201a6  mov     rcx, rsi; string
0x1800201a9  call    cs:__imp_WindowsGetStringLen
0x1800201af  test    eax, eax
0x1800201b1  jz      short loc_1800201B7
0x1800201b3  mov     al, 1
0x1800201b5  jmp     short loc_1800201B9
0x1800201b7  xor     al, al
0x1800201b9  mov     [rdi+0D9h], al
0x1800201bf  lea     rcx, [rsp+28h+arg_0]
0x1800201c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800201c9  xor     eax, eax
0x1800201cb  jmp     short loc_1800201DF
0x1800201cd  lea     rcx, [rsp+28h+arg_0]
0x1800201d2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800201d7  xor     eax, eax
0x1800201d9  jmp     short loc_1800201DF
0x1800201db  mov     eax, dword ptr [rsp+28h+arg_0]
0x1800201df  mov     rbx, [rsp+28h+arg_8]
0x1800201e4  mov     rsi, [rsp+28h+arg_10]
0x1800201e9  add     rsp, 20h
0x1800201ed  pop     rdi
0x1800201ee  retn
0x1800201ef  mov     r9d, eax; char *
0x1800201f2  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x1800201f9  mov     edx, 53h ; 'S'; void *
0x1800201fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

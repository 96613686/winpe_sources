# RPCAccessCheck

- ea: `0x1800b5d70`
- end: `0x1800b606f`
- name: `RPCAccessCheck`
- size: `767`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x180020fcc`
- `0x18002392c`
- `0x18003f4a0`
- `0x1800464d0`
- `0x18006874c`
- `0x18006ca84`
- `0x180071848`
- `0x180074160`
- `0x1800753c0`
- `0x1800b52c4`
- `0x1800b5d70`
- `0x1800b6448`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b5e8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b5e8e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b5e51`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b5e51`

## string_xrefs

- `0x1800b6028`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b6040`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b605a`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RPCAccessCheck(__int64 a1, __int64 a2, __int64 a3, DWORD a4, int a5, int *a6)
{
  PVOID *v9; // rcx
  char *v10; // rbx
  std::_Ref_count_base **v11; // rax
  char v12; // bl
  unsigned int v13; // eax
  __int64 v14; // rax
  int v15; // ebx
  int v16; // eax
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-C8h]
  void *TokenHandle; // [rsp+38h] [rbp-B0h] BYREF
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v21; // [rsp+40h] [rbp-A8h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-A0h]
  char *v23; // [rsp+50h] [rbp-98h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+58h] [rbp-90h] BYREF
  __m128i si128; // [rsp+68h] [rbp-80h]
  _BYTE v26[32]; // [rsp+78h] [rbp-70h] BYREF
  int v27[8]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ba398d49f73833a47629aaaf6d810685_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)0x80070057LL,
        v19);
    if ( !a6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)0x80004003LL,
        v19);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
        (const char *)0x80070057LL,
        v19);
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_dSS((TRACEHANDLE)v9[2], a2, a3);
    v10 = (char *)OpenProcess(0x1000u, 0, a4);
    v23 = v10;
    TokenHandle = 0;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &TokenHandle,
            0),
          OpenProcessToken(v10, 0xEu, &TokenHandle)) )
    {
      std::wstring::wstring(v27, a2);
      if ( a3 )
      {
        LODWORD(v11) = std::wstring::wstring(v26, a3);
        v12 = 1;
      }
      else
      {
        *(_OWORD *)v24 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v24[0]) = 0;
        v11 = v24;
        v12 = 2;
      }
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithProcessId(
        (int)&v21,
        (int)v11,
        (int)v27,
        a4,
        0,
        1);
      if ( (v12 & 2) != 0 )
      {
        v12 &= ~2u;
        std::wstring::_Tidy_deallocate(v24);
      }
      if ( (v12 & 1) != 0 )
        std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(v27);
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressUserConsentPrompt(v21, a5 != 0);
      v13 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck((__int64)v21);
      *a6 = CapabilityAccessStatusToRPC(v13);
    }
    else
    {
      v14 = std::wstring::wstring(v26, a2);
      Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Create((__int64)&v21, v14);
      std::wstring::_Tidy_deallocate(v26);
      v15 = *(_DWORD *)(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetSystemGlobalConsent(
                                     v21,
                                     v24)
                      + 192LL);
      if ( v24[1] )
        std::_Ref_count_base::_Decref(v24[1]);
      v16 = 3;
      if ( v15 != 1 )
        v16 = 1;
      *a6 = v16;
    }
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8F,
                           (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800b5d70  mov     [rsp+arg_0], rbx
0x1800b5d75  push    rsi
0x1800b5d76  push    rdi
0x1800b5d77  push    r12
0x1800b5d79  push    r14
0x1800b5d7b  push    r15
0x1800b5d7d  sub     rsp, 0C0h
0x1800b5d84  mov     rax, cs:__security_cookie
0x1800b5d8b  xor     rax, rsp
0x1800b5d8e  mov     [rsp+0E8h+var_30], rax
0x1800b5d96  mov     r15d, r9d
0x1800b5d99  mov     r14, r8
0x1800b5d9c  mov     rsi, rdx
0x1800b5d9f  mov     r12, [rsp+0E8h+arg_28]
0x1800b5da7  mov     [rsp+0E8h+var_B8], 0
0x1800b5daf  lea     rbx, WPP_GLOBAL_Control
0x1800b5db6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5dbd  mov     edi, 1
0x1800b5dc2  cmp     rcx, rbx
0x1800b5dc5  jz      short loc_1800B5DED
0x1800b5dc7  test    [rcx+1Ch], dil
0x1800b5dcb  jz      short loc_1800B5DED
0x1800b5dcd  cmp     byte ptr [rcx+19h], 5
0x1800b5dd1  jb      short loc_1800B5DED
0x1800b5dd3  lea     edx, [rdi+0Dh]
0x1800b5dd6  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b5ddd  mov     rcx, [rcx+10h]
0x1800b5de1  call    WPP_SF_
0x1800b5de6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ded  mov     rax, [rsp+0E8h]
0x1800b5df5  test    rsi, rsi
0x1800b5df8  jz      loc_1800B6022
0x1800b5dfe  mov     rax, [rsp+0E8h]
0x1800b5e06  test    r12, r12
0x1800b5e09  jz      loc_1800B603A
0x1800b5e0f  mov     rax, [rsp+0E8h]
0x1800b5e17  test    r15d, r15d
0x1800b5e1a  jz      loc_1800B6054
0x1800b5e20  cmp     rcx, rbx
0x1800b5e23  jz      short loc_1800B5E47
0x1800b5e25  test    [rcx+1Ch], dil
0x1800b5e29  jz      short loc_1800B5E47
0x1800b5e2b  cmp     byte ptr [rcx+19h], 4
0x1800b5e2f  jb      short loc_1800B5E47
0x1800b5e31  mov     qword ptr [rsp+0E8h+var_C0], r14; __int64
0x1800b5e36  mov     [rsp+0E8h+var_C8], rsi; __int64
0x1800b5e3b  mov     r9d, r15d
0x1800b5e3e  mov     rcx, [rcx+10h]; LoggerHandle
0x1800b5e42  call    WPP_SF_dSS
0x1800b5e47  mov     r8d, r15d; dwProcessId
0x1800b5e4a  xor     edx, edx; bInheritHandle
0x1800b5e4c  mov     ecx, 1000h; dwDesiredAccess
0x1800b5e51  call    cs:__imp_OpenProcess
0x1800b5e57  mov     rbx, rax
0x1800b5e5a  mov     [rsp+0E8h+var_98], rax
0x1800b5e5f  mov     [rsp+0E8h+TokenHandle], 0
0x1800b5e68  dec     rax
0x1800b5e6b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b5e6f  ja      loc_1800B5F71
0x1800b5e75  xor     edx, edx
0x1800b5e77  lea     rcx, [rsp+0E8h+TokenHandle]
0x1800b5e7c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b5e81  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800b5e86  mov     edx, 0Eh; DesiredAccess
0x1800b5e8b  mov     rcx, rbx; ProcessHandle
0x1800b5e8e  call    cs:__imp_OpenProcessToken
0x1800b5e94  test    eax, eax
0x1800b5e96  jz      loc_1800B5F71
0x1800b5e9c  mov     rdx, rsi
0x1800b5e9f  lea     rcx, [rsp+0E8h+var_50]
0x1800b5ea7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b5eac  nop
0x1800b5ead  test    r14, r14
0x1800b5eb0  jz      short loc_1800B5EC4
0x1800b5eb2  mov     rdx, r14
0x1800b5eb5  lea     rcx, [rsp+0E8h+var_70]
0x1800b5eba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b5ebf  nop
0x1800b5ec0  mov     ebx, edi
0x1800b5ec2  jmp     short loc_1800B5EEB
0x1800b5ec4  xorps   xmm0, xmm0
0x1800b5ec7  movups  xmmword ptr [rsp+0E8h+var_90], xmm0
0x1800b5ecc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800b5ed4  movdqu  [rsp+0E8h+var_80], xmm1
0x1800b5eda  xor     eax, eax
0x1800b5edc  mov     word ptr [rsp+0E8h+var_90], ax
0x1800b5ee1  lea     rax, [rsp+0E8h+var_90]
0x1800b5ee6  mov     ebx, 2
0x1800b5eeb  mov     [rsp+0E8h+var_B8], ebx
0x1800b5eef  mov     [rsp+0E8h+var_C0], dil; char
0x1800b5ef4  mov     dword ptr [rsp+0E8h+var_C8], 0; int
0x1800b5efc  mov     r9d, r15d; dwProcessId
0x1800b5eff  lea     r8, [rsp+0E8h+var_50]; int
0x1800b5f07  mov     rdx, rax; int
0x1800b5f0a  lea     rcx, [rsp+0E8h+var_A8]; int
0x1800b5f0f  call    ?CreateWithProcessId@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0KK_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithProcessId(std::wstring const &,std::wstring const &,ulong,ulong,bool)
0x1800b5f14  nop
0x1800b5f15  test    bl, 2
0x1800b5f18  jz      short loc_1800B5F28
0x1800b5f1a  and     ebx, 0FFFFFFFDh
0x1800b5f1d  lea     rcx, [rsp+0E8h+var_90]
0x1800b5f22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5f27  nop
0x1800b5f28  test    dil, bl
0x1800b5f2b  jz      short loc_1800B5F38
0x1800b5f2d  lea     rcx, [rsp+0E8h+var_70]
0x1800b5f32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5f37  nop
0x1800b5f38  lea     rcx, [rsp+0E8h+var_50]
0x1800b5f40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5f45  cmp     [rsp+0E8h+arg_20], 0
0x1800b5f4d  setnz   dl; bool
0x1800b5f50  mov     rcx, [rsp+0E8h+var_A8]; this
0x1800b5f55  call    ?put_SuppressUserConsentPrompt@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAX_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressUserConsentPrompt(bool)
0x1800b5f5a  mov     rcx, [rsp+0E8h+var_A8]
0x1800b5f5f  call    ?AccessCheck@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4AccessCheckStatus@2345@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck(void)
0x1800b5f64  mov     ecx, eax
0x1800b5f66  call    ?CapabilityAccessStatusToRPC@@YA?AW4RPCCapabilityAccessStatus@@W4AccessCheckStatus@Private@CapabilityAccess@Internal@Windows@@@Z; CapabilityAccessStatusToRPC(Windows::Internal::CapabilityAccess::Private::AccessCheckStatus)
0x1800b5f6b  mov     [r12], eax
0x1800b5f6f  jmp     short loc_1800B5FCD
0x1800b5f71  mov     rdx, rsi
0x1800b5f74  lea     rcx, [rsp+0E8h+var_70]
0x1800b5f79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b5f7e  nop
0x1800b5f7f  mov     rdx, rax
0x1800b5f82  lea     rcx, [rsp+0E8h+var_A8]
0x1800b5f87  call    ?Create@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::Create(std::wstring const &)
0x1800b5f8c  nop
0x1800b5f8d  lea     rcx, [rsp+0E8h+var_70]
0x1800b5f92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5f97  lea     rdx, [rsp+0E8h+var_90]
0x1800b5f9c  mov     rcx, [rsp+0E8h+var_A8]
0x1800b5fa1  call    ?GetSystemGlobalConsent@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityConsent@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetSystemGlobalConsent(void)
0x1800b5fa6  mov     rax, [rax]
0x1800b5fa9  mov     ebx, [rax+0C0h]
0x1800b5faf  mov     rcx, [rsp+0E8h+var_90+8]; this
0x1800b5fb4  test    rcx, rcx
0x1800b5fb7  jz      short loc_1800B5FBF
0x1800b5fb9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b5fbe  nop
0x1800b5fbf  mov     eax, 3
0x1800b5fc4  cmp     ebx, edi
0x1800b5fc6  cmovnz  eax, edi
0x1800b5fc9  mov     [r12], eax
0x1800b5fcd  mov     rcx, [rsp+0E8h+var_A0]; this
0x1800b5fd2  test    rcx, rcx
0x1800b5fd5  jz      short loc_1800B5FDD
0x1800b5fd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b5fdc  nop
0x1800b5fdd  lea     rcx, [rsp+0E8h+TokenHandle]
0x1800b5fe2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b5fe7  nop
0x1800b5fe8  lea     rcx, [rsp+0E8h+var_98]
0x1800b5fed  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b5ff2  xor     eax, eax
0x1800b5ff4  jmp     short loc_1800B5FFA
0x1800b5ff6  mov     eax, [rsp+0E8h+var_B8]
0x1800b5ffa  mov     rcx, [rsp+0E8h+var_30]
0x1800b6002  xor     rcx, rsp; StackCookie
0x1800b6005  call    __security_check_cookie
0x1800b600a  mov     rbx, [rsp+0E8h+arg_0]
0x1800b6012  add     rsp, 0C0h
0x1800b6019  pop     r15
0x1800b601b  pop     r14
0x1800b601d  pop     r12
0x1800b601f  pop     rdi
0x1800b6020  pop     rsi
0x1800b6021  retn
0x1800b6022  mov     r9d, 80070057h; char *
0x1800b6028  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b602f  lea     edx, [rsi+6Ch]; void *
0x1800b6032  mov     rcx, rax; this
0x1800b6035  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b603a  mov     r9d, 80004003h; char *
0x1800b6040  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b6047  lea     edx, [r12+6Dh]; void *
0x1800b604c  mov     rcx, rax; this
0x1800b604f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b6054  mov     r9d, 80070057h; char *
0x1800b605a  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b6061  lea     edx, [r15+6Eh]; void *
0x1800b6065  mov     rcx, rax; this
0x1800b6068  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

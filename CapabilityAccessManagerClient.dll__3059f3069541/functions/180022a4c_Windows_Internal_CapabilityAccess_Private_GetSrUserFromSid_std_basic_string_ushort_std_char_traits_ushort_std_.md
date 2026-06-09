# Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180022a4c`
- end: `0x180022b7f`
- name: `?GetSrUserFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `307`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800225a0`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x1800204d4`
- `0x18002060c`
- `0x180022a4c`
- `0x180023690`
- `0x180039010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022b54`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022b54`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180022a89`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180022a89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(_QWORD *a1, __int64 a2)
{
  const unsigned __int16 *v4; // rdx
  const char *v5; // r9
  __int64 *v6; // rax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD *); // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  const unsigned __int16 *v13; // rax
  int v14; // eax
  int v16; // [rsp+20h] [rbp-40h]
  _QWORD v17[2]; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string[4]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v17[1] = a1;
  if ( !ImpersonateSelf(SecurityImpersonation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  BYTE1(v16) = 1;
  v17[0] = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[38])v4);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
         *v6,
         (__int64)v17);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v7,
      v16);
  *a1 = 0;
  v8 = v17[0];
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v17[0] + 80LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
  v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v10, v11, v12);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v13);
  v14 = v9(v8, string[0], a1);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v14,
      v16);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v17);
  RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x180022a4c  mov     [rsp-18h+arg_10], rbx
0x180022a51  mov     [rsp-18h+arg_18], rsi
0x180022a56  push    rbp
0x180022a57  push    rdi
0x180022a58  push    r14
0x180022a5a  mov     rbp, rsp
0x180022a5d  sub     rsp, 60h
0x180022a61  mov     rax, cs:__security_cookie
0x180022a68  xor     rax, rsp
0x180022a6b  mov     [rbp+var_8], rax
0x180022a6f  mov     r14, rdx
0x180022a72  mov     rsi, rcx
0x180022a75  mov     [rbp+var_30], rcx
0x180022a79  mov     [rbp+var_3C], 0
0x180022a80  mov     rbx, [rbp+18h]
0x180022a84  mov     ecx, 2; ImpersonationLevel
0x180022a89  call    cs:__imp_ImpersonateSelf
0x180022a8f  test    eax, eax
0x180022a91  jnz     short loc_180022AA8
0x180022a93  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022a9a  mov     edx, 2E5h; void *
0x180022a9f  mov     rcx, rbx; this
0x180022aa2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022aa8  mov     [rbp+var_3F], 1
0x180022aac  mov     [rbp+var_38], 0
0x180022ab4  lea     rcx, [rbp+string]; string
0x180022ab8  call    ??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[38])
0x180022abd  lea     rdx, [rbp+var_38]
0x180022ac1  mov     rcx, [rax]
0x180022ac4  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x180022ac9  mov     rcx, [rbp+18h]; this
0x180022acd  test    eax, eax
0x180022acf  jns     short loc_180022AE6
0x180022ad1  mov     r9d, eax; char *
0x180022ad4  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022adb  mov     edx, 2EEh; void *
0x180022ae0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022ae6  mov     qword ptr [rsi], 0
0x180022aed  mov     [rbp+var_3C], 1
0x180022af4  mov     rdi, [rbp+var_38]
0x180022af8  mov     rax, [rdi]
0x180022afb  mov     rbx, [rax+50h]
0x180022aff  mov     rcx, rsi
0x180022b02  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022b07  mov     rcx, r14
0x180022b0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022b0f  mov     rdx, rax; unsigned __int16 *
0x180022b12  lea     rcx, [rbp+string]; this
0x180022b16  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180022b1b  mov     r8, rsi
0x180022b1e  mov     rdx, [rbp+string]
0x180022b22  mov     rcx, rdi
0x180022b25  mov     rax, rbx
0x180022b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b2d  mov     rcx, [rbp+18h]; this
0x180022b31  test    eax, eax
0x180022b33  jns     short loc_180022B4A
0x180022b35  mov     r9d, eax; char *
0x180022b38  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022b3f  mov     edx, 2F3h; void *
0x180022b44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022b4a  lea     rcx, [rbp+var_38]
0x180022b4e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022b53  nop
0x180022b54  call    cs:__imp_RevertToSelf
0x180022b5a  mov     rax, rsi
0x180022b5d  mov     rcx, [rbp+var_8]
0x180022b61  xor     rcx, rsp; StackCookie
0x180022b64  call    __security_check_cookie
0x180022b69  lea     r11, [rsp+60h+var_s0]
0x180022b6e  mov     rbx, [r11+30h]
0x180022b72  mov     rsi, [r11+38h]
0x180022b76  mov     rsp, r11
0x180022b79  pop     r14
0x180022b7b  pop     rdi
0x180022b7c  pop     rbp
0x180022b7d  retn
```

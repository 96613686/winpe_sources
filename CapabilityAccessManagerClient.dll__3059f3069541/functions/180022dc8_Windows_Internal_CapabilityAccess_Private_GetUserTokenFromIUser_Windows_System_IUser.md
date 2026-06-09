# Windows::Internal::CapabilityAccess::Private::GetUserTokenFromIUser(Windows::System::IUser *)

- ea: `0x180022dc8`
- end: `0x180022f32`
- name: `?GetUserTokenFromIUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@4@@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180022cec`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x180011dac`
- `0x1800120f8`
- `0x1800123c8`
- `0x18001b5ac`
- `0x180022dc8`
- `0x180039010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180022eda`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180022eda`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetUserTokenFromIUser(
        _QWORD *a1,
        const unsigned __int16 *a2)
{
  __int64 *v4; // rax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int UserToken; // eax
  __int64 v10; // [rsp+28h] [rbp-48h] BYREF
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-40h] BYREF
  _QWORD v12[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v12[1] = a1;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x80070057LL,
      0);
  v12[0] = 0;
  v11 = 0;
  v10 = 0;
  *a1 = 0;
  v4 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[36])a2);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
         *v4,
         (__int64)&v11);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v5,
      1);
  v6 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
         &v11,
         (__int64)&v10);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x549,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v6,
      1);
  v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)v10 + 136LL))(v10, a2, v12);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v7,
      1);
  UserToken = UMgrQueryUserToken(v12[0], a1);
  if ( UserToken < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)UserToken,
      1);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  return a1;
}

```

## disassembly

```asm
0x180022dc8  mov     [rsp-8+arg_10], rbx
0x180022dcd  mov     [rsp-8+arg_18], rdi
0x180022dd2  push    rbp
0x180022dd3  mov     rbp, rsp
0x180022dd6  sub     rsp, 70h
0x180022dda  mov     rax, cs:__security_cookie
0x180022de1  xor     rax, rsp
0x180022de4  mov     [rbp+var_8], rax
0x180022de8  mov     rdi, rdx
0x180022deb  mov     rbx, rcx
0x180022dee  mov     [rbp+var_30], rcx
0x180022df2  mov     [rbp+var_50], 0
0x180022df9  mov     rcx, [rbp+8]; this
0x180022dfd  test    rdx, rdx
0x180022e00  jnz     short loc_180022E1A
0x180022e02  mov     r9d, 80070057h; char *
0x180022e08  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022e0f  mov     edx, 53Fh; void *
0x180022e14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022e1a  mov     [rbp+var_38], 0
0x180022e22  mov     [rbp+var_40], 0
0x180022e2a  mov     [rbp+var_48], 0
0x180022e32  mov     qword ptr [rbx], 0
0x180022e39  mov     [rbp+var_50], 1
0x180022e40  lea     rcx, [rbp+string]; string
0x180022e44  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x180022e49  lea     rdx, [rbp+var_40]
0x180022e4d  mov     rcx, [rax]
0x180022e50  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x180022e55  mov     rcx, [rbp+8]; this
0x180022e59  test    eax, eax
0x180022e5b  jns     short loc_180022E72
0x180022e5d  mov     r9d, eax; char *
0x180022e60  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022e67  mov     edx, 548h; void *
0x180022e6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022e72  lea     rdx, [rbp+var_48]
0x180022e76  lea     rcx, [rbp+var_40]
0x180022e7a  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180022e7f  mov     rcx, [rbp+8]; this
0x180022e83  test    eax, eax
0x180022e85  jns     short loc_180022E9C
0x180022e87  mov     r9d, eax; char *
0x180022e8a  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022e91  mov     edx, 549h; void *
0x180022e96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022e9c  mov     rcx, [rbp+var_48]
0x180022ea0  mov     rax, [rcx]
0x180022ea3  lea     r8, [rbp+var_38]
0x180022ea7  mov     rdx, rdi
0x180022eaa  mov     rax, [rax+88h]
0x180022eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eb6  mov     rcx, [rbp+8]; this
0x180022eba  test    eax, eax
0x180022ebc  jns     short loc_180022ED3
0x180022ebe  mov     r9d, eax; char *
0x180022ec1  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022ec8  mov     edx, 54Ah; void *
0x180022ecd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022ed3  mov     rdx, rbx
0x180022ed6  mov     rcx, [rbp+var_38]
0x180022eda  call    cs:__imp_UMgrQueryUserToken
0x180022ee0  mov     rcx, [rbp+8]; this
0x180022ee4  test    eax, eax
0x180022ee6  jns     short loc_180022EFD
0x180022ee8  mov     r9d, eax; char *
0x180022eeb  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022ef2  mov     edx, 54Bh; void *
0x180022ef7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022efd  lea     rcx, [rbp+var_48]
0x180022f01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022f06  nop
0x180022f07  lea     rcx, [rbp+var_40]
0x180022f0b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022f10  mov     rax, rbx
0x180022f13  mov     rcx, [rbp+var_8]
0x180022f17  xor     rcx, rsp; StackCookie
0x180022f1a  call    __security_check_cookie
0x180022f1f  lea     r11, [rsp+70h+var_s0]
0x180022f24  mov     rbx, [r11+20h]
0x180022f28  mov     rdi, [r11+28h]
0x180022f2c  mov     rsp, r11
0x180022f2f  pop     rbp
0x180022f30  retn
```

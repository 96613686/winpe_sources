# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(HSTRING__ *,Windows::System::IUser * *)

- ea: `0x180016a38`
- end: `0x180016ba2`
- name: `?GetIUserFromSidString@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@SAJPEAUHSTRING__@@PEAPEAUIUser@System@5@@Z`
- size: `362`
- prototype: `__int64 __fastcall(HSTRING string, struct Windows::System::IUser **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f014`
- `0x18001f424`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x180011dac`
- `0x1800120f8`
- `0x1800123c8`
- `0x1800142d4`
- `0x180016a38`
- `0x18001b5ac`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016af3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x180016b01`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x180016b01`

## string_xrefs

- `0x180016ab1`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x180016add`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x180016b13`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x180016b4c`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(
        HSTRING string,
        struct Windows::System::IUser **a2)
{
  __int64 *v5; // rax
  int v6; // eax
  int v7; // eax
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  int v10; // eax
  int v11[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-50h] BYREF
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+38h] [rbp-40h] BYREF
  HSTRING stringa; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a2 = 0;
  if ( !string )
    return 0;
  v13 = 0;
  v12 = 0;
  *(_QWORD *)v11 = 0;
  v14 = 0;
  v5 = (__int64 *)Windows::Internal::StringReference::StringReference(&stringa, (const unsigned __int16 (*)[36])a2);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
         *v5,
         (__int64)&v12);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v6,
      v11[0]);
  v7 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
         &v12,
         (__int64)v11);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v7,
      v11[0]);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v9 = UMgrQueryUserContextFromSid(StringRawBuffer, &v13);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v9,
      v11[0]);
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct Windows::System::IUser **))(**(_QWORD **)v11 + 160LL))(
          *(_QWORD *)v11,
          v13,
          a2);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v10,
      v11[0]);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v11);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
  return 0;
}

```

## disassembly

```asm
0x180016a38  mov     [rsp+arg_0], rbx
0x180016a3d  push    rdi
0x180016a3e  sub     rsp, 70h
0x180016a42  mov     rax, cs:__security_cookie
0x180016a49  xor     rax, rsp
0x180016a4c  mov     [rsp+78h+var_18], rax
0x180016a51  mov     rdi, rdx
0x180016a54  mov     rbx, rcx
0x180016a57  mov     qword ptr [rdx], 0
0x180016a5e  test    rcx, rcx
0x180016a61  jnz     short loc_180016A6A
0x180016a63  xor     eax, eax
0x180016a65  jmp     loc_180016B86
0x180016a6a  mov     [rsp+78h+var_48], 0
0x180016a73  mov     [rsp+78h+var_50], 0
0x180016a7c  mov     qword ptr [rsp+78h+var_58], 0; int
0x180016a85  mov     [rsp+78h+var_40], 0
0x180016a8e  lea     rcx, [rsp+78h+string]; string
0x180016a93  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x180016a98  lea     rdx, [rsp+78h+var_50]
0x180016a9d  mov     rcx, [rax]
0x180016aa0  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x180016aa5  mov     rcx, [rsp+78h]; this
0x180016aaa  test    eax, eax
0x180016aac  jns     short loc_180016AC2
0x180016aae  mov     r9d, eax; char *
0x180016ab1  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180016ab8  mov     edx, 0CFh; void *
0x180016abd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016ac2  lea     rdx, [rsp+78h+var_58]
0x180016ac7  lea     rcx, [rsp+78h+var_50]
0x180016acc  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180016ad1  mov     rcx, [rsp+78h]; this
0x180016ad6  test    eax, eax
0x180016ad8  jns     short loc_180016AEE
0x180016ada  mov     r9d, eax; char *
0x180016add  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180016ae4  mov     edx, 0D0h; void *
0x180016ae9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016aee  xor     edx, edx; length
0x180016af0  mov     rcx, rbx; string
0x180016af3  call    cs:__imp_WindowsGetStringRawBuffer
0x180016af9  lea     rdx, [rsp+78h+var_48]
0x180016afe  mov     rcx, rax
0x180016b01  call    cs:__imp_UMgrQueryUserContextFromSid
0x180016b07  mov     rcx, [rsp+78h]; this
0x180016b0c  test    eax, eax
0x180016b0e  jns     short loc_180016B24
0x180016b10  mov     r9d, eax; char *
0x180016b13  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180016b1a  mov     edx, 0D1h; void *
0x180016b1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016b24  mov     rcx, qword ptr [rsp+78h+var_58]
0x180016b29  mov     rax, [rcx]
0x180016b2c  mov     r8, rdi
0x180016b2f  mov     rdx, [rsp+78h+var_48]
0x180016b34  mov     rax, [rax+0A0h]
0x180016b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b40  mov     rcx, [rsp+78h]; this
0x180016b45  test    eax, eax
0x180016b47  jns     short loc_180016B5E
0x180016b49  mov     r9d, eax; char *
0x180016b4c  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180016b53  mov     edx, 0D2h; void *
0x180016b58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016b5e  lea     rcx, [rsp+78h+var_40]
0x180016b63  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180016b68  nop
0x180016b69  lea     rcx, [rsp+78h+var_58]
0x180016b6e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016b73  nop
0x180016b74  lea     rcx, [rsp+78h+var_50]
0x180016b79  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016b7e  xor     eax, eax
0x180016b80  jmp     short loc_180016B86
0x180016b82  mov     eax, [rsp+78h+var_58]
0x180016b86  mov     rcx, [rsp+78h+var_18]
0x180016b8b  xor     rcx, rsp; StackCookie
0x180016b8e  call    __security_check_cookie
0x180016b93  mov     rbx, [rsp+78h+arg_0]
0x180016b9b  add     rsp, 70h
0x180016b9f  pop     rdi
0x180016ba0  retn
```

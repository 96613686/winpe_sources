# GetUserTokenHandleForImpersonation(Windows::System::IUser *)

- ea: `0x180036bf4`
- end: `0x180036e00`
- name: `?GetUserTokenHandleForImpersonation@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `524`
- prototype: `HSTRING __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015410`

## callees

- `0x180003a00`
- `0x180004f20`
- `0x180012a98`
- `0x18002d838`
- `0x180034f80`
- `0x180036bf4`
- `0x18003771c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036c46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036c46`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180036d53`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180036d53`

## string_xrefs

- `0x180036da1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180036dbe`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180036dd3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180036deb`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HSTRING __fastcall GetUserTokenHandleForImpersonation(HSTRING a1, __int64 a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rbx
  __int64 v8; // rcx
  int ActivationFactory; // eax
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  int UserToken; // eax
  __int64 v15; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  string[1] = a1;
  v19 = 0;
  string[0] = 0;
  v4 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    goto LABEL_17;
  }
  v7 = string[0];
  v8 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  ActivationFactory = RoGetActivationFactory(v7, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v19);
  v10 = retaddr;
  if ( ActivationFactory < 0 )
LABEL_17:
    wil::details::in1diag3::Throw_Hr(
      v10,
      (void *)0x148,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)ActivationFactory,
      0);
  v20 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v19 + 136LL))(v19, a2, &v20);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)v11,
      0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  if ( !(unsigned __int8)IsUMgrQueryDefaultAccountTokenPresent(retaddr) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)0x8000FFFFLL,
      1);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
    a1,
    &hstringHeader);
  v12 = *(volatile signed __int32 **)&hstringHeader.Reserved.Reserved2[8];
  if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
  {
    if ( _InterlockedExchangeAdd(
           (volatile signed __int32 *)(*(_QWORD *)&hstringHeader.Reserved.Reserved2[8] + 8LL),
           0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(a1);
  UserToken = UMgrQueryUserToken(v20, v13);
  if ( UserToken < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)(unsigned int)UserToken,
      1);
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x180036bf4  mov     [rsp-18h+arg_10], rbx
0x180036bf9  push    rbp
0x180036bfa  push    rsi
0x180036bfb  push    rdi
0x180036bfc  mov     rbp, rsp
0x180036bff  sub     rsp, 70h
0x180036c03  mov     rax, cs:__security_cookie
0x180036c0a  xor     rax, rsp
0x180036c0d  mov     [rbp+var_10], rax
0x180036c11  mov     rsi, rdx
0x180036c14  mov     rdi, rcx
0x180036c17  mov     [rbp+var_28], rcx
0x180036c1b  mov     [rbp+var_50], 0
0x180036c22  mov     [rbp+var_20], 0
0x180036c2a  mov     [rbp+string], 0
0x180036c32  lea     r9, [rbp+string]; string
0x180036c36  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180036c3a  mov     edx, 23h ; '#'; length
0x180036c3f  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180036c46  call    cs:__imp_WindowsCreateStringReference
0x180036c4c  test    eax, eax
0x180036c4e  js      loc_180036DB3
0x180036c54  mov     rbx, [rbp+string]
0x180036c58  mov     rcx, [rbp+var_20]
0x180036c5c  test    rcx, rcx
0x180036c5f  jz      short loc_180036C76
0x180036c61  mov     [rbp+var_20], 0
0x180036c69  mov     rax, [rcx]
0x180036c6c  mov     rax, [rax+10h]
0x180036c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c75  nop
0x180036c76  lea     r8, [rbp+var_20]
0x180036c7a  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180036c81  mov     rcx, rbx
0x180036c84  call    cs:__imp_RoGetActivationFactory
0x180036c8a  mov     rcx, [rbp+18h]
0x180036c8e  test    eax, eax
0x180036c90  js      loc_180036DBB
0x180036c96  mov     [rbp+var_18], 0
0x180036c9e  mov     rcx, [rbp+var_20]
0x180036ca2  mov     rax, [rcx]
0x180036ca5  lea     r8, [rbp+var_18]
0x180036ca9  mov     rdx, rsi
0x180036cac  mov     rax, [rax+88h]
0x180036cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cb8  mov     rcx, [rbp+18h]; this
0x180036cbc  test    eax, eax
0x180036cbe  js      loc_180036DD0
0x180036cc4  xorps   xmm0, xmm0
0x180036cc7  movups  xmmword ptr [rdi], xmm0
0x180036cca  mov     qword ptr [rdi], 0
0x180036cd1  mov     qword ptr [rdi+8], 0
0x180036cd9  mov     [rbp+var_50], 1
0x180036ce0  mov     rbx, [rbp+18h]
0x180036ce4  call    IsUMgrQueryDefaultAccountTokenPresent
0x180036ce9  test    al, al
0x180036ceb  jz      loc_180036DE5
0x180036cf1  xorps   xmm0, xmm0
0x180036cf4  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180036cf9  lea     rdx, [rbp+hstringHeader]
0x180036cfd  mov     rcx, rdi
0x180036d00  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180036d05  mov     rbx, qword ptr [rbp+hstringHeader.Reserved+8]
0x180036d09  test    rbx, rbx
0x180036d0c  jz      short loc_180036D44
0x180036d0e  or      esi, 0FFFFFFFFh
0x180036d11  mov     eax, esi
0x180036d13  lock xadd [rbx+8], eax
0x180036d18  add     eax, esi
0x180036d1a  jnz     short loc_180036D44
0x180036d1c  mov     rax, [rbx]
0x180036d1f  mov     rcx, rbx
0x180036d22  mov     rax, [rax]
0x180036d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d2a  mov     eax, esi
0x180036d2c  lock xadd [rbx+0Ch], eax
0x180036d31  add     eax, esi
0x180036d33  jnz     short loc_180036D44
0x180036d35  mov     rax, [rbx]
0x180036d38  mov     rcx, rbx
0x180036d3b  mov     rax, [rax+8]
0x180036d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d44  mov     rcx, rdi
0x180036d47  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAXXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x180036d4c  mov     rdx, rax
0x180036d4f  mov     rcx, [rbp+var_18]
0x180036d53  call    cs:__imp_UMgrQueryUserToken
0x180036d59  mov     rcx, [rbp+18h]; this
0x180036d5d  test    eax, eax
0x180036d5f  js      short loc_180036D9E
0x180036d61  mov     rcx, [rbp+var_20]
0x180036d65  test    rcx, rcx
0x180036d68  jz      short loc_180036D7F
0x180036d6a  mov     [rbp+var_20], 0
0x180036d72  mov     rdx, [rcx]
0x180036d75  mov     rax, [rdx+10h]
0x180036d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d7e  nop
0x180036d7f  mov     rax, rdi
0x180036d82  mov     rcx, [rbp+var_10]
0x180036d86  xor     rcx, rsp; StackCookie
0x180036d89  call    __security_check_cookie
0x180036d8e  mov     rbx, [rsp+70h+arg_10]
0x180036d96  add     rsp, 70h
0x180036d9a  pop     rdi
0x180036d9b  pop     rsi
0x180036d9c  pop     rbp
0x180036d9d  retn
0x180036d9e  mov     r9d, eax; char *
0x180036da1  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036da8  mov     edx, 14Fh; void *
0x180036dad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036db3  mov     ecx, eax; this
0x180036db5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180036dba  nop
0x180036dbb  mov     r9d, eax; char *
0x180036dbe  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036dc5  mov     edx, 148h; void *
0x180036dca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036dd0  mov     r9d, eax; char *
0x180036dd3  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036dda  mov     edx, 14Bh; void *
0x180036ddf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036de5  mov     r9d, 8000FFFFh; char *
0x180036deb  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036df2  mov     edx, 14Eh; void *
0x180036df7  mov     rcx, rbx; this
0x180036dfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)

- ea: `0x1800b81b0`
- end: `0x1800b83d4`
- name: `?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z`
- size: `548`
- prototype: `bool __fastcall(Windows::Internal::CapabilityAccess::WinRT::CallerValidation *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180098720`
- `0x1800988e0`
- `0x180098aa0`
- `0x180098eb0`
- `0x1800992f0`
- `0x180099730`
- `0x18009b1a0`
- `0x18009d554`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x180039e9c`
- `0x18003f4a0`
- `0x1800464d0`
- `0x1800b805c`
- `0x1800b81b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b8223`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b8223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b8209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b8209`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b8371`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b8386`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b8371`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b8386`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b81d2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b81d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(
        Windows::Internal::CapabilityAccess::WinRT::CallerValidation *this)
{
  char v1; // di
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  char v6; // bl
  char v7; // bl
  char v8; // bl
  char v9; // bl
  char v10; // bl
  char v11; // bl
  void *TokenHandle; // [rsp+20h] [rbp-40h] BYREF
  char v13; // [rsp+29h] [rbp-37h]
  _BYTE v14[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v1 = (char)this;
  v2 = CoImpersonateClient();
  if ( v2 == -2147417833 )
    return 1;
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\callervalidation\\callervalidation.cpp",
      (const char *)(unsigned int)v2,
      (int)TokenHandle);
  v13 = 1;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\callervalidation\\callervalidation.cpp",
      v5);
  if ( (v1 & 4) != 0 )
  {
    std::wstring::wstring(v14, L"O:SYG:SYD:(A;;0x1;;;SY)");
    v6 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle);
    std::wstring::_Tidy_deallocate(v14);
    if ( v6 )
      goto LABEL_15;
  }
  if ( (v1 & 8) != 0 )
  {
    std::wstring::wstring(v14, L"O:SYG:SYD:(A;;0x1;;;BA)");
    v7 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle);
    std::wstring::_Tidy_deallocate(v14);
    if ( v7 )
      goto LABEL_15;
  }
  if ( (v1 & 1) != 0 )
  {
    std::wstring::wstring(
      v14,
      L"O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID Contains \"windows.immersivecontrolpanel_cw5n1h2txyewy\"))");
    v8 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle);
    std::wstring::_Tidy_deallocate(v14);
    if ( v8 )
      goto LABEL_15;
  }
  if ( (v1 & 2) != 0 )
  {
    std::wstring::wstring(
      v14,
      L"O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID Contains \"MicrosoftWindows.CopilotRuntime.Actions_cw5n1h2txyewy\"))");
    v9 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle);
    std::wstring::_Tidy_deallocate(v14);
    if ( v9
      || (std::wstring::wstring(
            v14,
            L"O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID Contains \"MicrosoftWindows.Client.CBS_cw5n1h2txyewy\"))"),
          v10 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle),
          std::wstring::_Tidy_deallocate(v14),
          v10)
      || (std::wstring::wstring(
            v14,
            L"O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID Contains \"MicrosoftWindows.WMSS_cw5n1h2txyewy\"))"),
          v11 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(TokenHandle),
          std::wstring::_Tidy_deallocate(v14),
          v11) )
    {
LABEL_15:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      CoRevertToSelf();
      return 1;
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1800b81b0  mov     [rsp-8+arg_0], rbx
0x1800b81b5  mov     [rsp-8+arg_8], rdi
0x1800b81ba  push    rbp
0x1800b81bb  mov     rbp, rsp
0x1800b81be  sub     rsp, 60h
0x1800b81c2  mov     rax, cs:__security_cookie
0x1800b81c9  xor     rax, rsp
0x1800b81cc  mov     [rbp+var_10], rax
0x1800b81d0  mov     edi, ecx
0x1800b81d2  call    cs:__imp_CoImpersonateClient
0x1800b81d8  cmp     eax, 80010117h
0x1800b81dd  jnz     short loc_1800B81E6
0x1800b81df  mov     al, 1
0x1800b81e1  jmp     loc_1800B838E
0x1800b81e6  mov     rcx, [rbp+8]; this
0x1800b81ea  test    eax, eax
0x1800b81ec  js      loc_1800B83BF
0x1800b81f2  mov     [rbp+var_37], 1
0x1800b81f6  mov     [rbp+TokenHandle], 0
0x1800b81fe  xor     edx, edx
0x1800b8200  lea     rcx, [rbp+TokenHandle]
0x1800b8204  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b8209  call    cs:__imp_GetCurrentThread
0x1800b820f  mov     rbx, [rbp+8]
0x1800b8213  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800b8217  mov     edx, 8; DesiredAccess
0x1800b821c  lea     r8d, [rdx-7]; OpenAsSelf
0x1800b8220  mov     rcx, rax; ThreadHandle
0x1800b8223  call    cs:__imp_OpenThreadToken
0x1800b8229  test    eax, eax
0x1800b822b  jz      loc_1800B83AA
0x1800b8231  test    dil, 4
0x1800b8235  jz      short loc_1800B8268
0x1800b8237  lea     rdx, aOSygSydA0x1Sy_0; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800b823e  lea     rcx, [rbp+var_30]
0x1800b8242  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b8247  nop
0x1800b8248  lea     rdx, [rbp+var_30]
0x1800b824c  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b8250  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b8255  mov     bl, al
0x1800b8257  lea     rcx, [rbp+var_30]
0x1800b825b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b8260  test    bl, bl
0x1800b8262  jnz     loc_1800B8367
0x1800b8268  test    dil, 8
0x1800b826c  jz      short loc_1800B829F
0x1800b826e  lea     rdx, aOSygSydA0x1Ba; "O:SYG:SYD:(A;;0x1;;;BA)"
0x1800b8275  lea     rcx, [rbp+var_30]
0x1800b8279  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b827e  nop
0x1800b827f  lea     rdx, [rbp+var_30]
0x1800b8283  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b8287  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b828c  mov     bl, al
0x1800b828e  lea     rcx, [rbp+var_30]
0x1800b8292  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b8297  test    bl, bl
0x1800b8299  jnz     loc_1800B8367
0x1800b829f  test    dil, 1
0x1800b82a3  jz      short loc_1800B82D6
0x1800b82a5  lea     rdx, aOSygSydXa0x1Iu; "O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID"...
0x1800b82ac  lea     rcx, [rbp+var_30]
0x1800b82b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b82b5  nop
0x1800b82b6  lea     rdx, [rbp+var_30]
0x1800b82ba  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b82be  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b82c3  mov     bl, al
0x1800b82c5  lea     rcx, [rbp+var_30]
0x1800b82c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b82ce  test    bl, bl
0x1800b82d0  jnz     loc_1800B8367
0x1800b82d6  test    dil, 2
0x1800b82da  jz      loc_1800B837C
0x1800b82e0  lea     rdx, aOSygSydXa0x1Iu_0; "O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID"...
0x1800b82e7  lea     rcx, [rbp+var_30]
0x1800b82eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b82f0  nop
0x1800b82f1  lea     rdx, [rbp+var_30]
0x1800b82f5  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b82f9  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b82fe  mov     bl, al
0x1800b8300  lea     rcx, [rbp+var_30]
0x1800b8304  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b8309  test    bl, bl
0x1800b830b  jnz     short loc_1800B8367
0x1800b830d  lea     rdx, aOSygSydXa0x1Iu_1; "O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID"...
0x1800b8314  lea     rcx, [rbp+var_30]
0x1800b8318  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b831d  nop
0x1800b831e  lea     rdx, [rbp+var_30]
0x1800b8322  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b8326  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b832b  mov     bl, al
0x1800b832d  lea     rcx, [rbp+var_30]
0x1800b8331  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b8336  test    bl, bl
0x1800b8338  jnz     short loc_1800B8367
0x1800b833a  lea     rdx, aOSygSydXa0x1Iu_2; "O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID"...
0x1800b8341  lea     rcx, [rbp+var_30]
0x1800b8345  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b834a  nop
0x1800b834b  lea     rdx, [rbp+var_30]
0x1800b834f  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800b8353  call    ?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::wstring const &)
0x1800b8358  mov     bl, al
0x1800b835a  lea     rcx, [rbp+var_30]
0x1800b835e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b8363  test    bl, bl
0x1800b8365  jz      short loc_1800B837C
0x1800b8367  lea     rcx, [rbp+TokenHandle]
0x1800b836b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b8370  nop
0x1800b8371  call    cs:__imp_CoRevertToSelf
0x1800b8377  jmp     loc_1800B81DF
0x1800b837c  lea     rcx, [rbp+TokenHandle]
0x1800b8380  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b8385  nop
0x1800b8386  call    cs:__imp_CoRevertToSelf
0x1800b838c  xor     al, al
0x1800b838e  mov     rcx, [rbp+var_10]
0x1800b8392  xor     rcx, rsp; StackCookie
0x1800b8395  call    __security_check_cookie
0x1800b839a  mov     rbx, [rsp+60h+arg_0]
0x1800b839f  mov     rdi, [rsp+60h+arg_8]
0x1800b83a4  add     rsp, 60h
0x1800b83a8  pop     rbp
0x1800b83a9  retn
0x1800b83aa  lea     r8, aOnecoreBaseDev_51; "onecore\\base\\devices\\cam\\winrt\\cal"...
0x1800b83b1  mov     edx, 37h ; '7'; void *
0x1800b83b6  mov     rcx, rbx; this
0x1800b83b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b83bf  mov     r9d, eax; char *
0x1800b83c2  lea     r8, aOnecoreBaseDev_51; "onecore\\base\\devices\\cam\\winrt\\cal"...
0x1800b83c9  mov     edx, 26h ; '&'; void *
0x1800b83ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

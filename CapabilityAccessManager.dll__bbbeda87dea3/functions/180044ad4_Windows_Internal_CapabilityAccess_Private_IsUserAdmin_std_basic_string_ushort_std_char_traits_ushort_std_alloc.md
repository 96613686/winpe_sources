# Windows::Internal::CapabilityAccess::Private::IsUserAdmin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180044ad4`
- end: `0x180044b95`
- name: `?IsUserAdmin@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180069d00`
- `0x18006a080`

## callees

- `0x180039e9c`
- `0x18003f4a0`
- `0x18003ff78`
- `0x1800437d0`
- `0x180044ad4`
- `0x1800464d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180044b33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180044b33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Windows::Internal::CapabilityAccess::Private::IsUserAdmin(__int64 a1)
{
  bool v1; // bl
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  DWORD ReturnLength; // [rsp+48h] [rbp+18h] BYREF
  HANDLE TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+28h] BYREF

  Windows::Internal::CapabilityAccess::Private::GetUserTokenFromSidString(&TokenHandle, a1);
  v1 = 0;
  if ( Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(&TokenHandle, WinBuiltinAdministratorsSid) )
  {
    v1 = 1;
  }
  else
  {
    TokenInformation = 0;
    ReturnLength = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenInformation,
      0);
    if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
    {
      v1 = Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(
             &TokenInformation,
             WinBuiltinAdministratorsSid);
    }
    else if ( ((GetLastError() - 1312) & 0xFFFFFFFD) != 0 )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8F4,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v2);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180044ad4  mov     [rsp-8+arg_0], rbx
0x180044ad9  push    rbp
0x180044ada  mov     rbp, rsp
0x180044add  sub     rsp, 30h
0x180044ae1  mov     rdx, rcx
0x180044ae4  lea     rcx, [rbp+TokenHandle]
0x180044ae8  call    ?GetUserTokenFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserTokenFromSidString(std::wstring const &)
0x180044aed  nop
0x180044aee  mov     edx, 1Ah
0x180044af3  lea     rcx, [rbp+TokenHandle]
0x180044af7  call    ?CheckTokenMembership@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4WELL_KNOWN_SID_TYPE@@@Z; Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,WELL_KNOWN_SID_TYPE)
0x180044afc  xor     ebx, ebx
0x180044afe  test    al, al
0x180044b00  jz      short loc_180044B06
0x180044b02  mov     bl, 1
0x180044b04  jmp     short loc_180044B7F
0x180044b06  mov     [rbp+TokenInformation], rbx
0x180044b0a  mov     [rbp+arg_8], ebx
0x180044b0d  xor     edx, edx
0x180044b0f  lea     rcx, [rbp+TokenInformation]
0x180044b13  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180044b18  lea     rax, [rbp+arg_8]
0x180044b1c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180044b21  mov     r9d, 8; TokenInformationLength
0x180044b27  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180044b2b  lea     edx, [r9+0Bh]; TokenInformationClass
0x180044b2f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180044b33  call    cs:__imp_GetTokenInformation
0x180044b39  test    eax, eax
0x180044b3b  jnz     short loc_180044B65
0x180044b3d  call    cs:__imp_GetLastError
0x180044b43  add     eax, 0FFFFFAE0h
0x180044b48  test    eax, 0FFFFFFFDh
0x180044b4d  jz      short loc_180044B75
0x180044b4f  mov     rcx, [rbp+8]; this
0x180044b53  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044b5a  mov     edx, 8F4h; void *
0x180044b5f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180044b65  mov     edx, 1Ah
0x180044b6a  lea     rcx, [rbp+TokenInformation]
0x180044b6e  call    ?CheckTokenMembership@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4WELL_KNOWN_SID_TYPE@@@Z; Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,WELL_KNOWN_SID_TYPE)
0x180044b73  mov     bl, al
0x180044b75  lea     rcx, [rbp+TokenInformation]
0x180044b79  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180044b7e  nop
0x180044b7f  lea     rcx, [rbp+TokenHandle]
0x180044b83  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180044b88  mov     al, bl
0x180044b8a  mov     rbx, [rsp+30h+arg_0]
0x180044b8f  add     rsp, 30h
0x180044b93  pop     rbp
0x180044b94  retn
```

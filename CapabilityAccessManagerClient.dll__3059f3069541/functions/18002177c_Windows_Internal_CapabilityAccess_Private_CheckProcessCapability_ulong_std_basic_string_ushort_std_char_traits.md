# Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002177c`
- end: `0x180021801`
- name: `?CheckProcessCapability@Private@CapabilityAccess@Internal@Windows@@YA_NKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024440`

## callees

- `0x1800142d4`
- `0x18002177c`
- `0x180021808`
- `0x180022838`
- `0x180023690`
- `0x180023a8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800217b6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800217b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(DWORD dwProcessId, __int64 a2)
{
  const char *v3; // r9
  char v4; // bl
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *DuplicateTokenHandle; // [rsp+40h] [rbp+18h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+48h] [rbp+20h] BYREF

  Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(&ExistingTokenHandle, dwProcessId);
  DuplicateTokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &DuplicateTokenHandle,
    0);
  if ( !DuplicateToken(ExistingTokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v3);
  v4 = Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(&DuplicateTokenHandle, a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18002177c  push    rbx
0x18002177e  sub     rsp, 20h
0x180021782  mov     rbx, rdx
0x180021785  mov     edx, ecx; dwProcessId
0x180021787  lea     rcx, [rsp+28h+ExistingTokenHandle]; phNewToken
0x18002178c  call    ?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)
0x180021791  nop
0x180021792  mov     [rsp+28h+DuplicateTokenHandle], 0
0x18002179b  xor     edx, edx
0x18002179d  lea     rcx, [rsp+28h+DuplicateTokenHandle]
0x1800217a2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800217a7  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800217ac  mov     edx, 1; ImpersonationLevel
0x1800217b1  mov     rcx, [rsp+28h+ExistingTokenHandle]; ExistingTokenHandle
0x1800217b6  call    cs:__imp_DuplicateToken
0x1800217bc  mov     rcx, [rsp+28h]; this
0x1800217c1  test    eax, eax
0x1800217c3  jnz     short loc_1800217D5
0x1800217c5  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800217cc  lea     edx, [rax+2Fh]; void *
0x1800217cf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800217d5  mov     rdx, rbx
0x1800217d8  lea     rcx, [rsp+28h+DuplicateTokenHandle]
0x1800217dd  call    ?CheckTokenCapability@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::wstring const &)
0x1800217e2  mov     bl, al
0x1800217e4  lea     rcx, [rsp+28h+DuplicateTokenHandle]
0x1800217e9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800217ee  nop
0x1800217ef  lea     rcx, [rsp+28h+ExistingTokenHandle]
0x1800217f4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800217f9  mov     al, bl
0x1800217fb  add     rsp, 20h
0x1800217ff  pop     rbx
0x180021800  retn
```

# ?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180020354`
- end: `0x180020395`
- name: `?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `65`
- prototype: `bool __fastcall(wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this, const wchar_t *name, unsigned int dwFlags, unsigned int name, _SECURITY_ATTRIBUTES *dwFlags, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fab0`
- `0x1800201b0`

## callees

- `0x18000e300`
- `0x180020354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020369`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180020369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020377`

## pseudocode

```c
bool __fastcall _try_create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this,
        const wchar_t *name,
        DWORD dwFlags,
        unsigned int a4)
{
  HANDLE Mutex; // rax
  void *v6; // rbx

  Mutex = CreateMutexExW(0, name, dwFlags, 0x1F0001u);
  v6 = Mutex;
  if ( Mutex )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      v6);
    LOBYTE(Mutex) = 1;
  }
  return (char)Mutex;
}

```

## disassembly

```asm
0x180020354  mov     [rsp+arg_0], rbx
0x180020359  push    rdi
0x18002035a  sub     rsp, 20h
0x18002035e  mov     rdi, this
0x180020361  mov     r9d, 1F0001h; dwDesiredAccess
0x180020367  xor     ecx, ecx; lpMutexAttributes
0x180020369  call    cs:__imp_CreateMutexExW
0x18002036f  mov     rbx, rax
0x180020372  test    rax, rax
0x180020375  jz      short loc_18002038A
0x180020377  call    cs:__imp_GetLastError
0x18002037d  mov     name, rbx; ptr
0x180020380  mov     this, rdi; this
0x180020383  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020388  mov     al, 1
0x18002038a  mov     rbx, [rsp+28h+arg_0]
0x18002038f  add     rsp, 20h
0x180020393  pop     rdi
0x180020394  retn
```

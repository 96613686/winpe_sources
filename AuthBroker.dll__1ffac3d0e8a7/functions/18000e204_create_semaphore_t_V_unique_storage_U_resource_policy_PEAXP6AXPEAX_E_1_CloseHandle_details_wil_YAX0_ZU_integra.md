# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000e204`
- end: `0x18000e256`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `HRESULT __fastcall(wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this, LONG lInitialCount, LONG lMaximumCount, const wchar_t *name)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aa74`

## callees

- `0x180007674`
- `0x18000e204`
- `0x18000e300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e223`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e231`

## pseudocode

```c
HRESULT __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this,
        LONG lInitialCount,
        LONG lMaximumCount,
        const wchar_t *name)
{
  HANDLE Semaphore; // rbx

  Semaphore = CreateSemaphoreExW(0, lInitialCount, lMaximumCount, name, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr();
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    this,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x18000e204  mov     [rsp+arg_0], rbx
0x18000e209  push    rdi
0x18000e20a  sub     rsp, 30h
0x18000e20e  mov     rdi, this
0x18000e211  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000e219  xor     ecx, ecx; lpSemaphoreAttributes
0x18000e21b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000e223  call    cs:__imp_CreateSemaphoreExW
0x18000e229  mov     rbx, rax
0x18000e22c  test    rax, rax
0x18000e22f  jz      short loc_18000E246
0x18000e231  call    cs:__imp_GetLastError
0x18000e237  mov     rdx, rbx; ptr
0x18000e23a  mov     this, rdi; this
0x18000e23d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e242  xor     eax, eax
0x18000e244  jmp     short loc_18000E24B
0x18000e246  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e24b  mov     rbx, [rsp+38h+arg_0]
0x18000e250  add     rsp, 30h
0x18000e254  pop     rdi
0x18000e255  retn
```

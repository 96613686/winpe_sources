# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180028584`
- end: `0x1800285e0`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028910`
- `0x180109718`

## callees

- `0x180012f30`
- `0x18001c180`
- `0x180028584`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x1800285a0`
- `KERNEL32!CreateEventExW` at `0x1800285a0`
- `KERNEL32!GetLastError` at `0x1800285ae`
- `KERNEL32!GetLastError` at `0x1800285ae`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3)
{
  HANDLE Event; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, a3, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180028584  mov     [rsp+arg_0], rbx
0x180028589  push    rdi
0x18002858a  sub     rsp, 20h
0x18002858e  mov     rdi, rcx
0x180028591  mov     rdx, r8; lpName
0x180028594  xor     ecx, ecx; lpEventAttributes
0x180028596  mov     r9d, 1F0003h; dwDesiredAccess
0x18002859c  lea     r8d, [rcx+1]; dwFlags
0x1800285a0  call    cs:__imp_CreateEventExW
0x1800285a6  mov     rbx, rax
0x1800285a9  test    rax, rax
0x1800285ac  jz      short loc_1800285C9
0x1800285ae  call    cs:__imp_GetLastError
0x1800285b4  mov     rdx, rbx
0x1800285b7  mov     rcx, rdi
0x1800285ba  mov     rbx, [rsp+28h+arg_0]
0x1800285bf  add     rsp, 20h
0x1800285c3  pop     rdi
0x1800285c4  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800285c9  mov     rcx, [rsp+28h]; this
0x1800285ce  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x1800285d5  mov     edx, 1CC8h; void *
0x1800285da  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

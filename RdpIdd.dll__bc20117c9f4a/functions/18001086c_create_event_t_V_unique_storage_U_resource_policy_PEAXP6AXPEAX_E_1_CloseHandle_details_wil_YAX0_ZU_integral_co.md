# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001086c`
- end: `0x1800108c9`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9b8`
- `0x180030120`

## callees

- `0x18000c354`
- `0x180010690`
- `0x18001086c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010889`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001089d`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  void *v3; // rdx
  HANDLE Event; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x18001086c  mov     [rsp+arg_0], rbx
0x180010871  push    rdi
0x180010872  sub     rsp, 20h
0x180010876  and     edx, 3
0x180010879  mov     rdi, rcx
0x18001087c  mov     r8d, edx; dwFlags
0x18001087f  mov     r9d, 1F0003h; dwDesiredAccess
0x180010885  xor     edx, edx; lpName
0x180010887  xor     ecx, ecx; lpEventAttributes
0x180010889  call    cs:__imp_CreateEventExW
0x180010890  nop     dword ptr [rax+rax+00h]
0x180010895  mov     rbx, rax
0x180010898  test    rax, rax
0x18001089b  jz      short loc_1800108BE
0x18001089d  call    cs:__imp_GetLastError
0x1800108a4  nop     dword ptr [rax+rax+00h]
0x1800108a9  mov     rdx, rbx
0x1800108ac  mov     rcx, rdi
0x1800108af  mov     rbx, [rsp+28h+arg_0]
0x1800108b4  add     rsp, 20h
0x1800108b8  pop     rdi
0x1800108b9  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800108be  mov     rcx, [rsp+28h]; this
0x1800108c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

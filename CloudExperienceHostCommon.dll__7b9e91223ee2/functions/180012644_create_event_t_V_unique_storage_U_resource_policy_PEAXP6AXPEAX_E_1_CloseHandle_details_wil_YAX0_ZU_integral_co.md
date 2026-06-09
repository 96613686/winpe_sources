# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012644`
- end: `0x1800126a5`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800124f4`
- `0x180019c90`
- `0x18007f0e8`

## callees

- `0x180012644`
- `0x180020028`
- `0x180022790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180012665`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180012665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012673`

## string_xrefs

- `0x180012693`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  HANDLE Event; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
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
0x180012644  mov     [rsp+arg_0], rbx
0x180012649  push    rdi
0x18001264a  sub     rsp, 20h
0x18001264e  and     edx, 3
0x180012651  mov     rax, r8
0x180012654  mov     r8d, edx; dwFlags
0x180012657  mov     rdi, rcx
0x18001265a  mov     rdx, rax; lpName
0x18001265d  mov     r9d, 1F0003h; dwDesiredAccess
0x180012663  xor     ecx, ecx; lpEventAttributes
0x180012665  call    cs:__imp_CreateEventExW
0x18001266b  mov     rbx, rax
0x18001266e  test    rax, rax
0x180012671  jz      short loc_18001268E
0x180012673  call    cs:__imp_GetLastError
0x180012679  mov     rdx, rbx
0x18001267c  mov     rcx, rdi
0x18001267f  mov     rbx, [rsp+28h+arg_0]
0x180012684  add     rsp, 20h
0x180012688  pop     rdi
0x180012689  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001268e  mov     rcx, [rsp+28h]; this
0x180012693  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001269a  mov     edx, 1CC8h; void *
0x18001269f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

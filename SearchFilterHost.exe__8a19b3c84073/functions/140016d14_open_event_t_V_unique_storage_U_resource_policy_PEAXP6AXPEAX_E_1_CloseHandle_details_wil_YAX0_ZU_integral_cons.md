# ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEB_WK_N@Z

- ea: `0x140016d14`
- end: `0x140016d4f`
- name: `?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEB_WK_N@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e7ec`
- `0x14001e68c`

## callees

- `0x140007bb0`
- `0x14000bc5c`
- `0x140016d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140016d27`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140016d27`

## pseudocode

```c
__int64 __fastcall _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEB_WK_N_Z(
        __int64 a1,
        const WCHAR *a2)
{
  HANDLE v3; // rax
  wil::details *v4; // rcx

  v3 = OpenEventW(0x100000u, 0, a2);
  if ( !v3 )
    return wil::details::GetLastErrorFailHr(v4);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    v3);
  return 0;
}

```

## disassembly

```asm
0x140016d14  push    rbx
0x140016d16  sub     rsp, 20h
0x140016d1a  mov     rbx, rcx
0x140016d1d  mov     r8, rdx; lpName
0x140016d20  xor     edx, edx; bInheritHandle
0x140016d22  mov     ecx, 100000h; dwDesiredAccess
0x140016d27  call    cs:__imp_OpenEventW
0x140016d2d  test    rax, rax
0x140016d30  jz      short loc_140016D45
0x140016d32  mov     rdx, rax
0x140016d35  mov     rcx, rbx
0x140016d38  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016d3d  xor     eax, eax
0x140016d3f  add     rsp, 20h
0x140016d43  pop     rbx
0x140016d44  retn
0x140016d45  add     rsp, 20h
0x140016d49  pop     rbx
0x140016d4a  jmp     ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
```

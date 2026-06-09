# ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGK_N@Z

- ea: `0x18001ff58`
- end: `0x18001ff93`
- name: `?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGK_N@Z`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f9f0`
- `0x180020ec0`

## callees

- `0x1800062d8`
- `0x1800084bc`
- `0x18001ff58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001ff6b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001ff6b`

## pseudocode

```c
__int64 __fastcall _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGK_N_Z(
        __int64 a1,
        const WCHAR *a2)
{
  HANDLE v3; // rax
  wil::details *v4; // rcx

  v3 = OpenEventW(0x100002u, 0, a2);
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
0x18001ff58  push    rbx
0x18001ff5a  sub     rsp, 20h
0x18001ff5e  mov     rbx, rcx
0x18001ff61  mov     r8, rdx; lpName
0x18001ff64  xor     edx, edx; bInheritHandle
0x18001ff66  mov     ecx, 100002h; dwDesiredAccess
0x18001ff6b  call    cs:__imp_OpenEventW
0x18001ff71  test    rax, rax
0x18001ff74  jz      short loc_18001FF89
0x18001ff76  mov     rdx, rax
0x18001ff79  mov     rcx, rbx
0x18001ff7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001ff81  xor     eax, eax
0x18001ff83  add     rsp, 20h
0x18001ff87  pop     rbx
0x18001ff88  retn
0x18001ff89  add     rsp, 20h
0x18001ff8d  pop     rbx
0x18001ff8e  jmp     ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
```

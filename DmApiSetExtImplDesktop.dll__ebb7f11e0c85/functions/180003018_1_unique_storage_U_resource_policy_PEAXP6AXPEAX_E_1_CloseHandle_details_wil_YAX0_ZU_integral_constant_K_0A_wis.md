# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180003018`
- end: `0x18000302f`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002eb8`
- `0x180003094`
- `0x1800031e4`
- `0x180005548`

## callees

- `0x180003018`
- `0x180003440`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::CloseHandle(v2, a2);
}

```

## disassembly

```asm
0x180003018  sub     rsp, 28h
0x18000301c  mov     rcx, [rcx]; this
0x18000301f  test    rcx, rcx
0x180003022  jz      short loc_180003029
0x180003024  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180003029  add     rsp, 28h
0x18000302d  retn
```

# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18000a934`
- end: `0x18000a94a`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009ce8`
- `0x180009e54`
- `0x180009fc0`
- `0x18000f44c`
- `0x18000f47c`
- `0x18000f634`

## callees

- `0x18000a934`
- `0x18000f770`

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
0x18000a934  sub     rsp, 28h
0x18000a938  mov     rcx, [rcx]; this
0x18000a93b  test    rcx, rcx
0x18000a93e  jz      short loc_18000A945
0x18000a940  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000a945  add     rsp, 28h
0x18000a949  retn
```

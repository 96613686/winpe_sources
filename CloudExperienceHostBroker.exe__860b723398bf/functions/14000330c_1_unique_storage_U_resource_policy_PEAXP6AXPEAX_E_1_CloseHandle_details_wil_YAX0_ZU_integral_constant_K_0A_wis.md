# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x14000330c`
- end: `0x140003322`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000317c`
- `0x14000337c`
- `0x140003440`
- `0x140005440`
- `0x140007544`
- `0x14000759c`
- `0x140008fdc`

## callees

- `0x14000330c`
- `0x1400035f0`

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
0x14000330c  sub     rsp, 28h
0x140003310  mov     rcx, [rcx]; this
0x140003313  test    rcx, rcx
0x140003316  jz      short loc_14000331D
0x140003318  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000331d  add     rsp, 28h
0x140003321  retn
```

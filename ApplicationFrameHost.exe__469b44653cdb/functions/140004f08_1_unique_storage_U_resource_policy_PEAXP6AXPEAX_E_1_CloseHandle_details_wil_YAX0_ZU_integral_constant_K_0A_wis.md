# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x140004f08`
- end: `0x140004f1e`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004d44`
- `0x140004d74`
- `0x140005024`
- `0x1400052f8`
- `0x140005464`
- `0x140008e8c`

## callees

- `0x140004f08`
- `0x1400055d0`

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
0x140004f08  sub     rsp, 28h
0x140004f0c  mov     rcx, [rcx]; this
0x140004f0f  test    rcx, rcx
0x140004f12  jz      short loc_140004F19
0x140004f14  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140004f19  add     rsp, 28h
0x140004f1d  retn
```

# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180030a38`
- end: `0x180030a59`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `33`
- prototype: `int __fastcall(PSECURITY_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030a2c`
- `0x180030a60`
- `0x180031a9c`
- `0x180034e10`
- `0x1800352c8`

## callees

- `0x180030a38`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030a4e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030a4e`

## pseudocode

```c
int __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        PSECURITY_DESCRIPTOR *a1)
{
  PSECURITY_DESCRIPTOR v1; // rax
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    ObjectDescriptor = *a1;
    LODWORD(v1) = DestroyPrivateObjectSecurity(&ObjectDescriptor);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x180030a38  sub     rsp, 28h
0x180030a3c  mov     rax, [rcx]
0x180030a3f  test    rax, rax
0x180030a42  jz      short loc_180030A54
0x180030a44  lea     rcx, [rsp+28h+ObjectDescriptor]; ObjectDescriptor
0x180030a49  mov     [rsp+28h+ObjectDescriptor], rax
0x180030a4e  call    cs:__imp_DestroyPrivateObjectSecurity
0x180030a54  add     rsp, 28h
0x180030a58  retn
```

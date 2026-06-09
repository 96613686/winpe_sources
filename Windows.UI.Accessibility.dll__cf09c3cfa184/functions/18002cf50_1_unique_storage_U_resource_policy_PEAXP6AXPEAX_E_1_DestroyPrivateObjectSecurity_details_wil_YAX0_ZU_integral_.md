# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18002cf50`
- end: `0x18002cf71`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cebc`
- `0x18002d2b0`

## callees

- `0x18002cf50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002cf66`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002cf66`

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
0x18002cf50  sub     rsp, 28h
0x18002cf54  mov     rax, [rcx]
0x18002cf57  test    rax, rax
0x18002cf5a  jz      short loc_18002CF6C
0x18002cf5c  lea     rcx, [rsp+28h+ObjectDescriptor]; ObjectDescriptor
0x18002cf61  mov     [rsp+28h+ObjectDescriptor], rax
0x18002cf66  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002cf6c  add     rsp, 28h
0x18002cf70  retn
```

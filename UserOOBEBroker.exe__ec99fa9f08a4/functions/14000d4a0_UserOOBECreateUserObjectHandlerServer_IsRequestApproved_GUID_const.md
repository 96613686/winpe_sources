# UserOOBECreateUserObjectHandlerServer::_IsRequestApproved(_GUID const &)

- ea: `0x14000d4a0`
- end: `0x14000d4af`
- name: `?_IsRequestApproved@UserOOBECreateUserObjectHandlerServer@@EEAA_NAEBU_GUID@@@Z`
- size: `15`
- prototype: `bool __fastcall(const unsigned __int16 **this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000a54c`

## pseudocode

```c
bool __fastcall UserOOBECreateUserObjectHandlerServer::_IsRequestApproved(
        const unsigned __int16 **this,
        const struct _GUID *a2)
{
  return IsClsidApproved(a2, this[2]);
}

```

## disassembly

```asm
0x14000d4a0  mov     rax, rdx
0x14000d4a3  mov     rdx, [rcx+10h]; unsigned __int16 *
0x14000d4a7  mov     rcx, rax; struct _GUID *
0x14000d4aa  jmp     ?IsClsidApproved@@YA_NAEBU_GUID@@PEBG@Z; IsClsidApproved(_GUID const &,ushort const *)
```

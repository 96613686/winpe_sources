# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::GetVersion(void)

- ea: `0x18000b8a0`
- end: `0x18000b8a6`
- name: `?GetVersion@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@EEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::GetVersion(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *this)
{
  return 2;
}

```

## disassembly

```asm
0x18000b8a0  mov     eax, 2
0x18000b8a5  retn
```

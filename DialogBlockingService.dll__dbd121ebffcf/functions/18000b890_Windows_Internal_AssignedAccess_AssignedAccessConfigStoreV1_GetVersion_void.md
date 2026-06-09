# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::GetVersion(void)

- ea: `0x18000b890`
- end: `0x18000b896`
- name: `?GetVersion@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@EEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800016d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::GetVersion(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this)
{
  return 1;
}

```

## disassembly

```asm
0x18000b890  mov     eax, 1
0x18000b895  retn
```

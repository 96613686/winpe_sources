# CPropertyCache::locateproperty(ushort *,ulong *)

- ea: `0x180010ec0`
- end: `0x180010ec5`
- name: `?locateproperty@CPropertyCache@@UEAAJPEAGPEAK@Z`
- size: `5`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800102e0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CPropertyCache::locateproperty(CCoreADsObject **this, unsigned __int16 *a2, unsigned int *a3)
{
  return CPropertyCache::DispatchLocateProperty(this, a2, a3);
}

```

## disassembly

```asm
0x180010ec0  jmp     ?DispatchLocateProperty@CPropertyCache@@IEAAJPEAGPEAK@Z; CPropertyCache::DispatchLocateProperty(ushort *,ulong *)
```

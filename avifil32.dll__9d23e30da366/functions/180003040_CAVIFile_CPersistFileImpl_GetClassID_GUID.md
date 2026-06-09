# CAVIFile::CPersistFileImpl::GetClassID(_GUID *)

- ea: `0x180003040`
- end: `0x180003043`
- name: `?GetClassID@CPersistFileImpl@CAVIFile@@UEAAJPEAU_GUID@@@Z`
- size: `3`
- prototype: `__int64 __fastcall(CAVIFile::CPersistFileImpl *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1800016e0`

## pseudocode

```c
__int64 __fastcall CAVIFile::CPersistFileImpl::GetClassID(CAVIFile::CPersistFileImpl *this, struct _GUID *a2)
{
  return 0;
}

```

## disassembly

```asm
0x180003040  xor     eax, eax
0x180003042  retn
```

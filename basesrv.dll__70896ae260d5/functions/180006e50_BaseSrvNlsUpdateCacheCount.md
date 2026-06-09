# BaseSrvNlsUpdateCacheCount

- ea: `0x180006e50`
- end: `0x180006e6b`
- name: `BaseSrvNlsUpdateCacheCount`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 BaseSrvNlsUpdateCacheCount()
{
  bCacheDirty = 1;
  _InterlockedIncrement((volatile signed __int32 *)pNlsRegUserInfo + 414);
  return 0;
}

```

## disassembly

```asm
0x180006e50  mov     rax, cs:pNlsRegUserInfo
0x180006e57  mov     cs:bCacheDirty, 1
0x180006e61  lock inc dword ptr [rax+678h]
0x180006e68  xor     eax, eax
0x180006e6a  retn
```

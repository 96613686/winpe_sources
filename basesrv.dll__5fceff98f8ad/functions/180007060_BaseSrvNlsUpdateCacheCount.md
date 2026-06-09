# BaseSrvNlsUpdateCacheCount

- ea: `0x180007060`
- end: `0x18000707b`
- name: `BaseSrvNlsUpdateCacheCount`
- size: `27`
- prototype: ``
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
0x180007060  mov     rax, cs:pNlsRegUserInfo
0x180007067  mov     cs:bCacheDirty, 1
0x180007071  lock inc dword ptr [rax+678h]
0x180007078  xor     eax, eax
0x18000707a  retn
```

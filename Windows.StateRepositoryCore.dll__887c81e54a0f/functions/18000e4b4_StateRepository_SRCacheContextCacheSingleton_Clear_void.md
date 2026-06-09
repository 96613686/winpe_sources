# StateRepository::SRCacheContextCacheSingleton::Clear(void)

- ea: `0x18000e4b4`
- end: `0x18000e4b9`
- name: `?Clear@SRCacheContextCacheSingleton@StateRepository@@SAJXZ`
- size: `5`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ca10`
- `0x18000e55c`
- `0x18000e6d8`

## callees

- `0x18000f760`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall StateRepository::SRCacheContextCacheSingleton::Clear(HKEY *this)
{
  return StateRepository::SRCacheContextCache::Clear(this);
}

```

## disassembly

```asm
0x18000e4b4  jmp     ?Clear@SRCacheContextCache@StateRepository@@QEAAJXZ; StateRepository::SRCacheContextCache::Clear(void)
```

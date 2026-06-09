# MosQueryPackagesFromPath(ushort const *,std::vector<uint,std::allocator<uint>> *,StackMode)

- ea: `0x18000b270`
- end: `0x18000b27d`
- name: `?MosQueryPackagesFromPath@@YAJPEBGPEAV?$vector@IV?$allocator@I@std@@@std@@W4StackMode@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b284`

## pseudocode

```c
__int64 __fastcall MosQueryPackagesFromPath(__int64 a1, __int64 a2, unsigned int a3)
{
  return MosQueryPackagesFromPathInternal(a1, 0, a2, a3);
}

```

## disassembly

```asm
0x18000b270  mov     r9d, r8d
0x18000b273  mov     r8, rdx
0x18000b276  xor     edx, edx
0x18000b278  jmp     MosQueryPackagesFromPathInternal
```

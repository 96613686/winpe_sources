# ProvPackage::GetPackagePath(void)

- ea: `0x14000c910`
- end: `0x14000c915`
- name: `?GetPackagePath@ProvPackage@@UEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall ProvPackage::GetPackagePath(__int64 a1)
{
  return a1 + 8;
}

```

## disassembly

```asm
0x14000c910  lea     rax, [rcx+8]
0x14000c914  retn
```

# __imp_load_WICCreateImagingFactory_Proxy

- ea: `0x18000221f`
- end: `0x18000222b`
- name: `__imp_load_WICCreateImagingFactory_Proxy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800021a0`

## import_xrefs

- `WindowsCodecs!WICCreateImagingFactory_Proxy` at `0x18000221f`

## pseudocode

```c
__int64 load_WICCreateImagingFactory_Proxy()
{
  return _tailMerge_windowscodecs_dll();
}

```

## disassembly

```asm
0x18000221f  lea     rax, __imp_WICCreateImagingFactory_Proxy
0x180002226  jmp     __tailMerge_windowscodecs_dll
```

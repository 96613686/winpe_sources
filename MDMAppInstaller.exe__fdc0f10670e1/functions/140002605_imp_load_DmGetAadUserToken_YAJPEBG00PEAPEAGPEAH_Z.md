# __imp_load_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z

- ea: `0x140002605`
- end: `0x140002611`
- name: `__imp_load_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002550`

## import_xrefs

- `DMCmnUtils!DmGetAadUserToken` at `0x140002605`

## pseudocode

```c
__int64 load__DmGetAadUserToken__YAJPEBG00PEAPEAGPEAH_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x140002605  lea     rax, __imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x14000260c  jmp     __tailMerge_dmcmnutils_dll
```

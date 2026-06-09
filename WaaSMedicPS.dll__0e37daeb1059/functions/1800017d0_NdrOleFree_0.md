# NdrOleFree_0

- ea: `0x1800017d0`
- end: `0x1800017d6`
- name: `NdrOleFree_0`
- size: `6`
- prototype: `void __stdcall(void *NodeToFree)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrOleFree` at `0x1800017d0`

## pseudocode

```c
// attributes: thunk
void __stdcall NdrOleFree_0(void *NodeToFree)
{
  NdrOleFree(NodeToFree);
}

```

## disassembly

```asm
0x1800017d0  jmp     cs:__imp_NdrOleFree
```

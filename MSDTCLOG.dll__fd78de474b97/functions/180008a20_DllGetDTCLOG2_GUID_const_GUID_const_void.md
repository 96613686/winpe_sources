# DllGetDTCLOG2(_GUID const &,_GUID const &,void * *)

- ea: `0x180008a20`
- end: `0x180008a25`
- name: `?DllGetDTCLOG2@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008a30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall DllGetDTCLOG2(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  return DllGetDTCLOG(a1, a2, a3);
}

```

## disassembly

```asm
0x180008a20  jmp     ?DllGetDTCLOG@@YAJAEBU_GUID@@0PEAPEAX@Z; DllGetDTCLOG(_GUID const &,_GUID const &,void * *)
```

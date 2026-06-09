# operator delete(void *,unsigned __int64)

- ea: `0x1800016f4`
- end: `0x1800016f9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `51`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002788`
- `0x180003370`
- `0x180004bf0`
- `0x180004fc0`
- `0x1800051d4`
- `0x180006c54`
- `0x18000a2cc`
- `0x18000a3f0`
- `0x18000a430`
- `0x18000a4c0`
- `0x18000a520`
- `0x18000b7e8`
- `0x18000c130`
- `0x18000c190`
- `0x18000c500`
- `0x18000e624`
- `0x18000e69c`
- `0x18000e798`
- `0x18000e8e8`
- `0x18000f024`
- `0x18000f8bc`
- `0x1800101fc`
- `0x180010ae8`
- `0x180011e44`
- `0x180012470`
- `0x180013320`
- `0x180013700`
- `0x180014cc0`
- `0x180014d00`
- `0x180014d40`
- `0x180019f20`
- `0x18001a0f0`
- `0x18001cb90`
- `0x18001dbc0`
- `0x18001dc10`
- `0x18001ddc0`
- `0x18001e600`
- `0x18001e650`
- `0x180021b70`
- `0x180022d70`
- `0x180022dc0`
- `0x1800247a8`
- `0x1800248b0`
- `0x1800286a0`
- `0x1800286f0`
- `0x18002b025`
- `0x18002b0cd`
- `0x18002b0f3`
- `0x18002b119`
- `0x18002b155`

## callees

- `0x18000dc30`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(HLOCAL hMem)
{
  ??3@YAXPEAX@Z(hMem);
}

```

## disassembly

```asm
0x1800016f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

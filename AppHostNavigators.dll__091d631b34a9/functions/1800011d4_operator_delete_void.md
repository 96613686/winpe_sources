# operator delete(void *)

- ea: `0x1800011d4`
- end: `0x1800011d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `56`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800017d0`
- `0x180002270`
- `0x1800022b0`
- `0x1800023ec`
- `0x1800024d0`
- `0x180004580`
- `0x1800045c0`
- `0x180004600`
- `0x180004640`
- `0x180004680`
- `0x1800046b0`
- `0x1800046f0`
- `0x180004d20`
- `0x180005d10`
- `0x180005d50`
- `0x180005d90`
- `0x180006a50`
- `0x180007890`
- `0x1800078d0`
- `0x180007910`
- `0x180007950`
- `0x180007990`
- `0x1800079d0`
- `0x180007a10`
- `0x1800086f0`
- `0x180008730`
- `0x180008fe0`
- `0x180009bc0`
- `0x180009c00`
- `0x180009c40`
- `0x180009c80`
- `0x18000aa00`
- `0x18000aa40`
- `0x18000aa80`
- `0x18000aac0`
- `0x18000ab00`
- `0x18000c448`
- `0x18000e0a0`
- `0x18000e0e0`
- `0x18000e120`
- `0x18000e160`
- `0x18000f030`
- `0x18000f744`
- `0x18000fa20`
- `0x18000fa60`
- `0x1800108a0`
- `0x1800108e0`
- `0x180011590`
- `0x180011d00`
- `0x180011d40`

## callees

- `0x1800017ac`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x1800011d4  jmp     free_0
```

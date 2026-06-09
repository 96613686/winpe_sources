# operator delete(void *,uint)

- ea: `0x40eb05`
- end: `0x40eb15`
- name: `??3@YAXPAXI@Z`
- size: `16`
- prototype: `void __cdecl(void *lpMem)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x40d860`
- `0x40dc30`
- `0x40de00`
- `0x40e280`

## callees

- `0x402712`

## pseudocode

```c
void __cdecl operator delete(void *lpMem)
{
  operator delete(lpMem);
}

```

## disassembly

```asm
0x40eb05  mov     edi, edi
0x40eb07  push    ebp
0x40eb08  mov     ebp, esp
0x40eb0a  push    [ebp+lpMem]; lpMem
0x40eb0d  call    ??3@YAXPAX@Z; operator delete(void *)
0x40eb12  pop     ecx
0x40eb13  pop     ebp
0x40eb14  retn
```

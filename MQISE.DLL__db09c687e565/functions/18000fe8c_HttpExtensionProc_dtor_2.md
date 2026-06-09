# HttpExtensionProc$dtor$2

- ea: `0x18000fe8c`
- end: `0x18000fe98`
- name: `HttpExtensionProc$dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000344c`

## pseudocode

```c
__int64 __fastcall HttpExtensionProc_dtor_2(__int64 a1, __int64 a2)
{
  return CStaticResizeBuffer<char,2048>::~CStaticResizeBuffer<char,2048>(*(_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000fe8c  mov     rcx, [rdx+38h]
0x18000fe93  jmp     ??1?$CStaticResizeBuffer@D$0IAA@@@QEAA@XZ; CStaticResizeBuffer<char,2048>::~CStaticResizeBuffer<char,2048>(void)
```

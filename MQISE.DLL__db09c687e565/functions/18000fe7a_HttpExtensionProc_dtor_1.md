# HttpExtensionProc$dtor$1

- ea: `0x18000fe7a`
- end: `0x18000fe86`
- name: `HttpExtensionProc$dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000348c`

## pseudocode

```c
__int64 __fastcall HttpExtensionProc_dtor_1(__int64 a1, __int64 a2)
{
  return P<Context>::~P<Context>(a2 + 72);
}

```

## disassembly

```asm
0x18000fe7a  lea     rcx, [rdx+48h]
0x18000fe81  jmp     ??1?$P@UContext@@@@QEAA@XZ; P<Context>::~P<Context>(void)
```

# GetExtensionlessUrlAppendage(void)

- ea: `0x180002040`
- end: `0x180002048`
- name: `?GetExtensionlessUrlAppendage@@YAPEBGXZ`
- size: `8`
- prototype: `unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
unsigned __int16 *GetExtensionlessUrlAppendage(void)
{
  return EURL::sm_pszEURLAppendageW;
}

```

## disassembly

```asm
0x180002040  mov     rax, cs:?sm_pszEURLAppendageW@EURL@@0PEAGEA; ushort * EURL::sm_pszEURLAppendageW
0x180002047  retn
```

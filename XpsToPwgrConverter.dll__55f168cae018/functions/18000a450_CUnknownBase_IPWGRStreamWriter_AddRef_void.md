# CUnknownBase<IPWGRStreamWriter>::AddRef(void)

- ea: `0x18000a450`
- end: `0x18000a45d`
- name: `?AddRef@?$CUnknownBase@UIPWGRStreamWriter@@@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CUnknownBase<IPWGRStreamWriter>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x18000a450  mov     eax, 1
0x18000a455  lock xadd [rcx+8], eax
0x18000a45a  inc     eax
0x18000a45c  retn
```

# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x180006c6c`
- end: `0x180006c7d`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *__hidden this, int, unsigned int)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000378c`
- `0x180003b08`
- `0x180004210`
- `0x180006280`
- `0x1800087a0`
- `0x180008f80`
- `0x180009670`
- `0x1800098a0`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180006c76`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x180006c6c  xor     r9d, r9d
0x180006c6f  xor     r8d, r8d
0x180006c72  lea     edx, [r9+1]
0x180006c76  jmp     cs:__imp_RaiseException
```

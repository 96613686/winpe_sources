# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x18000e9c4`
- end: `0x18000e9d5`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *__hidden this, int, unsigned int)`
- caller_count: `19`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001480`
- `0x1800014d0`
- `0x180001520`
- `0x180006ab0`
- `0x180006b04`
- `0x180006b58`
- `0x180006bac`
- `0x180006c00`
- `0x180006cb4`
- `0x1800070d4`
- `0x18000762c`
- `0x18000e9e0`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e9ce`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000e9c4  xor     r9d, r9d
0x18000e9c7  xor     r8d, r8d
0x18000e9ca  lea     edx, [r9+1]
0x18000e9ce  jmp     cs:__imp_RaiseException
```

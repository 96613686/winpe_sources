# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x14000ff44`
- end: `0x14000ff55`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000597c`
- `0x1400059c0`
- `0x140005a04`
- `0x140005a48`
- `0x140005a8c`
- `0x140007dcc`
- `0x140012a38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000ff4e`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000ff44  xor     r9d, r9d
0x14000ff47  xor     r8d, r8d
0x14000ff4a  lea     edx, [r9+1]
0x14000ff4e  jmp     cs:__imp_RaiseException
```

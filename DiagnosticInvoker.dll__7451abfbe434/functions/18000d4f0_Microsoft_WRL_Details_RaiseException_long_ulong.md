# Microsoft::WRL::Details::RaiseException(long,ulong)

- ea: `0x18000d4f0`
- end: `0x18000d501`
- name: `?RaiseException@Details@WRL@Microsoft@@YAXJK@Z`
- size: `17`
- prototype: `void __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007b98`
- `0x18000881c`
- `0x18000b994`
- `0x18000c780`
- `0x18000dad0`
- `0x18000e070`
- `0x18000e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d4fa`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::RaiseException(Microsoft::WRL::Details *this)
{
  RaiseException((DWORD)this, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000d4f0  xor     r9d, r9d
0x18000d4f3  xor     r8d, r8d
0x18000d4f6  lea     edx, [r9+1]
0x18000d4fa  jmp     cs:__imp_RaiseException
```

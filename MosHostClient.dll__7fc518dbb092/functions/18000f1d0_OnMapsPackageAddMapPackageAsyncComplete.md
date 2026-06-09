# OnMapsPackageAddMapPackageAsyncComplete

- ea: `0x18000f1d0`
- end: `0x18000f1dd`
- name: `OnMapsPackageAddMapPackageAsyncComplete`
- size: `13`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall OnMapsPackageAddMapPackageAsyncComplete(__int64 a1, __int64 a2, __int64 a3)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(a3 + 8))(a1, *(_QWORD *)(a3 + 16));
}

```

## disassembly

```asm
0x18000f1d0  mov     rdx, [r8+10h]
0x18000f1d4  mov     rax, [r8+8]
0x18000f1d8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# OnMapsPackageFindNearbyPackagesAsyncComplete

- ea: `0x18000dab0`
- end: `0x18000dad0`
- name: `OnMapsPackageFindNearbyPackagesAsyncComplete`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall OnMapsPackageFindNearbyPackagesAsyncComplete(__int64 a1, __int64 a2, __int64 a3)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(a3 + 48))(
           a1,
           *(unsigned int *)(a3 + 64),
           *(_QWORD *)(a3 + 72),
           *(_QWORD *)(a3 + 56));
}

```

## disassembly

```asm
0x18000dab0  sub     rsp, 38h
0x18000dab4  mov     r9, [r8+38h]
0x18000dab8  mov     rax, r8
0x18000dabb  mov     r8, [r8+48h]
0x18000dabf  mov     edx, [rax+40h]
0x18000dac2  mov     rax, [rax+30h]
0x18000dac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dacb  add     rsp, 38h
0x18000dacf  retn
```

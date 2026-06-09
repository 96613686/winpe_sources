# ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::Release(void)

- ea: `0x18000a0e0`
- end: `0x18000a0f0`
- name: `?Release@?$CComContainedObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000a0e0  mov     rcx, [rcx+8]
0x18000a0e4  mov     rax, [rcx]
0x18000a0e7  mov     rax, [rax+10h]
0x18000a0eb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

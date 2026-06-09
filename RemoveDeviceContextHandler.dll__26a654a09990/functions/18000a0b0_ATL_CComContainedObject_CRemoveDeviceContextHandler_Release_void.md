# ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release(void)

- ea: `0x18000a0b0`
- end: `0x18000a0c0`
- name: `?Release@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a0d0`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x18000a0b0  mov     rcx, [rcx+10h]
0x18000a0b4  mov     rax, [rcx]
0x18000a0b7  mov     rax, [rax+10h]
0x18000a0bb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

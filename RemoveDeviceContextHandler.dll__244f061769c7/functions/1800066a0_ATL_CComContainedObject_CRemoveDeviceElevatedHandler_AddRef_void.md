# ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::AddRef(void)

- ea: `0x1800066a0`
- end: `0x1800066b0`
- name: `?AddRef@?$CComContainedObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800066a0  mov     rcx, [rcx+8]
0x1800066a4  mov     rax, [rcx]
0x1800066a7  mov     rax, [rax+8]
0x1800066ab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef(void)

- ea: `0x180006670`
- end: `0x180006680`
- name: `?AddRef@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006690`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180006670  mov     rcx, [rcx+10h]
0x180006674  mov     rax, [rcx]
0x180006677  mov     rax, [rax+8]
0x18000667b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

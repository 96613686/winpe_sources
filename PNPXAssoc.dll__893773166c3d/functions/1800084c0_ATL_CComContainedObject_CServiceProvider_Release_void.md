# ATL::CComContainedObject<CServiceProvider>::Release(void)

- ea: `0x1800084c0`
- end: `0x1800084d0`
- name: `?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800084e0`
- `0x1800084f0`
- `0x180008500`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 16LL))(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x1800084c0  mov     rcx, [rcx+20h]
0x1800084c4  mov     rax, [rcx]
0x1800084c7  mov     rax, [rax+10h]
0x1800084cb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

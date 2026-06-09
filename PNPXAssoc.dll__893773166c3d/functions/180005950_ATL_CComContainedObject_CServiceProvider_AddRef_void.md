# ATL::CComContainedObject<CServiceProvider>::AddRef(void)

- ea: `0x180005950`
- end: `0x180005960`
- name: `?AddRef@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005970`
- `0x180005980`
- `0x180005990`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 8LL))(*(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x180005950  mov     rcx, [rcx+20h]
0x180005954  mov     rax, [rcx]
0x180005957  mov     rax, [rax+8]
0x18000595b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

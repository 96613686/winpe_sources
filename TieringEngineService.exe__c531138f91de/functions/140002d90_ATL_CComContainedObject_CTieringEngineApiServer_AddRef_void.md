# ATL::CComContainedObject<CTieringEngineApiServer>::AddRef(void)

- ea: `0x140002d90`
- end: `0x140002daa`
- name: `?AddRef@?$CComContainedObject@VCTieringEngineApiServer@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CTieringEngineApiServer>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140002d90  sub     rsp, 28h
0x140002d94  mov     rcx, [rcx+8]
0x140002d98  mov     rax, [rcx]
0x140002d9b  mov     rax, [rax+8]
0x140002d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002da4  nop
0x140002da5  add     rsp, 28h
0x140002da9  retn
```

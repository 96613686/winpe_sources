# ATL::CComContainedObject<CTieringEngineApiServer>::Release(void)

- ea: `0x140003c80`
- end: `0x140003c9a`
- name: `?Release@?$CComContainedObject@VCTieringEngineApiServer@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CTieringEngineApiServer>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140003c80  sub     rsp, 28h
0x140003c84  mov     rcx, [rcx+8]
0x140003c88  mov     rax, [rcx]
0x140003c8b  mov     rax, [rax+10h]
0x140003c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c94  nop
0x140003c95  add     rsp, 28h
0x140003c99  retn
```

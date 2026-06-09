# ATL::CComContainedObject<CRASrv>::AddRef(void)

- ea: `0x140004560`
- end: `0x14000457a`
- name: `?AddRef@?$CComContainedObject@VCRASrv@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004580`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRASrv>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x140004560  sub     rsp, 28h
0x140004564  mov     rcx, [rcx+10h]
0x140004568  mov     rax, [rcx]
0x14000456b  mov     rax, [rax+8]
0x14000456f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004574  nop
0x140004575  add     rsp, 28h
0x140004579  retn
```

# ATL::CComContainedObject<CRASrv>::Release(void)

- ea: `0x140009db0`
- end: `0x140009dca`
- name: `?Release@?$CComContainedObject@VCRASrv@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009dd0`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRASrv>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x140009db0  sub     rsp, 28h
0x140009db4  mov     rcx, [rcx+10h]
0x140009db8  mov     rax, [rcx]
0x140009dbb  mov     rax, [rax+10h]
0x140009dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dc4  nop
0x140009dc5  add     rsp, 28h
0x140009dc9  retn
```

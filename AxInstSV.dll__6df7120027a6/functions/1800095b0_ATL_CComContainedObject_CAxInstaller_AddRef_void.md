# ATL::CComContainedObject<CAxInstaller>::AddRef(void)

- ea: `0x1800095b0`
- end: `0x1800095ca`
- name: `?AddRef@?$CComContainedObject@VCAxInstaller@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800095d0`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAxInstaller>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800095b0  sub     rsp, 28h
0x1800095b4  mov     rcx, [rcx+10h]
0x1800095b8  mov     rax, [rcx]
0x1800095bb  mov     rax, [rax+8]
0x1800095bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c4  nop
0x1800095c5  add     rsp, 28h
0x1800095c9  retn
```

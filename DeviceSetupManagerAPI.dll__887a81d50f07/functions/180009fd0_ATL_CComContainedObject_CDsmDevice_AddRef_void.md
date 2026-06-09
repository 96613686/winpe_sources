# ATL::CComContainedObject<CDsmDevice>::AddRef(void)

- ea: `0x180009fd0`
- end: `0x180009fea`
- name: `?AddRef@?$CComContainedObject@VCDsmDevice@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDsmDevice>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180009fd0  sub     rsp, 28h
0x180009fd4  mov     rcx, [rcx+8]
0x180009fd8  mov     rax, [rcx]
0x180009fdb  mov     rax, [rax+8]
0x180009fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe4  nop
0x180009fe5  add     rsp, 28h
0x180009fe9  retn
```

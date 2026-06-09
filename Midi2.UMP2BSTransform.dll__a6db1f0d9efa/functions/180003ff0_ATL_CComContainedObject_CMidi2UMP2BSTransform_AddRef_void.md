# ATL::CComContainedObject<CMidi2UMP2BSTransform>::AddRef(void)

- ea: `0x180003ff0`
- end: `0x18000400a`
- name: `?AddRef@?$CComContainedObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2UMP2BSTransform>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003ff0  sub     rsp, 28h
0x180003ff4  mov     rcx, [rcx+8]
0x180003ff8  mov     rax, [rcx]
0x180003ffb  mov     rax, [rax+8]
0x180003fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004004  nop
0x180004005  add     rsp, 28h
0x180004009  retn
```

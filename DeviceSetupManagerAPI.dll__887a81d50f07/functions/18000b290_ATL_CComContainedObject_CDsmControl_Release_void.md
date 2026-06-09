# ATL::CComContainedObject<CDsmControl>::Release(void)

- ea: `0x18000b290`
- end: `0x18000b2aa`
- name: `?Release@?$CComContainedObject@VCDsmControl@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDsmControl>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x18000b290  sub     rsp, 28h
0x18000b294  mov     rcx, [rcx+8]
0x18000b298  mov     rax, [rcx]
0x18000b29b  mov     rax, [rax+10h]
0x18000b29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a4  nop
0x18000b2a5  add     rsp, 28h
0x18000b2a9  retn
```

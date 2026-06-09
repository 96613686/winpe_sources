# ATL::CComContainedObject<CConnectedUserStore>::Release(void)

- ea: `0x180011ad0`
- end: `0x180011aea`
- name: `?Release@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011af0`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180011ad0  sub     rsp, 28h
0x180011ad4  mov     rcx, [rcx+10h]
0x180011ad8  mov     rax, [rcx]
0x180011adb  mov     rax, [rax+10h]
0x180011adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae4  nop
0x180011ae5  add     rsp, 28h
0x180011ae9  retn
```

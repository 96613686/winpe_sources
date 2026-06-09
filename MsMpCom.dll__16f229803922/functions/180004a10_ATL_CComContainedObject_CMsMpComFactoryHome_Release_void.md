# ATL::CComContainedObject<CMsMpComFactoryHome>::Release(void)

- ea: `0x180004a10`
- end: `0x180004a2a`
- name: `?Release@?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMsMpComFactoryHome>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 56) + 16LL))(*(_QWORD *)(a1 - 56));
}

```

## disassembly

```asm
0x180004a10  sub     rsp, 28h
0x180004a14  mov     rcx, [rcx-38h]
0x180004a18  mov     rax, [rcx]
0x180004a1b  mov     rax, [rax+10h]
0x180004a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a24  nop
0x180004a25  add     rsp, 28h
0x180004a29  retn
```

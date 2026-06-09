# ATL::CComContainedObject<CMsMpComFactoryHome>::AddRef(void)

- ea: `0x180002fc0`
- end: `0x180002fda`
- name: `?AddRef@?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMsMpComFactoryHome>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 56) + 8LL))(*(_QWORD *)(a1 - 56));
}

```

## disassembly

```asm
0x180002fc0  sub     rsp, 28h
0x180002fc4  mov     rcx, [rcx-38h]
0x180002fc8  mov     rax, [rcx]
0x180002fcb  mov     rax, [rax+8]
0x180002fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd4  nop
0x180002fd5  add     rsp, 28h
0x180002fd9  retn
```

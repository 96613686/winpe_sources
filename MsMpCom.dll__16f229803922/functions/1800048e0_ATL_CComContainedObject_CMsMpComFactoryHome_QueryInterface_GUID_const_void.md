# ATL::CComContainedObject<CMsMpComFactoryHome>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800048e0`
- end: `0x1800048f9`
- name: `?QueryInterface@?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMsMpComFactoryHome>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 - 56))(*(_QWORD *)(a1 - 56));
}

```

## disassembly

```asm
0x1800048e0  sub     rsp, 28h
0x1800048e4  mov     rcx, [rcx-38h]
0x1800048e8  mov     rax, [rcx]
0x1800048eb  mov     rax, [rax]
0x1800048ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f3  nop
0x1800048f4  add     rsp, 28h
0x1800048f8  retn
```

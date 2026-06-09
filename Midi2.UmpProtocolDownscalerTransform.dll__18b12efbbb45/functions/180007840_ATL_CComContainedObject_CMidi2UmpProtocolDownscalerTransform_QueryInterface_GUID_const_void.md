# ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007840`
- end: `0x180007859`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2UmpProtocolDownscalerTransform>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180007840  sub     rsp, 28h
0x180007844  mov     rcx, [rcx+8]
0x180007848  mov     rax, [rcx]
0x18000784b  mov     rax, [rax]
0x18000784e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007853  nop
0x180007854  add     rsp, 28h
0x180007858  retn
```

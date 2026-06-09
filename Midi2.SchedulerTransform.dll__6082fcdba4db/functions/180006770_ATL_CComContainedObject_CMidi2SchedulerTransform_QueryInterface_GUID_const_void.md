# ATL::CComContainedObject<CMidi2SchedulerTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006770`
- end: `0x180006789`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2SchedulerTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2SchedulerTransform>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180006770  sub     rsp, 28h
0x180006774  mov     rcx, [rcx+8]
0x180006778  mov     rax, [rcx]
0x18000677b  mov     rax, [rax]
0x18000677e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006783  nop
0x180006784  add     rsp, 28h
0x180006788  retn
```

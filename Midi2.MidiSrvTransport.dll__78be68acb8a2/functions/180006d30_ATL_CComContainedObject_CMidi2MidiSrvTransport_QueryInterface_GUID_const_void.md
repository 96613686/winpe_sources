# ATL::CComContainedObject<CMidi2MidiSrvTransport>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006d30`
- end: `0x180006d49`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2MidiSrvTransport>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180006d30  sub     rsp, 28h
0x180006d34  mov     rcx, [rcx+8]
0x180006d38  mov     rax, [rcx]
0x180006d3b  mov     rax, [rax]
0x180006d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d43  nop
0x180006d44  add     rsp, 28h
0x180006d48  retn
```

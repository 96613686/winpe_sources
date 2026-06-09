# ATL::CComContainedObject<CMidi2MidiSrvTransport>::AddRef(void)

- ea: `0x1800046b0`
- end: `0x1800046ca`
- name: `?AddRef@?$CComContainedObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2MidiSrvTransport>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800046b0  sub     rsp, 28h
0x1800046b4  mov     rcx, [rcx+8]
0x1800046b8  mov     rax, [rcx]
0x1800046bb  mov     rax, [rax+8]
0x1800046bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c4  nop
0x1800046c5  add     rsp, 28h
0x1800046c9  retn
```

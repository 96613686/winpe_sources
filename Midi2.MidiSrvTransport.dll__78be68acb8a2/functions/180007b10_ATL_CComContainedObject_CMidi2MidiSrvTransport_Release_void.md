# ATL::CComContainedObject<CMidi2MidiSrvTransport>::Release(void)

- ea: `0x180007b10`
- end: `0x180007b2a`
- name: `?Release@?$CComContainedObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2MidiSrvTransport>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180007b10  sub     rsp, 28h
0x180007b14  mov     rcx, [rcx+8]
0x180007b18  mov     rax, [rcx]
0x180007b1b  mov     rax, [rax+10h]
0x180007b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b24  nop
0x180007b25  add     rsp, 28h
0x180007b29  retn
```

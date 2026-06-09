# ATL::CComContainedObject<CMidi2DiagnosticsTransport>::Release(void)

- ea: `0x180008c60`
- end: `0x180008c7a`
- name: `?Release@?$CComContainedObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2DiagnosticsTransport>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180008c60  sub     rsp, 28h
0x180008c64  mov     rcx, [rcx+8]
0x180008c68  mov     rax, [rcx]
0x180008c6b  mov     rax, [rax+10h]
0x180008c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c74  nop
0x180008c75  add     rsp, 28h
0x180008c79  retn
```

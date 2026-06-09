# ATL::CComContainedObject<CMidi2DiagnosticsTransport>::AddRef(void)

- ea: `0x180005810`
- end: `0x18000582a`
- name: `?AddRef@?$CComContainedObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2DiagnosticsTransport>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005810  sub     rsp, 28h
0x180005814  mov     rcx, [rcx+8]
0x180005818  mov     rax, [rcx]
0x18000581b  mov     rax, [rax+8]
0x18000581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005824  nop
0x180005825  add     rsp, 28h
0x180005829  retn
```

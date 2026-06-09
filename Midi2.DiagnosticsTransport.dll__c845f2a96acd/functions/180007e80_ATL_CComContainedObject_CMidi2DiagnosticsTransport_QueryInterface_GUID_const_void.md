# ATL::CComContainedObject<CMidi2DiagnosticsTransport>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007e80`
- end: `0x180007e99`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2DiagnosticsTransport>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180007e80  sub     rsp, 28h
0x180007e84  mov     rcx, [rcx+8]
0x180007e88  mov     rax, [rcx]
0x180007e8b  mov     rax, [rax]
0x180007e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e93  nop
0x180007e94  add     rsp, 28h
0x180007e98  retn
```

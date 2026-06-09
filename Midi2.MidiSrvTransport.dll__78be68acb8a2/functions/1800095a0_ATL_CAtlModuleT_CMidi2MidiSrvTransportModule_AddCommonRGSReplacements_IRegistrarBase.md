# ATL::CAtlModuleT<CMidi2MidiSrvTransportModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800095a0`
- end: `0x1800095c7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2MidiSrvTransportModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2MidiSrvTransportModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}");
}

```

## disassembly

```asm
0x1800095a0  sub     rsp, 28h
0x1800095a4  mov     rcx, rdx
0x1800095a7  mov     rax, [rdx]
0x1800095aa  lea     r8, a15c88c784cb349; "{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}"
0x1800095b1  lea     rdx, aAppid; "APPID"
0x1800095b8  mov     rax, [rax+18h]
0x1800095bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c1  nop
0x1800095c2  add     rsp, 28h
0x1800095c6  retn
```

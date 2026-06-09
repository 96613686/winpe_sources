# ATL::CAtlModuleT<CMidi2DiagnosticsTransportModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000a780`
- end: `0x18000a7a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2DiagnosticsTransportModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2DiagnosticsTransportModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{578daa61-200b-4622-8cb1-6d8a6fa93c17}");
}

```

## disassembly

```asm
0x18000a780  sub     rsp, 28h
0x18000a784  mov     rcx, rdx
0x18000a787  mov     rax, [rdx]
0x18000a78a  lea     r8, a578daa61200b46; "{578daa61-200b-4622-8cb1-6d8a6fa93c17}"
0x18000a791  lea     rdx, aAppid; "APPID"
0x18000a798  mov     rax, [rax+18h]
0x18000a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a1  nop
0x18000a7a2  add     rsp, 28h
0x18000a7a6  retn
```

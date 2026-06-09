# ATL::CAtlModuleT<CTieringEngineService>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140002d30`
- end: `0x140002d57`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCTieringEngineService@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CTieringEngineService>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{6DF5BCF4-22E9-446D-8763-A2C7677ECF7D}");
}

```

## disassembly

```asm
0x140002d30  sub     rsp, 28h
0x140002d34  mov     rcx, rdx
0x140002d37  mov     rax, [rdx]
0x140002d3a  lea     r8, a6df5bcf422e944; "{6DF5BCF4-22E9-446D-8763-A2C7677ECF7D}"
0x140002d41  lea     rdx, aAppid; "APPID"
0x140002d48  mov     rax, [rax+18h]
0x140002d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d51  nop
0x140002d52  add     rsp, 28h
0x140002d56  retn
```

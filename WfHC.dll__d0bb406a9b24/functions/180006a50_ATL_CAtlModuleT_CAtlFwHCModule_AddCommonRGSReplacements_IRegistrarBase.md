# ATL::CAtlModuleT<CAtlFwHCModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180006a50`
- end: `0x180006a77`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCAtlFwHCModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CAtlFwHCModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_1800117E0);
}

```

## disassembly

```asm
0x180006a50  sub     rsp, 28h
0x180006a54  mov     rcx, rdx
0x180006a57  mov     rax, [rdx]
0x180006a5a  lea     r8, qword_1800117E0
0x180006a61  lea     rdx, aAppid_0; "APPID"
0x180006a68  mov     rax, [rax+18h]
0x180006a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a71  nop
0x180006a72  add     rsp, 28h
0x180006a76  retn
```

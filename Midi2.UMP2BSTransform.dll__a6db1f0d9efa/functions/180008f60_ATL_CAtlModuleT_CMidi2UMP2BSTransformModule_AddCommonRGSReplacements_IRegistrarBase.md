# ATL::CAtlModuleT<CMidi2UMP2BSTransformModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008f60`
- end: `0x180008f87`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2UMP2BSTransformModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2UMP2BSTransformModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}");
}

```

## disassembly

```asm
0x180008f60  sub     rsp, 28h
0x180008f64  mov     rcx, rdx
0x180008f67  mov     rax, [rdx]
0x180008f6a  lea     r8, a5a2e778a245042; "{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}"
0x180008f71  lea     rdx, aAppid; "APPID"
0x180008f78  mov     rax, [rax+18h]
0x180008f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f81  nop
0x180008f82  add     rsp, 28h
0x180008f86  retn
```

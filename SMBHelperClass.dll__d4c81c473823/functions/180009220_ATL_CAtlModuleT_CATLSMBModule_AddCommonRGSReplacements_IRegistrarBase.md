# ATL::CAtlModuleT<CATLSMBModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180009220`
- end: `0x180009247`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCATLSMBModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CATLSMBModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}");
}

```

## disassembly

```asm
0x180009220  sub     rsp, 28h
0x180009224  mov     rcx, rdx
0x180009227  mov     rax, [rdx]
0x18000922a  lea     r8, a71962dd65a514c; "{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}"
0x180009231  lea     rdx, aAppid; "APPID"
0x180009238  mov     rax, [rax+18h]
0x18000923c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009241  nop
0x180009242  add     rsp, 28h
0x180009246  retn
```

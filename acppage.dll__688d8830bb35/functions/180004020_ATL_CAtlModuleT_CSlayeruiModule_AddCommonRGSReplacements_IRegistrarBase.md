# ATL::CAtlModuleT<CSlayeruiModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180004020`
- end: `0x18000403d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCSlayeruiModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CSlayeruiModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_1800196B4);
}

```

## disassembly

```asm
0x180004020  mov     rax, [rdx]
0x180004023  lea     r8, byte_1800196B4
0x18000402a  mov     rcx, rdx
0x18000402d  lea     rdx, aAppid; "APPID"
0x180004034  mov     rax, [rax+18h]
0x180004038  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

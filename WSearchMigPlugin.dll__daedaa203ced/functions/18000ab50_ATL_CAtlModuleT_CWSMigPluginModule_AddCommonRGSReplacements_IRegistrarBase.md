# ATL::CAtlModuleT<CWSMigPluginModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000ab50`
- end: `0x18000ab80`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCWSMigPluginModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `48`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CWSMigPluginModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_18001B074);
}

```

## disassembly

```asm
0x18000ab50  sub     rsp, 38h
0x18000ab54  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000ab5d  mov     rcx, rdx
0x18000ab60  mov     rax, [rdx]
0x18000ab63  lea     r8, word_18001B074
0x18000ab6a  lea     rdx, aAppid_0; "APPID"
0x18000ab71  mov     rax, [rax+18h]
0x18000ab75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab7a  nop
0x18000ab7b  add     rsp, 38h
0x18000ab7f  retn
```

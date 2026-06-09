# ATL::CAtlModuleT<DmrcComServer>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180012b90`
- end: `0x180012bad`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VDmrcComServer@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<DmrcComServer>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_180017E8C);
}

```

## disassembly

```asm
0x180012b90  mov     rax, [rdx]
0x180012b93  lea     r8, word_180017E8C
0x180012b9a  mov     rcx, rdx
0x180012b9d  lea     rdx, aAppid; "APPID"
0x180012ba4  mov     rax, [rax+18h]
0x180012ba8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

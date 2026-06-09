# ATL::CAtlModuleT<CMpComExportsModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002280`
- end: `0x1800022a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMpComExportsModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMpComExportsModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000D2B8);
}

```

## disassembly

```asm
0x180002280  sub     rsp, 28h
0x180002284  mov     rcx, rdx
0x180002287  mov     rax, [rdx]
0x18000228a  lea     r8, qword_18000D2B8
0x180002291  lea     rdx, aAppid; "APPID"
0x180002298  mov     rax, [rax+18h]
0x18000229c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a1  nop
0x1800022a2  add     rsp, 28h
0x1800022a6  retn
```

# ATL::CAtlModuleT<CDsmApiModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008e40`
- end: `0x180008e67`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCDsmApiModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CDsmApiModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180013330);
}

```

## disassembly

```asm
0x180008e40  sub     rsp, 28h
0x180008e44  mov     rcx, rdx
0x180008e47  mov     rax, [rdx]
0x180008e4a  lea     r8, qword_180013330
0x180008e51  lea     rdx, aAppid; "APPID"
0x180008e58  mov     rax, [rax+18h]
0x180008e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e61  nop
0x180008e62  add     rsp, 28h
0x180008e66  retn
```

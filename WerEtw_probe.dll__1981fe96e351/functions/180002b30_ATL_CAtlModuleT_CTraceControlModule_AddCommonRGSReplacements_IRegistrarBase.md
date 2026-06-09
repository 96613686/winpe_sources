# ATL::CAtlModuleT<CTraceControlModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002b30`
- end: `0x180002b57`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCTraceControlModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CTraceControlModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_18002D338);
}

```

## disassembly

```asm
0x180002b30  sub     rsp, 28h
0x180002b34  mov     rcx, rdx
0x180002b37  mov     rax, [rdx]
0x180002b3a  lea     r8, word_18002D338
0x180002b41  lea     rdx, aAppid; "APPID"
0x180002b48  mov     rax, [rax+18h]
0x180002b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b51  nop
0x180002b52  add     rsp, 28h
0x180002b56  retn
```

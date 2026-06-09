# ATL::CAtlModuleT<CRAServerModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x14000cc20`
- end: `0x14000cc47`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCRAServerModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CRAServerModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}");
}

```

## disassembly

```asm
0x14000cc20  sub     rsp, 28h
0x14000cc24  mov     rcx, rdx
0x14000cc27  mov     rax, [rdx]
0x14000cc2a  lea     r8, aF8fd03a6Ddd94c; "{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}"
0x14000cc31  lea     rdx, aAppid; "APPID"
0x14000cc38  mov     rax, [rax+18h]
0x14000cc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc41  nop
0x14000cc42  add     rsp, 28h
0x14000cc46  retn
```

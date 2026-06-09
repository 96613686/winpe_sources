# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18001f2c0`
- end: `0x18001f2e7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18002FDE4);
}

```

## disassembly

```asm
0x18001f2c0  sub     rsp, 28h
0x18001f2c4  mov     rcx, rdx
0x18001f2c7  mov     rax, [rdx]
0x18001f2ca  lea     r8, dword_18002FDE4
0x18001f2d1  lea     rdx, aAppid; "APPID"
0x18001f2d8  mov     rax, [rax+18h]
0x18001f2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2e1  nop
0x18001f2e2  add     rsp, 28h
0x18001f2e6  retn
```

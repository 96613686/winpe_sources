# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003110`
- end: `0x180003137`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18000F72C);
}

```

## disassembly

```asm
0x180003110  sub     rsp, 28h
0x180003114  mov     rcx, rdx
0x180003117  mov     rax, [rdx]
0x18000311a  lea     r8, dword_18000F72C
0x180003121  lea     rdx, aAppid; "APPID"
0x180003128  mov     rax, [rax+18h]
0x18000312c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003131  nop
0x180003132  add     rsp, 28h
0x180003136  retn
```

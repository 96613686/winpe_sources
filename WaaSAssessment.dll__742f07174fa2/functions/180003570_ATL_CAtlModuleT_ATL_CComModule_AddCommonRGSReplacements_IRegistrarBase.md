# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003570`
- end: `0x180003597`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18001D62C);
}

```

## disassembly

```asm
0x180003570  sub     rsp, 28h
0x180003574  mov     rcx, rdx
0x180003577  mov     rax, [rdx]
0x18000357a  lea     r8, dword_18001D62C
0x180003581  lea     rdx, aAppid; "APPID"
0x180003588  mov     rax, [rax+18h]
0x18000358c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003591  nop
0x180003592  add     rsp, 28h
0x180003596  retn
```

# ATL::CAtlModuleT<Host>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140006bf0`
- end: `0x140006c0d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VHost@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<Host>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_140009864);
}

```

## disassembly

```asm
0x140006bf0  mov     rax, [rdx]
0x140006bf3  lea     r8, dword_140009864
0x140006bfa  mov     rcx, rdx
0x140006bfd  lea     rdx, aAppid; "APPID"
0x140006c04  mov     rax, [rax+18h]
0x140006c08  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

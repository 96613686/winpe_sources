# ATL::CAtlModuleT<CUICOMModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002630`
- end: `0x18000264d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCUICOMModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CUICOMModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{E8054D20-497D-4E16-BF41-6E69FCD381A5}");
}

```

## disassembly

```asm
0x180002630  mov     rax, [rdx]
0x180002633  lea     r8, aE8054d20497d4e; "{E8054D20-497D-4E16-BF41-6E69FCD381A5}"
0x18000263a  mov     rcx, rdx
0x18000263d  lea     rdx, aAppid; "APPID"
0x180002644  mov     rax, [rax+18h]
0x180002648  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

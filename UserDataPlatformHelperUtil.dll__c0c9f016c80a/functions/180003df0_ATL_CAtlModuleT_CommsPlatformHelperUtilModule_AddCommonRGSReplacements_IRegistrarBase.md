# ATL::CAtlModuleT<CommsPlatformHelperUtilModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003df0`
- end: `0x180003e0d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCommsPlatformHelperUtilModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CommsPlatformHelperUtilModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const OLECHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_18000D1D0);
}

```

## disassembly

```asm
0x180003df0  mov     rax, [rdx]
0x180003df3  lea     r8, word_18000D1D0
0x180003dfa  mov     rcx, rdx
0x180003dfd  lea     rdx, aAppid; "APPID"
0x180003e04  mov     rax, [rax+18h]
0x180003e08  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

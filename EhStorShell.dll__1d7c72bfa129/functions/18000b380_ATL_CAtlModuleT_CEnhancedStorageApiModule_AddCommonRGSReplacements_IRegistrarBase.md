# ATL::CAtlModuleT<CEnhancedStorageApiModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000b380`
- end: `0x18000b3a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCEnhancedStorageApiModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CEnhancedStorageApiModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{CC70FEAD-94B9-4F76-88CC-004BB068ACDF}");
}

```

## disassembly

```asm
0x18000b380  sub     rsp, 28h
0x18000b384  mov     rcx, rdx
0x18000b387  mov     rax, [rdx]
0x18000b38a  lea     r8, aCc70fead94b94f; "{CC70FEAD-94B9-4F76-88CC-004BB068ACDF}"
0x18000b391  lea     rdx, aAppid; "APPID"
0x18000b398  mov     rax, [rax+18h]
0x18000b39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a1  nop
0x18000b3a2  add     rsp, 28h
0x18000b3a6  retn
```

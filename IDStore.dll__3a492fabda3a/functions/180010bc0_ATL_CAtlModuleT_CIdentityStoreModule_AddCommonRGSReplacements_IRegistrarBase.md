# ATL::CAtlModuleT<CIdentityStoreModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180010bc0`
- end: `0x180010be7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCIdentityStoreModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CIdentityStoreModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &byte_18001F5B0);
}

```

## disassembly

```asm
0x180010bc0  sub     rsp, 28h
0x180010bc4  mov     rcx, rdx
0x180010bc7  mov     rax, [rdx]
0x180010bca  lea     r8, byte_18001F5B0
0x180010bd1  lea     rdx, aAppid; "APPID"
0x180010bd8  mov     rax, [rax+18h]
0x180010bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be1  nop
0x180010be2  add     rsp, 28h
0x180010be6  retn
```

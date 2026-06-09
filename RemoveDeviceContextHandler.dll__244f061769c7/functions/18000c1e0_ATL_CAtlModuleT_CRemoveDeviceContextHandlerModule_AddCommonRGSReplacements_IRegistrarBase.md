# ATL::CAtlModuleT<CRemoveDeviceContextHandlerModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000c1e0`
- end: `0x18000c1fd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCRemoveDeviceContextHandlerModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CRemoveDeviceContextHandlerModule>::AddCommonRGSReplacements(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180010930);
}

```

## disassembly

```asm
0x18000c1e0  mov     rax, [rdx]
0x18000c1e3  lea     r8, qword_180010930
0x18000c1ea  mov     rcx, rdx
0x18000c1ed  lea     rdx, aAppid; "APPID"
0x18000c1f4  mov     rax, [rax+18h]
0x18000c1f8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

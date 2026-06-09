# ATL::CAtlModuleT<CMessagingServiceDll>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002d30`
- end: `0x180002d57`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMessagingServiceDll@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMessagingServiceDll>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000F388);
}

```

## disassembly

```asm
0x180002d30  sub     rsp, 28h
0x180002d34  mov     rcx, rdx
0x180002d37  mov     rax, [rdx]
0x180002d3a  lea     r8, qword_18000F388
0x180002d41  lea     rdx, aAppid; "APPID"
0x180002d48  mov     rax, [rax+18h]
0x180002d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d51  nop
0x180002d52  add     rsp, 28h
0x180002d56  retn
```

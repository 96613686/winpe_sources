# ATL::CAtlModuleT<CVSFileHandlerModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180001550`
- end: `0x180001568`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCVSFileHandlerModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CVSFileHandlerModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, void *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &unk_1800340EC);
}

```

## disassembly

```asm
0x180001550  mov     rax, [rdx]
0x180001553  lea     r8, unk_1800340EC
0x18000155a  mov     rcx, rdx
0x18000155d  lea     rdx, aAppid; "APPID"
0x180001564  jmp     qword ptr [rax+18h]
```

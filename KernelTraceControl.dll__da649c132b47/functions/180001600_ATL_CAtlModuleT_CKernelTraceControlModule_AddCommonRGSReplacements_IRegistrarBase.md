# ATL::CAtlModuleT<CKernelTraceControlModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180001600`
- end: `0x18000161f`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCKernelTraceControlModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CKernelTraceControlModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18002BEF8);
}

```

## disassembly

```asm
0x180001600  mov     rax, [rdx]
0x180001603  lea     r8, qword_18002BEF8
0x18000160a  mov     rcx, rdx
0x18000160d  lea     rdx, aAppid; "APPID"
0x180001614  mov     rax, [rax+18h]
0x180001618  jmp     cs:__guard_dispatch_icall_fptr
```

# ATL::CAtlModuleT<CMidi2BS2UMPTransformModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008ed0`
- end: `0x180008ef7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2BS2UMPTransformModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2BS2UMPTransformModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{04CE96FD-36B2-41ED-8A3E-A5606951F766}");
}

```

## disassembly

```asm
0x180008ed0  sub     rsp, 28h
0x180008ed4  mov     rcx, rdx
0x180008ed7  mov     rax, [rdx]
0x180008eda  lea     r8, a04ce96fd36b241; "{04CE96FD-36B2-41ED-8A3E-A5606951F766}"
0x180008ee1  lea     rdx, aAppid; "APPID"
0x180008ee8  mov     rax, [rax+18h]
0x180008eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef1  nop
0x180008ef2  add     rsp, 28h
0x180008ef6  retn
```

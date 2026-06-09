# ATL::CAtlModuleT<CMidi2UmpProtocolDownscalerTransformModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000a140`
- end: `0x18000a167`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCMidi2UmpProtocolDownscalerTransformModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CMidi2UmpProtocolDownscalerTransformModule>::AddCommonRGSReplacements(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{1b2e6e7f-e780-4406-92e0-14f4b8b04552}");
}

```

## disassembly

```asm
0x18000a140  sub     rsp, 28h
0x18000a144  mov     rcx, rdx
0x18000a147  mov     rax, [rdx]
0x18000a14a  lea     r8, a1b2e6e7fE78044; "{1b2e6e7f-e780-4406-92e0-14f4b8b04552}"
0x18000a151  lea     rdx, aAppid; "APPID"
0x18000a158  mov     rax, [rax+18h]
0x18000a15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a161  nop
0x18000a162  add     rsp, 28h
0x18000a166  retn
```

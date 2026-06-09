# ATL::CAtlModuleT<CPenImcModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180001950`
- end: `0x18000196f`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCPenImcModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CPenImcModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{953E4863-7AD1-4DAE-B2BD-108F1D57967B}");
}

```

## disassembly

```asm
0x180001950  mov     rax, [rdx]
0x180001953  lea     r8, a953e48637ad14d; "{953E4863-7AD1-4DAE-B2BD-108F1D57967B}"
0x18000195a  mov     rcx, rdx
0x18000195d  lea     rdx, aAppid; "APPID"
0x180001964  mov     rax, [rax+18h]
0x180001968  jmp     cs:__guard_dispatch_icall_fptr
```

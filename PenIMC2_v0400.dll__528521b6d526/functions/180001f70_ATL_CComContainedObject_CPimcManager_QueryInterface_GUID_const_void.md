# ATL::CComContainedObject<CPimcManager>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001f70`
- end: `0x180001f81`
- name: `?QueryInterface@?$CComContainedObject@VCPimcManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPimcManager>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180001f70  mov     rcx, [rcx+8]
0x180001f74  mov     rax, [rcx]
0x180001f77  mov     rax, [rax]
0x180001f7a  jmp     cs:__guard_dispatch_icall_fptr
```

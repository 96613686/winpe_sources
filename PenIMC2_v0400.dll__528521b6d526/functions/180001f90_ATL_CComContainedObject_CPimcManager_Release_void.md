# ATL::CComContainedObject<CPimcManager>::Release(void)

- ea: `0x180001f90`
- end: `0x180001fa2`
- name: `?Release@?$CComContainedObject@VCPimcManager@@@ATL@@UEAAKXZ`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPimcManager>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180001f90  mov     rcx, [rcx+8]
0x180001f94  mov     rax, [rcx]
0x180001f97  mov     rax, [rax+10h]
0x180001f9b  jmp     cs:__guard_dispatch_icall_fptr
```

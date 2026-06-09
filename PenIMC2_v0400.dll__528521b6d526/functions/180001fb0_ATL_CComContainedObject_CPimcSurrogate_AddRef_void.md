# ATL::CComContainedObject<CPimcSurrogate>::AddRef(void)

- ea: `0x180001fb0`
- end: `0x180001fc2`
- name: `?AddRef@?$CComContainedObject@VCPimcSurrogate@@@ATL@@UEAAKXZ`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPimcSurrogate>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180001fb0  mov     rcx, [rcx+8]
0x180001fb4  mov     rax, [rcx]
0x180001fb7  mov     rax, [rax+8]
0x180001fbb  jmp     cs:__guard_dispatch_icall_fptr
```

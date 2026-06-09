# ATL::CComContainedObject<CMidi2BS2UMPTransform>::Release(void)

- ea: `0x1800073b0`
- end: `0x1800073ca`
- name: `?Release@?$CComContainedObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2BS2UMPTransform>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800073b0  sub     rsp, 28h
0x1800073b4  mov     rcx, [rcx+8]
0x1800073b8  mov     rax, [rcx]
0x1800073bb  mov     rax, [rax+10h]
0x1800073bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c4  nop
0x1800073c5  add     rsp, 28h
0x1800073c9  retn
```

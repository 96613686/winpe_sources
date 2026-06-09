# ATL::CComContainedObject<CMidi2BS2UMPTransform>::AddRef(void)

- ea: `0x180003f60`
- end: `0x180003f7a`
- name: `?AddRef@?$CComContainedObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2BS2UMPTransform>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003f60  sub     rsp, 28h
0x180003f64  mov     rcx, [rcx+8]
0x180003f68  mov     rax, [rcx]
0x180003f6b  mov     rax, [rax+8]
0x180003f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f74  nop
0x180003f75  add     rsp, 28h
0x180003f79  retn
```

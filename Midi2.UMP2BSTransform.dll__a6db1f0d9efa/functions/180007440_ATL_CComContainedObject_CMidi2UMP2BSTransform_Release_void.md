# ATL::CComContainedObject<CMidi2UMP2BSTransform>::Release(void)

- ea: `0x180007440`
- end: `0x18000745a`
- name: `?Release@?$CComContainedObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2UMP2BSTransform>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180007440  sub     rsp, 28h
0x180007444  mov     rcx, [rcx+8]
0x180007448  mov     rax, [rcx]
0x18000744b  mov     rax, [rax+10h]
0x18000744f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007454  nop
0x180007455  add     rsp, 28h
0x180007459  retn
```

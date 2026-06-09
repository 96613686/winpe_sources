# ATL::CComContainedObject<CMidi2SchedulerTransform>::AddRef(void)

- ea: `0x180004100`
- end: `0x18000411a`
- name: `?AddRef@?$CComContainedObject@VCMidi2SchedulerTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2SchedulerTransform>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180004100  sub     rsp, 28h
0x180004104  mov     rcx, [rcx+8]
0x180004108  mov     rax, [rcx]
0x18000410b  mov     rax, [rax+8]
0x18000410f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004114  nop
0x180004115  add     rsp, 28h
0x180004119  retn
```

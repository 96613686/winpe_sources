# ATL::CComContainedObject<CMidi2SchedulerTransform>::Release(void)

- ea: `0x180007550`
- end: `0x18000756a`
- name: `?Release@?$CComContainedObject@VCMidi2SchedulerTransform@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2SchedulerTransform>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180007550  sub     rsp, 28h
0x180007554  mov     rcx, [rcx+8]
0x180007558  mov     rax, [rcx]
0x18000755b  mov     rax, [rax+10h]
0x18000755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007564  nop
0x180007565  add     rsp, 28h
0x180007569  retn
```

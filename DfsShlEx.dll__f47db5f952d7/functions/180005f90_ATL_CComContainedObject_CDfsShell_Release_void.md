# ATL::CComContainedObject<CDfsShell>::Release(void)

- ea: `0x180005f90`
- end: `0x180005faa`
- name: `?Release@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005fb0`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180005f90  sub     rsp, 28h
0x180005f94  mov     rcx, [rcx+10h]
0x180005f98  mov     rax, [rcx]
0x180005f9b  mov     rax, [rax+10h]
0x180005f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa4  nop
0x180005fa5  add     rsp, 28h
0x180005fa9  retn
```

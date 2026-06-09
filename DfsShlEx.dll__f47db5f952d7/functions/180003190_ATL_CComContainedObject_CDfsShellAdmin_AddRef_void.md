# ATL::CComContainedObject<CDfsShellAdmin>::AddRef(void)

- ea: `0x180003190`
- end: `0x1800031aa`
- name: `?AddRef@?$CComContainedObject@VCDfsShellAdmin@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShellAdmin>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003190  sub     rsp, 28h
0x180003194  mov     rcx, [rcx+8]
0x180003198  mov     rax, [rcx]
0x18000319b  mov     rax, [rax+8]
0x18000319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a4  nop
0x1800031a5  add     rsp, 28h
0x1800031a9  retn
```

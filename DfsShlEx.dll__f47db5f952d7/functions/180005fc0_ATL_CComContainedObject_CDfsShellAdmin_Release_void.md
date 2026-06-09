# ATL::CComContainedObject<CDfsShellAdmin>::Release(void)

- ea: `0x180005fc0`
- end: `0x180005fda`
- name: `?Release@?$CComContainedObject@VCDfsShellAdmin@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShellAdmin>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005fc0  sub     rsp, 28h
0x180005fc4  mov     rcx, [rcx+8]
0x180005fc8  mov     rax, [rcx]
0x180005fcb  mov     rax, [rax+10h]
0x180005fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd4  nop
0x180005fd5  add     rsp, 28h
0x180005fd9  retn
```

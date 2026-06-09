# ATL::CComContainedObject<CBrowserCap>::Release(void)

- ea: `0x180005c30`
- end: `0x180005c4a`
- name: `?Release@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005c50`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180005c30  sub     rsp, 28h
0x180005c34  mov     rcx, [rcx+10h]
0x180005c38  mov     rax, [rcx]
0x180005c3b  mov     rax, [rax+10h]
0x180005c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c44  nop
0x180005c45  add     rsp, 28h
0x180005c49  retn
```

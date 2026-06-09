# ATL::CComContainedObject<CBrowserCap>::AddRef(void)

- ea: `0x180002a40`
- end: `0x180002a5a`
- name: `?AddRef@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002a60`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180002a40  sub     rsp, 28h
0x180002a44  mov     rcx, [rcx+10h]
0x180002a48  mov     rax, [rcx]
0x180002a4b  mov     rax, [rax+8]
0x180002a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a54  nop
0x180002a55  add     rsp, 28h
0x180002a59  retn
```

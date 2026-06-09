# ATL::CComContainedObject<CBrowserCap>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004d60`
- end: `0x180004d79`
- name: `?QueryInterface@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004d80`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180004d60  sub     rsp, 28h
0x180004d64  mov     rcx, [rcx+10h]
0x180004d68  mov     rax, [rcx]
0x180004d6b  mov     rax, [rax]
0x180004d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d73  nop
0x180004d74  add     rsp, 28h
0x180004d78  retn
```

# ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::AddRef(void)

- ea: `0x180004340`
- end: `0x18000435a`
- name: `?AddRef@?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180004340  sub     rsp, 28h
0x180004344  mov     rcx, [rcx+8]
0x180004348  mov     rax, [rcx]
0x18000434b  mov     rax, [rax+8]
0x18000434f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004354  nop
0x180004355  add     rsp, 28h
0x180004359  retn
```

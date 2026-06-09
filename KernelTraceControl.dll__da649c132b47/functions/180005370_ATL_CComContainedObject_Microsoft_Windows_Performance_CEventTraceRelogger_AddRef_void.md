# ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::AddRef(void)

- ea: `0x180005370`
- end: `0x180005382`
- name: `?AddRef@?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005370  mov     rcx, [rcx+8]
0x180005374  mov     rax, [rcx]
0x180005377  mov     rax, [rax+8]
0x18000537b  jmp     cs:__guard_dispatch_icall_fptr
```

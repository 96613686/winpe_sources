# ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::Release(void)

- ea: `0x180004680`
- end: `0x180004690`
- name: `?Release@?$CComContainedObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180004680  mov     rcx, [rcx+8]
0x180004684  mov     rax, [rcx]
0x180004687  mov     rax, [rax+10h]
0x18000468b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::AddRef(void)

- ea: `0x180003e50`
- end: `0x180003e60`
- name: `?AddRef@?$CComContainedObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<HtmlDocForParsingSiteUnmarshaller>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180003e50  mov     rcx, [rcx+8]
0x180003e54  mov     rax, [rcx]
0x180003e57  mov     rax, [rax+8]
0x180003e5b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

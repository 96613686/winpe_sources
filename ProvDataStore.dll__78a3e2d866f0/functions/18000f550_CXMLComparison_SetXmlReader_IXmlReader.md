# CXMLComparison::SetXmlReader(IXmlReader *)

- ea: `0x18000f550`
- end: `0x18000f56e`
- name: `?SetXmlReader@CXMLComparison@@UEAAJPEAUIXmlReader@@@Z`
- size: `30`
- prototype: `__int64 __fastcall(CXMLComparison *__hidden this, struct IXmlReader *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CXMLComparison::SetXmlReader(CXMLComparison *this, struct IXmlReader *a2)
{
  *((_QWORD *)this + 1) = a2;
  ((void (__fastcall *)(struct IXmlReader *))a2->lpVtbl->AddRef)(a2);
  return 0;
}

```

## disassembly

```asm
0x18000f550  sub     rsp, 28h
0x18000f554  mov     [rcx+8], rdx
0x18000f558  mov     rcx, rdx
0x18000f55b  mov     rax, [rdx]
0x18000f55e  mov     rax, [rax+8]
0x18000f562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f567  xor     eax, eax
0x18000f569  add     rsp, 28h
0x18000f56d  retn
```

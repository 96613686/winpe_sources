# XPathQueryStringCompiler::Dispatch(Node *)

- ea: `0x18000835c`
- end: `0x180008371`
- name: `?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z`
- size: `21`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Node *)`
- caller_count: `17`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001b20`
- `0x180001bc0`
- `0x180001dc0`
- `0x180001fc0`
- `0x1800080b8`
- `0x180008e50`
- `0x180009164`
- `0x180009390`
- `0x1800094f4`
- `0x1800096d8`
- `0x1800097cc`
- `0x180009890`
- `0x180009b1c`
- `0x180009bfc`
- `0x180009d84`
- `0x180009f24`
- `0x18000a094`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::Dispatch(XPathQueryStringCompiler *this, struct Node *a2)
{
  return ((__int64 (__fastcall *)(struct Node *, XPathQueryStringCompiler *))a2->lpVtbl->AddRef)(a2, this);
}

```

## disassembly

```asm
0x18000835c  mov     rax, [rdx]
0x18000835f  mov     r8, rdx
0x180008362  mov     rdx, rcx
0x180008365  mov     rcx, r8
0x180008368  mov     rax, [rax+8]
0x18000836c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

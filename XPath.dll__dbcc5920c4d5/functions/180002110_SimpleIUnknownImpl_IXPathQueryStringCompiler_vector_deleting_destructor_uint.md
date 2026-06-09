# SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vector deleting destructor'(uint)

- ea: `0x180002110`
- end: `0x180002149`
- name: `??_E?$SimpleIUnknownImpl@UIXPathQueryStringCompiler@@@@UEAAPEAXI@Z`
- size: `57`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010b8`
- `0x180002110`
- `0x180002398`

## pseudocode

```c
_QWORD *__fastcall SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vector deleting destructor'(_QWORD *Block, char a2)
{
  *Block = &SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable';
  ModuleRefCounter::Release();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_0], rbx
0x180002115  push    rdi
0x180002116  sub     rsp, 20h
0x18000211a  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathQueryStringCompiler@@@@6B@; const SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable'
0x180002121  mov     ebx, edx
0x180002123  mov     [rcx], rax
0x180002126  mov     rdi, rcx
0x180002129  call    ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
0x18000212e  test    bl, 1
0x180002131  jz      short loc_18000213B
0x180002133  mov     rcx, rdi; Block
0x180002136  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000213b  mov     rbx, [rsp+28h+arg_0]
0x180002140  mov     rax, rdi
0x180002143  add     rsp, 20h
0x180002147  pop     rdi
0x180002148  retn
```

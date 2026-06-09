# SimpleIUnknownImpl<IXPathEvaluationContext>::`scalar deleting destructor'(uint)

- ea: `0x1800034f0`
- end: `0x180003529`
- name: `??_G?$SimpleIUnknownImpl@UIXPathEvaluationContext@@@@UEAAPEAXI@Z`
- size: `57`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800010b8`
- `0x180002398`
- `0x1800034f0`

## pseudocode

```c
_QWORD *__fastcall SimpleIUnknownImpl<IXPathEvaluationContext>::`scalar deleting destructor'(_QWORD *Block, char a2)
{
  *Block = &SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable';
  ModuleRefCounter::Release();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800034f0  mov     [rsp+arg_0], rbx
0x1800034f5  push    rdi
0x1800034f6  sub     rsp, 20h
0x1800034fa  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathEvaluationContext@@@@6B@; const SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable'
0x180003501  mov     ebx, edx
0x180003503  mov     [rcx], rax
0x180003506  mov     rdi, rcx
0x180003509  call    ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
0x18000350e  test    bl, 1
0x180003511  jz      short loc_18000351B
0x180003513  mov     rcx, rdi; Block
0x180003516  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000351b  mov     rbx, [rsp+28h+arg_0]
0x180003520  mov     rax, rdi
0x180003523  add     rsp, 20h
0x180003527  pop     rdi
0x180003528  retn
```

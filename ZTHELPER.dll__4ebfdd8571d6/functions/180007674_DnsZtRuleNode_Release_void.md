# DnsZtRuleNode::Release(void)

- ea: `0x180007674`
- end: `0x1800076af`
- name: `?Release@DnsZtRuleNode@@QEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(DnsZtRuleNode *this)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007490`
- `0x1800076b8`
- `0x1800110b8`
- `0x1800111cc`
- `0x180011548`
- `0x180011858`
- `0x1800126d8`
- `0x180012838`

## callees

- `0x180001518`
- `0x180007674`
- `0x180012690`

## pseudocode

```c
__int64 __fastcall DnsZtRuleNode::Release(DnsZtRuleNode *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this);
  if ( !v2 && this )
  {
    DnsZtRuleNode::~DnsZtRuleNode(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180007674  mov     [rsp+arg_0], rbx
0x180007679  push    rdi
0x18000767a  sub     rsp, 20h
0x18000767e  mov     rbx, rcx
0x180007681  or      edi, 0FFFFFFFFh
0x180007684  lock xadd [rcx], edi
0x180007688  sub     edi, 1
0x18000768b  jnz     short loc_1800076A2
0x18000768d  test    rcx, rcx
0x180007690  jz      short loc_1800076A2
0x180007692  call    ??1DnsZtRuleNode@@AEAA@XZ; DnsZtRuleNode::~DnsZtRuleNode(void)
0x180007697  lea     edx, [rdi+30h]; unsigned __int64
0x18000769a  mov     rcx, rbx; void *
0x18000769d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800076a2  mov     rbx, [rsp+28h+arg_0]
0x1800076a7  mov     eax, edi
0x1800076a9  add     rsp, 20h
0x1800076ad  pop     rdi
0x1800076ae  retn
```

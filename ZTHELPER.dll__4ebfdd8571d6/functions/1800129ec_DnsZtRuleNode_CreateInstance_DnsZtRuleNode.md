# DnsZtRuleNode::CreateInstance(DnsZtRuleNode * *)

- ea: `0x1800129ec`
- end: `0x180012a3d`
- name: `?CreateInstance@DnsZtRuleNode@@SAJPEAPEAV1@@Z`
- size: `81`
- prototype: `__int64 __fastcall(struct DnsZtRuleNode **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800126d8`
- `0x180012838`

## callees

- `0x1800014d4`
- `0x1800129ec`

## pseudocode

```c
__int64 __fastcall DnsZtRuleNode::CreateInstance(struct DnsZtRuleNode **a1)
{
  unsigned int v2; // edi
  struct DnsZtRuleNode *v3; // rax

  if ( a1 )
  {
    v2 = 0;
    *a1 = 0;
    v3 = (struct DnsZtRuleNode *)operator new(0x30u);
    *((_QWORD *)v3 + 5) = 0;
    *(_QWORD *)v3 = 1;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *a1 = v3;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x1800129ec  mov     [rsp+arg_0], rbx
0x1800129f1  push    rdi
0x1800129f2  sub     rsp, 20h
0x1800129f6  mov     rbx, rcx
0x1800129f9  test    rcx, rcx
0x1800129fc  jz      short loc_180012A2B
0x1800129fe  xor     edi, edi
0x180012a00  mov     [rcx], rdi
0x180012a03  lea     ecx, [rdi+30h]; Size
0x180012a06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012a0b  mov     [rax+28h], rdi
0x180012a0f  mov     qword ptr [rax], 1
0x180012a16  mov     [rax+8], rdi
0x180012a1a  mov     [rax+10h], rdi
0x180012a1e  mov     [rax+18h], rdi
0x180012a22  mov     [rax+20h], rdi
0x180012a26  mov     [rbx], rax
0x180012a29  jmp     short loc_180012A30
0x180012a2b  mov     edi, 80070057h
0x180012a30  mov     rbx, [rsp+28h+arg_0]
0x180012a35  mov     eax, edi
0x180012a37  add     rsp, 20h
0x180012a3b  pop     rdi
0x180012a3c  retn
```

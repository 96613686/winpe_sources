# XPathEvaluationContext::QueryContextNode(void)

- ea: `0x1800052bc`
- end: `0x1800052d9`
- name: `?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ`
- size: `29`
- prototype: `struct XPathNavigatorInternal *__fastcall(XPathEvaluationContext *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180005900`
- `0x18000b970`
- `0x18000ba20`
- `0x18000bb50`
- `0x18000bc00`
- `0x18000c040`
- `0x18000d7f0`
- `0x18000d8a0`

## callees

- `0x1800052bc`
- `0x180012010`

## pseudocode

```c
struct XPathNavigatorInternal *__fastcall XPathEvaluationContext::QueryContextNode(XPathEvaluationContext *this)
{
  __int64 v1; // rdx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
    return (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 72LL))(*((_QWORD *)this + 3));
  else
    return (XPathEvaluationContext *)((char *)this + 32);
}

```

## disassembly

```asm
0x1800052bc  mov     rdx, [rcx+18h]
0x1800052c0  test    rdx, rdx
0x1800052c3  jz      short loc_1800052D4
0x1800052c5  mov     rax, [rdx]
0x1800052c8  mov     rcx, rdx
0x1800052cb  mov     rax, [rax+48h]
0x1800052cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d4  lea     rax, [rcx+20h]
0x1800052d8  retn
```

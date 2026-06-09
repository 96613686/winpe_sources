# XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult(void)

- ea: `0x180006770`
- end: `0x18000678f`
- name: `??1QNameDispatchResult@XPathQueryStringCompiler@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(XPathQueryStringCompiler::QNameDispatchResult *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001dc0`
- `0x180009b1c`

## callees

- `0x180010fac`

## pseudocode

```c
void __fastcall XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult(
        XPathQueryStringCompiler::QNameDispatchResult *this)
{
  String::Reset((XPathQueryStringCompiler::QNameDispatchResult *)((char *)this + 8));
  String::Reset(this);
}

```

## disassembly

```asm
0x180006770  push    rbx
0x180006772  sub     rsp, 20h
0x180006776  mov     rbx, rcx
0x180006779  add     rcx, 8; this
0x18000677d  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x180006782  mov     rcx, rbx; this
0x180006785  add     rsp, 20h
0x180006789  pop     rbx
0x18000678a  jmp     ?Reset@String@@QEAAXXZ; String::Reset(void)
```

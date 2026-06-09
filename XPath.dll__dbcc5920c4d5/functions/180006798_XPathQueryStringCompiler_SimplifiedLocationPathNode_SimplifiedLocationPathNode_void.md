# XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(void)

- ea: `0x180006798`
- end: `0x1800067c0`
- name: `??1SimplifiedLocationPathNode@XPathQueryStringCompiler@@UEAA@XZ`
- size: `40`
- prototype: `void __fastcall(Node *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c50`
- `0x180009390`

## callees

- `0x1800066c0`
- `0x18000a240`

## pseudocode

```c
void __fastcall XPathQueryStringCompiler::SimplifiedLocationPathNode::~SimplifiedLocationPathNode(Node *this)
{
  InvasivePtr<Node>::Reset(&this[6]);
  InvasivePtr<Node>::Reset(&this[5]);
  Node::~Node(this);
}

```

## disassembly

```asm
0x180006798  push    rbx
0x18000679a  sub     rsp, 20h
0x18000679e  mov     rbx, rcx
0x1800067a1  add     rcx, 30h ; '0'
0x1800067a5  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x1800067aa  lea     rcx, [rbx+28h]
0x1800067ae  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x1800067b3  mov     rcx, rbx; this
0x1800067b6  add     rsp, 20h
0x1800067ba  pop     rbx
0x1800067bb  jmp     ??1Node@@UEAA@XZ; Node::~Node(void)
```

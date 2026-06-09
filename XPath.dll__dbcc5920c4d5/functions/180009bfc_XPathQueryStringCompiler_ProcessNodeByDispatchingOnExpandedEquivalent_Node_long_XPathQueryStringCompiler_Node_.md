# XPathQueryStringCompiler::ProcessNodeByDispatchingOnExpandedEquivalent(Node *,long (XPathQueryStringCompiler::*)(Node *,InvasivePtr<Node> &))

- ea: `0x180009bfc`
- end: `0x180009c51`
- name: `?ProcessNodeByDispatchingOnExpandedEquivalent@XPathQueryStringCompiler@@AEAAJPEAVNode@@P81@EAAJ0AEAV?$InvasivePtr@VNode@@@@@Z@Z`
- size: `85`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *this)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001a50`
- `0x180008eb0`
- `0x180008ed0`
- `0x180008ef0`

## callees

- `0x18000835c`
- `0x180009bfc`
- `0x18000a240`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNodeByDispatchingOnExpandedEquivalent(
        XPathQueryStringCompiler *this,
        __int64 a2,
        __int64 (__fastcall *a3)(XPathQueryStringCompiler *, __int64, struct Node **))
{
  int v4; // ebx
  struct Node *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v4 = a3(this, a2, &v6);
  if ( v4 >= 0 )
  {
    v4 = XPathQueryStringCompiler::Dispatch(this, v6);
    if ( v4 >= 0 )
      v4 = 0;
  }
  InvasivePtr<Node>::Reset(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009bfc  mov     [rsp+arg_0], rbx
0x180009c01  push    rdi
0x180009c02  sub     rsp, 20h
0x180009c06  mov     rax, r8
0x180009c09  mov     [rsp+28h+arg_10], 0
0x180009c12  lea     r8, [rsp+28h+arg_10]
0x180009c17  mov     rdi, rcx
0x180009c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c1f  mov     ebx, eax
0x180009c21  test    eax, eax
0x180009c23  js      short loc_180009C3A
0x180009c25  mov     rdx, [rsp+28h+arg_10]; struct Node *
0x180009c2a  mov     rcx, rdi; this
0x180009c2d  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180009c32  mov     ebx, eax
0x180009c34  test    eax, eax
0x180009c36  js      short loc_180009C3A
0x180009c38  xor     ebx, ebx
0x180009c3a  lea     rcx, [rsp+28h+arg_10]
0x180009c3f  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x180009c44  mov     eax, ebx
0x180009c46  mov     rbx, [rsp+28h+arg_0]
0x180009c4b  add     rsp, 20h
0x180009c4f  pop     rdi
0x180009c50  retn
```

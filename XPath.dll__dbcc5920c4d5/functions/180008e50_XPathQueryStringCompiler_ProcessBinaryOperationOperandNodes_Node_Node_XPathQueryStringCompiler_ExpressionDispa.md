# XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(Node *,Node *,XPathQueryStringCompiler::ExpressionDispatchResult &,XPathQueryStringCompiler::ExpressionDispatchResult &)

- ea: `0x180008e50`
- end: `0x180008ea3`
- name: `?ProcessBinaryOperationOperandNodes@XPathQueryStringCompiler@@AEAAJPEAVNode@@0AEAVExpressionDispatchResult@1@1@Z`
- size: `83`
- prototype: `__int64 __usercall@<rax>(XPathQueryStringCompiler *__hidden this@<rcx>, struct Node *@<rdx>, struct Node *@<r8>, struct XPathQueryStringCompiler::ExpressionDispatchResult *@<r9>, struct XPathQueryStringCompiler::ExpressionDispatchResult *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008d28`
- `0x180008dc4`
- `0x180008f04`

## callees

- `0x18000835c`
- `0x180008e50`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessBinaryOperationOperandNodes(
        XPathQueryStringCompiler *this,
        struct Node *a2,
        struct Node *a3,
        struct XPathQueryStringCompiler::ExpressionDispatchResult *a4,
        struct XPathQueryStringCompiler::ExpressionDispatchResult *a5)
{
  __int64 result; // rax
  int v8; // eax
  unsigned int v9; // ecx

  *((_DWORD *)this + 12) = 5;
  *((_QWORD *)this + 5) = a4;
  result = XPathQueryStringCompiler::Dispatch(this, a2);
  if ( (int)result >= 0 )
  {
    *((_QWORD *)this + 5) = a5;
    *((_DWORD *)this + 12) = 5;
    v8 = XPathQueryStringCompiler::Dispatch(this, a3);
    v9 = 0;
    if ( v8 < 0 )
      return (unsigned int)v8;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180008e50  mov     [rsp+arg_0], rbx
0x180008e55  push    rdi
0x180008e56  sub     rsp, 20h
0x180008e5a  mov     rdi, r8
0x180008e5d  mov     dword ptr [rcx+30h], 5
0x180008e64  mov     rbx, rcx
0x180008e67  mov     [rcx+28h], r9
0x180008e6b  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180008e70  test    eax, eax
0x180008e72  js      short loc_180008E98
0x180008e74  mov     rax, [rsp+28h+arg_20]
0x180008e79  mov     rdx, rdi; struct Node *
0x180008e7c  mov     rcx, rbx; this
0x180008e7f  mov     [rbx+28h], rax
0x180008e83  mov     dword ptr [rbx+30h], 5
0x180008e8a  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180008e8f  xor     ecx, ecx
0x180008e91  test    eax, eax
0x180008e93  cmovs   ecx, eax
0x180008e96  mov     eax, ecx
0x180008e98  mov     rbx, [rsp+28h+arg_0]
0x180008e9d  add     rsp, 20h
0x180008ea1  pop     rdi
0x180008ea2  retn
```

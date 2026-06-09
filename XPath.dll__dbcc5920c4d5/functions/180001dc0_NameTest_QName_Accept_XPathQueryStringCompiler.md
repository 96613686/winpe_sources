# NameTest__QName::Accept(XPathQueryStringCompiler *)

- ea: `0x180001dc0`
- end: `0x180001e49`
- name: `?Accept@NameTest__QName@@UEAAJPEAVXPathQueryStringCompiler@@@Z`
- size: `137`
- prototype: `int(NameTest__QName *__hidden this, struct XPathQueryStringCompiler *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180006770`
- `0x1800068d8`
- `0x18000835c`

## pseudocode

```c
__int64 __fastcall NameTest__QName::Accept(NameTest__QName *this, struct XPathQueryStringCompiler *a2)
{
  __int64 v2; // rbx
  _DWORD *v4; // rsi
  struct Node *v5; // rdx
  int v6; // edi
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v2 = *((_QWORD *)a2 + 5);
  v4 = (_DWORD *)*((_QWORD *)a2 + 3);
  *((_QWORD *)a2 + 3) = 0;
  *((_DWORD *)a2 + 12) = 8;
  *((_QWORD *)a2 + 5) = &v8;
  v5 = (struct Node *)*((_QWORD *)this + 2);
  v8 = 0;
  v6 = XPathQueryStringCompiler::Dispatch(a2, v5);
  if ( v6 >= 0 )
  {
    String::operator=(v2, &v8);
    String::operator=(v2 + 8, (char *)&v8 + 8);
    *(_DWORD *)(v2 + 16) = *v4;
  }
  XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult((XPathQueryStringCompiler::QNameDispatchResult *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001dc0  mov     [rsp+arg_0], rbx
0x180001dc5  mov     [rsp+arg_8], rsi
0x180001dca  push    rdi
0x180001dcb  sub     rsp, 30h
0x180001dcf  mov     rbx, [rdx+28h]
0x180001dd3  mov     rax, rdx
0x180001dd6  mov     rsi, [rdx+18h]
0x180001dda  xorps   xmm0, xmm0
0x180001ddd  mov     qword ptr [rdx+18h], 0
0x180001de5  mov     dword ptr [rdx+30h], 8
0x180001dec  lea     rdx, [rsp+38h+var_18]
0x180001df1  mov     [rax+28h], rdx
0x180001df5  mov     rdx, [rcx+10h]; struct Node *
0x180001df9  mov     rcx, rax; this
0x180001dfc  movdqu  [rsp+38h+var_18], xmm0
0x180001e02  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180001e07  mov     edi, eax
0x180001e09  test    eax, eax
0x180001e0b  js      short loc_180001E2D
0x180001e0d  lea     rdx, [rsp+38h+var_18]
0x180001e12  mov     rcx, rbx
0x180001e15  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180001e1a  lea     rcx, [rbx+8]
0x180001e1e  lea     rdx, [rsp+38h+var_18+8]
0x180001e23  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180001e28  mov     ecx, [rsi]
0x180001e2a  mov     [rbx+10h], ecx
0x180001e2d  lea     rcx, [rsp+38h+var_18]; this
0x180001e32  call    ??1QNameDispatchResult@XPathQueryStringCompiler@@QEAA@XZ; XPathQueryStringCompiler::QNameDispatchResult::~QNameDispatchResult(void)
0x180001e37  mov     rbx, [rsp+38h+arg_0]
0x180001e3c  mov     eax, edi
0x180001e3e  mov     rsi, [rsp+38h+arg_8]
0x180001e43  add     rsp, 30h
0x180001e47  pop     rdi
0x180001e48  retn
```

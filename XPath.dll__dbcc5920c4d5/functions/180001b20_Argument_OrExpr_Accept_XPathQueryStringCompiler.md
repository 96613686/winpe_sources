# Argument__OrExpr::Accept(XPathQueryStringCompiler *)

- ea: `0x180001b20`
- end: `0x180001bb2`
- name: `?Accept@Argument__OrExpr@@UEAAJPEAVXPathQueryStringCompiler@@@Z`
- size: `146`
- prototype: `int(Argument__OrExpr *__hidden this, struct XPathQueryStringCompiler *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001b20`
- `0x1800020b4`
- `0x180004aac`
- `0x180004c30`
- `0x18000835c`
- `0x180008c24`

## pseudocode

```c
__int64 __fastcall Argument__OrExpr::Accept(struct Node **this, struct XPathQueryStringCompiler *a2)
{
  unsigned int *v2; // rsi
  int IteratorCompleteIfNecessary; // ebx
  struct IUnknown *v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = (unsigned int *)*((_QWORD *)a2 + 5);
  *((_DWORD *)a2 + 12) = 5;
  v5 = 0;
  *((_QWORD *)a2 + 5) = &v5;
  IteratorCompleteIfNecessary = XPathQueryStringCompiler::Dispatch(a2, this[2]);
  if ( IteratorCompleteIfNecessary >= 0 )
  {
    if ( *v2 <= v2[6]
      || (IteratorCompleteIfNecessary = List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(
                                          (__int64)(v2 + 2),
                                          *v2),
          IteratorCompleteIfNecessary >= 0) )
    {
      IteratorCompleteIfNecessary = XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(&v5);
      if ( IteratorCompleteIfNecessary >= 0 )
        IteratorCompleteIfNecessary = List<ATL::CComPtr<XPathExpressionBase>>::Append((__int64)(v2 + 2), &v5);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v5);
  return (unsigned int)IteratorCompleteIfNecessary;
}

```

## disassembly

```asm
0x180001b20  mov     r11, rsp
0x180001b23  mov     [r11+10h], rbx
0x180001b27  mov     [r11+18h], rsi
0x180001b2b  push    rdi
0x180001b2c  sub     rsp, 20h
0x180001b30  mov     rsi, [rdx+28h]
0x180001b34  mov     rax, rdx
0x180001b37  mov     dword ptr [rdx+30h], 5
0x180001b3e  lea     rdx, [r11+8]
0x180001b42  mov     qword ptr [r11+8], 0
0x180001b4a  mov     [rax+28h], rdx
0x180001b4e  mov     rdx, [rcx+10h]; struct Node *
0x180001b52  mov     rcx, rax; this
0x180001b55  call    ?Dispatch@XPathQueryStringCompiler@@QEAAJPEAVNode@@@Z; XPathQueryStringCompiler::Dispatch(Node *)
0x180001b5a  mov     ebx, eax
0x180001b5c  test    eax, eax
0x180001b5e  js      short loc_180001B96
0x180001b60  mov     edx, [rsi]
0x180001b62  cmp     edx, [rsi+18h]
0x180001b65  jbe     short loc_180001B76
0x180001b67  lea     rcx, [rsi+8]
0x180001b6b  call    ?CloneBackingStore@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@AEAAJK@Z; List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(ulong)
0x180001b70  mov     ebx, eax
0x180001b72  test    eax, eax
0x180001b74  js      short loc_180001B96
0x180001b76  lea     rcx, [rsp+28h+arg_0]; struct IUnknown **
0x180001b7b  call    ?MakeIteratorCompleteIfNecessary@XPathQueryStringCompiler@@CAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; XPathQueryStringCompiler::MakeIteratorCompleteIfNecessary(ATL::CComPtr<XPathExpressionBase> &)
0x180001b80  mov     ebx, eax
0x180001b82  test    eax, eax
0x180001b84  js      short loc_180001B96
0x180001b86  lea     rdx, [rsp+28h+arg_0]
0x180001b8b  lea     rcx, [rsi+8]
0x180001b8f  call    ?Append@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z; List<ATL::CComPtr<XPathExpressionBase>>::Append(ATL::CComPtr<XPathExpressionBase> &)
0x180001b94  mov     ebx, eax
0x180001b96  lea     rcx, [rsp+28h+arg_0]
0x180001b9b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180001ba0  mov     rsi, [rsp+28h+arg_10]
0x180001ba5  mov     eax, ebx
0x180001ba7  mov     rbx, [rsp+28h+arg_8]
0x180001bac  add     rsp, 20h
0x180001bb0  pop     rdi
0x180001bb1  retn
```

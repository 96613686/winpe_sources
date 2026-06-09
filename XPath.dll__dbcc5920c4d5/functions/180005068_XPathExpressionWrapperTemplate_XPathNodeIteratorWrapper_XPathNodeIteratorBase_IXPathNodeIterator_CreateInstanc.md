# XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::CreateInstance(IXPathNodeIterator *,XPathExpressionBase * *)

- ea: `0x180005068`
- end: `0x18000511c`
- name: `?CreateInstance@?$XPathExpressionWrapperTemplate@VXPathNodeIteratorWrapper@@VXPathNodeIteratorBase@@UIXPathNodeIterator@@@@SAJPEAUIXPathNodeIterator@@PEAPEAVXPathExpressionBase@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004d24`

## callees

- `0x180001078`
- `0x1800032f4`
- `0x180004b84`
- `0x180005068`

## pseudocode

```c
__int64 __fastcall XPathExpressionWrapperTemplate<XPathNodeIteratorWrapper,XPathNodeIteratorBase,IXPathNodeIterator>::CreateInstance(
        struct IUnknown *a1,
        unsigned __int64 *a2)
{
  void *v4; // rbx

  v4 = operator new(0x38u);
  if ( !v4 )
    return 2147942414LL;
  *(_OWORD *)v4 = 0;
  *((_OWORD *)v4 + 1) = 0;
  *((_OWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 6) = 0;
  XPathNodeIteratorBase::XPathNodeIteratorBase((XPathNodeIteratorBase *)v4);
  *((_QWORD *)v4 + 3) = 0;
  *(_QWORD *)v4 = &XPathNodeIteratorWrapper::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v4 + 1) = &XPathNodeIteratorWrapper::`vftable'{for `XPathExpressionBase'};
  *((_QWORD *)v4 + 4) = 0;
  *((_DWORD *)v4 + 10) = 0;
  *((_DWORD *)v4 + 11) = 7;
  *((_BYTE *)v4 + 48) = 0;
  if ( *((struct IUnknown **)v4 + 3) != a1 )
    ATL::AtlComPtrAssign((struct IUnknown **)v4 + 3, a1);
  *a2 = ((unsigned __int64)v4 + 8) & -(__int64)(v4 != 0);
  return 0;
}

```

## disassembly

```asm
0x180005068  mov     [rsp+arg_0], rbx
0x18000506d  mov     [rsp+arg_8], rsi
0x180005072  push    rdi
0x180005073  sub     rsp, 20h
0x180005077  mov     rdi, rcx
0x18000507a  mov     rsi, rdx
0x18000507d  mov     ecx, 38h ; '8'; Size
0x180005082  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005087  mov     rbx, rax
0x18000508a  test    rax, rax
0x18000508d  jz      short loc_180005107
0x18000508f  xorps   xmm0, xmm0
0x180005092  xor     eax, eax
0x180005094  movups  xmmword ptr [rbx], xmm0
0x180005097  mov     rcx, rbx; this
0x18000509a  movups  xmmword ptr [rbx+10h], xmm0
0x18000509e  movups  xmmword ptr [rbx+20h], xmm0
0x1800050a2  mov     [rbx+30h], rax
0x1800050a6  call    ??0XPathNodeIteratorBase@@QEAA@XZ; XPathNodeIteratorBase::XPathNodeIteratorBase(void)
0x1800050ab  mov     qword ptr [rbx+18h], 0
0x1800050b3  lea     rax, ??_7XPathNodeIteratorWrapper@@6BIXPathNodeIterator@@@; const XPathNodeIteratorWrapper::`vftable'{for `IXPathNodeIterator'}
0x1800050ba  mov     [rbx], rax
0x1800050bd  lea     rcx, [rbx+18h]; struct IUnknown **
0x1800050c1  lea     rax, ??_7XPathNodeIteratorWrapper@@6BXPathExpressionBase@@@; const XPathNodeIteratorWrapper::`vftable'{for `XPathExpressionBase'}
0x1800050c8  mov     [rbx+8], rax
0x1800050cc  mov     qword ptr [rbx+20h], 0
0x1800050d4  mov     dword ptr [rbx+28h], 0
0x1800050db  mov     dword ptr [rbx+2Ch], 7
0x1800050e2  mov     byte ptr [rbx+30h], 0
0x1800050e6  cmp     [rcx], rdi
0x1800050e9  jz      short loc_1800050F3
0x1800050eb  mov     rdx, rdi; struct IUnknown *
0x1800050ee  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800050f3  lea     rcx, [rbx+8]
0x1800050f7  neg     rbx
0x1800050fa  sbb     rax, rax
0x1800050fd  and     rax, rcx
0x180005100  mov     [rsi], rax
0x180005103  xor     eax, eax
0x180005105  jmp     short loc_18000510C
0x180005107  mov     eax, 8007000Eh
0x18000510c  mov     rbx, [rsp+28h+arg_0]
0x180005111  mov     rsi, [rsp+28h+arg_8]
0x180005116  add     rsp, 20h
0x18000511a  pop     rdi
0x18000511b  retn
```
